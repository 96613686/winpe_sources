# utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(void)

- ea: `0x18000f20c`
- end: `0x18000f259`
- name: `??1WorkItemWrapper@CThreadPool@utils@@QEAA@XZ`
- size: `77`
- prototype: `void __fastcall(utils::CThreadPool::WorkItemWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f1e0`
- `0x18000f260`
- `0x18000f360`

## callees

- `0x18000f20c`
- `0x180011010`

## pseudocode

```c
void __fastcall utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(utils::CThreadPool::WorkItemWrapper *this)
{
  volatile signed __int32 *v1; // rbx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v1 && _InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
    if ( _InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
  }
}

```

## disassembly

```asm
0x18000f20c  push    rbx
0x18000f20e  sub     rsp, 20h
0x18000f212  mov     rbx, [rcx+8]
0x18000f216  test    rbx, rbx
0x18000f219  jz      short loc_18000F253
0x18000f21b  or      eax, 0FFFFFFFFh
0x18000f21e  lock xadd [rbx+8], eax
0x18000f223  cmp     eax, 1
0x18000f226  jnz     short loc_18000F253
0x18000f228  mov     rax, [rbx]
0x18000f22b  mov     rcx, rbx
0x18000f22e  mov     rax, [rax]
0x18000f231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f236  or      eax, 0FFFFFFFFh
0x18000f239  lock xadd [rbx+0Ch], eax
0x18000f23e  cmp     eax, 1
0x18000f241  jnz     short loc_18000F253
0x18000f243  mov     rax, [rbx]
0x18000f246  mov     rcx, rbx
0x18000f249  mov     rax, [rax+8]
0x18000f24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f252  nop
0x18000f253  add     rsp, 20h
0x18000f257  pop     rbx
0x18000f258  retn
```
