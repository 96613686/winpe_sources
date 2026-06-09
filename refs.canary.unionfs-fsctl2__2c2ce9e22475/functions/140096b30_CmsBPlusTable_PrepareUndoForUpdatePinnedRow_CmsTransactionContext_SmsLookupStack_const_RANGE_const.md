# CmsBPlusTable::PrepareUndoForUpdatePinnedRow(CmsTransactionContext *,SmsLookupStack const &,_RANGE const *)

- ea: `0x140096b30`
- end: `0x140096fc3`
- name: `?PrepareUndoForUpdatePinnedRow@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@AEBUSmsLookupStack@@PEBU_RANGE@@@Z`
- size: `1171`
- prototype: `int(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, const struct SmsLookupStack *, const struct _RANGE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14008eec0`

## callees

- `0x14001a0c0`
- `0x140096b30`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140096f23`
- `ntoskrnl!KdDebuggerEnabled` at `0x140096f47`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140096f86`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140096f86`
- `ntoskrnl!ExAllocatePool2` at `0x140096bff`
- `ntoskrnl!ExAllocatePool2` at `0x140096bff`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140096bc4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140096bc4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9c18`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9c18`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140096fa3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140096fa3`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140096d36`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140096d36`

## string_xrefs

- `0x140096c16`: `Lookaside list allocation must be double quad aligned.`

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
  unsigned __int64 v16; // rdx
  __int64 Pool2; // rax
  _DWORD *v18; // rbx
  unsigned int v19; // eax
  int v20; // ecx
  char *v21; // rsi
  _DWORD *v22; // rbp
  unsigned int v23; // eax
  size_t v24; // r8
  const void *v25; // rdx
  char *v26; // rcx
  __int64 v27; // rdi
  __int128 v28; // xmm0
  unsigned __int16 v29; // r8
  __int16 v30; // ax
  __int16 v31; // ax
  void *v32; // rcx
  const void *v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r9d
  __int64 v37; // r10
  int v38; // r11d
  __int64 v39; // rax
  unsigned int v40; // eax
  char *v41; // rcx
  __int64 result; // rax
  struct _NPAGED_LOOKASIDE_LIST *v43; // rcx
  _DWORD *v44; // rax

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
      v19 = (*(unsigned __int16 *)(v9 + 10) + 7) & 0xFFFFFFF8;
    else
      v19 = *(_DWORD *)v9;
    v13 = v19 * v8;
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
  v15 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v14 > *v15 )
  {
    v15 = 0;
    v16 = v14 + 16;
    goto LABEL_10;
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v43 = (struct _NPAGED_LOOKASIDE_LIST *)(v15 + 16);
    if ( *((_BYTE *)v15 + 9) )
      v44 = ExAllocateFromNPagedLookasideList(v43);
    else
      v44 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v43);
LABEL_21:
    v18 = v44;
    if ( v44 )
    {
LABEL_22:
      *(_QWORD *)v18 = v15;
      v18 += 4;
      goto LABEL_23;
    }
    goto LABEL_19;
  }
  if ( (int)*((_QWORD *)v15 + 11) > (int)HIDWORD(*((_QWORD *)v15 + 11)) )
  {
    v20 = _InterlockedDecrement((volatile signed __int32 *)v15 + 22);
    if ( v20 >= (int)v15[23] && v20 >= 0 )
    {
      v44 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v15 + 4);
      goto LABEL_21;
    }
    _InterlockedIncrement((volatile signed __int32 *)v15 + 22);
  }
LABEL_19:
  v16 = v15[1];
LABEL_10:
  Pool2 = ExAllocatePool2(66, v16, 1766871885);
  v18 = (_DWORD *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_22;
LABEL_23:
  if ( !v18 )
    return 3221225626LL;
  v18[4] = 7;
  v18[3] = v13 + 40;
  v18[2] = v13 + 40;
  *((_QWORD *)v18 + 5) = this;
  *((_WORD *)v18 + 10) = 0;
  *((_OWORD *)v18 + 3) = 0;
  *((_OWORD *)v18 + 4) = 0;
  *((_QWORD *)v18 + 10) = 0;
  v18[8] = 0;
  if ( v13 == -40 )
  {
    *((_QWORD *)v18 + 3) = 0;
    v21 = 0;
  }
  else
  {
    *((_QWORD *)v18 + 3) = v18 + 22;
    memset(v18 + 22, 0, v13 + 40);
    v21 = (char *)*((_QWORD *)v18 + 3);
  }
  v22 = v21 + 20;
  if ( a4 )
  {
    v28 = *(_OWORD *)a4;
    v21[16] = 1;
    v29 = 12;
    *(_OWORD *)v21 = v28;
    *((_WORD *)v21 + 14) = *(_WORD *)(v9 + 8);
    *v22 = v13 + 16;
    v30 = 12;
    *((_WORD *)v21 + 12) = 16;
    if ( (*(_BYTE *)(v9 + 8) & 0x40) == 0 )
      v30 = *(_WORD *)(v9 + 6);
    *((_WORD *)v21 + 13) = v30;
    v31 = 12;
    if ( (*(_BYTE *)(v9 + 8) & 0x40) == 0 )
      v31 = *(_WORD *)(v9 + 6);
    v32 = v21 + 32;
    *((_WORD *)v21 + 15) = (v31 + 23) & 0xFFF8;
    *((_DWORD *)v21 + 8) = *((_DWORD *)a4 + 2);
    if ( (*(_BYTE *)(v9 + 8) & 0x40) != 0 )
    {
      v33 = (const void *)(v9 + 12);
    }
    else
    {
      v29 = *(_WORD *)(v9 + 6);
      v33 = (const void *)(v9 + *(unsigned __int16 *)(v9 + 4));
    }
    if ( (v21[28] & 0x40) == 0 )
      v32 = v21 + 36;
    memmove(v32, v33, v29);
    if ( (*(_BYTE *)(v9 + 8) & 0x40) == 0 )
      v9 += *(unsigned __int16 *)(v9 + 10);
    if ( (v21[28] & 0x40) != 0 )
      v26 = v21 + 20;
    else
      v26 = (char *)v22 + *((unsigned __int16 *)v21 + 15);
    v24 = *((_QWORD *)a4 + 1);
    v25 = (const void *)(v9 + *(_QWORD *)a4);
  }
  else
  {
    *(_QWORD *)v21 = 0;
    *((_QWORD *)v21 + 1) = 0;
    v21[16] = 0;
    if ( (*(_BYTE *)(v9 + 8) & 0x40) != 0 )
      v23 = (*(unsigned __int16 *)(v9 + 10) + 7) & 0xFFFFFFF8;
    else
      v23 = *(_DWORD *)v9;
    v24 = v23;
    v25 = (const void *)v9;
    v26 = v21 + 20;
  }
  memmove(v26, v25, v24);
  v18[2] = v13 + 40;
  *((_QWORD *)v18 + 5) = this;
  v18[8] = 0;
  v27 = *(_QWORD *)v5;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v5 + 380LL));
  if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v27 + 560) )
    ++*(_DWORD *)(v27 + 384);
  else
    SmsPageLatch::AcquireShared((SmsPageLatch *)(v27 + 560), a2, 1);
  if ( *(char *)(*(_QWORD *)(v27 + 96) + 14LL) >= 0 )
    ++*((_DWORD *)a2 + 49);
  ++*(_DWORD *)(v27 + 388);
  v34 = *((_QWORD *)v5 + 1);
  v35 = *((_QWORD *)v5 + 2);
  v36 = *((_DWORD *)v5 + 6);
  v37 = *((_QWORD *)v5 + 4);
  v38 = *((_DWORD *)v5 + 7);
  if ( *((_QWORD *)v18 + 6) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *((_QWORD *)v18 + 6) = *(_QWORD *)v5;
  *((_QWORD *)v18 + 7) = v34;
  *((_QWORD *)v18 + 8) = v35;
  v18[18] = v36;
  *((_QWORD *)v18 + 10) = v37;
  v18[19] = v38;
  v39 = *(_QWORD *)v5;
  if ( *(_QWORD *)v5 && (!*(_BYTE *)(v39 + 392) && *(CmsBPlusTable **)(v39 + 96) == this || !*((_BYTE *)this + 212)) )
    *((_BYTE *)v18 + 20) |= 1u;
  v40 = v18[2];
  if ( v40 )
  {
    v41 = (char *)*((_QWORD *)v18 + 3);
    if ( v21 )
    {
      if ( v21 != v41 )
        memmove(v41, v21, v40);
    }
    else
    {
      memset(v41, 0, (unsigned int)v18[2]);
    }
  }
  *(_QWORD *)v18 = *((_QWORD *)a2 + 18);
  result = 0;
  *((_QWORD *)a2 + 18) = v18;
  return result;
}

```

## disassembly

```asm
0x140096b30  mov     [rsp+arg_0], rcx
0x140096b35  push    rbp
0x140096b36  push    rdi
0x140096b37  push    r12
0x140096b39  push    r13
0x140096b3b  push    r14
0x140096b3d  push    r15
0x140096b3f  sub     rsp, 28h
0x140096b43  mov     rax, [rcx+18h]
0x140096b47  mov     r12, r9
0x140096b4a  mov     r13, r8
0x140096b4d  mov     r15, rdx
0x140096b50  mov     rbp, rcx
0x140096b53  mov     r10d, [rax+2Ch]
0x140096b57  test    r10b, 2
0x140096b5b  jnz     loc_140096F5D
0x140096b61  mov     edi, 1
0x140096b66  mov     r14, [r8+10h]
0x140096b6a  mov     ecx, 0Ch
0x140096b6f  movzx   eax, word ptr [r14+8]
0x140096b74  and     ax, 40h
0x140096b78  test    r12, r12
0x140096b7b  jz      loc_140096C23
0x140096b81  test    ax, ax
0x140096b84  movzx   eax, cx
0x140096b87  jnz     short loc_140096B8E
0x140096b89  movzx   eax, word ptr [r14+6]
0x140096b8e  movzx   edi, ax
0x140096b91  add     edi, 7
0x140096b94  and     edi, 0FFFFFFF8h
0x140096b97  add     edi, [r9+8]
0x140096b9b  mov     eax, [rdx]
0x140096b9d  mov     [rsp+58h+arg_10], rbx
0x140096ba2  mov     [rsp+58h+var_38], rsi
0x140096ba7  bt      rax, 0Ch
0x140096bac  jb      loc_140096F23
0x140096bb2  lea     eax, [rdi+28h]
0x140096bb5  xor     ecx, ecx; ProcNumber
0x140096bb7  lea     ebx, [rax+7]
0x140096bba  mov     [rsp+58h+arg_8], eax
0x140096bbe  and     ebx, 0FFFFFFF8h
0x140096bc1  add     ebx, 58h ; 'X'
0x140096bc4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140096bcb  nop     dword ptr [rax+rax+00h]
0x140096bd0  xor     edx, edx
0x140096bd2  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140096bd8  lea     rsi, [rdx+rdx*2]
0x140096bdc  shl     rsi, 6
0x140096be0  add     rsi, cs:qword_140262410
0x140096be7  mov     eax, [rsi]
0x140096be9  cmp     rbx, rax
0x140096bec  jbe     short loc_140096C33
0x140096bee  xor     esi, esi
0x140096bf0  lea     rdx, [rbx+10h]
0x140096bf4  mov     ecx, 42h ; 'B'
0x140096bf9  mov     r8d, 6950534Dh
0x140096bff  call    cs:__imp_ExAllocatePool2
0x140096c06  nop     dword ptr [rax+rax+00h]
0x140096c0b  mov     rbx, rax
0x140096c0e  test    al, 0Fh
0x140096c10  jz      loc_1401F9C2A
0x140096c16  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140096c1d  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140096c23  test    ax, ax
0x140096c26  jnz     short loc_140096C70
0x140096c28  mov     eax, [r14]
0x140096c2b  imul    edi, eax
0x140096c2e  jmp     loc_140096B9B
0x140096c33  cmp     byte ptr [rsi+8], 0
0x140096c37  jnz     loc_140096F78
0x140096c3d  mov     rcx, [rsi+58h]
0x140096c41  mov     rax, rcx
0x140096c44  shr     rax, 20h
0x140096c48  cmp     ecx, eax
0x140096c4a  jle     short loc_140096C6B
0x140096c4c  nop
0x140096c4d  mov     ecx, 0FFFFFFFFh
0x140096c52  lock xadd [rsi+58h], ecx
0x140096c57  nop
0x140096c58  dec     ecx
0x140096c5a  mov     eax, [rsi+5Ch]
0x140096c5d  cmp     ecx, eax
0x140096c5f  jge     loc_140096F97
0x140096c65  nop
0x140096c66  lock inc dword ptr [rsi+58h]
0x140096c6a  nop
0x140096c6b  mov     edx, [rsi+4]
0x140096c6e  jmp     short loc_140096BF4
0x140096c70  movzx   eax, word ptr [r14+0Ah]
0x140096c75  add     eax, 7
0x140096c78  and     eax, 0FFFFFFF8h
0x140096c7b  imul    edi, eax
0x140096c7e  jmp     loc_140096B9B
0x140096c83  mov     rbx, rax
0x140096c86  test    rax, rax
0x140096c89  jz      short loc_140096C6B
0x140096c8b  mov     [rbx], rsi
0x140096c8e  add     rbx, 10h
0x140096c92  test    rbx, rbx
0x140096c95  jz      loc_140096F40
0x140096c9b  mov     dword ptr [rbx+10h], 7
0x140096ca2  lea     eax, [rdi+28h]
0x140096ca5  mov     [rbx+0Ch], eax
0x140096ca8  xor     ecx, ecx
0x140096caa  mov     [rbx+8], eax
0x140096cad  xorps   xmm0, xmm0
0x140096cb0  mov     [rbx+28h], rbp
0x140096cb4  mov     word ptr [rbx+14h], 0
0x140096cba  movups  xmmword ptr [rbx+30h], xmm0
0x140096cbe  movups  xmmword ptr [rbx+40h], xmm0
0x140096cc2  mov     [rbx+50h], rcx
0x140096cc6  mov     [rbx+20h], ecx
0x140096cc9  test    eax, eax
0x140096ccb  jnz     loc_140096D61
0x140096cd1  mov     [rbx+18h], rcx
0x140096cd5  mov     esi, ecx
0x140096cd7  lea     rbp, [rsi+14h]
0x140096cdb  test    r12, r12
0x140096cde  jnz     loc_140096D7E
0x140096ce4  mov     [rsi], rcx
0x140096ce7  mov     [rsi+8], rcx
0x140096ceb  mov     [rsi+10h], r12b
0x140096cef  test    byte ptr [r14+8], 40h
0x140096cf4  jnz     loc_140096E43
0x140096cfa  mov     eax, [r14]
0x140096cfd  mov     r8d, eax; Size
0x140096d00  mov     rdx, r14; Src
0x140096d03  mov     rcx, rbp; void *
0x140096d06  call    memmove
0x140096d0b  mov     rbp, [rsp+58h+arg_0]
0x140096d10  mov     eax, [rsp+58h+arg_8]
0x140096d14  mov     [rbx+8], eax
0x140096d17  mov     [rbx+28h], rbp
0x140096d1b  mov     dword ptr [rbx+20h], 0
0x140096d22  mov     rdi, [r13+0]
0x140096d26  nop
0x140096d27  lock inc dword ptr [rdi+17Ch]
0x140096d2e  lea     rcx, [rdi+230h]
0x140096d35  nop
0x140096d36  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140096d3d  nop     dword ptr [rax+rax+00h]
0x140096d42  test    al, al
0x140096d44  jnz     loc_140096E53
0x140096d4a  mov     r8b, 1; bool
0x140096d4d  lea     rcx, [rdi+230h]; this
0x140096d54  mov     rdx, r15; struct CmsTransactionContext *
0x140096d57  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x140096d5c  jmp     loc_140096E59
0x140096d61  lea     rcx, [rbx+58h]; void *
0x140096d65  mov     r8d, eax; Size
0x140096d68  xor     edx, edx; Val
0x140096d6a  mov     [rbx+18h], rcx
0x140096d6e  call    memset
0x140096d73  mov     rsi, [rbx+18h]
0x140096d77  xor     ecx, ecx
0x140096d79  jmp     loc_140096CD7
0x140096d7e  movups  xmm0, xmmword ptr [r12]
0x140096d83  mov     byte ptr [rsi+10h], 1
0x140096d87  mov     r8d, 0Ch
0x140096d8d  movups  xmmword ptr [rsi], xmm0
0x140096d90  movzx   eax, word ptr [r14+8]
0x140096d95  mov     [rbp+8], ax
0x140096d99  lea     eax, [rdi+10h]
0x140096d9c  mov     [rbp+0], eax
0x140096d9f  movzx   eax, r8w
0x140096da3  mov     word ptr [rbp+4], 10h
0x140096da9  test    byte ptr [r14+8], 40h
0x140096dae  jnz     short loc_140096DB5
0x140096db0  movzx   eax, word ptr [r14+6]
0x140096db5  mov     [rbp+6], ax
0x140096db9  movzx   eax, r8w
0x140096dbd  test    byte ptr [r14+8], 40h
0x140096dc2  jnz     short loc_140096DC9
0x140096dc4  movzx   eax, word ptr [r14+6]
0x140096dc9  add     ax, 17h
0x140096dcd  mov     ecx, 0FFF8h
0x140096dd2  and     ax, cx
0x140096dd5  lea     rcx, [rbp+0Ch]
0x140096dd9  mov     [rbp+0Ah], ax
0x140096ddd  mov     eax, [r12+8]
0x140096de2  mov     [rcx], eax
0x140096de4  test    byte ptr [r14+8], 40h
0x140096de9  jz      short loc_140096E2F
0x140096deb  lea     rdx, [r14+0Ch]; Src
0x140096def  test    byte ptr [rbp+8], 40h
0x140096df3  jnz     short loc_140096DF9
0x140096df5  lea     rcx, [rbp+10h]; void *
0x140096df9  movzx   r8d, r8w; Size
0x140096dfd  call    memmove
0x140096e02  test    byte ptr [r14+8], 40h
0x140096e07  jnz     short loc_140096E11
0x140096e09  movzx   eax, word ptr [r14+0Ah]
0x140096e0e  add     r14, rax
0x140096e11  test    byte ptr [rbp+8], 40h
0x140096e15  jnz     short loc_140096E3E
0x140096e17  movzx   ecx, word ptr [rbp+0Ah]
0x140096e1b  add     rcx, rbp
0x140096e1e  mov     rdx, [r12]
0x140096e22  mov     r8, [r12+8]
0x140096e27  add     rdx, r14
0x140096e2a  jmp     loc_140096D06
0x140096e2f  movzx   edx, word ptr [r14+4]
0x140096e34  movzx   r8d, word ptr [r14+6]
0x140096e39  add     rdx, r14
0x140096e3c  jmp     short loc_140096DEF
0x140096e3e  mov     rcx, rbp
0x140096e41  jmp     short loc_140096E1E
0x140096e43  movzx   eax, word ptr [r14+0Ah]
0x140096e48  add     eax, 7
0x140096e4b  and     eax, 0FFFFFFF8h
0x140096e4e  jmp     loc_140096CFD
0x140096e53  inc     dword ptr [rdi+180h]
0x140096e59  mov     rax, [rdi+60h]
0x140096e5d  cmp     byte ptr [rax+0Eh], 0
0x140096e61  jl      short loc_140096E6A
0x140096e63  inc     dword ptr [r15+0C4h]
0x140096e6a  inc     dword ptr [rdi+184h]
0x140096e70  cmp     qword ptr [rbx+30h], 0
0x140096e75  mov     rcx, [r13+0]
0x140096e79  mov     rdx, [r13+8]
0x140096e7d  mov     r8, [r13+10h]
0x140096e81  mov     r9d, [r13+18h]
0x140096e85  mov     r10, [r13+20h]
0x140096e89  mov     r11d, [r13+1Ch]
0x140096e8d  jnz     loc_140096F47
0x140096e93  mov     [rbx+30h], rcx
0x140096e97  mov     [rbx+38h], rdx
0x140096e9b  mov     [rbx+40h], r8
0x140096e9f  mov     [rbx+48h], r9d
0x140096ea3  mov     [rbx+50h], r10
0x140096ea7  mov     [rbx+4Ch], r11d
0x140096eab  mov     rax, [r13+0]
0x140096eaf  test    rax, rax
0x140096eb2  jz      short loc_140096EC7
0x140096eb4  cmp     byte ptr [rax+188h], 0
0x140096ebb  jnz     short loc_140096F18
0x140096ebd  cmp     [rax+60h], rbp
0x140096ec1  jnz     short loc_140096F18
0x140096ec3  or      byte ptr [rbx+14h], 1
0x140096ec7  mov     eax, [rbx+8]
0x140096eca  test    eax, eax
0x140096ecc  jz      short loc_140096EEB
0x140096ece  mov     rcx, [rbx+18h]; void *
0x140096ed2  test    rsi, rsi
0x140096ed5  jz      loc_140096FB4
0x140096edb  cmp     rsi, rcx
0x140096ede  jz      short loc_140096EEB
0x140096ee0  mov     r8d, eax; Size
0x140096ee3  mov     rdx, rsi; Src
0x140096ee6  call    memmove
0x140096eeb  mov     rax, [r15+90h]
0x140096ef2  mov     [rbx], rax
0x140096ef5  xor     eax, eax
0x140096ef7  mov     [r15+90h], rbx
0x140096efe  mov     rsi, [rsp+58h+var_38]
0x140096f03  mov     rbx, [rsp+58h+arg_10]
0x140096f08  add     rsp, 28h
0x140096f0c  pop     r15
0x140096f0e  pop     r14
0x140096f10  pop     r13
0x140096f12  pop     r12
0x140096f14  pop     rdi
0x140096f15  pop     rbp
0x140096f16  retn
0x140096f18  cmp     byte ptr [rbp+0D4h], 0
0x140096f1f  jz      short loc_140096EC3
0x140096f21  jmp     short loc_140096EC7
0x140096f23  mov     rax, cs:KdDebuggerEnabled
0x140096f2a  cmp     byte ptr [rax], 0
0x140096f2d  jnz     short loc_140096F75
0x140096f2f  mov     rcx, [r15+8]
0x140096f33  mov     r8b, 1
0x140096f36  mov     edx, 20000000h
0x140096f3b  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140096f40  mov     eax, 0C000009Ah
0x140096f45  jmp     short loc_140096EFE
0x140096f47  mov     rax, cs:KdDebuggerEnabled
0x140096f4e  cmp     byte ptr [rax], 0
0x140096f51  jz      loc_140096E93
0x140096f57  int     3; Trap to Debugger
0x140096f58  jmp     loc_140096E93
0x140096f5d  mov     rax, [r8+8]
0x140096f61  mov     edi, 2
0x140096f66  cmp     byte ptr [rax+0Ch], 0
0x140096f6a  jz      loc_140096B66
0x140096f70  jmp     loc_140096B61
0x140096f75  int     3; Trap to Debugger
0x140096f76  jmp     short loc_140096F2F
0x140096f78  cmp     byte ptr [rsi+9], 0
0x140096f7c  lea     rcx, [rsi+40h]; Lookaside
0x140096f80  jz      loc_1401F9C18
0x140096f86  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140096f8d  nop     dword ptr [rax+rax+00h]
0x140096f92  jmp     loc_140096C83
0x140096f97  test    ecx, ecx
0x140096f99  js      loc_140096C65
0x140096f9f  lea     rcx, [rsi+40h]; ListHead
0x140096fa3  call    cs:__imp_ExpInterlockedPopEntrySList
0x140096faa  nop     dword ptr [rax+rax+00h]
0x140096faf  jmp     loc_140096C83
  ... truncated ...
```
