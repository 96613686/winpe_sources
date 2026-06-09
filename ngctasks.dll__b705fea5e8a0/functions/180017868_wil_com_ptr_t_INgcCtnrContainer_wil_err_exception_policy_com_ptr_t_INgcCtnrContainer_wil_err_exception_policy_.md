# wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)

- ea: `0x180017868`
- end: `0x180017886`
- name: `??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800189d4`
- `0x18001c254`
- `0x180020a80`
- `0x180020afe`

## callees

- `0x180017868`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(
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
0x180017868  sub     rsp, 28h
0x18001786c  mov     rcx, [rcx]
0x18001786f  test    rcx, rcx
0x180017872  jz      short loc_180017881
0x180017874  mov     rax, [rcx]
0x180017877  mov     rax, [rax+10h]
0x18001787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017880  nop
0x180017881  add     rsp, 28h
0x180017885  retn
```
