# DOProcessGroupPolicy(ulong,void *,HKEY__ *,_GROUP_POLICY_OBJECTA *,_GROUP_POLICY_OBJECTA *,unsigned __int64,int *,ulong (*)(int,ushort *))

- ea: `0x18000bbd0`
- end: `0x18000bcfb`
- name: `?DOProcessGroupPolicy@@YAKKPEAXPEAUHKEY__@@PEAU_GROUP_POLICY_OBJECTA@@2_KPEAHP6AKHPEAG@Z@Z`
- size: `299`
- prototype: `__int64 __fastcall(__int64, void *, HKEY, struct _GROUP_POLICY_OBJECTA *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001ba0`
- `0x18000badc`
- `0x18000bb54`
- `0x18000bbd0`
- `0x18000bd84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x18000bc5f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x18000bce1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x18000bc5f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x18000bce1`

## pseudocode

```c
__int64 __fastcall DOProcessGroupPolicy(__int64 a1, void *a2, HKEY a3, struct _GROUP_POLICY_OBJECTA *a4)
{
  if ( (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_1___("DOSetHoursToLimitBackgroundDownloadBandwidth_From") < 0
    || (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_1___("DOSetHoursToLimitBackgroundDownloadBandwidth_To") < 0
    || (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_2___("DOSetHoursToLimitBackgroundDownloadBandwidth_In") < 0
    || (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_2___("DOSetHoursToLimitBackgroundDownloadBandwidth_Out") < 0 )
  {
    RegDeleteKeyValueA(
      HKEY_LOCAL_MACHINE,
      "SOFTWARE\\Policies\\Microsoft\\Windows\\DeliveryOptimization",
      "DOSetHoursToLimitBackgroundDownloadBandwidth");
  }
  else
  {
    ApplySetHoursToLimitDownloadBandwidthXml("DOSetHoursToLimitBackgroundDownloadBandwidth");
  }
  if ( (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_1___("DOSetHoursToLimitForegroundDownloadBandwidth_From") < 0
    || (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_1___("DOSetHoursToLimitForegroundDownloadBandwidth_To") < 0
    || (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_2___("DOSetHoursToLimitForegroundDownloadBandwidth_In") < 0
    || (int)GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth_::_2_::_lambda_2___("DOSetHoursToLimitForegroundDownloadBandwidth_Out") < 0 )
  {
    RegDeleteKeyValueA(
      HKEY_LOCAL_MACHINE,
      "SOFTWARE\\Policies\\Microsoft\\Windows\\DeliveryOptimization",
      "DOSetHoursToLimitForegroundDownloadBandwidth");
  }
  else
  {
    ApplySetHoursToLimitDownloadBandwidthXml("DOSetHoursToLimitForegroundDownloadBandwidth");
  }
  return 0;
}

```

## disassembly

```asm
0x18000bbd0  sub     rsp, 48h
0x18000bbd4  mov     rax, cs:__security_cookie
0x18000bbdb  xor     rax, rsp
0x18000bbde  mov     [rsp+48h+var_18], rax
0x18000bbe3  lea     rdx, [rsp+48h+var_28]
0x18000bbe8  lea     rcx, aDosethourstoli_0; "DOSetHoursToLimitBackgroundDownloadBand"...
0x18000bbef  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_1___
0x18000bbf4  test    eax, eax
0x18000bbf6  js      short loc_18000BC4A
0x18000bbf8  lea     rdx, [rsp+48h+var_24]
0x18000bbfd  lea     rcx, aDosethourstoli_2; "DOSetHoursToLimitBackgroundDownloadBand"...
0x18000bc04  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_1___
0x18000bc09  test    eax, eax
0x18000bc0b  js      short loc_18000BC4A
0x18000bc0d  lea     rdx, [rsp+48h+var_20]
0x18000bc12  lea     rcx, aDosethourstoli_6; "DOSetHoursToLimitBackgroundDownloadBand"...
0x18000bc19  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_2___
0x18000bc1e  test    eax, eax
0x18000bc20  js      short loc_18000BC4A
0x18000bc22  lea     rdx, [rsp+48h+var_1C]
0x18000bc27  lea     rcx, aDosethourstoli_7; "DOSetHoursToLimitBackgroundDownloadBand"...
0x18000bc2e  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_2___
0x18000bc33  test    eax, eax
0x18000bc35  js      short loc_18000BC4A
0x18000bc37  lea     rdx, [rsp+48h+var_28]
0x18000bc3c  lea     rcx, ValueName; "DOSetHoursToLimitBackgroundDownloadBand"...
0x18000bc43  call    _ApplySetHoursToLimitDownloadBandwidthXml
0x18000bc48  jmp     short loc_18000BC65
0x18000bc4a  lea     r8, ValueName; "DOSetHoursToLimitBackgroundDownloadBand"...
0x18000bc51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc58  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000bc5f  call    cs:__imp_RegDeleteKeyValueA
0x18000bc65  lea     rdx, [rsp+48h+var_28]
0x18000bc6a  lea     rcx, aDosethourstoli_5; "DOSetHoursToLimitForegroundDownloadBand"...
0x18000bc71  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_1___
0x18000bc76  test    eax, eax
0x18000bc78  js      short loc_18000BCCC
0x18000bc7a  lea     rdx, [rsp+48h+var_24]
0x18000bc7f  lea     rcx, aDosethourstoli_1; "DOSetHoursToLimitForegroundDownloadBand"...
0x18000bc86  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_1___
0x18000bc8b  test    eax, eax
0x18000bc8d  js      short loc_18000BCCC
0x18000bc8f  lea     rdx, [rsp+48h+var_20]
0x18000bc94  lea     rcx, aDosethourstoli_4; "DOSetHoursToLimitForegroundDownloadBand"...
0x18000bc9b  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_2___
0x18000bca0  test    eax, eax
0x18000bca2  js      short loc_18000BCCC
0x18000bca4  lea     rdx, [rsp+48h+var_1C]
0x18000bca9  lea     rcx, aDosethourstoli_3; "DOSetHoursToLimitForegroundDownloadBand"...
0x18000bcb0  call    _GetAndValidatePolicy___ProcessSetHoursToLimitDownloadBandwidth____2____lambda_2___
0x18000bcb5  test    eax, eax
0x18000bcb7  js      short loc_18000BCCC
0x18000bcb9  lea     rdx, [rsp+48h+var_28]
0x18000bcbe  lea     rcx, aDosethourstoli; "DOSetHoursToLimitForegroundDownloadBand"...
0x18000bcc5  call    _ApplySetHoursToLimitDownloadBandwidthXml
0x18000bcca  jmp     short loc_18000BCE7
0x18000bccc  lea     r8, aDosethourstoli; "DOSetHoursToLimitForegroundDownloadBand"...
0x18000bcd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bcda  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000bce1  call    cs:__imp_RegDeleteKeyValueA
0x18000bce7  xor     eax, eax
0x18000bce9  mov     rcx, [rsp+48h+var_18]
0x18000bcee  xor     rcx, rsp; StackCookie
0x18000bcf1  call    __security_check_cookie
0x18000bcf6  add     rsp, 48h
0x18000bcfa  retn
```
