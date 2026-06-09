# CSynchWindow::Register(CComponentData *)

- ea: `0x18001e264`
- end: `0x18001e3a9`
- name: `?Register@CSynchWindow@@QEAAJPEAVCComponentData@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(CSynchWindow *__hidden this, struct CComponentData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800061b0`

## callees

- `0x180002bb8`
- `0x1800036a6`
- `0x18001e264`
- `0x180022292`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e342`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e342`

## pseudocode

```c
__int64 __fastcall CSynchWindow::Register(CSynchWindow *this, struct CComponentData *a2)
{
  unsigned int v2; // ebx
  _OWORD *v4; // rax
  __int64 i; // rax
  void *v6; // rax
  void *v7; // rsi

  v2 = 0;
  if ( dword_180031E9C )
  {
    if ( dword_180031E98 >= (unsigned int)dword_180031E9C )
    {
      v6 = operator new[](saturated_mul((unsigned int)(2 * dword_180031E9C), 8u));
      v7 = v6;
      if ( v6 )
      {
        memcpy_0(v6, Src, 8LL * (unsigned int)dword_180031E98);
        operator delete[](Src);
        Src = v7;
        dword_180031E9C *= 2;
        *((_QWORD *)v7 + (unsigned int)dword_180031E98++) = a2;
        memset_0(
          (char *)Src + 8 * (unsigned int)dword_180031E98,
          0,
          8LL * (unsigned int)(dword_180031E9C - dword_180031E98));
        return v2;
      }
      return (unsigned int)-2147024882;
    }
    for ( i = 0; (unsigned int)i < dword_180031E9C; i = (unsigned int)(i + 1) )
    {
      if ( !*((_QWORD *)Src + i) )
      {
        *((_QWORD *)Src + i) = a2;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = operator new[](0x28u);
    Src = v4;
    if ( !v4 )
      return (unsigned int)-2147024882;
    dword_180031E9C = 5;
    *v4 = 0;
    v4[1] = 0;
    *((_QWORD *)v4 + 4) = 0;
    *(_QWORD *)Src = a2;
LABEL_5:
    ++dword_180031E98;
  }
  return v2;
}

```

## disassembly

```asm
0x18001e264  mov     [rsp+arg_0], rbx
0x18001e269  mov     [rsp+arg_8], rsi
0x18001e26e  push    rdi
0x18001e26f  sub     rsp, 20h
0x18001e273  mov     ecx, cs:dword_180031E9C
0x18001e279  xor     ebx, ebx
0x18001e27b  mov     rdi, rdx
0x18001e27e  test    ecx, ecx
0x18001e280  jnz     short loc_18001E2CF
0x18001e282  lea     ecx, [rbx+28h]; unsigned __int64
0x18001e285  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e28a  mov     cs:Src, rax
0x18001e291  test    rax, rax
0x18001e294  jnz     short loc_18001E2A0
0x18001e296  mov     ebx, 8007000Eh
0x18001e29b  jmp     loc_18001E397
0x18001e2a0  mov     cs:dword_180031E9C, 5
0x18001e2aa  xorps   xmm0, xmm0
0x18001e2ad  movups  xmmword ptr [rax], xmm0
0x18001e2b0  xor     ecx, ecx
0x18001e2b2  movups  xmmword ptr [rax+10h], xmm0
0x18001e2b6  mov     [rax+20h], rcx
0x18001e2ba  mov     rax, cs:Src
0x18001e2c1  mov     [rax], rdi
0x18001e2c4  inc     cs:dword_180031E98
0x18001e2ca  jmp     loc_18001E397
0x18001e2cf  cmp     cs:dword_180031E98, ecx
0x18001e2d5  jnb     short loc_18001E2F8
0x18001e2d7  mov     r8, cs:Src
0x18001e2de  xor     eax, eax
0x18001e2e0  cmp     eax, ecx
0x18001e2e2  jnb     loc_18001E397
0x18001e2e8  cmp     [r8+rax*8], rbx
0x18001e2ec  jz      short loc_18001E2F2
0x18001e2ee  inc     eax
0x18001e2f0  jmp     short loc_18001E2E0
0x18001e2f2  mov     [r8+rax*8], rdi
0x18001e2f6  jmp     short loc_18001E2C4
0x18001e2f8  add     ecx, ecx
0x18001e2fa  mov     eax, 8
0x18001e2ff  mul     rcx
0x18001e302  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e309  cmovb   rax, rcx
0x18001e30d  mov     rcx, rax; unsigned __int64
0x18001e310  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e315  mov     rsi, rax
0x18001e318  test    rax, rax
0x18001e31b  jz      loc_18001E296
0x18001e321  mov     r8d, cs:dword_180031E98
0x18001e328  mov     rcx, rax; void *
0x18001e32b  mov     rdx, cs:Src; Src
0x18001e332  shl     r8, 3; Size
0x18001e336  call    memcpy_0
0x18001e33b  mov     rcx, cs:Src
0x18001e342  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e348  mov     eax, cs:dword_180031E9C
0x18001e34e  add     eax, eax
0x18001e350  mov     cs:Src, rsi
0x18001e357  mov     cs:dword_180031E9C, eax
0x18001e35d  mov     eax, cs:dword_180031E98
0x18001e363  mov     [rsi+rax*8], rdi
0x18001e367  mov     ecx, cs:dword_180031E98
0x18001e36d  mov     r8d, cs:dword_180031E9C
0x18001e374  inc     ecx
0x18001e376  mov     edx, ecx
0x18001e378  sub     r8d, ecx
0x18001e37b  mov     cs:dword_180031E98, ecx
0x18001e381  mov     rcx, cs:Src
0x18001e388  shl     r8, 3; Size
0x18001e38c  lea     rcx, [rcx+rdx*8]; void *
0x18001e390  xor     edx, edx; Val
0x18001e392  call    memset_0
0x18001e397  mov     rsi, [rsp+28h+arg_8]
0x18001e39c  mov     eax, ebx
0x18001e39e  mov     rbx, [rsp+28h+arg_0]
0x18001e3a3  add     rsp, 20h
0x18001e3a7  pop     rdi
0x18001e3a8  retn
```
