# GetPhonebookDirectory

- ea: `0x18006d4c4`
- end: `0x18006d977`
- name: `GetPhonebookDirectory`
- size: `1203`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c0e4`
- `0x18006d324`
- `0x18006df64`
- `0x180076514`
- `0x180080430`
- `0x1800845b0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x18000c37c`
- `0x18005f32c`
- `0x18005fe20`
- `0x18006051c`
- `0x18006d4c4`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d61d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d61d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d63c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d63c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d667`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006d67d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006d67d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d8da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d68f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d68f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d8ba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d8ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006d581`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006d581`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006d7ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006d804`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006d7ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006d804`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18006d789`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18006d789`

## pseudocode

```c
__int64 __fastcall GetPhonebookDirectory(unsigned int a1, wchar_t *a2)
{
  struct _LIST_ENTRY *v4; // rbx
  unsigned int v5; // esi
  DWORD v6; // edi
  STRSAFE_LPWSTR *v7; // r9
  HRESULT v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  __int64 v13; // rdx
  int v14; // ebx
  unsigned __int16 BasicProfileFolderPath; // ax
  __int64 v16; // r9
  int v17; // ebx
  HRESULT v18; // eax
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL hMem; // [rsp+38h] [rbp-C8h]
  _BYTE v23[528]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 31, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a1, 261);
    v4 = WPP_GLOBAL_Control;
  }
  hMem = 0;
  TokenHandle = 0;
  memset_0(v23, 0, 0x20Au);
  if ( a1 >= 2 )
  {
    v5 = 0;
    v6 = 0;
    if ( GetSystemDirectoryW(a2, 0x105u) - 1 <= 0xF2 )
    {
      v8 = StringCchCatExW(a2, 0x105u, L"\\Ras\\", v7, pcchRemaining, 0x100u);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_13;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 42, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (unsigned int)v8);
      }
      v9 = WPP_GLOBAL_Control;
LABEL_13:
      v5 = 1;
      goto LABEL_59;
    }
    goto LABEL_58;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 0x80) != 0 && BYTE1(v4[1].Blink) >= 5u )
    WPP_SF_(v4[1].Flink, 34, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  CurrentThread = GetCurrentThread();
  v5 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( !v5 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 1008 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 36;
        goto LABEL_56;
      }
      goto LABEL_59;
    }
    CurrentProcess = GetCurrentProcess();
    v5 = OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle);
    if ( !v5 )
    {
      LastError = GetLastError();
      v6 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 35;
LABEL_56:
        v16 = LastError;
        goto LABEL_57;
      }
      goto LABEL_59;
    }
  }
  LastError = GetSidFromToken(TokenHandle);
  v6 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v13 = 37;
      goto LABEL_56;
    }
  }
  else
  {
    v14 = a1 != 0 ? 3 : 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        38,
        &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        (unsigned int)(v14 + 4));
    }
    BasicProfileFolderPath = GetBasicProfileFolderPath((unsigned int)(v14 + 4), hMem, v23, 261);
    v6 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 39;
        v16 = BasicProfileFolderPath;
LABEL_57:
        WPP_SF_d(v9[1].Flink, v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v16);
        goto LABEL_58;
      }
    }
    else
    {
      LastError = StringCchCopyWrapW(a2, 261, v23);
      v6 = LastError;
      if ( !LastError )
      {
        v17 = 260 - lstrlenW(L"\\Microsoft\\Network\\Connections\\Pbk\\");
        if ( lstrlenW(a2) <= v17 )
        {
          v18 = StringCchCatExW(a2, 0x105u, L"\\Microsoft\\Network\\Connections\\Pbk\\", v7, pcchRemaining, 0x100u);
          if ( v18 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                40,
                &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                (unsigned int)v18);
              v9 = WPP_GLOBAL_Control;
            }
            v5 = 0;
            goto LABEL_59;
          }
          v5 = 1;
        }
LABEL_58:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_59;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 41;
        goto LABEL_56;
      }
    }
  }
LABEL_59:
  if ( hMem )
  {
    GlobalFree(hMem);
    v9 = WPP_GLOBAL_Control;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 0x80) != 0 && BYTE1(v9[1].Blink) >= 6u )
      WPP_SF_c(v9[1].Flink, 43, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
    return 0;
  }
  else
  {
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 0x80) != 0 && BYTE1(v9[1].Blink) >= 6u )
    {
      LOBYTE(v7) = v5 != 0;
      WPP_SF_c(v9[1].Flink, 44, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x18006d4c4  mov     [rsp-8+arg_10], rbx
0x18006d4c9  push    rbp
0x18006d4ca  push    rsi
0x18006d4cb  push    rdi
0x18006d4cc  push    r12
0x18006d4ce  push    r13
0x18006d4d0  push    r14
0x18006d4d2  push    r15
0x18006d4d4  lea     rbp, [rsp-160h]
0x18006d4dc  sub     rsp, 260h
0x18006d4e3  mov     rax, cs:__security_cookie
0x18006d4ea  xor     rax, rsp
0x18006d4ed  mov     [rbp+190h+var_40], rax
0x18006d4f4  mov     r15, rdx
0x18006d4f7  mov     r14d, ecx
0x18006d4fa  mov     rbx, cs:WPP_GLOBAL_Control
0x18006d501  lea     r13, WPP_GLOBAL_Control
0x18006d508  mov     r12b, 80h
0x18006d50b  cmp     rbx, r13
0x18006d50e  jz      short loc_18006D543
0x18006d510  test    [rbx+1Ch], r12b
0x18006d514  jz      short loc_18006D543
0x18006d516  cmp     byte ptr [rbx+19h], 6
0x18006d51a  jb      short loc_18006D543
0x18006d51c  mov     r9d, ecx
0x18006d51f  mov     dword ptr [rsp+290h+pcchRemaining], 105h; pcchRemaining
0x18006d527  mov     rcx, [rbx+10h]
0x18006d52b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d532  mov     edx, 1Fh
0x18006d537  call    WPP_SF_Dd
0x18006d53c  mov     rbx, cs:WPP_GLOBAL_Control
0x18006d543  xor     edx, edx; Val
0x18006d545  mov     [rsp+290h+hMem], 0
0x18006d54e  mov     r8d, 20Ah; Size
0x18006d554  mov     [rsp+290h+TokenHandle], 0
0x18006d55d  lea     rcx, [rsp+290h+var_250]; void *
0x18006d562  call    memset_0
0x18006d567  cmp     r14d, 2
0x18006d56b  jb      loc_18006D5F7
0x18006d571  mov     r14d, 105h
0x18006d577  mov     rcx, r15; lpBuffer
0x18006d57a  mov     edx, r14d; uSize
0x18006d57d  xor     esi, esi
0x18006d57f  xor     edi, edi
0x18006d581  call    cs:__imp_GetSystemDirectoryW
0x18006d588  nop     dword ptr [rax+rax+00h]
0x18006d58d  dec     eax
0x18006d58f  cmp     eax, 0F2h
0x18006d594  ja      loc_18006D8A6
0x18006d59a  lea     r8, aRas; "\\Ras\\"
0x18006d5a1  mov     [rsp+290h+dwFlags], 100h; dwFlags
0x18006d5a9  mov     edx, r14d; cchDest
0x18006d5ac  mov     rcx, r15; pszDest
0x18006d5af  call    StringCchCatExW
0x18006d5b4  test    eax, eax
0x18006d5b6  jns     short loc_18006D5E6
0x18006d5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5bf  cmp     rcx, r13
0x18006d5c2  jz      short loc_18006D5ED
0x18006d5c4  test    [rcx+1Ch], r12b
0x18006d5c8  jz      short loc_18006D5ED
0x18006d5ca  cmp     byte ptr [rcx+19h], 2
0x18006d5ce  jb      short loc_18006D5ED
0x18006d5d0  mov     rcx, [rcx+10h]
0x18006d5d4  lea     edx, [rsi+2Ah]
0x18006d5d7  mov     r9d, eax
0x18006d5da  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d5e1  call    WPP_SF_d
0x18006d5e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5ed  mov     esi, 1
0x18006d5f2  jmp     loc_18006D8AD
0x18006d5f7  cmp     rbx, r13
0x18006d5fa  jz      short loc_18006D61D
0x18006d5fc  test    [rbx+1Ch], r12b
0x18006d600  jz      short loc_18006D61D
0x18006d602  cmp     byte ptr [rbx+19h], 5
0x18006d606  jb      short loc_18006D61D
0x18006d608  mov     rcx, [rbx+10h]
0x18006d60c  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d613  mov     edx, 22h ; '"'
0x18006d618  call    WPP_SF_
0x18006d61d  call    cs:__imp_GetCurrentThread
0x18006d624  nop     dword ptr [rax+rax+00h]
0x18006d629  mov     ebx, 0Ch
0x18006d62e  lea     r9, [rsp+290h+TokenHandle]; TokenHandle
0x18006d633  mov     rcx, rax; ThreadHandle
0x18006d636  mov     edx, ebx; DesiredAccess
0x18006d638  lea     r8d, [rbx-0Bh]; OpenAsSelf
0x18006d63c  call    cs:__imp_OpenThreadToken
0x18006d643  nop     dword ptr [rax+rax+00h]
0x18006d648  mov     esi, eax
0x18006d64a  test    eax, eax
0x18006d64c  jnz     loc_18006D6F7
0x18006d652  call    cs:__imp_GetLastError
0x18006d659  nop     dword ptr [rax+rax+00h]
0x18006d65e  mov     edi, eax
0x18006d660  cmp     eax, 3F0h
0x18006d665  jnz     short loc_18006D6C9
0x18006d667  call    cs:__imp_GetCurrentProcess
0x18006d66e  nop     dword ptr [rax+rax+00h]
0x18006d673  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x18006d678  mov     edx, ebx; DesiredAccess
0x18006d67a  mov     rcx, rax; ProcessHandle
0x18006d67d  call    cs:__imp_OpenProcessToken
0x18006d684  nop     dword ptr [rax+rax+00h]
0x18006d689  mov     esi, eax
0x18006d68b  test    eax, eax
0x18006d68d  jnz     short loc_18006D6F7
0x18006d68f  call    cs:__imp_GetLastError
0x18006d696  nop     dword ptr [rax+rax+00h]
0x18006d69b  mov     edi, eax
0x18006d69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d6a4  cmp     rcx, r13
0x18006d6a7  jz      loc_18006D8AD
0x18006d6ad  test    [rcx+1Ch], r12b
0x18006d6b1  jz      loc_18006D8AD
0x18006d6b7  cmp     byte ptr [rcx+19h], 2
0x18006d6bb  jb      loc_18006D8AD
0x18006d6c1  lea     edx, [rbx+17h]
0x18006d6c4  jmp     loc_18006D893
0x18006d6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d6d0  cmp     rcx, r13
0x18006d6d3  jz      loc_18006D8AD
0x18006d6d9  test    [rcx+1Ch], r12b
0x18006d6dd  jz      loc_18006D8AD
0x18006d6e3  cmp     byte ptr [rcx+19h], 2
0x18006d6e7  jb      loc_18006D8AD
0x18006d6ed  mov     edx, 24h ; '$'
0x18006d6f2  jmp     loc_18006D893
0x18006d6f7  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x18006d6fc  lea     rdx, [rsp+290h+hMem]
0x18006d701  call    GetSidFromToken
0x18006d706  mov     edi, eax
0x18006d708  test    eax, eax
0x18006d70a  jz      short loc_18006D73A
0x18006d70c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d713  cmp     rcx, r13
0x18006d716  jz      loc_18006D8AD
0x18006d71c  test    [rcx+1Ch], r12b
0x18006d720  jz      loc_18006D8AD
0x18006d726  cmp     byte ptr [rcx+19h], 2
0x18006d72a  jb      loc_18006D8AD
0x18006d730  mov     edx, 25h ; '%'
0x18006d735  jmp     loc_18006D893
0x18006d73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d741  neg     r14d
0x18006d744  sbb     ebx, ebx
0x18006d746  and     ebx, 3
0x18006d749  cmp     rcx, r13
0x18006d74c  jz      short loc_18006D773
0x18006d74e  test    [rcx+1Ch], r12b
0x18006d752  jz      short loc_18006D773
0x18006d754  cmp     byte ptr [rcx+19h], 5
0x18006d758  jb      short loc_18006D773
0x18006d75a  mov     rcx, [rcx+10h]
0x18006d75e  lea     r9d, [rbx+4]
0x18006d762  mov     edx, 26h ; '&'
0x18006d767  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d76e  call    WPP_SF_d
0x18006d773  mov     rdx, [rsp+290h+hMem]
0x18006d778  lea     r8, [rsp+290h+var_250]
0x18006d77d  mov     r14d, 105h
0x18006d783  lea     ecx, [rbx+4]
0x18006d786  mov     r9d, r14d
0x18006d789  call    cs:__imp_GetBasicProfileFolderPath
0x18006d790  nop     dword ptr [rax+rax+00h]
0x18006d795  movzx   edi, ax
0x18006d798  test    edi, edi
0x18006d79a  jz      short loc_18006D7CD
0x18006d79c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d7a3  cmp     rcx, r13
0x18006d7a6  jz      loc_18006D8AD
0x18006d7ac  test    [rcx+1Ch], r12b
0x18006d7b0  jz      loc_18006D8AD
0x18006d7b6  cmp     byte ptr [rcx+19h], 2
0x18006d7ba  jb      loc_18006D8AD
0x18006d7c0  mov     edx, 27h ; '''
0x18006d7c5  mov     r9d, edi
0x18006d7c8  jmp     loc_18006D896
0x18006d7cd  lea     r8, [rsp+290h+var_250]
0x18006d7d2  mov     rdx, r14
0x18006d7d5  mov     rcx, r15
0x18006d7d8  call    StringCchCopyWrapW
0x18006d7dd  mov     edi, eax
0x18006d7df  test    eax, eax
0x18006d7e1  jnz     loc_18006D876
0x18006d7e7  lea     rcx, aMicrosoftNetwo; "\\Microsoft\\Network\\Connections\\Pbk"...
0x18006d7ee  call    cs:__imp_lstrlenW
0x18006d7f5  nop     dword ptr [rax+rax+00h]
0x18006d7fa  mov     ebx, 104h
0x18006d7ff  mov     rcx, r15; lpString
0x18006d802  sub     ebx, eax
0x18006d804  call    cs:__imp_lstrlenW
0x18006d80b  nop     dword ptr [rax+rax+00h]
0x18006d810  cmp     eax, ebx
0x18006d812  jg      loc_18006D8A6
0x18006d818  lea     r8, aMicrosoftNetwo; "\\Microsoft\\Network\\Connections\\Pbk"...
0x18006d81f  mov     [rsp+290h+dwFlags], 100h; dwFlags
0x18006d827  mov     rdx, r14; cchDest
0x18006d82a  mov     rcx, r15; pszDest
0x18006d82d  call    StringCchCatExW
0x18006d832  test    eax, eax
0x18006d834  jns     short loc_18006D86F
0x18006d836  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d83d  cmp     rcx, r13
0x18006d840  jz      short loc_18006D86B
0x18006d842  test    [rcx+1Ch], r12b
0x18006d846  jz      short loc_18006D86B
0x18006d848  cmp     byte ptr [rcx+19h], 2
0x18006d84c  jb      short loc_18006D86B
0x18006d84e  mov     rcx, [rcx+10h]
0x18006d852  lea     edx, [rdi+28h]
0x18006d855  mov     r9d, eax
0x18006d858  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d85f  call    WPP_SF_d
0x18006d864  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d86b  xor     esi, esi
0x18006d86d  jmp     short loc_18006D8AD
0x18006d86f  mov     esi, 1
0x18006d874  jmp     short loc_18006D8A6
0x18006d876  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d87d  cmp     rcx, r13
0x18006d880  jz      short loc_18006D8AD
0x18006d882  test    [rcx+1Ch], r12b
0x18006d886  jz      short loc_18006D8AD
0x18006d888  cmp     byte ptr [rcx+19h], 2
0x18006d88c  jb      short loc_18006D8AD
0x18006d88e  mov     edx, 29h ; ')'
0x18006d893  mov     r9d, eax
0x18006d896  mov     rcx, [rcx+10h]
0x18006d89a  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d8a1  call    WPP_SF_d
0x18006d8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d8ad  mov     rax, [rsp+290h+hMem]
0x18006d8b2  test    rax, rax
0x18006d8b5  jz      short loc_18006D8CD
0x18006d8b7  mov     rcx, rax; hMem
0x18006d8ba  call    cs:__imp_GlobalFree
0x18006d8c1  nop     dword ptr [rax+rax+00h]
0x18006d8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d8cd  mov     rax, [rsp+290h+TokenHandle]
0x18006d8d2  test    rax, rax
0x18006d8d5  jz      short loc_18006D8ED
0x18006d8d7  mov     rcx, rax; hObject
0x18006d8da  call    cs:__imp_CloseHandle
0x18006d8e1  nop     dword ptr [rax+rax+00h]
0x18006d8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d8ed  test    edi, edi
0x18006d8ef  jz      short loc_18006D91E
0x18006d8f1  cmp     rcx, r13
0x18006d8f4  jz      short loc_18006D91A
0x18006d8f6  test    [rcx+1Ch], r12b
0x18006d8fa  jz      short loc_18006D91A
0x18006d8fc  cmp     byte ptr [rcx+19h], 6
0x18006d900  jb      short loc_18006D91A
0x18006d902  mov     rcx, [rcx+10h]
0x18006d906  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d90d  mov     edx, 2Bh ; '+'
0x18006d912  xor     r9d, r9d
0x18006d915  call    WPP_SF_c
0x18006d91a  xor     eax, eax
0x18006d91c  jmp     short loc_18006D94C
0x18006d91e  cmp     rcx, r13
0x18006d921  jz      short loc_18006D94A
0x18006d923  test    [rcx+1Ch], r12b
0x18006d927  jz      short loc_18006D94A
0x18006d929  cmp     byte ptr [rcx+19h], 6
0x18006d92d  jb      short loc_18006D94A
0x18006d92f  mov     rcx, [rcx+10h]
0x18006d933  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d93a  test    esi, esi
0x18006d93c  mov     edx, 2Ch ; ','
0x18006d941  setnz   r9b
0x18006d945  call    WPP_SF_c
0x18006d94a  mov     eax, esi
0x18006d94c  mov     rcx, [rbp+190h+var_40]
0x18006d953  xor     rcx, rsp; StackCookie
0x18006d956  call    __security_check_cookie
0x18006d95b  mov     rbx, [rsp+290h+arg_10]
0x18006d963  add     rsp, 260h
0x18006d96a  pop     r15
0x18006d96c  pop     r14
0x18006d96e  pop     r13
0x18006d970  pop     r12
0x18006d972  pop     rdi
0x18006d973  pop     rsi
0x18006d974  pop     rbp
0x18006d975  retn
```
