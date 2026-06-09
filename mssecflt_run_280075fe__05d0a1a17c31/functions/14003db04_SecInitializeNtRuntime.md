# SecInitializeNtRuntime

- ea: `0x14003db04`
- end: `0x14003dd13`
- name: `SecInitializeNtRuntime`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003df4c`

## callees

- `0x140011650`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003db42`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003db77`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dbac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dbe1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dc16`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dc4b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dc80`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dcb5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dcea`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003db42`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003db77`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dbac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dbe1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dc16`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dc4b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dc80`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dcb5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14003dcea`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003db32`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003db67`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003db9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dbd1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc06`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc70`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dca5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dcda`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003db32`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003db67`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003db9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dbd1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc06`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc70`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dca5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dcda`

## string_xrefs

- `0x14003db51`: `PsSetCreateProcessNotifyRoutineEx2`
- `0x14003dc25`: `ZwGetNextThread`
- `0x14003dc5a`: `SeConvertSecurityDescriptorToStringSecurityDescriptor`
- `0x14003dcc4`: `IoCheckFileObjectOpenedAsCopyDestination`

## pseudocode

```c
PVOID SecInitializeNtRuntime()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING v3; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING v4; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING v5; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING v6; // [rsp+70h] [rbp+7h] BYREF
  struct _UNICODE_STRING v7; // [rsp+80h] [rbp+17h] BYREF
  struct _UNICODE_STRING v8; // [rsp+90h] [rbp+27h] BYREF
  struct _UNICODE_STRING v9; // [rsp+A0h] [rbp+37h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"ExAllocatePool2");
  qword_140020008 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
  SystemRoutineName = 0;
  RtlInitUnicodeString(&SystemRoutineName, L"PsSetCreateProcessNotifyRoutineEx2");
  qword_140020010 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&SystemRoutineName);
  v3 = 0;
  RtlInitUnicodeString(&v3, L"PsSetLoadImageNotifyRoutineEx");
  qword_140020018 = (__int64 (__fastcall *)(_QWORD, _QWORD))MmGetSystemRoutineAddress(&v3);
  v4 = 0;
  RtlInitUnicodeString(&v4, L"PsGetProcessStartKey");
  qword_140020020 = (__int64 (*)(void))MmGetSystemRoutineAddress(&v4);
  v5 = 0;
  RtlInitUnicodeString(&v5, L"FsRtlQueryInformationFile");
  qword_140020028 = (__int64)MmGetSystemRoutineAddress(&v5);
  v6 = 0;
  RtlInitUnicodeString(&v6, L"ZwGetNextThread");
  qword_140020030 = (__int64)MmGetSystemRoutineAddress(&v6);
  v7 = 0;
  RtlInitUnicodeString(&v7, L"SeConvertSecurityDescriptorToStringSecurityDescriptor");
  qword_140020038 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&v7);
  v8 = 0;
  RtlInitUnicodeString(&v8, L"MmProtectDriverSection");
  qword_140020040 = (__int64)MmGetSystemRoutineAddress(&v8);
  v9 = 0;
  RtlInitUnicodeString(&v9, L"IoCheckFileObjectOpenedAsCopyDestination");
  result = MmGetSystemRoutineAddress(&v9);
  qword_140020048 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x14003db04  push    rbp
0x14003db06  lea     rbp, [rsp-57h]
0x14003db0b  sub     rsp, 0C0h
0x14003db12  mov     rax, cs:__security_cookie
0x14003db19  xor     rax, rsp
0x14003db1c  mov     [rbp+57h+var_10], rax
0x14003db20  xorps   xmm0, xmm0
0x14003db23  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x14003db2a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003db2e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003db32  call    cs:__imp_RtlInitUnicodeString
0x14003db39  nop     dword ptr [rax+rax+00h]
0x14003db3e  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14003db42  call    cs:__imp_MmGetSystemRoutineAddress
0x14003db49  nop     dword ptr [rax+rax+00h]
0x14003db4e  xorps   xmm0, xmm0
0x14003db51  lea     rdx, aPssetcreatepro; "PsSetCreateProcessNotifyRoutineEx2"
0x14003db58  lea     rcx, [rbp+57h+SystemRoutineName]; DestinationString
0x14003db5c  mov     cs:qword_140020008, rax
0x14003db63  movups  xmmword ptr [rbp+57h+SystemRoutineName.Length], xmm0
0x14003db67  call    cs:__imp_RtlInitUnicodeString
0x14003db6e  nop     dword ptr [rax+rax+00h]
0x14003db73  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x14003db77  call    cs:__imp_MmGetSystemRoutineAddress
0x14003db7e  nop     dword ptr [rax+rax+00h]
0x14003db83  xorps   xmm0, xmm0
0x14003db86  lea     rdx, aPssetloadimage; "PsSetLoadImageNotifyRoutineEx"
0x14003db8d  lea     rcx, [rbp+57h+var_80]; DestinationString
0x14003db91  mov     cs:qword_140020010, rax
0x14003db98  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x14003db9c  call    cs:__imp_RtlInitUnicodeString
0x14003dba3  nop     dword ptr [rax+rax+00h]
0x14003dba8  lea     rcx, [rbp+57h+var_80]; SystemRoutineName
0x14003dbac  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dbb3  nop     dword ptr [rax+rax+00h]
0x14003dbb8  xorps   xmm0, xmm0
0x14003dbbb  lea     rdx, aPsgetprocessst; "PsGetProcessStartKey"
0x14003dbc2  lea     rcx, [rbp+57h+var_70]; DestinationString
0x14003dbc6  mov     cs:qword_140020018, rax
0x14003dbcd  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x14003dbd1  call    cs:__imp_RtlInitUnicodeString
0x14003dbd8  nop     dword ptr [rax+rax+00h]
0x14003dbdd  lea     rcx, [rbp+57h+var_70]; SystemRoutineName
0x14003dbe1  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dbe8  nop     dword ptr [rax+rax+00h]
0x14003dbed  xorps   xmm0, xmm0
0x14003dbf0  lea     rdx, aFsrtlqueryinfo; "FsRtlQueryInformationFile"
0x14003dbf7  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14003dbfb  mov     cs:qword_140020020, rax
0x14003dc02  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14003dc06  call    cs:__imp_RtlInitUnicodeString
0x14003dc0d  nop     dword ptr [rax+rax+00h]
0x14003dc12  lea     rcx, [rbp+57h+var_60]; SystemRoutineName
0x14003dc16  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dc1d  nop     dword ptr [rax+rax+00h]
0x14003dc22  xorps   xmm0, xmm0
0x14003dc25  lea     rdx, aZwgetnextthrea; "ZwGetNextThread"
0x14003dc2c  lea     rcx, [rbp+57h+var_50]; DestinationString
0x14003dc30  mov     cs:qword_140020028, rax
0x14003dc37  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x14003dc3b  call    cs:__imp_RtlInitUnicodeString
0x14003dc42  nop     dword ptr [rax+rax+00h]
0x14003dc47  lea     rcx, [rbp+57h+var_50]; SystemRoutineName
0x14003dc4b  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dc52  nop     dword ptr [rax+rax+00h]
0x14003dc57  xorps   xmm0, xmm0
0x14003dc5a  lea     rdx, aSeconvertsecur; "SeConvertSecurityDescriptorToStringSecu"...
0x14003dc61  lea     rcx, [rbp+57h+var_40]; DestinationString
0x14003dc65  mov     cs:qword_140020030, rax
0x14003dc6c  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x14003dc70  call    cs:__imp_RtlInitUnicodeString
0x14003dc77  nop     dword ptr [rax+rax+00h]
0x14003dc7c  lea     rcx, [rbp+57h+var_40]; SystemRoutineName
0x14003dc80  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dc87  nop     dword ptr [rax+rax+00h]
0x14003dc8c  xorps   xmm0, xmm0
0x14003dc8f  lea     rdx, aMmprotectdrive; "MmProtectDriverSection"
0x14003dc96  lea     rcx, [rbp+57h+var_30]; DestinationString
0x14003dc9a  mov     cs:qword_140020038, rax
0x14003dca1  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x14003dca5  call    cs:__imp_RtlInitUnicodeString
0x14003dcac  nop     dword ptr [rax+rax+00h]
0x14003dcb1  lea     rcx, [rbp+57h+var_30]; SystemRoutineName
0x14003dcb5  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dcbc  nop     dword ptr [rax+rax+00h]
0x14003dcc1  xorps   xmm0, xmm0
0x14003dcc4  lea     rdx, aIocheckfileobj; "IoCheckFileObjectOpenedAsCopyDestinatio"...
0x14003dccb  lea     rcx, [rbp+57h+var_20]; DestinationString
0x14003dccf  mov     cs:qword_140020040, rax
0x14003dcd6  movups  xmmword ptr [rbp+57h+var_20.Length], xmm0
0x14003dcda  call    cs:__imp_RtlInitUnicodeString
0x14003dce1  nop     dword ptr [rax+rax+00h]
0x14003dce6  lea     rcx, [rbp+57h+var_20]; SystemRoutineName
0x14003dcea  call    cs:__imp_MmGetSystemRoutineAddress
0x14003dcf1  nop     dword ptr [rax+rax+00h]
0x14003dcf6  mov     cs:qword_140020048, rax
0x14003dcfd  mov     rcx, [rbp+57h+var_10]
0x14003dd01  xor     rcx, rsp; StackCookie
0x14003dd04  call    __security_check_cookie
0x14003dd09  add     rsp, 0C0h
0x14003dd10  pop     rbp
0x14003dd11  retn
```
