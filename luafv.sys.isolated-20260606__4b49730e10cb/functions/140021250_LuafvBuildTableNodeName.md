# LuafvBuildTableNodeName

- ea: `0x140021250`
- end: `0x1400216e4`
- name: `LuafvBuildTableNodeName`
- size: `1172`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001730`
- `0x140015bb0`
- `0x14001a3c8`
- `0x14001d060`

## callees

- `0x140006080`
- `0x140021250`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400215e3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400215e3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400212a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400212e0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021478`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400212a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400212e0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021478`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021283`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400212cd`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021423`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021283`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400212cd`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021423`
- `ntoskrnl!ExAllocatePool2` at `0x1400214a9`
- `ntoskrnl!ExAllocatePool2` at `0x1400214a9`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400212ba`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400212f5`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400212ba`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400212f5`
- `FLTMGR!FltReleasePushLockEx` at `0x140021410`
- `FLTMGR!FltReleasePushLockEx` at `0x140021465`
- `FLTMGR!FltReleasePushLockEx` at `0x1400214ec`
- `FLTMGR!FltReleasePushLockEx` at `0x140021410`
- `FLTMGR!FltReleasePushLockEx` at `0x140021465`
- `FLTMGR!FltReleasePushLockEx` at `0x1400214ec`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400214d1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400214d1`

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
  FltAcquirePushLockSharedEx(&qword_14000F2A0, 0);
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
        dword_14000F2FC += v10,
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
  FltReleasePushLockEx(&qword_14000F2A0, 0);
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
0x140021250  push    rbx
0x140021252  push    rsi
0x140021253  sub     rsp, 58h
0x140021257  mov     [rsp+68h+arg_8], rbp
0x14002125c  mov     rsi, rcx
0x14002125f  mov     [rsp+68h+var_18], rdi
0x140021264  lea     rcx, FastMutex; FastMutex
0x14002126b  mov     [rsp+68h+var_20], r12
0x140021270  mov     rbp, r9
0x140021273  mov     [rsp+68h+var_28], r13
0x140021278  mov     r12, rdx
0x14002127b  mov     [rsp+68h+var_30], r14
0x140021280  mov     r14, r8
0x140021283  call    cs:__imp_ExAcquireFastMutex
0x14002128a  nop     dword ptr [rax+rax+00h]
0x14002128f  mov     rax, gs:188h
0x140021298  cmp     [rsi+8], rax
0x14002129c  jz      loc_14002169C
0x1400212a2  lea     rcx, FastMutex; FastMutex
0x1400212a9  call    cs:__imp_ExReleaseFastMutex
0x1400212b0  nop     dword ptr [rax+rax+00h]
0x1400212b5  xor     edx, edx
0x1400212b7  mov     rcx, rsi
0x1400212ba  call    cs:__imp_FltAcquirePushLockSharedEx
0x1400212c1  nop     dword ptr [rax+rax+00h]
0x1400212c6  lea     rcx, FastMutex; FastMutex
0x1400212cd  call    cs:__imp_ExAcquireFastMutex
0x1400212d4  nop     dword ptr [rax+rax+00h]
0x1400212d9  lea     rcx, FastMutex; FastMutex
0x1400212e0  call    cs:__imp_ExReleaseFastMutex
0x1400212e7  nop     dword ptr [rax+rax+00h]
0x1400212ec  xor     edx, edx
0x1400212ee  lea     rcx, qword_14000F2A0
0x1400212f5  call    cs:__imp_FltAcquirePushLockSharedEx
0x1400212fc  nop     dword ptr [rax+rax+00h]
0x140021301  xor     edi, edi
0x140021303  mov     rax, rsi
0x140021306  mov     rdx, [rax+20h]
0x14002130a  mov     r8d, edi
0x14002130d  test    rdx, rdx
0x140021310  jz      short loc_14002132F
0x140021312  cmp     rax, r12
0x140021315  jz      short loc_14002132F
0x140021317  cmp     qword ptr [rax+0F8h], 0
0x14002131f  jz      loc_140021619
0x140021325  mov     r12, rax
0x140021328  lea     r14, [rax+0F0h]
0x14002132f  test    r14, r14
0x140021332  jz      loc_140021669
0x140021338  movzx   eax, word ptr [r14]
0x14002133c  test    ax, ax
0x14002133f  jz      loc_140021669
0x140021345  movzx   edi, word ptr [r14]
0x140021349  mov     ecx, eax
0x14002134b  mov     rax, [r14+8]
0x14002134f  shr     rcx, 1
0x140021352  mov     [rsp+68h+arg_18], 1
0x14002135a  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140021360  jnz     loc_14002167B
0x140021366  add     edi, 0FFFFFFFEh
0x140021369  mov     [rsp+68h+var_48], 1
0x14002136e  add     edi, r8d
0x140021371  test    rbp, rbp
0x140021374  jz      loc_140021606
0x14002137a  cmp     word ptr [rbp+0], 0
0x14002137f  jz      loc_140021606
0x140021385  mov     rax, [rbp+8]
0x140021389  movzx   ecx, word ptr [rax]
0x14002138c  cmp     cx, 5Ch ; '\'
0x140021390  jnz     loc_1400216A4
0x140021396  mov     r13b, 1
0x140021399  movzx   r8d, r13b
0x14002139d  movzx   ecx, word ptr [rbp+0]
0x1400213a1  mov     eax, 8
0x1400213a6  mov     rdx, rbp
0x1400213a9  shr     rcx, 1
0x1400213ac  mov     [rsp+68h+arg_10], r8b
0x1400213b4  mov     rax, [rdx+rax]
0x1400213b8  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400213be  jz      loc_140021695
0x1400213c4  xor     al, al
0x1400213c6  mov     [rsp+68h+arg_0], al
0x1400213ca  test    r13b, r13b
0x1400213cd  jz      short loc_1400213E3
0x1400213cf  movzx   eax, word ptr [rbp+0]
0x1400213d3  add     edi, eax
0x1400213d5  movzx   eax, [rsp+68h+arg_0]
0x1400213da  test    r8b, r8b
0x1400213dd  jz      loc_140021661
0x1400213e3  cmp     [rsp+68h+arg_20], 0
0x1400213eb  jnz     loc_1400216B9
0x1400213f1  lea     eax, [rdi+8]
0x1400213f4  mov     [rsp+68h+var_38], r15
0x1400213f9  cmp     eax, 8
0x1400213fc  jnb     loc_14002148E
0x140021402  mov     ebx, 0C000009Ah
0x140021407  xor     edx, edx
0x140021409  lea     rcx, qword_14000F2A0
0x140021410  call    cs:__imp_FltReleasePushLockEx
0x140021417  nop     dword ptr [rax+rax+00h]
0x14002141c  lea     rcx, FastMutex; FastMutex
0x140021423  call    cs:__imp_ExAcquireFastMutex
0x14002142a  nop     dword ptr [rax+rax+00h]
0x14002142f  mov     rax, gs:188h
0x140021438  mov     r15, [rsp+68h+var_38]
0x14002143d  mov     r14, [rsp+68h+var_30]
0x140021442  mov     r13, [rsp+68h+var_28]
0x140021447  mov     r12, [rsp+68h+var_20]
0x14002144c  mov     rdi, [rsp+68h+var_18]
0x140021451  mov     rbp, [rsp+68h+arg_8]
0x140021456  cmp     [rsi+8], rax
0x14002145a  jz      loc_1400215A7
0x140021460  xor     edx, edx
0x140021462  mov     rcx, rsi
0x140021465  call    cs:__imp_FltReleasePushLockEx
0x14002146c  nop     dword ptr [rax+rax+00h]
0x140021471  lea     rcx, FastMutex; FastMutex
0x140021478  call    cs:__imp_ExReleaseFastMutex
0x14002147f  nop     dword ptr [rax+rax+00h]
0x140021484  mov     eax, ebx
0x140021486  add     rsp, 58h
0x14002148a  pop     rsi
0x14002148b  pop     rbx
0x14002148c  retn
0x14002148e  cmp     edi, 0B8h
0x140021494  jbe     loc_1400215BE
0x14002149a  mov     bl, 0FFh
0x14002149c  mov     edx, eax
0x14002149e  mov     ecx, 100h
0x1400214a3  mov     r8d, 6661754Ch
0x1400214a9  call    cs:__imp_ExAllocatePool2
0x1400214b0  nop     dword ptr [rax+rax+00h]
0x1400214b5  mov     r15, rax
0x1400214b8  test    r15, r15
0x1400214bb  jz      loc_140021402
0x1400214c1  xor     edx, edx
0x1400214c3  mov     [r15], edi
0x1400214c6  lea     rcx, PoolLock
0x1400214cd  mov     [r15+4], bl
0x1400214d1  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400214d8  nop     dword ptr [rax+rax+00h]
0x1400214dd  add     cs:dword_14000F2FC, edi
0x1400214e3  lea     rcx, PoolLock
0x1400214ea  xor     edx, edx
0x1400214ec  call    cs:__imp_FltReleasePushLockEx
0x1400214f3  nop     dword ptr [rax+rax+00h]
0x1400214f8  add     r15, 8
0x1400214fc  jz      loc_140021402
0x140021502  mov     ebx, edi
0x140021504  add     rbx, r15
0x140021507  mov     r15d, 5Ch ; '\'
0x14002150d  cmp     [rsp+68h+arg_20], 0
0x140021515  jnz     loc_1400216C9
0x14002151b  test    r13b, r13b
0x14002151e  jz      short loc_140021549
0x140021520  movzx   r8d, word ptr [rbp+0]; Size
0x140021525  mov     rdx, [rbp+8]; Src
0x140021529  mov     eax, r8d
0x14002152c  neg     eax
0x14002152e  cdqe
0x140021530  add     rbx, rax
0x140021533  mov     rcx, rbx; void *
0x140021536  call    memmove
0x14002153b  cmp     [rsp+68h+arg_10], 0
0x140021543  jz      loc_140021688
0x140021549  cmp     qword ptr [rsi+20h], 0
0x14002154e  mov     rbp, rsi
0x140021551  jz      short loc_14002155C
0x140021553  cmp     rbp, r12
0x140021556  jnz     loc_14002162A
0x14002155c  cmp     [rsp+68h+arg_18], 0
0x140021564  jz      short loc_14002158D
0x140021566  movzx   eax, word ptr [r14]
0x14002156a  cmp     [rsp+68h+var_48], 0
0x14002156f  mov     rdx, [r14+8]; Src
0x140021573  lea     ecx, [rax-2]
0x140021576  cmovz   ecx, eax
0x140021579  mov     eax, ecx
0x14002157b  movsxd  r8, ecx; Size
0x14002157e  neg     eax
0x140021580  cdqe
0x140021582  add     rbx, rax
0x140021585  mov     rcx, rbx; void *
0x140021588  call    memmove
0x14002158d  mov     rax, [rsp+68h+arg_28]
0x140021595  mov     [rax+8], rbx
0x140021599  xor     ebx, ebx
0x14002159b  mov     [rax], di
0x14002159e  mov     [rax+2], di
0x1400215a2  jmp     loc_140021407
0x1400215a7  sub     dword ptr [rsi+10h], 1
0x1400215ab  jnz     loc_140021471
0x1400215b1  mov     qword ptr [rsi+8], 0
0x1400215b9  jmp     loc_140021460
0x1400215be  xor     ebx, ebx
0x1400215c0  mov     eax, 38h ; '8'
0x1400215c5  cmp     edi, eax
0x1400215c7  jbe     short loc_1400215D3
0x1400215c9  inc     ebx
0x1400215cb  add     eax, 20h ; ' '
0x1400215ce  cmp     ebx, 5
0x1400215d1  jb      short loc_1400215C5
0x1400215d3  lea     rax, StringLookaside
0x1400215da  mov     ecx, ebx
0x1400215dc  shl     rcx, 7
0x1400215e0  add     rcx, rax; Lookaside
0x1400215e3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400215ea  nop     dword ptr [rax+rax+00h]
0x1400215ef  add     bl, 2
0x1400215f2  mov     r15, rax
0x1400215f5  cmp     bl, 0FFh
0x1400215f8  jnz     loc_1400214B8
0x1400215fe  lea     eax, [rdi+8]
0x140021601  jmp     loc_14002149C
0x140021606  xor     r13b, r13b
0x140021609  xor     r8b, r8b
0x14002160c  mov     [rsp+68h+arg_10], r8b
0x140021614  jmp     loc_1400213C4
0x140021619  movzx   ecx, word ptr [rax+50h]
0x14002161d  add     edi, 2
0x140021620  add     edi, ecx
0x140021622  mov     rax, rdx
0x140021625  jmp     loc_140021306
0x14002162a  movzx   r8d, word ptr [rbp+50h]; Size
0x14002162f  mov     rdx, [rbp+58h]; Src
0x140021633  mov     eax, r8d
0x140021636  neg     eax
0x140021638  cdqe
0x14002163a  add     rbx, rax
0x14002163d  mov     rcx, rbx; void *
0x140021640  call    memmove
0x140021645  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140021649  mov     [rbx], r15w
0x14002164d  mov     rbp, [rbp+20h]
0x140021651  cmp     qword ptr [rbp+20h], 0
0x140021656  jnz     loc_140021553
0x14002165c  jmp     loc_14002155C
0x140021661  add     edi, 2
0x140021664  jmp     loc_1400213E3
0x140021669  mov     [rsp+68h+arg_18], 0
0x140021671  mov     [rsp+68h+var_48], 0
0x140021676  jmp     loc_140021371
0x14002167b  add     edi, r8d
0x14002167e  mov     [rsp+68h+var_48], 0
0x140021683  jmp     loc_140021371
0x140021688  add     rbx, 0FFFFFFFFFFFFFFFEh
0x14002168c  mov     [rbx], r15w
0x140021690  jmp     loc_140021549
0x140021695  mov     al, 1
0x140021697  jmp     loc_1400213C6
0x14002169c  inc     dword ptr [rsi+10h]
0x14002169f  jmp     loc_1400212D9
0x1400216a4  cmp     cx, 3Ah ; ':'
0x1400216a8  jz      loc_140021396
0x1400216ae  xor     r8b, r8b
0x1400216b1  mov     r13b, 1
0x1400216b4  jmp     loc_14002139D
0x1400216b9  test    al, al
0x1400216bb  jnz     loc_1400213F1
0x1400216c1  add     edi, 2
0x1400216c4  jmp     loc_1400213F1
0x1400216c9  cmp     [rsp+68h+arg_0], 0
0x1400216ce  jnz     loc_14002151B
0x1400216d4  lea     rax, [rbx-2]
0x1400216d8  mov     rbx, rax
0x1400216db  mov     [rax], r15w
0x1400216df  jmp     loc_14002151B
```
