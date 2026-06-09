# PerfpDosError(long)

- ea: `0x18000bef8`
- end: `0x18000bf32`
- name: `?PerfpDosError@@YAKJ@Z`
- size: `58`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008c30`
- `0x1800093a8`
- `0x18000a7b8`
- `0x18000b8a0`
- `0x18000c2b0`
- `0x18000c424`
- `0x18000e1a8`
- `0x18000f640`
- `0x180011b08`

## callees

- `0x18000bef8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000bf28`

## pseudocode

```c
ULONG __fastcall PerfpDosError(NTSTATUS a1)
{
  ULONG result; // eax

  if ( !a1 )
    return 0;
  if ( a1 == -2147483643 )
    return 234;
  result = 258;
  if ( a1 != 258 )
  {
    if ( a1 != 63 )
    {
      if ( (unsigned int)(a1 - 128) > 0x3F )
        return RtlNtStatusToDosError(a1);
      else
        return 1223;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bef8  test    ecx, ecx
0x18000befa  jz      short loc_18000BF2F
0x18000befc  cmp     ecx, 80000005h
0x18000bf02  jnz     short loc_18000BF0B
0x18000bf04  mov     eax, 0EAh
0x18000bf09  jmp     short locret_18000BF31
0x18000bf0b  mov     eax, 102h
0x18000bf10  cmp     ecx, eax
0x18000bf12  jz      short locret_18000BF31
0x18000bf14  cmp     ecx, 3Fh ; '?'
0x18000bf17  jz      short loc_18000BF2F
0x18000bf19  lea     eax, [rcx-80h]
0x18000bf1c  cmp     eax, 3Fh ; '?'
0x18000bf1f  ja      short loc_18000BF28
0x18000bf21  mov     eax, 4C7h
0x18000bf26  jmp     short locret_18000BF31
0x18000bf28  jmp     cs:__imp_RtlNtStatusToDosError
0x18000bf2f  xor     eax, eax
0x18000bf31  retn
```
