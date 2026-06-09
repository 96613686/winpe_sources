# DfdTask::~DfdTask(void)

- ea: `0x180007084`
- end: `0x1800070d2`
- name: `??1DfdTask@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(DfdTask *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000357c`

## callees

- `0x180007084`
- `0x180009010`

## pseudocode

```c
void __fastcall DfdTask::~DfdTask(DfdTask *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180007084  push    rbx
0x180007086  sub     rsp, 20h
0x18000708a  mov     rbx, rcx
0x18000708d  mov     rcx, [rcx+10h]
0x180007091  test    rcx, rcx
0x180007094  jz      short loc_1800070A2
0x180007096  mov     rax, [rcx]
0x180007099  mov     rax, [rax+10h]
0x18000709d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a2  mov     rcx, [rbx+8]
0x1800070a6  test    rcx, rcx
0x1800070a9  jz      short loc_1800070B7
0x1800070ab  mov     rax, [rcx]
0x1800070ae  mov     rax, [rax+10h]
0x1800070b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b7  mov     rcx, [rbx]
0x1800070ba  test    rcx, rcx
0x1800070bd  jz      short loc_1800070CC
0x1800070bf  mov     rax, [rcx]
0x1800070c2  mov     rax, [rax+10h]
0x1800070c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070cb  nop
0x1800070cc  add     rsp, 20h
0x1800070d0  pop     rbx
0x1800070d1  retn
```
