# TlsOpenRegKey

- ea: `0x180083f94`
- end: `0x1800840f1`
- name: `TlsOpenRegKey`
- size: `349`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR, PHANDLE KeyHandle)`
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180045c90`
- `0x180081428`
- `0x180082324`
- `0x180084174`
- `0x180084550`
- `0x1800849e0`
- `0x180084e1c`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180083f94`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180083fd2`
- `ntoskrnl!RtlInitUnicodeString` at `0x180083fd2`
- `ntoskrnl!ZwOpenKey` at `0x1800840c5`
- `ntoskrnl!ZwOpenKey` at `0x1800840c5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180084061`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180084077`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180084089`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180084061`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180084077`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180084089`

## pseudocode

```c
__int64 __fastcall TlsOpenRegKey(PCWSTR Source, PCWSTR a2, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  USHORT v9; // r14
  struct _UNICODE_STRING *v10; // rax
  unsigned int v11; // edi
  struct _UNICODE_STRING v13; // [rsp+28h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-70h] BYREF

  v13 = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a2 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    do
      ++v7;
    while ( Source[v7] );
    v9 = 2 * (v8 + v7) + 4;
    v10 = (struct _UNICODE_STRING *)MSCryptAlloc((unsigned int)(2 * (v8 + v7) + 4) + 16LL, a2);
    v6 = v10;
    if ( !v10 )
    {
      v11 = -1073741801;
      goto LABEL_10;
    }
    v10->Length = 0;
    v10->MaximumLength = v9;
    v10->Buffer = &v10[1].Length;
    RtlAppendUnicodeToString(v10, Source);
    RtlAppendUnicodeToString(v6, L"\\");
    RtlAppendUnicodeToString(v6, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v6;
  }
  else
  {
    RtlInitUnicodeString(&v13, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v13;
  }
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
LABEL_10:
  if ( v6 )
    MSCryptFree(v6);
  return v11;
}

```

## disassembly

```asm
0x180083f94  mov     rax, rsp
0x180083f97  push    rbx
0x180083f98  push    rsi
0x180083f99  push    rdi
0x180083f9a  push    r12
0x180083f9c  push    r14
0x180083f9e  push    r15
0x180083fa0  sub     rsp, 78h
0x180083fa4  mov     r15, r8
0x180083fa7  mov     rdi, rdx
0x180083faa  mov     rsi, rcx
0x180083fad  xorps   xmm0, xmm0
0x180083fb0  movups  xmmword ptr [rax-80h], xmm0
0x180083fb4  xor     r12d, r12d
0x180083fb7  mov     ebx, r12d
0x180083fba  movups  xmmword ptr [rax-70h], xmm0
0x180083fbe  movups  xmmword ptr [rax-60h], xmm0
0x180083fc2  movups  xmmword ptr [rax-50h], xmm0
0x180083fc6  test    rdx, rdx
0x180083fc9  jnz     short loc_180084002
0x180083fcb  mov     rdx, rcx; SourceString
0x180083fce  lea     rcx, [rax-80h]; DestinationString
0x180083fd2  call    cs:__imp_RtlInitUnicodeString
0x180083fd9  nop     dword ptr [rax+rax+00h]
0x180083fde  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180083fe6  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180083feb  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x180083ff3  lea     rax, [rsp+0A8h+var_80]
0x180083ff8  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180083ffd  jmp     loc_1800840AF
0x180084002  or      rax, 0FFFFFFFFFFFFFFFFh
0x180084006  mov     rcx, rax
0x180084009  inc     rcx
0x18008400c  cmp     [rdx+rcx*2], r12w
0x180084011  jnz     short loc_180084009
0x180084013  inc     rax
0x180084016  cmp     [rsi+rax*2], r12w
0x18008401b  jnz     short loc_180084013
0x18008401d  add     eax, ecx
0x18008401f  lea     r14d, ds:4[rax*2]
0x180084027  mov     ecx, r14d
0x18008402a  add     rcx, 10h
0x18008402e  call    MSCryptAlloc
0x180084033  mov     rbx, rax
0x180084036  mov     [rsp+0A8h+var_88], rax
0x18008403b  test    rax, rax
0x18008403e  jnz     short loc_18008404A
0x180084040  mov     edi, 0C0000017h
0x180084045  jmp     loc_1800840D3
0x18008404a  mov     [rax], r12w
0x18008404e  mov     [rax+2], r14w
0x180084053  add     rax, 10h
0x180084057  mov     [rbx+8], rax
0x18008405b  mov     rdx, rsi; Source
0x18008405e  mov     rcx, rbx; Destination
0x180084061  call    cs:__imp_RtlAppendUnicodeToString
0x180084068  nop     dword ptr [rax+rax+00h]
0x18008406d  lea     rdx, asc_1800AE840; "\\"
0x180084074  mov     rcx, rbx; Destination
0x180084077  call    cs:__imp_RtlAppendUnicodeToString
0x18008407e  nop     dword ptr [rax+rax+00h]
0x180084083  mov     rdx, rdi; Source
0x180084086  mov     rcx, rbx; Destination
0x180084089  call    cs:__imp_RtlAppendUnicodeToString
0x180084090  nop     dword ptr [rax+rax+00h]
0x180084095  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18008409d  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x1800840a2  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x1800840aa  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x1800840af  xorps   xmm0, xmm0
0x1800840b2  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800840b8  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800840bd  mov     edx, 20019h; DesiredAccess
0x1800840c2  mov     rcx, r15; KeyHandle
0x1800840c5  call    cs:__imp_ZwOpenKey
0x1800840cc  nop     dword ptr [rax+rax+00h]
0x1800840d1  mov     edi, eax
0x1800840d3  test    rbx, rbx
0x1800840d6  jz      short loc_1800840E0
0x1800840d8  mov     rcx, rbx; P
0x1800840db  call    MSCryptFree
0x1800840e0  mov     eax, edi
0x1800840e2  add     rsp, 78h
0x1800840e6  pop     r15
0x1800840e8  pop     r14
0x1800840ea  pop     r12
0x1800840ec  pop     rdi
0x1800840ed  pop     rsi
0x1800840ee  pop     rbx
0x1800840ef  retn
0x18009e29a  push    rbp
0x18009e29c  sub     rsp, 20h
0x18009e2a0  mov     rbp, rdx
0x18009e2a3  add     rsp, 20h
0x18009e2a7  pop     rbp
0x18009e2a8  retn
```
