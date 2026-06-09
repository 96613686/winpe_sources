# DsrCmdAzureHelper::HandleAuthChallenge(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002708c`
- end: `0x1800276b2`
- name: `?HandleAuthChallenge@DsrCmdAzureHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `1574`
- prototype: `__int64 __fastcall(unsigned __int16 *lpFileName, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180028440`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x180012c7c`
- `0x180012cf0`
- `0x18001378c`
- `0x180016b90`
- `0x18001b560`
- `0x18002708c`
- `0x18002927c`
- `0x18002b9b4`
- `0x18002dd24`
- `0x1800319ac`
- `0x18003b2bc`
- `0x180044300`
- `0x180044d30`
- `0x180046410`
- `0x180046ae8`
- `0x180046b3c`
- `0x18006c144`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002735b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002735b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275a6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027517`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027517`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180027450`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180027450`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027348`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027348`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002717f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002717f`

## string_xrefs

- `0x1800270df`: `\AzureConnectedMachineAgent\Tokens`
- `0x180027178`: `%ProgramData%`
- `0x180027600`: `%s: Getting secret file path length failed as the path is invalid.\n`
- `0x180027372`: `%s: Opening exsting file failed with Win32 error code 0x%08x.\n`
- `0x1800273e8`: `%s: User must have sufficient privileges to access the secret file!\n`
- `0x18002722b`: `%s: Failed to validate secret file path with error code 0x%08x%\n`
- `0x1800272b4`: `%s: Secret file path does not match, invalid path!\n`
- `0x18002752e`: `%s: Reading opened secret file failed with Win32 error code 0x%08x\n`

## pseudocode

```c
__int64 __fastcall DsrCmdAzureHelper::HandleAuthChallenge(unsigned __int16 *lpFileName, __int64 a2)
{
  CHAR *v4; // r12
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int16 *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int16 *v11; // rbx
  __int64 end_2; // rax
  __int64 v13; // rdi
  __int64 v14; // r8
  const unsigned __int16 *v15; // rbx
  const WCHAR *v16; // rcx
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rcx
  _BYTE **CurrentRef; // rax
  const wchar_t *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rdx
  _QWORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  __int64 v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  const WCHAR *v36; // rcx
  HANDLE FileW; // rax
  void *v38; // r15
  DWORD v39; // esi
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  _QWORD *v44; // rax
  __int64 v45; // rdx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  _QWORD *v53; // rax
  __int64 v54; // rdx
  _QWORD *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  DWORD FileSize; // eax
  unsigned __int64 v59; // rbx
  __int64 v60; // rdx
  __int64 v61; // rcx
  _BYTE **v62; // rax
  const wchar_t *v63; // r13
  __int64 v64; // rdx
  __int64 v65; // rcx
  _QWORD *v66; // rax
  __int64 v67; // rdx
  _QWORD *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rax
  CHAR *v71; // rax
  unsigned int v72; // edx
  __int64 v73; // rdx
  __int64 v74; // rcx
  int v75; // eax
  __int64 v76; // rax
  signed int LastError; // eax
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rdx
  _QWORD *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  unsigned int v88; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v90[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD Src[4]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWCH lpString1[4]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v93[2]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Dst[264]; // [rsp+C0h] [rbp-40h] BYREF

  v90[1] = lpFileName;
  NumberOfBytesRead = 0;
  v88 = 1;
  v4 = 0;
  v90[0] = 0;
  std::wstring::wstring(v93, L"\\AzureConnectedMachineAgent\\Tokens");
  std::wstring::wstring(Src);
  memset_0(Dst, 0, 0x208u);
  v7 = *((_QWORD *)lpFileName + 2);
  if ( *((_QWORD *)lpFileName + 3) <= 7u )
    v8 = lpFileName;
  else
    v8 = *(unsigned __int16 **)lpFileName;
  if ( v7 )
  {
    v9 = v7 - 1;
    v10 = -1;
    if ( v9 != -1 )
      v10 = v9;
    v11 = &v8[v10 + 1];
    end_2 = _std_find_end_2(v8, v11, L"\\", 1);
    if ( (unsigned __int16 *)end_2 != v11 )
    {
      v13 = (end_2 - (__int64)v8) >> 1;
      if ( v13 != -1 )
      {
        if ( ExpandEnvironmentStringsW(L"%ProgramData%", Dst, 0x104u) - 1 > 0x102 )
        {
          LastError = GetLastError();
          v17 = LastError;
          if ( LastError > 0 )
            v17 = (unsigned __int16)LastError | 0x80070000;
          CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v79, v78);
          v21 = L"%s: Failed to load program data location with error code 0x%08x%.\n";
          goto LABEL_18;
        }
        v14 = -1;
        do
          ++v14;
        while ( Dst[v14] );
        std::wstring::_Assign<unsigned short>(Src, Dst);
        std::wstring::_Append<unsigned short>(Src);
        v15 = (const unsigned __int16 *)Src;
        if ( Src[3] > 7u )
          v15 = (const unsigned __int16 *)Src[0];
        std::wstring::wstring(lpString1, lpFileName, 0, v13);
        v16 = (const WCHAR *)lpString1;
        if ( lpString1[3] > (LPCWCH)7 )
          v16 = lpString1[0];
        v17 = StringCompare(v16, v15, 1u, (int *)&v88);
        std::wstring::_Tidy_deallocate(lpString1);
        if ( (v17 & 0x80000000) != 0 )
        {
          CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v19, v18);
          v21 = L"%s: Failed to validate secret file path with error code 0x%08x%\n";
LABEL_18:
          if ( **CurrentRef )
          {
            wprintf(v21, L"DsrCmdAzureHelper::HandleAuthChallenge", v17);
            v24 = (_QWORD *)CmdOptions::GetCurrentRef(v23, v22);
            if ( *(_BYTE *)(*v24 + 12LL) )
            {
              v26 = (_QWORD *)CmdOptions::GetCurrentRef(*v24, v25);
              if ( *(_QWORD *)(*v26 + 184LL) )
              {
                v28 = CmdOptions::GetCurrentRef(*v26, v27);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v28 + 184LL),
                  v21,
                  L"DsrCmdAzureHelper::HandleAuthChallenge",
                  v17);
              }
            }
          }
          Logger::TraceError(v21, L"DsrCmdAzureHelper::HandleAuthChallenge", v17);
          goto LABEL_72;
        }
        if ( !v88 )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v19, v18) )
          {
            wprintf(L"%s: Secret file path does not match, invalid path!\n", L"DsrCmdAzureHelper::HandleAuthChallenge");
            v31 = (_QWORD *)CmdOptions::GetCurrentRef(v30, v29);
            if ( *(_BYTE *)(*v31 + 12LL) )
            {
              v33 = (_QWORD *)CmdOptions::GetCurrentRef(*v31, v32);
              if ( *(_QWORD *)(*v33 + 184LL) )
              {
                v35 = CmdOptions::GetCurrentRef(*v33, v34);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v35 + 184LL),
                  L"%s: Secret file path does not match, invalid path!\n",
                  L"DsrCmdAzureHelper::HandleAuthChallenge");
              }
            }
          }
          Logger::TraceError(
            L"%s: Secret file path does not match, invalid path!\n",
            L"DsrCmdAzureHelper::HandleAuthChallenge");
          v17 = -2145648494;
          goto LABEL_72;
        }
        if ( *((_QWORD *)lpFileName + 3) <= 7u )
          v36 = lpFileName;
        else
          v36 = *(const WCHAR **)lpFileName;
        FileW = CreateFileW(v36, 0x80000000, 0, 0, 3u, 0x80u, 0);
        v38 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v39 = GetLastError();
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v41, v40) )
          {
            wprintf(
              L"%s: Opening exsting file failed with Win32 error code 0x%08x.\n",
              L"DsrCmdAzureHelper::HandleAuthChallenge",
              v39);
            v44 = (_QWORD *)CmdOptions::GetCurrentRef(v43, v42);
            if ( *(_BYTE *)(*v44 + 12LL) )
            {
              v46 = (_QWORD *)CmdOptions::GetCurrentRef(*v44, v45);
              if ( *(_QWORD *)(*v46 + 184LL) )
              {
                v48 = CmdOptions::GetCurrentRef(*v46, v47);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v48 + 184LL),
                  L"%s: Opening exsting file failed with Win32 error code 0x%08x.\n",
                  L"DsrCmdAzureHelper::HandleAuthChallenge",
                  v39);
              }
            }
          }
          Logger::TraceError(
            L"%s: Opening exsting file failed with Win32 error code 0x%08x.\n",
            L"DsrCmdAzureHelper::HandleAuthChallenge",
            v39);
          if ( v39 == 5 )
          {
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v50, v49) )
            {
              wprintf(
                L"%s: User must have sufficient privileges to access the secret file!\n",
                L"DsrCmdAzureHelper::HandleAuthChallenge");
              v53 = (_QWORD *)CmdOptions::GetCurrentRef(v52, v51);
              if ( *(_BYTE *)(*v53 + 12LL) )
              {
                v55 = (_QWORD *)CmdOptions::GetCurrentRef(*v53, v54);
                if ( *(_QWORD *)(*v55 + 184LL) )
                {
                  v57 = CmdOptions::GetCurrentRef(*v55, v56);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v57 + 184LL),
                    L"%s: User must have sufficient privileges to access the secret file!\n",
                    L"DsrCmdAzureHelper::HandleAuthChallenge");
                }
              }
            }
            Logger::TraceError(
              L"%s: User must have sufficient privileges to access the secret file!\n",
              L"DsrCmdAzureHelper::HandleAuthChallenge");
          }
LABEL_59:
          CloseHandle(v38);
LABEL_60:
          if ( v39 )
          {
            if ( (int)v39 > 0 )
              v17 = (unsigned __int16)v39 | 0x80070000;
            else
              v17 = v39;
          }
          goto LABEL_72;
        }
        v39 = 0;
        FileSize = GetFileSize(FileW, 0);
        v59 = FileSize;
        if ( FileSize == -1 && (v39 = GetLastError()) != 0 )
        {
          v62 = (_BYTE **)CmdOptions::GetCurrentRef(v61, v60);
          v63 = L"%s: File size exceeds with Win32 error code 0x%08x.\n";
        }
        else
        {
          v71 = (CHAR *)SafeAlloc(v59);
          v4 = v71;
          if ( !v71 )
          {
            v17 = -2147024882;
            goto LABEL_58;
          }
          if ( ReadFile(v38, v71, v59, &NumberOfBytesRead, 0) )
          {
            v4[NumberOfBytesRead] = 0;
            v75 = MBToUnicode(v4, v72, v90, &v88);
            v17 = v75;
            if ( v75 >= 0 )
            {
              v76 = std::wstring::wstring(lpString1, v90[0]);
              std::wstring::operator=(a2, v76);
              std::wstring::_Tidy_deallocate(lpString1);
            }
            else
            {
              Logger::TraceError(
                L"%s: %s failed with error code: 0x%08x.",
                L"DsrCmdAzureHelper::HandleAuthChallenge",
                L"MBToUnicode",
                (unsigned int)v75);
            }
            goto LABEL_58;
          }
          v39 = GetLastError();
          v62 = (_BYTE **)CmdOptions::GetCurrentRef(v74, v73);
          v63 = L"%s: Reading opened secret file failed with Win32 error code 0x%08x\n";
        }
        if ( **v62 )
        {
          wprintf(v63, L"DsrCmdAzureHelper::HandleAuthChallenge", v39);
          v66 = (_QWORD *)CmdOptions::GetCurrentRef(v65, v64);
          if ( *(_BYTE *)(*v66 + 12LL) )
          {
            v68 = (_QWORD *)CmdOptions::GetCurrentRef(*v66, v67);
            if ( *(_QWORD *)(*v68 + 184LL) )
            {
              v70 = CmdOptions::GetCurrentRef(*v68, v69);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v70 + 184LL), v63, L"DsrCmdAzureHelper::HandleAuthChallenge", v39);
            }
          }
        }
        Logger::TraceError(v63, L"DsrCmdAzureHelper::HandleAuthChallenge", v39);
LABEL_58:
        if ( !v38 )
          goto LABEL_60;
        goto LABEL_59;
      }
    }
  }
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v6, v5) )
  {
    wprintf(
      L"%s: Getting secret file path length failed as the path is invalid.\n",
      L"DsrCmdAzureHelper::HandleAuthChallenge");
    v82 = (_QWORD *)CmdOptions::GetCurrentRef(v81, v80);
    if ( *(_BYTE *)(*v82 + 12LL) )
    {
      v84 = (_QWORD *)CmdOptions::GetCurrentRef(*v82, v83);
      if ( *(_QWORD *)(*v84 + 184LL) )
      {
        v86 = CmdOptions::GetCurrentRef(*v84, v85);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v86 + 184LL),
          L"%s: Getting secret file path length failed as the path is invalid.\n",
          L"DsrCmdAzureHelper::HandleAuthChallenge");
      }
    }
  }
  Logger::TraceError(
    L"%s: Getting secret file path length failed as the path is invalid.\n",
    L"DsrCmdAzureHelper::HandleAuthChallenge");
  v17 = -2147024809;
LABEL_72:
  SafeFree(v4);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v93);
  std::wstring::_Tidy_deallocate(lpFileName);
  return v17;
}

```

## disassembly

```asm
0x18002708c  mov     [rsp-8+arg_10], rbx
0x180027091  push    rbp
0x180027092  push    rsi
0x180027093  push    rdi
0x180027094  push    r12
0x180027096  push    r13
0x180027098  push    r14
0x18002709a  push    r15
0x18002709c  lea     rbp, [rsp-1E0h]
0x1800270a4  sub     rsp, 2E0h
0x1800270ab  mov     rax, cs:__security_cookie
0x1800270b2  xor     rax, rsp
0x1800270b5  mov     [rbp+210h+var_40], rax
0x1800270bc  mov     r13, rdx
0x1800270bf  mov     r14, rcx
0x1800270c2  mov     [rsp+310h+var_2C0], rcx
0x1800270c7  xor     r15d, r15d
0x1800270ca  mov     [rsp+310h+NumberOfBytesRead], r15d
0x1800270cf  lea     edi, [r15+1]
0x1800270d3  mov     [rsp+310h+var_2D0], edi
0x1800270d7  mov     r12d, r15d
0x1800270da  mov     [rsp+310h+var_2C8], r15
0x1800270df  lea     rdx, aAzureconnected; "\\AzureConnectedMachineAgent\\Tokens"
0x1800270e6  lea     rcx, [rbp+210h+var_278]
0x1800270ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800270ef  nop
0x1800270f0  lea     rcx, [rsp+310h+Src]
0x1800270f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800270fa  nop
0x1800270fb  xor     edx, edx; Val
0x1800270fd  mov     r8d, 208h; Size
0x180027103  lea     rcx, [rbp+210h+Dst]; void *
0x180027107  call    memset_0
0x18002710c  mov     rax, [r14+10h]
0x180027110  cmp     qword ptr [r14+18h], 7
0x180027115  jbe     short loc_18002711C
0x180027117  mov     rsi, [r14]
0x18002711a  jmp     short loc_18002711F
0x18002711c  mov     rsi, r14
0x18002711f  cmp     rax, rdi
0x180027122  jb      loc_1800275F1
0x180027128  dec     rax
0x18002712b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002712f  cmp     rax, rcx
0x180027132  cmovb   rcx, rax
0x180027136  inc     rcx
0x180027139  lea     rbx, [rsi+rcx*2]
0x18002713d  mov     r9, rdi
0x180027140  lea     r8, asc_1800D720C; "\\"
0x180027147  mov     rdx, rbx
0x18002714a  mov     rcx, rsi
0x18002714d  call    __std_find_end_2
0x180027152  mov     rdi, rax
0x180027155  cmp     rax, rbx
0x180027158  jz      loc_1800275F1
0x18002715e  sub     rdi, rsi
0x180027161  sar     rdi, 1
0x180027164  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180027168  jz      loc_1800275F1
0x18002716e  mov     r8d, 104h; nSize
0x180027174  lea     rdx, [rbp+210h+Dst]; lpDst
0x180027178  lea     rcx, Src; "%ProgramData%"
0x18002717f  call    cs:__imp_ExpandEnvironmentStringsW
0x180027185  dec     eax
0x180027187  cmp     eax, 102h
0x18002718c  ja      loc_1800275CB
0x180027192  lea     rax, [rbp+210h+Dst]
0x180027196  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002719a  inc     r8
0x18002719d  cmp     [rax+r8*2], r15w
0x1800271a2  jnz     short loc_18002719A
0x1800271a4  lea     rdx, [rbp+210h+Dst]
0x1800271a8  lea     rcx, [rsp+310h+Src]
0x1800271ad  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800271b2  lea     rdx, [rbp+210h+var_278]
0x1800271b6  cmp     [rbp+210h+var_260], 7
0x1800271bb  cmova   rdx, [rbp+210h+var_278]
0x1800271c0  mov     r8, [rbp+210h+var_268]
0x1800271c4  lea     rcx, [rsp+310h+Src]; Src
0x1800271c9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800271ce  lea     rbx, [rsp+310h+Src]
0x1800271d3  cmp     [rsp+310h+var_2A0], 7
0x1800271d9  cmova   rbx, [rsp+310h+Src]
0x1800271df  mov     r9, rdi
0x1800271e2  xor     r8d, r8d
0x1800271e5  mov     rdx, r14
0x1800271e8  lea     rcx, [rsp+310h+lpString1]
0x1800271ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800271f2  nop
0x1800271f3  lea     rcx, [rsp+310h+lpString1]
0x1800271f8  cmp     [rbp+210h+var_280], 7
0x1800271fd  cmova   rcx, [rsp+310h+lpString1]; lpString1
0x180027203  lea     r9, [rsp+310h+var_2D0]; int *
0x180027208  mov     r8d, 1; unsigned int
0x18002720e  mov     rdx, rbx; unsigned __int16 *
0x180027211  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180027216  mov     edi, eax
0x180027218  lea     rcx, [rsp+310h+lpString1]
0x18002721d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027222  test    edi, edi
0x180027224  jns     short loc_18002729E
0x180027226  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002722b  lea     rsi, aSFailedToValid; "%s: Failed to validate secret file path"...
0x180027232  mov     rcx, [rax]
0x180027235  cmp     [rcx], r15b
0x180027238  lea     rbx, aDsrcmdazurehel; "DsrCmdAzureHelper::HandleAuthChallenge"
0x18002723f  jz      short loc_18002728B
0x180027241  mov     r8d, edi
0x180027244  mov     rdx, rbx
0x180027247  mov     rcx, rsi; Format
0x18002724a  call    wprintf
0x18002724f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027254  mov     rcx, [rax]
0x180027257  cmp     [rcx+0Ch], r15b
0x18002725b  jz      short loc_18002728B
0x18002725d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027262  mov     rcx, [rax]
0x180027265  cmp     [rcx+0B8h], r15
0x18002726c  jz      short loc_18002728B
0x18002726e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027273  mov     rcx, [rax]
0x180027276  mov     r9d, edi
0x180027279  mov     r8, rbx
0x18002727c  mov     rdx, rsi; Format
0x18002727f  mov     rcx, [rcx+0B8h]; Stream
0x180027286  call    fwprintf_s
0x18002728b  mov     r8d, edi
0x18002728e  mov     rdx, rbx
0x180027291  mov     rcx, rsi; unsigned __int16 *
0x180027294  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180027299  jmp     loc_180027660
0x18002729e  cmp     [rsp+310h+var_2D0], r15d
0x1800272a3  jnz     short loc_180027319
0x1800272a5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800272aa  mov     rcx, [rax]
0x1800272ad  lea     rbx, aDsrcmdazurehel; "DsrCmdAzureHelper::HandleAuthChallenge"
0x1800272b4  lea     rdi, aSSecretFilePat; "%s: Secret file path does not match, in"...
0x1800272bb  cmp     [rcx], r15b
0x1800272be  jz      short loc_180027304
0x1800272c0  mov     rdx, rbx
0x1800272c3  mov     rcx, rdi; Format
0x1800272c6  call    wprintf
0x1800272cb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800272d0  mov     rcx, [rax]
0x1800272d3  cmp     [rcx+0Ch], r15b
0x1800272d7  jz      short loc_180027304
0x1800272d9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800272de  mov     rcx, [rax]
0x1800272e1  cmp     [rcx+0B8h], r15
0x1800272e8  jz      short loc_180027304
0x1800272ea  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800272ef  mov     rcx, [rax]
0x1800272f2  mov     r8, rbx
0x1800272f5  mov     rdx, rdi; Format
0x1800272f8  mov     rcx, [rcx+0B8h]; Stream
0x1800272ff  call    fwprintf_s
0x180027304  mov     rdx, rbx
0x180027307  mov     rcx, rdi; unsigned __int16 *
0x18002730a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002730f  mov     edi, 801C0092h
0x180027314  jmp     loc_180027660
0x180027319  cmp     qword ptr [r14+18h], 7
0x18002731e  jbe     short loc_180027325
0x180027320  mov     rcx, [r14]
0x180027323  jmp     short loc_180027328
0x180027325  mov     rcx, r14; lpFileName
0x180027328  mov     [rsp+310h+hTemplateFile], r15; hTemplateFile
0x18002732d  mov     [rsp+310h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180027335  mov     [rsp+310h+dwCreationDisposition], 3; dwCreationDisposition
0x18002733d  xor     r9d, r9d; lpSecurityAttributes
0x180027340  xor     r8d, r8d; dwShareMode
0x180027343  mov     edx, 80000000h; dwDesiredAccess
0x180027348  call    cs:__imp_CreateFileW
0x18002734e  mov     r15, rax
0x180027351  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027355  jnz     loc_180027449
0x18002735b  call    cs:__imp_GetLastError
0x180027361  mov     esi, eax
0x180027363  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027368  mov     rcx, [rax]
0x18002736b  lea     rbx, aDsrcmdazurehel; "DsrCmdAzureHelper::HandleAuthChallenge"
0x180027372  lea     r13, aSOpeningExstin; "%s: Opening exsting file failed with Wi"...
0x180027379  cmp     byte ptr [rcx], 0
0x18002737c  jz      short loc_1800273C9
0x18002737e  mov     r8d, esi
0x180027381  mov     rdx, rbx
0x180027384  mov     rcx, r13; Format
0x180027387  call    wprintf
0x18002738c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027391  mov     rcx, [rax]
0x180027394  cmp     byte ptr [rcx+0Ch], 0
0x180027398  jz      short loc_1800273C9
0x18002739a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002739f  mov     rcx, [rax]
0x1800273a2  cmp     qword ptr [rcx+0B8h], 0
0x1800273aa  jz      short loc_1800273C9
0x1800273ac  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800273b1  mov     rcx, [rax]
0x1800273b4  mov     r9d, esi
0x1800273b7  mov     r8, rbx
0x1800273ba  mov     rdx, r13; Format
0x1800273bd  mov     rcx, [rcx+0B8h]; Stream
0x1800273c4  call    fwprintf_s
0x1800273c9  mov     r8d, esi
0x1800273cc  mov     rdx, rbx
0x1800273cf  mov     rcx, r13; unsigned __int16 *
0x1800273d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800273d7  cmp     esi, 5
0x1800273da  jnz     loc_1800275A3
0x1800273e0  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800273e5  mov     rcx, [rax]
0x1800273e8  lea     r13, aSUserMustHaveS; "%s: User must have sufficient privilege"...
0x1800273ef  cmp     byte ptr [rcx], 0
0x1800273f2  jz      short loc_180027439
0x1800273f4  mov     rdx, rbx
0x1800273f7  mov     rcx, r13; Format
0x1800273fa  call    wprintf
0x1800273ff  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027404  mov     rcx, [rax]
0x180027407  cmp     byte ptr [rcx+0Ch], 0
0x18002740b  jz      short loc_180027439
0x18002740d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027412  mov     rcx, [rax]
0x180027415  cmp     qword ptr [rcx+0B8h], 0
0x18002741d  jz      short loc_180027439
0x18002741f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027424  mov     rcx, [rax]
0x180027427  mov     r8, rbx
0x18002742a  mov     rdx, r13; Format
0x18002742d  mov     rcx, [rcx+0B8h]; Stream
0x180027434  call    fwprintf_s
0x180027439  mov     rdx, rbx
0x18002743c  mov     rcx, r13; unsigned __int16 *
0x18002743f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180027444  jmp     loc_1800275A3
0x180027449  xor     esi, esi
0x18002744b  xor     edx, edx; lpFileSizeHigh
0x18002744d  mov     rcx, r15; hFile
0x180027450  call    cs:__imp_GetFileSize
0x180027456  mov     ebx, eax
0x180027458  cmp     eax, 0FFFFFFFFh
0x18002745b  jnz     loc_1800274E6
0x180027461  call    cs:__imp_GetLastError
0x180027467  mov     esi, eax
0x180027469  test    eax, eax
0x18002746b  jz      short loc_1800274E6
0x18002746d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180027472  lea     r13, aSFileSizeExcee; "%s: File size exceeds with Win32 error "...
0x180027479  mov     rcx, [rax]
0x18002747c  cmp     byte ptr [rcx], 0
0x18002747f  lea     rbx, aDsrcmdazurehel; "DsrCmdAzureHelper::HandleAuthChallenge"
0x180027486  jz      short loc_1800274D3
0x180027488  mov     r8d, esi
0x18002748b  mov     rdx, rbx
0x18002748e  mov     rcx, r13; Format
0x180027491  call    wprintf
0x180027496  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002749b  mov     rcx, [rax]
0x18002749e  cmp     byte ptr [rcx+0Ch], 0
0x1800274a2  jz      short loc_1800274D3
0x1800274a4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800274a9  mov     rcx, [rax]
0x1800274ac  cmp     qword ptr [rcx+0B8h], 0
0x1800274b4  jz      short loc_1800274D3
0x1800274b6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800274bb  mov     rcx, [rax]
0x1800274be  mov     r9d, esi
0x1800274c1  mov     r8, rbx
0x1800274c4  mov     rdx, r13; Format
0x1800274c7  mov     rcx, [rcx+0B8h]; Stream
0x1800274ce  call    fwprintf_s
0x1800274d3  mov     r8d, esi
0x1800274d6  mov     rdx, rbx
0x1800274d9  mov     rcx, r13; unsigned __int16 *
0x1800274dc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800274e1  jmp     loc_18002759E
0x1800274e6  mov     rcx, rbx; unsigned __int64
0x1800274e9  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800274ee  mov     r12, rax
0x1800274f1  test    rax, rax
0x1800274f4  jnz     short loc_180027500
0x1800274f6  mov     edi, 8007000Eh
0x1800274fb  jmp     loc_18002759E
0x180027500  mov     qword ptr [rsp+310h+dwCreationDisposition], 0; lpOverlapped
0x180027509  lea     r9, [rsp+310h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002750e  mov     r8d, ebx; nNumberOfBytesToRead
0x180027511  mov     rdx, r12; lpBuffer
0x180027514  mov     rcx, r15; hFile
0x180027517  call    cs:__imp_ReadFile
0x18002751d  test    eax, eax
0x18002751f  jnz     short loc_18002753A
0x180027521  call    cs:__imp_GetLastError
0x180027527  mov     esi, eax
0x180027529  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002752e  lea     r13, aSReadingOpened; "%s: Reading opened secret file failed w"...
0x180027535  jmp     loc_180027479
0x18002753a  mov     eax, [rsp+310h+NumberOfBytesRead]
0x18002753e  mov     byte ptr [rax+r12], 0
0x180027543  lea     r9, [rsp+310h+var_2D0]; unsigned int *
0x180027548  lea     r8, [rsp+310h+var_2C8]; unsigned __int16 **
  ... truncated ...
```
