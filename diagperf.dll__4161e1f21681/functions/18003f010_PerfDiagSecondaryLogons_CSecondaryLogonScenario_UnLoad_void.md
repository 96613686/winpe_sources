# PerfDiagSecondaryLogons::CSecondaryLogonScenario::UnLoad(void *)

- ea: `0x18003f010`
- end: `0x18003f044`
- name: `?UnLoad@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@UEAAJPEAX@Z`
- size: `52`
- prototype: `__int64 __fastcall(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003f010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x18003f026`
- `KERNEL32!DeleteTimerQueueEx` at `0x18003f026`

## pseudocode

```c
__int64 __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::UnLoad(
        PerfDiagSecondaryLogons::CSecondaryLogonScenario *this,
        void *a2)
{
  void *v3; // rcx

  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    DeleteTimerQueueEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 4) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18003f010  push    rbx
0x18003f012  sub     rsp, 20h
0x18003f016  mov     rbx, rcx
0x18003f019  mov     rcx, [rcx+20h]; TimerQueue
0x18003f01d  test    rcx, rcx
0x18003f020  jz      short loc_18003F03C
0x18003f022  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003f026  call    cs:__imp_DeleteTimerQueueEx
0x18003f02c  mov     qword ptr [rbx+28h], 0
0x18003f034  mov     qword ptr [rbx+20h], 0
0x18003f03c  xor     eax, eax
0x18003f03e  add     rsp, 20h
0x18003f042  pop     rbx
0x18003f043  retn
```
