# CAVLTree::DelNode(void *)

- ea: `0x1400033f0`
- end: `0x1400035b2`
- name: `?DelNode@CAVLTree@@QEAAXPEAX@Z`
- size: `450`
- prototype: `void __fastcall(CAVLTree *__hidden this, void *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140010568`
- `0x140010984`
- `0x140010e2c`
- `0x140020300`
- `0x14002054c`

## callees

- `0x1400010a4`
- `0x1400032ac`
- `0x1400033f0`
- `0x140003698`
- `0x140024bf0`

## pseudocode

```c
void __fastcall CAVLTree::DelNode(CAVLTree *this, void *a2)
{
  struct AVLNODE *v4; // rbx
  _QWORD *v5; // rdx
  _WORD *v6; // rcx
  _QWORD *v7; // rcx
  struct AVLNODE **v8; // rsi
  struct AVLNODE **v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rcx
  unsigned __int8 v15; // al
  unsigned __int8 v16; // cl
  __int64 v17; // rcx
  unsigned __int8 v18; // al
  unsigned __int8 v19; // cl
  struct AVLNODE *v20; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)this )
    return;
  v20 = 0;
  if ( (unsigned int)CAVLTree::Search(this, a2, &v20) )
    return;
  v4 = v20;
  if ( !(*((unsigned int (__fastcall **)(void *, _QWORD, _QWORD))this + 1))(a2, *((_QWORD *)v20 + 3), 0) )
    return;
  v5 = *(_QWORD **)this;
  if ( v4 == *(struct AVLNODE **)this && !v5[1] && !v5[2] )
  {
    operator delete(*(void **)this);
    *(_QWORD *)this = 0;
    return;
  }
  v6 = (_WORD *)*((_QWORD *)v4 + 2);
  if ( v6 )
  {
    *((_WORD *)v4 + 17) &= ~1u;
    if ( *((_QWORD *)v6 + 1) )
    {
      do
      {
        v6[17] |= 1u;
        v6 = (_WORD *)*((_QWORD *)v6 + 1);
      }
      while ( *((_QWORD *)v6 + 1) );
      *((_QWORD *)v4 + 3) = *((_QWORD *)v6 + 3);
      v4 = *(struct AVLNODE **)v6;
      v20 = v4;
      v7 = (_QWORD *)*((_QWORD *)v4 + 1);
      v8 = (struct AVLNODE **)v7[2];
      operator delete(v7);
      *((_QWORD *)v4 + 1) = v8;
      if ( v8 )
        *v8 = v4;
      goto LABEL_24;
    }
    *((_QWORD *)v4 + 3) = *((_QWORD *)v6 + 3);
    v9 = (struct AVLNODE **)*((_QWORD *)v6 + 2);
    *((_QWORD *)v4 + 2) = v9;
    if ( v9 )
      *v9 = v4;
  }
  else
  {
    v10 = *(_QWORD *)v4;
    v20 = (struct AVLNODE *)v10;
    v4 = (struct AVLNODE *)v10;
    if ( !v10 )
    {
      v11 = (_QWORD *)v5[1];
      *(_QWORD *)this = v11;
      *v11 = 0;
      operator delete(v5);
      return;
    }
    if ( (*(_BYTE *)(v10 + 34) & 1) != 0 )
    {
      v12 = *(_QWORD **)(v10 + 8);
      v13 = (_QWORD *)v12[1];
      *(_QWORD *)(v10 + 8) = v13;
    }
    else
    {
      v12 = *(_QWORD **)(v10 + 16);
      v13 = (_QWORD *)v12[1];
      *(_QWORD *)(v10 + 16) = v13;
    }
    if ( v13 )
      *v13 = v10;
    v6 = v12;
  }
  operator delete(v6);
  do
  {
LABEL_24:
    if ( (*((_BYTE *)v4 + 34) & 1) != 0 )
    {
      v14 = *((_QWORD *)v4 + 1);
      if ( v14 )
      {
        v15 = *(_BYTE *)(v14 + 33);
        v16 = *(_BYTE *)(v14 + 32);
        if ( v16 <= v15 )
          v16 = v15;
        *((_BYTE *)v4 + 32) = v16 + 1;
      }
      else
      {
        *((_BYTE *)v4 + 32) = 0;
      }
    }
    else
    {
      v17 = *((_QWORD *)v4 + 2);
      if ( v17 )
      {
        v18 = *(_BYTE *)(v17 + 33);
        v19 = *(_BYTE *)(v17 + 32);
        if ( v19 <= v18 )
          v19 = v18;
        *((_BYTE *)v4 + 33) = v19 + 1;
      }
      else
      {
        *((_BYTE *)v4 + 33) = 0;
      }
    }
    CAVLTree::Balance(this, &v20);
    v4 = *(struct AVLNODE **)v20;
    v20 = v4;
  }
  while ( v4 );
}

```

## disassembly

```asm
0x1400033f0  mov     rax, rsp
0x1400033f3  mov     [rax+10h], rbx
0x1400033f7  mov     [rax+18h], rsi
0x1400033fb  push    rdi
0x1400033fc  sub     rsp, 20h
0x140003400  cmp     qword ptr [rcx], 0
0x140003404  mov     rsi, rdx
0x140003407  mov     rdi, rcx
0x14000340a  jz      loc_1400035A1
0x140003410  lea     r8, [rax+8]; struct AVLNODE **
0x140003414  mov     qword ptr [rax+8], 0
0x14000341c  call    ?Search@CAVLTree@@AEAAHPEAXAEAPEAUAVLNODE@@@Z; CAVLTree::Search(void *,AVLNODE * &)
0x140003421  test    eax, eax
0x140003423  jnz     loc_1400035A1
0x140003429  mov     rbx, [rsp+28h+arg_0]
0x14000342e  xor     r8d, r8d
0x140003431  mov     rax, [rdi+8]
0x140003435  mov     rcx, rsi
0x140003438  mov     rdx, [rbx+18h]
0x14000343c  call    _guard_dispatch_icall
0x140003441  test    eax, eax
0x140003443  jz      loc_1400035A1
0x140003449  mov     rdx, [rdi]
0x14000344c  cmp     rbx, rdx
0x14000344f  jnz     short loc_140003473
0x140003451  cmp     qword ptr [rdx+8], 0
0x140003456  jnz     short loc_140003473
0x140003458  cmp     qword ptr [rdx+10h], 0
0x14000345d  jnz     short loc_140003473
0x14000345f  mov     rcx, rdx; void *
0x140003462  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003467  mov     qword ptr [rdi], 0
0x14000346e  jmp     loc_1400035A1
0x140003473  mov     rcx, [rbx+10h]
0x140003477  test    rcx, rcx
0x14000347a  jz      short loc_1400034E1
0x14000347c  mov     eax, 0FFFEh
0x140003481  and     [rbx+22h], ax
0x140003485  cmp     qword ptr [rcx+8], 0
0x14000348a  jz      short loc_1400034C7
0x14000348c  or      word ptr [rcx+22h], 1
0x140003491  mov     rcx, [rcx+8]
0x140003495  cmp     qword ptr [rcx+8], 0
0x14000349a  jnz     short loc_14000348C
0x14000349c  mov     rax, [rcx+18h]
0x1400034a0  mov     [rbx+18h], rax
0x1400034a4  mov     rbx, [rcx]
0x1400034a7  mov     [rsp+28h+arg_0], rbx
0x1400034ac  mov     rcx, [rbx+8]; void *
0x1400034b0  mov     rsi, [rcx+10h]
0x1400034b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400034b9  mov     [rbx+8], rsi
0x1400034bd  test    rsi, rsi
0x1400034c0  jz      short loc_140003538
0x1400034c2  mov     [rsi], rbx
0x1400034c5  jmp     short loc_140003538
0x1400034c7  mov     rax, [rcx+18h]
0x1400034cb  mov     [rbx+18h], rax
0x1400034cf  mov     rax, [rcx+10h]
0x1400034d3  mov     [rbx+10h], rax
0x1400034d7  test    rax, rax
0x1400034da  jz      short loc_140003533
0x1400034dc  mov     [rax], rbx
0x1400034df  jmp     short loc_140003533
0x1400034e1  mov     rcx, [rbx]
0x1400034e4  mov     [rsp+28h+arg_0], rcx
0x1400034e9  mov     rbx, rcx
0x1400034ec  test    rcx, rcx
0x1400034ef  jnz     short loc_140003508
0x1400034f1  mov     rax, [rdx+8]
0x1400034f5  mov     [rdi], rax
0x1400034f8  mov     [rax], rcx
0x1400034fb  mov     rcx, rdx; void *
0x1400034fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003503  jmp     loc_1400035A1
0x140003508  test    byte ptr [rcx+22h], 1
0x14000350c  jz      short loc_14000351C
0x14000350e  mov     rax, [rcx+8]
0x140003512  mov     rdx, [rax+8]
0x140003516  mov     [rcx+8], rdx
0x14000351a  jmp     short loc_140003528
0x14000351c  mov     rax, [rcx+10h]
0x140003520  mov     rdx, [rax+8]
0x140003524  mov     [rcx+10h], rdx
0x140003528  test    rdx, rdx
0x14000352b  jz      short loc_140003530
0x14000352d  mov     [rdx], rcx
0x140003530  mov     rcx, rax; void *
0x140003533  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003538  test    byte ptr [rbx+22h], 1
0x14000353c  jz      short loc_140003561
0x14000353e  mov     rcx, [rbx+8]
0x140003542  test    rcx, rcx
0x140003545  jz      short loc_14000355B
0x140003547  movzx   eax, byte ptr [rcx+21h]
0x14000354b  movzx   ecx, byte ptr [rcx+20h]
0x14000354f  cmp     cl, al
0x140003551  cmovbe  ecx, eax
0x140003554  inc     cl
0x140003556  mov     [rbx+20h], cl
0x140003559  jmp     short loc_140003582
0x14000355b  mov     byte ptr [rbx+20h], 0
0x14000355f  jmp     short loc_140003582
0x140003561  mov     rcx, [rbx+10h]
0x140003565  test    rcx, rcx
0x140003568  jz      short loc_14000357E
0x14000356a  movzx   eax, byte ptr [rcx+21h]
0x14000356e  movzx   ecx, byte ptr [rcx+20h]
0x140003572  cmp     cl, al
0x140003574  cmovbe  ecx, eax
0x140003577  inc     cl
0x140003579  mov     [rbx+21h], cl
0x14000357c  jmp     short loc_140003582
0x14000357e  mov     byte ptr [rbx+21h], 0
0x140003582  lea     rdx, [rsp+28h+arg_0]; struct AVLNODE **
0x140003587  mov     rcx, rdi; this
0x14000358a  call    ?Balance@CAVLTree@@AEAAXPEAPEAUAVLNODE@@@Z; CAVLTree::Balance(AVLNODE * *)
0x14000358f  mov     rax, [rsp+28h+arg_0]
0x140003594  mov     rbx, [rax]
0x140003597  mov     [rsp+28h+arg_0], rbx
0x14000359c  test    rbx, rbx
0x14000359f  jnz     short loc_140003538
0x1400035a1  mov     rbx, [rsp+28h+arg_8]
0x1400035a6  mov     rsi, [rsp+28h+arg_10]
0x1400035ab  add     rsp, 20h
0x1400035af  pop     rdi
0x1400035b0  retn
```
