# CImageList::LoadEx(ulong,IStream *)

- ea: `0x18009d950`
- end: `0x18009de82`
- name: `?LoadEx@CImageList@@UEAAJKPEAUIStream@@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(CImageList *this, char, struct IStream *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1800106e8`
- `0x180010850`
- `0x180012444`
- `0x18009d868`
- `0x18009d950`
- `0x18009df50`
- `0x18009dff8`
- `0x18009e3e8`
- `0x1800ca600`
- `0x1800e4e94`
- `0x1800eec9c`
- `0x180114520`
- `0x180147d6c`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009da4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ddfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009da4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ddfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d9b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ddb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d9b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ddb9`
- `GDI32!DeleteObject` at `0x18009dcfd`
- `GDI32!DeleteObject` at `0x18009dd0b`
- `GDI32!DeleteObject` at `0x18009de12`
- `GDI32!DeleteObject` at `0x18009de24`
- `GDI32!DeleteObject` at `0x18009dcfd`
- `GDI32!DeleteObject` at `0x18009dd0b`
- `GDI32!DeleteObject` at `0x18009de12`
- `GDI32!DeleteObject` at `0x18009de24`

## pseudocode

```c
__int64 __fastcall CImageList::LoadEx(CImageList *this, char a2, struct IStream *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  HDSA v10; // rbx
  int v11; // r12d
  HGDIOBJ v12; // rcx
  _WORD *v13; // rdi
  __int64 i; // rcx
  __int16 v15; // ax
  struct _DSA *v16; // rcx
  int v17; // eax
  HDSA v18; // rbx
  int v19; // eax
  CImageList **v20; // rsi
  HGDIOBJ v21; // rcx
  HDSA hdsa; // [rsp+40h] [rbp-C0h] BYREF
  HGDIOBJ ho; // [rsp+48h] [rbp-B8h] BYREF
  HGDIOBJ v24; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v26; // [rsp+88h] [rbp-78h]
  unsigned __int16 v27[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( a3 )
  {
    v26 = 0;
    memset(v25, 0, sizeof(v25));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v6 = (*(__int64 (__fastcall **)(struct IStream *, _OWORD *, __int64, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, v25, 28, 0);
    if ( v6 >= 0 && (LOWORD(v25[0]) != 19529 || WORD1(v25[0]) != 1568 && WORD1(v25[0]) != 1536 && WORD1(v25[0]) != 257) )
      v6 = -2147467259;
    StringCchPrintfW(
      v27,
      0x104u,
      L"ImageList: %d x %d Count: %d",
      (unsigned int)SWORD5(v25[0]),
      SWORD6(v25[0]),
      SWORD2(v25[0]));
    if ( byte_180211081 < 0 )
      McTemplateU0z_EtwEventWriteTransfer(v8, v7, v27);
    if ( WORD1(v25[0]) == 257 )
      a2 |= 1u;
    if ( ((WORD1(v25[0]) - 1536) & 0xFFDF) == 0 )
      a2 &= ~1u;
    if ( v6 < 0 )
      goto LABEL_10;
    v10 = 0;
    ho = 0;
    v24 = 0;
    v11 = BYTE2(v25[1]) & 0xFE;
    hdsa = 0;
    if ( (a2 & 1) != 0 )
    {
      v6 = Stream_ReadBitmap(
             a3,
             4 * SWORD5(v25[0]),
             SWORD6(v25[0]) * (SWORD3(v25[0]) / 4 + 1),
             v11,
             (HBITMAP *)&ho,
             &v24);
      if ( v6 >= 0 )
        v6 = CreateUplevelBitmap(SWORD5(v25[0]), SWORD6(v25[0]), SWORD3(v25[0]), v11 == 32, 0, (HBITMAP *)&ho, &v24);
    }
    else
    {
      v6 = Stream_ReadBitmap(a3, SWORD5(v25[0]), SWORD6(v25[0]) * SWORD3(v25[0]), v11, (HBITMAP *)&ho, &v24);
    }
    if ( v6 < 0
      || (BYTE2(v25[1]) & 1) != 0
      && (v17 = ReadAndConvertBitmap(a3, (const struct _ILFILEHEADER *)v25, a2, 1, (HBITMAP *)&hdsa, 0),
          v10 = hdsa,
          v6 = v17,
          v17 < 0) )
    {
      v12 = ho;
    }
    else
    {
      v6 = CImageList::_Read(
             (CImageList *)((char *)this - 40),
             (const struct _ILFILEHEADER *)v25,
             (HBITMAP)ho,
             v24,
             (HBITMAP)v10);
      v12 = 0;
      v10 = 0;
    }
    if ( v12 )
      DeleteObject(v12);
    if ( v10 )
      DeleteObject(v10);
    if ( v6 < 0 )
      goto LABEL_10;
    if ( (WORD1(v25[1]) & 0x1000) != 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64))(*(_QWORD *)a3 + 24LL))(
             a3,
             (char *)&v25[1] + 12,
             22);
      if ( v6 < 0 )
        goto LABEL_10;
      v15 = WORD1(v25[1]) & 0xEFFF;
      WORD1(v25[1]) &= ~0x1000u;
    }
    else
    {
      v13 = (_WORD *)&v25[1] + 6;
      for ( i = 11; i; --i )
        *v13++ = -1;
      v15 = WORD1(v25[1]);
    }
    if ( (v15 & 0x2000) != 0 )
    {
      v24 = 0;
      ho = 0;
      WORD1(v25[1]) = v15 & 0xDFFF;
      v18 = 0;
      hdsa = 0;
      v6 = ReadAndConvertBitmap(a3, (const struct _ILFILEHEADER *)v25, a2, 0, (HBITMAP *)&v24, &ho);
      if ( v6 < 0 )
        goto LABEL_53;
      if ( (BYTE2(v25[1]) & 1) != 0 )
      {
        v19 = ReadAndConvertBitmap(a3, (const struct _ILFILEHEADER *)v25, a2, 1, (HBITMAP *)&hdsa, 0);
        v18 = hdsa;
        v6 = v19;
        if ( v19 < 0 )
          goto LABEL_53;
      }
      v20 = (CImageList **)((char *)this + 528);
      v6 = CImageList::Recreate((struct CImageList **)this + 66);
      if ( v6 < 0 )
      {
LABEL_53:
        v21 = v24;
      }
      else
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)*v20 + 64));
        CImageList::_Destroy(*v20);
        v6 = CImageList::_Read(*v20, (const struct _ILFILEHEADER *)v25, (HBITMAP)v24, ho, (HBITMAP)v18);
        if ( v6 >= 0 )
          v6 = CImageList::_ScanForAlpha(*v20);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)*v20 + 64));
        v21 = 0;
        v18 = 0;
      }
      if ( v21 )
        DeleteObject(v21);
      if ( v18 )
        DeleteObject(v18);
      if ( v6 < 0 )
        goto LABEL_10;
    }
    v16 = (struct _DSA *)*((_QWORD *)this + 17);
    if ( v16 )
    {
      DSA_Destroy(v16);
      *((_QWORD *)this + 17) = 0;
    }
    if ( WORD1(v25[0]) == 1568 )
    {
      hdsa = 0;
      v6 = DSA_LoadStream(&hdsa, a3);
      if ( v6 < 0 )
        goto LABEL_10;
      if ( *((_DWORD *)hdsa + 5) != 8 )
      {
        DSA_Destroy(hdsa);
        v6 = -2147024883;
        goto LABEL_10;
      }
      *((_QWORD *)this + 17) = hdsa;
    }
    v6 = CImageList::_ScanForAlpha((CImageList *)((char *)this - 40));
LABEL_10:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    return (unsigned int)v6;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009d950  mov     [rsp-8+arg_8], rbx
0x18009d955  push    rbp
0x18009d956  push    rsi
0x18009d957  push    rdi
0x18009d958  push    r12
0x18009d95a  push    r13
0x18009d95c  push    r14
0x18009d95e  push    r15
0x18009d960  lea     rbp, [rsp-1B0h]
0x18009d968  sub     rsp, 2B0h
0x18009d96f  mov     rax, cs:__security_cookie
0x18009d976  xor     rax, rsp
0x18009d979  mov     [rbp+1E0h+var_40], rax
0x18009d980  xor     r12d, r12d
0x18009d983  mov     r14, r8
0x18009d986  mov     esi, edx
0x18009d988  mov     r15, rcx
0x18009d98b  test    r8, r8
0x18009d98e  jz      loc_18009DA80
0x18009d994  xorps   xmm0, xmm0
0x18009d997  xor     eax, eax
0x18009d999  add     rcx, 18h; lpCriticalSection
0x18009d99d  mov     [rbp+1E0h+var_258], ax
0x18009d9a1  movups  [rsp+2E0h+var_288], xmm0
0x18009d9a6  movups  [rsp+2E0h+var_278], xmm0
0x18009d9ab  movups  [rsp+2E0h+var_268], xmm0
0x18009d9b0  call    cs:__imp_EnterCriticalSection
0x18009d9b6  mov     rax, [r14]
0x18009d9b9  lea     r8d, [r12+1Ch]
0x18009d9be  xor     r9d, r9d
0x18009d9c1  lea     rdx, [rsp+2E0h+var_288]
0x18009d9c6  mov     rcx, r14
0x18009d9c9  mov     rax, [rax+18h]
0x18009d9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9d2  mov     edx, 620h
0x18009d9d7  mov     edi, eax
0x18009d9d9  mov     ebx, 101h
0x18009d9de  lea     ecx, [rdx-20h]
0x18009d9e1  test    eax, eax
0x18009d9e3  jns     loc_18009DCA5
0x18009d9e9  movsx   ecx, word ptr [rsp+2E0h+var_288+0Ch]
0x18009d9ee  lea     r8, aImagelistDXDCo; "ImageList: %d x %d Count: %d"
0x18009d9f5  movsx   eax, word ptr [rsp+2E0h+var_288+4]
0x18009d9fa  mov     edx, 104h; unsigned __int64
0x18009d9ff  movsx   r9d, word ptr [rsp+2E0h+var_288+0Ah]
0x18009da05  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x18009da09  mov     dword ptr [rsp+2E0h+var_2C0], ecx
0x18009da0d  lea     rcx, [rbp+1E0h+var_250]; unsigned __int16 *
0x18009da11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009da16  cmp     cs:byte_180211081, r12b
0x18009da1d  jl      loc_18009DCDB
0x18009da23  movzx   eax, word ptr [rsp+2E0h+var_288+2]
0x18009da28  cmp     ax, bx
0x18009da2b  jnz     short loc_18009DA30
0x18009da2d  or      esi, 1
0x18009da30  mov     ecx, 600h
0x18009da35  sub     ax, cx
0x18009da38  mov     ecx, 0FFDFh
0x18009da3d  test    cx, ax
0x18009da40  jz      loc_18009DCE9
0x18009da46  test    edi, edi
0x18009da48  jns     short loc_18009DA87
0x18009da4a  lea     rcx, [r15+18h]; lpCriticalSection
0x18009da4e  call    cs:__imp_LeaveCriticalSection
0x18009da54  mov     eax, edi
0x18009da56  mov     rcx, [rbp+1E0h+var_40]
0x18009da5d  xor     rcx, rsp; StackCookie
0x18009da60  call    __security_check_cookie
0x18009da65  mov     rbx, [rsp+2E0h+arg_8]
0x18009da6d  add     rsp, 2B0h
0x18009da74  pop     r15
0x18009da76  pop     r14
0x18009da78  pop     r13
0x18009da7a  pop     r12
0x18009da7c  pop     rdi
0x18009da7d  pop     rsi
0x18009da7e  pop     rbp
0x18009da7f  retn
0x18009da80  mov     eax, 80070057h
0x18009da85  jmp     short loc_18009DA56
0x18009da87  mov     rbx, r12
0x18009da8a  mov     [rsp+2E0h+ho], r12
0x18009da8f  mov     [rsp+2E0h+var_290], r12
0x18009da94  movzx   r12d, word ptr [rsp+2E0h+var_278+2]
0x18009da9a  and     r12d, 0FEh
0x18009daa1  mov     [rsp+2E0h+hdsa], rbx
0x18009daa6  mov     r9d, r12d; int
0x18009daa9  test    sil, 1
0x18009daad  jnz     loc_18009DB73
0x18009dab3  movsx   eax, word ptr [rsp+2E0h+var_288+0Ch]
0x18009dab8  mov     rcx, r14; struct IStream *
0x18009dabb  movsx   r8d, word ptr [rsp+2E0h+var_288+6]
0x18009dac1  movsx   edx, word ptr [rsp+2E0h+var_288+0Ah]; int
0x18009dac6  imul    r8d, eax; int
0x18009daca  lea     rax, [rsp+2E0h+var_290]
0x18009dacf  mov     [rsp+2E0h+var_2B8], rax; void **
0x18009dad4  lea     rax, [rsp+2E0h+ho]
0x18009dad9  mov     [rsp+2E0h+var_2C0], rax; HBITMAP *
0x18009dade  call    ?Stream_ReadBitmap@@YAJPEAUIStream@@HHHPEAPEAUHBITMAP__@@PEAPEAX@Z; Stream_ReadBitmap(IStream *,int,int,int,HBITMAP__ * *,void * *)
0x18009dae3  mov     edi, eax
0x18009dae5  xor     r12d, r12d
0x18009dae8  test    edi, edi
0x18009daea  jns     loc_18009DCF1
0x18009daf0  mov     rcx, [rsp+2E0h+ho]; ho
0x18009daf5  test    rcx, rcx
0x18009daf8  jnz     loc_18009DCFD
0x18009dafe  test    rbx, rbx
0x18009db01  jnz     loc_18009DD08
0x18009db07  test    edi, edi
0x18009db09  js      loc_18009DA4A
0x18009db0f  mov     eax, 1000h
0x18009db14  test    word ptr [rsp+2E0h+var_278+2], ax
0x18009db19  jnz     loc_18009DBFE
0x18009db1f  or      eax, 0FFFFFFFFh
0x18009db22  lea     rdi, [rsp+2E0h+var_278+0Ch]
0x18009db27  movsx   rax, ax
0x18009db2b  mov     ecx, 0Bh
0x18009db30  rep stosw
0x18009db33  movzx   eax, word ptr [rsp+2E0h+var_278+2]
0x18009db38  bt      ax, 0Dh
0x18009db3d  jb      loc_18009DD16
0x18009db43  mov     rcx, [r15+88h]; hdsa
0x18009db4a  test    rcx, rcx
0x18009db4d  jnz     loc_18009DE2F
0x18009db53  mov     eax, 620h
0x18009db58  cmp     word ptr [rsp+2E0h+var_288+2], ax
0x18009db5d  jz      loc_18009DE40
0x18009db63  lea     rcx, [r15-28h]; this
0x18009db67  call    ?_ScanForAlpha@CImageList@@IEAAJXZ; CImageList::_ScanForAlpha(void)
0x18009db6c  mov     edi, eax
0x18009db6e  jmp     loc_18009DA4A
0x18009db73  movsx   eax, word ptr [rsp+2E0h+var_288+6]
0x18009db78  mov     ecx, 4
0x18009db7d  cdq
0x18009db7e  idiv    ecx
0x18009db80  movsx   edx, word ptr [rsp+2E0h+var_288+0Ah]
0x18009db85  mov     rcx, r14; struct IStream *
0x18009db88  shl     edx, 2; int
0x18009db8b  lea     r8d, [rax+1]
0x18009db8f  movsx   eax, word ptr [rsp+2E0h+var_288+0Ch]
0x18009db94  imul    r8d, eax; int
0x18009db98  lea     rax, [rsp+2E0h+var_290]
0x18009db9d  mov     [rsp+2E0h+var_2B8], rax; void **
0x18009dba2  lea     rax, [rsp+2E0h+ho]
0x18009dba7  mov     [rsp+2E0h+var_2C0], rax; HBITMAP *
0x18009dbac  call    ?Stream_ReadBitmap@@YAJPEAUIStream@@HHHPEAPEAUHBITMAP__@@PEAPEAX@Z; Stream_ReadBitmap(IStream *,int,int,int,HBITMAP__ * *,void * *)
0x18009dbb1  mov     edi, eax
0x18009dbb3  test    eax, eax
0x18009dbb5  js      loc_18009DAE5
0x18009dbbb  movsx   r8d, word ptr [rsp+2E0h+var_288+6]; int
0x18009dbc1  lea     rax, [rsp+2E0h+var_290]
0x18009dbc6  movsx   edx, word ptr [rsp+2E0h+var_288+0Ch]; int
0x18009dbcb  xor     r9d, r9d
0x18009dbce  movsx   ecx, word ptr [rsp+2E0h+var_288+0Ah]; cx
0x18009dbd3  cmp     r12d, 20h ; ' '
0x18009dbd7  mov     [rsp+2E0h+var_2B0], rax; void **
0x18009dbdc  lea     rax, [rsp+2E0h+ho]
0x18009dbe1  setz    r9b; int
0x18009dbe5  mov     [rsp+2E0h+var_2B8], rax; HBITMAP *
0x18009dbea  xor     r12d, r12d
0x18009dbed  mov     dword ptr [rsp+2E0h+var_2C0], r12d; int
0x18009dbf2  call    ?CreateUplevelBitmap@@YAJHHHHHPEAPEAUHBITMAP__@@PEAPEAX@Z; CreateUplevelBitmap(int,int,int,int,int,HBITMAP__ * *,void * *)
0x18009dbf7  mov     edi, eax
0x18009dbf9  jmp     loc_18009DAE8
0x18009dbfe  mov     rax, [r14]
0x18009dc01  lea     rdx, [rsp+2E0h+var_278+0Ch]
0x18009dc06  xor     r9d, r9d
0x18009dc09  mov     rcx, r14
0x18009dc0c  mov     rax, [rax+18h]
0x18009dc10  lea     r8d, [r9+16h]
0x18009dc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc19  mov     edi, eax
0x18009dc1b  test    eax, eax
0x18009dc1d  js      loc_18009DA4A
0x18009dc23  movzx   eax, word ptr [rsp+2E0h+var_278+2]
0x18009dc28  mov     ecx, 0EFFFh
0x18009dc2d  and     ax, cx
0x18009dc30  mov     word ptr [rsp+2E0h+var_278+2], ax
0x18009dc35  jmp     loc_18009DB38
0x18009dc3a  test    edi, edi
0x18009dc3c  js      loc_18009DA4A
0x18009dc42  jmp     loc_18009DB43
0x18009dc47  lea     rax, [rsp+2E0h+hdsa]
0x18009dc4c  mov     [rsp+2E0h+var_2B8], r12; void **
0x18009dc51  mov     r9d, 1; int
0x18009dc57  mov     [rsp+2E0h+var_2C0], rax; HBITMAP *
0x18009dc5c  mov     r8d, esi; unsigned int
0x18009dc5f  lea     rdx, [rsp+2E0h+var_288]; struct _ILFILEHEADER *
0x18009dc64  mov     rcx, r14; struct IStream *
0x18009dc67  call    ?ReadAndConvertBitmap@@YAJPEAUIStream@@PEBU_ILFILEHEADER@@KHPEAPEAUHBITMAP__@@PEAPEAX@Z; ReadAndConvertBitmap(IStream *,_ILFILEHEADER const *,ulong,int,HBITMAP__ * *,void * *)
0x18009dc6c  mov     rbx, [rsp+2E0h+hdsa]
0x18009dc71  mov     edi, eax
0x18009dc73  test    eax, eax
0x18009dc75  js      loc_18009DAF0
0x18009dc7b  mov     r9, [rsp+2E0h+var_290]; void *
0x18009dc80  lea     rcx, [r15-28h]; this
0x18009dc84  mov     r8, [rsp+2E0h+ho]; HBITMAP
0x18009dc89  lea     rdx, [rsp+2E0h+var_288]; struct _ILFILEHEADER *
0x18009dc8e  mov     [rsp+2E0h+var_2C0], rbx; HBITMAP
0x18009dc93  call    ?_Read@CImageList@@IEAAJPEBU_ILFILEHEADER@@PEAUHBITMAP__@@PEAX1@Z; CImageList::_Read(_ILFILEHEADER const *,HBITMAP__ *,void *,HBITMAP__ *)
0x18009dc98  mov     edi, eax
0x18009dc9a  mov     rcx, r12
0x18009dc9d  mov     rbx, r12
0x18009dca0  jmp     loc_18009DAF5
0x18009dca5  mov     eax, 4C49h
0x18009dcaa  cmp     word ptr [rsp+2E0h+var_288], ax
0x18009dcaf  jnz     short loc_18009DCD1
0x18009dcb1  movzx   eax, word ptr [rsp+2E0h+var_288+2]
0x18009dcb6  cmp     ax, dx
0x18009dcb9  jz      loc_18009D9E9
0x18009dcbf  cmp     ax, cx
0x18009dcc2  jz      loc_18009D9E9
0x18009dcc8  cmp     ax, bx
0x18009dccb  jz      loc_18009D9E9
0x18009dcd1  mov     edi, 80004005h
0x18009dcd6  jmp     loc_18009D9E9
0x18009dcdb  lea     r8, [rbp+1E0h+var_250]
0x18009dcdf  call    McTemplateU0z_EtwEventWriteTransfer
0x18009dce4  jmp     loc_18009DA23
0x18009dce9  and     esi, 0FFFFFFFEh
0x18009dcec  jmp     loc_18009DA46
0x18009dcf1  test    byte ptr [rsp+2E0h+var_278+2], 1
0x18009dcf6  jz      short loc_18009DC7B
0x18009dcf8  jmp     loc_18009DC47
0x18009dcfd  call    cs:__imp_DeleteObject
0x18009dd03  jmp     loc_18009DAFE
0x18009dd08  mov     rcx, rbx; ho
0x18009dd0b  call    cs:__imp_DeleteObject
0x18009dd11  jmp     loc_18009DB07
0x18009dd16  mov     ecx, 0DFFFh
0x18009dd1b  mov     [rsp+2E0h+var_290], r12
0x18009dd20  and     ax, cx
0x18009dd23  mov     [rsp+2E0h+ho], r12
0x18009dd28  mov     word ptr [rsp+2E0h+var_278+2], ax
0x18009dd2d  lea     rdx, [rsp+2E0h+var_288]; struct _ILFILEHEADER *
0x18009dd32  lea     rax, [rsp+2E0h+ho]
0x18009dd37  mov     rbx, r12
0x18009dd3a  mov     [rsp+2E0h+var_2B8], rax; void **
0x18009dd3f  xor     r9d, r9d; int
0x18009dd42  lea     rax, [rsp+2E0h+var_290]
0x18009dd47  mov     [rsp+2E0h+hdsa], rbx
0x18009dd4c  mov     r8d, esi; unsigned int
0x18009dd4f  mov     [rsp+2E0h+var_2C0], rax; HBITMAP *
0x18009dd54  mov     rcx, r14; struct IStream *
0x18009dd57  call    ?ReadAndConvertBitmap@@YAJPEAUIStream@@PEBU_ILFILEHEADER@@KHPEAPEAUHBITMAP__@@PEAPEAX@Z; ReadAndConvertBitmap(IStream *,_ILFILEHEADER const *,ulong,int,HBITMAP__ * *,void * *)
0x18009dd5c  mov     edi, eax
0x18009dd5e  test    eax, eax
0x18009dd60  js      loc_18009DE08
0x18009dd66  test    byte ptr [rsp+2E0h+var_278+2], 1
0x18009dd6b  jz      short loc_18009DD9D
0x18009dd6d  lea     rax, [rsp+2E0h+hdsa]
0x18009dd72  mov     [rsp+2E0h+var_2B8], r12; void **
0x18009dd77  mov     r9d, 1; int
0x18009dd7d  mov     [rsp+2E0h+var_2C0], rax; HBITMAP *
0x18009dd82  mov     r8d, esi; unsigned int
0x18009dd85  lea     rdx, [rsp+2E0h+var_288]; struct _ILFILEHEADER *
0x18009dd8a  mov     rcx, r14; struct IStream *
0x18009dd8d  call    ?ReadAndConvertBitmap@@YAJPEAUIStream@@PEBU_ILFILEHEADER@@KHPEAPEAUHBITMAP__@@PEAPEAX@Z; ReadAndConvertBitmap(IStream *,_ILFILEHEADER const *,ulong,int,HBITMAP__ * *,void * *)
0x18009dd92  mov     rbx, [rsp+2E0h+hdsa]
0x18009dd97  mov     edi, eax
0x18009dd99  test    eax, eax
0x18009dd9b  js      short loc_18009DE08
0x18009dd9d  lea     rsi, [r15+210h]
0x18009dda4  mov     rcx, rsi; struct CImageList **
0x18009dda7  call    ?Recreate@CImageList@@KAJPEAPEAV1@@Z; CImageList::Recreate(CImageList * *)
0x18009ddac  mov     edi, eax
0x18009ddae  test    eax, eax
0x18009ddb0  js      short loc_18009DE08
0x18009ddb2  mov     rcx, [rsi]
0x18009ddb5  add     rcx, 40h ; '@'; lpCriticalSection
0x18009ddb9  call    cs:__imp_EnterCriticalSection
0x18009ddbf  mov     rcx, [rsi]; this
0x18009ddc2  call    ?_Destroy@CImageList@@AEAAXXZ; CImageList::_Destroy(void)
0x18009ddc7  mov     r9, [rsp+2E0h+ho]; void *
0x18009ddcc  lea     rdx, [rsp+2E0h+var_288]; struct _ILFILEHEADER *
0x18009ddd1  mov     r8, [rsp+2E0h+var_290]; HBITMAP
0x18009ddd6  mov     rcx, [rsi]; this
0x18009ddd9  mov     [rsp+2E0h+var_2C0], rbx; HBITMAP
0x18009ddde  call    ?_Read@CImageList@@IEAAJPEBU_ILFILEHEADER@@PEAUHBITMAP__@@PEAX1@Z; CImageList::_Read(_ILFILEHEADER const *,HBITMAP__ *,void *,HBITMAP__ *)
0x18009dde3  mov     edi, eax
0x18009dde5  test    eax, eax
0x18009dde7  js      short loc_18009DDF3
0x18009dde9  mov     rcx, [rsi]; this
0x18009ddec  call    ?_ScanForAlpha@CImageList@@IEAAJXZ; CImageList::_ScanForAlpha(void)
0x18009ddf1  mov     edi, eax
0x18009ddf3  mov     rcx, [rsi]
0x18009ddf6  add     rcx, 40h ; '@'; lpCriticalSection
0x18009ddfa  call    cs:__imp_LeaveCriticalSection
0x18009de00  mov     rcx, r12
0x18009de03  mov     rbx, r12
0x18009de06  jmp     short loc_18009DE0D
0x18009de08  mov     rcx, [rsp+2E0h+var_290]; ho
0x18009de0d  test    rcx, rcx
0x18009de10  jz      short loc_18009DE18
0x18009de12  call    cs:__imp_DeleteObject
0x18009de18  test    rbx, rbx
0x18009de1b  jz      loc_18009DC3A
0x18009de21  mov     rcx, rbx; ho
0x18009de24  call    cs:__imp_DeleteObject
0x18009de2a  jmp     loc_18009DC3A
  ... truncated ...
```
