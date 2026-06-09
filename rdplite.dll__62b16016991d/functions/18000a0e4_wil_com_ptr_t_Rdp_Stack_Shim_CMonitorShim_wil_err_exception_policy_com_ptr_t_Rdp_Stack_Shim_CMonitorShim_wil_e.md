# wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)

- ea: `0x18000a0e4`
- end: `0x18000a10d`
- name: `??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `37`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a114`
- `0x18000a3f4`
- `0x18000c0f0`
- `0x18000ee70`
- `0x18000f2c0`
- `0x18000f39c`
- `0x180010324`
- `0x1800106e4`
- `0x180010a30`
- `0x180010bc0`
- `0x180010cbc`
- `0x180011048`
- `0x180011490`
- `0x18001174c`
- `0x18001339c`
- `0x18001367c`
- `0x180015c24`
- `0x180016304`
- `0x180016b1c`
- `0x1800183b4`
- `0x180018570`
- `0x180018afc`
- `0x1800192c4`
- `0x1800197e4`
- `0x180019894`
- `0x18001b698`
- `0x18001c52c`
- `0x18001c858`
- `0x18001c914`
- `0x18001ce84`
- `0x18001f55c`
- `0x18001fd70`
- `0x180020cec`
- `0x180020fdc`
- `0x180021b78`
- `0x1800220b0`
- `0x1800230a8`

## callees

- `0x18000a0e4`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x18000a0e4  push    rbx
0x18000a0e6  sub     rsp, 20h
0x18000a0ea  mov     rbx, rcx
0x18000a0ed  mov     [rcx], rdx
0x18000a0f0  test    rdx, rdx
0x18000a0f3  jz      short loc_18000A104
0x18000a0f5  mov     rax, [rdx]
0x18000a0f8  mov     rcx, rdx
0x18000a0fb  mov     rax, [rax+8]
0x18000a0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a104  mov     rax, rbx
0x18000a107  add     rsp, 20h
0x18000a10b  pop     rbx
0x18000a10c  retn
```
