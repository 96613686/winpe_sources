# TImgPipelineManager::StartOperationX(void)

- ea: `0x14001f6e0`
- end: `0x14001fa7a`
- name: `?StartOperationX@TImgPipelineManager@@UEAAXXZ`
- size: `922`
- prototype: `void __fastcall(TImgPipelineManager *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x14000f9d8`
- `0x14000fa68`
- `0x1400172e8`
- `0x140017a4c`
- `0x14001b1f8`
- `0x14001b240`
- `0x14001bd50`
- `0x14001cb6c`
- `0x14001ce08`
- `0x14001f6e0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x140046578`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001f7a1`
- `KERNEL32!LeaveCriticalSection` at `0x14001f947`
- `KERNEL32!LeaveCriticalSection` at `0x14001f96b`
- `KERNEL32!LeaveCriticalSection` at `0x14001f9c3`
- `KERNEL32!LeaveCriticalSection` at `0x14001f7a1`
- `KERNEL32!LeaveCriticalSection` at `0x14001f947`
- `KERNEL32!LeaveCriticalSection` at `0x14001f96b`
- `KERNEL32!LeaveCriticalSection` at `0x14001f9c3`
- `KERNEL32!QueueUserWorkItem` at `0x14001f910`
- `KERNEL32!QueueUserWorkItem` at `0x14001f910`

## string_xrefs

- `0x14001f759`: `The pipeline is already operating`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall TImgPipelineManager::StartOperationX(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  const struct SplException::TSystemException *v3; // r8
  const struct _GUID *v4; // r9
  int v5; // r13d
  int *p_SpinCount; // rbx
  __int64 v7; // r12
  __int64 v8; // rbx
  const char *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // r15
  __int64 v12; // r15
  struct _RTL_CRITICAL_SECTION *v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // r12
  _QWORD *v17; // rcx
  unsigned int v18; // edx
  int SpinCount; // eax
  bool v20; // sf
  int DebugInfo_high; // eax
  int v22; // r14d
  __int64 LockSemaphore; // rbx
  int v24; // edx
  const char *v25; // r8
  NCoreLibrary *v26; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v28; // r8
  const struct _GUID *v29; // r9
  struct IErrorInfo *v30; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v31; // [rsp+28h] [rbp-D8h]
  HINSTANCE v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v34; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+54h] [rbp-ACh]
  _QWORD v36[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+68h] [rbp-98h]
  int v38; // [rsp+6Ch] [rbp-94h]
  _BYTE v39[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp+10h] BYREF

  v2 = this + 4;
  v34 = this + 4;
  NCoreLibrary::TCriticalSection::Enter(this + 4);
  if ( BYTE1(this[5].OwningThread) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v39, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v39,
      0x80004003,
      v3,
      v4,
      (unsigned int)v30,
      v31,
      v32);
    SplException::TSystemException::Message((SplException::TSystemException *)v39, "The pipeline is already operating");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v39);
    throw (SplException::THResultException *)pExceptionObject;
  }
  BYTE1(this[5].OwningThread) = 1;
  if ( !--HIDWORD(v2[1].DebugInfo) )
    LODWORD(v2[1].DebugInfo) = 0;
  LeaveCriticalSection(v2);
  v36[1] = TImgPipelineManager::ShutdownEveryFilterAndClear;
  v37 = 0;
  v38 = v35;
  v36[0] = (char *)this - 16;
  v5 = 0;
  p_SpinCount = (int *)&this[5].SpinCount;
  while ( v5 < SHIDWORD(this[5].SpinCount) )
  {
    v7 = v5;
    v8 = **(_QWORD **)(*(_QWORD *)&this[2].LockCount
                     + 8 * (((__int64)this[2].OwningThread - 1) & ((__int64)this[2].LockSemaphore + v5)));
    v33 = v8;
    PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(v8);
    v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&this[2].LockCount
                                + 8 * (((__int64)this[2].OwningThread - 1) & ((__int64)this[2].LockSemaphore + v5)))
                    + 64LL);
    if ( v11 )
    {
      v12 = *(_QWORD *)(v11 + 16);
      if ( v12 == -1 )
        v12 = 0;
    }
    else
    {
      v12 = -1;
    }
    v13 = (struct _RTL_CRITICAL_SECTION *)operator new(0x40u, v9, v10);
    v34 = v13;
    if ( v13 )
    {
      v14 = ((__int64)this[2].OwningThread - 1) & ((__int64)this[2].LockSemaphore + v5);
      v15 = *(_QWORD *)&this[2].LockCount;
      v16 = (_QWORD *)(*(_QWORD *)(v15 + 8 * v14) + 72LL);
      if ( *(_QWORD *)(*(_QWORD *)(v15 + 8 * v14) + 96LL) > 7u )
        v16 = (_QWORD *)*v16;
      v13->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v8;
      PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(v8);
      *(_QWORD *)&v13->LockCount = (char *)this - 16;
      PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(&this[-1].LockSemaphore);
      v13->OwningThread = (HANDLE)-1LL;
      LODWORD(v13->LockSemaphore) = v5;
      std::wstring::wstring((__int64)&v13->SpinCount, (__int64)v16);
      if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        NCoreLibrary::TRefHandleNT::CopyFrom((NCoreLibrary::TRefHandleNT *)&v13->OwningThread, (void *)v12);
      v7 = v5;
    }
    else
    {
      v13 = 0;
    }
    v17 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)&this[2].LockCount
                               + 8 * (((__int64)this[2].OwningThread - 1) & ((__int64)this[2].LockSemaphore + v7)))
                   + 64LL);
    if ( *v17 )
      PrnExcept::SmartRelease<PrnExcept::TRefHandle>(v17);
    if ( !QueueUserWorkItem(TSyncThreadContext::PoolThreadProc, v13, 0x10u) )
    {
      if ( v13 )
        TSyncThreadContext::`scalar deleting destructor'((TSyncThreadContext *)v13, v18);
      SplException::THResultException::THResultException((SplException::THResultException *)v39, "-", 0);
      LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v26);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v39,
        LastErrorAsHResult,
        v28,
        v29,
        (unsigned int)v30,
        v31,
        v32);
      SplException::TSystemException::Message((SplException::TSystemException *)v39, "QueueUserWorkItem failed.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v39);
      throw (SplException::THResultException *)pExceptionObject;
    }
    NCoreLibrary::TCriticalSection::Enter(v2);
    p_SpinCount = (int *)&this[5].SpinCount;
    SpinCount = this[5].SpinCount;
    --HIDWORD(this[5].DebugInfo);
    v20 = SpinCount < 0;
    DebugInfo_high = HIDWORD(v2[1].DebugInfo);
    if ( v20 )
    {
      if ( !DebugInfo_high )
        LODWORD(v2[1].DebugInfo) = 0;
      LeaveCriticalSection(v2);
      PrnExcept::SmartRelease<IPartResourceDictionary>(&v33);
      break;
    }
    if ( !DebugInfo_high )
      LODWORD(v2[1].DebugInfo) = 0;
    LeaveCriticalSection(v2);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v33);
    ++v5;
  }
  NCoreLibrary::TCriticalSection::Enter(v2);
  BYTE2(this[5].OwningThread) = 1;
  v22 = *p_SpinCount;
  v33 = 0;
  LockSemaphore = (__int64)this[5].LockSemaphore;
  v34 = (struct _RTL_CRITICAL_SECTION *)LockSemaphore;
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(LockSemaphore);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v33);
  if ( !--HIDWORD(v2[1].DebugInfo) )
    LODWORD(v2[1].DebugInfo) = 0;
  LeaveCriticalSection(v2);
  if ( v22 < 0 )
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v22, v24, v25, LockSemaphore, v30);
  v36[0] = 0;
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v34);
  PrnExcept::TMethodRundown<PrnComps::TImgWriterFileItem>::~TMethodRundown<PrnComps::TImgWriterFileItem>((__int64)v36);
}

```

## disassembly

```asm
0x14001f6e0  push    rbp
0x14001f6e2  push    rbx
0x14001f6e3  push    rsi
0x14001f6e4  push    rdi
0x14001f6e5  push    r12
0x14001f6e7  push    r13
0x14001f6e9  push    r14
0x14001f6eb  push    r15
0x14001f6ed  lea     rbp, [rsp-0C8h]
0x14001f6f5  sub     rsp, 1C8h
0x14001f6fc  mov     rax, cs:__security_cookie
0x14001f703  xor     rax, rsp
0x14001f706  mov     [rbp+100h+var_50], rax
0x14001f70d  mov     rsi, rcx
0x14001f710  lea     rdi, [rcx+0A0h]
0x14001f717  mov     [rsp+200h+var_1B8], rdi
0x14001f71c  mov     rcx, rdi; this
0x14001f71f  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14001f724  nop
0x14001f725  lea     rbx, [rsi-10h]
0x14001f729  xor     r15d, r15d
0x14001f72c  cmp     [rbx+0E9h], r15b
0x14001f733  jz      short loc_14001F789
0x14001f735  xor     r8d, r8d; unsigned int
0x14001f738  lea     rdx, asc_1400696D8; "-"
0x14001f73f  lea     rcx, [rsp+200h+var_190]; this
0x14001f744  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001f749  nop
0x14001f74a  mov     edx, 80004003h; unsigned int
0x14001f74f  lea     rcx, [rsp+200h+var_190]; this
0x14001f754  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001f759  lea     rdx, aThePipelineIsA; "The pipeline is already operating"
0x14001f760  lea     rcx, [rsp+200h+var_190]; this
0x14001f765  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001f76a  lea     rdx, [rsp+200h+var_190]; struct SplException::THResultException *
0x14001f76f  lea     rcx, [rbp+100h+pExceptionObject]; this
0x14001f773  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001f778  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001f77f  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x14001f783  call    _CxxThrowException_0
0x14001f789  mov     byte ptr [rsi+0D9h], 1
0x14001f790  dec     dword ptr [rdi+2Ch]
0x14001f793  mov     eax, [rdi+2Ch]
0x14001f796  test    eax, eax
0x14001f798  jnz     short loc_14001F79E
0x14001f79a  mov     [rdi+28h], r15d
0x14001f79e  mov     rcx, rdi; lpCriticalSection
0x14001f7a1  call    cs:__imp_LeaveCriticalSection
0x14001f7a7  lea     rax, ?ShutdownEveryFilterAndClear@TImgPipelineManager@@AEAAXXZ; TImgPipelineManager::ShutdownEveryFilterAndClear(void)
0x14001f7ae  mov     [rsp+200h+var_1A0], rax
0x14001f7b3  mov     [rsp+200h+var_198], r15d
0x14001f7b8  mov     eax, [rsp+200h+var_1AC]
0x14001f7bc  mov     [rsp+200h+var_194], eax
0x14001f7c0  mov     [rsp+200h+var_1A8], rbx
0x14001f7c5  mov     r13d, r15d
0x14001f7c8  lea     rbx, [rsi+0E8h]
0x14001f7cf  cmp     r13d, [rsi+0ECh]
0x14001f7d6  jge     loc_14001F97D
0x14001f7dc  movsxd  r12, r13d
0x14001f7df  mov     rbx, [rsi+68h]
0x14001f7e3  add     rbx, r12
0x14001f7e6  mov     rax, [rsi+60h]
0x14001f7ea  dec     rax
0x14001f7ed  and     rbx, rax
0x14001f7f0  mov     rax, [rsi+58h]
0x14001f7f4  mov     rbx, [rax+rbx*8]
0x14001f7f8  mov     rbx, [rbx]
0x14001f7fb  mov     [rsp+200h+var_1C0], rbx
0x14001f800  mov     rcx, rbx
0x14001f803  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14001f808  nop
0x14001f809  mov     rcx, [rsi+68h]
0x14001f80d  add     rcx, r12
0x14001f810  mov     rax, [rsi+60h]
0x14001f814  dec     rax
0x14001f817  and     rcx, rax
0x14001f81a  mov     rax, [rsi+58h]
0x14001f81e  mov     rcx, [rax+rcx*8]
0x14001f822  mov     r15, [rcx+40h]
0x14001f826  test    r15, r15
0x14001f829  jz      short loc_14001F83B
0x14001f82b  mov     r15, [r15+10h]
0x14001f82f  xor     eax, eax
0x14001f831  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14001f835  cmovz   r15, rax
0x14001f839  jmp     short loc_14001F83F
0x14001f83b  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001f83f  mov     ecx, 40h ; '@'; unsigned __int64
0x14001f844  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14001f849  mov     r14, rax
0x14001f84c  mov     [rsp+200h+var_1B8], rax
0x14001f851  test    rax, rax
0x14001f854  jz      short loc_14001F8D3
0x14001f856  mov     rcx, [rsi+68h]
0x14001f85a  add     rcx, r12
0x14001f85d  mov     rax, [rsi+60h]
0x14001f861  dec     rax
0x14001f864  and     rcx, rax
0x14001f867  mov     rax, [rsi+58h]
0x14001f86b  mov     r12, [rax+rcx*8]
0x14001f86f  add     r12, 48h ; 'H'
0x14001f873  cmp     qword ptr [r12+18h], 7
0x14001f879  jbe     short loc_14001F87F
0x14001f87b  mov     r12, [r12]
0x14001f87f  mov     [r14], rbx
0x14001f882  mov     rcx, rbx
0x14001f885  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14001f88a  nop
0x14001f88b  lea     rax, [rsi-10h]
0x14001f88f  mov     [r14+8], rax
0x14001f893  mov     rcx, rax
0x14001f896  call    ??$SmartAddRef@V?$PiboResourceDictionary@VMuslConstructPartStream@@@@@PrnExcept@@YAXPEAV?$PiboResourceDictionary@VMuslConstructPartStream@@@@@Z; PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(PiboResourceDictionary<MuslConstructPartStream> *)
0x14001f89b  nop
0x14001f89c  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x14001f8a4  mov     [r14+18h], r13d
0x14001f8a8  lea     rcx, [r14+20h]
0x14001f8ac  mov     rdx, r12
0x14001f8af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001f8b4  lea     rax, [r15-1]
0x14001f8b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001f8bc  ja      short loc_14001F8CB
0x14001f8be  mov     rdx, r15; void *
0x14001f8c1  lea     rcx, [r14+10h]; this
0x14001f8c5  call    ?CopyFrom@TRefHandleNT@NCoreLibrary@@QEAAJPEAX@Z; NCoreLibrary::TRefHandleNT::CopyFrom(void *)
0x14001f8ca  nop
0x14001f8cb  movsxd  r12, r13d
0x14001f8ce  xor     r15d, r15d
0x14001f8d1  jmp     short loc_14001F8D9
0x14001f8d3  xor     r15d, r15d
0x14001f8d6  mov     r14d, r15d
0x14001f8d9  mov     rcx, [rsi+68h]
0x14001f8dd  add     rcx, r12
0x14001f8e0  mov     rax, [rsi+60h]
0x14001f8e4  dec     rax
0x14001f8e7  and     rcx, rax
0x14001f8ea  mov     rax, [rsi+58h]
0x14001f8ee  mov     rcx, [rax+rcx*8]
0x14001f8f2  add     rcx, 40h ; '@'
0x14001f8f6  cmp     [rcx], r15
0x14001f8f9  jz      short loc_14001F900
0x14001f8fb  call    ??$SmartRelease@VTRefHandle@PrnExcept@@@PrnExcept@@YAXPEAPEAVTRefHandle@0@@Z; PrnExcept::SmartRelease<PrnExcept::TRefHandle>(PrnExcept::TRefHandle * *)
0x14001f900  mov     r8d, 10h; Flags
0x14001f906  mov     rdx, r14; Context
0x14001f909  lea     rcx, ?PoolThreadProc@TSyncThreadContext@@SAKPEAX@Z; Function
0x14001f910  call    cs:__imp_QueueUserWorkItem
0x14001f916  test    eax, eax
0x14001f918  jz      loc_14001F9DA
0x14001f91e  mov     rcx, rdi; this
0x14001f921  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14001f926  lea     rbx, [rsi+0E8h]
0x14001f92d  mov     eax, [rbx]
0x14001f92f  dec     dword ptr [rsi+0CCh]
0x14001f935  test    eax, eax
0x14001f937  mov     eax, [rdi+2Ch]
0x14001f93a  js      short loc_14001F960
0x14001f93c  test    eax, eax
0x14001f93e  jnz     short loc_14001F944
0x14001f940  mov     [rdi+28h], r15d
0x14001f944  mov     rcx, rdi; lpCriticalSection
0x14001f947  call    cs:__imp_LeaveCriticalSection
0x14001f94d  nop
0x14001f94e  lea     rcx, [rsp+200h+var_1C0]
0x14001f953  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001f958  inc     r13d
0x14001f95b  jmp     loc_14001F7CF
0x14001f960  test    eax, eax
0x14001f962  jnz     short loc_14001F968
0x14001f964  mov     [rdi+28h], r15d
0x14001f968  mov     rcx, rdi; lpCriticalSection
0x14001f96b  call    cs:__imp_LeaveCriticalSection
0x14001f971  nop
0x14001f972  lea     rcx, [rsp+200h+var_1C0]
0x14001f977  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001f97c  nop
0x14001f97d  mov     rcx, rdi; this
0x14001f980  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14001f985  mov     byte ptr [rsi+0DAh], 1
0x14001f98c  mov     r14d, [rbx]
0x14001f98f  mov     [rsp+200h+var_1C0], r15
0x14001f994  mov     rbx, [rsi+0E0h]
0x14001f99b  mov     [rsp+200h+var_1B8], rbx
0x14001f9a0  mov     rcx, rbx
0x14001f9a3  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14001f9a8  lea     rcx, [rsp+200h+var_1C0]
0x14001f9ad  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001f9b2  dec     dword ptr [rdi+2Ch]
0x14001f9b5  mov     eax, [rdi+2Ch]
0x14001f9b8  test    eax, eax
0x14001f9ba  jnz     short loc_14001F9C0
0x14001f9bc  mov     [rdi+28h], r15d
0x14001f9c0  mov     rcx, rdi; lpCriticalSection
0x14001f9c3  call    cs:__imp_LeaveCriticalSection
0x14001f9c9  test    r14d, r14d
0x14001f9cc  jns     short loc_14001FA3D
0x14001f9ce  mov     r9, rbx; unsigned int
0x14001f9d1  mov     ecx, r14d; this
0x14001f9d4  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDKPEAUIErrorInfo@@@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong,IErrorInfo *)
0x14001f9da  test    r14, r14
0x14001f9dd  jz      short loc_14001F9E7
0x14001f9df  mov     rcx, r14; this
0x14001f9e2  call    ??_GTSyncThreadContext@@QEAAPEAXI@Z; TSyncThreadContext::`scalar deleting destructor'(uint)
0x14001f9e7  xor     r8d, r8d; unsigned int
0x14001f9ea  lea     rdx, asc_1400696D8; "-"
0x14001f9f1  lea     rcx, [rsp+200h+var_190]; this
0x14001f9f6  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001f9fb  nop
0x14001f9fc  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14001fa01  mov     edx, eax; unsigned int
0x14001fa03  lea     rcx, [rsp+200h+var_190]; this
0x14001fa08  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001fa0d  lea     rdx, aQueueuserworki; "QueueUserWorkItem failed."
0x14001fa14  lea     rcx, [rsp+200h+var_190]; this
0x14001fa19  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001fa1e  lea     rdx, [rsp+200h+var_190]; struct SplException::THResultException *
0x14001fa23  lea     rcx, [rbp+100h+pExceptionObject]; this
0x14001fa27  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001fa2c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001fa33  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x14001fa37  call    _CxxThrowException_0
0x14001fa3d  mov     [rsp+200h+var_1A8], r15
0x14001fa42  lea     rcx, [rsp+200h+var_1B8]
0x14001fa47  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001fa4c  nop
0x14001fa4d  lea     rcx, [rsp+200h+var_1A8]
0x14001fa52  call    ??1?$TMethodRundown@VTImgWriterFileItem@PrnComps@@@PrnExcept@@QEAA@XZ; PrnExcept::TMethodRundown<PrnComps::TImgWriterFileItem>::~TMethodRundown<PrnComps::TImgWriterFileItem>(void)
0x14001fa57  mov     rcx, [rbp+100h+var_50]
0x14001fa5e  xor     rcx, rsp; StackCookie
0x14001fa61  call    __security_check_cookie
0x14001fa66  add     rsp, 1C8h
0x14001fa6d  pop     r15
0x14001fa6f  pop     r14
0x14001fa71  pop     r13
0x14001fa73  pop     r12
0x14001fa75  pop     rdi
0x14001fa76  pop     rsi
0x14001fa77  pop     rbx
0x14001fa78  pop     rbp
0x14001fa79  retn
```
