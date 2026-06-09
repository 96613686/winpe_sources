# CmsAllocator::EndAllocationRequest(CmsTransactionContext *,SmsAllocationContext *,SmsUndoRecord * &,long *,_RANGE_TUPLE const *,CmsStream *)

- ea: `0x140022220`
- end: `0x1400228aa`
- name: `?EndAllocationRequest@CmsAllocator@@AEAAXPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@AEAPEAUSmsUndoRecord@@PEAJPEBU_RANGE_TUPLE@@PEAVCmsStream@@@Z`
- size: `1674`
- prototype: `void __usercall(CmsAllocator *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct SmsAllocationContext *@<r8>, struct SmsUndoRecord **@<r9>, int *, const struct _RANGE_TUPLE *, struct CmsStream *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020380`
- `0x14015b998`

## callees

- `0x140012660`
- `0x140022220`
- `0x140023ac0`
- `0x140029a90`
- `0x14003234c`
- `0x140072934`
- `0x1400ad490`
- `0x1400b499c`
- `0x1400c4acc`
- `0x1400cd944`
- `0x14011abfc`
- `0x1401e9ce0`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140022675`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002237e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002237e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140022644`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140022644`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400223e6`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14002250b`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400223e6`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14002250b`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14002247a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400225a4`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14002247a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400225a4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f068e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f068e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022887`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022887`

## pseudocode

```c
void __fastcall CmsAllocator::EndAllocationRequest(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        struct SmsAllocationContext *a3,
        struct SmsUndoRecord **a4,
        int *a5,
        const struct _RANGE_TUPLE *a6,
        struct CmsStream *a7)
{
  struct CmsTransactionContext *v7; // rsi
  __int64 v8; // r13
  __int64 v11; // r9
  struct CmsStream *v12; // r11
  const struct _RANGE_TUPLE *v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int64 v17; // rcx
  __int128 v18; // xmm0
  struct SmsUndoRecord *v19; // rcx
  __int64 v20; // rdi
  struct _SLIST_ENTRY *v21; // r8
  struct _NPAGED_LOOKASIDE_LIST *v22; // rcx
  SmsAllocationRegionEx *v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // r11
  int v27; // eax
  __int64 v28; // r12
  _QWORD *v29; // rdx
  _QWORD *v30; // r10
  __int64 v31; // rax
  unsigned __int64 v32; // rcx
  __int64 v33; // r11
  struct SmsUndoRecord *v34; // rdi
  unsigned int v35; // eax
  _OWORD *v36; // rcx
  _QWORD *v37; // rcx
  int v38; // eax
  __int64 v39; // rsi
  __int64 v40; // r8
  __int64 v41; // rcx
  struct CmsTransactionContext *v42; // rdx
  struct CmsTransactionContext *v43; // [rsp+58h] [rbp-B0h]
  _BYTE v44[16]; // [rsp+60h] [rbp-A8h] BYREF
  __int16 v45; // [rsp+78h] [rbp-90h]
  char v46; // [rsp+7Ah] [rbp-8Eh]
  int v47; // [rsp+88h] [rbp-80h]
  _OWORD Src[4]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v49; // [rsp+D8h] [rbp-30h]
  __int128 i; // [rsp+E8h] [rbp-20h]
  __int64 v51; // [rsp+F8h] [rbp-10h]

  v7 = a2;
  v8 = *((_QWORD *)this + 57);
  v11 = 0;
  v12 = a7;
  v43 = a2;
  LODWORD(a2) = (_DWORD)a6;
  v49 = 0;
  v51 = 0;
  v14 = a6;
  for ( i = 0; v14 < (const struct _RANGE_TUPLE *)((char *)a6 + 64); v14 = (const struct _RANGE_TUPLE *)((char *)v14 + 16) )
  {
    v15 = *((_QWORD *)v14 + 1);
    if ( !v15 )
      break;
    v11 += v15;
  }
  v16 = *(_OWORD *)a6;
  v17 = *((unsigned int *)a3 + 17);
  *(_QWORD *)&i = this;
  Src[0] = v16;
  v18 = *((_OWORD *)a6 + 2);
  Src[1] = *((_OWORD *)a6 + 1);
  Src[2] = v18;
  Src[3] = *((_OWORD *)a6 + 3);
  LOBYTE(v49) = (v17 & 0x10) != 0 || *((_BYTE *)this + 492) == 2;
  *((_QWORD *)&v49 + 1) = a7;
  LODWORD(v51) = 0;
  *((_QWORD *)&i + 1) = v11;
  BYTE3(v49) = v17 & 1;
  *(_WORD *)((char *)&v49 + 1) = (unsigned __int8)v17 >> 7;
  if ( *a5 >= 0 )
  {
    if ( *((_BYTE *)this + 492) == 3 )
    {
      if ( (v17 & 4) != 0 )
      {
        BYTE2(v49) = 1;
        CmsAllocator::AdjustAllocatorSummary(this, 0, 0, v11, 0);
      }
      v27 = *((_DWORD *)a3 + 17);
      if ( (v27 & 0x21) != 0 )
      {
        if ( (v27 & 1) != 0 )
        {
          *((_DWORD *)a3 + 14) |= 0x100u;
          LODWORD(v51) = 512;
          CmsStream::IncrementStreamReserveClusters(v12, v7, v11);
        }
        else
        {
          v28 = v11;
          if ( (v27 & 0x1000) == 0 )
          {
            v38 = *((_DWORD *)a3 + 14);
            if ( (v38 & 0x100) != 0 && *((_QWORD *)a3 + 6) == v11 )
            {
              v28 = 0;
              *((_DWORD *)a3 + 14) = v38 & 0xFFFFFEFF;
            }
          }
          v29 = 0;
          v30 = (_QWORD *)(*((_QWORD *)v12 + 2) + 16LL);
          if ( (_QWORD *)*v30 != v30 )
          {
            v29 = (_QWORD *)(*v30 - 32LL);
            do
            {
              if ( v29[2] == *((_QWORD *)v12 + 3) )
                break;
              v37 = (_QWORD *)v29[4];
              v29 = 0;
              if ( v37 != v30 )
                v29 = v37 - 4;
            }
            while ( v29 );
          }
          if ( (*(_BYTE *)(*(_QWORD *)(*v29 + 88LL) + 8LL) & 8) != 0 )
          {
            v39 = *((_QWORD *)v7 + 1);
            if ( (int)CmsStream::UpdateStreamSummary((__int64)v12, v43, 0, -v11, 0, 0, 0, 0, 0, 0) < 0 )
            {
              if ( (_BYTE)KdDebuggerEnabled )
                __debugbreak();
              LOBYTE(v40) = 1;
              CmsVolume::ChangeVolumeOptionDynamically(v39, 0x20000000, v40);
            }
            v7 = v43;
          }
          v31 = ExAcquireAutoExpandPushLockShared(v8 + 3960, 2);
          v32 = *((_QWORD *)a3 + 6);
          v33 = v31;
          if ( v32 )
          {
            if ( (*((_DWORD *)a3 + 14) & 0x10) != 0 )
              _InterlockedAdd64((volatile signed __int64 *)(v8 + 3904), v32);
            if ( (*((_DWORD *)a3 + 14) & 0x1000) != 0 )
              _InterlockedAdd64((volatile signed __int64 *)(v8 + 3952), *((_QWORD *)a3 + 6));
            if ( (*((_DWORD *)a3 + 14) & 0x2000) != 0 )
              _InterlockedAdd64((volatile signed __int64 *)(v8 + 3952), -*((_QWORD *)a3 + 6));
            if ( (*((_DWORD *)a3 + 14) & 0x20) != 0 )
              _InterlockedAdd64((volatile signed __int64 *)(v8 + 3904), -*((_QWORD *)a3 + 6));
            if ( (*((_DWORD *)a3 + 14) & 0x40) != 0 )
              _InterlockedAdd64((volatile signed __int64 *)(v8 + 3784), *((_QWORD *)a3 + 6));
            if ( (*((_DWORD *)a3 + 14) & 0x80u) != 0 )
              _InterlockedAdd64((volatile signed __int64 *)(v8 + 3784), -*((_QWORD *)a3 + 6));
            if ( (*((_DWORD *)a3 + 14) & 0x100) != 0 )
              CmsVolume::AddReservationForGlobalStreamReserve((CmsVolume *)v8, *((_QWORD *)a3 + 6));
            if ( (*((_DWORD *)a3 + 14) & 0x200) != 0 )
              CmsVolume::RemoveReservationForGlobalStreamReserve((CmsVolume *)v8, *((_QWORD *)a3 + 6));
          }
          *((_DWORD *)a3 + 14) = 0;
          if ( v28 )
            CmsVolume::RemoveReservationForGlobalStreamReserve((CmsVolume *)v8, v28);
          ExReleaseAutoExpandPushLockShared(v33, 2);
          LODWORD(v51) = 256;
        }
      }
      else if ( (v27 & 0x40) != 0 && (*(_DWORD *)(v8 + 3460) & 0x800000) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 3840));
      }
    }
    v34 = *a4;
    *((_QWORD *)v34 + 5) = *(_QWORD *)this;
    *((_DWORD *)v34 + 2) = 104;
    *((_DWORD *)v34 + 8) = 0;
    *((_OWORD *)v34 + 3) = 0;
    *((_OWORD *)v34 + 4) = 0;
    *((_QWORD *)v34 + 10) = 0;
    v35 = *((_DWORD *)v34 + 2);
    if ( v35 )
    {
      v36 = (_OWORD *)*((_QWORD *)v34 + 3);
      a2 = (struct CmsTransactionContext *)Src;
      if ( Src != v36 )
        memmove(v36, Src, v35);
    }
    *(_QWORD *)v34 = *((_QWORD *)v7 + 18);
    *((_QWORD *)v7 + 18) = v34;
    *a4 = 0;
  }
  else if ( v11 )
  {
    LOBYTE(v11) = 1;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    CmsVolume::BeginTopLevelActionInternal(v17, v7, v44, v11, 0, 0);
    CmsBPlusTable::FormatUndoRecord(*(CmsBPlusTable **)this, v42, *a4, 0, Src, 0x68u, 0);
    *a4 = 0;
    CmsVolume::AbortTopLevelAction((CmsVolume *)v8, v7, (struct _SmsTopLevelAction *)v44);
  }
  if ( *((_DWORD *)a3 + 14) && (*((_DWORD *)a3 + 17) & 0x1000) == 0 )
  {
    v24 = ExAcquireAutoExpandPushLockShared(v8 + 3960, 2);
    v25 = *((_QWORD *)a3 + 6);
    v26 = v24;
    if ( v25 )
    {
      if ( (*((_DWORD *)a3 + 14) & 0x10) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v8 + 3904), v25);
      if ( (*((_DWORD *)a3 + 14) & 0x1000) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v8 + 3952), *((_QWORD *)a3 + 6));
      if ( (*((_DWORD *)a3 + 14) & 0x2000) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v8 + 3952), -*((_QWORD *)a3 + 6));
      if ( (*((_DWORD *)a3 + 14) & 0x20) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v8 + 3904), -*((_QWORD *)a3 + 6));
      if ( (*((_DWORD *)a3 + 14) & 0x40) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v8 + 3784), *((_QWORD *)a3 + 6));
      if ( (*((_DWORD *)a3 + 14) & 0x80u) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v8 + 3784), -*((_QWORD *)a3 + 6));
      if ( (*((_DWORD *)a3 + 14) & 0x100) != 0 )
        CmsVolume::AddReservationForGlobalStreamReserve((CmsVolume *)v8, *((_QWORD *)a3 + 6));
      if ( (*((_DWORD *)a3 + 14) & 0x200) != 0 )
        CmsVolume::RemoveReservationForGlobalStreamReserve((CmsVolume *)v8, *((_QWORD *)a3 + 6));
    }
    *((_DWORD *)a3 + 14) = 0;
    ExReleaseAutoExpandPushLockShared(v26, 2);
  }
  v19 = *a4;
  if ( *a4 && (*((_BYTE *)v19 + 20) & 4) == 0 )
  {
    v20 = *((_QWORD *)v19 - 2);
    v21 = (struct _SLIST_ENTRY *)((char *)v19 - 16);
    if ( !v20 )
      goto LABEL_94;
    if ( *(_BYTE *)(v20 + 8) )
    {
      v22 = (struct _NPAGED_LOOKASIDE_LIST *)(v20 + 64);
      if ( *(_BYTE *)(v20 + 9) )
        ExFreeToNPagedLookasideList(v22, v21);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v22, v21);
      goto LABEL_16;
    }
    v41 = *(_QWORD *)(v20 + 88);
    if ( (int)v41 < *(_DWORD *)(v20 + 80) || SHIDWORD(v41) >= (int)v41 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v20 + 64), v21);
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 88));
    }
    else
    {
LABEL_94:
      ExFreePoolWithTag(v21, 0);
    }
  }
LABEL_16:
  v23 = (SmsAllocationRegionEx *)*((_QWORD *)a3 + 3);
  if ( v23 )
  {
    SmsAllocationRegionEx::`scalar deleting destructor'(v23, (unsigned int)a2);
    *((_QWORD *)a3 + 3) = 0;
  }
}

```

## disassembly

```asm
0x140022220  mov     r11, rsp
0x140022223  push    rbp
0x140022224  push    rbx
0x140022225  lea     rbp, [r11-58h]
0x140022229  sub     rsp, 148h
0x140022230  mov     rax, cs:__security_cookie
0x140022237  xor     rax, rsp
0x14002223a  mov     [rbp+50h+var_50], rax
0x14002223e  mov     [r11-18h], rsi
0x140022242  xor     eax, eax
0x140022244  mov     [r11-20h], rdi
0x140022248  xorps   xmm0, xmm0
0x14002224b  mov     [r11-30h], r13
0x14002224f  mov     rsi, rdx
0x140022252  mov     r13, [rcx+1C8h]
0x140022259  mov     rbx, r8
0x14002225c  mov     [r11-38h], r14
0x140022260  mov     r14, r9
0x140022263  mov     [r11-40h], r15
0x140022267  xor     r9d, r9d
0x14002226a  mov     r11, [rbp+50h+arg_30]
0x140022271  mov     r15, rcx
0x140022274  mov     [rsp+150h+var_100], rdx
0x140022279  mov     rdx, [rbp+50h+arg_28]
0x140022280  movups  [rbp+50h+var_80], xmm0
0x140022284  mov     [rbp+50h+var_60], rax
0x140022288  mov     rcx, rdx
0x14002228b  movups  [rbp+50h+var_70], xmm0
0x14002228f  lea     r8, [rdx+40h]
0x140022293  cmp     rdx, r8
0x140022296  jnb     short loc_1400222AD
0x140022298  mov     rax, [rcx+8]
0x14002229c  test    rax, rax
0x14002229f  jz      short loc_1400222AD
0x1400222a1  add     r9, rax; __int64
0x1400222a4  add     rcx, 10h
0x1400222a8  cmp     rcx, r8
0x1400222ab  jb      short loc_140022298
0x1400222ad  movups  xmm0, xmmword ptr [rdx]
0x1400222b0  mov     ecx, [rbx+44h]
0x1400222b3  mov     qword ptr [rbp+50h+var_70], r15
0x1400222b7  movaps  [rbp+50h+Src], xmm0
0x1400222bb  movups  xmm1, xmmword ptr [rdx+10h]
0x1400222bf  movups  xmm0, xmmword ptr [rdx+20h]
0x1400222c3  movaps  [rbp+50h+var_B0], xmm1
0x1400222c7  movaps  [rbp+50h+var_A0], xmm0
0x1400222cb  movups  xmm1, xmmword ptr [rdx+30h]
0x1400222cf  movaps  [rbp+50h+var_90], xmm1
0x1400222d3  test    cl, 10h
0x1400222d6  jz      loc_1400223B6
0x1400222dc  mov     byte ptr [rbp+50h+var_80], 1
0x1400222e0  xor     edi, edi
0x1400222e2  mov     qword ptr [rbp+50h+var_80+8], r11
0x1400222e6  movzx   eax, cl
0x1400222e9  mov     dword ptr [rbp+50h+var_60], edi
0x1400222ec  and     al, 1
0x1400222ee  mov     qword ptr [rbp+50h+var_70+8], r9
0x1400222f2  mov     byte ptr [rbp+50h+var_80+3], al
0x1400222f5  movzx   eax, cl
0x1400222f8  shr     al, 7
0x1400222fb  mov     byte ptr [rbp+50h+var_80+1], al
0x1400222fe  mov     rax, [rbp+50h+arg_20]
0x140022305  mov     byte ptr [rbp+50h+var_80+2], dil
0x140022309  cmp     [rax], edi
0x14002230b  jge     loc_14002248B
0x140022311  test    r9, r9
0x140022314  jnz     loc_1401F0624
0x14002231a  cmp     dword ptr [rbx+38h], 0
0x14002231e  mov     r15, [rsp+150h+var_38]
0x140022326  mov     rsi, [rsp+140h]
0x14002232e  jnz     loc_1400223CD
0x140022334  mov     rcx, [r14]
0x140022337  mov     r14, [rsp+150h+var_30]
0x14002233f  mov     r13, [rsp+150h+var_28]
0x140022347  test    rcx, rcx
0x14002234a  jz      short loc_14002238A
0x14002234c  test    byte ptr [rcx+14h], 4
0x140022350  jnz     short loc_14002238A
0x140022352  mov     rdi, [rcx-10h]
0x140022356  lea     r8, [rcx-10h]
0x14002235a  test    rdi, rdi
0x14002235d  jz      loc_140022882
0x140022363  cmp     byte ptr [rdi+8], 0
0x140022367  jz      loc_140022866
0x14002236d  cmp     byte ptr [rdi+9], 0
0x140022371  lea     rcx, [rdi+40h]; Lookaside
0x140022375  mov     rdx, r8; Entry
0x140022378  jz      loc_140022644
0x14002237e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140022385  nop     dword ptr [rax+rax+00h]
0x14002238a  mov     rcx, [rbx+18h]; this
0x14002238e  mov     rdi, [rsp+150h+var_18]
0x140022396  test    rcx, rcx
0x140022399  jnz     loc_140022898
0x14002239f  mov     rcx, [rbp+50h+var_50]
0x1400223a3  xor     rcx, rsp; StackCookie
0x1400223a6  call    __security_check_cookie
0x1400223ab  add     rsp, 148h
0x1400223b2  pop     rbx
0x1400223b3  pop     rbp
0x1400223b4  retn
0x1400223b6  cmp     byte ptr [r15+1ECh], 2
0x1400223be  jz      loc_1400222DC
0x1400223c4  mov     byte ptr [rbp+50h+var_80], 0
0x1400223c8  jmp     loc_1400222E0
0x1400223cd  test    dword ptr [rbx+44h], 1000h
0x1400223d4  jnz     loc_140022334
0x1400223da  lea     rcx, [r13+0F78h]
0x1400223e1  mov     edx, 2
0x1400223e6  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1400223ed  nop     dword ptr [rax+rax+00h]
0x1400223f2  mov     rcx, [rbx+30h]
0x1400223f6  mov     r11, rax
0x1400223f9  test    rcx, rcx
0x1400223fc  jz      short loc_14002246B
0x1400223fe  mov     eax, [rbx+38h]
0x140022401  test    al, 10h
0x140022403  jnz     loc_1400227E7
0x140022409  test    dword ptr [rbx+38h], 1000h
0x140022410  jnz     loc_1400227F6
0x140022416  test    dword ptr [rbx+38h], 2000h
0x14002241d  jnz     loc_140022807
0x140022423  mov     eax, [rbx+38h]
0x140022426  test    al, 20h
0x140022428  jnz     loc_14002281B
0x14002242e  mov     eax, [rbx+38h]
0x140022431  test    al, 40h
0x140022433  jnz     loc_140022831
0x140022439  mov     eax, [rbx+38h]
0x14002243c  test    al, al
0x14002243e  jns     short loc_140022451
0x140022440  mov     rax, [rbx+30h]
0x140022444  nop
0x140022445  neg     rax
0x140022448  lock add [r13+0EC8h], rax
0x140022450  nop
0x140022451  test    dword ptr [rbx+38h], 100h
0x140022458  jnz     loc_140022844
0x14002245e  test    dword ptr [rbx+38h], 200h
0x140022465  jnz     loc_140022855
0x14002246b  mov     edx, 2
0x140022470  mov     dword ptr [rbx+38h], 0
0x140022477  mov     rcx, r11
0x14002247a  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140022481  nop     dword ptr [rax+rax+00h]
0x140022486  jmp     loc_140022334
0x14002248b  cmp     byte ptr [r15+1ECh], 3
0x140022493  jnz     loc_1400225BF
0x140022499  test    cl, 4
0x14002249c  jnz     loc_14002269F
0x1400224a2  mov     eax, [rbx+44h]
0x1400224a5  test    al, 21h
0x1400224a7  jz      loc_1400227DA
0x1400224ad  test    al, 1
0x1400224af  jnz     loc_1400226BA
0x1400224b5  mov     [rsp+150h+var_20], r12
0x1400224bd  mov     r12, r9
0x1400224c0  bt      eax, 0Ch
0x1400224c4  jnb     loc_1400226DB
0x1400224ca  mov     r10, [r11+10h]
0x1400224ce  xor     edx, edx
0x1400224d0  add     r10, 10h
0x1400224d4  mov     rax, [r10]
0x1400224d7  cmp     rax, r10
0x1400224da  jz      short loc_1400224EE
0x1400224dc  mov     r8, [r11+18h]
0x1400224e0  lea     rdx, [rax-20h]
0x1400224e4  cmp     [rdx+10h], r8
0x1400224e8  jnz     loc_140022625
0x1400224ee  mov     rax, [rdx]
0x1400224f1  mov     rcx, [rax+58h]
0x1400224f5  test    byte ptr [rcx+8], 8
0x1400224f9  jnz     loc_140022701
0x1400224ff  lea     rcx, [r13+0F78h]
0x140022506  mov     edx, 2
0x14002250b  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x140022512  nop     dword ptr [rax+rax+00h]
0x140022517  mov     rcx, [rbx+30h]
0x14002251b  mov     r11, rax
0x14002251e  test    rcx, rcx
0x140022521  jz      short loc_140022590
0x140022523  mov     eax, [rbx+38h]
0x140022526  test    al, 10h
0x140022528  jnz     loc_14002274B
0x14002252e  test    dword ptr [rbx+38h], 1000h
0x140022535  jnz     loc_14002275A
0x14002253b  test    dword ptr [rbx+38h], 2000h
0x140022542  jnz     loc_14002276B
0x140022548  mov     eax, [rbx+38h]
0x14002254b  test    al, 20h
0x14002254d  jnz     loc_14002277F
0x140022553  mov     eax, [rbx+38h]
0x140022556  test    al, 40h
0x140022558  jnz     loc_140022795
0x14002255e  mov     eax, [rbx+38h]
0x140022561  test    al, al
0x140022563  jns     short loc_140022576
0x140022565  mov     rax, [rbx+30h]
0x140022569  nop
0x14002256a  neg     rax
0x14002256d  lock add [r13+0EC8h], rax
0x140022575  nop
0x140022576  test    dword ptr [rbx+38h], 100h
0x14002257d  jnz     loc_1400227A8
0x140022583  test    dword ptr [rbx+38h], 200h
0x14002258a  jnz     loc_1400227B9
0x140022590  mov     [rbx+38h], edi
0x140022593  test    r12, r12
0x140022596  jnz     loc_1400227CA
0x14002259c  mov     edx, 2
0x1400225a1  mov     rcx, r11
0x1400225a4  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1400225ab  nop     dword ptr [rax+rax+00h]
0x1400225b0  mov     r12, [rsp+150h+var_20]
0x1400225b8  bts     edi, 8
0x1400225bc  mov     dword ptr [rbp+50h+var_60], edi
0x1400225bf  mov     rdi, [r14]
0x1400225c2  xorps   xmm0, xmm0
0x1400225c5  mov     rax, [r15]
0x1400225c8  mov     [rdi+28h], rax
0x1400225cc  xor     eax, eax
0x1400225ce  mov     dword ptr [rdi+8], 68h ; 'h'
0x1400225d5  mov     dword ptr [rdi+20h], 0
0x1400225dc  movups  xmmword ptr [rdi+30h], xmm0
0x1400225e0  movups  xmmword ptr [rdi+40h], xmm0
0x1400225e4  mov     [rdi+50h], rax
0x1400225e8  mov     eax, [rdi+8]
0x1400225eb  test    eax, eax
0x1400225ed  jz      short loc_140022608
0x1400225ef  mov     rcx, [rdi+18h]; void *
0x1400225f3  lea     rdx, [rbp+50h+Src]
0x1400225f7  cmp     rdx, rcx
0x1400225fa  jz      short loc_140022608
0x1400225fc  mov     r8d, eax; Size
0x1400225ff  lea     rdx, [rbp+50h+Src]; Src
0x140022603  call    memmove
0x140022608  mov     rax, [rsi+90h]
0x14002260f  mov     [rdi], rax
0x140022612  mov     [rsi+90h], rdi
0x140022619  mov     qword ptr [r14], 0
0x140022620  jmp     loc_14002231A
0x140022625  mov     rcx, [rdx+20h]
0x140022629  xor     edx, edx
0x14002262b  cmp     rcx, r10
0x14002262e  lea     rax, [rcx-20h]
0x140022632  cmovnz  rdx, rax
0x140022636  test    rdx, rdx
0x140022639  jnz     loc_1400224E4
0x14002263f  jmp     loc_1400224EE
0x140022644  call    cs:__imp_ExFreeToPagedLookasideList
0x14002264b  nop     dword ptr [rax+rax+00h]
0x140022650  jmp     loc_14002238A
0x140022655  test    dword ptr [r13+0D84h], 800000h
0x140022660  jnz     loc_1400225BF
0x140022666  nop
0x140022667  lock inc dword ptr [r13+0F00h]
0x14002266f  nop
0x140022670  jmp     loc_1400225BF
0x140022675  mov     rax, cs:KdDebuggerEnabled
0x14002267c  cmp     [rax], dil
0x14002267f  jnz     loc_140022745
0x140022685  mov     r8b, 1
0x140022688  mov     edx, 20000000h
0x14002268d  mov     rcx, rsi
0x140022690  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140022695  mov     rsi, [rsp+150h+var_100]
0x14002269a  jmp     loc_1400224FF
0x14002269f  xor     r8d, r8d; __int64
0x1400226a2  mov     byte ptr [rbp+50h+var_80+2], 1
0x1400226a6  xor     edx, edx; __int64
0x1400226a8  mov     [rsp+150h+var_130], rdi; __int64
0x1400226ad  mov     rcx, r15; this
0x1400226b0  call    ?AdjustAllocatorSummary@CmsAllocator@@QEAAX_J000@Z; CmsAllocator::AdjustAllocatorSummary(__int64,__int64,__int64,__int64)
0x1400226b5  jmp     loc_1400224A2
0x1400226ba  or      dword ptr [rbx+38h], 100h
0x1400226c1  mov     r8, r9; __int64
0x1400226c4  mov     rdx, rsi; struct CmsTransactionContext *
0x1400226c7  mov     dword ptr [rbp+50h+var_60], 200h
0x1400226ce  mov     rcx, r11; this
0x1400226d1  call    ?IncrementStreamReserveClusters@CmsStream@@QEAAXAEAVCmsTransactionContext@@_J@Z; CmsStream::IncrementStreamReserveClusters(CmsTransactionContext &,__int64)
0x1400226d6  jmp     loc_1400225BF
0x1400226db  mov     eax, [rbx+38h]
0x1400226de  bt      eax, 8
0x1400226e2  jnb     loc_1400224CA
0x1400226e8  cmp     [rbx+30h], r9
0x1400226ec  jnz     loc_1400224CA
0x1400226f2  xor     r12d, r12d
0x1400226f5  btr     eax, 8
0x1400226f9  mov     [rbx+38h], eax
0x1400226fc  jmp     loc_1400224CA
0x140022701  mov     rdx, [rsp+150h+var_100]
0x140022706  xor     eax, eax
0x140022708  mov     rsi, [rsi+8]
0x14002270c  xor     ecx, ecx
0x14002270e  mov     word ptr [rsp+150h+var_108], ax
0x140022713  neg     r9
0x140022716  mov     [rsp+150h+var_110], cx
0x14002271b  xor     r8d, r8d
0x14002271e  mov     qword ptr [rsp+150h+var_118], rax
0x140022723  mov     rcx, r11
  ... truncated ...
```
