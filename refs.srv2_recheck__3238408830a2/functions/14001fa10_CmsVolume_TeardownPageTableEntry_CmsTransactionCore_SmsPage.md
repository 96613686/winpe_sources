# CmsVolume::TeardownPageTableEntry(CmsTransactionCore *,SmsPage *)

- ea: `0x14001fa10`
- end: `0x14001fe62`
- name: `?TeardownPageTableEntry@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@@Z`
- size: `1106`
- prototype: `void __fastcall(CmsVolume *__hidden this, struct CmsTransactionCore *, struct SmsPage *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14001e060`
- `0x1400568e0`

## callees

- `0x140016f60`
- `0x14001fa10`
- `0x140021720`
- `0x140021b70`
- `0x1400222e0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001fc5f`
- `ntoskrnl!KeSetEvent` at `0x14001fd3b`
- `ntoskrnl!KeSetEvent` at `0x14001fc5f`
- `ntoskrnl!KeSetEvent` at `0x14001fd3b`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001fa36`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fc1e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fc1e`
- `ntoskrnl!ExDeleteFastResource` at `0x14001fa94`
- `ntoskrnl!ExDeleteFastResource` at `0x14001fa94`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001fc98`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001fc98`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9fc7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9fc7`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001fd58`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001fd58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fe3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fe51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fe3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fe51`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001fcef`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001fcef`

## pseudocode

```c
void __fastcall CmsVolume::TeardownPageTableEntry(CmsVolume *this, struct CmsTransactionCore *a2, struct SmsPage *a3)
{
  __int64 v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  bool v11; // zf
  unsigned __int64 v12; // rdx
  struct SmsHashEntry *v13; // rax
  struct SmsHashEntry *v14; // rbx
  __int64 v15; // rdx
  __int16 v16; // cx
  __int16 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  __int64 v21; // rcx
  void *v22; // rsi
  __int64 v23; // r15
  struct SmsHashEntry *v24; // rdi
  __int64 v25; // rbx
  struct _SLIST_ENTRY *v26; // r15
  struct _NPAGED_LOOKASIDE_LIST *v27; // rcx
  _QWORD *v28; // rbx
  _QWORD *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 *v32; // rbx
  __int64 **v33; // rcx
  struct _KEVENT *v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  struct _SmsHashLocation *v37; // [rsp+38h] [rbp-51h]
  struct SmsHashEntry **v38; // [rsp+40h] [rbp-49h]
  __int128 v39; // [rsp+50h] [rbp-39h] BYREF
  __int64 v40; // [rsp+60h] [rbp-29h]
  __int128 v41; // [rsp+68h] [rbp-21h]
  __int128 v42; // [rsp+88h] [rbp-1h] BYREF
  int v43; // [rsp+98h] [rbp+Fh]
  int v44; // [rsp+9Ch] [rbp+13h]
  __int64 v45; // [rsp+A0h] [rbp+17h]
  struct SmsHashEntry *v46; // [rsp+F0h] [rbp+67h] BYREF
  _QWORD *v47; // [rsp+100h] [rbp+77h] BYREF

  v46 = this;
  v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a3 + 12) + 32LL) + 40LL);
  if ( (_BYTE)KdDebuggerEnabled && (*((_DWORD *)a3 + 138) & 0x3000) != 0 )
    __debugbreak();
  v6 = *((_QWORD *)a3 + 16);
  if ( v6 )
  {
    MsKmeUnpinData(v6, a2);
    *((_QWORD *)a3 + 16) = 0;
    *((_QWORD *)a3 + 15) = 0;
    *((_DWORD *)a3 + 34) = 0;
  }
  v7 = *((_QWORD *)a3 + 20);
  if ( v7 )
  {
    MsKmeUnpinData(v7, a2);
    *((_QWORD *)a3 + 20) = 0;
    *((_QWORD *)a3 + 19) = 0;
    *((_DWORD *)a3 + 42) = 0;
  }
  v8 = *((_QWORD *)a3 + 24);
  if ( v8 )
  {
    MsKmeUnpinData(v8, a2);
    *((_QWORD *)a3 + 24) = 0;
    *((_QWORD *)a3 + 23) = 0;
    *((_DWORD *)a3 + 50) = 0;
  }
  v9 = *((_QWORD *)a3 + 28);
  if ( v9 )
  {
    MsKmeUnpinData(v9, a2);
    *((_QWORD *)a3 + 28) = 0;
    *((_QWORD *)a3 + 27) = 0;
    *((_DWORD *)a3 + 58) = 0;
  }
  ExDeleteFastResource((char *)a3 + 560);
  v10 = (void *)*((_QWORD *)a3 + 35);
  if ( v10 != (void *)-1LL )
  {
    *((_QWORD *)a3 + 36) = v10;
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
  }
  v11 = (*((_DWORD *)a3 + 138) & 0x4000) == 0;
  v47 = 0;
  if ( !v11 )
  {
    v35 = (_QWORD *)*((_QWORD *)a3 + 8);
    *((_QWORD *)a3 + 8) = 0;
    v47 = v35;
    CmsHashTable::FreeIndexEntry((struct SmsPage *)((char *)a3 - 16));
    goto LABEL_29;
  }
  v12 = *(_QWORD *)a3;
  v11 = *(_QWORD *)(v5 + 32) == 0;
  v40 = 0;
  v46 = 0;
  v39 = 0;
  v13 = CmsHashTable::FindAndLockEntryInternal(
          (CmsHashTable *)(v5 + 16),
          v12,
          0,
          0,
          !v11,
          (struct _SmsHashLocation *)&v39,
          &v46,
          v37,
          v38);
  v14 = v13;
  if ( !v13 )
    goto LABEL_29;
  v15 = *((_QWORD *)v13 + 1);
  v42 = 0;
  v43 = 0;
  v45 = 0;
  v16 = *(_WORD *)(v15 + 8);
  v17 = v16 & 3;
  if ( (v16 & 0x40) != 0 )
  {
    WORD2(v41) = v16 & 3;
    v20 = *(unsigned __int16 *)(v15 + 10);
    WORD3(v41) = WORD3(v39);
    LODWORD(v41) = 12;
    *((_QWORD *)&v41 + 1) = v15 + 12;
  }
  else
  {
    v18 = *(unsigned __int16 *)(v15 + 10);
    LODWORD(v41) = *(unsigned __int16 *)(v15 + 6);
    WORD3(v41) = WORD3(v39);
    v19 = v15 + *(unsigned __int16 *)(v15 + 4);
    WORD2(v41) = v17 | 4;
    v20 = *(_DWORD *)(v15 + 12);
    v15 += v18;
    *((_QWORD *)&v41 + 1) = v19;
  }
  v43 = v20;
  v45 = v15;
  v42 = v41;
  v44 = DWORD1(v39);
  if ( (unsigned int)DequeueTeardownWaiters(a2, &v42, &v47) )
    goto LABEL_29;
  v21 = v39;
  v22 = 0;
  v23 = *((_QWORD *)v14 + 1);
  v24 = v46;
  *((_QWORD *)v14 + 1) = 0;
  if ( v21 == -1 )
  {
    *(_QWORD *)v14 = 0;
    v30 = *((_QWORD *)v24 + 1);
    v11 = (*(_DWORD *)(v30 + 4))-- == 1;
    if ( !v11 )
      goto LABEL_20;
    v22 = (void *)*((_QWORD *)v24 + 1);
    *((_QWORD *)v24 + 1) = 0;
  }
  v21 = 0;
LABEL_20:
  if ( _InterlockedExchange64((volatile __int64 *)v24, v21) == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
    v31 = qword_14026C3C8;
    if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
    {
      do
      {
        v32 = *(__int64 **)v31;
        if ( *(struct SmsHashEntry **)(v31 + 24) == v24 )
        {
          if ( v32[1] != v31 || (v33 = *(__int64 ***)(v31 + 8), *v33 != (__int64 *)v31) )
            __fastfail(3u);
          *v33 = v32;
          v32[1] = (__int64)v33;
          v34 = *(struct _KEVENT **)(v31 + 16);
          *(_QWORD *)v31 = 0;
          KeSetEvent(v34, 0, 0);
        }
        v31 = (__int64)v32;
      }
      while ( v32 != &qword_14026C3C8 );
    }
    ExReleasePushLockEx(&qword_14026C3C0, 0);
  }
  if ( !v23 )
    goto LABEL_26;
  v25 = *(_QWORD *)(v23 - 16);
  v26 = (struct _SLIST_ENTRY *)(v23 - 16);
  if ( !v25 )
    goto LABEL_49;
  if ( *(_BYTE *)(v25 + 8) )
  {
    v27 = (struct _NPAGED_LOOKASIDE_LIST *)(v25 + 64);
    if ( *(_BYTE *)(v25 + 9) )
      ExFreeToNPagedLookasideList(v27, v26);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v27, v26);
    goto LABEL_26;
  }
  v36 = *(_QWORD *)(v25 + 88);
  if ( (int)v36 < *(_DWORD *)(v25 + 80) || SHIDWORD(v36) >= (int)v36 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v25 + 64), v26);
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 88));
  }
  else
  {
LABEL_49:
    ExFreePoolWithTag(v26, 0);
  }
LABEL_26:
  if ( v22 )
    ExFreePoolWithTag(v22, 0);
  _InterlockedDecrement((volatile signed __int32 *)(16LL * DWORD2(v39) + v5 + 28));
LABEL_29:
  v28 = v47;
  while ( v28 )
  {
    v29 = v28;
    v28 = (_QWORD *)*v28;
    KeSetEvent((PRKEVENT)(v29 + 1), 0, 0);
  }
}

```

## disassembly

```asm
0x14001fa10  mov     [rsp-8+arg_0], rcx
0x14001fa15  push    rbp
0x14001fa16  push    rbx
0x14001fa17  push    rdi
0x14001fa18  push    r12
0x14001fa1a  push    r14
0x14001fa1c  lea     rbp, [rsp-37h]
0x14001fa21  sub     rsp, 0C0h
0x14001fa28  mov     rax, [r8+60h]
0x14001fa2c  mov     rbx, r8
0x14001fa2f  mov     rdi, rdx
0x14001fa32  mov     rcx, [rax+20h]
0x14001fa36  mov     rax, cs:KdDebuggerEnabled
0x14001fa3d  mov     r14, [rcx+28h]
0x14001fa41  cmp     byte ptr [rax], 0
0x14001fa44  jnz     loc_14001FD8A
0x14001fa4a  mov     rcx, [r8+80h]
0x14001fa51  xor     r12d, r12d
0x14001fa54  test    rcx, rcx
0x14001fa57  jnz     loc_14001FDA1
0x14001fa5d  mov     rcx, [rbx+0A0h]
0x14001fa64  test    rcx, rcx
0x14001fa67  jnz     loc_14001FDBD
0x14001fa6d  mov     rcx, [rbx+0C0h]
0x14001fa74  test    rcx, rcx
0x14001fa77  jnz     loc_14001FDDC
0x14001fa7d  mov     rcx, [rbx+0E0h]
0x14001fa84  test    rcx, rcx
0x14001fa87  jnz     loc_14001FDFB
0x14001fa8d  lea     rcx, [rbx+230h]
0x14001fa94  call    cs:__imp_ExDeleteFastResource
0x14001fa9b  nop     dword ptr [rax+rax+00h]
0x14001faa0  mov     rcx, [rbx+118h]; P
0x14001faa7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001faab  jz      short loc_14001FAC7
0x14001faad  mov     [rbx+120h], rcx
0x14001fab4  test    rcx, rcx
0x14001fab7  jz      short loc_14001FAC7
0x14001fab9  xor     edx, edx; Tag
0x14001fabb  call    cs:__imp_ExFreePoolWithTag
0x14001fac2  nop     dword ptr [rax+rax+00h]
0x14001fac7  test    dword ptr [rbx+228h], 4000h
0x14001fad1  mov     [rsp+0E0h+arg_8], rsi
0x14001fad9  mov     [rsp+0E0h+var_28], r13
0x14001fae1  mov     [rsp+0E0h+var_30], r15
0x14001fae9  mov     [rbp+57h+arg_10], r12
0x14001faed  jnz     loc_14001FD70
0x14001faf3  mov     rdx, [rbx]; unsigned __int64
0x14001faf6  lea     rcx, [rbp+57h+arg_0]
0x14001fafa  mov     [rsp+0E0h+var_B0], rcx; struct SmsHashEntry **
0x14001faff  xor     eax, eax
0x14001fb01  cmp     [r14+20h], rax
0x14001fb05  lea     rcx, [rbp+57h+var_90]
0x14001fb09  mov     [rsp+0E0h+var_B8], rcx; struct _SmsHashLocation *
0x14001fb0e  xorps   xmm0, xmm0
0x14001fb11  mov     [rbp+57h+var_80], rax
0x14001fb15  lea     rcx, [r14+10h]; this
0x14001fb19  setnz   al
0x14001fb1c  mov     [rbp+57h+arg_0], r12
0x14001fb20  xor     r9d, r9d; unsigned __int8
0x14001fb23  mov     [rsp+0E0h+var_C0], al; char
0x14001fb27  xor     r8d, r8d; unsigned __int8
0x14001fb2a  movups  [rbp+57h+var_90], xmm0
0x14001fb2e  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x14001fb33  mov     rbx, rax
0x14001fb36  test    rax, rax
0x14001fb39  jz      loc_14001FC42
0x14001fb3f  mov     rdx, [rax+8]
0x14001fb43  xorps   xmm0, xmm0
0x14001fb46  movups  [rbp+57h+var_58], xmm0
0x14001fb4a  mov     [rbp+57h+var_48], r12d
0x14001fb4e  mov     [rbp+57h+var_40], r12
0x14001fb52  movzx   ecx, word ptr [rdx+8]
0x14001fb56  lea     r9, [rdx+0Ch]
0x14001fb5a  movzx   r8d, cx
0x14001fb5e  and     r8w, 3
0x14001fb63  test    cl, 40h
0x14001fb66  jnz     loc_14001FCC4
0x14001fb6c  movzx   eax, word ptr [rdx+6]
0x14001fb70  or      r8w, 4
0x14001fb75  movzx   ecx, word ptr [rdx+0Ah]
0x14001fb79  mov     dword ptr [rbp+57h+var_78], eax
0x14001fb7c  movzx   eax, word ptr [rbp+57h+var_90+6]
0x14001fb80  mov     word ptr [rbp+57h+var_78+6], ax
0x14001fb84  movzx   eax, word ptr [rdx+4]
0x14001fb88  add     rax, rdx
0x14001fb8b  mov     word ptr [rbp+57h+var_78+4], r8w
0x14001fb90  mov     r8d, [r9]
0x14001fb93  add     rdx, rcx
0x14001fb96  mov     qword ptr [rbp+57h+var_78+8], rax
0x14001fb9a  movups  xmm0, [rbp+57h+var_78]
0x14001fb9e  mov     eax, dword ptr [rbp+57h+var_90+4]
0x14001fba1  mov     rcx, rdi
0x14001fba4  mov     [rbp+57h+var_48], r8d
0x14001fba8  lea     r8, [rbp+57h+arg_10]
0x14001fbac  mov     [rbp+57h+var_40], rdx
0x14001fbb0  lea     rdx, [rbp+57h+var_58]
0x14001fbb4  movups  [rbp+57h+var_58], xmm0
0x14001fbb8  mov     [rbp+57h+var_44], eax
0x14001fbbb  call    DequeueTeardownWaiters
0x14001fbc0  test    eax, eax
0x14001fbc2  jnz     short loc_14001FC42
0x14001fbc4  mov     rcx, qword ptr [rbp+57h+var_90]
0x14001fbc8  mov     rsi, r12
0x14001fbcb  mov     r15, [rbx+8]
0x14001fbcf  mov     rdi, [rbp+57h+arg_0]
0x14001fbd3  mov     [rbx+8], r12
0x14001fbd7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001fbdb  jz      loc_14001FCA6
0x14001fbe1  mov     rcx, r12
0x14001fbe4  xchg    rcx, [rdi]
0x14001fbe7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14001fbeb  jz      loc_14001FCE6
0x14001fbf1  test    r15, r15
0x14001fbf4  jz      short loc_14001FC2A
0x14001fbf6  mov     rbx, [r15-10h]
0x14001fbfa  add     r15, 0FFFFFFFFFFFFFFF0h
0x14001fbfe  test    rbx, rbx
0x14001fc01  jz      loc_14001FE36
0x14001fc07  cmp     [rbx+8], r12b
0x14001fc0b  jz      loc_14001FE1A
0x14001fc11  lea     rcx, [rbx+40h]; Lookaside
0x14001fc15  mov     rdx, r15; Entry
0x14001fc18  cmp     [rbx+9], r12b
0x14001fc1c  jz      short loc_14001FC98
0x14001fc1e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001fc25  nop     dword ptr [rax+rax+00h]
0x14001fc2a  test    rsi, rsi
0x14001fc2d  jnz     loc_14001FE4C
0x14001fc33  mov     eax, dword ptr [rbp+57h+var_90+8]
0x14001fc36  nop
0x14001fc37  shl     rax, 4
0x14001fc3b  lock dec dword ptr [rax+r14+1Ch]
0x14001fc41  nop
0x14001fc42  mov     rbx, [rbp+57h+arg_10]
0x14001fc46  test    rbx, rbx
0x14001fc49  jz      short loc_14001FC70
0x14001fc4b  nop     dword ptr [rax+rax+00h]
0x14001fc50  mov     rcx, rbx
0x14001fc53  xor     r8d, r8d; Wait
0x14001fc56  mov     rbx, [rbx]
0x14001fc59  add     rcx, 8; Event
0x14001fc5d  xor     edx, edx; Increment
0x14001fc5f  call    cs:__imp_KeSetEvent
0x14001fc66  nop     dword ptr [rax+rax+00h]
0x14001fc6b  test    rbx, rbx
0x14001fc6e  jnz     short loc_14001FC50
0x14001fc70  mov     r15, [rsp+0E0h+var_30]
0x14001fc78  mov     r13, [rsp+0E0h+var_28]
0x14001fc80  mov     rsi, [rsp+0E0h+arg_8]
0x14001fc88  add     rsp, 0C0h
0x14001fc8f  pop     r14
0x14001fc91  pop     r12
0x14001fc93  pop     rdi
0x14001fc94  pop     rbx
0x14001fc95  pop     rbp
0x14001fc96  retn
0x14001fc98  call    cs:__imp_ExFreeToPagedLookasideList
0x14001fc9f  nop     dword ptr [rax+rax+00h]
0x14001fca4  jmp     short loc_14001FC2A
0x14001fca6  mov     [rbx], r12
0x14001fca9  mov     rax, [rdi+8]
0x14001fcad  add     dword ptr [rax+4], 0FFFFFFFFh
0x14001fcb1  jnz     loc_14001FBE4
0x14001fcb7  mov     rsi, [rdi+8]
0x14001fcbb  mov     [rdi+8], r12
0x14001fcbf  jmp     loc_14001FBE1
0x14001fcc4  movzx   eax, word ptr [rbp+57h+var_90+6]
0x14001fcc8  mov     word ptr [rbp+57h+var_78+4], r8w
0x14001fccd  movzx   r8d, word ptr [rdx+0Ah]
0x14001fcd2  mov     word ptr [rbp+57h+var_78+6], ax
0x14001fcd6  mov     dword ptr [rbp+57h+var_78], 0Ch
0x14001fcdd  mov     qword ptr [rbp+57h+var_78+8], r9
0x14001fce1  jmp     loc_14001FB9A
0x14001fce6  xor     edx, edx
0x14001fce8  lea     rcx, qword_14026C3C0
0x14001fcef  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001fcf6  nop     dword ptr [rax+rax+00h]
0x14001fcfb  mov     rax, cs:qword_14026C3C8
0x14001fd02  lea     r13, qword_14026C3C8
0x14001fd09  cmp     rax, r13
0x14001fd0c  jz      short loc_14001FD4F
0x14001fd0e  xchg    ax, ax
0x14001fd10  mov     rbx, [rax]
0x14001fd13  cmp     [rax+18h], rdi
0x14001fd17  jnz     short loc_14001FD47
0x14001fd19  cmp     [rbx+8], rax
0x14001fd1d  jnz     short loc_14001FD69
0x14001fd1f  mov     rcx, [rax+8]
0x14001fd23  cmp     [rcx], rax
0x14001fd26  jnz     short loc_14001FD69
0x14001fd28  mov     [rcx], rbx
0x14001fd2b  xor     r8d, r8d; Wait
0x14001fd2e  mov     [rbx+8], rcx
0x14001fd32  xor     edx, edx; Increment
0x14001fd34  mov     rcx, [rax+10h]; Event
0x14001fd38  mov     [rax], r12
0x14001fd3b  call    cs:__imp_KeSetEvent
0x14001fd42  nop     dword ptr [rax+rax+00h]
0x14001fd47  mov     rax, rbx
0x14001fd4a  cmp     rbx, r13
0x14001fd4d  jnz     short loc_14001FD10
0x14001fd4f  xor     edx, edx
0x14001fd51  lea     rcx, qword_14026C3C0
0x14001fd58  call    cs:__imp_ExReleasePushLockEx
0x14001fd5f  nop     dword ptr [rax+rax+00h]
0x14001fd64  jmp     loc_14001FBF1
0x14001fd69  mov     ecx, 3
0x14001fd6e  int     29h; Win8: RtlFailFast(ecx)
0x14001fd70  mov     rax, [rbx+40h]
0x14001fd74  lea     rcx, [rbx-10h]; struct _SmsIndexEntry *
0x14001fd78  mov     [rbx+40h], r12
0x14001fd7c  mov     [rbp+57h+arg_10], rax
0x14001fd80  call    ?FreeIndexEntry@CmsHashTable@@CAXPEAU_SmsIndexEntry@@@Z; CmsHashTable::FreeIndexEntry(_SmsIndexEntry *)
0x14001fd85  jmp     loc_14001FC42
0x14001fd8a  test    dword ptr [r8+228h], 3000h
0x14001fd95  jz      loc_14001FA4A
0x14001fd9b  int     3; Trap to Debugger
0x14001fd9c  jmp     loc_14001FA4A
0x14001fda1  call    MsKmeUnpinData
0x14001fda6  mov     [rbx+80h], r12
0x14001fdad  mov     [rbx+78h], r12
0x14001fdb1  mov     [rbx+88h], r12d
0x14001fdb8  jmp     loc_14001FA5D
0x14001fdbd  call    MsKmeUnpinData
0x14001fdc2  mov     [rbx+0A0h], r12
0x14001fdc9  mov     [rbx+98h], r12
0x14001fdd0  mov     [rbx+0A8h], r12d
0x14001fdd7  jmp     loc_14001FA6D
0x14001fddc  call    MsKmeUnpinData
0x14001fde1  mov     [rbx+0C0h], r12
0x14001fde8  mov     [rbx+0B8h], r12
0x14001fdef  mov     [rbx+0C8h], r12d
0x14001fdf6  jmp     loc_14001FA7D
0x14001fdfb  call    MsKmeUnpinData
0x14001fe00  mov     [rbx+0E0h], r12
0x14001fe07  mov     [rbx+0D8h], r12
0x14001fe0e  mov     [rbx+0E8h], r12d
0x14001fe15  jmp     loc_14001FA8D
0x14001fe1a  mov     rcx, [rbx+58h]
0x14001fe1e  cmp     ecx, [rbx+50h]
0x14001fe21  jl      loc_1401F9FC0
0x14001fe27  mov     rax, rcx
0x14001fe2a  shr     rax, 20h
0x14001fe2e  cmp     eax, ecx
0x14001fe30  jge     loc_1401F9FC0
0x14001fe36  xor     edx, edx; Tag
0x14001fe38  mov     rcx, r15; P
0x14001fe3b  call    cs:__imp_ExFreePoolWithTag
0x14001fe42  nop     dword ptr [rax+rax+00h]
0x14001fe47  jmp     loc_14001FC2A
0x14001fe4c  xor     edx, edx; Tag
0x14001fe4e  mov     rcx, rsi; P
0x14001fe51  call    cs:__imp_ExFreePoolWithTag
0x14001fe58  nop     dword ptr [rax+rax+00h]
0x14001fe5d  jmp     loc_14001FC33
0x1401f9fc0  lea     rcx, [rbx+40h]; ListHead
0x1401f9fc4  mov     rdx, r15; ListEntry
0x1401f9fc7  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f9fce  nop     dword ptr [rax+rax+00h]
0x1401f9fd3  nop
0x1401f9fd4  lock inc dword ptr [rbx+58h]
0x1401f9fd8  nop
0x1401f9fd9  jmp     loc_14001FC2A
```
