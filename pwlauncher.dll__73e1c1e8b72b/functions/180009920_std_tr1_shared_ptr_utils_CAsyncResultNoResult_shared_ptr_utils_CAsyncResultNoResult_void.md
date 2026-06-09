# std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(void)

- ea: `0x180009920`
- end: `0x18000996d`
- name: `??1?$shared_ptr@VCAsyncResultNoResult@utils@@@tr1@std@@QEAA@XZ`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001065c`
- `0x180010763`
- `0x180010789`
- `0x18001079b`
- `0x1800108f3`
- `0x180010905`

## callees

- `0x180009920`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(
        __int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009920  push    rbx
0x180009922  sub     rsp, 20h
0x180009926  mov     rbx, [rcx+8]
0x18000992a  test    rbx, rbx
0x18000992d  jz      short loc_180009967
0x18000992f  or      eax, 0FFFFFFFFh
0x180009932  lock xadd [rbx+8], eax
0x180009937  cmp     eax, 1
0x18000993a  jnz     short loc_180009967
0x18000993c  mov     rax, [rbx]
0x18000993f  mov     rcx, rbx
0x180009942  mov     rax, [rax]
0x180009945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000994a  or      eax, 0FFFFFFFFh
0x18000994d  lock xadd [rbx+0Ch], eax
0x180009952  cmp     eax, 1
0x180009955  jnz     short loc_180009967
0x180009957  mov     rax, [rbx]
0x18000995a  mov     rcx, rbx
0x18000995d  mov     rax, [rax+8]
0x180009961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009966  nop
0x180009967  add     rsp, 20h
0x18000996b  pop     rbx
0x18000996c  retn
```
