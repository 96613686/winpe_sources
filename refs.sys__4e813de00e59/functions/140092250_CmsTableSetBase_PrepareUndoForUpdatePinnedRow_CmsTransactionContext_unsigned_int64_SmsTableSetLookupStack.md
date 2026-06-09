# CmsTableSetBase::PrepareUndoForUpdatePinnedRow(CmsTransactionContext *,unsigned __int64,SmsTableSetLookupStack *)

- ea: `0x140092250`
- end: `0x14009264c`
- name: `?PrepareUndoForUpdatePinnedRow@CmsTableSetBase@@QEAAJPEAVCmsTransactionContext@@_KPEAUSmsTableSetLookupStack@@@Z`
- size: `1020`
- prototype: `int(CmsTableSetBase *__hidden this, struct CmsTransactionContext *, unsigned __int64, struct SmsTableSetLookupStack *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c62c0`
- `0x14014d054`
- `0x140150174`

## callees

- `0x14003f0f0`
- `0x140092250`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140092594`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400925bb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009260f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009260f`
- `ntoskrnl!ExAllocatePool2` at `0x14009233b`
- `ntoskrnl!ExAllocatePool2` at `0x14009233b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400922fe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400922fe`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14020199c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14020199c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009262c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009262c`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400924d9`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400924d9`

## string_xrefs

- `0x140092352`: `Lookaside list allocation must be double quad aligned.`

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
  __int64 v18; // r9
  unsigned int *v19; // r14
  unsigned __int64 v20; // rdx
  __int64 Pool2; // rax
  _DWORD *v22; // rbx
  int v23; // ecx
  _QWORD *v24; // r14
  unsigned int v25; // eax
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v29; // rsi
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // r9d
  __int64 v33; // r10
  int v34; // r11d
  __int64 v35; // rax
  char *v36; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v37; // rcx
  _DWORD *v38; // rax

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
    v36 = (char *)*((_QWORD *)v8 + 4);
    v8 = 0;
    if ( v36 != v4 )
      v8 = v36 - 32;
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
  v19 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v17 > *v19 )
  {
    v19 = 0;
    v20 = v17 + 16;
    goto LABEL_15;
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    v37 = (struct _NPAGED_LOOKASIDE_LIST *)(v19 + 16);
    if ( *((_BYTE *)v19 + 9) )
      v38 = ExAllocateFromNPagedLookasideList(v37);
    else
      v38 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v37);
LABEL_24:
    v22 = v38;
    if ( v38 )
    {
LABEL_25:
      *(_QWORD *)v22 = v19;
      v22 += 4;
      goto LABEL_26;
    }
    goto LABEL_22;
  }
  if ( (int)*((_QWORD *)v19 + 11) > (int)HIDWORD(*((_QWORD *)v19 + 11)) )
  {
    v23 = _InterlockedDecrement((volatile signed __int32 *)v19 + 22);
    if ( v23 >= (int)v19[23] && v23 >= 0 )
    {
      v38 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v19 + 4);
      goto LABEL_24;
    }
    _InterlockedIncrement((volatile signed __int32 *)v19 + 22);
  }
LABEL_22:
  v20 = v19[1];
LABEL_15:
  Pool2 = ExAllocatePool2(66, v20, 1766871885, v18);
  v22 = (_DWORD *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_25;
LABEL_26:
  if ( !v22 )
    return (unsigned int)-1073741670;
  v22[4] = 7;
  *((_QWORD *)v22 + 5) = v11;
  v22[3] = v16;
  v22[2] = v16;
  *((_WORD *)v22 + 10) = 0;
  *((_OWORD *)v22 + 3) = 0;
  *((_OWORD *)v22 + 4) = 0;
  *((_QWORD *)v22 + 10) = 0;
  v22[8] = 0;
  if ( v16 )
  {
    *((_QWORD *)v22 + 3) = v22 + 22;
    memset(v22 + 22, 0, v16);
    v24 = (_QWORD *)*((_QWORD *)v22 + 3);
  }
  else
  {
    *((_QWORD *)v22 + 3) = 0;
    v24 = 0;
  }
  *v24 = 0;
  v24[1] = 0;
  *((_BYTE *)v24 + 16) = 0;
  if ( (v14[2] & 0x40) != 0 )
    v25 = (*((unsigned __int16 *)v14 + 5) + 7) & 0xFFFFFFF8;
  else
    v25 = *v14;
  memmove((char *)v24 + 20, v14, v25);
  v22[2] = v16;
  v22[8] = 0;
  *((_QWORD *)v22 + 5) = v11;
  if ( v12 )
  {
    v29 = *(_QWORD *)v12;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v12 + 380LL));
    if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v29 + 560) )
      ++*(_DWORD *)(v29 + 384);
    else
      SmsPageLatch::AcquireShared((SmsPageLatch *)(v29 + 560), a2, 1);
    if ( *(char *)(*(_QWORD *)(v29 + 96) + 14LL) >= 0 )
      ++*((_DWORD *)a2 + 49);
    ++*(_DWORD *)(v29 + 388);
    v30 = *((_QWORD *)v12 + 1);
    v31 = *((_QWORD *)v12 + 2);
    v32 = *((_DWORD *)v12 + 6);
    v33 = *((_QWORD *)v12 + 4);
    v34 = *((_DWORD *)v12 + 7);
    if ( *((_QWORD *)v22 + 6) && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    *((_QWORD *)v22 + 6) = *(_QWORD *)v12;
    *((_QWORD *)v22 + 7) = v30;
    *((_QWORD *)v22 + 8) = v31;
    v22[18] = v32;
    *((_QWORD *)v22 + 10) = v33;
    v22[19] = v34;
    v35 = *(_QWORD *)v12;
    if ( *(_QWORD *)v12 && (!*(_BYTE *)(v35 + 392) && *(_QWORD *)(v35 + 96) == v11 || !*(_BYTE *)(v11 + 212)) )
      *((_BYTE *)v22 + 20) |= 1u;
  }
  else
  {
    *((_OWORD *)v22 + 3) = 0;
    *((_OWORD *)v22 + 4) = 0;
    *((_QWORD *)v22 + 10) = 0;
  }
  v26 = v22[2];
  if ( v26 )
  {
    v27 = (_QWORD *)*((_QWORD *)v22 + 3);
    if ( v24 )
    {
      if ( v24 != v27 )
        memmove(v27, v24, v26);
    }
    else
    {
      memset(v27, 0, (unsigned int)v22[2]);
    }
  }
  *(_QWORD *)v22 = *((_QWORD *)a2 + 18);
  *((_QWORD *)a2 + 18) = v22;
  return v9;
}

```

## disassembly

```asm
0x140092250  push    rbp
0x140092252  push    rsi
0x140092253  push    rdi
0x140092254  push    r13
0x140092256  push    r15
0x140092258  sub     rsp, 20h
0x14009225c  lea     r11, [rcx+10h]
0x140092260  mov     r10, r8
0x140092263  mov     r8, [r11]
0x140092266  mov     r15, rdx
0x140092269  cmp     r8, r11
0x14009226c  jz      loc_1400923B0
0x140092272  add     r8, 0FFFFFFFFFFFFFFE0h
0x140092276  xor     edi, edi
0x140092278  cmp     [r8+10h], r10
0x14009227c  jz      short loc_140092295
0x14009227e  mov     rcx, [r8+20h]
0x140092282  mov     r8, rdi
0x140092285  cmp     rcx, r11
0x140092288  lea     rax, [rcx-20h]
0x14009228c  cmovnz  r8, rax
0x140092290  test    r8, r8
0x140092293  jnz     short loc_140092278
0x140092295  test    byte ptr [r8+30h], 2
0x14009229a  jnz     loc_1400925CD
0x1400922a0  mov     r13, [r8]
0x1400922a3  lea     rbp, [r9+50h]
0x1400922a7  mov     [rsp+48h+arg_8], r12
0x1400922ac  mov     rax, [r13+18h]
0x1400922b0  mov     ecx, [rax+2Ch]
0x1400922b3  test    cl, 2
0x1400922b6  jnz     loc_1400925E4
0x1400922bc  mov     r12d, 1
0x1400922c2  mov     rsi, [rbp+10h]
0x1400922c6  test    byte ptr [rsi+8], 40h
0x1400922ca  jnz     loc_14009235F
0x1400922d0  mov     ecx, [rsi]
0x1400922d2  mov     eax, [rdx]
0x1400922d4  mov     [rsp+48h+arg_0], rbx
0x1400922d9  mov     [rsp+48h+arg_10], r14
0x1400922de  bt      rax, 0Ch
0x1400922e3  jb      loc_140092594
0x1400922e9  imul    r12d, ecx
0x1400922ed  xor     ecx, ecx; ProcNumber
0x1400922ef  add     r12d, 28h ; '('
0x1400922f3  lea     ebx, [r12+7]
0x1400922f8  and     ebx, 0FFFFFFF8h
0x1400922fb  add     ebx, 58h ; 'X'
0x1400922fe  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140092305  nop     dword ptr [rax+rax+00h]
0x14009230a  xor     edx, edx
0x14009230c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140092312  lea     r14, [rdx+rdx*2]
0x140092316  shl     r14, 6
0x14009231a  add     r14, cs:qword_140269410
0x140092321  mov     eax, [r14]
0x140092324  cmp     rbx, rax
0x140092327  jbe     short loc_14009236E
0x140092329  mov     r14, rdi
0x14009232c  lea     rdx, [rbx+10h]
0x140092330  mov     ecx, 42h ; 'B'
0x140092335  mov     r8d, 6950534Dh
0x14009233b  call    cs:__imp_ExAllocatePool2
0x140092342  nop     dword ptr [rax+rax+00h]
0x140092347  mov     rbx, rax
0x14009234a  test    al, 0Fh
0x14009234c  jz      loc_1402019AE
0x140092352  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140092359  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14009235f  movzx   ecx, word ptr [rsi+0Ah]
0x140092363  add     ecx, 7
0x140092366  and     ecx, 0FFFFFFF8h
0x140092369  jmp     loc_1400922D2
0x14009236e  cmp     byte ptr [r14+8], 0
0x140092373  jnz     loc_140092600
0x140092379  mov     rcx, [r14+58h]
0x14009237d  mov     rax, rcx
0x140092380  shr     rax, 20h
0x140092384  cmp     ecx, eax
0x140092386  jle     short loc_1400923AA
0x140092388  nop
0x140092389  mov     ecx, 0FFFFFFFFh
0x14009238e  lock xadd [r14+58h], ecx
0x140092394  nop
0x140092395  dec     ecx
0x140092397  mov     eax, [r14+5Ch]
0x14009239b  cmp     ecx, eax
0x14009239d  jge     loc_140092620
0x1400923a3  nop
0x1400923a4  lock inc dword ptr [r14+58h]
0x1400923a9  nop
0x1400923aa  mov     edx, [r14+4]
0x1400923ae  jmp     short loc_140092330
0x1400923b0  xor     edi, edi
0x1400923b2  mov     r8d, edi
0x1400923b5  jmp     loc_140092295
0x1400923ba  mov     rbx, rax
0x1400923bd  test    rax, rax
0x1400923c0  jz      short loc_1400923AA
0x1400923c2  mov     [rbx], r14
0x1400923c5  add     rbx, 10h
0x1400923c9  test    rbx, rbx
0x1400923cc  jz      loc_1400925B1
0x1400923d2  mov     dword ptr [rbx+10h], 7
0x1400923d9  xorps   xmm0, xmm0
0x1400923dc  mov     [rbx+28h], r13
0x1400923e0  xor     eax, eax
0x1400923e2  mov     [rbx+0Ch], r12d
0x1400923e6  mov     [rbx+8], r12d
0x1400923ea  mov     word ptr [rbx+14h], 0
0x1400923f0  movups  xmmword ptr [rbx+30h], xmm0
0x1400923f4  movups  xmmword ptr [rbx+40h], xmm0
0x1400923f8  mov     [rbx+50h], rax
0x1400923fc  mov     [rbx+20h], edi
0x1400923ff  test    r12d, r12d
0x140092402  jnz     loc_1400924AA
0x140092408  mov     [rbx+18h], rdi
0x14009240c  mov     r14, rdi
0x14009240f  mov     [r14], rdi
0x140092412  mov     [r14+8], rdi
0x140092416  mov     byte ptr [r14+10h], 0
0x14009241b  test    byte ptr [rsi+8], 40h
0x14009241f  jnz     loc_1400924FD
0x140092425  mov     eax, [rsi]
0x140092427  mov     r8d, eax; Size
0x14009242a  lea     rcx, [r14+14h]; void *
0x14009242e  mov     rdx, rsi; Src
0x140092431  call    memmove
0x140092436  mov     [rbx+8], r12d
0x14009243a  mov     [rbx+20h], edi
0x14009243d  mov     [rbx+28h], r13
0x140092441  test    rbp, rbp
0x140092444  jnz     short loc_1400924C5
0x140092446  xorps   xmm0, xmm0
0x140092449  xor     eax, eax
0x14009244b  movups  xmmword ptr [rbx+30h], xmm0
0x14009244f  movups  xmmword ptr [rbx+40h], xmm0
0x140092453  mov     [rbx+50h], rax
0x140092457  mov     eax, [rbx+8]
0x14009245a  test    eax, eax
0x14009245c  jz      short loc_14009247B
0x14009245e  mov     rcx, [rbx+18h]; void *
0x140092462  test    r14, r14
0x140092465  jz      loc_14009263D
0x14009246b  cmp     r14, rcx
0x14009246e  jz      short loc_14009247B
0x140092470  mov     r8d, eax; Size
0x140092473  mov     rdx, r14; Src
0x140092476  call    memmove
0x14009247b  mov     rcx, [r15+90h]
0x140092482  mov     [rbx], rcx
0x140092485  mov     [r15+90h], rbx
0x14009248c  mov     r14, [rsp+48h+arg_10]
0x140092491  mov     eax, edi
0x140092493  mov     r12, [rsp+48h+arg_8]
0x140092498  mov     rbx, [rsp+48h+arg_0]
0x14009249d  add     rsp, 20h
0x1400924a1  pop     r15
0x1400924a3  pop     r13
0x1400924a5  pop     rdi
0x1400924a6  pop     rsi
0x1400924a7  pop     rbp
0x1400924a8  retn
0x1400924aa  lea     rcx, [rbx+58h]; void *
0x1400924ae  mov     r8d, r12d; Size
0x1400924b1  xor     edx, edx; Val
0x1400924b3  mov     [rbx+18h], rcx
0x1400924b7  call    memset
0x1400924bc  mov     r14, [rbx+18h]
0x1400924c0  jmp     loc_14009240F
0x1400924c5  mov     rsi, [rbp+0]
0x1400924c9  nop
0x1400924ca  lock inc dword ptr [rsi+17Ch]
0x1400924d1  lea     rcx, [rsi+230h]
0x1400924d8  nop
0x1400924d9  call    cs:__imp_ExIsFastResourceHeldExclusive
0x1400924e0  nop     dword ptr [rax+rax+00h]
0x1400924e5  test    al, al
0x1400924e7  jnz     short loc_14009250C
0x1400924e9  mov     r8b, 1; bool
0x1400924ec  lea     rcx, [rsi+230h]; this
0x1400924f3  mov     rdx, r15; struct CmsTransactionContext *
0x1400924f6  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x1400924fb  jmp     short loc_140092512
0x1400924fd  movzx   eax, word ptr [rsi+0Ah]
0x140092501  add     eax, 7
0x140092504  and     eax, 0FFFFFFF8h
0x140092507  jmp     loc_140092427
0x14009250c  inc     dword ptr [rsi+180h]
0x140092512  mov     rax, [rsi+60h]
0x140092516  cmp     byte ptr [rax+0Eh], 0
0x14009251a  jl      short loc_140092523
0x14009251c  inc     dword ptr [r15+0C4h]
0x140092523  inc     dword ptr [rsi+184h]
0x140092529  cmp     qword ptr [rbx+30h], 0
0x14009252e  mov     rcx, [rbp+0]
0x140092532  mov     rdx, [rbp+8]
0x140092536  mov     r8, [rbp+10h]
0x14009253a  mov     r9d, [rbp+18h]
0x14009253e  mov     r10, [rbp+20h]
0x140092542  mov     r11d, [rbp+1Ch]
0x140092546  jnz     short loc_1400925BB
0x140092548  mov     [rbx+30h], rcx
0x14009254c  mov     [rbx+38h], rdx
0x140092550  mov     [rbx+40h], r8
0x140092554  mov     [rbx+48h], r9d
0x140092558  mov     [rbx+50h], r10
0x14009255c  mov     [rbx+4Ch], r11d
0x140092560  mov     rax, [rbp+0]
0x140092564  test    rax, rax
0x140092567  jz      loc_140092457
0x14009256d  cmp     byte ptr [rax+188h], 0
0x140092574  jnz     short loc_140092585
0x140092576  cmp     [rax+60h], r13
0x14009257a  jnz     short loc_140092585
0x14009257c  or      byte ptr [rbx+14h], 1
0x140092580  jmp     loc_140092457
0x140092585  cmp     byte ptr [r13+0D4h], 0
0x14009258d  jz      short loc_14009257C
0x14009258f  jmp     loc_140092457
0x140092594  mov     rax, cs:KdDebuggerEnabled
0x14009259b  cmp     byte ptr [rax], 0
0x14009259e  jnz     short loc_1400925FD
0x1400925a0  mov     rcx, [r15+8]
0x1400925a4  mov     r8b, 1
0x1400925a7  mov     edx, 20000000h
0x1400925ac  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x1400925b1  mov     edi, 0C000009Ah
0x1400925b6  jmp     loc_14009248C
0x1400925bb  mov     rax, cs:KdDebuggerEnabled
0x1400925c2  cmp     byte ptr [rax], 0
0x1400925c5  jz      short loc_140092548
0x1400925c7  int     3; Trap to Debugger
0x1400925c8  jmp     loc_140092548
0x1400925cd  mov     rcx, [r8+20h]
0x1400925d1  mov     r8, rdi
0x1400925d4  cmp     rcx, r11
0x1400925d7  lea     rax, [rcx-20h]
0x1400925db  cmovnz  r8, rax
0x1400925df  jmp     loc_1400922A0
0x1400925e4  mov     rax, [rbp+8]
0x1400925e8  mov     r12d, 2
0x1400925ee  cmp     byte ptr [rax+0Ch], 0
0x1400925f2  jz      loc_1400922C2
0x1400925f8  jmp     loc_1400922BC
0x1400925fd  int     3; Trap to Debugger
0x1400925fe  jmp     short loc_1400925A0
0x140092600  cmp     byte ptr [r14+9], 0
0x140092605  lea     rcx, [r14+40h]; Lookaside
0x140092609  jz      loc_14020199C
0x14009260f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140092616  nop     dword ptr [rax+rax+00h]
0x14009261b  jmp     loc_1400923BA
0x140092620  test    ecx, ecx
0x140092622  js      loc_1400923A3
0x140092628  lea     rcx, [r14+40h]; ListHead
0x14009262c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140092633  nop     dword ptr [rax+rax+00h]
0x140092638  jmp     loc_1400923BA
0x14009263d  mov     r8, rax; Size
0x140092640  xor     edx, edx; Val
0x140092642  call    memset
0x140092647  jmp     loc_14009247B
0x14020199c  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402019a3  nop     dword ptr [rax+rax+00h]
0x1402019a8  nop
0x1402019a9  jmp     loc_1400923BA
0x1402019ae  test    rax, rax
0x1402019b1  jz      loc_1400923C9
0x1402019b7  jmp     loc_1400923C2
```
