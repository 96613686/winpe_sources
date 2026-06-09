# SmbCeFindOrConstructVNetRootContext

- ea: `0x1400302f0`
- end: `0x140030a10`
- name: `SmbCeFindOrConstructVNetRootContext`
- size: `1824`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002eeb0`

## callees

- `0x140005b20`
- `0x1400097e0`
- `0x140017e60`
- `0x1400189c0`
- `0x140018abc`
- `0x140021130`
- `0x1400221e0`
- `0x140026d60`
- `0x14002dff0`
- `0x1400302f0`
- `0x140037fa4`
- `0x14003838c`
- `0x14003e14c`
- `0x1400478d0`
- `0x140059ea0`
- `0x140059f00`
- `0x14008770c`
- `0x140087730`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x140030590`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140030590`
- `ntoskrnl!KeInitializeSpinLock` at `0x140030633`
- `ntoskrnl!KeInitializeSpinLock` at `0x140030633`
- `ntoskrnl!ExAllocatePool2` at `0x140030566`
- `ntoskrnl!ExAllocatePool2` at `0x1400307c9`
- `ntoskrnl!ExAllocatePool2` at `0x140030566`
- `ntoskrnl!ExAllocatePool2` at `0x1400307c9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400304a9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140030992`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400304a9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140030992`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140030439`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140030915`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140030439`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140030915`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140030448`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140030928`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140030448`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140030928`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030797`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030797`
- `rdbss!RxInitializeDiagnosticLogger` at `0x14003089d`
- `rdbss!RxInitializeDiagnosticLogger` at `0x14003089d`
- `rdbss!RxReferenceCredential` at `0x140030682`
- `rdbss!RxReferenceCredential` at `0x140030682`
- `rdbss!RxDiagnosticTrace` at `0x140030489`
- `rdbss!RxDiagnosticTrace` at `0x140030489`

## pseudocode

```c
__int64 __fastcall SmbCeFindOrConstructVNetRootContext(__int64 a1, __int64 a2, __int64 a3, ULONG_PTR *a4)
{
  int v4; // edi
  char v5; // si
  __int64 v8; // rbp
  void *v9; // r12
  _DWORD *VNetRootContext; // rax
  ULONG_PTR v11; // r14
  _DWORD *v12; // rcx
  int v13; // eax
  _WORD *v14; // rdx
  ULONG_PTR v15; // rdi
  __int64 v16; // rsi
  KIRQL v17; // bl
  int v18; // r8d
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // ebx
  int v22; // edi
  int v23; // edx
  ULONG_PTR v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rdx
  struct _LIST_ENTRY *Pool2; // rax
  ULONG_PTR *v28; // rsi
  _QWORD *v29; // rbp
  ULONG_PTR v30; // rcx
  __int64 v31; // rcx
  void *v32; // rcx
  void *v33; // rax
  signed __int32 v34; // r8d
  ULONG_PTR v35; // rbx
  __int64 v36; // r15
  ULONG_PTR v37; // rbx
  ULONG_PTR **v38; // rcx
  _QWORD *v39; // rdx
  int Size_4; // [rsp+34h] [rbp-54h]
  ULONG_PTR BugCheckParameter2; // [rsp+38h] [rbp-50h] BYREF
  void *Src; // [rsp+40h] [rbp-48h]
  char v45; // [rsp+A0h] [rbp+18h]
  KIRQL v46; // [rsp+A0h] [rbp+18h]

  v4 = *(_DWORD *)(a3 + 184);
  v5 = 0;
  BugCheckParameter2 = 0;
  Src = 0;
  v8 = a1;
  v9 = 0;
  if ( v4 == 4 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 88) + 716LL) & 0x8000) != 0 )
    {
      *(_DWORD *)(a3 + 184) = 3;
      v4 = 3;
    }
    else
    {
      *(_DWORD *)(a3 + 184) = 2;
      v4 = 2;
    }
  }
  VNetRootContext = (_DWORD *)SmbCeFindVNetRootContext(a1, a3, a2);
  v11 = (ULONG_PTR)VNetRootContext;
  if ( !VNetRootContext )
  {
    v45 = 0;
    v21 = v4;
    goto LABEL_24;
  }
  if ( VNetRootContext[24] != `RxIsGlobalMappingLuid'::`2'::globalMappingLuid || VNetRootContext[25] != dword_14007025C )
  {
    v12 = VNetRootContext + 113;
LABEL_20:
    v22 = 0;
    v23 = *(_DWORD *)(a3 + 184);
    if ( v23 <= *v12 )
      *(_DWORD *)(a3 + 184) = *v12;
    else
      *v12 = v23;
    goto LABEL_66;
  }
  v12 = VNetRootContext + 113;
  *(_DWORD *)(a3 + 188) |= VNetRootContext[114];
  v13 = VNetRootContext[113];
  if ( v13 <= v4 )
    v13 = v4;
  Size_4 = v13;
  v14 = *(_WORD **)(*(_QWORD *)(a2 + 88) + 64LL);
  if ( !v14
    || *v14 <= 3u && (*v14 < 3u || v14[1] <= 1u && (!v14[1] || !v14[2]))
    || !dbgForceIdentityRemoting && (*(_DWORD *)(a2 + 184) & 0x40000) == 0 )
  {
    goto LABEL_20;
  }
  BugCheckParameter2 = *(_QWORD *)(v11 + 416);
  v45 = 1;
  SmbCeReferenceSessionEntry(BugCheckParameter2);
  v15 = BugCheckParameter2;
  v16 = *(_QWORD *)(BugCheckParameter2 + 24);
  v17 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v16 + 1920));
  *(_DWORD *)(v16 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v18 = ++*(_DWORD *)(v15 + 428);
  RxDiagnosticTrace(
    *(_QWORD *)(v15 + 16),
    2,
    "Active VnrCtxts++ %x, Total VnrCtxts++ %x",
    ++*(_DWORD *)(v15 + 424),
    v18);
  *(_DWORD *)(v16 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v16 + 1920), v17);
  SmbCeDecrementActiveVNetRootsOnVNetRootContext(v11, a3, v19, v20);
  SmbCeDereferenceVNetRootContext(v11);
  v21 = Size_4;
  v11 = 0;
  v8 = a1;
  v5 = 0;
LABEL_24:
  v24 = BugCheckParameter2;
  if ( !BugCheckParameter2 )
  {
    v22 = SmbCeFindOrConstructSessionEntry(v8, a3, &BugCheckParameter2);
    if ( v22 )
      goto LABEL_67;
    v24 = BugCheckParameter2;
  }
  v25 = *(_QWORD *)(v24 + 24);
  v26 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v24 + 384) + 56LL) + 20LL);
  if ( (unsigned int)xmmword_140070ED0 > (unsigned int)v26 )
    v26 = (unsigned int)xmmword_140070ED0;
  Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(64, v26 + 16, 1834181955);
  if ( !Pool2 )
  {
    v22 = -1073741670;
    goto LABEL_72;
  }
  v11 = (ULONG_PTR)&Pool2[1];
  ExInterlockedInsertTailList(&stru_140070E60, Pool2, &SmbMmSpinLock);
  *(_DWORD *)(v11 + 4) = 0;
  *(_DWORD *)v11 = 4252164;
  v28 = (ULONG_PTR *)(v11 + 384);
  *(_DWORD *)(v11 + 12) = 1;
  v29 = (_QWORD *)(v11 + 400);
  *(_DWORD *)(v11 + 8) = 1;
  *(_QWORD *)(v11 + 24) = v25;
  *(_QWORD *)(v11 + 392) = v11 + 384;
  *(_QWORD *)(v11 + 384) = v11 + 384;
  *(_QWORD *)(v11 + 408) = v11 + 400;
  *(_QWORD *)(v11 + 400) = v11 + 400;
  if ( *(_WORD *)(v11 + 2) )
  {
    v30 = v11 + *(unsigned __int16 *)(v11 + 2);
    if ( v30 )
    {
      *(_DWORD *)(v30 + 208) = -1073741300;
      *(_QWORD *)(v30 + 16) = v30 + 8;
      *(_QWORD *)(v30 + 8) = v30 + 8;
      *(_QWORD *)(v30 + 256) = v30 + 248;
      *(_QWORD *)(v30 + 248) = v30 + 248;
      *(_QWORD *)(v30 + 224) = v30 + 216;
      *(_QWORD *)(v30 + 216) = v30 + 216;
      *(_DWORD *)(v30 + 212) = 0;
      *(_QWORD *)(v30 + 240) = v30 + 232;
      *(_QWORD *)(v30 + 232) = v30 + 232;
      KeInitializeSpinLock((PKSPIN_LOCK)(v30 + 128));
    }
  }
  *(_QWORD *)(v11 + 64) = &off_1400616F0;
  *(_QWORD *)(v11 + 416) = BugCheckParameter2;
  v31 = *(_QWORD *)(a3 + 104);
  *(_OWORD *)(v11 + 96) = *(_OWORD *)(a3 + 72);
  *(_OWORD *)(v11 + 112) = *(_OWORD *)(a3 + 88);
  *(_QWORD *)(v11 + 128) = *(_QWORD *)(a3 + 104);
  if ( v31 )
    RxReferenceCredential();
  if ( *(_DWORD *)(v11 + 96) == `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
    && *(_DWORD *)(v11 + 100) == dword_14007025C )
  {
    *(_DWORD *)(v11 + 456) = *(_DWORD *)(a3 + 188);
  }
  *(_DWORD *)(v11 + 452) = v21;
  *(_QWORD *)(v11 + 424) = a2;
  if ( v45 )
  {
    SmbCeSetComputerNameSid();
    v22 = SmbCamSerializeToken(*(struct _SECURITY_SUBJECT_CONTEXT **)(a1 + 40));
    if ( v22 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
          (unsigned int)v22);
      }
      v9 = Src;
      goto LABEL_45;
    }
    v9 = Src;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids, Src, 0);
    }
    v33 = (void *)ExAllocatePool2(66, 0, 1834186049);
    *(_QWORD *)(v11 + 464) = v33;
    if ( !v33 )
    {
      v22 = -1073741670;
      goto LABEL_45;
    }
    memmove(v33, v9, 0);
    *(_WORD *)(v11 + 472) = 0;
    SmbCamFreeSerializationBuffer(v9);
    v9 = 0;
    v28 = (ULONG_PTR *)(v11 + 384);
  }
  else
  {
    *(_QWORD *)(v11 + 464) = 0;
    *(_WORD *)(v11 + 472) = 0;
  }
  v22 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)(*(_QWORD *)(BugCheckParameter2 + 384) + 56LL) + 760LL))(v11);
  if ( v22 < 0 )
  {
LABEL_45:
    if ( v11 )
    {
      v32 = *(void **)(v11 + 464);
      if ( v32 )
      {
        ExFreePoolWithTag(v32, 0x6D537541u);
        *(_QWORD *)(v11 + 464) = 0;
      }
      SmbMmFreeObjectPool(v11);
    }
    goto LABEL_72;
  }
  *(_QWORD *)(v11 + 16) = RxInitializeDiagnosticLogger(v11, 64, (unsigned int)SmbCeTraceFlags);
  v34 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_f7d52e057b303f00897e3719f4b0e901_Traceguids,
      a2,
      v34 - 1,
      v34);
  }
  *(_DWORD *)(v11 + 432) = 1;
  v35 = BugCheckParameter2;
  v36 = *(_QWORD *)(BugCheckParameter2 + 24);
  v46 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v36 + 1920));
  v37 = v35 + 408;
  *(_DWORD *)(v36 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v38 = *(ULONG_PTR ***)(v37 + 8);
  if ( *v38 != (ULONG_PTR *)v37
    || (*v28 = v37,
        v28[1] = (ULONG_PTR)v38,
        *v38 = v28,
        *(_QWORD *)(v37 + 8) = v28,
        v39 = *(_QWORD **)(a2 + 56),
        *v39 != a2 + 48) )
  {
    __fastfail(3u);
  }
  *(_QWORD *)(v11 + 408) = v39;
  *v29 = a2 + 48;
  v5 = 1;
  *v39 = v29;
  *(_QWORD *)(a2 + 56) = v29;
  *(_DWORD *)(v36 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v36 + 1920), v46);
LABEL_66:
  *a4 = v11;
LABEL_67:
  if ( v22 >= 0 )
    goto LABEL_74;
  if ( v5 )
    goto LABEL_45;
LABEL_72:
  if ( BugCheckParameter2 )
  {
    SmbCeDecrementActiveVNetRootContextsOnSession(BugCheckParameter2);
    SmbCeDecrementTotalVNetRootContextsOnSession(BugCheckParameter2);
    SmbCeDereferenceSessionEntryEx(BugCheckParameter2);
  }
LABEL_74:
  if ( v9 )
    SmbCamFreeSerializationBuffer(v9);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1400302f0  mov     [rsp+arg_8], rbx
0x1400302f5  mov     [rsp+arg_18], r9
0x1400302fa  mov     [rsp+arg_0], rcx
0x1400302ff  push    rbp
0x140030300  push    rsi
0x140030301  push    rdi
0x140030302  push    r12
0x140030304  push    r13
0x140030306  push    r14
0x140030308  push    r15
0x14003030a  sub     rsp, 50h
0x14003030e  mov     edi, [r8+0B8h]
0x140030315  xor     eax, eax
0x140030317  xor     sil, sil
0x14003031a  mov     [rsp+88h+BugCheckParameter2], rax
0x14003031f  mov     [rsp+88h+Src], rax
0x140030324  mov     r15, r8
0x140030327  mov     dword ptr [rsp+88h+Size], eax
0x14003032b  mov     r13, rdx
0x14003032e  mov     rbp, rcx
0x140030331  mov     r12d, eax
0x140030334  cmp     edi, 4
0x140030337  jnz     short loc_14003036B
0x140030339  mov     rax, [rdx+58h]
0x14003033d  test    dword ptr [rax+2CCh], 8000h
0x140030347  jz      short loc_14003035B
0x140030349  mov     dword ptr [r8+0B8h], 3
0x140030354  mov     edi, 3
0x140030359  jmp     short loc_14003036B
0x14003035b  mov     dword ptr [r8+0B8h], 2
0x140030366  mov     edi, 2
0x14003036b  mov     r8, r13
0x14003036e  mov     rdx, r15
0x140030371  call    SmbCeFindVNetRootContext
0x140030376  mov     r14, rax
0x140030379  test    rax, rax
0x14003037c  jz      loc_140030505
0x140030382  mov     ecx, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x140030388  cmp     [rax+60h], ecx
0x14003038b  jnz     loc_1400304DC
0x140030391  mov     ecx, cs:dword_14007025C
0x140030397  cmp     [rax+64h], ecx
0x14003039a  jnz     loc_1400304DC
0x1400303a0  mov     eax, [rax+1C8h]
0x1400303a6  lea     rcx, [r14+1C4h]
0x1400303ad  or      [r15+0BCh], eax
0x1400303b4  mov     eax, [rcx]
0x1400303b6  cmp     eax, edi
0x1400303b8  cmovle  eax, edi
0x1400303bb  mov     dword ptr [rsp+88h+Size+4], eax
0x1400303bf  mov     rax, [r13+58h]
0x1400303c3  mov     rdx, [rax+40h]
0x1400303c7  test    rdx, rdx
0x1400303ca  jz      loc_1400304E3
0x1400303d0  cmp     word ptr [rdx], 3
0x1400303d4  ja      short loc_1400303F4
0x1400303d6  jb      loc_1400304E3
0x1400303dc  cmp     word ptr [rdx+2], 1
0x1400303e1  ja      short loc_1400303F4
0x1400303e3  jb      loc_1400304E3
0x1400303e9  cmp     word ptr [rdx+4], 1
0x1400303ee  jb      loc_1400304E3
0x1400303f4  movzx   eax, cs:dbgForceIdentityRemoting
0x1400303fb  test    al, al
0x1400303fd  jnz     short loc_140030410
0x1400303ff  test    dword ptr [r13+0B8h], 40000h
0x14003040a  jz      loc_1400304E3
0x140030410  mov     rcx, [r14+1A0h]
0x140030417  mov     [rsp+88h+BugCheckParameter2], rcx
0x14003041c  mov     [rsp+88h+arg_10], 1
0x140030424  call    SmbCeReferenceSessionEntry
0x140030429  mov     rdi, [rsp+88h+BugCheckParameter2]
0x14003042e  mov     rsi, [rdi+18h]
0x140030432  lea     rcx, [rsi+780h]; SpinLock
0x140030439  call    cs:__imp_ExAcquireSpinLockExclusive
0x140030440  nop     dword ptr [rax+rax+00h]
0x140030445  movzx   ebx, al
0x140030448  call    cs:__imp_PsGetCurrentThreadId
0x14003044f  nop     dword ptr [rax+rax+00h]
0x140030454  mov     [rsi+930h], eax
0x14003045a  mov     edx, 2
0x14003045f  inc     dword ptr [rdi+1ACh]
0x140030465  mov     r8d, [rdi+1ACh]
0x14003046c  inc     dword ptr [rdi+1A8h]
0x140030472  mov     r9d, [rdi+1A8h]
0x140030479  mov     rcx, [rdi+10h]
0x14003047d  mov     [rsp+88h+var_68], r8d
0x140030482  lea     r8, aActiveVnrctxts_0; "Active VnrCtxts++ %x, Total VnrCtxts++ "...
0x140030489  call    cs:__imp_RxDiagnosticTrace
0x140030490  nop     dword ptr [rax+rax+00h]
0x140030495  movzx   edx, bl; OldIrql
0x140030498  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x1400304a2  lea     rcx, [rsi+780h]; SpinLock
0x1400304a9  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400304b0  nop     dword ptr [rax+rax+00h]
0x1400304b5  mov     rdx, r15
0x1400304b8  mov     rcx, r14
0x1400304bb  call    SmbCeDecrementActiveVNetRootsOnVNetRootContext
0x1400304c0  mov     rcx, r14; BugCheckParameter2
0x1400304c3  call    SmbCeDereferenceVNetRootContext
0x1400304c8  mov     ebx, dword ptr [rsp+88h+Size+4]
0x1400304cc  xor     r14d, r14d
0x1400304cf  mov     rbp, [rsp+88h+arg_0]
0x1400304d7  xor     sil, sil
0x1400304da  jmp     short loc_14003050F
0x1400304dc  lea     rcx, [rax+1C4h]
0x1400304e3  mov     eax, [rcx]
0x1400304e5  xor     edi, edi
0x1400304e7  mov     edx, [r15+0B8h]
0x1400304ee  cmp     edx, eax
0x1400304f0  jle     short loc_1400304F9
0x1400304f2  mov     [rcx], edx
0x1400304f4  jmp     loc_14003099E
0x1400304f9  mov     [r15+0B8h], eax
0x140030500  jmp     loc_14003099E
0x140030505  mov     [rsp+88h+arg_10], sil
0x14003050d  mov     ebx, edi
0x14003050f  mov     rax, [rsp+88h+BugCheckParameter2]
0x140030514  test    rax, rax
0x140030517  jnz     short loc_140030538
0x140030519  lea     r8, [rsp+88h+BugCheckParameter2]
0x14003051e  mov     rdx, r15
0x140030521  mov     rcx, rbp
0x140030524  call    SmbCeFindOrConstructSessionEntry
0x140030529  mov     edi, eax
0x14003052b  test    eax, eax
0x14003052d  jnz     loc_1400309A9
0x140030533  mov     rax, [rsp+88h+BugCheckParameter2]
0x140030538  mov     rdi, [rax+18h]
0x14003053c  mov     r8d, 6D536543h
0x140030542  mov     rax, [rax+180h]
0x140030549  mov     rcx, [rax+38h]
0x14003054d  mov     edx, [rcx+14h]
0x140030550  mov     ecx, 40h ; '@'
0x140030555  cmp     dword ptr cs:xmmword_140070ED0, edx
0x14003055b  cmova   edx, dword ptr cs:xmmword_140070ED0
0x140030562  add     rdx, 10h
0x140030566  call    cs:__imp_ExAllocatePool2
0x14003056d  nop     dword ptr [rax+rax+00h]
0x140030572  test    rax, rax
0x140030575  jz      loc_1400309BE
0x14003057b  lea     r8, SmbMmSpinLock; Lock
0x140030582  mov     rdx, rax; ListEntry
0x140030585  lea     rcx, stru_140070E60; ListHead
0x14003058c  lea     r14, [rax+10h]
0x140030590  call    cs:__imp_ExInterlockedInsertTailList
0x140030597  nop     dword ptr [rax+rax+00h]
0x14003059c  mov     [r14+4], r12d
0x1400305a0  mov     dword ptr [r14], 40E204h
0x1400305a7  lea     rsi, [r14+180h]
0x1400305ae  mov     dword ptr [r14+0Ch], 1
0x1400305b6  lea     rbp, [r14+190h]
0x1400305bd  mov     dword ptr [r14+8], 1
0x1400305c5  mov     [r14+18h], rdi
0x1400305c9  mov     [rsi+8], rsi
0x1400305cd  mov     [rsi], rsi
0x1400305d0  mov     [rbp+8], rbp
0x1400305d4  mov     [rbp+0], rbp
0x1400305d8  movzx   eax, word ptr [r14+2]
0x1400305dd  test    ax, ax
0x1400305e0  jz      short loc_14003063F
0x1400305e2  mov     ecx, eax
0x1400305e4  add     rcx, r14
0x1400305e7  jz      short loc_14003063F
0x1400305e9  lea     rax, [rcx+8]
0x1400305ed  mov     dword ptr [rcx+0D0h], 0C000020Ch
0x1400305f7  mov     [rax+8], rax
0x1400305fb  mov     [rax], rax
0x1400305fe  lea     rax, [rcx+0F8h]
0x140030605  mov     [rax+8], rax
0x140030609  mov     [rax], rax
0x14003060c  lea     rax, [rcx+0D8h]
0x140030613  mov     [rax+8], rax
0x140030617  mov     [rax], rax
0x14003061a  lea     rax, [rcx+0E8h]
0x140030621  mov     [rcx+0D4h], r12d
0x140030628  sub     rcx, 0FFFFFFFFFFFFFF80h; SpinLock
0x14003062c  mov     [rax+8], rax
0x140030630  mov     [rax], rax
0x140030633  call    cs:__imp_KeInitializeSpinLock
0x14003063a  nop     dword ptr [rax+rax+00h]
0x14003063f  lea     rax, off_1400616F0
0x140030646  mov     [r14+40h], rax
0x14003064a  mov     rax, [rsp+88h+BugCheckParameter2]
0x14003064f  mov     [r14+1A0h], rax
0x140030656  movups  xmm0, xmmword ptr [r15+48h]
0x14003065b  mov     rcx, [r15+68h]
0x14003065f  movups  xmmword ptr [r14+60h], xmm0
0x140030664  movups  xmm1, xmmword ptr [r15+58h]
0x140030669  movups  xmmword ptr [r14+70h], xmm1
0x14003066e  movsd   xmm0, qword ptr [r15+68h]
0x140030674  movsd   qword ptr [r14+80h], xmm0
0x14003067d  test    rcx, rcx
0x140030680  jz      short loc_14003068E
0x140030682  call    cs:__imp_RxReferenceCredential
0x140030689  nop     dword ptr [rax+rax+00h]
0x14003068e  mov     eax, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x140030694  cmp     [r14+60h], eax
0x140030698  jnz     short loc_1400306B4
0x14003069a  mov     eax, cs:dword_14007025C
0x1400306a0  cmp     [r14+64h], eax
0x1400306a4  jnz     short loc_1400306B4
0x1400306a6  mov     eax, [r15+0BCh]
0x1400306ad  mov     [r14+1C8h], eax
0x1400306b4  mov     [r14+1C4h], ebx
0x1400306bb  lea     rbx, WPP_GLOBAL_Control
0x1400306c2  mov     [r14+1A8h], r13
0x1400306c9  cmp     [rsp+88h+arg_10], r12b
0x1400306d1  jz      loc_140030854
0x1400306d7  call    SmbCeSetComputerNameSid
0x1400306dc  mov     rcx, [rsp+88h+arg_0]
0x1400306e4  lea     r9, [rsp+88h+Size]
0x1400306e9  lea     r8, [rsp+88h+Src]
0x1400306ee  mov     rcx, [rcx+28h]; struct _SECURITY_SUBJECT_CONTEXT *
0x1400306f2  call    SmbCamSerializeToken
0x1400306f7  mov     edi, eax
0x1400306f9  test    eax, eax
0x1400306fb  js      loc_140030812
0x140030701  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030708  mov     r12, [rsp+88h+Src]
0x14003070d  mov     esi, dword ptr [rsp+88h+Size]
0x140030711  cmp     rcx, rbx
0x140030714  jz      short loc_14003073F
0x140030716  mov     eax, [rcx+2Ch]
0x140030719  test    al, 8
0x14003071b  jz      short loc_14003073F
0x14003071d  cmp     byte ptr [rcx+29h], 4
0x140030721  jb      short loc_14003073F
0x140030723  mov     rcx, [rcx+18h]
0x140030727  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14003072e  mov     edx, 1Dh
0x140030733  mov     [rsp+88h+var_68], esi
0x140030737  mov     r9, r12
0x14003073a  call    WPP_SF_qD
0x14003073f  cmp     esi, 0FFFFh
0x140030745  jbe     short loc_1400307BB
0x140030747  mov     edi, 0C0000079h
0x14003074c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030753  cmp     rcx, rbx
0x140030756  jz      short loc_14003077D
0x140030758  mov     eax, [rcx+2Ch]
0x14003075b  test    al, 8
0x14003075d  jz      short loc_14003077D
0x14003075f  cmp     byte ptr [rcx+29h], 4
0x140030763  jb      short loc_14003077D
0x140030765  mov     rcx, [rcx+18h]
0x140030769  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x140030770  mov     edx, 1Eh
0x140030775  mov     r9d, esi
0x140030778  call    WPP_SF_d
0x14003077d  test    r14, r14
0x140030780  jz      loc_1400309C3
0x140030786  mov     rcx, [r14+1D0h]; P
0x14003078d  test    rcx, rcx
0x140030790  jz      short loc_1400307AE
0x140030792  mov     edx, 6D537541h; Tag
0x140030797  call    cs:__imp_ExFreePoolWithTag
0x14003079e  nop     dword ptr [rax+rax+00h]
0x1400307a3  mov     qword ptr [r14+1D0h], 0
0x1400307ae  mov     rcx, r14
0x1400307b1  call    SmbMmFreeObjectPool
0x1400307b6  jmp     loc_1400309C3
0x1400307bb  mov     r8d, 6D537541h
0x1400307c1  mov     rdx, rsi
0x1400307c4  mov     ecx, 42h ; 'B'
0x1400307c9  call    cs:__imp_ExAllocatePool2
0x1400307d0  nop     dword ptr [rax+rax+00h]
0x1400307d5  mov     [r14+1D0h], rax
0x1400307dc  test    rax, rax
0x1400307df  jnz     short loc_1400307E8
0x1400307e1  mov     edi, 0C000009Ah
0x1400307e6  jmp     short loc_14003077D
0x1400307e8  mov     r8, rsi; Size
0x1400307eb  mov     rdx, r12; Src
0x1400307ee  mov     rcx, rax; void *
0x1400307f1  call    memmove
0x1400307f6  mov     rcx, r12
0x1400307f9  mov     [r14+1D8h], si
0x140030801  call    SmbCamFreeSerializationBuffer
0x140030806  xor     r12d, r12d
0x140030809  lea     rsi, [r14+180h]
0x140030810  jmp     short loc_140030865
0x140030812  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030819  lea     rbx, WPP_GLOBAL_Control
0x140030820  cmp     rcx, rbx
0x140030823  jz      short loc_14003084A
0x140030825  mov     eax, [rcx+2Ch]
0x140030828  test    al, 8
0x14003082a  jz      short loc_14003084A
0x14003082c  cmp     byte ptr [rcx+29h], 4
0x140030830  jb      short loc_14003084A
0x140030832  mov     rcx, [rcx+18h]
0x140030836  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14003083d  mov     edx, 1Fh
0x140030842  mov     r9d, edi
0x140030845  call    WPP_SF_d
0x14003084a  mov     r12, [rsp+88h+Src]
0x14003084f  jmp     loc_14003077D
0x140030854  xor     eax, eax
0x140030856  mov     [r14+1D0h], r12
  ... truncated ...
```
