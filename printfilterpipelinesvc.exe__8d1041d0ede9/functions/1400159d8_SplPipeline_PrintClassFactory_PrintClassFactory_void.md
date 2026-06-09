# SplPipeline::PrintClassFactory::PrintClassFactory(void)

- ea: `0x1400159d8`
- end: `0x140015b34`
- name: `??0PrintClassFactory@SplPipeline@@QEAA@XZ`
- size: `348`
- prototype: `SplPipeline::PrintClassFactory *__fastcall(SplPipeline::PrintClassFactory *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015dcc`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x1400086f8`
- `0x140010180`
- `0x1400159d8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140015a6b`
- `KERNEL32!GetProcAddress` at `0x140015a6b`
- `KERNEL32!LoadLibraryW` at `0x140015a4d`
- `KERNEL32!LoadLibraryW` at `0x140015a4d`

## string_xrefs

- `0x140015afc`: `LoadLibrary failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
SplPipeline::PrintClassFactory *__fastcall SplPipeline::PrintClassFactory::PrintClassFactory(
        SplPipeline::PrintClassFactory *this)
{
  HMODULE *v2; // rbx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  NCoreLibrary *v6; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  unsigned int v10; // [rsp+20h] [rbp-188h]
  const struct win_musl::TStringEllipseBase *v11; // [rsp+28h] [rbp-180h]
  HINSTANCE v12; // [rsp+30h] [rbp-178h]
  _BYTE v13[160]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-B8h] BYREF

  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  *((_DWORD *)this + 2) = 1852534389;
  *((_DWORD *)this + 3) = 1;
  _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
  *(_QWORD *)this = &SplPipeline::PrintClassFactory::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &SplPipeline::PrintClassFactory::`vftable'{for `IPrintClassObjectFactory'};
  *((_QWORD *)this + 3) = 0;
  v2 = (HMODULE *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  LibraryW = LoadLibraryW(L"winspool.drv");
  NCoreLibrary::TAutoHandleHMODULE::operator=(v2, LibraryW);
  if ( !*v2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v13, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v6);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v13,
      LastErrorAsHResult,
      v8,
      v9,
      v10,
      v11,
      v12);
    SplException::TSystemException::Message((SplException::TSystemException *)v13, "LoadLibrary failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v13);
    throw (SplException::THResultException *)pExceptionObject;
  }
  ProcAddress = GetProcAddress(*v2, (LPCSTR)0xFB);
  *((_QWORD *)this + 3) = ProcAddress;
  if ( !ProcAddress
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_5a9f99331a6131c020fc81a2a98f0016_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x1400159d8  mov     [rsp+arg_8], rbx
0x1400159dd  push    rdi
0x1400159de  sub     rsp, 1A0h
0x1400159e5  mov     rax, cs:__security_cookie
0x1400159ec  xor     rax, rsp
0x1400159ef  mov     [rsp+1A8h+var_18], rax
0x1400159f7  mov     rdi, rcx
0x1400159fa  mov     [rsp+1A8h+var_168], rcx
0x1400159ff  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140015a06  mov     [rcx], rax
0x140015a09  mov     dword ptr [rcx+8], 6E6B6E75h
0x140015a10  mov     dword ptr [rcx+0Ch], 1
0x140015a17  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140015a1e  lea     rax, ??_7PrintClassFactory@SplPipeline@@6BTUnknown@NCOMLibrary@@@; const SplPipeline::PrintClassFactory::`vftable'{for `NCOMLibrary::TUnknown'}
0x140015a25  mov     [rcx], rax
0x140015a28  lea     rax, ??_7PrintClassFactory@SplPipeline@@6BIPrintClassObjectFactory@@@; const SplPipeline::PrintClassFactory::`vftable'{for `IPrintClassObjectFactory'}
0x140015a2f  mov     [rcx+10h], rax
0x140015a33  mov     qword ptr [rcx+18h], 0
0x140015a3b  lea     rbx, [rcx+20h]
0x140015a3f  mov     qword ptr [rbx], 0
0x140015a46  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x140015a4d  call    cs:__imp_LoadLibraryW
0x140015a53  mov     rdx, rax
0x140015a56  mov     rcx, rbx
0x140015a59  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x140015a5e  mov     rcx, [rbx]; hModule
0x140015a61  test    rcx, rcx
0x140015a64  jz      short loc_140015AD6
0x140015a66  mov     edx, 0FBh; lpProcName
0x140015a6b  call    cs:__imp_GetProcAddress
0x140015a71  mov     [rdi+18h], rax
0x140015a75  test    rax, rax
0x140015a78  jnz     short loc_140015AB2
0x140015a7a  lea     rax, WPP_GLOBAL_Control
0x140015a81  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a88  cmp     rcx, rax
0x140015a8b  jz      short loc_140015AB2
0x140015a8d  test    dword ptr [rcx+1Ch], 100h
0x140015a94  jz      short loc_140015AB2
0x140015a96  cmp     byte ptr [rcx+19h], 2
0x140015a9a  jb      short loc_140015AB2
0x140015a9c  mov     edx, 15h
0x140015aa1  lea     r8, WPP_5a9f99331a6131c020fc81a2a98f0016_Traceguids
0x140015aa8  mov     rcx, [rcx+10h]
0x140015aac  call    WPP_SF_
0x140015ab1  nop
0x140015ab2  mov     rax, rdi
0x140015ab5  mov     rcx, [rsp+1A8h+var_18]
0x140015abd  xor     rcx, rsp; StackCookie
0x140015ac0  call    __security_check_cookie
0x140015ac5  mov     rbx, [rsp+1A8h+arg_8]
0x140015acd  add     rsp, 1A0h
0x140015ad4  pop     rdi
0x140015ad5  retn
0x140015ad6  xor     r8d, r8d; unsigned int
0x140015ad9  lea     rdx, asc_1400696D8; "-"
0x140015ae0  lea     rcx, [rsp+1A8h+var_158]; this
0x140015ae5  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140015aea  nop
0x140015aeb  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140015af0  mov     edx, eax; unsigned int
0x140015af2  lea     rcx, [rsp+1A8h+var_158]; this
0x140015af7  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140015afc  lea     rdx, aLoadlibraryFai; "LoadLibrary failed."
0x140015b03  lea     rcx, [rsp+1A8h+var_158]; this
0x140015b08  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140015b0d  lea     rdx, [rsp+1A8h+var_158]; struct SplException::THResultException *
0x140015b12  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x140015b1a  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140015b1f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140015b26  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x140015b2e  call    _CxxThrowException_0
```
