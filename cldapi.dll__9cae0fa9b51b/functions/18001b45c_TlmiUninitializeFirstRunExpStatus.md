# TlmiUninitializeFirstRunExpStatus

- ea: `0x18001b45c`
- end: `0x18001b50f`
- name: `TlmiUninitializeFirstRunExpStatus`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011ccc`
- `0x180012b08`
- `0x180019520`

## callees

- `0x18001b45c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b467`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b467`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b503`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001b4a4`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001b4a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4da`

## pseudocode

```c
__int64 TlmiUninitializeFirstRunExpStatus()
{
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  RtlAcquireSRWLockExclusive(&qword_18002A970);
  if ( hTimer )
  {
    DueTime.QuadPart = 1;
    SetWaitableTimer(hTimer, &DueTime, 0, 0, 0, 0);
    CloseHandle(hTimer);
    hTimer = 0;
  }
  if ( qword_18002A9A0 )
  {
    CloseHandle(qword_18002A9A0);
    qword_18002A9A0 = 0;
  }
  byte_18002A968 = 0;
  return RtlReleaseSRWLockExclusive(&qword_18002A970);
}

```

## disassembly

```asm
0x18001b45c  sub     rsp, 38h
0x18001b460  lea     rcx, qword_18002A970
0x18001b467  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b46e  nop     dword ptr [rax+rax+00h]
0x18001b473  mov     rcx, cs:hTimer; hTimer
0x18001b47a  test    rcx, rcx
0x18001b47d  jz      short loc_18001B4CE
0x18001b47f  mov     [rsp+38h+fResume], 0; fResume
0x18001b487  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x18001b48c  xor     r9d, r9d; pfnCompletionRoutine
0x18001b48f  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18001b498  xor     r8d, r8d; lPeriod
0x18001b49b  mov     qword ptr [rsp+38h+DueTime], 1
0x18001b4a4  call    cs:__imp_SetWaitableTimer
0x18001b4ab  nop     dword ptr [rax+rax+00h]
0x18001b4b0  mov     rcx, cs:hTimer; hObject
0x18001b4b7  call    cs:__imp_CloseHandle
0x18001b4be  nop     dword ptr [rax+rax+00h]
0x18001b4c3  mov     cs:hTimer, 0
0x18001b4ce  mov     rcx, cs:qword_18002A9A0; hObject
0x18001b4d5  test    rcx, rcx
0x18001b4d8  jz      short loc_18001B4F1
0x18001b4da  call    cs:__imp_CloseHandle
0x18001b4e1  nop     dword ptr [rax+rax+00h]
0x18001b4e6  mov     cs:qword_18002A9A0, 0
0x18001b4f1  lea     rcx, qword_18002A970
0x18001b4f8  mov     cs:byte_18002A968, 0
0x18001b4ff  add     rsp, 38h
0x18001b503  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
