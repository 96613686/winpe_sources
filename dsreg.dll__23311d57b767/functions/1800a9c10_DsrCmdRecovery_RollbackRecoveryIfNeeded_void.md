# DsrCmdRecovery::RollbackRecoveryIfNeeded(void)

- ea: `0x1800a9c10`
- end: `0x1800aa23d`
- name: `?RollbackRecoveryIfNeeded@DsrCmdRecovery@@SAJXZ`
- size: `1581`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009b940`

## callees

- `0x1800084f4`
- `0x18000ab70`
- `0x18000bac0`
- `0x18000bd20`
- `0x180012948`
- `0x180012c7c`
- `0x180046ae8`
- `0x180046b3c`
- `0x180049f70`
- `0x1800a9c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a9c85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a9c85`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a9eae`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a9eae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a9edd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a9edd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa21e`

## string_xrefs

- `0x1800a9c56`: `DsrCmdRecovery::RollbackRecoveryIfNeeded`
- `0x1800a9cae`: `DsrCmdRecovery::RollbackRecoveryIfNeeded`
- `0x1800a9cc5`: `DsrCmdRecovery::RollbackRecoveryIfNeeded`
- `0x1800a9cb5`: `%s: CreateEvent failed with error 0x%08x.\n`
- `0x1800a9f9c`: `%s: DsrEndRecovery completed with code 0x%08x.\n`
- `0x1800a9fd2`: `%s: DsrEndRecovery completed with code 0x%08x.\n`
- `0x1800a9fee`: `%s: DsrEndRecovery completed with code 0x%08x.\n`
- `0x1800aa03e`: `%s: Recovery rollback successfully completed.\n`

## pseudocode

```c
__int64 DsrCmdRecovery::RollbackRecoveryIfNeeded(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  unsigned int JoinInfo; // ebx
  _BYTE **CurrentRef; // rax
  const wchar_t *v4; // rsi
  __int64 v5; // rdx
  signed int LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _DWORD *v9; // rcx
  int v10; // r15d
  __int64 v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  const WCHAR *v19; // rbx
  __int64 v20; // rax
  wchar_t *v21; // rcx
  const WCHAR *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  const WCHAR *v29; // rbx
  __int64 v30; // rax
  const WCHAR *v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // rax
  __int64 v35; // rdx
  _QWORD *v36; // rax
  __int64 v37; // rdx
  const WCHAR *v38; // rbx
  __int64 v39; // rax
  const WCHAR *v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rcx
  DWORD v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  DWORD v46; // esi
  signed int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  _QWORD *v52; // rax
  __int64 v53; // rdx
  _QWORD *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  _QWORD *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rcx
  _QWORD *v67; // rax
  __int64 v68; // rdx
  _QWORD *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  _QWORD *v74; // rax
  __int64 v75; // rdx
  _QWORD *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rax
  _BYTE **v79; // rax
  const wchar_t *v80; // rsi
  __int64 v81; // rdx
  __int64 v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rdx
  _QWORD *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  _QWORD *v90; // rax
  __int64 v91; // rdx
  _QWORD *v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rax
  HANDLE hEvent[2]; // [rsp+20h] [rbp-10h] BYREF
  void *Block; // [rsp+60h] [rbp+30h] BYREF
  __int64 v98; // [rsp+68h] [rbp+38h] BYREF

  Block = 0;
  v98 = 0;
  *(_OWORD *)hEvent = 0;
  JoinInfo = DsrGetJoinInfoEx(0xFFFFFFFFLL, &v98, &Block);
  if ( (JoinInfo & 0x80000000) != 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v1, v0);
LABEL_3:
    v4 = L"%s: DsrGetJoinInfoEx failed with error code 0x%08x.\n";
    goto LABEL_81;
  }
  if ( !Block )
  {
    JoinInfo = 1;
    goto LABEL_88;
  }
  hEvent[1] = CreateEventW(0, 1, 0, 0);
  if ( !hEvent[1] )
  {
    LastError = GetLastError();
    JoinInfo = LastError;
    if ( LastError > 0 )
      JoinInfo = (unsigned __int16)LastError | 0x80070000;
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v8, v7);
    v4 = L"%s: CreateEvent failed with error 0x%08x.\n";
LABEL_81:
    if ( **CurrentRef )
    {
      wprintf(v4, L"DsrCmdRecovery::RollbackRecoveryIfNeeded", JoinInfo);
      v90 = (_QWORD *)CmdOptions::GetCurrentRef(v89, v88);
      if ( *(_BYTE *)(*v90 + 12LL) )
      {
        v92 = (_QWORD *)CmdOptions::GetCurrentRef(*v90, v91);
        if ( *(_QWORD *)(*v92 + 184LL) )
        {
          v94 = CmdOptions::GetCurrentRef(*v92, v93);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v94 + 184LL),
            v4,
            L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
            JoinInfo);
        }
      }
    }
    Logger::TraceError(v4, L"DsrCmdRecovery::RollbackRecoveryIfNeeded", JoinInfo);
    goto LABEL_86;
  }
  v9 = Block;
  v10 = 1;
  while ( 1 )
  {
    v11 = (unsigned int)(v9[1] - 1);
    if ( (_DWORD)v11 )
    {
      if ( (_DWORD)v11 == 1 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v11, v5) )
        {
          v22 = &cchOriginalDestLength;
          if ( *((_QWORD *)Block + 2) )
            v22 = (const WCHAR *)*((_QWORD *)Block + 2);
          wprintf(
            L"%s: WORKPLACE recovery information found. Device ID: %s\n",
            L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
            v22);
          v25 = (_QWORD *)CmdOptions::GetCurrentRef(v24, v23);
          if ( *(_BYTE *)(*v25 + 12LL) )
          {
            v27 = (_QWORD *)CmdOptions::GetCurrentRef(*v25, v26);
            if ( *(_QWORD *)(*v27 + 184LL) )
            {
              v29 = &cchOriginalDestLength;
              if ( *((_QWORD *)Block + 2) )
                v29 = (const WCHAR *)*((_QWORD *)Block + 2);
              v30 = CmdOptions::GetCurrentRef(*v27, v28);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v30 + 184LL),
                L"%s: WORKPLACE recovery information found. Device ID: %s\n",
                L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
                v29);
            }
          }
        }
        v21 = (wchar_t *)L"%s: WORKPLACE recovery information found. Device ID: %s\n";
      }
      else
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v11, v5) )
        {
          v12 = &cchOriginalDestLength;
          if ( *((_QWORD *)Block + 2) )
            v12 = (const WCHAR *)*((_QWORD *)Block + 2);
          wprintf(
            L"%s: UNKNOWN recovery information found. Device ID: %s\n",
            L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
            v12);
          v15 = (_QWORD *)CmdOptions::GetCurrentRef(v14, v13);
          if ( *(_BYTE *)(*v15 + 12LL) )
          {
            v17 = (_QWORD *)CmdOptions::GetCurrentRef(*v15, v16);
            if ( *(_QWORD *)(*v17 + 184LL) )
            {
              v19 = &cchOriginalDestLength;
              if ( *((_QWORD *)Block + 2) )
                v19 = (const WCHAR *)*((_QWORD *)Block + 2);
              v20 = CmdOptions::GetCurrentRef(*v17, v18);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v20 + 184LL),
                L"%s: UNKNOWN recovery information found. Device ID: %s\n",
                L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
                v19);
            }
          }
        }
        v21 = (wchar_t *)L"%s: UNKNOWN recovery information found. Device ID: %s\n";
      }
    }
    else
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v11, v5) )
      {
        v31 = &cchOriginalDestLength;
        if ( *((_QWORD *)Block + 2) )
          v31 = (const WCHAR *)*((_QWORD *)Block + 2);
        wprintf(
          L"%s: DEVICE recovery information found. Device ID: %s\n",
          L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
          v31);
        v34 = (_QWORD *)CmdOptions::GetCurrentRef(v33, v32);
        if ( *(_BYTE *)(*v34 + 12LL) )
        {
          v36 = (_QWORD *)CmdOptions::GetCurrentRef(*v34, v35);
          if ( *(_QWORD *)(*v36 + 184LL) )
          {
            v38 = &cchOriginalDestLength;
            if ( *((_QWORD *)Block + 2) )
              v38 = (const WCHAR *)*((_QWORD *)Block + 2);
            v39 = CmdOptions::GetCurrentRef(*v36, v37);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v39 + 184LL),
              L"%s: DEVICE recovery information found. Device ID: %s\n",
              L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
              v38);
          }
        }
      }
      v21 = (wchar_t *)L"%s: DEVICE recovery information found. Device ID: %s\n";
    }
    v40 = &cchOriginalDestLength;
    if ( *((_QWORD *)Block + 2) )
      v40 = (const WCHAR *)*((_QWORD *)Block + 2);
    Logger::TraceVerbose(v21, L"DsrCmdRecovery::RollbackRecoveryIfNeeded", v40);
    DsrFreeJoinInfoEx(Block);
    Block = 0;
    LODWORD(hEvent[0]) = 0;
    ResetEvent(hEvent[1]);
    JoinInfo = DsrEndRecovery(&DsrCmdRecovery::RecoveryRollbackCallback, hEvent, 1);
    if ( (JoinInfo & 0x80000000) != 0 )
    {
      CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v42, v41);
      v4 = L"%s: DsrEndRecovery failed with error code 0x%08x.\n";
      goto LABEL_81;
    }
    v43 = WaitForSingleObject(hEvent[1], 0x4E20u);
    v46 = v43;
    if ( v43 )
      break;
    JoinInfo = (unsigned int)hEvent[0];
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v45, v44) )
    {
      wprintf(
        L"%s: DsrEndRecovery completed with code 0x%08x.\n",
        L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
        JoinInfo);
      v59 = (_QWORD *)CmdOptions::GetCurrentRef(v58, v57);
      if ( *(_BYTE *)(*v59 + 12LL) )
      {
        v61 = (_QWORD *)CmdOptions::GetCurrentRef(*v59, v60);
        if ( *(_QWORD *)(*v61 + 184LL) )
        {
          v63 = CmdOptions::GetCurrentRef(*v61, v62);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v63 + 184LL),
            L"%s: DsrEndRecovery completed with code 0x%08x.\n",
            L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
            JoinInfo);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: DsrEndRecovery completed with code 0x%08x.\n",
      L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
      JoinInfo);
LABEL_58:
    if ( (JoinInfo & 0x80000000) != 0 )
      goto LABEL_86;
    JoinInfo = DsrGetJoinInfoEx(0xFFFFFFFFLL, &v98, &Block);
    if ( (JoinInfo & 0x80000000) != 0 )
    {
      CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v64, v5);
      goto LABEL_3;
    }
    if ( (unsigned int)++v10 > 0x64 )
    {
      JoinInfo = -2147418113;
      v79 = (_BYTE **)CmdOptions::GetCurrentRef(v64, v5);
      v80 = L"%s: Number of iterations is suspiciously high. Aborting.\n";
LABEL_74:
      if ( **v79 )
      {
        wprintf(v80, L"DsrCmdRecovery::RollbackRecoveryIfNeeded");
        v83 = (_QWORD *)CmdOptions::GetCurrentRef(v82, v81);
        if ( *(_BYTE *)(*v83 + 12LL) )
        {
          v85 = (_QWORD *)CmdOptions::GetCurrentRef(*v83, v84);
          if ( *(_QWORD *)(*v85 + 184LL) )
          {
            v87 = CmdOptions::GetCurrentRef(v86, *v85);
            fwprintf_s(*(FILE *const *)(*(_QWORD *)v87 + 184LL), v80, L"DsrCmdRecovery::RollbackRecoveryIfNeeded");
          }
        }
      }
      Logger::TraceError(v80, L"DsrCmdRecovery::RollbackRecoveryIfNeeded");
      goto LABEL_86;
    }
    v9 = Block;
    if ( !Block )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(0, v5) )
      {
        wprintf(L"%s: Recovery rollback successfully completed.\n", L"DsrCmdRecovery::RollbackRecoveryIfNeeded");
        v67 = (_QWORD *)CmdOptions::GetCurrentRef(v66, v65);
        if ( *(_BYTE *)(*v67 + 12LL) )
        {
          v69 = (_QWORD *)CmdOptions::GetCurrentRef(*v67, v68);
          if ( *(_QWORD *)(*v69 + 184LL) )
          {
            v71 = CmdOptions::GetCurrentRef(v70, *v69);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v71 + 184LL),
              L"%s: Recovery rollback successfully completed.\n",
              L"DsrCmdRecovery::RollbackRecoveryIfNeeded");
          }
        }
      }
      Logger::TraceInformation(
        L"%s: Recovery rollback successfully completed.\n",
        L"DsrCmdRecovery::RollbackRecoveryIfNeeded");
      goto LABEL_86;
    }
  }
  if ( v43 == 258 )
  {
    JoinInfo = -2147024638;
    v79 = (_BYTE **)CmdOptions::GetCurrentRef(v45, v44);
    v80 = L"%s: DsrEndRecovery call timed out.\n";
    goto LABEL_74;
  }
  if ( v43 == -1 )
  {
    v47 = GetLastError();
    JoinInfo = v47;
    if ( v47 > 0 )
      JoinInfo = (unsigned __int16)v47 | 0x80070000;
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v49, v48) )
    {
      wprintf(
        L"%s: WaitForSingleObject call failed with code 0x%08x.\n",
        L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
        JoinInfo);
      v52 = (_QWORD *)CmdOptions::GetCurrentRef(v51, v50);
      if ( *(_BYTE *)(*v52 + 12LL) )
      {
        v54 = (_QWORD *)CmdOptions::GetCurrentRef(*v52, v53);
        if ( *(_QWORD *)(*v54 + 184LL) )
        {
          v56 = CmdOptions::GetCurrentRef(*v54, v55);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v56 + 184LL),
            L"%s: WaitForSingleObject call failed with code 0x%08x.\n",
            L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
            JoinInfo);
        }
      }
    }
    Logger::TraceError(
      L"%s: WaitForSingleObject call failed with code 0x%08x.\n",
      L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
      JoinInfo);
    goto LABEL_58;
  }
  JoinInfo = -2147418113;
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v45, v44) )
  {
    wprintf(
      L"%s: WaitForSingleObject returned unexpected wait status 0x%08x.\n",
      L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
      v46);
    v74 = (_QWORD *)CmdOptions::GetCurrentRef(v73, v72);
    if ( *(_BYTE *)(*v74 + 12LL) )
    {
      v76 = (_QWORD *)CmdOptions::GetCurrentRef(*v74, v75);
      if ( *(_QWORD *)(*v76 + 184LL) )
      {
        v78 = CmdOptions::GetCurrentRef(*v76, v77);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v78 + 184LL),
          L"%s: WaitForSingleObject returned unexpected wait status 0x%08x.\n",
          L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
          v46);
      }
    }
  }
  Logger::TraceError(
    L"%s: WaitForSingleObject returned unexpected wait status 0x%08x.\n",
    L"DsrCmdRecovery::RollbackRecoveryIfNeeded",
    v46);
LABEL_86:
  if ( Block )
    DsrFreeJoinInfoEx(Block);
LABEL_88:
  if ( hEvent[1] )
    CloseHandle(hEvent[1]);
  return JoinInfo;
}

```

## disassembly

```asm
0x1800a9c10  mov     [rsp-28h+arg_10], rbx
0x1800a9c15  mov     [rsp-28h+arg_18], rsi
0x1800a9c1a  push    rbp
0x1800a9c1b  push    rdi
0x1800a9c1c  push    r12
0x1800a9c1e  push    r13
0x1800a9c20  push    r15
0x1800a9c22  mov     rbp, rsp
0x1800a9c25  sub     rsp, 30h
0x1800a9c29  xor     r12d, r12d
0x1800a9c2c  lea     r8, [rbp+Block]
0x1800a9c30  xorps   xmm0, xmm0
0x1800a9c33  mov     [rbp+Block], r12
0x1800a9c37  lea     rdx, [rbp+arg_8]
0x1800a9c3b  mov     [rbp+arg_8], r12
0x1800a9c3f  or      ecx, 0FFFFFFFFh
0x1800a9c42  movups  xmmword ptr [rbp+hEvent], xmm0
0x1800a9c46  call    DsrGetJoinInfoEx
0x1800a9c4b  mov     ebx, eax
0x1800a9c4d  test    eax, eax
0x1800a9c4f  jns     short loc_1800A9C69
0x1800a9c51  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9c56  lea     rdi, aDsrcmdrecovery_4; "DsrCmdRecovery::RollbackRecoveryIfNeede"...
0x1800a9c5d  lea     rsi, aSDsrgetjoininf; "%s: DsrGetJoinInfoEx failed with error "...
0x1800a9c64  jmp     loc_1800AA1A7
0x1800a9c69  cmp     [rbp+Block], r12
0x1800a9c6d  jnz     short loc_1800A9C79
0x1800a9c6f  mov     ebx, 1
0x1800a9c74  jmp     loc_1800AA215
0x1800a9c79  xor     r9d, r9d; lpName
0x1800a9c7c  xor     r8d, r8d; bInitialState
0x1800a9c7f  xor     ecx, ecx; lpEventAttributes
0x1800a9c81  lea     edx, [r9+1]; bManualReset
0x1800a9c85  call    cs:__imp_CreateEventW
0x1800a9c8b  mov     [rbp+hEvent+8], rax
0x1800a9c8f  test    rax, rax
0x1800a9c92  jnz     short loc_1800A9CC1
0x1800a9c94  call    cs:__imp_GetLastError
0x1800a9c9a  mov     ebx, eax
0x1800a9c9c  test    eax, eax
0x1800a9c9e  jle     short loc_1800A9CA9
0x1800a9ca0  movzx   ebx, ax
0x1800a9ca3  or      ebx, 80070000h
0x1800a9ca9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9cae  lea     rdi, aDsrcmdrecovery_4; "DsrCmdRecovery::RollbackRecoveryIfNeede"...
0x1800a9cb5  lea     rsi, aSCreateeventFa; "%s: CreateEvent failed with error 0x%08"...
0x1800a9cbc  jmp     loc_1800AA1A7
0x1800a9cc1  mov     rcx, [rbp+Block]
0x1800a9cc5  lea     rdi, aDsrcmdrecovery_4; "DsrCmdRecovery::RollbackRecoveryIfNeede"...
0x1800a9ccc  mov     r15d, 1
0x1800a9cd2  lea     r13, cchOriginalDestLength
0x1800a9cd9  mov     ecx, [rcx+4]
0x1800a9cdc  sub     ecx, 1
0x1800a9cdf  jz      loc_1800A9DFE
0x1800a9ce5  cmp     ecx, 1
0x1800a9ce8  jz      loc_1800A9D76
0x1800a9cee  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9cf3  mov     rcx, [rax]
0x1800a9cf6  cmp     [rcx], r12b
0x1800a9cf9  jz      short loc_1800A9D6A
0x1800a9cfb  mov     rax, [rbp+Block]
0x1800a9cff  lea     rcx, aSUnknownRecove; "%s: UNKNOWN recovery information found."...
0x1800a9d06  mov     r8, r13
0x1800a9d09  mov     rdx, rdi
0x1800a9d0c  cmp     [rax+10h], r12
0x1800a9d10  cmovnz  r8, [rax+10h]
0x1800a9d15  call    wprintf
0x1800a9d1a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9d1f  mov     rcx, [rax]
0x1800a9d22  cmp     [rcx+0Ch], r12b
0x1800a9d26  jz      short loc_1800A9D6A
0x1800a9d28  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9d2d  mov     rcx, [rax]
0x1800a9d30  cmp     [rcx+0B8h], r12
0x1800a9d37  jz      short loc_1800A9D6A
0x1800a9d39  mov     rax, [rbp+Block]
0x1800a9d3d  mov     rbx, r13
0x1800a9d40  cmp     [rax+10h], r12
0x1800a9d44  cmovnz  rbx, [rax+10h]
0x1800a9d49  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9d4e  mov     r9, rbx
0x1800a9d51  lea     rdx, aSUnknownRecove; "%s: UNKNOWN recovery information found."...
0x1800a9d58  mov     r8, rdi
0x1800a9d5b  mov     rcx, [rax]
0x1800a9d5e  mov     rcx, [rcx+0B8h]; Stream
0x1800a9d65  call    fwprintf_s
0x1800a9d6a  lea     rcx, aSUnknownRecove; "%s: UNKNOWN recovery information found."...
0x1800a9d71  jmp     loc_1800A9E81
0x1800a9d76  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9d7b  mov     rcx, [rax]
0x1800a9d7e  cmp     [rcx], r12b
0x1800a9d81  jz      short loc_1800A9DF2
0x1800a9d83  mov     rax, [rbp+Block]
0x1800a9d87  lea     rcx, aSWorkplaceReco; "%s: WORKPLACE recovery information foun"...
0x1800a9d8e  mov     r8, r13
0x1800a9d91  mov     rdx, rdi
0x1800a9d94  cmp     [rax+10h], r12
0x1800a9d98  cmovnz  r8, [rax+10h]
0x1800a9d9d  call    wprintf
0x1800a9da2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9da7  mov     rcx, [rax]
0x1800a9daa  cmp     [rcx+0Ch], r12b
0x1800a9dae  jz      short loc_1800A9DF2
0x1800a9db0  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9db5  mov     rcx, [rax]
0x1800a9db8  cmp     [rcx+0B8h], r12
0x1800a9dbf  jz      short loc_1800A9DF2
0x1800a9dc1  mov     rax, [rbp+Block]
0x1800a9dc5  mov     rbx, r13
0x1800a9dc8  cmp     [rax+10h], r12
0x1800a9dcc  cmovnz  rbx, [rax+10h]
0x1800a9dd1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9dd6  mov     r9, rbx
0x1800a9dd9  lea     rdx, aSWorkplaceReco; "%s: WORKPLACE recovery information foun"...
0x1800a9de0  mov     r8, rdi
0x1800a9de3  mov     rcx, [rax]
0x1800a9de6  mov     rcx, [rcx+0B8h]; Stream
0x1800a9ded  call    fwprintf_s
0x1800a9df2  lea     rcx, aSWorkplaceReco; "%s: WORKPLACE recovery information foun"...
0x1800a9df9  jmp     loc_1800A9E81
0x1800a9dfe  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9e03  mov     rcx, [rax]
0x1800a9e06  cmp     [rcx], r12b
0x1800a9e09  jz      short loc_1800A9E7A
0x1800a9e0b  mov     rax, [rbp+Block]
0x1800a9e0f  lea     rcx, aSDeviceRecover; "%s: DEVICE recovery information found. "...
0x1800a9e16  mov     r8, r13
0x1800a9e19  mov     rdx, rdi
0x1800a9e1c  cmp     [rax+10h], r12
0x1800a9e20  cmovnz  r8, [rax+10h]
0x1800a9e25  call    wprintf
0x1800a9e2a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9e2f  mov     rcx, [rax]
0x1800a9e32  cmp     [rcx+0Ch], r12b
0x1800a9e36  jz      short loc_1800A9E7A
0x1800a9e38  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9e3d  mov     rcx, [rax]
0x1800a9e40  cmp     [rcx+0B8h], r12
0x1800a9e47  jz      short loc_1800A9E7A
0x1800a9e49  mov     rax, [rbp+Block]
0x1800a9e4d  mov     rbx, r13
0x1800a9e50  cmp     [rax+10h], r12
0x1800a9e54  cmovnz  rbx, [rax+10h]
0x1800a9e59  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9e5e  mov     r9, rbx
0x1800a9e61  lea     rdx, aSDeviceRecover; "%s: DEVICE recovery information found. "...
0x1800a9e68  mov     r8, rdi
0x1800a9e6b  mov     rcx, [rax]
0x1800a9e6e  mov     rcx, [rcx+0B8h]; Stream
0x1800a9e75  call    fwprintf_s
0x1800a9e7a  lea     rcx, aSDeviceRecover; "%s: DEVICE recovery information found. "...
0x1800a9e81  mov     rax, [rbp+Block]
0x1800a9e85  mov     r8, r13
0x1800a9e88  mov     rdx, rdi
0x1800a9e8b  cmp     [rax+10h], r12
0x1800a9e8f  cmovnz  r8, [rax+10h]
0x1800a9e94  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800a9e99  mov     rcx, [rbp+Block]; Block
0x1800a9e9d  call    DsrFreeJoinInfoEx
0x1800a9ea2  mov     rcx, [rbp+hEvent+8]; hEvent
0x1800a9ea6  mov     [rbp+Block], r12
0x1800a9eaa  mov     dword ptr [rbp+hEvent], r12d
0x1800a9eae  call    cs:__imp_ResetEvent
0x1800a9eb4  mov     r8d, 1
0x1800a9eba  lea     rdx, [rbp+hEvent]
0x1800a9ebe  lea     rcx, ?RecoveryRollbackCallback@DsrCmdRecovery@@CAXUstruct_dsreg_server_response@@_KJ@Z; DsrCmdRecovery::RecoveryRollbackCallback(struct_dsreg_server_response,unsigned __int64,long)
0x1800a9ec5  call    DsrEndRecovery
0x1800a9eca  mov     ebx, eax
0x1800a9ecc  test    eax, eax
0x1800a9ece  js      loc_1800AA19B
0x1800a9ed4  mov     rcx, [rbp+hEvent+8]; hHandle
0x1800a9ed8  mov     edx, 4E20h; dwMilliseconds
0x1800a9edd  call    cs:__imp_WaitForSingleObject
0x1800a9ee3  mov     esi, eax
0x1800a9ee5  test    eax, eax
0x1800a9ee7  jz      loc_1800A9F89
0x1800a9eed  cmp     eax, 102h
0x1800a9ef2  jz      loc_1800AA114
0x1800a9ef8  cmp     eax, 0FFFFFFFFh
0x1800a9efb  jnz     loc_1800AA0A1
0x1800a9f01  call    cs:__imp_GetLastError
0x1800a9f07  mov     ebx, eax
0x1800a9f09  test    eax, eax
0x1800a9f0b  jle     short loc_1800A9F16
0x1800a9f0d  movzx   ebx, ax
0x1800a9f10  or      ebx, 80070000h
0x1800a9f16  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9f1b  mov     rcx, [rax]
0x1800a9f1e  cmp     [rcx], r12b
0x1800a9f21  jz      short loc_1800A9F75
0x1800a9f23  mov     r8d, ebx
0x1800a9f26  lea     rcx, aSWaitforsingle_11; "%s: WaitForSingleObject call failed wit"...
0x1800a9f2d  mov     rdx, rdi
0x1800a9f30  call    wprintf
0x1800a9f35  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9f3a  mov     rcx, [rax]
0x1800a9f3d  cmp     [rcx+0Ch], r12b
0x1800a9f41  jz      short loc_1800A9F75
0x1800a9f43  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9f48  mov     rcx, [rax]
0x1800a9f4b  cmp     [rcx+0B8h], r12
0x1800a9f52  jz      short loc_1800A9F75
0x1800a9f54  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9f59  mov     r9d, ebx
0x1800a9f5c  lea     rdx, aSWaitforsingle_11; "%s: WaitForSingleObject call failed wit"...
0x1800a9f63  mov     r8, rdi
0x1800a9f66  mov     rcx, [rax]
0x1800a9f69  mov     rcx, [rcx+0B8h]; Stream
0x1800a9f70  call    fwprintf_s
0x1800a9f75  mov     r8d, ebx
0x1800a9f78  lea     rcx, aSWaitforsingle_11; "%s: WaitForSingleObject call failed wit"...
0x1800a9f7f  mov     rdx, rdi
0x1800a9f82  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800a9f87  jmp     short loc_1800A9FFD
0x1800a9f89  mov     ebx, dword ptr [rbp+hEvent]
0x1800a9f8c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9f91  mov     rcx, [rax]
0x1800a9f94  cmp     [rcx], r12b
0x1800a9f97  jz      short loc_1800A9FEB
0x1800a9f99  mov     r8d, ebx
0x1800a9f9c  lea     rcx, aSDsrendrecover_1; "%s: DsrEndRecovery completed with code "...
0x1800a9fa3  mov     rdx, rdi
0x1800a9fa6  call    wprintf
0x1800a9fab  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9fb0  mov     rcx, [rax]
0x1800a9fb3  cmp     [rcx+0Ch], r12b
0x1800a9fb7  jz      short loc_1800A9FEB
0x1800a9fb9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9fbe  mov     rcx, [rax]
0x1800a9fc1  cmp     [rcx+0B8h], r12
0x1800a9fc8  jz      short loc_1800A9FEB
0x1800a9fca  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a9fcf  mov     r9d, ebx
0x1800a9fd2  lea     rdx, aSDsrendrecover_1; "%s: DsrEndRecovery completed with code "...
0x1800a9fd9  mov     r8, rdi
0x1800a9fdc  mov     rcx, [rax]
0x1800a9fdf  mov     rcx, [rcx+0B8h]; Stream
0x1800a9fe6  call    fwprintf_s
0x1800a9feb  mov     r8d, ebx
0x1800a9fee  lea     rcx, aSDsrendrecover_1; "%s: DsrEndRecovery completed with code "...
0x1800a9ff5  mov     rdx, rdi
0x1800a9ff8  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800a9ffd  test    ebx, ebx
0x1800a9fff  js      loc_1800AA207
0x1800aa005  lea     r8, [rbp+Block]
0x1800aa009  or      ecx, 0FFFFFFFFh
0x1800aa00c  lea     rdx, [rbp+arg_8]
0x1800aa010  call    DsrGetJoinInfoEx
0x1800aa015  mov     ebx, eax
0x1800aa017  test    eax, eax
0x1800aa019  js      loc_1800AA191
0x1800aa01f  inc     r15d
0x1800aa022  cmp     r15d, 64h ; 'd'
0x1800aa026  ja      loc_1800AA127
0x1800aa02c  mov     rcx, [rbp+Block]
0x1800aa030  test    rcx, rcx
0x1800aa033  jnz     loc_1800A9CD9
0x1800aa039  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa03e  lea     rsi, aSRecoveryRollb; "%s: Recovery rollback successfully comp"...
0x1800aa045  mov     rcx, [rax]
0x1800aa048  cmp     [rcx], r12b
0x1800aa04b  jz      short loc_1800AA091
0x1800aa04d  mov     rdx, rdi
0x1800aa050  mov     rcx, rsi; Format
0x1800aa053  call    wprintf
0x1800aa058  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa05d  mov     rcx, [rax]
0x1800aa060  cmp     [rcx+0Ch], r12b
0x1800aa064  jz      short loc_1800AA091
0x1800aa066  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa06b  mov     rdx, [rax]
0x1800aa06e  cmp     [rdx+0B8h], r12
0x1800aa075  jz      short loc_1800AA091
0x1800aa077  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa07c  mov     r8, rdi
0x1800aa07f  mov     rdx, rsi; Format
0x1800aa082  mov     rcx, [rax]
0x1800aa085  mov     rcx, [rcx+0B8h]; Stream
0x1800aa08c  call    fwprintf_s
0x1800aa091  mov     rdx, rdi
0x1800aa094  mov     rcx, rsi; unsigned __int16 *
0x1800aa097  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800aa09c  jmp     loc_1800AA207
0x1800aa0a1  mov     ebx, 8000FFFFh
0x1800aa0a6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa0ab  mov     rcx, [rax]
0x1800aa0ae  cmp     [rcx], r12b
0x1800aa0b1  jz      short loc_1800AA105
0x1800aa0b3  mov     r8d, esi
0x1800aa0b6  lea     rcx, aSWaitforsingle_9; "%s: WaitForSingleObject returned unexpe"...
0x1800aa0bd  mov     rdx, rdi
0x1800aa0c0  call    wprintf
0x1800aa0c5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa0ca  mov     rcx, [rax]
0x1800aa0cd  cmp     [rcx+0Ch], r12b
0x1800aa0d1  jz      short loc_1800AA105
0x1800aa0d3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aa0d8  mov     rcx, [rax]
0x1800aa0db  cmp     [rcx+0B8h], r12
0x1800aa0e2  jz      short loc_1800AA105
  ... truncated ...
```
