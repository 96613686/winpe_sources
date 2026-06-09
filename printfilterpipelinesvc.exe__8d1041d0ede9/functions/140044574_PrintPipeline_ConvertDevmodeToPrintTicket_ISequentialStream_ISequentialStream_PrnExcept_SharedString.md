# PrintPipeline::ConvertDevmodeToPrintTicket(ISequentialStream *,ISequentialStream *,PrnExcept::SharedString *)

- ea: `0x140044574`
- end: `0x140044977`
- name: `?ConvertDevmodeToPrintTicket@PrintPipeline@@YA_NPEAUISequentialStream@@0PEAVSharedString@PrnExcept@@@Z`
- size: `1027`
- prototype: `bool(PrintPipeline *__hidden this, struct ISequentialStream *, struct ISequentialStream *, struct PrnExcept::SharedString *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400443c4`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000fa68`
- `0x1400123d8`
- `0x140013170`
- `0x14002a5bc`
- `0x140044574`
- `0x140044980`
- `0x140044cac`
- `0x140044cd8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14004469c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400446b6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004469c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400446b6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140044811`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140044811`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400445d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400445d5`
- `prntvpt!__imp_PTOpenProvider` at `0x140044898`
- `prntvpt!__imp_PTOpenProvider` at `0x140044898`
- `prntvpt!__imp_PTCloseProvider` at `0x1400448f3`
- `prntvpt!__imp_PTCloseProvider` at `0x1400448f3`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1400448cb`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1400448cb`

## string_xrefs

- `0x1400446af`: `xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework' xmlns:psk='http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords'`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall PrintPipeline::ConvertDevmodeToPrintTicket(
        struct ISequentialStream *this,
        struct ISequentialStream *a2,
        struct ISequentialStream *a3,
        struct PrnExcept::SharedString *a4)
{
  HRESULT v7; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  int v11; // eax
  int v12; // edx
  const char *v13; // r8
  unsigned int v14; // r9d
  const struct SplException::TSystemException *v15; // r8
  const struct _GUID *v16; // r9
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  __int64 v19; // rax
  int v20; // eax
  const wchar_t *v21; // rdx
  const char *v22; // r8
  unsigned int v23; // r9d
  wchar_t *v24; // rax
  int v25; // eax
  int v26; // edx
  const char *v27; // r8
  unsigned int v28; // r9d
  int v29; // eax
  int v30; // edx
  const char *v31; // r8
  unsigned int v32; // r9d
  HRESULT v34; // eax
  int v35; // edx
  const char *v36; // r8
  int *v37; // r9
  int v38; // eax
  int v39; // edx
  const char *v40; // r8
  unsigned int v41; // r9d
  DEVMODEA *v42; // rbx
  int v43; // edx
  const char *v44; // r8
  unsigned int v45; // r9d
  DEVMODEA *v46; // rdi
  HRESULT v47; // eax
  int v48; // edx
  const char *v49; // r8
  unsigned int v50; // r9d
  HRESULT v51; // eax
  int v52; // edx
  char *v53; // r8
  unsigned int v54; // r9d
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v56; // [rsp+28h] [rbp-D8h]
  HINSTANCE v57; // [rsp+30h] [rbp-D0h]
  _WORD v58[2]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG cbDevmode; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v60; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v61[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  struct ISequentialStream *v63; // [rsp+68h] [rbp-98h]
  __int64 v64; // [rsp+70h] [rbp-90h]
  HPTPROVIDER phProvider; // [rsp+80h] [rbp-80h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp-78h] BYREF
  __int64 v67; // [rsp+90h] [rbp-70h] BYREF
  publicdm *v68; // [rsp+98h] [rbp-68h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h] BYREF
  struct ISequentialStream *v70; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v71[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v72[160]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+160h] [rbp+60h] BYREF

  v60 = 0;
  v67 = 0;
  v7 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &v60);
  if ( v7 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v7, v8, v9, v10);
  v58[0] = 0;
  v62 = 13;
  v63 = this;
  v64 = 0;
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, _WORD *))(*(_QWORD *)v60 + 464LL))(v60, &v62, v58);
  if ( v11 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v11, v12, v13, v14);
  if ( !v58[0] )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v72, "-", 0);
    SplException::TSystemException::InternalInit((SplException::TSystemException *)v72, 1u, v15, v16, ppv, v56, v57);
    SplException::TSystemException::Message((SplException::TSystemException *)v72, "Input PT malformed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v72);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v17 = SysAllocString(L"SelectionNamespaces");
  NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR((NCoreLibrary::TAutoPtrBSTR *)v71, v17);
  v18 = SysAllocString(
          L"xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework' xmlns:psk='http://schem"
           "as.microsoft.com/windows/2003/08/printing/printschemakeywords'");
  NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR((NCoreLibrary::TAutoPtrBSTR *)&v70, v18);
  v62 = 8;
  v63 = v70;
  v19 = *(_QWORD *)v60;
  v64 = 0;
  v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(v19 + 640))(v60, v71[0], &v62);
  if ( v20 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v20, (int)v21, v22, v23);
  v24 = PrnExcept::SysAllocString(
          (PrnExcept *)L"psf:PrintTicket/psf:ParameterInit[@name = 'MXDWPageDevmodeSnapshot']/psf:Value",
          v21,
          v22,
          v23);
  NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR((NCoreLibrary::TAutoPtrBSTR *)&v69, v24);
  v25 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v60 + 296LL))(v60, v69, &v67);
  if ( v25 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v25, v26, v27, v28);
  if ( v67 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64, publicdm **))(*(_QWORD *)v67 + 208LL))(v67, &v68);
    ppstm = 0;
    v34 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v34 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v34, v35, v36, (unsigned int)v37);
    *(_QWORD *)v61 = 0;
    cbDevmode = 0;
    v38 = publicdm::FromBase64String(v68, v61, (unsigned __int8 **)&cbDevmode, v37);
    if ( v38 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v38, v39, v40, v41);
    v42 = *(DEVMODEA **)v61;
    *(_QWORD *)v61 = 0;
    NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrTaskMem<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(v61);
    if ( v42 )
    {
      v46 = v42;
    }
    else
    {
      v42 = 0;
      v46 = 0;
    }
    *(_QWORD *)v61 = v42;
    if ( (cbDevmode & 0x80000000) != 0 )
      SplException::RealThrowFromHR((SplException *)0x80070216LL, v43, v44, v45);
    phProvider = 0;
    v47 = PTOpenProvider((PCWSTR)a3[2].lpVtbl, 1u, &phProvider);
    if ( v47 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v47, v48, v49, v50);
    if ( !v42 )
      v46 = 0;
    v51 = PTConvertDevModeToPrintTicket(phProvider, cbDevmode, v46, kPTJobScope, ppstm);
    if ( v51 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v51, v52, v53, v54);
    PrintPipeline::StreamToSeqStreamCopy(ppstm, (struct IStream *)a2, (struct ISequentialStream *)v53);
    if ( phProvider )
    {
      PTCloseProvider(phProvider);
      phProvider = 0;
    }
    NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrTaskMem<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(v61);
    PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&ppstm);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v68);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v69);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v70);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(v71);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v67);
    PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v60);
    return 1;
  }
  else
  {
    v62 = 13;
    v63 = a2;
    v64 = 0;
    v29 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v60 + 528LL))(v60, &v62);
    if ( v29 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v29, v30, v31, v32);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v69);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v70);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(v71);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v67);
    PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v60);
    return 0;
  }
}

```

## disassembly

```asm
0x140044574  mov     [rsp-8+arg_18], rbx
0x140044579  push    rbp
0x14004457a  push    rdi
0x14004457b  push    r12
0x14004457d  push    r14
0x14004457f  push    r15
0x140044581  lea     rbp, [rsp-110h]
0x140044589  sub     rsp, 210h
0x140044590  mov     rax, cs:__security_cookie
0x140044597  xor     rax, rsp
0x14004459a  mov     [rbp+130h+var_30], rax
0x1400445a1  mov     r15, r8
0x1400445a4  mov     r14, rdx
0x1400445a7  mov     rbx, rcx
0x1400445aa  xor     r12d, r12d
0x1400445ad  mov     [rsp+230h+var_1E8], r12
0x1400445b2  mov     [rbp+130h+var_1A0], r12
0x1400445b6  lea     rax, [rsp+230h+var_1E8]
0x1400445bb  mov     [rsp+230h+ppv], rax; unsigned int
0x1400445c0  lea     r9, IID_IXMLDOMDocument2; riid
0x1400445c7  xor     edx, edx; pUnkOuter
0x1400445c9  lea     r8d, [r12+1]; dwClsContext
0x1400445ce  lea     rcx, CLSID_DOMDocument60; rclsid
0x1400445d5  call    cs:__imp_CoCreateInstance
0x1400445db  test    eax, eax
0x1400445dd  jns     short loc_1400445E7
0x1400445df  mov     ecx, eax; this
0x1400445e1  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400445e7  mov     [rsp+230h+var_1F0], r12w
0x1400445ed  xorps   xmm0, xmm0
0x1400445f0  xor     eax, eax
0x1400445f2  movups  [rsp+230h+var_1D0], xmm0
0x1400445f7  lea     edi, [rax+0Dh]
0x1400445fa  mov     word ptr [rsp+230h+var_1D0], di
0x1400445ff  mov     qword ptr [rsp+230h+var_1D0+8], rbx
0x140044604  mov     rcx, [rsp+230h+var_1E8]
0x140044609  movups  xmm0, [rsp+230h+var_1D0]
0x14004460e  movaps  [rsp+230h+var_1D0], xmm0
0x140044613  mov     [rsp+230h+var_1C0], rax
0x140044618  mov     rax, [rcx]
0x14004461b  lea     r8, [rsp+230h+var_1F0]
0x140044620  lea     rdx, [rsp+230h+var_1D0]
0x140044625  mov     rax, [rax+1D0h]
0x14004462c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044631  test    eax, eax
0x140044633  jns     short loc_14004463D
0x140044635  mov     ecx, eax; this
0x140044637  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14004463d  cmp     [rsp+230h+var_1F0], r12w
0x140044643  jnz     short loc_140044695
0x140044645  xor     r8d, r8d; unsigned int
0x140044648  lea     rdx, asc_1400696D8; "-"
0x14004464f  lea     rcx, [rbp+130h+var_170]; this
0x140044653  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140044658  nop
0x140044659  mov     edx, 1; unsigned int
0x14004465e  lea     rcx, [rbp+130h+var_170]; this
0x140044662  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140044667  lea     rdx, aInputPtMalform; "Input PT malformed"
0x14004466e  lea     rcx, [rbp+130h+var_170]; this
0x140044672  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140044677  lea     rdx, [rbp+130h+var_170]; struct SplException::THResultException *
0x14004467b  lea     rcx, [rbp+130h+pExceptionObject]; this
0x14004467f  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140044684  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14004468b  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x14004468f  call    _CxxThrowException_0
0x140044695  lea     rcx, psz; "SelectionNamespaces"
0x14004469c  call    cs:__imp_SysAllocString
0x1400446a2  mov     rdx, rax; wchar_t *
0x1400446a5  lea     rcx, [rbp+130h+var_180]; this
0x1400446a9  call    ??0TAutoPtrBSTR@NCoreLibrary@@QEAA@PEA_W@Z; NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR(wchar_t *)
0x1400446ae  nop
0x1400446af  lea     rcx, aXmlnsPsfHttpSc; "xmlns:psf='http://schemas.microsoft.com"...
0x1400446b6  call    cs:__imp_SysAllocString
0x1400446bc  mov     rdx, rax; wchar_t *
0x1400446bf  lea     rcx, [rbp+130h+var_188]; this
0x1400446c3  call    ??0TAutoPtrBSTR@NCoreLibrary@@QEAA@PEA_W@Z; NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR(wchar_t *)
0x1400446c8  nop
0x1400446c9  xorps   xmm0, xmm0
0x1400446cc  xor     edx, edx
0x1400446ce  movups  [rsp+230h+var_1D0], xmm0
0x1400446d3  lea     eax, [rdx+8]
0x1400446d6  mov     word ptr [rsp+230h+var_1D0], ax
0x1400446db  mov     rax, [rbp+130h+var_188]
0x1400446df  mov     qword ptr [rsp+230h+var_1D0+8], rax
0x1400446e4  mov     rcx, [rsp+230h+var_1E8]
0x1400446e9  mov     rax, [rcx]
0x1400446ec  movups  xmm0, [rsp+230h+var_1D0]
0x1400446f1  movaps  [rsp+230h+var_1D0], xmm0
0x1400446f6  mov     [rsp+230h+var_1C0], rdx
0x1400446fb  lea     r8, [rsp+230h+var_1D0]
0x140044700  mov     rdx, [rbp+130h+var_180]
0x140044704  mov     rax, [rax+280h]
0x14004470b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044710  test    eax, eax
0x140044712  jns     short loc_14004471C
0x140044714  mov     ecx, eax; this
0x140044716  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14004471c  lea     rcx, aPsfPrintticket; "psf:PrintTicket/psf:ParameterInit[@name"...
0x140044723  call    ?SysAllocString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::SysAllocString(wchar_t const *,char const *,ulong)
0x140044728  mov     rdx, rax; wchar_t *
0x14004472b  lea     rcx, [rbp+130h+var_190]; this
0x14004472f  call    ??0TAutoPtrBSTR@NCoreLibrary@@QEAA@PEA_W@Z; NCoreLibrary::TAutoPtrBSTR::TAutoPtrBSTR(wchar_t *)
0x140044734  nop
0x140044735  mov     rcx, [rsp+230h+var_1E8]
0x14004473a  mov     rax, [rcx]
0x14004473d  lea     r8, [rbp+130h+var_1A0]
0x140044741  mov     rdx, [rbp+130h+var_190]
0x140044745  mov     rax, [rax+128h]
0x14004474c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044751  test    eax, eax
0x140044753  jns     short loc_14004475D
0x140044755  mov     ecx, eax; this
0x140044757  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14004475d  mov     rcx, [rbp+130h+var_1A0]
0x140044761  test    rcx, rcx
0x140044764  jnz     loc_1400447EB
0x14004476a  xorps   xmm0, xmm0
0x14004476d  xor     eax, eax
0x14004476f  movups  [rsp+230h+var_1D0], xmm0
0x140044774  mov     word ptr [rsp+230h+var_1D0], di
0x140044779  mov     qword ptr [rsp+230h+var_1D0+8], r14
0x14004477e  mov     rcx, [rsp+230h+var_1E8]
0x140044783  movups  xmm0, [rsp+230h+var_1D0]
0x140044788  movaps  [rsp+230h+var_1D0], xmm0
0x14004478d  mov     [rsp+230h+var_1C0], rax
0x140044792  mov     rax, [rcx]
0x140044795  lea     rdx, [rsp+230h+var_1D0]
0x14004479a  mov     rax, [rax+210h]
0x1400447a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400447a6  test    eax, eax
0x1400447a8  jns     short loc_1400447B2
0x1400447aa  mov     ecx, eax; this
0x1400447ac  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400447b2  lea     rcx, [rbp+130h+var_190]
0x1400447b6  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x1400447bb  nop
0x1400447bc  lea     rcx, [rbp+130h+var_188]
0x1400447c0  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x1400447c5  nop
0x1400447c6  lea     rcx, [rbp+130h+var_180]
0x1400447ca  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x1400447cf  nop
0x1400447d0  lea     rcx, [rbp+130h+var_1A0]
0x1400447d4  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400447d9  nop
0x1400447da  lea     rcx, [rsp+230h+var_1E8]
0x1400447df  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400447e4  xor     al, al
0x1400447e6  jmp     loc_140044950
0x1400447eb  mov     [rbp+130h+var_198], r12
0x1400447ef  mov     rax, [rcx]
0x1400447f2  lea     rdx, [rbp+130h+var_198]
0x1400447f6  mov     rax, [rax+0D0h]
0x1400447fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044802  mov     [rbp+130h+ppstm], r12
0x140044806  lea     r8, [rbp+130h+ppstm]; ppstm
0x14004480a  mov     edx, 1; fDeleteOnRelease
0x14004480f  xor     ecx, ecx; hGlobal
0x140044811  call    cs:__imp_CreateStreamOnHGlobal
0x140044817  test    eax, eax
0x140044819  jns     short loc_140044823
0x14004481b  mov     ecx, eax; this
0x14004481d  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140044823  mov     qword ptr [rsp+230h+var_1E0], r12
0x140044828  mov     [rsp+230h+cbDevmode], r12d
0x14004482d  lea     r8, [rsp+230h+cbDevmode]; unsigned __int8 **
0x140044832  lea     rdx, [rsp+230h+var_1E0]; wchar_t *
0x140044837  mov     rcx, [rbp+130h+var_198]; this
0x14004483b  call    ?FromBase64String@publicdm@@YAJPEA_WPEAPEAEPEAH@Z; publicdm::FromBase64String(wchar_t *,uchar * *,int *)
0x140044840  test    eax, eax
0x140044842  jns     short loc_14004484C
0x140044844  mov     ecx, eax; this
0x140044846  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14004484c  mov     rbx, qword ptr [rsp+230h+var_1E0]
0x140044851  mov     qword ptr [rsp+230h+var_1E0], r12
0x140044856  lea     rcx, [rsp+230h+var_1E0]
0x14004485b  call    ?Reset@?$TGenericSP@EV?$TAutoPtrTaskMem@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrTaskMem<uchar>,uchar *,0,uchar const *>::Reset(void)
0x140044860  test    rbx, rbx
0x140044863  jz      short loc_14004486A
0x140044865  mov     rdi, rbx
0x140044868  jmp     short loc_140044870
0x14004486a  mov     rbx, r12
0x14004486d  mov     rdi, r12
0x140044870  mov     qword ptr [rsp+230h+var_1E0], rbx
0x140044875  cmp     [rsp+230h+cbDevmode], r12d
0x14004487a  jge     short loc_140044887
0x14004487c  mov     ecx, 80070216h; this
0x140044881  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140044887  mov     [rbp+130h+phProvider], r12
0x14004488b  lea     r8, [rbp+130h+phProvider]; phProvider
0x14004488f  mov     edx, 1; dwVersion
0x140044894  mov     rcx, [r15+10h]; pszPrinterName
0x140044898  call    cs:__imp_PTOpenProvider
0x14004489e  test    eax, eax
0x1400448a0  jns     short loc_1400448AA
0x1400448a2  mov     ecx, eax; this
0x1400448a4  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400448aa  mov     rcx, [rbp+130h+ppstm]
0x1400448ae  test    rbx, rbx
0x1400448b1  cmovz   rdi, r12
0x1400448b5  mov     [rsp+230h+ppv], rcx; pPrintTicket
0x1400448ba  mov     r9d, 2; scope
0x1400448c0  mov     r8, rdi; pDevmode
0x1400448c3  mov     edx, [rsp+230h+cbDevmode]; cbDevmode
0x1400448c7  mov     rcx, [rbp+130h+phProvider]; hProvider
0x1400448cb  call    cs:__imp_PTConvertDevModeToPrintTicket
0x1400448d1  test    eax, eax
0x1400448d3  jns     short loc_1400448DD
0x1400448d5  mov     ecx, eax; this
0x1400448d7  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400448dd  mov     rdx, r14; struct IStream *
0x1400448e0  mov     rcx, [rbp+130h+ppstm]; this
0x1400448e4  call    ?StreamToSeqStreamCopy@PrintPipeline@@YAXPEAUIStream@@PEAUISequentialStream@@@Z; PrintPipeline::StreamToSeqStreamCopy(IStream *,ISequentialStream *)
0x1400448e9  nop
0x1400448ea  mov     rcx, [rbp+130h+phProvider]; hProvider
0x1400448ee  test    rcx, rcx
0x1400448f1  jz      short loc_1400448FD
0x1400448f3  call    cs:__imp_PTCloseProvider
0x1400448f9  mov     [rbp+130h+phProvider], r12
0x1400448fd  lea     rcx, [rsp+230h+var_1E0]
0x140044902  call    ?Reset@?$TGenericSP@EV?$TAutoPtrTaskMem@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrTaskMem<uchar>,uchar *,0,uchar const *>::Reset(void)
0x140044907  nop
0x140044908  lea     rcx, [rbp+130h+ppstm]
0x14004490c  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140044911  nop
0x140044912  lea     rcx, [rbp+130h+var_198]
0x140044916  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x14004491b  nop
0x14004491c  lea     rcx, [rbp+130h+var_190]
0x140044920  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x140044925  nop
0x140044926  lea     rcx, [rbp+130h+var_188]
0x14004492a  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x14004492f  nop
0x140044930  lea     rcx, [rbp+130h+var_180]
0x140044934  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x140044939  nop
0x14004493a  lea     rcx, [rbp+130h+var_1A0]
0x14004493e  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140044943  nop
0x140044944  lea     rcx, [rsp+230h+var_1E8]
0x140044949  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14004494e  mov     al, 1
0x140044950  mov     rcx, [rbp+130h+var_30]
0x140044957  xor     rcx, rsp; StackCookie
0x14004495a  call    __security_check_cookie
0x14004495f  mov     rbx, [rsp+230h+arg_18]
0x140044967  add     rsp, 210h
0x14004496e  pop     r15
0x140044970  pop     r14
0x140044972  pop     r12
0x140044974  pop     rdi
0x140044975  pop     rbp
0x140044976  retn
```
