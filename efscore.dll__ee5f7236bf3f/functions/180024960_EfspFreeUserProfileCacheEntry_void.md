# EfspFreeUserProfileCacheEntry(void *)

- ea: `0x180024960`
- end: `0x180024aae`
- name: `?EfspFreeUserProfileCacheEntry@@YAHPEAX@Z`
- size: `334`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024bc4`
- `0x180026328`

## callees

- `0x180024960`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800249cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800249cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800249b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800249b9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800249ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180024a43`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800249ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180024a43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a7c`
- `USERENV!UnloadUserProfile` at `0x180024a29`
- `USERENV!UnloadUserProfile` at `0x180024a29`
- `ntdll!NtClose` at `0x180024a86`
- `ntdll!NtClose` at `0x180024a86`
- `ntdll!RtlLeaveCriticalSection` at `0x180024a9b`
- `ntdll!RtlLeaveCriticalSection` at `0x180024a9b`
- `ntdll!RtlEnterCriticalSection` at `0x18002497b`
- `ntdll!RtlEnterCriticalSection` at `0x18002497b`

## pseudocode

```c
__int64 __fastcall EfspFreeUserProfileCacheEntry(void *a1)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  HANDLE CurrentThread; // rax
  DWORD v5; // eax
  DWORD LastError; // eax
  void *v7; // rdx
  DWORD v8; // eax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  TokenHandle = 0;
  RtlEnterCriticalSection(&GuardCacheListLock);
  if ( a1 && _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, 0xFFFFFFFF) == 1 )
  {
    v2 = 1;
    if ( *(_DWORD *)a1 != 40 || *((_DWORD *)a1 + 1) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v3);
    if ( NtCurrentTeb()->IsImpersonating )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      {
        if ( !SetThreadToken(0, 0) )
        {
          LastError = GetLastError();
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 3, 11);
        }
      }
      else
      {
        v5 = GetLastError();
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v5, 3, 7);
      }
    }
    UnloadUserProfile(*((HANDLE *)a1 + 3), *((HANDLE *)a1 + 4));
    v7 = TokenHandle;
    *((_QWORD *)a1 + 4) = 0;
    if ( v7 )
    {
      if ( !SetThreadToken(0, v7) )
      {
        v8 = GetLastError();
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v8, 3, 24);
      }
      CloseHandle(TokenHandle);
    }
    NtClose(*((HANDLE *)a1 + 3));
    *((_QWORD *)a1 + 3) = 0;
  }
  RtlLeaveCriticalSection(&GuardCacheListLock);
  return v2;
}

```

## disassembly

```asm
0x180024960  mov     [rsp+arg_8], rbx
0x180024965  push    rdi
0x180024966  sub     rsp, 30h
0x18002496a  mov     rbx, rcx
0x18002496d  xor     edi, edi
0x18002496f  lea     rcx, ?GuardCacheListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180024976  mov     [rsp+38h+TokenHandle], rdi
0x18002497b  call    cs:__imp_RtlEnterCriticalSection
0x180024981  test    rbx, rbx
0x180024984  jz      loc_180024A94
0x18002498a  or      eax, 0FFFFFFFFh
0x18002498d  lock xadd [rbx+10h], eax
0x180024992  cmp     eax, 1
0x180024995  jnz     loc_180024A94
0x18002499b  cmp     dword ptr [rbx], 28h ; '('
0x18002499e  mov     edi, eax
0x1800249a0  jnz     short loc_1800249A8
0x1800249a2  cmp     dword ptr [rbx+4], 0
0x1800249a6  jz      short loc_1800249AD
0x1800249a8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pUserProfileDesc->h.Size == sizeof(EFS_USER_PROFILE_DESCRIPTOR) && pUserProfileDesc->h.Type == EFS_DESC_ENTRY_TYPE_USER_INFO")
0x1800249ad  mov     eax, gs:179Ch
0x1800249b5  test    eax, eax
0x1800249b7  jz      short loc_180024A21
0x1800249b9  call    cs:__imp_GetCurrentThread
0x1800249bf  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800249c4  mov     r8d, edi; OpenAsSelf
0x1800249c7  mov     rcx, rax; ThreadHandle
0x1800249ca  mov     edx, 4; DesiredAccess
0x1800249cf  call    cs:__imp_OpenThreadToken
0x1800249d5  test    eax, eax
0x1800249d7  jnz     short loc_1800249E9
0x1800249d9  call    cs:__imp_GetLastError
0x1800249df  mov     [rsp+38h+var_18], 507h
0x1800249e7  jmp     short loc_180024A05
0x1800249e9  xor     edx, edx; Token
0x1800249eb  xor     ecx, ecx; Thread
0x1800249ed  call    cs:__imp_SetThreadToken
0x1800249f3  test    eax, eax
0x1800249f5  jnz     short loc_180024A21
0x1800249f7  call    cs:__imp_GetLastError
0x1800249fd  mov     [rsp+38h+var_18], 50Bh
0x180024a05  mov     rcx, cs:g_hPublisher
0x180024a0c  lea     rdx, EFS_API_ERROR
0x180024a13  mov     r9d, 3
0x180024a19  mov     r8d, eax
0x180024a1c  call    fnEfsLogTrace1
0x180024a21  mov     rdx, [rbx+20h]; hProfile
0x180024a25  mov     rcx, [rbx+18h]; hToken
0x180024a29  call    cs:__imp_UnloadUserProfile
0x180024a2f  mov     rdx, [rsp+38h+TokenHandle]; Token
0x180024a34  mov     qword ptr [rbx+20h], 0
0x180024a3c  test    rdx, rdx
0x180024a3f  jz      short loc_180024A82
0x180024a41  xor     ecx, ecx; Thread
0x180024a43  call    cs:__imp_SetThreadToken
0x180024a49  test    eax, eax
0x180024a4b  jnz     short loc_180024A77
0x180024a4d  call    cs:__imp_GetLastError
0x180024a53  mov     rcx, cs:g_hPublisher
0x180024a5a  lea     rdx, EFS_API_ERROR
0x180024a61  mov     r8d, eax
0x180024a64  mov     [rsp+38h+var_18], 518h
0x180024a6c  mov     r9d, 3
0x180024a72  call    fnEfsLogTrace1
0x180024a77  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180024a7c  call    cs:__imp_CloseHandle
0x180024a82  mov     rcx, [rbx+18h]; Handle
0x180024a86  call    cs:__imp_NtClose
0x180024a8c  mov     qword ptr [rbx+18h], 0
0x180024a94  lea     rcx, ?GuardCacheListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180024a9b  call    cs:__imp_RtlLeaveCriticalSection
0x180024aa1  mov     rbx, [rsp+38h+arg_8]
0x180024aa6  mov     eax, edi
0x180024aa8  add     rsp, 30h
0x180024aac  pop     rdi
0x180024aad  retn
```
