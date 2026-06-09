# NfsProtocolFlagsToBitfield

- ea: `0x14002e2d8`
- end: `0x14002e327`
- name: `NfsProtocolFlagsToBitfield`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14002dec4`

## pseudocode

```c
char __fastcall NfsProtocolFlagsToBitfield(unsigned int a1, _BYTE *a2)
{
  char result; // al

  *a2 = a1;
  a2[2] = a1 >> 14;
  a2[1] = BYTE1(a1) & 0xF | (a1 >> 20) & 0x30 | (a1 >> 6) & 0xC0;
  result = (a1 >> 22) & 3 | HIBYTE(a1) & 0xC;
  a2[3] = result;
  return result;
}

```

## disassembly

```asm
0x14002e2d8  mov     r8d, ecx
0x14002e2db  mov     al, cl
0x14002e2dd  and     al, 0FEh
0x14002e2df  and     r8b, 1
0x14002e2e3  or      r8b, al
0x14002e2e6  mov     eax, ecx
0x14002e2e8  shr     eax, 14h
0x14002e2eb  and     al, 30h
0x14002e2ed  mov     [rdx], r8b
0x14002e2f0  mov     r8d, ecx
0x14002e2f3  shr     r8d, 6
0x14002e2f7  and     r8b, 0C0h
0x14002e2fb  or      r8b, al
0x14002e2fe  mov     eax, ecx
0x14002e300  shr     eax, 8
0x14002e303  and     al, 0Fh
0x14002e305  or      r8b, al
0x14002e308  mov     eax, ecx
0x14002e30a  shr     eax, 0Eh
0x14002e30d  mov     [rdx+2], al
0x14002e310  mov     eax, ecx
0x14002e312  shr     eax, 18h
0x14002e315  shr     ecx, 16h
0x14002e318  and     al, 0Ch
0x14002e31a  and     cl, 3
0x14002e31d  mov     [rdx+1], r8b
0x14002e321  or      al, cl
0x14002e323  mov     [rdx+3], al
0x14002e326  retn
```
