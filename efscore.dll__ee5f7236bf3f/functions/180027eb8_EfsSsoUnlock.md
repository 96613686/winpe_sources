# EfsSsoUnlock

- ea: `0x180027eb8`
- end: `0x180027f66`
- name: `EfsSsoUnlock`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800276bc`

## callees

- `0x1800274b8`
- `0x180027eb8`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f58`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027f1a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027f1a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027ef4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027ef4`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180027ecc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180027ecc`

## pseudocode

```c
__int64 __fastcall EfsSsoUnlock(__int64 a1)
{
  DWORD LastError; // eax
  unsigned int v2; // ebx
  __int64 *v3; // rdx
  char v5; // [rsp+20h] [rbp-18h]
  HANDLE hToken; // [rsp+48h] [rbp+10h] BYREF

  hToken = 0;
  if ( !(unsigned int)QueryUserToken(a1, &hToken) )
  {
    LastError = GetLastError();
    v5 = -61;
LABEL_3:
    v2 = LastError;
    v3 = EFS_TRACE_ERROR;
    goto LABEL_8;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v5 = -56;
    goto LABEL_3;
  }
  v2 = EfsSsopOnNotification(2u);
  if ( RevertToSelf() )
    goto LABEL_9;
  LastError = GetLastError();
  v3 = (__int64 *)&EFS_API_ERROR;
  v5 = -41;
LABEL_8:
  fnEfsLogTrace1(g_hPublisher, (_DWORD)v3, LastError, 7, v5);
LABEL_9:
  if ( hToken )
    CloseHandle(hToken);
  return v2;
}

```

## disassembly

```asm
0x180027eb8  push    rbx
0x180027eba  sub     rsp, 30h
0x180027ebe  lea     rdx, [rsp+38h+hToken]
0x180027ec3  mov     [rsp+38h+hToken], 0
0x180027ecc  call    cs:__imp_QueryUserToken
0x180027ed2  test    eax, eax
0x180027ed4  jnz     short loc_180027EEF
0x180027ed6  call    cs:__imp_GetLastError
0x180027edc  mov     dword ptr [rsp+38h+var_18], 1C3h
0x180027ee4  mov     ebx, eax
0x180027ee6  lea     rdx, EFS_TRACE_ERROR
0x180027eed  jmp     short loc_180027F39
0x180027eef  mov     rcx, [rsp+38h+hToken]; hToken
0x180027ef4  call    cs:__imp_ImpersonateLoggedOnUser
0x180027efa  test    eax, eax
0x180027efc  jnz     short loc_180027F0E
0x180027efe  call    cs:__imp_GetLastError
0x180027f04  mov     dword ptr [rsp+38h+var_18], 1C8h
0x180027f0c  jmp     short loc_180027EE4
0x180027f0e  mov     ecx, 2; unsigned int
0x180027f13  call    ?EfsSsopOnNotification@@YAKK@Z; EfsSsopOnNotification(ulong)
0x180027f18  mov     ebx, eax
0x180027f1a  call    cs:__imp_RevertToSelf
0x180027f20  test    eax, eax
0x180027f22  jnz     short loc_180027F4E
0x180027f24  call    cs:__imp_GetLastError
0x180027f2a  lea     rdx, EFS_API_ERROR
0x180027f31  mov     dword ptr [rsp+38h+var_18], 1D7h
0x180027f39  mov     rcx, cs:g_hPublisher
0x180027f40  mov     r9d, 7
0x180027f46  mov     r8d, eax
0x180027f49  call    fnEfsLogTrace1
0x180027f4e  mov     rcx, [rsp+38h+hToken]; hObject
0x180027f53  test    rcx, rcx
0x180027f56  jz      short loc_180027F5E
0x180027f58  call    cs:__imp_CloseHandle
0x180027f5e  mov     eax, ebx
0x180027f60  add     rsp, 30h
0x180027f64  pop     rbx
0x180027f65  retn
```
