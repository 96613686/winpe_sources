# ReleaseLock(int)

- ea: `0x14002b26c`
- end: `0x14002b3c2`
- name: `?ReleaseLock@@YAXH@Z`
- size: `342`
- prototype: `void __fastcall(int)`
- caller_count: `12`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e8b8`
- `0x140012794`
- `0x14001b7b0`
- `0x14001c9c8`
- `0x14001da70`
- `0x140020310`
- `0x140020fac`
- `0x140027ce0`
- `0x140027f24`
- `0x140029418`
- `0x140031a2c`
- `0x140032274`

## callees

- `0x1400187cc`
- `0x14002b26c`
- `0x140034ce4`
- `0x1400388d4`
- `0x14003894c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14002b297`
- `KERNEL32!SetEvent` at `0x14002b297`
- `KERNEL32!CreateThread` at `0x14002b322`
- `KERNEL32!CreateThread` at `0x14002b322`
- `KERNEL32!HeapFree` at `0x14002b2f2`
- `KERNEL32!HeapFree` at `0x14002b2f2`
- `KERNEL32!GetProcessHeap` at `0x14002b2de`
- `KERNEL32!GetProcessHeap` at `0x14002b2de`
- `KERNEL32!CloseHandle` at `0x14002b2ca`
- `KERNEL32!CloseHandle` at `0x14002b361`
- `KERNEL32!CloseHandle` at `0x14002b2ca`
- `KERNEL32!CloseHandle` at `0x14002b361`

## string_xrefs

- `0x14002b3a2`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002b337`: `base\diagnosis\ra\racommon\src\eventwatcher.cpp`
- `0x14002b33e`: `CEventWatcher::RemoveEvent`

## pseudocode

```c
void __fastcall ReleaseLock(int a1)
{
  _QWORD *v2; // rdi
  _DWORD *v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  void *v6; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE Thread; // rax
  CEventLogger *v9; // rcx
  CReadWriteLock *v10; // rcx
  int Lock; // eax
  __int64 v12; // rdx
  int dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (_QWORD *)((char *)_AtlModule + 568);
  v3 = (_DWORD *)*((_QWORD *)_AtlModule + 71);
  if ( v3 != (_DWORD *)((char *)_AtlModule + 568) )
  {
    SetEvent(*((HANDLE *)_AtlModule + 73));
    while ( 1 )
    {
      v4 = *(_QWORD **)v3;
      if ( v3[6] == 1 )
        break;
      v3 = *(_DWORD **)v3;
      if ( v4 == v2 )
        goto LABEL_9;
    }
    v5 = (_QWORD *)*((_QWORD *)v3 + 1);
    *v5 = v4;
    v4[1] = v5;
    v6 = (void *)*((_QWORD *)v3 + 2);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)v3 + 2) = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
LABEL_9:
  if ( (_QWORD *)*v2 != v2 )
  {
    Thread = CreateThread(0, 0, CEventWatcher::EventWatchThread, v2, 0, 0);
    if ( Thread )
      CloseHandle(Thread);
    else
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\eventwatcher.cpp",
        0x127u,
        L"CEventWatcher::RemoveEvent",
        0);
  }
  v10 = (CEventLogger *)((char *)_AtlModule + 672);
  if ( a1 )
  {
    Lock = CReadWriteLock::ReleaseWriteLock(v10);
    if ( Lock >= 0 )
      return;
    v12 = 6604;
  }
  else
  {
    Lock = CReadWriteLock::ReleaseReadLock(v10);
    if ( Lock >= 0 )
      return;
    v12 = 6608;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    (const char *)(unsigned int)Lock,
    dwCreationFlags);
}

```

## disassembly

```asm
0x14002b26c  mov     [rsp+arg_0], rbx
0x14002b271  mov     [rsp+arg_8], rsi
0x14002b276  push    rdi
0x14002b277  sub     rsp, 30h
0x14002b27b  mov     rdi, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b282  mov     esi, ecx
0x14002b284  add     rdi, 238h
0x14002b28b  mov     rbx, [rdi]
0x14002b28e  cmp     rbx, rdi
0x14002b291  jz      short loc_14002B2FE
0x14002b293  mov     rcx, [rdi+10h]; hEvent
0x14002b297  call    cs:__imp_SetEvent
0x14002b29e  nop     dword ptr [rax+rax+00h]
0x14002b2a3  cmp     dword ptr [rbx+18h], 1
0x14002b2a7  mov     rcx, [rbx]
0x14002b2aa  jz      short loc_14002B2B6
0x14002b2ac  mov     rbx, rcx
0x14002b2af  cmp     rcx, rdi
0x14002b2b2  jnz     short loc_14002B2A3
0x14002b2b4  jmp     short loc_14002B2FE
0x14002b2b6  mov     rax, [rbx+8]
0x14002b2ba  mov     [rax], rcx
0x14002b2bd  mov     [rcx+8], rax
0x14002b2c1  mov     rcx, [rbx+10h]; hObject
0x14002b2c5  test    rcx, rcx
0x14002b2c8  jz      short loc_14002B2DE
0x14002b2ca  call    cs:__imp_CloseHandle
0x14002b2d1  nop     dword ptr [rax+rax+00h]
0x14002b2d6  mov     qword ptr [rbx+10h], 0
0x14002b2de  call    cs:__imp_GetProcessHeap
0x14002b2e5  nop     dword ptr [rax+rax+00h]
0x14002b2ea  mov     r8, rbx; lpMem
0x14002b2ed  xor     edx, edx; dwFlags
0x14002b2ef  mov     rcx, rax; hHeap
0x14002b2f2  call    cs:__imp_HeapFree
0x14002b2f9  nop     dword ptr [rax+rax+00h]
0x14002b2fe  cmp     [rdi], rdi
0x14002b301  jz      short loc_14002B36D
0x14002b303  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x14002b30c  lea     r8, ?EventWatchThread@CEventWatcher@@SAKPEAPEAX@Z; lpStartAddress
0x14002b313  mov     r9, rdi; lpParameter
0x14002b316  mov     [rsp+38h+dwCreationFlags], 0; int
0x14002b31e  xor     edx, edx; dwStackSize
0x14002b320  xor     ecx, ecx; lpThreadAttributes
0x14002b322  call    cs:__imp_CreateThread
0x14002b329  nop     dword ptr [rax+rax+00h]
0x14002b32e  test    rax, rax
0x14002b331  jnz     short loc_14002B35E
0x14002b333  mov     dword ptr [rsp+38h+lpThreadId], eax; unsigned int
0x14002b337  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\racommon\\src\\eve"...
0x14002b33e  lea     rax, aCeventwatcherR; "CEventWatcher::RemoveEvent"
0x14002b345  mov     r9d, 127h; unsigned int
0x14002b34b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002b352  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x14002b357  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002b35c  jmp     short loc_14002B36D
0x14002b35e  mov     rcx, rax; hObject
0x14002b361  call    cs:__imp_CloseHandle
0x14002b368  nop     dword ptr [rax+rax+00h]
0x14002b36d  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b374  add     rcx, 2A0h; this
0x14002b37b  test    esi, esi
0x14002b37d  jz      short loc_14002B38F
0x14002b37f  call    ?ReleaseWriteLock@CReadWriteLock@@QEAAJXZ; CReadWriteLock::ReleaseWriteLock(void)
0x14002b384  test    eax, eax
0x14002b386  jns     short loc_14002B3B1
0x14002b388  mov     edx, 19CCh
0x14002b38d  jmp     short loc_14002B39D
0x14002b38f  call    ?ReleaseReadLock@CReadWriteLock@@QEAAJXZ; CReadWriteLock::ReleaseReadLock(void)
0x14002b394  test    eax, eax
0x14002b396  jns     short loc_14002B3B1
0x14002b398  mov     edx, 19D0h; void *
0x14002b39d  mov     rcx, [rsp+38h]; this
0x14002b3a2  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002b3a9  mov     r9d, eax; char *
0x14002b3ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002b3b1  mov     rbx, [rsp+38h+arg_0]
0x14002b3b6  mov     rsi, [rsp+38h+arg_8]
0x14002b3bb  add     rsp, 30h
0x14002b3bf  pop     rdi
0x14002b3c0  retn
```
