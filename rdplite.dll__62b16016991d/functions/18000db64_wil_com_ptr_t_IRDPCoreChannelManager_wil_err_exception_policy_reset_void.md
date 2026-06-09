# wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)

- ea: `0x18000db64`
- end: `0x18000db8c`
- name: `?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a114`
- `0x18000a7bc`
- `0x18000ad3c`
- `0x18000b2c0`
- `0x18000bef0`
- `0x18000c010`
- `0x18000c410`
- `0x18000cbc0`
- `0x1800143c0`
- `0x1800174c0`
- `0x180017d90`
- `0x18001a2a0`
- `0x18001a8a8`
- `0x18001d09c`
- `0x18001d954`
- `0x18001e0b8`
- `0x18001e4b4`
- `0x18001e824`
- `0x18001ec84`

## callees

- `0x18000db64`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000db64  sub     rsp, 28h
0x18000db68  mov     rdx, [rcx]
0x18000db6b  mov     qword ptr [rcx], 0
0x18000db72  test    rdx, rdx
0x18000db75  jz      short loc_18000DB87
0x18000db77  mov     rax, [rdx]
0x18000db7a  mov     rcx, rdx
0x18000db7d  mov     rax, [rax+10h]
0x18000db81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db86  nop
0x18000db87  add     rsp, 28h
0x18000db8b  retn
```
