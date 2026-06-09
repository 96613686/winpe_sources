# createCollation

- ea: `0x140026634`
- end: `0x1400267b1`
- name: `createCollation`
- size: `381`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14003bbec`
- `0x140088cc0`
- `0x140088da0`

## callees

- `0x140026634`
- `0x14002c1b8`
- `0x140056074`
- `0x140056170`
- `0x14005622c`
- `0x14005a574`
- `0x140063280`
- `0x1400a8010`

## string_xrefs

- `0x1400266b4`: `unable to delete/modify collation sequence due to active statements`

## pseudocode

```c
__int64 __fastcall createCollation(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v7; // rbp
  __int64 v8; // r12
  int v10; // edi
  __int64 v12; // r8
  __int64 CollSeq; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r13
  __int64 v17; // r14
  __int64 v18; // r15
  void (__fastcall *v19)(_QWORD); // rax
  __int64 v20; // rax
  bool v21; // zf

  v7 = a4;
  v8 = a2;
  v10 = a3;
  if ( a3 == 4 || a3 == 8 )
  {
    v10 = 2;
  }
  else if ( (unsigned int)a3 - 1 > 2 )
  {
    return sqlite3MisuseError(179132);
  }
  v12 = a2;
  LOBYTE(a2) = v10;
  CollSeq = sqlite3FindCollSeq(a1, a2, v12, 0);
  v16 = CollSeq;
  if ( CollSeq && *(_QWORD *)(CollSeq + 24) )
  {
    if ( *(_DWORD *)(a1 + 216) )
    {
      sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify collation sequence due to active statements", v15);
      return 5;
    }
    sqlite3ExpirePreparedStatements(a1, 0);
    if ( (*(_BYTE *)(v16 + 8) & 0xF7) == v10 )
    {
      v17 = 0;
      v18 = *(_QWORD *)(findElementWithHash(a1 + 624, v8, 0) + 16);
      do
      {
        if ( *(_BYTE *)(v18 + 40 * v17 + 8) == *(_BYTE *)(v16 + 8) )
        {
          v19 = *(void (__fastcall **)(_QWORD))(v18 + 40 * v17 + 32);
          if ( v19 )
            v19(*(_QWORD *)(v18 + 40 * v17 + 16));
          *(_QWORD *)(v18 + 40 * v17 + 24) = 0;
        }
        ++v17;
      }
      while ( v17 != 3 );
      v7 = a4;
    }
  }
  LOBYTE(v14) = v10;
  v20 = sqlite3FindCollSeq(a1, v14, v8, 1);
  if ( !v20 )
    return 7;
  *(_QWORD *)(v20 + 24) = a5;
  *(_QWORD *)(v20 + 32) = a6;
  *(_QWORD *)(v20 + 16) = v7;
  *(_BYTE *)(v20 + 8) = v10 | a3 & 8;
  v21 = *(_QWORD *)(a1 + 400) == 0;
  *(_DWORD *)(a1 + 80) = 0;
  if ( v21 )
    *(_DWORD *)(a1 + 84) = -1;
  else
    sqlite3ErrorFinish(a1, 0);
  return 0;
}

```

## disassembly

```asm
0x140026634  mov     [rsp+arg_18], r9
0x140026639  push    rbx
0x14002663a  push    rbp
0x14002663b  push    rsi
0x14002663c  push    rdi
0x14002663d  push    r12
0x14002663f  push    r13
0x140026641  push    r14
0x140026643  push    r15
0x140026645  sub     rsp, 28h
0x140026649  movzx   esi, r8b
0x14002664d  mov     rbp, r9
0x140026650  mov     r12, rdx
0x140026653  mov     rbx, rcx
0x140026656  mov     edi, esi
0x140026658  cmp     esi, 4
0x14002665b  jz      short loc_140026679
0x14002665d  cmp     esi, 8
0x140026660  jz      short loc_140026679
0x140026662  lea     eax, [rsi-1]
0x140026665  cmp     eax, 2
0x140026668  jbe     short loc_14002667E
0x14002666a  mov     ecx, 2BBBCh
0x14002666f  call    sqlite3MisuseError
0x140026674  jmp     loc_1400267A0
0x140026679  mov     edi, 2
0x14002667e  xor     r9d, r9d
0x140026681  mov     r8, r12
0x140026684  mov     dl, dil
0x140026687  call    sqlite3FindCollSeq
0x14002668c  mov     r13, rax
0x14002668f  test    rax, rax
0x140026692  jz      loc_140026732
0x140026698  cmp     qword ptr [rax+18h], 0
0x14002669d  jz      loc_140026732
0x1400266a3  cmp     dword ptr [rbx+0D8h], 0
0x1400266aa  mov     rcx, rbx
0x1400266ad  jz      short loc_1400266C9
0x1400266af  mov     edi, 5
0x1400266b4  lea     r8, aUnableToDelete; "unable to delete/modify collation seque"...
0x1400266bb  mov     edx, edi
0x1400266bd  call    sqlite3ErrorWithMsg
0x1400266c2  mov     eax, edi
0x1400266c4  jmp     loc_1400267A0
0x1400266c9  xor     edx, edx
0x1400266cb  call    sqlite3ExpirePreparedStatements
0x1400266d0  movzx   eax, byte ptr [r13+8]
0x1400266d5  and     eax, 0FFFFFFF7h
0x1400266d8  cmp     eax, edi
0x1400266da  jnz     short loc_140026732
0x1400266dc  lea     rcx, [rbx+270h]
0x1400266e3  xor     r8d, r8d
0x1400266e6  mov     rdx, r12
0x1400266e9  call    findElementWithHash
0x1400266ee  xor     r14d, r14d
0x1400266f1  mov     r15, [rax+10h]
0x1400266f5  mov     al, [r13+8]
0x1400266f9  lea     rbp, [r14+r14*4]
0x1400266fd  cmp     [r15+rbp*8+8], al
0x140026702  jnz     short loc_140026721
0x140026704  mov     rax, [r15+rbp*8+20h]
0x140026709  test    rax, rax
0x14002670c  jz      short loc_140026718
0x14002670e  mov     rcx, [r15+rbp*8+10h]
0x140026713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026718  mov     qword ptr [r15+rbp*8+18h], 0
0x140026721  inc     r14
0x140026724  cmp     r14, 3
0x140026728  jnz     short loc_1400266F5
0x14002672a  mov     rbp, [rsp+68h+arg_18]
0x140026732  mov     r9d, 1
0x140026738  mov     r8, r12
0x14002673b  mov     dl, dil
0x14002673e  mov     rcx, rbx
0x140026741  call    sqlite3FindCollSeq
0x140026746  mov     rcx, rax
0x140026749  test    rax, rax
0x14002674c  jnz     short loc_140026753
0x14002674e  lea     eax, [rcx+7]
0x140026751  jmp     short loc_1400267A0
0x140026753  mov     rax, [rsp+68h+arg_20]
0x14002675b  and     sil, 8
0x14002675f  mov     [rcx+18h], rax
0x140026763  or      sil, dil
0x140026766  mov     rax, [rsp+68h+arg_28]
0x14002676e  mov     [rcx+20h], rax
0x140026772  mov     [rcx+10h], rbp
0x140026776  mov     [rcx+8], sil
0x14002677a  cmp     qword ptr [rbx+190h], 0
0x140026782  mov     dword ptr [rbx+50h], 0
0x140026789  jz      short loc_140026797
0x14002678b  xor     edx, edx
0x14002678d  mov     rcx, rbx
0x140026790  call    sqlite3ErrorFinish
0x140026795  jmp     short loc_14002679E
0x140026797  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x14002679e  xor     eax, eax
0x1400267a0  add     rsp, 28h
0x1400267a4  pop     r15
0x1400267a6  pop     r14
0x1400267a8  pop     r13
0x1400267aa  pop     r12
0x1400267ac  pop     rdi
0x1400267ad  pop     rsi
0x1400267ae  pop     rbp
0x1400267af  pop     rbx
0x1400267b0  retn
```
