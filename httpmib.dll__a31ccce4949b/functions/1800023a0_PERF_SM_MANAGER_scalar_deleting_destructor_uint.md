# PERF_SM_MANAGER::`scalar deleting destructor'(uint)

- ea: `0x1800023a0`
- end: `0x1800023cf`
- name: `??_GPERF_SM_MANAGER@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(PERF_SM_MANAGER *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001928`
- `0x1800021c4`
- `0x1800023a0`

## pseudocode

```c
PERF_SM_MANAGER *__fastcall PERF_SM_MANAGER::`scalar deleting destructor'(PERF_SM_MANAGER *this, char a2)
{
  PERF_SM_MANAGER::~PERF_SM_MANAGER(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800023a0  mov     [rsp+arg_0], rbx
0x1800023a5  push    rdi
0x1800023a6  sub     rsp, 20h
0x1800023aa  mov     ebx, edx
0x1800023ac  mov     rdi, rcx
0x1800023af  call    ??1PERF_SM_MANAGER@@UEAA@XZ; PERF_SM_MANAGER::~PERF_SM_MANAGER(void)
0x1800023b4  test    bl, 1
0x1800023b7  jz      short loc_1800023C1
0x1800023b9  mov     rcx, rdi; Block
0x1800023bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800023c1  mov     rbx, [rsp+28h+arg_0]
0x1800023c6  mov     rax, rdi
0x1800023c9  add     rsp, 20h
0x1800023cd  pop     rdi
0x1800023ce  retn
```
