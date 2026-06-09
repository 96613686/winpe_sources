# CWbemCallSecurity::GetAuthenticationLuid(void *)

- ea: `0x18008e7b0`
- end: `0x18008e8a3`
- name: `?GetAuthenticationLuid@CWbemCallSecurity@@UEAAJPEAX@Z`
- size: `243`
- prototype: `int(CWbemCallSecurity *__hidden this, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180037120`
- `0x18008e6c0`
- `0x18008e7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008e804`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008e804`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e7dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e7dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008e817`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008e817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e7c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e7c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7e5`
- `wbemcomn!GetMemLogObject` at `0x18008e84e`
- `wbemcomn!GetMemLogObject` at `0x18008e84e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008e859`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008e859`

## pseudocode

```c
__int64 __fastcall CWbemCallSecurity::GetAuthenticationLuid(CWbemCallSecurity *this, void *a2)
{
  HANDLE CurrentThread; // rax
  BOOL v4; // ebx
  DWORD LastError; // eax
  unsigned int AuthenticationLuid; // ebx
  HANDLE CurrentProcess; // rax
  BOOL v8; // eax
  CMemoryLog *MemLogObject; // rax
  HANDLE TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v4 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  LastError = GetLastError();
  if ( v4 )
    goto LABEL_6;
  if ( LastError != 1309 && LastError != 1008 )
  {
    AuthenticationLuid = -2147217405;
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, AuthenticationLuid);
    goto LABEL_9;
  }
  CurrentProcess = GetCurrentProcess();
  v8 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  AuthenticationLuid = !v8 ? 0x80041003 : 0;
  if ( v8 )
  {
LABEL_6:
    AuthenticationLuid = GetAuthenticationLuid(TokenHandle, a2);
    CloseHandle(TokenHandle);
  }
  if ( (AuthenticationLuid & 0x80000000) != 0 )
    goto LABEL_8;
LABEL_9:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_a3414c62bfc43c14b650084b64f85981_Traceguids,
      AuthenticationLuid);
  }
  return AuthenticationLuid;
}

```

## disassembly

```asm
0x18008e7b0  mov     [rsp+arg_0], rbx
0x18008e7b5  push    rdi
0x18008e7b6  sub     rsp, 20h
0x18008e7ba  mov     rdi, rdx
0x18008e7bd  mov     [rsp+28h+TokenHandle], 0
0x18008e7c6  call    cs:__imp_GetCurrentThread
0x18008e7cc  mov     edx, 8; DesiredAccess
0x18008e7d1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18008e7d6  mov     rcx, rax; ThreadHandle
0x18008e7d9  lea     r8d, [rdx-7]; OpenAsSelf
0x18008e7dd  call    cs:__imp_OpenThreadToken
0x18008e7e3  mov     ebx, eax
0x18008e7e5  call    cs:__imp_GetLastError
0x18008e7eb  test    ebx, ebx
0x18008e7ed  jnz     short loc_18008E830
0x18008e7ef  cmp     eax, 51Dh
0x18008e7f4  jz      short loc_18008E804
0x18008e7f6  cmp     eax, 3F0h
0x18008e7fb  jz      short loc_18008E804
0x18008e7fd  mov     ebx, 80041003h
0x18008e802  jmp     short loc_18008E84E
0x18008e804  call    cs:__imp_GetCurrentProcess
0x18008e80a  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18008e80f  mov     edx, 8; DesiredAccess
0x18008e814  mov     rcx, rax; ProcessHandle
0x18008e817  call    cs:__imp_OpenProcessToken
0x18008e81d  mov     ecx, eax
0x18008e81f  mov     ebx, 80041003h
0x18008e824  neg     ecx
0x18008e826  sbb     edx, edx
0x18008e828  not     edx
0x18008e82a  and     ebx, edx
0x18008e82c  test    eax, eax
0x18008e82e  jz      short loc_18008E84A
0x18008e830  mov     rcx, [rsp+28h+TokenHandle]; void *
0x18008e835  mov     rdx, rdi; void *
0x18008e838  call    ?GetAuthenticationLuid@@YAJPEAX0@Z; GetAuthenticationLuid(void *,void *)
0x18008e83d  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18008e842  mov     ebx, eax
0x18008e844  call    cs:__imp_CloseHandle
0x18008e84a  test    ebx, ebx
0x18008e84c  jns     short loc_18008E85F
0x18008e84e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008e854  mov     rcx, rax
0x18008e857  mov     edx, ebx
0x18008e859  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008e85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e866  lea     rax, WPP_GLOBAL_Control
0x18008e86d  cmp     rcx, rax
0x18008e870  jz      short loc_18008E896
0x18008e872  test    byte ptr [rcx+1Ch], 1
0x18008e876  jz      short loc_18008E896
0x18008e878  cmp     byte ptr [rcx+19h], 2
0x18008e87c  jb      short loc_18008E896
0x18008e87e  mov     rcx, [rcx+10h]
0x18008e882  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008e889  mov     edx, 1Ch
0x18008e88e  mov     r9d, ebx
0x18008e891  call    WPP_SF_d
0x18008e896  mov     eax, ebx
0x18008e898  mov     rbx, [rsp+28h+arg_0]
0x18008e89d  add     rsp, 20h
0x18008e8a1  pop     rdi
0x18008e8a2  retn
```
