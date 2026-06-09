# InterfaceBuilder::XpsToSpoolerSerialize(ulong)

- ea: `0x14001fea8`
- end: `0x14002018c`
- name: `?XpsToSpoolerSerialize@InterfaceBuilder@@AEAAXK@Z`
- size: `740`
- prototype: `void __fastcall(InterfaceBuilder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14001ed28`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000f9d8`
- `0x14000fa68`
- `0x14000fb28`
- `0x14001b0f0`
- `0x14001b624`
- `0x14001c7f4`
- `0x14001c82c`
- `0x14001d774`
- `0x14001fea8`
- `0x14002a7d0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x1400520ec`
- `0x140063010`

## import_xrefs

- `XpsPushLayer!__imp_ProdXpsPackageToStream1` at `0x14001ff88`
- `XpsPushLayer!__imp_ProdXpsPackageToStream1` at `0x14001ff88`

## string_xrefs

- `0x140020039`: `This version of XPS PUSH does not support OpenXPS.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall InterfaceBuilder::XpsToSpoolerSerialize(InterfaceBuilder *this, unsigned int a2)
{
  __int64 v2; // r15
  int v4; // r14d
  unsigned int v5; // edi
  bool v6; // bl
  _QWORD *Interface; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  unsigned int v13; // r9d
  int v14; // eax
  int v15; // edx
  const char *v16; // r8
  unsigned int v17; // r9d
  int v18; // eax
  const char *v19; // rdx
  const char *v20; // r8
  unsigned int v21; // r9d
  const struct SplException::TSystemException *v22; // r8
  const struct _GUID *v23; // r9
  void *v24; // rax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, _QWORD *); // rdi
  __int64 v26; // rbx
  const struct win_musl::TStringEllipseBase *v27; // [rsp+28h] [rbp-D8h]
  HINSTANCE v28; // [rsp+30h] [rbp-D0h]
  _BYTE v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, _QWORD *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v33[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ****v35)(_QWORD, GUID *, _QWORD *); // [rsp+70h] [rbp-90h]
  __int64 (__fastcall ****v36)(_QWORD, GUID *, _QWORD *); // [rsp+78h] [rbp-88h]
  _BYTE v37[160]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+120h] [rbp+20h] BYREF

  v2 = a2;
  v4 = *(_DWORD *)(*((_QWORD *)this + 2) + 276LL);
  *(_QWORD *)v33 = 0;
  v31 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)this + 8);
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)v31);
  v36 = &v31;
  v30 = v31;
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)v31);
  v35 = &v30;
  win_musl::detail::QueryInterface<IStream,IUnknown>(&v32, v30);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v30);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v31);
  v5 = 3;
  if ( v4 != 1 )
    v5 = 1;
  v6 = *((_DWORD *)this + 25) == 0;
  Interface = (_QWORD *)win_dox::Stream::GetInterface(&v32, &v30);
  LOBYTE(v8) = v6;
  LOBYTE(v9) = 1;
  v10 = ProdXpsPackageToStream1(*Interface, v9, v8, v5);
  if ( v10 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v10, v11, v12, v13);
  if ( v30 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v30)[2])(v30);
  v29[0] = 0;
  v34 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v33 + 24LL))(*(_QWORD *)v33, &v34);
  if ( v14 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v14, v15, v16, v17);
  v18 = (*(__int64 (__fastcall **)(__int64, bool, _BYTE *))(*(_QWORD *)v34 + 48LL))(v34, v4 == 1, v29);
  if ( v18 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v18, (int)v19, v20, v21);
  if ( v4 == 1 && !v29[0] )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v37, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v37,
      0x80004005,
      v22,
      v23,
      (unsigned int)v33,
      v27,
      v28);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v37,
      "This version of XPS PUSH does not support OpenXPS.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v37);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v30 = 0;
  v24 = operator new(0x98u, v19, (unsigned int)v20);
  v35 = (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v24;
  if ( v24 )
    v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))XpsSerializerPibo::XpsSerializerPibo(
                                                                v24,
                                                                *((_QWORD *)this + 3),
                                                                *(_QWORD *)v33,
                                                                *((_QWORD *)this + 12));
  else
    v25 = 0;
  v31 = 0;
  v30 = v25;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v31);
  PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(
    16 * v2 + 8 + **(_QWORD **)this,
    (unsigned __int64)(v25 + 2) & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64));
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 9);
  PrnExcept::TRefSmartPtr<XpsSerializerPibo>::operator=((char *)this + 72, &v30);
  v26 = *((_QWORD *)this + 2);
  v31 = 0;
  PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(&v31, (unsigned __int64)(v25 + 3) & -(__int64)(v25 != 0));
  std::deque<PrnExcept::TRefSmartPtr<IUnknown>>::_Emplace_back_internal<PrnExcept::TRefSmartPtr<IUnknown> const &>(
    v26 + 56,
    &v31);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v31);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v30);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v34);
  win_dox::Uri::~Uri((win_dox::Uri *)&v32);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)v33);
}

```

## disassembly

```asm
0x14001fea8  mov     [rsp-8+arg_10], rbx
0x14001fead  mov     [rsp-8+arg_18], rsi
0x14001feb2  push    rbp
0x14001feb3  push    rdi
0x14001feb4  push    r13
0x14001feb6  push    r14
0x14001feb8  push    r15
0x14001feba  lea     rbp, [rsp-0D0h]
0x14001fec2  sub     rsp, 1D0h
0x14001fec9  mov     rax, cs:__security_cookie
0x14001fed0  xor     rax, rsp
0x14001fed3  mov     [rbp+0F0h+var_30], rax
0x14001feda  mov     r15d, edx
0x14001fedd  mov     rsi, rcx
0x14001fee0  mov     rax, [rcx+10h]
0x14001fee4  mov     r14d, [rax+114h]
0x14001feeb  mov     qword ptr [rsp+1F0h+var_190], 0
0x14001fef4  mov     rcx, [rcx+40h]
0x14001fef8  mov     [rsp+1F0h+var_1A0], rcx
0x14001fefd  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14001ff02  lea     rax, [rsp+1F0h+var_1A0]
0x14001ff07  mov     [rsp+1F0h+var_178], rax
0x14001ff0c  mov     rcx, [rsp+1F0h+var_1A0]
0x14001ff11  mov     [rsp+1F0h+var_1A8], rcx
0x14001ff16  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14001ff1b  lea     rax, [rsp+1F0h+var_1A8]
0x14001ff20  mov     [rsp+1F0h+var_180], rax
0x14001ff25  mov     rdx, [rsp+1F0h+var_1A8]
0x14001ff2a  lea     rcx, [rsp+1F0h+var_198]
0x14001ff2f  call    ??$QueryInterface@UIStream@@UIUnknown@@@detail@win_musl@@YA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIUnknown@@@Z; win_musl::detail::QueryInterface<IStream,IUnknown>(IUnknown *)
0x14001ff34  nop
0x14001ff35  lea     rcx, [rsp+1F0h+var_1A8]
0x14001ff3a  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001ff3f  nop
0x14001ff40  lea     rcx, [rsp+1F0h+var_1A0]
0x14001ff45  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001ff4a  nop
0x14001ff4b  mov     edi, 3
0x14001ff50  lea     r13d, [rdi-2]
0x14001ff54  cmp     r14d, r13d
0x14001ff57  cmovnz  edi, r13d
0x14001ff5b  cmp     dword ptr [rsi+64h], 0
0x14001ff5f  setbe   bl
0x14001ff62  lea     rdx, [rsp+1F0h+var_1A8]
0x14001ff67  lea     rcx, [rsp+1F0h+var_198]
0x14001ff6c  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x14001ff71  nop
0x14001ff72  lea     rcx, [rsp+1F0h+var_190]
0x14001ff77  mov     qword ptr [rsp+1F0h+var_1D0], rcx; unsigned int
0x14001ff7c  mov     r9d, edi
0x14001ff7f  mov     r8b, bl
0x14001ff82  mov     dl, r13b
0x14001ff85  mov     rcx, [rax]
0x14001ff88  call    cs:__imp_ProdXpsPackageToStream1
0x14001ff8e  test    eax, eax
0x14001ff90  jns     short loc_14001FF9A
0x14001ff92  mov     ecx, eax; this
0x14001ff94  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001ff9a  mov     rcx, [rsp+1F0h+var_1A8]
0x14001ff9f  test    rcx, rcx
0x14001ffa2  jz      short loc_14001FFB1
0x14001ffa4  mov     rax, [rcx]
0x14001ffa7  mov     rax, [rax+10h]
0x14001ffab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ffb0  nop
0x14001ffb1  mov     [rsp+1F0h+var_1B0], 0
0x14001ffb6  mov     [rsp+1F0h+var_188], 0
0x14001ffbf  mov     rcx, qword ptr [rsp+1F0h+var_190]
0x14001ffc4  mov     rax, [rcx]
0x14001ffc7  lea     rdx, [rsp+1F0h+var_188]
0x14001ffcc  mov     rax, [rax+18h]
0x14001ffd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ffd5  test    eax, eax
0x14001ffd7  jns     short loc_14001FFE1
0x14001ffd9  mov     ecx, eax; this
0x14001ffdb  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001ffe1  mov     rcx, [rsp+1F0h+var_188]
0x14001ffe6  mov     rax, [rcx]
0x14001ffe9  xor     edx, edx
0x14001ffeb  cmp     r14d, r13d
0x14001ffee  setz    dl
0x14001fff1  lea     r8, [rsp+1F0h+var_1B0]
0x14001fff6  mov     rax, [rax+30h]
0x14001fffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ffff  test    eax, eax
0x140020001  jns     short loc_14002000B
0x140020003  mov     ecx, eax; this
0x140020005  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14002000b  cmp     r14d, r13d
0x14002000e  jnz     short loc_140020067
0x140020010  cmp     [rsp+1F0h+var_1B0], 0
0x140020015  jnz     short loc_140020067
0x140020017  xor     r8d, r8d; unsigned int
0x14002001a  lea     rdx, asc_1400696D8; "-"
0x140020021  lea     rcx, [rbp+0F0h+var_170]; this
0x140020025  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14002002a  nop
0x14002002b  mov     edx, 80004005h; unsigned int
0x140020030  lea     rcx, [rbp+0F0h+var_170]; this
0x140020034  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140020039  lea     rdx, aThisVersionOfX; "This version of XPS PUSH does not suppo"...
0x140020040  lea     rcx, [rbp+0F0h+var_170]; this
0x140020044  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140020049  lea     rdx, [rbp+0F0h+var_170]; struct SplException::THResultException *
0x14002004d  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x140020051  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140020056  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14002005d  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x140020061  call    _CxxThrowException_0
0x140020067  mov     [rsp+1F0h+var_1A8], 0
0x140020070  mov     ecx, 98h; unsigned __int64
0x140020075  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14002007a  mov     [rsp+1F0h+var_180], rax
0x14002007f  test    rax, rax
0x140020082  jz      short loc_14002009E
0x140020084  mov     r9, [rsi+60h]
0x140020088  mov     r8, qword ptr [rsp+1F0h+var_190]
0x14002008d  mov     rdx, [rsi+18h]
0x140020091  mov     rcx, rax
0x140020094  call    ??0XpsSerializerPibo@@QEAA@PEAVXpsObjectModelState@@PEAUIXpsProdPackageContent@XpsProductionLayer@XpsPush@@U__MIDL___MIDL_itf_filterpipelinei_0000_0000_0003@@@Z; XpsSerializerPibo::XpsSerializerPibo(XpsObjectModelState *,XpsPush::XpsProductionLayer::IXpsProdPackageContent *,__MIDL___MIDL_itf_filterpipelinei_0000_0000_0003)
0x140020099  mov     rdi, rax
0x14002009c  jmp     short loc_1400200A0
0x14002009e  xor     edi, edi
0x1400200a0  mov     [rsp+1F0h+var_1A0], 0
0x1400200a9  mov     [rsp+1F0h+var_1A8], rdi
0x1400200ae  lea     rcx, [rsp+1F0h+var_1A0]
0x1400200b3  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400200b8  mov     rax, rdi
0x1400200bb  lea     rcx, [rdi+10h]
0x1400200bf  neg     rax
0x1400200c2  sbb     rdx, rdx
0x1400200c5  and     rdx, rcx
0x1400200c8  mov     r8, r15
0x1400200cb  shl     r8, 4
0x1400200cf  mov     rax, [rsi]
0x1400200d2  mov     rcx, [rax]
0x1400200d5  add     r8, 8
0x1400200d9  add     rcx, r8
0x1400200dc  call    ??4?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@QEAAAEAV01@PEAUIShutdownComponent@@@Z; PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(IShutdownComponent *)
0x1400200e1  lea     rcx, [rsi+48h]
0x1400200e5  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400200ea  lea     rdx, [rsp+1F0h+var_1A8]
0x1400200ef  lea     rcx, [rsi+48h]
0x1400200f3  call    ??4?$TRefSmartPtr@VXpsSerializerPibo@@@PrnExcept@@QEAAAEAV01@AEBV01@@Z; PrnExcept::TRefSmartPtr<XpsSerializerPibo>::operator=(PrnExcept::TRefSmartPtr<XpsSerializerPibo> const &)
0x1400200f8  mov     rbx, [rsi+10h]
0x1400200fc  lea     rax, [rdi+18h]
0x140020100  neg     rdi
0x140020103  sbb     rdx, rdx
0x140020106  and     rdx, rax
0x140020109  mov     [rsp+1F0h+var_1A0], 0
0x140020112  lea     rcx, [rsp+1F0h+var_1A0]
0x140020117  call    ??4?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@QEAAAEAV01@PEAUIShutdownComponent@@@Z; PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(IShutdownComponent *)
0x14002011c  lea     rcx, [rbx+38h]
0x140020120  lea     rdx, [rsp+1F0h+var_1A0]
0x140020125  call    ??$_Emplace_back_internal@AEBV?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@?$deque@V?$TRefSmartPtr@UIUnknown@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@std@@@std@@AEAAXAEBV?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@Z; std::deque<PrnExcept::TRefSmartPtr<IUnknown>>::_Emplace_back_internal<PrnExcept::TRefSmartPtr<IUnknown> const &>(PrnExcept::TRefSmartPtr<IUnknown> const &)
0x14002012a  nop
0x14002012b  lea     rcx, [rsp+1F0h+var_1A0]
0x140020130  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140020135  nop
0x140020136  lea     rcx, [rsp+1F0h+var_1A8]
0x14002013b  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140020140  nop
0x140020141  lea     rcx, [rsp+1F0h+var_188]
0x140020146  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002014b  nop
0x14002014c  lea     rcx, [rsp+1F0h+var_198]; this
0x140020151  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x140020156  nop
0x140020157  lea     rcx, [rsp+1F0h+var_190]
0x14002015c  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140020161  mov     rcx, [rbp+0F0h+var_30]
0x140020168  xor     rcx, rsp; StackCookie
0x14002016b  call    __security_check_cookie
0x140020170  lea     r11, [rsp+1F0h+var_20]
0x140020178  mov     rbx, [r11+40h]
0x14002017c  mov     rsi, [r11+48h]
0x140020180  mov     rsp, r11
0x140020183  pop     r15
0x140020185  pop     r14
0x140020187  pop     r13
0x140020189  pop     rdi
0x14002018a  pop     rbp
0x14002018b  retn
```
