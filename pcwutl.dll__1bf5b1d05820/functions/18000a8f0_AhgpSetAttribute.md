# AhgpSetAttribute

- ea: `0x18000a8f0`
- end: `0x18000a964`
- name: `AhgpSetAttribute`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009cdc`
- `0x180009fe8`
- `0x18000a208`

## callees

- `0x18000a8f0`

## pseudocode

```c
__int64 __fastcall AhgpSetAttribute(__int64 a1, unsigned __int16 a2, _DWORD *a3)
{
  int v3; // r9d
  unsigned int v4; // r10d

  v3 = *(_DWORD *)(a1 + 4);
  v4 = 1;
  if ( (v3 & 1) == 0 )
  {
    if ( a3 )
    {
      switch ( dword_18001E644[2 * a2] )
      {
        case 16384:
          *(_DWORD *)(a1 + 8) = *a3;
          break;
        case 20480:
          *(_QWORD *)(a1 + 8) = *(_QWORD *)a3;
          break;
        case 24576:
          *(_QWORD *)(a1 + 8) = a3;
          break;
        default:
          return 0;
      }
      *(_WORD *)a1 = a2;
      *(_DWORD *)(a1 + 4) = v3 | 1;
      return v4;
    }
    *(_DWORD *)(a1 + 4) = v3 & 0xFFFFFFFC | 2;
  }
  return v4;
}

```

## disassembly

```asm
0x18000a8f0  mov     r9d, [rcx+4]
0x18000a8f4  mov     r10d, 1
0x18000a8fa  mov     r11, rcx
0x18000a8fd  test    r10b, r9b
0x18000a900  jnz     short loc_18000A960
0x18000a902  test    r8, r8
0x18000a905  jnz     short loc_18000A915
0x18000a907  and     r9d, 0FFFFFFFEh
0x18000a90b  or      r9d, 2
0x18000a90f  mov     [rcx+4], r9d
0x18000a913  jmp     short loc_18000A960
0x18000a915  movzx   eax, dx
0x18000a918  lea     rcx, dword_18001E644
0x18000a91f  cmp     dword ptr [rcx+rax*8], 4000h
0x18000a926  jz      short loc_18000A94E
0x18000a928  cmp     dword ptr [rcx+rax*8], 5000h
0x18000a92f  jz      short loc_18000A945
0x18000a931  cmp     dword ptr [rcx+rax*8], 6000h
0x18000a938  jz      short loc_18000A93F
0x18000a93a  xor     r10d, r10d
0x18000a93d  jmp     short loc_18000A960
0x18000a93f  mov     [r11+8], r8
0x18000a943  jmp     short loc_18000A955
0x18000a945  mov     rax, [r8]
0x18000a948  mov     [r11+8], rax
0x18000a94c  jmp     short loc_18000A955
0x18000a94e  mov     ecx, [r8]
0x18000a951  mov     [r11+8], ecx
0x18000a955  or      r9d, r10d
0x18000a958  mov     [r11], dx
0x18000a95c  mov     [r11+4], r9d
0x18000a960  mov     eax, r10d
0x18000a963  retn
```
