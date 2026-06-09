# SpQueryNegotiatedTlsExtensions(CSslUserContext *,_SecPkgContext_NegotiatedTlsExtensions *)

- ea: `0x140004940`
- end: `0x140004aa8`
- name: `?SpQueryNegotiatedTlsExtensions@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_NegotiatedTlsExtensions@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(struct CSslUserContext *, struct _SecPkgContext_NegotiatedTlsExtensions *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002f880`

## callees

- `0x140004940`
- `0x1400102c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400049fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400049fd`

## pseudocode

```c
__int64 __fastcall SpQueryNegotiatedTlsExtensions(
        struct CSslUserContext *a1,
        struct _SecPkgContext_NegotiatedTlsExtensions *a2)
{
  __int64 v2; // r8
  unsigned int v3; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  void *Pool2; // rax
  void *v10; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 Src; // [rsp+20h] [rbp-18h] BYREF
  int v16; // [rsp+28h] [rbp-10h]
  __int16 v17; // [rsp+2Ch] [rbp-Ch]

  v2 = *((_QWORD *)a1 + 2);
  v3 = 0;
  Src = 0;
  v16 = 0;
  v17 = 0;
  if ( (v2 & 0x20000) != 0 )
  {
    v3 = 1;
    LOWORD(Src) = 5;
  }
  v5 = *((_QWORD *)a1 + 54);
  if ( v5 && *(_DWORD *)(v5 + 4) == 2 )
  {
    v12 = v3++;
    *((_WORD *)&Src + v12) = 16;
  }
  if ( *((_QWORD *)a1 + 55) )
  {
    v13 = v3++;
    *((_WORD *)&Src + v13) = 14;
  }
  if ( *((_QWORD *)a1 + 56) )
  {
    v14 = v3++;
    *((_WORD *)&Src + v14) = 24;
  }
  if ( (v2 & 0x8000000) != 0 )
  {
    v6 = v3++;
    *((_WORD *)&Src + v6) = 23;
  }
  if ( *((_BYTE *)a1 + 32) )
  {
    v7 = v3++;
    *((_WORD *)&Src + v7) = -255;
  }
  if ( *((_BYTE *)a1 + 504) )
  {
    v8 = v3++;
    *((_WORD *)&Src + v8) = 49;
  }
  if ( !v3 )
  {
    *(_OWORD *)a2 = 0;
    return 0;
  }
  Pool2 = (void *)ExAllocatePool2(SslPoolType, 2 * v3, 1131180883);
  v10 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, &Src, 2 * v3);
    *((_QWORD *)a2 + 1) = v10;
    *(_DWORD *)a2 = v3;
    return 0;
  }
  return 2148074240LL;
}

```

## disassembly

```asm
0x140004940  mov     [rsp+arg_18], rbx
0x140004945  push    r14
0x140004947  sub     rsp, 30h
0x14000494b  mov     r8, [rcx+10h]
0x14000494f  xor     eax, eax
0x140004951  xor     ebx, ebx
0x140004953  mov     [rsp+38h+Src], rax
0x140004958  mov     [rsp+38h+var_10], eax
0x14000495c  mov     r14, rdx
0x14000495f  mov     [rsp+38h+var_C], ax
0x140004964  bt      r8, 11h
0x140004969  jb      loc_140004A6E
0x14000496f  mov     rax, [rcx+1B0h]
0x140004976  test    rax, rax
0x140004979  jnz     loc_140004A48
0x14000497f  cmp     qword ptr [rcx+1B8h], 0
0x140004987  jnz     loc_140004A82
0x14000498d  cmp     qword ptr [rcx+1C0h], 0
0x140004995  jnz     loc_140004A95
0x14000499b  bt      r8, 1Bh
0x1400049a0  jnb     short loc_1400049B0
0x1400049a2  mov     eax, ebx
0x1400049a4  mov     edx, 17h
0x1400049a9  inc     ebx
0x1400049ab  mov     word ptr [rsp+rax*2+38h+Src], dx
0x1400049b0  cmp     byte ptr [rcx+20h], 0
0x1400049b4  jz      short loc_1400049C4
0x1400049b6  mov     eax, ebx
0x1400049b8  mov     edx, 0FF01h
0x1400049bd  inc     ebx
0x1400049bf  mov     word ptr [rsp+rax*2+38h+Src], dx
0x1400049c4  cmp     byte ptr [rcx+1F8h], 0
0x1400049cb  jz      short loc_1400049DB
0x1400049cd  mov     eax, ebx
0x1400049cf  mov     ecx, 31h ; '1'
0x1400049d4  inc     ebx
0x1400049d6  mov     word ptr [rsp+rax*2+38h+Src], cx
0x1400049db  mov     [rsp+38h+arg_0], rsi
0x1400049e0  mov     [rsp+38h+arg_10], rdi
0x1400049e5  test    ebx, ebx
0x1400049e7  jz      short loc_140004A65
0x1400049e9  mov     rcx, cs:?SslPoolType@@3_KA; unsigned __int64 SslPoolType
0x1400049f0  lea     eax, [rbx+rbx]
0x1400049f3  mov     edx, eax
0x1400049f5  mov     r8d, 436C7353h
0x1400049fb  mov     esi, eax
0x1400049fd  call    cs:__imp_ExAllocatePool2
0x140004a04  nop     dword ptr [rax+rax+00h]
0x140004a09  mov     rdi, rax
0x140004a0c  test    rax, rax
0x140004a0f  jnz     short loc_140004A2D
0x140004a11  mov     eax, 80090300h
0x140004a16  mov     rdi, [rsp+38h+arg_10]
0x140004a1b  mov     rsi, [rsp+38h+arg_0]
0x140004a20  mov     rbx, [rsp+38h+arg_18]
0x140004a25  add     rsp, 30h
0x140004a29  pop     r14
0x140004a2b  retn
0x140004a2d  mov     r8, rsi; Size
0x140004a30  lea     rdx, [rsp+38h+Src]; Src
0x140004a35  mov     rcx, rdi; void *
0x140004a38  call    memmove
0x140004a3d  mov     [r14+8], rdi
0x140004a41  mov     [r14], ebx
0x140004a44  xor     eax, eax
0x140004a46  jmp     short loc_140004A16
0x140004a48  cmp     dword ptr [rax+4], 2
0x140004a4c  jnz     loc_14000497F
0x140004a52  mov     eax, ebx
0x140004a54  mov     edx, 10h
0x140004a59  inc     ebx
0x140004a5b  mov     word ptr [rsp+rax*2+38h+Src], dx
0x140004a60  jmp     loc_14000497F
0x140004a65  xorps   xmm0, xmm0
0x140004a68  movups  xmmword ptr [r14], xmm0
0x140004a6c  jmp     short loc_140004A44
0x140004a6e  mov     eax, 5
0x140004a73  mov     ebx, 1
0x140004a78  mov     word ptr [rsp+38h+Src], ax
0x140004a7d  jmp     loc_14000496F
0x140004a82  mov     eax, ebx
0x140004a84  mov     edx, 0Eh
0x140004a89  inc     ebx
0x140004a8b  mov     word ptr [rsp+rax*2+38h+Src], dx
0x140004a90  jmp     loc_14000498D
0x140004a95  mov     eax, ebx
0x140004a97  mov     edx, 18h
0x140004a9c  inc     ebx
0x140004a9e  mov     word ptr [rsp+rax*2+38h+Src], dx
0x140004aa3  jmp     loc_14000499B
```
