# HrInvokeDiagnostics

- ea: `0x180011540`
- end: `0x1800116dd`
- name: `HrInvokeDiagnostics`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800182bc`

## callees

- `0x180011540`
- `0x18002c364`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011666`
- `rtutils!TracePrintfExA` at `0x180011694`
- `rtutils!TracePrintfExA` at `0x1800116b3`
- `rtutils!TracePrintfExA` at `0x180011694`
- `rtutils!TracePrintfExA` at `0x1800116b3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800115b4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800115b4`
- `SHELL32!ShellExecuteExW` at `0x180011659`
- `SHELL32!ShellExecuteExW` at `0x180011659`

## string_xrefs

- `0x18001162f`: `%systemroot%\system32\rundll32.exe`
- `0x1800115c2`: `rasdlg.dll,RasHandleDiagnostics`

## pseudocode

```c
__int64 __fastcall HrInvokeDiagnostics(HWND a1, const GUID *a2, int a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v11[176]; // [rsp+F0h] [rbp-10h] BYREF

  if ( !a2 )
  {
    v6 = -2147024809;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Invalid connection GUID pointer. hr = %#x", 2147942487LL);
    return v6;
  }
  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(a2, sz, 40);
  v6 = StringCchPrintfWrapW(v11, 83, L"%s %s %u", L"rasdlg.dll,RasHandleDiagnostics", sz, a3);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrInvokeDiagnostics: StringCchPrintfWrap failed with hr = %#x", v6);
    return v6;
  }
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.lpVerb = L"open";
  pExecInfo.hwnd = a1;
  pExecInfo.lpFile = L"%systemroot%\\system32\\rundll32.exe";
  pExecInfo.lpParameters = (LPCWSTR)v11;
  pExecInfo.fMask = 512;
  pExecInfo.nShow = 1;
  if ( ShellExecuteExW(&pExecInfo) )
    goto LABEL_12;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "Failed to launch diagnostics. hr = %#x", v6);
LABEL_12:
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrInvokeDiagnostics returned:hr = %#x", v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180011540  mov     [rsp-8+arg_18], rbx
0x180011545  push    rbp
0x180011546  push    rsi
0x180011547  push    rdi
0x180011548  lea     rbp, [rsp-0B0h]
0x180011550  sub     rsp, 1B0h
0x180011557  mov     rax, cs:__security_cookie
0x18001155e  xor     rax, rsp
0x180011561  mov     [rbp+0C0h+var_20], rax
0x180011568  mov     edi, r8d
0x18001156b  mov     rbx, rdx
0x18001156e  mov     rsi, rcx
0x180011571  test    rdx, rdx
0x180011574  jnz     short loc_180011598
0x180011576  mov     ecx, cs:g_dwTraceId
0x18001157c  or      edi, 0FFFFFFFFh
0x18001157f  mov     ebx, 80070057h
0x180011584  cmp     ecx, edi
0x180011586  jz      loc_1800116B9
0x18001158c  lea     r8, aInvalidConnect; "Invalid connection GUID pointer. hr = %"...
0x180011593  jmp     loc_1800116AB
0x180011598  xor     edx, edx; Val
0x18001159a  lea     rcx, [rbp+0C0h+sz]; void *
0x18001159e  lea     r8d, [rdx+50h]; Size
0x1800115a2  call    memset_0
0x1800115a7  mov     r8d, 28h ; '('; cchMax
0x1800115ad  lea     rdx, [rbp+0C0h+sz]; lpsz
0x1800115b1  mov     rcx, rbx; rguid
0x1800115b4  call    cs:__imp_StringFromGUID2
0x1800115ba  lea     rax, [rbp+0C0h+sz]
0x1800115be  mov     [rsp+1C0h+var_198], edi
0x1800115c2  lea     r9, aRasdlgDllRasha; "rasdlg.dll,RasHandleDiagnostics"
0x1800115c9  mov     [rsp+1C0h+var_1A0], rax
0x1800115ce  lea     r8, aSSU; "%s %s %u"
0x1800115d5  mov     edx, 53h ; 'S'
0x1800115da  lea     rcx, [rbp+0C0h+var_D0]
0x1800115de  call    StringCchPrintfWrapW
0x1800115e3  mov     ebx, eax
0x1800115e5  test    eax, eax
0x1800115e7  jns     short loc_180011606
0x1800115e9  mov     ecx, cs:g_dwTraceId
0x1800115ef  or      edi, 0FFFFFFFFh
0x1800115f2  cmp     ecx, edi
0x1800115f4  jz      loc_1800116B9
0x1800115fa  lea     r8, aHrinvokediagno; "HrInvokeDiagnostics: StringCchPrintfWra"...
0x180011601  jmp     loc_1800116AB
0x180011606  mov     edi, 70h ; 'p'
0x18001160b  lea     rcx, [rsp+1C0h+pExecInfo]; void *
0x180011610  mov     r8d, edi; Size
0x180011613  xor     edx, edx; Val
0x180011615  call    memset_0
0x18001161a  lea     rax, aOpen; "open"
0x180011621  mov     [rsp+1C0h+pExecInfo.cbSize], edi
0x180011625  mov     [rsp+1C0h+pExecInfo.lpVerb], rax
0x18001162a  lea     rcx, [rsp+1C0h+pExecInfo]; pExecInfo
0x18001162f  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\rundll32.exe"
0x180011636  mov     [rsp+1C0h+pExecInfo.hwnd], rsi
0x18001163b  mov     [rsp+1C0h+pExecInfo.lpFile], rax
0x180011640  lea     rax, [rbp+0C0h+var_D0]
0x180011644  mov     [rsp+1C0h+pExecInfo.lpParameters], rax
0x180011649  mov     [rsp+1C0h+pExecInfo.fMask], 200h
0x180011651  mov     [rsp+1C0h+pExecInfo.nShow], 1
0x180011659  call    cs:__imp_ShellExecuteExW
0x18001165f  or      edi, 0FFFFFFFFh
0x180011662  test    eax, eax
0x180011664  jnz     short loc_18001169A
0x180011666  call    cs:__imp_GetLastError
0x18001166c  mov     ebx, eax
0x18001166e  test    eax, eax
0x180011670  jle     short loc_18001167B
0x180011672  movzx   ebx, ax
0x180011675  or      ebx, 80070000h
0x18001167b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011681  cmp     ecx, edi
0x180011683  jz      short loc_1800116B9
0x180011685  mov     r9d, ebx
0x180011688  lea     r8, aFailedToLaunch; "Failed to launch diagnostics. hr = %#x"
0x18001168f  mov     edx, 0Ch; dwFlags
0x180011694  call    cs:__imp_TracePrintfExA
0x18001169a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800116a0  cmp     ecx, edi
0x1800116a2  jz      short loc_1800116B9
0x1800116a4  lea     r8, aHrinvokediagno_0; "HrInvokeDiagnostics returned:hr = %#x"
0x1800116ab  mov     r9d, ebx
0x1800116ae  mov     edx, 0Ch; dwFlags
0x1800116b3  call    cs:__imp_TracePrintfExA
0x1800116b9  mov     eax, ebx
0x1800116bb  mov     rcx, [rbp+0C0h+var_20]
0x1800116c2  xor     rcx, rsp; StackCookie
0x1800116c5  call    __security_check_cookie
0x1800116ca  mov     rbx, [rsp+1C0h+arg_18]
0x1800116d2  add     rsp, 1B0h
0x1800116d9  pop     rdi
0x1800116da  pop     rsi
0x1800116db  pop     rbp
0x1800116dc  retn
```
