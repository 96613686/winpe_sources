# IsDesktopShellProcess(void)

- ea: `0x180182674`
- end: `0x1801827fa`
- name: `?IsDesktopShellProcess@@YA_NXZ`
- size: `390`
- prototype: `bool __fastcall()`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180182448`
- `0x180186dc0`

## callees

- `0x18000712c`
- `0x1800818c4`
- `0x180182674`
- `0x1801ab028`
- `0x1801ace5c`
- `0x1801ad8d0`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180182737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018274c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180182761`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180182737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018274c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180182761`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18018271d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18018271d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801827a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801827a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801826f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801826f8`

## string_xrefs

- `0x180182714`: `ext-ms-win-ntuser-window-l1-1-0.dll`
- `0x180182742`: `GetWindowThreadProcessId`
- `0x180182757`: `IsGUIThread`

## pseudocode

```c
bool __fastcall IsDesktopShellProcess(const wchar_t *a1)
{
  IsDesktopShellProcessDetails::IsDesktopShellProcessState Value; // bl
  _UNICODE_STRING *FileName; // rax
  __int64 (*ProcAddress)(void); // rbp
  FARPROC v4; // rdi
  FARPROC v5; // rax
  __int64 v6; // rcx
  unsigned int (__fastcall *v7)(_QWORD); // rsi
  __int64 v8; // rax
  __int64 v9; // rcx
  _UNICODE_STRING result; // [rsp+30h] [rbp-28h] BYREF
  unsigned int shellProcessId; // [rsp+60h] [rbp+8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (__cdecl*)(HINSTANCE__ *),&FreeLibrary,wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t> > > user32; // [rsp+68h] [rbp+10h] BYREF

  Value = IsDesktopShellProcessDetails::g_isDesktopShellProcessState._Storage._Value;
  if ( IsDesktopShellProcessDetails::g_isDesktopShellProcessState._Storage._Value == Undetermined )
  {
    Value = IsNotDesktopShellProcess;
    if ( IsDesktopShellProcessDetails::IsApiSetPresent(a1) )
    {
      if ( NtCurrentPeb()->SessionId )
      {
        if ( !IsDesktopShellProcessDetails::WasCurrentProcessCreatedWithExplicitNonDefaultDesktop() )
        {
          FileName = ImagePath::GetFileName(&result);
          if ( CompareStringOrdinal(FileName->Buffer, FileName->Length >> 1, L"explorer.exe", -1, 1) == 2 )
          {
            user32.m_ptr = 0;
            if ( GetModuleHandleExW(0, L"ext-ms-win-ntuser-window-l1-1-0.dll", &user32.m_ptr) )
            {
              ProcAddress = GetProcAddress(user32.m_ptr, "GetShellWindow");
              v4 = GetProcAddress(user32.m_ptr, "GetWindowThreadProcessId");
              v5 = GetProcAddress(user32.m_ptr, "IsGUIThread");
              v7 = (unsigned int (__fastcall *)(_QWORD))v5;
              if ( ProcAddress && v4 && v5 )
              {
                v8 = ProcAddress();
                if ( v8 )
                {
                  shellProcessId = 0;
                  if ( !((unsigned int (__fastcall *)(__int64, unsigned int *))v4)(v8, &shellProcessId) )
                    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
                  if ( GetCurrentProcessId() == shellProcessId )
                    Value = IsDesktopShellProcess;
                }
                else if ( v7(0) )
                {
                  Value = IsDesktopShellProcess;
                }
              }
              else
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v6);
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&user32);
          }
        }
      }
    }
    IsDesktopShellProcessDetails::g_isDesktopShellProcessState._Storage._Value = Value;
  }
  return Value == IsDesktopShellProcess;
}

```

## disassembly

```asm
0x180182674  mov     [rsp+arg_10], rbx
0x180182679  mov     [rsp+arg_18], rbp
0x18018267e  push    rsi
0x18018267f  push    rdi
0x180182680  push    r15
0x180182682  sub     rsp, 40h
0x180182686  mov     bl, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A._Storage._Value; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState ...
0x18018268c  mov     r15d, 1
0x180182692  mov     al, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A._Storage._Value; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState ...
0x180182698  nop
0x180182699  test    al, al
0x18018269b  jnz     loc_1801827E1
0x1801826a1  lea     ebx, [r15+1]
0x1801826a5  call    ?IsApiSetPresent@IsDesktopShellProcessDetails@@YA_NPEBG@Z; IsDesktopShellProcessDetails::IsApiSetPresent(ushort const *)
0x1801826aa  test    al, al
0x1801826ac  jz      loc_1801827D9
0x1801826b2  mov     rax, gs:60h
0x1801826bb  cmp     dword ptr [rax+2C0h], 0
0x1801826c2  jz      loc_1801827D9
0x1801826c8  call    ?WasCurrentProcessCreatedWithExplicitNonDefaultDesktop@IsDesktopShellProcessDetails@@YA_NXZ; IsDesktopShellProcessDetails::WasCurrentProcessCreatedWithExplicitNonDefaultDesktop(void)
0x1801826cd  test    al, al
0x1801826cf  jnz     loc_1801827D9
0x1801826d5  lea     rcx, [rsp+58h+result]; result
0x1801826da  call    ?GetFileName@ImagePath@@CA?AU_UNICODE_STRING@@XZ; ImagePath::GetFileName(void)
0x1801826df  or      r9d, 0FFFFFFFFh; cchCount2
0x1801826e3  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x1801826e8  lea     r8, aExplorerExe; "explorer.exe"
0x1801826ef  movzx   edx, word ptr [rax]
0x1801826f2  mov     rcx, [rax+8]; lpString1
0x1801826f6  shr     edx, 1; cchCount1
0x1801826f8  call    cs:__imp_CompareStringOrdinal
0x1801826fe  cmp     eax, ebx
0x180182700  jnz     loc_1801827D9
0x180182706  lea     r8, [rsp+58h+user32]; phModule
0x18018270b  mov     [rsp+58h+user32.m_ptr], 0
0x180182714  lea     rdx, aExtMsWinNtuser; "ext-ms-win-ntuser-window-l1-1-0.dll"
0x18018271b  xor     ecx, ecx; dwFlags
0x18018271d  call    cs:__imp_GetModuleHandleExW
0x180182723  test    eax, eax
0x180182725  jz      loc_1801827CF
0x18018272b  mov     rcx, [rsp+58h+user32.m_ptr]; hModule
0x180182730  lea     rdx, aGetshellwindow; "GetShellWindow"
0x180182737  call    cs:__imp_GetProcAddress
0x18018273d  mov     rcx, [rsp+58h+user32.m_ptr]; hModule
0x180182742  lea     rdx, aGetwindowthrea; "GetWindowThreadProcessId"
0x180182749  mov     rbp, rax
0x18018274c  call    cs:__imp_GetProcAddress
0x180182752  mov     rcx, [rsp+58h+user32.m_ptr]; hModule
0x180182757  lea     rdx, aIsguithread_0; "IsGUIThread"
0x18018275e  mov     rdi, rax
0x180182761  call    cs:__imp_GetProcAddress
0x180182767  mov     rsi, rax
0x18018276a  test    rbp, rbp
0x18018276d  jz      short loc_1801827CA
0x18018276f  test    rdi, rdi
0x180182772  jz      short loc_1801827CA
0x180182774  test    rax, rax
0x180182777  jz      short loc_1801827CA
0x180182779  mov     rax, rbp
0x18018277c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182781  test    rax, rax
0x180182784  jz      short loc_1801827B8
0x180182786  mov     rcx, rax
0x180182789  mov     [rsp+58h+shellProcessId], 0
0x180182791  mov     rax, rdi
0x180182794  lea     rdx, [rsp+58h+shellProcessId]
0x180182799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018279e  test    eax, eax
0x1801827a0  jnz     short loc_1801827A7
0x1801827a2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "shellThreadId != 0")
0x1801827a7  call    cs:__imp_GetCurrentProcessId
0x1801827ad  cmp     eax, [rsp+58h+shellProcessId]
0x1801827b1  jnz     short loc_1801827CF
0x1801827b3  mov     bl, r15b
0x1801827b6  jmp     short loc_1801827CF
0x1801827b8  xor     ecx, ecx
0x1801827ba  mov     rax, rsi
0x1801827bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801827c2  test    eax, eax
0x1801827c4  cmovnz  ebx, r15d
0x1801827c8  jmp     short loc_1801827CF
0x1801827ca  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "getShellWindow && getWindowThreadProcessId && isGUIThread")
0x1801827cf  lea     rcx, [rsp+58h+user32]; this
0x1801827d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801827d9  mov     al, bl
0x1801827db  xchg    al, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A._Storage._Value; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState ...
0x1801827e1  mov     rbp, [rsp+58h+arg_18]
0x1801827e6  cmp     bl, r15b
0x1801827e9  mov     rbx, [rsp+58h+arg_10]
0x1801827ee  setz    al
0x1801827f1  add     rsp, 40h
0x1801827f5  pop     r15
0x1801827f7  pop     rdi
0x1801827f8  pop     rsi
0x1801827f9  retn
```
