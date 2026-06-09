# LuafvBuildTableNodeName2

- ea: `0x140024fd0`
- end: `0x14002533f`
- name: `LuafvBuildTableNodeName2`
- size: `879`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, unsigned __int16 *, char, char, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001730`
- `0x140015bb0`
- `0x14001a3c8`
- `0x14001d060`

## callees

- `0x140006080`
- `0x14001b6a0`
- `0x140024fd0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14002501e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002504d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002531f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002501e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002504d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002531f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024ffb`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002503e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400252e2`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024ffb`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002503e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400252e2`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14002502f`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140025062`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14002502f`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140025062`
- `FLTMGR!FltReleasePushLockEx` at `0x14002528f`
- `FLTMGR!FltReleasePushLockEx` at `0x1400252cf`
- `FLTMGR!FltReleasePushLockEx` at `0x14002530c`
- `FLTMGR!FltReleasePushLockEx` at `0x14002528f`
- `FLTMGR!FltReleasePushLockEx` at `0x1400252cf`
- `FLTMGR!FltReleasePushLockEx` at `0x14002530c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400252a4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400252a4`

## pseudocode

```c
__int64 __fastcall LuafvBuildTableNodeName2(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        char a5,
        char a6,
        __int64 a7)
{
  __int64 v11; // rax
  unsigned int v12; // esi
  __int16 v13; // cx
  char v14; // r8
  char v15; // r15
  char v16; // r14
  char *Pool; // rbx
  unsigned int v18; // ebx
  char *v19; // rbx
  __int64 i; // rbp
  char *v21; // rbx
  int v22; // ecx
  char v25; // [rsp+70h] [rbp+8h]
  __int64 v26; // [rsp+78h] [rbp+10h]
  char v27; // [rsp+80h] [rbp+18h]
  bool v28; // [rsp+88h] [rbp+20h]

  v26 = a2;
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
  v11 = a1;
  v12 = 0;
  while ( *(_QWORD *)(v11 + 32) && v11 != a2 )
  {
    if ( *(_QWORD *)(v11 + 248) )
    {
      v26 = v11;
      a3 = (unsigned __int16 *)(v11 + 240);
      break;
    }
    v12 += *(unsigned __int16 *)(v11 + 80) + 2;
    v11 = *(_QWORD *)(v11 + 32);
  }
  if ( a3 && *a3 )
  {
    v27 = 1;
    v12 += *a3;
    v28 = *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)*a3 >> 1) - 2) == 92;
    if ( *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)*a3 >> 1) - 2) == 92 )
      v12 -= 2;
  }
  else
  {
    v27 = 0;
    v28 = 0;
  }
  if ( !a4 || !*a4 )
  {
    v15 = 0;
    v25 = 0;
    v14 = 0;
LABEL_24:
    v16 = 0;
    goto LABEL_25;
  }
  v13 = **((_WORD **)a4 + 1);
  if ( v13 == 92 || v13 == 58 )
  {
    v15 = 1;
    v14 = 1;
  }
  else
  {
    v14 = 0;
    v15 = 1;
  }
  v25 = v14;
  if ( *(_WORD *)(*((_QWORD *)a4 + 1) + 2 * ((unsigned __int64)*a4 >> 1) - 2) != 92 )
    goto LABEL_24;
  v16 = 1;
LABEL_25:
  if ( v15 )
  {
    v12 += *a4;
    if ( !v14 )
      v12 += 2;
  }
  if ( a5 && !v16 )
    v12 += 2;
  Pool = LuafvAllocatePool(1, v12, 2);
  if ( Pool )
  {
    v19 = &Pool[v12];
    if ( a5 && !v16 )
    {
      v19 -= 2;
      *(_WORD *)v19 = 92;
    }
    if ( v15 )
    {
      v19 -= *a4;
      memmove(v19, *((const void **)a4 + 1), *a4);
      if ( !v25 )
      {
        v19 -= 2;
        *(_WORD *)v19 = 92;
      }
    }
    for ( i = a1; *(_QWORD *)(i + 32); i = *(_QWORD *)(i + 32) )
    {
      if ( i == v26 )
        break;
      v21 = &v19[-*(unsigned __int16 *)(i + 80)];
      memmove(v21, *(const void **)(i + 88), *(unsigned __int16 *)(i + 80));
      v19 = v21 - 2;
      *(_WORD *)v19 = 92;
    }
    if ( v27 )
    {
      v22 = *a3 - 2;
      if ( !v28 )
        v22 = *a3;
      v19 -= v22;
      memmove(v19, *((const void **)a3 + 1), v22);
    }
    if ( a6 )
    {
      FltReleasePushLockEx(&qword_14000F2A0, 0);
      FltAcquirePushLockExclusiveEx(&qword_14000F2A0, 0);
    }
    *(_QWORD *)(a7 + 8) = v19;
    v18 = 0;
    *(_WORD *)a7 = v12;
    *(_WORD *)(a7 + 2) = v12;
  }
  else
  {
    v18 = -1073741670;
  }
  FltReleasePushLockEx(&qword_14000F2A0, 0);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(a1 + 8) != KeGetCurrentThread() )
    goto LABEL_52;
  if ( (*(_DWORD *)(a1 + 16))-- == 1 )
  {
    *(_QWORD *)(a1 + 8) = 0;
LABEL_52:
    FltReleasePushLockEx(a1, 0);
  }
  ExReleaseFastMutex(&FastMutex);
  return v18;
}

```

## disassembly

```asm
0x140024fd0  mov     [rsp+arg_8], rdx
0x140024fd5  push    rbx
0x140024fd6  push    rbp
0x140024fd7  push    rsi
0x140024fd8  push    rdi
0x140024fd9  push    r12
0x140024fdb  push    r13
0x140024fdd  push    r14
0x140024fdf  push    r15
0x140024fe1  sub     rsp, 28h
0x140024fe5  mov     rdi, rcx
0x140024fe8  lea     rsi, FastMutex
0x140024fef  mov     rcx, rsi; FastMutex
0x140024ff2  mov     rbp, r9
0x140024ff5  mov     r13, r8
0x140024ff8  mov     rbx, rdx
0x140024ffb  call    cs:__imp_ExAcquireFastMutex
0x140025002  nop     dword ptr [rax+rax+00h]
0x140025007  mov     rax, gs:188h
0x140025010  cmp     [rdi+8], rax
0x140025014  jnz     short loc_14002501B
0x140025016  inc     dword ptr [rdi+10h]
0x140025019  jmp     short loc_14002504A
0x14002501b  mov     rcx, rsi; FastMutex
0x14002501e  call    cs:__imp_ExReleaseFastMutex
0x140025025  nop     dword ptr [rax+rax+00h]
0x14002502a  xor     edx, edx
0x14002502c  mov     rcx, rdi
0x14002502f  call    cs:__imp_FltAcquirePushLockSharedEx
0x140025036  nop     dword ptr [rax+rax+00h]
0x14002503b  mov     rcx, rsi; FastMutex
0x14002503e  call    cs:__imp_ExAcquireFastMutex
0x140025045  nop     dword ptr [rax+rax+00h]
0x14002504a  mov     rcx, rsi; FastMutex
0x14002504d  call    cs:__imp_ExReleaseFastMutex
0x140025054  nop     dword ptr [rax+rax+00h]
0x140025059  xor     edx, edx
0x14002505b  lea     rcx, qword_14000F2A0
0x140025062  call    cs:__imp_FltAcquirePushLockSharedEx
0x140025069  nop     dword ptr [rax+rax+00h]
0x14002506e  xor     r9d, r9d
0x140025071  mov     rax, rdi
0x140025074  mov     esi, r9d
0x140025077  mov     rcx, [rax+20h]
0x14002507b  test    rcx, rcx
0x14002507e  jz      short loc_1400250A8
0x140025080  cmp     rax, rbx
0x140025083  jz      short loc_1400250A8
0x140025085  cmp     [rax+0F8h], r9
0x14002508c  jnz     short loc_14002509C
0x14002508e  movzx   eax, word ptr [rax+50h]
0x140025092  add     eax, 2
0x140025095  add     esi, eax
0x140025097  mov     rax, rcx
0x14002509a  jmp     short loc_140025077
0x14002509c  mov     [rsp+68h+arg_8], rax
0x1400250a1  lea     r13, [rax+0F0h]
0x1400250a8  mov     r10d, 5Ch ; '\'
0x1400250ae  test    r13, r13
0x1400250b1  jz      short loc_1400250F2
0x1400250b3  movzx   eax, word ptr [r13+0]
0x1400250b8  test    ax, ax
0x1400250bb  jz      short loc_1400250F2
0x1400250bd  mov     ecx, eax
0x1400250bf  mov     [rsp+68h+arg_10], 1
0x1400250c7  mov     rax, [r13+8]
0x1400250cb  shr     rcx, 1
0x1400250ce  cmp     [rax+rcx*2-2], r10w
0x1400250d4  mov     cl, 1
0x1400250d6  jz      short loc_1400250DB
0x1400250d8  mov     cl, r9b
0x1400250db  movzx   eax, word ptr [r13+0]
0x1400250e0  add     esi, eax
0x1400250e2  mov     [rsp+68h+arg_18], cl
0x1400250e9  test    cl, cl
0x1400250eb  jz      short loc_140025102
0x1400250ed  add     esi, 0FFFFFFFEh
0x1400250f0  jmp     short loc_140025102
0x1400250f2  mov     [rsp+68h+arg_10], r9b
0x1400250fa  mov     [rsp+68h+arg_18], r9b
0x140025102  test    rbp, rbp
0x140025105  jz      short loc_140025154
0x140025107  cmp     [rbp+0], r9w
0x14002510c  jz      short loc_140025154
0x14002510e  mov     rax, [rbp+8]
0x140025112  movzx   ecx, word ptr [rax]
0x140025115  cmp     cx, r10w
0x140025119  jz      short loc_140025129
0x14002511b  cmp     cx, 3Ah ; ':'
0x14002511f  jz      short loc_140025129
0x140025121  mov     r8b, r9b
0x140025124  mov     r15b, 1
0x140025127  jmp     short loc_14002512F
0x140025129  mov     r15b, 1
0x14002512c  mov     r8b, r15b
0x14002512f  movzx   ecx, word ptr [rbp+0]
0x140025133  mov     eax, 8
0x140025138  mov     rdx, rbp
0x14002513b  shr     rcx, 1
0x14002513e  mov     [rsp+68h+arg_0], r8b
0x140025143  mov     rax, [rdx+rax]
0x140025147  cmp     [rax+rcx*2-2], r10w
0x14002514d  jnz     short loc_14002515F
0x14002514f  mov     r14b, 1
0x140025152  jmp     short loc_140025162
0x140025154  mov     r15b, r9b
0x140025157  mov     [rsp+68h+arg_0], r9b
0x14002515c  mov     r8b, r9b
0x14002515f  mov     r14b, r9b
0x140025162  test    r15b, r15b
0x140025165  jz      short loc_140025175
0x140025167  movzx   eax, word ptr [rbp+0]
0x14002516b  add     esi, eax
0x14002516d  test    r8b, r8b
0x140025170  jnz     short loc_140025175
0x140025172  add     esi, 2
0x140025175  mov     r12b, [rsp+68h+arg_20]
0x14002517d  test    r12b, r12b
0x140025180  jz      short loc_14002518A
0x140025182  test    r14b, r14b
0x140025185  jnz     short loc_14002518A
0x140025187  add     esi, 2
0x14002518a  mov     r8b, 2
0x14002518d  mov     edx, esi
0x14002518f  mov     ecx, 1
0x140025194  call    LuafvAllocatePool
0x140025199  mov     rbx, rax
0x14002519c  test    rax, rax
0x14002519f  jnz     short loc_1400251AE
0x1400251a1  mov     ebx, 0C000009Ah
0x1400251a6  xor     r12d, r12d
0x1400251a9  jmp     loc_1400252C6
0x1400251ae  mov     eax, esi
0x1400251b0  add     rbx, rax
0x1400251b3  test    r12b, r12b
0x1400251b6  jz      short loc_1400251CF
0x1400251b8  xor     r12d, r12d
0x1400251bb  test    r14b, r14b
0x1400251be  lea     r14d, [r12+5Ch]
0x1400251c3  jnz     short loc_1400251D7
0x1400251c5  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1400251c9  mov     [rbx], r14w
0x1400251cd  jmp     short loc_1400251D7
0x1400251cf  xor     r12d, r12d
0x1400251d2  lea     r14d, [r12+5Ch]
0x1400251d7  test    r15b, r15b
0x1400251da  jz      short loc_140025206
0x1400251dc  movzx   r8d, word ptr [rbp+0]; Size
0x1400251e1  mov     rdx, [rbp+8]; Src
0x1400251e5  mov     eax, r8d
0x1400251e8  neg     eax
0x1400251ea  cdqe
0x1400251ec  add     rbx, rax
0x1400251ef  mov     rcx, rbx; void *
0x1400251f2  call    memmove
0x1400251f7  cmp     [rsp+68h+arg_0], r12b
0x1400251fc  jnz     short loc_140025206
0x1400251fe  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140025202  mov     [rbx], r14w
0x140025206  mov     rbp, rdi
0x140025209  cmp     [rdi+20h], r12
0x14002520d  jz      short loc_140025247
0x14002520f  mov     r14, [rsp+68h+arg_8]
0x140025214  cmp     rbp, r14
0x140025217  jz      short loc_140025247
0x140025219  movzx   r8d, word ptr [rbp+50h]; Size
0x14002521e  mov     rdx, [rbp+58h]; Src
0x140025222  mov     eax, r8d
0x140025225  neg     eax
0x140025227  cdqe
0x140025229  add     rbx, rax
0x14002522c  mov     rcx, rbx; void *
0x14002522f  call    memmove
0x140025234  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140025238  mov     word ptr [rbx], 5Ch ; '\'
0x14002523d  mov     rbp, [rbp+20h]
0x140025241  cmp     [rbp+20h], r12
0x140025245  jnz     short loc_140025214
0x140025247  cmp     [rsp+68h+arg_10], r12b
0x14002524f  jz      short loc_14002527C
0x140025251  movzx   eax, word ptr [r13+0]
0x140025256  cmp     [rsp+68h+arg_18], r12b
0x14002525e  mov     rdx, [r13+8]; Src
0x140025262  lea     ecx, [rax-2]
0x140025265  cmovz   ecx, eax
0x140025268  mov     eax, ecx
0x14002526a  movsxd  r8, ecx; Size
0x14002526d  neg     eax
0x14002526f  cdqe
0x140025271  add     rbx, rax
0x140025274  mov     rcx, rbx; void *
0x140025277  call    memmove
0x14002527c  cmp     [rsp+68h+arg_28], r12b
0x140025284  jz      short loc_1400252B0
0x140025286  xor     edx, edx
0x140025288  lea     rcx, qword_14000F2A0
0x14002528f  call    cs:__imp_FltReleasePushLockEx
0x140025296  nop     dword ptr [rax+rax+00h]
0x14002529b  xor     edx, edx
0x14002529d  lea     rcx, qword_14000F2A0
0x1400252a4  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400252ab  nop     dword ptr [rax+rax+00h]
0x1400252b0  mov     rax, [rsp+68h+arg_30]
0x1400252b8  mov     [rax+8], rbx
0x1400252bc  mov     ebx, r12d
0x1400252bf  mov     [rax], si
0x1400252c2  mov     [rax+2], si
0x1400252c6  xor     edx, edx
0x1400252c8  lea     rcx, qword_14000F2A0
0x1400252cf  call    cs:__imp_FltReleasePushLockEx
0x1400252d6  nop     dword ptr [rax+rax+00h]
0x1400252db  lea     rcx, FastMutex; FastMutex
0x1400252e2  call    cs:__imp_ExAcquireFastMutex
0x1400252e9  nop     dword ptr [rax+rax+00h]
0x1400252ee  mov     rax, gs:188h
0x1400252f7  cmp     [rdi+8], rax
0x1400252fb  jnz     short loc_140025307
0x1400252fd  sub     dword ptr [rdi+10h], 1
0x140025301  jnz     short loc_140025318
0x140025303  mov     [rdi+8], r12
0x140025307  xor     edx, edx
0x140025309  mov     rcx, rdi
0x14002530c  call    cs:__imp_FltReleasePushLockEx
0x140025313  nop     dword ptr [rax+rax+00h]
0x140025318  lea     rcx, FastMutex; FastMutex
0x14002531f  call    cs:__imp_ExReleaseFastMutex
0x140025326  nop     dword ptr [rax+rax+00h]
0x14002532b  mov     eax, ebx
0x14002532d  add     rsp, 28h
0x140025331  pop     r15
0x140025333  pop     r14
0x140025335  pop     r13
0x140025337  pop     r12
0x140025339  pop     rdi
0x14002533a  pop     rsi
0x14002533b  pop     rbp
0x14002533c  pop     rbx
0x14002533d  retn
```
