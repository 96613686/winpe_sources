# I_UrlCacheGetCacheFileName

- ea: `0x180002a90`
- end: `0x180002c2e`
- name: `I_UrlCacheGetCacheFileName`
- size: `414`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, void *@<r8>, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800015bc`
- `0x180002460`
- `0x18001ff84`

## callees

- `0x180002a90`
- `0x180003170`
- `0x18000a990`
- `0x180026552`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b07`

## pseudocode

```c
char *__fastcall I_UrlCacheGetCacheFileName(_WORD *Src, _WORD *a2, _WORD *a3, __int64 a4, int a5)
{
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rbp
  char *v11; // r13
  unsigned __int64 v12; // rdx

  v8 = -1;
  if ( Src )
  {
    v9 = -1;
    do
      ++v9;
    while ( Src[v9] );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
  }
  else
  {
    LODWORD(v10) = 0;
  }
  if ( a3 )
  {
    do
      ++v8;
    while ( a3[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v11 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v9 + v10 + v8 + 34));
  if ( !v11 )
  {
    SetLastError(0x8007000E);
    return v11;
  }
  memcpy_0(v11, Src, 2LL * (unsigned int)v9);
  memcpy_0(&v11[2 * (unsigned int)v9], a2, 2LL * (unsigned int)(v10 + 1));
  if ( !a5 || I_CryptRecursiveCreateLowIntegrityDirectory((LPCWSTR)v11) )
  {
    *(_WORD *)&v11[2 * (unsigned int)(v9 + v10)] = 92;
    if ( (_DWORD)v8 )
      memcpy_0(&v11[2 * (unsigned int)v9 + 2 + 2 * (unsigned __int64)(unsigned int)v10], a3, 2LL * (unsigned int)v8);
    v12 = (unsigned int)v9 + (unsigned __int64)(unsigned int)v8 + (unsigned int)v10;
    *(_OWORD *)&v11[2 * v12 + 2] = *(_OWORD *)a4;
    *(_OWORD *)&v11[2 * v12 + 18] = *(_OWORD *)(a4 + 16);
    *(_OWORD *)&v11[2 * v12 + 34] = *(_OWORD *)(a4 + 32);
    *(_OWORD *)&v11[2 * v12 + 50] = *(_OWORD *)(a4 + 48);
    *(_WORD *)&v11[2 * v12 + 66] = *(_WORD *)(a4 + 64);
    return v11;
  }
  operator delete(v11);
  return 0;
}

```

## disassembly

```asm
0x180002a90  mov     [rsp+arg_18], r9
0x180002a95  push    rbx
0x180002a96  push    rbp
0x180002a97  push    rsi
0x180002a98  push    r12
0x180002a9a  push    r13
0x180002a9c  push    r14
0x180002a9e  push    r15
0x180002aa0  sub     rsp, 20h
0x180002aa4  mov     r12, r8
0x180002aa7  mov     r15, rdx
0x180002aaa  mov     r14, rcx
0x180002aad  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180002ab4  test    rcx, rcx
0x180002ab7  jz      loc_180002C13
0x180002abd  mov     rbx, rsi
0x180002ac0  inc     rbx
0x180002ac3  cmp     word ptr [rcx+rbx*2], 0
0x180002ac8  jnz     short loc_180002AC0
0x180002aca  test    r15, r15
0x180002acd  jz      loc_180002C1A
0x180002ad3  mov     rbp, rsi
0x180002ad6  inc     rbp
0x180002ad9  cmp     word ptr [rdx+rbp*2], 0
0x180002ade  jnz     short loc_180002AD6
0x180002ae0  test    r12, r12
0x180002ae3  jz      loc_180002BE2
0x180002ae9  nop     dword ptr [rax+00000000h]
0x180002af0  inc     rsi
0x180002af3  cmp     word ptr [r8+rsi*2], 0
0x180002af9  jnz     short loc_180002AF0
0x180002afb  lea     edx, [rsi+22h]
0x180002afe  xor     ecx, ecx; uFlags
0x180002b00  add     edx, ebp
0x180002b02  add     edx, ebx
0x180002b04  add     rdx, rdx; uBytes
0x180002b07  call    cs:__imp_LocalAlloc
0x180002b0d  mov     r13, rax
0x180002b10  test    rax, rax
0x180002b13  jz      loc_180002C21
0x180002b19  mov     [rsp+58h+arg_8], rdi
0x180002b1e  mov     eax, ebx
0x180002b20  mov     rdx, r14; Src
0x180002b23  mov     rcx, r13; void *
0x180002b26  mov     [rsp+58h+arg_0], rax
0x180002b2b  lea     rdi, [rax+rax]
0x180002b2f  mov     r8, rdi; Size
0x180002b32  call    memcpy_0
0x180002b37  lea     r8d, [rbp+1]
0x180002b3b  mov     rdx, r15; Src
0x180002b3e  add     r8, r8; Size
0x180002b41  lea     rcx, [rdi+r13]; void *
0x180002b45  call    memcpy_0
0x180002b4a  cmp     [rsp+58h+arg_20], 0
0x180002b52  mov     rdi, [rsp+58h+arg_8]
0x180002b57  jnz     loc_180002BE9
0x180002b5d  lea     eax, [rbx+rbp]
0x180002b60  mov     rbx, [rsp+58h+arg_0]
0x180002b65  mov     word ptr [r13+rax*2+0], 5Ch ; '\'
0x180002b6d  test    esi, esi
0x180002b6f  jz      short loc_180002B8F
0x180002b71  mov     eax, ebp
0x180002b73  mov     rdx, r12; Src
0x180002b76  add     rax, rbx
0x180002b79  mov     r8d, esi
0x180002b7c  add     r8, r8; Size
0x180002b7f  lea     rcx, ds:2[rax*2]
0x180002b87  add     rcx, r13; void *
0x180002b8a  call    memcpy_0
0x180002b8f  mov     ecx, esi
0x180002b91  add     rcx, rbx
0x180002b94  mov     edx, ebp
0x180002b96  add     rdx, rcx
0x180002b99  mov     rcx, [rsp+58h+arg_18]
0x180002b9e  movaps  xmm0, xmmword ptr [rcx]
0x180002ba1  movups  xmmword ptr [r13+rdx*2+2], xmm0
0x180002ba7  movaps  xmm1, xmmword ptr [rcx+10h]
0x180002bab  movups  xmmword ptr [r13+rdx*2+12h], xmm1
0x180002bb1  movaps  xmm0, xmmword ptr [rcx+20h]
0x180002bb5  movups  xmmword ptr [r13+rdx*2+22h], xmm0
0x180002bbb  movaps  xmm1, xmmword ptr [rcx+30h]
0x180002bbf  movups  xmmword ptr [r13+rdx*2+32h], xmm1
0x180002bc5  movzx   ecx, word ptr [rcx+40h]
0x180002bc9  mov     [r13+rdx*2+42h], cx
0x180002bcf  mov     rax, r13
0x180002bd2  add     rsp, 20h
0x180002bd6  pop     r15
0x180002bd8  pop     r14
0x180002bda  pop     r13
0x180002bdc  pop     r12
0x180002bde  pop     rsi
0x180002bdf  pop     rbp
0x180002be0  pop     rbx
0x180002be1  retn
0x180002be2  xor     esi, esi
0x180002be4  jmp     loc_180002AFB
0x180002be9  mov     rcx, r13; lpFileName
0x180002bec  call    I_CryptRecursiveCreateLowIntegrityDirectory
0x180002bf1  test    eax, eax
0x180002bf3  jnz     loc_180002B5D
0x180002bf9  mov     rcx, r13; hMem
0x180002bfc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c01  xor     eax, eax
0x180002c03  add     rsp, 20h
0x180002c07  pop     r15
0x180002c09  pop     r14
0x180002c0b  pop     r13
0x180002c0d  pop     r12
0x180002c0f  pop     rsi
0x180002c10  pop     rbp
0x180002c11  pop     rbx
0x180002c12  retn
0x180002c13  xor     ebx, ebx
0x180002c15  jmp     loc_180002ACA
0x180002c1a  xor     ebp, ebp
0x180002c1c  jmp     loc_180002AE0
0x180002c21  mov     ecx, 8007000Eh; dwErrCode
0x180002c26  call    cs:__imp_SetLastError
0x180002c2c  jmp     short loc_180002BCF
```
