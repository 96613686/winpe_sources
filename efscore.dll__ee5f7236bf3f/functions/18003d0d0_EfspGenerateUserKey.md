# EfspGenerateUserKey

- ea: `0x18003d0d0`
- end: `0x18003d33f`
- name: `EfspGenerateUserKey`
- size: `623`
- prototype: `__int64 __fastcall(struct _EFS_USER_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017ab4`
- `0x1800392a0`

## callees

- `0x180010bf0`
- `0x18003c9d8`
- `0x18003cfe0`
- `0x18003d0d0`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18003d126`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18003d126`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003d302`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003d302`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d1a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d1a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d310`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d323`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d323`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d25f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d25f`

## pseudocode

```c
__int64 __fastcall EfspGenerateUserKey(struct _EFS_USER_INFO *a1, __int64 a2, _QWORD *a3)
{
  int v3; // ebp
  unsigned __int16 *v4; // rdx
  __int64 v6; // rcx
  DWORD MutexName; // edi
  HANDLE MutexW; // rbx
  int v9; // r8d
  char v10; // r15
  int v11; // eax
  DWORD v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  DWORD LastError; // eax
  char v16; // bp
  int v17; // eax
  DWORD dwDisposition; // [rsp+80h] [rbp+8h] BYREF
  LPCWSTR lpName; // [rsp+90h] [rbp+18h]
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v4 = (unsigned __int16 *)*((_QWORD *)a1 + 3);
  *a3 = 0;
  dwDisposition = 0;
  hKey = 0;
  lpName = 0;
  MutexName = EfspGenerateMutexName(L"Local\\{6F884C5F-38C5-4662-BC91-53BD684CCB0D}", v4);
  if ( MutexName )
  {
    MutexW = 0;
    goto LABEL_18;
  }
  MutexW = CreateMutexW(0, 1, lpName);
  if ( !MutexW )
  {
    MutexName = GetLastError();
    v9 = MutexName;
    v10 = 91;
LABEL_4:
    v11 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v9, 12, v10);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 12, v10);
    goto LABEL_18;
  }
  if ( GetLastError() != 183 )
  {
    LastError = RegCreateKeyExW(
                  HKEY_USERS,
                  *((LPCWSTR *)a1 + 4),
                  0,
                  (LPWSTR)L"REG_SZ",
                  0,
                  0x2001Fu,
                  0,
                  &hKey,
                  &dwDisposition);
    MutexName = LastError;
    if ( LastError )
    {
      v16 = -94;
    }
    else
    {
      if ( (unsigned int)EfspEnrollKeyPair(a1) )
        goto LABEL_14;
      LastError = GetLastError();
      MutexName = LastError;
      v16 = -84;
    }
    v17 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 12, v16);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v17, 12, v16);
LABEL_14:
    v3 = 1;
    goto LABEL_18;
  }
  v12 = WaitForSingleObject(MutexW, 0xFFFFFFFF);
  if ( v12 != -1 )
  {
    if ( v12 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v13);
    MutexName = 1237;
    v3 = 1;
    v9 = 1237;
    v10 = -127;
    goto LABEL_4;
  }
  MutexName = GetLastError();
  v14 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, MutexName, 12, 123);
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v14, 12, 123);
  v3 = 0;
LABEL_18:
  if ( lpName )
    EfsFreeHeap((LPVOID)lpName);
  if ( v3 )
  {
    if ( !MutexW )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    ReleaseMutex(MutexW);
  }
  if ( MutexW )
    CloseHandle(MutexW);
  if ( hKey )
    RegCloseKey(hKey);
  return MutexName;
}

```

## disassembly

```asm
0x18003d0d0  mov     rax, rsp
0x18003d0d3  mov     [rax+10h], rbx
0x18003d0d7  push    rbp
0x18003d0d8  push    rsi
0x18003d0d9  push    rdi
0x18003d0da  push    r12
0x18003d0dc  push    r15
0x18003d0de  sub     rsp, 50h
0x18003d0e2  xor     ebp, ebp
0x18003d0e4  mov     r12b, dl
0x18003d0e7  mov     rdx, [rcx+18h]; unsigned __int16 *
0x18003d0eb  mov     r15, r8
0x18003d0ee  mov     [r8], rbp
0x18003d0f1  mov     rsi, rcx
0x18003d0f4  lea     r8, [rax+18h]
0x18003d0f8  mov     [rax+8], ebp
0x18003d0fb  lea     rcx, aLocal6f884c5f3; "Local\\{6F884C5F-38C5-4662-BC91-53BD684"...
0x18003d102  mov     [rax+20h], rbp
0x18003d106  mov     [rax+18h], rbp
0x18003d10a  call    EfspGenerateMutexName
0x18003d10f  mov     edi, eax
0x18003d111  test    eax, eax
0x18003d113  jnz     loc_18003D2D7
0x18003d119  mov     r8, [rsp+78h+lpName]; lpName
0x18003d121  lea     edx, [rbp+1]; bInitialOwner
0x18003d124  xor     ecx, ecx; lpMutexAttributes
0x18003d126  call    cs:__imp_CreateMutexW
0x18003d12c  mov     rbx, rax
0x18003d12f  test    rax, rax
0x18003d132  jnz     short loc_18003D188
0x18003d134  call    cs:__imp_GetLastError
0x18003d13a  mov     edi, eax
0x18003d13c  mov     r8d, eax
0x18003d13f  mov     r15d, 25Bh
0x18003d145  mov     rcx, cs:g_hPublisher
0x18003d14c  lea     rdx, EFS_API_ERROR
0x18003d153  mov     esi, 0Ch
0x18003d158  mov     [rsp+78h+dwOptions], r15d
0x18003d15d  mov     r9d, esi
0x18003d160  call    fnEfsLogTrace1
0x18003d165  mov     rcx, cs:g_hPublisher
0x18003d16c  lea     rdx, EFS_TRACE_ERROR
0x18003d173  mov     r9d, esi
0x18003d176  mov     [rsp+78h+dwOptions], r15d
0x18003d17b  mov     r8d, eax
0x18003d17e  call    fnEfsLogTrace1
0x18003d183  jmp     loc_18003D2D9
0x18003d188  call    cs:__imp_GetLastError
0x18003d18e  cmp     eax, 0B7h
0x18003d193  jnz     loc_18003D21F
0x18003d199  or      edi, 0FFFFFFFFh
0x18003d19c  mov     rcx, rbx; hHandle
0x18003d19f  mov     edx, edi; dwMilliseconds
0x18003d1a1  call    cs:__imp_WaitForSingleObject
0x18003d1a7  cmp     eax, edi
0x18003d1a9  jnz     short loc_18003D1FE
0x18003d1ab  call    cs:__imp_GetLastError
0x18003d1b1  mov     rcx, cs:g_hPublisher
0x18003d1b8  lea     rdx, EFS_API_ERROR
0x18003d1bf  mov     esi, 0Ch
0x18003d1c4  mov     ebp, 27Bh
0x18003d1c9  mov     r9d, esi
0x18003d1cc  mov     [rsp+78h+dwOptions], ebp
0x18003d1d0  mov     r8d, eax
0x18003d1d3  mov     edi, eax
0x18003d1d5  call    fnEfsLogTrace1
0x18003d1da  mov     rcx, cs:g_hPublisher
0x18003d1e1  lea     rdx, EFS_TRACE_ERROR
0x18003d1e8  mov     r9d, esi
0x18003d1eb  mov     [rsp+78h+dwOptions], ebp
0x18003d1ef  mov     r8d, eax
0x18003d1f2  call    fnEfsLogTrace1
0x18003d1f7  xor     ebp, ebp
0x18003d1f9  jmp     loc_18003D2D9
0x18003d1fe  test    eax, eax
0x18003d200  jz      short loc_18003D207
0x18003d202  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "rc == WAIT_OBJECT_0")
0x18003d207  mov     edi, 4D5h
0x18003d20c  mov     ebp, 1
0x18003d211  mov     r8d, edi
0x18003d214  mov     r15d, 281h
0x18003d21a  jmp     loc_18003D145
0x18003d21f  mov     rdx, [rsi+20h]; lpSubKey
0x18003d223  lea     rax, [rsp+78h+dwDisposition]
0x18003d22b  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18003d230  lea     r9, Class; "REG_SZ"
0x18003d237  lea     rax, [rsp+78h+hKey]
0x18003d23f  xor     r8d, r8d; Reserved
0x18003d242  mov     [rsp+78h+phkResult], rax; phkResult
0x18003d247  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003d24e  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18003d253  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18003d25b  mov     [rsp+78h+dwOptions], ebp; dwOptions
0x18003d25f  call    cs:__imp_RegCreateKeyExW
0x18003d265  mov     edi, eax
0x18003d267  test    eax, eax
0x18003d269  jz      short loc_18003D2B6
0x18003d26b  mov     ebp, 2A2h
0x18003d270  mov     rcx, cs:g_hPublisher
0x18003d277  lea     rdx, EFS_API_ERROR
0x18003d27e  mov     esi, 0Ch
0x18003d283  mov     [rsp+78h+dwOptions], ebp
0x18003d287  mov     r9d, esi
0x18003d28a  mov     r8d, eax
0x18003d28d  call    fnEfsLogTrace1
0x18003d292  mov     rcx, cs:g_hPublisher
0x18003d299  lea     rdx, EFS_TRACE_ERROR
0x18003d2a0  mov     r9d, esi
0x18003d2a3  mov     [rsp+78h+dwOptions], ebp
0x18003d2a7  mov     r8d, eax
0x18003d2aa  call    fnEfsLogTrace1
0x18003d2af  mov     ebp, 1
0x18003d2b4  jmp     short loc_18003D2D9
0x18003d2b6  mov     r8, r15
0x18003d2b9  mov     dl, r12b
0x18003d2bc  mov     rcx, rsi; struct _EFS_USER_INFO *
0x18003d2bf  call    EfspEnrollKeyPair
0x18003d2c4  test    eax, eax
0x18003d2c6  jnz     short loc_18003D2AF
0x18003d2c8  call    cs:__imp_GetLastError
0x18003d2ce  mov     edi, eax
0x18003d2d0  mov     ebp, 2ACh
0x18003d2d5  jmp     short loc_18003D270
0x18003d2d7  xor     ebx, ebx
0x18003d2d9  cmp     [rsp+78h+lpName], 0
0x18003d2e2  jz      short loc_18003D2F1
0x18003d2e4  mov     rcx, [rsp+78h+lpName]; lpMem
0x18003d2ec  call    EfsFreeHeap
0x18003d2f1  test    ebp, ebp
0x18003d2f3  jz      short loc_18003D308
0x18003d2f5  test    rbx, rbx
0x18003d2f8  jnz     short loc_18003D2FF
0x18003d2fa  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != hMutex")
0x18003d2ff  mov     rcx, rbx; hMutex
0x18003d302  call    cs:__imp_ReleaseMutex
0x18003d308  test    rbx, rbx
0x18003d30b  jz      short loc_18003D316
0x18003d30d  mov     rcx, rbx; hObject
0x18003d310  call    cs:__imp_CloseHandle
0x18003d316  mov     rcx, [rsp+78h+hKey]; hKey
0x18003d31e  test    rcx, rcx
0x18003d321  jz      short loc_18003D329
0x18003d323  call    cs:__imp_RegCloseKey
0x18003d329  mov     rbx, [rsp+78h+arg_8]
0x18003d331  mov     eax, edi
0x18003d333  add     rsp, 50h
0x18003d337  pop     r15
0x18003d339  pop     r12
0x18003d33b  pop     rdi
0x18003d33c  pop     rsi
0x18003d33d  pop     rbp
0x18003d33e  retn
```
