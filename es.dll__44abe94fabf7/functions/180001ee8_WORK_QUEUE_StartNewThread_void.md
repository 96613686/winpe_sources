# WORK_QUEUE::StartNewThread(void)

- ea: `0x180001ee8`
- end: `0x180002016`
- name: `?StartNewThread@WORK_QUEUE@@QEAAHXZ`
- size: `302`
- prototype: `__int64 __fastcall(WORK_QUEUE *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001e44`
- `0x18002c74c`
- `0x180041160`

## callees

- `0x180001ee8`
- `0x18000201c`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180001f93`
- `msvcrt!_beginthreadex` at `0x180001f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f01`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001fec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002000`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001fec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001f34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001f34`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001f48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000200e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000200e`

## pseudocode

```c
__int64 __fastcall WORK_QUEUE::StartNewThread(WORK_QUEUE *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edi
  HANDLE CurrentThread; // rax
  BOOL v5; // esi
  int v6; // edx
  HINSTANCE v7; // rcx
  void *v8; // rax
  unsigned int ThrdAddr; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( *((_DWORD *)this + 6) )
  {
    LeaveCriticalSection(v1);
    return 1;
  }
  else
  {
    v3 = 1;
    _InterlockedAdd((volatile signed __int32 *)this + 10, 1u);
    LeaveCriticalSection(v1);
    ThrdAddr = 0;
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      v5 = SetThreadToken(0, 0);
    }
    else
    {
      v5 = 0;
      if ( GetLastError() != 1008 )
      {
        _InterlockedDecrement((volatile signed __int32 *)this + 10);
        return 0;
      }
    }
    if ( !*((_DWORD *)this + 8) )
    {
      *((_DWORD *)this + 8) = 1;
      IncrementLibraryUsageCount(v7, v6);
    }
    v8 = (void *)_beginthreadex(0, 0, WORK_QUEUE::ThreadLoop, this, 0, &ThrdAddr);
    if ( v8 )
    {
      _InterlockedAdd((volatile signed __int32 *)this + 11, 1u);
      CloseHandle(v8);
    }
    else
    {
      v3 = 0;
      _InterlockedDecrement((volatile signed __int32 *)this + 10);
    }
    if ( v5 )
      v3 &= -SetThreadToken(0, TokenHandle);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v3;
  }
}

```

## disassembly

```asm
0x180001ee8  mov     [rsp+arg_10], rbx
0x180001eed  mov     [rsp+arg_18], rsi
0x180001ef2  push    rdi
0x180001ef3  sub     rsp, 30h
0x180001ef7  lea     rsi, [rcx+68h]
0x180001efb  mov     rbx, rcx
0x180001efe  mov     rcx, rsi; lpCriticalSection
0x180001f01  call    cs:__imp_EnterCriticalSection
0x180001f07  cmp     dword ptr [rbx+18h], 0
0x180001f0b  mov     rcx, rsi; lpCriticalSection
0x180001f0e  jnz     loc_180001FDB
0x180001f14  mov     edi, 1
0x180001f19  lock add [rbx+28h], edi
0x180001f1d  call    cs:__imp_LeaveCriticalSection
0x180001f23  mov     [rsp+38h+arg_0], 0
0x180001f2b  mov     [rsp+38h+TokenHandle], 0
0x180001f34  call    cs:__imp_GetCurrentThread
0x180001f3a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180001f3f  mov     r8d, edi; OpenAsSelf
0x180001f42  mov     rcx, rax; ThreadHandle
0x180001f45  lea     edx, [rdi+3]; DesiredAccess
0x180001f48  call    cs:__imp_OpenThreadToken
0x180001f4e  test    eax, eax
0x180001f50  jnz     loc_180001FE8
0x180001f56  xor     esi, esi
0x180001f58  call    cs:__imp_GetLastError
0x180001f5e  cmp     eax, 3F0h
0x180001f63  jnz     short loc_180001FD3
0x180001f65  cmp     dword ptr [rbx+20h], 0
0x180001f69  jnz     short loc_180001F73
0x180001f6b  mov     [rbx+20h], edi
0x180001f6e  call    ?IncrementLibraryUsageCount@@YAXPEAUHINSTANCE__@@H@Z; IncrementLibraryUsageCount(HINSTANCE__ *,int)
0x180001f73  lea     rax, [rsp+38h+arg_0]
0x180001f78  mov     r9, rbx; ArgList
0x180001f7b  mov     [rsp+38h+ThrdAddr], rax; ThrdAddr
0x180001f80  lea     r8, ?ThreadLoop@WORK_QUEUE@@CAIPEAX@Z; StartAddress
0x180001f87  xor     edx, edx; StackSize
0x180001f89  mov     [rsp+38h+InitFlag], 0; InitFlag
0x180001f91  xor     ecx, ecx; Security
0x180001f93  call    cs:__imp__beginthreadex
0x180001f99  test    rax, rax
0x180001f9c  jz      short loc_180001FCB
0x180001f9e  lock add [rbx+2Ch], edi
0x180001fa2  mov     rcx, rax; hObject
0x180001fa5  call    cs:__imp_CloseHandle
0x180001fab  test    esi, esi
0x180001fad  jnz     short loc_180001FF9
0x180001faf  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180001fb4  test    rcx, rcx
0x180001fb7  jnz     short loc_18000200E
0x180001fb9  mov     eax, edi
0x180001fbb  mov     rbx, [rsp+38h+arg_10]
0x180001fc0  mov     rsi, [rsp+38h+arg_18]
0x180001fc5  add     rsp, 30h
0x180001fc9  pop     rdi
0x180001fca  retn
0x180001fcb  xor     edi, edi
0x180001fcd  lock dec dword ptr [rbx+28h]
0x180001fd1  jmp     short loc_180001FAB
0x180001fd3  lock dec dword ptr [rbx+28h]
0x180001fd7  xor     eax, eax
0x180001fd9  jmp     short loc_180001FBB
0x180001fdb  call    cs:__imp_LeaveCriticalSection
0x180001fe1  mov     eax, 1
0x180001fe6  jmp     short loc_180001FBB
0x180001fe8  xor     edx, edx; Token
0x180001fea  xor     ecx, ecx; Thread
0x180001fec  call    cs:__imp_SetThreadToken
0x180001ff2  mov     esi, eax
0x180001ff4  jmp     loc_180001F65
0x180001ff9  mov     rdx, [rsp+38h+TokenHandle]; Token
0x180001ffe  xor     ecx, ecx; Thread
0x180002000  call    cs:__imp_SetThreadToken
0x180002006  neg     eax
0x180002008  sbb     ecx, ecx
0x18000200a  and     edi, ecx
0x18000200c  jmp     short loc_180001FAF
0x18000200e  call    cs:__imp_CloseHandle
0x180002014  jmp     short loc_180001FB9
```
