# FltpReadDriverParameters

- ea: `0x180089cec`
- end: `0x18008a129`
- name: `FltpReadDriverParameters`
- size: `1085`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180089078`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180089cec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180089d92`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089df7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089e43`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089e93`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089ee4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089f35`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089f81`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089fcd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a019`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a065`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a0b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089d92`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089df7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089e43`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089e93`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089ee4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089f35`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089f81`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089fcd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a019`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a065`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a0b1`
- `ntoskrnl!ZwClose` at `0x18008a0fb`
- `ntoskrnl!ZwClose` at `0x18008a0fb`
- `ntoskrnl!ZwOpenKey` at `0x180089d4b`
- `ntoskrnl!ZwOpenKey` at `0x180089d4b`
- `ntoskrnl!ZwQueryValueKey` at `0x180089dba`
- `ntoskrnl!ZwQueryValueKey` at `0x180089e1f`
- `ntoskrnl!ZwQueryValueKey` at `0x180089e6b`
- `ntoskrnl!ZwQueryValueKey` at `0x180089ebb`
- `ntoskrnl!ZwQueryValueKey` at `0x180089f0c`
- `ntoskrnl!ZwQueryValueKey` at `0x180089f5d`
- `ntoskrnl!ZwQueryValueKey` at `0x180089fa9`
- `ntoskrnl!ZwQueryValueKey` at `0x180089ff5`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a041`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a08d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a0d9`
- `ntoskrnl!ZwQueryValueKey` at `0x180089dba`
- `ntoskrnl!ZwQueryValueKey` at `0x180089e1f`
- `ntoskrnl!ZwQueryValueKey` at `0x180089e6b`
- `ntoskrnl!ZwQueryValueKey` at `0x180089ebb`
- `ntoskrnl!ZwQueryValueKey` at `0x180089f0c`
- `ntoskrnl!ZwQueryValueKey` at `0x180089f5d`
- `ntoskrnl!ZwQueryValueKey` at `0x180089fa9`
- `ntoskrnl!ZwQueryValueKey` at `0x180089ff5`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a041`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a08d`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a0d9`

## pseudocode

```c
NTSTATUS __fastcall FltpReadDriverParameters(UNICODE_STRING *a1)
{
  unsigned int v1; // eax
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+37h] BYREF
  int v8; // [rsp+84h] [rbp+3Bh]
  __int64 v9; // [rsp+8Ch] [rbp+43h]

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  DestinationString = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  result = FltpDbgStatus(v1, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 11422, 0);
  if ( result >= 0 )
  {
    if ( !FltGlobals[0] )
    {
      RtlInitUnicodeString(&DestinationString, L"DebugFlags");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x18u,
             &ResultLength) >= 0
        && v8 == 4 )
      {
        FltGlobals[0] = v9;
      }
    }
    if ( !dword_18003FD70 )
    {
      dword_18003FD70 = 30;
      RtlInitUnicodeString(&DestinationString, L"LostItemDetectionDelay");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x18u,
             &ResultLength) >= 0 )
        dword_18003FD70 = v9;
    }
    RtlInitUnicodeString(&DestinationString, L"UseTildeShortcut");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0
      && (_DWORD)v9 )
    {
      dword_18003E750 &= ~2u;
    }
    RtlInitUnicodeString(&DestinationString, L"FastManualAttachTimerPeriod");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0
      && (_DWORD)v9 )
    {
      dword_18003E9F0 = v9;
    }
    RtlInitUnicodeString(&DestinationString, L"ManualAttachTimerPeriod");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0
      && (_DWORD)v9 )
    {
      LODWORD(qword_18003E9F4) = v9;
    }
    RtlInitUnicodeString(&DestinationString, L"ManualAttachDelay");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      HIDWORD(qword_18003E9F4) = v9;
    RtlInitUnicodeString(&DestinationString, L"CallbackStackSwapThreshold");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      dword_18003EA00 = v9;
    RtlInitUnicodeString(&DestinationString, L"ManualAttachIgnoredDevices");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      byte_18003E9FC = v9;
    RtlInitUnicodeString(&DestinationString, L"ManualAttachOnlyOnceDevices");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      byte_18003E9FD = v9;
    RtlInitUnicodeString(&DestinationString, L"ManualAttachFastAttachDevices");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
      byte_18003E9FE = v9;
    RtlInitUnicodeString(&DestinationString, L"DisableFrameMonitoring");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength) >= 0 )
    {
      if ( (_DWORD)v9 )
        dword_18003E750 &= ~0x100u;
    }
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x180089cec  mov     [rsp-8+arg_8], rsi
0x180089cf1  mov     [rsp-8+arg_10], rdi
0x180089cf6  push    rbp
0x180089cf7  lea     rbp, [rsp-57h]
0x180089cfc  sub     rsp, 0A0h
0x180089d03  mov     rax, cs:__security_cookie
0x180089d0a  xor     rax, rsp
0x180089d0d  mov     [rbp+57h+var_8], rax
0x180089d11  xor     eax, eax
0x180089d13  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x180089d17  xorps   xmm0, xmm0
0x180089d1a  mov     [rbp+57h+KeyHandle], rax
0x180089d1e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089d22  mov     [rbp+57h+var_70], eax
0x180089d25  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180089d29  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180089d2d  mov     edx, 20019h; DesiredAccess
0x180089d32  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180089d3a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180089d3e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180089d46  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180089d4b  call    cs:__imp_ZwOpenKey
0x180089d52  nop     dword ptr [rax+rax+00h]
0x180089d57  mov     r8d, 2C9Eh
0x180089d5d  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180089d64  mov     ecx, eax
0x180089d66  xor     r9d, r9d
0x180089d69  call    FltpDbgStatus
0x180089d6e  test    eax, eax
0x180089d70  js      loc_18008A107
0x180089d76  cmp     cs:FltGlobals, 0
0x180089d7d  mov     edi, 18h
0x180089d82  lea     esi, [rdi-16h]
0x180089d85  jnz     short loc_180089DD9
0x180089d87  lea     rdx, aDebugflags; "DebugFlags"
0x180089d8e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089d92  call    cs:__imp_RtlInitUnicodeString
0x180089d99  nop     dword ptr [rax+rax+00h]
0x180089d9e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089da2  lea     rax, [rbp+57h+var_70]
0x180089da6  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089dab  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089daf  mov     r8d, esi; KeyValueInformationClass
0x180089db2  mov     [rsp+0A0h+Length], edi; Length
0x180089db6  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089dba  call    cs:__imp_ZwQueryValueKey
0x180089dc1  nop     dword ptr [rax+rax+00h]
0x180089dc6  test    eax, eax
0x180089dc8  js      short loc_180089DD9
0x180089dca  cmp     [rbp+57h+var_1C], 4
0x180089dce  jnz     short loc_180089DD9
0x180089dd0  mov     eax, dword ptr [rbp+57h+var_14]
0x180089dd3  mov     cs:FltGlobals, eax
0x180089dd9  cmp     cs:dword_18003FD70, 0
0x180089de0  jnz     short loc_180089E38
0x180089de2  lea     rdx, aLostitemdetect; "LostItemDetectionDelay"
0x180089de9  mov     cs:dword_18003FD70, 1Eh
0x180089df3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089df7  call    cs:__imp_RtlInitUnicodeString
0x180089dfe  nop     dword ptr [rax+rax+00h]
0x180089e03  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089e07  lea     rax, [rbp+57h+var_70]
0x180089e0b  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089e10  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089e14  mov     r8d, esi; KeyValueInformationClass
0x180089e17  mov     [rsp+0A0h+Length], edi; Length
0x180089e1b  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089e1f  call    cs:__imp_ZwQueryValueKey
0x180089e26  nop     dword ptr [rax+rax+00h]
0x180089e2b  test    eax, eax
0x180089e2d  js      short loc_180089E38
0x180089e2f  mov     eax, dword ptr [rbp+57h+var_14]
0x180089e32  mov     cs:dword_18003FD70, eax
0x180089e38  lea     rdx, aUsetildeshortc; "UseTildeShortcut"
0x180089e3f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089e43  call    cs:__imp_RtlInitUnicodeString
0x180089e4a  nop     dword ptr [rax+rax+00h]
0x180089e4f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089e53  lea     rax, [rbp+57h+var_70]
0x180089e57  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089e5c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089e60  mov     r8d, esi; KeyValueInformationClass
0x180089e63  mov     [rsp+0A0h+Length], edi; Length
0x180089e67  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089e6b  call    cs:__imp_ZwQueryValueKey
0x180089e72  nop     dword ptr [rax+rax+00h]
0x180089e77  test    eax, eax
0x180089e79  js      short loc_180089E88
0x180089e7b  cmp     dword ptr [rbp+57h+var_14], 0
0x180089e7f  jz      short loc_180089E88
0x180089e81  and     cs:dword_18003E750, 0FFFFFFFDh
0x180089e88  lea     rdx, aFastmanualatta; "FastManualAttachTimerPeriod"
0x180089e8f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089e93  call    cs:__imp_RtlInitUnicodeString
0x180089e9a  nop     dword ptr [rax+rax+00h]
0x180089e9f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089ea3  lea     rax, [rbp+57h+var_70]
0x180089ea7  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089eac  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089eb0  mov     r8d, esi; KeyValueInformationClass
0x180089eb3  mov     [rsp+0A0h+Length], edi; Length
0x180089eb7  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089ebb  call    cs:__imp_ZwQueryValueKey
0x180089ec2  nop     dword ptr [rax+rax+00h]
0x180089ec7  test    eax, eax
0x180089ec9  js      short loc_180089ED9
0x180089ecb  mov     rax, [rbp+57h+var_14]
0x180089ecf  test    eax, eax
0x180089ed1  jz      short loc_180089ED9
0x180089ed3  mov     cs:dword_18003E9F0, eax
0x180089ed9  lea     rdx, aManualattachti; "ManualAttachTimerPeriod"
0x180089ee0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089ee4  call    cs:__imp_RtlInitUnicodeString
0x180089eeb  nop     dword ptr [rax+rax+00h]
0x180089ef0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089ef4  lea     rax, [rbp+57h+var_70]
0x180089ef8  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089efd  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089f01  mov     r8d, esi; KeyValueInformationClass
0x180089f04  mov     [rsp+0A0h+Length], edi; Length
0x180089f08  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089f0c  call    cs:__imp_ZwQueryValueKey
0x180089f13  nop     dword ptr [rax+rax+00h]
0x180089f18  test    eax, eax
0x180089f1a  js      short loc_180089F2A
0x180089f1c  mov     rax, [rbp+57h+var_14]
0x180089f20  test    eax, eax
0x180089f22  jz      short loc_180089F2A
0x180089f24  mov     dword ptr cs:qword_18003E9F4, eax
0x180089f2a  lea     rdx, aManualattachde; "ManualAttachDelay"
0x180089f31  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089f35  call    cs:__imp_RtlInitUnicodeString
0x180089f3c  nop     dword ptr [rax+rax+00h]
0x180089f41  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089f45  lea     rax, [rbp+57h+var_70]
0x180089f49  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089f4e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089f52  mov     r8d, esi; KeyValueInformationClass
0x180089f55  mov     [rsp+0A0h+Length], edi; Length
0x180089f59  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089f5d  call    cs:__imp_ZwQueryValueKey
0x180089f64  nop     dword ptr [rax+rax+00h]
0x180089f69  test    eax, eax
0x180089f6b  js      short loc_180089F76
0x180089f6d  mov     eax, dword ptr [rbp+57h+var_14]
0x180089f70  mov     dword ptr cs:qword_18003E9F4+4, eax
0x180089f76  lea     rdx, aCallbackstacks; "CallbackStackSwapThreshold"
0x180089f7d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089f81  call    cs:__imp_RtlInitUnicodeString
0x180089f88  nop     dword ptr [rax+rax+00h]
0x180089f8d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089f91  lea     rax, [rbp+57h+var_70]
0x180089f95  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089f9a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089f9e  mov     r8d, esi; KeyValueInformationClass
0x180089fa1  mov     [rsp+0A0h+Length], edi; Length
0x180089fa5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089fa9  call    cs:__imp_ZwQueryValueKey
0x180089fb0  nop     dword ptr [rax+rax+00h]
0x180089fb5  test    eax, eax
0x180089fb7  js      short loc_180089FC2
0x180089fb9  mov     eax, dword ptr [rbp+57h+var_14]
0x180089fbc  mov     cs:dword_18003EA00, eax
0x180089fc2  lea     rdx, aManualattachig; "ManualAttachIgnoredDevices"
0x180089fc9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180089fcd  call    cs:__imp_RtlInitUnicodeString
0x180089fd4  nop     dword ptr [rax+rax+00h]
0x180089fd9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180089fdd  lea     rax, [rbp+57h+var_70]
0x180089fe1  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180089fe6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089fea  mov     r8d, esi; KeyValueInformationClass
0x180089fed  mov     [rsp+0A0h+Length], edi; Length
0x180089ff1  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180089ff5  call    cs:__imp_ZwQueryValueKey
0x180089ffc  nop     dword ptr [rax+rax+00h]
0x18008a001  test    eax, eax
0x18008a003  js      short loc_18008A00E
0x18008a005  mov     al, byte ptr [rbp+57h+var_14]
0x18008a008  mov     cs:byte_18003E9FC, al
0x18008a00e  lea     rdx, aManualattachon; "ManualAttachOnlyOnceDevices"
0x18008a015  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008a019  call    cs:__imp_RtlInitUnicodeString
0x18008a020  nop     dword ptr [rax+rax+00h]
0x18008a025  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008a029  lea     rax, [rbp+57h+var_70]
0x18008a02d  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008a032  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008a036  mov     r8d, esi; KeyValueInformationClass
0x18008a039  mov     [rsp+0A0h+Length], edi; Length
0x18008a03d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008a041  call    cs:__imp_ZwQueryValueKey
0x18008a048  nop     dword ptr [rax+rax+00h]
0x18008a04d  test    eax, eax
0x18008a04f  js      short loc_18008A05A
0x18008a051  mov     al, byte ptr [rbp+57h+var_14]
0x18008a054  mov     cs:byte_18003E9FD, al
0x18008a05a  lea     rdx, aManualattachfa; "ManualAttachFastAttachDevices"
0x18008a061  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008a065  call    cs:__imp_RtlInitUnicodeString
0x18008a06c  nop     dword ptr [rax+rax+00h]
0x18008a071  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008a075  lea     rax, [rbp+57h+var_70]
0x18008a079  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008a07e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008a082  mov     r8d, esi; KeyValueInformationClass
0x18008a085  mov     [rsp+0A0h+Length], edi; Length
0x18008a089  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008a08d  call    cs:__imp_ZwQueryValueKey
0x18008a094  nop     dword ptr [rax+rax+00h]
0x18008a099  test    eax, eax
0x18008a09b  js      short loc_18008A0A6
0x18008a09d  mov     al, byte ptr [rbp+57h+var_14]
0x18008a0a0  mov     cs:byte_18003E9FE, al
0x18008a0a6  lea     rdx, aDisableframemo; "DisableFrameMonitoring"
0x18008a0ad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008a0b1  call    cs:__imp_RtlInitUnicodeString
0x18008a0b8  nop     dword ptr [rax+rax+00h]
0x18008a0bd  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008a0c1  lea     rax, [rbp+57h+var_70]
0x18008a0c5  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18008a0ca  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008a0ce  mov     r8d, esi; KeyValueInformationClass
0x18008a0d1  mov     [rsp+0A0h+Length], edi; Length
0x18008a0d5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18008a0d9  call    cs:__imp_ZwQueryValueKey
0x18008a0e0  nop     dword ptr [rax+rax+00h]
0x18008a0e5  test    eax, eax
0x18008a0e7  js      short loc_18008A0F7
0x18008a0e9  cmp     dword ptr [rbp+57h+var_14], 0
0x18008a0ed  jz      short loc_18008A0F7
0x18008a0ef  btr     cs:dword_18003E750, 8
0x18008a0f7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008a0fb  call    cs:__imp_ZwClose
0x18008a102  nop     dword ptr [rax+rax+00h]
0x18008a107  mov     rcx, [rbp+57h+var_8]
0x18008a10b  xor     rcx, rsp; StackCookie
0x18008a10e  call    __security_check_cookie
0x18008a113  lea     r11, [rsp+0A0h+var_s0]
0x18008a11b  mov     rsi, [r11+18h]
0x18008a11f  mov     rdi, [r11+20h]
0x18008a123  mov     rsp, r11
0x18008a126  pop     rbp
0x18008a127  retn
```
