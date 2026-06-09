# DevhlprGenerateBitmapFromImageBlobInternal(std::vector<uchar,std::allocator<uchar>> &,HBITMAP__ * *)

- ea: `0x180008820`
- end: `0x180008bb4`
- name: `?DevhlprGenerateBitmapFromImageBlobInternal@@YA?AV?$scoped_error@Utag@hresult_error@@@errorlib@@AEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAUHBITMAP__@@@Z`
- size: `916`
- prototype: `_DWORD *__fastcall(_DWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800075d0`

## callees

- `0x1800066d8`
- `0x180006700`
- `0x180008820`
- `0x1800092f8`
- `0x180009bd8`
- `0x180013fac`
- `0x180015894`
- `0x18001e054`
- `0x18001e074`
- `0x1800243f8`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008890`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008b90`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008b90`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008852`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008852`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800088d2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800088d2`
- `KERNEL32!GlobalLock` at `0x180008885`
- `KERNEL32!GlobalLock` at `0x180008885`
- `KERNEL32!GlobalUnlock` at `0x1800088bf`
- `KERNEL32!GlobalUnlock` at `0x1800088bf`
- `GDI32!GetObjectW` at `0x1800089fc`
- `GDI32!GetObjectW` at `0x1800089fc`
- `GDI32!DeleteObject` at `0x180008a23`
- `GDI32!DeleteObject` at `0x180008ac4`
- `GDI32!DeleteObject` at `0x180008a23`
- `GDI32!DeleteObject` at `0x180008ac4`
- `gdiplus!GdipCreateBitmapFromStream` at `0x18000892a`
- `gdiplus!GdipCreateBitmapFromStream` at `0x18000892a`
- `gdiplus!GdipDisposeImage` at `0x180008a2d`
- `gdiplus!GdipDisposeImage` at `0x180008a4f`
- `gdiplus!GdipDisposeImage` at `0x180008ace`
- `gdiplus!GdipDisposeImage` at `0x180008b27`
- `gdiplus!GdipDisposeImage` at `0x180008a2d`
- `gdiplus!GdipDisposeImage` at `0x180008a4f`
- `gdiplus!GdipDisposeImage` at `0x180008ace`
- `gdiplus!GdipDisposeImage` at `0x180008b27`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180008990`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180008990`

## pseudocode

```c
_DWORD *__fastcall DevhlprGenerateBitmapFromImageBlobInternal(_DWORD *a1, __int64 a2, _QWORD *a3)
{
  HGLOBAL v6; // rax
  void *v7; // rbx
  signed int LastError; // eax
  void *v9; // rax
  unsigned int v10; // esi
  unsigned int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // r15
  unsigned int v14; // r12d
  unsigned int v15; // edx
  unsigned int HBITMAPFromBitmap; // eax
  int v17; // esi
  unsigned int v18; // edx
  unsigned int v19; // edx
  HANDLE v20; // rax
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  LPSTREAM ppstm; // [rsp+28h] [rbp-58h] BYREF
  HANDLE h[4]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-30h]
  _OWORD pv[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+48h] BYREF
  unsigned int v30; // [rsp+D8h] [rbp+58h] BYREF
  int v31; // [rsp+DCh] [rbp+5Ch]

  v6 = GlobalAlloc(2u, *(_QWORD *)(a2 + 8) - *(_QWORD *)a2);
  v7 = v6;
  h[1] = v6;
  if ( v6 )
  {
    v9 = GlobalLock(v6);
    if ( v9 )
    {
      memcpy_0(v9, *(const void **)a2, *(_QWORD *)(a2 + 8) - *(_QWORD *)a2);
      GlobalUnlock(v7);
      ppstm = 0;
      v10 = CreateStreamOnHGlobal(v7, 0, &ppstm);
      v29 = v10 | 0x200000000LL;
      if ( (v10 & 0x80000000) != 0 )
      {
        errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
        errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v29);
        v30 = v10;
        v29 = 0x100000000LL;
        errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v29, v23);
        *a1 = v10;
        a1[1] = 2;
        v31 = 5;
        errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
      }
      else
      {
        errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v29);
        v30 = v10;
        v29 = 0x100000000LL;
        errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v29, v11);
        v31 = 3;
        h[2] = &Gdiplus::Image::`vftable';
        v29 = 0;
        v12 = GdipCreateBitmapFromStream(ppstm, &v29);
        v13 = v29;
        h[3] = (HANDLE)v29;
        v27 = 0;
        v14 = HRESULT_FROM_GDIPLUS(v12);
        v29 = v14 | 0x200000000LL;
        if ( (v14 & 0x80000000) != 0 )
        {
          errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
          errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v29);
          v30 = v14;
          v29 = v10 | 0x300000000LL;
          errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v29, v22);
          *a1 = v14;
          a1[1] = 2;
          v31 = 5;
          errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
          GdipDisposeImage(v13);
        }
        else
        {
          errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v29);
          v30 = v14;
          v29 = v10 | 0x300000000LL;
          errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v29, v15);
          v31 = 3;
          h[0] = 0;
          HBITMAPFromBitmap = GdipCreateHBITMAPFromBitmap(v13, h, 4294902015LL);
          if ( HBITMAPFromBitmap )
            v27 = HBITMAPFromBitmap;
          else
            HBITMAPFromBitmap = 0;
          v17 = HRESULT_FROM_GDIPLUS(HBITMAPFromBitmap);
          v29 = (unsigned int)v17 | 0x200000000LL;
          if ( v17 < 0 )
          {
            errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
            errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v29);
            v30 = v17;
            v29 = v14 | 0x300000000LL;
            errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v29, v21);
            *a1 = v17;
            a1[1] = 2;
            v31 = 5;
            errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
            if ( h[0] )
              DeleteObject(h[0]);
          }
          else
          {
            errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v29);
            v30 = v17;
            v29 = v14 | 0x300000000LL;
            errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v29, v18);
            v31 = 3;
            memset(pv, 0, sizeof(pv));
            if ( GetObjectW(h[0], 32, pv) )
            {
              v20 = h[0];
              h[0] = 0;
              *a3 = v20;
              *a1 = v17;
              a1[1] = 2;
              GdipDisposeImage(v13);
              if ( ppstm )
                (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
              goto LABEL_26;
            }
            LODWORD(v29) = -2146435041;
            errorlib::scoped_error<hresult_error::tag>::make_initiated<unsigned long>(a1, &v29);
            if ( h[0] )
              DeleteObject(h[0]);
          }
          GdipDisposeImage(v13);
        }
      }
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v30, v19);
      ATL::CComPtr<IStream>::~CComPtr<IStream>((__int64 *)&ppstm);
    }
    else
    {
      LODWORD(v29) = GetLastError();
      errorlib::scoped_error<hresult_error::tag>::make_initiated<unsigned long>(a1, &v29);
    }
LABEL_26:
    GlobalFree(v7);
    return a1;
  }
  LastError = GetLastError();
  *a1 = LastError;
  a1[1] = 1;
  if ( LastError < 0 )
    errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>();
  return a1;
}

```

## disassembly

```asm
0x180008820  mov     [rsp-38h+arg_0], rbx
0x180008825  push    rbp
0x180008826  push    rsi
0x180008827  push    rdi
0x180008828  push    r12
0x18000882a  push    r13
0x18000882c  push    r14
0x18000882e  push    r15
0x180008830  mov     rbp, rsp
0x180008833  sub     rsp, 80h
0x18000883a  mov     r14, r8
0x18000883d  mov     rsi, rdx
0x180008840  mov     rdi, rcx
0x180008843  xor     r13d, r13d
0x180008846  mov     rdx, [rdx+8]
0x18000884a  sub     rdx, [rsi]; dwBytes
0x18000884d  mov     ecx, 2; uFlags
0x180008852  call    cs:__imp_GlobalAlloc
0x180008858  mov     rbx, rax
0x18000885b  mov     [rbp+var_48], rax
0x18000885f  test    rax, rax
0x180008862  jnz     short loc_180008882
0x180008864  call    cs:__imp_GetLastError
0x18000886a  mov     [rdi], eax
0x18000886c  mov     dword ptr [rdi+4], 1
0x180008873  test    eax, eax
0x180008875  jns     short loc_18000887D
0x180008877  call    ??$error_initiated@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x18000887c  nop
0x18000887d  jmp     loc_180008B96
0x180008882  mov     rcx, rbx; hMem
0x180008885  call    cs:__imp_GlobalLock
0x18000888b  test    rax, rax
0x18000888e  jnz     short loc_1800088AA
0x180008890  call    cs:__imp_GetLastError
0x180008896  mov     dword ptr [rbp+arg_8], eax
0x180008899  lea     rdx, [rbp+arg_8]
0x18000889d  mov     rcx, rdi
0x1800088a0  call    ??$make_initiated@K@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAK@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<ulong>(ulong &&)
0x1800088a5  jmp     loc_180008B8D
0x1800088aa  mov     rdx, [rsi]; Src
0x1800088ad  mov     r8, [rsi+8]
0x1800088b1  sub     r8, rdx; Size
0x1800088b4  mov     rcx, rax; void *
0x1800088b7  call    memcpy_0
0x1800088bc  mov     rcx, rbx; hMem
0x1800088bf  call    cs:__imp_GlobalUnlock
0x1800088c5  mov     [rbp+ppstm], r13
0x1800088c9  lea     r8, [rbp+ppstm]; ppstm
0x1800088cd  xor     edx, edx; fDeleteOnRelease
0x1800088cf  mov     rcx, rbx; hGlobal
0x1800088d2  call    cs:__imp_CreateStreamOnHGlobal
0x1800088d8  mov     esi, eax
0x1800088da  mov     dword ptr [rbp+arg_8], eax
0x1800088dd  mov     dword ptr [rbp+arg_8+4], 2
0x1800088e4  test    eax, eax
0x1800088e6  js      loc_180008B2F
0x1800088ec  lea     rcx, [rbp+arg_8]
0x1800088f0  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x1800088f5  mov     [rbp+arg_18], esi
0x1800088f8  mov     dword ptr [rbp+arg_8], r13d
0x1800088fc  mov     dword ptr [rbp+arg_8+4], 1
0x180008903  lea     rcx, [rbp+arg_8]
0x180008907  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18000890c  mov     [rbp+arg_1C], 3
0x180008913  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18000891a  mov     [rbp+var_40], rax
0x18000891e  mov     [rbp+arg_8], r13
0x180008922  lea     rdx, [rbp+arg_8]
0x180008926  mov     rcx, [rbp+ppstm]
0x18000892a  call    cs:__imp_GdipCreateBitmapFromStream
0x180008930  mov     r15, [rbp+arg_8]
0x180008934  mov     [rbp+var_38], r15
0x180008938  mov     [rbp+var_30], r13d
0x18000893c  mov     ecx, eax
0x18000893e  call    ?HRESULT_FROM_GDIPLUS@@YAJW4Status@Gdiplus@@@Z; HRESULT_FROM_GDIPLUS(Gdiplus::Status)
0x180008943  mov     r12d, eax
0x180008946  mov     dword ptr [rbp+arg_8], eax
0x180008949  mov     dword ptr [rbp+arg_8+4], 2
0x180008950  test    eax, eax
0x180008952  js      loc_180008AD9
0x180008958  lea     rcx, [rbp+arg_8]
0x18000895c  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x180008961  mov     [rbp+arg_18], r12d
0x180008965  mov     dword ptr [rbp+arg_8], esi
0x180008968  mov     dword ptr [rbp+arg_8+4], 3
0x18000896f  lea     rcx, [rbp+arg_8]
0x180008973  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180008978  mov     [rbp+arg_1C], 3
0x18000897f  mov     [rbp+h], r13
0x180008983  mov     r8d, 0FFFF00FFh
0x180008989  lea     rdx, [rbp+h]
0x18000898d  mov     rcx, r15
0x180008990  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x180008996  test    eax, eax
0x180008998  jz      short loc_18000899F
0x18000899a  mov     [rbp+var_30], eax
0x18000899d  jmp     short loc_1800089A2
0x18000899f  mov     eax, r13d
0x1800089a2  mov     ecx, eax
0x1800089a4  call    ?HRESULT_FROM_GDIPLUS@@YAJW4Status@Gdiplus@@@Z; HRESULT_FROM_GDIPLUS(Gdiplus::Status)
0x1800089a9  mov     esi, eax
0x1800089ab  mov     dword ptr [rbp+arg_8], eax
0x1800089ae  mov     dword ptr [rbp+arg_8+4], 2
0x1800089b5  test    eax, eax
0x1800089b7  js      loc_180008A71
0x1800089bd  lea     rcx, [rbp+arg_8]
0x1800089c1  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x1800089c6  mov     [rbp+arg_18], esi
0x1800089c9  mov     dword ptr [rbp+arg_8], r12d
0x1800089cd  mov     dword ptr [rbp+arg_8+4], 3
0x1800089d4  lea     rcx, [rbp+arg_8]
0x1800089d8  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800089dd  mov     [rbp+arg_1C], 3
0x1800089e4  xorps   xmm0, xmm0
0x1800089e7  movups  [rbp+pv], xmm0
0x1800089eb  movups  [rbp+var_18], xmm0
0x1800089ef  lea     r8, [rbp+pv]; pv
0x1800089f3  mov     edx, 20h ; ' '; c
0x1800089f8  mov     rcx, [rbp+h]; h
0x1800089fc  call    cs:__imp_GetObjectW
0x180008a02  test    eax, eax
0x180008a04  jnz     short loc_180008A38
0x180008a06  mov     dword ptr [rbp+arg_8], 8010001Fh
0x180008a0d  lea     rdx, [rbp+arg_8]
0x180008a11  mov     rcx, rdi
0x180008a14  call    ??$make_initiated@K@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAK@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<ulong>(ulong &&)
0x180008a19  nop
0x180008a1a  mov     rcx, [rbp+h]; ho
0x180008a1e  test    rcx, rcx
0x180008a21  jz      short loc_180008A2A
0x180008a23  call    cs:__imp_DeleteObject
0x180008a29  nop
0x180008a2a  mov     rcx, r15
0x180008a2d  call    cs:__imp_GdipDisposeImage
0x180008a33  jmp     loc_180008B79
0x180008a38  mov     rax, [rbp+h]
0x180008a3c  mov     [rbp+h], r13
0x180008a40  mov     [r14], rax
0x180008a43  mov     [rdi], esi
0x180008a45  mov     dword ptr [rdi+4], 2
0x180008a4c  mov     rcx, r15
0x180008a4f  call    cs:__imp_GdipDisposeImage
0x180008a55  nop
0x180008a56  mov     rcx, [rbp+ppstm]
0x180008a5a  test    rcx, rcx
0x180008a5d  jz      short loc_180008A6C
0x180008a5f  mov     rax, [rcx]
0x180008a62  mov     rax, [rax+10h]
0x180008a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a6b  nop
0x180008a6c  jmp     loc_180008B8D
0x180008a71  call    ??$error_received@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x180008a76  lea     rcx, [rbp+arg_8]
0x180008a7a  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x180008a7f  mov     [rbp+arg_18], esi
0x180008a82  mov     dword ptr [rbp+arg_8], r12d
0x180008a86  mov     dword ptr [rbp+arg_8+4], 3
0x180008a8d  lea     rcx, [rbp+arg_8]
0x180008a91  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180008a96  mov     [rbp+arg_1C], 3
0x180008a9d  mov     [rdi], esi
0x180008a9f  mov     dword ptr [rdi+4], 2
0x180008aa6  mov     [rbp+arg_1C], 5
0x180008aad  mov     edx, 3
0x180008ab2  mov     rcx, rdi
0x180008ab5  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180008aba  nop
0x180008abb  mov     rcx, [rbp+h]; ho
0x180008abf  test    rcx, rcx
0x180008ac2  jz      short loc_180008ACB
0x180008ac4  call    cs:__imp_DeleteObject
0x180008aca  nop
0x180008acb  mov     rcx, r15
0x180008ace  call    cs:__imp_GdipDisposeImage
0x180008ad4  jmp     loc_180008B79
0x180008ad9  call    ??$error_received@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x180008ade  lea     rcx, [rbp+arg_8]
0x180008ae2  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x180008ae7  mov     [rbp+arg_18], r12d
0x180008aeb  mov     dword ptr [rbp+arg_8], esi
0x180008aee  mov     dword ptr [rbp+arg_8+4], 3
0x180008af5  lea     rcx, [rbp+arg_8]
0x180008af9  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180008afe  mov     [rbp+arg_1C], 3
0x180008b05  mov     [rdi], r12d
0x180008b08  mov     dword ptr [rdi+4], 2
0x180008b0f  mov     [rbp+arg_1C], 5
0x180008b16  mov     edx, 3
0x180008b1b  mov     rcx, rdi
0x180008b1e  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180008b23  nop
0x180008b24  mov     rcx, r15
0x180008b27  call    cs:__imp_GdipDisposeImage
0x180008b2d  jmp     short loc_180008B79
0x180008b2f  call    ??$error_received@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x180008b34  lea     rcx, [rbp+arg_8]
0x180008b38  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x180008b3d  mov     [rbp+arg_18], esi
0x180008b40  mov     dword ptr [rbp+arg_8], r13d
0x180008b44  mov     dword ptr [rbp+arg_8+4], 1
0x180008b4b  lea     rcx, [rbp+arg_8]
0x180008b4f  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180008b54  mov     [rbp+arg_1C], 3
0x180008b5b  mov     [rdi], esi
0x180008b5d  mov     dword ptr [rdi+4], 2
0x180008b64  mov     [rbp+arg_1C], 5
0x180008b6b  mov     edx, 3
0x180008b70  mov     rcx, rdi
0x180008b73  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180008b78  nop
0x180008b79  lea     rcx, [rbp+arg_18]
0x180008b7d  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180008b82  nop
0x180008b83  lea     rcx, [rbp+ppstm]
0x180008b87  call    ??1?$CComPtr@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtr<IStream>::~CComPtr<IStream>(void)
0x180008b8c  nop
0x180008b8d  mov     rcx, rbx; hMem
0x180008b90  call    cs:__imp_GlobalFree
0x180008b96  mov     rax, rdi
0x180008b99  mov     rbx, [rsp+80h+arg_0]
0x180008ba1  add     rsp, 80h
0x180008ba8  pop     r15
0x180008baa  pop     r14
0x180008bac  pop     r13
0x180008bae  pop     r12
0x180008bb0  pop     rdi
0x180008bb1  pop     rsi
0x180008bb2  pop     rbp
0x180008bb3  retn
```
