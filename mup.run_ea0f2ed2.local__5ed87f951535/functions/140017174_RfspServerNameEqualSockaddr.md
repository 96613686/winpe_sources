# RfspServerNameEqualSockaddr

- ea: `0x140017174`
- end: `0x1400171df`
- name: `RfspServerNameEqualSockaddr`
- size: `107`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140017f00`
- `0x140018520`
- `0x14001a8d0`
- `0x14001e980`

## callees

- `0x140017174`

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
0x140017174  mov     rax, [rdx+10h]
0x140017178  cmp     [rcx+10h], rax
0x14001717c  jnz     short loc_1400171DC
0x14001717e  mov     rcx, [rcx+8]
0x140017182  mov     rdx, [rdx+8]
0x140017186  movzx   eax, word ptr [rcx]
0x140017189  cmp     ax, [rdx]
0x14001718c  jnz     short loc_1400171DC
0x14001718e  cmp     ax, 2
0x140017192  jz      short loc_1400171C7
0x140017194  cmp     ax, 17h
0x140017198  jnz     short loc_1400171DC
0x14001719a  mov     r8, [rcx+8]
0x14001719e  sub     r8, [rdx+8]
0x1400171a2  jnz     short loc_1400171AC
0x1400171a4  mov     r8, [rcx+10h]
0x1400171a8  sub     r8, [rdx+10h]
0x1400171ac  test    r8, r8
0x1400171af  jnz     short loc_1400171DC
0x1400171b1  movzx   eax, word ptr [rdx+2]
0x1400171b5  cmp     [rcx+2], ax
0x1400171b9  jnz     short loc_1400171DC
0x1400171bb  mov     eax, [rdx+18h]
0x1400171be  cmp     [rcx+18h], eax
0x1400171c1  jnz     short loc_1400171DC
0x1400171c3  mov     al, 1
0x1400171c5  retn
0x1400171c7  mov     eax, [rdx+4]
0x1400171ca  cmp     [rcx+4], eax
0x1400171cd  jnz     short loc_1400171DC
0x1400171cf  movzx   eax, word ptr [rdx+2]
0x1400171d3  cmp     [rcx+2], ax
0x1400171d7  setz    al
0x1400171da  retn
0x1400171dc  xor     al, al
0x1400171de  retn
```
