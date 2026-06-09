# CDescriptor::Get(_DMUS_OBJECTDESC *)

- ea: `0x18000abec`
- end: `0x18000acfb`
- name: `?Get@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@@Z`
- size: `271`
- prototype: `void __fastcall(CDescriptor *__hidden this, struct _DMUS_OBJECTDESC *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085b0`
- `0x180008e90`
- `0x180009b20`
- `0x18000a310`
- `0x18000ae74`
- `0x18000c5d8`

## callees

- `0x18000abec`

## pseudocode

```c
void __fastcall CDescriptor::Get(CDescriptor *this, struct _DMUS_OBJECTDESC *a2)
{
  __int64 v3; // r10
  _WORD *v4; // rcx
  __int64 v5; // r9
  _WORD *v6; // rax
  _WORD *v7; // rcx
  _WORD *v8; // rcx
  _WORD *v9; // rax
  _WORD *v10; // rcx
  _WORD *v11; // rax
  __int64 v12; // r8
  _WORD *v13; // rdx
  _WORD *v14; // rcx

  if ( a2 )
  {
    v3 = 64;
    *((_DWORD *)a2 + 1) = *((_DWORD *)this + 2) & 0xFFFFF7FF;
    *(_OWORD *)((char *)a2 + 8) = *(_OWORD *)((char *)this + 12);
    *(_OWORD *)((char *)a2 + 24) = *(_OWORD *)((char *)this + 28);
    *((_QWORD *)a2 + 5) = *(_QWORD *)((char *)this + 44);
    *((_QWORD *)a2 + 6) = *(_QWORD *)((char *)this + 52);
    *((_QWORD *)a2 + 104) = *(_QWORD *)this;
    *((_QWORD *)a2 + 105) = *((_QWORD *)this + 12);
    v4 = (_WORD *)*((_QWORD *)this + 8);
    if ( v4 )
    {
      v5 = 64;
      v6 = (_WORD *)((char *)a2 + 56);
      do
      {
        if ( !*v4 )
          break;
        *v6++ = *v4++;
        --v5;
      }
      while ( v5 );
      v7 = v6 - 1;
      if ( v5 )
        v7 = v6;
      *v7 = 0;
    }
    v8 = (_WORD *)*((_QWORD *)this + 9);
    if ( v8 )
    {
      v9 = (_WORD *)((char *)a2 + 184);
      do
      {
        if ( !*v8 )
          break;
        *v9++ = *v8++;
        --v3;
      }
      while ( v3 );
      v10 = v9 - 1;
      if ( v3 )
        v10 = v9;
      *v10 = 0;
    }
    v11 = (_WORD *)*((_QWORD *)this + 10);
    if ( v11 )
    {
      v12 = 260;
      v13 = (_WORD *)((char *)a2 + 312);
      do
      {
        if ( !*v11 )
          break;
        *v13++ = *v11++;
        --v12;
      }
      while ( v12 );
      v14 = v13 - 1;
      if ( v12 )
        v14 = v13;
      *v14 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000abec  mov     [rsp+arg_0], rbx
0x18000abf1  xor     ebx, ebx
0x18000abf3  mov     r8, rcx
0x18000abf6  test    rdx, rdx
0x18000abf9  jz      loc_18000ACF5
0x18000abff  mov     eax, [rcx+8]
0x18000ac02  lea     r10d, [rbx+40h]
0x18000ac06  btr     eax, 0Bh
0x18000ac0a  mov     [rdx+4], eax
0x18000ac0d  movups  xmm0, xmmword ptr [rcx+0Ch]
0x18000ac11  movdqu  xmmword ptr [rdx+8], xmm0
0x18000ac16  movups  xmm1, xmmword ptr [rcx+1Ch]
0x18000ac1a  movdqu  xmmword ptr [rdx+18h], xmm1
0x18000ac1f  mov     rax, [rcx+2Ch]
0x18000ac23  mov     [rdx+28h], rax
0x18000ac27  mov     rax, [rcx+34h]
0x18000ac2b  mov     [rdx+30h], rax
0x18000ac2f  mov     rax, [rcx]
0x18000ac32  mov     [rdx+340h], rax
0x18000ac39  mov     rax, [rcx+60h]
0x18000ac3d  mov     [rdx+348h], rax
0x18000ac44  mov     rcx, [rcx+40h]
0x18000ac48  test    rcx, rcx
0x18000ac4b  jz      short loc_18000AC7E
0x18000ac4d  mov     r9d, r10d
0x18000ac50  lea     rax, [rdx+38h]
0x18000ac54  movzx   r11d, word ptr [rcx]
0x18000ac58  test    r11w, r11w
0x18000ac5c  jz      short loc_18000AC70
0x18000ac5e  mov     [rax], r11w
0x18000ac62  add     rcx, 2
0x18000ac66  add     rax, 2
0x18000ac6a  sub     r9, 1
0x18000ac6e  jnz     short loc_18000AC54
0x18000ac70  test    r9, r9
0x18000ac73  lea     rcx, [rax-2]
0x18000ac77  cmovnz  rcx, rax
0x18000ac7b  mov     [rcx], bx
0x18000ac7e  mov     rcx, [r8+48h]
0x18000ac82  test    rcx, rcx
0x18000ac85  jz      short loc_18000ACB8
0x18000ac87  lea     rax, [rdx+0B8h]
0x18000ac8e  movzx   r9d, word ptr [rcx]
0x18000ac92  test    r9w, r9w
0x18000ac96  jz      short loc_18000ACAA
0x18000ac98  mov     [rax], r9w
0x18000ac9c  add     rcx, 2
0x18000aca0  add     rax, 2
0x18000aca4  sub     r10, 1
0x18000aca8  jnz     short loc_18000AC8E
0x18000acaa  test    r10, r10
0x18000acad  lea     rcx, [rax-2]
0x18000acb1  cmovnz  rcx, rax
0x18000acb5  mov     [rcx], bx
0x18000acb8  mov     rax, [r8+50h]
0x18000acbc  test    rax, rax
0x18000acbf  jz      short loc_18000ACF5
0x18000acc1  mov     r8d, 104h
0x18000acc7  add     rdx, 138h
0x18000acce  movzx   ecx, word ptr [rax]
0x18000acd1  test    cx, cx
0x18000acd4  jz      short loc_18000ACE7
0x18000acd6  mov     [rdx], cx
0x18000acd9  add     rax, 2
0x18000acdd  add     rdx, 2
0x18000ace1  sub     r8, 1
0x18000ace5  jnz     short loc_18000ACCE
0x18000ace7  test    r8, r8
0x18000acea  lea     rcx, [rdx-2]
0x18000acee  cmovnz  rcx, rdx
0x18000acf2  mov     [rcx], bx
0x18000acf5  mov     rbx, [rsp+arg_0]
0x18000acfa  retn
```
