# PrnSharedState::LoadedModule::LoadedModule(wchar_t const *)

- ea: `0x14004530c`
- end: `0x140045518`
- name: `??0LoadedModule@PrnSharedState@@QEAA@PEB_W@Z`
- size: `524`
- prototype: `PrnSharedState::LoadedModule *__fastcall(PrnSharedState::LoadedModule *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x1400459a4`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140009848`
- `0x14000dce8`
- `0x140010180`
- `0x14004530c`
- `0x140045be4`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140045406`
- `KERNEL32!GetProcAddress` at `0x140045478`
- `KERNEL32!GetProcAddress` at `0x14004548c`
- `KERNEL32!GetProcAddress` at `0x140045406`
- `KERNEL32!GetProcAddress` at `0x140045478`
- `KERNEL32!GetProcAddress` at `0x14004548c`
- `KERNEL32!LoadLibraryExW` at `0x1400453e2`
- `KERNEL32!LoadLibraryExW` at `0x1400453e2`

## string_xrefs

- `0x1400454e8`: `LoadLibraryEx failed %ws.`
- `0x14004543e`: `GetProcAddress DllCanUnloadNow failed %ws.`
- `0x1400453ff`: `DllCanUnloadNow`
- `0x140045482`: `DrvPopulateFilterServices`
- `0x14004546e`: `DllGetClassObject`

## pseudocode

```c
PrnSharedState::LoadedModule *__fastcall PrnSharedState::LoadedModule::LoadedModule(
        PrnSharedState::LoadedModule *this,
        const wchar_t *a2)
{
  HMODULE *v4; // rsi
  wchar_t **v5; // r15
  int v6; // eax
  int v7; // edx
  const char *v8; // r8
  unsigned int v9; // r9d
  unsigned __int64 v10; // rbx
  unsigned __int128 v11; // rax
  void *v12; // rax
  int v13; // eax
  int v14; // edx
  const char *v15; // r8
  unsigned int v16; // r9d
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  NCoreLibrary *v19; // rcx
  unsigned int v20; // eax
  const struct SplException::TSystemException *v21; // r8
  const struct _GUID *v22; // r9
  NCoreLibrary *v24; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v26; // r8
  const struct _GUID *v27; // r9
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v29; // [rsp+28h] [rbp-D8h]
  HINSTANCE v30; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[160]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-10h] BYREF

  v31[1] = (unsigned __int64)this;
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &PrnSharedState::LoadedModule::`vftable';
  v4 = (HMODULE *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  v5 = (wchar_t **)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v31[0] = 0;
  v6 = StringCchLengthW(a2, 0x7FFFFFFFu, v31);
  if ( v6 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v6, v7, v8, v9);
  v10 = v31[0] + 1;
  v11 = (v31[0] + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v31[0] + 1, 2u) )
    *(_QWORD *)&v11 = -1;
  v12 = operator new(v11, *((const char **)&v11 + 1), (unsigned int)v8);
  NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(v5, v12);
  v13 = StringCchCopyW(*v5, v10, a2);
  if ( v13 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v13, v14, v15, v16);
  Library = LoadLibraryExW(a2, 0, 8u);
  NCoreLibrary::TAutoHandleHMODULE::operator=(v4, Library);
  if ( !*v4 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v32, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v24);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v32,
      LastErrorAsHResult,
      v26,
      v27,
      v28,
      v29,
      v30);
    SplException::TSystemException::Message((SplException::TSystemException *)v32, "LoadLibraryEx failed %ws.", a2);
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v32);
    throw (SplException::THResultException *)pExceptionObject;
  }
  ProcAddress = GetProcAddress(*v4, "DllCanUnloadNow");
  *((_QWORD *)this + 3) = ProcAddress;
  if ( !ProcAddress )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v32, "-", 0);
    v20 = NCoreLibrary::GetLastErrorAsHResult(v19);
    SplException::TSystemException::InternalInit((SplException::TSystemException *)v32, v20, v21, v22, v28, v29, v30);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v32,
      "GetProcAddress DllCanUnloadNow failed %ws.",
      a2);
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v32);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *((_QWORD *)this + 4) = GetProcAddress(*v4, "DllGetClassObject");
  *((_QWORD *)this + 5) = GetProcAddress(*v4, "DrvPopulateFilterServices");
  return this;
}

```

## disassembly

```asm
0x14004530c  mov     [rsp-8+arg_10], rbx
0x140045311  push    rbp
0x140045312  push    rsi
0x140045313  push    rdi
0x140045314  push    r14
0x140045316  push    r15
0x140045318  lea     rbp, [rsp-0A0h]
0x140045320  sub     rsp, 1A0h
0x140045327  mov     rax, cs:__security_cookie
0x14004532e  xor     rax, rsp
0x140045331  mov     [rbp+0C0h+var_30], rax
0x140045338  mov     r14, rdx
0x14004533b  mov     rdi, rcx
0x14004533e  mov     [rsp+1C0h+var_178], rcx
0x140045343  mov     dword ptr [rcx+8], 1
0x14004534a  lea     rax, ??_7LoadedModule@PrnSharedState@@6B@; const PrnSharedState::LoadedModule::`vftable'
0x140045351  mov     [rcx], rax
0x140045354  lea     rsi, [rcx+10h]
0x140045358  mov     qword ptr [rsi], 0
0x14004535f  lea     r15, [rcx+30h]
0x140045363  mov     qword ptr [r15], 0
0x14004536a  mov     [rsp+1C0h+var_180], 0
0x140045373  lea     r8, [rsp+1C0h+var_180]; unsigned __int64 *
0x140045378  mov     edx, 7FFFFFFFh; unsigned __int64
0x14004537d  mov     rcx, r14; wchar_t *
0x140045380  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x140045385  test    eax, eax
0x140045387  jns     short loc_140045391
0x140045389  mov     ecx, eax; this
0x14004538b  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140045391  mov     rbx, [rsp+1C0h+var_180]
0x140045396  inc     rbx
0x140045399  mov     eax, 2
0x14004539e  mul     rbx
0x1400453a1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400453a8  cmovb   rax, rcx
0x1400453ac  mov     rcx, rax; unsigned __int64
0x1400453af  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400453b4  mov     rdx, rax
0x1400453b7  mov     rcx, r15
0x1400453ba  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x1400453bf  mov     r8, r14; wchar_t *
0x1400453c2  mov     rdx, rbx; unsigned __int64
0x1400453c5  mov     rcx, [r15]; wchar_t *
0x1400453c8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400453cd  test    eax, eax
0x1400453cf  jns     short loc_1400453D9
0x1400453d1  mov     ecx, eax; this
0x1400453d3  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400453d9  xor     edx, edx; hFile
0x1400453db  lea     r8d, [rdx+8]; dwFlags
0x1400453df  mov     rcx, r14; lpLibFileName
0x1400453e2  call    cs:__imp_LoadLibraryExW
0x1400453e8  mov     rdx, rax
0x1400453eb  mov     rcx, rsi
0x1400453ee  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x1400453f3  mov     rcx, [rsi]; hModule
0x1400453f6  test    rcx, rcx
0x1400453f9  jz      loc_1400454BF
0x1400453ff  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x140045406  call    cs:__imp_GetProcAddress
0x14004540c  mov     [rdi+18h], rax
0x140045410  test    rax, rax
0x140045413  jnz     short loc_14004546E
0x140045415  xor     r8d, r8d; unsigned int
0x140045418  lea     rdx, asc_1400696D8; "-"
0x14004541f  lea     rcx, [rsp+1C0h+var_170]; this
0x140045424  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140045429  nop
0x14004542a  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14004542f  mov     edx, eax; unsigned int
0x140045431  lea     rcx, [rsp+1C0h+var_170]; this
0x140045436  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14004543b  mov     r8, r14
0x14004543e  lea     rdx, aGetprocaddress; "GetProcAddress DllCanUnloadNow failed %"...
0x140045445  lea     rcx, [rsp+1C0h+var_170]; this
0x14004544a  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14004544f  lea     rdx, [rsp+1C0h+var_170]; struct SplException::THResultException *
0x140045454  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x140045458  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14004545d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140045464  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x140045468  call    _CxxThrowException_0
0x14004546e  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140045475  mov     rcx, [rsi]; hModule
0x140045478  call    cs:__imp_GetProcAddress
0x14004547e  mov     [rdi+20h], rax
0x140045482  lea     rdx, aDrvpopulatefil; "DrvPopulateFilterServices"
0x140045489  mov     rcx, [rsi]; hModule
0x14004548c  call    cs:__imp_GetProcAddress
0x140045492  mov     [rdi+28h], rax
0x140045496  mov     rax, rdi
0x140045499  mov     rcx, [rbp+0C0h+var_30]
0x1400454a0  xor     rcx, rsp; StackCookie
0x1400454a3  call    __security_check_cookie
0x1400454a8  mov     rbx, [rsp+1C0h+arg_10]
0x1400454b0  add     rsp, 1A0h
0x1400454b7  pop     r15
0x1400454b9  pop     r14
0x1400454bb  pop     rdi
0x1400454bc  pop     rsi
0x1400454bd  pop     rbp
0x1400454be  retn
0x1400454bf  xor     r8d, r8d; unsigned int
0x1400454c2  lea     rdx, asc_1400696D8; "-"
0x1400454c9  lea     rcx, [rsp+1C0h+var_170]; this
0x1400454ce  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400454d3  nop
0x1400454d4  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400454d9  mov     edx, eax; unsigned int
0x1400454db  lea     rcx, [rsp+1C0h+var_170]; this
0x1400454e0  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400454e5  mov     r8, r14
0x1400454e8  lea     rdx, aLoadlibraryexF; "LoadLibraryEx failed %ws."
0x1400454ef  lea     rcx, [rsp+1C0h+var_170]; this
0x1400454f4  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400454f9  lea     rdx, [rsp+1C0h+var_170]; struct SplException::THResultException *
0x1400454fe  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x140045502  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140045507  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14004550e  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x140045512  call    _CxxThrowException_0
```
