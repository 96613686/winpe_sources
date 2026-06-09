# PiboFixedDocumentReceiver::AddPage(IOpcPartUri *,__MIDL___MIDL_itf_msopc_0000_0002_0002,__MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0002 *,__MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0001 *,XpsPush::XpsConsumerLayer::IXpsConsumerPageContent *)

- ea: `0x14002dd30`
- end: `0x14002e15e`
- name: `?AddPage@PiboFixedDocumentReceiver@@UEAAJPEAUIOpcPartUri@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAU__MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0002@@PEAU__MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0001@@PEAUIXpsConsumerPageContent@XpsConsumerLayer@XpsPush@@@Z`
- size: `1070`
- prototype: `int(PiboFixedDocumentReceiver *__hidden this, struct IOpcPartUri *, enum __MIDL___MIDL_itf_msopc_0000_0002_0002, struct __MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0002 *, struct __MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0001 *, struct XpsPush::XpsConsumerLayer::IXpsConsumerPageContent *)`
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000f9d8`
- `0x14000fa68`
- `0x14000fb28`
- `0x140015980`
- `0x1400172e8`
- `0x140020f74`
- `0x140027b1c`
- `0x140027bac`
- `0x140027e28`
- `0x140028dd4`
- `0x14002a054`
- `0x14002bf6c`
- `0x14002dd30`
- `0x14003d6b0`
- `0x140041258`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140055c44`
- `0x140055e58`
- `0x140063010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14002debe`
- `KERNEL32!LeaveCriticalSection` at `0x14002e062`
- `KERNEL32!LeaveCriticalSection` at `0x14002debe`
- `KERNEL32!LeaveCriticalSection` at `0x14002e062`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PiboFixedDocumentReceiver::AddPage(
        PiboFixedDocumentReceiver *this,
        struct IOpcPartUri *a2,
        unsigned int a3,
        struct __MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0002 *a4,
        struct __MIDL___MIDL_itf_win72Exps2Eio_0000_0000_0001 *a5,
        struct XpsPush::XpsConsumerLayer::IXpsConsumerPageContent *a6)
{
  int v8; // r8d
  unsigned int *v9; // rax
  __int64 v10; // rbx
  const char *v11; // rdx
  unsigned int v12; // r8d
  PiboFixedPageReceiver *v13; // r10
  PiboFixedPageReceiver *v14; // rdi
  char v15; // r14
  bool v16; // zf
  int v17; // eax
  int v18; // edx
  const char *v19; // r8
  unsigned int v20; // r9d
  int v21; // eax
  int v22; // edx
  const char *v23; // r8
  unsigned int v24; // r9d
  struct win_dox::ByteSender *v25; // rax
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  unsigned int v29; // r9d
  struct win_dox::ByteSender *v30; // rax
  int v31; // eax
  int v32; // edx
  const char *v33; // r8
  unsigned int v34; // r9d
  const struct SplException::TSystemException *v35; // r8
  const struct _GUID *v36; // r9
  unsigned int *v37; // r8
  SplException *v39; // rbx
  struct SplException::TSystemException *v40; // rdx
  __int64 v41; // [rsp+0h] [rbp-248h] BYREF
  bool v42[8]; // [rsp+20h] [rbp-228h]
  struct PrnExcept::SharedString *v43; // [rsp+28h] [rbp-220h]
  HINSTANCE v44; // [rsp+30h] [rbp-218h]
  PiboFixedPageReceiver *v45; // [rsp+40h] [rbp-208h] BYREF
  unsigned int v46; // [rsp+48h] [rbp-200h]
  __int64 v47; // [rsp+50h] [rbp-1F8h] BYREF
  PiboFixedPageReceiver *v48; // [rsp+58h] [rbp-1F0h] BYREF
  PiboFixedPageReceiver *v49; // [rsp+60h] [rbp-1E8h] BYREF
  void **v50; // [rsp+68h] [rbp-1E0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-1D8h]
  void **v52; // [rsp+78h] [rbp-1D0h] BYREF
  __int64 v53; // [rsp+80h] [rbp-1C8h]
  SplException::TSystemException *v54; // [rsp+88h] [rbp-1C0h] BYREF
  __int64 v55[3]; // [rsp+90h] [rbp-1B8h] BYREF
  char v56[8]; // [rsp+A8h] [rbp-1A0h] BYREF
  unsigned int v57[2]; // [rsp+B0h] [rbp-198h] BYREF
  unsigned __int64 v58; // [rsp+C8h] [rbp-180h]
  _BYTE v59[160]; // [rsp+D0h] [rbp-178h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+170h] [rbp-D8h] BYREF
  std::bad_alloc *v61; // [rsp+210h] [rbp-38h] BYREF
  std::exception *v62; // [rsp+218h] [rbp-30h] BYREF

  v46 = 0;
  try
  {
    win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v55, a2);
    win_dox::Uri::GetAbsoluteUri(v55, (OLECHAR *)v57);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = v57;
      if ( v58 > 7 )
        v9 = *(unsigned int **)v57;
      WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, v8, (_DWORD)this - 32, (__int64)v9);
    }
    v10 = *((_QWORD *)this + 13);
    if ( *(_QWORD *)std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(
                      v10 + 272,
                      v56,
                      v55) != *(_QWORD *)(v10 + 272) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v59, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v59,
        0x8000FFFF,
        v35,
        v36,
        *(unsigned int *)v42,
        v43,
        v44);
      v37 = v57;
      if ( v58 > 7 )
        v37 = *(unsigned int **)v57;
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v59,
        "AddPage() : the same fixed page %ws part is referenced more than once (M12.3).",
        v37);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v59);
      throw (SplException::THResultException *)pExceptionObject;
    }
    std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::insert<0,0>(
      (__int64 *)(*((_QWORD *)this + 13) + 272LL),
      (__int64)&v52,
      (const struct win_dox::OpcPartUri *)v55);
    v49 = 0;
    v13 = (PiboFixedPageReceiver *)operator new(0xA0u, v11, v12);
    v45 = v13;
    if ( v13 )
      v14 = PiboFixedPageReceiver::PiboFixedPageReceiver(
              v13,
              (const struct win_dox::OpcPartUri *)v55,
              a3,
              *((struct IImgFilePool ***)this + 13),
              *((_BYTE *)this + 120),
              *((struct PrnExcept::SharedString **)this + 16));
    else
      v14 = 0;
    v45 = 0;
    v49 = v14;
    PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v45);
    NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
    v15 = *((_BYTE *)this + 144);
    v16 = (*((_DWORD *)this + 15))-- == 1;
    if ( v16 )
      *((_DWORD *)this + 14) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v48 = 0;
    v17 = (*(__int64 (__fastcall **)(struct XpsPush::XpsConsumerLayer::IXpsConsumerPageContent *, PiboFixedPageReceiver **))(*(_QWORD *)a6 + 32LL))(
            a6,
            &v48);
    if ( v17 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v17, v18, v19, v20);
    v47 = 0;
    v21 = (*(__int64 (__fastcall **)(struct XpsPush::XpsConsumerLayer::IXpsConsumerPageContent *, __int64 *))(*(_QWORD *)a6 + 24LL))(
            a6,
            &v47);
    if ( v21 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v21, v22, v23, v24);
    v45 = v48;
    PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)v48);
    if ( v15 )
    {
      v25 = (struct win_dox::ByteSender *)win_dox::ByteSender::ByteSender(&v50, &v45);
      PiboFixedPageReceiver::SetByteSender(v14, v25);
      v50 = &win_dox::StartSendBase<IByteSender>::`vftable';
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 32LL))(
              v47,
              ((unsigned __int64)v14 + 120) & ((unsigned __int128)-(__int128)(unsigned __int64)v14 >> 64));
      if ( v26 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v26, v27, v28, v29);
      WaitingLockedQueue<IUnknown>::Add((LPCRITICAL_SECTION)(*((_QWORD *)this + 13) + 96LL));
    }
    else
    {
      v30 = (struct win_dox::ByteSender *)win_dox::ByteSender::ByteSender(&v52, &v45);
      PiboFixedPageReceiver::SetByteSender(v14, v30);
      v52 = &win_dox::StartSendBase<IByteSender>::`vftable';
      if ( v53 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        v53 = 0;
      }
      v31 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v47 + 32LL))(
              v47,
              ((unsigned __int64)v14 + 120) & -(__int64)(v14 != 0));
      if ( v31 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v31, v32, v33, v34);
      v50 = (void **)((char *)this + 16);
      NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
      std::deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>::_Emplace_back_internal<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver> const &>(
        (char *)this + 152,
        &v49);
      v16 = (*((_DWORD *)this + 15))-- == 1;
      if ( v16 )
        *((_DWORD *)this + 14) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    }
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v47);
    PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v48);
    PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v49);
    std::wstring::_Tidy_deallocate(v57);
    win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v55);
  }
  catch ( SplException::TSystemException *v54 )
  {
    v40 = (struct SplException::TSystemException *)&v41;
    v39 = v54;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v54);
    return (unsigned int)SplException::SetErrorInfoFromException(v39, v40);
  }
  catch ( std::bad_alloc *v61 )
  {
    v46 = -2147024882;
    SetErrorInfo(0, 0);
    return v46;
  }
  catch ( std::exception *v62 )
  {
    v46 = -2147418113;
    SetErrorInfo(0, 0);
  }
  return v46;
}

```

## disassembly

```asm
0x14002dd30  mov     [rsp+arg_10], rbx
0x14002dd35  mov     [rsp+arg_18], rsi
0x14002dd3a  push    rdi
0x14002dd3b  push    r14
0x14002dd3d  push    r15
0x14002dd3f  sub     rsp, 230h
0x14002dd46  mov     rax, cs:__security_cookie
0x14002dd4d  xor     rax, rsp
0x14002dd50  mov     [rsp+248h+var_28], rax
0x14002dd58  mov     edi, r8d
0x14002dd5b  mov     rsi, rcx
0x14002dd5e  mov     r15, [rsp+248h+arg_28]
0x14002dd66  mov     [rsp+248h+var_200], 0
0x14002dd6e  lea     rcx, [rsp+248h+var_1B8]; this
0x14002dd76  call    ??$?0PEAUIOpcPartUri@@@OpcPartUri@win_dox@@QEAA@PEAUIOpcPartUri@@@Z; win_dox::OpcPartUri::OpcPartUri(IOpcPartUri *)
0x14002dd7b  nop
0x14002dd7c  lea     rdx, [rsp+248h+var_198]
0x14002dd84  lea     rcx, [rsp+248h+var_1B8]
0x14002dd8c  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x14002dd91  nop
0x14002dd92  lea     rax, WPP_GLOBAL_Control
0x14002dd99  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dda0  cmp     rcx, rax
0x14002dda3  jz      short loc_14002DDE2
0x14002dda5  test    byte ptr [rcx+1Ch], 10h
0x14002dda9  jz      short loc_14002DDE2
0x14002ddab  cmp     byte ptr [rcx+19h], 2
0x14002ddaf  jb      short loc_14002DDE2
0x14002ddb1  lea     rax, [rsp+248h+var_198]
0x14002ddb9  cmp     [rsp+248h+var_180], 7
0x14002ddc2  cmova   rax, qword ptr [rsp+248h+var_198]
0x14002ddcb  lea     r9, [rsi-20h]
0x14002ddcf  mov     edx, 6Fh ; 'o'
0x14002ddd4  mov     qword ptr [rsp+248h+var_228], rax; unsigned int
0x14002ddd9  mov     rcx, [rcx+10h]
0x14002dddd  call    WPP_SF_qS
0x14002dde2  mov     rbx, [rsi+68h]
0x14002dde6  lea     r8, [rsp+248h+var_1B8]
0x14002ddee  lea     rdx, [rsp+248h+var_1A0]
0x14002ddf6  lea     rcx, [rbx+110h]
0x14002ddfd  call    ?find@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VOpcPartUri@win_dox@@@std@@@std@@@2@AEBVOpcPartUri@win_dox@@@Z; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(win_dox::OpcPartUri const &)
0x14002de02  mov     rcx, [rbx+110h]
0x14002de09  cmp     [rax], rcx
0x14002de0c  jnz     loc_14002E0AB
0x14002de12  mov     rcx, [rsi+68h]
0x14002de16  add     rcx, 110h
0x14002de1d  lea     r8, [rsp+248h+var_1B8]
0x14002de25  lea     rdx, [rsp+248h+var_1D0]
0x14002de2a  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VOpcPartUri@win_dox@@@std@@@std@@@std@@_N@1@AEBVOpcPartUri@win_dox@@@Z; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::insert<0,0>(win_dox::OpcPartUri const &)
0x14002de2f  mov     [rsp+248h+var_1E8], 0
0x14002de38  mov     ecx, 0A0h; unsigned __int64
0x14002de3d  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14002de42  mov     r10, rax
0x14002de45  mov     [rsp+248h+var_208], rax
0x14002de4a  test    rax, rax
0x14002de4d  jz      short loc_14002DE7E
0x14002de4f  mov     rcx, [rsi+80h]
0x14002de56  mov     [rsp+248h+var_220], rcx; struct PrnExcept::SharedString *
0x14002de5b  mov     al, [rsi+78h]
0x14002de5e  mov     [rsp+248h+var_228], al; bool
0x14002de62  mov     r9, [rsi+68h]; struct XpsObjectModelState *
0x14002de66  mov     r8d, edi; enum __MIDL___MIDL_itf_msopc_0000_0002_0002
0x14002de69  lea     rdx, [rsp+248h+var_1B8]; struct win_dox::OpcPartUri *
0x14002de71  mov     rcx, r10; this
0x14002de74  call    ??0PiboFixedPageReceiver@@QEAA@AEBVOpcPartUri@win_dox@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAVXpsObjectModelState@@_NPEAVSharedString@PrnExcept@@@Z; PiboFixedPageReceiver::PiboFixedPageReceiver(win_dox::OpcPartUri const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,XpsObjectModelState *,bool,PrnExcept::SharedString *)
0x14002de79  mov     rdi, rax
0x14002de7c  jmp     short loc_14002DE80
0x14002de7e  xor     edi, edi
0x14002de80  mov     [rsp+248h+var_208], 0
0x14002de89  mov     [rsp+248h+var_1E8], rdi
0x14002de8e  lea     rcx, [rsp+248h+var_208]
0x14002de93  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x14002de98  lea     rbx, [rsi+10h]
0x14002de9c  mov     rcx, rbx; this
0x14002de9f  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14002dea4  mov     r14b, [rsi+90h]
0x14002deab  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14002deaf  mov     eax, [rbx+2Ch]
0x14002deb2  jnz     short loc_14002DEBB
0x14002deb4  mov     dword ptr [rbx+28h], 0
0x14002debb  mov     rcx, rbx; lpCriticalSection
0x14002debe  call    cs:__imp_LeaveCriticalSection
0x14002dec4  mov     [rsp+248h+var_1F0], 0
0x14002decd  mov     rax, [r15]
0x14002ded0  lea     rdx, [rsp+248h+var_1F0]
0x14002ded5  mov     rcx, r15
0x14002ded8  mov     rax, [rax+20h]
0x14002dedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002dee1  test    eax, eax
0x14002dee3  jns     short loc_14002DEEC
0x14002dee5  mov     ecx, eax; this
0x14002dee7  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14002deec  mov     [rsp+248h+var_1F8], 0
0x14002def5  mov     rax, [r15]
0x14002def8  lea     rdx, [rsp+248h+var_1F8]
0x14002defd  mov     rcx, r15
0x14002df00  mov     rax, [rax+18h]
0x14002df04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002df09  test    eax, eax
0x14002df0b  jns     short loc_14002DF14
0x14002df0d  mov     ecx, eax; this
0x14002df0f  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14002df14  mov     rcx, [rsp+248h+var_1F0]
0x14002df19  mov     [rsp+248h+var_208], rcx
0x14002df1e  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14002df23  lea     rdx, [rsp+248h+var_208]
0x14002df28  test    r14b, r14b
0x14002df2b  jz      loc_14002DFBE
0x14002df31  lea     rcx, [rsp+248h+var_1E0]
0x14002df36  call    ??$?0V?$TRefSmartPtr@UIByteSender@@@PrnExcept@@@ByteSender@win_dox@@QEAA@V?$TRefSmartPtr@UIByteSender@@@PrnExcept@@@Z; win_dox::ByteSender::ByteSender(PrnExcept::TRefSmartPtr<IByteSender>)
0x14002df3b  nop
0x14002df3c  mov     rdx, rax; struct win_dox::ByteSender *
0x14002df3f  mov     rcx, rdi; this
0x14002df42  call    ?SetByteSender@PiboFixedPageReceiver@@QEAAXAEAVByteSender@win_dox@@@Z; PiboFixedPageReceiver::SetByteSender(win_dox::ByteSender &)
0x14002df47  nop
0x14002df48  lea     rax, ??_7?$StartSendBase@UIByteSender@@@win_dox@@6B@; const win_dox::StartSendBase<IByteSender>::`vftable'
0x14002df4f  mov     [rsp+248h+var_1E0], rax
0x14002df54  mov     rcx, [rsp+248h+var_1D8]
0x14002df59  test    rcx, rcx
0x14002df5c  jz      short loc_14002DF73
0x14002df5e  mov     rax, [rcx]
0x14002df61  mov     rax, [rax+10h]
0x14002df65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002df6a  mov     [rsp+248h+var_1D8], 0
0x14002df73  mov     rcx, [rsp+248h+var_1F8]
0x14002df78  mov     r9, [rcx]
0x14002df7b  mov     rax, rdi
0x14002df7e  lea     r8, [rdi+78h]
0x14002df82  neg     rax
0x14002df85  sbb     rdx, rdx
0x14002df88  and     rdx, r8
0x14002df8b  mov     rax, [r9+20h]
0x14002df8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002df94  test    eax, eax
0x14002df96  jns     short loc_14002DF9F
0x14002df98  mov     ecx, eax; this
0x14002df9a  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14002df9f  lea     rax, [rdi+10h]
0x14002dfa3  neg     rdi
0x14002dfa6  sbb     rdx, rdx
0x14002dfa9  and     rdx, rax
0x14002dfac  mov     rcx, [rsi+68h]
0x14002dfb0  add     rcx, 60h ; '`'; lpCriticalSection
0x14002dfb4  call    ?Add@?$WaitingLockedQueue@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; WaitingLockedQueue<IUnknown>::Add(IUnknown *)
0x14002dfb9  jmp     loc_14002E069
0x14002dfbe  lea     rcx, [rsp+248h+var_1D0]
0x14002dfc3  call    ??$?0V?$TRefSmartPtr@UIByteSender@@@PrnExcept@@@ByteSender@win_dox@@QEAA@V?$TRefSmartPtr@UIByteSender@@@PrnExcept@@@Z; win_dox::ByteSender::ByteSender(PrnExcept::TRefSmartPtr<IByteSender>)
0x14002dfc8  nop
0x14002dfc9  mov     rdx, rax; struct win_dox::ByteSender *
0x14002dfcc  mov     rcx, rdi; this
0x14002dfcf  call    ?SetByteSender@PiboFixedPageReceiver@@QEAAXAEAVByteSender@win_dox@@@Z; PiboFixedPageReceiver::SetByteSender(win_dox::ByteSender &)
0x14002dfd4  nop
0x14002dfd5  lea     rax, ??_7?$StartSendBase@UIByteSender@@@win_dox@@6B@; const win_dox::StartSendBase<IByteSender>::`vftable'
0x14002dfdc  mov     [rsp+248h+var_1D0], rax
0x14002dfe1  mov     rcx, [rsp+248h+var_1C8]
0x14002dfe9  test    rcx, rcx
0x14002dfec  jz      short loc_14002E006
0x14002dfee  mov     rax, [rcx]
0x14002dff1  mov     rax, [rax+10h]
0x14002dff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002dffa  mov     [rsp+248h+var_1C8], 0
0x14002e006  mov     rcx, [rsp+248h+var_1F8]
0x14002e00b  mov     r8, [rcx]
0x14002e00e  lea     rax, [rdi+78h]
0x14002e012  neg     rdi
0x14002e015  sbb     rdx, rdx
0x14002e018  and     rdx, rax
0x14002e01b  mov     rax, [r8+20h]
0x14002e01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e024  test    eax, eax
0x14002e026  jns     short loc_14002E02F
0x14002e028  mov     ecx, eax; this
0x14002e02a  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14002e02f  mov     [rsp+248h+var_1E0], rbx
0x14002e034  mov     rcx, rbx; this
0x14002e037  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14002e03c  nop
0x14002e03d  lea     rcx, [rsi+98h]
0x14002e044  lea     rdx, [rsp+248h+var_1E8]
0x14002e049  call    ??$_Emplace_back_internal@AEBV?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@@?$deque@V?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@@std@@@std@@AEAAXAEBV?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@@Z; std::deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>::_Emplace_back_internal<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver> const &>(PrnExcept::TRefSmartPtr<PiboFixedPageReceiver> const &)
0x14002e04e  nop
0x14002e04f  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14002e053  mov     eax, [rbx+2Ch]
0x14002e056  jnz     short loc_14002E05F
0x14002e058  mov     dword ptr [rbx+28h], 0
0x14002e05f  mov     rcx, rbx; lpCriticalSection
0x14002e062  call    cs:__imp_LeaveCriticalSection
0x14002e068  nop
0x14002e069  lea     rcx, [rsp+248h+var_1F8]
0x14002e06e  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002e073  nop
0x14002e074  lea     rcx, [rsp+248h+var_1F0]
0x14002e079  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002e07e  nop
0x14002e07f  lea     rcx, [rsp+248h+var_1E8]
0x14002e084  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x14002e089  nop
0x14002e08a  lea     rcx, [rsp+248h+var_198]
0x14002e092  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002e097  nop
0x14002e098  lea     rcx, [rsp+248h+var_1B8]; this
0x14002e0a0  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x14002e0a5  nop
0x14002e0a6  jmp     loc_14002E131
0x14002e0ab  xor     r8d, r8d; unsigned int
0x14002e0ae  lea     rdx, asc_1400696D8; "-"
0x14002e0b5  lea     rcx, [rsp+248h+var_178]; this
0x14002e0bd  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14002e0c2  nop
0x14002e0c3  mov     edx, 8000FFFFh; unsigned int
0x14002e0c8  lea     rcx, [rsp+248h+var_178]; this
0x14002e0d0  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14002e0d5  lea     r8, [rsp+248h+var_198]
0x14002e0dd  cmp     [rsp+248h+var_180], 7
0x14002e0e6  cmova   r8, qword ptr [rsp+248h+var_198]
0x14002e0ef  lea     rdx, aAddpageTheSame; "AddPage() : the same fixed page %ws par"...
0x14002e0f6  lea     rcx, [rsp+248h+var_178]; this
0x14002e0fe  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14002e103  lea     rdx, [rsp+248h+var_178]; struct SplException::THResultException *
0x14002e10b  lea     rcx, [rsp+248h+pExceptionObject]; this
0x14002e113  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14002e118  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14002e11f  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x14002e127  call    _CxxThrowException_0
0x14002e12d  jmp     short loc_14002E131
0x14002e12f  jmp     short $+2
0x14002e131  mov     eax, [rsp+248h+var_200]
0x14002e135  mov     rcx, [rsp+248h+var_28]
0x14002e13d  xor     rcx, rsp; StackCookie
0x14002e140  call    __security_check_cookie
0x14002e145  lea     r11, [rsp+248h+var_18]
0x14002e14d  mov     rbx, [r11+30h]
0x14002e151  mov     rsi, [r11+38h]
0x14002e155  mov     rsp, r11
0x14002e158  pop     r15
0x14002e15a  pop     r14
0x14002e15c  pop     rdi
0x14002e15d  retn
```
