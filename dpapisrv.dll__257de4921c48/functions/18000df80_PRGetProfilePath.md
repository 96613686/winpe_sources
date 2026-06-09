# PRGetProfilePath

- ea: `0x18000df80`
- end: `0x18000e0b6`
- name: `PRGetProfilePath`
- size: `310`
- prototype: `__int64 __fastcall(void *, WCHAR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004e60`
- `0x18000dd40`
- `0x1800285dc`

## callees

- `0x180007f10`
- `0x18000df80`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e003`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e088`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dfc3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000dfc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dfa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000dfa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e01b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e01b`
- `USERENV!GetUserProfileDirectoryW` at `0x18000dfe0`
- `USERENV!GetUserProfileDirectoryW` at `0x18000dfe0`

## string_xrefs

- `0x18000e05b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x18000e09a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall PRGetProfilePath(void *a1, WCHAR *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  int v6; // edx
  DWORD cchSize; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  cchSize = 260;
  TokenHandle = 0;
  *a2 = 0;
  if ( a1 )
    goto LABEL_4;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    a1 = TokenHandle;
LABEL_4:
    if ( GetUserProfileDirectoryW(a1, a2, &cchSize) )
    {
      _o_wcscat_s(a2, 260, L"\\AppData\\Roaming");
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1278);
    }
    goto LABEL_6;
  }
  LastError = GetLastError();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_sDsd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v6,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"Status",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
      237);
LABEL_6:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18000df80  push    rbx
0x18000df82  sub     rsp, 40h
0x18000df86  xor     eax, eax
0x18000df88  mov     [rsp+48h+cchSize], 104h
0x18000df90  mov     [rsp+48h+TokenHandle], 0
0x18000df99  mov     rbx, rdx
0x18000df9c  mov     [rdx], ax
0x18000df9f  test    rcx, rcx
0x18000dfa2  jnz     short loc_18000DFD8
0x18000dfa4  call    cs:__imp_GetCurrentThread
0x18000dfab  nop     dword ptr [rax+rax+00h]
0x18000dfb0  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18000dfb5  mov     edx, 8; DesiredAccess
0x18000dfba  mov     rcx, rax; ThreadHandle
0x18000dfbd  mov     r8d, 1; OpenAsSelf
0x18000dfc3  call    cs:__imp_OpenThreadToken
0x18000dfca  nop     dword ptr [rax+rax+00h]
0x18000dfcf  test    eax, eax
0x18000dfd1  jz      short loc_18000E030
0x18000dfd3  mov     rcx, [rsp+48h+TokenHandle]; hToken
0x18000dfd8  lea     r8, [rsp+48h+cchSize]; lpcchSize
0x18000dfdd  mov     rdx, rbx; lpProfileDir
0x18000dfe0  call    cs:__imp_GetUserProfileDirectoryW
0x18000dfe7  nop     dword ptr [rax+rax+00h]
0x18000dfec  test    eax, eax
0x18000dfee  jz      loc_18000E088
0x18000dff4  lea     r8, aAppdataRoaming; "\\AppData\\Roaming"
0x18000dffb  mov     edx, 104h
0x18000e000  mov     rcx, rbx
0x18000e003  call    cs:__imp__o_wcscat_s
0x18000e00a  nop     dword ptr [rax+rax+00h]
0x18000e00f  xor     ebx, ebx
0x18000e011  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000e016  test    rcx, rcx
0x18000e019  jz      short loc_18000E027
0x18000e01b  call    cs:__imp_CloseHandle
0x18000e022  nop     dword ptr [rax+rax+00h]
0x18000e027  mov     eax, ebx
0x18000e029  add     rsp, 40h
0x18000e02d  pop     rbx
0x18000e02e  retn
0x18000e030  call    cs:__imp_GetLastError
0x18000e037  nop     dword ptr [rax+rax+00h]
0x18000e03c  mov     ebx, eax
0x18000e03e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e045  lea     rax, WPP_GLOBAL_Control
0x18000e04c  cmp     rcx, rax
0x18000e04f  jz      short loc_18000E011
0x18000e051  test    byte ptr [rcx+1Ch], 1
0x18000e055  jz      short loc_18000E011
0x18000e057  mov     rcx, [rcx+10h]
0x18000e05b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e062  mov     [rsp+48h+var_18], 4EDh
0x18000e06a  lea     r9, aStatus; "Status"
0x18000e071  mov     [rsp+48h+var_20], r8
0x18000e076  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000e07d  mov     [rsp+48h+var_28], ebx
0x18000e081  call    WPP_SF_sDsd
0x18000e086  jmp     short loc_18000E011
0x18000e088  call    cs:__imp_GetLastError
0x18000e08f  nop     dword ptr [rax+rax+00h]
0x18000e094  mov     r9d, 4FEh
0x18000e09a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e0a1  mov     ecx, eax
0x18000e0a3  lea     rdx, aStatus; "Status"
0x18000e0aa  mov     ebx, eax
0x18000e0ac  call    DebugTraceError
0x18000e0b1  jmp     loc_18000E011
```
