# wil::com_ptr_t<IRunningTask,wil::err_exception_policy>::~com_ptr_t<IRunningTask,wil::err_exception_policy>(void)

- ea: `0x18001e670`
- end: `0x18001e68f`
- name: `??1?$com_ptr_t@UIRunningTask@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800232b9`
- `0x1800232cb`
- `0x1800232dd`
- `0x1800232ef`
- `0x180023301`

## callees

- `0x18001e670`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IRunningTask,wil::err_exception_policy>::~com_ptr_t<IRunningTask,wil::err_exception_policy>(
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
0x18001e670  sub     rsp, 28h
0x18001e674  mov     rcx, [rcx]
0x18001e677  test    rcx, rcx
0x18001e67a  jz      short loc_18001E689
0x18001e67c  mov     rax, [rcx]
0x18001e67f  mov     rax, [rax+10h]
0x18001e683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e688  nop
0x18001e689  add     rsp, 28h
0x18001e68d  retn
```
