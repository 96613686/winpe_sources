# wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)

- ea: `0x18000dcdc`
- end: `0x18000dcfa`
- name: `??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e4b0`
- `0x18000e5e0`
- `0x18000e668`
- `0x18000f7cc`
- `0x18001111f`
- `0x180011131`
- `0x18001116f`
- `0x180011181`
- `0x180011436`
- `0x180011448`
- `0x180011490`

## callees

- `0x18000dcdc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
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
0x18000dcdc  sub     rsp, 28h
0x18000dce0  mov     rcx, [rcx]
0x18000dce3  test    rcx, rcx
0x18000dce6  jz      short loc_18000DCF5
0x18000dce8  mov     rax, [rcx]
0x18000dceb  mov     rax, [rax+10h]
0x18000dcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf4  nop
0x18000dcf5  add     rsp, 28h
0x18000dcf9  retn
```
