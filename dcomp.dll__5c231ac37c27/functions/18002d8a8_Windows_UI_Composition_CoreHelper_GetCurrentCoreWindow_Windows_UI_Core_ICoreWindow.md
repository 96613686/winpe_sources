# Windows::UI::Composition::CoreHelper::GetCurrentCoreWindow(Windows::UI::Core::ICoreWindow * *)

- ea: `0x18002d8a8`
- end: `0x18002d9f9`
- name: `?GetCurrentCoreWindow@CoreHelper@Composition@UI@Windows@@SAJPEAPEAUICoreWindow@Core@34@@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct Windows::UI::Core::ICoreWindow **)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d700`
- `0x1800a5d90`
- `0x1800c9290`

## callees

- `0x18001358c`
- `0x18002d8a8`
- `0x1800ad1c4`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d94a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d94a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d8da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d8da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d903`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d9bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d903`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d9bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d98a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d98a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d8e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d8e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d974`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d9a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d9a4`

## string_xrefs

- `0x18002d943`: `windows.ui.dll`
- `0x18002d9de`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionroot.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CoreHelper::GetCurrentCoreWindow(
        struct Windows::UI::Core::ICoreWindow **a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  HRESULT v5; // eax
  int v6[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  *(_QWORD *)v6 = &Windows::UI::Composition::CoreHelper::s_lock;
  AcquireSRWLockExclusive(&Windows::UI::Composition::CoreHelper::s_lock);
  dword_1801E1578 = GetCurrentThreadId();
  if ( !Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics )
  {
    if ( !GetModuleHandleW(L"windows.ui.dll") )
    {
      CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(v6);
      return 0;
    }
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      __debugbreak();
    }
    if ( (int)RoGetActivationFactory(
                string,
                &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1,
                &Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics) < 0 )
    {
      dword_1801E1578 = 0;
      ReleaseSRWLockExclusive(&Windows::UI::Composition::CoreHelper::s_lock);
      return 0;
    }
  }
  dword_1801E1578 = 0;
  ReleaseSRWLockExclusive(&Windows::UI::Composition::CoreHelper::s_lock);
  v2 = (*(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreWindowStatic *, struct Windows::UI::Core::ICoreWindow **))(*(_QWORD *)Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics + 48LL))(
         Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics,
         a1);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionroot.cpp",
    (const char *)(unsigned int)v2,
    v6[0]);
  return v3;
}

```

## disassembly

```asm
0x18002d8a8  mov     [rsp+arg_8], rbx
0x18002d8ad  push    rsi
0x18002d8ae  sub     rsp, 50h
0x18002d8b2  mov     rax, cs:__security_cookie
0x18002d8b9  xor     rax, rsp
0x18002d8bc  mov     [rsp+58h+var_10], rax
0x18002d8c1  lea     rsi, ?s_lock@CoreHelper@Composition@UI@Windows@@1VCReadWriteLock@@A; CReadWriteLock Windows::UI::Composition::CoreHelper::s_lock
0x18002d8c8  mov     qword ptr [rcx], 0
0x18002d8cf  mov     rbx, rcx
0x18002d8d2  mov     qword ptr [rsp+58h+var_38], rsi; int
0x18002d8d7  mov     rcx, rsi; SRWLock
0x18002d8da  call    cs:__imp_AcquireSRWLockExclusive
0x18002d8e0  call    cs:__imp_GetCurrentThreadId
0x18002d8e6  cmp     cs:?s_pAgileCoreWindowStatics@CoreHelper@Composition@UI@Windows@@1PEAUICoreWindowStatic@Core@34@EA, 0; Windows::UI::Core::ICoreWindowStatic * Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics
0x18002d8ee  mov     cs:dword_1801E1578, eax
0x18002d8f4  jz      short loc_18002D943
0x18002d8f6  mov     rcx, rsi; SRWLock
0x18002d8f9  mov     cs:dword_1801E1578, 0
0x18002d903  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d909  mov     rcx, cs:?s_pAgileCoreWindowStatics@CoreHelper@Composition@UI@Windows@@1PEAUICoreWindowStatic@Core@34@EA; Windows::UI::Core::ICoreWindowStatic * Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics
0x18002d910  mov     rdx, rbx
0x18002d913  mov     rax, [rcx]
0x18002d916  mov     rax, [rax+30h]
0x18002d91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d91f  mov     ebx, eax
0x18002d921  test    eax, eax
0x18002d923  js      loc_18002D9D9
0x18002d929  xor     eax, eax
0x18002d92b  mov     rcx, [rsp+58h+var_10]
0x18002d930  xor     rcx, rsp; StackCookie
0x18002d933  call    __security_check_cookie
0x18002d938  mov     rbx, [rsp+58h+arg_8]
0x18002d93d  add     rsp, 50h
0x18002d941  pop     rsi
0x18002d942  retn
0x18002d943  lea     rcx, ModuleName; "windows.ui.dll"
0x18002d94a  call    cs:__imp_GetModuleHandleW
0x18002d950  test    rax, rax
0x18002d953  jz      short loc_18002D9CA
0x18002d955  lea     r9, [rsp+58h+string]; string
0x18002d95a  mov     [rsp+58h+string], 0
0x18002d963  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18002d968  mov     edx, 1Ah; length
0x18002d96d  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x18002d974  call    cs:__imp_WindowsCreateStringReference
0x18002d97a  test    eax, eax
0x18002d97c  jns     short loc_18002D991
0x18002d97e  xor     r9d, r9d; lpArguments
0x18002d981  xor     r8d, r8d; nNumberOfArguments
0x18002d984  mov     ecx, eax; dwExceptionCode
0x18002d986  lea     edx, [r9+1]; dwExceptionFlags
0x18002d98a  call    cs:__imp_RaiseException
0x18002d990  int     3; Trap to Debugger
0x18002d991  mov     rcx, [rsp+58h+string]
0x18002d996  lea     r8, ?s_pAgileCoreWindowStatics@CoreHelper@Composition@UI@Windows@@1PEAUICoreWindowStatic@Core@34@EA; Windows::UI::Core::ICoreWindowStatic * Windows::UI::Composition::CoreHelper::s_pAgileCoreWindowStatics
0x18002d99d  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x18002d9a4  call    cs:__imp_RoGetActivationFactory
0x18002d9aa  test    eax, eax
0x18002d9ac  jns     loc_18002D8F6
0x18002d9b2  mov     rcx, rsi; SRWLock
0x18002d9b5  mov     cs:dword_1801E1578, 0
0x18002d9bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d9c5  jmp     loc_18002D929
0x18002d9ca  lea     rcx, [rsp+58h+var_38]
0x18002d9cf  call    ??1?$CWriteGuard@VCReadWriteLock@@@@QEAA@XZ; CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(void)
0x18002d9d4  jmp     loc_18002D929
0x18002d9d9  mov     rcx, [rsp+58h]; this
0x18002d9de  lea     r8, aOnecoreuapWind_59; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002d9e5  mov     r9d, ebx; char *
0x18002d9e8  mov     edx, 45h ; 'E'; void *
0x18002d9ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d9f2  mov     eax, ebx
0x18002d9f4  jmp     loc_18002D92B
```
