# DestroyAggregateSession

- ea: `0x18001bc44`
- end: `0x18001bc7d`
- name: `DestroyAggregateSession`
- size: `57`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bb68`
- `0x18001c76c`
- `0x18001c920`

## callees

- `0x18001b8b0`
- `0x18001bc44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc6a`

## pseudocode

```c
void __fastcall DestroyAggregateSession(LPVOID lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    CancelTimerCallbacksAndDeleteTimer((__int64)lpMem);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18001bc44  test    rcx, rcx
0x18001bc47  jz      short locret_18001BC7B
0x18001bc49  push    rbx
0x18001bc4a  sub     rsp, 20h
0x18001bc4e  mov     rbx, rcx
0x18001bc51  call    CancelTimerCallbacksAndDeleteTimer
0x18001bc56  call    cs:__imp_GetProcessHeap
0x18001bc5d  nop     dword ptr [rax+rax+00h]
0x18001bc62  mov     r8, rbx; lpMem
0x18001bc65  xor     edx, edx; dwFlags
0x18001bc67  mov     rcx, rax; hHeap
0x18001bc6a  call    cs:__imp_HeapFree
0x18001bc71  nop     dword ptr [rax+rax+00h]
0x18001bc76  add     rsp, 20h
0x18001bc7a  pop     rbx
0x18001bc7b  retn
```
