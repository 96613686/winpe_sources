# EfspCheckEfsPolicy

- ea: `0x1402ee660`
- end: `0x1402ee917`
- name: `EfspCheckEfsPolicy`
- size: `695`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1402ee598`
- `0x1402ee660`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1402ee70d`
- `ntoskrnl!KeDelayExecutionThread` at `0x1402ee70d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ee6cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ee795`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ee819`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ee6cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ee795`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ee819`
- `ntoskrnl!ZwClose` at `0x1402ee8d4`
- `ntoskrnl!ZwClose` at `0x1402ee8e9`
- `ntoskrnl!ZwClose` at `0x1402ee8d4`
- `ntoskrnl!ZwClose` at `0x1402ee8e9`
- `ntoskrnl!ZwOpenKey` at `0x1402ee72d`
- `ntoskrnl!ZwOpenKey` at `0x1402ee7d1`
- `ntoskrnl!ZwOpenKey` at `0x1402ee72d`
- `ntoskrnl!ZwOpenKey` at `0x1402ee7d1`
- `ntoskrnl!ExAllocatePool2` at `0x1402ee7f7`
- `ntoskrnl!ExAllocatePool2` at `0x1402ee7f7`
- `ntoskrnl!ZwQueryValueKey` at `0x1402ee843`
- `ntoskrnl!ZwQueryValueKey` at `0x1402ee843`
- `ntoskrnl!ZwQueryWnfStateData` at `0x1402ee8a2`
- `ntoskrnl!ZwQueryWnfStateData` at `0x1402ee8a2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1402ee77e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1402ee77e`
- `ntoskrnl!PsTerminateSystemThread` at `0x1402ee8f7`
- `ntoskrnl!PsTerminateSystemThread` at `0x1402ee8f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ee86f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ee86f`

## string_xrefs

- `0x1402ee693`: `\Registry\Machine\Software`
- `0x1402ee78a`: `\Registry\Machine\Software\Policies\Microsoft\Windows NT\CurrentVersion\EFS`

## pseudocode

```c
void __fastcall EfspCheckEfsPolicy(PVOID StartContext)
{
  int v1; // ebx
  unsigned int v2; // edi
  NTSTATUS v3; // eax
  __int64 v4; // r9
  _DWORD *Pool2; // rdi
  char v6; // si
  int v7; // [rsp+40h] [rbp-39h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-31h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp+17h] BYREF
  struct _UNICODE_STRING v13; // [rsp+A0h] [rbp+27h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+B0h] [rbp+37h] BYREF
  int v15; // [rsp+E8h] [rbp+6Fh] BYREF
  int v16; // [rsp+F0h] [rbp+77h] BYREF
  ULONG ResultLength; // [rsp+F8h] [rbp+7Fh] BYREF

  Handle = 0;
  ResultLength = 0;
  v1 = 0;
  KeyHandle = 0;
  v7 = 0;
  v16 = 0;
  v13 = 0;
  v15 = 4;
  ValueName = 0;
  Interval.QuadPart = -30000000;
  memset(&ObjectAttributes.Length + 1, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  v2 = 0;
  ObjectAttributes.Attributes = 576;
  while ( v2 < 0x14 )
  {
    v1 = KeDelayExecutionThread(0, 0, &Interval);
    if ( v1 < 0 )
      goto LABEL_20;
    v3 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v1 = v3;
    if ( v3 >= 0 )
      goto LABEL_8;
    if ( v3 != -1073741772 )
      goto LABEL_20;
    ++v2;
  }
  if ( v1 < 0 )
    goto LABEL_20;
LABEL_8:
  ZwUpdateWnfStateData(&WNF_EFS_SOFTWARE_HIVE_AVAILABLE, 0, 0, 0, 0, 0, 0);
  RtlInitUnicodeString(&v13, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows NT\\CurrentVersion\\EFS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v13;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
    goto LABEL_15;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 1024, 1836279365, v4);
  if ( !Pool2 )
    goto LABEL_15;
  v6 = 0;
  RtlInitUnicodeString(&ValueName, L"EfsOptions");
  v1 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength);
  if ( v1 >= 0 && Pool2[1] == 4 && (Pool2[3] & 1) != 0 )
  {
    EfsTriggerServiceStart();
    v6 = 1;
  }
  ExFreePoolWithTag(Pool2, 0);
  if ( !v6 )
  {
LABEL_15:
    v1 = ZwQueryWnfStateData(&WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED, 0, 0, &v7, &v16, &v15);
    if ( v1 >= 0 && v15 == 4 && v16 && v16 < 4 )
      EfsTriggerServiceStart();
  }
LABEL_20:
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  PsTerminateSystemThread(v1);
}

```

## disassembly

```asm
0x1402ee660  mov     [rsp-8+arg_0], rbx
0x1402ee665  push    rbp
0x1402ee666  push    rsi
0x1402ee667  push    rdi
0x1402ee668  lea     rbp, [rsp-47h]
0x1402ee66d  sub     rsp, 0C0h
0x1402ee674  xorps   xmm0, xmm0
0x1402ee677  mov     [rbp+57h+Handle], 0
0x1402ee67f  xorps   xmm1, xmm1
0x1402ee682  mov     [rbp+57h+arg_18], 0
0x1402ee689  xor     ebx, ebx
0x1402ee68b  mov     [rbp+57h+KeyHandle], 0
0x1402ee693  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Software"
0x1402ee69a  mov     [rbp+57h+var_90], ebx
0x1402ee69d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1402ee6a1  mov     [rbp+57h+arg_10], ebx
0x1402ee6a4  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x1402ee6a8  mov     [rbp+57h+arg_8], 4
0x1402ee6af  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1402ee6b3  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFE363C80h
0x1402ee6bb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1402ee6bf  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1402ee6c3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402ee6c7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1402ee6cb  call    cs:__imp_RtlInitUnicodeString
0x1402ee6d2  nop     dword ptr [rax+rax+00h]
0x1402ee6d7  lea     rax, [rbp+57h+DestinationString]
0x1402ee6db  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1402ee6e2  xorps   xmm0, xmm0
0x1402ee6e5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1402ee6e9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402ee6ee  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1402ee6f2  xor     edi, edi
0x1402ee6f4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1402ee6fb  mov     esi, 20019h
0x1402ee700  cmp     edi, 14h
0x1402ee703  jnb     short loc_1402EE74E
0x1402ee705  lea     r8, [rbp+57h+Interval]; Interval
0x1402ee709  xor     edx, edx; Alertable
0x1402ee70b  xor     ecx, ecx; WaitMode
0x1402ee70d  call    cs:__imp_KeDelayExecutionThread
0x1402ee714  nop     dword ptr [rax+rax+00h]
0x1402ee719  mov     ebx, eax
0x1402ee71b  test    eax, eax
0x1402ee71d  js      loc_1402EE8CB
0x1402ee723  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1402ee727  mov     edx, esi; DesiredAccess
0x1402ee729  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1402ee72d  call    cs:__imp_ZwOpenKey
0x1402ee734  nop     dword ptr [rax+rax+00h]
0x1402ee739  mov     ebx, eax
0x1402ee73b  test    eax, eax
0x1402ee73d  jns     short loc_1402EE756
0x1402ee73f  cmp     eax, 0C0000034h
0x1402ee744  jnz     loc_1402EE8CB
0x1402ee74a  inc     edi
0x1402ee74c  jmp     short loc_1402EE700
0x1402ee74e  test    ebx, ebx
0x1402ee750  js      loc_1402EE8CB
0x1402ee756  mov     [rsp+0D0h+var_A0], 0
0x1402ee75e  lea     rcx, WNF_EFS_SOFTWARE_HIVE_AVAILABLE
0x1402ee765  mov     dword ptr [rsp+0D0h+ResultLength], 0
0x1402ee76d  xor     r9d, r9d
0x1402ee770  xor     r8d, r8d
0x1402ee773  mov     qword ptr [rsp+0D0h+Length], 0
0x1402ee77c  xor     edx, edx
0x1402ee77e  call    cs:__imp_ZwUpdateWnfStateData
0x1402ee785  nop     dword ptr [rax+rax+00h]
0x1402ee78a  lea     rdx, aRegistryMachin_11; "\\Registry\\Machine\\Software\\Policies"...
0x1402ee791  lea     rcx, [rbp+57h+var_30]; DestinationString
0x1402ee795  call    cs:__imp_RtlInitUnicodeString
0x1402ee79c  nop     dword ptr [rax+rax+00h]
0x1402ee7a1  lea     rax, [rbp+57h+var_30]
0x1402ee7a5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1402ee7ac  xorps   xmm0, xmm0
0x1402ee7af  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1402ee7b3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1402ee7b7  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1402ee7bf  mov     edx, esi; DesiredAccess
0x1402ee7c1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1402ee7c8  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1402ee7cc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402ee7d1  call    cs:__imp_ZwOpenKey
0x1402ee7d8  nop     dword ptr [rax+rax+00h]
0x1402ee7dd  test    eax, eax
0x1402ee7df  js      loc_1402EE880
0x1402ee7e5  mov     ebx, 400h
0x1402ee7ea  mov     r8d, 6D736645h
0x1402ee7f0  mov     edx, ebx
0x1402ee7f2  mov     ecx, 40h ; '@'
0x1402ee7f7  call    cs:__imp_ExAllocatePool2
0x1402ee7fe  nop     dword ptr [rax+rax+00h]
0x1402ee803  mov     rdi, rax
0x1402ee806  test    rax, rax
0x1402ee809  jz      short loc_1402EE880
0x1402ee80b  lea     rdx, aEfsoptions; "EfsOptions"
0x1402ee812  xor     sil, sil
0x1402ee815  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1402ee819  call    cs:__imp_RtlInitUnicodeString
0x1402ee820  nop     dword ptr [rax+rax+00h]
0x1402ee825  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1402ee829  lea     rax, [rbp+57h+arg_18]
0x1402ee82d  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1402ee832  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1402ee836  mov     r9, rdi; KeyValueInformation
0x1402ee839  mov     [rsp+0D0h+Length], ebx; Length
0x1402ee83d  mov     r8d, 2; KeyValueInformationClass
0x1402ee843  call    cs:__imp_ZwQueryValueKey
0x1402ee84a  nop     dword ptr [rax+rax+00h]
0x1402ee84f  mov     ebx, eax
0x1402ee851  test    eax, eax
0x1402ee853  js      short loc_1402EE86A
0x1402ee855  cmp     dword ptr [rdi+4], 4
0x1402ee859  jnz     short loc_1402EE86A
0x1402ee85b  mov     eax, [rdi+0Ch]
0x1402ee85e  test    al, 1
0x1402ee860  jz      short loc_1402EE86A
0x1402ee862  call    EfsTriggerServiceStart
0x1402ee867  mov     sil, 1
0x1402ee86a  xor     edx, edx; Tag
0x1402ee86c  mov     rcx, rdi; P
0x1402ee86f  call    cs:__imp_ExFreePoolWithTag
0x1402ee876  nop     dword ptr [rax+rax+00h]
0x1402ee87b  test    sil, sil
0x1402ee87e  jnz     short loc_1402EE8CB
0x1402ee880  lea     rax, [rbp+57h+arg_8]
0x1402ee884  xor     r8d, r8d
0x1402ee887  mov     [rsp+0D0h+ResultLength], rax
0x1402ee88c  lea     r9, [rbp+57h+var_90]
0x1402ee890  lea     rax, [rbp+57h+arg_10]
0x1402ee894  xor     edx, edx
0x1402ee896  lea     rcx, WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x1402ee89d  mov     qword ptr [rsp+0D0h+Length], rax
0x1402ee8a2  call    cs:__imp_ZwQueryWnfStateData
0x1402ee8a9  nop     dword ptr [rax+rax+00h]
0x1402ee8ae  mov     ebx, eax
0x1402ee8b0  test    eax, eax
0x1402ee8b2  js      short loc_1402EE8CB
0x1402ee8b4  cmp     [rbp+57h+arg_8], 4
0x1402ee8b8  jnz     short loc_1402EE8CB
0x1402ee8ba  mov     eax, [rbp+57h+arg_10]
0x1402ee8bd  test    eax, eax
0x1402ee8bf  jz      short loc_1402EE8CB
0x1402ee8c1  cmp     eax, 4
0x1402ee8c4  jge     short loc_1402EE8CB
0x1402ee8c6  call    EfsTriggerServiceStart
0x1402ee8cb  mov     rcx, [rbp+57h+Handle]; Handle
0x1402ee8cf  test    rcx, rcx
0x1402ee8d2  jz      short loc_1402EE8E0
0x1402ee8d4  call    cs:__imp_ZwClose
0x1402ee8db  nop     dword ptr [rax+rax+00h]
0x1402ee8e0  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1402ee8e4  test    rcx, rcx
0x1402ee8e7  jz      short loc_1402EE8F5
0x1402ee8e9  call    cs:__imp_ZwClose
0x1402ee8f0  nop     dword ptr [rax+rax+00h]
0x1402ee8f5  mov     ecx, ebx; ExitStatus
0x1402ee8f7  call    cs:__imp_PsTerminateSystemThread
0x1402ee8fe  nop     dword ptr [rax+rax+00h]
0x1402ee903  mov     rbx, [rsp+0D0h+arg_0]
0x1402ee90b  add     rsp, 0C0h
0x1402ee912  pop     rdi
0x1402ee913  pop     rsi
0x1402ee914  pop     rbp
0x1402ee915  retn
```
