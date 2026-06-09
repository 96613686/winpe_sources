# EfspCheckEfsPolicy

- ea: `0x140115150`
- end: `0x140115407`
- name: `EfspCheckEfsPolicy`
- size: `695`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140115150`
- `0x140270ed4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401153c4`
- `ntoskrnl!ZwClose` at `0x1401153d9`
- `ntoskrnl!ZwClose` at `0x1401153c4`
- `ntoskrnl!ZwClose` at `0x1401153d9`
- `ntoskrnl!ZwOpenKey` at `0x14011521d`
- `ntoskrnl!ZwOpenKey` at `0x1401152c1`
- `ntoskrnl!ZwOpenKey` at `0x14011521d`
- `ntoskrnl!ZwOpenKey` at `0x1401152c1`
- `ntoskrnl!ZwQueryValueKey` at `0x140115333`
- `ntoskrnl!ZwQueryValueKey` at `0x140115333`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401151bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140115285`
- `ntoskrnl!RtlInitUnicodeString` at `0x140115309`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401151bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140115285`
- `ntoskrnl!RtlInitUnicodeString` at `0x140115309`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011535f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011535f`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401151fd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401151fd`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011526e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011526e`
- `ntoskrnl!ZwQueryWnfStateData` at `0x140115392`
- `ntoskrnl!ZwQueryWnfStateData` at `0x140115392`
- `ntoskrnl!ExAllocatePool2` at `0x1401152e7`
- `ntoskrnl!ExAllocatePool2` at `0x1401152e7`
- `ntoskrnl!PsTerminateSystemThread` at `0x1401153e7`
- `ntoskrnl!PsTerminateSystemThread` at `0x1401153e7`

## string_xrefs

- `0x14011527a`: `\Registry\Machine\Software\Policies\Microsoft\Windows NT\CurrentVersion\EFS`
- `0x140115183`: `\Registry\Machine\Software`

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
0x140115150  mov     [rsp-8+arg_0], rbx
0x140115155  push    rbp
0x140115156  push    rsi
0x140115157  push    rdi
0x140115158  lea     rbp, [rsp-47h]
0x14011515d  sub     rsp, 0C0h
0x140115164  xorps   xmm0, xmm0
0x140115167  mov     [rbp+57h+Handle], 0
0x14011516f  xorps   xmm1, xmm1
0x140115172  mov     [rbp+57h+arg_18], 0
0x140115179  xor     ebx, ebx
0x14011517b  mov     [rbp+57h+KeyHandle], 0
0x140115183  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\Software"
0x14011518a  mov     [rbp+57h+var_90], ebx
0x14011518d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140115191  mov     [rbp+57h+arg_10], ebx
0x140115194  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x140115198  mov     [rbp+57h+arg_8], 4
0x14011519f  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1401151a3  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFE363C80h
0x1401151ab  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1401151af  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1401151b3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401151b7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401151bb  call    cs:__imp_RtlInitUnicodeString
0x1401151c2  nop     dword ptr [rax+rax+00h]
0x1401151c7  lea     rax, [rbp+57h+DestinationString]
0x1401151cb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1401151d2  xorps   xmm0, xmm0
0x1401151d5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1401151d9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401151de  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1401151e2  xor     edi, edi
0x1401151e4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1401151eb  mov     esi, 20019h
0x1401151f0  cmp     edi, 14h
0x1401151f3  jnb     short loc_14011523E
0x1401151f5  lea     r8, [rbp+57h+Interval]; Interval
0x1401151f9  xor     edx, edx; Alertable
0x1401151fb  xor     ecx, ecx; WaitMode
0x1401151fd  call    cs:__imp_KeDelayExecutionThread
0x140115204  nop     dword ptr [rax+rax+00h]
0x140115209  mov     ebx, eax
0x14011520b  test    eax, eax
0x14011520d  js      loc_1401153BB
0x140115213  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140115217  mov     edx, esi; DesiredAccess
0x140115219  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14011521d  call    cs:__imp_ZwOpenKey
0x140115224  nop     dword ptr [rax+rax+00h]
0x140115229  mov     ebx, eax
0x14011522b  test    eax, eax
0x14011522d  jns     short loc_140115246
0x14011522f  cmp     eax, 0C0000034h
0x140115234  jnz     loc_1401153BB
0x14011523a  inc     edi
0x14011523c  jmp     short loc_1401151F0
0x14011523e  test    ebx, ebx
0x140115240  js      loc_1401153BB
0x140115246  mov     [rsp+0D0h+var_A0], 0
0x14011524e  lea     rcx, WNF_EFS_SOFTWARE_HIVE_AVAILABLE
0x140115255  mov     dword ptr [rsp+0D0h+ResultLength], 0
0x14011525d  xor     r9d, r9d
0x140115260  xor     r8d, r8d
0x140115263  mov     qword ptr [rsp+0D0h+Length], 0
0x14011526c  xor     edx, edx
0x14011526e  call    cs:__imp_ZwUpdateWnfStateData
0x140115275  nop     dword ptr [rax+rax+00h]
0x14011527a  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\Software\\Policies"...
0x140115281  lea     rcx, [rbp+57h+var_30]; DestinationString
0x140115285  call    cs:__imp_RtlInitUnicodeString
0x14011528c  nop     dword ptr [rax+rax+00h]
0x140115291  lea     rax, [rbp+57h+var_30]
0x140115295  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14011529c  xorps   xmm0, xmm0
0x14011529f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1401152a3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1401152a7  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1401152af  mov     edx, esi; DesiredAccess
0x1401152b1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1401152b8  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1401152bc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401152c1  call    cs:__imp_ZwOpenKey
0x1401152c8  nop     dword ptr [rax+rax+00h]
0x1401152cd  test    eax, eax
0x1401152cf  js      loc_140115370
0x1401152d5  mov     ebx, 400h
0x1401152da  mov     r8d, 6D736645h
0x1401152e0  mov     edx, ebx
0x1401152e2  mov     ecx, 40h ; '@'
0x1401152e7  call    cs:__imp_ExAllocatePool2
0x1401152ee  nop     dword ptr [rax+rax+00h]
0x1401152f3  mov     rdi, rax
0x1401152f6  test    rax, rax
0x1401152f9  jz      short loc_140115370
0x1401152fb  lea     rdx, aEfsoptions; "EfsOptions"
0x140115302  xor     sil, sil
0x140115305  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140115309  call    cs:__imp_RtlInitUnicodeString
0x140115310  nop     dword ptr [rax+rax+00h]
0x140115315  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140115319  lea     rax, [rbp+57h+arg_18]
0x14011531d  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x140115322  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140115326  mov     r9, rdi; KeyValueInformation
0x140115329  mov     [rsp+0D0h+Length], ebx; Length
0x14011532d  mov     r8d, 2; KeyValueInformationClass
0x140115333  call    cs:__imp_ZwQueryValueKey
0x14011533a  nop     dword ptr [rax+rax+00h]
0x14011533f  mov     ebx, eax
0x140115341  test    eax, eax
0x140115343  js      short loc_14011535A
0x140115345  cmp     dword ptr [rdi+4], 4
0x140115349  jnz     short loc_14011535A
0x14011534b  mov     eax, [rdi+0Ch]
0x14011534e  test    al, 1
0x140115350  jz      short loc_14011535A
0x140115352  call    EfsTriggerServiceStart
0x140115357  mov     sil, 1
0x14011535a  xor     edx, edx; Tag
0x14011535c  mov     rcx, rdi; P
0x14011535f  call    cs:__imp_ExFreePoolWithTag
0x140115366  nop     dword ptr [rax+rax+00h]
0x14011536b  test    sil, sil
0x14011536e  jnz     short loc_1401153BB
0x140115370  lea     rax, [rbp+57h+arg_8]
0x140115374  xor     r8d, r8d
0x140115377  mov     [rsp+0D0h+ResultLength], rax
0x14011537c  lea     r9, [rbp+57h+var_90]
0x140115380  lea     rax, [rbp+57h+arg_10]
0x140115384  xor     edx, edx
0x140115386  lea     rcx, WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x14011538d  mov     qword ptr [rsp+0D0h+Length], rax
0x140115392  call    cs:__imp_ZwQueryWnfStateData
0x140115399  nop     dword ptr [rax+rax+00h]
0x14011539e  mov     ebx, eax
0x1401153a0  test    eax, eax
0x1401153a2  js      short loc_1401153BB
0x1401153a4  cmp     [rbp+57h+arg_8], 4
0x1401153a8  jnz     short loc_1401153BB
0x1401153aa  mov     eax, [rbp+57h+arg_10]
0x1401153ad  test    eax, eax
0x1401153af  jz      short loc_1401153BB
0x1401153b1  cmp     eax, 4
0x1401153b4  jge     short loc_1401153BB
0x1401153b6  call    EfsTriggerServiceStart
0x1401153bb  mov     rcx, [rbp+57h+Handle]; Handle
0x1401153bf  test    rcx, rcx
0x1401153c2  jz      short loc_1401153D0
0x1401153c4  call    cs:__imp_ZwClose
0x1401153cb  nop     dword ptr [rax+rax+00h]
0x1401153d0  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1401153d4  test    rcx, rcx
0x1401153d7  jz      short loc_1401153E5
0x1401153d9  call    cs:__imp_ZwClose
0x1401153e0  nop     dword ptr [rax+rax+00h]
0x1401153e5  mov     ecx, ebx; ExitStatus
0x1401153e7  call    cs:__imp_PsTerminateSystemThread
0x1401153ee  nop     dword ptr [rax+rax+00h]
0x1401153f3  mov     rbx, [rsp+0D0h+arg_0]
0x1401153fb  add     rsp, 0C0h
0x140115402  pop     rdi
0x140115403  pop     rsi
0x140115404  pop     rbp
0x140115405  retn
```
