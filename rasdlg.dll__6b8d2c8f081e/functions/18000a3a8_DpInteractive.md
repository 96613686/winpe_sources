# DpInteractive

- ea: `0x18000a3a8`
- end: `0x18000a5fa`
- name: `DpInteractive`
- size: `594`
- prototype: `_BOOL8 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800097c8`

## callees

- `0x18000a3a8`
- `0x18002a674`
- `0x18003bea0`
- `0x18003c860`
- `0x1800442bc`
- `0x180048b6c`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a561`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a561`
- `RASAPI32!WritePhonebookFile` at `0x18000a5a3`
- `RASAPI32!WritePhonebookFile` at `0x18000a5a3`
- `rtutils!TracePrintfExA` at `0x18000a3eb`
- `rtutils!TracePrintfExA` at `0x18000a4d5`
- `rtutils!TracePrintfExA` at `0x18000a508`
- `rtutils!TracePrintfExA` at `0x18000a53f`
- `rtutils!TracePrintfExA` at `0x18000a3eb`
- `rtutils!TracePrintfExA` at `0x18000a4d5`
- `rtutils!TracePrintfExA` at `0x18000a508`
- `rtutils!TracePrintfExA` at `0x18000a53f`

## pseudocode

```c
_BOOL8 __fastcall DpInteractive(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdi
  int v9; // eax
  DWORD v10; // eax
  DWORD v11; // edi
  const WCHAR *v13; // rax
  const WCHAR *v14; // rdx
  DWORD v15; // eax
  int v16; // [rsp+20h] [rbp-78h]
  int v17; // [rsp+20h] [rbp-78h]
  WCHAR String1[20]; // [rsp+40h] [rbp-58h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DpInteractive");
  *a3 = 0;
  v6 = *(_QWORD *)(a1 + 8);
  v7 = *(_DWORD *)(a2 + 68);
  v8 = *(_QWORD *)(v6 + 440);
  String1[0] = 0;
  if ( v7 == 437 )
    v9 = 472;
  else
    v9 = 471 - (v7 != 436);
  if ( *(_DWORD *)(v8 + 232) == 1 )
  {
    if ( !*(_QWORD *)(v6 + 376) )
    {
      v10 = DwCustomTerminalDlg(**(_QWORD **)(v6 + 32), *(_QWORD *)(a1 + 56), v8, *(_QWORD *)(a1 + 16), v6 + 488);
      v11 = v10;
      if ( v10 )
        ErrorDlgUtil(*(HWND *)(a1 + 16), 0x154u, v10, v17, 0x169u, 0xFAu);
      return v11 == 0;
    }
    goto LABEL_16;
  }
  if ( *(_QWORD *)(v6 + 376)
    || (v16 = v9, (unsigned int)TerminalDlg(*(_QWORD *)(v6 + 440), v6 + 488, *(_QWORD *)(a1 + 16), *(_QWORD *)(a2 + 88))) )
  {
LABEL_16:
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "pszIpAddress=0x%08x(%ls)", (unsigned int)String1, String1);
      if ( g_dwTraceId != -1 )
      {
        v13 = &WideCharStr;
        if ( *(_QWORD *)(v8 + 280) )
          v13 = *(const WCHAR **)(v8 + 280);
        v16 = (int)v13;
        TracePrintfExA(g_dwTraceId, 0xCu, "pEntry->pszIpAddress=0x%08x(%ls)");
      }
    }
    if ( String1[0] )
    {
      v14 = *(const WCHAR **)(v8 + 280);
      if ( !v14 || lstrcmpW(String1, v14) )
      {
        Free0(*(_QWORD *)(v8 + 280));
        *(_QWORD *)(v8 + 280) = StrDup(String1);
        *(_DWORD *)(v8 + 532) = 1;
        *a3 = 1;
        v15 = WritePhonebookFile(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 32LL), 0);
        if ( v15 )
          ErrorDlgUtil(*(HWND *)(a1 + 16), 0x158u, v15, v16, 0x169u, 0xFAu);
      }
    }
    *(_DWORD *)(a2 + 68) = 0;
    return 1;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "TerminalDlg==FALSE");
  return 0;
}

```

## disassembly

```asm
0x18000a3a8  mov     [rsp+arg_18], rbx
0x18000a3ad  push    rbp
0x18000a3ae  push    rsi
0x18000a3af  push    rdi
0x18000a3b0  push    r14
0x18000a3b2  push    r15
0x18000a3b4  sub     rsp, 70h
0x18000a3b8  mov     rax, cs:__security_cookie
0x18000a3bf  xor     rax, rsp
0x18000a3c2  mov     [rsp+98h+var_30], rax
0x18000a3c7  mov     rbx, rcx
0x18000a3ca  or      r15d, 0FFFFFFFFh
0x18000a3ce  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a3d4  mov     r14, r8
0x18000a3d7  mov     rsi, rdx
0x18000a3da  cmp     ecx, r15d
0x18000a3dd  jz      short loc_18000A3F1
0x18000a3df  lea     r8, aDpinteractive; "DpInteractive"
0x18000a3e6  mov     edx, 0Ch; dwFlags
0x18000a3eb  call    cs:__imp_TracePrintfExA
0x18000a3f1  xor     ebp, ebp
0x18000a3f3  mov     [r14], ebp
0x18000a3f6  mov     rcx, [rbx+8]
0x18000a3fa  mov     eax, [rsi+44h]
0x18000a3fd  mov     rdi, [rcx+1B8h]
0x18000a404  mov     [rsp+98h+String1], bp
0x18000a409  cmp     eax, 1B5h
0x18000a40e  jnz     short loc_18000A417
0x18000a410  mov     eax, 1D8h
0x18000a415  jmp     short loc_18000A425
0x18000a417  sub     eax, 1B4h
0x18000a41c  neg     eax
0x18000a41e  sbb     eax, eax
0x18000a420  add     eax, 1D7h
0x18000a425  cmp     dword ptr [rdi+0E8h], 1
0x18000a42c  jnz     short loc_18000A494
0x18000a42e  cmp     [rcx+178h], rbp
0x18000a435  jnz     loc_18000A4E2
0x18000a43b  mov     r9, [rbx+10h]
0x18000a43f  lea     rax, [rcx+1E8h]
0x18000a446  mov     rcx, [rcx+20h]
0x18000a44a  mov     r8, rdi
0x18000a44d  mov     rdx, [rbx+38h]
0x18000a451  mov     qword ptr [rsp+98h+var_78], rax; int
0x18000a456  mov     rcx, [rcx]
0x18000a459  call    DwCustomTerminalDlg
0x18000a45e  mov     edi, eax
0x18000a460  test    eax, eax
0x18000a462  jz      short loc_18000A488
0x18000a464  mov     rcx, [rbx+10h]; hWnd
0x18000a468  xor     r9d, r9d
0x18000a46b  mov     [rsp+98h+var_68], 0FAh; UINT
0x18000a473  mov     r8d, eax; dwMessageId
0x18000a476  mov     edx, 154h; uID
0x18000a47b  mov     [rsp+98h+var_70], 169h; UINT
0x18000a483  call    ErrorDlgUtil
0x18000a488  test    edi, edi
0x18000a48a  mov     eax, ebp
0x18000a48c  setz    al
0x18000a48f  jmp     loc_18000A5D9
0x18000a494  cmp     [rcx+178h], rbp
0x18000a49b  jnz     short loc_18000A4E2
0x18000a49d  mov     r9, [rsi+58h]
0x18000a4a1  lea     rdx, [rcx+1E8h]
0x18000a4a8  mov     rcx, [rcx+1B8h]
0x18000a4af  mov     r8, [rbx+10h]
0x18000a4b3  mov     [rsp+98h+var_78], eax
0x18000a4b7  call    TerminalDlg
0x18000a4bc  test    eax, eax
0x18000a4be  jnz     short loc_18000A4E2
0x18000a4c0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a4c6  cmp     ecx, r15d
0x18000a4c9  jz      short loc_18000A4DB
0x18000a4cb  lea     r8, aTerminaldlgFal; "TerminalDlg==FALSE"
0x18000a4d2  lea     edx, [rax+0Ch]; dwFlags
0x18000a4d5  call    cs:__imp_TracePrintfExA
0x18000a4db  xor     eax, eax
0x18000a4dd  jmp     loc_18000A5D9
0x18000a4e2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a4e8  cmp     ecx, r15d
0x18000a4eb  jz      short loc_18000A545
0x18000a4ed  lea     rax, [rsp+98h+String1]
0x18000a4f2  mov     edx, 0Ch; dwFlags
0x18000a4f7  lea     r9, [rsp+98h+String1]
0x18000a4fc  mov     qword ptr [rsp+98h+var_78], rax
0x18000a501  lea     r8, aPszipaddress0x; "pszIpAddress=0x%08x(%ls)"
0x18000a508  call    cs:__imp_TracePrintfExA
0x18000a50e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a514  cmp     ecx, r15d
0x18000a517  jz      short loc_18000A545
0x18000a519  mov     r9, [rdi+118h]
0x18000a520  lea     rax, WideCharStr
0x18000a527  test    r9, r9
0x18000a52a  lea     r8, aPentryPszipadd; "pEntry->pszIpAddress=0x%08x(%ls)"
0x18000a531  mov     edx, 0Ch; dwFlags
0x18000a536  cmovnz  rax, r9
0x18000a53a  mov     qword ptr [rsp+98h+var_78], rax; int
0x18000a53f  call    cs:__imp_TracePrintfExA
0x18000a545  cmp     [rsp+98h+String1], bp
0x18000a54a  jz      loc_18000A5D1
0x18000a550  mov     rdx, [rdi+118h]; lpString2
0x18000a557  test    rdx, rdx
0x18000a55a  jz      short loc_18000A56B
0x18000a55c  lea     rcx, [rsp+98h+String1]; lpString1
0x18000a561  call    cs:__imp_lstrcmpW
0x18000a567  test    eax, eax
0x18000a569  jz      short loc_18000A5D1
0x18000a56b  mov     rcx, [rdi+118h]
0x18000a572  call    Free0
0x18000a577  lea     rcx, [rsp+98h+String1]; pszSrc
0x18000a57c  call    StrDup
0x18000a581  mov     [rdi+118h], rax
0x18000a588  xor     edx, edx
0x18000a58a  mov     dword ptr [rdi+214h], 1
0x18000a594  mov     dword ptr [r14], 1
0x18000a59b  mov     rcx, [rbx+8]
0x18000a59f  mov     rcx, [rcx+20h]
0x18000a5a3  call    cs:__imp_WritePhonebookFile
0x18000a5a9  test    eax, eax
0x18000a5ab  jz      short loc_18000A5D1
0x18000a5ad  mov     rcx, [rbx+10h]; hWnd
0x18000a5b1  xor     r9d, r9d
0x18000a5b4  mov     [rsp+98h+var_68], 0FAh; UINT
0x18000a5bc  mov     r8d, eax; dwMessageId
0x18000a5bf  mov     edx, 158h; uID
0x18000a5c4  mov     [rsp+98h+var_70], 169h; UINT
0x18000a5cc  call    ErrorDlgUtil
0x18000a5d1  mov     [rsi+44h], ebp
0x18000a5d4  mov     eax, 1
0x18000a5d9  mov     rcx, [rsp+98h+var_30]
0x18000a5de  xor     rcx, rsp; StackCookie
0x18000a5e1  call    __security_check_cookie
0x18000a5e6  mov     rbx, [rsp+98h+arg_18]
0x18000a5ee  add     rsp, 70h
0x18000a5f2  pop     r15
0x18000a5f4  pop     r14
0x18000a5f6  pop     rdi
0x18000a5f7  pop     rsi
0x18000a5f8  pop     rbp
0x18000a5f9  retn
```
