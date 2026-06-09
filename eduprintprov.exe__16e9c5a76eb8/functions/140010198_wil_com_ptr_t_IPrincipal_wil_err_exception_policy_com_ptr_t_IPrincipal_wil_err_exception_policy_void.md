# wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)

- ea: `0x140010198`
- end: `0x1400101b6`
- name: `??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013619`
- `0x14001362f`
- `0x140013645`
- `0x1400136fc`
- `0x14001370e`
- `0x140013732`
- `0x140013756`
- `0x140013768`
- `0x14001377a`
- `0x14001378c`
- `0x14001379e`
- `0x1400137b0`
- `0x1400137c2`
- `0x1400137d4`

## callees

- `0x140010198`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(
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
0x140010198  sub     rsp, 28h
0x14001019c  mov     rcx, [rcx]
0x14001019f  test    rcx, rcx
0x1400101a2  jz      short loc_1400101B1
0x1400101a4  mov     rax, [rcx]
0x1400101a7  mov     rax, [rax+10h]
0x1400101ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101b0  nop
0x1400101b1  add     rsp, 28h
0x1400101b5  retn
```
