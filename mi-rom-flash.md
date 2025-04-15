# 小米刷机

以 redmi note 11tpro+ 为例，使用线刷的方式：

1. 解 BL
2. 在 **设置 - 关于手机 - 全部信息 - MIUI 版本**，找到对应的 rom 版本，例如 `13.2.2.0(TLOEUXM)`，就到 [这里](https://xiaomirom.com/series/) 找到对应手机的对应版本 `13.2.2.0(TLOEUXM)` 下载完整 rom，得到 tgz 文件
3. 解压 tgz、tar，得到一个包含 `images`、`flash_all.sh`、`flash.bat` 文件的文件夹
4. 手机连接 adb
5. 进入到上面的文件夹，执行 `flash_all.sh` 或 `flash.bat`
6. 刷写完成后开机要等一会

如果发现手机 fastboot 没动静未响应，可以试试：

1. 换线，比如原装数据线
2. 适用 USB 2.0 接口
3. 手机进入 fastboot（bootloader） 模式，在插上线一瞬间，pc 端输入 `fastboot getvar product`，有回显说明 fastboot 功能其实是好的，那就拔掉再来一次：插上线一瞬间，执行 `./flash_all.sh` 或 `./flash_all.bat`

> 完整刷写参考

```bash
$ ./flash_all.sh
product: xagapro
crc: 1
Warning: skip copying crclist image avb footer (crclist partition size: 0, crclist image size: 521).
Sending 'crclist' (0 KB)                           OKAY [  0.010s]
Writing 'crclist'                                  OKAY [  0.019s]
Finished. Total time: 0.095s
Warning: skip copying sparsecrclist image avb footer (sparsecrclist partition size: 0, sparsecrclist image size: 421).
Sending 'sparsecrclist' (0 KB)                     OKAY [  0.010s]
Writing 'sparsecrclist'                            OKAY [  0.019s]
Finished. Total time: 0.096s
Erasing 'boot_ab'                                  OKAY [  0.019s]
Finished. Total time: 0.038s
Erasing 'expdb'                                    OKAY [  0.020s]
Finished. Total time: 0.040s
Erasing 'metadata'                                 OKAY [  0.020s]
Finished. Total time: 0.040s
Warning: skip copying preloader1 image avb footer (preloader1 partition size: 0, preloader1 image size: 479680).
Sending 'preloader1' (468 KB)                      OKAY [  0.030s]
Writing 'preloader1'                               OKAY [  0.024s]
Finished. Total time: 0.113s
Warning: skip copying preloader2 image avb footer (preloader2 partition size: 0, preloader2 image size: 479680).
Sending 'preloader2' (468 KB)                      OKAY [  0.023s]
Writing 'preloader2'                               OKAY [  0.024s]
Finished. Total time: 0.106s
Warning: skip copying vbmeta_ab image avb footer (vbmeta_ab partition size: 0, vbmeta_ab image size: 8192).
Sending 'vbmeta_ab' (8 KB)                         OKAY [  0.011s]
Writing 'vbmeta_ab'                                OKAY [  0.019s]
Finished. Total time: 0.095s
Warning: skip copying vbmeta_system_ab image avb footer (vbmeta_system_ab partition size: 0, vbmeta_system_ab image size: 4096).
Sending 'vbmeta_system_ab' (4 KB)                  OKAY [  0.010s]
Writing 'vbmeta_system_ab'                         OKAY [  0.019s]
Finished. Total time: 0.096s
Warning: skip copying vbmeta_vendor_ab image avb footer (vbmeta_vendor_ab partition size: 0, vbmeta_vendor_ab image size: 4096).
Sending 'vbmeta_vendor_ab' (4 KB)                  OKAY [  0.010s]
Writing 'vbmeta_vendor_ab'                         OKAY [  0.019s]
Finished. Total time: 0.089s
Warning: skip copying md1img_ab image avb footer (md1img_ab partition size: 0, md1img_ab image size: 76670656).
Sending 'md1img_ab' (74873 KB)                     OKAY [  2.079s]
Writing 'md1img_ab'                                OKAY [  0.451s]
Finished. Total time: 2.596s
Warning: skip copying spmfw_ab image avb footer (spmfw_ab partition size: 0, spmfw_ab image size: 18144).
Sending 'spmfw_ab' (17 KB)                         OKAY [  0.011s]
Writing 'spmfw_ab'                                 OKAY [  0.019s]
Finished. Total time: 0.089s
Warning: skip copying mcf_ota_ab image avb footer (mcf_ota_ab partition size: 0, mcf_ota_ab image size: 3407872).
Sending 'mcf_ota_ab' (3328 KB)                     OKAY [  0.103s]
Writing 'mcf_ota_ab'                               OKAY [  0.039s]
Finished. Total time: 0.208s
Warning: skip copying audio_dsp_ab image avb footer (audio_dsp_ab partition size: 0, audio_dsp_ab image size: 5516000).
Sending 'audio_dsp_ab' (5386 KB)                   OKAY [  0.160s]
Writing 'audio_dsp_ab'                             OKAY [  0.051s]
Finished. Total time: 0.276s
Warning: skip copying pi_img_ab image avb footer (pi_img_ab partition size: 0, pi_img_ab image size: 5136).
Sending 'pi_img_ab' (5 KB)                         OKAY [  0.010s]
Writing 'pi_img_ab'                                OKAY [  0.019s]
Finished. Total time: 0.088s
Warning: skip copying dpm_ab image avb footer (dpm_ab partition size: 0, dpm_ab image size: 264032).
Sending 'dpm_ab' (257 KB)                          OKAY [  0.017s]
Writing 'dpm_ab'                                   OKAY [  0.022s]
Finished. Total time: 0.105s
Warning: skip copying scp_ab image avb footer (scp_ab partition size: 0, scp_ab image size: 2168448).
Sending 'scp_ab' (2117 KB)                         OKAY [  0.069s]
Writing 'scp_ab'                                   OKAY [  0.032s]
Finished. Total time: 0.167s
Warning: skip copying ccu_ab image avb footer (ccu_ab partition size: 0, ccu_ab image size: 176080).
Sending 'ccu_ab' (171 KB)                          OKAY [  0.016s]
Writing 'ccu_ab'                                   OKAY [  0.021s]
Finished. Total time: 0.103s
Warning: skip copying vcp_ab image avb footer (vcp_ab partition size: 0, vcp_ab image size: 1586480).
Sending 'vcp_ab' (1549 KB)                         OKAY [  0.053s]
Writing 'vcp_ab'                                   OKAY [  0.029s]
Finished. Total time: 0.149s
Warning: skip copying sspm_ab image avb footer (sspm_ab partition size: 0, sspm_ab image size: 998848).
Sending 'sspm_ab' (975 KB)                         OKAY [  0.038s]
Writing 'sspm_ab'                                  OKAY [  0.027s]
Finished. Total time: 0.131s
Warning: skip copying mcupm_ab image avb footer (mcupm_ab partition size: 0, mcupm_ab image size: 628080).
Sending 'mcupm_ab' (613 KB)                        OKAY [  0.027s]
Writing 'mcupm_ab'                                 OKAY [  0.024s]
Finished. Total time: 0.116s
Warning: skip copying gpueb_ab image avb footer (gpueb_ab partition size: 0, gpueb_ab image size: 129952).
Sending 'gpueb_ab' (126 KB)                        OKAY [  0.014s]
Writing 'gpueb_ab'                                 OKAY [  0.021s]
Finished. Total time: 0.102s
Warning: skip copying apusys_ab image avb footer (apusys_ab partition size: 0, apusys_ab image size: 1402672).
Sending 'apusys_ab' (1369 KB)                      OKAY [  0.048s]
Writing 'apusys_ab'                                OKAY [  0.028s]
Finished. Total time: 0.143s
Warning: skip copying mvpu_algo_ab image avb footer (mvpu_algo_ab partition size: 0, mvpu_algo_ab image size: 59488).
Sending 'mvpu_algo_ab' (58 KB)                     OKAY [  0.012s]
Writing 'mvpu_algo_ab'                             OKAY [  0.020s]
Finished. Total time: 0.098s
Warning: skip copying gz_ab image avb footer (gz_ab partition size: 0, gz_ab image size: 2029104).
Sending 'gz_ab' (1981 KB)                          OKAY [  0.066s]
Writing 'gz_ab'                                    OKAY [  0.032s]
Finished. Total time: 0.164s
Warning: skip copying lk_ab image avb footer (lk_ab partition size: 0, lk_ab image size: 2997568).
Sending 'lk_ab' (2927 KB)                          OKAY [  0.092s]
Writing 'lk_ab'                                    OKAY [  0.037s]
Finished. Total time: 0.195s
Warning: skip copying vendor_boot_ab image avb footer (vendor_boot_ab partition size: 0, vendor_boot_ab image size: 67108864).
Sending 'vendor_boot_ab' (65536 KB)                OKAY [  1.820s]
Writing 'vendor_boot_ab'                           OKAY [  0.434s]
Finished. Total time: 2.320s
Warning: skip copying dtbo_ab image avb footer (dtbo_ab partition size: 0, dtbo_ab image size: 33554432).
Sending 'dtbo_ab' (32768 KB)                       OKAY [  0.911s]
Writing 'dtbo_ab'                                  OKAY [  0.087s]
Finished. Total time: 1.071s
Warning: skip copying tee_ab image avb footer (tee_ab partition size: 0, tee_ab image size: 3487472).
Sending 'tee_ab' (3405 KB)                         OKAY [  0.103s]
Writing 'tee_ab'                                   OKAY [  0.040s]
Finished. Total time: 0.207s
Warning: skip copying logo_ab image avb footer (logo_ab partition size: 0, logo_ab image size: 3425792).
Sending 'logo_ab' (3345 KB)                        OKAY [  0.107s]
Writing 'logo_ab'                                  OKAY [  0.040s]
Finished. Total time: 0.204s
Sending sparse 'super' 1/26 (262140 KB)            OKAY [  7.250s]
Writing 'super'                                    OKAY [  1.675s]
Sending sparse 'super' 2/26 (262140 KB)            OKAY [  7.249s]
Writing 'super'                                    OKAY [  1.518s]
Sending sparse 'super' 3/26 (262140 KB)            OKAY [  7.259s]
Writing 'super'                                    OKAY [  1.545s]
Sending sparse 'super' 4/26 (262140 KB)            OKAY [  7.241s]
Writing 'super'                                    OKAY [  1.587s]
Sending sparse 'super' 5/26 (262140 KB)            OKAY [  7.252s]
Writing 'super'                                    OKAY [  1.520s]
Sending sparse 'super' 6/26 (262140 KB)            OKAY [  7.262s]
Writing 'super'                                    OKAY [  1.546s]
Sending sparse 'super' 7/26 (262140 KB)            OKAY [  7.258s]
Writing 'super'                                    OKAY [  1.563s]
Sending sparse 'super' 8/26 (262140 KB)            OKAY [  7.256s]
Writing 'super'                                    OKAY [  1.524s]
Sending sparse 'super' 9/26 (262140 KB)            OKAY [  7.260s]
Writing 'super'                                    OKAY [  1.573s]
Sending sparse 'super' 10/26 (262140 KB)           OKAY [  7.260s]
Writing 'super'                                    OKAY [  1.565s]
Sending sparse 'super' 11/26 (262140 KB)           OKAY [  7.254s]
Writing 'super'                                    OKAY [  1.524s]
Sending sparse 'super' 12/26 (262140 KB)           OKAY [  7.264s]
Writing 'super'                                    OKAY [  1.546s]
Sending sparse 'super' 13/26 (262140 KB)           OKAY [  7.164s]
Writing 'super'                                    OKAY [  1.624s]
Sending sparse 'super' 14/26 (262140 KB)           OKAY [  7.157s]
Writing 'super'                                    OKAY [  1.547s]
Sending sparse 'super' 15/26 (262140 KB)           OKAY [  7.153s]
Writing 'super'                                    OKAY [  1.550s]
Sending sparse 'super' 16/26 (261868 KB)           OKAY [  6.964s]
Writing 'super'                                    OKAY [  1.580s]
Sending sparse 'super' 17/26 (249560 KB)           OKAY [  6.713s]
Writing 'super'                                    OKAY [  1.456s]
Sending sparse 'super' 18/26 (262140 KB)           OKAY [  7.247s]
Writing 'super'                                    OKAY [  1.557s]
Sending sparse 'super' 19/26 (262140 KB)           OKAY [  7.268s]
Writing 'super'                                    OKAY [  1.587s]
Sending sparse 'super' 20/26 (262140 KB)           OKAY [  7.293s]
Writing 'super'                                    OKAY [  1.520s]
Sending sparse 'super' 21/26 (262140 KB)           OKAY [  7.275s]
Writing 'super'                                    OKAY [  1.552s]
Sending sparse 'super' 22/26 (262140 KB)           OKAY [  7.261s]
Writing 'super'                                    OKAY [  1.655s]
Sending sparse 'super' 23/26 (262140 KB)           OKAY [  7.230s]
Writing 'super'                                    OKAY [  1.555s]
Sending sparse 'super' 24/26 (239292 KB)           OKAY [  6.603s]
Writing 'super'                                    OKAY [  1.426s]
Sending sparse 'super' 25/26 (243704 KB)           OKAY [  6.747s]
Writing 'super'                                    OKAY [  1.502s]
Sending sparse 'super' 26/26 (126140 KB)           OKAY [  3.505s]
Writing 'super'                                    OKAY [  0.843s]
Finished. Total time: 222.358s
Warning: skip copying rescue image avb footer due to sparse image.
Sending 'rescue' (40 KB)                           OKAY [  0.011s]
Writing 'rescue'                                   OKAY [  0.019s]
Finished. Total time: 0.078s
Sending sparse 'cust' 1/6 (258644 KB)              OKAY [  7.174s]
Writing 'cust'                                     OKAY [  1.544s]
Sending sparse 'cust' 2/6 (258040 KB)              OKAY [  7.146s]
Writing 'cust'                                     OKAY [  1.523s]
Sending sparse 'cust' 3/6 (258040 KB)              OKAY [  7.150s]
Writing 'cust'                                     OKAY [  1.524s]
Sending sparse 'cust' 4/6 (258044 KB)              OKAY [  7.152s]
Writing 'cust'                                     OKAY [  1.541s]
Sending sparse 'cust' 5/6 (258040 KB)              OKAY [  7.165s]
Writing 'cust'                                     OKAY [  1.497s]
Sending sparse 'cust' 6/6 (253996 KB)              OKAY [  7.053s]
Writing 'cust'                                     OKAY [  1.499s]
Finished. Total time: 52.007s
Warning: skip copying userdata image avb footer due to sparse image.
Sending 'userdata' (2300 KB)                       OKAY [  0.074s]
Writing 'userdata'                                 OKAY [  0.157s]
Finished. Total time: 0.279s
Warning: skip copying boot_ab image avb footer (boot_ab partition size: 0, boot_ab image size: 67108864).
Sending 'boot_ab' (65536 KB)                       OKAY [  1.818s]
Writing 'boot_ab'                                  OKAY [  0.428s]
Finished. Total time: 2.312s
OKAY [  0.023s]
Finished. Total time: 0.023s
Setting current slot to 'a'                        OKAY [  0.010s]
Finished. Total time: 0.020s
Rebooting                                          OKAY [  0.010s]
Finished. Total time: 0.111s
```

