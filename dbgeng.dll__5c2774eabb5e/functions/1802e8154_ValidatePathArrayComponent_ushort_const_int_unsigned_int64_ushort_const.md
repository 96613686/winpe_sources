# ValidatePathArrayComponent(ushort const *,int,unsigned __int64,ushort const *)

- ea: `0x1802e8154`
- end: `0x1802e891c`
- name: `?ValidatePathArrayComponent@@YAHPEBGH_K0@Z`
- size: `1992`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802e2e34`

## callees

- `0x1800727b8`
- `0x18007daa4`
- `0x180098468`
- `0x1800986ec`
- `0x1800a7e58`
- `0x1800c12b8`
- `0x1800e5a38`
- `0x1800f0f40`
- `0x1800f13ec`
- `0x1800f16fc`
- `0x1800f1720`
- `0x1802bdf98`
- `0x1802e2354`
- `0x1802e52f0`
- `0x1802e5340`
- `0x1802e8154`
- `0x1802ea6c8`
- `0x18041c610`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e8267`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e828b`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e82af`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e8267`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e828b`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e82af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e868f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e878e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e87bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e880b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e868f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e878e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e87bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802e880b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802e8605`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802e8605`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802e86ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802e8839`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802e86ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802e8839`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802e8853`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802e8853`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1802e8558`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1802e8558`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1802e8582`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1802e8582`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1802e864b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1802e870f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1802e864b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1802e870f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1802e84a6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1802e84a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e85a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e875a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e85a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e875a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e82f1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e82f1`

## string_xrefs

- `0x1802e82a5`: `CACHE*`
- `0x1802e84f2`: `WARNING: Network path disallowed: '%s'\n`
- `0x1802e8355`: `WARNING: Unable to net-check path: '%s'\n`
- `0x1802e8361`: `WARNING: Invalid path disallowed: '%s'\n`
- `0x1802e81dd`: `Error: Cannot allocate the Validation Path status block.\n`
- `0x1802e88e3`: `Error: Empty Path.\n`
- `0x1802e836a`: `WARNING: Network paths disallowed '%s'\n`
- `0x1802e8523`: `Error: Invalid Path length: %s.\n`
- `0x1802e844f`: `Error: Not enough memory to create the validation thread data for: '%s'\n`
- `0x1802e838e`: `WARNING: We won't validate this path (system process): '%s'\n`
- `0x1802e8534`: `Error: Invalid number of Threads. Path validation failed.\n`
- `0x1802e84c3`: `Error: Unable to create the validation thread for: '%s'\n`
- `0x1802e87d9`: `Warning: Thread validation still active.\n`
- `0x1802e8592`: `Error: The thread could not be resumed.\n`
- `0x1802e8820`: `Error: The working thread timed out\n`
- `0x1802e87f8`: `Thread still active`
- `0x1802e87aa`: `Error: The working thread timed out for validating: '%s'\n`
- `0x1802e871f`: `Warning: Unable to get the thread termination status.\n`
- `0x1802e8667`: `Thread failed`
- `0x1802e87d0`: `Error: The thread waiting function failed\n`
- `0x1802e8861`: `\n************* Path validation summary **************\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidatePathArrayComponent(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v5; // r14
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rax
  char *v8; // rax
  char *v9; // rsi
  unsigned int v10; // r13d
  _QWORD *v11; // rbx
  unsigned __int64 v12; // r12
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  unsigned int v15; // eax
  WCHAR *v16; // rdx
  const unsigned __int16 *v17; // rcx
  _QWORD *v18; // rdi
  HANDLE Thread; // rax
  char *v20; // rbx
  unsigned __int64 i; // r14
  void *v22; // rcx
  char *v23; // rbx
  unsigned __int64 v24; // r12
  int v25; // r13d
  unsigned int v26; // r14d
  DWORD v27; // eax
  void *v29; // rcx
  const struct std::nothrow_t *v30; // rdx
  char *v31; // rbx
  __int64 v32; // r8
  wchar_t *v33; // rdx
  _QWORD *ExitCode; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v36; // [rsp+48h] [rbp-C0h]
  const unsigned __int16 *v37; // [rsp+50h] [rbp-B8h]
  __int64 v38; // [rsp+58h] [rbp-B0h]
  WCHAR Dst[520]; // [rsp+68h] [rbp-A0h] BYREF

  v38 = -2;
  v37 = a4;
  v5 = a1;
  v6 = 0;
  if ( !a1 || !*a1 || !a3 )
  {
    dprintf(L"Error: Empty Path.\n");
    return 0;
  }
  v7 = 1664 * a3;
  if ( !is_mul_ok(a3, 0x680u) )
    v7 = -1;
  v8 = (char *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    dprintf(L"Error: Cannot allocate the Validation Path status block.\n");
    return 0;
  }
  v10 = 0;
  LODWORD(v35) = 0;
  memset(v8, 0, 1664 * a3);
  v11 = v9;
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    v36 = v13;
    if ( v13 >= a3 || !v11 )
      break;
    v14 = -1;
    do
      ++v14;
    while ( v5[v14] );
    if ( v14 > 0x104 )
    {
      dprintf(L"Error: Invalid Path length: %s.\n", v5);
      break;
    }
    v11[133] = v9;
    CopyNStringW(v11);
    if ( !_wcsnicmp((const wchar_t *)v11, L"SYMSRV*", 7u)
      || !_wcsnicmp((const wchar_t *)v11, L"SRV*", 4u)
      || !_wcsnicmp((const wchar_t *)v11, L"CACHE*", 6u)
      || IsSourceServerPathComponent((wchar_t *)v11)
      || (unsigned int)DbgClientLibIsUrlPathComponent((wchar_t *)v11) )
    {
      if ( (g_EngOptions & 8) == 0 )
        goto LABEL_49;
      v16 = (WCHAR *)v11;
      goto LABEL_47;
    }
    if ( !ExpandEnvironmentStringsW((LPCWSTR)v11, Dst, 0x208u) )
    {
      dprintf(L"WARNING: Environment expansion failed: '%s'\n", v11);
      *((_WORD *)v11 + 528) |= 2u;
      *((_DWORD *)v11 + 269) = 2;
      goto LABEL_50;
    }
    if ( (g_EngOptions & 8) != 0 )
    {
      v15 = NetworkPathCheck(Dst);
      if ( v15 )
      {
        if ( v15 != 161 )
        {
          v16 = Dst;
          if ( v15 != 4350 )
          {
            dprintf(L"WARNING: Unable to net-check path: '%s'\n", Dst);
LABEL_49:
            *((_DWORD *)v11 + 269) = 2;
            goto LABEL_50;
          }
LABEL_47:
          v17 = L"WARNING: Network path disallowed: '%s'\n";
LABEL_48:
          dprintf(v17, v16);
          goto LABEL_49;
        }
        v17 = L"WARNING: Invalid path disallowed: '%s'\n";
      }
      else
      {
        v17 = L"WARNING: Network paths disallowed '%s'\n";
      }
      v16 = Dst;
      goto LABEL_48;
    }
    if ( (unsigned int)AnySystemProcesses(1) )
    {
      dprintf(L"WARNING: We won't validate this path (system process): '%s'\n", Dst);
      *((_WORD *)v11 + 528) |= 4u;
      goto LABEL_49;
    }
    memset(v11, 0, 0x412u);
    CopyNStringW(v11);
    if ( NetworkPathCheck((const unsigned __int16 *)v11) == 4350 && !IsPathNetworkMappedDrive((LPCWSTR)v11) )
    {
      if ( !(unsigned int)IsSupportedUNCPath((struct PATH_VAL_BLK *)v11) )
        goto LABEL_50;
      *((_WORD *)v11 + 528) |= 8u;
    }
    v18 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    ExitCode = v18;
    if ( v18 )
    {
      *v18 = 0;
      v18[1] = 0;
      v18[2] = 0;
      *((_WORD *)v18 + 12) = 256;
      *((_DWORD *)v18 + 7) = 64;
    }
    else
    {
      v18 = 0;
    }
    ExitCode = v18;
    if ( v18 && (*v18 = v11, DbsDynamicString<unsigned short>::CopyStr(v18 + 1, v37, 0xFFFFFFFFLL)) )
    {
      Thread = CreateThread(0, 0, ValidatePathThreadProc, v18, 4u, 0);
      v11[131] = Thread;
      v6 = 0;
      if ( Thread )
      {
        ExitCode = 0;
        ++v12;
      }
      else
      {
        dprintf(L"Error: Unable to create the validation thread for: '%s'\n", v11);
      }
      DbsDeletePtr<ValidatePathThreadProcData>::~DbsDeletePtr<ValidatePathThreadProcData>(&ExitCode);
    }
    else
    {
      dprintf(L"Error: Not enough memory to create the validation thread data for: '%s'\n", v11);
      DbsDeletePtr<ValidatePathThreadProcData>::~DbsDeletePtr<ValidatePathThreadProcData>(&ExitCode);
      v6 = 0;
    }
LABEL_50:
    v13 = v36 + 1;
    v11 += 208;
    v5 += 261;
  }
  if ( v12 <= a3 )
  {
    if ( !v12 )
      goto LABEL_103;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
    *((_DWORD *)v9 + 270) = v12;
    v20 = v9;
    for ( i = 0; i < a3; v20 += 1664 )
    {
      v22 = (void *)*((_QWORD *)v20 + 131);
      if ( v22 && !ResumeThread(v22) )
      {
        dprintf(L"Error: The thread could not be resumed.\n");
        CloseHandle(*((HANDLE *)v20 + 131));
        *((_QWORD *)v20 + 131) = 0;
      }
      ++i;
    }
    v23 = v9;
    v24 = 0;
LABEL_61:
    if ( v24 >= a3 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
      v6 = 0;
      goto LABEL_103;
    }
    if ( !*((_QWORD *)v23 + 131) )
      goto LABEL_91;
    v25 = 1;
    v26 = 0;
    while ( 1 )
    {
      LODWORD(ExitCode) = 0;
      v27 = WaitForSingleObject(*((HANDLE *)v23 + 131), 0x3E8u);
      if ( !v27 )
      {
        if ( GetExitCodeThread(*((HANDLE *)v23 + 131), (LPDWORD)&ExitCode) )
        {
          if ( (_DWORD)ExitCode == 259 )
          {
            dprintf(L"Warning: Thread validation still active.\n");
            if ( (v23[1056] & 1) == 0 )
              *((_DWORD *)v23 + 269) = 0;
            PrintLastError((int)ExitCode, L"Thread still active");
            EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
            if ( !*((_DWORD *)v23 + 272) )
            {
              dprintf(L"Error: The working thread timed out\n");
LABEL_100:
              *((_DWORD *)v9 + 271) = 1;
            }
LABEL_101:
            LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
            return 1;
          }
        }
        else
        {
          dprintf(L"Warning: Unable to get the thread termination status.\n");
        }
        if ( (v23[1056] & 1) == 0 )
          *((_DWORD *)v23 + 269) = 0;
LABEL_88:
        v29 = (void *)*((_QWORD *)v23 + 131);
        if ( v29 )
        {
          CloseHandle(v29);
          *((_QWORD *)v23 + 131) = 0;
        }
        v10 = 1;
        LODWORD(v35) = 1;
LABEL_91:
        ++v24;
        v23 += 1664;
        goto LABEL_61;
      }
      if ( v27 != 128 )
      {
        if ( v27 == 258 )
        {
          if ( CheckUserInterruptInternal(0) )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
            if ( *((_DWORD *)v23 + 272) )
            {
              v25 = 0;
            }
            else
            {
              *((_DWORD *)v9 + 271) = 1;
              WarnOut(L" -- User interrupt\n");
              LODWORD(v35) = 1;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
            if ( (_DWORD)v35 )
              return (unsigned int)v35;
          }
          else
          {
            if ( v26 >= 0x1D4C0 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
              if ( !*((_DWORD *)v23 + 272) )
              {
                dprintf(L"Error: The working thread timed out for validating: '%s'\n", v23);
                goto LABEL_100;
              }
              goto LABEL_101;
            }
            v26 += 1000;
          }
          goto LABEL_72;
        }
        if ( v27 != -1 )
          goto LABEL_72;
      }
      if ( (v23[1056] & 1) == 0 )
        *((_DWORD *)v23 + 269) = 0;
      GetExitCodeThread(*((HANDLE *)v23 + 131), (LPDWORD)&ExitCode);
      if ( (_DWORD)ExitCode == 259 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1096));
        if ( !*((_DWORD *)v23 + 272) )
        {
          dprintf(L"Error: The thread waiting function failed\n");
          goto LABEL_100;
        }
        goto LABEL_101;
      }
      PrintLastError((int)ExitCode, L"Thread failed");
LABEL_72:
      if ( !v25 )
        goto LABEL_88;
    }
  }
  dprintf(L"Error: Invalid number of Threads. Path validation failed.\n");
LABEL_103:
  WarnOut(L"\n************* Path validation summary **************\n");
  WarnOut(L"Response                         Time (ms)     Location\n");
  v31 = v9;
  if ( a3 )
  {
    do
    {
      if ( !v31 )
        break;
      v32 = *((unsigned int *)v31 + 268);
      v33 = (&off_18079C508)[2 * *((int *)v31 + 269)];
      if ( (_DWORD)v32 )
        WarnOut(L"%-32.32s %-13d %s\n", v33, v32, v31);
      else
        WarnOut(L"%-46.46s %s\n", v33, v31);
      ++v6;
      v31 += 1664;
    }
    while ( v6 < a3 );
  }
  operator delete(v9, v30);
  return v10;
}

```

## disassembly

```asm
0x1802e8154  mov     rax, rsp
0x1802e8157  push    rbp
0x1802e8158  push    rsi
0x1802e8159  push    rdi
0x1802e815a  push    r12
0x1802e815c  push    r13
0x1802e815e  push    r14
0x1802e8160  push    r15
0x1802e8162  lea     rbp, [rax-3B8h]
0x1802e8169  sub     rsp, 480h
0x1802e8170  mov     [rsp+4B0h+var_460], 0FFFFFFFFFFFFFFFEh
0x1802e8179  mov     [rax+10h], rbx
0x1802e817d  mov     rax, cs:__security_cookie
0x1802e8184  xor     rax, rsp
0x1802e8187  mov     [rbp+3B0h+var_40], rax
0x1802e818e  mov     [rsp+4B0h+var_468], r9
0x1802e8193  mov     r15, r8
0x1802e8196  mov     r14, rcx
0x1802e8199  xor     edi, edi
0x1802e819b  test    rcx, rcx
0x1802e819e  jz      loc_1802E88E3
0x1802e81a4  cmp     [rcx], di
0x1802e81a7  jz      loc_1802E88E3
0x1802e81ad  test    r8, r8
0x1802e81b0  jz      loc_1802E88E3
0x1802e81b6  mov     eax, 680h
0x1802e81bb  mul     r15
0x1802e81be  lea     rcx, [rdi-1]
0x1802e81c2  cmovb   rax, rcx
0x1802e81c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802e81cd  mov     rcx, rax; unsigned __int64
0x1802e81d0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1802e81d5  mov     rsi, rax
0x1802e81d8  test    rax, rax
0x1802e81db  jnz     short loc_1802E81E9
0x1802e81dd  lea     rcx, aErrorCannotAll; "Error: Cannot allocate the Validation P"...
0x1802e81e4  jmp     loc_1802E88EA
0x1802e81e9  mov     r13d, edi
0x1802e81ec  mov     dword ptr [rsp+4B0h+var_478], edi
0x1802e81f0  imul    r8, r15, 680h; Size
0x1802e81f7  xor     edx, edx; Val
0x1802e81f9  mov     rcx, rsi; void *
0x1802e81fc  call    memset
0x1802e8201  mov     rbx, rsi
0x1802e8204  mov     r12, rdi
0x1802e8207  mov     rax, rdi
0x1802e820a  mov     [rsp+4B0h+var_470], rax
0x1802e820f  cmp     rax, r15
0x1802e8212  jnb     loc_1802E852F
0x1802e8218  test    rbx, rbx
0x1802e821b  jz      loc_1802E852F
0x1802e8221  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802e8225  inc     rax
0x1802e8228  cmp     [r14+rax*2], di
0x1802e822d  jnz     short loc_1802E8225
0x1802e822f  mov     rdx, r14
0x1802e8232  cmp     rax, 104h
0x1802e8238  ja      loc_1802E8523
0x1802e823e  mov     [rbx+428h], rsi
0x1802e8245  mov     r9d, 209h
0x1802e824b  or      r8d, 0FFFFFFFFh
0x1802e824f  mov     rcx, rbx; void *
0x1802e8252  call    CopyNStringW
0x1802e8257  mov     r8d, 7; MaxCount
0x1802e825d  lea     rdx, aSymsrv; "SYMSRV*"
0x1802e8264  mov     rcx, rbx; String1
0x1802e8267  call    cs:__imp__wcsnicmp
0x1802e826e  nop     dword ptr [rax+rax+00h]
0x1802e8273  test    eax, eax
0x1802e8275  jz      loc_1802E84E6
0x1802e827b  mov     r8d, 4; MaxCount
0x1802e8281  lea     rdx, aSrv; "SRV*"
0x1802e8288  mov     rcx, rbx; String1
0x1802e828b  call    cs:__imp__wcsnicmp
0x1802e8292  nop     dword ptr [rax+rax+00h]
0x1802e8297  test    eax, eax
0x1802e8299  jz      loc_1802E84E6
0x1802e829f  mov     r8d, 6; MaxCount
0x1802e82a5  lea     rdx, aCache; "CACHE*"
0x1802e82ac  mov     rcx, rbx; String1
0x1802e82af  call    cs:__imp__wcsnicmp
0x1802e82b6  nop     dword ptr [rax+rax+00h]
0x1802e82bb  test    eax, eax
0x1802e82bd  jz      loc_1802E84E6
0x1802e82c3  mov     rcx, rbx; Str
0x1802e82c6  call    ?IsSourceServerPathComponent@@YA_NPEBG@Z; IsSourceServerPathComponent(ushort const *)
0x1802e82cb  test    al, al
0x1802e82cd  jnz     loc_1802E84E6
0x1802e82d3  mov     rcx, rbx; String1
0x1802e82d6  call    DbgClientLibIsUrlPathComponent
0x1802e82db  test    eax, eax
0x1802e82dd  jnz     loc_1802E84E6
0x1802e82e3  mov     r8d, 208h; nSize
0x1802e82e9  lea     rdx, [rsp+4B0h+Dst]; lpDst
0x1802e82ee  mov     rcx, rbx; lpSrc
0x1802e82f1  call    cs:__imp_ExpandEnvironmentStringsW
0x1802e82f8  nop     dword ptr [rax+rax+00h]
0x1802e82fd  test    eax, eax
0x1802e82ff  jnz     short loc_1802E8327
0x1802e8301  mov     rdx, rbx
0x1802e8304  lea     rcx, aWarningEnviron; "WARNING: Environment expansion failed: "...
0x1802e830b  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e8310  mov     ecx, 2
0x1802e8315  or      [rbx+420h], cx
0x1802e831c  mov     [rbx+434h], ecx
0x1802e8322  jmp     loc_1802E8508
0x1802e8327  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x1802e832e  jz      short loc_1802E837B
0x1802e8330  lea     rcx, [rsp+4B0h+Dst]; Src
0x1802e8335  call    ?NetworkPathCheck@@YAKPEBG@Z; NetworkPathCheck(ushort const *)
0x1802e833a  test    eax, eax
0x1802e833c  jz      short loc_1802E836A
0x1802e833e  cmp     eax, 0A1h
0x1802e8343  jz      short loc_1802E8361
0x1802e8345  lea     rdx, [rsp+4B0h+Dst]
0x1802e834a  cmp     eax, 10FEh
0x1802e834f  jz      loc_1802E84F2
0x1802e8355  lea     rcx, aWarningUnableT_2; "WARNING: Unable to net-check path: '%s'"...
0x1802e835c  jmp     loc_1802E84F9
0x1802e8361  lea     rcx, aWarningInvalid; "WARNING: Invalid path disallowed: '%s'"...
0x1802e8368  jmp     short loc_1802E8371
0x1802e836a  lea     rcx, aWarningNetwork; "WARNING: Network paths disallowed '%s'"...
0x1802e8371  lea     rdx, [rsp+4B0h+Dst]
0x1802e8376  jmp     loc_1802E84F9
0x1802e837b  mov     ecx, 1; int
0x1802e8380  call    ?AnySystemProcesses@@YAHH@Z; AnySystemProcesses(int)
0x1802e8385  test    eax, eax
0x1802e8387  jz      short loc_1802E83AB
0x1802e8389  lea     rdx, [rsp+4B0h+Dst]
0x1802e838e  lea     rcx, aWarningWeWonTV_0; "WARNING: We won't validate this path (s"...
0x1802e8395  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e839a  mov     eax, 4
0x1802e839f  or      [rbx+420h], ax
0x1802e83a6  jmp     loc_1802E84FE
0x1802e83ab  xor     edx, edx; Val
0x1802e83ad  mov     r8d, 412h; Size
0x1802e83b3  mov     rcx, rbx; void *
0x1802e83b6  call    memset
0x1802e83bb  mov     r9d, 209h
0x1802e83c1  or      r8d, 0FFFFFFFFh
0x1802e83c5  lea     rdx, [rsp+4B0h+Dst]
0x1802e83ca  mov     rcx, rbx; void *
0x1802e83cd  call    CopyNStringW
0x1802e83d2  mov     rcx, rbx; Src
0x1802e83d5  call    ?NetworkPathCheck@@YAKPEBG@Z; NetworkPathCheck(ushort const *)
0x1802e83da  cmp     eax, 10FEh
0x1802e83df  jnz     short loc_1802E8405
0x1802e83e1  mov     rcx, rbx; lpRootPathName
0x1802e83e4  call    ?IsPathNetworkMappedDrive@@YA_NPEBG@Z; IsPathNetworkMappedDrive(ushort const *)
0x1802e83e9  test    al, al
0x1802e83eb  jnz     short loc_1802E8405
0x1802e83ed  mov     rcx, rbx; struct PATH_VAL_BLK *
0x1802e83f0  call    ?IsSupportedUNCPath@@YAHPEAUPATH_VAL_BLK@@@Z; IsSupportedUNCPath(PATH_VAL_BLK *)
0x1802e83f5  test    eax, eax
0x1802e83f7  jz      loc_1802E8508
0x1802e83fd  or      word ptr [rbx+420h], 8
0x1802e8405  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802e840c  mov     ecx, 20h ; ' '; unsigned __int64
0x1802e8411  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1802e8416  mov     rdi, rax
0x1802e8419  mov     [rsp+4B0h+ExitCode], rax
0x1802e841e  xor     eax, eax
0x1802e8420  test    rdi, rdi
0x1802e8423  jz      short loc_1802E843F
0x1802e8425  mov     [rdi], rax
0x1802e8428  mov     [rdi+8], rax
0x1802e842c  mov     [rdi+10h], rax
0x1802e8430  mov     word ptr [rdi+18h], 100h
0x1802e8436  mov     dword ptr [rdi+1Ch], 40h ; '@'
0x1802e843d  jmp     short loc_1802E8442
0x1802e843f  mov     rdi, rax
0x1802e8442  mov     [rsp+4B0h+ExitCode], rdi
0x1802e8447  test    rdi, rdi
0x1802e844a  jnz     short loc_1802E846D
0x1802e844c  mov     rdx, rbx
0x1802e844f  lea     rcx, aErrorNotEnough; "Error: Not enough memory to create the "...
0x1802e8456  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e845b  nop
0x1802e845c  lea     rcx, [rsp+4B0h+ExitCode]
0x1802e8461  call    ??1?$DbsDeletePtr@UValidatePathThreadProcData@@@@QEAA@XZ; DbsDeletePtr<ValidatePathThreadProcData>::~DbsDeletePtr<ValidatePathThreadProcData>(void)
0x1802e8466  xor     edi, edi
0x1802e8468  jmp     loc_1802E8508
0x1802e846d  mov     [rdi], rbx
0x1802e8470  lea     rcx, [rdi+8]
0x1802e8474  or      r8d, 0FFFFFFFFh
0x1802e8478  mov     rdx, [rsp+4B0h+var_468]
0x1802e847d  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1802e8482  test    rax, rax
0x1802e8485  jz      short loc_1802E844C
0x1802e8487  mov     [rsp+4B0h+lpThreadId], 0; lpThreadId
0x1802e8490  mov     [rsp+4B0h+dwCreationFlags], 4; dwCreationFlags
0x1802e8498  mov     r9, rdi; lpParameter
0x1802e849b  lea     r8, ?ValidatePathThreadProc@@YAKPEAX@Z; lpStartAddress
0x1802e84a2  xor     edx, edx; dwStackSize
0x1802e84a4  xor     ecx, ecx; lpThreadAttributes
0x1802e84a6  call    cs:__imp_CreateThread
0x1802e84ad  nop     dword ptr [rax+rax+00h]
0x1802e84b2  mov     [rbx+418h], rax
0x1802e84b9  xor     edi, edi
0x1802e84bb  test    rax, rax
0x1802e84be  jnz     short loc_1802E84DC
0x1802e84c0  mov     rdx, rbx
0x1802e84c3  lea     rcx, aErrorUnableToC_1; "Error: Unable to create the validation "...
0x1802e84ca  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e84cf  nop
0x1802e84d0  lea     rcx, [rsp+4B0h+ExitCode]
0x1802e84d5  call    ??1?$DbsDeletePtr@UValidatePathThreadProcData@@@@QEAA@XZ; DbsDeletePtr<ValidatePathThreadProcData>::~DbsDeletePtr<ValidatePathThreadProcData>(void)
0x1802e84da  jmp     short loc_1802E8508
0x1802e84dc  mov     [rsp+4B0h+ExitCode], rdi
0x1802e84e1  inc     r12
0x1802e84e4  jmp     short loc_1802E84D0
0x1802e84e6  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x1802e84ed  jz      short loc_1802E84FE
0x1802e84ef  mov     rdx, rbx
0x1802e84f2  lea     rcx, aWarningNetwork_0; "WARNING: Network path disallowed: '%s'"...
0x1802e84f9  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e84fe  mov     dword ptr [rbx+434h], 2
0x1802e8508  mov     rax, [rsp+4B0h+var_470]
0x1802e850d  inc     rax
0x1802e8510  add     rbx, 680h
0x1802e8517  add     r14, 20Ah
0x1802e851e  jmp     loc_1802E820A
0x1802e8523  lea     rcx, aErrorInvalidPa; "Error: Invalid Path length: %s.\n"
0x1802e852a  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e852f  cmp     r12, r15
0x1802e8532  jbe     short loc_1802E8545
0x1802e8534  lea     rcx, aErrorInvalidNu; "Error: Invalid number of Threads. Path "...
0x1802e853b  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e8540  jmp     loc_1802E8861
0x1802e8545  test    r12, r12
0x1802e8548  jz      loc_1802E8861
0x1802e854e  lea     rdi, [rsi+448h]
0x1802e8555  mov     rcx, rdi; lpCriticalSection
0x1802e8558  call    cs:__imp_InitializeCriticalSection
0x1802e855f  nop     dword ptr [rax+rax+00h]
0x1802e8564  mov     [rsi+438h], r12d
0x1802e856b  mov     rbx, rsi
0x1802e856e  xor     r14d, r14d
0x1802e8571  test    r15, r15
0x1802e8574  jz      short loc_1802E85CB
0x1802e8576  mov     rcx, [rbx+418h]; hThread
0x1802e857d  test    rcx, rcx
0x1802e8580  jz      short loc_1802E85BC
0x1802e8582  call    cs:__imp_ResumeThread
0x1802e8589  nop     dword ptr [rax+rax+00h]
0x1802e858e  test    eax, eax
0x1802e8590  jnz     short loc_1802E85BC
0x1802e8592  lea     rcx, aErrorTheThread; "Error: The thread could not be resumed."...
0x1802e8599  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e859e  mov     rcx, [rbx+418h]; hObject
0x1802e85a5  call    cs:__imp_CloseHandle
0x1802e85ac  nop     dword ptr [rax+rax+00h]
0x1802e85b1  mov     qword ptr [rbx+418h], 0
0x1802e85bc  inc     r14
0x1802e85bf  add     rbx, 680h
0x1802e85c6  cmp     r14, r15
0x1802e85c9  jb      short loc_1802E8576
0x1802e85cb  mov     rbx, rsi
0x1802e85ce  xor     r12d, r12d
0x1802e85d1  cmp     r12, r15
0x1802e85d4  jnb     loc_1802E8850
0x1802e85da  cmp     qword ptr [rbx+418h], 0
0x1802e85e2  jz      loc_1802E877C
0x1802e85e8  mov     r13d, 1
0x1802e85ee  xor     r14d, r14d
0x1802e85f1  mov     dword ptr [rsp+4B0h+ExitCode], 0
0x1802e85f9  mov     edx, 3E8h; dwMilliseconds
0x1802e85fe  mov     rcx, [rbx+418h]; hHandle
0x1802e8605  call    cs:__imp_WaitForSingleObject
0x1802e860c  nop     dword ptr [rax+rax+00h]
0x1802e8611  test    eax, eax
0x1802e8613  jz      loc_1802E8703
0x1802e8619  cmp     eax, 80h
0x1802e861e  jz      short loc_1802E862C
0x1802e8620  cmp     eax, 102h
0x1802e8625  jz      short loc_1802E8681
0x1802e8627  cmp     eax, 0FFFFFFFFh
0x1802e862a  jnz     short loc_1802E8673
0x1802e862c  test    byte ptr [rbx+420h], 1
0x1802e8633  jnz     short loc_1802E863F
0x1802e8635  mov     dword ptr [rbx+434h], 0
0x1802e863f  lea     rdx, [rsp+4B0h+ExitCode]; lpExitCode
0x1802e8644  mov     rcx, [rbx+418h]; hThread
0x1802e864b  call    cs:__imp_GetExitCodeThread
0x1802e8652  nop     dword ptr [rax+rax+00h]
0x1802e8657  mov     ecx, dword ptr [rsp+4B0h+ExitCode]; int
0x1802e865b  cmp     ecx, 103h
0x1802e8661  jz      loc_1802E87B8
0x1802e8667  lea     rdx, aThreadFailed; "Thread failed"
0x1802e866e  call    ?PrintLastError@@YAXJPEBG@Z; PrintLastError(long,ushort const *)
0x1802e8673  test    r13d, r13d
0x1802e8676  jnz     loc_1802E85F1
0x1802e867c  jmp     loc_1802E874E
0x1802e8681  xor     ecx, ecx; unsigned __int8
0x1802e8683  call    ?CheckUserInterruptInternal@@YAKE@Z; CheckUserInterruptInternal(uchar)
0x1802e8688  test    eax, eax
0x1802e868a  jz      short loc_1802E86EA
0x1802e868c  mov     rcx, rdi; lpCriticalSection
0x1802e868f  call    cs:__imp_EnterCriticalSection
0x1802e8696  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
