# VALIDATE_ATTR

- ea: `0x18000d2c8`
- end: `0x18000d35e`
- name: `VALIDATE_ATTR`
- size: `150`
- prototype: `char __fastcall(__int64, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d9d0`
- `0x18000de60`
- `0x18000e040`
- `0x18000eac0`
- `0x18001c788`

## callees

- `0x18000d2c8`

## pseudocode

```c
char __fastcall VALIDATE_ATTR(__int64 a1, unsigned __int64 a2)
{
  char v3; // r10
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdi
  unsigned __int64 v7; // r8
  unsigned int v8; // r9d

  v3 = 0;
  v4 = a1 + 8;
  if ( v4 <= a2 )
  {
    v5 = *(unsigned __int8 *)(a1 + 7);
    v6 = (*(_DWORD *)(a1 + 4) & 0xFF00u | (*(_DWORD *)(a1 + 4) << 16)) << 8;
    v7 = v4 + (v6 | v5 | ((unsigned __int64)*(unsigned int *)(a1 + 4) >> 8) & 0xFF00);
    if ( v7 >= v4 && v7 <= a2 )
    {
      v3 = 1;
      v8 = v6 | v5 | (*(_DWORD *)(a1 + 4) >> 8) & 0xFF00;
      if ( !(*(unsigned __int8 *)(a1 + 3)
           | (*(_DWORD *)a1 >> 8) & 0xFF00
           | ((*(_DWORD *)a1 & 0xFF00 | (*(_DWORD *)a1 << 16)) << 8)) )
      {
        if ( !v8 )
          return v3;
        return 0;
      }
      if ( v8 < 4 )
        return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000d2c8  push    rbx
0x18000d2ca  push    rsi
0x18000d2cb  push    rdi
0x18000d2cc  mov     r11, rcx
0x18000d2cf  xor     r10b, r10b
0x18000d2d2  add     rcx, 8
0x18000d2d6  cmp     rcx, rdx
0x18000d2d9  ja      short loc_18000D357
0x18000d2db  mov     r9d, [r11+4]
0x18000d2df  mov     esi, 0FF00h
0x18000d2e4  movzx   ebx, byte ptr [r11+7]
0x18000d2e9  mov     edi, r9d
0x18000d2ec  shl     edi, 10h
0x18000d2ef  mov     eax, r9d
0x18000d2f2  and     eax, esi
0x18000d2f4  mov     r8d, r9d
0x18000d2f7  shr     r8, 8
0x18000d2fb  or      edi, eax
0x18000d2fd  and     r8, rsi
0x18000d300  shl     edi, 8
0x18000d303  or      r8, rbx
0x18000d306  or      r8, rdi
0x18000d309  add     r8, rcx
0x18000d30c  cmp     r8, rcx
0x18000d30f  jb      short loc_18000D357
0x18000d311  cmp     r8, rdx
0x18000d314  ja      short loc_18000D357
0x18000d316  mov     ecx, [r11]
0x18000d319  mov     r10b, 1
0x18000d31c  shr     r9d, 8
0x18000d320  mov     edx, ecx
0x18000d322  shl     edx, 10h
0x18000d325  mov     eax, ecx
0x18000d327  and     eax, esi
0x18000d329  shr     ecx, 8
0x18000d32c  or      edx, eax
0x18000d32e  and     r9d, esi
0x18000d331  movzx   eax, byte ptr [r11+3]
0x18000d336  or      r9d, ebx
0x18000d339  shl     edx, 8
0x18000d33c  and     ecx, esi
0x18000d33e  or      edx, ecx
0x18000d340  or      r9d, edi
0x18000d343  or      edx, eax
0x18000d345  jnz     short loc_18000D34E
0x18000d347  test    r9d, r9d
0x18000d34a  jnz     short loc_18000D354
0x18000d34c  jmp     short loc_18000D357
0x18000d34e  cmp     r9d, 4
0x18000d352  jnb     short loc_18000D357
0x18000d354  xor     r10b, r10b
0x18000d357  mov     al, r10b
0x18000d35a  pop     rdi
0x18000d35b  pop     rsi
0x18000d35c  pop     rbx
0x18000d35d  retn
```
