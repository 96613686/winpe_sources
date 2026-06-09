# SplFilters::MsXpsToOpenXpsConversionFilter::ConvertResourceDictionaryFromMsXpsToOpenXps(PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>,std::map<win_dox::OpcPartUri,IStream *,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,IStream *>>> &)

- ea: `0x140025ee4`
- end: `0x1400261c9`
- name: `?ConvertResourceDictionaryFromMsXpsToOpenXps@MsXpsToOpenXpsConversionFilter@SplFilters@@AEAAXV?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@AEAV?$map@VOpcPartUri@win_dox@@PEAUIStream@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@5@@std@@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1400267f0`

## callees

- `0x140002070`
- `0x14000f9d8`
- `0x14000fa68`
- `0x14000fb28`
- `0x14001b1f8`
- `0x140024760`
- `0x1400248d0`
- `0x140024b68`
- `0x140024be0`
- `0x140024d64`
- `0x140025478`
- `0x1400254d4`
- `0x1400254fc`
- `0x140025914`
- `0x140025ee4`
- `0x1400261d0`
- `0x1400263c8`
- `0x140027b1c`
- `0x140042c98`
- `0x14004650c`
- `0x140055bc4`
- `0x140055c44`
- `0x14005a1a4`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140025fd4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140025fd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SplFilters::MsXpsToOpenXpsConversionFilter::ConvertResourceDictionaryFromMsXpsToOpenXps(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  const struct win_dox::OpcPartUri *v7; // r14
  __int64 v8; // rbx
  HRESULT v9; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  win_dox::OpcPartUri *v13; // rax
  __int64 v14; // rdx
  struct IStream *v15; // r9
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  win_dox::OpcPartUri *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  LPSTREAM ppstm; // [rsp+20h] [rbp-E0h] BYREF
  LPSTREAM v26; // [rsp+28h] [rbp-D8h] BYREF
  struct IStream *v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v35[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[24]; // [rsp+80h] [rbp-80h] BYREF
  LPSTREAM v37; // [rsp+98h] [rbp-68h]
  __int64 *v38; // [rsp+A0h] [rbp-60h]
  _BYTE v39[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v40[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v41[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v42[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v43[48]; // [rsp+F8h] [rbp-8h] BYREF

  v38 = a2;
  CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(
    (CEtwEventBracketForLocalFunction *)v43,
    *(_DWORD *)(a1 + 80),
    &DocPerf_PFPM_ConvertResourceDictionary_Start,
    &DocPerf_PFPM_ConvertResourceDictionary_Stop);
  v6 = **(_QWORD **)(*a2 + 96);
  v33 = v6;
  while ( v6 != *(_QWORD *)(*a2 + 96) )
  {
    v30 = 0;
    v7 = (const struct win_dox::OpcPartUri *)(v6 + 32);
    if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v6 + 80))(
           *(_QWORD *)(v6 + 80),
           &IID_IPartResourceDictionary,
           &v30) >= 0 )
    {
      std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(
        a1 + 64,
        &v34,
        v7);
      if ( v34 == *(_QWORD *)(a1 + 64) )
      {
        v8 = (v30 - 16) & -(__int64)(v30 != 0);
        v32 = v8;
        PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(v8);
        ppstm = 0;
        v9 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v9 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v9, v10, v11, v12);
        v29 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v8 + 16) + 32LL))(v8 + 16, &v29);
        v26 = ppstm;
        PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)ppstm);
        v31 = v29;
        PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(v29);
        SplFilters::MsXpsToOpenXpsConversionFilter::CopyPStreamContentsToIStream(&v31, &v26);
        win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v36, v7);
        v37 = ppstm;
        PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)ppstm);
        std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri,PrnExcept::TRefSmartPtr<IStream>,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>>,0>>::_Emplace<std::pair<win_dox::OpcPartUri,PrnExcept::TRefSmartPtr<IStream>>>(
          (__int64 *)(a1 + 64),
          (__int64)v39,
          (const struct win_dox::OpcPartUri *)v36);
        std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>::~pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>((win_dox::OpcPartUri *)v36);
        v26 = ppstm;
        v13 = std::pair<win_dox::OpcPartUri,IStream *>::pair<win_dox::OpcPartUri,IStream *>(
                (win_dox::OpcPartUri *)v36,
                v7,
                &v26);
        std::map<win_dox::OpcPartUri,IStream *>::insert<std::pair<win_dox::OpcPartUri,IStream *>,0>(
          a3,
          (__int64)v40,
          v13);
        win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v36);
        CEnsureGlobalFree::CEnsureGlobalFree(v35, v14, &ppstm);
        v27 = 0;
        CEnsureGlobalFree::CreateStreamOnHGlobal(v35, &v27);
        v16 = OpenXpsUtility::ConvertResourceDictionaryFromMsXpsToOpenXps(v7, ppstm, v27, v15);
        if ( v16 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v16, v17, v18, v19);
        v28 = 0;
        MuslConstructPartStream::CopyIStreamContentsToPStream(*(MuslConstructPartStream **)(v8 + 64), v27, &v28);
        PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v27);
        CEnsureGlobalFree::~CEnsureGlobalFree((CEnsureGlobalFree *)v35);
        PrnExcept::SmartRelease<IPartResourceDictionary>(&v29);
        PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&ppstm);
        PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(&v32);
      }
      else
      {
        v32 = *(_QWORD *)(v34 + 56);
        v20 = std::pair<win_dox::OpcPartUri,IStream *>::pair<win_dox::OpcPartUri,IStream *>(
                (win_dox::OpcPartUri *)v42,
                (const struct win_dox::OpcPartUri *)(v34 + 32),
                &v32);
        std::map<win_dox::OpcPartUri,IStream *>::insert<std::pair<win_dox::OpcPartUri,IStream *>,0>(
          a3,
          (__int64)v41,
          v20);
        win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v42);
      }
    }
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v30);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<win_dox::OpcPartUri const,PartMapItem>>>,std::_Iterator_base0>::operator++(
      &v33,
      v21,
      v22,
      v23);
    v6 = v33;
  }
  CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction((CEtwEventBracketForLocalFunction *)v43);
  return PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(a2);
}

```

## disassembly

```asm
0x140025ee4  push    rbp
0x140025ee6  push    rbx
0x140025ee7  push    rsi
0x140025ee8  push    rdi
0x140025ee9  push    r12
0x140025eeb  push    r14
0x140025eed  push    r15
0x140025eef  lea     rbp, [rsp-30h]
0x140025ef4  sub     rsp, 130h
0x140025efb  mov     rax, cs:__security_cookie
0x140025f02  xor     rax, rsp
0x140025f05  mov     [rbp+60h+var_38], rax
0x140025f09  mov     r12, r8
0x140025f0c  mov     rdi, rdx
0x140025f0f  mov     r15, rcx
0x140025f12  mov     [rbp+60h+var_C0], rdx
0x140025f16  lea     r9, DocPerf_PFPM_ConvertResourceDictionary_Stop; struct _EVENT_DESCRIPTOR *
0x140025f1d  lea     r8, DocPerf_PFPM_ConvertResourceDictionary_Start; struct _EVENT_DESCRIPTOR *
0x140025f24  mov     edx, [rcx+50h]; unsigned int
0x140025f27  lea     rcx, [rbp+60h+var_68]; this
0x140025f2b  call    ??0CEtwEventBracketForLocalFunction@@QEAA@KAEBU_EVENT_DESCRIPTOR@@0@Z; CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(ulong,_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)
0x140025f30  nop
0x140025f31  mov     rax, [rdi]
0x140025f34  mov     rax, [rax+60h]
0x140025f38  mov     rax, [rax]
0x140025f3b  mov     [rsp+160h+var_100], rax
0x140025f40  mov     rcx, [rdi]
0x140025f43  cmp     rax, [rcx+60h]
0x140025f47  jz      loc_140026199
0x140025f4d  mov     [rsp+160h+var_118], 0
0x140025f56  lea     r14, [rax+20h]
0x140025f5a  mov     rcx, [r14+30h]
0x140025f5e  mov     rax, [rcx]
0x140025f61  lea     r8, [rsp+160h+var_118]
0x140025f66  lea     rdx, IID_IPartResourceDictionary
0x140025f6d  mov     rax, [rax]
0x140025f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025f75  test    eax, eax
0x140025f77  js      loc_14002616B
0x140025f7d  lea     rsi, [r15+40h]
0x140025f81  mov     r8, r14
0x140025f84  lea     rdx, [rsp+160h+var_F8]
0x140025f89  mov     rcx, rsi
0x140025f8c  call    ?find@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VOpcPartUri@win_dox@@@std@@@std@@@2@AEBVOpcPartUri@win_dox@@@Z; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(win_dox::OpcPartUri const &)
0x140025f91  mov     rax, [rsp+160h+var_F8]
0x140025f96  cmp     rax, [rsi]
0x140025f99  jnz     loc_140026135
0x140025f9f  mov     rax, [rsp+160h+var_118]
0x140025fa4  lea     rcx, [rax-10h]
0x140025fa8  neg     rax
0x140025fab  sbb     rbx, rbx
0x140025fae  and     rbx, rcx
0x140025fb1  mov     [rsp+160h+var_108], rbx
0x140025fb6  mov     rcx, rbx
0x140025fb9  call    ??$SmartAddRef@V?$PiboResourceDictionary@VMuslConstructPartStream@@@@@PrnExcept@@YAXPEAV?$PiboResourceDictionary@VMuslConstructPartStream@@@@@Z; PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(PiboResourceDictionary<MuslConstructPartStream> *)
0x140025fbe  nop
0x140025fbf  mov     [rsp+160h+ppstm], 0
0x140025fc8  lea     r8, [rsp+160h+ppstm]; ppstm
0x140025fcd  mov     edx, 1; fDeleteOnRelease
0x140025fd2  xor     ecx, ecx; hGlobal
0x140025fd4  call    cs:__imp_CreateStreamOnHGlobal
0x140025fda  test    eax, eax
0x140025fdc  js      loc_140026191
0x140025fe2  mov     [rsp+160h+var_120], 0
0x140025feb  lea     rcx, [rbx+10h]
0x140025fef  mov     rax, [rcx]
0x140025ff2  lea     rdx, [rsp+160h+var_120]
0x140025ff7  mov     rax, [rax+20h]
0x140025ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026000  mov     rcx, [rsp+160h+ppstm]
0x140026005  mov     [rsp+160h+var_138], rcx
0x14002600a  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14002600f  mov     rcx, [rsp+160h+var_120]
0x140026014  mov     [rsp+160h+var_110], rcx
0x140026019  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14002601e  lea     rdx, [rsp+160h+var_138]
0x140026023  lea     rcx, [rsp+160h+var_110]
0x140026028  call    ?CopyPStreamContentsToIStream@MsXpsToOpenXpsConversionFilter@SplFilters@@SAXV?$TRefSmartPtr@UIPrintReadStream@@@PrnExcept@@V?$TRefSmartPtr@UIStream@@@4@@Z; SplFilters::MsXpsToOpenXpsConversionFilter::CopyPStreamContentsToIStream(PrnExcept::TRefSmartPtr<IPrintReadStream>,PrnExcept::TRefSmartPtr<IStream>)
0x14002602d  mov     rdx, r14; struct win_dox::OpcPartUri *
0x140026030  lea     rcx, [rbp+60h+var_E0]; this
0x140026034  call    ??0OpcPartUri@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcPartUri::OpcPartUri(win_dox::OpcPartUri const &)
0x140026039  mov     rcx, [rsp+160h+ppstm]
0x14002603e  mov     [rbp+60h+var_C8], rcx
0x140026042  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x140026047  nop
0x140026048  lea     r8, [rbp+60h+var_E0]
0x14002604c  lea     rdx, [rbp+60h+var_B8]
0x140026050  mov     rcx, rsi
0x140026053  call    ??$_Emplace@U?$pair@VOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@std@@@?$_Tree@V?$_Tmap_traits@VOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@VOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@1@@Z; std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri,PrnExcept::TRefSmartPtr<IStream>,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>>,0>>::_Emplace<std::pair<win_dox::OpcPartUri,PrnExcept::TRefSmartPtr<IStream>>>(std::pair<win_dox::OpcPartUri,PrnExcept::TRefSmartPtr<IStream>> &&)
0x140026058  nop
0x140026059  lea     rcx, [rbp+60h+var_E0]; this
0x14002605d  call    ??1?$pair@$$CBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@std@@QEAA@XZ; std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>::~pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>(void)
0x140026062  mov     rax, [rsp+160h+ppstm]
0x140026067  mov     [rsp+160h+var_138], rax
0x14002606c  lea     r8, [rsp+160h+var_138]
0x140026071  mov     rdx, r14
0x140026074  lea     rcx, [rbp+60h+var_E0]
0x140026078  call    ??$?0AEBVOpcPartUri@win_dox@@PEAUIStream@@$0A@@?$pair@VOpcPartUri@win_dox@@PEAUIStream@@@std@@QEAA@AEBVOpcPartUri@win_dox@@$$QEAPEAUIStream@@@Z; std::pair<win_dox::OpcPartUri,IStream *>::pair<win_dox::OpcPartUri,IStream *>(win_dox::OpcPartUri const &,IStream * &&)
0x14002607d  nop
0x14002607e  mov     r8, rax
0x140026081  lea     rdx, [rbp+60h+var_A8]
0x140026085  mov     rcx, r12
0x140026088  call    ??$insert@U?$pair@VOpcPartUri@win_dox@@PEAUIStream@@@std@@$0A@@?$map@VOpcPartUri@win_dox@@PEAUIStream@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@VOpcPartUri@win_dox@@PEAUIStream@@@1@@Z; std::map<win_dox::OpcPartUri,IStream *>::insert<std::pair<win_dox::OpcPartUri,IStream *>,0>(std::pair<win_dox::OpcPartUri,IStream *> &&)
0x14002608d  nop
0x14002608e  lea     rcx, [rbp+60h+var_E0]; this
0x140026092  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x140026097  movsd   xmm3, cs:__real@3ff3333333333333
0x14002609f  lea     r8, [rsp+160h+ppstm]
0x1400260a4  lea     rcx, [rsp+160h+var_F0]
0x1400260a9  call    ??0CEnsureGlobalFree@@QEAA@IAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@N@Z; CEnsureGlobalFree::CEnsureGlobalFree(uint,PrnExcept::TRefSmartPtr<IStream> &,double)
0x1400260ae  nop
0x1400260af  mov     [rsp+160h+var_130], 0
0x1400260b8  lea     rdx, [rsp+160h+var_130]
0x1400260bd  lea     rcx, [rsp+160h+var_F0]
0x1400260c2  call    ?CreateStreamOnHGlobal@CEnsureGlobalFree@@QEAAXAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@@Z; CEnsureGlobalFree::CreateStreamOnHGlobal(PrnExcept::TRefSmartPtr<IStream> &)
0x1400260c7  mov     r8, [rsp+160h+var_130]; struct IStream *
0x1400260cc  mov     rdx, [rsp+160h+ppstm]; struct win_dox::OpcPartUri *
0x1400260d1  mov     rcx, r14; this
0x1400260d4  call    ?ConvertResourceDictionaryFromMsXpsToOpenXps@OpenXpsUtility@@YAJAEAVOpcPartUri@win_dox@@PEAUIStream@@1@Z; OpenXpsUtility::ConvertResourceDictionaryFromMsXpsToOpenXps(win_dox::OpcPartUri &,IStream *,IStream *)
0x1400260d9  test    eax, eax
0x1400260db  js      loc_140026189
0x1400260e1  mov     [rsp+160h+var_128], 0
0x1400260e9  lea     r8, [rsp+160h+var_128]; unsigned int *
0x1400260ee  mov     rdx, [rsp+160h+var_130]; struct IStream *
0x1400260f3  mov     rcx, [rbx+40h]; this
0x1400260f7  call    ?CopyIStreamContentsToPStream@MuslConstructPartStream@@QEAAXPEAUIStream@@PEAK@Z; MuslConstructPartStream::CopyIStreamContentsToPStream(IStream *,ulong *)
0x1400260fc  nop
0x1400260fd  lea     rcx, [rsp+160h+var_130]
0x140026102  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140026107  nop
0x140026108  lea     rcx, [rsp+160h+var_F0]; this
0x14002610d  call    ??1CEnsureGlobalFree@@QEAA@XZ; CEnsureGlobalFree::~CEnsureGlobalFree(void)
0x140026112  nop
0x140026113  lea     rcx, [rsp+160h+var_120]
0x140026118  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002611d  nop
0x14002611e  lea     rcx, [rsp+160h+ppstm]
0x140026123  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140026128  nop
0x140026129  lea     rcx, [rsp+160h+var_108]
0x14002612e  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140026133  jmp     short loc_14002616B
0x140026135  lea     rdx, [rax+20h]
0x140026139  mov     rax, [rdx+18h]
0x14002613d  mov     [rsp+160h+var_108], rax
0x140026142  lea     r8, [rsp+160h+var_108]
0x140026147  lea     rcx, [rbp+60h+var_88]
0x14002614b  call    ??$?0AEBVOpcPartUri@win_dox@@PEAUIStream@@$0A@@?$pair@VOpcPartUri@win_dox@@PEAUIStream@@@std@@QEAA@AEBVOpcPartUri@win_dox@@$$QEAPEAUIStream@@@Z; std::pair<win_dox::OpcPartUri,IStream *>::pair<win_dox::OpcPartUri,IStream *>(win_dox::OpcPartUri const &,IStream * &&)
0x140026150  nop
0x140026151  mov     r8, rax
0x140026154  lea     rdx, [rbp+60h+var_98]
0x140026158  mov     rcx, r12
0x14002615b  call    ??$insert@U?$pair@VOpcPartUri@win_dox@@PEAUIStream@@@std@@$0A@@?$map@VOpcPartUri@win_dox@@PEAUIStream@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@VOpcPartUri@win_dox@@PEAUIStream@@@1@@Z; std::map<win_dox::OpcPartUri,IStream *>::insert<std::pair<win_dox::OpcPartUri,IStream *>,0>(std::pair<win_dox::OpcPartUri,IStream *> &&)
0x140026160  nop
0x140026161  lea     rcx, [rbp+60h+var_88]; this
0x140026165  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x14002616a  nop
0x14002616b  lea     rcx, [rsp+160h+var_118]
0x140026170  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140026175  lea     rcx, [rsp+160h+var_100]
0x14002617a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVOpcPartUri@win_dox@@UPartMapItem@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<win_dox::OpcPartUri const,PartMapItem>>>,std::_Iterator_base0>::operator++(void)
0x14002617f  mov     rax, [rsp+160h+var_100]
0x140026184  jmp     loc_140025F40
0x140026189  mov     ecx, eax; this
0x14002618b  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140026191  mov     ecx, eax; this
0x140026193  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140026199  lea     rcx, [rbp+60h+var_68]; this
0x14002619d  call    ??1CEtwEventBracketForLocalFunction@@QEAA@XZ; CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction(void)
0x1400261a2  nop
0x1400261a3  mov     rcx, rdi
0x1400261a6  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400261ab  mov     rcx, [rbp+60h+var_38]
0x1400261af  xor     rcx, rsp; StackCookie
0x1400261b2  call    __security_check_cookie
0x1400261b7  add     rsp, 130h
0x1400261be  pop     r15
0x1400261c0  pop     r14
0x1400261c2  pop     r12
0x1400261c4  pop     rdi
0x1400261c5  pop     rsi
0x1400261c6  pop     rbx
0x1400261c7  pop     rbp
0x1400261c8  retn
```
