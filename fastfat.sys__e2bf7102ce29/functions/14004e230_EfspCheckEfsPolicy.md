# EfspCheckEfsPolicy

- ea: `0x14004e230`
- end: `0x14004e4ec`
- name: `EfspCheckEfsPolicy`
- size: `700`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14004e16c`
- `0x14004e230`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14004e2e2`
- `ntoskrnl!KeDelayExecutionThread` at `0x14004e2e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e2a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e36a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e3ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e2a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e36a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e3ee`
- `ntoskrnl!ZwOpenKey` at `0x14004e302`
- `ntoskrnl!ZwOpenKey` at `0x14004e3a6`
- `ntoskrnl!ZwOpenKey` at `0x14004e302`
- `ntoskrnl!ZwOpenKey` at `0x14004e3a6`
- `ntoskrnl!ZwQueryValueKey` at `0x14004e418`
- `ntoskrnl!ZwQueryValueKey` at `0x14004e418`
- `ntoskrnl!ZwClose` at `0x14004e4a9`
- `ntoskrnl!ZwClose` at `0x14004e4be`
- `ntoskrnl!ZwClose` at `0x14004e4a9`
- `ntoskrnl!ZwClose` at `0x14004e4be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e444`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e444`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14004e353`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14004e353`
- `ntoskrnl!ZwQueryWnfStateData` at `0x14004e477`
- `ntoskrnl!ZwQueryWnfStateData` at `0x14004e477`
- `ntoskrnl!ExAllocatePool2` at `0x14004e3cc`
- `ntoskrnl!ExAllocatePool2` at `0x14004e3cc`
- `ntoskrnl!PsTerminateSystemThread` at `0x14004e4cc`
- `ntoskrnl!PsTerminateSystemThread` at `0x14004e4cc`

## string_xrefs

- `0x14004e259`: `\Registry\Machine\Software`
- `0x14004e35f`: `\Registry\Machine\Software\Policies\Microsoft\Windows NT\CurrentVersion\EFS`

## pseudocode

```c
NTSTATUS EfspCheckEfsPolicy()
{
  int v0; // edi
  int v1; // ebx
  NTSTATUS v2; // eax
  _DWORD *Pool2; // rdi
  char v4; // si
  int v6; // [rsp+40h] [rbp-39h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-31h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp+17h] BYREF
  struct _UNICODE_STRING v12; // [rsp+A0h] [rbp+27h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+B0h] [rbp+37h] BYREF
  int v14; // [rsp+E8h] [rbp+6Fh] BYREF
  int v15; // [rsp+F0h] [rbp+77h] BYREF
  ULONG ResultLength; // [rsp+F8h] [rbp+7Fh] BYREF

  Handle = 0;
  ResultLength = 0;
  KeyHandle = 0;
  v6 = 0;
  v12 = 0;
  v15 = 0;
  ValueName = 0;
  v14 = 4;
  memset(&ObjectAttributes.Length + 1, 0, 44);
  Interval.QuadPart = -30000000;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  v0 = 0;
  ObjectAttributes.Attributes = 576;
  while ( 1 )
  {
    v1 = KeDelayExecutionThread(0, 0, &Interval);
    if ( v1 < 0 )
      break;
    v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v1 = v2;
    if ( v2 >= 0 )
    {
      ZwUpdateWnfStateData(&WNF_EFS_SOFTWARE_HIVE_AVAILABLE, 0, 0, 0, 0, 0, 0);
      RtlInitUnicodeString(&v12, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows NT\\CurrentVersion\\EFS");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v12;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
        goto LABEL_14;
      Pool2 = (_DWORD *)ExAllocatePool2(64, 1024, 1836279365);
      if ( !Pool2 )
        goto LABEL_14;
      v4 = 0;
      RtlInitUnicodeString(&ValueName, L"EfsOptions");
      v1 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength);
      if ( v1 >= 0 && Pool2[1] == 4 && (Pool2[3] & 1) != 0 )
      {
        EfsTriggerServiceStart();
        v4 = 1;
      }
      ExFreePoolWithTag(Pool2, 0);
      if ( !v4 )
      {
LABEL_14:
        v1 = ZwQueryWnfStateData(&WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED, 0, 0, &v6, &v15, &v14);
        if ( v1 >= 0 && v14 == 4 && v15 && v15 < 4 )
          EfsTriggerServiceStart();
      }
      break;
    }
    if ( v2 == -1073741772 && (unsigned int)++v0 < 0x14 )
      continue;
    break;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return PsTerminateSystemThread(v1);
}

```

## disassembly

```asm
0x14004e230  mov     [rsp-8+arg_0], rbx
0x14004e235  push    rbp
0x14004e236  push    rsi
0x14004e237  push    rdi
0x14004e238  lea     rbp, [rsp-47h]
0x14004e23d  sub     rsp, 0C0h
0x14004e244  xorps   xmm0, xmm0
0x14004e247  mov     [rbp+57h+Handle], 0
0x14004e24f  xorps   xmm1, xmm1
0x14004e252  mov     [rbp+57h+arg_18], 0
0x14004e259  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\Software"
0x14004e260  mov     [rbp+57h+KeyHandle], 0
0x14004e268  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004e26c  mov     [rbp+57h+var_90], 0
0x14004e273  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x14004e277  mov     [rbp+57h+arg_10], 0
0x14004e27e  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14004e282  mov     [rbp+57h+arg_8], 4
0x14004e289  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004e28d  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFE363C80h
0x14004e295  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004e299  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e29d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004e2a1  call    cs:__imp_RtlInitUnicodeString
0x14004e2a8  nop     dword ptr [rax+rax+00h]
0x14004e2ad  lea     rax, [rbp+57h+DestinationString]
0x14004e2b1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004e2b8  xorps   xmm0, xmm0
0x14004e2bb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004e2bf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e2c4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14004e2cc  xor     edi, edi
0x14004e2ce  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004e2d5  mov     esi, 20019h
0x14004e2da  lea     r8, [rbp+57h+Interval]; Interval
0x14004e2de  xor     edx, edx; Alertable
0x14004e2e0  xor     ecx, ecx; WaitMode
0x14004e2e2  call    cs:__imp_KeDelayExecutionThread
0x14004e2e9  nop     dword ptr [rax+rax+00h]
0x14004e2ee  mov     ebx, eax
0x14004e2f0  test    eax, eax
0x14004e2f2  js      loc_14004E4A0
0x14004e2f8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004e2fc  mov     edx, esi; DesiredAccess
0x14004e2fe  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004e302  call    cs:__imp_ZwOpenKey
0x14004e309  nop     dword ptr [rax+rax+00h]
0x14004e30e  mov     ebx, eax
0x14004e310  test    eax, eax
0x14004e312  jns     short loc_14004E32B
0x14004e314  cmp     eax, 0C0000034h
0x14004e319  jnz     loc_14004E4A0
0x14004e31f  inc     edi
0x14004e321  cmp     edi, 14h
0x14004e324  jb      short loc_14004E2DA
0x14004e326  jmp     loc_14004E4A0
0x14004e32b  mov     [rsp+0D0h+var_A0], 0
0x14004e333  lea     rcx, WNF_EFS_SOFTWARE_HIVE_AVAILABLE
0x14004e33a  mov     dword ptr [rsp+0D0h+ResultLength], 0
0x14004e342  xor     r9d, r9d
0x14004e345  xor     r8d, r8d
0x14004e348  mov     qword ptr [rsp+0D0h+Length], 0
0x14004e351  xor     edx, edx
0x14004e353  call    cs:__imp_ZwUpdateWnfStateData
0x14004e35a  nop     dword ptr [rax+rax+00h]
0x14004e35f  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Policies"...
0x14004e366  lea     rcx, [rbp+57h+var_30]; DestinationString
0x14004e36a  call    cs:__imp_RtlInitUnicodeString
0x14004e371  nop     dword ptr [rax+rax+00h]
0x14004e376  lea     rax, [rbp+57h+var_30]
0x14004e37a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004e381  xorps   xmm0, xmm0
0x14004e384  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004e388  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004e38c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14004e394  mov     edx, esi; DesiredAccess
0x14004e396  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004e39d  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x14004e3a1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e3a6  call    cs:__imp_ZwOpenKey
0x14004e3ad  nop     dword ptr [rax+rax+00h]
0x14004e3b2  test    eax, eax
0x14004e3b4  js      loc_14004E455
0x14004e3ba  mov     ebx, 400h
0x14004e3bf  mov     r8d, 6D736645h
0x14004e3c5  mov     edx, ebx
0x14004e3c7  mov     ecx, 40h ; '@'
0x14004e3cc  call    cs:__imp_ExAllocatePool2
0x14004e3d3  nop     dword ptr [rax+rax+00h]
0x14004e3d8  mov     rdi, rax
0x14004e3db  test    rax, rax
0x14004e3de  jz      short loc_14004E455
0x14004e3e0  lea     rdx, aEfsoptions; "EfsOptions"
0x14004e3e7  xor     sil, sil
0x14004e3ea  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14004e3ee  call    cs:__imp_RtlInitUnicodeString
0x14004e3f5  nop     dword ptr [rax+rax+00h]
0x14004e3fa  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14004e3fe  lea     rax, [rbp+57h+arg_18]
0x14004e402  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x14004e407  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14004e40b  mov     r9, rdi; KeyValueInformation
0x14004e40e  mov     [rsp+0D0h+Length], ebx; Length
0x14004e412  mov     r8d, 2; KeyValueInformationClass
0x14004e418  call    cs:__imp_ZwQueryValueKey
0x14004e41f  nop     dword ptr [rax+rax+00h]
0x14004e424  mov     ebx, eax
0x14004e426  test    eax, eax
0x14004e428  js      short loc_14004E43F
0x14004e42a  cmp     dword ptr [rdi+4], 4
0x14004e42e  jnz     short loc_14004E43F
0x14004e430  mov     eax, [rdi+0Ch]
0x14004e433  test    al, 1
0x14004e435  jz      short loc_14004E43F
0x14004e437  call    EfsTriggerServiceStart
0x14004e43c  mov     sil, 1
0x14004e43f  xor     edx, edx; Tag
0x14004e441  mov     rcx, rdi; P
0x14004e444  call    cs:__imp_ExFreePoolWithTag
0x14004e44b  nop     dword ptr [rax+rax+00h]
0x14004e450  test    sil, sil
0x14004e453  jnz     short loc_14004E4A0
0x14004e455  lea     rax, [rbp+57h+arg_8]
0x14004e459  xor     r8d, r8d
0x14004e45c  mov     [rsp+0D0h+ResultLength], rax
0x14004e461  lea     r9, [rbp+57h+var_90]
0x14004e465  lea     rax, [rbp+57h+arg_10]
0x14004e469  xor     edx, edx
0x14004e46b  lea     rcx, WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x14004e472  mov     qword ptr [rsp+0D0h+Length], rax
0x14004e477  call    cs:__imp_ZwQueryWnfStateData
0x14004e47e  nop     dword ptr [rax+rax+00h]
0x14004e483  mov     ebx, eax
0x14004e485  test    eax, eax
0x14004e487  js      short loc_14004E4A0
0x14004e489  cmp     [rbp+57h+arg_8], 4
0x14004e48d  jnz     short loc_14004E4A0
0x14004e48f  mov     eax, [rbp+57h+arg_10]
0x14004e492  test    eax, eax
0x14004e494  jz      short loc_14004E4A0
0x14004e496  cmp     eax, 4
0x14004e499  jge     short loc_14004E4A0
0x14004e49b  call    EfsTriggerServiceStart
0x14004e4a0  mov     rcx, [rbp+57h+Handle]; Handle
0x14004e4a4  test    rcx, rcx
0x14004e4a7  jz      short loc_14004E4B5
0x14004e4a9  call    cs:__imp_ZwClose
0x14004e4b0  nop     dword ptr [rax+rax+00h]
0x14004e4b5  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14004e4b9  test    rcx, rcx
0x14004e4bc  jz      short loc_14004E4CA
0x14004e4be  call    cs:__imp_ZwClose
0x14004e4c5  nop     dword ptr [rax+rax+00h]
0x14004e4ca  mov     ecx, ebx; ExitStatus
0x14004e4cc  call    cs:__imp_PsTerminateSystemThread
0x14004e4d3  nop     dword ptr [rax+rax+00h]
0x14004e4d8  mov     rbx, [rsp+0D0h+arg_0]
0x14004e4e0  add     rsp, 0C0h
0x14004e4e7  pop     rdi
0x14004e4e8  pop     rsi
0x14004e4e9  pop     rbp
0x14004e4ea  retn
```
