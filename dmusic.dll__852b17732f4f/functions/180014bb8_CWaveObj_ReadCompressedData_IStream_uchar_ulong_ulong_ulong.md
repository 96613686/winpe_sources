# CWaveObj::ReadCompressedData(IStream *,uchar *,ulong,ulong *,ulong *)

- ea: `0x180014bb8`
- end: `0x180014d40`
- name: `?ReadCompressedData@CWaveObj@@AEAAJPEAUIStream@@PEAEKPEAK2@Z`
- size: `392`
- prototype: `__int64 __fastcall(CWaveObj *this, struct IStream *, unsigned __int8 *, unsigned int, struct tWAVEFORMATEX *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014724`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x1800140a4`
- `0x180014530`
- `0x180014bb8`
- `0x1800217bc`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CWaveObj::ReadCompressedData(
        CWaveObj *this,
        struct IStream *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        struct tWAVEFORMATEX *a5,
        unsigned int *a6)
{
  struct tWAVEFORMATEX *v6; // rbp
  unsigned int v7; // r15d
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // r14
  unsigned __int64 v14; // rdx
  int v15; // ebx
  unsigned int v16; // r12d
  unsigned __int16 v17; // ax
  struct tWAVEFORMATEX *v18; // rax
  struct tWAVEFORMATEX *v19; // rdi
  const void *v20; // rdx
  int v21; // eax
  unsigned int v22; // eax
  unsigned __int64 v23; // [rsp+A8h] [rbp+20h] BYREF

  v6 = a5;
  LODWORD(v23) = 0;
  v7 = a4;
  if ( *((_DWORD *)this + 37) - *(_DWORD *)&a5->wFormatTag < a4 )
    v7 = *((_DWORD *)this + 37) - *(_DWORD *)&a5->wFormatTag;
  v11 = (unsigned __int8 *)operator new[](v7);
  v12 = v11;
  if ( !v11 )
    return 2147500037LL;
  v15 = ((__int64 (__fastcall *)(struct IStream *, unsigned __int8 *, _QWORD, unsigned __int64 *))a2->lpVtbl->Read)(
          a2,
          v11,
          v7,
          &v23);
  if ( v15 < 0 )
  {
    if ( a6 )
      *a6 = 0;
    goto LABEL_23;
  }
  v16 = *((_DWORD *)this + 35);
  v17 = *((_WORD *)this + 28) - 352;
  a5 = 0;
  if ( v17 <= 1u )
  {
    v15 = CWaveObj::AllocWMAudioFormat(this, (const struct tWAVEFORMATEX *)((char *)this + 56), &a5);
    if ( v15 < 0 )
      goto LABEL_23;
    v19 = a5;
LABEL_13:
    v21 = CWaveObj::DecompressWave(this, v19, (struct tWAVEFORMATEX *)((char *)this + 74), v12, a3, v7, v16);
    v14 = (unsigned int)v23;
    v15 = v21;
    if ( v21 >= 0 )
      *(_DWORD *)&v6->wFormatTag += v23;
    if ( a6 )
    {
      v22 = 0;
      if ( v15 >= 0 )
        v22 = v14;
      *a6 = v22;
    }
    if ( v19 )
      operator delete(v19, v14);
    goto LABEL_23;
  }
  v18 = (struct tWAVEFORMATEX *)operator new[](*((unsigned __int16 *)this + 36) + 18LL);
  v19 = v18;
  if ( v18 )
  {
    *(_OWORD *)&v18->wFormatTag = *(_OWORD *)((char *)this + 56);
    v18->cbSize = *((_WORD *)this + 36);
    v20 = (const void *)*((_QWORD *)this + 14);
    if ( v20 )
      memcpy_0(&v18[1], v20, *((unsigned __int16 *)this + 36));
    goto LABEL_13;
  }
  v15 = -2147024882;
LABEL_23:
  operator delete(v12, v14);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180014bb8  mov     rax, rsp
0x180014bbb  push    rbx
0x180014bbc  push    rbp
0x180014bbd  push    rsi
0x180014bbe  push    rdi
0x180014bbf  push    r12
0x180014bc1  push    r13
0x180014bc3  push    r14
0x180014bc5  push    r15
0x180014bc7  sub     rsp, 48h
0x180014bcb  mov     rbp, [rsp+88h+arg_20]
0x180014bd3  xor     edi, edi
0x180014bd5  mov     [rax+20h], edi
0x180014bd8  mov     r15d, r9d
0x180014bdb  mov     eax, [rcx+94h]
0x180014be1  mov     rsi, rcx
0x180014be4  mov     r13, r8
0x180014be7  mov     rbx, rdx
0x180014bea  sub     eax, [rbp+0]
0x180014bed  cmp     eax, r9d
0x180014bf0  cmovb   r15d, eax
0x180014bf4  mov     ecx, r15d; unsigned __int64
0x180014bf7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014bfc  mov     r14, rax
0x180014bff  test    rax, rax
0x180014c02  jnz     short loc_180014C0E
0x180014c04  mov     eax, 80004005h
0x180014c09  jmp     loc_180014D2F
0x180014c0e  mov     rax, [rbx]
0x180014c11  lea     r9, [rsp+88h+arg_18]
0x180014c19  mov     r8d, r15d
0x180014c1c  mov     rdx, r14
0x180014c1f  mov     rcx, rbx
0x180014c22  mov     rax, [rax+18h]
0x180014c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c2b  mov     ebx, eax
0x180014c2d  test    eax, eax
0x180014c2f  js      loc_180014D16
0x180014c35  mov     r12d, [rsi+8Ch]
0x180014c3c  lea     rbx, [rsi+38h]
0x180014c40  movzx   eax, word ptr [rbx]
0x180014c43  mov     ecx, 160h
0x180014c48  sub     ax, cx
0x180014c4b  mov     [rsp+88h+arg_20], rdi
0x180014c53  cmp     ax, 1
0x180014c57  jbe     short loc_180014C9F
0x180014c59  movzx   ecx, word ptr [rsi+48h]
0x180014c5d  add     rcx, 12h; unsigned __int64
0x180014c61  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014c66  mov     rdi, rax
0x180014c69  test    rax, rax
0x180014c6c  jnz     short loc_180014C78
0x180014c6e  mov     ebx, 8007000Eh
0x180014c73  jmp     loc_180014D25
0x180014c78  movups  xmm0, xmmword ptr [rbx]
0x180014c7b  movups  xmmword ptr [rax], xmm0
0x180014c7e  movzx   eax, word ptr [rbx+10h]
0x180014c82  mov     [rdi+10h], ax
0x180014c86  mov     rdx, [rsi+70h]; Src
0x180014c8a  test    rdx, rdx
0x180014c8d  jz      short loc_180014CC0
0x180014c8f  movzx   r8d, word ptr [rsi+48h]; Size
0x180014c94  lea     rcx, [rdi+12h]; void *
0x180014c98  call    memcpy_0
0x180014c9d  jmp     short loc_180014CC0
0x180014c9f  lea     r8, [rsp+88h+arg_20]; struct tWAVEFORMATEX **
0x180014ca7  mov     rdx, rbx; struct tWAVEFORMATEX *
0x180014caa  mov     rcx, rsi; this
0x180014cad  call    ?AllocWMAudioFormat@CWaveObj@@AEAAJPEBUtWAVEFORMATEX@@PEAPEAU2@@Z; CWaveObj::AllocWMAudioFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180014cb2  mov     ebx, eax
0x180014cb4  test    eax, eax
0x180014cb6  js      short loc_180014D25
0x180014cb8  mov     rdi, [rsp+88h+arg_20]
0x180014cc0  mov     [rsp+88h+var_58], r12d; unsigned int
0x180014cc5  lea     r8, [rsi+4Ah]; struct tWAVEFORMATEX *
0x180014cc9  mov     [rsp+88h+var_60], r15d; unsigned int
0x180014cce  mov     r9, r14; unsigned __int8 *
0x180014cd1  mov     rdx, rdi; struct tWAVEFORMATEX *
0x180014cd4  mov     [rsp+88h+var_68], r13; unsigned __int8 *
0x180014cd9  mov     rcx, rsi; this
0x180014cdc  call    ?DecompressWave@CWaveObj@@AEAAJPEAUtWAVEFORMATEX@@0PEAE1KK@Z; CWaveObj::DecompressWave(tWAVEFORMATEX *,tWAVEFORMATEX *,uchar *,uchar *,ulong,ulong)
0x180014ce1  mov     edx, dword ptr [rsp+88h+arg_18]; unsigned __int64
0x180014ce8  mov     ebx, eax
0x180014cea  test    eax, eax
0x180014cec  js      short loc_180014CF1
0x180014cee  add     [rbp+0], edx
0x180014cf1  mov     rcx, [rsp+88h+arg_28]
0x180014cf9  test    rcx, rcx
0x180014cfc  jz      short loc_180014D07
0x180014cfe  xor     eax, eax
0x180014d00  test    ebx, ebx
0x180014d02  cmovns  eax, edx
0x180014d05  mov     [rcx], eax
0x180014d07  test    rdi, rdi
0x180014d0a  jz      short loc_180014D25
0x180014d0c  mov     rcx, rdi; void *
0x180014d0f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014d14  jmp     short loc_180014D25
0x180014d16  mov     rax, [rsp+88h+arg_28]
0x180014d1e  test    rax, rax
0x180014d21  jz      short loc_180014D25
0x180014d23  mov     [rax], edi
0x180014d25  mov     rcx, r14; void *
0x180014d28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014d2d  mov     eax, ebx
0x180014d2f  add     rsp, 48h
0x180014d33  pop     r15
0x180014d35  pop     r14
0x180014d37  pop     r13
0x180014d39  pop     r12
0x180014d3b  pop     rdi
0x180014d3c  pop     rsi
0x180014d3d  pop     rbp
0x180014d3e  pop     rbx
0x180014d3f  retn
```
