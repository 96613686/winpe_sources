# ValidateSslProvHandle

- ea: `0x180009ea0`
- end: `0x180009ec3`
- name: `ValidateSslProvHandle`
- size: `35`
- prototype: `__int64(void)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x180009830`
- `0x180009aa0`
- `0x180009cf0`
- `0x180009e50`
- `0x1800116b0`
- `0x180012120`
- `0x180012a70`
- `0x180015cd0`
- `0x180016350`
- `0x180019be0`
- `0x18001a8e0`
- `0x18001aa60`
- `0x18001ab20`
- `0x18001ac70`
- `0x18001add0`
- `0x18001aef0`
- `0x18001b050`
- `0x18001b140`
- `0x18001b2c0`
- `0x18001b490`
- `0x18001b500`
- `0x18001b5c0`
- `0x18001b680`

## callees

- `0x180009ea0`

## pseudocode

```c
_DWORD *__fastcall ValidateSslProvHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 )
    return 0;
  result = 0;
  if ( !a1[3] )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180009ea0  test    rcx, rcx
0x180009ea3  jz      short loc_180009EC0
0x180009ea5  cmp     dword ptr [rcx], 1B0h
0x180009eab  jb      short loc_180009EC0
0x180009ead  cmp     dword ptr [rcx+4], 44444441h
0x180009eb4  jnz     short loc_180009EC0
0x180009eb6  xor     eax, eax
0x180009eb8  cmp     [rcx+0Ch], eax
0x180009ebb  cmovz   rax, rcx
0x180009ebf  retn
0x180009ec0  xor     eax, eax
0x180009ec2  retn
```
