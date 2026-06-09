# wil::com_ptr_t<IContextCallback,wil::err_exception_policy>::~com_ptr_t<IContextCallback,wil::err_exception_policy>(void)

- ea: `0x1800095f4`
- end: `0x180009612`
- name: `??1?$com_ptr_t@UIContextCallback@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800158e9`

## callees

- `0x1800095f4`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IContextCallback,wil::err_exception_policy>::~com_ptr_t<IContextCallback,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800095f4  sub     rsp, 28h
0x1800095f8  mov     rcx, [rcx]
0x1800095fb  test    rcx, rcx
0x1800095fe  jz      short loc_18000960D
0x180009600  mov     rax, [rcx]
0x180009603  mov     rax, [rax+10h]
0x180009607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000960c  nop
0x18000960d  add     rsp, 28h
0x180009611  retn
```
