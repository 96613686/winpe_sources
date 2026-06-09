# LuafvBuildTableNodeName2

- ea: `0x140024f80`
- end: `0x1400252ef`
- name: `LuafvBuildTableNodeName2`
- size: `879`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, unsigned __int16 *, char, char, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001730`
- `0x140015bb0`
- `0x14001a378`
- `0x14001d010`

## callees

- `0x140005d00`
- `0x14001b650`
- `0x140024f80`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140024fce`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024ffd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400252cf`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024fce`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024ffd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400252cf`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024fab`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024fee`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025292`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024fab`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024fee`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025292`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140024fdf`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140025012`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140024fdf`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140025012`
- `FLTMGR!FltReleasePushLockEx` at `0x14002523f`
- `FLTMGR!FltReleasePushLockEx` at `0x14002527f`
- `FLTMGR!FltReleasePushLockEx` at `0x1400252bc`
- `FLTMGR!FltReleasePushLockEx` at `0x14002523f`
- `FLTMGR!FltReleasePushLockEx` at `0x14002527f`
- `FLTMGR!FltReleasePushLockEx` at `0x1400252bc`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140025254`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140025254`

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
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned int v13; // esi
  __int16 v14; // cx
  char v15; // r8
  char v16; // r15
  char v17; // r14
  __int64 Pool; // rbx
  unsigned int v19; // ebx
  char *v20; // rbx
  __int64 i; // rbp
  char *v22; // rbx
  int v23; // ecx
  char v26; // [rsp+70h] [rbp+8h]
  __int64 v27; // [rsp+78h] [rbp+10h]
  char v28; // [rsp+80h] [rbp+18h]
  bool v29; // [rsp+88h] [rbp+20h]

  v27 = a2;
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
  v12 = a1;
  v13 = 0;
  while ( *(_QWORD *)(v12 + 32) && v12 != a2 )
  {
    if ( *(_QWORD *)(v12 + 248) )
    {
      v27 = v12;
      a3 = (unsigned __int16 *)(v12 + 240);
      break;
    }
    v13 += *(unsigned __int16 *)(v12 + 80) + 2;
    v12 = *(_QWORD *)(v12 + 32);
  }
  if ( a3 && *a3 )
  {
    v28 = 1;
    v13 += *a3;
    v29 = *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)*a3 >> 1) - 2) == 92;
    if ( *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * ((unsigned __int64)*a3 >> 1) - 2) == 92 )
      v13 -= 2;
  }
  else
  {
    v28 = 0;
    v29 = 0;
  }
  if ( !a4 || !*a4 )
  {
    v16 = 0;
    v26 = 0;
    v15 = 0;
LABEL_24:
    v17 = 0;
    goto LABEL_25;
  }
  v14 = **((_WORD **)a4 + 1);
  if ( v14 == 92 || v14 == 58 )
  {
    v16 = 1;
    v15 = 1;
  }
  else
  {
    v15 = 0;
    v16 = 1;
  }
  v26 = v15;
  if ( *(_WORD *)(*((_QWORD *)a4 + 1) + 2 * ((unsigned __int64)*a4 >> 1) - 2) != 92 )
    goto LABEL_24;
  v17 = 1;
LABEL_25:
  if ( v16 )
  {
    v13 += *a4;
    if ( !v15 )
      v13 += 2;
  }
  if ( a5 && !v17 )
    v13 += 2;
  LOBYTE(v11) = 2;
  Pool = LuafvAllocatePool(1, v13, v11);
  if ( Pool )
  {
    v20 = (char *)(v13 + Pool);
    if ( a5 && !v17 )
    {
      v20 -= 2;
      *(_WORD *)v20 = 92;
    }
    if ( v16 )
    {
      v20 -= *a4;
      memmove(v20, *((const void **)a4 + 1), *a4);
      if ( !v26 )
      {
        v20 -= 2;
        *(_WORD *)v20 = 92;
      }
    }
    for ( i = a1; *(_QWORD *)(i + 32); i = *(_QWORD *)(i + 32) )
    {
      if ( i == v27 )
        break;
      v22 = &v20[-*(unsigned __int16 *)(i + 80)];
      memmove(v22, *(const void **)(i + 88), *(unsigned __int16 *)(i + 80));
      v20 = v22 - 2;
      *(_WORD *)v20 = 92;
    }
    if ( v28 )
    {
      v23 = *a3 - 2;
      if ( !v29 )
        v23 = *a3;
      v20 -= v23;
      memmove(v20, *((const void **)a3 + 1), v23);
    }
    if ( a6 )
    {
      FltReleasePushLockEx(&qword_14000EC60, 0);
      FltAcquirePushLockExclusiveEx(&qword_14000EC60, 0);
    }
    *(_QWORD *)(a7 + 8) = v20;
    v19 = 0;
    *(_WORD *)a7 = v13;
    *(_WORD *)(a7 + 2) = v13;
  }
  else
  {
    v19 = -1073741670;
  }
  FltReleasePushLockEx(&qword_14000EC60, 0);
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
  return v19;
}

```

## disassembly

```asm
0x140024f80  mov     [rsp+arg_8], rdx
0x140024f85  push    rbx
0x140024f86  push    rbp
0x140024f87  push    rsi
0x140024f88  push    rdi
0x140024f89  push    r12
0x140024f8b  push    r13
0x140024f8d  push    r14
0x140024f8f  push    r15
0x140024f91  sub     rsp, 28h
0x140024f95  mov     rdi, rcx
0x140024f98  lea     rsi, FastMutex
0x140024f9f  mov     rcx, rsi; FastMutex
0x140024fa2  mov     rbp, r9
0x140024fa5  mov     r13, r8
0x140024fa8  mov     rbx, rdx
0x140024fab  call    cs:__imp_ExAcquireFastMutex
0x140024fb2  nop     dword ptr [rax+rax+00h]
0x140024fb7  mov     rax, gs:188h
0x140024fc0  cmp     [rdi+8], rax
0x140024fc4  jnz     short loc_140024FCB
0x140024fc6  inc     dword ptr [rdi+10h]
0x140024fc9  jmp     short loc_140024FFA
0x140024fcb  mov     rcx, rsi; FastMutex
0x140024fce  call    cs:__imp_ExReleaseFastMutex
0x140024fd5  nop     dword ptr [rax+rax+00h]
0x140024fda  xor     edx, edx
0x140024fdc  mov     rcx, rdi
0x140024fdf  call    cs:__imp_FltAcquirePushLockSharedEx
0x140024fe6  nop     dword ptr [rax+rax+00h]
0x140024feb  mov     rcx, rsi; FastMutex
0x140024fee  call    cs:__imp_ExAcquireFastMutex
0x140024ff5  nop     dword ptr [rax+rax+00h]
0x140024ffa  mov     rcx, rsi; FastMutex
0x140024ffd  call    cs:__imp_ExReleaseFastMutex
0x140025004  nop     dword ptr [rax+rax+00h]
0x140025009  xor     edx, edx
0x14002500b  lea     rcx, qword_14000EC60
0x140025012  call    cs:__imp_FltAcquirePushLockSharedEx
0x140025019  nop     dword ptr [rax+rax+00h]
0x14002501e  xor     r9d, r9d
0x140025021  mov     rax, rdi
0x140025024  mov     esi, r9d
0x140025027  mov     rcx, [rax+20h]
0x14002502b  test    rcx, rcx
0x14002502e  jz      short loc_140025058
0x140025030  cmp     rax, rbx
0x140025033  jz      short loc_140025058
0x140025035  cmp     [rax+0F8h], r9
0x14002503c  jnz     short loc_14002504C
0x14002503e  movzx   eax, word ptr [rax+50h]
0x140025042  add     eax, 2
0x140025045  add     esi, eax
0x140025047  mov     rax, rcx
0x14002504a  jmp     short loc_140025027
0x14002504c  mov     [rsp+68h+arg_8], rax
0x140025051  lea     r13, [rax+0F0h]
0x140025058  mov     r10d, 5Ch ; '\'
0x14002505e  test    r13, r13
0x140025061  jz      short loc_1400250A2
0x140025063  movzx   eax, word ptr [r13+0]
0x140025068  test    ax, ax
0x14002506b  jz      short loc_1400250A2
0x14002506d  mov     ecx, eax
0x14002506f  mov     [rsp+68h+arg_10], 1
0x140025077  mov     rax, [r13+8]
0x14002507b  shr     rcx, 1
0x14002507e  cmp     [rax+rcx*2-2], r10w
0x140025084  mov     cl, 1
0x140025086  jz      short loc_14002508B
0x140025088  mov     cl, r9b
0x14002508b  movzx   eax, word ptr [r13+0]
0x140025090  add     esi, eax
0x140025092  mov     [rsp+68h+arg_18], cl
0x140025099  test    cl, cl
0x14002509b  jz      short loc_1400250B2
0x14002509d  add     esi, 0FFFFFFFEh
0x1400250a0  jmp     short loc_1400250B2
0x1400250a2  mov     [rsp+68h+arg_10], r9b
0x1400250aa  mov     [rsp+68h+arg_18], r9b
0x1400250b2  test    rbp, rbp
0x1400250b5  jz      short loc_140025104
0x1400250b7  cmp     [rbp+0], r9w
0x1400250bc  jz      short loc_140025104
0x1400250be  mov     rax, [rbp+8]
0x1400250c2  movzx   ecx, word ptr [rax]
0x1400250c5  cmp     cx, r10w
0x1400250c9  jz      short loc_1400250D9
0x1400250cb  cmp     cx, 3Ah ; ':'
0x1400250cf  jz      short loc_1400250D9
0x1400250d1  mov     r8b, r9b
0x1400250d4  mov     r15b, 1
0x1400250d7  jmp     short loc_1400250DF
0x1400250d9  mov     r15b, 1
0x1400250dc  mov     r8b, r15b
0x1400250df  movzx   ecx, word ptr [rbp+0]
0x1400250e3  mov     eax, 8
0x1400250e8  mov     rdx, rbp
0x1400250eb  shr     rcx, 1
0x1400250ee  mov     [rsp+68h+arg_0], r8b
0x1400250f3  mov     rax, [rdx+rax]
0x1400250f7  cmp     [rax+rcx*2-2], r10w
0x1400250fd  jnz     short loc_14002510F
0x1400250ff  mov     r14b, 1
0x140025102  jmp     short loc_140025112
0x140025104  mov     r15b, r9b
0x140025107  mov     [rsp+68h+arg_0], r9b
0x14002510c  mov     r8b, r9b
0x14002510f  mov     r14b, r9b
0x140025112  test    r15b, r15b
0x140025115  jz      short loc_140025125
0x140025117  movzx   eax, word ptr [rbp+0]
0x14002511b  add     esi, eax
0x14002511d  test    r8b, r8b
0x140025120  jnz     short loc_140025125
0x140025122  add     esi, 2
0x140025125  mov     r12b, [rsp+68h+arg_20]
0x14002512d  test    r12b, r12b
0x140025130  jz      short loc_14002513A
0x140025132  test    r14b, r14b
0x140025135  jnz     short loc_14002513A
0x140025137  add     esi, 2
0x14002513a  mov     r8b, 2
0x14002513d  mov     edx, esi
0x14002513f  mov     ecx, 1
0x140025144  call    LuafvAllocatePool
0x140025149  mov     rbx, rax
0x14002514c  test    rax, rax
0x14002514f  jnz     short loc_14002515E
0x140025151  mov     ebx, 0C000009Ah
0x140025156  xor     r12d, r12d
0x140025159  jmp     loc_140025276
0x14002515e  mov     eax, esi
0x140025160  add     rbx, rax
0x140025163  test    r12b, r12b
0x140025166  jz      short loc_14002517F
0x140025168  xor     r12d, r12d
0x14002516b  test    r14b, r14b
0x14002516e  lea     r14d, [r12+5Ch]
0x140025173  jnz     short loc_140025187
0x140025175  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140025179  mov     [rbx], r14w
0x14002517d  jmp     short loc_140025187
0x14002517f  xor     r12d, r12d
0x140025182  lea     r14d, [r12+5Ch]
0x140025187  test    r15b, r15b
0x14002518a  jz      short loc_1400251B6
0x14002518c  movzx   r8d, word ptr [rbp+0]; Size
0x140025191  mov     rdx, [rbp+8]; Src
0x140025195  mov     eax, r8d
0x140025198  neg     eax
0x14002519a  cdqe
0x14002519c  add     rbx, rax
0x14002519f  mov     rcx, rbx; void *
0x1400251a2  call    memmove
0x1400251a7  cmp     [rsp+68h+arg_0], r12b
0x1400251ac  jnz     short loc_1400251B6
0x1400251ae  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1400251b2  mov     [rbx], r14w
0x1400251b6  mov     rbp, rdi
0x1400251b9  cmp     [rdi+20h], r12
0x1400251bd  jz      short loc_1400251F7
0x1400251bf  mov     r14, [rsp+68h+arg_8]
0x1400251c4  cmp     rbp, r14
0x1400251c7  jz      short loc_1400251F7
0x1400251c9  movzx   r8d, word ptr [rbp+50h]; Size
0x1400251ce  mov     rdx, [rbp+58h]; Src
0x1400251d2  mov     eax, r8d
0x1400251d5  neg     eax
0x1400251d7  cdqe
0x1400251d9  add     rbx, rax
0x1400251dc  mov     rcx, rbx; void *
0x1400251df  call    memmove
0x1400251e4  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1400251e8  mov     word ptr [rbx], 5Ch ; '\'
0x1400251ed  mov     rbp, [rbp+20h]
0x1400251f1  cmp     [rbp+20h], r12
0x1400251f5  jnz     short loc_1400251C4
0x1400251f7  cmp     [rsp+68h+arg_10], r12b
0x1400251ff  jz      short loc_14002522C
0x140025201  movzx   eax, word ptr [r13+0]
0x140025206  cmp     [rsp+68h+arg_18], r12b
0x14002520e  mov     rdx, [r13+8]; Src
0x140025212  lea     ecx, [rax-2]
0x140025215  cmovz   ecx, eax
0x140025218  mov     eax, ecx
0x14002521a  movsxd  r8, ecx; Size
0x14002521d  neg     eax
0x14002521f  cdqe
0x140025221  add     rbx, rax
0x140025224  mov     rcx, rbx; void *
0x140025227  call    memmove
0x14002522c  cmp     [rsp+68h+arg_28], r12b
0x140025234  jz      short loc_140025260
0x140025236  xor     edx, edx
0x140025238  lea     rcx, qword_14000EC60
0x14002523f  call    cs:__imp_FltReleasePushLockEx
0x140025246  nop     dword ptr [rax+rax+00h]
0x14002524b  xor     edx, edx
0x14002524d  lea     rcx, qword_14000EC60
0x140025254  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14002525b  nop     dword ptr [rax+rax+00h]
0x140025260  mov     rax, [rsp+68h+arg_30]
0x140025268  mov     [rax+8], rbx
0x14002526c  mov     ebx, r12d
0x14002526f  mov     [rax], si
0x140025272  mov     [rax+2], si
0x140025276  xor     edx, edx
0x140025278  lea     rcx, qword_14000EC60
0x14002527f  call    cs:__imp_FltReleasePushLockEx
0x140025286  nop     dword ptr [rax+rax+00h]
0x14002528b  lea     rcx, FastMutex; FastMutex
0x140025292  call    cs:__imp_ExAcquireFastMutex
0x140025299  nop     dword ptr [rax+rax+00h]
0x14002529e  mov     rax, gs:188h
0x1400252a7  cmp     [rdi+8], rax
0x1400252ab  jnz     short loc_1400252B7
0x1400252ad  sub     dword ptr [rdi+10h], 1
0x1400252b1  jnz     short loc_1400252C8
0x1400252b3  mov     [rdi+8], r12
0x1400252b7  xor     edx, edx
0x1400252b9  mov     rcx, rdi
0x1400252bc  call    cs:__imp_FltReleasePushLockEx
0x1400252c3  nop     dword ptr [rax+rax+00h]
0x1400252c8  lea     rcx, FastMutex; FastMutex
0x1400252cf  call    cs:__imp_ExReleaseFastMutex
0x1400252d6  nop     dword ptr [rax+rax+00h]
0x1400252db  mov     eax, ebx
0x1400252dd  add     rsp, 28h
0x1400252e1  pop     r15
0x1400252e3  pop     r14
0x1400252e5  pop     r13
0x1400252e7  pop     r12
0x1400252e9  pop     rdi
0x1400252ea  pop     rsi
0x1400252eb  pop     rbp
0x1400252ec  pop     rbx
0x1400252ed  retn
```
