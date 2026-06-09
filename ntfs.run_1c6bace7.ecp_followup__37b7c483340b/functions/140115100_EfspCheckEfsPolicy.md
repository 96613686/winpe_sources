# EfspCheckEfsPolicy

- ea: `0x140115100`
- end: `0x1401153b7`
- name: `EfspCheckEfsPolicy`
- size: `695`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140115100`
- `0x140270e84`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140115374`
- `ntoskrnl!ZwClose` at `0x140115389`
- `ntoskrnl!ZwClose` at `0x140115374`
- `ntoskrnl!ZwClose` at `0x140115389`
- `ntoskrnl!ZwOpenKey` at `0x1401151cd`
- `ntoskrnl!ZwOpenKey` at `0x140115271`
- `ntoskrnl!ZwOpenKey` at `0x1401151cd`
- `ntoskrnl!ZwOpenKey` at `0x140115271`
- `ntoskrnl!ZwQueryValueKey` at `0x1401152e3`
- `ntoskrnl!ZwQueryValueKey` at `0x1401152e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011516b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140115235`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401152b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011516b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140115235`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401152b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011530f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011530f`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401151ad`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401151ad`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011521e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011521e`
- `ntoskrnl!ZwQueryWnfStateData` at `0x140115342`
- `ntoskrnl!ZwQueryWnfStateData` at `0x140115342`
- `ntoskrnl!ExAllocatePool2` at `0x140115297`
- `ntoskrnl!ExAllocatePool2` at `0x140115297`
- `ntoskrnl!PsTerminateSystemThread` at `0x140115397`
- `ntoskrnl!PsTerminateSystemThread` at `0x140115397`

## string_xrefs

- `0x14011522a`: `\Registry\Machine\Software\Policies\Microsoft\Windows NT\CurrentVersion\EFS`
- `0x140115133`: `\Registry\Machine\Software`

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
0x140115100  mov     [rsp-8+arg_0], rbx
0x140115105  push    rbp
0x140115106  push    rsi
0x140115107  push    rdi
0x140115108  lea     rbp, [rsp-47h]
0x14011510d  sub     rsp, 0C0h
0x140115114  xorps   xmm0, xmm0
0x140115117  mov     [rbp+57h+Handle], 0
0x14011511f  xorps   xmm1, xmm1
0x140115122  mov     [rbp+57h+arg_18], 0
0x140115129  xor     ebx, ebx
0x14011512b  mov     [rbp+57h+KeyHandle], 0
0x140115133  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\Software"
0x14011513a  mov     [rbp+57h+var_90], ebx
0x14011513d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140115141  mov     [rbp+57h+arg_10], ebx
0x140115144  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x140115148  mov     [rbp+57h+arg_8], 4
0x14011514f  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140115153  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFE363C80h
0x14011515b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14011515f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140115163  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140115167  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14011516b  call    cs:__imp_RtlInitUnicodeString
0x140115172  nop     dword ptr [rax+rax+00h]
0x140115177  lea     rax, [rbp+57h+DestinationString]
0x14011517b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140115182  xorps   xmm0, xmm0
0x140115185  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140115189  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14011518e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140115192  xor     edi, edi
0x140115194  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14011519b  mov     esi, 20019h
0x1401151a0  cmp     edi, 14h
0x1401151a3  jnb     short loc_1401151EE
0x1401151a5  lea     r8, [rbp+57h+Interval]; Interval
0x1401151a9  xor     edx, edx; Alertable
0x1401151ab  xor     ecx, ecx; WaitMode
0x1401151ad  call    cs:__imp_KeDelayExecutionThread
0x1401151b4  nop     dword ptr [rax+rax+00h]
0x1401151b9  mov     ebx, eax
0x1401151bb  test    eax, eax
0x1401151bd  js      loc_14011536B
0x1401151c3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1401151c7  mov     edx, esi; DesiredAccess
0x1401151c9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401151cd  call    cs:__imp_ZwOpenKey
0x1401151d4  nop     dword ptr [rax+rax+00h]
0x1401151d9  mov     ebx, eax
0x1401151db  test    eax, eax
0x1401151dd  jns     short loc_1401151F6
0x1401151df  cmp     eax, 0C0000034h
0x1401151e4  jnz     loc_14011536B
0x1401151ea  inc     edi
0x1401151ec  jmp     short loc_1401151A0
0x1401151ee  test    ebx, ebx
0x1401151f0  js      loc_14011536B
0x1401151f6  mov     [rsp+0D0h+var_A0], 0
0x1401151fe  lea     rcx, WNF_EFS_SOFTWARE_HIVE_AVAILABLE
0x140115205  mov     dword ptr [rsp+0D0h+ResultLength], 0
0x14011520d  xor     r9d, r9d
0x140115210  xor     r8d, r8d
0x140115213  mov     qword ptr [rsp+0D0h+Length], 0
0x14011521c  xor     edx, edx
0x14011521e  call    cs:__imp_ZwUpdateWnfStateData
0x140115225  nop     dword ptr [rax+rax+00h]
0x14011522a  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\Software\\Policies"...
0x140115231  lea     rcx, [rbp+57h+var_30]; DestinationString
0x140115235  call    cs:__imp_RtlInitUnicodeString
0x14011523c  nop     dword ptr [rax+rax+00h]
0x140115241  lea     rax, [rbp+57h+var_30]
0x140115245  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14011524c  xorps   xmm0, xmm0
0x14011524f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140115253  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140115257  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14011525f  mov     edx, esi; DesiredAccess
0x140115261  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140115268  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x14011526c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140115271  call    cs:__imp_ZwOpenKey
0x140115278  nop     dword ptr [rax+rax+00h]
0x14011527d  test    eax, eax
0x14011527f  js      loc_140115320
0x140115285  mov     ebx, 400h
0x14011528a  mov     r8d, 6D736645h
0x140115290  mov     edx, ebx
0x140115292  mov     ecx, 40h ; '@'
0x140115297  call    cs:__imp_ExAllocatePool2
0x14011529e  nop     dword ptr [rax+rax+00h]
0x1401152a3  mov     rdi, rax
0x1401152a6  test    rax, rax
0x1401152a9  jz      short loc_140115320
0x1401152ab  lea     rdx, aEfsoptions; "EfsOptions"
0x1401152b2  xor     sil, sil
0x1401152b5  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1401152b9  call    cs:__imp_RtlInitUnicodeString
0x1401152c0  nop     dword ptr [rax+rax+00h]
0x1401152c5  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1401152c9  lea     rax, [rbp+57h+arg_18]
0x1401152cd  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1401152d2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401152d6  mov     r9, rdi; KeyValueInformation
0x1401152d9  mov     [rsp+0D0h+Length], ebx; Length
0x1401152dd  mov     r8d, 2; KeyValueInformationClass
0x1401152e3  call    cs:__imp_ZwQueryValueKey
0x1401152ea  nop     dword ptr [rax+rax+00h]
0x1401152ef  mov     ebx, eax
0x1401152f1  test    eax, eax
0x1401152f3  js      short loc_14011530A
0x1401152f5  cmp     dword ptr [rdi+4], 4
0x1401152f9  jnz     short loc_14011530A
0x1401152fb  mov     eax, [rdi+0Ch]
0x1401152fe  test    al, 1
0x140115300  jz      short loc_14011530A
0x140115302  call    EfsTriggerServiceStart
0x140115307  mov     sil, 1
0x14011530a  xor     edx, edx; Tag
0x14011530c  mov     rcx, rdi; P
0x14011530f  call    cs:__imp_ExFreePoolWithTag
0x140115316  nop     dword ptr [rax+rax+00h]
0x14011531b  test    sil, sil
0x14011531e  jnz     short loc_14011536B
0x140115320  lea     rax, [rbp+57h+arg_8]
0x140115324  xor     r8d, r8d
0x140115327  mov     [rsp+0D0h+ResultLength], rax
0x14011532c  lea     r9, [rbp+57h+var_90]
0x140115330  lea     rax, [rbp+57h+arg_10]
0x140115334  xor     edx, edx
0x140115336  lea     rcx, WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x14011533d  mov     qword ptr [rsp+0D0h+Length], rax
0x140115342  call    cs:__imp_ZwQueryWnfStateData
0x140115349  nop     dword ptr [rax+rax+00h]
0x14011534e  mov     ebx, eax
0x140115350  test    eax, eax
0x140115352  js      short loc_14011536B
0x140115354  cmp     [rbp+57h+arg_8], 4
0x140115358  jnz     short loc_14011536B
0x14011535a  mov     eax, [rbp+57h+arg_10]
0x14011535d  test    eax, eax
0x14011535f  jz      short loc_14011536B
0x140115361  cmp     eax, 4
0x140115364  jge     short loc_14011536B
0x140115366  call    EfsTriggerServiceStart
0x14011536b  mov     rcx, [rbp+57h+Handle]; Handle
0x14011536f  test    rcx, rcx
0x140115372  jz      short loc_140115380
0x140115374  call    cs:__imp_ZwClose
0x14011537b  nop     dword ptr [rax+rax+00h]
0x140115380  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140115384  test    rcx, rcx
0x140115387  jz      short loc_140115395
0x140115389  call    cs:__imp_ZwClose
0x140115390  nop     dword ptr [rax+rax+00h]
0x140115395  mov     ecx, ebx; ExitStatus
0x140115397  call    cs:__imp_PsTerminateSystemThread
0x14011539e  nop     dword ptr [rax+rax+00h]
0x1401153a3  mov     rbx, [rsp+0D0h+arg_0]
0x1401153ab  add     rsp, 0C0h
0x1401153b2  pop     rdi
0x1401153b3  pop     rsi
0x1401153b4  pop     rbp
0x1401153b5  retn
```
