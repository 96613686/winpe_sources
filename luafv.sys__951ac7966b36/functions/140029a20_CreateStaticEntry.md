# CreateStaticEntry

- ea: `0x140029a20`
- end: `0x140029b27`
- name: `CreateStaticEntry`
- size: `263`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140029784`

## callees

- `0x14001bab0`
- `0x14001d930`
- `0x140029a20`

## pseudocode

```c
__int64 __fastcall CreateStaticEntry(__int64 a1)
{
  __int128 *v2; // rdx
  __int64 result; // rax
  __int64 v4; // rbx
  char v5; // al
  char v6; // cl
  unsigned __int8 v7; // cl
  __int64 v8; // rcx
  int TableNode; // esi
  char v10; // al
  char v11; // dl
  unsigned __int8 v12; // dl
  _OWORD v13[5]; // [rsp+20h] [rbp-58h] BYREF

  v2 = &StaticEntryRoots[*(int *)(a1 + 16)];
  v13[0] = 0;
  result = LuafvFindTableNode(0, v2, 2, v13);
  if ( (int)result >= 0 )
  {
    v4 = *(_QWORD *)&v13[0];
    if ( *(_WORD *)a1 )
    {
      TableNode = LuafvFindTableNode(*(_QWORD *)&v13[0], a1, 2, v13);
      LuafvDereferenceTableNodeEx(v4, 0, 0);
      if ( TableNode < 0 )
        return (unsigned int)TableNode;
      v8 = *(_QWORD *)&v13[0];
      *(_BYTE *)(*(_QWORD *)&v13[0] + 28LL) = 0;
      v10 = *(_BYTE *)(a1 + 20) & 1;
      *(_BYTE *)(v8 + 28) = v10;
      v11 = *(_BYTE *)(a1 + 21);
      *(_WORD *)(v8 + 30) |= 2u;
      v12 = v10 | (8 * (v11 & 1));
      *(_BYTE *)(v8 + 28) = v12;
      if ( !v10 || v12 >= 8u )
        *(_WORD *)(*(_QWORD *)(v8 + 32) + 30LL) |= 0x100u;
    }
    else
    {
      *(_BYTE *)(*(_QWORD *)&v13[0] + 28LL) = 0;
      v5 = *(_BYTE *)(a1 + 20) & 1;
      *(_BYTE *)(v4 + 28) = v5;
      v6 = *(_BYTE *)(a1 + 21);
      *(_WORD *)(v4 + 30) |= 2u;
      v7 = v5 | (8 * (v6 & 1));
      *(_BYTE *)(v4 + 28) = v7;
      if ( !v5 || v7 >= 8u )
        *(_WORD *)(*(_QWORD *)(v4 + 32) + 30LL) |= 0x100u;
      v8 = v4;
    }
    LuafvDereferenceTableNodeEx(v8, 0, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140029a20  push    rbx
0x140029a22  push    rbp
0x140029a23  push    rsi
0x140029a24  push    rdi
0x140029a25  push    r14
0x140029a27  sub     rsp, 50h
0x140029a2b  movsxd  rdx, dword ptr [rcx+10h]
0x140029a2f  lea     rax, StaticEntryRoots
0x140029a36  shl     rdx, 4
0x140029a3a  lea     r9, [rsp+78h+var_58]
0x140029a3f  mov     rdi, rcx
0x140029a42  xorps   xmm0, xmm0
0x140029a45  mov     r14d, 2
0x140029a4b  add     rdx, rax
0x140029a4e  mov     r8d, r14d
0x140029a51  xor     ecx, ecx
0x140029a53  movups  [rsp+78h+var_58], xmm0
0x140029a58  call    LuafvFindTableNode
0x140029a5d  xor     ebp, ebp
0x140029a5f  test    eax, eax
0x140029a61  js      loc_140029B1B
0x140029a67  mov     rbx, qword ptr [rsp+78h+var_58]
0x140029a6c  cmp     [rdi], bp
0x140029a6f  jnz     short loc_140029AAB
0x140029a71  mov     [rbx+1Ch], bpl
0x140029a75  mov     al, [rdi+14h]
0x140029a78  and     al, 1
0x140029a7a  mov     [rbx+1Ch], al
0x140029a7d  mov     cl, [rdi+15h]
0x140029a80  or      [rbx+1Eh], r14w
0x140029a85  and     cl, 1
0x140029a88  shl     cl, 3
0x140029a8b  or      cl, al
0x140029a8d  mov     [rbx+1Ch], cl
0x140029a90  test    al, al
0x140029a92  jz      short loc_140029A99
0x140029a94  cmp     cl, 8
0x140029a97  jb      short loc_140029AA6
0x140029a99  mov     rax, [rbx+20h]
0x140029a9d  mov     edx, 100h
0x140029aa2  or      [rax+1Eh], dx
0x140029aa6  mov     rcx, rbx
0x140029aa9  jmp     short loc_140029B0F
0x140029aab  lea     r9, [rsp+78h+var_58]
0x140029ab0  mov     r8d, r14d
0x140029ab3  mov     rdx, rdi
0x140029ab6  mov     rcx, rbx
0x140029ab9  call    LuafvFindTableNode
0x140029abe  xor     r8d, r8d
0x140029ac1  xor     edx, edx
0x140029ac3  mov     rcx, rbx
0x140029ac6  mov     esi, eax
0x140029ac8  call    LuafvDereferenceTableNodeEx
0x140029acd  test    esi, esi
0x140029acf  jns     short loc_140029AD5
0x140029ad1  mov     eax, esi
0x140029ad3  jmp     short loc_140029B1B
0x140029ad5  mov     rcx, qword ptr [rsp+78h+var_58]
0x140029ada  mov     [rcx+1Ch], bpl
0x140029ade  mov     al, [rdi+14h]
0x140029ae1  and     al, 1
0x140029ae3  mov     [rcx+1Ch], al
0x140029ae6  mov     dl, [rdi+15h]
0x140029ae9  or      [rcx+1Eh], r14w
0x140029aee  and     dl, 1
0x140029af1  shl     dl, 3
0x140029af4  or      dl, al
0x140029af6  mov     [rcx+1Ch], dl
0x140029af9  test    al, al
0x140029afb  jz      short loc_140029B02
0x140029afd  cmp     dl, 8
0x140029b00  jb      short loc_140029B0F
0x140029b02  mov     rax, [rcx+20h]
0x140029b06  mov     edx, 100h
0x140029b0b  or      [rax+1Eh], dx
0x140029b0f  xor     r8d, r8d
0x140029b12  xor     edx, edx
0x140029b14  call    LuafvDereferenceTableNodeEx
0x140029b19  xor     eax, eax
0x140029b1b  add     rsp, 50h
0x140029b1f  pop     r14
0x140029b21  pop     rdi
0x140029b22  pop     rsi
0x140029b23  pop     rbp
0x140029b24  pop     rbx
0x140029b25  retn
```
