# BootScenario::UnLoad(void *)

- ea: `0x18003f050`
- end: `0x18003f08c`
- name: `?UnLoad@BootScenario@@UEAAJPEAX@Z`
- size: `60`
- prototype: `__int64 __fastcall(BootScenario *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003f050`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x18003f066`
- `KERNEL32!DeleteTimerQueueEx` at `0x18003f066`

## pseudocode

```c
__int64 __fastcall BootScenario::UnLoad(BootScenario *this, void *a2)
{
  void *v3; // rcx

  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    DeleteTimerQueueEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18003f050  push    rbx
0x18003f052  sub     rsp, 20h
0x18003f056  mov     rbx, rcx
0x18003f059  mov     rcx, [rcx+20h]; TimerQueue
0x18003f05d  test    rcx, rcx
0x18003f060  jz      short loc_18003F084
0x18003f062  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003f066  call    cs:__imp_DeleteTimerQueueEx
0x18003f06c  mov     qword ptr [rbx+20h], 0
0x18003f074  mov     qword ptr [rbx+28h], 0
0x18003f07c  mov     qword ptr [rbx+30h], 0
0x18003f084  xor     eax, eax
0x18003f086  add     rsp, 20h
0x18003f08a  pop     rbx
0x18003f08b  retn
```
