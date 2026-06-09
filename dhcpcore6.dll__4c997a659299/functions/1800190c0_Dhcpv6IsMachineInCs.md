# Dhcpv6IsMachineInCs

- ea: `0x1800190c0`
- end: `0x1800190e2`
- name: `Dhcpv6IsMachineInCs`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180008440`
- `0x180008d70`
- `0x180014590`
- `0x18001b1d0`
- `0x18001bbb0`
- `0x18001bd50`
- `0x18001d4c4`
- `0x18001f0d8`
- `0x180020610`
- `0x180020940`
- `0x180020d50`
- `0x180021150`
- `0x18002458c`
- `0x180025094`

## callees

- `0x1800190c0`

## pseudocode

```c
__int64 Dhcpv6IsMachineInCs()
{
  __int64 result; // rax

  result = 0;
  if ( Dhcpv6GlobalIsCrmRegistered )
  {
    if ( !Dhcpv6GlobalCrmIsInCS )
      return result;
  }
  else if ( !Dhcpv6GlobalIsInCS )
  {
    return result;
  }
  return 1;
}

```

## disassembly

```asm
0x1800190c0  xor     eax, eax
0x1800190c2  cmp     cs:Dhcpv6GlobalIsCrmRegistered, eax
0x1800190c8  jz      short loc_1800190D4
0x1800190ca  cmp     cs:Dhcpv6GlobalCrmIsInCS, eax
0x1800190d0  jz      short locret_1800190E1
0x1800190d2  jmp     short loc_1800190DC
0x1800190d4  cmp     cs:Dhcpv6GlobalIsInCS, eax
0x1800190da  jz      short locret_1800190E1
0x1800190dc  mov     eax, 1
0x1800190e1  retn
```
