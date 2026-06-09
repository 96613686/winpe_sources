# DwTerminalDlg

- ea: `0x18000d3b0`
- end: `0x18000d66d`
- name: `DwTerminalDlg`
- size: `701`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, HWND, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000d3b0`
- `0x18002a674`
- `0x18002b960`
- `0x18002bfc8`
- `0x18003bea0`
- `0x18003c860`
- `0x180048b6c`
- `0x1800490c4`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d57d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d57d`
- `RASAPI32!GetPbkAndEntryName` at `0x18000d496`
- `RASAPI32!GetPbkAndEntryName` at `0x18000d496`
- `RASAPI32!ClosePhonebookFile` at `0x18000d618`
- `RASAPI32!ClosePhonebookFile` at `0x18000d618`
- `RASAPI32!WritePhonebookFile` at `0x18000d5fe`
- `RASAPI32!WritePhonebookFile` at `0x18000d5fe`
- `rtutils!TracePrintfExA` at `0x18000d44c`
- `rtutils!TracePrintfExA` at `0x18000d4f9`
- `rtutils!TracePrintfExA` at `0x18000d526`
- `rtutils!TracePrintfExA` at `0x18000d55c`
- `rtutils!TracePrintfExA` at `0x18000d5c3`
- `rtutils!TracePrintfExA` at `0x18000d63b`
- `rtutils!TracePrintfExA` at `0x18000d44c`
- `rtutils!TracePrintfExA` at `0x18000d4f9`
- `rtutils!TracePrintfExA` at `0x18000d526`
- `rtutils!TracePrintfExA` at `0x18000d55c`
- `rtutils!TracePrintfExA` at `0x18000d5c3`
- `rtutils!TracePrintfExA` at `0x18000d63b`

## pseudocode

```c
__int64 __fastcall DwTerminalDlg(__int64 a1, __int64 a2, __int64 a3, HWND a4, __int64 a5)
{
  __int64 result; // rax
  unsigned int Ras; // ebx
  unsigned int PbkAndEntryName; // eax
  __int64 v12; // rsi
  const WCHAR *v13; // rax
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  DWORD v16; // r8d
  unsigned int v17; // eax
  int v18; // [rsp+20h] [rbp-71h]
  __int64 v19; // [rsp+40h] [rbp-51h] BYREF
  __int128 v20; // [rsp+48h] [rbp-49h] BYREF
  __int128 v21; // [rsp+58h] [rbp-39h]
  __int128 v22; // [rsp+68h] [rbp-29h]
  __int64 v23; // [rsp+78h] [rbp-19h]
  WCHAR String1[20]; // [rsp+80h] [rbp-11h] BYREF

  v23 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  RasDlgInit();
  result = CheckPhonebookAndEntryWParams(a1, a2, 0);
  if ( (_DWORD)result )
    return result;
  if ( (unsigned __int64)(a5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( !a3 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Invalid RASDIALPARAMS.");
      return 610;
    }
    v20 = 0;
    v23 = 0;
    v21 = 0;
    v22 = 0;
    Ras = LoadRas();
    if ( !Ras )
    {
      PbkAndEntryName = GetPbkAndEntryName(a1, a2, 0, &v20, &v19);
      Ras = PbkAndEntryName;
      if ( !v19 || PbkAndEntryName )
      {
        Ras = 623;
        goto LABEL_31;
      }
      v12 = *(_QWORD *)(v19 + 16);
      if ( v12 )
      {
        String1[0] = 0;
        v18 = 471;
        if ( !(unsigned int)TerminalDlg(v12, a3, a4, a5) )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, Ras + 12, "TerminalDlg==FALSE");
          Ras = 16389;
          goto LABEL_31;
        }
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "pszIpAddress=0x%08x(%ls)", (unsigned int)String1, String1);
          if ( g_dwTraceId != -1 )
          {
            v13 = &WideCharStr;
            if ( *(_QWORD *)(v12 + 280) )
              v13 = *(const WCHAR **)(v12 + 280);
            v18 = (int)v13;
            TracePrintfExA(g_dwTraceId, 0xCu, "pEntry->pszIpAddress=0x%08x(%ls)");
          }
        }
        if ( !String1[0] )
          goto LABEL_31;
        v14 = *(const WCHAR **)(v12 + 280);
        if ( v14 )
        {
          if ( !lstrcmpW(String1, v14) )
            goto LABEL_31;
        }
        Free0(*(_QWORD *)(v12 + 280));
        v15 = StrDup(String1);
        *(_QWORD *)(v12 + 280) = v15;
        if ( v15 )
        {
          *(_DWORD *)(v12 + 532) = 1;
          v17 = WritePhonebookFile(&v20, 0);
          Ras = v17;
          if ( !v17 )
            goto LABEL_31;
          v16 = v17;
        }
        else
        {
          Ras = 8;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "Allocating memory for IPaddress failed");
          v16 = 8;
        }
        ErrorDlgUtil(a4, 0x158u, v16, v18, 0x169u, 0xFAu);
      }
    }
LABEL_31:
    ClosePhonebookFile(&v20);
    return Ras;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "Invalid hRasconn.");
  return 6;
}

```

## disassembly

```asm
0x18000d3b0  mov     [rsp-8+arg_10], rbx
0x18000d3b5  push    rbp
0x18000d3b6  push    rsi
0x18000d3b7  push    rdi
0x18000d3b8  push    r12
0x18000d3ba  push    r13
0x18000d3bc  push    r14
0x18000d3be  push    r15
0x18000d3c0  lea     rbp, [rsp-1Fh]
0x18000d3c5  sub     rsp, 0B0h
0x18000d3cc  mov     rax, cs:__security_cookie
0x18000d3d3  xor     rax, rsp
0x18000d3d6  mov     [rbp+4Fh+var_38], rax
0x18000d3da  xorps   xmm0, xmm0
0x18000d3dd  xor     eax, eax
0x18000d3df  xor     r13d, r13d
0x18000d3e2  mov     [rbp+4Fh+var_68], rax
0x18000d3e6  movups  [rbp+4Fh+var_98], xmm0
0x18000d3ea  mov     [rbp+4Fh+var_A0], r13
0x18000d3ee  mov     r15, r9
0x18000d3f1  movups  [rbp+4Fh+var_88], xmm0
0x18000d3f5  mov     r14, r8
0x18000d3f8  mov     r12, rdx
0x18000d3fb  movups  [rbp+4Fh+var_78], xmm0
0x18000d3ff  mov     rsi, rcx
0x18000d402  call    RasDlgInit
0x18000d407  xor     r8d, r8d
0x18000d40a  mov     rdx, r12
0x18000d40d  mov     rcx, rsi
0x18000d410  call    CheckPhonebookAndEntryWParams
0x18000d415  test    eax, eax
0x18000d417  jnz     loc_18000D646
0x18000d41d  mov     rdi, [rbp+4Fh+arg_20]
0x18000d421  lea     rax, [rdi-1]
0x18000d425  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d429  ja      loc_18000D622
0x18000d42f  test    r14, r14
0x18000d432  jnz     short loc_18000D45C
0x18000d434  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d43a  or      edi, 0FFFFFFFFh
0x18000d43d  cmp     ecx, edi
0x18000d43f  jz      short loc_18000D452
0x18000d441  lea     r8, aInvalidRasdial; "Invalid RASDIALPARAMS."
0x18000d448  lea     edx, [r13+0Ch]; dwFlags
0x18000d44c  call    cs:__imp_TracePrintfExA
0x18000d452  mov     eax, 262h
0x18000d457  jmp     loc_18000D646
0x18000d45c  xorps   xmm0, xmm0
0x18000d45f  xor     eax, eax
0x18000d461  movups  [rbp+4Fh+var_98], xmm0
0x18000d465  mov     [rbp+4Fh+var_68], rax
0x18000d469  movups  [rbp+4Fh+var_88], xmm0
0x18000d46d  movups  [rbp+4Fh+var_78], xmm0
0x18000d471  call    LoadRas
0x18000d476  mov     ebx, eax
0x18000d478  test    eax, eax
0x18000d47a  jnz     loc_18000D614
0x18000d480  lea     rax, [rbp+4Fh+var_A0]
0x18000d484  xor     r8d, r8d
0x18000d487  lea     r9, [rbp+4Fh+var_98]
0x18000d48b  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18000d490  mov     rdx, r12
0x18000d493  mov     rcx, rsi
0x18000d496  call    cs:__imp_GetPbkAndEntryName
0x18000d49c  mov     rsi, [rbp+4Fh+var_A0]
0x18000d4a0  mov     ebx, eax
0x18000d4a2  test    rsi, rsi
0x18000d4a5  jz      loc_18000D60F
0x18000d4ab  test    eax, eax
0x18000d4ad  jnz     loc_18000D60F
0x18000d4b3  mov     rsi, [rsi+10h]
0x18000d4b7  test    rsi, rsi
0x18000d4ba  jz      loc_18000D614
0x18000d4c0  mov     r9, rdi
0x18000d4c3  mov     [rbp+4Fh+String1], r13w
0x18000d4c8  mov     r8, r15
0x18000d4cb  mov     [rsp+0E0h+var_C0], 1D7h
0x18000d4d3  mov     rdx, r14
0x18000d4d6  mov     rcx, rsi
0x18000d4d9  call    TerminalDlg
0x18000d4de  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d4e4  or      edi, 0FFFFFFFFh
0x18000d4e7  test    eax, eax
0x18000d4e9  jnz     short loc_18000D509
0x18000d4eb  cmp     ecx, edi
0x18000d4ed  jz      short loc_18000D4FF
0x18000d4ef  lea     r8, aTerminaldlgFal; "TerminalDlg==FALSE"
0x18000d4f6  lea     edx, [rbx+0Ch]; dwFlags
0x18000d4f9  call    cs:__imp_TracePrintfExA
0x18000d4ff  mov     ebx, 4005h
0x18000d504  jmp     loc_18000D614
0x18000d509  cmp     ecx, edi
0x18000d50b  jz      short loc_18000D562
0x18000d50d  lea     rax, [rbp+4Fh+String1]
0x18000d511  mov     edx, 0Ch; dwFlags
0x18000d516  lea     r9, [rbp+4Fh+String1]
0x18000d51a  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18000d51f  lea     r8, aPszipaddress0x; "pszIpAddress=0x%08x(%ls)"
0x18000d526  call    cs:__imp_TracePrintfExA
0x18000d52c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d532  cmp     ecx, edi
0x18000d534  jz      short loc_18000D562
0x18000d536  mov     r9, [rsi+118h]
0x18000d53d  lea     rax, WideCharStr
0x18000d544  test    r9, r9
0x18000d547  lea     r8, aPentryPszipadd; "pEntry->pszIpAddress=0x%08x(%ls)"
0x18000d54e  mov     edx, 0Ch; dwFlags
0x18000d553  cmovnz  rax, r9
0x18000d557  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18000d55c  call    cs:__imp_TracePrintfExA
0x18000d562  cmp     [rbp+4Fh+String1], r13w
0x18000d567  jz      loc_18000D614
0x18000d56d  mov     rdx, [rsi+118h]; lpString2
0x18000d574  test    rdx, rdx
0x18000d577  jz      short loc_18000D58B
0x18000d579  lea     rcx, [rbp+4Fh+String1]; lpString1
0x18000d57d  call    cs:__imp_lstrcmpW
0x18000d583  test    eax, eax
0x18000d585  jz      loc_18000D614
0x18000d58b  mov     rcx, [rsi+118h]
0x18000d592  call    Free0
0x18000d597  lea     rcx, [rbp+4Fh+String1]; pszSrc
0x18000d59b  call    StrDup
0x18000d5a0  mov     [rsi+118h], rax
0x18000d5a7  test    rax, rax
0x18000d5aa  jnz     short loc_18000D5EE
0x18000d5ac  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d5b2  lea     ebx, [rax+8]
0x18000d5b5  cmp     ecx, edi
0x18000d5b7  jz      short loc_18000D5C9
0x18000d5b9  lea     r8, aAllocatingMemo; "Allocating memory for IPaddress failed"
0x18000d5c0  lea     edx, [rax+0Ch]; dwFlags
0x18000d5c3  call    cs:__imp_TracePrintfExA
0x18000d5c9  mov     r8d, ebx; dwMessageId
0x18000d5cc  mov     [rsp+0E0h+var_B0], 0FAh; UINT
0x18000d5d4  xor     r9d, r9d
0x18000d5d7  mov     edx, 158h; uID
0x18000d5dc  mov     [rsp+0E0h+var_B8], 169h; UINT
0x18000d5e4  mov     rcx, r15; hWnd
0x18000d5e7  call    ErrorDlgUtil
0x18000d5ec  jmp     short loc_18000D614
0x18000d5ee  xor     edx, edx
0x18000d5f0  mov     dword ptr [rsi+214h], 1
0x18000d5fa  lea     rcx, [rbp+4Fh+var_98]
0x18000d5fe  call    cs:__imp_WritePhonebookFile
0x18000d604  mov     ebx, eax
0x18000d606  test    eax, eax
0x18000d608  jz      short loc_18000D614
0x18000d60a  mov     r8d, eax
0x18000d60d  jmp     short loc_18000D5CC
0x18000d60f  mov     ebx, 26Fh
0x18000d614  lea     rcx, [rbp+4Fh+var_98]
0x18000d618  call    cs:__imp_ClosePhonebookFile
0x18000d61e  mov     eax, ebx
0x18000d620  jmp     short loc_18000D646
0x18000d622  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d628  or      edi, 0FFFFFFFFh
0x18000d62b  cmp     ecx, edi
0x18000d62d  jz      short loc_18000D641
0x18000d62f  lea     r8, aInvalidHrascon; "Invalid hRasconn."
0x18000d636  mov     edx, 0Ch; dwFlags
0x18000d63b  call    cs:__imp_TracePrintfExA
0x18000d641  mov     eax, 6
0x18000d646  mov     rcx, [rbp+4Fh+var_38]
0x18000d64a  xor     rcx, rsp; StackCookie
0x18000d64d  call    __security_check_cookie
0x18000d652  mov     rbx, [rsp+0E0h+arg_10]
0x18000d65a  add     rsp, 0B0h
0x18000d661  pop     r15
0x18000d663  pop     r14
0x18000d665  pop     r13
0x18000d667  pop     r12
0x18000d669  pop     rdi
0x18000d66a  pop     rsi
0x18000d66b  pop     rbp
0x18000d66c  retn
```
