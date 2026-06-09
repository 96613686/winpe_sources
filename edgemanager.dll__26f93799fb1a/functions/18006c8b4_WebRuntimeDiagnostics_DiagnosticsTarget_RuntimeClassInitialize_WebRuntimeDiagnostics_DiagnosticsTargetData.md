# WebRuntimeDiagnostics::DiagnosticsTarget::RuntimeClassInitialize(WebRuntimeDiagnostics::DiagnosticsTargetData * &&)

- ea: `0x18006c8b4`
- end: `0x18006c989`
- name: `?RuntimeClassInitialize@DiagnosticsTarget@WebRuntimeDiagnostics@@QEAAJ$$QEAPEAVDiagnosticsTargetData@2@@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002389c`

## callees

- `0x180013540`
- `0x180018b30`
- `0x18006ac3c`
- `0x18006b060`
- `0x18006c8b4`
- `0x180074508`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18006c958`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18006c958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c916`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c916`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::RuntimeClassInitialize(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rcx
  unsigned int *v5; // r9
  __int64 v6; // rsi
  HSTRING *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a2;
  v4 = *(_QWORD *)(a1 + 48);
  v11 = 0;
  *(_QWORD *)(a1 + 48) = v2;
  if ( v4 )
    std::default_delete<WebRuntimeDiagnostics::DiagnosticsTargetData>::operator()(v4, v4);
  std::unique_ptr<WebRuntimeDiagnostics::DiagnosticsTargetData>::~unique_ptr<WebRuntimeDiagnostics::DiagnosticsTargetData>(&v11);
  v6 = *(_QWORD *)(a1 + 48);
  if ( *(_BYTE *)(v6 + 56) )
  {
    WindowsDeleteString(*(HSTRING *)(v6 + 48));
    *(_QWORD *)(v6 + 48) = 0;
    WindowsDeleteString(*(HSTRING *)(v6 + 40));
    *(_QWORD *)(v6 + 40) = 0;
    WebRuntimeDiagnostics::GetDataFromHtmlDocument(*(HWND *)(v6 + 8), (HWND)(v6 + 40), (HSTRING *)(v6 + 48), v7);
  }
  else
  {
    WebRuntimeDiagnosticsUtilities::ParseIDString(
      (WebRuntimeDiagnosticsUtilities *)(v6 + 20),
      (const struct _GUID *)v6,
      (unsigned int *)(v6 + 72),
      v5);
  }
  if ( !InitOnceExecuteOnce(
          &WebRuntimeDiagnostics::DiagnosticsTarget::s_initOnce,
          WebRuntimeDiagnostics::DiagnosticsTarget::InitializeOnce,
          0,
          0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      v8);
  return 0;
}

```

## disassembly

```asm
0x18006c8b4  mov     [rsp+arg_8], rbx
0x18006c8b9  mov     [rsp+arg_10], rsi
0x18006c8be  push    rdi
0x18006c8bf  sub     rsp, 20h
0x18006c8c3  mov     rax, [rdx]
0x18006c8c6  mov     rsi, rcx
0x18006c8c9  mov     rcx, [rcx+30h]
0x18006c8cd  mov     [rsp+28h+arg_0], 0
0x18006c8d6  mov     [rsi+30h], rax
0x18006c8da  test    rcx, rcx
0x18006c8dd  jz      short loc_18006C8E7
0x18006c8df  mov     rdx, rcx
0x18006c8e2  call    ??R?$default_delete@VDiagnosticsTargetData@WebRuntimeDiagnostics@@@std@@QEBAXPEAVDiagnosticsTargetData@WebRuntimeDiagnostics@@@Z; std::default_delete<WebRuntimeDiagnostics::DiagnosticsTargetData>::operator()(WebRuntimeDiagnostics::DiagnosticsTargetData *)
0x18006c8e7  lea     rcx, [rsp+28h+arg_0]
0x18006c8ec  call    ??1?$unique_ptr@VDiagnosticsTargetData@WebRuntimeDiagnostics@@U?$default_delete@VDiagnosticsTargetData@WebRuntimeDiagnostics@@@std@@@std@@QEAA@XZ; std::unique_ptr<WebRuntimeDiagnostics::DiagnosticsTargetData>::~unique_ptr<WebRuntimeDiagnostics::DiagnosticsTargetData>(void)
0x18006c8f1  mov     rsi, [rsi+30h]
0x18006c8f5  cmp     byte ptr [rsi+38h], 0
0x18006c8f9  jz      short loc_18006C934
0x18006c8fb  lea     rdi, [rsi+30h]
0x18006c8ff  mov     rcx, [rdi]; string
0x18006c902  call    cs:__imp_WindowsDeleteString
0x18006c908  mov     qword ptr [rdi], 0
0x18006c90f  lea     rbx, [rsi+28h]
0x18006c913  mov     rcx, [rbx]; string
0x18006c916  call    cs:__imp_WindowsDeleteString
0x18006c91c  mov     qword ptr [rbx], 0
0x18006c923  mov     r8, rdi; HSTRING *
0x18006c926  mov     rcx, [rsi+8]; hWnd
0x18006c92a  mov     rdx, rbx; newString
0x18006c92d  call    ?GetDataFromHtmlDocument@WebRuntimeDiagnostics@@YAXQEAUHWND__@@PEAPEAUHSTRING__@@1@Z; WebRuntimeDiagnostics::GetDataFromHtmlDocument(HWND__ * const,HSTRING__ * *,HSTRING__ * *)
0x18006c932  jmp     short loc_18006C944
0x18006c934  lea     r8, [rsi+48h]; unsigned int *
0x18006c938  mov     rdx, rsi; struct _GUID *
0x18006c93b  lea     rcx, [rsi+14h]; this
0x18006c93f  call    ?ParseIDString@WebRuntimeDiagnosticsUtilities@@YAXAEBU_GUID@@PEAK1@Z; WebRuntimeDiagnosticsUtilities::ParseIDString(_GUID const &,ulong *,ulong *)
0x18006c944  xor     r9d, r9d; Context
0x18006c947  lea     rdx, ?InitializeOnce@DiagnosticsTarget@WebRuntimeDiagnostics@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18006c94e  xor     r8d, r8d; Parameter
0x18006c951  lea     rcx, ?s_initOnce@DiagnosticsTarget@WebRuntimeDiagnostics@@0T_RTL_RUN_ONCE@@A; InitOnce
0x18006c958  call    cs:__imp_InitOnceExecuteOnce
0x18006c95e  test    eax, eax
0x18006c960  jnz     short loc_18006C977
0x18006c962  mov     rcx, [rsp+28h]; this
0x18006c967  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006c96e  lea     edx, [rax+7Bh]; void *
0x18006c971  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006c977  mov     rbx, [rsp+28h+arg_8]
0x18006c97c  xor     eax, eax
0x18006c97e  mov     rsi, [rsp+28h+arg_10]
0x18006c983  add     rsp, 20h
0x18006c987  pop     rdi
0x18006c988  retn
```
