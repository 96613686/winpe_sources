# CMSMQTriggersConfig::InterfaceSupportsErrorInfo(_GUID const &)

- ea: `0x18000c6e0`
- end: `0x18000c717`
- name: `?InterfaceSupportsErrorInfo@CMSMQTriggersConfig@@UEAAJAEBU_GUID@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800033e4`
- `0x18000c6e0`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::InterfaceSupportsErrorInfo(CMSMQTriggersConfig *this, const struct _GUID *a2)
{
  int i; // r8d
  int v3; // r8d

  for ( i = 0; !i; i = v3 + 1 )
  {
    if ( (unsigned int)InlineIsEqualGUID(&IID_IMSMQTriggersConfig, a2) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000c6e0  sub     rsp, 28h
0x18000c6e4  xor     r8d, r8d
0x18000c6e7  cmp     r8d, 1
0x18000c6eb  jnb     short loc_18000C70D
0x18000c6ed  lea     rax, off_180023A98
0x18000c6f4  movsxd  rcx, r8d
0x18000c6f7  mov     rcx, [rax+rcx*8]; struct _GUID *
0x18000c6fb  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000c700  test    eax, eax
0x18000c702  jnz     short loc_18000C709
0x18000c704  inc     r8d
0x18000c707  jmp     short loc_18000C6E7
0x18000c709  xor     eax, eax
0x18000c70b  jmp     short loc_18000C712
0x18000c70d  mov     eax, 1
0x18000c712  add     rsp, 28h
0x18000c716  retn
```
