# CdLookupLastFileDirent

- ea: `0x140012508`
- end: `0x14001270f`
- name: `CdLookupLastFileDirent`
- size: `519`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140010f68`
- `0x140012198`
- `0x14001233c`

## callees

- `0x140001114`
- `0x140012508`
- `0x140012718`
- `0x14001292c`

## pseudocode

```c
unsigned __int64 __fastcall CdLookupLastFileDirent(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  int v4; // r14d
  char i; // bp
  __int64 v9; // r8
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int16 v13; // ax
  __int64 v14; // rax
  int v15; // ecx
  int v16; // eax
  unsigned __int64 result; // rax
  __int64 v18; // rdx

  v3 = *(_QWORD *)(a3 + 8);
  v4 = 0;
  for ( i = 1; ; i = 0 )
  {
    v9 = *(unsigned int *)(v3 + 68);
    if ( !(_DWORD)v9 || (*(_DWORD *)(*(_QWORD *)(a2 + 120) + 48LL) & 0x40) == 0 )
      goto LABEL_36;
    v10 = 0;
    if ( (unsigned int)(*(_DWORD *)(v3 + 36) - v9) >= 0xE )
    {
      v11 = v9 + *(unsigned int *)(v3 + 24);
      v12 = *(_QWORD *)v3;
      if ( *(_WORD *)(v11 + *(_QWORD *)v3 + 6) == 16728 )
      {
        v13 = *(_WORD *)(v11 + v12 + 4);
        if ( (v13 & 0x40) != 0 )
          v10 = 2;
        else
          v10 = (v13 & 0x10) != 0;
        *(_WORD *)(v3 + 72) = v13;
        *(_BYTE *)(v3 + 74) = *(_BYTE *)(v11 + v12 + 8);
      }
    }
    *(_DWORD *)(v3 + 152) = v10;
    if ( v10 )
    {
      if ( !i && v4 != v10 )
        CdRaiseStatusEx(a1, -1073741566, 0, 786432, 1509);
      v14 = *(_QWORD *)(a2 + 120);
      if ( *(_DWORD *)(v14 + 424) != 2048 )
      {
        v15 = *(_DWORD *)(v14 + 436) - 1;
        if ( (v15 & *(_DWORD *)(v3 + 40)) != 0 || (v15 & *(_DWORD *)(v3 + 44)) != 0 )
          CdRaiseStatusEx(a1, -1073741566, 0, 786432, 1531);
        v16 = *(_DWORD *)(v3 + 60);
        if ( v16 && ((v16 & v15) != 0 || (v15 & *(_DWORD *)(v3 + 64)) != 0) )
          CdRaiseStatusEx(a1, -1073741566, 0, 786432, 1543);
      }
      if ( i )
        *(_QWORD *)(a3 + 32) = 44;
      result = 2352 * ((unsigned __int64)*(unsigned int *)(v3 + 44) >> 11);
    }
    else
    {
LABEL_36:
      if ( !i && v4 != *(_DWORD *)(v3 + 152) )
        CdRaiseStatusEx(a1, -1073741566, 0, 786432, 1574);
      result = *(unsigned int *)(v3 + 44);
    }
    *(_QWORD *)(a3 + 32) += result;
    if ( *(char *)(v3 + 56) >= 0 )
      break;
    v4 = *(_DWORD *)(v3 + 152);
    if ( !CdLookupNextDirent(a1, a2, (unsigned int *)v3, *(_QWORD *)(a3 + 16)) )
      CdRaiseStatusEx(a1, -1073741566, 0, 786432, 1614);
    v3 = *(_QWORD *)(a3 + 16);
    CdUpdateDirentFromRawDirent(a1, v18, v3, v3 + 32);
    *(_DWORD *)(a3 + 24) |= 1u;
  }
  return result;
}

```

## disassembly

```asm
0x140012508  push    rbx
0x14001250a  push    rbp
0x14001250b  push    rsi
0x14001250c  push    rdi
0x14001250d  push    r12
0x14001250f  push    r14
0x140012511  push    r15
0x140012513  sub     rsp, 30h
0x140012517  mov     rbx, [r8+8]
0x14001251b  xor     r14d, r14d
0x14001251e  mov     rdi, r8
0x140012521  mov     r15, rdx
0x140012524  mov     rsi, rcx
0x140012527  lea     r12d, [r14+1]
0x14001252b  mov     bpl, r12b
0x14001252e  mov     r8d, [rbx+44h]
0x140012532  test    r8d, r8d
0x140012535  jz      loc_140012608
0x14001253b  mov     rax, [r15+78h]
0x14001253f  mov     ecx, [rax+30h]
0x140012542  test    cl, 40h
0x140012545  jz      loc_140012608
0x14001254b  mov     eax, [rbx+24h]
0x14001254e  xor     ecx, ecx
0x140012550  sub     eax, r8d
0x140012553  cmp     eax, 0Eh
0x140012556  jb      short loc_140012591
0x140012558  mov     edx, [rbx+18h]
0x14001255b  mov     eax, 4158h
0x140012560  add     rdx, r8
0x140012563  mov     r8, [rbx]
0x140012566  cmp     [rdx+r8+6], ax
0x14001256c  jnz     short loc_140012591
0x14001256e  movzx   eax, word ptr [rdx+r8+4]
0x140012574  test    al, 40h
0x140012576  jz      short loc_14001257F
0x140012578  mov     ecx, 2
0x14001257d  jmp     short loc_140012585
0x14001257f  test    al, 10h
0x140012581  cmovnz  ecx, r12d
0x140012585  mov     [rbx+48h], ax
0x140012589  mov     al, [rdx+r8+8]
0x14001258e  mov     [rbx+4Ah], al
0x140012591  mov     [rbx+98h], ecx
0x140012597  test    ecx, ecx
0x140012599  jz      short loc_140012608
0x14001259b  test    bpl, bpl
0x14001259e  jnz     short loc_1400125A9
0x1400125a0  cmp     r14d, ecx
0x1400125a3  jnz     loc_140012677
0x1400125a9  mov     rax, [r15+78h]
0x1400125ad  cmp     dword ptr [rax+1A8h], 800h
0x1400125b7  jz      short loc_1400125EB
0x1400125b9  mov     ecx, [rax+1B4h]
0x1400125bf  dec     ecx
0x1400125c1  test    [rbx+28h], ecx
0x1400125c4  jnz     loc_1400126B5
0x1400125ca  test    [rbx+2Ch], ecx
0x1400125cd  jnz     loc_1400126B5
0x1400125d3  mov     eax, [rbx+3Ch]
0x1400125d6  test    eax, eax
0x1400125d8  jz      short loc_1400125EB
0x1400125da  test    ecx, eax
0x1400125dc  jnz     loc_140012696
0x1400125e2  test    [rbx+40h], ecx
0x1400125e5  jnz     loc_140012696
0x1400125eb  test    bpl, bpl
0x1400125ee  jz      short loc_1400125F8
0x1400125f0  mov     qword ptr [rdi+20h], 2Ch ; ','
0x1400125f8  mov     eax, [rbx+2Ch]
0x1400125fb  shr     rax, 0Bh
0x1400125ff  imul    rax, 930h
0x140012606  jmp     short loc_14001261D
0x140012608  test    bpl, bpl
0x14001260b  jnz     short loc_14001261A
0x14001260d  cmp     r14d, [rbx+98h]
0x140012614  jnz     loc_1400126D4
0x14001261a  mov     eax, [rbx+2Ch]
0x14001261d  add     [rdi+20h], rax
0x140012621  cmp     byte ptr [rbx+38h], 0
0x140012625  jge     short loc_140012667
0x140012627  mov     r9, [rdi+10h]
0x14001262b  mov     r8, rbx
0x14001262e  mov     r14d, [rbx+98h]
0x140012635  mov     rdx, r15
0x140012638  mov     rcx, rsi
0x14001263b  call    CdLookupNextDirent
0x140012640  mov     rcx, rsi
0x140012643  test    al, al
0x140012645  jz      loc_1400126F3
0x14001264b  mov     rbx, [rdi+10h]
0x14001264f  xor     bpl, bpl
0x140012652  mov     r8, rbx
0x140012655  lea     r9, [rbx+20h]
0x140012659  call    CdUpdateDirentFromRawDirent
0x14001265e  or      [rdi+18h], r12d
0x140012662  jmp     loc_14001252E
0x140012667  add     rsp, 30h
0x14001266b  pop     r15
0x14001266d  pop     r14
0x14001266f  pop     r12
0x140012671  pop     rdi
0x140012672  pop     rsi
0x140012673  pop     rbp
0x140012674  pop     rbx
0x140012675  retn
0x140012677  mov     r9d, 0C0000h
0x14001267d  mov     [rsp+68h+var_48], 5E5h
0x140012685  xor     r8d, r8d
0x140012688  mov     edx, 0C0000102h
0x14001268d  mov     rcx, rsi
0x140012690  call    CdRaiseStatusEx
0x140012696  mov     r9d, 0C0000h
0x14001269c  mov     [rsp+68h+var_48], 607h
0x1400126a4  xor     r8d, r8d
0x1400126a7  mov     edx, 0C0000102h
0x1400126ac  mov     rcx, rsi
0x1400126af  call    CdRaiseStatusEx
0x1400126b5  mov     r9d, 0C0000h
0x1400126bb  mov     [rsp+68h+var_48], 5FBh
0x1400126c3  xor     r8d, r8d
0x1400126c6  mov     edx, 0C0000102h
0x1400126cb  mov     rcx, rsi
0x1400126ce  call    CdRaiseStatusEx
0x1400126d4  mov     r9d, 0C0000h
0x1400126da  mov     [rsp+68h+var_48], 626h
0x1400126e2  xor     r8d, r8d
0x1400126e5  mov     edx, 0C0000102h
0x1400126ea  mov     rcx, rsi
0x1400126ed  call    CdRaiseStatusEx
0x1400126f3  mov     r9d, 0C0000h
0x1400126f9  mov     [rsp+68h+var_48], 64Eh
0x140012701  xor     r8d, r8d
0x140012704  mov     edx, 0C0000102h
0x140012709  call    CdRaiseStatusEx
```
