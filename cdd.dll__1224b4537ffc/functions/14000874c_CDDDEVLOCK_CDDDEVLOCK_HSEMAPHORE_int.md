# CDDDEVLOCK::CDDDEVLOCK(HSEMAPHORE__ *,int)

- ea: `0x14000874c`
- end: `0x14000876e`
- name: `??0CDDDEVLOCK@@QEAA@PEAUHSEMAPHORE__@@H@Z`
- size: `34`
- prototype: `CDDDEVLOCK *__fastcall(CDDDEVLOCK *__hidden this, HSEMAPHORE, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x14000919c`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x14002b5f0`
- `0x14002c640`
- `0x14002c6f0`

## callees

- `0x140008774`

## pseudocode

```c
CDDDEVLOCK *__fastcall CDDDEVLOCK::CDDDEVLOCK(CDDDEVLOCK *this, HSEMAPHORE a2)
{
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = 0;
  CDDDEVLOCK::vLock(this);
  return this;
}

```

## disassembly

```asm
0x14000874c  push    rbx
0x14000874e  sub     rsp, 20h
0x140008752  mov     rbx, rcx
0x140008755  mov     [rcx], rdx
0x140008758  mov     dword ptr [rcx+8], 0
0x14000875f  call    ?vLock@CDDDEVLOCK@@QEAAXXZ; CDDDEVLOCK::vLock(void)
0x140008764  mov     rax, rbx
0x140008767  add     rsp, 20h
0x14000876b  pop     rbx
0x14000876c  retn
```
