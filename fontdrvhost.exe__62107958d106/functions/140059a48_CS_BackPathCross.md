# CS_BackPathCross

- ea: `0x140059a48`
- end: `0x140059a70`
- name: `CS_BackPathCross`
- size: `40`
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

- `0x140059a48`

## pseudocode

```c
__int64 __fastcall CS_BackPathCross(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rcx

  for ( result = a1 - 24; (*(_WORD *)result & 0x2000) != 0; result += v2 )
  {
    if ( (*(_WORD *)result & 0x1000) != 0 )
      v2 = *(int *)(result + 20);
    else
      v2 = -24;
  }
  return result;
}

```

## disassembly

```asm
0x140059a48  lea     rax, [rcx-18h]
0x140059a4c  jmp     short loc_140059A5C
0x140059a4e  bt      cx, 0Ch
0x140059a53  jnb     short loc_140059A67
0x140059a55  movsxd  rcx, dword ptr [rax+14h]
0x140059a59  add     rax, rcx
0x140059a5c  movzx   ecx, word ptr [rax]
0x140059a5f  bt      cx, 0Dh
0x140059a64  jb      short loc_140059A4E
0x140059a66  retn
0x140059a67  mov     rcx, 0FFFFFFFFFFFFFFE8h
0x140059a6e  jmp     short loc_140059A59
```
