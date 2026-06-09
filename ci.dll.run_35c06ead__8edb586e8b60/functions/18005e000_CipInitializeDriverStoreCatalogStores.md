# CipInitializeDriverStoreCatalogStores

- ea: `0x18005e000`
- end: `0x18005e2b2`
- name: `CipInitializeDriverStoreCatalogStores`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800619f8`
- `0x1800e2e18`

## callees

- `0x18005e000`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005e047`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005e047`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005e1b7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005e1b7`
- `ntoskrnl!ExAllocatePool2` at `0x18005e0b5`
- `ntoskrnl!ExAllocatePool2` at `0x18005e157`
- `ntoskrnl!ExAllocatePool2` at `0x18005e197`
- `ntoskrnl!ExAllocatePool2` at `0x18005e0b5`
- `ntoskrnl!ExAllocatePool2` at `0x18005e157`
- `ntoskrnl!ExAllocatePool2` at `0x18005e197`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e25d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e291`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e25d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005e291`
- `ntoskrnl!ZwClose` at `0x18005e27a`
- `ntoskrnl!ZwClose` at `0x18005e27a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e1cd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e1df`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e1f5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e1cd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e1df`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005e1f5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005e20b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005e20b`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x18005e0fb`
- `ntoskrnl!ZwQueryDirectoryObject` at `0x18005e0fb`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x18005e081`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x18005e081`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005e136`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005e136`

## string_xrefs

- `0x18005e201`: `System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

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
    if ( !RtlEqualUnicodeString(i, &stru_1800304F0, 1u) )
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
0x18005e000  push    rbp
0x18005e002  push    rbx
0x18005e003  push    rsi
0x18005e004  push    rdi
0x18005e005  push    r12
0x18005e007  push    r14
0x18005e009  push    r15
0x18005e00b  mov     rbp, rsp
0x18005e00e  sub     rsp, 80h
0x18005e015  xorps   xmm0, xmm0
0x18005e018  lea     rdx, SourceString; "\\DriverStore\\Nodes"
0x18005e01f  xor     r15d, r15d
0x18005e022  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005e026  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18005e02a  xor     eax, eax
0x18005e02c  mov     [rbp+DirectoryHandle], r15
0x18005e030  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18005e034  mov     edi, r15d
0x18005e037  mov     [rbp+arg_8], r15d
0x18005e03b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005e03f  mov     [rbp+arg_0], r15d
0x18005e043  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18005e047  call    cs:__imp_RtlInitUnicodeString
0x18005e04e  nop     dword ptr [rax+rax+00h]
0x18005e053  lea     rax, [rbp+DestinationString]
0x18005e057  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005e05e  xorps   xmm0, xmm0
0x18005e061  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005e065  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005e069  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x18005e06d  lea     edx, [r15+1]; DesiredAccess
0x18005e071  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18005e078  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x18005e07c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e081  call    cs:__imp_ZwOpenDirectoryObject
0x18005e088  nop     dword ptr [rax+rax+00h]
0x18005e08d  mov     ebx, eax
0x18005e08f  mov     r12d, 72634943h
0x18005e095  cmp     eax, 0C000003Ah
0x18005e09a  jz      loc_18005E26E
0x18005e0a0  test    eax, eax
0x18005e0a2  js      loc_18005E271
0x18005e0a8  mov     r8d, r12d
0x18005e0ab  mov     edx, 400h
0x18005e0b0  mov     ecx, 100h
0x18005e0b5  call    cs:__imp_ExAllocatePool2
0x18005e0bc  nop     dword ptr [rax+rax+00h]
0x18005e0c1  mov     rdi, rax
0x18005e0c4  test    rax, rax
0x18005e0c7  jnz     short loc_18005E0D3
0x18005e0c9  mov     ebx, 0C0000017h
0x18005e0ce  jmp     loc_18005E271
0x18005e0d3  mov     al, 1
0x18005e0d5  lea     rcx, [rbp+arg_0]
0x18005e0d9  mov     r9b, 1; ReturnSingleEntry
0x18005e0dc  mov     [rsp+80h+ReturnLength], rcx; ReturnLength
0x18005e0e1  mov     r8d, 400h; BufferLength
0x18005e0e7  lea     rcx, [rbp+arg_8]
0x18005e0eb  mov     rdx, rdi; Buffer
0x18005e0ee  mov     [rsp+80h+Context], rcx; Context
0x18005e0f3  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x18005e0f7  mov     [rsp+80h+RestartScan], al; RestartScan
0x18005e0fb  call    cs:__imp_ZwQueryDirectoryObject
0x18005e102  nop     dword ptr [rax+rax+00h]
0x18005e107  mov     ebx, eax
0x18005e109  cmp     eax, 8000001Ah
0x18005e10e  jz      loc_18005E26E
0x18005e114  test    eax, eax
0x18005e116  js      loc_18005E271
0x18005e11c  mov     rbx, rdi
0x18005e11f  cmp     [rbx], r15w
0x18005e123  jz      loc_18005E248
0x18005e129  mov     r8b, 1; CaseInSensitive
0x18005e12c  lea     rdx, stru_1800304F0; String2
0x18005e133  mov     rcx, rbx; String1
0x18005e136  call    cs:__imp_RtlEqualUnicodeString
0x18005e13d  nop     dword ptr [rax+rax+00h]
0x18005e142  test    al, al
0x18005e144  jnz     loc_18005E23F
0x18005e14a  mov     r8d, r12d
0x18005e14d  mov     edx, 28h ; '('
0x18005e152  mov     ecx, 100h
0x18005e157  call    cs:__imp_ExAllocatePool2
0x18005e15e  nop     dword ptr [rax+rax+00h]
0x18005e163  mov     rsi, rax
0x18005e166  test    rax, rax
0x18005e169  jz      loc_18005E0C9
0x18005e16f  mov     dword ptr [rax], 2Ah ; '*'
0x18005e175  lea     r14, [rax+8]
0x18005e179  mov     [r14], r15w
0x18005e17d  mov     r8d, r12d
0x18005e180  movzx   ecx, [rbp+DestinationString.Length]
0x18005e184  add     cx, 76h ; 'v'
0x18005e188  add     cx, [rbx]
0x18005e18b  movzx   edx, cx
0x18005e18e  mov     ecx, 102h
0x18005e193  mov     [rax+0Ah], dx
0x18005e197  call    cs:__imp_ExAllocatePool2
0x18005e19e  nop     dword ptr [rax+rax+00h]
0x18005e1a3  mov     [rsi+10h], rax
0x18005e1a7  test    rax, rax
0x18005e1aa  jz      loc_18005E257
0x18005e1b0  lea     rdx, [rbp+DestinationString]; SourceString
0x18005e1b4  mov     rcx, r14; DestinationString
0x18005e1b7  call    cs:__imp_RtlCopyUnicodeString
0x18005e1be  nop     dword ptr [rax+rax+00h]
0x18005e1c3  lea     rdx, Source; Source
0x18005e1ca  mov     rcx, r14; Destination
0x18005e1cd  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005e1d4  nop     dword ptr [rax+rax+00h]
0x18005e1d9  mov     rdx, rbx; Source
0x18005e1dc  mov     rcx, r14; Destination
0x18005e1df  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005e1e6  nop     dword ptr [rax+rax+00h]
0x18005e1eb  lea     rdx, Source; Source
0x18005e1f2  mov     rcx, r14; Destination
0x18005e1f5  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005e1fc  nop     dword ptr [rax+rax+00h]
0x18005e201  lea     rdx, aSystem32Catroo; "System32\\CatRoot\\{F750E6C3-38EE-11D1-"...
0x18005e208  mov     rcx, r14; Destination
0x18005e20b  call    cs:__imp_RtlAppendUnicodeToString
0x18005e212  nop     dword ptr [rax+rax+00h]
0x18005e217  mov     rcx, cs:qword_180049788
0x18005e21e  lea     r14, qword_180049780
0x18005e225  cmp     [rcx], r14
0x18005e228  jnz     short loc_18005E250
0x18005e22a  lea     rax, [rsi+18h]
0x18005e22e  mov     [rax], r14
0x18005e231  mov     [rax+8], rcx
0x18005e235  mov     [rcx], rax
0x18005e238  mov     cs:qword_180049788, rax
0x18005e23f  add     rbx, 20h ; ' '
0x18005e243  jmp     loc_18005E11F
0x18005e248  mov     al, r15b
0x18005e24b  jmp     loc_18005E0D5
0x18005e250  mov     ecx, 3
0x18005e255  int     29h; Win8: RtlFailFast(ecx)
0x18005e257  mov     edx, r12d; Tag
0x18005e25a  mov     rcx, rsi; P
0x18005e25d  call    cs:__imp_ExFreePoolWithTag
0x18005e264  nop     dword ptr [rax+rax+00h]
0x18005e269  jmp     loc_18005E0C9
0x18005e26e  mov     ebx, r15d
0x18005e271  mov     rcx, [rbp+DirectoryHandle]; Handle
0x18005e275  test    rcx, rcx
0x18005e278  jz      short loc_18005E286
0x18005e27a  call    cs:__imp_ZwClose
0x18005e281  nop     dword ptr [rax+rax+00h]
0x18005e286  test    rdi, rdi
0x18005e289  jz      short loc_18005E29D
0x18005e28b  mov     edx, r12d; Tag
0x18005e28e  mov     rcx, rdi; P
0x18005e291  call    cs:__imp_ExFreePoolWithTag
0x18005e298  nop     dword ptr [rax+rax+00h]
0x18005e29d  mov     eax, ebx
0x18005e29f  add     rsp, 80h
0x18005e2a6  pop     r15
0x18005e2a8  pop     r14
0x18005e2aa  pop     r12
0x18005e2ac  pop     rdi
0x18005e2ad  pop     rsi
0x18005e2ae  pop     rbx
0x18005e2af  pop     rbp
0x18005e2b0  retn
```
