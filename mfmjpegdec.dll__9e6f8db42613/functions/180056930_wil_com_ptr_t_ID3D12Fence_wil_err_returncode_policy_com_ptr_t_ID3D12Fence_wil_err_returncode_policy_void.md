# wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)

- ea: `0x180056930`
- end: `0x18005694e`
- name: `??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `36`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056988`
- `0x180056f20`
- `0x180057d90`
- `0x1800587e4`
- `0x1800590d4`
- `0x180059be4`
- `0x18005a064`
- `0x18005af70`
- `0x18005d000`
- `0x180060174`
- `0x180060f90`
- `0x180063370`
- `0x180064190`
- `0x18006560c`
- `0x180066514`
- `0x1800665d4`
- `0x18006677c`
- `0x180066a34`
- `0x18006f7f7`
- `0x18006f810`
- `0x18006f829`
- `0x18006f842`
- `0x18006f91c`
- `0x18006f963`
- `0x18006f975`
- `0x18006fa05`
- `0x18006fa17`
- `0x18006fa29`
- `0x18006facb`
- `0x18006fadd`
- `0x18006fb49`
- `0x18006fbaa`
- `0x18006fbe9`
- `0x18006fbfb`
- `0x18006fc0d`
- `0x18006fc1f`

## callees

- `0x180056930`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(
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
0x180056930  sub     rsp, 28h
0x180056934  mov     rcx, [rcx]
0x180056937  test    rcx, rcx
0x18005693a  jz      short loc_180056949
0x18005693c  mov     rax, [rcx]
0x18005693f  mov     rax, [rax+10h]
0x180056943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056948  nop
0x180056949  add     rsp, 28h
0x18005694d  retn
```
