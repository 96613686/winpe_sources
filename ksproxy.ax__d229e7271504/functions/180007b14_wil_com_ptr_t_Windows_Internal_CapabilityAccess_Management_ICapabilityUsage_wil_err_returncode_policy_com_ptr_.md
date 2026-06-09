# wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)

- ea: `0x180007b14`
- end: `0x180007b32`
- name: `??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007838`
- `0x180007918`
- `0x180007b38`
- `0x180007eb0`
- `0x1800111fc`
- `0x1800119f0`
- `0x180012d00`
- `0x180019108`
- `0x18001c5c4`
- `0x1800420c0`
- `0x180043890`
- `0x1800438b8`
- `0x1800439d8`
- `0x180043dbc`
- `0x180043e30`
- `0x180043f14`
- `0x1800440d0`

## callees

- `0x180007b14`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(
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
0x180007b14  sub     rsp, 28h
0x180007b18  mov     rcx, [rcx]
0x180007b1b  test    rcx, rcx
0x180007b1e  jz      short loc_180007B2C
0x180007b20  mov     rax, [rcx]
0x180007b23  mov     rax, [rax+10h]
0x180007b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b2c  add     rsp, 28h
0x180007b30  retn
```
