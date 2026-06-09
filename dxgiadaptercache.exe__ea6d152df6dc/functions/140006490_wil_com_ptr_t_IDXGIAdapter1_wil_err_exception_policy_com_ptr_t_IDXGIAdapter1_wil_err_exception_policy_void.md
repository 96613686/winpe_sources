# wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>(void)

- ea: `0x140006490`
- end: `0x1400064ae`
- name: `??1?$com_ptr_t@UIDXGIAdapter1@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011666`
- `0x140011678`
- `0x14001169c`
- `0x14001177f`
- `0x140011a52`
- `0x140011a64`
- `0x140011a88`

## callees

- `0x140006490`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>(
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
0x140006490  sub     rsp, 28h
0x140006494  mov     rcx, [rcx]
0x140006497  test    rcx, rcx
0x14000649a  jz      short loc_1400064A9
0x14000649c  mov     rax, [rcx]
0x14000649f  mov     rax, [rax+10h]
0x1400064a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064a8  nop
0x1400064a9  add     rsp, 28h
0x1400064ad  retn
```
