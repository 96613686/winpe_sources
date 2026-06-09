# UxSslReceiveData

- ea: `0x1c00c8560`
- end: `0x1c00c882a`
- name: `UxSslReceiveData`
- size: `714`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0156440`
- `0x1c0156570`

## callees

- `0x1c0001118`
- `0x1c000eb40`
- `0x1c0011c4c`
- `0x1c001b610`
- `0x1c00c8560`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00c881c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00c881c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00c85e8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f46c1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00c85e8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f46c1`
- `ntoskrnl!ExQueryDepthSList` at `0x1c00c87cd`
- `ntoskrnl!ExQueryDepthSList` at `0x1c00f4759`
- `ntoskrnl!ExQueryDepthSList` at `0x1c00c87cd`
- `ntoskrnl!ExQueryDepthSList` at `0x1c00f4759`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f4681`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f4718`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f4681`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f4718`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c86d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c86d5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c866f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c866f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c86e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c86e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c865a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c865a`

## pseudocode

```c
__int64 __fastcall UxSslReceiveData(
        __int64 a1,
        int a2,
        struct _SLIST_ENTRY *a3,
        __int64 a4,
        unsigned int a5,
        void (__fastcall *a6)(struct _SLIST_ENTRY *, _QWORD, _QWORD),
        struct _SLIST_ENTRY *a7)
{
  PSLIST_ENTRY v7; // rbx
  unsigned int v12; // esi
  unsigned int v13; // r8d
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rbp
  __int64 v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rcx
  int v21; // r12d
  bool v22; // bp
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(__int64, __int64, __int64, __int64); // rax
  unsigned int v28; // r8d
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdi
  void (__fastcall *v33)(PSLIST_ENTRY, __int64); // rax
  __int64 v34; // rbx
  unsigned int v35; // r8d
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // r14
  unsigned int v40; // r8d
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rax

  v7 = 0;
  v12 = -1073741463;
  if ( !a4 )
    goto LABEL_11;
  if ( !UxCompactMode )
  {
    v13 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v14 = *(_DWORD *)qword_1C00743F0 - 1;
    if ( v13 < *(_DWORD *)qword_1C00743F0 )
      v14 = v13;
    v15 = v14;
    v16 = *(_QWORD *)(qword_1C00743F0 + 32);
    v17 = *(_QWORD *)(v16 + 8 * v15);
    if ( !*(_BYTE *)(v17 + 112) )
      PplpLazyInitializeLookasideList(qword_1C00743F0, *(_QWORD *)(v16 + 8 * v15));
    ++*(_DWORD *)(v17 + 20);
    v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v17);
    if ( v7 )
      goto LABEL_8;
LABEL_22:
    v24 = *(unsigned int *)(v17 + 40);
    v25 = *(unsigned int *)(v17 + 44);
    v26 = *(unsigned int *)(v17 + 36);
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v17 + 48);
    ++*(_DWORD *)(v17 + 24);
    v7 = (PSLIST_ENTRY)v27(v26, v25, v24, v17);
    goto LABEL_8;
  }
  v34 = qword_1C00743F0;
  v35 = KeGetCurrentNodeNumber() + 1;
  v36 = *(_DWORD *)v34 - 1;
  if ( v35 < *(_DWORD *)v34 )
    v36 = v35;
  v37 = v36;
  v38 = *(_QWORD *)(v34 + 32);
  v17 = *(_QWORD *)(v38 + 8 * v37);
  if ( !*(_BYTE *)(v17 + 112) )
    PplpLazyInitializeLookasideList(v34, *(_QWORD *)(v38 + 8 * v37));
  ++*(_DWORD *)(v17 + 20);
  v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v17);
  if ( !v7 )
    goto LABEL_22;
LABEL_8:
  if ( v7 )
  {
    LODWORD(v7[1].Next) = 1414756437;
    v7[2].Next = (PSLIST_ENTRY)((char *)v7 + 24);
    *((_QWORD *)&v7[1].Next + 1) = (char *)v7 + 24;
    v7[4].Next = (struct _SLIST_ENTRY *)a5;
    v18 = (__int64)a7;
    v7[5].Next = a7;
    *((_DWORD *)&v7[2].Next + 2) = a2;
    v7[3].Next = a3;
    *((_QWORD *)&v7[3].Next + 1) = a4;
    *((_QWORD *)&v7[4].Next + 1) = a6;
    *((_DWORD *)&v7[5].Next + 2) = 0;
    v7[6].Next = 0;
  }
  else
  {
    v18 = (__int64)a7;
  }
  if ( v7 )
  {
LABEL_11:
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 208, 0);
    if ( *(_DWORD *)(a1 + 220) == 4 )
    {
      v22 = 0;
      v12 = -1073741436;
      v21 = -1073741436;
      if ( (*(_DWORD *)(a1 + 792) & 4) != 0 )
        v12 = 0;
    }
    else
    {
      if ( v7 )
      {
        v19 = &v7[1].Next + 1;
        v20 = *(_QWORD **)(a1 + 784);
        if ( *v20 != a1 + 776 )
          __fastfail(3u);
        *v19 = a1 + 776;
        v19[1] = v20;
        *v20 = v19;
        *(_QWORD *)(a1 + 784) = v19;
        v7 = 0;
      }
      *(_DWORD *)(a1 + 792) |= 2u;
      v21 = 0;
      v22 = (*(_DWORD *)(a1 + 792) & 1) == 0;
    }
    ExReleasePushLockExclusiveEx(a1 + 208, 0);
    KeLeaveCriticalRegion();
    if ( v22 )
      UxSslQueueReceiverWorkItem(a1, 0);
    if ( v21 >= 0 )
    {
      if ( !a4 )
        return (unsigned int)UlInvokeCompletionRoutine(0, 0, a6, a7);
      return 259;
    }
    if ( !v7 )
    {
LABEL_33:
      if ( !a6 )
        return v12;
      a6(a7, v12, 0);
      return 259;
    }
    *((_QWORD *)&v7[4].Next + 1) = 0;
    LODWORD(v7[1].Next) = 1953716341;
    if ( UxCompactMode )
    {
      v39 = qword_1C00743F0;
      v40 = KeGetCurrentNodeNumber() + 1;
      v41 = *(_DWORD *)v39 - 1;
      if ( v40 < *(_DWORD *)v39 )
        v41 = v40;
      v42 = v41;
      v43 = *(_QWORD *)(v39 + 32);
      v32 = *(_QWORD *)(v43 + 8 * v42);
      if ( !*(_BYTE *)(v32 + 112) )
        PplpLazyInitializeLookasideList(v39, *(_QWORD *)(v43 + 8 * v42));
      ++*(_DWORD *)(v32 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v32) >= *(_WORD *)(v32 + 16) )
        goto LABEL_32;
    }
    else
    {
      v28 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v29 = *(_DWORD *)qword_1C00743F0 - 1;
      if ( v28 < *(_DWORD *)qword_1C00743F0 )
        v29 = v28;
      v30 = v29;
      v31 = *(_QWORD *)(qword_1C00743F0 + 32);
      v32 = *(_QWORD *)(v31 + 8 * v30);
      if ( !*(_BYTE *)(v32 + 112) )
        PplpLazyInitializeLookasideList(qword_1C00743F0, *(_QWORD *)(v31 + 8 * v30));
      ++*(_DWORD *)(v32 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v32) >= *(_WORD *)(v32 + 16) )
      {
LABEL_32:
        v33 = *(void (__fastcall **)(PSLIST_ENTRY, __int64))(v32 + 56);
        ++*(_DWORD *)(v32 + 32);
        v33(v7, v32);
        goto LABEL_33;
      }
    }
    ExpInterlockedPushEntrySList((PSLIST_HEADER)v32, v7);
    goto LABEL_33;
  }
  return UlInvokeCompletionRoutine(3221225626LL, 0, a6, v18);
}

```

## disassembly

```asm
0x1c00c8560  mov     [rsp+arg_0], rbx
0x1c00c8565  mov     [rsp+arg_8], rbp
0x1c00c856a  mov     [rsp+arg_10], rsi
0x1c00c856f  push    rdi
0x1c00c8570  push    r12
0x1c00c8572  push    r13
0x1c00c8574  push    r14
0x1c00c8576  push    r15
0x1c00c8578  sub     rsp, 30h
0x1c00c857c  mov     r13, [rsp+58h+arg_28]
0x1c00c8584  xor     ebx, ebx
0x1c00c8586  mov     r14, r9
0x1c00c8589  mov     r15, r8
0x1c00c858c  mov     r12d, edx
0x1c00c858f  mov     rdi, rcx
0x1c00c8592  mov     esi, 0C0000169h
0x1c00c8597  test    r9, r9
0x1c00c859a  jz      loc_1C00C865A
0x1c00c85a0  cmp     cs:UxCompactMode, bl
0x1c00c85a6  jnz     loc_1C00F467A
0x1c00c85ac  mov     eax, gs:1A4h
0x1c00c85b4  mov     rcx, cs:qword_1C00743F0
0x1c00c85bb  lea     r8d, [rax+1]
0x1c00c85bf  mov     edx, [rcx]
0x1c00c85c1  cmp     r8d, edx
0x1c00c85c4  lea     eax, [rdx-1]
0x1c00c85c7  cmovb   eax, r8d
0x1c00c85cb  mov     edx, eax
0x1c00c85cd  mov     rax, [rcx+20h]
0x1c00c85d1  mov     rbp, [rax+rdx*8]
0x1c00c85d5  cmp     [rbp+70h], bl
0x1c00c85d8  jnz     short loc_1C00C85E2
0x1c00c85da  mov     rdx, rbp
0x1c00c85dd  call    PplpLazyInitializeLookasideList
0x1c00c85e2  inc     dword ptr [rbp+14h]
0x1c00c85e5  mov     rcx, rbp; ListHead
0x1c00c85e8  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00c85ef  nop     dword ptr [rax+rax+00h]
0x1c00c85f4  mov     rbx, rax
0x1c00c85f7  test    rax, rax
0x1c00c85fa  jz      loc_1C00C872F
0x1c00c8600  test    rbx, rbx
0x1c00c8603  jz      loc_1C00F46DE
0x1c00c8609  lea     rax, [rbx+18h]
0x1c00c860d  mov     dword ptr [rbx+10h], 54537855h
0x1c00c8614  mov     [rax+8], rax
0x1c00c8618  mov     [rax], rax
0x1c00c861b  mov     eax, [rsp+58h+arg_20]
0x1c00c8622  mov     [rbx+40h], rax
0x1c00c8626  mov     rax, [rsp+58h+arg_30]
0x1c00c862e  mov     [rbx+50h], rax
0x1c00c8632  mov     [rbx+28h], r12d
0x1c00c8636  mov     [rbx+30h], r15
0x1c00c863a  mov     [rbx+38h], r14
0x1c00c863e  mov     [rbx+48h], r13
0x1c00c8642  mov     dword ptr [rbx+58h], 0
0x1c00c8649  mov     qword ptr [rbx+60h], 0
0x1c00c8651  test    rbx, rbx
0x1c00c8654  jz      loc_1C00F46EB
0x1c00c865a  call    cs:__imp_KeEnterCriticalRegion
0x1c00c8661  nop     dword ptr [rax+rax+00h]
0x1c00c8666  xor     edx, edx
0x1c00c8668  lea     rcx, [rdi+0D0h]
0x1c00c866f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00c8676  nop     dword ptr [rax+rax+00h]
0x1c00c867b  cmp     dword ptr [rdi+0DCh], 4
0x1c00c8682  jz      loc_1C00C8751
0x1c00c8688  test    rbx, rbx
0x1c00c868b  jz      short loc_1C00C86B5
0x1c00c868d  lea     rax, [rdi+308h]
0x1c00c8694  add     rbx, 18h
0x1c00c8698  mov     rcx, [rax+8]
0x1c00c869c  cmp     [rcx], rax
0x1c00c869f  jnz     loc_1C00F4703
0x1c00c86a5  mov     [rbx], rax
0x1c00c86a8  mov     [rbx+8], rcx
0x1c00c86ac  mov     [rcx], rbx
0x1c00c86af  mov     [rax+8], rbx
0x1c00c86b3  xor     ebx, ebx
0x1c00c86b5  or      dword ptr [rdi+318h], 2
0x1c00c86bc  xor     r12d, r12d
0x1c00c86bf  mov     ebp, [rdi+318h]
0x1c00c86c5  not     bpl
0x1c00c86c8  and     bpl, 1
0x1c00c86cc  xor     edx, edx
0x1c00c86ce  lea     rcx, [rdi+0D0h]
0x1c00c86d5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00c86dc  nop     dword ptr [rax+rax+00h]
0x1c00c86e1  call    cs:__imp_KeLeaveCriticalRegion
0x1c00c86e8  nop     dword ptr [rax+rax+00h]
0x1c00c86ed  test    bpl, bpl
0x1c00c86f0  jz      short loc_1C00C86FC
0x1c00c86f2  xor     edx, edx
0x1c00c86f4  mov     rcx, rdi
0x1c00c86f7  call    UxSslQueueReceiverWorkItem
0x1c00c86fc  test    r12d, r12d
0x1c00c86ff  js      short loc_1C00C876F
0x1c00c8701  test    r14, r14
0x1c00c8704  jz      loc_1C00F4774
0x1c00c870a  mov     esi, 103h
0x1c00c870f  mov     eax, esi
0x1c00c8711  mov     rbx, [rsp+58h+arg_0]
0x1c00c8716  mov     rbp, [rsp+58h+arg_8]
0x1c00c871b  mov     rsi, [rsp+58h+arg_10]
0x1c00c8720  add     rsp, 30h
0x1c00c8724  pop     r15
0x1c00c8726  pop     r14
0x1c00c8728  pop     r13
0x1c00c872a  pop     r12
0x1c00c872c  pop     rdi
0x1c00c872d  retn
0x1c00c872f  mov     r8d, [rbp+28h]
0x1c00c8733  mov     r9, rbp
0x1c00c8736  mov     edx, [rbp+2Ch]
0x1c00c8739  mov     ecx, [rbp+24h]
0x1c00c873c  mov     rax, [rbp+30h]
0x1c00c8740  inc     dword ptr [rbp+18h]
0x1c00c8743  call    cs:__guard_dispatch_icall_fptr
0x1c00c8749  mov     rbx, rax
0x1c00c874c  jmp     loc_1C00C8600
0x1c00c8751  mov     eax, [rdi+318h]
0x1c00c8757  xor     bpl, bpl
0x1c00c875a  mov     esi, 0C0000184h
0x1c00c875f  mov     r12d, esi
0x1c00c8762  test    al, 4
0x1c00c8764  jz      loc_1C00C86CC
0x1c00c876a  jmp     loc_1C00F470A
0x1c00c876f  test    rbx, rbx
0x1c00c8772  jz      short loc_1C00C87F2
0x1c00c8774  mov     qword ptr [rbx+48h], 0
0x1c00c877c  mov     dword ptr [rbx+10h], 74735875h
0x1c00c8783  cmp     cs:UxCompactMode, 0
0x1c00c878a  jnz     loc_1C00F4711
0x1c00c8790  mov     eax, gs:1A4h
0x1c00c8798  mov     rcx, cs:qword_1C00743F0
0x1c00c879f  lea     r8d, [rax+1]
0x1c00c87a3  mov     edx, [rcx]
0x1c00c87a5  cmp     r8d, edx
0x1c00c87a8  lea     eax, [rdx-1]
0x1c00c87ab  cmovb   eax, r8d
0x1c00c87af  mov     edx, eax
0x1c00c87b1  mov     rax, [rcx+20h]
0x1c00c87b5  mov     rdi, [rax+rdx*8]
0x1c00c87b9  cmp     byte ptr [rdi+70h], 0
0x1c00c87bd  jnz     short loc_1C00C87C7
0x1c00c87bf  mov     rdx, rdi
0x1c00c87c2  call    PplpLazyInitializeLookasideList
0x1c00c87c7  inc     dword ptr [rdi+1Ch]
0x1c00c87ca  mov     rcx, rdi; SListHead
0x1c00c87cd  call    cs:__imp_ExQueryDepthSList
0x1c00c87d4  nop     dword ptr [rax+rax+00h]
0x1c00c87d9  cmp     ax, [rdi+10h]
0x1c00c87dd  jb      short loc_1C00C8816
0x1c00c87df  mov     rax, [rdi+38h]
0x1c00c87e3  mov     rdx, rdi
0x1c00c87e6  inc     dword ptr [rdi+20h]
0x1c00c87e9  mov     rcx, rbx
0x1c00c87ec  call    cs:__guard_dispatch_icall_fptr
0x1c00c87f2  test    r13, r13
0x1c00c87f5  jz      loc_1C00C870F
0x1c00c87fb  mov     rcx, [rsp+58h+arg_30]
0x1c00c8803  xor     r8d, r8d
0x1c00c8806  mov     edx, esi
0x1c00c8808  mov     rax, r13
0x1c00c880b  call    cs:__guard_dispatch_icall_fptr
0x1c00c8811  jmp     loc_1C00C870A
0x1c00c8816  mov     rdx, rbx; ListEntry
0x1c00c8819  mov     rcx, rdi; ListHead
0x1c00c881c  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c00c8823  nop     dword ptr [rax+rax+00h]
0x1c00c8828  jmp     short loc_1C00C87F2
0x1c00f467a  mov     rbx, cs:qword_1C00743F0
0x1c00f4681  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00f4688  nop     dword ptr [rax+rax+00h]
0x1c00f468d  mov     edx, [rbx]
0x1c00f468f  movzx   r8d, ax
0x1c00f4693  inc     r8d
0x1c00f4696  cmp     r8d, edx
0x1c00f4699  lea     eax, [rdx-1]
0x1c00f469c  cmovb   eax, r8d
0x1c00f46a0  mov     edx, eax
0x1c00f46a2  mov     rax, [rbx+20h]
0x1c00f46a6  mov     rbp, [rax+rdx*8]
0x1c00f46aa  cmp     byte ptr [rbp+70h], 0
0x1c00f46ae  jnz     short loc_1C00F46BB
0x1c00f46b0  mov     rdx, rbp
0x1c00f46b3  mov     rcx, rbx
0x1c00f46b6  call    PplpLazyInitializeLookasideList
0x1c00f46bb  inc     dword ptr [rbp+14h]
0x1c00f46be  mov     rcx, rbp; ListHead
0x1c00f46c1  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00f46c8  nop     dword ptr [rax+rax+00h]
0x1c00f46cd  mov     rbx, rax
0x1c00f46d0  test    rax, rax
0x1c00f46d3  jnz     loc_1C00C8600
0x1c00f46d9  jmp     loc_1C00C872F
0x1c00f46de  mov     rax, [rsp+58h+arg_30]
0x1c00f46e6  jmp     loc_1C00C8651
0x1c00f46eb  mov     r9, rax
0x1c00f46ee  mov     r8, r13
0x1c00f46f1  xor     edx, edx
0x1c00f46f3  mov     ecx, 0C000009Ah
0x1c00f46f8  call    UlInvokeCompletionRoutine
0x1c00f46fd  nop
0x1c00f46fe  jmp     loc_1C00C8711
0x1c00f4703  mov     ecx, 3
0x1c00f4708  int     29h; Win8: RtlFailFast(ecx)
0x1c00f470a  xor     esi, esi
0x1c00f470c  jmp     loc_1C00C86CC
0x1c00f4711  mov     r14, cs:qword_1C00743F0
0x1c00f4718  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00f471f  nop     dword ptr [rax+rax+00h]
0x1c00f4724  mov     edx, [r14]
0x1c00f4727  movzx   r8d, ax
0x1c00f472b  inc     r8d
0x1c00f472e  cmp     r8d, edx
0x1c00f4731  lea     eax, [rdx-1]
0x1c00f4734  cmovb   eax, r8d
0x1c00f4738  mov     edx, eax
0x1c00f473a  mov     rax, [r14+20h]
0x1c00f473e  mov     rdi, [rax+rdx*8]
0x1c00f4742  cmp     byte ptr [rdi+70h], 0
0x1c00f4746  jnz     short loc_1C00F4753
0x1c00f4748  mov     rdx, rdi
0x1c00f474b  mov     rcx, r14
0x1c00f474e  call    PplpLazyInitializeLookasideList
0x1c00f4753  inc     dword ptr [rdi+1Ch]
0x1c00f4756  mov     rcx, rdi; SListHead
0x1c00f4759  call    cs:__imp_ExQueryDepthSList
0x1c00f4760  nop     dword ptr [rax+rax+00h]
0x1c00f4765  cmp     ax, [rdi+10h]
0x1c00f4769  jb      loc_1C00C8816
0x1c00f476f  jmp     loc_1C00C87DF
0x1c00f4774  mov     r9, [rsp+58h+arg_30]
0x1c00f477c  mov     r8, r13
0x1c00f477f  xor     edx, edx
0x1c00f4781  xor     ecx, ecx
0x1c00f4783  call    UlInvokeCompletionRoutine
0x1c00f4788  mov     esi, eax
0x1c00f478a  jmp     loc_1C00C870F
```
