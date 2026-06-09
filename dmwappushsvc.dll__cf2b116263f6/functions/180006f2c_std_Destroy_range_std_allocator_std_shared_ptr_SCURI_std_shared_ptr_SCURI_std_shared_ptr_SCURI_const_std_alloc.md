# std::_Destroy_range<std::allocator<std::shared_ptr<SCURI>>>(std::shared_ptr<SCURI> *,std::shared_ptr<SCURI> * const,std::allocator<std::shared_ptr<SCURI>> &)

- ea: `0x180006f2c`
- end: `0x180006f9f`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@VSCURI@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VSCURI@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VSCURI@@@std@@@0@@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ca0`

## callees

- `0x180006f2c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<SCURI>>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  volatile signed __int32 *v4; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(volatile signed __int32 **)(v3 + 8);
      if ( v4 )
      {
        result = (unsigned int)_InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
          result = (unsigned int)_InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF);
          if ( (_DWORD)result == 1 )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        }
      }
      v3 += 16;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180006f2c  cmp     rcx, rdx
0x180006f2f  jz      short locret_180006F9E
0x180006f31  mov     [rsp+arg_0], rbx
0x180006f36  mov     [rsp+arg_8], rsi
0x180006f3b  push    rdi
0x180006f3c  sub     rsp, 20h
0x180006f40  mov     rsi, rdx
0x180006f43  mov     rdi, rcx
0x180006f46  mov     rbx, [rdi+8]
0x180006f4a  test    rbx, rbx
0x180006f4d  jz      short loc_180006F86
0x180006f4f  or      eax, 0FFFFFFFFh
0x180006f52  lock xadd [rbx+8], eax
0x180006f57  cmp     eax, 1
0x180006f5a  jnz     short loc_180006F86
0x180006f5c  mov     rax, [rbx]
0x180006f5f  mov     rcx, rbx
0x180006f62  mov     rax, [rax]
0x180006f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6a  or      eax, 0FFFFFFFFh
0x180006f6d  lock xadd [rbx+0Ch], eax
0x180006f72  cmp     eax, 1
0x180006f75  jnz     short loc_180006F86
0x180006f77  mov     rax, [rbx]
0x180006f7a  mov     rcx, rbx
0x180006f7d  mov     rax, [rax+8]
0x180006f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f86  add     rdi, 10h
0x180006f8a  cmp     rdi, rsi
0x180006f8d  jnz     short loc_180006F46
0x180006f8f  mov     rbx, [rsp+28h+arg_0]
0x180006f94  mov     rsi, [rsp+28h+arg_8]
0x180006f99  add     rsp, 20h
0x180006f9d  pop     rdi
0x180006f9e  retn
```
