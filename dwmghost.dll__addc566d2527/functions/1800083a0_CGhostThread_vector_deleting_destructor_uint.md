# CGhostThread::`vector deleting destructor'(uint)

- ea: `0x1800083a0`
- end: `0x1800083e2`
- name: `??_ECGhostThread@@UEAAPEAXI@Z`
- size: `66`
- prototype: `void *__fastcall(CGhostThread *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800059c0`
- `0x180008314`
- `0x1800083a0`
- `0x18000a8cc`

## pseudocode

```c
CGhostThread *__fastcall CGhostThread::`vector deleting destructor'(CGhostThread *this, char a2)
{
  CGhostThread::~CGhostThread(this);
  if ( (a2 & 1) != 0 )
  {
    if ( (a2 & 4) != 0 )
      __global_delete(this);
    else
      DefaultHeap::Free(this);
  }
  return this;
}

```

## disassembly

```asm
0x1800083a0  mov     [rsp+arg_0], rbx
0x1800083a5  push    rdi
0x1800083a6  sub     rsp, 20h
0x1800083aa  mov     edi, edx
0x1800083ac  mov     rbx, rcx
0x1800083af  call    ??1CGhostThread@@UEAA@XZ; CGhostThread::~CGhostThread(void)
0x1800083b4  test    dil, 1
0x1800083b8  jz      short loc_1800083D4
0x1800083ba  mov     rcx, rbx; void *
0x1800083bd  test    dil, 4
0x1800083c1  jnz     short loc_1800083CA
0x1800083c3  call    ?Free@DefaultHeap@@SAXPEAX@Z; DefaultHeap::Free(void *)
0x1800083c8  jmp     short loc_1800083D4
0x1800083ca  mov     edx, 90h; unsigned __int64
0x1800083cf  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x1800083d4  mov     rax, rbx
0x1800083d7  mov     rbx, [rsp+28h+arg_0]
0x1800083dc  add     rsp, 20h
0x1800083e0  pop     rdi
0x1800083e1  retn
```
