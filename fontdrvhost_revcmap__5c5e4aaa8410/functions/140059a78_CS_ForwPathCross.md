# CS_ForwPathCross

- ea: `0x140059a78`
- end: `0x140059a9e`
- name: `CS_ForwPathCross`
- size: `38`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140059324`
- `0x140059518`
- `0x140059734`
- `0x1400597e8`
- `0x1400598dc`
- `0x1400599b0`
- `0x140064a58`
- `0x140064ea4`
- `0x14006a71c`
- `0x14006a978`
- `0x14006ab90`
- `0x14006b1bc`
- `0x14008da34`

## callees

- `0x140059a78`

## pseudocode

```c
__int64 __fastcall CS_ForwPathCross(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rcx

  for ( result = a1 + 24; (*(_WORD *)result & 0x2000) != 0; result += v2 )
  {
    if ( (*(_WORD *)result & 0x1000) != 0 )
      v2 = *(int *)(result + 16);
    else
      v2 = 24;
  }
  return result;
}

```

## disassembly

```asm
0x140059a78  lea     rax, [rcx+18h]
0x140059a7c  jmp     short loc_140059A8D
0x140059a7e  bt      cx, 0Ch
0x140059a83  jb      short loc_140059A98
0x140059a85  mov     ecx, 18h
0x140059a8a  add     rax, rcx
0x140059a8d  movzx   ecx, word ptr [rax]
0x140059a90  bt      cx, 0Dh
0x140059a95  jb      short loc_140059A7E
0x140059a97  retn
0x140059a98  movsxd  rcx, dword ptr [rax+10h]
0x140059a9c  jmp     short loc_140059A8A
```
