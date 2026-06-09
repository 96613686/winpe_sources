# SplFilters::MsXpsToOpenXpsConversionFilter::ConvertHDPhotoToJpegXR(PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>,ulong)

- ea: `0x140025b48`
- end: `0x140025d54`
- name: `?ConvertHDPhotoToJpegXR@MsXpsToOpenXpsConversionFilter@SplFilters@@SAXV?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@K@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400267f0`

## callees

- `0x140002070`
- `0x14000f9d8`
- `0x14000fa68`
- `0x14000fb28`
- `0x14001b1f8`
- `0x140024be0`
- `0x140024d64`
- `0x1400254d4`
- `0x1400254fc`
- `0x140025914`
- `0x140025b48`
- `0x1400261d0`
- `0x1400263c8`
- `0x140042c98`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140025c17`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140025c17`
- `xpsservices!__imp_ConvertHDPhotoToJpegXR` at `0x140025c9b`
- `xpsservices!__imp_ConvertHDPhotoToJpegXR` at `0x140025c9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SplFilters::MsXpsToOpenXpsConversionFilter::ConvertHDPhotoToJpegXR(__int64 *a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  HRESULT v4; // eax
  int v5; // edx
  const char *v6; // r8
  unsigned int v7; // r9d
  __int64 v8; // rdx
  int v9; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  LPSTREAM ppstm; // [rsp+20h] [rbp-49h] BYREF
  struct IStream *v18; // [rsp+28h] [rbp-41h] BYREF
  unsigned int v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+38h] [rbp-31h] BYREF
  __int64 v21; // [rsp+40h] [rbp-29h] BYREF
  LPSTREAM v22; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v26[16]; // [rsp+68h] [rbp-1h] BYREF
  __int64 *v27; // [rsp+78h] [rbp+Fh]
  _BYTE v28[48]; // [rsp+80h] [rbp+17h] BYREF

  v27 = a1;
  CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(
    (CEtwEventBracketForLocalFunction *)v28,
    0,
    &DocPerf_PFPM_ConvertHdPhotoToJpegXR_Start,
    &DocPerf_PFPM_ConvertHdPhotoToJpegXR_Stop);
  v2 = **(_QWORD **)(*a1 + 96);
  v24 = v2;
  while ( v2 != *(_QWORD *)(*a1 + 96) )
  {
    v21 = 0;
    if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v2 + 80))(*(_QWORD *)(v2 + 80), &IID_IPartImage, &v21) >= 0 )
    {
      v3 = (v21 - 16) & -(__int64)(v21 != 0);
      v25 = v3;
      PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(v3);
      if ( v3 && !*(_DWORD *)(v3 + 112) )
      {
        ppstm = 0;
        v4 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v4 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v4, v5, v6, v7);
        v20 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v3 + 16) + 32LL))(v3 + 16, &v20);
        v22 = ppstm;
        PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)ppstm);
        v23 = v20;
        PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(v20);
        SplFilters::MsXpsToOpenXpsConversionFilter::CopyPStreamContentsToIStream(&v23, &v22);
        CEnsureGlobalFree::CEnsureGlobalFree(v26, v8, &ppstm);
        v18 = 0;
        CEnsureGlobalFree::CreateStreamOnHGlobal(v26, &v18);
        v9 = ConvertHDPhotoToJpegXR(ppstm, v18);
        if ( v9 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v9, v10, v11, v12);
        v19 = 0;
        MuslConstructPartStream::CopyIStreamContentsToPStream(*(MuslConstructPartStream **)(v3 + 96), v18, &v19);
        *(_DWORD *)(v3 + 112) = 1;
        PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v18);
        CEnsureGlobalFree::~CEnsureGlobalFree((CEnsureGlobalFree *)v26);
        PrnExcept::SmartRelease<IPartResourceDictionary>(&v20);
        PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&ppstm);
      }
      PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(&v25);
    }
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v21);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<win_dox::OpcPartUri const,PartMapItem>>>,std::_Iterator_base0>::operator++(
      &v24,
      v13,
      v14,
      v15);
    v2 = v24;
  }
  CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction((CEtwEventBracketForLocalFunction *)v28);
  return PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(a1);
}

```

## disassembly

```asm
0x140025b48  mov     [rsp-8+arg_8], rbx
0x140025b4d  mov     [rsp-8+arg_10], rdi
0x140025b52  push    rbp
0x140025b53  lea     rbp, [rsp-57h]
0x140025b58  sub     rsp, 0C0h
0x140025b5f  mov     rax, cs:__security_cookie
0x140025b66  xor     rax, rsp
0x140025b69  mov     [rbp+57h+var_10], rax
0x140025b6d  mov     rdi, rcx
0x140025b70  mov     [rbp+57h+var_48], rcx
0x140025b74  lea     r9, DocPerf_PFPM_ConvertHdPhotoToJpegXR_Stop; struct _EVENT_DESCRIPTOR *
0x140025b7b  lea     r8, DocPerf_PFPM_ConvertHdPhotoToJpegXR_Start; struct _EVENT_DESCRIPTOR *
0x140025b82  xor     edx, edx; unsigned int
0x140025b84  lea     rcx, [rbp+57h+var_40]; this
0x140025b88  call    ??0CEtwEventBracketForLocalFunction@@QEAA@KAEBU_EVENT_DESCRIPTOR@@0@Z; CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(ulong,_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)
0x140025b8d  nop
0x140025b8e  mov     rax, [rdi]
0x140025b91  mov     rax, [rax+60h]
0x140025b95  mov     rax, [rax]
0x140025b98  mov     [rbp+57h+var_68], rax
0x140025b9c  mov     rcx, [rdi]
0x140025b9f  cmp     rax, [rcx+60h]
0x140025ba3  jz      loc_140025D21
0x140025ba9  mov     [rbp+57h+var_80], 0
0x140025bb1  mov     rcx, [rax+50h]
0x140025bb5  mov     rax, [rcx]
0x140025bb8  lea     r8, [rbp+57h+var_80]
0x140025bbc  lea     rdx, IID_IPartImage
0x140025bc3  mov     rax, [rax]
0x140025bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025bcb  test    eax, eax
0x140025bcd  js      loc_140025CF6
0x140025bd3  mov     rax, [rbp+57h+var_80]
0x140025bd7  lea     rcx, [rax-10h]
0x140025bdb  neg     rax
0x140025bde  sbb     rbx, rbx
0x140025be1  and     rbx, rcx
0x140025be4  mov     [rbp+57h+var_60], rbx
0x140025be8  mov     rcx, rbx
0x140025beb  call    ??$SmartAddRef@V?$PiboResourceDictionary@VMuslConstructPartStream@@@@@PrnExcept@@YAXPEAV?$PiboResourceDictionary@VMuslConstructPartStream@@@@@Z; PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(PiboResourceDictionary<MuslConstructPartStream> *)
0x140025bf0  nop
0x140025bf1  test    rbx, rbx
0x140025bf4  jz      loc_140025CEC
0x140025bfa  cmp     dword ptr [rbx+70h], 0
0x140025bfe  jnz     loc_140025CEC
0x140025c04  mov     [rbp+57h+ppstm], 0
0x140025c0c  lea     r8, [rbp+57h+ppstm]; ppstm
0x140025c10  mov     edx, 1; fDeleteOnRelease
0x140025c15  xor     ecx, ecx; hGlobal
0x140025c17  call    cs:__imp_CreateStreamOnHGlobal
0x140025c1d  test    eax, eax
0x140025c1f  js      loc_140025D19
0x140025c25  mov     [rbp+57h+var_88], 0
0x140025c2d  lea     rcx, [rbx+10h]
0x140025c31  mov     rax, [rcx]
0x140025c34  lea     rdx, [rbp+57h+var_88]
0x140025c38  mov     rax, [rax+20h]
0x140025c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025c41  mov     rcx, [rbp+57h+ppstm]
0x140025c45  mov     [rbp+57h+var_78], rcx
0x140025c49  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x140025c4e  mov     rcx, [rbp+57h+var_88]
0x140025c52  mov     [rbp+57h+var_70], rcx
0x140025c56  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x140025c5b  lea     rdx, [rbp+57h+var_78]
0x140025c5f  lea     rcx, [rbp+57h+var_70]
0x140025c63  call    ?CopyPStreamContentsToIStream@MsXpsToOpenXpsConversionFilter@SplFilters@@SAXV?$TRefSmartPtr@UIPrintReadStream@@@PrnExcept@@V?$TRefSmartPtr@UIStream@@@4@@Z; SplFilters::MsXpsToOpenXpsConversionFilter::CopyPStreamContentsToIStream(PrnExcept::TRefSmartPtr<IPrintReadStream>,PrnExcept::TRefSmartPtr<IStream>)
0x140025c68  movsd   xmm3, cs:__real@3ff3333333333333
0x140025c70  lea     r8, [rbp+57h+ppstm]
0x140025c74  lea     rcx, [rbp+57h+var_58]
0x140025c78  call    ??0CEnsureGlobalFree@@QEAA@IAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@N@Z; CEnsureGlobalFree::CEnsureGlobalFree(uint,PrnExcept::TRefSmartPtr<IStream> &,double)
0x140025c7d  nop
0x140025c7e  mov     [rbp+57h+var_98], 0
0x140025c86  lea     rdx, [rbp+57h+var_98]
0x140025c8a  lea     rcx, [rbp+57h+var_58]
0x140025c8e  call    ?CreateStreamOnHGlobal@CEnsureGlobalFree@@QEAAXAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@@Z; CEnsureGlobalFree::CreateStreamOnHGlobal(PrnExcept::TRefSmartPtr<IStream> &)
0x140025c93  mov     rdx, [rbp+57h+var_98]
0x140025c97  mov     rcx, [rbp+57h+ppstm]
0x140025c9b  call    cs:__imp_ConvertHDPhotoToJpegXR
0x140025ca1  test    eax, eax
0x140025ca3  js      short loc_140025D11
0x140025ca5  mov     [rbp+57h+var_90], 0
0x140025cac  lea     r8, [rbp+57h+var_90]; unsigned int *
0x140025cb0  mov     rdx, [rbp+57h+var_98]; struct IStream *
0x140025cb4  mov     rcx, [rbx+60h]; this
0x140025cb8  call    ?CopyIStreamContentsToPStream@MuslConstructPartStream@@QEAAXPEAUIStream@@PEAK@Z; MuslConstructPartStream::CopyIStreamContentsToPStream(IStream *,ulong *)
0x140025cbd  mov     dword ptr [rbx+70h], 1
0x140025cc4  lea     rcx, [rbp+57h+var_98]
0x140025cc8  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025ccd  nop
0x140025cce  lea     rcx, [rbp+57h+var_58]; this
0x140025cd2  call    ??1CEnsureGlobalFree@@QEAA@XZ; CEnsureGlobalFree::~CEnsureGlobalFree(void)
0x140025cd7  nop
0x140025cd8  lea     rcx, [rbp+57h+var_88]
0x140025cdc  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025ce1  nop
0x140025ce2  lea     rcx, [rbp+57h+ppstm]
0x140025ce6  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025ceb  nop
0x140025cec  lea     rcx, [rbp+57h+var_60]
0x140025cf0  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140025cf5  nop
0x140025cf6  lea     rcx, [rbp+57h+var_80]
0x140025cfa  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025cff  lea     rcx, [rbp+57h+var_68]
0x140025d03  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVOpcPartUri@win_dox@@UPartMapItem@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<win_dox::OpcPartUri const,PartMapItem>>>,std::_Iterator_base0>::operator++(void)
0x140025d08  mov     rax, [rbp+57h+var_68]
0x140025d0c  jmp     loc_140025B9C
0x140025d11  mov     ecx, eax; this
0x140025d13  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140025d19  mov     ecx, eax; this
0x140025d1b  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140025d21  lea     rcx, [rbp+57h+var_40]; this
0x140025d25  call    ??1CEtwEventBracketForLocalFunction@@QEAA@XZ; CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction(void)
0x140025d2a  nop
0x140025d2b  mov     rcx, rdi
0x140025d2e  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140025d33  mov     rcx, [rbp+57h+var_10]
0x140025d37  xor     rcx, rsp; StackCookie
0x140025d3a  call    __security_check_cookie
0x140025d3f  lea     r11, [rsp+0C0h+var_s0]
0x140025d47  mov     rbx, [r11+18h]
0x140025d4b  mov     rdi, [r11+20h]
0x140025d4f  mov     rsp, r11
0x140025d52  pop     rbp
0x140025d53  retn
```
