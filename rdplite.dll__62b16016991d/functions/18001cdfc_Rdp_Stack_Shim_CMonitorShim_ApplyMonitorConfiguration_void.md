# Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(void)

- ea: `0x18001cdfc`
- end: `0x18001ce7d`
- name: `?ApplyMonitorConfiguration@CMonitorShim@Shim@Stack@Rdp@@QEAA?AW4AVENC_MONITOR_UPDATE_FLAGS@Avenc@4@XZ`
- size: `129`
- prototype: `__int64 __fastcall(Rdp::Stack::Shim::CMonitorShim *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001a974`
- `0x18001aac8`
- `0x18001e824`

## callees

- `0x18001cdfc`
- `0x18001d09c`
- `0x18001d954`
- `0x18001e0b8`
- `0x18001e4b4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(Rdp::Stack::Shim::CMonitorShim *a1)
{
  unsigned int v2; // ebx
  int v3; // esi

  v2 = 0;
  v3 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *))(**((_QWORD **)a1 + 30) + 32LL))(*((_QWORD **)a1 + 30));
  if ( (v3 & 2) != 0 )
  {
    Rdp::Stack::Shim::CMonitorShim::SetDisplayModeProperties(a1);
    v2 = 1;
  }
  if ( (v3 & 4) != 0 )
  {
    Rdp::Stack::Shim::CMonitorShim::SetScaleFactorProperties(a1);
    v2 |= 2u;
  }
  if ( (v3 & 0x10) != 0 )
  {
    Rdp::Stack::Shim::CMonitorShim::SetColorimetryProperties(a1);
    v2 |= 4u;
  }
  if ( (v3 & 0x20) != 0 )
  {
    Rdp::Stack::Shim::CMonitorShim::SetSdrWhiteLevelProperties(a1);
    v2 |= 8u;
  }
  return v2;
}

```

## disassembly

```asm
0x18001cdfc  mov     [rsp+arg_0], rbx
0x18001ce01  mov     [rsp+arg_8], rsi
0x18001ce06  push    rdi
0x18001ce07  sub     rsp, 20h
0x18001ce0b  mov     rdi, rcx
0x18001ce0e  mov     rcx, [rcx+0F0h]
0x18001ce15  mov     rax, [rcx]
0x18001ce18  mov     rax, [rax+20h]
0x18001ce1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce21  xor     ebx, ebx
0x18001ce23  mov     esi, [rax]
0x18001ce25  test    sil, 2
0x18001ce29  jz      short loc_18001CE38
0x18001ce2b  mov     rcx, rdi; this
0x18001ce2e  call    ?SetDisplayModeProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CMonitorShim::SetDisplayModeProperties(void)
0x18001ce33  mov     ebx, 1
0x18001ce38  test    sil, 4
0x18001ce3c  jz      short loc_18001CE49
0x18001ce3e  mov     rcx, rdi; this
0x18001ce41  call    ?SetScaleFactorProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CMonitorShim::SetScaleFactorProperties(void)
0x18001ce46  or      ebx, 2
0x18001ce49  test    sil, 10h
0x18001ce4d  jz      short loc_18001CE5A
0x18001ce4f  mov     rcx, rdi; this
0x18001ce52  call    ?SetColorimetryProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CMonitorShim::SetColorimetryProperties(void)
0x18001ce57  or      ebx, 4
0x18001ce5a  test    sil, 20h
0x18001ce5e  jz      short loc_18001CE6B
0x18001ce60  mov     rcx, rdi; this
0x18001ce63  call    ?SetSdrWhiteLevelProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CMonitorShim::SetSdrWhiteLevelProperties(void)
0x18001ce68  or      ebx, 8
0x18001ce6b  mov     rsi, [rsp+28h+arg_8]
0x18001ce70  mov     eax, ebx
0x18001ce72  mov     rbx, [rsp+28h+arg_0]
0x18001ce77  add     rsp, 20h
0x18001ce7b  pop     rdi
0x18001ce7c  retn
```
