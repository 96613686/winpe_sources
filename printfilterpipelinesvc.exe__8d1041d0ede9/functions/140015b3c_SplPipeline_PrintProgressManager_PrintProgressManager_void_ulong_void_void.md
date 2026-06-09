# SplPipeline::PrintProgressManager::PrintProgressManager(void *,ulong,void *,void *)

- ea: `0x140015b3c`
- end: `0x140015cb6`
- name: `??0PrintProgressManager@SplPipeline@@QEAA@PEAXK00@Z`
- size: `378`
- prototype: `SplPipeline::PrintProgressManager *__fastcall(SplPipeline::PrintProgressManager *this, void *, int, void *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015dcc`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140005470`
- `0x1400086f8`
- `0x140010180`
- `0x140015b3c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140015bed`
- `KERNEL32!GetProcAddress` at `0x140015bed`
- `KERNEL32!LoadLibraryW` at `0x140015bcd`
- `KERNEL32!LoadLibraryW` at `0x140015bcd`

## string_xrefs

- `0x140015c7e`: `LoadLibrary failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
SplPipeline::PrintProgressManager *__fastcall SplPipeline::PrintProgressManager::PrintProgressManager(
        SplPipeline::PrintProgressManager *this,
        void *a2,
        int a3,
        void *a4,
        void *a5)
{
  HMODULE *v6; // rbx
  _QWORD *v7; // rcx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  NCoreLibrary *v11; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v13; // r8
  const struct _GUID *v14; // r9
  unsigned int v15; // [rsp+20h] [rbp-188h]
  const struct win_musl::TStringEllipseBase *v16; // [rsp+28h] [rbp-180h]
  HINSTANCE v17; // [rsp+30h] [rbp-178h]
  _BYTE v18[160]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-B8h] BYREF

  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  *((_DWORD *)this + 2) = 1852534389;
  *((_DWORD *)this + 3) = 1;
  _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
  *(_QWORD *)this = &SplPipeline::PrintProgressManager::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &SplPipeline::PrintProgressManager::`vftable'{for `IPrintPipelineProgressReport'};
  *((_QWORD *)this + 3) = a4;
  *((_QWORD *)this + 4) = a5;
  v6 = (HMODULE *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = a3;
  v7 = (_QWORD *)((char *)this + 64);
  *v7 = -1;
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(v7, a2);
  LibraryW = LoadLibraryW(L"winspool.drv");
  NCoreLibrary::TAutoHandleHMODULE::operator=(v6, LibraryW);
  if ( !*v6 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v18, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v11);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v18,
      LastErrorAsHResult,
      v13,
      v14,
      v15,
      v16,
      v17);
    SplException::TSystemException::Message((SplException::TSystemException *)v18, "LoadLibrary failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v18);
    throw (SplException::THResultException *)pExceptionObject;
  }
  ProcAddress = GetProcAddress(*v6, "ReportJobProcessingProgress");
  *((_QWORD *)this + 5) = ProcAddress;
  if ( !ProcAddress
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a9f99331a6131c020fc81a2a98f0016_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x140015b3c  mov     [rsp+arg_8], rbx
0x140015b41  push    rdi
0x140015b42  sub     rsp, 1A0h
0x140015b49  mov     rax, cs:__security_cookie
0x140015b50  xor     rax, rsp
0x140015b53  mov     [rsp+1A8h+var_18], rax
0x140015b5b  mov     rdi, rcx
0x140015b5e  mov     [rsp+1A8h+var_168], rcx
0x140015b63  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140015b6a  mov     [rcx], rax
0x140015b6d  mov     dword ptr [rcx+8], 6E6B6E75h
0x140015b74  mov     dword ptr [rcx+0Ch], 1
0x140015b7b  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140015b82  lea     rax, ??_7PrintProgressManager@SplPipeline@@6BTUnknown@NCOMLibrary@@@; const SplPipeline::PrintProgressManager::`vftable'{for `NCOMLibrary::TUnknown'}
0x140015b89  mov     [rcx], rax
0x140015b8c  lea     rax, ??_7PrintProgressManager@SplPipeline@@6BIPrintPipelineProgressReport@@@; const SplPipeline::PrintProgressManager::`vftable'{for `IPrintPipelineProgressReport'}
0x140015b93  mov     [rcx+10h], rax
0x140015b97  mov     [rcx+18h], r9
0x140015b9b  mov     rax, [rsp+1A8h+arg_20]
0x140015ba3  mov     [rcx+20h], rax
0x140015ba7  lea     rbx, [rcx+30h]
0x140015bab  mov     qword ptr [rbx], 0
0x140015bb2  mov     [rcx+38h], r8d
0x140015bb6  add     rcx, 40h ; '@'
0x140015bba  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140015bc1  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140015bc6  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x140015bcd  call    cs:__imp_LoadLibraryW
0x140015bd3  mov     rdx, rax
0x140015bd6  mov     rcx, rbx
0x140015bd9  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x140015bde  mov     rcx, [rbx]; hModule
0x140015be1  test    rcx, rcx
0x140015be4  jz      short loc_140015C58
0x140015be6  lea     rdx, aReportjobproce; "ReportJobProcessingProgress"
0x140015bed  call    cs:__imp_GetProcAddress
0x140015bf3  mov     [rdi+28h], rax
0x140015bf7  test    rax, rax
0x140015bfa  jnz     short loc_140015C34
0x140015bfc  lea     rax, WPP_GLOBAL_Control
0x140015c03  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c0a  cmp     rcx, rax
0x140015c0d  jz      short loc_140015C34
0x140015c0f  test    dword ptr [rcx+1Ch], 100h
0x140015c16  jz      short loc_140015C34
0x140015c18  cmp     byte ptr [rcx+19h], 2
0x140015c1c  jb      short loc_140015C34
0x140015c1e  mov     edx, 0Ah
0x140015c23  lea     r8, WPP_5a9f99331a6131c020fc81a2a98f0016_Traceguids
0x140015c2a  mov     rcx, [rcx+10h]
0x140015c2e  call    WPP_SF_
0x140015c33  nop
0x140015c34  mov     rax, rdi
0x140015c37  mov     rcx, [rsp+1A8h+var_18]
0x140015c3f  xor     rcx, rsp; StackCookie
0x140015c42  call    __security_check_cookie
0x140015c47  mov     rbx, [rsp+1A8h+arg_8]
0x140015c4f  add     rsp, 1A0h
0x140015c56  pop     rdi
0x140015c57  retn
0x140015c58  xor     r8d, r8d; unsigned int
0x140015c5b  lea     rdx, asc_1400696D8; "-"
0x140015c62  lea     rcx, [rsp+1A8h+var_158]; this
0x140015c67  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140015c6c  nop
0x140015c6d  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140015c72  mov     edx, eax; unsigned int
0x140015c74  lea     rcx, [rsp+1A8h+var_158]; this
0x140015c79  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140015c7e  lea     rdx, aLoadlibraryFai; "LoadLibrary failed."
0x140015c85  lea     rcx, [rsp+1A8h+var_158]; this
0x140015c8a  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140015c8f  lea     rdx, [rsp+1A8h+var_158]; struct SplException::THResultException *
0x140015c94  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x140015c9c  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140015ca1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140015ca8  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x140015cb0  call    _CxxThrowException_0
```
