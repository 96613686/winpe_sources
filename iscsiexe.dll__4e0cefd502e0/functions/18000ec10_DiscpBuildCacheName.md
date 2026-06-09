# DiscpBuildCacheName

- ea: `0x18000ec10`
- end: `0x18000ecd6`
- name: `DiscpBuildCacheName`
- size: `198`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fbdc`
- `0x180010b5c`

## callees

- `0x18000325c`
- `0x18000bdb0`
- `0x18000ec10`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18000ec63`
- `ISCSIUM!DiscpAllocMemory` at `0x18000ec9f`
- `ISCSIUM!DiscpAllocMemory` at `0x18000ec63`
- `ISCSIUM!DiscpAllocMemory` at `0x18000ec9f`

## pseudocode

```c
__int64 __fastcall DiscpBuildCacheName(__int64 a1, int a2, const wchar_t *a3, wchar_t **a4)
{
  const wchar_t *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // r14d
  wchar_t *v11; // rax
  wchar_t *v12; // rdi
  unsigned int v13; // ebx
  wchar_t *v14; // rax

  if ( a1 )
  {
    v7 = L"*";
    if ( a3 )
      v7 = a3;
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    do
      ++v8;
    while ( *(_WORD *)(a1 + 2 * v8) );
    v10 = v8 + v9 + 11;
    v11 = (wchar_t *)DiscpAllocMemory(2 * v10);
    v12 = v11;
    if ( v11 )
    {
      StringCchPrintfW(v11, v10, L"%ws %8x %ws", a1, a2, v7);
LABEL_12:
      v13 = 0;
      goto LABEL_13;
    }
    v13 = 8;
  }
  else
  {
    v13 = 8;
    v14 = (wchar_t *)DiscpAllocMemory(8);
    v12 = v14;
    if ( v14 )
    {
      StringCchCopyW(v14, 4u, L"All");
      goto LABEL_12;
    }
  }
LABEL_13:
  *a4 = v12;
  return v13;
}

```

## disassembly

```asm
0x18000ec10  push    rbx
0x18000ec12  push    rbp
0x18000ec13  push    rsi
0x18000ec14  push    rdi
0x18000ec15  push    r12
0x18000ec17  push    r14
0x18000ec19  push    r15
0x18000ec1b  sub     rsp, 30h
0x18000ec1f  xor     r12d, r12d
0x18000ec22  mov     r15, r9
0x18000ec25  mov     ebp, edx
0x18000ec27  mov     rbx, rcx
0x18000ec2a  test    rcx, rcx
0x18000ec2d  jz      short loc_18000EC98
0x18000ec2f  test    r8, r8
0x18000ec32  lea     rsi, pszSrc; "*"
0x18000ec39  cmovnz  rsi, r8
0x18000ec3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ec41  mov     rcx, rax
0x18000ec44  inc     rcx
0x18000ec47  cmp     [rsi+rcx*2], r12w
0x18000ec4c  jnz     short loc_18000EC44
0x18000ec4e  inc     rax
0x18000ec51  cmp     [rbx+rax*2], r12w
0x18000ec56  jnz     short loc_18000EC4E
0x18000ec58  lea     r14d, [rcx+0Bh]
0x18000ec5c  add     r14d, eax
0x18000ec5f  lea     ecx, [r14+r14]
0x18000ec63  call    cs:__imp_DiscpAllocMemory
0x18000ec69  mov     rdi, rax
0x18000ec6c  test    rax, rax
0x18000ec6f  jz      short loc_18000EC91
0x18000ec71  mov     edx, r14d; cchDest
0x18000ec74  lea     r8, aWs8xWs; "%ws %8x %ws"
0x18000ec7b  mov     [rsp+68h+var_40], rsi
0x18000ec80  mov     r9, rbx
0x18000ec83  mov     rcx, rax; pszDest
0x18000ec86  mov     [rsp+68h+var_48], ebp
0x18000ec8a  call    StringCchPrintfW
0x18000ec8f  jmp     short loc_18000ECBF
0x18000ec91  mov     ebx, 8
0x18000ec96  jmp     short loc_18000ECC2
0x18000ec98  mov     ebx, 8
0x18000ec9d  mov     ecx, ebx
0x18000ec9f  call    cs:__imp_DiscpAllocMemory
0x18000eca5  mov     rdi, rax
0x18000eca8  test    rax, rax
0x18000ecab  jz      short loc_18000ECC2
0x18000ecad  lea     r8, aAll; "All"
0x18000ecb4  mov     rcx, rax; pszDest
0x18000ecb7  lea     edx, [rbx-4]; cchDest
0x18000ecba  call    StringCchCopyW
0x18000ecbf  mov     ebx, r12d
0x18000ecc2  mov     [r15], rdi
0x18000ecc5  mov     eax, ebx
0x18000ecc7  add     rsp, 30h
0x18000eccb  pop     r15
0x18000eccd  pop     r14
0x18000eccf  pop     r12
0x18000ecd1  pop     rdi
0x18000ecd2  pop     rsi
0x18000ecd3  pop     rbp
0x18000ecd4  pop     rbx
0x18000ecd5  retn
```
