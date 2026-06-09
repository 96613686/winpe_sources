# LsapFindRegisteredInterface

- ea: `0x14000362c`
- end: `0x14000364c`
- name: `LsapFindRegisteredInterface`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400034a0`
- `0x140003c04`

## callees

- `0x14000362c`

## pseudocode

```c
__int64 __fastcall LsapFindRegisteredInterface(int a1)
{
  __int64 result; // rax

  for ( result = gLsapIfList; (__int64 *)result != &gLsapIfList; result = *(_QWORD *)result )
  {
    if ( *(_DWORD *)(result + 16) == a1 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x14000362c  mov     rax, cs:gLsapIfList
0x140003633  lea     rdx, gLsapIfList
0x14000363a  cmp     rax, rdx
0x14000363d  jz      short loc_140003649
0x14000363f  cmp     [rax+10h], ecx
0x140003642  jz      short locret_14000364B
0x140003644  mov     rax, [rax]
0x140003647  jmp     short loc_140003633
0x140003649  xor     eax, eax
0x14000364b  retn
```
