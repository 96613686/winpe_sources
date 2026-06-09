# CmsTableSetBase::PrepareUndoForUpdatePinnedRow(CmsTransactionContext *,unsigned __int64,SmsTableSetLookupStack *)

- ea: `0x1400971f0`
- end: `0x1400975ec`
- name: `?PrepareUndoForUpdatePinnedRow@CmsTableSetBase@@QEAAJPEAVCmsTransactionContext@@_KPEAUSmsTableSetLookupStack@@@Z`
- size: `1020`
- prototype: `int(CmsTableSetBase *__hidden this, struct CmsTransactionContext *, unsigned __int64, struct SmsTableSetLookupStack *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401449a8`
- `0x140147598`

## callees

- `0x14001a0c0`
- `0x1400971f0`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140097534`
- `ntoskrnl!KdDebuggerEnabled` at `0x14009755b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400975af`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400975af`
- `ntoskrnl!ExAllocatePool2` at `0x1400972db`
- `ntoskrnl!ExAllocatePool2` at `0x1400972db`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009729e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009729e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9cc8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9cc8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400975cc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400975cc`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140097479`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140097479`

## string_xrefs

- `0x1400972f2`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsTableSetBase::PrepareUndoForUpdatePinnedRow(
        CmsTableSetBase *this,
        struct CmsTransactionContext *a2,
        __int64 a3,
        struct SmsTableSetLookupStack *a4)
{
  char *v4; // r11
  CmsTableSetBase *v6; // r8
  char *v8; // r8
  unsigned int v9; // edi
  char *v10; // rcx
  __int64 v11; // r13
  char *v12; // rbp
  int v13; // r12d
  unsigned int *v14; // rsi
  unsigned int v15; // ecx
  unsigned int v16; // r12d
  unsigned __int64 v17; // rbx
  unsigned int *v18; // r14
  unsigned __int64 v19; // rdx
  __int64 Pool2; // rax
  _DWORD *v21; // rbx
  int v22; // ecx
  _QWORD *v23; // r14
  unsigned int v24; // eax
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  __int64 v28; // rsi
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // r9d
  __int64 v32; // r10
  int v33; // r11d
  __int64 v34; // rax
  char *v35; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v36; // rcx
  _DWORD *v37; // rax

  v4 = (char *)this + 16;
  v6 = (CmsTableSetBase *)*((_QWORD *)this + 2);
  if ( v6 == (CmsTableSetBase *)((char *)this + 16) )
  {
    v9 = 0;
    v8 = 0;
  }
  else
  {
    v8 = (char *)v6 - 32;
    v9 = 0;
    do
    {
      if ( *((_QWORD *)v8 + 2) == a3 )
        break;
      v10 = (char *)*((_QWORD *)v8 + 4);
      v8 = 0;
      if ( v10 != v4 )
        v8 = v10 - 32;
    }
    while ( v8 );
  }
  if ( (v8[48] & 2) != 0 )
  {
    v35 = (char *)*((_QWORD *)v8 + 4);
    v8 = 0;
    if ( v35 != v4 )
      v8 = v35 - 32;
  }
  v11 = *(_QWORD *)v8;
  v12 = (char *)a4 + 80;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v8 + 24LL) + 44LL) & 2) == 0
    || (v13 = 2, *(_BYTE *)(*((_QWORD *)a4 + 11) + 12LL)) )
  {
    v13 = 1;
  }
  v14 = (unsigned int *)*((_QWORD *)a4 + 12);
  if ( (v14[2] & 0x40) != 0 )
    v15 = (*((unsigned __int16 *)v14 + 5) + 7) & 0xFFFFFFF8;
  else
    v15 = *v14;
  if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(v8) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)a2 + 1), 0x20000000, v8);
    return (unsigned int)-1073741670;
  }
  v16 = v15 * v13 + 40;
  v17 = ((v16 + 7) & 0xFFFFFFF8) + 88;
  v18 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v17 > *v18 )
  {
    v18 = 0;
    v19 = v17 + 16;
    goto LABEL_15;
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v36 = (struct _NPAGED_LOOKASIDE_LIST *)(v18 + 16);
    if ( *((_BYTE *)v18 + 9) )
      v37 = ExAllocateFromNPagedLookasideList(v36);
    else
      v37 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v36);
LABEL_24:
    v21 = v37;
    if ( v37 )
    {
LABEL_25:
      *(_QWORD *)v21 = v18;
      v21 += 4;
      goto LABEL_26;
    }
    goto LABEL_22;
  }
  if ( (int)*((_QWORD *)v18 + 11) > (int)HIDWORD(*((_QWORD *)v18 + 11)) )
  {
    v22 = _InterlockedDecrement((volatile signed __int32 *)v18 + 22);
    if ( v22 >= (int)v18[23] && v22 >= 0 )
    {
      v37 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v18 + 4);
      goto LABEL_24;
    }
    _InterlockedIncrement((volatile signed __int32 *)v18 + 22);
  }
LABEL_22:
  v19 = v18[1];
LABEL_15:
  Pool2 = ExAllocatePool2(66, v19, 1766871885);
  v21 = (_DWORD *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_25;
LABEL_26:
  if ( !v21 )
    return (unsigned int)-1073741670;
  v21[4] = 7;
  *((_QWORD *)v21 + 5) = v11;
  v21[3] = v16;
  v21[2] = v16;
  *((_WORD *)v21 + 10) = 0;
  *((_OWORD *)v21 + 3) = 0;
  *((_OWORD *)v21 + 4) = 0;
  *((_QWORD *)v21 + 10) = 0;
  v21[8] = 0;
  if ( v16 )
  {
    *((_QWORD *)v21 + 3) = v21 + 22;
    memset(v21 + 22, 0, v16);
    v23 = (_QWORD *)*((_QWORD *)v21 + 3);
  }
  else
  {
    *((_QWORD *)v21 + 3) = 0;
    v23 = 0;
  }
  *v23 = 0;
  v23[1] = 0;
  *((_BYTE *)v23 + 16) = 0;
  if ( (v14[2] & 0x40) != 0 )
    v24 = (*((unsigned __int16 *)v14 + 5) + 7) & 0xFFFFFFF8;
  else
    v24 = *v14;
  memmove((char *)v23 + 20, v14, v24);
  v21[2] = v16;
  v21[8] = 0;
  *((_QWORD *)v21 + 5) = v11;
  if ( v12 )
  {
    v28 = *(_QWORD *)v12;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v12 + 380LL));
    if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v28 + 560) )
      ++*(_DWORD *)(v28 + 384);
    else
      SmsPageLatch::AcquireShared((SmsPageLatch *)(v28 + 560), a2, 1);
    if ( *(char *)(*(_QWORD *)(v28 + 96) + 14LL) >= 0 )
      ++*((_DWORD *)a2 + 49);
    ++*(_DWORD *)(v28 + 388);
    v29 = *((_QWORD *)v12 + 1);
    v30 = *((_QWORD *)v12 + 2);
    v31 = *((_DWORD *)v12 + 6);
    v32 = *((_QWORD *)v12 + 4);
    v33 = *((_DWORD *)v12 + 7);
    if ( *((_QWORD *)v21 + 6) && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    *((_QWORD *)v21 + 6) = *(_QWORD *)v12;
    *((_QWORD *)v21 + 7) = v29;
    *((_QWORD *)v21 + 8) = v30;
    v21[18] = v31;
    *((_QWORD *)v21 + 10) = v32;
    v21[19] = v33;
    v34 = *(_QWORD *)v12;
    if ( *(_QWORD *)v12 && (!*(_BYTE *)(v34 + 392) && *(_QWORD *)(v34 + 96) == v11 || !*(_BYTE *)(v11 + 212)) )
      *((_BYTE *)v21 + 20) |= 1u;
  }
  else
  {
    *((_OWORD *)v21 + 3) = 0;
    *((_OWORD *)v21 + 4) = 0;
    *((_QWORD *)v21 + 10) = 0;
  }
  v25 = v21[2];
  if ( v25 )
  {
    v26 = (_QWORD *)*((_QWORD *)v21 + 3);
    if ( v23 )
    {
      if ( v23 != v26 )
        memmove(v26, v23, v25);
    }
    else
    {
      memset(v26, 0, (unsigned int)v21[2]);
    }
  }
  *(_QWORD *)v21 = *((_QWORD *)a2 + 18);
  *((_QWORD *)a2 + 18) = v21;
  return v9;
}

```

## disassembly

```asm
0x1400971f0  push    rbp
0x1400971f2  push    rsi
0x1400971f3  push    rdi
0x1400971f4  push    r13
0x1400971f6  push    r15
0x1400971f8  sub     rsp, 20h
0x1400971fc  lea     r11, [rcx+10h]
0x140097200  mov     r10, r8
0x140097203  mov     r8, [r11]
0x140097206  mov     r15, rdx
0x140097209  cmp     r8, r11
0x14009720c  jz      loc_140097350
0x140097212  add     r8, 0FFFFFFFFFFFFFFE0h
0x140097216  xor     edi, edi
0x140097218  cmp     [r8+10h], r10
0x14009721c  jz      short loc_140097235
0x14009721e  mov     rcx, [r8+20h]
0x140097222  mov     r8, rdi
0x140097225  cmp     rcx, r11
0x140097228  lea     rax, [rcx-20h]
0x14009722c  cmovnz  r8, rax
0x140097230  test    r8, r8
0x140097233  jnz     short loc_140097218
0x140097235  test    byte ptr [r8+30h], 2
0x14009723a  jnz     loc_14009756D
0x140097240  mov     r13, [r8]
0x140097243  lea     rbp, [r9+50h]
0x140097247  mov     [rsp+48h+arg_8], r12
0x14009724c  mov     rax, [r13+18h]
0x140097250  mov     ecx, [rax+2Ch]
0x140097253  test    cl, 2
0x140097256  jnz     loc_140097584
0x14009725c  mov     r12d, 1
0x140097262  mov     rsi, [rbp+10h]
0x140097266  test    byte ptr [rsi+8], 40h
0x14009726a  jnz     loc_1400972FF
0x140097270  mov     ecx, [rsi]
0x140097272  mov     eax, [rdx]
0x140097274  mov     [rsp+48h+arg_0], rbx
0x140097279  mov     [rsp+48h+arg_10], r14
0x14009727e  bt      rax, 0Ch
0x140097283  jb      loc_140097534
0x140097289  imul    r12d, ecx
0x14009728d  xor     ecx, ecx; ProcNumber
0x14009728f  add     r12d, 28h ; '('
0x140097293  lea     ebx, [r12+7]
0x140097298  and     ebx, 0FFFFFFF8h
0x14009729b  add     ebx, 58h ; 'X'
0x14009729e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400972a5  nop     dword ptr [rax+rax+00h]
0x1400972aa  xor     edx, edx
0x1400972ac  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400972b2  lea     r14, [rdx+rdx*2]
0x1400972b6  shl     r14, 6
0x1400972ba  add     r14, cs:qword_140262410
0x1400972c1  mov     eax, [r14]
0x1400972c4  cmp     rbx, rax
0x1400972c7  jbe     short loc_14009730E
0x1400972c9  mov     r14, rdi
0x1400972cc  lea     rdx, [rbx+10h]
0x1400972d0  mov     ecx, 42h ; 'B'
0x1400972d5  mov     r8d, 6950534Dh
0x1400972db  call    cs:__imp_ExAllocatePool2
0x1400972e2  nop     dword ptr [rax+rax+00h]
0x1400972e7  mov     rbx, rax
0x1400972ea  test    al, 0Fh
0x1400972ec  jz      loc_1401F9CDA
0x1400972f2  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400972f9  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400972ff  movzx   ecx, word ptr [rsi+0Ah]
0x140097303  add     ecx, 7
0x140097306  and     ecx, 0FFFFFFF8h
0x140097309  jmp     loc_140097272
0x14009730e  cmp     byte ptr [r14+8], 0
0x140097313  jnz     loc_1400975A0
0x140097319  mov     rcx, [r14+58h]
0x14009731d  mov     rax, rcx
0x140097320  shr     rax, 20h
0x140097324  cmp     ecx, eax
0x140097326  jle     short loc_14009734A
0x140097328  nop
0x140097329  mov     ecx, 0FFFFFFFFh
0x14009732e  lock xadd [r14+58h], ecx
0x140097334  nop
0x140097335  dec     ecx
0x140097337  mov     eax, [r14+5Ch]
0x14009733b  cmp     ecx, eax
0x14009733d  jge     loc_1400975C0
0x140097343  nop
0x140097344  lock inc dword ptr [r14+58h]
0x140097349  nop
0x14009734a  mov     edx, [r14+4]
0x14009734e  jmp     short loc_1400972D0
0x140097350  xor     edi, edi
0x140097352  mov     r8d, edi
0x140097355  jmp     loc_140097235
0x14009735a  mov     rbx, rax
0x14009735d  test    rax, rax
0x140097360  jz      short loc_14009734A
0x140097362  mov     [rbx], r14
0x140097365  add     rbx, 10h
0x140097369  test    rbx, rbx
0x14009736c  jz      loc_140097551
0x140097372  mov     dword ptr [rbx+10h], 7
0x140097379  xorps   xmm0, xmm0
0x14009737c  mov     [rbx+28h], r13
0x140097380  xor     eax, eax
0x140097382  mov     [rbx+0Ch], r12d
0x140097386  mov     [rbx+8], r12d
0x14009738a  mov     word ptr [rbx+14h], 0
0x140097390  movups  xmmword ptr [rbx+30h], xmm0
0x140097394  movups  xmmword ptr [rbx+40h], xmm0
0x140097398  mov     [rbx+50h], rax
0x14009739c  mov     [rbx+20h], edi
0x14009739f  test    r12d, r12d
0x1400973a2  jnz     loc_14009744A
0x1400973a8  mov     [rbx+18h], rdi
0x1400973ac  mov     r14, rdi
0x1400973af  mov     [r14], rdi
0x1400973b2  mov     [r14+8], rdi
0x1400973b6  mov     byte ptr [r14+10h], 0
0x1400973bb  test    byte ptr [rsi+8], 40h
0x1400973bf  jnz     loc_14009749D
0x1400973c5  mov     eax, [rsi]
0x1400973c7  mov     r8d, eax; Size
0x1400973ca  lea     rcx, [r14+14h]; void *
0x1400973ce  mov     rdx, rsi; Src
0x1400973d1  call    memmove
0x1400973d6  mov     [rbx+8], r12d
0x1400973da  mov     [rbx+20h], edi
0x1400973dd  mov     [rbx+28h], r13
0x1400973e1  test    rbp, rbp
0x1400973e4  jnz     short loc_140097465
0x1400973e6  xorps   xmm0, xmm0
0x1400973e9  xor     eax, eax
0x1400973eb  movups  xmmword ptr [rbx+30h], xmm0
0x1400973ef  movups  xmmword ptr [rbx+40h], xmm0
0x1400973f3  mov     [rbx+50h], rax
0x1400973f7  mov     eax, [rbx+8]
0x1400973fa  test    eax, eax
0x1400973fc  jz      short loc_14009741B
0x1400973fe  mov     rcx, [rbx+18h]; void *
0x140097402  test    r14, r14
0x140097405  jz      loc_1400975DD
0x14009740b  cmp     r14, rcx
0x14009740e  jz      short loc_14009741B
0x140097410  mov     r8d, eax; Size
0x140097413  mov     rdx, r14; Src
0x140097416  call    memmove
0x14009741b  mov     rcx, [r15+90h]
0x140097422  mov     [rbx], rcx
0x140097425  mov     [r15+90h], rbx
0x14009742c  mov     r14, [rsp+48h+arg_10]
0x140097431  mov     eax, edi
0x140097433  mov     r12, [rsp+48h+arg_8]
0x140097438  mov     rbx, [rsp+48h+arg_0]
0x14009743d  add     rsp, 20h
0x140097441  pop     r15
0x140097443  pop     r13
0x140097445  pop     rdi
0x140097446  pop     rsi
0x140097447  pop     rbp
0x140097448  retn
0x14009744a  lea     rcx, [rbx+58h]; void *
0x14009744e  mov     r8d, r12d; Size
0x140097451  xor     edx, edx; Val
0x140097453  mov     [rbx+18h], rcx
0x140097457  call    memset
0x14009745c  mov     r14, [rbx+18h]
0x140097460  jmp     loc_1400973AF
0x140097465  mov     rsi, [rbp+0]
0x140097469  nop
0x14009746a  lock inc dword ptr [rsi+17Ch]
0x140097471  lea     rcx, [rsi+230h]
0x140097478  nop
0x140097479  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140097480  nop     dword ptr [rax+rax+00h]
0x140097485  test    al, al
0x140097487  jnz     short loc_1400974AC
0x140097489  mov     r8b, 1; bool
0x14009748c  lea     rcx, [rsi+230h]; this
0x140097493  mov     rdx, r15; struct CmsTransactionContext *
0x140097496  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x14009749b  jmp     short loc_1400974B2
0x14009749d  movzx   eax, word ptr [rsi+0Ah]
0x1400974a1  add     eax, 7
0x1400974a4  and     eax, 0FFFFFFF8h
0x1400974a7  jmp     loc_1400973C7
0x1400974ac  inc     dword ptr [rsi+180h]
0x1400974b2  mov     rax, [rsi+60h]
0x1400974b6  cmp     byte ptr [rax+0Eh], 0
0x1400974ba  jl      short loc_1400974C3
0x1400974bc  inc     dword ptr [r15+0C4h]
0x1400974c3  inc     dword ptr [rsi+184h]
0x1400974c9  cmp     qword ptr [rbx+30h], 0
0x1400974ce  mov     rcx, [rbp+0]
0x1400974d2  mov     rdx, [rbp+8]
0x1400974d6  mov     r8, [rbp+10h]
0x1400974da  mov     r9d, [rbp+18h]
0x1400974de  mov     r10, [rbp+20h]
0x1400974e2  mov     r11d, [rbp+1Ch]
0x1400974e6  jnz     short loc_14009755B
0x1400974e8  mov     [rbx+30h], rcx
0x1400974ec  mov     [rbx+38h], rdx
0x1400974f0  mov     [rbx+40h], r8
0x1400974f4  mov     [rbx+48h], r9d
0x1400974f8  mov     [rbx+50h], r10
0x1400974fc  mov     [rbx+4Ch], r11d
0x140097500  mov     rax, [rbp+0]
0x140097504  test    rax, rax
0x140097507  jz      loc_1400973F7
0x14009750d  cmp     byte ptr [rax+188h], 0
0x140097514  jnz     short loc_140097525
0x140097516  cmp     [rax+60h], r13
0x14009751a  jnz     short loc_140097525
0x14009751c  or      byte ptr [rbx+14h], 1
0x140097520  jmp     loc_1400973F7
0x140097525  cmp     byte ptr [r13+0D4h], 0
0x14009752d  jz      short loc_14009751C
0x14009752f  jmp     loc_1400973F7
0x140097534  mov     rax, cs:KdDebuggerEnabled
0x14009753b  cmp     byte ptr [rax], 0
0x14009753e  jnz     short loc_14009759D
0x140097540  mov     rcx, [r15+8]
0x140097544  mov     r8b, 1
0x140097547  mov     edx, 20000000h
0x14009754c  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140097551  mov     edi, 0C000009Ah
0x140097556  jmp     loc_14009742C
0x14009755b  mov     rax, cs:KdDebuggerEnabled
0x140097562  cmp     byte ptr [rax], 0
0x140097565  jz      short loc_1400974E8
0x140097567  int     3; Trap to Debugger
0x140097568  jmp     loc_1400974E8
0x14009756d  mov     rcx, [r8+20h]
0x140097571  mov     r8, rdi
0x140097574  cmp     rcx, r11
0x140097577  lea     rax, [rcx-20h]
0x14009757b  cmovnz  r8, rax
0x14009757f  jmp     loc_140097240
0x140097584  mov     rax, [rbp+8]
0x140097588  mov     r12d, 2
0x14009758e  cmp     byte ptr [rax+0Ch], 0
0x140097592  jz      loc_140097262
0x140097598  jmp     loc_14009725C
0x14009759d  int     3; Trap to Debugger
0x14009759e  jmp     short loc_140097540
0x1400975a0  cmp     byte ptr [r14+9], 0
0x1400975a5  lea     rcx, [r14+40h]; Lookaside
0x1400975a9  jz      loc_1401F9CC8
0x1400975af  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400975b6  nop     dword ptr [rax+rax+00h]
0x1400975bb  jmp     loc_14009735A
0x1400975c0  test    ecx, ecx
0x1400975c2  js      loc_140097343
0x1400975c8  lea     rcx, [r14+40h]; ListHead
0x1400975cc  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400975d3  nop     dword ptr [rax+rax+00h]
0x1400975d8  jmp     loc_14009735A
0x1400975dd  mov     r8, rax; Size
0x1400975e0  xor     edx, edx; Val
0x1400975e2  call    memset
0x1400975e7  jmp     loc_14009741B
0x1401f9cc8  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f9ccf  nop     dword ptr [rax+rax+00h]
0x1401f9cd4  nop
0x1401f9cd5  jmp     loc_14009735A
0x1401f9cda  test    rax, rax
0x1401f9cdd  jz      loc_140097369
0x1401f9ce3  jmp     loc_140097362
```
