# wil::com_ptr_t<IMessageSession,wil::err_returncode_policy>::~com_ptr_t<IMessageSession,wil::err_returncode_policy>(void)

- ea: `0x14000c690`
- end: `0x14000c6ad`
- name: `??1?$com_ptr_t@UIMessageSession@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c6b4`

## callees

- `0x14000c690`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IMessageSession,wil::err_returncode_policy>::~com_ptr_t<IMessageSession,wil::err_returncode_policy>(
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
0x14000c690  sub     rsp, 28h
0x14000c694  mov     rcx, [rcx]
0x14000c697  test    rcx, rcx
0x14000c69a  jz      short loc_14000C6A8
0x14000c69c  mov     rax, [rcx]
0x14000c69f  mov     rax, [rax+10h]
0x14000c6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6a8  add     rsp, 28h
0x14000c6ac  retn
```
