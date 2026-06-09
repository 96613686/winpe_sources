# CCallbackThread::StartThread(void)

- ea: `0x180141bd4`
- end: `0x180141c59`
- name: `?StartThread@CCallbackThread@@IEAAJXZ`
- size: `133`
- prototype: `__int64 __fastcall(CCallbackThread *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180141934`

## callees

- `0x180141bd4`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180141c44`
- `KERNEL32!SetThreadPriority` at `0x180141c44`
- `KERNEL32!CreateThread` at `0x180141c15`
- `KERNEL32!CreateThread` at `0x180141c15`
- `KERNEL32!ResetEvent` at `0x180141be1`
- `KERNEL32!ResetEvent` at `0x180141be1`
- `KERNEL32!GetLastError` at `0x180141c29`
- `KERNEL32!GetLastError` at `0x180141c29`

## pseudocode

```c
__int64 __fastcall CCallbackThread::StartThread(HANDLE *this)
{
  HANDLE v2; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ResetEvent(this[2]);
  ThreadId = 0;
  v2 = CreateThread(0, 0, CCallbackThread::InitialThreadProc, this, 0, &ThreadId);
  *this = v2;
  if ( !v2 )
    return GetLastError() | 0x80070000;
  SetThreadPriority(v2, 15);
  return 0;
}

```

## disassembly

```asm
0x180141bd4  push    rbx
0x180141bd6  sub     rsp, 30h
0x180141bda  mov     rbx, rcx
0x180141bdd  mov     rcx, [rcx+10h]; hEvent
0x180141be1  call    cs:__imp_ResetEvent
0x180141be8  nop     dword ptr [rax+rax+00h]
0x180141bed  lea     rax, [rsp+38h+ThreadId]
0x180141bf2  mov     [rsp+38h+ThreadId], 0
0x180141bfa  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180141bff  lea     r8, ?InitialThreadProc@CCallbackThread@@KAKPEAX@Z; lpStartAddress
0x180141c06  mov     r9, rbx; lpParameter
0x180141c09  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180141c11  xor     edx, edx; dwStackSize
0x180141c13  xor     ecx, ecx; lpThreadAttributes
0x180141c15  call    cs:__imp_CreateThread
0x180141c1c  nop     dword ptr [rax+rax+00h]
0x180141c21  mov     [rbx], rax
0x180141c24  test    rax, rax
0x180141c27  jnz     short loc_180141C3C
0x180141c29  call    cs:__imp_GetLastError
0x180141c30  nop     dword ptr [rax+rax+00h]
0x180141c35  or      eax, 80070000h
0x180141c3a  jmp     short loc_180141C52
0x180141c3c  mov     edx, 0Fh; nPriority
0x180141c41  mov     rcx, rax; hThread
0x180141c44  call    cs:__imp_SetThreadPriority
0x180141c4b  nop     dword ptr [rax+rax+00h]
0x180141c50  xor     eax, eax
0x180141c52  add     rsp, 30h
0x180141c56  pop     rbx
0x180141c57  retn
```
