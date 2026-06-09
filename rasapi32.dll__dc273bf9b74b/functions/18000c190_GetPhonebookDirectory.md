# GetPhonebookDirectory

- ea: `0x18000c190`
- end: `0x18000c96b`
- name: `GetPhonebookDirectory`
- size: `2011`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a0a8`
- `0x18000b960`
- `0x18000beb0`
- `0x18000ced8`
- `0x18000d5e0`
- `0x1800289e0`
- `0x1800cb0f8`

## callees

- `0x18000c190`
- `0x18000c980`
- `0x18000ce90`
- `0x18000dde0`
- `0x18003e0a8`
- `0x18004e580`
- `0x18004e984`
- `0x18007efdc`
- `0x18007f140`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c242`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c4ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c4ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c4fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c4fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c229`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000c41a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000c41a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c50b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c434`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000c5bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000c5bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c345`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c355`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c345`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c355`
- `rtutils!TracePrintfExA` at `0x18000c64c`
- `rtutils!TracePrintfExA` at `0x18000c854`
- `rtutils!TracePrintfExA` at `0x18000c930`
- `rtutils!TracePrintfExA` at `0x18000c64c`
- `rtutils!TracePrintfExA` at `0x18000c854`
- `rtutils!TracePrintfExA` at `0x18000c930`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000c29b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000c29b`

## string_xrefs

- `0x18000c846`: `StringCchCopy failed due to error 0x%x`
- `0x18000c63e`: `GetPhonebookDirectory: StringCchCatEx failed. hr=0x%08x`
- `0x18000c8c4`: `GetPhonebookDirectory: StringCchCatEx failed. hr=0x%08x`
- `0x18000c69b`: `GetPhonebookDirectory: GetBasicProfileFolderPath: returned %d`
- `0x18000c7b1`: `GetPhonebookDirectory: GetSidfromToken returned %d`
- `0x18000c91f`: `Unable to get AppPaths. Error=%d`

## pseudocode

```c
__int64 __fastcall GetPhonebookDirectory(unsigned int a1, WCHAR *a2, unsigned int a3)
{
  size_t v3; // r15
  _QWORD *v6; // rbx
  DWORD v7; // edi
  HANDLE CurrentThread; // rax
  unsigned int v9; // r12d
  DWORD SidFromToken; // eax
  STRSAFE_LPWSTR *v11; // r9
  int v12; // ebx
  unsigned __int16 BasicProfileFolderPath; // ax
  size_t v14; // r8
  _WORD *v15; // rcx
  __int64 v16; // rax
  size_t v17; // rdx
  STRSAFE_LPWSTR *v18; // rcx
  unsigned int v19; // r15d
  signed int v20; // ebx
  DWORD v21; // eax
  int v22; // ebx
  HRESULT v23; // eax
  size_t v24; // rsi
  __int64 v25; // r8
  WCHAR *v26; // rdx
  const WCHAR *v27; // rcx
  WCHAR *v28; // rcx
  char *v29; // rcx
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  __int64 v33; // rdx
  HRESULT v34; // ebx
  const CHAR *v35; // r8
  bool v36; // zf
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL hMem; // [rsp+38h] [rbp-C8h]
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v42[528]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = a3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a1, a3);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  hMem = 0;
  TokenHandle = 0;
  memset_0(v42, 0, 0x20Au);
  if ( (unsigned int)v3 < 0x105 )
  {
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 0x80) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_(v6[2], 32, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x80) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_(v6[2], 33, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    }
    return 0;
  }
  if ( a1 >= 2 )
  {
    v9 = 0;
    if ( GetSystemDirectoryW(a2, 0x105u) - 1 > 0xF2 )
      goto LABEL_32;
    v34 = StringCchCatExW(a2, v3, L"\\Ras\\", v11, pcchRemaining, 0x100u);
    if ( v34 < 0 )
    {
      v29 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
          (unsigned int)v34);
        v29 = (char *)WPP_GLOBAL_Control;
      }
      if ( g_dwTraceId == -1 )
        goto LABEL_67;
      TracePrintfExA(g_dwTraceId, 0xCu, "GetPhonebookDirectory: StringCchCatEx failed. hr=0x%08x", v34);
    }
    v29 = (char *)WPP_GLOBAL_Control;
LABEL_67:
    v9 = 1;
    goto LABEL_33;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x80) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_(v6[2], 34, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  CurrentThread = GetCurrentThread();
  v9 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( !v9 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      v9 = OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle);
      if ( v9 )
        goto LABEL_6;
      LastError = GetLastError();
      v7 = LastError;
      v29 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_33;
      }
      v33 = v9 + 35;
    }
    else
    {
      v29 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_33;
      }
      v33 = 36;
    }
    WPP_SF_d(*((_QWORD *)v29 + 2), v33, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
    goto LABEL_32;
  }
LABEL_6:
  SidFromToken = GetSidFromToken(TokenHandle);
  v7 = SidFromToken;
  if ( SidFromToken )
  {
    v29 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, SidFromToken);
      v29 = (char *)WPP_GLOBAL_Control;
    }
    v21 = g_dwTraceId;
    if ( g_dwTraceId == -1 )
      goto LABEL_33;
    v35 = "GetPhonebookDirectory: GetSidfromToken returned %d";
LABEL_115:
    TracePrintfExA(v21, 0xCu, v35, v7);
    goto LABEL_32;
  }
  v12 = a1 != 0 ? 3 : 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
      (unsigned int)(v12 + 4));
  }
  BasicProfileFolderPath = GetBasicProfileFolderPath((unsigned int)(v12 + 4), hMem, v42, 261);
  v7 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath )
  {
    v29 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        BasicProfileFolderPath);
      v29 = (char *)WPP_GLOBAL_Control;
    }
    v21 = g_dwTraceId;
    if ( g_dwTraceId == -1 )
      goto LABEL_33;
    v35 = "GetPhonebookDirectory: GetBasicProfileFolderPath: returned %d";
    goto LABEL_115;
  }
  v14 = v3;
  if ( a2 && (unsigned int)v3 <= 0x7FFFFFFF )
  {
    v15 = v42;
    v7 = 0;
    v16 = 2147483646;
    v17 = v3;
    v11 = (STRSAFE_LPWSTR *)a2;
    do
    {
      if ( !v16 )
        break;
      if ( !*v15 )
        break;
      *(_WORD *)v11 = *v15++;
      v11 = (STRSAFE_LPWSTR *)((char *)v11 + 2);
      --v16;
      --v17;
    }
    while ( v17 );
    v18 = (STRSAFE_LPWSTR *)((char *)v11 - 2);
    v19 = -2147024774;
    v20 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = v11;
    *(_WORD *)v18 = 0;
    if ( v17 )
      goto LABEL_18;
    StringExHandleOtherFlagsW(a2, 2 * v14, v14, &ppszDestEnd, &pcchLength, 0x900u);
    if ( v20 >= 0 )
      goto LABEL_18;
  }
  else
  {
    v20 = -2147024809;
    v36 = (_DWORD)v3 == 0;
    v19 = -2147024774;
    if ( !v36 )
      *a2 = 0;
  }
  v21 = g_dwTraceId;
  v7 = (unsigned __int16)v20;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v20);
LABEL_18:
    v21 = g_dwTraceId;
  }
  if ( v7 )
  {
    v29 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
      v29 = (char *)WPP_GLOBAL_Control;
      v21 = g_dwTraceId;
    }
    if ( v21 == -1 )
      goto LABEL_33;
    v35 = "Unable to get AppPaths. Error=%d";
    goto LABEL_115;
  }
  v22 = 260 - lstrlenW(L"\\Microsoft\\Network\\Connections\\Pbk\\");
  if ( lstrlenW(a2) > v22 )
  {
LABEL_32:
    v29 = (char *)WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v9 = 0;
  pcchLength = 0;
  if ( a2 )
  {
    v23 = StringLengthWorkerW(a2, 0x105u, &pcchLength);
    if ( v23 < 0 )
    {
      v19 = v23;
    }
    else
    {
      v24 = 261 - pcchLength;
      if ( pcchLength != 261 && pcchLength != 260 )
      {
        v25 = 2147483646;
        v26 = &a2[pcchLength];
        v27 = L"\\Microsoft\\Network\\Connections\\Pbk\\";
        do
        {
          if ( !v25 )
            break;
          if ( !*v27 )
            break;
          *v26++ = *v27++;
          --v25;
          --v24;
        }
        while ( v24 );
        v19 = v24 == 0 ? 0x8007007A : 0;
        v28 = v26 - 1;
        if ( v24 )
          v28 = v26;
        *v28 = 0;
        if ( v24 )
          goto LABEL_31;
      }
      if ( (v19 & 0x80000000) == 0 )
      {
LABEL_31:
        v9 = 1;
        goto LABEL_32;
      }
    }
  }
  else
  {
    v19 = -2147024809;
  }
  v29 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v19);
    v29 = (char *)WPP_GLOBAL_Control;
  }
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "GetPhonebookDirectory: StringCchCatEx failed. hr=0x%08x", v19);
    goto LABEL_32;
  }
LABEL_33:
  if ( hMem )
  {
    GlobalFree(hMem);
    v29 = (char *)WPP_GLOBAL_Control;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v29 = (char *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v29 != (char *)&WPP_GLOBAL_Control && v29[28] < 0 && (unsigned __int8)v29[25] >= 6u )
      WPP_SF_c(*((_QWORD *)v29 + 2), 43, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
    return 0;
  }
  if ( v29 != (char *)&WPP_GLOBAL_Control && v29[28] < 0 && (unsigned __int8)v29[25] >= 6u )
  {
    LOBYTE(v11) = v9 != 0;
    WPP_SF_c(*((_QWORD *)v29 + 2), 44, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v11);
  }
  return v9;
}

```

## disassembly

```asm
0x18000c190  mov     [rsp-8+arg_18], rbx
0x18000c195  push    rbp
0x18000c196  push    rsi
0x18000c197  push    rdi
0x18000c198  push    r12
0x18000c19a  push    r13
0x18000c19c  push    r14
0x18000c19e  push    r15
0x18000c1a0  lea     rbp, [rsp-170h]
0x18000c1a8  sub     rsp, 270h
0x18000c1af  mov     rax, cs:__security_cookie
0x18000c1b6  xor     rax, rsp
0x18000c1b9  mov     [rbp+1A0h+var_40], rax
0x18000c1c0  mov     r15d, r8d
0x18000c1c3  mov     r13, rdx
0x18000c1c6  mov     r14d, ecx
0x18000c1c9  mov     rbx, cs:WPP_GLOBAL_Control
0x18000c1d0  lea     rax, WPP_GLOBAL_Control
0x18000c1d7  mov     r12b, 80h
0x18000c1da  cmp     rbx, rax
0x18000c1dd  jnz     loc_18000C576
0x18000c1e3  xor     edi, edi
0x18000c1e5  lea     rcx, [rsp+2A0h+var_250]; void *
0x18000c1ea  xor     edx, edx; Val
0x18000c1ec  mov     [rsp+2A0h+hMem], rdi
0x18000c1f1  mov     r8d, 20Ah; Size
0x18000c1f7  mov     [rsp+2A0h+TokenHandle], rdi
0x18000c1fc  call    memset_0
0x18000c201  mov     esi, 105h
0x18000c206  cmp     r15d, esi
0x18000c209  jb      loc_18000C6A7
0x18000c20f  cmp     r14d, 2
0x18000c213  jnb     loc_18000C5B3
0x18000c219  lea     rax, WPP_GLOBAL_Control
0x18000c220  cmp     rbx, rax
0x18000c223  jnz     loc_18000C548
0x18000c229  call    cs:__imp_GetCurrentThread
0x18000c22f  mov     ebx, 0Ch
0x18000c234  lea     r9, [rsp+2A0h+TokenHandle]; TokenHandle
0x18000c239  mov     rcx, rax; ThreadHandle
0x18000c23c  mov     edx, ebx; DesiredAccess
0x18000c23e  lea     r8d, [rbx-0Bh]; OpenAsSelf
0x18000c242  call    cs:__imp_OpenThreadToken
0x18000c248  mov     r12d, eax
0x18000c24b  test    eax, eax
0x18000c24d  jz      loc_18000C4D7
0x18000c253  mov     rcx, [rsp+2A0h+TokenHandle]; TokenHandle
0x18000c258  lea     rdx, [rsp+2A0h+hMem]
0x18000c25d  call    GetSidFromToken
0x18000c262  mov     edi, eax
0x18000c264  test    eax, eax
0x18000c266  jnz     loc_18000C760
0x18000c26c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c273  lea     rax, WPP_GLOBAL_Control
0x18000c27a  neg     r14d
0x18000c27d  sbb     ebx, ebx
0x18000c27f  and     ebx, 3
0x18000c282  cmp     rcx, rax
0x18000c285  jnz     loc_18000C4A5
0x18000c28b  mov     rdx, [rsp+2A0h+hMem]
0x18000c290  lea     r8, [rsp+2A0h+var_250]
0x18000c295  mov     r9, rsi
0x18000c298  lea     ecx, [rbx+4]
0x18000c29b  call    cs:__imp_GetBasicProfileFolderPath
0x18000c2a1  movzx   edi, ax
0x18000c2a4  xor     r11d, r11d
0x18000c2a7  test    edi, edi
0x18000c2a9  jnz     loc_18000C66B
0x18000c2af  or      r14d, 0FFFFFFFFh
0x18000c2b3  mov     r8, r15; cchOriginalDestLength
0x18000c2b6  test    r13, r13
0x18000c2b9  jz      loc_18000C81E
0x18000c2bf  cmp     r15d, 7FFFFFFFh
0x18000c2c6  ja      loc_18000C81E
0x18000c2cc  lea     rcx, [rsp+2A0h+var_250]
0x18000c2d1  mov     edi, r11d
0x18000c2d4  mov     eax, 7FFFFFFEh
0x18000c2d9  mov     rdx, r15
0x18000c2dc  mov     r9, r13
0x18000c2df  test    r15, r15
0x18000c2e2  jz      short loc_18000C308
0x18000c2e4  test    rax, rax
0x18000c2e7  jz      short loc_18000C308
0x18000c2e9  movzx   r10d, word ptr [rcx]
0x18000c2ed  test    r10w, r10w
0x18000c2f1  jz      short loc_18000C308
0x18000c2f3  mov     [r9], r10w
0x18000c2f7  add     rcx, 2
0x18000c2fb  add     r9, 2
0x18000c2ff  dec     rax
0x18000c302  sub     rdx, 1
0x18000c306  jnz     short loc_18000C2E4
0x18000c308  mov     rax, rdx
0x18000c30b  lea     rcx, [r9-2]
0x18000c30f  neg     rax
0x18000c312  mov     r15d, 8007007Ah
0x18000c318  sbb     ebx, ebx
0x18000c31a  not     ebx
0x18000c31c  and     ebx, r15d
0x18000c31f  test    rdx, rdx
0x18000c322  cmovnz  rcx, r9
0x18000c326  mov     [rcx], r11w
0x18000c32a  jz      loc_18000C7ED
0x18000c330  mov     eax, cs:g_dwTraceId
0x18000c336  test    edi, edi
0x18000c338  jnz     loc_18000C8D2
0x18000c33e  lea     rcx, String; "\\Microsoft\\Network\\Connections\\Pbk"...
0x18000c345  call    cs:__imp_lstrlenW
0x18000c34b  mov     ebx, 104h
0x18000c350  mov     rcx, r13; lpString
0x18000c353  sub     ebx, eax
0x18000c355  call    cs:__imp_lstrlenW
0x18000c35b  cmp     eax, ebx
0x18000c35d  jg      loc_18000C3FF
0x18000c363  xor     r12d, r12d
0x18000c366  mov     [rsp+2A0h+pcchLength], r12
0x18000c36b  test    r13, r13
0x18000c36e  jz      loc_18000C86E
0x18000c374  lea     r8, [rsp+2A0h+pcchLength]; pcchLength
0x18000c379  mov     rdx, rsi; cchMax
0x18000c37c  mov     rcx, r13; psz
0x18000c37f  call    StringLengthWorkerW
0x18000c384  test    eax, eax
0x18000c386  js      loc_18000C869
0x18000c38c  mov     rax, [rsp+2A0h+pcchLength]
0x18000c391  sub     rsi, rax
0x18000c394  cmp     rsi, 1
0x18000c398  jbe     loc_18000C85F
0x18000c39e  lea     rdx, ds:0[rax*2]
0x18000c3a6  mov     r8d, 7FFFFFFEh
0x18000c3ac  add     rdx, r13
0x18000c3af  lea     rcx, String; "\\Microsoft\\Network\\Connections\\Pbk"...
0x18000c3b6  test    r8, r8
0x18000c3b9  jz      short loc_18000C3D7
0x18000c3bb  movzx   eax, word ptr [rcx]
0x18000c3be  test    ax, ax
0x18000c3c1  jz      short loc_18000C3D7
0x18000c3c3  mov     [rdx], ax
0x18000c3c6  add     rcx, 2
0x18000c3ca  add     rdx, 2
0x18000c3ce  dec     r8
0x18000c3d1  sub     rsi, 1
0x18000c3d5  jnz     short loc_18000C3B6
0x18000c3d7  mov     rax, rsi
0x18000c3da  neg     rax
0x18000c3dd  sbb     ecx, ecx
0x18000c3df  not     ecx
0x18000c3e1  and     r15d, ecx
0x18000c3e4  lea     rcx, [rdx-2]
0x18000c3e8  test    rsi, rsi
0x18000c3eb  cmovnz  rcx, rdx
0x18000c3ef  mov     [rcx], r12w
0x18000c3f3  jz      loc_18000C85F
0x18000c3f9  mov     r12d, 1
0x18000c3ff  lea     rsi, WPP_GLOBAL_Control
0x18000c406  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c40d  mov     rax, [rsp+2A0h+hMem]
0x18000c412  test    rax, rax
0x18000c415  jz      short loc_18000C427
0x18000c417  mov     rcx, rax; hMem
0x18000c41a  call    cs:__imp_GlobalFree
0x18000c420  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c427  mov     rax, [rsp+2A0h+TokenHandle]
0x18000c42c  test    rax, rax
0x18000c42f  jz      short loc_18000C441
0x18000c431  mov     rcx, rax; hObject
0x18000c434  call    cs:__imp_CloseHandle
0x18000c43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c441  test    edi, edi
0x18000c443  jnz     loc_18000C93B
0x18000c449  cmp     rcx, rsi
0x18000c44c  jnz     short loc_18000C47B
0x18000c44e  mov     eax, r12d
0x18000c451  mov     rcx, [rbp+1A0h+var_40]
0x18000c458  xor     rcx, rsp; StackCookie
0x18000c45b  call    __security_check_cookie
0x18000c460  mov     rbx, [rsp+2A0h+arg_18]
0x18000c468  add     rsp, 270h
0x18000c46f  pop     r15
0x18000c471  pop     r14
0x18000c473  pop     r13
0x18000c475  pop     r12
0x18000c477  pop     rdi
0x18000c478  pop     rsi
0x18000c479  pop     rbp
0x18000c47a  retn
0x18000c47b  test    byte ptr [rcx+1Ch], 80h
0x18000c47f  jz      short loc_18000C44E
0x18000c481  cmp     byte ptr [rcx+19h], 6
0x18000c485  jb      short loc_18000C44E
0x18000c487  mov     rcx, [rcx+10h]
0x18000c48b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000c492  test    r12d, r12d
0x18000c495  mov     edx, 2Ch ; ','
0x18000c49a  setnz   r9b
0x18000c49e  call    WPP_SF_c
0x18000c4a3  jmp     short loc_18000C44E
0x18000c4a5  test    byte ptr [rcx+1Ch], 80h
0x18000c4a9  jz      loc_18000C28B
0x18000c4af  cmp     byte ptr [rcx+19h], 5
0x18000c4b3  jb      loc_18000C28B
0x18000c4b9  mov     rcx, [rcx+10h]
0x18000c4bd  lea     r9d, [rbx+4]
0x18000c4c1  mov     edx, 26h ; '&'
0x18000c4c6  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000c4cd  call    WPP_SF_d
0x18000c4d2  jmp     loc_18000C28B
0x18000c4d7  call    cs:__imp_GetLastError
0x18000c4dd  mov     edi, eax
0x18000c4df  cmp     eax, 3F0h
0x18000c4e4  jnz     loc_18000C733
0x18000c4ea  call    cs:__imp_GetCurrentProcess
0x18000c4f0  lea     r8, [rsp+2A0h+TokenHandle]; TokenHandle
0x18000c4f5  mov     edx, ebx; DesiredAccess
0x18000c4f7  mov     rcx, rax; ProcessHandle
0x18000c4fa  call    cs:__imp_OpenProcessToken
0x18000c500  mov     r12d, eax
0x18000c503  test    eax, eax
0x18000c505  jnz     loc_18000C253
0x18000c50b  call    cs:__imp_GetLastError
0x18000c511  mov     edi, eax
0x18000c513  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c51a  lea     rsi, WPP_GLOBAL_Control
0x18000c521  cmp     rcx, rsi
0x18000c524  jz      loc_18000C40D
0x18000c52a  test    byte ptr [rcx+1Ch], 80h
0x18000c52e  jz      loc_18000C40D
0x18000c534  cmp     byte ptr [rcx+19h], 2
0x18000c538  jb      loc_18000C40D
0x18000c53e  lea     edx, [r12+23h]
0x18000c543  jmp     loc_18000C71B
0x18000c548  test    [rbx+1Ch], r12b
0x18000c54c  jz      loc_18000C229
0x18000c552  cmp     byte ptr [rbx+19h], 5
0x18000c556  jb      loc_18000C229
0x18000c55c  mov     rcx, [rbx+10h]
0x18000c560  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000c567  mov     edx, 22h ; '"'
0x18000c56c  call    WPP_SF_
0x18000c571  jmp     loc_18000C229
0x18000c576  test    [rbx+1Ch], r12b
0x18000c57a  jz      loc_18000C1E3
0x18000c580  cmp     byte ptr [rbx+19h], 6
0x18000c584  jb      loc_18000C1E3
0x18000c58a  mov     rcx, [rbx+10h]
0x18000c58e  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000c595  mov     edx, 1Fh
0x18000c59a  mov     dword ptr [rsp+2A0h+pcchRemaining], r15d
0x18000c59f  mov     r9d, r14d
0x18000c5a2  call    WPP_SF_Dd
0x18000c5a7  mov     rbx, cs:WPP_GLOBAL_Control
0x18000c5ae  jmp     loc_18000C1E3
0x18000c5b3  mov     edx, esi; uSize
0x18000c5b5  mov     rcx, r13; lpBuffer
0x18000c5b8  mov     r12d, edi
0x18000c5bb  call    cs:__imp_GetSystemDirectoryW
0x18000c5c1  dec     eax
0x18000c5c3  cmp     eax, 0F2h
0x18000c5c8  ja      loc_18000C3FF
0x18000c5ce  mov     rdx, r15; cchDest
0x18000c5d1  mov     [rsp+2A0h+dwFlags], 100h; dwFlags
0x18000c5d9  lea     r8, aRas; "\\Ras\\"
0x18000c5e0  mov     rcx, r13; pszDest
0x18000c5e3  call    StringCchCatExW
0x18000c5e8  mov     ebx, eax
0x18000c5ea  test    eax, eax
0x18000c5ec  jns     short loc_18000C652
0x18000c5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5f5  lea     rax, WPP_GLOBAL_Control
0x18000c5fc  cmp     rcx, rax
0x18000c5ff  jz      short loc_18000C62C
0x18000c601  test    byte ptr [rcx+1Ch], 80h
0x18000c605  jz      short loc_18000C62C
0x18000c607  cmp     byte ptr [rcx+19h], 2
0x18000c60b  jb      short loc_18000C62C
0x18000c60d  mov     rcx, [rcx+10h]
0x18000c611  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18000c618  mov     edx, 2Ah ; '*'
0x18000c61d  mov     r9d, ebx
0x18000c620  call    WPP_SF_d
0x18000c625  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c62c  mov     eax, cs:g_dwTraceId
0x18000c632  or      r14d, 0FFFFFFFFh
0x18000c636  cmp     eax, r14d
0x18000c639  jz      short loc_18000C659
0x18000c63b  mov     r9d, ebx
0x18000c63e  lea     r8, aGetphonebookdi_0; "GetPhonebookDirectory: StringCchCatEx f"...
0x18000c645  mov     edx, 0Ch; dwFlags
0x18000c64a  mov     ecx, eax; dwTraceID
0x18000c64c  call    cs:__imp_TracePrintfExA
0x18000c652  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c659  mov     r12d, 1
0x18000c65f  lea     rsi, WPP_GLOBAL_Control
0x18000c666  jmp     loc_18000C40D
0x18000c66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c672  lea     rsi, WPP_GLOBAL_Control
0x18000c679  cmp     rcx, rsi
0x18000c67c  jz      short loc_18000C688
0x18000c67e  test    byte ptr [rcx+1Ch], 80h
0x18000c682  jnz     loc_18000C7BF
  ... truncated ...
```
