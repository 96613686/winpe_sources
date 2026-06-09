# CreateCachedSslProv(CACHED_SSL_PROVIDER *,ushort const *)

- ea: `0x14000a9e4`
- end: `0x14000aaa3`
- name: `?CreateCachedSslProv@@YAJPEAUCACHED_SSL_PROVIDER@@PEBG@Z`
- size: `191`
- prototype: `int(struct CACHED_SSL_PROVIDER *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002510`

## callees

- `0x140006110`
- `0x14000a9e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000aa3e`
- `ntoskrnl!ExAllocatePool2` at `0x14000aa3e`
- `cng!SslFreeObject` at `0x14000aa63`
- `cng!SslFreeObject` at `0x14000aa63`
- `cng!SslOpenProvider` at `0x14000aa0a`
- `cng!SslOpenProvider` at `0x14000aa0a`

## pseudocode

```c
__int64 __fastcall CreateCachedSslProv(struct CACHED_SSL_PROVIDER *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  rsize_t v6; // r15
  wchar_t *Pool2; // rax
  wchar_t *v8; // rsi
  __int64 v9; // rcx
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF

  v11 = 0;
  v4 = SslOpenProvider(&v11, a2, (unsigned int)dword_14001952C);
  if ( v4 )
    goto LABEL_6;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  Pool2 = (wchar_t *)ExAllocatePool2(SslPoolType, 2 * (v5 + 1), 1131180883);
  v8 = Pool2;
  if ( !Pool2 )
  {
    v4 = -2146893056;
LABEL_6:
    v9 = v11;
    goto LABEL_7;
  }
  wcscpy_s(Pool2, v6, a2);
  v9 = 0;
  *(_QWORD *)a1 = v11;
  v11 = 0;
  *((_QWORD *)a1 + 1) = v8;
LABEL_7:
  if ( v9 )
    SslFreeObject(v9, 0);
  return v4;
}

```

## disassembly

```asm
0x14000a9e4  push    rbx
0x14000a9e6  push    rbp
0x14000a9e7  push    rsi
0x14000a9e8  push    rdi
0x14000a9e9  push    r14
0x14000a9eb  push    r15
0x14000a9ed  sub     rsp, 28h
0x14000a9f1  mov     r8d, cs:dword_14001952C
0x14000a9f8  mov     r14, rcx
0x14000a9fb  xor     ebp, ebp
0x14000a9fd  lea     rcx, [rsp+58h+arg_10]
0x14000aa02  mov     [rsp+58h+arg_10], rbp
0x14000aa07  mov     rdi, rdx
0x14000aa0a  call    cs:__imp_SslOpenProvider
0x14000aa11  nop     dword ptr [rax+rax+00h]
0x14000aa16  mov     ebx, eax
0x14000aa18  test    eax, eax
0x14000aa1a  jnz     short loc_14000AA57
0x14000aa1c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000aa20  inc     rdx
0x14000aa23  cmp     [rdi+rdx*2], bp
0x14000aa27  jnz     short loc_14000AA20
0x14000aa29  mov     rcx, cs:?SslPoolType@@3_KA; unsigned __int64 SslPoolType
0x14000aa30  lea     r15, [rdx+1]
0x14000aa34  lea     rdx, [r15+r15]
0x14000aa38  mov     r8d, 436C7353h
0x14000aa3e  call    cs:__imp_ExAllocatePool2
0x14000aa45  nop     dword ptr [rax+rax+00h]
0x14000aa4a  mov     rsi, rax
0x14000aa4d  test    rax, rax
0x14000aa50  jnz     short loc_14000AA7F
0x14000aa52  mov     ebx, 80090300h
0x14000aa57  mov     rcx, [rsp+58h+arg_10]
0x14000aa5c  test    rcx, rcx
0x14000aa5f  jz      short loc_14000AA6F
0x14000aa61  xor     edx, edx
0x14000aa63  call    cs:__imp_SslFreeObject
0x14000aa6a  nop     dword ptr [rax+rax+00h]
0x14000aa6f  mov     eax, ebx
0x14000aa71  add     rsp, 28h
0x14000aa75  pop     r15
0x14000aa77  pop     r14
0x14000aa79  pop     rdi
0x14000aa7a  pop     rsi
0x14000aa7b  pop     rbp
0x14000aa7c  pop     rbx
0x14000aa7d  retn
0x14000aa7f  mov     r8, rdi; Src
0x14000aa82  mov     rdx, r15; SizeInWords
0x14000aa85  mov     rcx, rsi; Dst
0x14000aa88  call    wcscpy_s
0x14000aa8d  mov     rax, [rsp+58h+arg_10]
0x14000aa92  mov     rcx, rbp
0x14000aa95  mov     [r14], rax
0x14000aa98  mov     [rsp+58h+arg_10], rcx
0x14000aa9d  mov     [r14+8], rsi
0x14000aaa1  jmp     short loc_14000AA5C
```
