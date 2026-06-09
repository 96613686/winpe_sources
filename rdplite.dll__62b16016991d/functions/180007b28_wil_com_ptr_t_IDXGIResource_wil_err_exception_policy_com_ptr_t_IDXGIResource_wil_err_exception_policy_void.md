# wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)

- ea: `0x180007b28`
- end: `0x180007b46`
- name: `??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `132`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007b70`
- `0x180009a78`
- `0x18000a114`
- `0x18000a7bc`
- `0x18000a8c4`
- `0x18000bef0`
- `0x18000c010`
- `0x18000c0f0`
- `0x18000f698`
- `0x18000fb28`
- `0x18000fd10`
- `0x18000fe3c`
- `0x18000fe88`
- `0x1800106e4`
- `0x180010a30`
- `0x180010bc0`
- `0x180010cbc`
- `0x180011048`
- `0x180011490`
- `0x18001174c`
- `0x180011a1c`
- `0x180011b5c`
- `0x180012558`
- `0x1800128e0`
- `0x1800135bc`
- `0x18001367c`
- `0x180016304`
- `0x180016738`
- `0x180017290`
- `0x180017d90`
- `0x180018170`
- `0x180018570`
- `0x180018688`
- `0x180018764`
- `0x18001888c`
- `0x18001890c`
- `0x180018afc`
- `0x180018cd0`
- `0x180019894`
- `0x18001a2a0`
- `0x18001b698`
- `0x18001bb08`
- `0x18001c230`
- `0x18001c4d4`
- `0x18001c500`
- `0x18001cb94`
- `0x18001cbc4`
- `0x18001cc58`
- `0x18001cc8c`
- `0x18001ccec`

## callees

- `0x180007b28`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(
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
0x180007b28  sub     rsp, 28h
0x180007b2c  mov     rcx, [rcx]
0x180007b2f  test    rcx, rcx
0x180007b32  jz      short loc_180007B41
0x180007b34  mov     rax, [rcx]
0x180007b37  mov     rax, [rax+10h]
0x180007b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b40  nop
0x180007b41  add     rsp, 28h
0x180007b45  retn
```
