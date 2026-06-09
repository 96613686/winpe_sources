# HvsocketAddressInfoToPartitionId

- ea: `0x1400190c8`
- end: `0x140019107`
- name: `HvsocketAddressInfoToPartitionId`
- size: `63`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140006f1c`
- `0x140018130`
- `0x140018e20`
- `0x14001ac90`
- `0x14001ae50`
- `0x14001b200`
- `0x14001b3c0`

## callees

- `0x1400190c8`

## pseudocode

```c
_OWORD *__fastcall HvsocketAddressInfoToPartitionId(_OWORD *a1, __int64 a2)
{
  __int128 v2; // xmm0
  _OWORD *result; // rax

  if ( *(_QWORD *)(a2 + 16) == *(_QWORD *)&HV_GUID_ZERO.Data1 && *(_QWORD *)(a2 + 24) == *(_QWORD *)HV_GUID_ZERO.Data4 )
  {
    if ( *(_QWORD *)(a2 + 32) == *(_QWORD *)&HV_GUID_ZERO.Data1 && *(_QWORD *)(a2 + 40) == *(_QWORD *)HV_GUID_ZERO.Data4 )
      __fastfail(3u);
    v2 = *(_OWORD *)(a2 + 32);
  }
  else
  {
    v2 = *(_OWORD *)(a2 + 16);
  }
  result = a1;
  *a1 = v2;
  return result;
}

```

## disassembly

```asm
0x1400190c8  mov     r9, qword ptr cs:HV_GUID_ZERO.Data1
0x1400190cf  cmp     [rdx+10h], r9
0x1400190d3  jnz     short loc_1400190FB
0x1400190d5  mov     r8, qword ptr cs:HV_GUID_ZERO.Data4
0x1400190dc  cmp     [rdx+18h], r8
0x1400190e0  jnz     short loc_1400190FB
0x1400190e2  cmp     [rdx+20h], r9
0x1400190e6  jnz     short loc_1400190F5
0x1400190e8  cmp     [rdx+28h], r8
0x1400190ec  jnz     short loc_1400190F5
0x1400190ee  mov     ecx, 3
0x1400190f3  int     29h; Win8: RtlFailFast(ecx)
0x1400190f5  movups  xmm0, xmmword ptr [rdx+20h]
0x1400190f9  jmp     short loc_1400190FF
0x1400190fb  movups  xmm0, xmmword ptr [rdx+10h]
0x1400190ff  mov     rax, rcx
0x140019102  movdqu  xmmword ptr [rcx], xmm0
0x140019106  retn
```
