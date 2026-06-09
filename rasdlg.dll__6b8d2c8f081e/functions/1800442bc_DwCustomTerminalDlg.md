# DwCustomTerminalDlg

- ea: `0x1800442bc`
- end: `0x1800444d4`
- name: `DwCustomTerminalDlg`
- size: `536`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a3a8`

## callees

- `0x1800442bc`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800443e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800443e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180044386`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180044386`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800443d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800443d3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800444a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800444a3`
- `rtutils!TracePrintfExA` at `0x180044332`
- `rtutils!TracePrintfExA` at `0x180044371`
- `rtutils!TracePrintfExA` at `0x1800443be`
- `rtutils!TracePrintfExA` at `0x18004449a`
- `rtutils!TracePrintfExA` at `0x180044332`
- `rtutils!TracePrintfExA` at `0x180044371`
- `rtutils!TracePrintfExA` at `0x1800443be`
- `rtutils!TracePrintfExA` at `0x18004449a`
- `rasman!RasSetCommSettings` at `0x180044404`
- `rasman!RasGetCustomScriptDll` at `0x180044347`
- `rasman!RasGetCustomScriptDll` at `0x180044347`

## string_xrefs

- `0x180044365`: `DwCustomTerminalDlg: RasGetCustomScriptDll returned 0x%x`

## pseudocode

```c
__int64 __fastcall DwCustomTerminalDlg(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // rsi
  DWORD v9; // ebx
  DWORD CustomScriptDll; // eax
  HMODULE Library; // rax
  HMODULE v12; // rdi
  DWORD LastError; // eax
  FARPROC ProcAddress; // r10
  DWORD v15; // eax
  DWORD v16; // eax
  _QWORD v18[2]; // [rsp+60h] [rbp-168h] BYREF
  CHAR LibFileName[272]; // [rsp+70h] [rbp-158h] BYREF

  memset(v18, 0, 12);
  if ( a2 )
  {
    v8 = ((__int64 (__fastcall *)(__int64))g_pRasGetHport)(a2);
    if ( v8 == -1 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomTermianlDlg: RasGetHport retured INVALID_HPORT");
      return 601;
    }
    CustomScriptDll = RasGetCustomScriptDll(LibFileName);
    v9 = CustomScriptDll;
    if ( CustomScriptDll )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomTerminalDlg: RasGetCustomScriptDll returned 0x%x", CustomScriptDll);
      return v9;
    }
    Library = LoadLibraryExA(LibFileName, 0, 0);
    v12 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomTerminalDlg: couldn't load %s. 0x%x", LibFileName, LastError);
      return v9;
    }
    ProcAddress = GetProcAddress(Library, "RasCustomScriptExecute");
    if ( !ProcAddress )
    {
      v15 = GetLastError();
      v9 = v15;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomTerminalDlg: GetprocAddress failed 0x%x", v15);
LABEL_18:
      FreeLibrary(v12);
      return v9;
    }
    *(_QWORD *)((char *)v18 + 4) = RasSetCommSettings;
    LODWORD(v18[0]) = 12;
    if ( a3 )
    {
      v16 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *))ProcAddress)(
              v8,
              a1,
              *(_QWORD *)(a3 + 8),
              g_pRasGetBuffer,
              g_pRasFreeBuffer,
              g_pRasPortSend,
              g_pRasPortReceive,
              g_pRasPortReceiveEx,
              a4,
              a5,
              v18);
      v9 = v16;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomTerminalDlg: fnCustomScript returned 0x%x", v16);
      goto LABEL_18;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x1800442bc  push    rbx
0x1800442be  push    rbp
0x1800442bf  push    rsi
0x1800442c0  push    rdi
0x1800442c1  push    r12
0x1800442c3  push    r14
0x1800442c5  push    r15
0x1800442c7  sub     rsp, 190h
0x1800442ce  mov     rax, cs:__security_cookie
0x1800442d5  xor     rax, rsp
0x1800442d8  mov     [rsp+1C8h+var_48], rax
0x1800442e0  mov     r12, [rsp+1C8h+arg_20]
0x1800442e8  xor     eax, eax
0x1800442ea  mov     [rsp+1C8h+var_168], rax
0x1800442ef  mov     r15, r9
0x1800442f2  mov     [rsp+1C8h+var_160], eax
0x1800442f6  mov     rbp, r8
0x1800442f9  mov     r14, rcx
0x1800442fc  test    rdx, rdx
0x1800442ff  jz      loc_1800444AD
0x180044305  mov     rax, cs:g_pRasGetHport
0x18004430c  mov     rcx, rdx
0x18004430f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044314  mov     rsi, rax
0x180044317  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004431b  jnz     short loc_180044342
0x18004431d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180044323  cmp     ecx, 0FFFFFFFFh
0x180044326  jz      short loc_180044338
0x180044328  lea     r8, aDwcustomtermia; "DwCustomTermianlDlg: RasGetHport reture"...
0x18004432f  lea     edx, [rax+0Dh]; dwFlags
0x180044332  call    cs:__imp_TracePrintfExA
0x180044338  mov     ebx, 259h
0x18004433d  jmp     loc_1800444A9
0x180044342  lea     rcx, [rsp+1C8h+LibFileName]
0x180044347  call    cs:__imp_RasGetCustomScriptDll
0x18004434d  mov     ebx, eax
0x18004434f  test    eax, eax
0x180044351  jz      short loc_18004437C
0x180044353  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180044359  cmp     ecx, 0FFFFFFFFh
0x18004435c  jz      loc_1800444A9
0x180044362  mov     r9d, eax
0x180044365  lea     r8, aDwcustomtermin_1; "DwCustomTerminalDlg: RasGetCustomScript"...
0x18004436c  mov     edx, 0Ch; dwFlags
0x180044371  call    cs:__imp_TracePrintfExA
0x180044377  jmp     loc_1800444A9
0x18004437c  xor     r8d, r8d; dwFlags
0x18004437f  lea     rcx, [rsp+1C8h+LibFileName]; lpLibFileName
0x180044384  xor     edx, edx; hFile
0x180044386  call    cs:__imp_LoadLibraryExA
0x18004438c  mov     rdi, rax
0x18004438f  test    rax, rax
0x180044392  jnz     short loc_1800443C9
0x180044394  call    cs:__imp_GetLastError
0x18004439a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800443a0  mov     ebx, eax
0x1800443a2  cmp     ecx, 0FFFFFFFFh
0x1800443a5  jz      loc_1800444A9
0x1800443ab  lea     r9, [rsp+1C8h+LibFileName]
0x1800443b0  mov     dword ptr [rsp+1C8h+var_1A8], eax
0x1800443b4  lea     r8, aDwcustomtermin_0; "DwCustomTerminalDlg: couldn't load %s. "...
0x1800443bb  lea     edx, [rdi+0Ch]; dwFlags
0x1800443be  call    cs:__imp_TracePrintfExA
0x1800443c4  jmp     loc_1800444A9
0x1800443c9  lea     rdx, aRascustomscrip; "RasCustomScriptExecute"
0x1800443d0  mov     rcx, rdi; hModule
0x1800443d3  call    cs:__imp_GetProcAddress
0x1800443d9  mov     r10, rax
0x1800443dc  test    rax, rax
0x1800443df  jnz     short loc_180044404
0x1800443e1  call    cs:__imp_GetLastError
0x1800443e7  mov     ecx, cs:g_dwTraceId
0x1800443ed  mov     ebx, eax
0x1800443ef  cmp     ecx, 0FFFFFFFFh
0x1800443f2  jz      loc_1800444A0
0x1800443f8  lea     r8, aDwcustomtermin_2; "DwCustomTerminalDlg: GetprocAddress fai"...
0x1800443ff  jmp     loc_180044492
0x180044404  mov     rax, cs:__imp_RasSetCommSettings
0x18004440b  mov     [rsp+1C8h+var_168+4], rax
0x180044410  mov     dword ptr [rsp+1C8h+var_168], 0Ch
0x180044418  test    rbp, rbp
0x18004441b  jz      loc_1800444AD
0x180044421  mov     r9, cs:g_pRasGetBuffer
0x180044428  lea     rax, [rsp+1C8h+var_168]
0x18004442d  mov     r8, [rbp+8]
0x180044431  mov     rdx, r14
0x180044434  mov     [rsp+1C8h+var_178], rax
0x180044439  mov     rcx, rsi
0x18004443c  mov     rax, cs:g_pRasPortReceiveEx
0x180044443  mov     [rsp+1C8h+var_180], r12
0x180044448  mov     [rsp+1C8h+var_188], r15
0x18004444d  mov     [rsp+1C8h+var_190], rax
0x180044452  mov     rax, cs:g_pRasPortReceive
0x180044459  mov     [rsp+1C8h+var_198], rax
0x18004445e  mov     rax, cs:g_pRasPortSend
0x180044465  mov     [rsp+1C8h+var_1A0], rax
0x18004446a  mov     rax, cs:g_pRasFreeBuffer
0x180044471  mov     [rsp+1C8h+var_1A8], rax
0x180044476  mov     rax, r10
0x180044479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004447e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180044484  mov     ebx, eax
0x180044486  cmp     ecx, 0FFFFFFFFh
0x180044489  jz      short loc_1800444A0
0x18004448b  lea     r8, aDwcustomtermin; "DwCustomTerminalDlg: fnCustomScript ret"...
0x180044492  mov     r9d, eax
0x180044495  mov     edx, 0Ch; dwFlags
0x18004449a  call    cs:__imp_TracePrintfExA
0x1800444a0  mov     rcx, rdi; hLibModule
0x1800444a3  call    cs:__imp_FreeLibrary
0x1800444a9  mov     eax, ebx
0x1800444ab  jmp     short loc_1800444B2
0x1800444ad  mov     eax, 57h ; 'W'
0x1800444b2  mov     rcx, [rsp+1C8h+var_48]
0x1800444ba  xor     rcx, rsp; StackCookie
0x1800444bd  call    __security_check_cookie
0x1800444c2  add     rsp, 190h
0x1800444c9  pop     r15
0x1800444cb  pop     r14
0x1800444cd  pop     r12
0x1800444cf  pop     rdi
0x1800444d0  pop     rsi
0x1800444d1  pop     rbp
0x1800444d2  pop     rbx
0x1800444d3  retn
```
