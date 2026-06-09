# std::shared_ptr<ProviderContext>::operator=(std::shared_ptr<ProviderContext> const &)

- ea: `0x140011c18`
- end: `0x140011c8e`
- name: `??4?$shared_ptr@VProviderContext@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `118`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140011ea4`
- `0x14001211c`
- `0x1400124d0`
- `0x140015cc4`

## callees

- `0x140011c18`
- `0x14001c010`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<ProviderContext>::operator=(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax
  volatile signed __int32 *v4; // rbx
  __int64 v5; // r8

  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v4 = (volatile signed __int32 *)a1[1];
  v5 = a2[1];
  *a1 = *a2;
  a1[1] = v5;
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140011c18  mov     [rsp+arg_0], rbx
0x140011c1d  push    rdi
0x140011c1e  sub     rsp, 20h
0x140011c22  mov     rax, [rdx+8]
0x140011c26  mov     rdi, rcx
0x140011c29  test    rax, rax
0x140011c2c  jz      short loc_140011C32
0x140011c2e  lock inc dword ptr [rax+8]
0x140011c32  mov     rbx, [rcx+8]
0x140011c36  mov     r8, [rdx+8]
0x140011c3a  mov     rax, [rdx]
0x140011c3d  mov     [rcx], rax
0x140011c40  mov     [rcx+8], r8
0x140011c44  test    rbx, rbx
0x140011c47  jz      short loc_140011C80
0x140011c49  or      eax, 0FFFFFFFFh
0x140011c4c  lock xadd [rbx+8], eax
0x140011c51  cmp     eax, 1
0x140011c54  jnz     short loc_140011C80
0x140011c56  mov     rax, [rbx]
0x140011c59  mov     rcx, rbx
0x140011c5c  mov     rax, [rax]
0x140011c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c64  or      eax, 0FFFFFFFFh
0x140011c67  lock xadd [rbx+0Ch], eax
0x140011c6c  cmp     eax, 1
0x140011c6f  jnz     short loc_140011C80
0x140011c71  mov     rax, [rbx]
0x140011c74  mov     rcx, rbx
0x140011c77  mov     rax, [rax+8]
0x140011c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c80  mov     rbx, [rsp+28h+arg_0]
0x140011c85  mov     rax, rdi
0x140011c88  add     rsp, 20h
0x140011c8c  pop     rdi
0x140011c8d  retn
```
