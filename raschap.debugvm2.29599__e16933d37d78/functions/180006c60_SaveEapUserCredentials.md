# SaveEapUserCredentials

- ea: `0x180006c60`
- end: `0x180007056`
- name: `SaveEapUserCredentials`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006a50`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x180006c60`
- `0x18000ea70`
- `0x18000ef70`
- `0x180010460`
- `0x18001124c`
- `0x1800125a4`
- `0x18001f6a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006e35`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006e85`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006e35`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006e85`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180006ccd`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180006cf3`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180006ccd`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180006cf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006dc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006dc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e95`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006eca`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fb8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006f54`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006f54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006f82`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006f82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006f1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006f1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006f23`

## pseudocode

```c
__int64 __fastcall SaveEapUserCredentials(
        int a1,
        const char *a2,
        const char *a3,
        const CHAR *a4,
        int cbMultiByte,
        HANDLE hSourceHandle,
        __int64 a7)
{
  char **v9; // rdi
  unsigned int HasWlanSvcMembership; // ebp
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  char **v16; // rax
  __int64 v17; // rdx
  char *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  char *v21; // rax
  __int64 v22; // rdx
  WCHAR *lpWideCharStr; // rax
  int v24; // eax
  DWORD LastError; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v29; // rax
  HANDLE Thread; // rax
  CWorkerThreadState *v31; // rcx
  int v33; // [rsp+70h] [rbp+8h] BYREF
  HANDLE TargetHandle; // [rsp+80h] [rbp+18h] BYREF

  v33 = a1;
  v9 = 0;
  if ( !a3 || !a4 || !cbMultiByte )
  {
    HasWlanSvcMembership = 87;
    goto LABEL_57;
  }
  HasWlanSvcMembership = 0;
  if ( a2 && *a2 )
    goto LABEL_13;
  if ( strchr(a3, 64) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_13;
    v13 = 58;
    goto LABEL_12;
  }
  if ( !strchr(a3, 92) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, a3);
    goto LABEL_57;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v13 = 59;
LABEL_12:
    WPP_SF_s(v12[2], v13, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, a3);
  }
LABEL_13:
  if ( !(unsigned int)SavedCredsFeatureEnabledForUsernamePassword() )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_57;
    v15 = 61;
    goto LABEL_16;
  }
  LOBYTE(v33) = 0;
  HasWlanSvcMembership = CallerHasWlanSvcMembership((bool *)&v33);
  if ( HasWlanSvcMembership )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v15 = 62;
LABEL_16:
      WPP_SF_(v14[2], v15, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
    }
  }
  else
  {
    if ( (_BYTE)v33 )
    {
      if ( !(unsigned int)CheckIfWirelessInterface(a7) )
        goto LABEL_57;
      v16 = (char **)LocalAlloc(0x40u, 0x28u);
      v9 = v16;
      if ( !v16 )
      {
        HasWlanSvcMembership = 8;
        goto LABEL_57;
      }
      v16[4] = (char *)-1LL;
      if ( a2 && *a2 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        v18 = (char *)LocalAlloc(0x40u, v17 + 1);
        *v9 = v18;
        if ( !v18 )
        {
          HasWlanSvcMembership = 8;
          goto LABEL_57;
        }
        v19 = -1;
        do
          ++v19;
        while ( a2[v19] );
        strcpy_s(v18, v19 + 1, a2);
      }
      v20 = -1;
      do
        ++v20;
      while ( a3[v20] );
      v21 = (char *)LocalAlloc(0x40u, v20 + 1);
      v9[1] = v21;
      if ( !v21 )
      {
        HasWlanSvcMembership = 8;
        goto LABEL_57;
      }
      v22 = -1;
      do
        ++v22;
      while ( a3[v22] );
      strcpy_s(v21, v22 + 1, a3);
      lpWideCharStr = (WCHAR *)LocalAlloc(0x40u, 0x202u);
      v9[2] = (char *)lpWideCharStr;
      if ( !lpWideCharStr )
      {
        HasWlanSvcMembership = 8;
        goto LABEL_57;
      }
      v24 = MultiByteToWideChar(0, 0, a4, cbMultiByte, lpWideCharStr, 257);
      if ( v24 )
      {
        *((_DWORD *)v9 + 6) = 2 * v24;
        TargetHandle = (HANDLE)-1LL;
        CurrentProcess = GetCurrentProcess();
        v29 = GetCurrentProcess();
        if ( DuplicateHandle(v29, hSourceHandle, CurrentProcess, &TargetHandle, 0, 1, 2u) )
        {
          v9[4] = (char *)TargetHandle;
          Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SaveCredsThread, v9, 0, 0);
          if ( Thread )
          {
            v9 = 0;
            CWorkerThreadState::SetThreadHandle(v31, Thread);
            goto LABEL_57;
          }
          LastError = GetLastError();
          HasWlanSvcMembership = LastError;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_57;
          v27 = 66;
        }
        else
        {
          LastError = GetLastError();
          HasWlanSvcMembership = LastError;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_57;
          v27 = 65;
        }
      }
      else
      {
        LastError = GetLastError();
        HasWlanSvcMembership = LastError;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_57;
        v27 = 64;
      }
      WPP_SF_d(v26[2], v27, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
      goto LABEL_57;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v15 = 63;
      goto LABEL_16;
    }
  }
LABEL_57:
  FreeEapCredStructure(v9);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
      HasWlanSvcMembership);
  return HasWlanSvcMembership;
}

```

## disassembly

```asm
0x180006c60  mov     rax, rsp
0x180006c63  mov     [rax+8], ecx
0x180006c66  push    rbp
0x180006c67  sub     rsp, 60h
0x180006c6b  mov     [rax+10h], rbx
0x180006c6f  mov     rbx, r8
0x180006c72  mov     [rax+20h], rsi
0x180006c76  mov     rsi, rdx
0x180006c79  mov     [rax-10h], rdi
0x180006c7d  mov     [rax-18h], r12
0x180006c81  xor     r12d, r12d
0x180006c84  mov     [rax-20h], r13
0x180006c88  mov     edi, r12d
0x180006c8b  mov     [rax-28h], r15
0x180006c8f  mov     r15, r9
0x180006c92  lea     r13, WPP_GLOBAL_Control
0x180006c99  test    r8, r8
0x180006c9c  jz      loc_180006FFC
0x180006ca2  test    r9, r9
0x180006ca5  jz      loc_180006FFC
0x180006cab  cmp     [rsp+68h+cbMultiByte], edi
0x180006cb2  jz      loc_180006FFC
0x180006cb8  mov     ebp, r12d
0x180006cbb  test    rdx, rdx
0x180006cbe  jz      short loc_180006CC5
0x180006cc0  cmp     [rdx], dil
0x180006cc3  jnz     short loc_180006D26
0x180006cc5  mov     edx, 40h ; '@'; Val
0x180006cca  mov     rcx, rbx; Str
0x180006ccd  call    cs:__imp_strchr
0x180006cd3  test    rax, rax
0x180006cd6  jz      short loc_180006CEB
0x180006cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cdf  cmp     rcx, r13
0x180006ce2  jz      short loc_180006D26
0x180006ce4  mov     edx, 3Ah ; ':'
0x180006ce9  jmp     short loc_180006D13
0x180006ceb  mov     edx, 5Ch ; '\'; Val
0x180006cf0  mov     rcx, rbx; Str
0x180006cf3  call    cs:__imp_strchr
0x180006cf9  test    rax, rax
0x180006cfc  jz      loc_180006FD6
0x180006d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d09  cmp     rcx, r13
0x180006d0c  jz      short loc_180006D26
0x180006d0e  mov     edx, 3Bh ; ';'
0x180006d13  mov     rcx, [rcx+10h]
0x180006d17  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180006d1e  mov     r9, rbx
0x180006d21  call    WPP_SF_s
0x180006d26  call    ?SavedCredsFeatureEnabledForUsernamePassword@@YAHXZ; SavedCredsFeatureEnabledForUsernamePassword(void)
0x180006d2b  test    eax, eax
0x180006d2d  jnz     short loc_180006D59
0x180006d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d36  cmp     rcx, r13
0x180006d39  jz      loc_180007001
0x180006d3f  mov     edx, 3Dh ; '='
0x180006d44  mov     rcx, [rcx+10h]
0x180006d48  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180006d4f  call    WPP_SF_
0x180006d54  jmp     loc_180007001
0x180006d59  lea     rcx, [rsp+68h+arg_0]; bool *
0x180006d5e  mov     byte ptr [rsp+68h+arg_0], dil
0x180006d63  call    ?CallerHasWlanSvcMembership@@YAKPEA_N@Z; CallerHasWlanSvcMembership(bool *)
0x180006d68  mov     ebp, eax
0x180006d6a  test    eax, eax
0x180006d6c  jz      short loc_180006D85
0x180006d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d75  cmp     rcx, r13
0x180006d78  jz      loc_180007001
0x180006d7e  mov     edx, 3Eh ; '>'
0x180006d83  jmp     short loc_180006D44
0x180006d85  cmp     byte ptr [rsp+68h+arg_0], dil
0x180006d8a  jnz     short loc_180006DA3
0x180006d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d93  cmp     rcx, r13
0x180006d96  jz      loc_180007001
0x180006d9c  mov     edx, 3Fh ; '?'
0x180006da1  jmp     short loc_180006D44
0x180006da3  mov     rcx, [rsp+68h+arg_30]
0x180006dab  call    CheckIfWirelessInterface
0x180006db0  test    eax, eax
0x180006db2  jz      loc_180007001
0x180006db8  mov     edx, 28h ; '('; uBytes
0x180006dbd  mov     ecx, 40h ; '@'; uFlags
0x180006dc2  call    cs:__imp_LocalAlloc
0x180006dc8  mov     rdi, rax
0x180006dcb  test    rax, rax
0x180006dce  jnz     short loc_180006DDA
0x180006dd0  mov     ebp, 8
0x180006dd5  jmp     loc_180007001
0x180006dda  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x180006de2  test    rsi, rsi
0x180006de5  jz      short loc_180006E3B
0x180006de7  cmp     [rsi], r12b
0x180006dea  jz      short loc_180006E3B
0x180006dec  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180006df3  inc     rdx
0x180006df6  cmp     [rsi+rdx], r12b
0x180006dfa  jnz     short loc_180006DF3
0x180006dfc  inc     rdx; uBytes
0x180006dff  mov     ecx, 40h ; '@'; uFlags
0x180006e04  call    cs:__imp_LocalAlloc
0x180006e0a  mov     [rdi], rax
0x180006e0d  test    rax, rax
0x180006e10  jnz     short loc_180006E1C
0x180006e12  mov     ebp, 8
0x180006e17  jmp     loc_180007001
0x180006e1c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180006e23  inc     rdx
0x180006e26  cmp     [rsi+rdx], r12b
0x180006e2a  jnz     short loc_180006E23
0x180006e2c  inc     rdx; SizeInBytes
0x180006e2f  mov     r8, rsi; Source
0x180006e32  mov     rcx, rax; Destination
0x180006e35  call    cs:__imp_strcpy_s
0x180006e3b  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180006e42  inc     rdx
0x180006e45  cmp     [rbx+rdx], r12b
0x180006e49  jnz     short loc_180006E42
0x180006e4b  inc     rdx; uBytes
0x180006e4e  mov     ecx, 40h ; '@'; uFlags
0x180006e53  call    cs:__imp_LocalAlloc
0x180006e59  mov     [rdi+8], rax
0x180006e5d  test    rax, rax
0x180006e60  jnz     short loc_180006E6C
0x180006e62  mov     ebp, 8
0x180006e67  jmp     loc_180007001
0x180006e6c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180006e73  inc     rdx
0x180006e76  cmp     [rbx+rdx], r12b
0x180006e7a  jnz     short loc_180006E73
0x180006e7c  inc     rdx; SizeInBytes
0x180006e7f  mov     r8, rbx; Source
0x180006e82  mov     rcx, rax; Destination
0x180006e85  call    cs:__imp_strcpy_s
0x180006e8b  mov     edx, 202h; uBytes
0x180006e90  mov     ecx, 40h ; '@'; uFlags
0x180006e95  call    cs:__imp_LocalAlloc
0x180006e9b  mov     [rdi+10h], rax
0x180006e9f  test    rax, rax
0x180006ea2  jnz     short loc_180006EAE
0x180006ea4  mov     ebp, 8
0x180006ea9  jmp     loc_180007001
0x180006eae  mov     r9d, [rsp+68h+cbMultiByte]; cbMultiByte
0x180006eb6  mov     r8, r15; lpMultiByteStr
0x180006eb9  mov     [rsp+68h+cchWideChar], 101h; cchWideChar
0x180006ec1  xor     edx, edx; dwFlags
0x180006ec3  xor     ecx, ecx; CodePage
0x180006ec5  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x180006eca  call    cs:__imp_MultiByteToWideChar
0x180006ed0  test    eax, eax
0x180006ed2  jnz     short loc_180006F09
0x180006ed4  call    cs:__imp_GetLastError
0x180006eda  mov     ebp, eax
0x180006edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ee3  cmp     rcx, r13
0x180006ee6  jz      loc_180007001
0x180006eec  mov     edx, 40h ; '@'
0x180006ef1  mov     rcx, [rcx+10h]
0x180006ef5  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180006efc  mov     r9d, eax
0x180006eff  call    WPP_SF_d
0x180006f04  jmp     loc_180007001
0x180006f09  add     eax, eax
0x180006f0b  mov     [rdi+18h], eax
0x180006f0e  mov     [rsp+68h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x180006f1a  call    cs:__imp_GetCurrentProcess
0x180006f20  mov     rbx, rax
0x180006f23  call    cs:__imp_GetCurrentProcess
0x180006f29  mov     rdx, [rsp+68h+hSourceHandle]; hSourceHandle
0x180006f31  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180006f39  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180006f41  mov     rcx, rax; hSourceProcessHandle
0x180006f44  mov     [rsp+68h+cchWideChar], 1; bInheritHandle
0x180006f4c  mov     r8, rbx; hTargetProcessHandle
0x180006f4f  mov     dword ptr [rsp+68h+lpWideCharStr], r12d; dwDesiredAccess
0x180006f54  call    cs:__imp_DuplicateHandle
0x180006f5a  test    eax, eax
0x180006f5c  jz      short loc_180006FB8
0x180006f5e  mov     rax, [rsp+68h+TargetHandle]
0x180006f66  lea     r8, ?SaveCredsThread@@YAKPEAX@Z; lpStartAddress
0x180006f6d  mov     qword ptr [rsp+68h+cchWideChar], r12; lpThreadId
0x180006f72  mov     r9, rdi; lpParameter
0x180006f75  xor     edx, edx; dwStackSize
0x180006f77  mov     [rdi+20h], rax
0x180006f7b  xor     ecx, ecx; lpThreadAttributes
0x180006f7d  mov     dword ptr [rsp+68h+lpWideCharStr], r12d; dwCreationFlags
0x180006f82  call    cs:__imp_CreateThread
0x180006f88  test    rax, rax
0x180006f8b  jnz     short loc_180006FAB
0x180006f8d  call    cs:__imp_GetLastError
0x180006f93  mov     ebp, eax
0x180006f95  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f9c  cmp     rcx, r13
0x180006f9f  jz      short loc_180007001
0x180006fa1  mov     edx, 42h ; 'B'
0x180006fa6  jmp     loc_180006EF1
0x180006fab  mov     rdx, rax; void *
0x180006fae  mov     rdi, r12
0x180006fb1  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x180006fb6  jmp     short loc_180007001
0x180006fb8  call    cs:__imp_GetLastError
0x180006fbe  mov     ebp, eax
0x180006fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fc7  cmp     rcx, r13
0x180006fca  jz      short loc_180007001
0x180006fcc  mov     edx, 41h ; 'A'
0x180006fd1  jmp     loc_180006EF1
0x180006fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fdd  cmp     rcx, r13
0x180006fe0  jz      short loc_180007001
0x180006fe2  mov     rcx, [rcx+10h]
0x180006fe6  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180006fed  mov     edx, 3Ch ; '<'
0x180006ff2  mov     r9, rbx
0x180006ff5  call    WPP_SF_s
0x180006ffa  jmp     short loc_180007001
0x180006ffc  mov     ebp, 57h ; 'W'
0x180007001  mov     rcx, rdi; hMem
0x180007004  call    ?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z; FreeEapCredStructure(_EapCredThreadArgs *)
0x180007009  mov     rcx, cs:WPP_GLOBAL_Control
0x180007010  mov     r15, [rsp+68h+var_28]
0x180007015  cmp     rcx, r13
0x180007018  mov     r13, [rsp+68h+var_20]
0x18000701d  mov     r12, [rsp+68h+var_18]
0x180007022  mov     rdi, [rsp+68h+var_10]
0x180007027  mov     rsi, [rsp+68h+arg_18]
0x18000702f  mov     rbx, [rsp+68h+arg_8]
0x180007034  jz      short loc_18000704E
0x180007036  mov     rcx, [rcx+10h]
0x18000703a  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180007041  mov     edx, 43h ; 'C'
0x180007046  mov     r9d, ebp
0x180007049  call    WPP_SF_d
0x18000704e  mov     eax, ebp
0x180007050  add     rsp, 60h
0x180007054  pop     rbp
0x180007055  retn
```
