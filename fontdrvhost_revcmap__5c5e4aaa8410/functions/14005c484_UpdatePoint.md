# UpdatePoint

- ea: `0x14005c484`
- end: `0x14005c4b1`
- name: `UpdatePoint`
- size: `45`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14003e980`
- `0x14005c360`
- `0x14005c378`
- `0x14005d460`
- `0x14005e2c0`
- `0x14007f4c0`
- `0x14007f5b0`
- `0x14007f630`

## callees

- `0x14005c484`

## pseudocode

```c
unsigned __int64 __fastcall UpdatePoint(unsigned __int64 a1, _DWORD *a2)
{
  unsigned __int64 result; // rax

  result = HIDWORD(a1);
  if ( (int)a1 < *a2 )
    *a2 = a1;
  if ( (int)a1 > a2[1] )
    a2[1] = a1;
  if ( SHIDWORD(a1) > a2[2] )
    a2[2] = HIDWORD(a1);
  if ( SHIDWORD(a1) < a2[3] )
    a2[3] = HIDWORD(a1);
  return result;
}

```

## disassembly

```asm
0x14005c484  mov     rax, rcx
0x14005c487  shr     rax, 20h
0x14005c48b  cmp     ecx, [rdx]
0x14005c48d  jl      short loc_14005C4A4
0x14005c48f  cmp     ecx, [rdx+4]
0x14005c492  jg      short loc_14005C4A8
0x14005c494  cmp     eax, [rdx+8]
0x14005c497  jg      short loc_14005C49F
0x14005c499  cmp     eax, [rdx+0Ch]
0x14005c49c  jl      short loc_14005C4AD
0x14005c49e  retn
0x14005c49f  mov     [rdx+8], eax
0x14005c4a2  jmp     short loc_14005C499
0x14005c4a4  mov     [rdx], ecx
0x14005c4a6  jmp     short loc_14005C48F
0x14005c4a8  mov     [rdx+4], ecx
0x14005c4ab  jmp     short loc_14005C494
0x14005c4ad  mov     [rdx+0Ch], eax
0x14005c4b0  retn
```
