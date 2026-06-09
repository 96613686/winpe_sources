# CWbemCallSecurity::GetUserSid(ulong *,void *)

- ea: `0x18008f440`
- end: `0x18008f543`
- name: `?GetUserSid@CWbemCallSecurity@@UEAAJPEAKPEAX@Z`
- size: `259`
- prototype: `int(CWbemCallSecurity *__hidden this, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180037120`
- `0x18008f2d8`
- `0x18008f440`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008f49c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008f49c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f475`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f475`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008f4af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008f4af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f45e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f45e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f47d`
- `wbemcomn!GetMemLogObject` at `0x18008f4e9`
- `wbemcomn!GetMemLogObject` at `0x18008f4e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f4f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f4f4`

## pseudocode

```c
__int64 __fastcall CWbemCallSecurity::GetUserSid(CWbemCallSecurity *this, unsigned int *a2, void *a3)
{
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  DWORD LastError; // eax
  unsigned int UserSid; // ebx
  HANDLE CurrentProcess; // rax
  BOOL v10; // eax
  CMemoryLog *MemLogObject; // rax
  HANDLE TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  LastError = GetLastError();
  if ( v6 )
    goto LABEL_6;
  if ( LastError != 1309 && LastError != 1008 )
  {
    UserSid = -2147217405;
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, UserSid);
    goto LABEL_9;
  }
  CurrentProcess = GetCurrentProcess();
  v10 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  UserSid = !v10 ? 0x80041003 : 0;
  if ( v10 )
  {
LABEL_6:
    UserSid = GetUserSid(TokenHandle, a2, a3);
    CloseHandle(TokenHandle);
  }
  if ( (UserSid & 0x80000000) != 0 )
    goto LABEL_8;
LABEL_9:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids, UserSid);
  }
  return UserSid;
}

```

## disassembly

```asm
0x18008f440  mov     [rsp+arg_0], rbx
0x18008f445  mov     [rsp+arg_8], rsi
0x18008f44a  push    rdi
0x18008f44b  sub     rsp, 20h
0x18008f44f  mov     rdi, r8
0x18008f452  mov     [rsp+28h+TokenHandle], 0
0x18008f45b  mov     rsi, rdx
0x18008f45e  call    cs:__imp_GetCurrentThread
0x18008f464  mov     edx, 8; DesiredAccess
0x18008f469  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18008f46e  mov     rcx, rax; ThreadHandle
0x18008f471  lea     r8d, [rdx-7]; OpenAsSelf
0x18008f475  call    cs:__imp_OpenThreadToken
0x18008f47b  mov     ebx, eax
0x18008f47d  call    cs:__imp_GetLastError
0x18008f483  test    ebx, ebx
0x18008f485  jnz     short loc_18008F4C8
0x18008f487  cmp     eax, 51Dh
0x18008f48c  jz      short loc_18008F49C
0x18008f48e  cmp     eax, 3F0h
0x18008f493  jz      short loc_18008F49C
0x18008f495  mov     ebx, 80041003h
0x18008f49a  jmp     short loc_18008F4E9
0x18008f49c  call    cs:__imp_GetCurrentProcess
0x18008f4a2  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18008f4a7  mov     edx, 8; DesiredAccess
0x18008f4ac  mov     rcx, rax; ProcessHandle
0x18008f4af  call    cs:__imp_OpenProcessToken
0x18008f4b5  mov     ecx, eax
0x18008f4b7  mov     ebx, 80041003h
0x18008f4bc  neg     ecx
0x18008f4be  sbb     edx, edx
0x18008f4c0  not     edx
0x18008f4c2  and     ebx, edx
0x18008f4c4  test    eax, eax
0x18008f4c6  jz      short loc_18008F4E5
0x18008f4c8  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18008f4cd  mov     r8, rdi; void *
0x18008f4d0  mov     rdx, rsi; unsigned int *
0x18008f4d3  call    ?GetUserSid@@YAJPEAXPEAK0@Z; GetUserSid(void *,ulong *,void *)
0x18008f4d8  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18008f4dd  mov     ebx, eax
0x18008f4df  call    cs:__imp_CloseHandle
0x18008f4e5  test    ebx, ebx
0x18008f4e7  jns     short loc_18008F4FA
0x18008f4e9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f4ef  mov     rcx, rax
0x18008f4f2  mov     edx, ebx
0x18008f4f4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f501  lea     rax, WPP_GLOBAL_Control
0x18008f508  cmp     rcx, rax
0x18008f50b  jz      short loc_18008F531
0x18008f50d  test    byte ptr [rcx+1Ch], 1
0x18008f511  jz      short loc_18008F531
0x18008f513  cmp     byte ptr [rcx+19h], 2
0x18008f517  jb      short loc_18008F531
0x18008f519  mov     rcx, [rcx+10h]
0x18008f51d  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008f524  mov     edx, 1Bh
0x18008f529  mov     r9d, ebx
0x18008f52c  call    WPP_SF_d
0x18008f531  mov     rsi, [rsp+28h+arg_8]
0x18008f536  mov     eax, ebx
0x18008f538  mov     rbx, [rsp+28h+arg_0]
0x18008f53d  add     rsp, 20h
0x18008f541  pop     rdi
0x18008f542  retn
```
