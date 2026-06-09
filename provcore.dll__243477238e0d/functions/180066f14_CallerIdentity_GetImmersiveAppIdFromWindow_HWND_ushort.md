# CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)

- ea: `0x180066f14`
- end: `0x180067018`
- name: `?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z`
- size: `260`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, wchar_t **result)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180067668`

## callees

- `0x1800061a8`
- `0x1800071d4`
- `0x1800071f4`
- `0x180066348`
- `0x18006675c`
- `0x180066f14`
- `0x180067068`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180066f65`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180066f65`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180066f36`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180066f36`
- `USER32!GetProcessUIContextInformation` at `0x180066f96`
- `USER32!GetProcessUIContextInformation` at `0x180066f96`

## pseudocode

```c
HRESULT __fastcall CallerIdentity::GetImmersiveAppIdFromWindow(HWND hwnd, wchar_t **result)
{
  HANDLE v5; // rbx
  int ProcessAppId; // eax
  int v7; // ebx
  HRESULT WeakWindowAppId; // eax
  HRESULT v9; // esi
  void *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int processId; // [rsp+48h] [rbp+10h] BYREF
  PROCESS_UICONTEXT_INFORMATION uicontextInfo; // [rsp+50h] [rbp+18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > windowProcessHandle; // [rsp+58h] [rbp+20h] BYREF

  *result = 0;
  processId = 0;
  if ( !GetWindowThreadProcessId(hwnd, &processId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             0x6Cu,
             "onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp");
  v5 = OpenProcess(0x1000u, 0, processId);
  windowProcessHandle.m_ptr = v5;
  if ( (((unsigned __int64)v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    uicontextInfo = 0;
    if ( (unsigned int)GetProcessUIContextInformation(v5, &uicontextInfo) )
    {
      if ( uicontextInfo.processUIContext == PROCESS_UICONTEXT_IMMERSIVE_BROKER )
      {
        WeakWindowAppId = CallerIdentity::GetWeakWindowAppId(hwnd, result);
        v9 = WeakWindowAppId;
        if ( WeakWindowAppId < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            0x79u,
            "onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
            WeakWindowAppId);
          v7 = v9;
          goto LABEL_14;
        }
      }
      if ( *result || (ProcessAppId = CallerIdentity::GetProcessAppId(v5, result), ProcessAppId >= 0) )
      {
        v7 = 0;
        goto LABEL_14;
      }
    }
    else
    {
      ProcessAppId = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       0x72u,
                       "onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp");
    }
  }
  else
  {
    ProcessAppId = wil::details::GetLastErrorFailHr();
  }
  v7 = ProcessAppId;
LABEL_14:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&windowProcessHandle);
  return v7;
}

```

## disassembly

```asm
0x180066f14  push    rbx
0x180066f16  push    rsi
0x180066f17  push    rdi
0x180066f18  sub     rsp, 20h
0x180066f1c  mov     rdi, result
0x180066f1f  mov     qword ptr [result], 0
0x180066f26  lea     result, [rsp+38h+processId]; lpdwProcessId
0x180066f2b  mov     [rsp+38h+processId], 0
0x180066f33  mov     rsi, hwnd
0x180066f36  call    cs:__imp_GetWindowThreadProcessId
0x180066f3c  test    eax, eax
0x180066f3e  jnz     short loc_180066F59
0x180066f40  mov     hwnd, [rsp+38h]; callerReturnAddress
0x180066f45  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180066f4c  lea     edx, [rax+6Ch]; lineNumber
0x180066f4f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180066f54  jmp     loc_180067010
0x180066f59  mov     r8d, [rsp+38h+processId]; dwProcessId
0x180066f5e  xor     edx, edx; bInheritHandle
0x180066f60  mov     ecx, 1000h; dwDesiredAccess
0x180066f65  call    cs:__imp_OpenProcess
0x180066f6b  mov     rbx, rax
0x180066f6e  mov     [rsp+38h+windowProcessHandle.m_ptr], rax
0x180066f73  inc     rax
0x180066f76  test    rax, 0FFFFFFFFFFFFFFFEh
0x180066f7c  jnz     short loc_180066F85
0x180066f7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180066f83  jmp     short loc_180066FB4
0x180066f85  lea     result, [rsp+38h+uicontextInfo]
0x180066f8a  mov     qword ptr [rsp+38h+uicontextInfo.processUIContext], 0
0x180066f93  mov     hwnd, rbx
0x180066f96  call    cs:__imp_GetProcessUIContextInformation
0x180066f9c  test    eax, eax
0x180066f9e  jnz     short loc_180066FB8
0x180066fa0  mov     hwnd, [rsp+38h]; callerReturnAddress
0x180066fa5  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180066fac  lea     edx, [rax+72h]; lineNumber
0x180066faf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180066fb4  mov     ebx, eax
0x180066fb6  jmp     short loc_180067004
0x180066fb8  cmp     [rsp+38h+uicontextInfo.processUIContext], 2
0x180066fbd  jnz     short loc_180066FED
0x180066fbf  mov     result, rdi; value
0x180066fc2  mov     hwnd, rsi; window
0x180066fc5  call    ?GetWeakWindowAppId@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetWeakWindowAppId(HWND__ *,ushort * *)
0x180066fca  mov     esi, eax
0x180066fcc  test    eax, eax
0x180066fce  jns     short loc_180066FED
0x180066fd0  mov     hwnd, [rsp+38h]; callerReturnAddress
0x180066fd5  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180066fdc  mov     r9d, eax; hr
0x180066fdf  mov     edx, 79h ; 'y'; lineNumber
0x180066fe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066fe9  mov     ebx, esi
0x180066feb  jmp     short loc_180067004
0x180066fed  cmp     qword ptr [rdi], 0
0x180066ff1  jnz     short loc_180067002
0x180066ff3  mov     result, rdi; ppszAppId
0x180066ff6  mov     hwnd, rbx; hProcess
0x180066ff9  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180066ffe  test    eax, eax
0x180067000  js      short loc_180066FB4
0x180067002  xor     ebx, ebx
0x180067004  lea     hwnd, [rsp+38h+windowProcessHandle]; this
0x180067009  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006700e  mov     eax, ebx
0x180067010  add     rsp, 20h
0x180067014  pop     rdi
0x180067015  pop     rsi
0x180067016  pop     rbx
0x180067017  retn
```
