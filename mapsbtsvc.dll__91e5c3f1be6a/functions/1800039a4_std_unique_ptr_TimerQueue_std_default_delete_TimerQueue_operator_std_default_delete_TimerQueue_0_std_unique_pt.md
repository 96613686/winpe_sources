# std::unique_ptr<TimerQueue,std::default_delete<TimerQueue>>::operator=<std::default_delete<TimerQueue>,0>(std::unique_ptr<TimerQueue,std::default_delete<TimerQueue>> &&)

- ea: `0x1800039a4`
- end: `0x1800039d0`
- name: `??$?4U?$default_delete@VTimerQueue@@@std@@$0A@@?$unique_ptr@VTimerQueue@@U?$default_delete@VTimerQueue@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004940`
- `0x180005000`

## callees

- `0x1800039a4`
- `0x180004874`

## pseudocode

```c
__int64 *__fastcall std::unique_ptr<TimerQueue>::operator=<std::default_delete<TimerQueue>,0>(__int64 *a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rdx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    std::default_delete<TimerQueue>::operator()();
  return a1;
}

```

## disassembly

```asm
0x1800039a4  push    rbx
0x1800039a6  sub     rsp, 20h
0x1800039aa  mov     rax, [rdx]
0x1800039ad  mov     rbx, rcx
0x1800039b0  mov     qword ptr [rdx], 0
0x1800039b7  mov     rdx, [rcx]
0x1800039ba  mov     [rcx], rax
0x1800039bd  test    rdx, rdx
0x1800039c0  jz      short loc_1800039C7
0x1800039c2  call    ??R?$default_delete@VTimerQueue@@@std@@QEBAXPEAVTimerQueue@@@Z; std::default_delete<TimerQueue>::operator()(TimerQueue *)
0x1800039c7  mov     rax, rbx
0x1800039ca  add     rsp, 20h
0x1800039ce  pop     rbx
0x1800039cf  retn
```
