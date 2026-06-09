# WebRuntimeDiagnostics::DiagnosticsTarget::CreateWebRuntimeDiagnosticsWindow(void)

- ea: `0x18006b6bc`
- end: `0x18006b812`
- name: `?CreateWebRuntimeDiagnosticsWindow@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(WebRuntimeDiagnostics::DiagnosticsTarget *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026258`

## callees

- `0x180018b30`
- `0x18002c5b0`
- `0x180037b5c`
- `0x18006b6bc`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18006b7dc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18006b7dc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18006b754`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18006b754`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006b6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006b6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b75f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b75f`

## pseudocode

```c
void __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::CreateWebRuntimeDiagnosticsWindow(
        WebRuntimeDiagnostics::DiagnosticsTarget *this)
{
  const char *v2; // r9
  signed int LastError; // eax
  const char *v4; // r9
  unsigned int v5; // ecx
  HWND Window; // rax
  const char *v7; // r9
  WNDCLASSEXW v8; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  HINSTANCE hInstance; // [rsp+E8h] [rbp+10h] BYREF

  hInstance = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)WebRuntimeDiagnostics::DiagnosticsTarget::ProcessWindowMessage, &hInstance) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x303,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      v2);
  if ( !s_messageWindowClassAtom )
  {
    memset_0(&v8, 0, sizeof(v8));
    v8.hInstance = hInstance;
    v8.cbSize = 80;
    v8.lpfnWndProc = (WNDPROC)WebRuntimeDiagnostics::DiagnosticsTarget::ProcessWindowMessage;
    v8.lpszClassName = L"WebRuntimeDiagnostics Message Window Class";
    if ( !RegisterClassExW(&v8) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 != -2147023486 )
      {
        s_messageWindowClassAtom = 0;
        if ( v5 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x31A,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
            v4);
      }
    }
  }
  Window = CreateWindowExW(
             0,
             L"WebRuntimeDiagnostics Message Window Class",
             0,
             0,
             0,
             0,
             0,
             0,
             HWND_MESSAGE,
             0,
             hInstance,
             this);
  *((_QWORD *)this + 8) = Window;
  if ( !Window )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      v7);
}

```

## disassembly

```asm
0x18006b6bc  mov     rax, rsp
0x18006b6bf  push    rbx
0x18006b6c0  push    rbp
0x18006b6c1  push    rsi
0x18006b6c2  push    r14
0x18006b6c4  sub     rsp, 0B8h
0x18006b6cb  xor     esi, esi
0x18006b6cd  lea     r14, ?ProcessWindowMessage@DiagnosticsTarget@WebRuntimeDiagnostics@@CA_JPEAUHWND__@@I_K_J@Z; WebRuntimeDiagnostics::DiagnosticsTarget::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18006b6d4  mov     rbx, rcx
0x18006b6d7  mov     [rax+10h], rsi
0x18006b6db  lea     r8, [rax+10h]; phModule
0x18006b6df  mov     rdx, r14; lpModuleName
0x18006b6e2  lea     ecx, [rsi+6]; dwFlags
0x18006b6e5  call    cs:__imp_GetModuleHandleExW
0x18006b6eb  test    eax, eax
0x18006b6ed  jnz     short loc_18006B709
0x18006b6ef  mov     rcx, [rsp+0D8h]; this
0x18006b6f7  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006b6fe  mov     edx, 303h; void *
0x18006b703  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006b709  cmp     cs:?s_messageWindowClassAtom@@3GA, si; ushort s_messageWindowClassAtom
0x18006b710  lea     rbp, aWebruntimediag_0; "WebRuntimeDiagnostics Message Window Cl"...
0x18006b717  jnz     loc_18006B7A1
0x18006b71d  xor     edx, edx; Val
0x18006b71f  lea     rcx, [rsp+0D8h+var_78]; void *
0x18006b724  lea     r8d, [rdx+50h]; Size
0x18006b728  call    memset_0
0x18006b72d  mov     rax, [rsp+0D8h+arg_8]
0x18006b735  lea     rcx, [rsp+0D8h+var_78]; WNDCLASSEXW *
0x18006b73a  mov     [rsp+0D8h+var_78.hInstance], rax
0x18006b73f  mov     [rsp+0D8h+var_78.cbSize], 50h ; 'P'
0x18006b747  mov     [rsp+0D8h+var_78.lpfnWndProc], r14
0x18006b74c  mov     [rsp+0D8h+var_78.lpszClassName], rbp
0x18006b754  call    cs:__imp_RegisterClassExW
0x18006b75a  test    ax, ax
0x18006b75d  jnz     short loc_18006B7A1
0x18006b75f  call    cs:__imp_GetLastError
0x18006b765  mov     ecx, eax
0x18006b767  test    eax, eax
0x18006b769  jle     short loc_18006B774
0x18006b76b  movzx   ecx, ax
0x18006b76e  or      ecx, 80070000h
0x18006b774  cmp     ecx, 80070582h
0x18006b77a  jz      short loc_18006B7A1
0x18006b77c  mov     cs:?s_messageWindowClassAtom@@3GA, si; ushort s_messageWindowClassAtom
0x18006b783  test    ecx, ecx
0x18006b785  jz      short loc_18006B7A1
0x18006b787  mov     rcx, [rsp+0D8h]; this
0x18006b78f  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006b796  mov     edx, 31Ah; void *
0x18006b79b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006b7a1  mov     rax, [rsp+0D8h+arg_8]
0x18006b7a9  xor     r9d, r9d; dwStyle
0x18006b7ac  mov     [rsp+0D8h+lpParam], rbx; lpParam
0x18006b7b1  xor     r8d, r8d; lpWindowName
0x18006b7b4  mov     [rsp+0D8h+hInstance], rax; hInstance
0x18006b7b9  mov     rdx, rbp; lpClassName
0x18006b7bc  mov     [rsp+0D8h+hMenu], rsi; hMenu
0x18006b7c1  xor     ecx, ecx; dwExStyle
0x18006b7c3  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18006b7cc  mov     [rsp+0D8h+nHeight], esi; nHeight
0x18006b7d0  mov     [rsp+0D8h+nWidth], esi; nWidth
0x18006b7d4  mov     [rsp+0D8h+Y], esi; Y
0x18006b7d8  mov     [rsp+0D8h+X], esi; X
0x18006b7dc  call    cs:__imp_CreateWindowExW
0x18006b7e2  mov     [rbx+40h], rax
0x18006b7e6  test    rax, rax
0x18006b7e9  jnz     short loc_18006B805
0x18006b7eb  mov     rcx, [rsp+0D8h]; this
0x18006b7f3  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006b7fa  mov     edx, 32Ch; void *
0x18006b7ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006b805  add     rsp, 0B8h
0x18006b80c  pop     r14
0x18006b80e  pop     rsi
0x18006b80f  pop     rbp
0x18006b810  pop     rbx
0x18006b811  retn
```
