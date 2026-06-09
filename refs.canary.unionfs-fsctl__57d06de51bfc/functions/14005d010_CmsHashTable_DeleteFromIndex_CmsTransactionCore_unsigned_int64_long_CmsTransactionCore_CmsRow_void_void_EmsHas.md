# CmsHashTable::DeleteFromIndex(CmsTransactionCore *,unsigned __int64,long (*)(CmsTransactionCore *,_CmsRow *,void *),void *,EmsHashTableFlags,_SmsQuickIndex *,_SmsHashOverflow * *)

- ea: `0x14005d010`
- end: `0x14005d448`
- name: `?DeleteFromIndex@CmsHashTable@@QEAAJPEAVCmsTransactionCore@@_KP6AJ0PEAU_CmsRow@@PEAX@Z3W4EmsHashTableFlags@@PEAU_SmsQuickIndex@@PEAPEAU_SmsHashOverflow@@@Z`
- size: `1080`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b4098`
- `0x14011aa4c`
- `0x14013e838`
- `0x140149b08`
- `0x14014be10`
- `0x14014bfb8`

## callees

- `0x14005c030`
- `0x14005d010`
- `0x14006db30`
- `0x140095290`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005d36f`
- `ntoskrnl!KeSetEvent` at `0x14005d36f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d1c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d1c5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14005d3cf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14005d3cf`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005d223`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005d223`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f5773`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f5773`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005d38c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005d437`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005d38c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005d437`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d405`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f578f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d405`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f578f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005d321`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005d321`

## pseudocode

```c
__int64 __fastcall CmsHashTable::DeleteFromIndex(
        CmsHashTable *a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 (__fastcall *a4)(__int64, struct SmsHashEntry **, __int64),
        __int64 a5,
        char a6,
        _DWORD *a7,
        _QWORD *a8)
{
  char v8; // r12
  unsigned __int64 v10; // r10
  CmsHashTable *v11; // r14
  struct SmsHashEntry *v12; // r13
  signed __int64 v13; // rbx
  struct SmsHashEntry *v14; // rdi
  __int64 v15; // rdx
  __int16 v16; // ax
  __int16 v17; // cx
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // esi
  struct SmsHashEntry *v22; // rcx
  _QWORD *v23; // rsi
  __int64 v24; // rbx
  struct _SLIST_ENTRY *v25; // r8
  struct _NPAGED_LOOKASIDE_LIST *v26; // rcx
  unsigned int v28; // edx
  __int64 v29; // r13
  __int64 v30; // rax
  __int64 v32; // rax
  __int64 *v33; // rbx
  __int64 **v34; // rcx
  struct _KEVENT *v35; // rcx
  __int64 v36; // rcx
  struct _SmsHashLocation *v37; // [rsp+38h] [rbp-71h]
  struct SmsHashEntry **v38; // [rsp+40h] [rbp-69h]
  struct SmsHashEntry *v39[2]; // [rsp+50h] [rbp-59h] BYREF
  int v40; // [rsp+60h] [rbp-49h]
  int v41; // [rsp+64h] [rbp-45h]
  __int64 v42; // [rsp+68h] [rbp-41h]
  __int128 v43; // [rsp+70h] [rbp-39h] BYREF
  __int64 v44; // [rsp+80h] [rbp-29h]
  int v45; // [rsp+90h] [rbp-19h] BYREF
  struct SmsHashEntry *v46; // [rsp+98h] [rbp-11h]
  __int64 v47; // [rsp+A0h] [rbp-9h]
  __int64 v48; // [rsp+A8h] [rbp-1h]
  unsigned int v52; // [rsp+120h] [rbp+77h]

  v8 = a6;
  v44 = 0;
  v39[0] = 0;
  v10 = a3;
  v11 = a1;
  v43 = 0;
  if ( (a6 & 8) != 0 )
  {
    ExAcquirePushLockSharedEx((char *)a1 + 40, 4);
    v10 = a3;
  }
  if ( a7 )
  {
    v28 = a7[2];
    v29 = (unsigned int)a7[4];
    HIDWORD(v43) = a7[3];
    v52 = v28;
    DWORD2(v43) = v28;
    v14 = (struct SmsHashEntry *)(16LL * HIDWORD(v43) + *((_QWORD *)v11 + 2 * v28));
    LODWORD(v44) = v29;
    v46 = v14;
    v45 = 0;
    v47 = -2;
    v48 = -3;
    do
    {
      while ( 1 )
      {
        v13 = *(_QWORD *)v14;
        if ( (unsigned __int64)(*(_QWORD *)v14 + 3LL) > 1 )
          break;
        if ( !MsBackoff((struct _SmsBackoff *)&v45, v28) )
          SmsHashEntry::WaitExtended(v14);
      }
    }
    while ( v13 != _InterlockedCompareExchange64((volatile signed __int64 *)v14, -2, v13) );
    *(_QWORD *)&v43 = v13;
    if ( v13 == -1 )
      v12 = (struct SmsHashEntry *)(*(_QWORD *)(*((_QWORD *)v14 + 1) + 8LL) + 16 * v29);
    else
      v12 = v14;
    v8 = a6;
    v39[0] = v14;
    if ( v12 )
      goto LABEL_6;
    v10 = a3;
  }
  v12 = CmsHashTable::FindAndLockEntryInternal(
          v11,
          v10,
          0,
          (v8 & 2) != 0,
          *((_QWORD *)v11 + 2) != 0,
          (struct _SmsHashLocation *)&v43,
          v39,
          v37,
          v38);
  if ( !v12 )
  {
    v21 = -1073741772;
    goto LABEL_21;
  }
  v13 = v43;
  v14 = v39[0];
  v52 = DWORD2(v43);
LABEL_6:
  if ( a4 )
  {
    v15 = *((_QWORD *)v12 + 1);
    v40 = 0;
    *(_OWORD *)v39 = 0;
    v42 = 0;
    v16 = *(_WORD *)(v15 + 8);
    v17 = v16 & 3;
    if ( (v16 & 0x40) != 0 )
    {
      *((_QWORD *)&v43 + 1) = v15 + 12;
      v18 = *(unsigned __int16 *)(v15 + 10);
      WORD3(v43) = HIWORD(v39[0]);
      LODWORD(v43) = 12;
      WORD2(v43) = v16 & 3;
    }
    else
    {
      v18 = *(_DWORD *)(v15 + 12);
      LODWORD(v43) = *(unsigned __int16 *)(v15 + 6);
      WORD3(v43) = HIWORD(v39[0]);
      v19 = v15 + *(unsigned __int16 *)(v15 + 4);
      WORD2(v43) = v17 | 4;
      v20 = *(unsigned __int16 *)(v15 + 10);
      *((_QWORD *)&v43 + 1) = v19;
      v15 += v20;
    }
    v40 = v18;
    v41 = HIDWORD(v39[0]);
    v42 = v15;
    *(_OWORD *)v39 = v43;
    v21 = a4(a2, v39, a5);
    if ( v21 )
    {
      v11 = a1;
      goto LABEL_21;
    }
  }
  v22 = (struct SmsHashEntry *)*((_QWORD *)v12 + 1);
  v39[0] = v22;
  v23 = 0;
  *((_QWORD *)v12 + 1) = 0;
  if ( v13 == -1 )
  {
    *(_QWORD *)v12 = 0;
    v30 = *((_QWORD *)v14 + 1);
    if ( (*(_DWORD *)(v30 + 4))-- != 1 )
      goto LABEL_12;
    v23 = (_QWORD *)*((_QWORD *)v14 + 1);
    *((_QWORD *)v14 + 1) = 0;
  }
  v13 = 0;
LABEL_12:
  if ( _InterlockedExchange64((volatile __int64 *)v14, v13) == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_1402653F0, 0);
    v32 = qword_1402653F8;
    if ( (__int64 *)qword_1402653F8 != &qword_1402653F8 )
    {
      do
      {
        v33 = *(__int64 **)v32;
        if ( *(struct SmsHashEntry **)(v32 + 24) == v14 )
        {
          if ( v33[1] != v32 || (v34 = *(__int64 ***)(v32 + 8), *v34 != (__int64 *)v32) )
            __fastfail(3u);
          *v34 = v33;
          v33[1] = (__int64)v34;
          v35 = *(struct _KEVENT **)(v32 + 16);
          *(_QWORD *)v32 = 0;
          KeSetEvent(v35, 0, 0);
        }
        v32 = (__int64)v33;
      }
      while ( v33 != &qword_1402653F8 );
    }
    ExReleasePushLockEx(&qword_1402653F0, 0);
    v22 = v39[0];
  }
  if ( (v8 & 1) != 0 || !v22 )
    goto LABEL_19;
  v24 = *((_QWORD *)v22 - 2);
  v25 = (struct _SLIST_ENTRY *)((char *)v22 - 16);
  if ( !v24 )
    goto LABEL_50;
  if ( *(_BYTE *)(v24 + 8) )
  {
    v26 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 64);
    if ( *(_BYTE *)(v24 + 9) )
      ExFreeToNPagedLookasideList(v26, v25);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v26, v25);
    goto LABEL_19;
  }
  v36 = *(_QWORD *)(v24 + 88);
  if ( (int)v36 < *(_DWORD *)(v24 + 80) || SHIDWORD(v36) >= (int)v36 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 64), v25);
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 88));
  }
  else
  {
LABEL_50:
    ExFreePoolWithTag(v25, 0);
  }
LABEL_19:
  if ( v23 )
  {
    if ( a8 )
    {
      *v23 = *a8;
      *a8 = v23;
    }
    else
    {
      ExFreePoolWithTag(v23, 0);
    }
  }
  v11 = a1;
  _InterlockedDecrement((volatile signed __int32 *)a1 + 4 * v52 + 3);
  v21 = 0;
LABEL_21:
  if ( (a6 & 8) != 0 )
    ExReleasePushLockEx((char *)v11 + 40, 0);
  return v21;
}

```

## disassembly

```asm
0x14005d010  mov     [rsp-8+arg_10], r8
0x14005d015  mov     [rsp-8+arg_8], rdx
0x14005d01a  mov     [rsp-8+arg_0], rcx
0x14005d01f  push    rbp
0x14005d020  push    rsi
0x14005d021  push    r12
0x14005d023  push    r14
0x14005d025  push    r15
0x14005d027  lea     rbp, [rsp-17h]
0x14005d02c  sub     rsp, 0C0h
0x14005d033  mov     r12d, dword ptr [rbp+37h+arg_28]
0x14005d037  xor     eax, eax
0x14005d039  mov     r15d, r12d
0x14005d03c  mov     [rbp+37h+var_60], rax
0x14005d040  mov     [rbp+37h+var_90], rax
0x14005d044  xorps   xmm0, xmm0
0x14005d047  mov     rsi, r9
0x14005d04a  mov     r10, r8
0x14005d04d  mov     r14, rcx
0x14005d050  movups  [rbp+37h+var_70], xmm0
0x14005d054  and     r15d, 8
0x14005d058  jnz     loc_14005D3C6
0x14005d05e  mov     rax, [rbp+37h+arg_30]
0x14005d062  mov     [rsp+0E0h+arg_18], rbx
0x14005d06a  mov     [rsp+0E0h+var_28], rdi
0x14005d072  mov     [rsp+0E0h+var_30], r13
0x14005d07a  test    rax, rax
0x14005d07d  jnz     loc_14005D231
0x14005d083  cmp     qword ptr [r14+10h], 0
0x14005d088  lea     rcx, [rbp+37h+var_90]
0x14005d08c  mov     [rsp+0E0h+var_B0], rcx; struct SmsHashEntry **
0x14005d091  mov     r9d, r12d
0x14005d094  setnz   al
0x14005d097  lea     rcx, [rbp+37h+var_70]
0x14005d09b  mov     [rsp+0E0h+var_B8], rcx; struct _SmsHashLocation *
0x14005d0a0  xor     r8d, r8d; unsigned __int8
0x14005d0a3  shr     r9d, 1
0x14005d0a6  mov     rcx, r14; this
0x14005d0a9  and     r9b, 1; unsigned __int8
0x14005d0ad  mov     [rsp+0E0h+var_C0], al; char
0x14005d0b1  mov     rdx, r10; unsigned __int64
0x14005d0b4  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x14005d0b9  mov     r13, rax
0x14005d0bc  test    rax, rax
0x14005d0bf  jz      loc_14005D310
0x14005d0c5  mov     eax, dword ptr [rbp+37h+var_70+8]
0x14005d0c8  mov     rbx, qword ptr [rbp+37h+var_70]
0x14005d0cc  mov     rdi, [rbp+37h+var_90]
0x14005d0d0  mov     [rbp+37h+arg_30], rax
0x14005d0d4  test    rsi, rsi
0x14005d0d7  jz      loc_14005D168
0x14005d0dd  mov     rdx, [r13+8]
0x14005d0e1  xor     eax, eax
0x14005d0e3  xorps   xmm0, xmm0
0x14005d0e6  mov     [rbp+37h+var_80], eax
0x14005d0e9  movups  xmmword ptr [rbp+37h+var_90], xmm0
0x14005d0ed  mov     [rbp+37h+var_78], rax
0x14005d0f1  movzx   eax, word ptr [rdx+8]
0x14005d0f5  lea     r8, [rdx+0Ch]
0x14005d0f9  movzx   ecx, ax
0x14005d0fc  and     cx, 3
0x14005d100  test    al, 40h
0x14005d102  jnz     loc_14005D2EF
0x14005d108  movzx   eax, word ptr [rdx+6]
0x14005d10c  or      cx, 4
0x14005d110  mov     r8d, [r8]
0x14005d113  mov     dword ptr [rbp+37h+var_70], eax
0x14005d116  movzx   eax, word ptr [rbp+37h+var_90+6]
0x14005d11a  mov     word ptr [rbp+37h+var_70+6], ax
0x14005d11e  movzx   eax, word ptr [rdx+4]
0x14005d122  add     rax, rdx
0x14005d125  mov     word ptr [rbp+37h+var_70+4], cx
0x14005d129  movzx   ecx, word ptr [rdx+0Ah]
0x14005d12d  mov     qword ptr [rbp+37h+var_70+8], rax
0x14005d131  add     rdx, rcx
0x14005d134  mov     eax, dword ptr [rbp+37h+var_90+4]
0x14005d137  movups  xmm0, [rbp+37h+var_70]
0x14005d13b  mov     rcx, [rbp+37h+arg_8]
0x14005d13f  mov     [rbp+37h+var_80], r8d
0x14005d143  mov     r8, [rbp+37h+arg_20]
0x14005d147  mov     [rbp+37h+var_7C], eax
0x14005d14a  mov     rax, rsi
0x14005d14d  mov     [rbp+37h+var_78], rdx
0x14005d151  lea     rdx, [rbp+37h+var_90]
0x14005d155  movups  xmmword ptr [rbp+37h+var_90], xmm0
0x14005d159  call    _guard_dispatch_icall
0x14005d15e  mov     esi, eax
0x14005d160  test    eax, eax
0x14005d162  jnz     loc_14005D2C7
0x14005d168  mov     rcx, [r13+8]
0x14005d16c  xor     edx, edx
0x14005d16e  mov     [rbp+37h+var_90], rcx
0x14005d172  mov     esi, edx
0x14005d174  mov     [r13+8], rdx
0x14005d178  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14005d17c  jz      loc_14005D2D0
0x14005d182  mov     rbx, rdx
0x14005d185  xchg    rbx, [rdi]
0x14005d188  cmp     rbx, 0FFFFFFFFFFFFFFFDh
0x14005d18c  jz      loc_14005D31A
0x14005d192  test    r12b, 1
0x14005d196  jnz     short loc_14005D1D1
0x14005d198  test    rcx, rcx
0x14005d19b  jz      short loc_14005D1D1
0x14005d19d  mov     rbx, [rcx-10h]
0x14005d1a1  lea     r8, [rcx-10h]
0x14005d1a5  test    rbx, rbx
0x14005d1a8  jz      loc_14005D400
0x14005d1ae  cmp     byte ptr [rbx+8], 0
0x14005d1b2  jz      loc_14005D3E4
0x14005d1b8  cmp     byte ptr [rbx+9], 0
0x14005d1bc  lea     rcx, [rbx+40h]; Lookaside
0x14005d1c0  mov     rdx, r8; Entry
0x14005d1c3  jz      short loc_14005D223
0x14005d1c5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005d1cc  nop     dword ptr [rax+rax+00h]
0x14005d1d1  test    rsi, rsi
0x14005d1d4  jnz     loc_14005D416
0x14005d1da  mov     eax, dword ptr [rbp+37h+arg_30]
0x14005d1dd  nop
0x14005d1de  mov     r14, [rbp+37h+arg_0]
0x14005d1e2  shl     rax, 4
0x14005d1e6  lock dec dword ptr [rax+r14+0Ch]
0x14005d1ec  nop
0x14005d1ed  xor     esi, esi
0x14005d1ef  test    r15d, r15d
0x14005d1f2  jnz     loc_14005D431
0x14005d1f8  mov     r13, [rsp+0E0h+var_30]
0x14005d200  mov     eax, esi
0x14005d202  mov     rdi, [rsp+0E0h+var_28]
0x14005d20a  mov     rbx, [rsp+0E0h+arg_18]
0x14005d212  add     rsp, 0C0h
0x14005d219  pop     r15
0x14005d21b  pop     r14
0x14005d21d  pop     r12
0x14005d21f  pop     rsi
0x14005d220  pop     rbp
0x14005d221  retn
0x14005d223  call    cs:__imp_ExFreeToPagedLookasideList
0x14005d22a  nop     dword ptr [rax+rax+00h]
0x14005d22f  jmp     short loc_14005D1D1
0x14005d231  mov     edx, [rax+8]; unsigned int
0x14005d234  mov     r12, 0FFFFFFFFFFFFFFFEh
0x14005d23b  mov     ecx, [rax+0Ch]
0x14005d23e  mov     r13d, [rax+10h]
0x14005d242  mov     eax, edx
0x14005d244  add     rax, rax
0x14005d247  mov     dword ptr [rbp+37h+var_70+0Ch], ecx
0x14005d24a  shl     rcx, 4
0x14005d24e  mov     [rbp+37h+arg_30], rdx
0x14005d252  mov     dword ptr [rbp+37h+var_70+8], edx
0x14005d255  mov     rdi, [r14+rax*8]
0x14005d259  add     rdi, rcx
0x14005d25c  mov     dword ptr [rbp+37h+var_60], r13d
0x14005d260  xor     eax, eax
0x14005d262  mov     [rbp+37h+var_48], rdi
0x14005d266  mov     [rbp+37h+var_50], eax
0x14005d269  mov     [rbp+37h+var_40], r12
0x14005d26d  mov     [rbp+37h+var_38], 0FFFFFFFFFFFFFFFDh
0x14005d275  mov     rbx, [rdi]
0x14005d278  lea     rax, [rbx+3]
0x14005d27c  cmp     rax, 1
0x14005d280  jbe     loc_14005D3A8
0x14005d286  nop
0x14005d287  mov     rax, rbx
0x14005d28a  lock cmpxchg [rdi], r12
0x14005d28f  nop
0x14005d290  jnz     short loc_14005D275
0x14005d292  mov     qword ptr [rbp+37h+var_70], rbx
0x14005d296  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14005d29a  jnz     short loc_14005D2C2
0x14005d29c  mov     rax, [rdi+8]
0x14005d2a0  shl     r13, 4
0x14005d2a4  add     r13, [rax+8]
0x14005d2a8  mov     r12d, dword ptr [rbp+37h+arg_28]
0x14005d2ac  mov     [rbp+37h+var_90], rdi
0x14005d2b0  test    r13, r13
0x14005d2b3  jnz     loc_14005D0D4
0x14005d2b9  mov     r10, [rbp+37h+arg_10]
0x14005d2bd  jmp     loc_14005D083
0x14005d2c2  mov     r13, rdi
0x14005d2c5  jmp     short loc_14005D2A8
0x14005d2c7  mov     r14, [rbp+37h+arg_0]
0x14005d2cb  jmp     loc_14005D1EF
0x14005d2d0  mov     [r13+0], rdx
0x14005d2d4  mov     rax, [rdi+8]
0x14005d2d8  add     dword ptr [rax+4], 0FFFFFFFFh
0x14005d2dc  jnz     loc_14005D185
0x14005d2e2  mov     rsi, [rdi+8]
0x14005d2e6  mov     [rdi+8], rdx
0x14005d2ea  jmp     loc_14005D182
0x14005d2ef  movzx   eax, word ptr [rbp+37h+var_90+6]
0x14005d2f3  mov     qword ptr [rbp+37h+var_70+8], r8
0x14005d2f7  movzx   r8d, word ptr [rdx+0Ah]
0x14005d2fc  mov     word ptr [rbp+37h+var_70+6], ax
0x14005d300  mov     dword ptr [rbp+37h+var_70], 0Ch
0x14005d307  mov     word ptr [rbp+37h+var_70+4], cx
0x14005d30b  jmp     loc_14005D134
0x14005d310  mov     esi, 0C0000034h
0x14005d315  jmp     loc_14005D1EF
0x14005d31a  lea     rcx, qword_1402653F0
0x14005d321  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005d328  nop     dword ptr [rax+rax+00h]
0x14005d32d  mov     rax, cs:qword_1402653F8
0x14005d334  lea     r14, qword_1402653F8
0x14005d33b  cmp     rax, r14
0x14005d33e  jz      short loc_14005D383
0x14005d340  mov     rbx, [rax]
0x14005d343  cmp     [rax+18h], rdi
0x14005d347  jnz     short loc_14005D37B
0x14005d349  cmp     [rbx+8], rax
0x14005d34d  jnz     short loc_14005D3A1
0x14005d34f  mov     rcx, [rax+8]
0x14005d353  cmp     [rcx], rax
0x14005d356  jnz     short loc_14005D3A1
0x14005d358  mov     [rcx], rbx
0x14005d35b  xor     r8d, r8d; Wait
0x14005d35e  mov     [rbx+8], rcx
0x14005d362  xor     edx, edx; Increment
0x14005d364  mov     rcx, [rax+10h]; Event
0x14005d368  mov     qword ptr [rax], 0
0x14005d36f  call    cs:__imp_KeSetEvent
0x14005d376  nop     dword ptr [rax+rax+00h]
0x14005d37b  mov     rax, rbx
0x14005d37e  cmp     rbx, r14
0x14005d381  jnz     short loc_14005D340
0x14005d383  xor     edx, edx
0x14005d385  lea     rcx, qword_1402653F0
0x14005d38c  call    cs:__imp_ExReleasePushLockEx
0x14005d393  nop     dword ptr [rax+rax+00h]
0x14005d398  mov     rcx, [rbp+37h+var_90]
0x14005d39c  jmp     loc_14005D192
0x14005d3a1  mov     ecx, 3
0x14005d3a6  int     29h; Win8: RtlFailFast(ecx)
0x14005d3a8  lea     rcx, [rbp+37h+var_50]; struct _SmsBackoff *
0x14005d3ac  call    ?MsBackoff@@YAEPEAU_SmsBackoff@@K@Z; MsBackoff(_SmsBackoff *,ulong)
0x14005d3b1  test    al, al
0x14005d3b3  jnz     loc_14005D275
0x14005d3b9  mov     rcx, rdi; this
0x14005d3bc  call    ?WaitExtended@SmsHashEntry@@AEAAXXZ; SmsHashEntry::WaitExtended(void)
0x14005d3c1  jmp     loc_14005D275
0x14005d3c6  add     rcx, 28h ; '('
0x14005d3ca  mov     edx, 4
0x14005d3cf  call    cs:__imp_ExAcquirePushLockSharedEx
0x14005d3d6  nop     dword ptr [rax+rax+00h]
0x14005d3db  mov     r10, [rbp+37h+arg_10]
0x14005d3df  jmp     loc_14005D05E
0x14005d3e4  mov     rcx, [rbx+58h]
0x14005d3e8  cmp     ecx, [rbx+50h]
0x14005d3eb  jl      loc_1401F576C
0x14005d3f1  mov     rax, rcx
0x14005d3f4  shr     rax, 20h
0x14005d3f8  cmp     eax, ecx
0x14005d3fa  jge     loc_1401F576C
0x14005d400  xor     edx, edx; Tag
0x14005d402  mov     rcx, r8; P
0x14005d405  call    cs:__imp_ExFreePoolWithTag
0x14005d40c  nop     dword ptr [rax+rax+00h]
0x14005d411  jmp     loc_14005D1D1
0x14005d416  mov     rcx, [rbp+37h+arg_38]
0x14005d41a  test    rcx, rcx
0x14005d41d  jz      loc_1401F578A
0x14005d423  mov     rax, [rcx]
0x14005d426  mov     [rsi], rax
0x14005d429  mov     [rcx], rsi
0x14005d42c  jmp     loc_14005D1DA
0x14005d431  lea     rcx, [r14+28h]
0x14005d435  xor     edx, edx
0x14005d437  call    cs:__imp_ExReleasePushLockEx
0x14005d43e  nop     dword ptr [rax+rax+00h]
0x14005d443  jmp     loc_14005D1F8
0x1401f576c  lea     rcx, [rbx+40h]; ListHead
0x1401f5770  mov     rdx, r8; ListEntry
0x1401f5773  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f577a  nop     dword ptr [rax+rax+00h]
0x1401f577f  nop
0x1401f5780  lock inc dword ptr [rbx+58h]
0x1401f5784  nop
0x1401f5785  jmp     loc_14005D1D1
0x1401f578a  xor     edx, edx; Tag
0x1401f578c  mov     rcx, rsi; P
0x1401f578f  call    cs:__imp_ExFreePoolWithTag
0x1401f5796  nop     dword ptr [rax+rax+00h]
0x1401f579b  nop
0x1401f579c  jmp     loc_14005D1DA
```
