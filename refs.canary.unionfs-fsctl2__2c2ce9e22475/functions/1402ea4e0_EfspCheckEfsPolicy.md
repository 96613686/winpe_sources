# EfspCheckEfsPolicy

- ea: `0x1402ea4e0`
- end: `0x1402ea797`
- name: `EfspCheckEfsPolicy`
- size: `695`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1402ea418`
- `0x1402ea4e0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1402ea58d`
- `ntoskrnl!KeDelayExecutionThread` at `0x1402ea58d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ea54b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ea615`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ea699`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ea54b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ea615`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ea699`
- `ntoskrnl!ZwClose` at `0x1402ea754`
- `ntoskrnl!ZwClose` at `0x1402ea769`
- `ntoskrnl!ZwClose` at `0x1402ea754`
- `ntoskrnl!ZwClose` at `0x1402ea769`
- `ntoskrnl!ZwOpenKey` at `0x1402ea5ad`
- `ntoskrnl!ZwOpenKey` at `0x1402ea651`
- `ntoskrnl!ZwOpenKey` at `0x1402ea5ad`
- `ntoskrnl!ZwOpenKey` at `0x1402ea651`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea677`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea677`
- `ntoskrnl!ZwQueryValueKey` at `0x1402ea6c3`
- `ntoskrnl!ZwQueryValueKey` at `0x1402ea6c3`
- `ntoskrnl!ZwQueryWnfStateData` at `0x1402ea722`
- `ntoskrnl!ZwQueryWnfStateData` at `0x1402ea722`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1402ea5fe`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1402ea5fe`
- `ntoskrnl!PsTerminateSystemThread` at `0x1402ea777`
- `ntoskrnl!PsTerminateSystemThread` at `0x1402ea777`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ea6ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ea6ef`

## string_xrefs

- `0x1402ea513`: `\Registry\Machine\Software`
- `0x1402ea60a`: `\Registry\Machine\Software\Policies\Microsoft\Windows NT\CurrentVersion\EFS`

## pseudocode

```c
void __fastcall EfspCheckEfsPolicy(PVOID StartContext)
{
  int v1; // ebx
  unsigned int v2; // edi
  NTSTATUS v3; // eax
  _DWORD *Pool2; // rdi
  char v5; // si
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
  v1 = 0;
  KeyHandle = 0;
  v6 = 0;
  v15 = 0;
  v12 = 0;
  v14 = 4;
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
  RtlInitUnicodeString(&v12, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows NT\\CurrentVersion\\EFS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v12;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
    goto LABEL_15;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 1024, 1836279365);
  if ( !Pool2 )
    goto LABEL_15;
  v5 = 0;
  RtlInitUnicodeString(&ValueName, L"EfsOptions");
  v1 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength);
  if ( v1 >= 0 && Pool2[1] == 4 && (Pool2[3] & 1) != 0 )
  {
    EfsTriggerServiceStart();
    v5 = 1;
  }
  ExFreePoolWithTag(Pool2, 0);
  if ( !v5 )
  {
LABEL_15:
    v1 = ZwQueryWnfStateData(&WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED, 0, 0, &v6, &v15, &v14);
    if ( v1 >= 0 && v14 == 4 && v15 && v15 < 4 )
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
0x1402ea4e0  mov     [rsp-8+arg_0], rbx
0x1402ea4e5  push    rbp
0x1402ea4e6  push    rsi
0x1402ea4e7  push    rdi
0x1402ea4e8  lea     rbp, [rsp-47h]
0x1402ea4ed  sub     rsp, 0C0h
0x1402ea4f4  xorps   xmm0, xmm0
0x1402ea4f7  mov     [rbp+57h+Handle], 0
0x1402ea4ff  xorps   xmm1, xmm1
0x1402ea502  mov     [rbp+57h+arg_18], 0
0x1402ea509  xor     ebx, ebx
0x1402ea50b  mov     [rbp+57h+KeyHandle], 0
0x1402ea513  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Software"
0x1402ea51a  mov     [rbp+57h+var_90], ebx
0x1402ea51d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1402ea521  mov     [rbp+57h+arg_10], ebx
0x1402ea524  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x1402ea528  mov     [rbp+57h+arg_8], 4
0x1402ea52f  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1402ea533  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFE363C80h
0x1402ea53b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1402ea53f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1402ea543  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402ea547  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1402ea54b  call    cs:__imp_RtlInitUnicodeString
0x1402ea552  nop     dword ptr [rax+rax+00h]
0x1402ea557  lea     rax, [rbp+57h+DestinationString]
0x1402ea55b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1402ea562  xorps   xmm0, xmm0
0x1402ea565  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1402ea569  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402ea56e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1402ea572  xor     edi, edi
0x1402ea574  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1402ea57b  mov     esi, 20019h
0x1402ea580  cmp     edi, 14h
0x1402ea583  jnb     short loc_1402EA5CE
0x1402ea585  lea     r8, [rbp+57h+Interval]; Interval
0x1402ea589  xor     edx, edx; Alertable
0x1402ea58b  xor     ecx, ecx; WaitMode
0x1402ea58d  call    cs:__imp_KeDelayExecutionThread
0x1402ea594  nop     dword ptr [rax+rax+00h]
0x1402ea599  mov     ebx, eax
0x1402ea59b  test    eax, eax
0x1402ea59d  js      loc_1402EA74B
0x1402ea5a3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1402ea5a7  mov     edx, esi; DesiredAccess
0x1402ea5a9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1402ea5ad  call    cs:__imp_ZwOpenKey
0x1402ea5b4  nop     dword ptr [rax+rax+00h]
0x1402ea5b9  mov     ebx, eax
0x1402ea5bb  test    eax, eax
0x1402ea5bd  jns     short loc_1402EA5D6
0x1402ea5bf  cmp     eax, 0C0000034h
0x1402ea5c4  jnz     loc_1402EA74B
0x1402ea5ca  inc     edi
0x1402ea5cc  jmp     short loc_1402EA580
0x1402ea5ce  test    ebx, ebx
0x1402ea5d0  js      loc_1402EA74B
0x1402ea5d6  mov     [rsp+0D0h+var_A0], 0
0x1402ea5de  lea     rcx, WNF_EFS_SOFTWARE_HIVE_AVAILABLE
0x1402ea5e5  mov     dword ptr [rsp+0D0h+ResultLength], 0
0x1402ea5ed  xor     r9d, r9d
0x1402ea5f0  xor     r8d, r8d
0x1402ea5f3  mov     qword ptr [rsp+0D0h+Length], 0
0x1402ea5fc  xor     edx, edx
0x1402ea5fe  call    cs:__imp_ZwUpdateWnfStateData
0x1402ea605  nop     dword ptr [rax+rax+00h]
0x1402ea60a  lea     rdx, aRegistryMachin_11; "\\Registry\\Machine\\Software\\Policies"...
0x1402ea611  lea     rcx, [rbp+57h+var_30]; DestinationString
0x1402ea615  call    cs:__imp_RtlInitUnicodeString
0x1402ea61c  nop     dword ptr [rax+rax+00h]
0x1402ea621  lea     rax, [rbp+57h+var_30]
0x1402ea625  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1402ea62c  xorps   xmm0, xmm0
0x1402ea62f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1402ea633  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1402ea637  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1402ea63f  mov     edx, esi; DesiredAccess
0x1402ea641  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1402ea648  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1402ea64c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402ea651  call    cs:__imp_ZwOpenKey
0x1402ea658  nop     dword ptr [rax+rax+00h]
0x1402ea65d  test    eax, eax
0x1402ea65f  js      loc_1402EA700
0x1402ea665  mov     ebx, 400h
0x1402ea66a  mov     r8d, 6D736645h
0x1402ea670  mov     edx, ebx
0x1402ea672  mov     ecx, 40h ; '@'
0x1402ea677  call    cs:__imp_ExAllocatePool2
0x1402ea67e  nop     dword ptr [rax+rax+00h]
0x1402ea683  mov     rdi, rax
0x1402ea686  test    rax, rax
0x1402ea689  jz      short loc_1402EA700
0x1402ea68b  lea     rdx, aEfsoptions; "EfsOptions"
0x1402ea692  xor     sil, sil
0x1402ea695  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1402ea699  call    cs:__imp_RtlInitUnicodeString
0x1402ea6a0  nop     dword ptr [rax+rax+00h]
0x1402ea6a5  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1402ea6a9  lea     rax, [rbp+57h+arg_18]
0x1402ea6ad  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1402ea6b2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1402ea6b6  mov     r9, rdi; KeyValueInformation
0x1402ea6b9  mov     [rsp+0D0h+Length], ebx; Length
0x1402ea6bd  mov     r8d, 2; KeyValueInformationClass
0x1402ea6c3  call    cs:__imp_ZwQueryValueKey
0x1402ea6ca  nop     dword ptr [rax+rax+00h]
0x1402ea6cf  mov     ebx, eax
0x1402ea6d1  test    eax, eax
0x1402ea6d3  js      short loc_1402EA6EA
0x1402ea6d5  cmp     dword ptr [rdi+4], 4
0x1402ea6d9  jnz     short loc_1402EA6EA
0x1402ea6db  mov     eax, [rdi+0Ch]
0x1402ea6de  test    al, 1
0x1402ea6e0  jz      short loc_1402EA6EA
0x1402ea6e2  call    EfsTriggerServiceStart
0x1402ea6e7  mov     sil, 1
0x1402ea6ea  xor     edx, edx; Tag
0x1402ea6ec  mov     rcx, rdi; P
0x1402ea6ef  call    cs:__imp_ExFreePoolWithTag
0x1402ea6f6  nop     dword ptr [rax+rax+00h]
0x1402ea6fb  test    sil, sil
0x1402ea6fe  jnz     short loc_1402EA74B
0x1402ea700  lea     rax, [rbp+57h+arg_8]
0x1402ea704  xor     r8d, r8d
0x1402ea707  mov     [rsp+0D0h+ResultLength], rax
0x1402ea70c  lea     r9, [rbp+57h+var_90]
0x1402ea710  lea     rax, [rbp+57h+arg_10]
0x1402ea714  xor     edx, edx
0x1402ea716  lea     rcx, WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x1402ea71d  mov     qword ptr [rsp+0D0h+Length], rax
0x1402ea722  call    cs:__imp_ZwQueryWnfStateData
0x1402ea729  nop     dword ptr [rax+rax+00h]
0x1402ea72e  mov     ebx, eax
0x1402ea730  test    eax, eax
0x1402ea732  js      short loc_1402EA74B
0x1402ea734  cmp     [rbp+57h+arg_8], 4
0x1402ea738  jnz     short loc_1402EA74B
0x1402ea73a  mov     eax, [rbp+57h+arg_10]
0x1402ea73d  test    eax, eax
0x1402ea73f  jz      short loc_1402EA74B
0x1402ea741  cmp     eax, 4
0x1402ea744  jge     short loc_1402EA74B
0x1402ea746  call    EfsTriggerServiceStart
0x1402ea74b  mov     rcx, [rbp+57h+Handle]; Handle
0x1402ea74f  test    rcx, rcx
0x1402ea752  jz      short loc_1402EA760
0x1402ea754  call    cs:__imp_ZwClose
0x1402ea75b  nop     dword ptr [rax+rax+00h]
0x1402ea760  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1402ea764  test    rcx, rcx
0x1402ea767  jz      short loc_1402EA775
0x1402ea769  call    cs:__imp_ZwClose
0x1402ea770  nop     dword ptr [rax+rax+00h]
0x1402ea775  mov     ecx, ebx; ExitStatus
0x1402ea777  call    cs:__imp_PsTerminateSystemThread
0x1402ea77e  nop     dword ptr [rax+rax+00h]
0x1402ea783  mov     rbx, [rsp+0D0h+arg_0]
0x1402ea78b  add     rsp, 0C0h
0x1402ea792  pop     rdi
0x1402ea793  pop     rsi
0x1402ea794  pop     rbp
0x1402ea795  retn
```
