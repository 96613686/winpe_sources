# KerbCreateKernelModeContext

- ea: `0x1400301f0`
- end: `0x140030590`
- name: `KerbCreateKernelModeContext`
- size: `928`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400209a0`
- `0x140020b90`

## callees

- `0x140004c00`
- `0x140004d00`
- `0x140004da0`
- `0x1400102c0`
- `0x1400301f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003033f`
- `ntoskrnl!ExAllocatePool2` at `0x1400303dc`
- `ntoskrnl!ExAllocatePool2` at `0x14003043c`
- `ntoskrnl!ExAllocatePool2` at `0x140030496`
- `ntoskrnl!ExAllocatePool2` at `0x1400304f9`
- `ntoskrnl!ExAllocatePool2` at `0x14003033f`
- `ntoskrnl!ExAllocatePool2` at `0x1400303dc`
- `ntoskrnl!ExAllocatePool2` at `0x14003043c`
- `ntoskrnl!ExAllocatePool2` at `0x140030496`
- `ntoskrnl!ExAllocatePool2` at `0x1400304f9`

## pseudocode

```c
__int64 __fastcall KerbCreateKernelModeContext(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, int a5)
{
  bool v6; // cf
  enum _POOL_TYPE v10; // r12d
  __int64 v11; // r15
  int Context; // eax
  _DWORD *v13; // r14
  int inserted; // ebp
  unsigned __int16 v15; // cx
  unsigned __int16 v16; // ax
  unsigned __int16 v17; // cx
  unsigned __int16 v18; // ax
  __int64 v19; // rdi
  char *Pool2; // rax
  char *v21; // rbx
  __int64 v22; // rcx
  unsigned int v23; // eax
  void *v24; // rax
  int v25; // eax
  unsigned int v26; // eax
  void *v27; // rax
  unsigned int v28; // eax
  void *v29; // rax
  unsigned int v30; // eax
  void *v31; // rax
  PVOID P; // [rsp+58h] [rbp+10h] BYREF

  v6 = *(_DWORD *)a2 < 0x98u;
  P = 0;
  if ( v6 )
    return 3221225485LL;
  v10 = KerbPoolType;
  v11 = *(_QWORD *)(a2 + 8);
  Context = KerbAllocateContext(KerbPoolType, (struct _KERB_KERNEL_CONTEXT **)&P);
  v13 = P;
  inserted = Context;
  if ( Context < 0 )
    goto LABEL_38;
  *((_QWORD *)P + 1) = 0;
  *(_QWORD *)v13 = 0;
  v13[4] = 1;
  v13[5] = 1112687947;
  *((_QWORD *)v13 + 3) = 0;
  *((_QWORD *)v13 + 4) = 0;
  *((_QWORD *)v13 + 7) = *(_QWORD *)(v11 + 24);
  *((_QWORD *)v13 + 5) = *(_QWORD *)(v11 + 8);
  *((_QWORD *)v13 + 6) = *(_QWORD *)(v11 + 16);
  *((_QWORD *)v13 + 8) = *(_QWORD *)(v11 + 32);
  *((_QWORD *)v13 + 17) = *(_QWORD *)(v11 + 88);
  *((_QWORD *)v13 + 18) = *(_QWORD *)(v11 + 96);
  v13[38] = *(_DWORD *)(v11 + 104);
  v13[39] = *(_DWORD *)(v11 + 108) | a5;
  v13[40] = *(_DWORD *)(v11 + 112);
  *((_QWORD *)v13 + 11) = a1;
  if ( a4 )
    *((_QWORD *)v13 + 13) = a4;
  else
    *((_QWORD *)v13 + 13) = *(int *)(v11 + 68);
  v15 = *(_WORD *)(v11 + 40);
  v16 = *(_WORD *)(v11 + 48) + v15;
  if ( v16 < v15 || (v17 = *(_WORD *)(v11 + 48) + v15, *((_WORD *)v13 + 37) = v16, v18 = v16 + 2, v18 < v17) )
  {
    inserted = -1073741675;
    *((_WORD *)v13 + 37) = -1;
    goto LABEL_38;
  }
  *((_WORD *)v13 + 37) = v18;
  v19 = 256;
  if ( v10 != PagedPool )
    v19 = 64;
  Pool2 = (char *)ExAllocatePool2((unsigned int)v19, *((unsigned __int16 *)v13 + 37), 1130525259);
  *((_QWORD *)v13 + 10) = Pool2;
  v21 = Pool2;
  if ( !Pool2 )
  {
    inserted = -1073741670;
    goto LABEL_38;
  }
  if ( *(_WORD *)(v11 + 48) )
  {
    memmove(Pool2, (const void *)(v11 + *(unsigned int *)(v11 + 52)), *(unsigned __int16 *)(v11 + 48));
    v22 = *(unsigned __int16 *)(v11 + 48);
    *(_WORD *)&v21[v22] = 92;
    v21 += v22 + 2;
  }
  if ( *(_WORD *)(v11 + 40) )
  {
    memmove(v21, (const void *)(v11 + *(unsigned int *)(v11 + 44)), *(unsigned __int16 *)(v11 + 40));
    LOWORD(v21) = *(_WORD *)(v11 + 40) + (_WORD)v21;
  }
  *((_WORD *)v13 + 36) = (_WORD)v21 - *((_WORD *)v13 + 40);
  v13[28] = *(_DWORD *)(v11 + 76);
  v23 = *(_DWORD *)(v11 + 84);
  v13[30] = v23;
  if ( v23 )
  {
    v24 = (void *)ExAllocatePool2(v19, v23, 1130525259);
    *((_QWORD *)v13 + 16) = v24;
    if ( !v24 )
    {
      inserted = -1073741670;
      goto LABEL_38;
    }
    memmove(v24, (const void *)(v11 + *(unsigned int *)(v11 + 80)), (unsigned int)v13[30]);
  }
  v25 = *(_DWORD *)(v11 + 132);
  v13[46] = v25;
  if ( v25 )
  {
    v26 = *(_DWORD *)(v11 + 140);
    v13[48] = v26;
    v27 = (void *)ExAllocatePool2(v19, v26, 1130525259);
    *((_QWORD *)v13 + 25) = v27;
    if ( !v27 )
    {
      inserted = -1073741670;
      goto LABEL_38;
    }
    memmove(v27, (const void *)(v11 + *(unsigned int *)(v11 + 136)), (unsigned int)v13[48]);
  }
  v28 = *(_DWORD *)(v11 + 128);
  v13[44] = v28;
  if ( *(_DWORD *)(v11 + 124) )
  {
    v29 = (void *)ExAllocatePool2(v19, v28, 1130525259);
    *((_QWORD *)v13 + 21) = v29;
    if ( !v29 )
    {
      inserted = -1073741670;
      goto LABEL_38;
    }
    memmove(v29, (const void *)(v11 + *(unsigned int *)(v11 + 124)), (unsigned int)v13[44]);
  }
  else
  {
    *((_QWORD *)v13 + 21) = 0;
  }
  v30 = *(_DWORD *)(v11 + 148);
  v13[54] = v30;
  if ( *(_DWORD *)(v11 + 144) )
  {
    v31 = (void *)ExAllocatePool2(v19, v30, 1130525259);
    *((_QWORD *)v13 + 26) = v31;
    if ( !v31 )
    {
      inserted = -1073741670;
      goto LABEL_38;
    }
    memmove(v31, (const void *)(v11 + *(unsigned int *)(v11 + 144)), (unsigned int)v13[54]);
  }
  else
  {
    *((_QWORD *)v13 + 26) = 0;
  }
  inserted = KerbInsertContext(v10, (struct _KERB_KERNEL_CONTEXT *)v13);
  if ( inserted < 0 )
  {
LABEL_38:
    if ( v13 )
      KerbFreeContext(v13);
    return (unsigned int)inserted;
  }
  *a3 = v13;
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1400301f0  push    rbx
0x1400301f2  push    rsi
0x1400301f3  push    rdi
0x1400301f4  push    r13
0x1400301f6  sub     rsp, 28h
0x1400301fa  xor     r13d, r13d
0x1400301fd  mov     rbx, r9
0x140030200  cmp     dword ptr [rdx], 98h
0x140030206  mov     rsi, r8
0x140030209  mov     rdi, rcx
0x14003020c  mov     [rsp+48h+P], r13
0x140030211  jnb     short loc_140030223
0x140030213  mov     eax, 0C000000Dh
0x140030218  add     rsp, 28h
0x14003021c  pop     r13
0x14003021e  pop     rdi
0x14003021f  pop     rsi
0x140030220  pop     rbx
0x140030221  retn
0x140030223  mov     [rsp+48h+arg_0], rbp
0x140030228  mov     [rsp+48h+arg_10], r12
0x14003022d  mov     r12d, cs:?KerbPoolType@@3W4_POOL_TYPE@@A; _POOL_TYPE KerbPoolType
0x140030234  mov     ecx, r12d; enum _POOL_TYPE
0x140030237  mov     [rsp+48h+arg_18], r14
0x14003023c  mov     [rsp+48h+var_28], r15
0x140030241  mov     r15, [rdx+8]
0x140030245  lea     rdx, [rsp+48h+P]; struct _KERB_KERNEL_CONTEXT **
0x14003024a  call    ?KerbAllocateContext@@YAJW4_POOL_TYPE@@PEAPEAU_KERB_KERNEL_CONTEXT@@@Z; KerbAllocateContext(_POOL_TYPE,_KERB_KERNEL_CONTEXT * *)
0x14003024f  mov     r14, [rsp+48h+P]
0x140030254  mov     ebp, eax
0x140030256  test    eax, eax
0x140030258  js      loc_14003055C
0x14003025e  mov     [r14+8], r13
0x140030262  mov     [r14], r13
0x140030265  mov     dword ptr [r14+10h], 1
0x14003026d  mov     dword ptr [r14+14h], 4252454Bh
0x140030275  mov     [r14+18h], r13
0x140030279  mov     [r14+20h], r13
0x14003027d  mov     rax, [r15+18h]
0x140030281  mov     [r14+38h], rax
0x140030285  mov     rax, [r15+8]
0x140030289  mov     [r14+28h], rax
0x14003028d  mov     rax, [r15+10h]
0x140030291  mov     [r14+30h], rax
0x140030295  mov     rax, [r15+20h]
0x140030299  mov     [r14+40h], rax
0x14003029d  mov     rax, [r15+58h]
0x1400302a1  mov     [r14+88h], rax
0x1400302a8  mov     rax, [r15+60h]
0x1400302ac  mov     [r14+90h], rax
0x1400302b3  mov     eax, [r15+68h]
0x1400302b7  mov     [r14+98h], eax
0x1400302be  mov     eax, [rsp+48h+arg_20]
0x1400302c2  or      eax, [r15+6Ch]
0x1400302c6  mov     [r14+9Ch], eax
0x1400302cd  mov     eax, [r15+70h]
0x1400302d1  mov     [r14+0A0h], eax
0x1400302d8  mov     [r14+58h], rdi
0x1400302dc  test    rbx, rbx
0x1400302df  jnz     short loc_1400302EB
0x1400302e1  movsxd  rax, dword ptr [r15+44h]
0x1400302e5  mov     [r14+68h], rax
0x1400302e9  jmp     short loc_1400302EF
0x1400302eb  mov     [r14+68h], rbx
0x1400302ef  movzx   ecx, word ptr [r15+28h]
0x1400302f4  movzx   eax, cx
0x1400302f7  add     ax, [r15+30h]
0x1400302fc  movzx   edx, ax
0x1400302ff  cmp     ax, cx
0x140030302  jb      loc_140030550
0x140030308  movzx   ecx, ax
0x14003030b  mov     [r14+4Ah], ax
0x140030310  lea     eax, [rcx+2]
0x140030313  cmp     ax, cx
0x140030316  jb      loc_140030550
0x14003031c  mov     [r14+4Ah], ax
0x140030321  cmp     r12d, 1
0x140030325  movzx   edx, word ptr [r14+4Ah]
0x14003032a  mov     eax, 40h ; '@'
0x14003032f  mov     edi, 100h
0x140030334  mov     r8d, 4362724Bh
0x14003033a  cmovnz  edi, eax
0x14003033d  mov     ecx, edi
0x14003033f  call    cs:__imp_ExAllocatePool2
0x140030346  nop     dword ptr [rax+rax+00h]
0x14003034b  mov     [r14+50h], rax
0x14003034f  mov     rbx, rax
0x140030352  test    rax, rax
0x140030355  jnz     short loc_140030361
0x140030357  mov     ebp, 0C000009Ah
0x14003035c  jmp     loc_14003055C
0x140030361  movzx   eax, word ptr [r15+30h]
0x140030366  test    ax, ax
0x140030369  jz      short loc_14003038F
0x14003036b  mov     edx, [r15+34h]
0x14003036f  mov     r8d, eax; Size
0x140030372  add     rdx, r15; Src
0x140030375  mov     rcx, rbx; void *
0x140030378  call    memmove
0x14003037d  movzx   ecx, word ptr [r15+30h]
0x140030382  mov     word ptr [rcx+rbx], 5Ch ; '\'
0x140030388  add     rbx, 2
0x14003038c  add     rbx, rcx
0x14003038f  movzx   eax, word ptr [r15+28h]
0x140030394  test    ax, ax
0x140030397  jz      short loc_1400303B3
0x140030399  mov     edx, [r15+2Ch]
0x14003039d  mov     r8d, eax; Size
0x1400303a0  add     rdx, r15; Src
0x1400303a3  mov     rcx, rbx; void *
0x1400303a6  call    memmove
0x1400303ab  movzx   eax, word ptr [r15+28h]
0x1400303b0  add     rbx, rax
0x1400303b3  sub     bx, [r14+50h]
0x1400303b8  mov     [r14+48h], bx
0x1400303bd  mov     eax, [r15+4Ch]
0x1400303c1  mov     [r14+70h], eax
0x1400303c5  mov     eax, [r15+54h]
0x1400303c9  mov     [r14+78h], eax
0x1400303cd  test    eax, eax
0x1400303cf  jz      short loc_140030411
0x1400303d1  mov     edx, eax
0x1400303d3  mov     r8d, 4362724Bh
0x1400303d9  mov     rcx, rdi
0x1400303dc  call    cs:__imp_ExAllocatePool2
0x1400303e3  nop     dword ptr [rax+rax+00h]
0x1400303e8  mov     [r14+80h], rax
0x1400303ef  test    rax, rax
0x1400303f2  jnz     short loc_1400303FE
0x1400303f4  mov     ebp, 0C000009Ah
0x1400303f9  jmp     loc_14003055C
0x1400303fe  mov     edx, [r15+50h]
0x140030402  mov     rcx, rax; void *
0x140030405  mov     r8d, [r14+78h]; Size
0x140030409  add     rdx, r15; Src
0x14003040c  call    memmove
0x140030411  mov     eax, [r15+84h]
0x140030418  mov     [r14+0B8h], eax
0x14003041f  test    eax, eax
0x140030421  jz      short loc_140030477
0x140030423  mov     eax, [r15+8Ch]
0x14003042a  mov     r8d, 4362724Bh
0x140030430  mov     edx, eax
0x140030432  mov     [r14+0C0h], eax
0x140030439  mov     rcx, rdi
0x14003043c  call    cs:__imp_ExAllocatePool2
0x140030443  nop     dword ptr [rax+rax+00h]
0x140030448  mov     [r14+0C8h], rax
0x14003044f  test    rax, rax
0x140030452  jnz     short loc_14003045E
0x140030454  mov     ebp, 0C000009Ah
0x140030459  jmp     loc_14003055C
0x14003045e  mov     edx, [r15+88h]
0x140030465  mov     rcx, rax; void *
0x140030468  mov     r8d, [r14+0C0h]; Size
0x14003046f  add     rdx, r15; Src
0x140030472  call    memmove
0x140030477  mov     eax, [r15+80h]
0x14003047e  mov     [r14+0B0h], eax
0x140030485  cmp     [r15+7Ch], r13d
0x140030489  jz      short loc_1400304D0
0x14003048b  mov     edx, eax
0x14003048d  mov     r8d, 4362724Bh
0x140030493  mov     rcx, rdi
0x140030496  call    cs:__imp_ExAllocatePool2
0x14003049d  nop     dword ptr [rax+rax+00h]
0x1400304a2  mov     [r14+0A8h], rax
0x1400304a9  test    rax, rax
0x1400304ac  jnz     short loc_1400304B8
0x1400304ae  mov     ebp, 0C000009Ah
0x1400304b3  jmp     loc_14003055C
0x1400304b8  mov     edx, [r15+7Ch]
0x1400304bc  mov     rcx, rax; void *
0x1400304bf  mov     r8d, [r14+0B0h]; Size
0x1400304c6  add     rdx, r15; Src
0x1400304c9  call    memmove
0x1400304ce  jmp     short loc_1400304D7
0x1400304d0  mov     [r14+0A8h], r13
0x1400304d7  mov     eax, [r15+94h]
0x1400304de  mov     [r14+0D8h], eax
0x1400304e5  cmp     [r15+90h], r13d
0x1400304ec  jz      short loc_140030533
0x1400304ee  mov     edx, eax
0x1400304f0  mov     r8d, 4362724Bh
0x1400304f6  mov     rcx, rdi
0x1400304f9  call    cs:__imp_ExAllocatePool2
0x140030500  nop     dword ptr [rax+rax+00h]
0x140030505  mov     [r14+0D0h], rax
0x14003050c  test    rax, rax
0x14003050f  jnz     short loc_140030518
0x140030511  mov     ebp, 0C000009Ah
0x140030516  jmp     short loc_14003055C
0x140030518  mov     edx, [r15+90h]
0x14003051f  mov     rcx, rax; void *
0x140030522  mov     r8d, [r14+0D8h]; Size
0x140030529  add     rdx, r15; Src
0x14003052c  call    memmove
0x140030531  jmp     short loc_14003053A
0x140030533  mov     [r14+0D0h], r13
0x14003053a  mov     rdx, r14; struct _KERB_KERNEL_CONTEXT *
0x14003053d  mov     ecx, r12d; enum _POOL_TYPE
0x140030540  call    ?KerbInsertContext@@YAJW4_POOL_TYPE@@PEAU_KERB_KERNEL_CONTEXT@@@Z; KerbInsertContext(_POOL_TYPE,_KERB_KERNEL_CONTEXT *)
0x140030545  mov     ebp, eax
0x140030547  test    eax, eax
0x140030549  js      short loc_14003055C
0x14003054b  mov     [rsi], r14
0x14003054e  jmp     short loc_140030569
0x140030550  mov     ebp, 0C0000095h
0x140030555  mov     word ptr [r14+4Ah], 0FFFFh
0x14003055c  test    r14, r14
0x14003055f  jz      short loc_140030569
0x140030561  mov     rcx, r14; P
0x140030564  call    ?KerbFreeContext@@YAXPEAU_KERB_KERNEL_CONTEXT@@@Z; KerbFreeContext(_KERB_KERNEL_CONTEXT *)
0x140030569  mov     r15, [rsp+48h+var_28]
0x14003056e  mov     eax, ebp
0x140030570  mov     rbp, [rsp+48h+arg_0]
0x140030575  mov     r14, [rsp+48h+arg_18]
0x14003057a  mov     r12, [rsp+48h+arg_10]
0x14003057f  add     rsp, 28h
0x140030583  pop     r13
0x140030585  pop     rdi
0x140030586  pop     rsi
0x140030587  pop     rbx
0x140030588  retn
```
