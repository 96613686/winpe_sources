# COutputQueue::NotifyThread(void)

- ea: `0x18001c480`
- end: `0x18001c4aa`
- name: `?NotifyThread@COutputQueue@@IEAAXXZ`
- size: `42`
- prototype: `void __fastcall(COutputQueue *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093c0`
- `0x18001c108`
- `0x18001c1dc`
- `0x18001c39c`
- `0x18001c4b0`
- `0x18001c6bc`

## callees

- `0x18001c480`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18001c497`
- `KERNEL32!ReleaseSemaphore` at `0x18001c497`

## pseudocode

```c
void __fastcall COutputQueue::NotifyThread(COutputQueue *this)
{
  LONG v1; // edx

  v1 = *((_DWORD *)this + 27);
  if ( v1 )
  {
    ReleaseSemaphore(*((HANDLE *)this + 9), v1, 0);
    *((_DWORD *)this + 27) = 0;
  }
}

```

## disassembly

```asm
0x18001c480  push    rbx
0x18001c482  sub     rsp, 20h
0x18001c486  mov     edx, [rcx+6Ch]; lReleaseCount
0x18001c489  mov     rbx, rcx
0x18001c48c  test    edx, edx
0x18001c48e  jz      short loc_18001C4A4
0x18001c490  mov     rcx, [rcx+48h]; hSemaphore
0x18001c494  xor     r8d, r8d; lpPreviousCount
0x18001c497  call    cs:__imp_ReleaseSemaphore
0x18001c49d  mov     dword ptr [rbx+6Ch], 0
0x18001c4a4  add     rsp, 20h
0x18001c4a8  pop     rbx
0x18001c4a9  retn
```
