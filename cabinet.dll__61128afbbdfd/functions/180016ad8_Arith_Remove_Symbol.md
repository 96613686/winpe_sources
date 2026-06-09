# Arith_Remove_Symbol

- ea: `0x180016ad8`
- end: `0x180016bed`
- name: `Arith_Remove_Symbol`
- size: `277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016288`

## callees

- `0x180016ad8`

## pseudocode

```c
bool __fastcall Arith_Remove_Symbol(__int64 a1, unsigned __int16 *a2)
{
  int v2; // r11d
  unsigned int v3; // r9d
  int v5; // r8d
  unsigned int v6; // eax
  __int16 v7; // bx
  _WORD *v8; // rdx
  int v9; // r8d
  bool result; // al
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  char *v14; // rax

  v2 = *(unsigned __int16 *)(a1 + 332);
  v3 = a2[2];
  v5 = *(unsigned __int16 *)(a1 + 334) - v2 + 1;
  v6 = v5 * *a2;
  v7 = v2 + v5 * (unsigned int)a2[1] / v3 - 1;
  *(_WORD *)(a1 + 334) = v7;
  v8 = (_WORD *)(a1 + 336);
  v9 = v2 + v6 / v3;
  *(_WORD *)(a1 + 332) = v9;
  while ( ((v9 ^ v7) & 0x8000u) == 0 )
  {
LABEL_5:
    *v8 *= 2;
    v11 = *(_DWORD *)(a1 + 32);
    v7 = (2 * v7) | 1;
    LOWORD(v9) = 2 * v9;
    *(_WORD *)(a1 + 334) = v7;
    *(_WORD *)(a1 + 332) = v9;
    if ( v11 )
    {
      *(_DWORD *)(a1 + 36) *= 2;
      v12 = *(_DWORD *)(a1 + 36);
      *(_DWORD *)(a1 + 32) = v11 - 1;
LABEL_9:
      if ( (v12 & 0x100) != 0 )
        *v8 |= 1u;
    }
    else
    {
      v13 = *(_DWORD *)(a1 + 44);
      if ( v13 )
      {
        *(_DWORD *)(a1 + 32) = 7;
        *(_DWORD *)(a1 + 44) = v13 - 1;
        v14 = *(char **)(a1 + 48);
        v12 = 2 * *v14;
        *(_QWORD *)(a1 + 48) = v14 + 1;
        *(_DWORD *)(a1 + 36) = v12;
        goto LABEL_9;
      }
      *(_DWORD *)(a1 + 40) = 1;
    }
  }
  result = (v9 & 0x4000) != 0;
  if ( (v7 & 0x4000) == 0 && result )
  {
    *v8 ^= 0x4000u;
    LOWORD(v9) = v9 & 0x3FFF;
    v7 |= 0x4000u;
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x180016ad8  push    rbx
0x180016ada  push    rsi
0x180016adb  push    rdi
0x180016adc  movzx   eax, word ptr [rdx+2]
0x180016ae0  mov     r10, rdx
0x180016ae3  movzx   r11d, word ptr [rcx+14Ch]
0x180016aeb  mov     esi, 1
0x180016af0  movzx   r9d, word ptr [rdx+4]
0x180016af5  mov     rdi, rcx
0x180016af8  movzx   r8d, word ptr [rcx+14Eh]
0x180016b00  xor     edx, edx
0x180016b02  sub     r8d, r11d
0x180016b05  inc     r8d
0x180016b08  imul    eax, r8d
0x180016b0c  div     r9d
0x180016b0f  xor     edx, edx
0x180016b11  lea     ebx, [r11+rax]
0x180016b15  movzx   eax, word ptr [r10]
0x180016b19  imul    eax, r8d
0x180016b1d  lea     r10d, [rsi+0Dh]
0x180016b21  sub     bx, si
0x180016b24  mov     [rcx+14Eh], bx
0x180016b2b  div     r9d
0x180016b2e  lea     rdx, [rcx+150h]
0x180016b35  lea     r8d, [r11+rax]
0x180016b39  mov     r11d, 4000h
0x180016b3f  mov     [rcx+14Ch], r8w
0x180016b47  movzx   eax, bx
0x180016b4a  xor     ax, r8w
0x180016b4e  jge     short loc_180016B79
0x180016b50  bt      bx, r10w
0x180016b55  setnb   cl
0x180016b58  bt      r8w, r10w
0x180016b5d  setb    al
0x180016b60  test    al, cl
0x180016b62  jz      loc_180016BE9
0x180016b68  xor     [rdx], r11w
0x180016b6c  mov     eax, 3FFFh
0x180016b71  and     r8w, ax
0x180016b75  or      bx, r11w
0x180016b79  shl     word ptr [rdx], 1
0x180016b7c  add     bx, bx
0x180016b7f  mov     eax, [rdi+20h]
0x180016b82  or      bx, si
0x180016b85  add     r8w, r8w
0x180016b89  mov     [rdi+14Eh], bx
0x180016b90  mov     [rdi+14Ch], r8w
0x180016b98  test    eax, eax
0x180016b9a  jz      short loc_180016BA9
0x180016b9c  dec     eax
0x180016b9e  shl     dword ptr [rdi+24h], 1
0x180016ba1  mov     ecx, [rdi+24h]
0x180016ba4  mov     [rdi+20h], eax
0x180016ba7  jmp     short loc_180016BCF
0x180016ba9  mov     eax, [rdi+2Ch]
0x180016bac  test    eax, eax
0x180016bae  jz      short loc_180016BE1
0x180016bb0  dec     eax
0x180016bb2  mov     dword ptr [rdi+20h], 7
0x180016bb9  mov     [rdi+2Ch], eax
0x180016bbc  mov     rax, [rdi+30h]
0x180016bc0  movsx   ecx, byte ptr [rax]
0x180016bc3  inc     rax
0x180016bc6  add     ecx, ecx
0x180016bc8  mov     [rdi+30h], rax
0x180016bcc  mov     [rdi+24h], ecx
0x180016bcf  bt      ecx, 8
0x180016bd3  jnb     loc_180016B47
0x180016bd9  or      [rdx], si
0x180016bdc  jmp     loc_180016B47
0x180016be1  mov     [rdi+28h], esi
0x180016be4  jmp     loc_180016B47
0x180016be9  pop     rdi
0x180016bea  pop     rsi
0x180016beb  pop     rbx
0x180016bec  retn
```
