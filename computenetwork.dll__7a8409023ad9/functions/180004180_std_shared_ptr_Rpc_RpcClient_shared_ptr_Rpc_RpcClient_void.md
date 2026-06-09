# std::shared_ptr<Rpc::RpcClient>::~shared_ptr<Rpc::RpcClient>(void)

- ea: `0x180004180`
- end: `0x1800041cc`
- name: `??1?$shared_ptr@VRpcClient@Rpc@@@std@@QEAA@XZ`
- size: `76`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d006`
- `0x18000d02a`
- `0x18000d04e`
- `0x18000d940`
- `0x18000e255`

## callees

- `0x180004180`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<Rpc::RpcClient>::~shared_ptr<Rpc::RpcClient>(__int64 a1)
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
0x180004180  push    rbx
0x180004182  sub     rsp, 20h
0x180004186  mov     rbx, [rcx+8]
0x18000418a  test    rbx, rbx
0x18000418d  jz      short loc_1800041C6
0x18000418f  or      eax, 0FFFFFFFFh
0x180004192  lock xadd [rbx+8], eax
0x180004197  cmp     eax, 1
0x18000419a  jnz     short loc_1800041C6
0x18000419c  mov     rax, [rbx]
0x18000419f  mov     rcx, rbx
0x1800041a2  mov     rax, [rax]
0x1800041a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041aa  or      eax, 0FFFFFFFFh
0x1800041ad  lock xadd [rbx+0Ch], eax
0x1800041b2  cmp     eax, 1
0x1800041b5  jnz     short loc_1800041C6
0x1800041b7  mov     rax, [rbx]
0x1800041ba  mov     rcx, rbx
0x1800041bd  mov     rax, [rax+8]
0x1800041c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c6  add     rsp, 20h
0x1800041ca  pop     rbx
0x1800041cb  retn
```
