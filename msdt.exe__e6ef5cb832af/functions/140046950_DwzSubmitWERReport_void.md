# DwzSubmitWERReport(void)

- ea: `0x140046950`
- end: `0x140046dfc`
- name: `?DwzSubmitWERReport@@YAJXZ`
- size: `1196`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x14003eb60`

## callees

- `0x1400039b1`
- `0x14000706c`
- `0x140020420`
- `0x140022070`
- `0x1400404f4`
- `0x140041578`
- `0x140041c54`
- `0x140043a14`
- `0x140044e6c`
- `0x140046950`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140046b1c`
- `KERNEL32!GetLastError` at `0x140046b1c`
- `KERNEL32!HeapAlloc` at `0x140046a0b`
- `KERNEL32!HeapAlloc` at `0x140046a60`
- `KERNEL32!HeapAlloc` at `0x140046ab4`
- `KERNEL32!HeapAlloc` at `0x140046a0b`
- `KERNEL32!HeapAlloc` at `0x140046a60`
- `KERNEL32!HeapAlloc` at `0x140046ab4`
- `KERNEL32!HeapFree` at `0x140046d75`
- `KERNEL32!HeapFree` at `0x140046d95`
- `KERNEL32!HeapFree` at `0x140046db5`
- `KERNEL32!HeapFree` at `0x140046d75`
- `KERNEL32!HeapFree` at `0x140046d95`
- `KERNEL32!HeapFree` at `0x140046db5`
- `KERNEL32!GetProcessHeap` at `0x1400469f2`
- `KERNEL32!GetProcessHeap` at `0x140046a4c`
- `KERNEL32!GetProcessHeap` at `0x140046aa0`
- `KERNEL32!GetProcessHeap` at `0x140046d61`
- `KERNEL32!GetProcessHeap` at `0x140046d81`
- `KERNEL32!GetProcessHeap` at `0x140046da1`
- `KERNEL32!GetProcessHeap` at `0x1400469f2`
- `KERNEL32!GetProcessHeap` at `0x140046a4c`
- `KERNEL32!GetProcessHeap` at `0x140046aa0`
- `KERNEL32!GetProcessHeap` at `0x140046d61`
- `KERNEL32!GetProcessHeap` at `0x140046d81`
- `KERNEL32!GetProcessHeap` at `0x140046da1`
- `KERNEL32!GetFullPathNameW` at `0x140046c62`
- `KERNEL32!GetFullPathNameW` at `0x140046c62`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140046b0c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140046b0c`
- `wer!WerReportAddFile` at `0x140046cdf`
- `wer!WerReportAddFile` at `0x140046cdf`
- `wer!WerReportSubmit` at `0x140046d10`
- `wer!WerReportSubmit` at `0x140046d10`
- `wer!WerReportCloseHandle` at `0x140046dce`
- `wer!WerReportCloseHandle` at `0x140046dce`
- `wer!WerReportCreate` at `0x140046ba8`
- `wer!WerReportCreate` at `0x140046ba8`

## string_xrefs

- `0x140046af6`: `%systemroot%\system32\msdt.exe`

## pseudocode

```c
__int64 DwzSubmitWERReport(void)
{
  signed int v0; // ebx
  HREPORT v1; // rdi
  HANDLE ProcessHeap; // rax
  LPWSTR v3; // r14
  HANDLE v4; // rax
  char *v5; // rdi
  HANDLE v6; // rax
  WCHAR *v7; // rsi
  signed int LastError; // eax
  int v9; // r9d
  int v10; // eax
  int LocalString; // eax
  HRESULT v12; // eax
  int v13; // eax
  int TemporaryFileName; // eax
  int v15; // eax
  unsigned __int64 v16; // rax
  int HistoryDirectory; // eax
  unsigned __int16 *v18; // r8
  int CabFromPath; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HREPORT phReportHandle; // [rsp+30h] [rbp-D0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+50h] [rbp-B0h] BYREF

  v0 = 0;
  v1 = 0;
  phReportHandle = 0;
  pSubmitResult = 0;
  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  FilePart = 0;
  v29 = 0;
  g_ErrorContext = 405;
  if ( !dword_140080158 && !*((_DWORD *)Config + 10) && (*((_DWORD *)Config + 16) || *((_DWORD *)Config + 66) == 9) )
  {
    memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
    pReportInformation.dwSize = 2208;
    ProcessHeap = GetProcessHeap();
    v3 = (LPWSTR)HeapAlloc(ProcessHeap, 0, 0x208u);
    if ( !v3 )
    {
      v0 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 986, -2147024882);
LABEL_46:
      v1 = phReportHandle;
      goto LABEL_47;
    }
    v4 = GetProcessHeap();
    v5 = (char *)HeapAlloc(v4, 0, 0x208u);
    if ( !v5 )
    {
      v0 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 987, -2147024882);
LABEL_45:
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v3);
      goto LABEL_46;
    }
    v6 = GetProcessHeap();
    v7 = (WCHAR *)HeapAlloc(v6, 0, 0x208u);
    if ( !v7 )
    {
      v0 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 988, -2147024882);
LABEL_44:
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v5);
      goto LABEL_45;
    }
    *v7 = 0;
    if ( !ExpandEnvironmentStringsW(L"%systemroot%\\system32\\msdt.exe", v7, 0x104u) )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      if ( v0 < 0 )
      {
        v9 = 998;
LABEL_42:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", v9, v0);
        goto LABEL_43;
      }
    }
    v10 = StringCchCopyW(pReportInformation.wzApplicationPath, 0x104u, v7);
    v0 = v10;
    if ( v10 >= 0 )
    {
      LocalString = DwzLoadLocalString(0x89u, pReportInformation.wzFriendlyEventName, 0x80u);
      v0 = LocalString;
      if ( LocalString >= 0 )
      {
        v12 = WerReportCreate(L"ScriptedDiagFailure", WerReportNonCritical, &pReportInformation, &phReportHandle);
        v0 = v12;
        if ( v12 >= 0 )
        {
          v13 = DwzAddWERParameters(phReportHandle);
          v0 = v13;
          if ( v13 >= 0 )
          {
            TemporaryFileName = GetTemporaryFileName((LPWSTR)v5);
            v0 = TemporaryFileName;
            if ( TemporaryFileName >= 0 )
            {
              v15 = StringCchLengthW((const unsigned __int16 *)v5, 0x104u, &v29);
              v0 = v15;
              if ( v15 >= 0 )
              {
                v16 = v29;
                if ( v29 >= 4 )
                {
                  *(_DWORD *)&v5[2 * v29 - 6] = 6357091;
                  *(_WORD *)&v5[2 * v16 - 2] = 98;
                  if ( GetFullPathNameW((LPCWSTR)v5, 0x104u, v3, &FilePart) - 1 <= 0x103 && FilePart > v3 )
                  {
                    *(FilePart - 1) = 0;
                    HistoryDirectory = MakeHistoryDirectory(0);
                    v0 = HistoryDirectory;
                    if ( HistoryDirectory >= 0 )
                    {
                      CabFromPath = CreateCabFromPath(v3, FilePart, v18, 0);
                      v0 = CabFromPath;
                      if ( CabFromPath >= 0 )
                      {
                        v20 = WerReportAddFile(phReportHandle, (PCWSTR)v5, WerFileTypeOther, 3u);
                        v0 = v20;
                        if ( v20 >= 0 )
                        {
                          v21 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 4u, &pSubmitResult);
                          v0 = v21;
                          if ( v21 >= 0 )
                            dword_140080158 = 1;
                          else
                            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1075, v21);
                        }
                        else
                        {
                          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1072, v20);
                        }
                      }
                      else
                      {
                        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1065, CabFromPath);
                      }
                    }
                    else
                    {
                      SdpDebugPrint(
                        1u,
                        "Dwz ERROR: %s:%d - hr = 0x%08X\n",
                        "DwzSubmitWERReport",
                        1062,
                        HistoryDirectory);
                    }
                    goto LABEL_43;
                  }
                  v0 = -2147319786;
                  v9 = 1052;
                }
                else
                {
                  v0 = -2147467259;
                  v9 = 1038;
                }
                goto LABEL_42;
              }
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1034, v15);
            }
            else
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1028, TemporaryFileName);
            }
          }
          else
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1025, v13);
          }
        }
        else
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1019, v12);
        }
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1016, LocalString);
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzSubmitWERReport", 1007, v10);
    }
LABEL_43:
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v7);
    goto LABEL_44;
  }
LABEL_47:
  if ( v1 )
    WerReportCloseHandle(v1);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140046950  push    rbp
0x140046952  push    rbx
0x140046953  push    rsi
0x140046954  push    rdi
0x140046955  push    r12
0x140046957  push    r14
0x140046959  lea     rbp, [rsp-808h]
0x140046961  sub     rsp, 908h
0x140046968  mov     rax, cs:__security_cookie
0x14004696f  xor     rax, rsp
0x140046972  mov     [rbp+830h+var_40], rax
0x140046979  mov     esi, 8A0h
0x14004697e  lea     rcx, [rsp+930h+pReportInformation]; void *
0x140046983  xor     ebx, ebx
0x140046985  xor     edi, edi
0x140046987  mov     r8d, esi; Size
0x14004698a  mov     [rsp+930h+phReportHandle], rdi
0x14004698f  xor     edx, edx; Val
0x140046991  mov     [rsp+930h+pSubmitResult], ebx
0x140046995  call    memset_0
0x14004699a  cmp     cs:dword_140080158, ebx
0x1400469a0  mov     [rsp+930h+FilePart], rbx
0x1400469a5  mov     [rsp+930h+var_8E8], rbx
0x1400469aa  mov     cs:?g_ErrorContext@@3IC, 195h; uint volatile g_ErrorContext
0x1400469b4  jnz     loc_140046DC6
0x1400469ba  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400469c1  cmp     [rax+28h], ebx
0x1400469c4  jnz     loc_140046DC6
0x1400469ca  cmp     [rax+40h], ebx
0x1400469cd  jnz     short loc_1400469DC
0x1400469cf  cmp     dword ptr [rax+108h], 9
0x1400469d6  jnz     loc_140046DC6
0x1400469dc  xor     edx, edx; Val
0x1400469de  lea     rcx, [rsp+930h+pReportInformation+4]; void *
0x1400469e3  mov     r8d, 89Ch; Size
0x1400469e9  call    memset_0
0x1400469ee  mov     [rsp+930h+pReportInformation.dwSize], esi
0x1400469f2  call    cs:__imp_GetProcessHeap
0x1400469f9  nop     dword ptr [rax+rax+00h]
0x1400469fe  mov     ebx, 208h
0x140046a03  xor     edx, edx; dwFlags
0x140046a05  mov     rcx, rax; hHeap
0x140046a08  mov     r8d, ebx; dwBytes
0x140046a0b  call    cs:__imp_HeapAlloc
0x140046a12  nop     dword ptr [rax+rax+00h]
0x140046a17  mov     r14, rax
0x140046a1a  test    rax, rax
0x140046a1d  jnz     short loc_140046A4C
0x140046a1f  mov     eax, 8007000Eh
0x140046a24  lea     r8, aDwzsubmitwerre; "DwzSubmitWERReport"
0x140046a2b  mov     r9d, 3DAh
0x140046a31  mov     [rsp+930h+var_910], eax
0x140046a35  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140046a3c  mov     ebx, eax
0x140046a3e  lea     ecx, [r14+1]; Level
0x140046a42  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140046a47  jmp     loc_140046DC1
0x140046a4c  call    cs:__imp_GetProcessHeap
0x140046a53  nop     dword ptr [rax+rax+00h]
0x140046a58  mov     r8, rbx; dwBytes
0x140046a5b  xor     edx, edx; dwFlags
0x140046a5d  mov     rcx, rax; hHeap
0x140046a60  call    cs:__imp_HeapAlloc
0x140046a67  nop     dword ptr [rax+rax+00h]
0x140046a6c  mov     rdi, rax
0x140046a6f  test    rax, rax
0x140046a72  jnz     short loc_140046AA0
0x140046a74  mov     eax, 8007000Eh
0x140046a79  lea     r8, aDwzsubmitwerre; "DwzSubmitWERReport"
0x140046a80  mov     r9d, 3DBh
0x140046a86  mov     [rsp+930h+var_910], eax
0x140046a8a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140046a91  mov     ebx, eax
0x140046a93  lea     ecx, [rdi+1]; Level
0x140046a96  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140046a9b  jmp     loc_140046DA1
0x140046aa0  call    cs:__imp_GetProcessHeap
0x140046aa7  nop     dword ptr [rax+rax+00h]
0x140046aac  mov     r8, rbx; dwBytes
0x140046aaf  xor     edx, edx; dwFlags
0x140046ab1  mov     rcx, rax; hHeap
0x140046ab4  call    cs:__imp_HeapAlloc
0x140046abb  nop     dword ptr [rax+rax+00h]
0x140046ac0  mov     rsi, rax
0x140046ac3  test    rax, rax
0x140046ac6  jnz     short loc_140046AF4
0x140046ac8  mov     eax, 8007000Eh
0x140046acd  lea     r8, aDwzsubmitwerre; "DwzSubmitWERReport"
0x140046ad4  mov     r9d, 3DCh
0x140046ada  mov     [rsp+930h+var_910], eax
0x140046ade  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140046ae5  mov     ebx, eax
0x140046ae7  lea     ecx, [rsi+1]; Level
0x140046aea  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140046aef  jmp     loc_140046D81
0x140046af4  xor     eax, eax
0x140046af6  lea     rcx, aSystemrootSyst; "%systemroot%\\system32\\msdt.exe"
0x140046afd  mov     r12d, 104h
0x140046b03  mov     [rsi], ax
0x140046b06  mov     r8d, r12d; nSize
0x140046b09  mov     rdx, rsi; lpDst
0x140046b0c  call    cs:__imp_ExpandEnvironmentStringsW
0x140046b13  nop     dword ptr [rax+rax+00h]
0x140046b18  test    eax, eax
0x140046b1a  jnz     short loc_140046B46
0x140046b1c  call    cs:__imp_GetLastError
0x140046b23  nop     dword ptr [rax+rax+00h]
0x140046b28  mov     ebx, eax
0x140046b2a  test    eax, eax
0x140046b2c  jle     short loc_140046B37
0x140046b2e  movzx   ebx, ax
0x140046b31  or      ebx, 80070000h
0x140046b37  test    ebx, ebx
0x140046b39  jns     short loc_140046B46
0x140046b3b  mov     r9d, 3E6h
0x140046b41  jmp     loc_140046D45
0x140046b46  mov     r8, rsi; unsigned __int16 *
0x140046b49  lea     rcx, [rbp+830h+pReportInformation.wzApplicationPath]; unsigned __int16 *
0x140046b50  mov     rdx, r12; unsigned __int64
0x140046b53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140046b58  mov     ebx, eax
0x140046b5a  test    eax, eax
0x140046b5c  jns     short loc_140046B6D
0x140046b5e  mov     [rsp+930h+var_910], eax
0x140046b62  mov     r9d, 3EFh
0x140046b68  jmp     loc_140046D49
0x140046b6d  mov     r8d, 80h; cchBufferMax
0x140046b73  lea     rdx, [rbp+830h+pReportInformation.wzFriendlyEventName]; lpBuffer
0x140046b77  lea     ecx, [r8+9]; uID
0x140046b7b  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x140046b80  mov     ebx, eax
0x140046b82  test    eax, eax
0x140046b84  jns     short loc_140046B95
0x140046b86  mov     [rsp+930h+var_910], eax
0x140046b8a  mov     r9d, 3F8h
0x140046b90  jmp     loc_140046D49
0x140046b95  lea     r9, [rsp+930h+phReportHandle]; phReportHandle
0x140046b9a  xor     edx, edx; repType
0x140046b9c  lea     r8, [rsp+930h+pReportInformation]; pReportInformation
0x140046ba1  lea     rcx, pwzEventType; "ScriptedDiagFailure"
0x140046ba8  call    cs:__imp_WerReportCreate
0x140046baf  nop     dword ptr [rax+rax+00h]
0x140046bb4  mov     ebx, eax
0x140046bb6  test    eax, eax
0x140046bb8  jns     short loc_140046BC9
0x140046bba  mov     [rsp+930h+var_910], eax
0x140046bbe  mov     r9d, 3FBh
0x140046bc4  jmp     loc_140046D49
0x140046bc9  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x140046bce  call    ?DwzAddWERParameters@@YAJPEAX@Z; DwzAddWERParameters(void *)
0x140046bd3  mov     ebx, eax
0x140046bd5  test    eax, eax
0x140046bd7  jns     short loc_140046BE8
0x140046bd9  mov     [rsp+930h+var_910], eax
0x140046bdd  mov     r9d, 401h
0x140046be3  jmp     loc_140046D49
0x140046be8  mov     rcx, rdi; lpTempFileName
0x140046beb  call    ?GetTemporaryFileName@@YAJPEAG@Z; GetTemporaryFileName(ushort *)
0x140046bf0  mov     ebx, eax
0x140046bf2  test    eax, eax
0x140046bf4  jns     short loc_140046C05
0x140046bf6  mov     [rsp+930h+var_910], eax
0x140046bfa  mov     r9d, 404h
0x140046c00  jmp     loc_140046D49
0x140046c05  lea     r8, [rsp+930h+var_8E8]; unsigned __int64 *
0x140046c0a  mov     rdx, r12; unsigned __int64
0x140046c0d  mov     rcx, rdi; unsigned __int16 *
0x140046c10  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140046c15  mov     ebx, eax
0x140046c17  test    eax, eax
0x140046c19  jns     short loc_140046C2A
0x140046c1b  mov     [rsp+930h+var_910], eax
0x140046c1f  mov     r9d, 40Ah
0x140046c25  jmp     loc_140046D49
0x140046c2a  mov     rax, [rsp+930h+var_8E8]
0x140046c2f  cmp     rax, 4
0x140046c33  jnb     short loc_140046C45
0x140046c35  mov     ebx, 80004005h
0x140046c3a  mov     r9d, 40Eh
0x140046c40  jmp     loc_140046D45
0x140046c45  mov     dword ptr [rdi+rax*2-6], 610063h
0x140046c4d  lea     r9, [rsp+930h+FilePart]; lpFilePart
0x140046c52  mov     r8, r14; lpBuffer
0x140046c55  mov     word ptr [rdi+rax*2-2], 62h ; 'b'
0x140046c5c  mov     edx, r12d; nBufferLength
0x140046c5f  mov     rcx, rdi; lpFileName
0x140046c62  call    cs:__imp_GetFullPathNameW
0x140046c69  nop     dword ptr [rax+rax+00h]
0x140046c6e  dec     eax
0x140046c70  cmp     eax, 103h
0x140046c75  ja      loc_140046D3A
0x140046c7b  mov     rcx, [rsp+930h+FilePart]
0x140046c80  cmp     rcx, r14
0x140046c83  jbe     loc_140046D3A
0x140046c89  xor     eax, eax
0x140046c8b  mov     [rcx-2], ax
0x140046c8f  xor     ecx, ecx; int
0x140046c91  call    ?MakeHistoryDirectory@@YAJH@Z; MakeHistoryDirectory(int)
0x140046c96  mov     ebx, eax
0x140046c98  test    eax, eax
0x140046c9a  jns     short loc_140046CAB
0x140046c9c  mov     [rsp+930h+var_910], eax
0x140046ca0  mov     r9d, 426h
0x140046ca6  jmp     loc_140046D49
0x140046cab  mov     rdx, [rsp+930h+FilePart]; unsigned __int16 *
0x140046cb0  xor     r9d, r9d; int
0x140046cb3  mov     rcx, r14; unsigned __int16 *
0x140046cb6  call    ?CreateCabFromPath@@YAJPEBG0PEAGH@Z; CreateCabFromPath(ushort const *,ushort const *,ushort *,int)
0x140046cbb  mov     ebx, eax
0x140046cbd  test    eax, eax
0x140046cbf  jns     short loc_140046CCD
0x140046cc1  mov     [rsp+930h+var_910], eax
0x140046cc5  mov     r9d, 429h
0x140046ccb  jmp     short loc_140046D49
0x140046ccd  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x140046cd2  mov     r9d, 3; dwFileFlags
0x140046cd8  mov     rdx, rdi; pwzPath
0x140046cdb  lea     r8d, [r9+2]; repFileType
0x140046cdf  call    cs:__imp_WerReportAddFile
0x140046ce6  nop     dword ptr [rax+rax+00h]
0x140046ceb  mov     ebx, eax
0x140046ced  test    eax, eax
0x140046cef  jns     short loc_140046CFD
0x140046cf1  mov     [rsp+930h+var_910], eax
0x140046cf5  mov     r9d, 430h
0x140046cfb  jmp     short loc_140046D49
0x140046cfd  mov     rcx, [rsp+930h+phReportHandle]; hReportHandle
0x140046d02  lea     r9, [rsp+930h+pSubmitResult]; pSubmitResult
0x140046d07  mov     edx, 1; consent
0x140046d0c  lea     r8d, [rdx+3]; dwFlags
0x140046d10  call    cs:__imp_WerReportSubmit
0x140046d17  nop     dword ptr [rax+rax+00h]
0x140046d1c  mov     ebx, eax
0x140046d1e  test    eax, eax
0x140046d20  jns     short loc_140046D2E
0x140046d22  mov     [rsp+930h+var_910], eax
0x140046d26  mov     r9d, 433h
0x140046d2c  jmp     short loc_140046D49
0x140046d2e  mov     cs:dword_140080158, 1
0x140046d38  jmp     short loc_140046D61
0x140046d3a  mov     ebx, 80028016h
0x140046d3f  mov     r9d, 41Ch
0x140046d45  mov     [rsp+930h+var_910], ebx
0x140046d49  lea     r8, aDwzsubmitwerre; "DwzSubmitWERReport"
0x140046d50  mov     ecx, 1; Level
0x140046d55  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140046d5c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140046d61  call    cs:__imp_GetProcessHeap
0x140046d68  nop     dword ptr [rax+rax+00h]
0x140046d6d  mov     r8, rsi; lpMem
0x140046d70  xor     edx, edx; dwFlags
0x140046d72  mov     rcx, rax; hHeap
0x140046d75  call    cs:__imp_HeapFree
0x140046d7c  nop     dword ptr [rax+rax+00h]
0x140046d81  call    cs:__imp_GetProcessHeap
0x140046d88  nop     dword ptr [rax+rax+00h]
0x140046d8d  mov     r8, rdi; lpMem
0x140046d90  xor     edx, edx; dwFlags
0x140046d92  mov     rcx, rax; hHeap
0x140046d95  call    cs:__imp_HeapFree
0x140046d9c  nop     dword ptr [rax+rax+00h]
0x140046da1  call    cs:__imp_GetProcessHeap
0x140046da8  nop     dword ptr [rax+rax+00h]
0x140046dad  mov     r8, r14; lpMem
0x140046db0  xor     edx, edx; dwFlags
0x140046db2  mov     rcx, rax; hHeap
0x140046db5  call    cs:__imp_HeapFree
0x140046dbc  nop     dword ptr [rax+rax+00h]
0x140046dc1  mov     rdi, [rsp+930h+phReportHandle]
0x140046dc6  test    rdi, rdi
0x140046dc9  jz      short loc_140046DDA
0x140046dcb  mov     rcx, rdi; hReportHandle
0x140046dce  call    cs:__imp_WerReportCloseHandle
0x140046dd5  nop     dword ptr [rax+rax+00h]
0x140046dda  mov     eax, ebx
0x140046ddc  mov     rcx, [rbp+830h+var_40]
0x140046de3  xor     rcx, rsp; StackCookie
0x140046de6  call    __security_check_cookie
0x140046deb  add     rsp, 908h
0x140046df2  pop     r14
0x140046df4  pop     r12
0x140046df6  pop     rdi
0x140046df7  pop     rsi
0x140046df8  pop     rbx
0x140046df9  pop     rbp
0x140046dfa  retn
```
