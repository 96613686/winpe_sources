# PcQoSPConfigureGlobalSetting

- ea: `0x14000ffe0`
- end: `0x14001003a`
- name: `PcQoSPConfigureGlobalSetting`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000ffe0`
- `0x140011670`

## pseudocode

```c
__int64 __fastcall PcQoSPConfigureGlobalSetting(__int64 a1)
{
  __int64 result; // rax
  int *v2; // rdx

  result = 0;
  if ( !*(_DWORD *)a1 )
  {
    if ( *(_DWORD *)(a1 + 16) == 4 )
    {
      v2 = *(int **)(a1 + 8);
      PcgAllowAppDSCPMarking = *v2;
      if ( PcgEventTraceEnabled )
        PcpEtwWriteEventUlongPtr(
          (const EVENT_DESCRIPTOR *)QOS_EVENT_PACER_ALLOW_APP_DSCP_MARKING,
          0,
          0,
          1u,
          (__int64)v2);
      return 0;
    }
    else
    {
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ffe0  sub     rsp, 38h
0x14000ffe4  xor     eax, eax
0x14000ffe6  cmp     [rcx], eax
0x14000ffe8  jnz     short loc_140010034
0x14000ffea  cmp     dword ptr [rcx+10h], 4
0x14000ffee  jz      short loc_14000FFF7
0x14000fff0  mov     eax, 0C000000Dh
0x14000fff5  jmp     short loc_140010034
0x14000fff7  mov     rdx, [rcx+8]
0x14000fffb  mov     eax, [rdx]
0x14000fffd  mov     cs:PcgAllowAppDSCPMarking, eax
0x140010003  mov     eax, cs:PcgEventTraceEnabled
0x140010009  test    eax, eax
0x14001000b  jz      short loc_140010032
0x14001000d  mov     [rsp+38h+var_10], 4
0x140010016  lea     rcx, QOS_EVENT_PACER_ALLOW_APP_DSCP_MARKING
0x14001001d  mov     [rsp+38h+var_18], rdx
0x140010022  mov     r9d, 1
0x140010028  xor     edx, edx
0x14001002a  xor     r8d, r8d
0x14001002d  call    PcpEtwWriteEventUlongPtr
0x140010032  xor     eax, eax
0x140010034  add     rsp, 38h
0x140010038  retn
```
