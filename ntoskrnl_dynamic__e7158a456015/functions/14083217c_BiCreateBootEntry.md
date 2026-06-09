# BiCreateBootEntry

- ea: `0x14083217c`
- end: `0x14083251e`
- name: `BiCreateBootEntry`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140832524`

## callees

- `0x1405490f0`
- `0x1406f6f80`
- `0x14083217c`
- `0x1409907b0`
- `0x140992ec0`
- `0x140993780`
- `0x140993cec`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x14083224f`: `BiCreateBootEntry: Could not retrieve BCD Object application path. Status: %x`
- `0x140832217`: `BiCreateBootEntry: Could not retrieve BCD Object application device. Status: %x`
- `0x1408321e3`: `BiCreateBootEntry: Could not retrieve BCD Object application description. Status: %x`

## pseudocode

```c
__int64 __fastcall BiCreateBootEntry(__int64 a1, _QWORD *a2)
{
  _DWORD *v2; // rdi
  void *v3; // rsi
  unsigned int *v4; // r14
  void *v5; // r15
  char *v6; // r12
  int Element; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  __int64 v12; // r13
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  char *Pool2; // rax
  __int64 v20; // rbx
  size_t v21; // r8
  int KeyName; // eax
  int v23; // r8d
  unsigned int v24; // ecx
  _DWORD *v25; // rax
  _DWORD *v26; // rbx
  int v27; // ecx
  size_t v28; // r8
  PVOID v29; // rdx
  int v30; // eax
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rax
  size_t v35; // [rsp+30h] [rbp-38h] BYREF
  void *v36; // [rsp+38h] [rbp-30h] BYREF
  void *Src; // [rsp+40h] [rbp-28h] BYREF
  _DWORD *v38; // [rsp+48h] [rbp-20h] BYREF
  void *v39; // [rsp+50h] [rbp-18h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-10h] BYREF
  size_t v43; // [rsp+C0h] [rbp+58h] BYREF
  size_t Size; // [rsp+C8h] [rbp+60h] BYREF

  LODWORD(v43) = 0;
  LODWORD(Size) = 0;
  LODWORD(v35) = 0;
  v2 = 0;
  P[0] = 0;
  v3 = 0;
  v38 = 0;
  v4 = 0;
  Src = 0;
  v5 = 0;
  v36 = 0;
  v6 = 0;
  v39 = 0;
  Element = BiGetElement(a1, 301989892, P, &v43);
  v9 = Element;
  if ( Element < 0 )
  {
    BiLogMessage(
      4,
      L"BiCreateBootEntry: Could not retrieve BCD Object application description. Status: %x",
      (unsigned int)Element);
    goto LABEL_25;
  }
  v10 = BiGetElement(a1, 285212673, &v38, &Size);
  v9 = v10;
  if ( v10 < 0 )
  {
    BiLogMessage(
      4,
      L"BiCreateBootEntry: Could not retrieve BCD Object application device. Status: %x",
      (unsigned int)v10);
    v2 = v38;
    goto LABEL_25;
  }
  v11 = BiGetElement(a1, 301989890, &Src, &v35);
  v9 = v11;
  if ( v11 < 0 )
  {
    BiLogMessage(4, L"BiCreateBootEntry: Could not retrieve BCD Object application path. Status: %x", (unsigned int)v11);
    v2 = v38;
    v3 = Src;
    goto LABEL_25;
  }
  v2 = v38;
  v3 = Src;
  if ( *v38 != 2 )
  {
    v9 = -1073741637;
    goto LABEL_25;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)Src + v13) );
  v14 = 2 * v13 + 2;
  v15 = -1;
  LODWORD(v35) = v14;
  do
    ++v15;
  while ( *((_WORD *)v38 + v15 + 10) );
  v16 = 2 * v15 + 2;
  v17 = v16 + v14;
  LODWORD(Size) = v16;
  if ( v16 + v14 < v16 )
    goto LABEL_24;
  v18 = v17 + 12;
  if ( v17 + 12 < v17 )
    goto LABEL_24;
  Pool2 = (char *)ExAllocatePool2(258, v18, 1262764866);
  v6 = Pool2;
  if ( !Pool2 )
  {
LABEL_16:
    v9 = -1073741670;
    goto LABEL_25;
  }
  *((_DWORD *)Pool2 + 1) = v18;
  v20 = (unsigned int)Size;
  v21 = (unsigned int)Size;
  *(_DWORD *)Pool2 = 1;
  *((_DWORD *)Pool2 + 2) = 3;
  memmove(Pool2 + 12, v2 + 5, v21);
  memmove(&v6[v20 + 12], v3, (unsigned int)v35);
  v9 = BiTranslateFilePath(v6, 4, &v36);
  if ( v9 < 0 || (KeyName = BiGetKeyName(a1, &v39), v5 = v39, v9 = KeyName, KeyName < 0) )
  {
    v4 = (unsigned int *)v36;
    goto LABEL_25;
  }
  do
    ++v12;
  while ( *((_WORD *)v39 + v12) );
  v4 = (unsigned int *)v36;
  LODWORD(v38) = (2 * v12 + 45) & 0xFFFFFFFC;
  LODWORD(v35) = (_DWORD)v38 + 16;
  v23 = *((_DWORD *)v36 + 1);
  v24 = ((_DWORD)v38 + 47) & 0xFFFFFFFC;
  LODWORD(Src) = v24;
  if ( (unsigned int)v43 + v24 + v23 + 4 < (unsigned int)v43 )
  {
LABEL_24:
    v9 = -1073741675;
  }
  else
  {
    LODWORD(Size) = (v24 + v43 + 3) & 0xFFFFFFFC;
    LODWORD(v36) = v23 + Size;
    v25 = (_DWORD *)ExAllocatePool2(258, (unsigned int)(v23 + Size), 1262764866);
    v26 = v25;
    if ( !v25 )
      goto LABEL_16;
    v27 = Size;
    v28 = (unsigned int)v43;
    v29 = P[0];
    *v25 = 1;
    v30 = (int)v36;
    v26[5] = v27;
    v31 = v35;
    v26[1] = v30;
    v32 = (unsigned int)Src;
    v26[6] = v31;
    v26[2] = -1;
    v26[3] = 5;
    v26[4] = v32;
    memmove((char *)v26 + v32, v29, v28);
    memmove((char *)v26 + (unsigned int)Size, v4, v4[1]);
    *(_QWORD *)(v26 + 7) = 0x53574F444E4957LL;
    v26[10] = v35;
    v26[11] = (_DWORD)v38;
    v26[9] = 1;
    swprintf_s((wchar_t *)v26 + 24, (unsigned int)v12 + 11LL, L"%s%s", L"BCDOBJECT=", v5);
    v33 = (unsigned int)v26[11];
    *(_DWORD *)((char *)v26 + v33 + 28) = 1;
    *(_DWORD *)((char *)v26 + v33 + 32) = 16;
    *(_DWORD *)((char *)v26 + v33 + 36) = 4;
    *(_DWORD *)((char *)v26 + v33 + 40) = 327551;
    *a2 = v26;
    v9 = 0;
  }
LABEL_25:
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0x4B444342u);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x4B444342u);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x4B444342u);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x4B444342u);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x4B444342u);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x4B444342u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14083217c  mov     [rsp-40h+arg_8], rdx
0x140832181  mov     [rsp-40h+arg_0], rcx
0x140832186  push    rbp
0x140832187  push    rbx
0x140832188  push    rsi
0x140832189  push    rdi
0x14083218a  push    r12
0x14083218c  push    r13
0x14083218e  push    r14
0x140832190  push    r15
0x140832192  mov     rbp, rsp
0x140832195  sub     rsp, 68h
0x140832199  xor     eax, eax
0x14083219b  lea     r9, [rbp+arg_10]
0x14083219f  lea     r8, [rbp+P]
0x1408321a3  mov     dword ptr [rbp+arg_10], eax
0x1408321a6  mov     edx, 12000004h
0x1408321ab  mov     dword ptr [rbp+Size], eax
0x1408321ae  mov     dword ptr [rbp+var_38], eax
0x1408321b1  mov     edi, eax
0x1408321b3  mov     [rbp+P], rax
0x1408321b7  mov     esi, eax
0x1408321b9  mov     [rbp+var_20], rax
0x1408321bd  mov     r14d, eax
0x1408321c0  mov     [rbp+Src], rax
0x1408321c4  mov     r15d, eax
0x1408321c7  mov     [rbp+var_30], rax
0x1408321cb  mov     r12d, eax
0x1408321ce  mov     [rbp+var_18], rax
0x1408321d2  mov     r13, rcx
0x1408321d5  call    BiGetElement
0x1408321da  mov     ebx, eax
0x1408321dc  test    eax, eax
0x1408321de  jns     short loc_1408321F9
0x1408321e0  mov     r8d, eax
0x1408321e3  lea     rdx, aBicreatebooten_1; "BiCreateBootEntry: Could not retrieve B"...
0x1408321ea  lea     ecx, [r12+4]
0x1408321ef  call    BiLogMessage
0x1408321f4  jmp     loc_1408324A0
0x1408321f9  lea     r9, [rbp+Size]
0x1408321fd  mov     edx, 11000001h
0x140832202  lea     r8, [rbp+var_20]
0x140832206  mov     rcx, r13
0x140832209  call    BiGetElement
0x14083220e  mov     ebx, eax
0x140832210  test    eax, eax
0x140832212  jns     short loc_140832231
0x140832214  mov     r8d, eax
0x140832217  lea     rdx, aBicreatebooten; "BiCreateBootEntry: Could not retrieve B"...
0x14083221e  mov     ecx, 4
0x140832223  call    BiLogMessage
0x140832228  mov     rdi, [rbp+var_20]
0x14083222c  jmp     loc_1408324A0
0x140832231  lea     r9, [rbp+var_38]
0x140832235  mov     edx, 12000002h
0x14083223a  lea     r8, [rbp+Src]
0x14083223e  mov     rcx, r13
0x140832241  call    BiGetElement
0x140832246  mov     ebx, eax
0x140832248  test    eax, eax
0x14083224a  jns     short loc_14083226D
0x14083224c  mov     r8d, eax
0x14083224f  lea     rdx, aBicreatebooten_0; "BiCreateBootEntry: Could not retrieve B"...
0x140832256  mov     ecx, 4
0x14083225b  call    BiLogMessage
0x140832260  mov     rdi, [rbp+var_20]
0x140832264  mov     rsi, [rbp+Src]
0x140832268  jmp     loc_1408324A0
0x14083226d  mov     rdi, [rbp+var_20]
0x140832271  mov     rsi, [rbp+Src]
0x140832275  cmp     dword ptr [rdi], 2
0x140832278  jz      short loc_140832284
0x14083227a  mov     ebx, 0C00000BBh
0x14083227f  jmp     loc_1408324A0
0x140832284  or      r13, 0FFFFFFFFFFFFFFFFh
0x140832288  mov     rax, r13
0x14083228b  xor     ebx, ebx
0x14083228d  inc     rax
0x140832290  cmp     [rsi+rax*2], bx
0x140832294  jnz     short loc_14083228D
0x140832296  lea     edx, ds:2[rax*2]
0x14083229d  mov     rax, r13
0x1408322a0  mov     dword ptr [rbp+var_38], edx
0x1408322a3  inc     rax
0x1408322a6  cmp     [rdi+rax*2+14h], bx
0x1408322ab  jnz     short loc_1408322A3
0x1408322ad  lea     ecx, ds:2[rax*2]
0x1408322b4  lea     eax, [rcx+rdx]
0x1408322b7  mov     dword ptr [rbp+Size], ecx
0x1408322ba  cmp     eax, ecx
0x1408322bc  jb      loc_14083249B
0x1408322c2  lea     ebx, [rax+0Ch]
0x1408322c5  cmp     ebx, eax
0x1408322c7  jb      loc_14083249B
0x1408322cd  mov     edx, ebx
0x1408322cf  mov     ecx, 102h
0x1408322d4  mov     r8d, 4B444342h
0x1408322da  call    ExAllocatePool2
0x1408322df  mov     r12, rax
0x1408322e2  test    rax, rax
0x1408322e5  jnz     short loc_1408322F1
0x1408322e7  mov     ebx, 0C000009Ah
0x1408322ec  jmp     loc_1408324A0
0x1408322f1  mov     [rax+4], ebx
0x1408322f4  lea     rcx, [rax+0Ch]; void *
0x1408322f8  mov     ebx, dword ptr [rbp+Size]
0x1408322fb  lea     rdx, [rdi+14h]; Src
0x1408322ff  mov     r8d, ebx; Size
0x140832302  mov     dword ptr [rax], 1
0x140832308  mov     dword ptr [rax+8], 3
0x14083230f  call    memmove
0x140832314  mov     r8d, dword ptr [rbp+var_38]; Size
0x140832318  lea     rcx, [rbx+0Ch]
0x14083231c  add     rcx, r12; void *
0x14083231f  mov     rdx, rsi; Src
0x140832322  call    memmove
0x140832327  lea     r8, [rbp+var_30]
0x14083232b  mov     edx, 4
0x140832330  mov     rcx, r12
0x140832333  call    BiTranslateFilePath
0x140832338  mov     ebx, eax
0x14083233a  test    eax, eax
0x14083233c  js      loc_140832495
0x140832342  mov     rcx, [rbp+arg_0]
0x140832346  lea     rdx, [rbp+var_18]
0x14083234a  call    BiGetKeyName
0x14083234f  mov     r15, [rbp+var_18]
0x140832353  mov     ebx, eax
0x140832355  test    eax, eax
0x140832357  js      loc_140832495
0x14083235d  inc     r13
0x140832360  cmp     [r15+r13*2], r14w
0x140832365  jnz     short loc_14083235D
0x140832367  mov     edx, dword ptr [rbp+arg_10]
0x14083236a  lea     eax, ds:2Dh[r13*2]
0x140832372  mov     r14, [rbp+var_30]
0x140832376  mov     r9d, 0FFFFFFFCh
0x14083237c  and     eax, r9d
0x14083237f  mov     dword ptr [rbp+var_20], eax
0x140832382  add     eax, 10h
0x140832385  mov     dword ptr [rbp+var_38], eax
0x140832388  mov     r8d, [r14+4]
0x14083238c  lea     ecx, [rax+1Fh]
0x14083238f  and     ecx, r9d
0x140832392  lea     eax, [r8+4]
0x140832396  mov     dword ptr [rbp+Src], ecx
0x140832399  add     eax, ecx
0x14083239b  add     eax, edx
0x14083239d  cmp     eax, edx
0x14083239f  jb      loc_14083249B
0x1408323a5  lea     eax, [rdx+3]
0x1408323a8  add     eax, ecx
0x1408323aa  mov     ecx, 102h
0x1408323af  and     eax, r9d
0x1408323b2  mov     dword ptr [rbp+Size], eax
0x1408323b5  add     eax, r8d
0x1408323b8  mov     edx, eax
0x1408323ba  mov     r8d, 4B444342h
0x1408323c0  mov     dword ptr [rbp+var_30], eax
0x1408323c3  call    ExAllocatePool2
0x1408323c8  mov     rbx, rax
0x1408323cb  test    rax, rax
0x1408323ce  jz      loc_1408322E7
0x1408323d4  mov     ecx, dword ptr [rbp+Size]
0x1408323d7  mov     r8d, dword ptr [rbp+arg_10]; Size
0x1408323db  mov     rdx, [rbp+P]; Src
0x1408323df  mov     dword ptr [rax], 1
0x1408323e5  mov     eax, dword ptr [rbp+var_30]
0x1408323e8  mov     [rbx+14h], ecx
0x1408323eb  mov     ecx, dword ptr [rbp+var_38]
0x1408323ee  mov     [rbx+4], eax
0x1408323f1  mov     eax, dword ptr [rbp+Src]
0x1408323f4  mov     [rbx+18h], ecx
0x1408323f7  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1408323fe  mov     dword ptr [rbx+0Ch], 5
0x140832405  lea     rcx, [rbx+rax]; void *
0x140832409  mov     [rbx+10h], eax
0x14083240c  call    memmove
0x140832411  mov     ecx, dword ptr [rbp+Size]
0x140832414  mov     rdx, r14; Src
0x140832417  mov     r8d, [r14+4]; Size
0x14083241b  add     rcx, rbx; void *
0x14083241e  call    memmove
0x140832423  mov     rax, 53574F444E4957h
0x14083242d  mov     edx, r13d
0x140832430  mov     [rbx+1Ch], rax
0x140832434  lea     rcx, [rbx+30h]; Dst
0x140832438  mov     eax, dword ptr [rbp+var_38]
0x14083243b  lea     r9, aBcdobject; "BCDOBJECT="
0x140832442  mov     [rbx+28h], eax
0x140832445  lea     r8, aSS_0; "%s%s"
0x14083244c  mov     eax, dword ptr [rbp+var_20]
0x14083244f  add     rdx, 0Bh; SizeInWords
0x140832453  mov     [rbx+2Ch], eax
0x140832456  mov     dword ptr [rbx+24h], 1
0x14083245d  mov     [rsp+68h+var_48], r15
0x140832462  call    swprintf_s
0x140832467  mov     eax, [rbx+2Ch]
0x14083246a  mov     dword ptr [rax+rbx+1Ch], 1
0x140832472  mov     dword ptr [rax+rbx+20h], 10h
0x14083247a  mov     dword ptr [rax+rbx+24h], 4
0x140832482  mov     dword ptr [rax+rbx+28h], 4FF7Fh
0x14083248a  mov     rax, [rbp+arg_8]
0x14083248e  mov     [rax], rbx
0x140832491  xor     ebx, ebx
0x140832493  jmp     short loc_1408324A0
0x140832495  mov     r14, [rbp+var_30]
0x140832499  jmp     short loc_1408324A0
0x14083249b  mov     ebx, 0C0000095h
0x1408324a0  mov     rax, [rbp+P]
0x1408324a4  mov     r13d, 4B444342h
0x1408324aa  test    rax, rax
0x1408324ad  jz      short loc_1408324BA
0x1408324af  mov     edx, r13d; Tag
0x1408324b2  mov     rcx, rax; P
0x1408324b5  call    ExFreePoolWithTag
0x1408324ba  test    rdi, rdi
0x1408324bd  jz      short loc_1408324CA
0x1408324bf  mov     edx, r13d; Tag
0x1408324c2  mov     rcx, rdi; P
0x1408324c5  call    ExFreePoolWithTag
0x1408324ca  test    rsi, rsi
0x1408324cd  jz      short loc_1408324DA
0x1408324cf  mov     edx, r13d; Tag
0x1408324d2  mov     rcx, rsi; P
0x1408324d5  call    ExFreePoolWithTag
0x1408324da  test    r14, r14
0x1408324dd  jz      short loc_1408324EA
0x1408324df  mov     edx, r13d; Tag
0x1408324e2  mov     rcx, r14; P
0x1408324e5  call    ExFreePoolWithTag
0x1408324ea  test    r15, r15
0x1408324ed  jz      short loc_1408324FA
0x1408324ef  mov     edx, r13d; Tag
0x1408324f2  mov     rcx, r15; P
0x1408324f5  call    ExFreePoolWithTag
0x1408324fa  test    r12, r12
0x1408324fd  jz      short loc_14083250A
0x1408324ff  mov     edx, r13d; Tag
0x140832502  mov     rcx, r12; P
0x140832505  call    ExFreePoolWithTag
0x14083250a  mov     eax, ebx
0x14083250c  add     rsp, 68h
0x140832510  pop     r15
0x140832512  pop     r14
0x140832514  pop     r13
0x140832516  pop     r12
0x140832518  pop     rdi
0x140832519  pop     rsi
0x14083251a  pop     rbx
0x14083251b  pop     rbp
0x14083251c  retn
```
