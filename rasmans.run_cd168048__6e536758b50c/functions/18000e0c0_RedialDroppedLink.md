# RedialDroppedLink

- ea: `0x18000e0c0`
- end: `0x18000e89c`
- name: `RedialDroppedLink`
- size: `2012`
- prototype: `void __stdcall(PVOID)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000de20`
- `0x18000df7c`
- `0x18000e0c0`
- `0x18000eae0`
- `0x18000eb54`
- `0x18000ebe8`
- `0x18000ec50`
- `0x180060f08`
- `0x1800e8e96`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e551`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e551`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000e6a6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000e6a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e296`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e3b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e296`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e3b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e841`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000e267`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000e317`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000e267`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000e317`
- `USERENV!CreateEnvironmentBlock` at `0x18000e603`
- `USERENV!CreateEnvironmentBlock` at `0x18000e603`
- `USERENV!DestroyEnvironmentBlock` at `0x18000e826`
- `USERENV!DestroyEnvironmentBlock` at `0x18000e826`

## pseudocode

```c
void __fastcall RedialDroppedLink(CHAR *a1)
{
  DWORD v2; // r15d
  WCHAR *v3; // r14
  void *v4; // rdi
  _WORD *v5; // r13
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rax
  UINT SystemDirectoryW; // ebx
  WCHAR *v10; // rax
  struct _LIST_ENTRY *Flink; // rbx
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rax
  size_t v18; // rdi
  wchar_t *v19; // rax
  WCHAR *v20; // rsi
  struct _LIST_ENTRY *v21; // rbx
  DWORD v22; // eax
  DWORD v23; // eax
  __int16 v24; // r11
  struct _LIST_ENTRY *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  DWORD v28; // eax
  DWORD v29; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-69h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-49h] BYREF
  __int64 v32; // [rsp+130h] [rbp+67h]
  void *TokenHandle; // [rsp+138h] [rbp+6Fh] BYREF
  LPVOID Environment; // [rsp+140h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  TokenHandle = 0;
  v2 = 0;
  Environment = 0;
  v3 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"winsta0\\default";
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v32 = StrdupAtoW(a1 + 8, 0xFDE9u);
  v4 = (void *)v32;
  if ( !v32 )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v7 = 19;
LABEL_10:
      WPP_SF_(v6[1].Flink, v7, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_92;
    }
    goto LABEL_92;
  }
  v5 = (_WORD *)StrdupAtoW(a1 + 269, 0xFDE9u);
  if ( v5 )
  {
    v8 = (WCHAR *)LocalAlloc(0x40u, 0x20Au);
    v3 = v8;
    if ( !v8 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v7 = 21;
        goto LABEL_10;
      }
      goto LABEL_92;
    }
    SystemDirectoryW = GetSystemDirectoryW(v8, 0x105u);
    if ( SystemDirectoryW > 0x105 )
    {
      LocalFree(v3);
      v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * SystemDirectoryW);
      v3 = v10;
      if ( !v10 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_92;
        }
        Flink = WPP_GLOBAL_Control[1].Flink;
        LastError = GetLastError();
        v13 = 22;
        goto LABEL_27;
      }
      SystemDirectoryW = GetSystemDirectoryW(v10, SystemDirectoryW);
    }
    if ( !SystemDirectoryW )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_92;
      }
      Flink = WPP_GLOBAL_Control[1].Flink;
      LastError = GetLastError();
      v13 = 23;
LABEL_27:
      WPP_SF_d(Flink, v13, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, LastError);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_92;
    }
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v32 + 2 * v15) );
    v16 = -1;
    do
      ++v16;
    while ( v5[v16] );
    v17 = -1;
    do
      ++v17;
    while ( v3[v17] );
    v18 = (unsigned int)(v15 + 32 + v16 + v17);
    v19 = (wchar_t *)LocalAlloc(0x40u, 2 * v18);
    v20 = v19;
    if ( !v19 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_91;
      }
      v21 = WPP_GLOBAL_Control[1].Flink;
      v22 = GetLastError();
      WPP_SF_d(v21, 24, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v22);
LABEL_90:
      v6 = WPP_GLOBAL_Control;
LABEL_91:
      v4 = (void *)v32;
      goto LABEL_92;
    }
    v23 = StringCchCopyW(v19, v18, v3);
    if ( v23 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_89;
      }
      v26 = 25;
    }
    else
    {
      v27 = -1;
      do
        ++v27;
      while ( v3[v27] != v24 );
      v20[v27] = 92;
      do
        ++v14;
      while ( v3[v14] != v24 );
      v23 = StringCchPrintfW(&v20[v14 + 1], v18 - v14 - 1, L"rasautou -r -c -f \"%s\" -e \"%s\"", v32, v5);
      if ( v23 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_89;
        }
        v26 = 26;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 27, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v20);
        }
        if ( OpenProcessToken(*(HANDLE *)a1, 0xF01FFu, &TokenHandle) )
        {
          v23 = RasImpersonateUser(TokenHandle);
          v2 = v23;
          if ( !v23 )
          {
            if ( CreateEnvironmentBlock(&Environment, TokenHandle, 0) )
            {
              if ( CreateProcessAsUserW(
                     TokenHandle,
                     0,
                     v20,
                     0,
                     0,
                     0,
                     0x428u,
                     Environment,
                     0,
                     &StartupInfo,
                     &ProcessInformation) )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    32,
                    WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids,
                    ProcessInformation.dwProcessId);
                }
              }
              else
              {
                v29 = GetLastError();
                v2 = v29;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control[1].Flink,
                    31,
                    (unsigned int)WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids,
                    (_DWORD)v20,
                    v29);
                }
              }
            }
            else
            {
              v28 = GetLastError();
              v2 = v28;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 30, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v28);
              }
            }
            RasRevertToSelf();
            goto LABEL_89;
          }
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
LABEL_89:
            LocalFree(v20);
            goto LABEL_90;
          }
          v26 = 29;
        }
        else
        {
          v23 = GetLastError();
          v2 = v23;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_89;
          }
          v26 = 28;
        }
      }
    }
    WPP_SF_d(v25[1].Flink, v26, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v23);
    goto LABEL_89;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v7 = 20;
    goto LABEL_10;
  }
LABEL_92:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v6 = WPP_GLOBAL_Control;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    v6 = WPP_GLOBAL_Control;
  }
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    LocalFree(v4);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    LocalFree(v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( *(_QWORD *)a1 )
      CloseHandle(*(HANDLE *)a1);
    LocalFree(a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( Environment )
  {
    DestroyEnvironmentBlock(Environment);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    LocalFree(v3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 6u )
  {
    WPP_SF_d(v6[1].Flink, 33, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v2);
  }
}

```

## disassembly

```asm
0x18000e0c0  mov     [rsp-8+arg_18], rbx
0x18000e0c5  push    rbp
0x18000e0c6  push    rsi
0x18000e0c7  push    rdi
0x18000e0c8  push    r12
0x18000e0ca  push    r13
0x18000e0cc  push    r14
0x18000e0ce  push    r15
0x18000e0d0  lea     rbp, [rsp-27h]
0x18000e0d5  sub     rsp, 0F0h
0x18000e0dc  mov     r12, rcx
0x18000e0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0e6  lea     rax, WPP_GLOBAL_Control
0x18000e0ed  cmp     rcx, rax
0x18000e0f0  jz      short loc_18000E116
0x18000e0f2  test    dword ptr [rcx+1Ch], 2000h
0x18000e0f9  jz      short loc_18000E116
0x18000e0fb  cmp     byte ptr [rcx+19h], 6
0x18000e0ff  jb      short loc_18000E116
0x18000e101  mov     rcx, [rcx+10h]
0x18000e105  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e10c  mov     edx, 12h
0x18000e111  call    WPP_SF_
0x18000e116  xor     esi, esi
0x18000e118  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18000e11c  xor     edx, edx; Val
0x18000e11e  mov     [rbp+57h+TokenHandle], rsi
0x18000e122  mov     r15d, esi
0x18000e125  mov     [rbp+57h+Environment], rsi
0x18000e129  mov     r14d, esi
0x18000e12c  lea     ebx, [rsi+68h]
0x18000e12f  mov     r8d, ebx; Size
0x18000e132  call    memset_0
0x18000e137  xor     eax, eax
0x18000e139  mov     [rbp+57h+StartupInfo.cb], ebx
0x18000e13c  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18000e140  lea     rcx, [r12+8]; lpMultiByteStr
0x18000e145  lea     rax, aWinsta0Default; "winsta0\\default"
0x18000e14c  xorps   xmm0, xmm0
0x18000e14f  mov     ebx, 0FDE9h
0x18000e154  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x18000e158  mov     edx, ebx; CodePage
0x18000e15a  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18000e15e  call    StrdupAtoW
0x18000e163  mov     [rbp+57h+arg_0], rax
0x18000e167  mov     rdi, rax
0x18000e16a  test    rax, rax
0x18000e16d  jnz     short loc_18000E1BF
0x18000e16f  mov     r13d, esi
0x18000e172  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e179  lea     rbx, WPP_GLOBAL_Control
0x18000e180  cmp     rcx, rbx
0x18000e183  jz      loc_18000E757
0x18000e189  test    dword ptr [rcx+1Ch], 2000h
0x18000e190  jz      loc_18000E757
0x18000e196  cmp     byte ptr [rcx+19h], 2
0x18000e19a  jb      loc_18000E757
0x18000e1a0  lea     edx, [rsi+13h]
0x18000e1a3  mov     rcx, [rcx+10h]
0x18000e1a7  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e1ae  call    WPP_SF_
0x18000e1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ba  jmp     loc_18000E757
0x18000e1bf  lea     rcx, [r12+10Dh]; lpMultiByteStr
0x18000e1c7  mov     edx, ebx; CodePage
0x18000e1c9  call    StrdupAtoW
0x18000e1ce  mov     r13, rax
0x18000e1d1  test    rax, rax
0x18000e1d4  jnz     short loc_18000E209
0x18000e1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1dd  lea     rbx, WPP_GLOBAL_Control
0x18000e1e4  cmp     rcx, rbx
0x18000e1e7  jz      loc_18000E757
0x18000e1ed  test    dword ptr [rcx+1Ch], 2000h
0x18000e1f4  jz      loc_18000E757
0x18000e1fa  cmp     byte ptr [rcx+19h], 2
0x18000e1fe  jb      loc_18000E757
0x18000e204  lea     edx, [rax+14h]
0x18000e207  jmp     short loc_18000E1A3
0x18000e209  mov     edx, 20Ah; uBytes
0x18000e20e  mov     ecx, 40h ; '@'; uFlags
0x18000e213  call    cs:__imp_LocalAlloc
0x18000e21a  nop     dword ptr [rax+rax+00h]
0x18000e21f  mov     r14, rax
0x18000e222  test    rax, rax
0x18000e225  jnz     short loc_18000E25D
0x18000e227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e22e  lea     rbx, WPP_GLOBAL_Control
0x18000e235  cmp     rcx, rbx
0x18000e238  jz      loc_18000E757
0x18000e23e  test    dword ptr [rcx+1Ch], 2000h
0x18000e245  jz      loc_18000E757
0x18000e24b  cmp     byte ptr [rcx+19h], 2
0x18000e24f  jb      loc_18000E757
0x18000e255  lea     edx, [rax+15h]
0x18000e258  jmp     loc_18000E1A3
0x18000e25d  mov     esi, 105h
0x18000e262  mov     rcx, r14; lpBuffer
0x18000e265  mov     edx, esi; uSize
0x18000e267  call    cs:__imp_GetSystemDirectoryW
0x18000e26e  nop     dword ptr [rax+rax+00h]
0x18000e273  mov     ebx, eax
0x18000e275  cmp     eax, esi
0x18000e277  jbe     loc_18000E327
0x18000e27d  mov     rcx, r14; hMem
0x18000e280  call    cs:__imp_LocalFree
0x18000e287  nop     dword ptr [rax+rax+00h]
0x18000e28c  mov     edx, ebx
0x18000e28e  mov     ecx, 40h ; '@'; uFlags
0x18000e293  add     rdx, rdx; uBytes
0x18000e296  call    cs:__imp_LocalAlloc
0x18000e29d  nop     dword ptr [rax+rax+00h]
0x18000e2a2  xor     esi, esi
0x18000e2a4  mov     r14, rax
0x18000e2a7  test    rax, rax
0x18000e2aa  jnz     short loc_18000E312
0x18000e2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2b3  lea     rbx, WPP_GLOBAL_Control
0x18000e2ba  cmp     rcx, rbx
0x18000e2bd  jz      loc_18000E757
0x18000e2c3  test    dword ptr [rcx+1Ch], 2000h
0x18000e2ca  jz      loc_18000E757
0x18000e2d0  cmp     byte ptr [rcx+19h], 2
0x18000e2d4  jb      loc_18000E757
0x18000e2da  mov     rbx, [rcx+10h]
0x18000e2de  call    cs:__imp_GetLastError
0x18000e2e5  nop     dword ptr [rax+rax+00h]
0x18000e2ea  lea     edx, [rsi+16h]
0x18000e2ed  mov     r9d, eax
0x18000e2f0  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e2f7  mov     rcx, rbx
0x18000e2fa  call    WPP_SF_d
0x18000e2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e306  lea     rbx, WPP_GLOBAL_Control
0x18000e30d  jmp     loc_18000E757
0x18000e312  mov     edx, ebx; uSize
0x18000e314  mov     rcx, rax; lpBuffer
0x18000e317  call    cs:__imp_GetSystemDirectoryW
0x18000e31e  nop     dword ptr [rax+rax+00h]
0x18000e323  mov     ebx, eax
0x18000e325  jmp     short loc_18000E329
0x18000e327  xor     esi, esi
0x18000e329  test    ebx, ebx
0x18000e32b  jnz     short loc_18000E375
0x18000e32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e334  lea     rbx, WPP_GLOBAL_Control
0x18000e33b  cmp     rcx, rbx
0x18000e33e  jz      loc_18000E757
0x18000e344  test    dword ptr [rcx+1Ch], 2000h
0x18000e34b  jz      loc_18000E757
0x18000e351  cmp     byte ptr [rcx+19h], 2
0x18000e355  jb      loc_18000E757
0x18000e35b  mov     rbx, [rcx+10h]
0x18000e35f  call    cs:__imp_GetLastError
0x18000e366  nop     dword ptr [rax+rax+00h]
0x18000e36b  mov     edx, 17h
0x18000e370  jmp     loc_18000E2ED
0x18000e375  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e379  mov     r8, rbx
0x18000e37c  inc     r8
0x18000e37f  cmp     [rdi+r8*2], si
0x18000e384  jnz     short loc_18000E37C
0x18000e386  mov     rdx, rbx
0x18000e389  inc     rdx
0x18000e38c  cmp     [r13+rdx*2+0], si
0x18000e392  jnz     short loc_18000E389
0x18000e394  mov     rax, rbx
0x18000e397  inc     rax
0x18000e39a  cmp     [r14+rax*2], si
0x18000e39f  jnz     short loc_18000E397
0x18000e3a1  lea     rdi, [rdx+rax]
0x18000e3a5  add     r8, 20h ; ' '
0x18000e3a9  add     rdi, r8
0x18000e3ac  mov     ecx, 40h ; '@'; uFlags
0x18000e3b1  mov     edi, edi
0x18000e3b3  lea     rdx, [rdi+rdi]; uBytes
0x18000e3b7  call    cs:__imp_LocalAlloc
0x18000e3be  nop     dword ptr [rax+rax+00h]
0x18000e3c3  xor     r11d, r11d
0x18000e3c6  mov     rsi, rax
0x18000e3c9  test    rax, rax
0x18000e3cc  jnz     short loc_18000E42D
0x18000e3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3d5  lea     rbx, WPP_GLOBAL_Control
0x18000e3dc  cmp     rcx, rbx
0x18000e3df  jz      loc_18000E753
0x18000e3e5  test    dword ptr [rcx+1Ch], 2000h
0x18000e3ec  jz      loc_18000E753
0x18000e3f2  cmp     byte ptr [rcx+19h], 2
0x18000e3f6  jb      loc_18000E753
0x18000e3fc  mov     rbx, [rcx+10h]
0x18000e400  call    cs:__imp_GetLastError
0x18000e407  nop     dword ptr [rax+rax+00h]
0x18000e40c  lea     edx, [rsi+18h]
0x18000e40f  mov     rcx, rbx
0x18000e412  mov     r9d, eax
0x18000e415  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e41c  call    WPP_SF_d
0x18000e421  lea     rbx, WPP_GLOBAL_Control
0x18000e428  jmp     loc_18000E74C
0x18000e42d  mov     r8, r14; pszSrc
0x18000e430  mov     rdx, rdi; cchDest
0x18000e433  mov     rcx, rsi; pszDest
0x18000e436  call    StringCchCopyW
0x18000e43b  test    eax, eax
0x18000e43d  jz      short loc_18000E48B
0x18000e43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e446  lea     rbx, WPP_GLOBAL_Control
0x18000e44d  cmp     rcx, rbx
0x18000e450  jz      loc_18000E73D
0x18000e456  mov     edi, 2000h
0x18000e45b  test    [rcx+1Ch], edi
0x18000e45e  jz      loc_18000E73D
0x18000e464  cmp     byte ptr [rcx+19h], 2
0x18000e468  jb      loc_18000E73D
0x18000e46e  mov     edx, 19h
0x18000e473  mov     rcx, [rcx+10h]
0x18000e477  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e47e  mov     r9d, eax
0x18000e481  call    WPP_SF_d
0x18000e486  jmp     loc_18000E73D
0x18000e48b  mov     rax, rbx
0x18000e48e  inc     rax
0x18000e491  cmp     [r14+rax*2], r11w
0x18000e496  jnz     short loc_18000E48E
0x18000e498  mov     word ptr [rsi+rax*2], 5Ch ; '\'
0x18000e49e  inc     rbx
0x18000e4a1  cmp     [r14+rbx*2], r11w
0x18000e4a6  jnz     short loc_18000E49E
0x18000e4a8  mov     r9, [rbp+57h+arg_0]
0x18000e4ac  lea     r8, aRasautouRCFSES; "rasautou -r -c -f \"%s\" -e \"%s\""
0x18000e4b3  sub     rdi, rbx
0x18000e4b6  mov     [rsp+120h+lpThreadAttributes], r13
0x18000e4bb  inc     rbx
0x18000e4be  lea     rdx, [rdi-1]; unsigned __int64
0x18000e4c2  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18000e4c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e4cb  xor     ebx, ebx
0x18000e4cd  test    eax, eax
0x18000e4cf  jz      short loc_18000E509
0x18000e4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4d8  lea     rbx, WPP_GLOBAL_Control
0x18000e4df  cmp     rcx, rbx
0x18000e4e2  jz      loc_18000E73D
0x18000e4e8  test    dword ptr [rcx+1Ch], 2000h
0x18000e4ef  jz      loc_18000E73D
0x18000e4f5  cmp     byte ptr [rcx+19h], 2
0x18000e4f9  jb      loc_18000E73D
0x18000e4ff  mov     edx, 1Ah
0x18000e504  jmp     loc_18000E473
0x18000e509  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e510  lea     rax, WPP_GLOBAL_Control
0x18000e517  mov     edi, 2000h
0x18000e51c  cmp     rcx, rax
0x18000e51f  jz      short loc_18000E544
0x18000e521  test    [rcx+1Ch], edi
0x18000e524  jz      short loc_18000E544
0x18000e526  cmp     byte ptr [rcx+19h], 4
0x18000e52a  jb      short loc_18000E544
0x18000e52c  mov     rcx, [rcx+10h]
0x18000e530  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e537  mov     edx, 1Bh
0x18000e53c  mov     r9, rsi
0x18000e53f  call    WPP_SF_S
0x18000e544  mov     rcx, [r12]; ProcessHandle
0x18000e548  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000e54c  mov     edx, 0F01FFh; DesiredAccess
0x18000e551  call    cs:__imp_OpenProcessToken
0x18000e558  nop     dword ptr [rax+rax+00h]
0x18000e55d  test    eax, eax
0x18000e55f  jnz     short loc_18000E5B7
0x18000e561  call    cs:__imp_GetLastError
0x18000e568  nop     dword ptr [rax+rax+00h]
0x18000e56d  mov     r15d, eax
0x18000e570  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e577  lea     rbx, WPP_GLOBAL_Control
0x18000e57e  cmp     rcx, rbx
0x18000e581  jz      loc_18000E73D
0x18000e587  test    [rcx+1Ch], edi
0x18000e58a  jz      loc_18000E73D
0x18000e590  cmp     byte ptr [rcx+19h], 2
0x18000e594  jb      loc_18000E73D
0x18000e59a  mov     edx, 1Ch
0x18000e59f  mov     rcx, [rcx+10h]
0x18000e5a3  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e5aa  mov     r9d, eax
0x18000e5ad  call    WPP_SF_d
0x18000e5b2  jmp     loc_18000E73D
0x18000e5b7  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18000e5bb  call    RasImpersonateUser
0x18000e5c0  mov     r15d, eax
0x18000e5c3  test    eax, eax
0x18000e5c5  jz      short loc_18000E5F8
0x18000e5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5ce  lea     rbx, WPP_GLOBAL_Control
0x18000e5d5  cmp     rcx, rbx
0x18000e5d8  jz      loc_18000E73D
0x18000e5de  test    [rcx+1Ch], edi
0x18000e5e1  jz      loc_18000E73D
0x18000e5e7  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
