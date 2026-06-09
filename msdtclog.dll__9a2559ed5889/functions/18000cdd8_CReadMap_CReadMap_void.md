# CReadMap::~CReadMap(void)

- ea: `0x18000cdd8`
- end: `0x18000ce02`
- name: `??1CReadMap@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CReadMap *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d7c`
- `0x18000ca18`
- `0x1800139e3`
- `0x18001423b`

## callees

- `0x18000d160`

## pseudocode

```c
void __fastcall CReadMap::~CReadMap(CReadMap *this)
{
  CReadMap::ReleaseAndSet(this, 0, 0);
  *((_QWORD *)this + 22) = 0;
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 11) = 0;
}

```

## disassembly

```asm
0x18000cdd8  push    rbx
0x18000cdda  sub     rsp, 20h
0x18000cdde  mov     rbx, rcx
0x18000cde1  xor     r8d, r8d; unsigned int
0x18000cde4  xor     edx, edx; unsigned int
0x18000cde6  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x18000cdeb  xor     eax, eax
0x18000cded  mov     [rbx+0B0h], rax
0x18000cdf4  mov     [rbx], eax
0x18000cdf6  mov     [rbx+8], eax
0x18000cdf9  mov     [rbx+2Ch], eax
0x18000cdfc  add     rsp, 20h
0x18000ce00  pop     rbx
0x18000ce01  retn
```
