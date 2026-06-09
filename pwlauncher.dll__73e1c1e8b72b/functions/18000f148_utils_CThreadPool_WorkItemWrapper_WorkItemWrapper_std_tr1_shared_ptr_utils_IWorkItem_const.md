# utils::CThreadPool::WorkItemWrapper::WorkItemWrapper(std::tr1::shared_ptr<utils::IWorkItem> const &)

- ea: `0x18000f148`
- end: `0x18000f1d7`
- name: `??0WorkItemWrapper@CThreadPool@utils@@QEAA@AEBV?$shared_ptr@VIWorkItem@utils@@@tr1@std@@@Z`
- size: `143`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f288`

## callees

- `0x18000f148`
- `0x180011010`

## pseudocode

```c
_QWORD *__fastcall utils::CThreadPool::WorkItemWrapper::WorkItemWrapper(_QWORD *a1, __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  signed __int32 v5; // eax
  volatile signed __int32 *v6; // rdi

  *a1 = 0;
  a1[1] = 0;
  v3 = a2[1];
  if ( v3 )
  {
    v4 = *a2;
    while ( 1 )
    {
      v5 = *(_DWORD *)(v3 + 8);
      if ( !v5 )
        break;
      if ( v5 == _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v5 + 1, v5) )
      {
        v6 = (volatile signed __int32 *)a1[1];
        if ( v6 )
        {
          if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
            if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
          }
        }
        a1[1] = v3;
        *a1 = v4;
        return a1;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000f148  push    rbx
0x18000f14a  push    rbp
0x18000f14b  push    rsi
0x18000f14c  push    rdi
0x18000f14d  sub     rsp, 28h
0x18000f151  mov     qword ptr [rcx], 0
0x18000f158  mov     rbx, rcx
0x18000f15b  mov     qword ptr [rcx+8], 0
0x18000f163  mov     rsi, [rdx+8]
0x18000f167  test    rsi, rsi
0x18000f16a  jz      short loc_18000F1CB
0x18000f16c  mov     rbp, [rdx]
0x18000f16f  jmp     short loc_18000F17B
0x18000f171  lea     ecx, [rax+1]
0x18000f174  lock cmpxchg [rsi+8], ecx
0x18000f179  jz      short loc_18000F184
0x18000f17b  mov     eax, [rsi+8]
0x18000f17e  test    eax, eax
0x18000f180  jnz     short loc_18000F171
0x18000f182  jmp     short loc_18000F1CB
0x18000f184  mov     rdi, [rbx+8]
0x18000f188  test    rdi, rdi
0x18000f18b  jz      short loc_18000F1C4
0x18000f18d  or      eax, 0FFFFFFFFh
0x18000f190  lock xadd [rdi+8], eax
0x18000f195  cmp     eax, 1
0x18000f198  jnz     short loc_18000F1C4
0x18000f19a  mov     rax, [rdi]
0x18000f19d  mov     rcx, rdi
0x18000f1a0  mov     rax, [rax]
0x18000f1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a8  or      eax, 0FFFFFFFFh
0x18000f1ab  lock xadd [rdi+0Ch], eax
0x18000f1b0  cmp     eax, 1
0x18000f1b3  jnz     short loc_18000F1C4
0x18000f1b5  mov     rax, [rdi]
0x18000f1b8  mov     rcx, rdi
0x18000f1bb  mov     rax, [rax+8]
0x18000f1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c4  mov     [rbx+8], rsi
0x18000f1c8  mov     [rbx], rbp
0x18000f1cb  mov     rax, rbx
0x18000f1ce  add     rsp, 28h
0x18000f1d2  pop     rdi
0x18000f1d3  pop     rsi
0x18000f1d4  pop     rbp
0x18000f1d5  pop     rbx
0x18000f1d6  retn
```
