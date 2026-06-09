# EventCompletedHandler<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>::~EventCompletedHandler<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>(void)

- ea: `0x180023350`
- end: `0x1800233b1`
- name: `??1?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@UEAA@XZ`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023490`

## callees

- `0x180023350`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::~EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>(
        __int64 a1)
{
  volatile signed __int32 *v2; // rbx
  __int64 result; // rax

  v2 = *(volatile signed __int32 **)(a1 + 24);
  if ( v2 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      result = (unsigned int)_InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  *(_DWORD *)(a1 + 12) = -1073741823;
  return result;
}

```

## disassembly

```asm
0x180023350  mov     [rsp+arg_0], rbx
0x180023355  push    rdi
0x180023356  sub     rsp, 20h
0x18002335a  mov     rdi, rcx
0x18002335d  mov     rbx, [rcx+18h]
0x180023361  test    rbx, rbx
0x180023364  jz      short loc_18002339E
0x180023366  or      eax, 0FFFFFFFFh
0x180023369  lock xadd [rbx+8], eax
0x18002336e  cmp     eax, 1
0x180023371  jnz     short loc_18002339E
0x180023373  mov     rax, [rbx]
0x180023376  mov     rcx, rbx
0x180023379  mov     rax, [rax]
0x18002337c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023381  or      eax, 0FFFFFFFFh
0x180023384  lock xadd [rbx+0Ch], eax
0x180023389  cmp     eax, 1
0x18002338c  jnz     short loc_18002339E
0x18002338e  mov     rax, [rbx]
0x180023391  mov     rcx, rbx
0x180023394  mov     rax, [rax+8]
0x180023398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002339d  nop
0x18002339e  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800233a5  mov     rbx, [rsp+28h+arg_0]
0x1800233aa  add     rsp, 20h
0x1800233ae  pop     rdi
0x1800233af  retn
```
