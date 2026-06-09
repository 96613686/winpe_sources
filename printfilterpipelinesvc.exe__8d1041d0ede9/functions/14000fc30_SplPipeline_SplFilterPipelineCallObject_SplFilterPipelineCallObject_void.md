# SplPipeline::SplFilterPipelineCallObject::SplFilterPipelineCallObject(void)

- ea: `0x14000fc30`
- end: `0x14000fdf1`
- name: `??0SplFilterPipelineCallObject@SplPipeline@@QEAA@XZ`
- size: `449`
- prototype: `SplPipeline::SplFilterPipelineCallObject *__fastcall(SplPipeline::SplFilterPipelineCallObject *this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140010b50`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140005470`
- `0x14000fa40`
- `0x14000fa98`
- `0x14000fc30`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x14000fd55`
- `KERNEL32!CreateSemaphoreW` at `0x14000fd55`

## string_xrefs

- `0x14000fdb9`: `CreateSemaphore failed`

## pseudocode

```c
SplPipeline::SplFilterPipelineCallObject *__fastcall SplPipeline::SplFilterPipelineCallObject::SplFilterPipelineCallObject(
        SplPipeline::SplFilterPipelineCallObject *this)
{
  _QWORD *v2; // rbx
  NCoreLibrary::TReferenceCount *v3; // rcx
  HANDLE SemaphoreW; // rax
  NCoreLibrary *v6; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  unsigned int v10; // [rsp+20h] [rbp-188h]
  const struct win_musl::TStringEllipseBase *v11; // [rsp+28h] [rbp-180h]
  HINSTANCE v12; // [rsp+30h] [rbp-178h]
  _QWORD v13[2]; // [rsp+40h] [rbp-168h] BYREF
  _BYTE v14[160]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-B8h] BYREF

  v13[1] = this;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 9) = -1;
  *((_QWORD *)this + 10) = -1;
  v2 = (_QWORD *)((char *)this + 88);
  *((_QWORD *)this + 11) = -1;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_BYTE *)this + 112) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 21) = DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context;
  *((_OWORD *)this + 11) = DocPerf_PFPM_PrintDocument_Start;
  *((_OWORD *)this + 12) = DocPerf_PFPM_PrintDocument_Stop;
  *((_DWORD *)this + 56) = 0;
  *((_BYTE *)this + 228) = 0;
  *((_DWORD *)this + 58) = 1953721460;
  *((_QWORD *)this + 30) = &NCoreLibrary::TLink::`vftable';
  *((_DWORD *)this + 62) = 1802398836;
  *((_QWORD *)this + 32) = (char *)this + 240;
  *((_QWORD *)this + 33) = (char *)this + 240;
  v13[0] = *((_QWORD *)this + 19);
  v3 = FrameState::TFrameGlobalState::m_gpFrameState;
  *((_QWORD *)this + 19) = FrameState::TFrameGlobalState::m_gpFrameState;
  PrnExcept::SmartAddRef<PrnExcept::SharedString>(v3);
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(v13);
  SemaphoreW = CreateSemaphoreW(0, 1, 1, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(v2, SemaphoreW);
  if ( *v2 == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v14, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v6);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v14,
      LastErrorAsHResult,
      v8,
      v9,
      v10,
      v11,
      v12);
    SplException::TSystemException::Message((SplException::TSystemException *)v14, "CreateSemaphore failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v14);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x14000fc30  mov     [rsp+arg_8], rbx
0x14000fc35  mov     [rsp+arg_10], rsi
0x14000fc3a  push    rdi
0x14000fc3b  sub     rsp, 1A0h
0x14000fc42  mov     rax, cs:__security_cookie
0x14000fc49  xor     rax, rsp
0x14000fc4c  mov     [rsp+1A8h+var_18], rax
0x14000fc54  mov     rdi, rcx
0x14000fc57  mov     [rsp+1A8h+var_160], rcx
0x14000fc5c  xor     ecx, ecx
0x14000fc5e  mov     [rdi+8], ecx
0x14000fc61  mov     [rdi+18h], rcx
0x14000fc65  mov     [rdi+20h], rcx
0x14000fc69  mov     [rdi+28h], rcx
0x14000fc6d  mov     [rdi+30h], rcx
0x14000fc71  mov     [rdi+38h], rcx
0x14000fc75  mov     [rdi+40h], cl
0x14000fc78  mov     [rdi+44h], ecx
0x14000fc7b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000fc7f  mov     [rdi+48h], rsi
0x14000fc83  mov     [rdi+50h], rsi
0x14000fc87  lea     rbx, [rdi+58h]
0x14000fc8b  mov     [rbx], rsi
0x14000fc8e  mov     [rdi+60h], rcx
0x14000fc92  mov     [rdi+68h], rcx
0x14000fc96  mov     [rdi+70h], cl
0x14000fc99  mov     [rdi+78h], rcx
0x14000fc9d  mov     [rdi+80h], rcx
0x14000fca4  mov     [rdi+88h], rcx
0x14000fcab  mov     [rdi+90h], rcx
0x14000fcb2  mov     [rdi+98h], rcx
0x14000fcb9  mov     [rdi+0A0h], ecx
0x14000fcbf  mov     rax, cs:DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context
0x14000fcc6  mov     [rdi+0A8h], rax
0x14000fccd  movups  xmm0, cs:DocPerf_PFPM_PrintDocument_Start
0x14000fcd4  movdqu  xmmword ptr [rdi+0B0h], xmm0
0x14000fcdc  movups  xmm1, cs:DocPerf_PFPM_PrintDocument_Stop
0x14000fce3  movdqu  xmmword ptr [rdi+0C0h], xmm1
0x14000fceb  mov     [rdi+0E0h], ecx
0x14000fcf1  mov     [rdi+0E4h], cl
0x14000fcf7  mov     dword ptr [rdi+0E8h], 74736C74h
0x14000fd01  lea     rax, [rdi+0F0h]
0x14000fd08  lea     rcx, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x14000fd0f  mov     [rax], rcx
0x14000fd12  mov     dword ptr [rax+8], 6B6E6C74h
0x14000fd19  mov     [rax+10h], rax
0x14000fd1d  mov     [rax+18h], rax
0x14000fd21  mov     rax, [rdi+98h]
0x14000fd28  mov     [rsp+1A8h+var_168], rax
0x14000fd2d  mov     rcx, cs:?m_gpFrameState@TFrameGlobalState@FrameState@@0PEAV12@EA; FrameState::TFrameGlobalState * FrameState::TFrameGlobalState::m_gpFrameState
0x14000fd34  mov     [rdi+98h], rcx
0x14000fd3b  call    ??$SmartAddRef@VSharedString@PrnExcept@@@PrnExcept@@YAXPEAVSharedString@0@@Z; PrnExcept::SmartAddRef<PrnExcept::SharedString>(PrnExcept::SharedString *)
0x14000fd40  lea     rcx, [rsp+1A8h+var_168]
0x14000fd45  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14000fd4a  xor     r9d, r9d; lpName
0x14000fd4d  lea     edx, [rsi+2]; lInitialCount
0x14000fd50  mov     r8d, edx; lMaximumCount
0x14000fd53  xor     ecx, ecx; lpSemaphoreAttributes
0x14000fd55  call    cs:__imp_CreateSemaphoreW
0x14000fd5b  mov     rdx, rax
0x14000fd5e  mov     rcx, rbx
0x14000fd61  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x14000fd66  cmp     [rbx], rsi
0x14000fd69  jz      short loc_14000FD93
0x14000fd6b  mov     rax, rdi
0x14000fd6e  mov     rcx, [rsp+1A8h+var_18]
0x14000fd76  xor     rcx, rsp; StackCookie
0x14000fd79  call    __security_check_cookie
0x14000fd7e  lea     r11, [rsp+1A8h+var_8]
0x14000fd86  mov     rbx, [r11+18h]
0x14000fd8a  mov     rsi, [r11+20h]
0x14000fd8e  mov     rsp, r11
0x14000fd91  pop     rdi
0x14000fd92  retn
0x14000fd93  xor     r8d, r8d; unsigned int
0x14000fd96  lea     rdx, asc_1400696D8; "-"
0x14000fd9d  lea     rcx, [rsp+1A8h+var_158]; this
0x14000fda2  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14000fda7  nop
0x14000fda8  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000fdad  mov     edx, eax; unsigned int
0x14000fdaf  lea     rcx, [rsp+1A8h+var_158]; this
0x14000fdb4  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14000fdb9  lea     rdx, aCreatesemaphor; "CreateSemaphore failed"
0x14000fdc0  lea     rcx, [rsp+1A8h+var_158]; this
0x14000fdc5  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14000fdca  lea     rdx, [rsp+1A8h+var_158]; struct SplException::THResultException *
0x14000fdcf  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x14000fdd7  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14000fddc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14000fde3  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x14000fdeb  call    _CxxThrowException_0
```
