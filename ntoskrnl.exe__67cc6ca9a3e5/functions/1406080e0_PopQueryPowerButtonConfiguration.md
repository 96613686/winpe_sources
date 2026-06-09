# PopQueryPowerButtonConfiguration

- ea: `0x1406080e0`
- end: `0x1406083f5`
- name: `PopQueryPowerButtonConfiguration`
- size: `789`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1407998a4`

## callees

- `0x14020fe90`
- `0x1403f2d50`
- `0x1406080e0`
- `0x1406d9d70`
- `0x1406dab70`

## string_xrefs

- `0x140608255`: `PopQueryPowerButtonConfiguration`
- `0x140608347`: `PopQueryPowerButtonConfiguration`
- `0x1406083a8`: `PopQueryPowerButtonConfiguration`
- `0x140608352`: `%s (LiveDump) completed with Status: %08x, ManualLiveDumpConfig %08x, OneSettingLiveDumpConfig: %08x\n`
- `0x140608260`: `%s (Bugcheck) completed with Status: %08x, ManualBugcheckConfig: %08x, OneSettingBugcheckConfig: %08x\n`
- `0x1406083b3`: `%s completed with settings: PopPowerButtonBugcheckConfig: %08x, PopPowerButtonLiveDumpConfig: %08x\n`

## pseudocode

```c
__int64 __fastcall PopQueryPowerButtonConfiguration(HANDLE KeyHandle, _BYTE *a2)
{
  NTSTATUS v4; // edx
  int v5; // ecx
  int v6; // eax
  NTSTATUS v7; // ebx
  int v8; // ecx
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  UNICODE_STRING ValueName; // [rsp+58h] [rbp-11h] BYREF
  UNICODE_STRING v13; // [rsp+68h] [rbp-1h] BYREF
  UNICODE_STRING v14; // [rsp+78h] [rbp+Fh] BYREF
  __int128 KeyValueInformation; // [rsp+88h] [rbp+1Fh] BYREF
  int v16; // [rsp+98h] [rbp+2Fh]

  v16 = 0;
  ResultLength = 0;
  DestinationString = 0;
  ValueName = 0;
  v13 = 0;
  v14 = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, L"PowerButtonBugcheck");
  RtlInitUnicodeString(&ValueName, L"OneSettingPowerButtonBugcheck");
  RtlInitUnicodeString(&v13, L"PowerButtonLiveDump");
  RtlInitUnicodeString(&v14, L"OneSettingPowerButtonLiveDump");
  v4 = ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x14u,
         &ResultLength);
  if ( v4 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL )
  {
    LODWORD(PopPdcDeviceListLock.Queue) = 0;
    v4 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    if ( v4 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL )
    {
      HIDWORD(PopPdcDeviceListLock.Queue) = 0;
      v4 = -1073741823;
      HIDWORD(PopPdcDeviceListLock.Affinity) = 0;
      goto LABEL_14;
    }
    v6 = HIDWORD(KeyValueInformation);
    *a2 = 1;
    if ( v6 )
    {
      HIDWORD(PopPdcDeviceListLock.Queue) = 2;
      goto LABEL_10;
    }
    HIDWORD(PopPdcDeviceListLock.Queue) = 1;
LABEL_12:
    HIDWORD(PopPdcDeviceListLock.Affinity) = 1;
    goto LABEL_14;
  }
  v5 = HIDWORD(KeyValueInformation);
  *a2 = 1;
  if ( !v5 )
  {
    LODWORD(PopPdcDeviceListLock.Queue) = 1;
    goto LABEL_12;
  }
  LODWORD(PopPdcDeviceListLock.Queue) = 2;
LABEL_10:
  HIDWORD(PopPdcDeviceListLock.Affinity) = 2;
LABEL_14:
  DbgPrintEx(
    0x92u,
    2u,
    "%s (Bugcheck) completed with Status: %08x, ManualBugcheckConfig: %08x, OneSettingBugcheckConfig: %08x\n",
    "PopQueryPowerButtonConfiguration",
    v4,
    LODWORD(PopPdcDeviceListLock.Queue),
    HIDWORD(PopPdcDeviceListLock.Queue));
  v7 = ZwQueryValueKey(KeyHandle, &v13, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
  if ( v7 >= 0 && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
  {
    v8 = WORD6(KeyValueInformation) & 0x1FF;
    BYTE1(PopPdcDeviceListLock.Teb) = 1;
    HIDWORD(PopPdcDeviceListLock.Teb) = v8;
  }
  else
  {
    BYTE1(PopPdcDeviceListLock.Teb) = 0;
    HIDWORD(PopPdcDeviceListLock.Teb) = 0;
    v7 = ZwQueryValueKey(KeyHandle, &v14, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    if ( v7 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL )
    {
      v8 = 0;
      v7 = -1073741823;
      LOBYTE(PopPdcDeviceListLock.RelativeTimerBias) = 0;
      HIDWORD(PopPdcDeviceListLock.RelativeTimerBias) = 0;
      goto LABEL_22;
    }
    v8 = WORD6(KeyValueInformation) & 0x1FF;
    LOBYTE(PopPdcDeviceListLock.RelativeTimerBias) = 1;
    HIDWORD(PopPdcDeviceListLock.RelativeTimerBias) = v8;
  }
  *a2 = 1;
LABEL_22:
  LODWORD(PopPdcDeviceListLock.Affinity) = v8;
  DbgPrintEx(
    0x92u,
    2u,
    "%s (LiveDump) completed with Status: %08x, ManualLiveDumpConfig %08x, OneSettingLiveDumpConfig: %08x\n",
    "PopQueryPowerButtonConfiguration",
    v7,
    HIDWORD(PopPdcDeviceListLock.Teb),
    HIDWORD(PopPdcDeviceListLock.RelativeTimerBias));
  if ( (BYTE4(PopPdcDeviceListLock.Teb) & 1) != 0
    && !LODWORD(PopPdcDeviceListLock.Queue)
    && HIDWORD(PopPdcDeviceListLock.Affinity) == 2 )
  {
    HIDWORD(PopPdcDeviceListLock.Affinity) = 1;
  }
  DbgPrintEx(
    0x92u,
    2u,
    "%s completed with settings: PopPowerButtonBugcheckConfig: %08x, PopPowerButtonLiveDumpConfig: %08x\n",
    "PopQueryPowerButtonConfiguration",
    HIDWORD(PopPdcDeviceListLock.Affinity),
    LODWORD(PopPdcDeviceListLock.Affinity));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1406080e0  mov     [rsp-8+arg_10], rbx
0x1406080e5  mov     [rsp-8+arg_18], rsi
0x1406080ea  push    rbp
0x1406080eb  push    rdi
0x1406080ec  push    r12
0x1406080ee  lea     rbp, [rsp-47h]
0x1406080f3  sub     rsp, 0B0h
0x1406080fa  mov     rax, cs:__security_cookie
0x140608101  xor     rax, rsp
0x140608104  mov     [rbp+57h+var_20], rax
0x140608108  xorps   xmm0, xmm0
0x14060810b  xorps   xmm1, xmm1
0x14060810e  xor     eax, eax
0x140608110  mov     rdi, rdx
0x140608113  mov     rsi, rcx
0x140608116  mov     [rbp+57h+var_28], eax
0x140608119  lea     rdx, PopPowerButtonBugcheckRegName; "PowerButtonBugcheck"
0x140608120  mov     [rbp+57h+var_80], eax
0x140608123  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140608127  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14060812b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14060812f  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140608133  movups  xmmword ptr [rbp+57h+var_48.Length], xmm1
0x140608137  movups  [rbp+57h+KeyValueInformation], xmm0
0x14060813b  call    RtlInitUnicodeString
0x140608140  lea     rdx, PopOneSettingPowerButtonBugcheckRegName; "OneSettingPowerButtonBugcheck"
0x140608147  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14060814b  call    RtlInitUnicodeString
0x140608150  lea     rdx, PopPowerButtonLiveDumpRegName; "PowerButtonLiveDump"
0x140608157  lea     rcx, [rbp+57h+var_58]; DestinationString
0x14060815b  call    RtlInitUnicodeString
0x140608160  lea     rdx, PopOneSettingPowerButtonLiveDumpRegName; "OneSettingPowerButtonLiveDump"
0x140608167  lea     rcx, [rbp+57h+var_48]; DestinationString
0x14060816b  call    RtlInitUnicodeString
0x140608170  mov     ebx, 14h
0x140608175  lea     rax, [rbp+57h+var_80]
0x140608179  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14060817e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140608182  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140608186  mov     [rsp+0C0h+Length], ebx; Length
0x14060818a  mov     rcx, rsi; KeyHandle
0x14060818d  lea     r12d, [rbx-12h]
0x140608191  mov     r8d, r12d; KeyValueInformationClass
0x140608194  call    ZwQueryValueKey
0x140608199  mov     edx, eax
0x14060819b  test    eax, eax
0x14060819d  js      short loc_1406081CA
0x14060819f  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1406081a3  jnz     short loc_1406081CA
0x1406081a5  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x1406081a9  jnz     short loc_1406081CA
0x1406081ab  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1406081ae  mov     byte ptr [rdi], 1
0x1406081b1  test    ecx, ecx
0x1406081b3  jz      short loc_1406081BE
0x1406081b5  mov     dword ptr cs:PopPdcDeviceListLock.Queue, r12d
0x1406081bc  jmp     short loc_140608217
0x1406081be  mov     dword ptr cs:PopPdcDeviceListLock.Queue, 1
0x1406081c8  jmp     short loc_14060822A
0x1406081ca  lea     rax, [rbp+57h+var_80]
0x1406081ce  mov     dword ptr cs:PopPdcDeviceListLock.Queue, 0
0x1406081d8  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1406081dd  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1406081e1  mov     r8d, r12d; KeyValueInformationClass
0x1406081e4  mov     [rsp+0C0h+Length], ebx; Length
0x1406081e8  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1406081ec  mov     rcx, rsi; KeyHandle
0x1406081ef  call    ZwQueryValueKey
0x1406081f4  mov     edx, eax
0x1406081f6  test    eax, eax
0x1406081f8  js      short loc_140608236
0x1406081fa  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1406081fe  jnz     short loc_140608236
0x140608200  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x140608204  jnz     short loc_140608236
0x140608206  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140608209  mov     byte ptr [rdi], 1
0x14060820c  test    eax, eax
0x14060820e  jz      short loc_140608220
0x140608210  mov     dword ptr cs:PopPdcDeviceListLock.Queue+4, r12d
0x140608217  mov     dword ptr cs:PopPdcDeviceListLock.Affinity+4, r12d
0x14060821e  jmp     short loc_14060824F
0x140608220  mov     dword ptr cs:PopPdcDeviceListLock.Queue+4, 1
0x14060822a  mov     dword ptr cs:PopPdcDeviceListLock.Affinity+4, 1
0x140608234  jmp     short loc_14060824F
0x140608236  mov     dword ptr cs:PopPdcDeviceListLock.Queue+4, 0
0x140608240  mov     edx, 0C0000001h
0x140608245  mov     dword ptr cs:PopPdcDeviceListLock.Affinity+4, 0
0x14060824f  mov     eax, dword ptr cs:PopPdcDeviceListLock.Queue+4
0x140608255  lea     r9, aPopquerypowerb; "PopQueryPowerButtonConfiguration"
0x14060825c  mov     [rsp+0C0h+var_90], eax
0x140608260  lea     r8, aSBugcheckCompl; "%s (Bugcheck) completed with Status: %0"...
0x140608267  mov     eax, dword ptr cs:PopPdcDeviceListLock.Queue
0x14060826d  mov     ecx, 92h; ComponentId
0x140608272  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x140608276  mov     [rsp+0C0h+Length], edx
0x14060827a  mov     edx, r12d; Level
0x14060827d  call    DbgPrintEx
0x140608282  lea     rax, [rbp+57h+var_80]
0x140608286  mov     r8d, r12d; KeyValueInformationClass
0x140608289  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14060828e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140608292  lea     rdx, [rbp+57h+var_58]; ValueName
0x140608296  mov     [rsp+0C0h+Length], ebx; Length
0x14060829a  mov     rcx, rsi; KeyHandle
0x14060829d  call    ZwQueryValueKey
0x1406082a2  mov     ebx, eax
0x1406082a4  test    eax, eax
0x1406082a6  js      short loc_1406082CC
0x1406082a8  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1406082ac  jnz     short loc_1406082CC
0x1406082ae  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x1406082b2  jnz     short loc_1406082CC
0x1406082b4  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1406082b7  and     ecx, 1FFh
0x1406082bd  mov     byte ptr cs:PopPdcDeviceListLock.Teb+1, 1
0x1406082c4  mov     dword ptr cs:PopPdcDeviceListLock.Teb+4, ecx
0x1406082ca  jmp     short loc_140608329
0x1406082cc  lea     rax, [rbp+57h+var_80]
0x1406082d0  mov     byte ptr cs:PopPdcDeviceListLock.Teb+1, 0
0x1406082d7  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1406082dc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1406082e0  mov     r8d, r12d; KeyValueInformationClass
0x1406082e3  mov     [rsp+0C0h+Length], 14h; Length
0x1406082eb  lea     rdx, [rbp+57h+var_48]; ValueName
0x1406082ef  mov     dword ptr cs:PopPdcDeviceListLock.Teb+4, 0
0x1406082f9  mov     rcx, rsi; KeyHandle
0x1406082fc  call    ZwQueryValueKey
0x140608301  mov     ebx, eax
0x140608303  test    eax, eax
0x140608305  js      short loc_14060832E
0x140608307  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14060830b  jnz     short loc_14060832E
0x14060830d  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x140608311  jnz     short loc_14060832E
0x140608313  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140608316  and     ecx, 1FFh
0x14060831c  mov     byte ptr cs:PopPdcDeviceListLock.RelativeTimerBias, 1
0x140608323  mov     dword ptr cs:PopPdcDeviceListLock.RelativeTimerBias+4, ecx
0x140608329  mov     byte ptr [rdi], 1
0x14060832c  jmp     short loc_140608341
0x14060832e  xor     ecx, ecx
0x140608330  mov     ebx, 0C0000001h
0x140608335  mov     byte ptr cs:PopPdcDeviceListLock.RelativeTimerBias, cl
0x14060833b  mov     dword ptr cs:PopPdcDeviceListLock.RelativeTimerBias+4, ecx
0x140608341  mov     eax, dword ptr cs:PopPdcDeviceListLock.RelativeTimerBias+4
0x140608347  lea     r9, aPopquerypowerb; "PopQueryPowerButtonConfiguration"
0x14060834e  mov     [rsp+0C0h+var_90], eax
0x140608352  lea     r8, aSLivedumpCompl; "%s (LiveDump) completed with Status: %0"...
0x140608359  mov     eax, dword ptr cs:PopPdcDeviceListLock.Teb+4
0x14060835f  mov     edi, 92h
0x140608364  mov     dword ptr cs:PopPdcDeviceListLock.Affinity, ecx
0x14060836a  mov     edx, r12d; Level
0x14060836d  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x140608371  mov     ecx, edi; ComponentId
0x140608373  mov     [rsp+0C0h+Length], ebx
0x140608377  call    DbgPrintEx
0x14060837c  mov     eax, dword ptr cs:PopPdcDeviceListLock.Teb+4
0x140608382  test    al, 1
0x140608384  jz      short loc_1406083A2
0x140608386  cmp     dword ptr cs:PopPdcDeviceListLock.Queue, 0
0x14060838d  jnz     short loc_1406083A2
0x14060838f  cmp     dword ptr cs:PopPdcDeviceListLock.Affinity+4, r12d
0x140608396  jnz     short loc_1406083A2
0x140608398  mov     dword ptr cs:PopPdcDeviceListLock.Affinity+4, 1
0x1406083a2  mov     eax, dword ptr cs:PopPdcDeviceListLock.Affinity
0x1406083a8  lea     r9, aPopquerypowerb; "PopQueryPowerButtonConfiguration"
0x1406083af  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x1406083b3  lea     r8, aSCompletedWith; "%s completed with settings: PopPowerBut"...
0x1406083ba  mov     eax, dword ptr cs:PopPdcDeviceListLock.Affinity+4
0x1406083c0  mov     edx, r12d; Level
0x1406083c3  mov     ecx, edi; ComponentId
0x1406083c5  mov     [rsp+0C0h+Length], eax
0x1406083c9  call    DbgPrintEx
0x1406083ce  mov     eax, ebx
0x1406083d0  mov     rcx, [rbp+57h+var_20]
0x1406083d4  xor     rcx, rsp; StackCookie
0x1406083d7  call    __security_check_cookie
0x1406083dc  lea     r11, [rsp+0C0h+var_10]
0x1406083e4  mov     rbx, [r11+30h]
0x1406083e8  mov     rsi, [r11+38h]
0x1406083ec  mov     rsp, r11
0x1406083ef  pop     r12
0x1406083f1  pop     rdi
0x1406083f2  pop     rbp
0x1406083f3  retn
```
