# ORUpdateValue

- ea: `0x140026374`
- end: `0x1400265b5`
- name: `ORUpdateValue`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140025f20`

## callees

- `0x1400029d2`
- `0x140002b2c`
- `0x1400259f0`
- `0x140026374`
- `0x140026fa8`
- `0x14002e8cc`

## pseudocode

```c
__int64 __fastcall ORUpdateValue(__int64 a1, _QWORD *a2, char *a3, unsigned int a4, int a5)
{
  _DWORD *v5; // r15
  _QWORD *v6; // rsi
  size_t v8; // r14
  __int64 v10; // rbx
  __int64 v11; // rbp
  __int64 v12; // r12
  _QWORD *v13; // rax
  unsigned int v14; // edi
  _WORD *v15; // rax
  unsigned int v16; // ecx
  bool v17; // zf
  __int64 v18; // rbx
  char *v19; // rax
  _DWORD *v20; // rbx
  void *v21; // rax
  _QWORD *v23; // [rsp+28h] [rbp-40h] BYREF
  unsigned int Size; // [rsp+78h] [rbp+10h]
  char *Src; // [rsp+80h] [rbp+18h]

  Src = a3;
  v5 = (_DWORD *)a2[3];
  v6 = 0;
  v23 = 0;
  v8 = a4;
  v10 = a1;
  ORFreeDataAttachedToValue();
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v10 + 16) + 24LL)
                    - 4096
                    + (*(_DWORD *)(*(_QWORD *)(v10 + 16) + 20LL) << 12)) < 4
    || (unsigned int)(v8 - 16345) > 0x7FFFC026 )
  {
    LODWORD(v11) = 0;
    if ( (unsigned int)v8 <= 4 )
    {
      v20 = v5 + 2;
      if ( !(_DWORD)v8 )
      {
        *v20 = 0;
        v14 = 0;
        v5[1] = 0x80000000;
        a2[5] = 0;
        return v14;
      }
      memcpy_0(v5 + 2, a3, v8);
      v5[1] = v8 + 0x80000000;
      a2[5] = v20;
      goto LABEL_21;
    }
    v21 = o__aligned_malloc_0(v8, 0x10u);
    a2[5] = v21;
    if ( !v21 )
      return 8;
    memcpy_0(v21, a3, v8);
    v5[2] = 0;
LABEL_20:
    v5[1] = v8;
LABEL_21:
    v14 = 0;
    v5[3] = a5;
LABEL_22:
    v10 = a1;
    goto LABEL_23;
  }
  v11 = 0;
  v12 = ((int)v8 + 16343) / 0x3FD8u;
  v13 = o__aligned_malloc_0(8 * v12 + 8, 0x10u);
  v23 = v13;
  v6 = v13;
  if ( !v13 )
  {
    v14 = 8;
    goto LABEL_23;
  }
  a2[4] = v13;
  memset_0(v13, 0, 8 * v12 + 8);
  v14 = 8;
  v15 = o__aligned_malloc_0(8u, 0x10u);
  if ( v15 )
  {
    *v6 = v15;
    v16 = v8;
    *v15 = 25188;
    v17 = (_DWORD)v12 == 0;
    v15[1] = v12;
    *((_DWORD *)v15 + 1) = 0;
    while ( 1 )
    {
      Size = v16;
      if ( v17 )
        break;
      v18 = 16344;
      if ( v16 < 0x3FD8 )
        v18 = v16;
      v19 = (char *)o__aligned_malloc_0((unsigned int)(v18 + 4), 0x10u);
      if ( !v19 )
        goto LABEL_22;
      v6[v11 + 1] = v19;
      memcpy_0(v19 + 4, Src, (unsigned int)v18);
      v11 = (unsigned int)(v11 + 1);
      Src += v18;
      v16 = Size - v18;
      v17 = (_DWORD)v11 == (_DWORD)v12;
    }
    v6 = 0;
    a2[5] = 0;
    v23 = 0;
    v5[2] = 0;
    goto LABEL_20;
  }
LABEL_23:
  if ( v6 )
  {
    while ( (_DWORD)v11 )
    {
      LODWORD(v11) = v11 - 1;
      ORFreeOrNop(v10, &v6[(unsigned int)v11 + 1]);
    }
    ORFreeOrNop(v10, v6);
    ORFreeOrNop(v10, &v23);
  }
  return v14;
}

```

## disassembly

```asm
0x140026374  mov     rax, rsp
0x140026377  mov     [rax+20h], rbx
0x14002637b  mov     [rax+18h], r8
0x14002637f  mov     [rax+8], rcx
0x140026383  push    rbp
0x140026384  push    rsi
0x140026385  push    rdi
0x140026386  push    r12
0x140026388  push    r13
0x14002638a  push    r14
0x14002638c  push    r15
0x14002638e  sub     rsp, 30h
0x140026392  mov     r15, [rdx+18h]
0x140026396  xor     esi, esi
0x140026398  mov     [rax-40h], rsi
0x14002639c  mov     rdi, r8
0x14002639f  mov     r14d, r9d
0x1400263a2  mov     r13, rdx
0x1400263a5  mov     rbx, rcx
0x1400263a8  call    ORFreeDataAttachedToValue
0x1400263ad  mov     rax, [rbx+10h]
0x1400263b1  mov     r8d, [rax+14h]
0x1400263b5  mov     eax, [rax+18h]
0x1400263b8  add     eax, 0FFFFF000h
0x1400263bd  shl     r8d, 0Ch
0x1400263c1  add     r8d, eax
0x1400263c4  cmp     r8d, 4
0x1400263c8  jb      loc_1400264DE
0x1400263ce  lea     eax, [r14-3FD9h]
0x1400263d5  cmp     eax, 7FFFC026h
0x1400263da  ja      loc_1400264DE
0x1400263e0  lea     r12d, [r14+3FD7h]
0x1400263e7  mov     eax, 0A0643Fh
0x1400263ec  mul     r12d
0x1400263ef  lea     edi, [rsi+10h]
0x1400263f2  xor     ebp, ebp
0x1400263f4  sub     r12d, edx
0x1400263f7  shr     r12d, 1
0x1400263fa  add     r12d, edx
0x1400263fd  mov     edx, edi; Alignment
0x1400263ff  shr     r12d, 0Dh
0x140026403  lea     rax, ds:8[r12*8]
0x14002640b  mov     rcx, rax; Size
0x14002640e  mov     [rsp+68h+Size], rax
0x140026413  call    _o__aligned_malloc_0
0x140026418  mov     [rsp+68h+var_40], rax
0x14002641d  mov     rsi, rax
0x140026420  test    rax, rax
0x140026423  jnz     short loc_14002642D
0x140026425  lea     edi, [rbp+8]
0x140026428  jmp     loc_140026567
0x14002642d  mov     r8, [rsp+68h+Size]; Size
0x140026432  xor     edx, edx; Val
0x140026434  mov     rcx, rsi; void *
0x140026437  mov     [r13+20h], rsi
0x14002643b  call    memset_0
0x140026440  mov     rdx, rdi; Alignment
0x140026443  mov     edi, 8
0x140026448  mov     ecx, edi; Size
0x14002644a  call    _o__aligned_malloc_0
0x14002644f  test    rax, rax
0x140026452  jz      loc_140026567
0x140026458  mov     [rsi], rax
0x14002645b  mov     ecx, r14d
0x14002645e  mov     word ptr [rax], 6264h
0x140026463  test    r12d, r12d
0x140026466  mov     [rax+2], r12w
0x14002646b  mov     [rax+4], ebp
0x14002646e  jmp     short loc_1400264BF
0x140026470  mov     ebx, 3FD8h
0x140026475  mov     edx, 10h; Alignment
0x14002647a  cmp     ecx, ebx
0x14002647c  cmovb   ebx, ecx
0x14002647f  lea     ecx, [rbx+4]; Size
0x140026482  call    _o__aligned_malloc_0
0x140026487  mov     rcx, rax
0x14002648a  test    rax, rax
0x14002648d  jz      loc_140026562
0x140026493  mov     rdx, [rsp+68h+Src]; Src
0x14002649b  add     rcx, 4; void *
0x14002649f  mov     r8d, ebx; Size
0x1400264a2  mov     [rsi+rbp*8+8], rax
0x1400264a7  call    memcpy_0
0x1400264ac  mov     ecx, dword ptr [rsp+68h+Size]
0x1400264b0  inc     ebp
0x1400264b2  add     [rsp+68h+Src], rbx
0x1400264ba  sub     ecx, ebx
0x1400264bc  cmp     ebp, r12d
0x1400264bf  mov     dword ptr [rsp+68h+Size], ecx
0x1400264c3  jnz     short loc_140026470
0x1400264c5  xor     esi, esi
0x1400264c7  mov     qword ptr [r13+28h], 0
0x1400264cf  mov     [rsp+68h+var_40], rsi
0x1400264d4  mov     dword ptr [r15+8], 0
0x1400264dc  jmp     short loc_140026551
0x1400264de  xor     ebp, ebp
0x1400264e0  cmp     r14d, 4
0x1400264e4  ja      short loc_140026524
0x1400264e6  lea     rbx, [r15+8]
0x1400264ea  test    r14d, r14d
0x1400264ed  jnz     short loc_140026504
0x1400264ef  mov     [rbx], esi
0x1400264f1  xor     edi, edi
0x1400264f3  mov     dword ptr [r15+4], 80000000h
0x1400264fb  mov     [r13+28h], rsi
0x1400264ff  jmp     loc_14002659A
0x140026504  mov     r8, r14; Size
0x140026507  mov     rdx, rdi; Src
0x14002650a  mov     rcx, rbx; void *
0x14002650d  call    memcpy_0
0x140026512  mov     eax, 80000000h
0x140026517  add     eax, r14d
0x14002651a  mov     [r15+4], eax
0x14002651e  mov     [r13+28h], rbx
0x140026522  jmp     short loc_140026555
0x140026524  mov     edx, 10h; Alignment
0x140026529  mov     rcx, r14; Size
0x14002652c  call    _o__aligned_malloc_0
0x140026531  mov     [r13+28h], rax
0x140026535  test    rax, rax
0x140026538  jnz     short loc_14002653F
0x14002653a  lea     edi, [rax+8]
0x14002653d  jmp     short loc_14002659A
0x14002653f  mov     r8, r14; Size
0x140026542  mov     rdx, rdi; Src
0x140026545  mov     rcx, rax; void *
0x140026548  call    memcpy_0
0x14002654d  mov     [r15+8], esi
0x140026551  mov     [r15+4], r14d
0x140026555  mov     eax, [rsp+68h+arg_20]
0x14002655c  xor     edi, edi
0x14002655e  mov     [r15+0Ch], eax
0x140026562  mov     rbx, [rsp+68h+arg_0]
0x140026567  test    rsi, rsi
0x14002656a  jz      short loc_14002659A
0x14002656c  jmp     short loc_14002657E
0x14002656e  dec     ebp
0x140026570  mov     eax, ebp
0x140026572  inc     rax
0x140026575  lea     rdx, [rsi+rax*8]
0x140026579  call    ORFreeOrNop
0x14002657e  mov     rcx, rbx
0x140026581  test    ebp, ebp
0x140026583  jnz     short loc_14002656E
0x140026585  mov     rdx, rsi
0x140026588  call    ORFreeOrNop
0x14002658d  lea     rdx, [rsp+68h+var_40]
0x140026592  mov     rcx, rbx
0x140026595  call    ORFreeOrNop
0x14002659a  mov     rbx, [rsp+68h+arg_18]
0x1400265a2  mov     eax, edi
0x1400265a4  add     rsp, 30h
0x1400265a8  pop     r15
0x1400265aa  pop     r14
0x1400265ac  pop     r13
0x1400265ae  pop     r12
0x1400265b0  pop     rdi
0x1400265b1  pop     rsi
0x1400265b2  pop     rbp
0x1400265b3  retn
```
