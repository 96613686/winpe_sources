# FltpInitializeFilterVerifier

- ea: `0x180057058`
- end: `0x1800573e7`
- name: `FltpInitializeFilterVerifier`
- size: `911`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004c810`

## callees

- `0x180009f20`
- `0x180024534`
- `0x180057058`
- `0x18007c010`
- `0x18007c408`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005718d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800571a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005718d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800571a5`
- `ntoskrnl!ExAllocatePool2` at `0x1800570af`
- `ntoskrnl!ExAllocatePool2` at `0x1800570fa`
- `ntoskrnl!ExAllocatePool2` at `0x1800570af`
- `ntoskrnl!ExAllocatePool2` at `0x1800570fa`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800573a5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800573a5`
- `ntoskrnl!KeInitializeSpinLock` at `0x180057368`
- `ntoskrnl!KeInitializeSpinLock` at `0x180057368`
- `ntoskrnl!DbgPrintEx` at `0x1800573c8`
- `ntoskrnl!DbgPrintEx` at `0x1800573c8`
- `ntoskrnl!MmIsDriverSuspectForVerifier` at `0x18005707b`
- `ntoskrnl!MmIsDriverSuspectForVerifier` at `0x18005707b`
- `ntoskrnl!MmLockPagableDataSection` at `0x1800571cb`
- `ntoskrnl!MmLockPagableDataSection` at `0x1800571cb`

## pseudocode

```c
__int64 __fastcall FltpInitializeFilterVerifier(__int64 a1)
{
  __int64 Pool2; // rax
  __int64 v3; // r9
  unsigned int v4; // ebx
  __int64 v6; // r9
  char *v7; // rcx
  __int64 v8; // r9
  PVOID v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned __int8 v18; // al
  __int64 v19; // r8
  __int64 v20; // r8

  if ( FltpVerifierTurnedOn
    && (unsigned int)MmIsDriverSuspectForVerifier(*(_QWORD *)(a1 + 104))
    && (FltGlobals[0] & 0x100) == 0 )
  {
    Pool2 = ExAllocatePool2(64, 1152, 1719029062);
    *(_QWORD *)(a1 + 240) = Pool2;
    if ( !Pool2 )
    {
      v4 = -1073741670;
      FltpvPrintErrors(79, a1, 3221225626LL, v3);
      return v4;
    }
    *(_QWORD *)(Pool2 + 872) = ExAllocatePool2(64, (*(unsigned __int16 *)(a1 + 64) >> 1) + 1, 1667321158);
    v7 = *(char **)(*(_QWORD *)(a1 + 240) + 872LL);
    if ( !v7 )
    {
      v4 = -1073741670;
      FltpvPrintErrors(79, a1, 3221225626LL, v6);
LABEL_11:
      ExFreePoolWithTag(*(PVOID *)(a1 + 240), 0x66764D46u);
      *(_QWORD *)(a1 + 240) = 0;
      return v4;
    }
    v4 = RtlStringCbPrintfA(v7, (*(unsigned __int16 *)(a1 + 64) >> 1) + 1, "%wZ", a1 + 64);
    if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\verifiersup.c", 2822, 0) < 0 )
    {
      FltpvPrintErrors(79, a1, v4, v8);
      ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a1 + 240) + 872LL), 0x63614D46u);
      goto LABEL_11;
    }
    v9 = MmLockPagableDataSection(FltvPreOperation);
    v10 = *(_QWORD *)(a1 + 272);
    FltpVerifierCodeSectionHandle = v9;
    if ( v10 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 16LL) = v10;
      *(_QWORD *)(a1 + 272) = FltvInstanceSetup;
    }
    v11 = *(_QWORD *)(a1 + 280);
    if ( v11 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 24LL) = v11;
      *(_QWORD *)(a1 + 280) = FltvInstanceQueryTeardown;
    }
    v12 = *(_QWORD *)(a1 + 288);
    if ( v12 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 32LL) = v12;
      *(_QWORD *)(a1 + 288) = FltvInstanceTeardownStart;
    }
    v13 = *(_QWORD *)(a1 + 296);
    if ( v13 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 40LL) = v13;
      *(_QWORD *)(a1 + 296) = FltvInstanceTeardownComplete;
    }
    v14 = *(_QWORD *)(a1 + 384);
    if ( v14 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 48LL) = v14;
      *(_QWORD *)(a1 + 384) = FltvGenerateFileName;
    }
    v15 = *(_QWORD *)(a1 + 392);
    if ( v15 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 56LL) = v15;
      *(_QWORD *)(a1 + 392) = FltvNormalizeNameComponent;
    }
    v16 = *(_QWORD *)(a1 + 400);
    if ( v16 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 240) + 64LL) = v16;
      *(_QWORD *)(a1 + 400) = FltvNormalizeNameComponentEx;
    }
    v17 = *(_QWORD *)(a1 + 432);
    if ( v17 )
    {
      while ( *(_BYTE *)v17 != 0x80 )
      {
        v18 = *(_BYTE *)v17 + 22;
        if ( v18 < 0x32u )
        {
          v19 = *(_QWORD *)(v17 + 8);
          if ( v19 )
          {
            *(_QWORD *)(*(_QWORD *)(a1 + 240) + 16LL * v18 + 72) = v19;
            *(_QWORD *)(v17 + 8) = FltvPreOperation;
          }
          v20 = *(_QWORD *)(v17 + 16);
          if ( v20 )
          {
            *(_QWORD *)(*(_QWORD *)(a1 + 240) + 16 * (v18 + 5LL)) = v20;
            *(_QWORD *)(v17 + 16) = FltvPostOperation;
          }
        }
        v17 += 32;
      }
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 240) + 1024LL) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 240) + 1032LL));
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 240) + 896LL),
      0,
      0,
      0x200u,
      0x50u,
      0x6A764D46u,
      0);
    FltpLinkFilter(a1);
    DbgPrintEx(0x2Fu, 0, "[FltMgr] Mini-filter verification enabled for \"%wZ\" filter.\n", a1 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x180057058  mov     [rsp+arg_0], rbx
0x18005705d  mov     [rsp+arg_8], rsi
0x180057062  push    rdi
0x180057063  sub     rsp, 40h
0x180057067  cmp     cs:FltpVerifierTurnedOn, 0
0x18005706e  mov     rdi, rcx
0x180057071  jz      loc_1800573D4
0x180057077  mov     rcx, [rcx+68h]
0x18005707b  call    cs:__imp_MmIsDriverSuspectForVerifier
0x180057082  nop     dword ptr [rax+rax+00h]
0x180057087  test    eax, eax
0x180057089  jz      loc_1800573D4
0x18005708f  test    cs:FltGlobals, 100h
0x180057099  jnz     loc_1800573D4
0x18005709f  mov     edx, 480h
0x1800570a4  mov     ecx, 40h ; '@'
0x1800570a9  mov     r8d, 66764D46h
0x1800570af  call    cs:__imp_ExAllocatePool2
0x1800570b6  nop     dword ptr [rax+rax+00h]
0x1800570bb  mov     [rdi+0F0h], rax
0x1800570c2  test    rax, rax
0x1800570c5  jnz     short loc_1800570E1
0x1800570c7  mov     ebx, 0C000009Ah
0x1800570cc  lea     ecx, [rax+4Fh]
0x1800570cf  mov     r8d, ebx
0x1800570d2  mov     rdx, rdi
0x1800570d5  call    FltpvPrintErrors
0x1800570da  mov     eax, ebx
0x1800570dc  jmp     loc_1800573D6
0x1800570e1  lea     rsi, [rdi+40h]
0x1800570e5  mov     ecx, 40h ; '@'
0x1800570ea  movzx   edx, word ptr [rsi]
0x1800570ed  mov     r8d, 63614D46h
0x1800570f3  shr     edx, 1
0x1800570f5  mov     rbx, rax
0x1800570f8  inc     edx
0x1800570fa  call    cs:__imp_ExAllocatePool2
0x180057101  nop     dword ptr [rax+rax+00h]
0x180057106  mov     [rbx+368h], rax
0x18005710d  mov     rax, [rdi+0F0h]
0x180057114  mov     rcx, [rax+368h]; pszDest
0x18005711b  test    rcx, rcx
0x18005711e  jnz     short loc_180057137
0x180057120  mov     ebx, 0C000009Ah
0x180057125  mov     rdx, rdi
0x180057128  mov     r8d, ebx
0x18005712b  mov     ecx, 4Fh ; 'O'
0x180057130  call    FltpvPrintErrors
0x180057135  jmp     short loc_180057199
0x180057137  movzx   edx, word ptr [rsi]
0x18005713a  lea     r8, pszFormat; "%wZ"
0x180057141  shr     edx, 1
0x180057143  mov     r9, rsi
0x180057146  inc     edx; cbDest
0x180057148  call    RtlStringCbPrintfA
0x18005714d  mov     r8d, 0B06h
0x180057153  lea     rdx, aMinkernelFsFil; "minkernel\\fs\\filtermgr\\filter\\verif"...
0x18005715a  xor     r9d, r9d
0x18005715d  mov     ecx, eax
0x18005715f  mov     ebx, eax
0x180057161  call    FltpDbgStatus
0x180057166  test    eax, eax
0x180057168  jns     short loc_1800571C1
0x18005716a  mov     r8d, ebx
0x18005716d  mov     rdx, rdi
0x180057170  mov     ecx, 4Fh ; 'O'
0x180057175  call    FltpvPrintErrors
0x18005717a  mov     rcx, [rdi+0F0h]
0x180057181  mov     edx, 63614D46h; Tag
0x180057186  mov     rcx, [rcx+368h]; P
0x18005718d  call    cs:__imp_ExFreePoolWithTag
0x180057194  nop     dword ptr [rax+rax+00h]
0x180057199  mov     rcx, [rdi+0F0h]; P
0x1800571a0  mov     edx, 66764D46h; Tag
0x1800571a5  call    cs:__imp_ExFreePoolWithTag
0x1800571ac  nop     dword ptr [rax+rax+00h]
0x1800571b1  mov     qword ptr [rdi+0F0h], 0
0x1800571bc  jmp     loc_1800570DA
0x1800571c1  lea     rbx, FltvPreOperation
0x1800571c8  mov     rcx, rbx; AddressWithinSection
0x1800571cb  call    cs:__imp_MmLockPagableDataSection
0x1800571d2  nop     dword ptr [rax+rax+00h]
0x1800571d7  mov     rcx, [rdi+110h]
0x1800571de  mov     cs:FltpVerifierCodeSectionHandle, rax
0x1800571e5  test    rcx, rcx
0x1800571e8  jz      short loc_180057203
0x1800571ea  mov     rax, [rdi+0F0h]
0x1800571f1  mov     [rax+10h], rcx
0x1800571f5  lea     rax, FltvInstanceSetup
0x1800571fc  mov     [rdi+110h], rax
0x180057203  mov     rcx, [rdi+118h]
0x18005720a  test    rcx, rcx
0x18005720d  jz      short loc_180057228
0x18005720f  mov     rax, [rdi+0F0h]
0x180057216  mov     [rax+18h], rcx
0x18005721a  lea     rax, FltvInstanceQueryTeardown
0x180057221  mov     [rdi+118h], rax
0x180057228  mov     rcx, [rdi+120h]
0x18005722f  test    rcx, rcx
0x180057232  jz      short loc_18005724D
0x180057234  mov     rax, [rdi+0F0h]
0x18005723b  mov     [rax+20h], rcx
0x18005723f  lea     rax, FltvInstanceTeardownStart
0x180057246  mov     [rdi+120h], rax
0x18005724d  mov     rcx, [rdi+128h]
0x180057254  test    rcx, rcx
0x180057257  jz      short loc_180057272
0x180057259  mov     rax, [rdi+0F0h]
0x180057260  mov     [rax+28h], rcx
0x180057264  lea     rax, FltvInstanceTeardownComplete
0x18005726b  mov     [rdi+128h], rax
0x180057272  mov     rcx, [rdi+180h]
0x180057279  test    rcx, rcx
0x18005727c  jz      short loc_180057297
0x18005727e  mov     rax, [rdi+0F0h]
0x180057285  mov     [rax+30h], rcx
0x180057289  lea     rax, FltvGenerateFileName
0x180057290  mov     [rdi+180h], rax
0x180057297  mov     rcx, [rdi+188h]
0x18005729e  test    rcx, rcx
0x1800572a1  jz      short loc_1800572BC
0x1800572a3  mov     rax, [rdi+0F0h]
0x1800572aa  mov     [rax+38h], rcx
0x1800572ae  lea     rax, FltvNormalizeNameComponent
0x1800572b5  mov     [rdi+188h], rax
0x1800572bc  mov     rcx, [rdi+190h]
0x1800572c3  test    rcx, rcx
0x1800572c6  jz      short loc_1800572E1
0x1800572c8  mov     rax, [rdi+0F0h]
0x1800572cf  mov     [rax+40h], rcx
0x1800572d3  lea     rax, FltvNormalizeNameComponentEx
0x1800572da  mov     [rdi+190h], rax
0x1800572e1  mov     rdx, [rdi+1B0h]
0x1800572e8  test    rdx, rdx
0x1800572eb  jz      short loc_180057348
0x1800572ed  jmp     short loc_180057342
0x1800572ef  add     al, 16h
0x1800572f1  cmp     al, 32h ; '2'
0x1800572f3  jnb     short loc_18005733E
0x1800572f5  mov     r8, [rdx+8]
0x1800572f9  movzx   r9d, al
0x1800572fd  test    r8, r8
0x180057300  jz      short loc_180057318
0x180057302  mov     rax, [rdi+0F0h]
0x180057309  mov     ecx, r9d
0x18005730c  add     rcx, rcx
0x18005730f  mov     [rax+rcx*8+48h], r8
0x180057314  mov     [rdx+8], rbx
0x180057318  mov     r8, [rdx+10h]
0x18005731c  test    r8, r8
0x18005731f  jz      short loc_18005733E
0x180057321  mov     rax, [rdi+0F0h]
0x180057328  lea     rcx, [r9+5]
0x18005732c  add     rcx, rcx
0x18005732f  mov     [rax+rcx*8], r8
0x180057333  lea     rax, FltvPostOperation
0x18005733a  mov     [rdx+10h], rax
0x18005733e  add     rdx, 20h ; ' '
0x180057342  mov     al, [rdx]
0x180057344  cmp     al, 80h
0x180057346  jnz     short loc_1800572EF
0x180057348  mov     rax, [rdi+0F0h]
0x18005734f  mov     qword ptr [rax+400h], 0
0x18005735a  mov     rcx, [rdi+0F0h]
0x180057361  add     rcx, 408h; SpinLock
0x180057368  call    cs:__imp_KeInitializeSpinLock
0x18005736f  nop     dword ptr [rax+rax+00h]
0x180057374  mov     rcx, [rdi+0F0h]
0x18005737b  xor     eax, eax
0x18005737d  mov     [rsp+48h+Depth], ax; Depth
0x180057382  add     rcx, 380h; Lookaside
0x180057389  mov     [rsp+48h+Tag], 6A764D46h; Tag
0x180057391  mov     r9d, 200h; Flags
0x180057397  xor     r8d, r8d; Free
0x18005739a  mov     [rsp+48h+Size], 50h ; 'P'; Size
0x1800573a3  xor     edx, edx; Allocate
0x1800573a5  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800573ac  nop     dword ptr [rax+rax+00h]
0x1800573b1  mov     rcx, rdi
0x1800573b4  call    FltpLinkFilter
0x1800573b9  xor     edx, edx; Level
0x1800573bb  lea     r8, Format; "[FltMgr] Mini-filter verification enabl"...
0x1800573c2  mov     r9, rsi
0x1800573c5  lea     ecx, [rdx+2Fh]; ComponentId
0x1800573c8  call    cs:__imp_DbgPrintEx
0x1800573cf  nop     dword ptr [rax+rax+00h]
0x1800573d4  xor     eax, eax
0x1800573d6  mov     rbx, [rsp+48h+arg_0]
0x1800573db  mov     rsi, [rsp+48h+arg_8]
0x1800573e0  add     rsp, 40h
0x1800573e4  pop     rdi
0x1800573e5  retn
```
