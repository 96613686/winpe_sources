# IsProcessILGreaterThanOrEqual(ulong)

- ea: `0x18005ee20`
- end: `0x18005ef37`
- name: `?IsProcessILGreaterThanOrEqual@@YAHK@Z`
- size: `279`
- prototype: `int __fastcall(unsigned int dwRID)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005e858`
- `0x1801ab048`

## callees

- `0x18005ee20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ef00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ef00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eea8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eea8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ef17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ef17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ee41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ee41`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005ee54`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005ee54`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005eeef`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005eeef`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18005eedf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18005eedf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ee7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005eed0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ee7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005eed0`

## pseudocode

```c
__int64 __fastcall IsProcessILGreaterThanOrEqual(unsigned int dwRID)
{
  HANDLE CurrentProcess; // rax
  unsigned int TokenInformation; // edi
  DWORD LastError; // eax
  PSID *v5; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  unsigned int dwBufSize; // [rsp+48h] [rbp+10h] BYREF
  void *hToken; // [rsp+50h] [rbp+18h] BYREF

  dwBufSize = 0;
  hToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &hToken) )
    return 0;
  TokenInformation = GetTokenInformation(hToken, TokenIntegrityLevel, 0, 0, &dwBufSize);
  LastError = GetLastError();
  if ( TokenInformation || LastError != 122 )
  {
    v5 = 0;
LABEL_7:
    TokenInformation = 0;
    goto LABEL_8;
  }
  v5 = (PSID *)HeapAlloc(g_hHeap, 0, dwBufSize);
  if ( v5 )
  {
    TokenInformation = GetTokenInformation(hToken, TokenIntegrityLevel, v5, dwBufSize, &dwBufSize);
    if ( TokenInformation )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
      if ( *GetSidSubAuthority(*v5, (unsigned __int8)(*SidSubAuthorityCount - 1)) < dwRID )
        goto LABEL_7;
    }
  }
LABEL_8:
  CloseHandle(hToken);
  if ( v5 )
    HeapFree(g_hHeap, 0, v5);
  return TokenInformation;
}

```

## disassembly

```asm
0x18005ee20  mov     rax, rsp
0x18005ee23  mov     [rax+8], rbx
0x18005ee27  mov     [rax+20h], rsi
0x18005ee2b  push    rdi
0x18005ee2c  sub     rsp, 30h
0x18005ee30  mov     esi, dwRID
0x18005ee32  mov     dword ptr [rax+10h], 0
0x18005ee39  mov     qword ptr [rax+18h], 0
0x18005ee41  call    cs:__imp_GetCurrentProcess
0x18005ee47  lea     r8, [rsp+38h+hToken]; TokenHandle
0x18005ee4c  mov     edx, 8; DesiredAccess
0x18005ee51  mov     rcx, rax; ProcessHandle
0x18005ee54  call    cs:__imp_OpenProcessToken
0x18005ee5a  test    eax, eax
0x18005ee5c  jz      loc_18005EF33
0x18005ee62  mov     rcx, [rsp+38h+hToken]; TokenHandle
0x18005ee67  lea     rax, [rsp+38h+dwBufSize]
0x18005ee6c  xor     r9d, r9d; TokenInformationLength
0x18005ee6f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005ee74  xor     r8d, r8d; TokenInformation
0x18005ee77  lea     edx, [r9+19h]; TokenInformationClass
0x18005ee7b  call    cs:__imp_GetTokenInformation
0x18005ee81  mov     edi, eax
0x18005ee83  call    cs:__imp_GetLastError
0x18005ee89  test    edi, edi
0x18005ee8b  jnz     loc_18005EF2F
0x18005ee91  cmp     eax, 7Ah ; 'z'
0x18005ee94  jnz     loc_18005EF2F
0x18005ee9a  mov     r8d, [rsp+38h+dwBufSize]; dwBytes
0x18005ee9f  xor     edx, edx; dwFlags
0x18005eea1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005eea8  call    cs:__imp_HeapAlloc
0x18005eeae  mov     rbx, rax
0x18005eeb1  test    rax, rax
0x18005eeb4  jz      short loc_18005EEFB
0x18005eeb6  mov     r9d, [rsp+38h+dwBufSize]; TokenInformationLength
0x18005eebb  lea     rax, [rsp+38h+dwBufSize]
0x18005eec0  mov     rcx, [rsp+38h+hToken]; TokenHandle
0x18005eec5  lea     edx, [rdi+19h]; TokenInformationClass
0x18005eec8  mov     r8, rbx; TokenInformation
0x18005eecb  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005eed0  call    cs:__imp_GetTokenInformation
0x18005eed6  mov     edi, eax
0x18005eed8  test    eax, eax
0x18005eeda  jz      short loc_18005EEFB
0x18005eedc  mov     rcx, [rbx]; pSid
0x18005eedf  call    cs:__imp_GetSidSubAuthorityCount
0x18005eee5  mov     cl, [rax]
0x18005eee7  dec     cl
0x18005eee9  movzx   edx, cl; nSubAuthority
0x18005eeec  mov     rcx, [rbx]; pSid
0x18005eeef  call    cs:__imp_GetSidSubAuthority
0x18005eef5  cmp     [rax], esi
0x18005eef7  jnb     short loc_18005EEFB
0x18005eef9  xor     edi, edi
0x18005eefb  mov     rcx, [rsp+38h+hToken]; hObject
0x18005ef00  call    cs:__imp_CloseHandle
0x18005ef06  test    rbx, rbx
0x18005ef09  jz      short loc_18005EF1D
0x18005ef0b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005ef12  mov     r8, rbx; lpMem
0x18005ef15  xor     edx, edx; dwFlags
0x18005ef17  call    cs:__imp_HeapFree
0x18005ef1d  mov     eax, edi
0x18005ef1f  mov     rbx, [rsp+38h+arg_0]
0x18005ef24  mov     rsi, [rsp+38h+arg_18]
0x18005ef29  add     rsp, 30h
0x18005ef2d  pop     rdi
0x18005ef2e  retn
0x18005ef2f  xor     ebx, ebx
0x18005ef31  jmp     short loc_18005EEF9
0x18005ef33  xor     eax, eax
0x18005ef35  jmp     short loc_18005EF1F
```
