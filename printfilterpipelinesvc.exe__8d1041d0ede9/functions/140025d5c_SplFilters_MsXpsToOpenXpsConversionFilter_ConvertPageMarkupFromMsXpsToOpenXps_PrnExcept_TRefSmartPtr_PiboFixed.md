# SplFilters::MsXpsToOpenXpsConversionFilter::ConvertPageMarkupFromMsXpsToOpenXps(PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>,PrnExcept::TRefSmartPtr<IPrintReadStream>,std::map<win_dox::OpcPartUri,IStream *,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,IStream *>>> &,ulong)

- ea: `0x140025d5c`
- end: `0x140025edb`
- name: `?ConvertPageMarkupFromMsXpsToOpenXps@MsXpsToOpenXpsConversionFilter@SplFilters@@SAXV?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@V?$TRefSmartPtr@UIPrintReadStream@@@4@AEAV?$map@VOpcPartUri@win_dox@@PEAUIStream@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@5@@std@@K@Z`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400267f0`

## callees

- `0x140002070`
- `0x14000f9d8`
- `0x14000fa68`
- `0x14000fb28`
- `0x140024be0`
- `0x140024d64`
- `0x1400254d4`
- `0x1400254fc`
- `0x140025d5c`
- `0x1400261d0`
- `0x1400263c8`
- `0x140042c98`
- `0x14004650c`
- `0x140055bc4`
- `0x140055c44`
- `0x14005a250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140025dc0`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140025dc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SplFilters::MsXpsToOpenXpsConversionFilter::ConvertPageMarkupFromMsXpsToOpenXps(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  HRESULT v6; // eax
  int v7; // edx
  const char *v8; // r8
  unsigned int v9; // r9d
  __int64 v10; // rdx
  struct IStream *v11; // rbx
  LPSTREAM v12; // rdi
  int v13; // eax
  int v14; // edx
  const char *v15; // r8
  unsigned int v16; // r9d
  unsigned int v18; // [rsp+20h] [rbp-59h] BYREF
  LPSTREAM ppstm; // [rsp+28h] [rbp-51h] BYREF
  struct IStream *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21[2]; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v23[24]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v24[48]; // [rsp+78h] [rbp-1h] BYREF

  v22[1] = a1;
  v22[2] = a2;
  CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(
    (CEtwEventBracketForLocalFunction *)v24,
    0,
    &DocPerf_PFPM_ConvertPageMarkup_Start,
    &DocPerf_PFPM_ConvertPageMarkup_Stop);
  ppstm = 0;
  v6 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v6 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v6, v7, v8, v9);
  v22[0] = ppstm;
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)ppstm);
  v21[0] = *a2;
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(v21[0]);
  SplFilters::MsXpsToOpenXpsConversionFilter::CopyPStreamContentsToIStream(v21, v22);
  CEnsureGlobalFree::CEnsureGlobalFree(v21, v10, &ppstm);
  v20 = 0;
  CEnsureGlobalFree::CreateStreamOnHGlobal(v21, &v20);
  v11 = v20;
  v12 = ppstm;
  win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v23, (const struct win_dox::OpcPartUri *)(*a1 + 40));
  v13 = OpenXpsUtility::ConvertToOpenXpsMarkupStream(v23, v12, a3, v11);
  if ( v13 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v13, v14, v15, v16);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v23);
  v18 = 0;
  MuslConstructPartStream::CopyIStreamContentsToPStream(*(MuslConstructPartStream **)(*a1 + 72), v20, &v18);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v20);
  CEnsureGlobalFree::~CEnsureGlobalFree((CEnsureGlobalFree *)v21);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&ppstm);
  CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction((CEtwEventBracketForLocalFunction *)v24);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(a1);
  return PrnExcept::SmartRelease<IPartResourceDictionary>(a2);
}

```

## disassembly

```asm
0x140025d5c  mov     [rsp-8+arg_18], rbx
0x140025d61  push    rbp
0x140025d62  push    rsi
0x140025d63  push    rdi
0x140025d64  push    r14
0x140025d66  push    r15
0x140025d68  lea     rbp, [rsp-37h]
0x140025d6d  sub     rsp, 0B0h
0x140025d74  mov     rax, cs:__security_cookie
0x140025d7b  xor     rax, rsp
0x140025d7e  mov     [rbp+57h+var_28], rax
0x140025d82  mov     r15, r8
0x140025d85  mov     r14, rdx
0x140025d88  mov     rsi, rcx
0x140025d8b  mov     [rbp+57h+var_80], rcx
0x140025d8f  mov     [rbp+57h+var_78], rdx
0x140025d93  lea     r9, DocPerf_PFPM_ConvertPageMarkup_Stop; struct _EVENT_DESCRIPTOR *
0x140025d9a  lea     r8, DocPerf_PFPM_ConvertPageMarkup_Start; struct _EVENT_DESCRIPTOR *
0x140025da1  xor     edx, edx; unsigned int
0x140025da3  lea     rcx, [rbp+57h+var_58]; this
0x140025da7  call    ??0CEtwEventBracketForLocalFunction@@QEAA@KAEBU_EVENT_DESCRIPTOR@@0@Z; CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(ulong,_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)
0x140025dac  nop
0x140025dad  mov     [rbp+57h+ppstm], 0
0x140025db5  lea     r8, [rbp+57h+ppstm]; ppstm
0x140025db9  mov     edx, 1; fDeleteOnRelease
0x140025dbe  xor     ecx, ecx; hGlobal
0x140025dc0  call    cs:__imp_CreateStreamOnHGlobal
0x140025dc6  test    eax, eax
0x140025dc8  jns     short loc_140025DD2
0x140025dca  mov     ecx, eax; this
0x140025dcc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140025dd2  mov     rcx, [rbp+57h+ppstm]
0x140025dd6  mov     [rbp+57h+var_88], rcx
0x140025dda  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x140025ddf  mov     rcx, [r14]
0x140025de2  mov     [rbp+57h+var_98], rcx
0x140025de6  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x140025deb  lea     rdx, [rbp+57h+var_88]
0x140025def  lea     rcx, [rbp+57h+var_98]
0x140025df3  call    ?CopyPStreamContentsToIStream@MsXpsToOpenXpsConversionFilter@SplFilters@@SAXV?$TRefSmartPtr@UIPrintReadStream@@@PrnExcept@@V?$TRefSmartPtr@UIStream@@@4@@Z; SplFilters::MsXpsToOpenXpsConversionFilter::CopyPStreamContentsToIStream(PrnExcept::TRefSmartPtr<IPrintReadStream>,PrnExcept::TRefSmartPtr<IStream>)
0x140025df8  movsd   xmm3, cs:__real@3ff3333333333333
0x140025e00  lea     r8, [rbp+57h+ppstm]
0x140025e04  lea     rcx, [rbp+57h+var_98]
0x140025e08  call    ??0CEnsureGlobalFree@@QEAA@IAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@N@Z; CEnsureGlobalFree::CEnsureGlobalFree(uint,PrnExcept::TRefSmartPtr<IStream> &,double)
0x140025e0d  nop
0x140025e0e  mov     [rbp+57h+var_A0], 0
0x140025e16  lea     rdx, [rbp+57h+var_A0]
0x140025e1a  lea     rcx, [rbp+57h+var_98]
0x140025e1e  call    ?CreateStreamOnHGlobal@CEnsureGlobalFree@@QEAAXAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@@Z; CEnsureGlobalFree::CreateStreamOnHGlobal(PrnExcept::TRefSmartPtr<IStream> &)
0x140025e23  mov     rbx, [rbp+57h+var_A0]
0x140025e27  mov     rdi, [rbp+57h+ppstm]
0x140025e2b  mov     rdx, [rsi]
0x140025e2e  add     rdx, 28h ; '('; struct win_dox::OpcPartUri *
0x140025e32  lea     rcx, [rbp+57h+var_70]; this
0x140025e36  call    ??0OpcPartUri@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcPartUri::OpcPartUri(win_dox::OpcPartUri const &)
0x140025e3b  nop
0x140025e3c  mov     r9, rbx
0x140025e3f  mov     r8, r15
0x140025e42  mov     rdx, rdi
0x140025e45  lea     rcx, [rbp+57h+var_70]
0x140025e49  call    ?ConvertToOpenXpsMarkupStream@OpenXpsUtility@@YAJAEAVOpcPartUri@win_dox@@PEAUIStream@@AEAV?$map@VOpcPartUri@win_dox@@PEAUIStream@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@5@@std@@1@Z; OpenXpsUtility::ConvertToOpenXpsMarkupStream(win_dox::OpcPartUri &,IStream *,std::map<win_dox::OpcPartUri,IStream *> &,IStream *)
0x140025e4e  test    eax, eax
0x140025e50  jns     short loc_140025E5A
0x140025e52  mov     ecx, eax; this
0x140025e54  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140025e5a  lea     rcx, [rbp+57h+var_70]; this
0x140025e5e  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x140025e63  mov     [rbp+57h+var_B0], 0
0x140025e6a  mov     rcx, [rsi]
0x140025e6d  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x140025e71  mov     rdx, [rbp+57h+var_A0]; struct IStream *
0x140025e75  mov     rcx, [rcx+48h]; this
0x140025e79  call    ?CopyIStreamContentsToPStream@MuslConstructPartStream@@QEAAXPEAUIStream@@PEAK@Z; MuslConstructPartStream::CopyIStreamContentsToPStream(IStream *,ulong *)
0x140025e7e  nop
0x140025e7f  lea     rcx, [rbp+57h+var_A0]
0x140025e83  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025e88  nop
0x140025e89  lea     rcx, [rbp+57h+var_98]; this
0x140025e8d  call    ??1CEnsureGlobalFree@@QEAA@XZ; CEnsureGlobalFree::~CEnsureGlobalFree(void)
0x140025e92  nop
0x140025e93  lea     rcx, [rbp+57h+ppstm]
0x140025e97  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025e9c  nop
0x140025e9d  lea     rcx, [rbp+57h+var_58]; this
0x140025ea1  call    ??1CEtwEventBracketForLocalFunction@@QEAA@XZ; CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction(void)
0x140025ea6  nop
0x140025ea7  mov     rcx, rsi
0x140025eaa  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140025eaf  nop
0x140025eb0  mov     rcx, r14
0x140025eb3  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140025eb8  mov     rcx, [rbp+57h+var_28]
0x140025ebc  xor     rcx, rsp; StackCookie
0x140025ebf  call    __security_check_cookie
0x140025ec4  mov     rbx, [rsp+0D0h+arg_18]
0x140025ecc  add     rsp, 0B0h
0x140025ed3  pop     r15
0x140025ed5  pop     r14
0x140025ed7  pop     rdi
0x140025ed8  pop     rsi
0x140025ed9  pop     rbp
0x140025eda  retn
```
