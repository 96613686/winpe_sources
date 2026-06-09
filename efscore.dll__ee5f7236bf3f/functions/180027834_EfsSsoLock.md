# EfsSsoLock

- ea: `0x180027834`
- end: `0x18002792c`
- name: `EfsSsoLock`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800276bc`

## callees

- `0x1800274b8`
- `0x180027834`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002789e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002789e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002791e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002791e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800278e0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800278e0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027894`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027894`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180027848`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180027848`

## pseudocode

```c
__int64 __fastcall EfsSsoLock(__int64 a1)
{
  DWORD LastError; // ebx
  DWORD v2; // eax
  __int64 *v3; // rdx
  char v5; // [rsp+20h] [rbp-18h]
  HANDLE hToken; // [rsp+48h] [rbp+10h] BYREF

  hToken = 0;
  if ( !(unsigned int)QueryUserToken(a1, &hToken) )
  {
    LastError = GetLastError();
    v2 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 7, 4);
    v5 = 4;
LABEL_3:
    v3 = EFS_TRACE_ERROR;
    goto LABEL_8;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v2 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 7, 11);
    v5 = 11;
    goto LABEL_3;
  }
  LastError = EfsSsopOnNotification(3u);
  if ( RevertToSelf() )
    goto LABEL_9;
  v2 = GetLastError();
  v3 = (__int64 *)&EFS_API_ERROR;
  v5 = 26;
LABEL_8:
  fnEfsLogTrace1(g_hPublisher, (_DWORD)v3, v2, 7, v5);
LABEL_9:
  if ( hToken )
    CloseHandle(hToken);
  return LastError;
}

```

## disassembly

```asm
0x180027834  push    rbx
0x180027836  sub     rsp, 30h
0x18002783a  lea     rdx, [rsp+38h+hToken]
0x18002783f  mov     [rsp+38h+hToken], 0
0x180027848  call    cs:__imp_QueryUserToken
0x18002784e  test    eax, eax
0x180027850  jnz     short loc_18002788F
0x180027852  call    cs:__imp_GetLastError
0x180027858  mov     rcx, cs:g_hPublisher
0x18002785f  lea     rdx, EFS_API_ERROR
0x180027866  mov     r8d, eax
0x180027869  mov     dword ptr [rsp+38h+var_18], 204h
0x180027871  mov     r9d, 7
0x180027877  mov     ebx, eax
0x180027879  call    fnEfsLogTrace1
0x18002787e  mov     dword ptr [rsp+38h+var_18], 204h
0x180027886  lea     rdx, EFS_TRACE_ERROR
0x18002788d  jmp     short loc_1800278FF
0x18002788f  mov     rcx, [rsp+38h+hToken]; hToken
0x180027894  call    cs:__imp_ImpersonateLoggedOnUser
0x18002789a  test    eax, eax
0x18002789c  jnz     short loc_1800278D4
0x18002789e  call    cs:__imp_GetLastError
0x1800278a4  mov     rcx, cs:g_hPublisher
0x1800278ab  lea     rdx, EFS_API_ERROR
0x1800278b2  mov     r8d, eax
0x1800278b5  mov     dword ptr [rsp+38h+var_18], 20Bh
0x1800278bd  mov     r9d, 7
0x1800278c3  mov     ebx, eax
0x1800278c5  call    fnEfsLogTrace1
0x1800278ca  mov     dword ptr [rsp+38h+var_18], 20Bh
0x1800278d2  jmp     short loc_180027886
0x1800278d4  mov     ecx, 3; unsigned int
0x1800278d9  call    ?EfsSsopOnNotification@@YAKK@Z; EfsSsopOnNotification(ulong)
0x1800278de  mov     ebx, eax
0x1800278e0  call    cs:__imp_RevertToSelf
0x1800278e6  test    eax, eax
0x1800278e8  jnz     short loc_180027914
0x1800278ea  call    cs:__imp_GetLastError
0x1800278f0  lea     rdx, EFS_API_ERROR
0x1800278f7  mov     dword ptr [rsp+38h+var_18], 21Ah
0x1800278ff  mov     rcx, cs:g_hPublisher
0x180027906  mov     r9d, 7
0x18002790c  mov     r8d, eax
0x18002790f  call    fnEfsLogTrace1
0x180027914  mov     rcx, [rsp+38h+hToken]; hObject
0x180027919  test    rcx, rcx
0x18002791c  jz      short loc_180027924
0x18002791e  call    cs:__imp_CloseHandle
0x180027924  mov     eax, ebx
0x180027926  add     rsp, 30h
0x18002792a  pop     rbx
0x18002792b  retn
```
