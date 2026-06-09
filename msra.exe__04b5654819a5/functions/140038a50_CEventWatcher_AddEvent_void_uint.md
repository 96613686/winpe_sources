# CEventWatcher::AddEvent(void *,uint)

- ea: `0x140038a50`
- end: `0x140038b3e`
- name: `?AddEvent@CEventWatcher@@QEAAXPEAXI@Z`
- size: `238`
- prototype: `void __fastcall(CEventWatcher *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002cb94`

## callees

- `0x140034ce4`
- `0x140038a50`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140038a69`
- `KERNEL32!SetEvent` at `0x140038a69`
- `KERNEL32!CreateThread` at `0x140038ae7`
- `KERNEL32!CreateThread` at `0x140038ae7`
- `KERNEL32!GetProcessHeap` at `0x140038a75`
- `KERNEL32!GetProcessHeap` at `0x140038a75`
- `KERNEL32!HeapAlloc` at `0x140038a8a`
- `KERNEL32!HeapAlloc` at `0x140038a8a`
- `KERNEL32!CloseHandle` at `0x140038b26`
- `KERNEL32!CloseHandle` at `0x140038b26`

## string_xrefs

- `0x140038afc`: `base\diagnosis\ra\racommon\src\eventwatcher.cpp`

## pseudocode

```c
void __fastcall CEventWatcher::AddEvent(HANDLE *this, void *a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  HANDLE Thread; // rax
  CEventLogger *v8; // rcx

  if ( *this != this )
    SetEvent(this[2]);
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0x20u);
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    v5[3] = 1;
    v5[2] = a2;
    v6 = this[1];
    *v5 = this;
    v5[1] = v6;
    *v6 = v5;
    this[1] = v5;
  }
  Thread = CreateThread(0, 0, CEventWatcher::EventWatchThread, this, 0, 0);
  if ( Thread )
    CloseHandle(Thread);
  else
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\eventwatcher.cpp",
      0x8Au,
      L"CEventWatcher::AddEvent",
      0);
}

```

## disassembly

```asm
0x140038a50  mov     [rsp+arg_0], rbx
0x140038a55  push    rdi
0x140038a56  sub     rsp, 30h
0x140038a5a  mov     rdi, rdx
0x140038a5d  mov     rbx, rcx
0x140038a60  cmp     [rcx], rcx
0x140038a63  jz      short loc_140038A75
0x140038a65  mov     rcx, [rcx+10h]; hEvent
0x140038a69  call    cs:__imp_SetEvent
0x140038a70  nop     dword ptr [rax+rax+00h]
0x140038a75  call    cs:__imp_GetProcessHeap
0x140038a7c  nop     dword ptr [rax+rax+00h]
0x140038a81  xor     edx, edx; dwFlags
0x140038a83  mov     rcx, rax; hHeap
0x140038a86  lea     r8d, [rdx+20h]; dwBytes
0x140038a8a  call    cs:__imp_HeapAlloc
0x140038a91  nop     dword ptr [rax+rax+00h]
0x140038a96  test    rax, rax
0x140038a99  jz      short loc_140038AC8
0x140038a9b  mov     qword ptr [rax], 0
0x140038aa2  mov     qword ptr [rax+8], 0
0x140038aaa  mov     qword ptr [rax+18h], 1
0x140038ab2  mov     [rax+10h], rdi
0x140038ab6  mov     rcx, [rbx+8]
0x140038aba  mov     [rax], rbx
0x140038abd  mov     [rax+8], rcx
0x140038ac1  mov     [rcx], rax
0x140038ac4  mov     [rbx+8], rax
0x140038ac8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140038ad1  lea     r8, ?EventWatchThread@CEventWatcher@@SAKPEAPEAX@Z; lpStartAddress
0x140038ad8  mov     r9, rbx; lpParameter
0x140038adb  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140038ae3  xor     edx, edx; dwStackSize
0x140038ae5  xor     ecx, ecx; lpThreadAttributes
0x140038ae7  call    cs:__imp_CreateThread
0x140038aee  nop     dword ptr [rax+rax+00h]
0x140038af3  test    rax, rax
0x140038af6  jnz     short loc_140038B23
0x140038af8  mov     dword ptr [rsp+38h+lpThreadId], eax; unsigned int
0x140038afc  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\racommon\\src\\eve"...
0x140038b03  lea     rax, aCeventwatcherA; "CEventWatcher::AddEvent"
0x140038b0a  mov     r9d, 8Ah; unsigned int
0x140038b10  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038b17  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x140038b1c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038b21  jmp     short loc_140038B32
0x140038b23  mov     rcx, rax; hObject
0x140038b26  call    cs:__imp_CloseHandle
0x140038b2d  nop     dword ptr [rax+rax+00h]
0x140038b32  mov     rbx, [rsp+38h+arg_0]
0x140038b37  add     rsp, 30h
0x140038b3b  pop     rdi
0x140038b3c  retn
```
