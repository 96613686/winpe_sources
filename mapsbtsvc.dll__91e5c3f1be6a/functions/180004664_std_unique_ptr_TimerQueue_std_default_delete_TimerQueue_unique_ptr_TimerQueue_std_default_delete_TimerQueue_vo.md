# std::unique_ptr<TimerQueue,std::default_delete<TimerQueue>>::~unique_ptr<TimerQueue,std::default_delete<TimerQueue>>(void)

- ea: `0x180004664`
- end: `0x18000467a`
- name: `??1?$unique_ptr@VTimerQueue@@U?$default_delete@VTimerQueue@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004940`
- `0x180005000`
- `0x180013cdc`
- `0x180014910`

## callees

- `0x180004664`
- `0x180004874`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<TimerQueue>::~unique_ptr<TimerQueue>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<TimerQueue>::operator()();
  return result;
}

```

## disassembly

```asm
0x180004664  sub     rsp, 28h
0x180004668  mov     rdx, [rcx]
0x18000466b  test    rdx, rdx
0x18000466e  jz      short loc_180004675
0x180004670  call    ??R?$default_delete@VTimerQueue@@@std@@QEBAXPEAVTimerQueue@@@Z; std::default_delete<TimerQueue>::operator()(TimerQueue *)
0x180004675  add     rsp, 28h
0x180004679  retn
```
