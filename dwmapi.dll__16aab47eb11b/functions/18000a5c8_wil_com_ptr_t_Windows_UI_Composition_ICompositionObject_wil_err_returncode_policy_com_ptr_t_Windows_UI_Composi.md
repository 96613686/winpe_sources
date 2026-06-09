# wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)

- ea: `0x18000a5c8`
- end: `0x18000a5e5`
- name: `??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006670`

## callees

- `0x18000a5c8`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(
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
0x18000a5c8  sub     rsp, 28h
0x18000a5cc  mov     rcx, [rcx]
0x18000a5cf  test    rcx, rcx
0x18000a5d2  jz      short loc_18000A5E0
0x18000a5d4  mov     rax, [rcx]
0x18000a5d7  mov     rax, [rax+10h]
0x18000a5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5e0  add     rsp, 28h
0x18000a5e4  retn
```
