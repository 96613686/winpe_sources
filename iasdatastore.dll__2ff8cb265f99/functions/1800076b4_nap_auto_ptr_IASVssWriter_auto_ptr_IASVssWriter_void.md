# nap::auto_ptr<IASVssWriter>::~auto_ptr<IASVssWriter>(void)

- ea: `0x1800076b4`
- end: `0x1800076d5`
- name: `??1?$auto_ptr@VIASVssWriter@@@nap@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e752`

## callees

- `0x1800076b4`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall nap::auto_ptr<IASVssWriter>::~auto_ptr<IASVssWriter>(__int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x1800076b4  sub     rsp, 28h
0x1800076b8  mov     rcx, [rcx]
0x1800076bb  test    rcx, rcx
0x1800076be  jz      short loc_1800076D0
0x1800076c0  mov     rax, [rcx]
0x1800076c3  mov     edx, 1
0x1800076c8  mov     rax, [rax]
0x1800076cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d0  add     rsp, 28h
0x1800076d4  retn
```
