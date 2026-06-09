# ShCreateHHWindow

- ea: `0x180035a48`
- end: `0x180035b0a`
- name: `ShCreateHHWindow`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800356f0`
- `0x1800358a0`

## callees

- `0x180035a48`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180035af8`
- `KERNEL32!CloseHandle` at `0x180035af8`
- `KERNEL32!ReleaseSemaphore` at `0x180035aeb`
- `KERNEL32!ReleaseSemaphore` at `0x180035aeb`
- `KERNEL32!WaitForSingleObject` at `0x180035a8d`
- `KERNEL32!WaitForSingleObject` at `0x180035ad7`
- `KERNEL32!WaitForSingleObject` at `0x180035a8d`
- `KERNEL32!WaitForSingleObject` at `0x180035ad7`
- `KERNEL32!CreateSemaphoreA` at `0x180035a7a`
- `KERNEL32!CreateSemaphoreA` at `0x180035a7a`
- `KERNEL32!CreateThread` at `0x180035ab5`
- `KERNEL32!CreateThread` at `0x180035ab5`
- `KERNEL32!SetThreadPriority` at `0x180035ac7`
- `KERNEL32!SetThreadPriority` at `0x180035ac7`

## pseudocode

```c
HANDLE ShCreateHHWindow()
{
  HANDLE result; // rax
  HANDLE SemaphoreA; // rax

  result = hObject;
  if ( !hObject )
  {
    SemaphoreA = g_hsemMemory;
    if ( !g_hsemMemory )
    {
      SemaphoreA = CreateSemaphoreA(0, 1, 9999, "hh_semaphore");
      g_hsemMemory = SemaphoreA;
    }
    WaitForSingleObject(SemaphoreA, 0xFFFFFFFF);
    hObject = CreateThread(0, 0, HhWindowThread, 0, 0, &ThreadId);
    SetThreadPriority(hObject, 0);
    WaitForSingleObject(g_hsemMemory, 0xFFFFFFFF);
    ReleaseSemaphore(g_hsemMemory, 1, 0);
    CloseHandle(hObject);
    return hObject;
  }
  return result;
}

```

## disassembly

```asm
0x180035a48  sub     rsp, 38h
0x180035a4c  mov     rax, cs:hObject
0x180035a53  test    rax, rax
0x180035a56  jnz     loc_180035B05
0x180035a5c  mov     rax, cs:?g_hsemMemory@@3PEAXEA; void * g_hsemMemory
0x180035a63  test    rax, rax
0x180035a66  jnz     short loc_180035A87
0x180035a68  lea     r9, aHhSemaphore; "hh_semaphore"
0x180035a6f  xor     ecx, ecx; lpSemaphoreAttributes
0x180035a71  lea     edx, [rax+1]; lInitialCount
0x180035a74  mov     r8d, 270Fh; lMaximumCount
0x180035a7a  call    cs:__imp_CreateSemaphoreA
0x180035a80  mov     cs:?g_hsemMemory@@3PEAXEA, rax; void * g_hsemMemory
0x180035a87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035a8a  mov     rcx, rax; hHandle
0x180035a8d  call    cs:__imp_WaitForSingleObject
0x180035a93  lea     rax, ThreadId
0x180035a9a  xor     r9d, r9d; lpParameter
0x180035a9d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180035aa2  lea     r8, HhWindowThread; lpStartAddress
0x180035aa9  xor     edx, edx; dwStackSize
0x180035aab  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180035ab3  xor     ecx, ecx; lpThreadAttributes
0x180035ab5  call    cs:__imp_CreateThread
0x180035abb  mov     rcx, rax; hThread
0x180035abe  mov     cs:hObject, rax
0x180035ac5  xor     edx, edx; nPriority
0x180035ac7  call    cs:__imp_SetThreadPriority
0x180035acd  mov     rcx, cs:?g_hsemMemory@@3PEAXEA; hHandle
0x180035ad4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035ad7  call    cs:__imp_WaitForSingleObject
0x180035add  mov     rcx, cs:?g_hsemMemory@@3PEAXEA; hSemaphore
0x180035ae4  xor     r8d, r8d; lpPreviousCount
0x180035ae7  lea     edx, [r8+1]; lReleaseCount
0x180035aeb  call    cs:__imp_ReleaseSemaphore
0x180035af1  mov     rcx, cs:hObject; hObject
0x180035af8  call    cs:__imp_CloseHandle
0x180035afe  mov     rax, cs:hObject
0x180035b05  add     rsp, 38h
0x180035b09  retn
```
