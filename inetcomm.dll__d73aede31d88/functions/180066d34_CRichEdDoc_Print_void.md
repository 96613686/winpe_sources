# CRichEdDoc::_Print(void)

- ea: `0x180066d34`
- end: `0x1800671e9`
- name: `?_Print@CRichEdDoc@@AEAAXXZ`
- size: `1205`
- prototype: `void __fastcall(CRichEdDoc *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180066664`

## callees

- `0x180002098`
- `0x180005748`
- `0x180063bdc`
- `0x180066d34`
- `0x18006f720`
- `0x1800c9b80`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrLPSZToBSTR` at `0x180067092`
- `MSOERT2!HrLPSZToBSTR` at `0x180067092`
- `MSOERT2!HrRewindStream` at `0x180066f14`
- `MSOERT2!HrRewindStream` at `0x180066f14`
- `GDI32!DeleteObject` at `0x180067079`
- `GDI32!DeleteObject` at `0x180067079`
- `GDI32!GetDeviceCaps` at `0x180067046`
- `GDI32!GetDeviceCaps` at `0x180067046`
- `GDI32!GetObjectA` at `0x180067029`
- `GDI32!GetObjectA` at `0x180067029`
- `KERNEL32!MulDiv` at `0x180067057`
- `KERNEL32!MulDiv` at `0x180067057`
- `USER32!LoadStringW` at `0x180066e04`
- `USER32!LoadStringW` at `0x180066e6e`
- `USER32!LoadStringW` at `0x180066e04`
- `USER32!LoadStringW` at `0x180066e6e`
- `USER32!GetDC` at `0x180067035`
- `USER32!GetDC` at `0x180067035`
- `USER32!ReleaseDC` at `0x18006706e`
- `USER32!ReleaseDC` at `0x18006706e`
- `OLEAUT32!__imp_SysAllocString` at `0x180066e0e`
- `OLEAUT32!__imp_SysAllocString` at `0x180066e78`
- `OLEAUT32!__imp_SysAllocString` at `0x180066e0e`
- `OLEAUT32!__imp_SysAllocString` at `0x180066e78`
- `OLEAUT32!__imp_SysFreeString` at `0x180067195`
- `OLEAUT32!__imp_SysFreeString` at `0x18006719e`
- `OLEAUT32!__imp_SysFreeString` at `0x180067195`
- `OLEAUT32!__imp_SysFreeString` at `0x18006719e`
- `OLEAUT32!__imp_VariantInit` at `0x180066f76`
- `OLEAUT32!__imp_VariantInit` at `0x180066f80`
- `OLEAUT32!__imp_VariantInit` at `0x180066f76`
- `OLEAUT32!__imp_VariantInit` at `0x180066f80`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180066dc8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180066dc8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800671ac`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800671ac`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066e49`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066eb4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066f45`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066e49`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066eb4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066f45`

## pseudocode

```c
void __fastcall CRichEdDoc::_Print(CRichEdDoc *this)
{
  SAFEARRAY *v2; // rdi
  OLECHAR *v3; // r14
  OLECHAR *v4; // r15
  unsigned int v5; // ebx
  int (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  const struct _GUID *v7; // rdx
  BSTR bstrVal; // r12
  int v9; // r13d
  HDC DC; // rbx
  int DeviceCaps; // eax
  int v12; // eax
  VARIANTARG *p_pvarg; // [rsp+28h] [rbp-D8h]
  LONG rgIndices; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  struct IStream *v18; // [rsp+68h] [rbp-98h] BYREF
  struct IMimeMessageW *v19; // [rsp+70h] [rbp-90h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v21; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  struct tagVARIANT v23; // [rsp+B0h] [rbp-50h] BYREF
  int nNumber[4]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v25[3]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR Buffer[512]; // [rsp+110h] [rbp+10h] BYREF

  v17 = 0;
  v2 = 0;
  v3 = 0;
  rgIndices = 0;
  v4 = 0;
  v18 = 0;
  pv = 0;
  v19 = 0;
  memset(&v23, 0, sizeof(v23));
  if ( *((_QWORD *)this + 90) )
  {
    if ( *((_QWORD *)this + 98) )
    {
      rgsabound = (SAFEARRAYBOUND)3LL;
      v2 = SafeArrayCreate(0xCu, 1u, &rgsabound);
      if ( v2 )
      {
        v23.llVal = (LONGLONG)v2;
        v23.vt = 24576;
        Buffer[0] = 0;
        LoadStringW(g_hLocRes, 0x47Fu, Buffer, 512);
        v4 = SysAllocString(Buffer);
        if ( v4 )
        {
          *((_QWORD *)&pv + 1) = v4;
          LOWORD(pv) = 8;
          rgIndices = 0;
          if ( SafeArrayPutElement(v2, &rgIndices, &pv) >= 0 )
          {
            Buffer[0] = 0;
            LoadStringW(g_hLocRes, 0x480u, Buffer, 512);
            v3 = SysAllocString(Buffer);
            if ( v3 )
            {
              *((_QWORD *)&pv + 1) = v3;
              LOWORD(pv) = 8;
              rgIndices = 1;
              if ( SafeArrayPutElement(v2, &rgIndices, &pv) >= 0
                && (***((int (__fastcall ****)(_QWORD, GUID *, struct IMimeMessageW **))this + 90))(
                     *((_QWORD *)this + 90),
                     &IID_IMimeMessageW,
                     &v19) >= 0
                && (int)GetHeaderTable(v19, *((unsigned __int16 **)this + 100), 0x40000000u, &v18) >= 0 )
              {
                v5 = (unsigned int)v18;
                HrRewindStream(v18);
                *((_QWORD *)&pv + 1) = __PAIR64__(HIDWORD(v18), v5);
                LOWORD(pv) = 13;
                rgIndices = 2;
                if ( SafeArrayPutElement(v2, &rgIndices, &pv) >= 0 )
                {
                  v15 = 0;
                  memset(&pvarg, 0, sizeof(pvarg));
                  memset(&v21, 0, sizeof(v21));
                  VariantInit(&pvarg);
                  VariantInit(&v21);
                  v6 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 86);
                  v21.vt = 0x4000;
                  v21.llVal = *((_QWORD *)this + 92);
                  *(_OWORD *)nNumber = 0;
                  memset(v25, 0, 44);
                  if ( (**v6)(v6, &IID_IOleCommandTarget, &v15) >= 0 )
                  {
                    p_pvarg = &pvarg;
                    (*(void (__fastcall **)(__int64, __int64 *, __int64, _QWORD, VARIANTARG *))(*(_QWORD *)v15 + 32LL))(
                      v15,
                      &CMDSETID_MimeEditHost,
                      28,
                      0,
                      &v21);
                    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v15);
                    bstrVal = pvarg.bstrVal;
                    if ( pvarg.llVal )
                    {
                      v9 = 0;
                      if ( GetObjectA(pvarg.bstrVal, 60, nNumber) >= 0 )
                      {
                        DC = GetDC(0);
                        DeviceCaps = GetDeviceCaps(DC, 90);
                        v12 = MulDiv(nNumber[0], 72, DeviceCaps);
                        v9 = PointSizeToHTMLSize(-v12);
                        ReleaseDC(0, DC);
                      }
                      DeleteObject(bstrVal);
                      LOWORD(pv) = 8;
                      HrLPSZToBSTR((char *)v25 + 12, (char *)&pv + 8);
                      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 98))(
                             *((_QWORD *)this + 98),
                             &IID_IOleCommandTarget,
                             &v15) >= 0 )
                      {
                        p_pvarg = 0;
                        if ( !(*(unsigned int (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v15 + 32LL))(
                                v15,
                                &CGID_MSHTML,
                                31) )
                        {
                          p_pvarg = 0;
                          if ( !(*(unsigned int (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v15 + 32LL))(
                                  v15,
                                  &CGID_MSHTML,
                                  18) )
                          {
                            DWORD2(pv) = v9;
                            LOWORD(pv) = 3;
                            p_pvarg = 0;
                            (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v15 + 32LL))(
                              v15,
                              &CGID_MSHTML,
                              19);
                          }
                        }
                        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v15);
                      }
                    }
                  }
                  OE_IUnknown_Exec(
                    *((struct IUnknown **)this + 98),
                    v7,
                    6u,
                    2 - (*((_DWORD *)this + 198) != 0),
                    &v23,
                    p_pvarg);
                }
              }
            }
          }
        }
      }
    }
  }
  SysFreeString(v3);
  SysFreeString(v4);
  if ( v2 )
    SafeArrayDestroy(v2);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v19);
  OE_SafeReleaseAndNullPtr<IStream>(&v18);
}

```

## disassembly

```asm
0x180066d34  push    rbp
0x180066d36  push    rbx
0x180066d37  push    rsi
0x180066d38  push    rdi
0x180066d39  push    r12
0x180066d3b  push    r13
0x180066d3d  push    r14
0x180066d3f  push    r15
0x180066d41  lea     rbp, [rsp-428h]
0x180066d49  sub     rsp, 528h
0x180066d50  mov     rax, cs:__security_cookie
0x180066d57  xor     rax, rsp
0x180066d5a  mov     [rbp+460h+var_50], rax
0x180066d61  xor     ebx, ebx
0x180066d63  xor     eax, eax
0x180066d65  xorps   xmm0, xmm0
0x180066d68  xorps   xmm1, xmm1
0x180066d6b  mov     rsi, rcx
0x180066d6e  mov     [rsp+560h+var_500], rax
0x180066d73  mov     edi, ebx
0x180066d75  mov     qword ptr [rbp+460h+var_4B0+10h], rax
0x180066d79  mov     r14d, ebx
0x180066d7c  mov     [rsp+560h+rgIndices], ebx
0x180066d80  mov     r15d, ebx
0x180066d83  mov     [rsp+560h+var_4F8], rbx
0x180066d88  movups  [rsp+560h+pv], xmm0
0x180066d8d  mov     [rsp+560h+var_4F0], rbx
0x180066d92  movups  xmmword ptr [rbp+460h+var_4B0], xmm1
0x180066d96  cmp     [rcx+2D0h], rbx
0x180066d9d  jz      loc_180067192
0x180066da3  cmp     [rcx+310h], rbx
0x180066daa  jz      loc_180067192
0x180066db0  lea     r12d, [rax+1]
0x180066db4  mov     qword ptr [rsp+560h+rgsabound.cElements], 3
0x180066dbd  mov     edx, r12d; cDims
0x180066dc0  lea     ecx, [rax+0Ch]; vt
0x180066dc3  lea     r8, [rsp+560h+rgsabound]; rgsabound
0x180066dc8  call    cs:__imp_SafeArrayCreate
0x180066dce  mov     rdi, rax
0x180066dd1  test    rax, rax
0x180066dd4  jz      loc_180067192
0x180066dda  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180066de1  lea     r8, [rbp+460h+Buffer]; lpBuffer
0x180066de5  mov     eax, 6000h
0x180066dea  mov     qword ptr [rbp+460h+var_4B0+8], rdi
0x180066dee  mov     r13d, 200h
0x180066df4  mov     word ptr [rbp+460h+var_4B0], ax
0x180066df8  mov     r9d, r13d; cchBufferMax
0x180066dfb  mov     [rbp+460h+Buffer], bx
0x180066dff  mov     edx, 47Fh; uID
0x180066e04  call    cs:__imp_LoadStringW
0x180066e0a  lea     rcx, [rbp+460h+Buffer]; psz
0x180066e0e  call    cs:__imp_SysAllocString
0x180066e14  mov     r15, rax
0x180066e17  test    rax, rax
0x180066e1a  jz      loc_180067192
0x180066e20  lea     eax, [rbx+8]
0x180066e23  mov     dword ptr [rsp+560h+pv+8], r15d
0x180066e28  mov     rcx, r15
0x180066e2b  mov     word ptr [rsp+560h+pv], ax
0x180066e30  sar     rcx, 20h
0x180066e34  lea     r8, [rsp+560h+pv]; pv
0x180066e39  mov     dword ptr [rsp+560h+pv+0Ch], ecx
0x180066e3d  lea     rdx, [rsp+560h+rgIndices]; rgIndices
0x180066e42  mov     rcx, rdi; psa
0x180066e45  mov     [rsp+560h+rgIndices], ebx
0x180066e49  call    cs:__imp_SafeArrayPutElement
0x180066e4f  test    eax, eax
0x180066e51  js      loc_180067192
0x180066e57  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180066e5e  lea     r8, [rbp+460h+Buffer]; lpBuffer
0x180066e62  mov     r9d, r13d; cchBufferMax
0x180066e65  mov     [rbp+460h+Buffer], bx
0x180066e69  mov     edx, 480h; uID
0x180066e6e  call    cs:__imp_LoadStringW
0x180066e74  lea     rcx, [rbp+460h+Buffer]; psz
0x180066e78  call    cs:__imp_SysAllocString
0x180066e7e  mov     r14, rax
0x180066e81  test    rax, rax
0x180066e84  jz      loc_180067192
0x180066e8a  lea     eax, [rbx+8]
0x180066e8d  mov     dword ptr [rsp+560h+pv+8], r14d
0x180066e92  mov     rcx, r14
0x180066e95  mov     word ptr [rsp+560h+pv], ax
0x180066e9a  sar     rcx, 20h
0x180066e9e  lea     r8, [rsp+560h+pv]; pv
0x180066ea3  mov     dword ptr [rsp+560h+pv+0Ch], ecx
0x180066ea7  lea     rdx, [rsp+560h+rgIndices]; rgIndices
0x180066eac  mov     rcx, rdi; psa
0x180066eaf  mov     [rsp+560h+rgIndices], r12d
0x180066eb4  call    cs:__imp_SafeArrayPutElement
0x180066eba  test    eax, eax
0x180066ebc  js      loc_180067192
0x180066ec2  mov     rcx, [rsi+2D0h]
0x180066ec9  lea     r8, [rsp+560h+var_4F0]
0x180066ece  lea     rdx, IID_IMimeMessageW
0x180066ed5  mov     rax, [rcx]
0x180066ed8  mov     rax, [rax]
0x180066edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ee0  test    eax, eax
0x180066ee2  js      loc_180067192
0x180066ee8  mov     rdx, [rsi+320h]; unsigned __int16 *
0x180066eef  lea     r9, [rsp+560h+var_4F8]; struct IStream **
0x180066ef4  mov     rcx, [rsp+560h+var_4F0]; struct IMimeMessageW *
0x180066ef9  mov     r8d, 40000000h; unsigned int
0x180066eff  call    ?GetHeaderTable@@YAJPEAUIMimeMessageW@@PEAGKPEAPEAUIStream@@@Z; GetHeaderTable(IMimeMessageW *,ushort *,ulong,IStream * *)
0x180066f04  test    eax, eax
0x180066f06  js      loc_180067192
0x180066f0c  mov     rbx, [rsp+560h+var_4F8]
0x180066f11  mov     rcx, rbx
0x180066f14  call    cs:__imp_HrRewindStream
0x180066f1a  lea     eax, [r12+0Ch]
0x180066f1f  mov     dword ptr [rsp+560h+pv+8], ebx
0x180066f23  mov     word ptr [rsp+560h+pv], ax
0x180066f28  lea     r8, [rsp+560h+pv]; pv
0x180066f2d  mov     eax, dword ptr [rsp+560h+var_4F8+4]
0x180066f31  lea     rdx, [rsp+560h+rgIndices]; rgIndices
0x180066f36  mov     rcx, rdi; psa
0x180066f39  mov     dword ptr [rsp+560h+pv+0Ch], eax
0x180066f3d  mov     [rsp+560h+rgIndices], 2
0x180066f45  call    cs:__imp_SafeArrayPutElement
0x180066f4b  xor     ebx, ebx
0x180066f4d  test    eax, eax
0x180066f4f  js      loc_180067192
0x180066f55  xor     eax, eax
0x180066f57  mov     [rsp+560h+var_518], rbx
0x180066f5c  xorps   xmm0, xmm0
0x180066f5f  mov     qword ptr [rbp+460h+pvarg+10h], rax
0x180066f63  xorps   xmm1, xmm1
0x180066f66  mov     qword ptr [rbp+460h+var_4E0+10h], rax
0x180066f6a  lea     rcx, [rbp+460h+pvarg]; pvarg
0x180066f6e  movups  xmmword ptr [rbp+460h+pvarg], xmm0
0x180066f72  movups  xmmword ptr [rbp+460h+var_4E0], xmm1
0x180066f76  call    cs:__imp_VariantInit
0x180066f7c  lea     rcx, [rbp+460h+var_4E0]; pvarg
0x180066f80  call    cs:__imp_VariantInit
0x180066f86  mov     rcx, [rsi+2B0h]
0x180066f8d  lea     r8, [rsp+560h+var_518]
0x180066f92  xorps   xmm0, xmm0
0x180066f95  lea     rdx, IID_IOleCommandTarget
0x180066f9c  movups  xmmword ptr [rbp+460h+var_478], xmm0
0x180066fa0  mov     eax, 4000h
0x180066fa5  mov     word ptr [rbp+460h+var_4E0], ax
0x180066fa9  mov     rax, [rsi+2E0h]
0x180066fb0  mov     qword ptr [rbp+460h+var_4E0+8], rax
0x180066fb4  movups  xmmword ptr [rbp+460h+nNumber], xmm0
0x180066fb8  movups  [rbp+460h+var_488], xmm0
0x180066fbc  movups  xmmword ptr [rbp+460h+var_478+0Ch], xmm0
0x180066fc0  mov     rax, [rcx]
0x180066fc3  mov     rax, [rax]
0x180066fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fcb  test    eax, eax
0x180066fcd  js      loc_180067168
0x180066fd3  mov     rcx, [rsp+560h+var_518]
0x180066fd8  lea     rdx, [rbp+460h+pvarg]
0x180066fdc  mov     [rsp+560h+var_538], rdx
0x180066fe1  lea     r8d, [r12+1Bh]
0x180066fe6  lea     rdx, [rbp+460h+var_4E0]
0x180066fea  xor     r9d, r9d
0x180066fed  mov     [rsp+560h+var_540], rdx
0x180066ff2  lea     rdx, CMDSETID_MimeEditHost
0x180066ff9  mov     rax, [rcx]
0x180066ffc  mov     rax, [rax+20h]
0x180067000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067005  lea     rcx, [rsp+560h+var_518]
0x18006700a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18006700f  mov     r12, qword ptr [rbp+460h+pvarg+8]
0x180067013  test    r12, r12
0x180067016  jz      loc_180067168
0x18006701c  lea     r8, [rbp+460h+nNumber]; pv
0x180067020  mov     rcx, r12; h
0x180067023  lea     edx, [rbx+3Ch]; c
0x180067026  mov     r13d, ebx
0x180067029  call    cs:__imp_GetObjectA
0x18006702f  test    eax, eax
0x180067031  js      short loc_180067076
0x180067033  xor     ecx, ecx; hWnd
0x180067035  call    cs:__imp_GetDC
0x18006703b  mov     rcx, rax; hdc
0x18006703e  mov     edx, 5Ah ; 'Z'; index
0x180067043  mov     rbx, rax
0x180067046  call    cs:__imp_GetDeviceCaps
0x18006704c  mov     ecx, [rbp+460h+nNumber]; nNumber
0x18006704f  mov     edx, 48h ; 'H'; nNumerator
0x180067054  mov     r8d, eax; nDenominator
0x180067057  call    cs:__imp_MulDiv
0x18006705d  neg     eax
0x18006705f  mov     ecx, eax; int
0x180067061  call    ?PointSizeToHTMLSize@@YAHH@Z; PointSizeToHTMLSize(int)
0x180067066  mov     rdx, rbx; hDC
0x180067069  xor     ecx, ecx; hWnd
0x18006706b  mov     r13d, eax
0x18006706e  call    cs:__imp_ReleaseDC
0x180067074  xor     ebx, ebx
0x180067076  mov     rcx, r12; ho
0x180067079  call    cs:__imp_DeleteObject
0x18006707f  mov     eax, 8
0x180067084  lea     rdx, [rsp+560h+pv+8]
0x180067089  lea     rcx, [rbp+460h+var_488+0Ch]
0x18006708d  mov     word ptr [rsp+560h+pv], ax
0x180067092  call    cs:__imp_HrLPSZToBSTR
0x180067098  mov     rcx, [rsi+310h]
0x18006709f  lea     rdx, IID_IOleCommandTarget
0x1800670a6  mov     r8, [rcx]
0x1800670a9  mov     rax, [r8]
0x1800670ac  lea     r8, [rsp+560h+var_518]
0x1800670b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670b6  test    eax, eax
0x1800670b8  js      loc_180067168
0x1800670be  mov     rcx, [rsp+560h+var_518]
0x1800670c3  lea     r12, CGID_MSHTML
0x1800670ca  mov     r9d, 2
0x1800670d0  mov     [rsp+560h+var_538], rbx
0x1800670d5  mov     rdx, r12
0x1800670d8  mov     [rsp+560h+var_540], rbx
0x1800670dd  mov     rax, [rcx]
0x1800670e0  lea     r8d, [r9+1Dh]
0x1800670e4  mov     rax, [rax+20h]
0x1800670e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670ed  test    eax, eax
0x1800670ef  jnz     short loc_18006715E
0x1800670f1  mov     rcx, [rsp+560h+var_518]
0x1800670f6  lea     rdx, [rsp+560h+pv]
0x1800670fb  mov     r9d, 2
0x180067101  mov     [rsp+560h+var_538], rbx
0x180067106  mov     [rsp+560h+var_540], rdx
0x18006710b  mov     rdx, r12
0x18006710e  mov     rax, [rcx]
0x180067111  lea     r8d, [r9+10h]
0x180067115  mov     rax, [rax+20h]
0x180067119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006711e  test    eax, eax
0x180067120  jnz     short loc_18006715E
0x180067122  mov     rcx, [rsp+560h+var_518]
0x180067127  lea     r8, [rsp+560h+pv]
0x18006712c  mov     eax, 3
0x180067131  mov     dword ptr [rsp+560h+pv+8], r13d
0x180067136  mov     word ptr [rsp+560h+pv], ax
0x18006713b  mov     r9d, 2
0x180067141  mov     [rsp+560h+var_538], rbx; struct tagVARIANT *
0x180067146  mov     rdx, r12
0x180067149  mov     rax, [rcx]
0x18006714c  mov     [rsp+560h+var_540], r8
0x180067151  lea     r8d, [r9+11h]
0x180067155  mov     rax, [rax+20h]
0x180067159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006715e  lea     rcx, [rsp+560h+var_518]
0x180067163  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180067168  mov     eax, [rsi+318h]
0x18006716e  mov     r8d, 6; unsigned int
0x180067174  mov     rcx, [rsi+310h]; struct IUnknown *
0x18006717b  neg     eax
0x18006717d  lea     rax, [rbp+460h+var_4B0]
0x180067181  sbb     r9d, r9d
0x180067184  mov     [rsp+560h+var_540], rax; struct tagVARIANT *
0x180067189  add     r9d, 2; unsigned int
0x18006718d  call    ?OE_IUnknown_Exec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; OE_IUnknown_Exec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x180067192  mov     rcx, r14; bstrString
0x180067195  call    cs:__imp_SysFreeString
0x18006719b  mov     rcx, r15; bstrString
0x18006719e  call    cs:__imp_SysFreeString
0x1800671a4  test    rdi, rdi
0x1800671a7  jz      short loc_1800671B2
0x1800671a9  mov     rcx, rdi; psa
0x1800671ac  call    cs:__imp_SafeArrayDestroy
0x1800671b2  lea     rcx, [rsp+560h+var_4F0]
0x1800671b7  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800671bc  lea     rcx, [rsp+560h+var_4F8]
0x1800671c1  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x1800671c6  mov     rcx, [rbp+460h+var_50]
0x1800671cd  xor     rcx, rsp; StackCookie
0x1800671d0  call    __security_check_cookie
0x1800671d5  add     rsp, 528h
0x1800671dc  pop     r15
0x1800671de  pop     r14
0x1800671e0  pop     r13
0x1800671e2  pop     r12
0x1800671e4  pop     rdi
0x1800671e5  pop     rsi
0x1800671e6  pop     rbx
0x1800671e7  pop     rbp
0x1800671e8  retn
```
