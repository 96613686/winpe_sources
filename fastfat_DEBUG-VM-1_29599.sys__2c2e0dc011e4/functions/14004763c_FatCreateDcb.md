# FatCreateDcb

- ea: `0x14004763c`
- end: `0x140047957`
- name: `FatCreateDcb`
- size: `795`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400268c0`
- `0x140028cc0`
- `0x14002aae8`

## callees

- `0x1400062c8`
- `0x14000656c`
- `0x14000c680`
- `0x1400471f8`
- `0x14004763c`
- `0x140049380`
- `0x140049428`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140047813`
- `ntoskrnl!KeInitializeEvent` at `0x140047813`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400477a6`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400477a6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400476b4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400476b4`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14004791a`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14004791a`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14005fa51`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14005fa51`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fa67`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fa67`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140047874`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140047874`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005facd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005facd`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400478fc`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400478fc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004768c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004768c`

## pseudocode

```c
_DWORD *__fastcall FatCreateDcb(
        union _LARGE_INTEGER a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  _DWORD *PoolWithTag; // rdi
  PVOID v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 v23; // r8
  union _LARGE_INTEGER v24; // rax
  __int64 v25; // rcx
  union _LARGE_INTEGER v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // ecx
  __int64 v31; // rcx
  __int64 v33; // [rsp+20h] [rbp-78h]
  __int64 v34; // [rsp+28h] [rbp-70h]
  __int64 v35; // [rsp+30h] [rbp-68h]
  union _LARGE_INTEGER SystemTime; // [rsp+A0h] [rbp+8h] BYREF

  SystemTime = a1;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x278u, 0x46746146u);
  memset(PoolWithTag, 0, 0x278u);
  v11 = ExAllocateFromNPagedLookasideList(&FatNonPagedFcbLookasideList);
  *((_QWORD *)PoolWithTag + 15) = v11;
  memset(v11, 0, 0x78u);
  *PoolWithTag = 41420035;
  PoolWithTag[49] = 1;
  *((_QWORD *)PoolWithTag + 1) = FatAllocateResource(v13, v12, v14, v15, 0, 0, 0);
  *((_QWORD *)PoolWithTag + 2) = FatAllocateResource(v17, v16, v18, v19, v33, v34, v35);
  v20 = (_QWORD *)(a3 + 320);
  v21 = *(_QWORD *)(a3 + 320);
  if ( *(_QWORD *)(v21 + 8) != a3 + 320 )
    __fastfail(3u);
  *((_QWORD *)PoolWithTag + 20) = v21;
  *((_QWORD *)PoolWithTag + 21) = v20;
  *(_QWORD *)(v21 + 8) = PoolWithTag + 40;
  *v20 = PoolWithTag + 40;
  *((_QWORD *)PoolWithTag + 22) = a3;
  *((_QWORD *)PoolWithTag + 23) = a2;
  PoolWithTag[62] = a4;
  PoolWithTag[61] = a5;
  v22 = a6;
  *((_BYTE *)PoolWithTag + 546) = *(_BYTE *)(a6 + 11);
  *((_QWORD *)PoolWithTag + 34) = FatFatTimeToNtTime(v20, *(unsigned int *)(v22 + 22), 0);
  if ( (byte_140017D4C & 1) != 0 )
  {
    v24.QuadPart = 0;
    SystemTime.QuadPart = 0;
    v25 = *(unsigned __int16 *)(v22 + 18);
    if ( ((unsigned __int16)v25 & *(_WORD *)(v22 + 16)) == 0 )
    {
      ExLocalTimeToSystemTime(&FatJanOne1980, &SystemTime);
      v24 = SystemTime;
    }
    if ( *(_WORD *)(v22 + 18) )
      v24.QuadPart = FatFatDateToNtTime(v25, *(unsigned __int16 *)(v22 + 18));
    *((union _LARGE_INTEGER *)PoolWithTag + 33) = v24;
    if ( *(_WORD *)(v22 + 16) )
    {
      LOBYTE(v23) = *(_BYTE *)(v22 + 13);
      v26.QuadPart = FatFatTimeToNtTime(v25, *(unsigned int *)(v22 + 14), v23);
    }
    else
    {
      v26 = SystemTime;
    }
    *((union _LARGE_INTEGER *)PoolWithTag + 32) = v26;
  }
  v27 = *((_QWORD *)PoolWithTag + 15);
  *(_DWORD *)(v27 + 40) = 1;
  *(_QWORD *)(v27 + 48) = 0;
  *(_DWORD *)(v27 + 56) = 0;
  KeInitializeEvent((PRKEVENT)(v27 + 64), SynchronizationEvent, 0);
  v28 = *((_QWORD *)PoolWithTag + 15);
  *((_BYTE *)PoolWithTag + 4) |= 0x40u;
  *((_BYTE *)PoolWithTag + 6) |= 2u;
  *((_BYTE *)PoolWithTag + 7) = *((_BYTE *)PoolWithTag + 7) & 0xF | 0x50;
  *((_QWORD *)PoolWithTag + 8) = PoolWithTag + 14;
  *((_QWORD *)PoolWithTag + 7) = PoolWithTag + 14;
  v29 = v28 + 40;
  if ( v29 )
    *((_QWORD *)PoolWithTag + 6) = v29;
  *((_QWORD *)PoolWithTag + 9) = 0;
  *((_QWORD *)PoolWithTag + 10) = 0;
  *((_QWORD *)PoolWithTag + 11) = 0;
  *((_QWORD *)PoolWithTag + 12) = 0;
  PoolWithTag[26] = 0;
  *((_QWORD *)PoolWithTag + 14) = 0;
  FsRtlInitializeLargeMcb((PLARGE_MCB)PoolWithTag + 9, PagedPool);
  v30 = *(unsigned __int16 *)(v22 + 26);
  PoolWithTag[32] = v30;
  if ( *(_BYTE *)(*((_QWORD *)PoolWithTag + 23) + 376LL) == 32 )
  {
    v30 += *(unsigned __int16 *)(v22 + 20) << 16;
    PoolWithTag[32] = v30;
  }
  *((_QWORD *)PoolWithTag + 3) = -(__int64)(v30 != 0);
  if ( (*(_DWORD *)(a2 + 200) & 0x400000) != 0 && (*(_BYTE *)(v22 + 12) & 1) != 0 )
  {
    PoolWithTag[48] |= 0x20000u;
    PoolWithTag[48] |= 0x40000u;
  }
  *((_QWORD *)PoolWithTag + 41) = PoolWithTag + 80;
  *((_QWORD *)PoolWithTag + 40) = PoolWithTag + 80;
  RtlInitializeBitMap((PRTL_BITMAP)PoolWithTag + 25, 0, 0);
  PoolWithTag[94] = -1;
  PoolWithTag[95] = -1;
  FsRtlInitializeOplock((POPLOCK)PoolWithTag + 11);
  FatConstructNamesInFcb(v31, PoolWithTag, v22, a7);
  *((_BYTE *)PoolWithTag + 496) = 1;
  return PoolWithTag;
}

```

## disassembly

```asm
0x14004763c  mov     rax, rsp
0x14004763f  mov     [rax+8], rcx
0x140047643  push    rbx
0x140047644  push    rsi
0x140047645  push    rdi
0x140047646  push    r12
0x140047648  push    r14
0x14004764a  push    r15
0x14004764c  sub     rsp, 68h
0x140047650  mov     esi, r9d
0x140047653  mov     rbx, r8
0x140047656  mov     r15, rdx
0x140047659  xorps   xmm0, xmm0
0x14004765c  movdqu  xmmword ptr [rax-50h], xmm0
0x140047661  xor     r12d, r12d
0x140047664  mov     [rax-60h], r12
0x140047668  mov     [rax-58h], r12
0x14004766c  mov     [rax-68h], r12
0x140047670  mov     [rax-70h], r12
0x140047674  mov     [rax-78h], r12
0x140047678  mov     r8d, 46746146h; Tag
0x14004767e  mov     r14d, 278h
0x140047684  mov     edx, r14d; NumberOfBytes
0x140047687  mov     ecx, 411h; PoolType
0x14004768c  call    cs:__imp_ExAllocatePoolWithTag
0x140047693  nop     dword ptr [rax+rax+00h]
0x140047698  mov     rdi, rax
0x14004769b  mov     [rsp+98h+var_50], rax
0x1400476a0  mov     r8d, r14d; Size
0x1400476a3  xor     edx, edx; Val
0x1400476a5  mov     rcx, rax; void *
0x1400476a8  call    memset
0x1400476ad  lea     rcx, FatNonPagedFcbLookasideList; Lookaside
0x1400476b4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400476bb  nop     dword ptr [rax+rax+00h]
0x1400476c0  mov     [rdi+78h], rax
0x1400476c4  mov     [rsp+98h+var_48], rax
0x1400476c9  xor     edx, edx; Val
0x1400476cb  lea     r8d, [r12+78h]; Size
0x1400476d0  mov     rcx, rax; void *
0x1400476d3  call    memset
0x1400476d8  mov     dword ptr [rdi], 2780503h
0x1400476de  mov     dword ptr [rdi+0C4h], 1
0x1400476e8  call    FatAllocateResource
0x1400476ed  mov     [rdi+8], rax
0x1400476f1  mov     [rsp+98h+var_60], rax
0x1400476f6  call    FatAllocateResource
0x1400476fb  mov     [rdi+10h], rax
0x1400476ff  mov     [rsp+98h+var_58], rax
0x140047704  lea     rcx, [rbx+140h]
0x14004770b  mov     rdx, [rcx]
0x14004770e  cmp     [rdx+8], rcx
0x140047712  jz      short loc_14004771B
0x140047714  lea     ecx, [r12+3]
0x140047719  int     29h; Win8: RtlFailFast(ecx)
0x14004771b  lea     rax, [rdi+0A0h]
0x140047722  mov     [rax], rdx
0x140047725  mov     [rax+8], rcx
0x140047729  mov     [rdx+8], rax
0x14004772d  mov     [rcx], rax
0x140047730  mov     [rsp+98h+var_68], rax
0x140047735  mov     [rdi+0B0h], rbx
0x14004773c  mov     [rdi+0B8h], r15
0x140047743  mov     [rdi+0F8h], esi
0x140047749  mov     eax, [rsp+98h+arg_20]
0x140047750  mov     [rdi+0F4h], eax
0x140047756  mov     rsi, [rsp+98h+arg_28]
0x14004775e  mov     al, [rsi+0Bh]
0x140047761  mov     [rdi+222h], al
0x140047767  xor     r8d, r8d
0x14004776a  mov     edx, [rsi+16h]
0x14004776d  call    FatFatTimeToNtTime
0x140047772  mov     [rdi+110h], rax
0x140047779  test    cs:byte_140017D4C, 1
0x140047780  jz      short loc_1400477F5
0x140047782  mov     rax, r12
0x140047785  mov     qword ptr [rsp+98h+SystemTime], rax
0x14004778d  movzx   ecx, word ptr [rsi+12h]
0x140047791  test    [rsi+10h], cx
0x140047795  jnz     short loc_1400477BA
0x140047797  lea     rdx, [rsp+98h+SystemTime]; SystemTime
0x14004779f  lea     rcx, FatJanOne1980; LocalTime
0x1400477a6  call    cs:__imp_ExLocalTimeToSystemTime
0x1400477ad  nop     dword ptr [rax+rax+00h]
0x1400477b2  mov     rax, qword ptr [rsp+98h+SystemTime]
0x1400477ba  cmp     [rsi+12h], r12w
0x1400477bf  jz      short loc_1400477CA
0x1400477c1  movzx   edx, word ptr [rsi+12h]
0x1400477c5  call    FatFatDateToNtTime
0x1400477ca  mov     [rdi+108h], rax
0x1400477d1  cmp     [rsi+10h], r12w
0x1400477d6  jz      short loc_1400477E6
0x1400477d8  mov     r8b, [rsi+0Dh]
0x1400477dc  mov     edx, [rsi+0Eh]
0x1400477df  call    FatFatTimeToNtTime
0x1400477e4  jmp     short loc_1400477EE
0x1400477e6  mov     rax, qword ptr [rsp+98h+SystemTime]
0x1400477ee  mov     [rdi+100h], rax
0x1400477f5  mov     rcx, [rdi+78h]
0x1400477f9  mov     dword ptr [rcx+28h], 1
0x140047800  mov     [rcx+30h], r12
0x140047804  mov     [rcx+38h], r12d
0x140047808  add     rcx, 40h ; '@'; Event
0x14004780c  xor     r8d, r8d; State
0x14004780f  lea     edx, [r8+1]; Type
0x140047813  call    cs:__imp_KeInitializeEvent
0x14004781a  nop     dword ptr [rax+rax+00h]
0x14004781f  mov     rcx, [rdi+78h]
0x140047823  or      byte ptr [rdi+4], 40h
0x140047827  or      byte ptr [rdi+6], 2
0x14004782b  mov     al, [rdi+7]
0x14004782e  and     al, 0Fh
0x140047830  or      al, 50h
0x140047832  mov     [rdi+7], al
0x140047835  lea     rax, [rdi+38h]
0x140047839  mov     [rax+8], rax
0x14004783d  mov     [rax], rax
0x140047840  add     rcx, 28h ; '('
0x140047844  jz      short loc_14004784A
0x140047846  mov     [rdi+30h], rcx
0x14004784a  mov     [rdi+48h], r12
0x14004784e  mov     [rdi+50h], r12
0x140047852  lea     r14, [rdi+58h]
0x140047856  mov     [r14], r12
0x140047859  mov     [rdi+60h], r12
0x14004785d  mov     [rdi+68h], r12d
0x140047861  mov     [rdi+70h], r12
0x140047865  lea     rbx, [rdi+120h]
0x14004786c  mov     edx, 1; PoolType
0x140047871  mov     rcx, rbx; Mcb
0x140047874  call    cs:__imp_FsRtlInitializeLargeMcb
0x14004787b  nop     dword ptr [rax+rax+00h]
0x140047880  mov     [rsp+98h+var_70], rbx
0x140047885  movzx   ecx, word ptr [rsi+1Ah]
0x140047889  mov     [rdi+80h], ecx
0x14004788f  mov     rax, [rdi+0B8h]
0x140047896  cmp     byte ptr [rax+178h], 20h ; ' '
0x14004789d  jnz     short loc_1400478AE
0x14004789f  movzx   eax, word ptr [rsi+14h]
0x1400478a3  shl     eax, 10h
0x1400478a6  add     ecx, eax
0x1400478a8  mov     [rdi+80h], ecx
0x1400478ae  neg     ecx
0x1400478b0  sbb     rax, rax
0x1400478b3  mov     [rdi+18h], rax
0x1400478b7  mov     eax, [r15+0C8h]
0x1400478be  bt      eax, 16h
0x1400478c2  jnb     short loc_1400478E2
0x1400478c4  test    byte ptr [rsi+0Ch], 1
0x1400478c8  jz      short loc_1400478E2
0x1400478ca  bts     dword ptr [rdi+0C0h], 11h
0x1400478d2  mov     eax, [rdi+0C0h]
0x1400478d8  bts     eax, 12h
0x1400478dc  mov     [rdi+0C0h], eax
0x1400478e2  lea     rax, [rdi+140h]
0x1400478e9  mov     [rax+8], rax
0x1400478ed  mov     [rax], rax
0x1400478f0  lea     rcx, [rdi+190h]; BitMapHeader
0x1400478f7  xor     r8d, r8d; SizeOfBitMap
0x1400478fa  xor     edx, edx; BitMapBuffer
0x1400478fc  call    cs:__imp_RtlInitializeBitMap
0x140047903  nop     dword ptr [rax+rax+00h]
0x140047908  or      eax, 0FFFFFFFFh
0x14004790b  mov     [rdi+178h], eax
0x140047911  mov     [rdi+17Ch], eax
0x140047917  mov     rcx, r14; Oplock
0x14004791a  call    cs:__imp_FsRtlInitializeOplock
0x140047921  nop     dword ptr [rax+rax+00h]
0x140047926  mov     [rsp+98h+var_78], r14
0x14004792b  mov     r9, [rsp+98h+arg_30]
0x140047933  mov     r8, rsi
0x140047936  mov     rdx, rdi
0x140047939  call    FatConstructNamesInFcb
0x14004793e  mov     byte ptr [rdi+1F0h], 1
0x140047945  mov     rax, rdi
0x140047948  add     rsp, 68h
0x14004794c  pop     r15
0x14004794e  pop     r14
0x140047950  pop     r12
0x140047952  pop     rdi
0x140047953  pop     rsi
0x140047954  pop     rbx
0x140047955  retn
0x14005fa33  push    rbx
0x14005fa35  push    rbp
0x14005fa36  sub     rsp, 28h
0x14005fa3a  mov     rbp, rdx
0x14005fa3d  movzx   eax, cl
0x14005fa40  test    cl, cl
0x14005fa42  jz      loc_14005FAE1
0x14005fa48  mov     rcx, [rbp+20h]; Oplock
0x14005fa4c  test    rcx, rcx
0x14005fa4f  jz      short loc_14005FA5E
0x14005fa51  call    cs:__imp_FsRtlUninitializeOplock
0x14005fa58  nop     dword ptr [rax+rax+00h]
0x14005fa5d  nop
0x14005fa5e  mov     rcx, [rbp+28h]; Mcb
0x14005fa62  test    rcx, rcx
0x14005fa65  jz      short loc_14005FA74
0x14005fa67  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14005fa6e  nop     dword ptr [rax+rax+00h]
0x14005fa73  nop
0x14005fa74  mov     rax, [rbp+30h]
0x14005fa78  test    rax, rax
0x14005fa7b  jz      short loc_14005FA9F
0x14005fa7d  mov     rdx, [rax]
0x14005fa80  mov     rcx, [rax+8]
0x14005fa84  cmp     [rdx+8], rax
0x14005fa88  jnz     short loc_14005FA98
0x14005fa8a  cmp     [rcx], rax
0x14005fa8d  jnz     short loc_14005FA98
0x14005fa8f  mov     [rcx], rdx
0x14005fa92  mov     [rdx+8], rcx
0x14005fa96  jmp     short loc_14005FA9F
0x14005fa98  mov     ecx, 3
0x14005fa9d  int     29h; Win8: RtlFailFast(ecx)
0x14005fa9f  mov     rcx, [rbp+38h]; Entry
0x14005faa3  test    rcx, rcx
0x14005faa6  jz      short loc_14005FAAE
0x14005faa8  call    FatFreeResource
0x14005faad  nop
0x14005faae  mov     rcx, [rbp+40h]; Entry
0x14005fab2  test    rcx, rcx
0x14005fab5  jz      short loc_14005FABD
0x14005fab7  call    FatFreeResource
0x14005fabc  nop
0x14005fabd  xor     ebx, ebx
0x14005fabf  mov     eax, ebx
0x14005fac1  mov     rcx, [rbp+rbx*8+48h]; P
0x14005fac6  test    rcx, rcx
0x14005fac9  jz      short loc_14005FADA
0x14005facb  xor     edx, edx; Tag
0x14005facd  call    cs:__imp_ExFreePoolWithTag
0x14005fad4  nop     dword ptr [rax+rax+00h]
0x14005fad9  nop
0x14005fada  inc     ebx
0x14005fadc  cmp     ebx, 2
0x14005fadf  jb      short loc_14005FABF
0x14005fae1  add     rsp, 28h
0x14005fae5  pop     rbp
0x14005fae6  pop     rbx
0x14005fae7  retn
```
