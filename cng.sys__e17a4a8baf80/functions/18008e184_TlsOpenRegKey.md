# TlsOpenRegKey

- ea: `0x18008e184`
- end: `0x18008e2e1`
- name: `TlsOpenRegKey`
- size: `349`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR, PHANDLE KeyHandle)`
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004fd80`
- `0x18008b618`
- `0x18008c514`
- `0x18008e364`
- `0x18008e740`
- `0x18008ebd0`
- `0x18008f00c`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18008e184`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18008e1c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008e1c2`
- `ntoskrnl!ZwOpenKey` at `0x18008e2b5`
- `ntoskrnl!ZwOpenKey` at `0x18008e2b5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18008e251`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18008e267`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18008e279`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18008e251`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18008e267`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18008e279`

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
0x18008e184  mov     rax, rsp
0x18008e187  push    rbx
0x18008e188  push    rsi
0x18008e189  push    rdi
0x18008e18a  push    r12
0x18008e18c  push    r14
0x18008e18e  push    r15
0x18008e190  sub     rsp, 78h
0x18008e194  mov     r15, r8
0x18008e197  mov     rdi, rdx
0x18008e19a  mov     rsi, rcx
0x18008e19d  xorps   xmm0, xmm0
0x18008e1a0  movups  xmmword ptr [rax-80h], xmm0
0x18008e1a4  xor     r12d, r12d
0x18008e1a7  mov     ebx, r12d
0x18008e1aa  movups  xmmword ptr [rax-70h], xmm0
0x18008e1ae  movups  xmmword ptr [rax-60h], xmm0
0x18008e1b2  movups  xmmword ptr [rax-50h], xmm0
0x18008e1b6  test    rdx, rdx
0x18008e1b9  jnz     short loc_18008E1F2
0x18008e1bb  mov     rdx, rcx; SourceString
0x18008e1be  lea     rcx, [rax-80h]; DestinationString
0x18008e1c2  call    cs:__imp_RtlInitUnicodeString
0x18008e1c9  nop     dword ptr [rax+rax+00h]
0x18008e1ce  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18008e1d6  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x18008e1db  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x18008e1e3  lea     rax, [rsp+0A8h+var_80]
0x18008e1e8  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x18008e1ed  jmp     loc_18008E29F
0x18008e1f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e1f6  mov     rcx, rax
0x18008e1f9  inc     rcx
0x18008e1fc  cmp     [rdx+rcx*2], r12w
0x18008e201  jnz     short loc_18008E1F9
0x18008e203  inc     rax
0x18008e206  cmp     [rsi+rax*2], r12w
0x18008e20b  jnz     short loc_18008E203
0x18008e20d  add     eax, ecx
0x18008e20f  lea     r14d, ds:4[rax*2]
0x18008e217  mov     ecx, r14d
0x18008e21a  add     rcx, 10h
0x18008e21e  call    MSCryptAlloc
0x18008e223  mov     rbx, rax
0x18008e226  mov     [rsp+0A8h+var_88], rax
0x18008e22b  test    rax, rax
0x18008e22e  jnz     short loc_18008E23A
0x18008e230  mov     edi, 0C0000017h
0x18008e235  jmp     loc_18008E2C3
0x18008e23a  mov     [rax], r12w
0x18008e23e  mov     [rax+2], r14w
0x18008e243  add     rax, 10h
0x18008e247  mov     [rbx+8], rax
0x18008e24b  mov     rdx, rsi; Source
0x18008e24e  mov     rcx, rbx; Destination
0x18008e251  call    cs:__imp_RtlAppendUnicodeToString
0x18008e258  nop     dword ptr [rax+rax+00h]
0x18008e25d  lea     rdx, asc_1800B5C40; "\\"
0x18008e264  mov     rcx, rbx; Destination
0x18008e267  call    cs:__imp_RtlAppendUnicodeToString
0x18008e26e  nop     dword ptr [rax+rax+00h]
0x18008e273  mov     rdx, rdi; Source
0x18008e276  mov     rcx, rbx; Destination
0x18008e279  call    cs:__imp_RtlAppendUnicodeToString
0x18008e280  nop     dword ptr [rax+rax+00h]
0x18008e285  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18008e28d  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x18008e292  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x18008e29a  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x18008e29f  xorps   xmm0, xmm0
0x18008e2a2  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008e2a8  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x18008e2ad  mov     edx, 20019h; DesiredAccess
0x18008e2b2  mov     rcx, r15; KeyHandle
0x18008e2b5  call    cs:__imp_ZwOpenKey
0x18008e2bc  nop     dword ptr [rax+rax+00h]
0x18008e2c1  mov     edi, eax
0x18008e2c3  test    rbx, rbx
0x18008e2c6  jz      short loc_18008E2D0
0x18008e2c8  mov     rcx, rbx; P
0x18008e2cb  call    MSCryptFree
0x18008e2d0  mov     eax, edi
0x18008e2d2  add     rsp, 78h
0x18008e2d6  pop     r15
0x18008e2d8  pop     r14
0x18008e2da  pop     r12
0x18008e2dc  pop     rdi
0x18008e2dd  pop     rsi
0x18008e2de  pop     rbx
0x18008e2df  retn
0x1800a5038  push    rbp
0x1800a503a  sub     rsp, 20h
0x1800a503e  mov     rbp, rdx
0x1800a5041  add     rsp, 20h
0x1800a5045  pop     rbp
0x1800a5046  retn
```
