# TImgPipelineManager::InitializePipelineX(IPrintFilterSequence *,IPrintPipelinePropertyBag *)

- ea: `0x14001d970`
- end: `0x14001e03d`
- name: `?InitializePipelineX@TImgPipelineManager@@UEAAXPEAUIPrintFilterSequence@@PEAUIPrintPipelinePropertyBag@@@Z`
- size: `1741`
- prototype: `void(TImgPipelineManager *__hidden this, struct IPrintFilterSequence *, struct IPrintPipelinePropertyBag *)`
- caller_count: `0`
- callee_count: `30`
- tags: `broker_com_uri`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004281`
- `0x140004484`
- `0x140005470`
- `0x1400086f8`
- `0x1400123d8`
- `0x14001525c`
- `0x140015980`
- `0x1400172e8`
- `0x140017a4c`
- `0x14001b240`
- `0x14001b5a0`
- `0x14001bd50`
- `0x14001c3d4`
- `0x14001c864`
- `0x14001cebc`
- `0x14001cf70`
- `0x14001d970`
- `0x14001e044`
- `0x14001e138`
- `0x14001e238`
- `0x14001e558`
- `0x14001e924`
- `0x14001fbf8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x140063010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001e00d`
- `KERNEL32!LeaveCriticalSection` at `0x14001e00d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14001da78`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14001dbe2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14001da78`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14001dbe2`

## string_xrefs

- `0x14001da46`: `Cannot add filters to the pipeline when the pipeline is already operating`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall TImgPipelineManager::InitializePipelineX(
        TImgPipelineManager *this,
        struct IPrintFilterSequence *a2,
        struct IPrintPipelinePropertyBag *a3)
{
  const struct SplException::TSystemException *v6; // r8
  const struct _GUID *v7; // r9
  char *v8; // rbx
  const struct SplException::TSystemException *v9; // r8
  const struct _GUID *v10; // r9
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // r8
  unsigned int v14; // r9d
  bool v15; // dl
  char v17; // r14
  char v18; // bl
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // r8
  unsigned int v22; // r9d
  __int64 v23; // rax
  _QWORD *v24; // r12
  const char *v25; // rdx
  bool v26; // cl
  __int64 v27; // r8
  _DWORD *v28; // rax
  _DWORD *v29; // r14
  TImgPipelineManager *v30; // rcx
  char *EventW; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rdx
  const struct SplException::TSystemException *v35; // r8
  const struct _GUID *v36; // r9
  struct _GUID *v37; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v38; // [rsp+28h] [rbp-D8h]
  HINSTANCE v39; // [rsp+30h] [rbp-D0h]
  __int64 v40; // [rsp+30h] [rbp-D0h]
  char v41; // [rsp+40h] [rbp-C0h]
  bool v42; // [rsp+44h] [rbp-BCh]
  _DWORD *v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  char *v45; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall *v46)(TImgPipelineManager *__hidden); // [rsp+60h] [rbp-A0h]
  int v47; // [rsp+68h] [rbp-98h]
  int v48; // [rsp+6Ch] [rbp-94h]
  struct _GUID v49; // [rsp+70h] [rbp-90h] BYREF
  GUID v50; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v51; // [rsp+90h] [rbp-70h] BYREF
  char *v52; // [rsp+A0h] [rbp-60h]
  int v53; // [rsp+ACh] [rbp-54h]
  _QWORD v54[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v55; // [rsp+D0h] [rbp-30h] BYREF
  GUID Buf1; // [rsp+E0h] [rbp-20h] BYREF
  GUID v57; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v58[3]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v59[88]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)&v51.Data1 = a3;
  if ( !a2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)&v55, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)&v55,
      0x80004003,
      v6,
      v7,
      (unsigned int)v37,
      v38,
      v39);
    SplException::TSystemException::Message((SplException::TSystemException *)&v55, "pISequence cannot be NULL");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)&v55);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = (char *)this + 160;
  v52 = (char *)this + 160;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)this + 4);
  if ( *((_BYTE *)this + 217) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)&v55, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)&v55,
      0x80004003,
      v9,
      v10,
      (unsigned int)v37,
      v38,
      v39);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)&v55,
      "Cannot add filters to the pipeline when the pipeline is already operating");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)&v55);
    throw (SplException::THResultException *)pExceptionObject;
  }
  SetErrorInfo(0, 0);
  v11 = (*(__int64 (__fastcall **)(struct IPrintFilterSequence *))(*(_QWORD *)a2 + 24LL))(a2);
  SplException::ThrowFromHRErrorInfo((SplException *)v11, v12, v13, v14);
  if ( (*(unsigned int (__fastcall **)(struct IPrintFilterSequence *))(*(_QWORD *)a2 + 40LL))(a2)
    && *((_DWORD *)this + 65) == 1
    && *((_DWORD *)this + 66) != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids);
    }
    v51 = IID_IXpsDocumentConsumer;
    v49 = IID_IPrintReadStream;
    TImgPipelineManager::InsertStreamOpenXpsConversionFilters(
      (TImgPipelineManager *)((char *)this - 16),
      v15,
      *((_BYTE *)this + 256),
      &v49,
      &v51);
    TImgPipelineManager::CreateInterFilterCommunicators((TImgPipelineManager *)((char *)this - 16), a3);
    if ( (*((_DWORD *)v8 + 11))-- == 1 )
      *((_DWORD *)v8 + 10) = 0;
  }
  else
  {
    v46 = TImgPipelineManager::CleanupFilters;
    v47 = 0;
    v48 = v53;
    v45 = (char *)this - 16;
    v17 = *((_BYTE *)this + 256);
    v41 = v17;
    v18 = 0;
    while ( !(*(unsigned int (__fastcall **)(struct IPrintFilterSequence *))(*(_QWORD *)a2 + 40LL))(a2) )
    {
      v55 = 0;
      Buf1 = GUID_NULL;
      v57 = GUID_NULL;
      v58[1] = 0;
      v58[2] = 0;
      std::wstring::wstring(v59);
      v58[0] = 1;
      v44 = 0;
      SetErrorInfo(0, 0);
      v39 = (HINSTANCE)&v44;
      v38 = (const struct win_musl::TStringEllipseBase *)v58;
      v37 = (struct _GUID *)((char *)&v55 + 8);
      v19 = (*(__int64 (__fastcall **)(struct IPrintFilterSequence *, __int128 *, GUID *, GUID *))(*(_QWORD *)a2 + 48LL))(
              a2,
              &v55,
              &Buf1,
              &v57);
      SplException::ThrowFromHRErrorInfo((SplException *)v19, v20, v21, v22);
      v23 = std::wstring::wstring((__int64)v54, v44);
      std::wstring::operator=(v59, v23);
      std::wstring::_Tidy_deallocate(v54);
      v24 = (_QWORD *)((char *)this + 112);
      if ( !memcmp_0(&Buf1, &IID_IXpsDocumentProvider, 0x10u) && !*v24 )
      {
        if ( *(_BYTE *)(*((_QWORD *)this + 31) + 18LL) )
        {
          v17 = 0;
          v41 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids);
          }
          TImgPipelineManager::InsertSpoolFileToStreamFilter((TImgPipelineManager *)((char *)this - 16));
          v18 = 1;
          v17 = 1;
          v41 = 1;
        }
      }
      if ( !memcmp_0(&Buf1, &IID_IXpsDocumentProvider, 0x10u)
        && *v24
        && !memcmp_0(
              (const void *)(*(_QWORD *)(*((_QWORD *)this + 11)
                                       + 8 * ((*((_QWORD *)this + 12) - 1LL) & (*((_QWORD *)this + 13) - 1LL + *v24)))
                           + 32LL),
              &IID_IPrintWriteStream,
              0x10u) )
      {
        v26 = 0;
        v42 = 0;
        if ( !*((_DWORD *)this + 65) )
        {
          v26 = *((_DWORD *)this + 66) == 2;
          v42 = v26;
        }
        v43 = 0;
        v27 = -1;
        if ( v17 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids);
          }
          v28 = operator new(0x18u, v25, v27);
          v29 = v28;
          *(_QWORD *)&v49.Data1 = v28;
          if ( v28 )
          {
            *(_QWORD *)v28 = &NCOMLibrary::TUnknown::`vftable';
            v28[2] = 1852534389;
            v28[3] = 1;
            _InterlockedAdd(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount, 1u);
            *((_QWORD *)v28 + 2) = -1;
            *(_QWORD *)v28 = &PrnExcept::TRefHandle::`vftable';
          }
          else
          {
            v29 = 0;
          }
          *(_QWORD *)&v50.Data1 = 0;
          v43 = v29;
          PrnExcept::SmartRelease<PrnExcept::TRefHandle>(&v50);
          EventW = TImgPipelineManager::CreateEventW(v30);
          NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(v29 + 4, EventW);
          v32 = *((_QWORD *)v29 + 2);
          if ( v32 == -1 )
            v32 = 0;
          *(_QWORD *)&v49.Data1 = v32;
          v33 = *(_QWORD *)(*((_QWORD *)this + 11)
                          + 8 * ((*((_QWORD *)this + 12) - 1LL) & (*v24 + *((_QWORD *)this + 13) - 1LL)));
          v43 = 0;
          *(_QWORD *)&v50.Data1 = *(_QWORD *)(v33 + 64);
          *(_QWORD *)(v33 + 64) = v29;
          PrnExcept::SmartRelease<PrnExcept::TRefHandle>(&v50);
          v26 = v42;
          v27 = *(_QWORD *)&v49.Data1;
          v17 = v41;
        }
        v34 = (_QWORD *)((char *)this + 80);
        v54[1] = 0;
        v54[2] = *((_QWORD *)this + 13) + *v24;
        if ( this == (TImgPipelineManager *)-80LL )
          v54[0] = 0;
        else
          v54[0] = *v34;
        v49 = IID_IXpsDocumentConsumer;
        v50 = IID_IPrintReadStream;
        v40 = v27;
        LOBYTE(v27) = v17;
        LOBYTE(v34) = v26;
        TImgPipelineManager::InsertStreamToXpsFilter(
          (_DWORD)this - 16,
          (_DWORD)v34,
          v27,
          (unsigned int)&v50,
          (__int64)&v49,
          (__int64)v54,
          v40);
        if ( v18 && *((_DWORD *)this + 65) == 1 && *((_DWORD *)this + 66) != 1 )
        {
          TImgPipelineManager::InsertMsXpsToOpenXpsConversionFilter((TImgPipelineManager *)((char *)this - 16), 0);
          v18 = 0;
        }
        PrnExcept::SmartRelease<PrnExcept::TRefHandle>(&v43);
      }
      std::deque<FilterInterfaceInfo>::_Emplace_back_internal<FilterInterfaceInfo const &>((char *)this + 80, &v55);
      NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v44);
      FilterInterfaceInfo::~FilterInterfaceInfo((FilterInterfaceInfo *)&v55);
      (*(void (__fastcall **)(struct IPrintFilterSequence *))(*(_QWORD *)a2 + 32LL))(a2);
    }
    v45 = 0;
    PrnExcept::TMethodRundown<PrnComps::TImgWriterFileItem>::~TMethodRundown<PrnComps::TImgWriterFileItem>((__int64)&v45);
    v8 = (char *)this + 160;
    if ( !*(_BYTE *)(*((_QWORD *)this + 31) + 16LL) && !*((_QWORD *)this + 14) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)&v55, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)&v55,
        0x8004A123,
        v35,
        v36,
        (unsigned int)v37,
        v38,
        v39);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)&v55,
        "There are no filters in the pipeline.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)&v55);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v46 = TImgPipelineManager::ShutdownEveryFilterAndClear;
    v47 = 0;
    v48 = v53;
    v45 = (char *)this - 16;
    TImgPipelineManager::ProcessFilterInterfaceGuids(
      (TImgPipelineManager *)((char *)this - 16),
      *(struct IPrintPipelinePropertyBag **)&v51.Data1);
    v45 = 0;
    PrnExcept::TMethodRundown<PrnComps::TImgWriterFileItem>::~TMethodRundown<PrnComps::TImgWriterFileItem>((__int64)&v45);
    if ( !--*((_DWORD *)this + 51) )
      *((_DWORD *)this + 50) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v8);
}

```

## disassembly

```asm
0x14001d970  mov     [rsp-8+arg_18], rbx
0x14001d975  push    rbp
0x14001d976  push    rsi
0x14001d977  push    rdi
0x14001d978  push    r12
0x14001d97a  push    r13
0x14001d97c  push    r14
0x14001d97e  push    r15
0x14001d980  lea     rbp, [rsp-120h]
0x14001d988  sub     rsp, 220h
0x14001d98f  mov     rax, cs:__security_cookie
0x14001d996  xor     rax, rsp
0x14001d999  mov     [rbp+150h+var_40], rax
0x14001d9a0  mov     r12, r8
0x14001d9a3  mov     qword ptr [rbp+150h+var_1C0.Data1], r8
0x14001d9a7  mov     r13, rdx
0x14001d9aa  mov     rsi, rcx
0x14001d9ad  test    rdx, rdx
0x14001d9b0  jnz     short loc_14001DA02
0x14001d9b2  xor     r8d, r8d; unsigned int
0x14001d9b5  lea     rdx, asc_1400696D8; "-"
0x14001d9bc  lea     rcx, [rbp+150h+var_180]; this
0x14001d9c0  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001d9c5  nop
0x14001d9c6  mov     edx, 80004003h; unsigned int
0x14001d9cb  lea     rcx, [rbp+150h+var_180]; this
0x14001d9cf  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001d9d4  lea     rdx, aPisequenceCann; "pISequence cannot be NULL"
0x14001d9db  lea     rcx, [rbp+150h+var_180]; this
0x14001d9df  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001d9e4  lea     rdx, [rbp+150h+var_180]; struct SplException::THResultException *
0x14001d9e8  lea     rcx, [rbp+150h+pExceptionObject]; this
0x14001d9ec  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001d9f1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001d9f8  lea     rcx, [rbp+150h+pExceptionObject]; pExceptionObject
0x14001d9fc  call    _CxxThrowException_0
0x14001da02  lea     rbx, [rcx+0A0h]
0x14001da09  mov     [rbp+150h+var_1B0], rbx
0x14001da0d  mov     rcx, rbx; this
0x14001da10  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14001da15  nop
0x14001da16  lea     r15, [rsi-10h]
0x14001da1a  cmp     byte ptr [r15+0E9h], 0
0x14001da22  jz      short loc_14001DA74
0x14001da24  xor     r8d, r8d; unsigned int
0x14001da27  lea     rdx, asc_1400696D8; "-"
0x14001da2e  lea     rcx, [rbp+150h+var_180]; this
0x14001da32  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001da37  nop
0x14001da38  mov     edx, 80004003h; unsigned int
0x14001da3d  lea     rcx, [rbp+150h+var_180]; this
0x14001da41  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001da46  lea     rdx, aCannotAddFilte; "Cannot add filters to the pipeline when"...
0x14001da4d  lea     rcx, [rbp+150h+var_180]; this
0x14001da51  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001da56  lea     rdx, [rbp+150h+var_180]; struct SplException::THResultException *
0x14001da5a  lea     rcx, [rbp+150h+pExceptionObject]; this
0x14001da5e  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001da63  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001da6a  lea     rcx, [rbp+150h+pExceptionObject]; pExceptionObject
0x14001da6e  call    _CxxThrowException_0
0x14001da74  xor     edx, edx; perrinfo
0x14001da76  xor     ecx, ecx; dwReserved
0x14001da78  call    cs:__imp_SetErrorInfo
0x14001da7e  mov     rax, [r13+0]
0x14001da82  mov     rcx, r13
0x14001da85  mov     rax, [rax+18h]
0x14001da89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da8e  mov     ecx, eax; this
0x14001da90  call    ?ThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::ThrowFromHRErrorInfo(long,char const *,ulong)
0x14001da95  mov     rax, [r13+0]
0x14001da99  mov     rcx, r13
0x14001da9c  mov     rax, [rax+28h]
0x14001daa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001daa5  mov     ecx, 1
0x14001daaa  test    eax, eax
0x14001daac  jz      loc_14001DB59
0x14001dab2  cmp     [rsi+104h], ecx
0x14001dab8  jnz     loc_14001DB59
0x14001dabe  cmp     [rsi+108h], ecx
0x14001dac4  jz      loc_14001DB59
0x14001daca  lea     rax, WPP_GLOBAL_Control
0x14001dad1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dad8  cmp     rcx, rax
0x14001dadb  jz      short loc_14001DAFE
0x14001dadd  test    byte ptr [rcx+1Ch], 8
0x14001dae1  jz      short loc_14001DAFE
0x14001dae3  cmp     byte ptr [rcx+19h], 2
0x14001dae7  jb      short loc_14001DAFE
0x14001dae9  mov     edx, 16h
0x14001daee  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14001daf5  mov     rcx, [rcx+10h]
0x14001daf9  call    WPP_SF_
0x14001dafe  movups  xmm0, xmmword ptr cs:IID_IXpsDocumentConsumer.Data1
0x14001db05  movdqu  xmmword ptr [rbp+150h+var_1C0.Data1], xmm0
0x14001db0a  movups  xmm1, xmmword ptr cs:IID_IPrintReadStream.Data1
0x14001db11  movdqu  xmmword ptr [rsp+250h+var_1E0.Data1], xmm1
0x14001db17  lea     rax, [rbp+150h+var_1C0]
0x14001db1b  mov     [rsp+250h+var_230], rax; struct _GUID
0x14001db20  lea     r9, [rsp+250h+var_1E0]; struct _GUID
0x14001db25  mov     r8b, [rsi+100h]; bool
0x14001db2c  mov     rcx, r15; this
0x14001db2f  call    ?InsertStreamOpenXpsConversionFilters@TImgPipelineManager@@AEAAX_N0U_GUID@@1@Z; TImgPipelineManager::InsertStreamOpenXpsConversionFilters(bool,bool,_GUID,_GUID)
0x14001db34  mov     rdx, r12; struct IPrintPipelinePropertyBag *
0x14001db37  mov     rcx, r15; this
0x14001db3a  call    ?CreateInterFilterCommunicators@TImgPipelineManager@@AEAAXPEAUIPrintPipelinePropertyBag@@@Z; TImgPipelineManager::CreateInterFilterCommunicators(IPrintPipelinePropertyBag *)
0x14001db3f  nop
0x14001db40  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14001db44  mov     eax, [rbx+2Ch]
0x14001db47  jnz     loc_14001E00A
0x14001db4d  mov     dword ptr [rbx+28h], 0
0x14001db54  jmp     loc_14001E00A
0x14001db59  lea     rax, ?CleanupFilters@TImgPipelineManager@@AEAAXXZ; TImgPipelineManager::CleanupFilters(void)
0x14001db60  mov     [rsp+250h+var_1F0], rax
0x14001db65  xor     r12d, r12d
0x14001db68  mov     [rsp+250h+var_1E8], r12d
0x14001db6d  mov     eax, [rbp+150h+var_1A4]
0x14001db70  mov     [rsp+250h+var_1E4], eax
0x14001db74  mov     [rsp+250h+var_1F8], r15
0x14001db79  mov     r14b, [rsi+100h]
0x14001db80  mov     [rsp+250h+var_210], r14b
0x14001db85  mov     bl, r12b
0x14001db88  lea     rdi, WPP_GLOBAL_Control
0x14001db8f  mov     rax, [r13+0]
0x14001db93  mov     rcx, r13
0x14001db96  mov     rax, [rax+28h]
0x14001db9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001db9f  test    eax, eax
0x14001dba1  jnz     loc_14001DF49
0x14001dba7  xorps   xmm0, xmm0
0x14001dbaa  movdqa  [rbp+150h+var_180], xmm0
0x14001dbaf  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x14001dbb6  movdqu  [rbp+150h+Buf1], xmm1
0x14001dbbb  movdqu  [rbp+150h+var_160], xmm1
0x14001dbc0  mov     [rbp+150h+var_148], r12
0x14001dbc4  mov     [rbp+150h+var_140], r12
0x14001dbc8  lea     rcx, [rbp+150h+var_138]
0x14001dbcc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14001dbd1  mov     [rbp+150h+var_150], 1
0x14001dbd9  mov     [rsp+250h+var_200], r12
0x14001dbde  xor     edx, edx; perrinfo
0x14001dbe0  xor     ecx, ecx; dwReserved
0x14001dbe2  call    cs:__imp_SetErrorInfo
0x14001dbe8  mov     rax, [r13+0]
0x14001dbec  lea     rcx, [rsp+250h+var_200]
0x14001dbf1  mov     [rsp+250h+var_220], rcx
0x14001dbf6  lea     rcx, [rbp+150h+var_150]
0x14001dbfa  mov     [rsp+250h+var_228], rcx
0x14001dbff  lea     rcx, [rbp+150h+var_180+8]
0x14001dc03  mov     [rsp+250h+var_230], rcx
0x14001dc08  lea     r9, [rbp+150h+var_160]
0x14001dc0c  lea     r8, [rbp+150h+Buf1]
0x14001dc10  lea     rdx, [rbp+150h+var_180]
0x14001dc14  mov     rcx, r13
0x14001dc17  mov     rax, [rax+30h]
0x14001dc1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dc20  mov     ecx, eax; this
0x14001dc22  call    ?ThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::ThrowFromHRErrorInfo(long,char const *,ulong)
0x14001dc27  mov     rdx, [rsp+250h+var_200]
0x14001dc2c  lea     rcx, [rbp+150h+var_1A0]
0x14001dc30  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001dc35  mov     rdx, rax
0x14001dc38  lea     rcx, [rbp+150h+var_138]
0x14001dc3c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001dc41  lea     rcx, [rbp+150h+var_1A0]
0x14001dc45  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001dc4a  mov     r8d, 10h; Size
0x14001dc50  lea     rdx, IID_IXpsDocumentProvider; Buf2
0x14001dc57  lea     rcx, [rbp+150h+Buf1]; Buf1
0x14001dc5b  call    memcmp_0
0x14001dc60  lea     r12, [rsi+70h]
0x14001dc64  test    eax, eax
0x14001dc66  jnz     short loc_14001DCC9
0x14001dc68  cmp     qword ptr [r12], 0
0x14001dc6d  jnz     short loc_14001DCC9
0x14001dc6f  mov     rax, [rsi+0F8h]
0x14001dc76  cmp     byte ptr [rax+12h], 0
0x14001dc7a  jnz     short loc_14001DCC1
0x14001dc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc83  cmp     rcx, rdi
0x14001dc86  jz      short loc_14001DCA9
0x14001dc88  test    byte ptr [rcx+1Ch], 8
0x14001dc8c  jz      short loc_14001DCA9
0x14001dc8e  cmp     byte ptr [rcx+19h], 2
0x14001dc92  jb      short loc_14001DCA9
0x14001dc94  mov     edx, 17h
0x14001dc99  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14001dca0  mov     rcx, [rcx+10h]
0x14001dca4  call    WPP_SF_
0x14001dca9  mov     rcx, r15; this
0x14001dcac  call    ?InsertSpoolFileToStreamFilter@TImgPipelineManager@@AEAAXXZ; TImgPipelineManager::InsertSpoolFileToStreamFilter(void)
0x14001dcb1  mov     eax, 1
0x14001dcb6  mov     bl, al
0x14001dcb8  mov     r14b, al
0x14001dcbb  mov     [rsp+250h+var_210], al
0x14001dcbf  jmp     short loc_14001DCC9
0x14001dcc1  xor     r14b, r14b
0x14001dcc4  mov     [rsp+250h+var_210], r14b
0x14001dcc9  mov     r8d, 10h; Size
0x14001dccf  lea     rdx, IID_IXpsDocumentProvider; Buf2
0x14001dcd6  lea     rcx, [rbp+150h+Buf1]; Buf1
0x14001dcda  call    memcmp_0
0x14001dcdf  test    eax, eax
0x14001dce1  jnz     loc_14001DF0F
0x14001dce7  mov     rcx, [r12]
0x14001dceb  test    rcx, rcx
0x14001dcee  jz      loc_14001DF0F
0x14001dcf4  mov     rax, [rsi+68h]
0x14001dcf8  dec     rax
0x14001dcfb  add     rcx, rax
0x14001dcfe  mov     rax, [rsi+60h]
0x14001dd02  dec     rax
0x14001dd05  and     rcx, rax
0x14001dd08  mov     rax, [rsi+58h]
0x14001dd0c  mov     rcx, [rax+rcx*8]
0x14001dd10  add     rcx, 20h ; ' '; Buf1
0x14001dd14  mov     r8d, 10h; Size
0x14001dd1a  lea     rdx, IID_IPrintWriteStream; Buf2
0x14001dd21  call    memcmp_0
0x14001dd26  test    eax, eax
0x14001dd28  jnz     loc_14001DF0F
0x14001dd2e  xor     cl, cl
0x14001dd30  mov     [rsp+250h+var_20C], ecx
0x14001dd34  cmp     [rsi+104h], eax
0x14001dd3a  jnz     short loc_14001DD52
0x14001dd3c  movzx   ecx, cl
0x14001dd3f  cmp     dword ptr [rsi+108h], 2
0x14001dd46  mov     eax, 1
0x14001dd4b  cmovz   ecx, eax
0x14001dd4e  mov     [rsp+250h+var_20C], ecx
0x14001dd52  mov     [rsp+250h+var_208], 0
0x14001dd5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001dd5f  test    r14b, r14b
0x14001dd62  jz      loc_14001DE6E
0x14001dd68  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd6f  cmp     rcx, rdi
0x14001dd72  jz      short loc_14001DD94
0x14001dd74  test    byte ptr [rcx+1Ch], 8
0x14001dd78  jz      short loc_14001DD94
0x14001dd7a  cmp     byte ptr [rcx+19h], 2
0x14001dd7e  jb      short loc_14001DD94
0x14001dd80  lea     edx, [r8+19h]
0x14001dd84  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14001dd8b  mov     rcx, [rcx+10h]
0x14001dd8f  call    WPP_SF_
0x14001dd94  mov     ecx, 18h; unsigned __int64
0x14001dd99  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14001dd9e  mov     r14, rax
0x14001dda1  mov     qword ptr [rsp+250h+var_1E0.Data1], rax
0x14001dda6  test    rax, rax
0x14001dda9  jz      short loc_14001DDE1
0x14001ddab  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x14001ddb2  mov     [r14], rax
0x14001ddb5  mov     dword ptr [r14+8], 6E6B6E75h
0x14001ddbd  mov     eax, 1
0x14001ddc2  mov     [r14+0Ch], eax
0x14001ddc6  lock add cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA, eax; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14001ddcd  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x14001ddd5  lea     rax, ??_7TRefHandle@PrnExcept@@6B@; const PrnExcept::TRefHandle::`vftable'
0x14001dddc  mov     [r14], rax
0x14001dddf  jmp     short loc_14001DDE4
0x14001dde1  xor     r14d, r14d
0x14001dde4  mov     qword ptr [rbp+150h+var_1D0], 0
0x14001ddec  mov     [rsp+250h+var_208], r14
0x14001ddf1  lea     rcx, [rbp+150h+var_1D0]
0x14001ddf5  call    ??$SmartRelease@VTRefHandle@PrnExcept@@@PrnExcept@@YAXPEAPEAVTRefHandle@0@@Z; PrnExcept::SmartRelease<PrnExcept::TRefHandle>(PrnExcept::TRefHandle * *)
0x14001ddfa  call    ?CreateEventW@TImgPipelineManager@@AEAAPEAXXZ; TImgPipelineManager::CreateEventW(void)
0x14001ddff  mov     rdx, rax
0x14001de02  lea     rcx, [r14+10h]
0x14001de06  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x14001de0b  mov     rcx, [r14+10h]
0x14001de0f  xor     eax, eax
0x14001de11  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001de15  cmovz   rcx, rax
0x14001de19  mov     qword ptr [rsp+250h+var_1E0.Data1], rcx
0x14001de1e  mov     rdx, [rsi+68h]
0x14001de22  dec     rdx
0x14001de25  add     rdx, [r12]
0x14001de29  mov     rax, [rsi+60h]
0x14001de2d  dec     rax
0x14001de30  and     rdx, rax
0x14001de33  mov     rax, [rsi+58h]
0x14001de37  mov     rcx, [rax+rdx*8]
0x14001de3b  mov     [rsp+250h+var_208], 0
0x14001de44  mov     rax, [rcx+40h]
0x14001de48  mov     qword ptr [rbp+150h+var_1D0], rax
0x14001de4c  mov     [rcx+40h], r14
0x14001de50  lea     rcx, [rbp+150h+var_1D0]
0x14001de54  call    ??$SmartRelease@VTRefHandle@PrnExcept@@@PrnExcept@@YAXPEAPEAVTRefHandle@0@@Z; PrnExcept::SmartRelease<PrnExcept::TRefHandle>(PrnExcept::TRefHandle * *)
0x14001de59  mov     ecx, [rsp+250h+var_20C]
0x14001de5d  lea     rdi, WPP_GLOBAL_Control
0x14001de64  mov     r8, qword ptr [rsp+250h+var_1E0.Data1]
0x14001de69  mov     r14b, [rsp+250h+var_210]
0x14001de6e  lea     rdx, [rsi+50h]
0x14001de72  mov     [rbp+150h+var_198], 0
0x14001de7a  mov     rax, [r12]
0x14001de7e  add     rax, [rsi+68h]
0x14001de82  mov     [rbp+150h+var_190], rax
0x14001de86  xor     r12d, r12d
0x14001de89  test    rdx, rdx
  ... truncated ...
```
