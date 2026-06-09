# CipInitializeDriverStoreCatalogStores

- ea: `0x18005e060`
- end: `0x18005e312`
- name: `CipInitializeDriverStoreCatalogStores`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180061894`
- `0x1800e2e48`

## callees

- `0x18005e060`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005e0a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005e0a7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005e217`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005e217`
- `ntoskrnl!ExAllocatePool2` at `0x18005e115`
- `ntoskrnl!ExAllocatePool2` at `0x18005e1b7`
- `ntoskrnl!ExAllocatePool2` at `0x18005e1f7`
- `ntoskrnl!ExAllocatePool2` at `0x18005e115`
- `ntoskrnl!ExAllocatePool2` at `0x18005e1b7`
- `ntoskrnl!ExAllocatePool2` at `0x18005e1f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e2bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e2f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e2bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e2f1`
- `ntoskrnl!ZwClose` at `0x18005e2da`
- `ntoskrnl!ZwClose` at `0x18005e2da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e22d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e23f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e255`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e22d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e23f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e255`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005e26b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005e26b`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x18005e15b`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x18005e15b`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x18005e0e1`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x18005e0e1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005e196`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005e196`

## string_xrefs

- `0x18005e261`: `System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
__int64 CipInitializeDriverStoreCatalogStores()
{
  UNICODE_STRING *Pool2; // rdi
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  BOOLEAN RestartScan; // al
  NTSTATUS v4; // eax
  const UNICODE_STRING *i; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rsi
  struct _UNICODE_STRING *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ReturnLength; // [rsp+C0h] [rbp+40h] BYREF
  ULONG Context; // [rsp+C8h] [rbp+48h] BYREF
  void *DirectoryHandle; // [rsp+D0h] [rbp+50h] BYREF

  DirectoryHandle = 0;
  Pool2 = 0;
  Context = 0;
  DestinationString = 0;
  ReturnLength = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\DriverStore\\Nodes");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenDirectoryObject(&DirectoryHandle, 1u, &ObjectAttributes);
  v2 = v1;
  if ( v1 == -1073741766 )
    goto LABEL_19;
  if ( v1 < 0 )
    goto LABEL_20;
  Pool2 = (UNICODE_STRING *)ExAllocatePool2(256, 1024, 1919109443);
  if ( !Pool2 )
    goto LABEL_4;
  RestartScan = 1;
LABEL_6:
  v4 = ZwQueryDirectoryObject(DirectoryHandle, Pool2, 0x400u, 1u, RestartScan, &Context, &ReturnLength);
  v2 = v4;
  if ( v4 == -2147483622 )
  {
LABEL_19:
    v2 = 0;
    goto LABEL_20;
  }
  if ( v4 < 0 )
    goto LABEL_20;
  for ( i = Pool2; ; i += 2 )
  {
    if ( !i->Length )
    {
      RestartScan = 0;
      goto LABEL_6;
    }
    if ( !RtlEqualUnicodeString(i, &stru_180030520, 1u) )
      break;
LABEL_15:
    ;
  }
  v6 = ExAllocatePool2(256, 40, 1919109443);
  v7 = (_QWORD *)v6;
  if ( !v6 )
    goto LABEL_4;
  *(_DWORD *)v6 = 42;
  v8 = (struct _UNICODE_STRING *)(v6 + 8);
  *(_WORD *)(v6 + 8) = 0;
  v9 = (unsigned __int16)(i->Length + DestinationString.Length + 118);
  *(_WORD *)(v6 + 10) = v9;
  v10 = ExAllocatePool2(258, v9, 1919109443);
  v7[2] = v10;
  if ( v10 )
  {
    RtlCopyUnicodeString(v8, &DestinationString);
    RtlAppendUnicodeStringToString(v8, &Source);
    RtlAppendUnicodeStringToString(v8, i);
    RtlAppendUnicodeStringToString(v8, &Source);
    RtlAppendUnicodeToString(v8, L"System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\");
    v11 = (_QWORD *)qword_180049788;
    if ( *(__int64 **)qword_180049788 != &qword_180049780 )
      __fastfail(3u);
    v7[3] = &qword_180049780;
    v7[4] = v11;
    *v11 = v7 + 3;
    qword_180049788 = (__int64)(v7 + 3);
    goto LABEL_15;
  }
  ExFreePoolWithTag(v7, 0x72634943u);
LABEL_4:
  v2 = -1073741801;
LABEL_20:
  if ( DirectoryHandle )
    ZwClose(DirectoryHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72634943u);
  return v2;
}

```

## disassembly

```asm
0x18005e060  push    rbp
0x18005e062  push    rbx
0x18005e063  push    rsi
0x18005e064  push    rdi
0x18005e065  push    r12
0x18005e067  push    r14
0x18005e069  push    r15
0x18005e06b  mov     rbp, rsp
0x18005e06e  sub     rsp, 80h
0x18005e075  xorps   xmm0, xmm0
0x18005e078  lea     rdx, SourceString; "\\DriverStore\\Nodes"
0x18005e07f  xor     r15d, r15d
0x18005e082  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005e086  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18005e08a  xor     eax, eax
0x18005e08c  mov     [rbp+DirectoryHandle], r15
0x18005e090  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18005e094  mov     edi, r15d
0x18005e097  mov     [rbp+arg_8], r15d
0x18005e09b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005e09f  mov     [rbp+arg_0], r15d
0x18005e0a3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18005e0a7  call    cs:__imp_RtlInitUnicodeString
0x18005e0ae  nop     dword ptr [rax+rax+00h]
0x18005e0b3  lea     rax, [rbp+DestinationString]
0x18005e0b7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005e0be  xorps   xmm0, xmm0
0x18005e0c1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005e0c5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005e0c9  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x18005e0cd  lea     edx, [r15+1]; DesiredAccess
0x18005e0d1  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18005e0d8  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x18005e0dc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e0e1  call    cs:__imp_ZwOpenDirectoryObject
0x18005e0e8  nop     dword ptr [rax+rax+00h]
0x18005e0ed  mov     ebx, eax
0x18005e0ef  mov     r12d, 72634943h
0x18005e0f5  cmp     eax, 0C000003Ah
0x18005e0fa  jz      loc_18005E2CE
0x18005e100  test    eax, eax
0x18005e102  js      loc_18005E2D1
0x18005e108  mov     r8d, r12d
0x18005e10b  mov     edx, 400h
0x18005e110  mov     ecx, 100h
0x18005e115  call    cs:__imp_ExAllocatePool2
0x18005e11c  nop     dword ptr [rax+rax+00h]
0x18005e121  mov     rdi, rax
0x18005e124  test    rax, rax
0x18005e127  jnz     short loc_18005E133
0x18005e129  mov     ebx, 0C0000017h
0x18005e12e  jmp     loc_18005E2D1
0x18005e133  mov     al, 1
0x18005e135  lea     rcx, [rbp+arg_0]
0x18005e139  mov     r9b, 1; ReturnSingleEntry
0x18005e13c  mov     [rsp+80h+ReturnLength], rcx; ReturnLength
0x18005e141  mov     r8d, 400h; BufferLength
0x18005e147  lea     rcx, [rbp+arg_8]
0x18005e14b  mov     rdx, rdi; Buffer
0x18005e14e  mov     [rsp+80h+Context], rcx; Context
0x18005e153  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x18005e157  mov     [rsp+80h+RestartScan], al; RestartScan
0x18005e15b  call    cs:__imp_ZwQueryDirectoryObject
0x18005e162  nop     dword ptr [rax+rax+00h]
0x18005e167  mov     ebx, eax
0x18005e169  cmp     eax, 8000001Ah
0x18005e16e  jz      loc_18005E2CE
0x18005e174  test    eax, eax
0x18005e176  js      loc_18005E2D1
0x18005e17c  mov     rbx, rdi
0x18005e17f  cmp     [rbx], r15w
0x18005e183  jz      loc_18005E2A8
0x18005e189  mov     r8b, 1; CaseInSensitive
0x18005e18c  lea     rdx, stru_180030520; String2
0x18005e193  mov     rcx, rbx; String1
0x18005e196  call    cs:__imp_RtlEqualUnicodeString
0x18005e19d  nop     dword ptr [rax+rax+00h]
0x18005e1a2  test    al, al
0x18005e1a4  jnz     loc_18005E29F
0x18005e1aa  mov     r8d, r12d
0x18005e1ad  mov     edx, 28h ; '('
0x18005e1b2  mov     ecx, 100h
0x18005e1b7  call    cs:__imp_ExAllocatePool2
0x18005e1be  nop     dword ptr [rax+rax+00h]
0x18005e1c3  mov     rsi, rax
0x18005e1c6  test    rax, rax
0x18005e1c9  jz      loc_18005E129
0x18005e1cf  mov     dword ptr [rax], 2Ah ; '*'
0x18005e1d5  lea     r14, [rax+8]
0x18005e1d9  mov     [r14], r15w
0x18005e1dd  mov     r8d, r12d
0x18005e1e0  movzx   ecx, [rbp+DestinationString.Length]
0x18005e1e4  add     cx, 76h ; 'v'
0x18005e1e8  add     cx, [rbx]
0x18005e1eb  movzx   edx, cx
0x18005e1ee  mov     ecx, 102h
0x18005e1f3  mov     [rax+0Ah], dx
0x18005e1f7  call    cs:__imp_ExAllocatePool2
0x18005e1fe  nop     dword ptr [rax+rax+00h]
0x18005e203  mov     [rsi+10h], rax
0x18005e207  test    rax, rax
0x18005e20a  jz      loc_18005E2B7
0x18005e210  lea     rdx, [rbp+DestinationString]; SourceString
0x18005e214  mov     rcx, r14; DestinationString
0x18005e217  call    cs:__imp_RtlCopyUnicodeString
0x18005e21e  nop     dword ptr [rax+rax+00h]
0x18005e223  lea     rdx, Source; Source
0x18005e22a  mov     rcx, r14; Destination
0x18005e22d  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005e234  nop     dword ptr [rax+rax+00h]
0x18005e239  mov     rdx, rbx; Source
0x18005e23c  mov     rcx, r14; Destination
0x18005e23f  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005e246  nop     dword ptr [rax+rax+00h]
0x18005e24b  lea     rdx, Source; Source
0x18005e252  mov     rcx, r14; Destination
0x18005e255  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005e25c  nop     dword ptr [rax+rax+00h]
0x18005e261  lea     rdx, aSystem32Catroo; "System32\\CatRoot\\{F750E6C3-38EE-11D1-"...
0x18005e268  mov     rcx, r14; Destination
0x18005e26b  call    cs:__imp_RtlAppendUnicodeToString
0x18005e272  nop     dword ptr [rax+rax+00h]
0x18005e277  mov     rcx, cs:qword_180049788
0x18005e27e  lea     r14, qword_180049780
0x18005e285  cmp     [rcx], r14
0x18005e288  jnz     short loc_18005E2B0
0x18005e28a  lea     rax, [rsi+18h]
0x18005e28e  mov     [rax], r14
0x18005e291  mov     [rax+8], rcx
0x18005e295  mov     [rcx], rax
0x18005e298  mov     cs:qword_180049788, rax
0x18005e29f  add     rbx, 20h ; ' '
0x18005e2a3  jmp     loc_18005E17F
0x18005e2a8  mov     al, r15b
0x18005e2ab  jmp     loc_18005E135
0x18005e2b0  mov     ecx, 3
0x18005e2b5  int     29h; Win8: RtlFailFast(ecx)
0x18005e2b7  mov     edx, r12d; Tag
0x18005e2ba  mov     rcx, rsi; P
0x18005e2bd  call    cs:__imp_ExFreePoolWithTag
0x18005e2c4  nop     dword ptr [rax+rax+00h]
0x18005e2c9  jmp     loc_18005E129
0x18005e2ce  mov     ebx, r15d
0x18005e2d1  mov     rcx, [rbp+DirectoryHandle]; Handle
0x18005e2d5  test    rcx, rcx
0x18005e2d8  jz      short loc_18005E2E6
0x18005e2da  call    cs:__imp_ZwClose
0x18005e2e1  nop     dword ptr [rax+rax+00h]
0x18005e2e6  test    rdi, rdi
0x18005e2e9  jz      short loc_18005E2FD
0x18005e2eb  mov     edx, r12d; Tag
0x18005e2ee  mov     rcx, rdi; P
0x18005e2f1  call    cs:__imp_ExFreePoolWithTag
0x18005e2f8  nop     dword ptr [rax+rax+00h]
0x18005e2fd  mov     eax, ebx
0x18005e2ff  add     rsp, 80h
0x18005e306  pop     r15
0x18005e308  pop     r14
0x18005e30a  pop     r12
0x18005e30c  pop     rdi
0x18005e30d  pop     rsi
0x18005e30e  pop     rbx
0x18005e30f  pop     rbp
0x18005e310  retn
```
