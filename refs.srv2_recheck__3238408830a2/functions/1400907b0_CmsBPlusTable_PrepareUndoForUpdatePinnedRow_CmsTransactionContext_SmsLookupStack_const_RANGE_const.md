# CmsBPlusTable::PrepareUndoForUpdatePinnedRow(CmsTransactionContext *,SmsLookupStack const &,_RANGE const *)

- ea: `0x1400907b0`
- end: `0x140090c43`
- name: `?PrepareUndoForUpdatePinnedRow@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@AEBUSmsLookupStack@@PEBU_RANGE@@@Z`
- size: `1171`
- prototype: `int(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, const struct SmsLookupStack *, const struct _RANGE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140061220`

## callees

- `0x14003f0f0`
- `0x1400907b0`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140090ba3`
- `ntoskrnl!KdDebuggerEnabled` at `0x140090bc7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140090c06`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140090c06`
- `ntoskrnl!ExAllocatePool2` at `0x14009087f`
- `ntoskrnl!ExAllocatePool2` at `0x14009087f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140090844`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140090844`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140201842`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140201842`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140090c23`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140090c23`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400909b6`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400909b6`

## string_xrefs

- `0x140090896`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::PrepareUndoForUpdatePinnedRow(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        const struct SmsLookupStack *a3,
        const struct _RANGE *a4)
{
  const struct SmsLookupStack *v5; // r13
  int v8; // edi
  __int64 v9; // r14
  __int16 v10; // ax
  bool v11; // zf
  unsigned __int16 v12; // ax
  unsigned int v13; // edi
  unsigned __int64 v14; // rbx
  unsigned int *v15; // rsi
  __int64 v16; // r9
  unsigned __int64 v17; // rdx
  __int64 Pool2; // rax
  _DWORD *v19; // rbx
  unsigned int v20; // eax
  int v21; // ecx
  char *v22; // rsi
  _DWORD *v23; // rbp
  unsigned int v24; // eax
  size_t v25; // r8
  const void *v26; // rdx
  char *v27; // rcx
  __int64 v28; // rdi
  __int128 v29; // xmm0
  unsigned __int16 v30; // r8
  __int16 v31; // ax
  __int16 v32; // ax
  void *v33; // rcx
  const void *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // r8
  int v37; // r9d
  __int64 v38; // r10
  int v39; // r11d
  __int64 v40; // rax
  unsigned int v41; // eax
  char *v42; // rcx
  __int64 result; // rax
  struct _NPAGED_LOOKASIDE_LIST *v44; // rcx
  _DWORD *v45; // rax

  v5 = a3;
  if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) == 0 || (v8 = 2, *(_BYTE *)(*((_QWORD *)a3 + 1) + 12LL)) )
    v8 = 1;
  v9 = *((_QWORD *)a3 + 2);
  v10 = *(_WORD *)(v9 + 8) & 0x40;
  if ( a4 )
  {
    v11 = v10 == 0;
    v12 = 12;
    if ( v11 )
      v12 = *(_WORD *)(v9 + 6);
    v13 = *((_DWORD *)a4 + 2) + ((v12 + 7) & 0xFFFFFFF8);
  }
  else
  {
    if ( v10 )
      v20 = (*(unsigned __int16 *)(v9 + 10) + 7) & 0xFFFFFFF8;
    else
      v20 = *(_DWORD *)v9;
    v13 = v20 * v8;
  }
  if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(a3) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)a2 + 1), 0x20000000, a3);
    return 3221225626LL;
  }
  v14 = ((v13 + 47) & 0xFFFFFFF8) + 88;
  v15 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v14 > *v15 )
  {
    v15 = 0;
    v17 = v14 + 16;
    goto LABEL_10;
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v44 = (struct _NPAGED_LOOKASIDE_LIST *)(v15 + 16);
    if ( *((_BYTE *)v15 + 9) )
      v45 = ExAllocateFromNPagedLookasideList(v44);
    else
      v45 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v44);
LABEL_21:
    v19 = v45;
    if ( v45 )
    {
LABEL_22:
      *(_QWORD *)v19 = v15;
      v19 += 4;
      goto LABEL_23;
    }
    goto LABEL_19;
  }
  if ( (int)*((_QWORD *)v15 + 11) > (int)HIDWORD(*((_QWORD *)v15 + 11)) )
  {
    v21 = _InterlockedDecrement((volatile signed __int32 *)v15 + 22);
    if ( v21 >= (int)v15[23] && v21 >= 0 )
    {
      v45 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v15 + 4);
      goto LABEL_21;
    }
    _InterlockedIncrement((volatile signed __int32 *)v15 + 22);
  }
LABEL_19:
  v17 = v15[1];
LABEL_10:
  Pool2 = ExAllocatePool2(66, v17, 1766871885, v16);
  v19 = (_DWORD *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_22;
LABEL_23:
  if ( !v19 )
    return 3221225626LL;
  v19[4] = 7;
  v19[3] = v13 + 40;
  v19[2] = v13 + 40;
  *((_QWORD *)v19 + 5) = this;
  *((_WORD *)v19 + 10) = 0;
  *((_OWORD *)v19 + 3) = 0;
  *((_OWORD *)v19 + 4) = 0;
  *((_QWORD *)v19 + 10) = 0;
  v19[8] = 0;
  if ( v13 == -40 )
  {
    *((_QWORD *)v19 + 3) = 0;
    v22 = 0;
  }
  else
  {
    *((_QWORD *)v19 + 3) = v19 + 22;
    memset(v19 + 22, 0, v13 + 40);
    v22 = (char *)*((_QWORD *)v19 + 3);
  }
  v23 = v22 + 20;
  if ( a4 )
  {
    v29 = *(_OWORD *)a4;
    v22[16] = 1;
    v30 = 12;
    *(_OWORD *)v22 = v29;
    *((_WORD *)v22 + 14) = *(_WORD *)(v9 + 8);
    *v23 = v13 + 16;
    v31 = 12;
    *((_WORD *)v22 + 12) = 16;
    if ( (*(_BYTE *)(v9 + 8) & 0x40) == 0 )
      v31 = *(_WORD *)(v9 + 6);
    *((_WORD *)v22 + 13) = v31;
    v32 = 12;
    if ( (*(_BYTE *)(v9 + 8) & 0x40) == 0 )
      v32 = *(_WORD *)(v9 + 6);
    v33 = v22 + 32;
    *((_WORD *)v22 + 15) = (v32 + 23) & 0xFFF8;
    *((_DWORD *)v22 + 8) = *((_DWORD *)a4 + 2);
    if ( (*(_BYTE *)(v9 + 8) & 0x40) != 0 )
    {
      v34 = (const void *)(v9 + 12);
    }
    else
    {
      v30 = *(_WORD *)(v9 + 6);
      v34 = (const void *)(v9 + *(unsigned __int16 *)(v9 + 4));
    }
    if ( (v22[28] & 0x40) == 0 )
      v33 = v22 + 36;
    memmove(v33, v34, v30);
    if ( (*(_BYTE *)(v9 + 8) & 0x40) == 0 )
      v9 += *(unsigned __int16 *)(v9 + 10);
    if ( (v22[28] & 0x40) != 0 )
      v27 = v22 + 20;
    else
      v27 = (char *)v23 + *((unsigned __int16 *)v22 + 15);
    v25 = *((_QWORD *)a4 + 1);
    v26 = (const void *)(v9 + *(_QWORD *)a4);
  }
  else
  {
    *(_QWORD *)v22 = 0;
    *((_QWORD *)v22 + 1) = 0;
    v22[16] = 0;
    if ( (*(_BYTE *)(v9 + 8) & 0x40) != 0 )
      v24 = (*(unsigned __int16 *)(v9 + 10) + 7) & 0xFFFFFFF8;
    else
      v24 = *(_DWORD *)v9;
    v25 = v24;
    v26 = (const void *)v9;
    v27 = v22 + 20;
  }
  memmove(v27, v26, v25);
  v19[2] = v13 + 40;
  *((_QWORD *)v19 + 5) = this;
  v19[8] = 0;
  v28 = *(_QWORD *)v5;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v5 + 380LL));
  if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v28 + 560) )
    ++*(_DWORD *)(v28 + 384);
  else
    SmsPageLatch::AcquireShared((SmsPageLatch *)(v28 + 560), a2, 1);
  if ( *(char *)(*(_QWORD *)(v28 + 96) + 14LL) >= 0 )
    ++*((_DWORD *)a2 + 49);
  ++*(_DWORD *)(v28 + 388);
  v35 = *((_QWORD *)v5 + 1);
  v36 = *((_QWORD *)v5 + 2);
  v37 = *((_DWORD *)v5 + 6);
  v38 = *((_QWORD *)v5 + 4);
  v39 = *((_DWORD *)v5 + 7);
  if ( *((_QWORD *)v19 + 6) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *((_QWORD *)v19 + 6) = *(_QWORD *)v5;
  *((_QWORD *)v19 + 7) = v35;
  *((_QWORD *)v19 + 8) = v36;
  v19[18] = v37;
  *((_QWORD *)v19 + 10) = v38;
  v19[19] = v39;
  v40 = *(_QWORD *)v5;
  if ( *(_QWORD *)v5 && (!*(_BYTE *)(v40 + 392) && *(CmsBPlusTable **)(v40 + 96) == this || !*((_BYTE *)this + 212)) )
    *((_BYTE *)v19 + 20) |= 1u;
  v41 = v19[2];
  if ( v41 )
  {
    v42 = (char *)*((_QWORD *)v19 + 3);
    if ( v22 )
    {
      if ( v22 != v42 )
        memmove(v42, v22, v41);
    }
    else
    {
      memset(v42, 0, (unsigned int)v19[2]);
    }
  }
  *(_QWORD *)v19 = *((_QWORD *)a2 + 18);
  result = 0;
  *((_QWORD *)a2 + 18) = v19;
  return result;
}

```

## disassembly

```asm
0x1400907b0  mov     [rsp+arg_0], rcx
0x1400907b5  push    rbp
0x1400907b6  push    rdi
0x1400907b7  push    r12
0x1400907b9  push    r13
0x1400907bb  push    r14
0x1400907bd  push    r15
0x1400907bf  sub     rsp, 28h
0x1400907c3  mov     rax, [rcx+18h]
0x1400907c7  mov     r12, r9
0x1400907ca  mov     r13, r8
0x1400907cd  mov     r15, rdx
0x1400907d0  mov     rbp, rcx
0x1400907d3  mov     r10d, [rax+2Ch]
0x1400907d7  test    r10b, 2
0x1400907db  jnz     loc_140090BDD
0x1400907e1  mov     edi, 1
0x1400907e6  mov     r14, [r8+10h]
0x1400907ea  mov     ecx, 0Ch
0x1400907ef  movzx   eax, word ptr [r14+8]
0x1400907f4  and     ax, 40h
0x1400907f8  test    r12, r12
0x1400907fb  jz      loc_1400908A3
0x140090801  test    ax, ax
0x140090804  movzx   eax, cx
0x140090807  jnz     short loc_14009080E
0x140090809  movzx   eax, word ptr [r14+6]
0x14009080e  movzx   edi, ax
0x140090811  add     edi, 7
0x140090814  and     edi, 0FFFFFFF8h
0x140090817  add     edi, [r9+8]
0x14009081b  mov     eax, [rdx]
0x14009081d  mov     [rsp+58h+arg_10], rbx
0x140090822  mov     [rsp+58h+var_38], rsi
0x140090827  bt      rax, 0Ch
0x14009082c  jb      loc_140090BA3
0x140090832  lea     eax, [rdi+28h]
0x140090835  xor     ecx, ecx; ProcNumber
0x140090837  lea     ebx, [rax+7]
0x14009083a  mov     [rsp+58h+arg_8], eax
0x14009083e  and     ebx, 0FFFFFFF8h
0x140090841  add     ebx, 58h ; 'X'
0x140090844  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009084b  nop     dword ptr [rax+rax+00h]
0x140090850  xor     edx, edx
0x140090852  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140090858  lea     rsi, [rdx+rdx*2]
0x14009085c  shl     rsi, 6
0x140090860  add     rsi, cs:qword_140269410
0x140090867  mov     eax, [rsi]
0x140090869  cmp     rbx, rax
0x14009086c  jbe     short loc_1400908B3
0x14009086e  xor     esi, esi
0x140090870  lea     rdx, [rbx+10h]
0x140090874  mov     ecx, 42h ; 'B'
0x140090879  mov     r8d, 6950534Dh
0x14009087f  call    cs:__imp_ExAllocatePool2
0x140090886  nop     dword ptr [rax+rax+00h]
0x14009088b  mov     rbx, rax
0x14009088e  test    al, 0Fh
0x140090890  jz      loc_140201854
0x140090896  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14009089d  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400908a3  test    ax, ax
0x1400908a6  jnz     short loc_1400908F0
0x1400908a8  mov     eax, [r14]
0x1400908ab  imul    edi, eax
0x1400908ae  jmp     loc_14009081B
0x1400908b3  cmp     byte ptr [rsi+8], 0
0x1400908b7  jnz     loc_140090BF8
0x1400908bd  mov     rcx, [rsi+58h]
0x1400908c1  mov     rax, rcx
0x1400908c4  shr     rax, 20h
0x1400908c8  cmp     ecx, eax
0x1400908ca  jle     short loc_1400908EB
0x1400908cc  nop
0x1400908cd  mov     ecx, 0FFFFFFFFh
0x1400908d2  lock xadd [rsi+58h], ecx
0x1400908d7  nop
0x1400908d8  dec     ecx
0x1400908da  mov     eax, [rsi+5Ch]
0x1400908dd  cmp     ecx, eax
0x1400908df  jge     loc_140090C17
0x1400908e5  nop
0x1400908e6  lock inc dword ptr [rsi+58h]
0x1400908ea  nop
0x1400908eb  mov     edx, [rsi+4]
0x1400908ee  jmp     short loc_140090874
0x1400908f0  movzx   eax, word ptr [r14+0Ah]
0x1400908f5  add     eax, 7
0x1400908f8  and     eax, 0FFFFFFF8h
0x1400908fb  imul    edi, eax
0x1400908fe  jmp     loc_14009081B
0x140090903  mov     rbx, rax
0x140090906  test    rax, rax
0x140090909  jz      short loc_1400908EB
0x14009090b  mov     [rbx], rsi
0x14009090e  add     rbx, 10h
0x140090912  test    rbx, rbx
0x140090915  jz      loc_140090BC0
0x14009091b  mov     dword ptr [rbx+10h], 7
0x140090922  lea     eax, [rdi+28h]
0x140090925  mov     [rbx+0Ch], eax
0x140090928  xor     ecx, ecx
0x14009092a  mov     [rbx+8], eax
0x14009092d  xorps   xmm0, xmm0
0x140090930  mov     [rbx+28h], rbp
0x140090934  mov     word ptr [rbx+14h], 0
0x14009093a  movups  xmmword ptr [rbx+30h], xmm0
0x14009093e  movups  xmmword ptr [rbx+40h], xmm0
0x140090942  mov     [rbx+50h], rcx
0x140090946  mov     [rbx+20h], ecx
0x140090949  test    eax, eax
0x14009094b  jnz     loc_1400909E1
0x140090951  mov     [rbx+18h], rcx
0x140090955  mov     esi, ecx
0x140090957  lea     rbp, [rsi+14h]
0x14009095b  test    r12, r12
0x14009095e  jnz     loc_1400909FE
0x140090964  mov     [rsi], rcx
0x140090967  mov     [rsi+8], rcx
0x14009096b  mov     [rsi+10h], r12b
0x14009096f  test    byte ptr [r14+8], 40h
0x140090974  jnz     loc_140090AC3
0x14009097a  mov     eax, [r14]
0x14009097d  mov     r8d, eax; Size
0x140090980  mov     rdx, r14; Src
0x140090983  mov     rcx, rbp; void *
0x140090986  call    memmove
0x14009098b  mov     rbp, [rsp+58h+arg_0]
0x140090990  mov     eax, [rsp+58h+arg_8]
0x140090994  mov     [rbx+8], eax
0x140090997  mov     [rbx+28h], rbp
0x14009099b  mov     dword ptr [rbx+20h], 0
0x1400909a2  mov     rdi, [r13+0]
0x1400909a6  nop
0x1400909a7  lock inc dword ptr [rdi+17Ch]
0x1400909ae  lea     rcx, [rdi+230h]
0x1400909b5  nop
0x1400909b6  call    cs:__imp_ExIsFastResourceHeldExclusive
0x1400909bd  nop     dword ptr [rax+rax+00h]
0x1400909c2  test    al, al
0x1400909c4  jnz     loc_140090AD3
0x1400909ca  mov     r8b, 1; bool
0x1400909cd  lea     rcx, [rdi+230h]; this
0x1400909d4  mov     rdx, r15; struct CmsTransactionContext *
0x1400909d7  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x1400909dc  jmp     loc_140090AD9
0x1400909e1  lea     rcx, [rbx+58h]; void *
0x1400909e5  mov     r8d, eax; Size
0x1400909e8  xor     edx, edx; Val
0x1400909ea  mov     [rbx+18h], rcx
0x1400909ee  call    memset
0x1400909f3  mov     rsi, [rbx+18h]
0x1400909f7  xor     ecx, ecx
0x1400909f9  jmp     loc_140090957
0x1400909fe  movups  xmm0, xmmword ptr [r12]
0x140090a03  mov     byte ptr [rsi+10h], 1
0x140090a07  mov     r8d, 0Ch
0x140090a0d  movups  xmmword ptr [rsi], xmm0
0x140090a10  movzx   eax, word ptr [r14+8]
0x140090a15  mov     [rbp+8], ax
0x140090a19  lea     eax, [rdi+10h]
0x140090a1c  mov     [rbp+0], eax
0x140090a1f  movzx   eax, r8w
0x140090a23  mov     word ptr [rbp+4], 10h
0x140090a29  test    byte ptr [r14+8], 40h
0x140090a2e  jnz     short loc_140090A35
0x140090a30  movzx   eax, word ptr [r14+6]
0x140090a35  mov     [rbp+6], ax
0x140090a39  movzx   eax, r8w
0x140090a3d  test    byte ptr [r14+8], 40h
0x140090a42  jnz     short loc_140090A49
0x140090a44  movzx   eax, word ptr [r14+6]
0x140090a49  add     ax, 17h
0x140090a4d  mov     ecx, 0FFF8h
0x140090a52  and     ax, cx
0x140090a55  lea     rcx, [rbp+0Ch]
0x140090a59  mov     [rbp+0Ah], ax
0x140090a5d  mov     eax, [r12+8]
0x140090a62  mov     [rcx], eax
0x140090a64  test    byte ptr [r14+8], 40h
0x140090a69  jz      short loc_140090AAF
0x140090a6b  lea     rdx, [r14+0Ch]; Src
0x140090a6f  test    byte ptr [rbp+8], 40h
0x140090a73  jnz     short loc_140090A79
0x140090a75  lea     rcx, [rbp+10h]; void *
0x140090a79  movzx   r8d, r8w; Size
0x140090a7d  call    memmove
0x140090a82  test    byte ptr [r14+8], 40h
0x140090a87  jnz     short loc_140090A91
0x140090a89  movzx   eax, word ptr [r14+0Ah]
0x140090a8e  add     r14, rax
0x140090a91  test    byte ptr [rbp+8], 40h
0x140090a95  jnz     short loc_140090ABE
0x140090a97  movzx   ecx, word ptr [rbp+0Ah]
0x140090a9b  add     rcx, rbp
0x140090a9e  mov     rdx, [r12]
0x140090aa2  mov     r8, [r12+8]
0x140090aa7  add     rdx, r14
0x140090aaa  jmp     loc_140090986
0x140090aaf  movzx   edx, word ptr [r14+4]
0x140090ab4  movzx   r8d, word ptr [r14+6]
0x140090ab9  add     rdx, r14
0x140090abc  jmp     short loc_140090A6F
0x140090abe  mov     rcx, rbp
0x140090ac1  jmp     short loc_140090A9E
0x140090ac3  movzx   eax, word ptr [r14+0Ah]
0x140090ac8  add     eax, 7
0x140090acb  and     eax, 0FFFFFFF8h
0x140090ace  jmp     loc_14009097D
0x140090ad3  inc     dword ptr [rdi+180h]
0x140090ad9  mov     rax, [rdi+60h]
0x140090add  cmp     byte ptr [rax+0Eh], 0
0x140090ae1  jl      short loc_140090AEA
0x140090ae3  inc     dword ptr [r15+0C4h]
0x140090aea  inc     dword ptr [rdi+184h]
0x140090af0  cmp     qword ptr [rbx+30h], 0
0x140090af5  mov     rcx, [r13+0]
0x140090af9  mov     rdx, [r13+8]
0x140090afd  mov     r8, [r13+10h]
0x140090b01  mov     r9d, [r13+18h]
0x140090b05  mov     r10, [r13+20h]
0x140090b09  mov     r11d, [r13+1Ch]
0x140090b0d  jnz     loc_140090BC7
0x140090b13  mov     [rbx+30h], rcx
0x140090b17  mov     [rbx+38h], rdx
0x140090b1b  mov     [rbx+40h], r8
0x140090b1f  mov     [rbx+48h], r9d
0x140090b23  mov     [rbx+50h], r10
0x140090b27  mov     [rbx+4Ch], r11d
0x140090b2b  mov     rax, [r13+0]
0x140090b2f  test    rax, rax
0x140090b32  jz      short loc_140090B47
0x140090b34  cmp     byte ptr [rax+188h], 0
0x140090b3b  jnz     short loc_140090B98
0x140090b3d  cmp     [rax+60h], rbp
0x140090b41  jnz     short loc_140090B98
0x140090b43  or      byte ptr [rbx+14h], 1
0x140090b47  mov     eax, [rbx+8]
0x140090b4a  test    eax, eax
0x140090b4c  jz      short loc_140090B6B
0x140090b4e  mov     rcx, [rbx+18h]; void *
0x140090b52  test    rsi, rsi
0x140090b55  jz      loc_140090C34
0x140090b5b  cmp     rsi, rcx
0x140090b5e  jz      short loc_140090B6B
0x140090b60  mov     r8d, eax; Size
0x140090b63  mov     rdx, rsi; Src
0x140090b66  call    memmove
0x140090b6b  mov     rax, [r15+90h]
0x140090b72  mov     [rbx], rax
0x140090b75  xor     eax, eax
0x140090b77  mov     [r15+90h], rbx
0x140090b7e  mov     rsi, [rsp+58h+var_38]
0x140090b83  mov     rbx, [rsp+58h+arg_10]
0x140090b88  add     rsp, 28h
0x140090b8c  pop     r15
0x140090b8e  pop     r14
0x140090b90  pop     r13
0x140090b92  pop     r12
0x140090b94  pop     rdi
0x140090b95  pop     rbp
0x140090b96  retn
0x140090b98  cmp     byte ptr [rbp+0D4h], 0
0x140090b9f  jz      short loc_140090B43
0x140090ba1  jmp     short loc_140090B47
0x140090ba3  mov     rax, cs:KdDebuggerEnabled
0x140090baa  cmp     byte ptr [rax], 0
0x140090bad  jnz     short loc_140090BF5
0x140090baf  mov     rcx, [r15+8]
0x140090bb3  mov     r8b, 1
0x140090bb6  mov     edx, 20000000h
0x140090bbb  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140090bc0  mov     eax, 0C000009Ah
0x140090bc5  jmp     short loc_140090B7E
0x140090bc7  mov     rax, cs:KdDebuggerEnabled
0x140090bce  cmp     byte ptr [rax], 0
0x140090bd1  jz      loc_140090B13
0x140090bd7  int     3; Trap to Debugger
0x140090bd8  jmp     loc_140090B13
0x140090bdd  mov     rax, [r8+8]
0x140090be1  mov     edi, 2
0x140090be6  cmp     byte ptr [rax+0Ch], 0
0x140090bea  jz      loc_1400907E6
0x140090bf0  jmp     loc_1400907E1
0x140090bf5  int     3; Trap to Debugger
0x140090bf6  jmp     short loc_140090BAF
0x140090bf8  cmp     byte ptr [rsi+9], 0
0x140090bfc  lea     rcx, [rsi+40h]; Lookaside
0x140090c00  jz      loc_140201842
0x140090c06  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140090c0d  nop     dword ptr [rax+rax+00h]
0x140090c12  jmp     loc_140090903
0x140090c17  test    ecx, ecx
0x140090c19  js      loc_1400908E5
0x140090c1f  lea     rcx, [rsi+40h]; ListHead
0x140090c23  call    cs:__imp_ExpInterlockedPopEntrySList
0x140090c2a  nop     dword ptr [rax+rax+00h]
0x140090c2f  jmp     loc_140090903
  ... truncated ...
```
