# InsertToHandleTable

- ea: `0x1400053c4`
- end: `0x140005475`
- name: `InsertToHandleTable`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005c90`
- `0x140014884`

## callees

- `0x1400053c4`

## pseudocode

```c
__int64 __fastcall InsertToHandleTable(__int64 *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r8d
  int v7; // ecx
  bool v8; // zf
  unsigned __int16 v9; // r10
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8

  if ( !a1 )
    return 0;
  if ( (_WORD)a2 == 0xFFFF )
  {
    v5 = *((_DWORD *)a1 + 2);
    a2 = 0;
    if ( v5 )
    {
      do
      {
        if ( !*(_BYTE *)(*a1 + 24 * a2) )
          break;
        a2 = (unsigned int)(a2 + 1);
      }
      while ( (unsigned int)a2 < v5 );
      if ( (unsigned int)a2 > 0xFFFF )
        return 0;
    }
  }
  else if ( *(_BYTE *)(*a1 + 24LL * (unsigned __int16)a2) )
  {
    return 0;
  }
  v7 = (unsigned __int16)a2;
  if ( (unsigned int)(unsigned __int16)a2 >= *((_DWORD *)a1 + 2) )
    return 0;
  v8 = (*((_WORD *)a1 + 8))++ == 0xFFFF;
  v9 = *((_WORD *)a1 + 8);
  if ( v8 )
  {
    *((_WORD *)a1 + 8) = 1;
    v9 = 1;
  }
  v10 = (unsigned __int16)a2;
  v11 = *a1;
  v12 = 3 * v10;
  *(_BYTE *)(v11 + 8 * v12) = 1;
  *(_QWORD *)(v11 + 8 * v12 + 16) = v9 | (unsigned __int64)(unsigned int)(v7 << 16);
  *(_QWORD *)(v11 + 8 * v12 + 8) = a3;
  ++*((_DWORD *)a1 + 3);
  return *(_QWORD *)(v11 + 24 * v10 + 16);
}

```

## disassembly

```asm
0x1400053c4  mov     [rsp+arg_0], rbx
0x1400053c9  mov     [rsp+arg_8], rdi
0x1400053ce  mov     r11, r8
0x1400053d1  mov     r9, rcx
0x1400053d4  test    rcx, rcx
0x1400053d7  jz      short loc_14000540C
0x1400053d9  mov     edi, 0FFFFh
0x1400053de  mov     ebx, 1
0x1400053e3  cmp     dx, di
0x1400053e6  jnz     short loc_14000541A
0x1400053e8  mov     r8d, [rcx+8]
0x1400053ec  xor     edx, edx
0x1400053ee  test    r8d, r8d
0x1400053f1  jz      short loc_14000542A
0x1400053f3  mov     r10, [rcx]
0x1400053f6  lea     rcx, [rdx+rdx*2]
0x1400053fa  cmp     byte ptr [r10+rcx*8], 0
0x1400053ff  jz      short loc_140005408
0x140005401  add     edx, ebx
0x140005403  cmp     edx, r8d
0x140005406  jb      short loc_1400053F6
0x140005408  cmp     edx, edi
0x14000540a  jbe     short loc_14000542A
0x14000540c  xor     eax, eax
0x14000540e  mov     rbx, [rsp+arg_0]
0x140005413  mov     rdi, [rsp+arg_8]
0x140005418  retn
0x14000541a  movzx   eax, dx
0x14000541d  lea     rcx, [rax+rax*2]
0x140005421  mov     rax, [r9]
0x140005424  cmp     byte ptr [rax+rcx*8], 0
0x140005428  jnz     short loc_14000540C
0x14000542a  movzx   ecx, dx
0x14000542d  cmp     ecx, [r9+8]
0x140005431  jnb     short loc_14000540C
0x140005433  add     [r9+10h], bx
0x140005438  movzx   r10d, word ptr [r9+10h]
0x14000543d  jnz     short loc_140005448
0x14000543f  mov     [r9+10h], bx
0x140005444  movzx   r10d, bx
0x140005448  movzx   eax, dx
0x14000544b  mov     rdx, [r9]
0x14000544e  shl     ecx, 10h
0x140005451  lea     r8, [rax+rax*2]
0x140005455  movzx   eax, r10w
0x140005459  or      rcx, rax
0x14000545c  mov     [rdx+r8*8], bl
0x140005460  mov     [rdx+r8*8+10h], rcx
0x140005465  mov     [rdx+r8*8+8], r11
0x14000546a  add     [r9+0Ch], ebx
0x14000546e  mov     rax, [rdx+r8*8+10h]
0x140005473  jmp     short loc_14000540E
```
