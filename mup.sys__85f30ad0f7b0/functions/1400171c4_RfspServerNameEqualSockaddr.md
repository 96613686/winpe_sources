# RfspServerNameEqualSockaddr

- ea: `0x1400171c4`
- end: `0x14001722f`
- name: `RfspServerNameEqualSockaddr`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140017f50`
- `0x140018570`
- `0x14001a920`
- `0x14001e9d0`

## callees

- `0x1400171c4`

## pseudocode

```c
bool __fastcall RfspServerNameEqualSockaddr(__int64 a1, __int64 a2)
{
  __int16 *v2; // rcx
  __int64 v3; // rdx
  __int16 v4; // ax
  __int64 v5; // r8

  if ( *(_QWORD *)(a1 + 16) == *(_QWORD *)(a2 + 16) )
  {
    v2 = *(__int16 **)(a1 + 8);
    v3 = *(_QWORD *)(a2 + 8);
    v4 = *v2;
    if ( *v2 == *(_WORD *)v3 )
    {
      if ( v4 == 2 )
      {
        if ( *((_DWORD *)v2 + 1) == *(_DWORD *)(v3 + 4) )
          return v2[1] == *(_WORD *)(v3 + 2);
      }
      else if ( v4 == 23 )
      {
        v5 = *((_QWORD *)v2 + 1) - *(_QWORD *)(v3 + 8);
        if ( !v5 )
          v5 = *((_QWORD *)v2 + 2) - *(_QWORD *)(v3 + 16);
        if ( !v5 && v2[1] == *(_WORD *)(v3 + 2) && *((_DWORD *)v2 + 6) == *(_DWORD *)(v3 + 24) )
          return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400171c4  mov     rax, [rdx+10h]
0x1400171c8  cmp     [rcx+10h], rax
0x1400171cc  jnz     short loc_14001722C
0x1400171ce  mov     rcx, [rcx+8]
0x1400171d2  mov     rdx, [rdx+8]
0x1400171d6  movzx   eax, word ptr [rcx]
0x1400171d9  cmp     ax, [rdx]
0x1400171dc  jnz     short loc_14001722C
0x1400171de  cmp     ax, 2
0x1400171e2  jz      short loc_140017217
0x1400171e4  cmp     ax, 17h
0x1400171e8  jnz     short loc_14001722C
0x1400171ea  mov     r8, [rcx+8]
0x1400171ee  sub     r8, [rdx+8]
0x1400171f2  jnz     short loc_1400171FC
0x1400171f4  mov     r8, [rcx+10h]
0x1400171f8  sub     r8, [rdx+10h]
0x1400171fc  test    r8, r8
0x1400171ff  jnz     short loc_14001722C
0x140017201  movzx   eax, word ptr [rdx+2]
0x140017205  cmp     [rcx+2], ax
0x140017209  jnz     short loc_14001722C
0x14001720b  mov     eax, [rdx+18h]
0x14001720e  cmp     [rcx+18h], eax
0x140017211  jnz     short loc_14001722C
0x140017213  mov     al, 1
0x140017215  retn
0x140017217  mov     eax, [rdx+4]
0x14001721a  cmp     [rcx+4], eax
0x14001721d  jnz     short loc_14001722C
0x14001721f  movzx   eax, word ptr [rdx+2]
0x140017223  cmp     [rcx+2], ax
0x140017227  setz    al
0x14001722a  retn
0x14001722c  xor     al, al
0x14001722e  retn
```
