# LuafvBuildTableNodeName

- ea: `0x140021200`
- end: `0x140021694`
- name: `LuafvBuildTableNodeName`
- size: `1172`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, unsigned __int16 *, char, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001730`
- `0x140015bb0`
- `0x14001a378`
- `0x14001d010`

## callees

- `0x140005d00`
- `0x140021200`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140021593`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140021593`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021259`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021290`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021428`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021259`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021290`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021428`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021233`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002127d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400213d3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021233`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002127d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400213d3`
- `ntoskrnl!ExAllocatePool2` at `0x140021459`
- `ntoskrnl!ExAllocatePool2` at `0x140021459`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14002126a`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400212a5`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14002126a`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400212a5`
- `FLTMGR!FltReleasePushLockEx` at `0x1400213c0`
- `FLTMGR!FltReleasePushLockEx` at `0x140021415`
- `FLTMGR!FltReleasePushLockEx` at `0x14002149c`
- `FLTMGR!FltReleasePushLockEx` at `0x1400213c0`
- `FLTMGR!FltReleasePushLockEx` at `0x140021415`
- `FLTMGR!FltReleasePushLockEx` at `0x14002149c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021481`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021481`

## pseudocode

```c
__int64 __fastcall LuafvBuildTableNodeName(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        char a5,
        __int64 a6)
{
  unsigned int v10; // edi
  __int64 i; // rax
  unsigned int v12; // r8d
  int v13; // edi
  __int16 v14; // cx
  char v15; // r13
  char v16; // r8
  char v17; // al
  unsigned int v18; // eax
  unsigned int v19; // ebx
  char v21; // bl
  __int64 Pool2; // r15
  __int64 v23; // r15
  char *v24; // rbx
  __int64 j; // rbp
  int v26; // ecx
  unsigned int v28; // ebx
  unsigned int v29; // eax
  PVOID v30; // rax
  char *v31; // rbx
  char v32; // [rsp+20h] [rbp-48h]
  char v33; // [rsp+70h] [rbp+8h]
  char v34; // [rsp+80h] [rbp+18h]
  char v35; // [rsp+88h] [rbp+20h]

  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(a1 + 8) == KeGetCurrentThread() )
  {
    ++*(_DWORD *)(a1 + 16);
  }
  else
  {
    ExReleaseFastMutex(&FastMutex);
    FltAcquirePushLockSharedEx(a1, 0);
    ExAcquireFastMutex(&FastMutex);
  }
  ExReleaseFastMutex(&FastMutex);
  FltAcquirePushLockSharedEx(&qword_14000EC60, 0);
  v10 = 0;
  for ( i = a1; ; i = *(_QWORD *)(i + 32) )
  {
    v12 = v10;
    if ( !*(_QWORD *)(i + 32) || i == a2 )
      break;
    if ( *(_QWORD *)(i + 248) )
    {
      a2 = i;
      a3 = (unsigned __int16 *)(i + 240);
      break;
    }
    v10 += *(unsigned __int16 *)(i + 80) + 2;
  }
  if ( a3 && *a3 )
  {
    v13 = *a3;
    v35 = 1;
    if ( *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)*a3 >> 1) - 2) == 92 )
    {
      v32 = 1;
      v10 = v12 + v13 - 2;
    }
    else
    {
      v10 = v12 + v13;
      v32 = 0;
    }
  }
  else
  {
    v35 = 0;
    v32 = 0;
  }
  if ( a4 && *a4 )
  {
    v14 = **((_WORD **)a4 + 1);
    if ( v14 == 92 || v14 == 58 )
    {
      v15 = 1;
      v16 = 1;
    }
    else
    {
      v16 = 0;
      v15 = 1;
    }
    v34 = v16;
    if ( *(_WORD *)(*((_QWORD *)a4 + 1) + 2 * ((unsigned __int64)*a4 >> 1) - 2) == 92 )
    {
      v17 = 1;
      goto LABEL_18;
    }
  }
  else
  {
    v15 = 0;
    v16 = 0;
    v34 = 0;
  }
  v17 = 0;
LABEL_18:
  v33 = v17;
  if ( v15 )
  {
    v10 += *a4;
    if ( !v16 )
      v10 += 2;
  }
  if ( a5 && !v17 )
    v10 += 2;
  v18 = v10 + 8;
  if ( v10 + 8 < 8 )
    goto LABEL_23;
  if ( v10 > 0xB8 )
  {
    v21 = -1;
LABEL_29:
    Pool2 = ExAllocatePool2(256, v18, 1717663052);
    goto LABEL_30;
  }
  v28 = 0;
  v29 = 56;
  do
  {
    if ( v10 <= v29 )
      break;
    ++v28;
    v29 += 32;
  }
  while ( v28 < 5 );
  v30 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&StringLookaside[16 * (unsigned __int64)v28]);
  v21 = v28 + 2;
  Pool2 = (__int64)v30;
  if ( v21 == -1 )
  {
    v18 = v10 + 8;
    goto LABEL_29;
  }
LABEL_30:
  if ( !Pool2
    || (*(_DWORD *)Pool2 = v10,
        *(_BYTE *)(Pool2 + 4) = v21,
        FltAcquirePushLockExclusiveEx(&PoolLock, 0),
        dword_14000ECBC += v10,
        FltReleasePushLockEx(&PoolLock, 0),
        (v23 = Pool2 + 8) == 0) )
  {
LABEL_23:
    v19 = -1073741670;
    goto LABEL_24;
  }
  v24 = (char *)(v23 + v10);
  if ( a5 && !v33 )
  {
    v24 -= 2;
    *(_WORD *)v24 = 92;
  }
  if ( v15 )
  {
    v24 -= *a4;
    memmove(v24, *((const void **)a4 + 1), *a4);
    if ( !v34 )
    {
      v24 -= 2;
      *(_WORD *)v24 = 92;
    }
  }
  for ( j = a1; *(_QWORD *)(j + 32); j = *(_QWORD *)(j + 32) )
  {
    if ( j == a2 )
      break;
    v31 = &v24[-*(unsigned __int16 *)(j + 80)];
    memmove(v31, *(const void **)(j + 88), *(unsigned __int16 *)(j + 80));
    v24 = v31 - 2;
    *(_WORD *)v24 = 92;
  }
  if ( v35 )
  {
    v26 = *a3 - 2;
    if ( !v32 )
      v26 = *a3;
    v24 -= v26;
    memmove(v24, *((const void **)a3 + 1), v26);
  }
  *(_QWORD *)(a6 + 8) = v24;
  v19 = 0;
  *(_WORD *)a6 = v10;
  *(_WORD *)(a6 + 2) = v10;
LABEL_24:
  FltReleasePushLockEx(&qword_14000EC60, 0);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(a1 + 8) == KeGetCurrentThread() )
  {
    if ( (*(_DWORD *)(a1 + 16))-- != 1 )
      goto LABEL_26;
    *(_QWORD *)(a1 + 8) = 0;
  }
  FltReleasePushLockEx(a1, 0);
LABEL_26:
  ExReleaseFastMutex(&FastMutex);
  return v19;
}

```

## disassembly

```asm
0x140021200  push    rbx
0x140021202  push    rsi
0x140021203  sub     rsp, 58h
0x140021207  mov     [rsp+68h+arg_8], rbp
0x14002120c  mov     rsi, rcx
0x14002120f  mov     [rsp+68h+var_18], rdi
0x140021214  lea     rcx, FastMutex; FastMutex
0x14002121b  mov     [rsp+68h+var_20], r12
0x140021220  mov     rbp, r9
0x140021223  mov     [rsp+68h+var_28], r13
0x140021228  mov     r12, rdx
0x14002122b  mov     [rsp+68h+var_30], r14
0x140021230  mov     r14, r8
0x140021233  call    cs:__imp_ExAcquireFastMutex
0x14002123a  nop     dword ptr [rax+rax+00h]
0x14002123f  mov     rax, gs:188h
0x140021248  cmp     [rsi+8], rax
0x14002124c  jz      loc_14002164C
0x140021252  lea     rcx, FastMutex; FastMutex
0x140021259  call    cs:__imp_ExReleaseFastMutex
0x140021260  nop     dword ptr [rax+rax+00h]
0x140021265  xor     edx, edx
0x140021267  mov     rcx, rsi
0x14002126a  call    cs:__imp_FltAcquirePushLockSharedEx
0x140021271  nop     dword ptr [rax+rax+00h]
0x140021276  lea     rcx, FastMutex; FastMutex
0x14002127d  call    cs:__imp_ExAcquireFastMutex
0x140021284  nop     dword ptr [rax+rax+00h]
0x140021289  lea     rcx, FastMutex; FastMutex
0x140021290  call    cs:__imp_ExReleaseFastMutex
0x140021297  nop     dword ptr [rax+rax+00h]
0x14002129c  xor     edx, edx
0x14002129e  lea     rcx, qword_14000EC60
0x1400212a5  call    cs:__imp_FltAcquirePushLockSharedEx
0x1400212ac  nop     dword ptr [rax+rax+00h]
0x1400212b1  xor     edi, edi
0x1400212b3  mov     rax, rsi
0x1400212b6  mov     rdx, [rax+20h]
0x1400212ba  mov     r8d, edi
0x1400212bd  test    rdx, rdx
0x1400212c0  jz      short loc_1400212DF
0x1400212c2  cmp     rax, r12
0x1400212c5  jz      short loc_1400212DF
0x1400212c7  cmp     qword ptr [rax+0F8h], 0
0x1400212cf  jz      loc_1400215C9
0x1400212d5  mov     r12, rax
0x1400212d8  lea     r14, [rax+0F0h]
0x1400212df  test    r14, r14
0x1400212e2  jz      loc_140021619
0x1400212e8  movzx   eax, word ptr [r14]
0x1400212ec  test    ax, ax
0x1400212ef  jz      loc_140021619
0x1400212f5  movzx   edi, word ptr [r14]
0x1400212f9  mov     ecx, eax
0x1400212fb  mov     rax, [r14+8]
0x1400212ff  shr     rcx, 1
0x140021302  mov     [rsp+68h+arg_18], 1
0x14002130a  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140021310  jnz     loc_14002162B
0x140021316  add     edi, 0FFFFFFFEh
0x140021319  mov     [rsp+68h+var_48], 1
0x14002131e  add     edi, r8d
0x140021321  test    rbp, rbp
0x140021324  jz      loc_1400215B6
0x14002132a  cmp     word ptr [rbp+0], 0
0x14002132f  jz      loc_1400215B6
0x140021335  mov     rax, [rbp+8]
0x140021339  movzx   ecx, word ptr [rax]
0x14002133c  cmp     cx, 5Ch ; '\'
0x140021340  jnz     loc_140021654
0x140021346  mov     r13b, 1
0x140021349  movzx   r8d, r13b
0x14002134d  movzx   ecx, word ptr [rbp+0]
0x140021351  mov     eax, 8
0x140021356  mov     rdx, rbp
0x140021359  shr     rcx, 1
0x14002135c  mov     [rsp+68h+arg_10], r8b
0x140021364  mov     rax, [rdx+rax]
0x140021368  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14002136e  jz      loc_140021645
0x140021374  xor     al, al
0x140021376  mov     [rsp+68h+arg_0], al
0x14002137a  test    r13b, r13b
0x14002137d  jz      short loc_140021393
0x14002137f  movzx   eax, word ptr [rbp+0]
0x140021383  add     edi, eax
0x140021385  movzx   eax, [rsp+68h+arg_0]
0x14002138a  test    r8b, r8b
0x14002138d  jz      loc_140021611
0x140021393  cmp     [rsp+68h+arg_20], 0
0x14002139b  jnz     loc_140021669
0x1400213a1  lea     eax, [rdi+8]
0x1400213a4  mov     [rsp+68h+var_38], r15
0x1400213a9  cmp     eax, 8
0x1400213ac  jnb     loc_14002143E
0x1400213b2  mov     ebx, 0C000009Ah
0x1400213b7  xor     edx, edx
0x1400213b9  lea     rcx, qword_14000EC60
0x1400213c0  call    cs:__imp_FltReleasePushLockEx
0x1400213c7  nop     dword ptr [rax+rax+00h]
0x1400213cc  lea     rcx, FastMutex; FastMutex
0x1400213d3  call    cs:__imp_ExAcquireFastMutex
0x1400213da  nop     dword ptr [rax+rax+00h]
0x1400213df  mov     rax, gs:188h
0x1400213e8  mov     r15, [rsp+68h+var_38]
0x1400213ed  mov     r14, [rsp+68h+var_30]
0x1400213f2  mov     r13, [rsp+68h+var_28]
0x1400213f7  mov     r12, [rsp+68h+var_20]
0x1400213fc  mov     rdi, [rsp+68h+var_18]
0x140021401  mov     rbp, [rsp+68h+arg_8]
0x140021406  cmp     [rsi+8], rax
0x14002140a  jz      loc_140021557
0x140021410  xor     edx, edx
0x140021412  mov     rcx, rsi
0x140021415  call    cs:__imp_FltReleasePushLockEx
0x14002141c  nop     dword ptr [rax+rax+00h]
0x140021421  lea     rcx, FastMutex; FastMutex
0x140021428  call    cs:__imp_ExReleaseFastMutex
0x14002142f  nop     dword ptr [rax+rax+00h]
0x140021434  mov     eax, ebx
0x140021436  add     rsp, 58h
0x14002143a  pop     rsi
0x14002143b  pop     rbx
0x14002143c  retn
0x14002143e  cmp     edi, 0B8h
0x140021444  jbe     loc_14002156E
0x14002144a  mov     bl, 0FFh
0x14002144c  mov     edx, eax
0x14002144e  mov     ecx, 100h
0x140021453  mov     r8d, 6661754Ch
0x140021459  call    cs:__imp_ExAllocatePool2
0x140021460  nop     dword ptr [rax+rax+00h]
0x140021465  mov     r15, rax
0x140021468  test    r15, r15
0x14002146b  jz      loc_1400213B2
0x140021471  xor     edx, edx
0x140021473  mov     [r15], edi
0x140021476  lea     rcx, PoolLock
0x14002147d  mov     [r15+4], bl
0x140021481  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021488  nop     dword ptr [rax+rax+00h]
0x14002148d  add     cs:dword_14000ECBC, edi
0x140021493  lea     rcx, PoolLock
0x14002149a  xor     edx, edx
0x14002149c  call    cs:__imp_FltReleasePushLockEx
0x1400214a3  nop     dword ptr [rax+rax+00h]
0x1400214a8  add     r15, 8
0x1400214ac  jz      loc_1400213B2
0x1400214b2  mov     ebx, edi
0x1400214b4  add     rbx, r15
0x1400214b7  mov     r15d, 5Ch ; '\'
0x1400214bd  cmp     [rsp+68h+arg_20], 0
0x1400214c5  jnz     loc_140021679
0x1400214cb  test    r13b, r13b
0x1400214ce  jz      short loc_1400214F9
0x1400214d0  movzx   r8d, word ptr [rbp+0]; Size
0x1400214d5  mov     rdx, [rbp+8]; Src
0x1400214d9  mov     eax, r8d
0x1400214dc  neg     eax
0x1400214de  cdqe
0x1400214e0  add     rbx, rax
0x1400214e3  mov     rcx, rbx; void *
0x1400214e6  call    memmove
0x1400214eb  cmp     [rsp+68h+arg_10], 0
0x1400214f3  jz      loc_140021638
0x1400214f9  cmp     qword ptr [rsi+20h], 0
0x1400214fe  mov     rbp, rsi
0x140021501  jz      short loc_14002150C
0x140021503  cmp     rbp, r12
0x140021506  jnz     loc_1400215DA
0x14002150c  cmp     [rsp+68h+arg_18], 0
0x140021514  jz      short loc_14002153D
0x140021516  movzx   eax, word ptr [r14]
0x14002151a  cmp     [rsp+68h+var_48], 0
0x14002151f  mov     rdx, [r14+8]; Src
0x140021523  lea     ecx, [rax-2]
0x140021526  cmovz   ecx, eax
0x140021529  mov     eax, ecx
0x14002152b  movsxd  r8, ecx; Size
0x14002152e  neg     eax
0x140021530  cdqe
0x140021532  add     rbx, rax
0x140021535  mov     rcx, rbx; void *
0x140021538  call    memmove
0x14002153d  mov     rax, [rsp+68h+arg_28]
0x140021545  mov     [rax+8], rbx
0x140021549  xor     ebx, ebx
0x14002154b  mov     [rax], di
0x14002154e  mov     [rax+2], di
0x140021552  jmp     loc_1400213B7
0x140021557  sub     dword ptr [rsi+10h], 1
0x14002155b  jnz     loc_140021421
0x140021561  mov     qword ptr [rsi+8], 0
0x140021569  jmp     loc_140021410
0x14002156e  xor     ebx, ebx
0x140021570  mov     eax, 38h ; '8'
0x140021575  cmp     edi, eax
0x140021577  jbe     short loc_140021583
0x140021579  inc     ebx
0x14002157b  add     eax, 20h ; ' '
0x14002157e  cmp     ebx, 5
0x140021581  jb      short loc_140021575
0x140021583  lea     rax, StringLookaside
0x14002158a  mov     ecx, ebx
0x14002158c  shl     rcx, 7
0x140021590  add     rcx, rax; Lookaside
0x140021593  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002159a  nop     dword ptr [rax+rax+00h]
0x14002159f  add     bl, 2
0x1400215a2  mov     r15, rax
0x1400215a5  cmp     bl, 0FFh
0x1400215a8  jnz     loc_140021468
0x1400215ae  lea     eax, [rdi+8]
0x1400215b1  jmp     loc_14002144C
0x1400215b6  xor     r13b, r13b
0x1400215b9  xor     r8b, r8b
0x1400215bc  mov     [rsp+68h+arg_10], r8b
0x1400215c4  jmp     loc_140021374
0x1400215c9  movzx   ecx, word ptr [rax+50h]
0x1400215cd  add     edi, 2
0x1400215d0  add     edi, ecx
0x1400215d2  mov     rax, rdx
0x1400215d5  jmp     loc_1400212B6
0x1400215da  movzx   r8d, word ptr [rbp+50h]; Size
0x1400215df  mov     rdx, [rbp+58h]; Src
0x1400215e3  mov     eax, r8d
0x1400215e6  neg     eax
0x1400215e8  cdqe
0x1400215ea  add     rbx, rax
0x1400215ed  mov     rcx, rbx; void *
0x1400215f0  call    memmove
0x1400215f5  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1400215f9  mov     [rbx], r15w
0x1400215fd  mov     rbp, [rbp+20h]
0x140021601  cmp     qword ptr [rbp+20h], 0
0x140021606  jnz     loc_140021503
0x14002160c  jmp     loc_14002150C
0x140021611  add     edi, 2
0x140021614  jmp     loc_140021393
0x140021619  mov     [rsp+68h+arg_18], 0
0x140021621  mov     [rsp+68h+var_48], 0
0x140021626  jmp     loc_140021321
0x14002162b  add     edi, r8d
0x14002162e  mov     [rsp+68h+var_48], 0
0x140021633  jmp     loc_140021321
0x140021638  add     rbx, 0FFFFFFFFFFFFFFFEh
0x14002163c  mov     [rbx], r15w
0x140021640  jmp     loc_1400214F9
0x140021645  mov     al, 1
0x140021647  jmp     loc_140021376
0x14002164c  inc     dword ptr [rsi+10h]
0x14002164f  jmp     loc_140021289
0x140021654  cmp     cx, 3Ah ; ':'
0x140021658  jz      loc_140021346
0x14002165e  xor     r8b, r8b
0x140021661  mov     r13b, 1
0x140021664  jmp     loc_14002134D
0x140021669  test    al, al
0x14002166b  jnz     loc_1400213A1
0x140021671  add     edi, 2
0x140021674  jmp     loc_1400213A1
0x140021679  cmp     [rsp+68h+arg_0], 0
0x14002167e  jnz     loc_1400214CB
0x140021684  lea     rax, [rbx-2]
0x140021688  mov     rbx, rax
0x14002168b  mov     [rax], r15w
0x14002168f  jmp     loc_1400214CB
```
