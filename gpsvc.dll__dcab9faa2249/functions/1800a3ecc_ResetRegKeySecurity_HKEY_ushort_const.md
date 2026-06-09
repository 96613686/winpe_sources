# ResetRegKeySecurity(HKEY__ *,ushort const *)

- ea: `0x1800a3ecc`
- end: `0x1800a4177`
- name: `?ResetRegKeySecurity@@YAHPEAUHKEY__@@PEBG@Z`
- size: `683`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053870`

## callees

- `0x180075ec0`
- `0x1800a3ecc`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3f6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a4158`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3f6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a4158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a407b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a40f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a407b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a40f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3f80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3f80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a404c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a40e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a404c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a40e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a40dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a40dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a406f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a406f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800a3f10`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800a3fe1`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800a3f10`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800a3fe1`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800a40d1`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800a40d1`

## string_xrefs

- `0x1800a3f32`: `ResetRegKeySecurity: RegGetKeySecurity returned 0`
- `0x1800a3f57`: `ResetRegKeySecurity: RegGetKeySecurity returned 0`
- `0x1800a3fae`: `ResetRegKeySecurity: Failed to allocate memory`
- `0x1800a3fc9`: `ResetRegKeySecurity: Failed to allocate memory`
- `0x1800a400d`: `ResetRegKeySecurity: Failed to query key security with %d`
- `0x1800a4035`: `ResetRegKeySecurity: Failed to query key security with %d`
- `0x1800a409b`: `ResetRegKeySecurity: Failed to open sub key with %d`
- `0x1800a40b9`: `ResetRegKeySecurity: Failed to open sub key with %d`
- `0x1800a4113`: `ResetRegKeySecure: Failed to set security, error = %d`
- `0x1800a413b`: `ResetRegKeySecure: Failed to set security, error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ResetRegKeySecurity(HKEY hKey, LPCWSTR lpSubKey)
{
  DWORD LastError; // ebx
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v6; // rdx
  HLOCAL v8; // rax
  void *v9; // rdi
  unsigned int KeySecurity; // esi
  void (*v11)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v12; // rdx
  unsigned int v13; // esi
  unsigned int v14; // edi
  HKEY hKeya; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  cbSecurityDescriptor = 0;
  hKeya = 0;
  LastError = GetLastError();
  RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
  if ( !cbSecurityDescriptor )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_9:
      SetLastError(LastError);
      return 0;
    }
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ResetRegKeySecurity: RegGetKeySecurity returned 0");
      }
      goto LABEL_9;
    }
    v6 = L"ResetRegKeySecurity: RegGetKeySecurity returned 0";
LABEL_5:
    v5(2u, v6);
    goto LABEL_9;
  }
  v8 = LocalAlloc(0x40u, cbSecurityDescriptor);
  v9 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_9;
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"ResetRegKeySecurity: Failed to allocate memory");
      goto LABEL_9;
    }
    v6 = L"ResetRegKeySecurity: Failed to allocate memory";
    goto LABEL_5;
  }
  KeySecurity = RegGetKeySecurity(hKey, 4u, v8, &cbSecurityDescriptor);
  if ( KeySecurity )
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_25:
      LocalFree(v9);
      goto LABEL_9;
    }
    v11 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"ResetRegKeySecurity: Failed to query key security with %d", KeySecurity);
      goto LABEL_25;
    }
    v12 = L"ResetRegKeySecurity: Failed to query key security with %d";
LABEL_21:
    v11(2u, v12, KeySecurity);
    goto LABEL_25;
  }
  KeySecurity = RegOpenKeyExW(hKey, lpSubKey, 0, 0x60008u, &hKeya);
  if ( KeySecurity )
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_25;
    v11 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"ResetRegKeySecurity: Failed to open sub key with %d", KeySecurity);
      goto LABEL_25;
    }
    v12 = L"ResetRegKeySecurity: Failed to open sub key with %d";
    goto LABEL_21;
  }
  v13 = RegSetKeySecurity(hKeya, 4u, v9);
  RegCloseKey(hKeya);
  LocalFree(v9);
  if ( v13 )
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ResetRegKeySecure: Failed to set security, error = %d", v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ResetRegKeySecure: Failed to set security, error = %d", v13);
      }
    }
    v14 = 0;
  }
  else
  {
    v14 = 1;
  }
  SetLastError(LastError);
  return v14;
}

```

## disassembly

```asm
0x1800a3ecc  mov     [rsp-28h+arg_0], rbx
0x1800a3ed1  mov     [rsp-28h+arg_8], rsi
0x1800a3ed6  push    rbp
0x1800a3ed7  push    rdi
0x1800a3ed8  push    r12
0x1800a3eda  push    r14
0x1800a3edc  push    r15
0x1800a3ede  mov     rbp, rsp
0x1800a3ee1  sub     rsp, 40h
0x1800a3ee5  mov     r15, rdx
0x1800a3ee8  mov     r14, rcx
0x1800a3eeb  xor     r12d, r12d
0x1800a3eee  mov     [rbp+cbSecurityDescriptor], r12d
0x1800a3ef2  mov     [rbp+hKey], r12
0x1800a3ef6  call    cs:__imp_GetLastError
0x1800a3efc  mov     ebx, eax
0x1800a3efe  mov     [rbp+arg_10], eax
0x1800a3f01  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800a3f05  xor     r8d, r8d; pSecurityDescriptor
0x1800a3f08  lea     edx, [r12+4]; SecurityInformation
0x1800a3f0d  mov     rcx, r14; hKey
0x1800a3f10  call    cs:__imp_RegGetKeySecurity
0x1800a3f16  mov     eax, [rbp+cbSecurityDescriptor]
0x1800a3f19  test    eax, eax
0x1800a3f1b  jnz     short loc_1800A3F78
0x1800a3f1d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a3f24  jz      short loc_1800A3F69
0x1800a3f26  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a3f2d  test    rax, rax
0x1800a3f30  jz      short loc_1800A3F45
0x1800a3f32  lea     rdx, aResetregkeysec_4; "ResetRegKeySecurity: RegGetKeySecurity "...
0x1800a3f39  mov     ecx, 2
0x1800a3f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f43  jmp     short loc_1800A3F69
0x1800a3f45  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a3f4c  jz      short loc_1800A3F69
0x1800a3f4e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a3f55  jz      short loc_1800A3F69
0x1800a3f57  lea     rdx, aResetregkeysec_4; "ResetRegKeySecurity: RegGetKeySecurity "...
0x1800a3f5e  mov     ecx, 2; unsigned int
0x1800a3f63  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a3f68  nop
0x1800a3f69  mov     ecx, ebx; dwErrCode
0x1800a3f6b  call    cs:__imp_SetLastError
0x1800a3f71  xor     eax, eax
0x1800a3f73  jmp     loc_1800A4160
0x1800a3f78  mov     rdx, rax; uBytes
0x1800a3f7b  mov     ecx, 40h ; '@'; uFlags
0x1800a3f80  call    cs:__imp_LocalAlloc
0x1800a3f86  mov     rdi, rax
0x1800a3f89  test    rax, rax
0x1800a3f8c  jnz     short loc_1800A3FD2
0x1800a3f8e  call    cs:__imp_GetLastError
0x1800a3f94  mov     ebx, eax
0x1800a3f96  mov     [rbp+arg_10], eax
0x1800a3f99  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a3fa0  jz      short loc_1800A3F69
0x1800a3fa2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a3fa9  test    rax, rax
0x1800a3fac  jz      short loc_1800A3FB7
0x1800a3fae  lea     rdx, aResetregkeysec_5; "ResetRegKeySecurity: Failed to allocate"...
0x1800a3fb5  jmp     short loc_1800A3F39
0x1800a3fb7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a3fbe  jz      short loc_1800A3F69
0x1800a3fc0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a3fc7  jz      short loc_1800A3F69
0x1800a3fc9  lea     rdx, aResetregkeysec_5; "ResetRegKeySecurity: Failed to allocate"...
0x1800a3fd0  jmp     short loc_1800A3F5E
0x1800a3fd2  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800a3fd6  mov     r8, rdi; pSecurityDescriptor
0x1800a3fd9  mov     edx, 4; SecurityInformation
0x1800a3fde  mov     rcx, r14; hKey
0x1800a3fe1  call    cs:__imp_RegGetKeySecurity
0x1800a3fe7  mov     esi, eax
0x1800a3fe9  test    eax, eax
0x1800a3feb  jz      short loc_1800A4057
0x1800a3fed  call    cs:__imp_GetLastError
0x1800a3ff3  mov     ebx, eax
0x1800a3ff5  mov     [rbp+arg_10], eax
0x1800a3ff8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a3fff  jz      short loc_1800A4049
0x1800a4001  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a4008  test    rax, rax
0x1800a400b  jz      short loc_1800A4023
0x1800a400d  lea     rdx, aResetregkeysec_3; "ResetRegKeySecurity: Failed to query ke"...
0x1800a4014  mov     r8d, esi
0x1800a4017  mov     ecx, 2
0x1800a401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4021  jmp     short loc_1800A4049
0x1800a4023  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a402a  jz      short loc_1800A4049
0x1800a402c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a4033  jz      short loc_1800A4049
0x1800a4035  lea     rdx, aResetregkeysec_3; "ResetRegKeySecurity: Failed to query ke"...
0x1800a403c  mov     r8d, esi
0x1800a403f  mov     ecx, 2; unsigned int
0x1800a4044  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a4049  mov     rcx, rdi; hMem
0x1800a404c  call    cs:__imp_LocalFree
0x1800a4052  jmp     loc_1800A3F69
0x1800a4057  lea     rax, [rbp+hKey]
0x1800a405b  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a4060  mov     r9d, 60008h; samDesired
0x1800a4066  xor     r8d, r8d; ulOptions
0x1800a4069  mov     rdx, r15; lpSubKey
0x1800a406c  mov     rcx, r14; hKey
0x1800a406f  call    cs:__imp_RegOpenKeyExW
0x1800a4075  mov     esi, eax
0x1800a4077  test    eax, eax
0x1800a4079  jz      short loc_1800A40C5
0x1800a407b  call    cs:__imp_GetLastError
0x1800a4081  mov     ebx, eax
0x1800a4083  mov     [rbp+arg_10], eax
0x1800a4086  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a408d  jz      short loc_1800A4049
0x1800a408f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a4096  test    rax, rax
0x1800a4099  jz      short loc_1800A40A7
0x1800a409b  lea     rdx, aResetregkeysec_2; "ResetRegKeySecurity: Failed to open sub"...
0x1800a40a2  jmp     loc_1800A4014
0x1800a40a7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a40ae  jz      short loc_1800A4049
0x1800a40b0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a40b7  jz      short loc_1800A4049
0x1800a40b9  lea     rdx, aResetregkeysec_2; "ResetRegKeySecurity: Failed to open sub"...
0x1800a40c0  jmp     loc_1800A403C
0x1800a40c5  mov     r8, rdi; pSecurityDescriptor
0x1800a40c8  mov     edx, 4; SecurityInformation
0x1800a40cd  mov     rcx, [rbp+hKey]; hKey
0x1800a40d1  call    cs:__imp_RegSetKeySecurity
0x1800a40d7  mov     esi, eax
0x1800a40d9  mov     rcx, [rbp+hKey]; hKey
0x1800a40dd  call    cs:__imp_RegCloseKey
0x1800a40e3  mov     rcx, rdi; hMem
0x1800a40e6  call    cs:__imp_LocalFree
0x1800a40ec  test    esi, esi
0x1800a40ee  jz      short loc_1800A4151
0x1800a40f0  call    cs:__imp_GetLastError
0x1800a40f6  mov     ebx, eax
0x1800a40f8  mov     [rbp+arg_10], eax
0x1800a40fb  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a4102  jz      short loc_1800A414C
0x1800a4104  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a410b  test    rax, rax
0x1800a410e  jz      short loc_1800A4126
0x1800a4110  mov     r8d, esi
0x1800a4113  lea     rdx, aResetregkeysec_1; "ResetRegKeySecure: Failed to set securi"...
0x1800a411a  mov     ecx, 2
0x1800a411f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4124  jmp     short loc_1800A414C
0x1800a4126  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a412d  jz      short loc_1800A414C
0x1800a412f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a4136  jz      short loc_1800A414C
0x1800a4138  mov     r8d, esi
0x1800a413b  lea     rdx, aResetregkeysec_1; "ResetRegKeySecure: Failed to set securi"...
0x1800a4142  mov     ecx, 2; unsigned int
0x1800a4147  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a414c  mov     edi, r12d
0x1800a414f  jmp     short loc_1800A4156
0x1800a4151  mov     edi, 1
0x1800a4156  mov     ecx, ebx; dwErrCode
0x1800a4158  call    cs:__imp_SetLastError
0x1800a415e  mov     eax, edi
0x1800a4160  mov     rbx, [rsp+40h+arg_0]
0x1800a4165  mov     rsi, [rsp+40h+arg_8]
0x1800a416a  add     rsp, 40h
0x1800a416e  pop     r15
0x1800a4170  pop     r14
0x1800a4172  pop     r12
0x1800a4174  pop     rdi
0x1800a4175  pop     rbp
0x1800a4176  retn
```
