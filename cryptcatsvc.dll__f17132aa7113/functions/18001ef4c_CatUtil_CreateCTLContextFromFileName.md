# CatUtil_CreateCTLContextFromFileName

- ea: `0x18001ef4c`
- end: `0x18001efe7`
- name: `CatUtil_CreateCTLContextFromFileName`
- size: `155`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD cbEncoded, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008888`
- `0x180017a04`

## callees

- `0x180009440`
- `0x18000aa00`
- `0x18001ef4c`

## import_xrefs

- `CRYPT32!CertCreateContext` at `0x18001efb5`
- `CRYPT32!CertCreateContext` at `0x18001efb5`

## pseudocode

```c
__int64 __fastcall CatUtil_CreateCTLContextFromFileName(
        const WCHAR *a1,
        _QWORD *a2,
        const BYTE **a3,
        _QWORD *a4,
        DWORD cbEncoded,
        __int64 *a6)
{
  __int64 *v6; // r14
  unsigned int v10; // ebx
  const void *Context; // rax

  v6 = a6;
  cbEncoded = 0;
  if ( !(unsigned int)CatUtil_Open((__int64)a1, a1, a2, a3, &cbEncoded, a6)
    || (v10 = 1, Context = CertCreateContext(3u, 0x10001u, *a3, cbEncoded, 1u, 0), (*a4 = Context) == 0) )
  {
    *a4 = 0;
    CatUtil_Close(a2, a3, v6);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18001ef4c  mov     rax, rsp
0x18001ef4f  push    rbx
0x18001ef50  push    rbp
0x18001ef51  push    rsi
0x18001ef52  push    rdi
0x18001ef53  push    r14
0x18001ef55  sub     rsp, 30h
0x18001ef59  mov     r14, [rsp+58h+arg_28]
0x18001ef61  mov     rsi, r9
0x18001ef64  mov     [rax-30h], r14
0x18001ef68  mov     rdi, r8
0x18001ef6b  mov     dword ptr [rax+28h], 0
0x18001ef72  lea     rax, [rax+28h]
0x18001ef76  mov     r9, r8
0x18001ef79  mov     qword ptr [rsp+58h+dwFlags], rax
0x18001ef7e  mov     rbp, rdx
0x18001ef81  mov     r8, rdx
0x18001ef84  mov     rdx, rcx
0x18001ef87  call    CatUtil_Open
0x18001ef8c  test    eax, eax
0x18001ef8e  jz      short loc_18001EFC3
0x18001ef90  mov     r9d, [rsp+58h+cbEncoded]; cbEncoded
0x18001ef98  mov     ebx, 1
0x18001ef9d  mov     r8, [rdi]; pbEncoded
0x18001efa0  mov     edx, 10001h; dwEncodingType
0x18001efa5  mov     [rsp+58h+pCreatePara], 0; pCreatePara
0x18001efae  mov     [rsp+58h+dwFlags], ebx; dwFlags
0x18001efb2  lea     ecx, [rbx+2]; dwContextType
0x18001efb5  call    cs:__imp_CertCreateContext
0x18001efbb  mov     [rsi], rax
0x18001efbe  test    rax, rax
0x18001efc1  jnz     short loc_18001EFDA
0x18001efc3  mov     r8, r14
0x18001efc6  mov     qword ptr [rsi], 0
0x18001efcd  mov     rdx, rdi
0x18001efd0  mov     rcx, rbp
0x18001efd3  call    CatUtil_Close
0x18001efd8  xor     ebx, ebx
0x18001efda  mov     eax, ebx
0x18001efdc  add     rsp, 30h
0x18001efe0  pop     r14
0x18001efe2  pop     rdi
0x18001efe3  pop     rsi
0x18001efe4  pop     rbp
0x18001efe5  pop     rbx
0x18001efe6  retn
```
