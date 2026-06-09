# NcaHResultToWindowsError

- ea: `0x180019784`
- end: `0x1800197a3`
- name: `NcaHResultToWindowsError`
- size: `31`
- prototype: `__int64 __fastcall(int)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x180001400`
- `0x1800026d0`
- `0x180004400`
- `0x1800050d8`
- `0x1800066ac`
- `0x18000673c`
- `0x180007b58`
- `0x180009714`
- `0x180009ce0`
- `0x18000cc94`
- `0x18000d720`
- `0x1800112ac`
- `0x180011744`
- `0x180011d54`
- `0x180014058`
- `0x180014188`
- `0x18001b300`
- `0x18001b3b0`
- `0x18001b460`
- `0x18001b530`
- `0x18001b680`
- `0x18001b760`
- `0x18001b810`
- `0x18001b8d0`
- `0x18001b9a0`
- `0x18001ba70`
- `0x18001bb40`
- `0x18001c4e0`

## callees

- `0x180019784`

## pseudocode

```c
__int64 __fastcall NcaHResultToWindowsError(int a1)
{
  unsigned int v1; // edx

  v1 = a1;
  if ( a1 >= 0 )
    return 0;
  if ( (a1 & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)a1;
  return v1;
}

```

## disassembly

```asm
0x180019784  mov     edx, ecx
0x180019786  test    ecx, ecx
0x180019788  js      short loc_18001978E
0x18001978a  xor     eax, eax
0x18001978c  retn
0x18001978e  movzx   eax, dx
0x180019791  and     ecx, 1FFF0000h
0x180019797  cmp     ecx, 70000h
0x18001979d  cmovz   edx, eax
0x1800197a0  mov     eax, edx
0x1800197a2  retn
```
