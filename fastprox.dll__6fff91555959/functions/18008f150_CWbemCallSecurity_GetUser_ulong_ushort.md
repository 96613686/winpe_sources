# CWbemCallSecurity::GetUser(ulong *,ushort *)

- ea: `0x18008f150`
- end: `0x18008f253`
- name: `?GetUser@CWbemCallSecurity@@UEAAJPEAKPEAG@Z`
- size: `259`
- prototype: `int(CWbemCallSecurity *__hidden this, unsigned int *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180037120`
- `0x18008eeac`
- `0x18008f150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008f1ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008f1ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f185`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f185`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008f1bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008f1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f16e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f16e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f1ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f18d`
- `wbemcomn!GetMemLogObject` at `0x18008f1f9`
- `wbemcomn!GetMemLogObject` at `0x18008f1f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f204`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f204`

## pseudocode

```c
__int64 __fastcall CWbemCallSecurity::GetUser(CWbemCallSecurity *this, unsigned int *a2, unsigned __int16 *a3)
{
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  DWORD LastError; // eax
  unsigned int User; // ebx
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
    User = -2147217405;
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, User);
    goto LABEL_9;
  }
  CurrentProcess = GetCurrentProcess();
  v10 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  User = !v10 ? 0x80041003 : 0;
  if ( v10 )
  {
LABEL_6:
    User = GetUser(TokenHandle, a2, a3);
    CloseHandle(TokenHandle);
  }
  if ( (User & 0x80000000) != 0 )
    goto LABEL_8;
LABEL_9:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids, User);
  }
  return User;
}

```

## disassembly

```asm
0x18008f150  mov     [rsp+arg_0], rbx
0x18008f155  mov     [rsp+arg_8], rsi
0x18008f15a  push    rdi
0x18008f15b  sub     rsp, 20h
0x18008f15f  mov     rdi, r8
0x18008f162  mov     [rsp+28h+TokenHandle], 0
0x18008f16b  mov     rsi, rdx
0x18008f16e  call    cs:__imp_GetCurrentThread
0x18008f174  mov     edx, 8; DesiredAccess
0x18008f179  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18008f17e  mov     rcx, rax; ThreadHandle
0x18008f181  lea     r8d, [rdx-7]; OpenAsSelf
0x18008f185  call    cs:__imp_OpenThreadToken
0x18008f18b  mov     ebx, eax
0x18008f18d  call    cs:__imp_GetLastError
0x18008f193  test    ebx, ebx
0x18008f195  jnz     short loc_18008F1D8
0x18008f197  cmp     eax, 51Dh
0x18008f19c  jz      short loc_18008F1AC
0x18008f19e  cmp     eax, 3F0h
0x18008f1a3  jz      short loc_18008F1AC
0x18008f1a5  mov     ebx, 80041003h
0x18008f1aa  jmp     short loc_18008F1F9
0x18008f1ac  call    cs:__imp_GetCurrentProcess
0x18008f1b2  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18008f1b7  mov     edx, 8; DesiredAccess
0x18008f1bc  mov     rcx, rax; ProcessHandle
0x18008f1bf  call    cs:__imp_OpenProcessToken
0x18008f1c5  mov     ecx, eax
0x18008f1c7  mov     ebx, 80041003h
0x18008f1cc  neg     ecx
0x18008f1ce  sbb     edx, edx
0x18008f1d0  not     edx
0x18008f1d2  and     ebx, edx
0x18008f1d4  test    eax, eax
0x18008f1d6  jz      short loc_18008F1F5
0x18008f1d8  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18008f1dd  mov     r8, rdi; unsigned __int16 *
0x18008f1e0  mov     rdx, rsi; unsigned int *
0x18008f1e3  call    ?GetUser@@YAJPEAXPEAKPEAG@Z; GetUser(void *,ulong *,ushort *)
0x18008f1e8  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18008f1ed  mov     ebx, eax
0x18008f1ef  call    cs:__imp_CloseHandle
0x18008f1f5  test    ebx, ebx
0x18008f1f7  jns     short loc_18008F20A
0x18008f1f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f1ff  mov     rcx, rax
0x18008f202  mov     edx, ebx
0x18008f204  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f211  lea     rax, WPP_GLOBAL_Control
0x18008f218  cmp     rcx, rax
0x18008f21b  jz      short loc_18008F241
0x18008f21d  test    byte ptr [rcx+1Ch], 1
0x18008f221  jz      short loc_18008F241
0x18008f223  cmp     byte ptr [rcx+19h], 2
0x18008f227  jb      short loc_18008F241
0x18008f229  mov     rcx, [rcx+10h]
0x18008f22d  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008f234  mov     edx, 1Ah
0x18008f239  mov     r9d, ebx
0x18008f23c  call    WPP_SF_d
0x18008f241  mov     rsi, [rsp+28h+arg_8]
0x18008f246  mov     eax, ebx
0x18008f248  mov     rbx, [rsp+28h+arg_0]
0x18008f24d  add     rsp, 20h
0x18008f251  pop     rdi
0x18008f252  retn
```
