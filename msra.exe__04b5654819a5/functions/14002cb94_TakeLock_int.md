# TakeLock(int)

- ea: `0x14002cb94`
- end: `0x14002cca5`
- name: `?TakeLock@@YAHH@Z`
- size: `273`
- prototype: `int(int)`
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e8b8`
- `0x140012794`
- `0x140013f4c`
- `0x14001c458`
- `0x140027ce0`
- `0x140029418`
- `0x140032274`
- `0x140032f7c`

## callees

- `0x1400187cc`
- `0x14002cb94`
- `0x140038564`
- `0x140038650`
- `0x140038a50`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14002cc56`
- `KERNEL32!SetEvent` at `0x14002cc56`
- `KERNEL32!CreateEventW` at `0x14002cbb8`
- `KERNEL32!CreateEventW` at `0x14002cbb8`
- `KERNEL32!CloseHandle` at `0x14002cc6a`
- `KERNEL32!CloseHandle` at `0x14002cc6a`
- `USER32!AllowSetForegroundWindow` at `0x14002cc47`
- `USER32!AllowSetForegroundWindow` at `0x14002cc47`

## string_xrefs

- `0x14002cbec`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002cc1e`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall TakeLock(int a1)
{
  HANDLE EventW; // rax
  CReadWriteLock *v3; // rcx
  void *v4; // rdi
  int v5; // eax
  unsigned int v6; // r8d
  CEventLogger *v7; // rcx
  __int64 v8; // rbx
  int ReadLock; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v13; // [rsp+30h] [rbp+8h] BYREF

  v13 = 0;
  EventW = CreateEventW(0, 1, 0, L"Local\\RAActivateEvent");
  v3 = (CEventLogger *)((char *)_AtlModule + 672);
  v4 = EventW;
  if ( a1 )
  {
    v5 = CReadWriteLock::GetWriteLock(v3, &v13);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1995,
        (unsigned int)"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        (const char *)(unsigned int)v5,
        v11);
    v7 = _AtlModule;
    v8 = *((_QWORD *)_AtlModule + 35);
  }
  else
  {
    ReadLock = CReadWriteLock::GetReadLock(v3, &v13);
    if ( ReadLock < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x199A,
        (unsigned int)"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        (const char *)(unsigned int)ReadLock,
        v11);
    v7 = _AtlModule;
    v8 = *((_QWORD *)_AtlModule + 10);
  }
  if ( v13 == 1 )
  {
    CEventWatcher::AddEvent((CEventLogger *)((char *)v7 + 568), v4, v6);
    *((_QWORD *)_AtlModule + 74) = v8;
  }
  else
  {
    AllowSetForegroundWindow(0xFFFFFFFF);
    SetEvent(v4);
    if ( v4 )
      CloseHandle(v4);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002cb94  mov     [rsp+arg_8], rbx
0x14002cb99  push    rdi; int
0x14002cb9a  sub     rsp, 20h
0x14002cb9e  xor     r8d, r8d; bInitialState
0x14002cba1  mov     [rsp+28h+arg_0], 0
0x14002cba9  mov     ebx, ecx
0x14002cbab  lea     r9, Name; "Local\\RAActivateEvent"
0x14002cbb2  xor     ecx, ecx; lpEventAttributes
0x14002cbb4  lea     edx, [r8+1]; bManualReset
0x14002cbb8  call    cs:__imp_CreateEventW
0x14002cbbf  nop     dword ptr [rax+rax+00h]
0x14002cbc4  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002cbcb  lea     rdx, [rsp+28h+arg_0]; int *
0x14002cbd0  add     rcx, 2A0h; this
0x14002cbd7  mov     rdi, rax
0x14002cbda  test    ebx, ebx
0x14002cbdc  jz      short loc_14002CC10
0x14002cbde  call    ?GetWriteLock@CReadWriteLock@@QEAAJPEAH@Z; CReadWriteLock::GetWriteLock(int *)
0x14002cbe3  test    eax, eax
0x14002cbe5  jns     short loc_14002CC00
0x14002cbe7  mov     rcx, [rsp+28h]; this
0x14002cbec  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002cbf3  mov     r9d, eax; char *
0x14002cbf6  mov     edx, 1995h; void *
0x14002cbfb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002cc00  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002cc07  mov     rbx, [rcx+118h]
0x14002cc0e  jmp     short loc_14002CC3D
0x14002cc10  call    ?GetReadLock@CReadWriteLock@@QEAAJPEAH@Z; CReadWriteLock::GetReadLock(int *)
0x14002cc15  test    eax, eax
0x14002cc17  jns     short loc_14002CC32
0x14002cc19  mov     rcx, [rsp+28h]; this
0x14002cc1e  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002cc25  mov     r9d, eax; char *
0x14002cc28  mov     edx, 199Ah; void *
0x14002cc2d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002cc32  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002cc39  mov     rbx, [rcx+50h]
0x14002cc3d  cmp     [rsp+28h+arg_0], 1
0x14002cc42  jz      short loc_14002CC78
0x14002cc44  or      ecx, 0FFFFFFFFh; dwProcessId
0x14002cc47  call    cs:__imp_AllowSetForegroundWindow
0x14002cc4e  nop     dword ptr [rax+rax+00h]
0x14002cc53  mov     rcx, rdi; hEvent
0x14002cc56  call    cs:__imp_SetEvent
0x14002cc5d  nop     dword ptr [rax+rax+00h]
0x14002cc62  test    rdi, rdi
0x14002cc65  jz      short loc_14002CC95
0x14002cc67  mov     rcx, rdi; hObject
0x14002cc6a  call    cs:__imp_CloseHandle
0x14002cc71  nop     dword ptr [rax+rax+00h]
0x14002cc76  jmp     short loc_14002CC95
0x14002cc78  add     rcx, 238h; this
0x14002cc7f  mov     rdx, rdi; void *
0x14002cc82  call    ?AddEvent@CEventWatcher@@QEAAXPEAXI@Z; CEventWatcher::AddEvent(void *,uint)
0x14002cc87  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002cc8e  mov     [rcx+250h], rbx
0x14002cc95  mov     eax, [rsp+28h+arg_0]
0x14002cc99  mov     rbx, [rsp+28h+arg_8]
0x14002cc9e  add     rsp, 20h
0x14002cca2  pop     rdi
0x14002cca3  retn
```
