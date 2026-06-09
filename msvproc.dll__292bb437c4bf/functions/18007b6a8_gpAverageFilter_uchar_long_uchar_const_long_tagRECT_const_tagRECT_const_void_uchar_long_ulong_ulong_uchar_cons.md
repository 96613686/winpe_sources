# gpAverageFilter(uchar *,long,uchar const *,long,tagRECT const *,tagRECT const *,void (*)(uchar *,long,ulong,ulong,uchar const *,long,ulong,ulong),void (*)(uchar *,long,ulong,ulong,uchar const *,long,ulong,ulong),long)

- ea: `0x18007b6a8`
- end: `0x18007b8e8`
- name: `?gpAverageFilter@@YAJPEAEJPEBEJPEBUtagRECT@@2P6AX0JKK1JKK@Z3J@Z`
- size: `576`
- prototype: `int(unsigned __int8 *, int, const unsigned __int8 *, int, const struct tagRECT *, const struct tagRECT *, void (*)(unsigned __int8 *, int, unsigned int, unsigned int, const unsigned __int8 *, int, unsigned int, unsigned int), void (*)(unsigned __int8 *, int, unsigned int, unsigned int, const unsigned __int8 *, int, unsigned int, unsigned int), int)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180079600`
- `0x1800798d0`
- `0x180079d80`
- `0x18007a0a0`
- `0x18007a210`
- `0x18007b1c4`

## callees

- `0x180053c3c`
- `0x180053c48`
- `0x180059bac`
- `0x180059c14`
- `0x180059d70`
- `0x180075ecc`
- `0x1800760ac`
- `0x18007b6a8`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x18007b8cb`
- `MFPlat!MFCopyImage` at `0x18007b8cb`

## pseudocode

```c
__int64 __fastcall gpAverageFilter(
        unsigned __int8 *a1,
        unsigned int a2,
        const unsigned __int8 *a3,
        LONG a4,
        const struct tagRECT *Block,
        const struct tagRECT *a6,
        void (*a7)(unsigned __int8 *, int, unsigned int, unsigned int, const unsigned __int8 *, int, unsigned int, unsigned int),
        void (*a8)(unsigned __int8 *, int, unsigned int, unsigned int, const unsigned __int8 *, int, unsigned int, unsigned int),
        int a9)
{
  int v12; // edi
  int v14; // esi
  LONG top; // ecx
  signed int dwLines; // ebx
  LONG v17; // edx
  int v18; // ebp
  int v19; // eax
  unsigned int v20; // r12d
  BYTE *v21; // r10
  const BYTE *v22; // rax
  unsigned int v23; // r14d
  void *v24; // rax
  BYTE *v25; // [rsp+50h] [rbp-58h]
  void *Blocka; // [rsp+D0h] [rbp+28h]
  const struct tagRECT *v27; // [rsp+D8h] [rbp+30h]

  v12 = a6->right - a6->left;
  if ( v12 < 0 )
    return XvpOriginateError<27>("gpAverageFilter", 2147942487LL, L"Invalid source image width");
  v14 = Block->right - Block->left;
  if ( v14 < 0 )
    return XvpOriginateError<32>();
  top = a6->top;
  dwLines = a6->bottom - top;
  if ( dwLines < 0 )
    return XvpOriginateError<28>("gpAverageFilter", 2147942487LL, L"invalid source image height");
  v17 = Block->top;
  v18 = Block->bottom - v17;
  if ( v18 < 0 )
    return XvpOriginateError<33>("gpAverageFilter", 2147942487LL, L"invalid destination image height");
  v19 = -a2;
  if ( (int)a2 > 0 )
    v19 = a2;
  if ( v19 < v14 )
    return XvpOriginateError<15>();
  v20 = 0;
  v21 = &a1[a9 * Block->left + a2 * v17];
  v22 = &a3[a9 * a6->left + a4 * top];
  v25 = v21;
  v27 = (const struct tagRECT *)v22;
  if ( v12 <= v14 )
  {
    if ( dwLines <= v18 )
      return (unsigned int)MFCopyImage(v21, a2, v22, a4, a9 * v12, dwLines);
    else
      ((void (__fastcall *)(BYTE *, _QWORD, _QWORD, _QWORD, const BYTE *, LONG, int, signed int))a8)(
        v21,
        a2,
        (unsigned int)v14,
        (unsigned int)v18,
        v22,
        a4,
        v12,
        dwLines);
  }
  else if ( dwLines <= v18 )
  {
    ((void (__fastcall *)(BYTE *, _QWORD, _QWORD, _QWORD, const BYTE *, LONG, int, signed int))a7)(
      v21,
      a2,
      (unsigned int)v14,
      (unsigned int)v18,
      v22,
      a4,
      v12,
      dwLines);
  }
  else
  {
    v23 = (a9 * v14 + 63) & 0xFFFFFFC0;
    v24 = operator new[]((int)(dwLines * v23));
    Blocka = v24;
    if ( v24 )
    {
      ((void (__fastcall *)(void *, _QWORD, _QWORD, _QWORD, const struct tagRECT *, LONG, int, signed int))a7)(
        v24,
        v23,
        (unsigned int)v14,
        (unsigned int)dwLines,
        v27,
        a4,
        v12,
        dwLines);
      ((void (__fastcall *)(BYTE *, _QWORD, _QWORD, _QWORD, void *, unsigned int, int, signed int))a8)(
        v25,
        a2,
        (unsigned int)v14,
        (unsigned int)v18,
        Blocka,
        v23,
        v14,
        dwLines);
      operator delete(Blocka);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v20;
}

```

## disassembly

```asm
0x18007b6a8  push    rbx
0x18007b6aa  push    rbp
0x18007b6ab  push    rsi
0x18007b6ac  push    rdi
0x18007b6ad  push    r12
0x18007b6af  push    r13
0x18007b6b1  push    r14
0x18007b6b3  push    r15
0x18007b6b5  sub     rsp, 68h
0x18007b6b9  mov     rbx, [rsp+0A8h+arg_28]
0x18007b6c1  mov     r13d, r9d
0x18007b6c4  mov     r14, r8
0x18007b6c7  mov     r15d, edx
0x18007b6ca  mov     r10, rcx
0x18007b6cd  mov     edi, [rbx+8]
0x18007b6d0  mov     r9d, [rbx]
0x18007b6d3  sub     edi, r9d
0x18007b6d6  jns     short loc_18007B6F5
0x18007b6d8  lea     r8, aInvalidSourceI_0; "Invalid source image width"
0x18007b6df  mov     edx, 80070057h
0x18007b6e4  lea     rcx, aGpaveragefilte; "gpAverageFilter"
0x18007b6eb  call    ??$XvpOriginateError@$0BL@@@YAJQEADJAEAY0BL@$$CBG@Z; XvpOriginateError<27>(char * const,long,ushort const (&)[27])
0x18007b6f0  jmp     loc_18007B8D7
0x18007b6f5  mov     rbp, [rsp+0A8h+Block]
0x18007b6fd  mov     esi, [rbp+8]
0x18007b700  mov     r8d, [rbp+0]
0x18007b704  sub     esi, r8d
0x18007b707  jns     short loc_18007B713
0x18007b709  call    ??$XvpOriginateError@$0CA@@@YAJQEADJAEAY0CA@$$CBG@Z; XvpOriginateError<32>(char * const,long,ushort const (&)[32])
0x18007b70e  jmp     loc_18007B8D7
0x18007b713  mov     ecx, [rbx+4]
0x18007b716  mov     ebx, [rbx+0Ch]
0x18007b719  sub     ebx, ecx
0x18007b71b  jns     short loc_18007B73A
0x18007b71d  lea     r8, aInvalidSourceI; "invalid source image height"
0x18007b724  mov     edx, 80070057h
0x18007b729  lea     rcx, aGpaveragefilte; "gpAverageFilter"
0x18007b730  call    ??$XvpOriginateError@$0BM@@@YAJQEADJAEAY0BM@$$CBG@Z; XvpOriginateError<28>(char * const,long,ushort const (&)[28])
0x18007b735  jmp     loc_18007B8D7
0x18007b73a  mov     edx, [rbp+4]
0x18007b73d  mov     ebp, [rbp+0Ch]
0x18007b740  sub     ebp, edx
0x18007b742  jns     short loc_18007B761
0x18007b744  lea     r8, aInvalidDestina_1; "invalid destination image height"
0x18007b74b  mov     edx, 80070057h
0x18007b750  lea     rcx, aGpaveragefilte; "gpAverageFilter"
0x18007b757  call    ??$XvpOriginateError@$0CB@@@YAJQEADJAEAY0CB@$$CBG@Z; XvpOriginateError<33>(char * const,long,ushort const (&)[33])
0x18007b75c  jmp     loc_18007B8D7
0x18007b761  mov     eax, r15d
0x18007b764  neg     eax
0x18007b766  cmovs   eax, r15d
0x18007b76a  cmp     eax, esi
0x18007b76c  jge     short loc_18007B778
0x18007b76e  call    ??$XvpOriginateError@$0P@@@YAJQEADJAEAY0P@$$CBG@Z; XvpOriginateError<15>(char * const,long,ushort const (&)[15])
0x18007b773  jmp     loc_18007B8D7
0x18007b778  mov     r11d, [rsp+0A8h+arg_40]
0x18007b780  xor     r12d, r12d
0x18007b783  imul    r8d, r11d
0x18007b787  imul    edx, r15d
0x18007b78b  imul    ecx, r13d
0x18007b78f  imul    r9d, r11d
0x18007b793  lea     eax, [r8+rdx]
0x18007b797  cdqe
0x18007b799  add     r10, rax
0x18007b79c  lea     eax, [r9+rcx]
0x18007b7a0  cdqe
0x18007b7a2  add     rax, r14
0x18007b7a5  mov     [rsp+0A8h+var_58], r10
0x18007b7aa  mov     [rsp+0A8h+arg_28], rax
0x18007b7b2  cmp     edi, esi
0x18007b7b4  jle     loc_18007B888
0x18007b7ba  cmp     ebx, ebp
0x18007b7bc  jle     loc_18007B866
0x18007b7c2  mov     r14d, esi
0x18007b7c5  imul    r14d, r11d
0x18007b7c9  add     r14d, 3Fh ; '?'
0x18007b7cd  and     r14d, 0FFFFFFC0h
0x18007b7d1  mov     eax, r14d
0x18007b7d4  imul    eax, ebx
0x18007b7d7  movsxd  rcx, eax; unsigned __int64
0x18007b7da  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007b7df  mov     [rsp+0A8h+Block], rax
0x18007b7e7  test    rax, rax
0x18007b7ea  jz      short loc_18007B85E
0x18007b7ec  mov     rcx, [rsp+0A8h+arg_28]
0x18007b7f4  mov     r9d, ebx
0x18007b7f7  mov     [rsp+0A8h+var_70], ebx
0x18007b7fb  mov     r8d, esi
0x18007b7fe  mov     [rsp+0A8h+var_78], edi
0x18007b802  mov     edx, r14d
0x18007b805  mov     [rsp+0A8h+dwLines], r13d
0x18007b80a  mov     qword ptr [rsp+0A8h+dwWidthInBytes], rcx
0x18007b80f  mov     rcx, rax
0x18007b812  mov     rax, [rsp+0A8h+arg_30]
0x18007b81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b81f  mov     rcx, [rsp+0A8h+var_58]
0x18007b824  mov     r9d, ebp
0x18007b827  mov     rax, [rsp+0A8h+arg_38]
0x18007b82f  mov     r8d, esi
0x18007b832  mov     [rsp+0A8h+var_70], ebx
0x18007b836  mov     edx, r15d
0x18007b839  mov     rbx, [rsp+0A8h+Block]
0x18007b841  mov     [rsp+0A8h+var_78], esi
0x18007b845  mov     [rsp+0A8h+dwLines], r14d
0x18007b84a  mov     qword ptr [rsp+0A8h+dwWidthInBytes], rbx
0x18007b84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b854  mov     rcx, rbx; Block
0x18007b857  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007b85c  jmp     short loc_18007B8D4
0x18007b85e  mov     r12d, 8007000Eh
0x18007b864  jmp     short loc_18007B8D4
0x18007b866  mov     [rsp+0A8h+var_70], ebx
0x18007b86a  mov     edx, r15d
0x18007b86d  mov     [rsp+0A8h+var_78], edi
0x18007b871  mov     rcx, r10
0x18007b874  mov     [rsp+0A8h+dwLines], r13d
0x18007b879  mov     qword ptr [rsp+0A8h+dwWidthInBytes], rax
0x18007b87e  mov     rax, [rsp+0A8h+arg_30]
0x18007b886  jmp     short loc_18007B8AC
0x18007b888  mov     edx, r15d; lDestStride
0x18007b88b  mov     rcx, r10; pDest
0x18007b88e  cmp     ebx, ebp
0x18007b890  jle     short loc_18007B8B9
0x18007b892  mov     [rsp+0A8h+var_70], ebx
0x18007b896  mov     [rsp+0A8h+var_78], edi
0x18007b89a  mov     [rsp+0A8h+dwLines], r13d
0x18007b89f  mov     qword ptr [rsp+0A8h+dwWidthInBytes], rax
0x18007b8a4  mov     rax, [rsp+0A8h+arg_38]
0x18007b8ac  mov     r8d, esi
0x18007b8af  mov     r9d, ebp
0x18007b8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b8b7  jmp     short loc_18007B8D4
0x18007b8b9  imul    edi, r11d
0x18007b8bd  mov     r9d, r13d; lSrcStride
0x18007b8c0  mov     [rsp+0A8h+dwLines], ebx; dwLines
0x18007b8c4  mov     r8, rax; pSrc
0x18007b8c7  mov     [rsp+0A8h+dwWidthInBytes], edi; dwWidthInBytes
0x18007b8cb  call    cs:__imp_MFCopyImage
0x18007b8d1  mov     r12d, eax
0x18007b8d4  mov     eax, r12d
0x18007b8d7  add     rsp, 68h
0x18007b8db  pop     r15
0x18007b8dd  pop     r14
0x18007b8df  pop     r13
0x18007b8e1  pop     r12
0x18007b8e3  pop     rdi
0x18007b8e4  pop     rsi
0x18007b8e5  pop     rbp
0x18007b8e6  pop     rbx
0x18007b8e7  retn
```
