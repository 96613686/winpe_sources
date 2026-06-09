# wil::com_ptr_t<IBaseFilter,wil::err_returncode_policy>::~com_ptr_t<IBaseFilter,wil::err_returncode_policy>(void)

- ea: `0x18000a990`
- end: `0x18000a9b0`
- name: `??1?$com_ptr_t@UIBaseFilter@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800889d0`

## callees

- `0x18000a990`
- `0x180088750`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IBaseFilter,wil::err_returncode_policy>::~com_ptr_t<IBaseFilter,wil::err_returncode_policy>(
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
0x18000a990  sub     rsp, 28h
0x18000a994  mov     rcx, [rcx]
0x18000a997  test    rcx, rcx
0x18000a99a  jz      short loc_18000A9AA
0x18000a99c  mov     rax, [rcx]
0x18000a99f  mov     rax, [rax+10h]
0x18000a9a3  call    cs:__guard_dispatch_icall_fptr
0x18000a9a9  nop
0x18000a9aa  add     rsp, 28h
0x18000a9ae  retn
```
