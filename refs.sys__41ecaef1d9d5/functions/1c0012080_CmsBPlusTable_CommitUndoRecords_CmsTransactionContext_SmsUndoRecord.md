# CmsBPlusTable::CommitUndoRecords(CmsTransactionContext *,SmsUndoRecord *)

- ea: `0x1c0012080`
- end: `0x1c001236f`
- name: `?CommitUndoRecords@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@@Z`
- size: `751`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct SmsUndoRecord *)`
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0010b30`
- `0x1c0011660`
- `0x1c00224d0`
- `0x1c002313c`
- `0x1c0036af0`
- `0x1c0040310`

## callees

- `0x1c000384c`
- `0x1c0012080`
- `0x1c002357c`
- `0x1c0024964`
- `0x1c006ac80`
- `0x1c00ccfc0`
- `0x1c00cd034`
- `0x1c00d1c8c`
- `0x1c00d7d34`
- `0x1c00dc880`
- `0x1c00dcbd8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c00121ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0074088`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00121ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0074088`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00740a9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00740c8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00740a9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00740c8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001214c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00741f3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001214c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00741f3`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001212e`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001212e`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c0074112`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00122d7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00122d7`

## pseudocode

```c
void __fastcall CmsBPlusTable::CommitUndoRecords(
        struct CmsTransactionContext *a1,
        struct SmsUndoRecord *a2,
        __int64 a3,
        unsigned __int8 a4)
{
  __int64 i; // rbx
  _QWORD *v7; // rdi
  int v8; // eax
  __int64 v9; // r14
  __int64 v10; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v11; // rcx
  unsigned __int64 v12; // rdi
  __int64 v13; // r15
  _BYTE *v14; // r14
  bool v15; // zf
  CmsVolumeContainer *v16; // r10
  ULONG_PTR v17; // r8
  struct _IO_REMOVE_LOCK *v18; // rcx
  signed __int32 v19; // ecx
  __int64 v20; // rdi
  void *v21; // rcx
  __int64 v22; // rcx
  struct _SmsTrashCleanerEntry **v23; // rdi
  __int64 v24; // rcx
  int v25; // edx
  unsigned __int64 v26; // r8
  int v27; // eax
  __int128 v28; // [rsp+40h] [rbp-48h] BYREF
  ULONG_PTR v29; // [rsp+98h] [rbp+10h] BYREF
  struct SmsContainer *v30; // [rsp+A0h] [rbp+18h] BYREF

  for ( i = *((_QWORD *)a1 + 324); (struct SmsUndoRecord *)i != a2; i = *((_QWORD *)a1 + 324) )
  {
    v7 = 0;
    *((_QWORD *)a1 + 324) = *(_QWORD *)i;
    v8 = *(_DWORD *)(i + 16);
    if ( v8 < 30 || v8 >= 32 )
    {
      switch ( v8 )
      {
        case 1:
        case 9:
        case 13:
        case 14:
          v7 = *(_QWORD **)(i + 24);
          goto LABEL_4;
        case 5:
        case 6:
          v7 = (_QWORD *)(*(_QWORD *)(i + 24) + 8LL);
          goto LABEL_4;
        case 10:
          v7 = (_QWORD *)(*(_QWORD *)(i + 24) + 24LL);
          v19 = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(i + 40) + 112LL));
          *(_DWORD *)(*v7 + 80LL) = v19;
          *(_DWORD *)(v7[1] + 80LL) = v19;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(i + 40) + 112LL));
          goto LABEL_4;
        case 11:
          v12 = *(_QWORD *)(i + 24);
          v13 = *((_QWORD *)a1 + 4);
          v29 = 0;
          if ( !*(_BYTE *)(v12 + 67) )
          {
            v14 = (_BYTE *)(v12 + 64);
            if ( !*(_BYTE *)(v12 + 64) && *(_BYTE *)(*(_QWORD *)(v12 + 72) + 84LL) == 4 && v12 < (unsigned __int64)v14 )
            {
              do
              {
                if ( !*(_QWORD *)(v12 + 8) )
                  break;
                v15 = *v14 == 0;
                v30 = 0;
                if ( v15 )
                {
                  v16 = *(CmsVolumeContainer **)(v13 + 3048);
                  v17 = *(_QWORD *)v12 >> (*(_BYTE *)(*((_QWORD *)v16 + 1) + 76LL) + 1);
                  v29 = v17;
                }
                else
                {
                  v22 = *(_QWORD *)(v13 + 3048);
                  v28 = *(_OWORD *)v12;
                  CmsVolumeContainer::GetContainerIdFromRealRange(v22, a1, &v28, &v29);
                  v16 = *(CmsVolumeContainer **)(v13 + 3048);
                  v17 = v29;
                }
                CmsVolumeContainer::GetContainerReference(v16, a1, v17, (PRTL_DYNAMIC_HASH_TABLE_ENTRY *)&v30, 1u, 0, 0);
                if ( _InterlockedDecrement((volatile signed __int32 *)v30 + 24) < 0 && (_BYTE)KdDebuggerEnabled )
                  __debugbreak();
                v18 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(v13 + 3048) + 328LL);
                _InterlockedDecrement((volatile signed __int32 *)v30 + 22);
                IoReleaseRemoveLockEx(v18, 0, 0x20u);
                --*((_DWORD *)a1 + 706);
                v12 += 16LL;
              }
              while ( v12 < (unsigned __int64)v14 );
            }
          }
          break;
        case 15:
          CmsBPlusTable::ProcessUndoDeleteQueue(*(CmsBPlusTable **)(i + 40), a2, *(void **)(i + 24), 1u);
          break;
        case 16:
          CmsBPlusTable::ProcessUndoProcessedDeleteQueue(*(CmsBPlusTable **)(i + 40), a2, *(void **)(i + 24), 1u);
          break;
        case 17:
          v20 = *(_QWORD *)(i + 24);
          if ( *(_QWORD *)(v20 + 24) )
          {
            v21 = *(void **)(v20 + 16);
            if ( v21 )
              ExFreePoolWithTag(v21, 0);
            CmsReferenced::Release(*(CmsReferenced **)v20);
          }
          ExReleasePushLockEx(*(_QWORD *)(i + 40) + 136LL, 0);
          goto LABEL_31;
        case 18:
LABEL_31:
          CmsReferenced::Release(*(CmsReferenced **)(i + 40));
          break;
        case 19:
          ExReleasePushLockEx(*(_QWORD *)(i + 40) + 136LL, 0);
          break;
        case 21:
        case 27:
        case 29:
          CmsReferenced::Release(**(CmsReferenced ***)(i + 24));
          break;
        case 32:
          v23 = *(struct _SmsTrashCleanerEntry ***)(i + 24);
          *(_QWORD *)(*((_QWORD *)*v23 + 4) + 16LL) |= 0x10000000uLL;
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)*v23 + 4) + 48LL) + 112LL) = 1;
          ((void (__fastcall *)(_QWORD))qword_1C0136A38)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)*v23 + 4) + 48LL) + 72LL));
          CmsTrashTable::AddTrashCleanerEntry(*(CmsTrashTable **)(*((_QWORD *)a1 + 4) + 3136LL), *v23, 1u);
          break;
        case 34:
          v24 = *(_QWORD *)(i + 24);
          v25 = *(_DWORD *)(v24 + 8);
          v26 = *(_QWORD *)v24;
          if ( !v25 )
          {
            CmsVolumeContainer::SetContainerHasGlobalTableDataUnsafe(
              *(CmsVolumeContainer **)(*((_QWORD *)a1 + 4) + 3048LL),
              a1,
              v26,
              a4);
            goto LABEL_4;
          }
          if ( v25 != 1 )
            goto LABEL_4;
          CmsVolumeContainer::SetContainerStationaryUnsafe(
            *(CmsVolumeContainer **)(*((_QWORD *)a1 + 4) + 3048LL),
            a1,
            v26,
            a4);
          break;
        default:
          goto LABEL_4;
      }
    }
    else
    {
LABEL_4:
      v9 = 0;
      if ( v7 )
      {
        while ( (unsigned int)v9 < 2 )
        {
          if ( v7[v9] )
            (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, _QWORD *, __int64))(**(_QWORD **)(*(_QWORD *)(i + 40) + 96LL)
                                                                                              + 72LL))(
              *(_QWORD *)(*(_QWORD *)(i + 40) + 96LL),
              a1,
              &v7[v9],
              3);
          v9 = (unsigned int)(v9 + 1);
        }
      }
    }
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, __int64))(**(_QWORD **)(i + 40) + 168LL))(
      *(_QWORD *)(i + 40),
      a1,
      i + 48);
    v10 = *(_QWORD *)(i - 8);
    if ( !v10 )
      goto LABEL_14;
    if ( *(_BYTE *)(v10 + 8) )
    {
      v11 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
      if ( *(_BYTE *)(v10 + 9) )
      {
        ++*(_DWORD *)(v10 + 92);
        if ( ExQueryDepthSList(&v11->L.ListHead) >= *(_WORD *)(v10 + 80) )
        {
          ++*(_DWORD *)(v10 + 96);
          (*(void (__fastcall **)(__int64))(v10 + 120))(i - 8);
        }
        else
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), (PSLIST_ENTRY)(i - 8));
        }
      }
      else
      {
        ExFreeToNPagedLookasideList(v11, (PVOID)(i - 8));
      }
      continue;
    }
    v27 = *(_DWORD *)(v10 + 80);
    if ( v27 < *(_DWORD *)(v10 + 84) || *(_DWORD *)(v10 + 88) >= v27 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), (PSLIST_ENTRY)(i - 8));
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 80));
    }
    else
    {
LABEL_14:
      ExFreePoolWithTag((PVOID)(i - 8), 0);
    }
  }
}

```

## disassembly

```asm
0x1c0012080  push    rbx
0x1c0012082  push    rbp
0x1c0012083  push    rsi
0x1c0012084  sub     rsp, 70h
0x1c0012088  mov     rbx, [rcx+0A20h]
0x1c001208f  mov     rbp, rdx
0x1c0012092  mov     rsi, rcx
0x1c0012095  cmp     rbx, rdx
0x1c0012098  jnz     short loc_1C00120A3
0x1c001209a  add     rsp, 70h
0x1c001209e  pop     rsi
0x1c001209f  pop     rbp
0x1c00120a0  pop     rbx
0x1c00120a1  retn
0x1c00120a3  mov     [rsp+88h+var_20], rdi
0x1c00120a8  mov     [rsp+88h+var_28], r12
0x1c00120ad  lea     r12, cs:1C0000000h
0x1c00120b4  mov     [rsp+88h+var_30], r14
0x1c00120b9  mov     [rsp+88h+var_38], r15
0x1c00120be  mov     rax, [rbx]
0x1c00120c1  xor     edi, edi
0x1c00120c3  mov     [rsi+0A20h], rax
0x1c00120ca  mov     eax, [rbx+10h]
0x1c00120cd  cmp     eax, 1Eh
0x1c00120d0  jl      loc_1C0012181
0x1c00120d6  cmp     eax, 20h ; ' '
0x1c00120d9  jge     loc_1C0012181
0x1c00120df  xor     r14d, r14d; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c00120e2  test    rdi, rdi
0x1c00120e5  jnz     loc_1C00121C0
0x1c00120eb  mov     rcx, [rbx+28h]
0x1c00120ef  lea     r8, [rbx+30h]
0x1c00120f3  mov     rdx, rsi
0x1c00120f6  mov     rax, [rcx]
0x1c00120f9  mov     rax, [rax+0A8h]
0x1c0012100  call    cs:__guard_dispatch_icall_fptr
0x1c0012106  mov     rdi, [rbx-8]
0x1c001210a  test    rdi, rdi
0x1c001210d  jz      loc_1C00121A8
0x1c0012113  cmp     byte ptr [rdi+8], 0
0x1c0012117  jz      loc_1C00741DA
0x1c001211d  cmp     byte ptr [rdi+9], 0
0x1c0012121  lea     rcx, [rdi+40h]; Lookaside
0x1c0012125  jz      loc_1C00741CB
0x1c001212b  inc     dword ptr [rdi+5Ch]
0x1c001212e  call    cs:__imp_ExQueryDepthSList
0x1c0012135  nop     dword ptr [rax+rax+00h]
0x1c001213a  cmp     ax, [rdi+50h]
0x1c001213e  jnb     loc_1C001230C
0x1c0012144  lea     rdx, [rbx-8]; ListEntry
0x1c0012148  lea     rcx, [rdi+40h]; ListHead
0x1c001214c  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c0012153  nop     dword ptr [rax+rax+00h]
0x1c0012158  mov     rbx, [rsi+0A20h]
0x1c001215f  cmp     rbx, rbp
0x1c0012162  jnz     loc_1C00120BE
0x1c0012168  mov     r15, [rsp+88h+var_38]
0x1c001216d  mov     r14, [rsp+88h+var_30]
0x1c0012172  mov     r12, [rsp+88h+var_28]
0x1c0012177  mov     rdi, [rsp+88h+var_20]
0x1c001217c  jmp     loc_1C001209A
0x1c0012181  dec     eax; switch 34 cases
0x1c0012183  cmp     eax, 21h
0x1c0012186  ja      def_1C0012199; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c001218c  cdqe
0x1c001218e  mov     ecx, ds:(jpt_1C0012199 - 1C0000000h)[r12+rax*4]
0x1c0012196  add     rcx, r12
0x1c0012199  jmp     rcx; switch jump
0x1c001219f  mov     rdi, [rbx+18h]; jumptable 00000001C0012199 cases 1,9,13,14
0x1c00121a3  jmp     def_1C0012199; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c00121a8  xor     edx, edx; Tag
0x1c00121aa  lea     rcx, [rbx-8]; P
0x1c00121ae  call    cs:__imp_ExFreePoolWithTag
0x1c00121b5  nop     dword ptr [rax+rax+00h]
0x1c00121ba  jmp     short loc_1C0012158
0x1c00121c0  cmp     r14d, 2
0x1c00121c4  jnb     loc_1C00120EB
0x1c00121ca  cmp     qword ptr [rdi+r14*8], 0
0x1c00121cf  lea     r8, [rdi+r14*8]
0x1c00121d3  jz      short loc_1C00121F3
0x1c00121d5  mov     rax, [rbx+28h]
0x1c00121d9  mov     r9d, 3
0x1c00121df  mov     rdx, rsi
0x1c00121e2  mov     rcx, [rax+60h]
0x1c00121e6  mov     rax, [rcx]
0x1c00121e9  mov     rax, [rax+48h]
0x1c00121ed  call    cs:__guard_dispatch_icall_fptr
0x1c00121f3  inc     r14d
0x1c00121f6  jmp     short loc_1C00121C0
0x1c00121f8  mov     rdi, [rbx+18h]; jumptable 00000001C0012199 case 11
0x1c00121fc  mov     r15, [rsi+20h]
0x1c0012200  mov     [rsp+88h+arg_8], 0
0x1c001220c  cmp     byte ptr [rdi+43h], 0
0x1c0012210  jnz     loc_1C00120EB
0x1c0012216  cmp     byte ptr [rdi+40h], 0
0x1c001221a  lea     r14, [rdi+40h]
0x1c001221e  jnz     loc_1C00120EB
0x1c0012224  mov     rax, [rdi+48h]
0x1c0012228  cmp     byte ptr [rax+54h], 4
0x1c001222c  jnz     loc_1C00120EB
0x1c0012232  cmp     rdi, r14
0x1c0012235  jnb     loc_1C00120EB
0x1c001223b  cmp     qword ptr [rdi+8], 0
0x1c0012240  jz      loc_1C00120EB
0x1c0012246  cmp     byte ptr [r14], 0
0x1c001224a  mov     [rsp+88h+arg_10], 0
0x1c0012256  jnz     loc_1C00740DA
0x1c001225c  mov     r10, [r15+0BE8h]
0x1c0012263  mov     r8, [rdi]
0x1c0012266  mov     rax, [r10+8]
0x1c001226a  mov     ecx, [rax+4Ch]
0x1c001226d  inc     ecx
0x1c001226f  shr     r8, cl; unsigned __int64
0x1c0012272  mov     [rsp+88h+arg_8], r8
0x1c001227a  mov     [rsp+88h+var_58], 0; unsigned __int8
0x1c001227f  lea     r9, [rsp+88h+arg_10]; struct SmsContainer **
0x1c0012287  mov     [rsp+88h+var_60], 0; unsigned __int8
0x1c001228c  mov     rdx, rsi; struct CmsTransactionContext *
0x1c001228f  mov     rcx, r10; this
0x1c0012292  mov     [rsp+88h+var_68], 1; unsigned __int8
0x1c0012297  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c001229c  mov     rax, [rsp+88h+arg_10]
0x1c00122a4  mov     ecx, 0FFFFFFFFh
0x1c00122a9  lock xadd [rax+60h], ecx
0x1c00122ae  cmp     ecx, 1
0x1c00122b1  js      loc_1C0074112
0x1c00122b7  mov     rcx, [r15+0BE8h]
0x1c00122be  xor     edx, edx; Tag
0x1c00122c0  mov     rax, [rsp+88h+arg_10]
0x1c00122c8  add     rcx, 148h; RemoveLock
0x1c00122cf  lea     r8d, [rdx+20h]; RemlockSize
0x1c00122d3  lock dec dword ptr [rax+58h]
0x1c00122d7  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00122de  nop     dword ptr [rax+rax+00h]
0x1c00122e3  dec     dword ptr [rsi+0B08h]
0x1c00122e9  add     rdi, 10h
0x1c00122ed  cmp     rdi, r14
0x1c00122f0  jb      loc_1C001223B
0x1c00122f6  jmp     loc_1C00120EB
0x1c00122fb  mov     rcx, [rbx+18h]; jumptable 00000001C0012199 cases 21,27,29
0x1c00122ff  mov     rcx, [rcx]; this
0x1c0012302  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1c0012307  jmp     loc_1C00120EB
0x1c001230c  inc     dword ptr [rdi+60h]
0x1c001230f  lea     rcx, [rbx-8]
0x1c0012313  mov     rax, [rdi+78h]
0x1c0012317  call    cs:__guard_dispatch_icall_fptr
0x1c001231d  jmp     loc_1C0012158
0x1c0012322  mov     rcx, [rbx+28h]; jumptable 00000001C0012199 case 18
0x1c0012326  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1c001232b  jmp     loc_1C00120EB
0x1c0012330  mov     rdi, [rbx+18h]; jumptable 00000001C0012199 case 10
0x1c0012334  mov     ecx, 1
0x1c0012339  mov     rax, [rbx+28h]
0x1c001233d  add     rdi, 18h
0x1c0012341  lock xadd [rax+70h], ecx
0x1c0012346  mov     rax, [rdi]
0x1c0012349  inc     ecx
0x1c001234b  mov     [rax+50h], ecx
0x1c001234e  mov     rax, [rdi+8]
0x1c0012352  mov     [rax+50h], ecx
0x1c0012355  mov     rax, [rbx+28h]
0x1c0012359  lock inc dword ptr [rax+70h]
0x1c001235d  jmp     def_1C0012199; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c0012362  mov     rdi, [rbx+18h]; jumptable 00000001C0012199 cases 5,6
0x1c0012366  add     rdi, 8
0x1c001236a  jmp     def_1C0012199; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c0074046  mov     r8, [rbx+18h]; jumptable 00000001C0012199 case 15
0x1c007404a  mov     r9b, 1; unsigned __int8
0x1c007404d  mov     rcx, [rbx+28h]; this
0x1c0074051  call    ?ProcessUndoDeleteQueue@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAXE@Z; CmsBPlusTable::ProcessUndoDeleteQueue(CmsTransactionContext *,void *,uchar)
0x1c0074056  nop
0x1c0074057  jmp     loc_1C00120EB
0x1c007405c  mov     r8, [rbx+18h]; jumptable 00000001C0012199 case 16
0x1c0074060  mov     r9b, 1; unsigned __int8
0x1c0074063  mov     rcx, [rbx+28h]; this
0x1c0074067  call    ?ProcessUndoProcessedDeleteQueue@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAXE@Z; CmsBPlusTable::ProcessUndoProcessedDeleteQueue(CmsTransactionContext *,void *,uchar)
0x1c007406c  nop
0x1c007406d  jmp     loc_1C00120EB
0x1c0074072  mov     rdi, [rbx+18h]; jumptable 00000001C0012199 case 17
0x1c0074076  cmp     qword ptr [rdi+18h], 0
0x1c007407b  jz      short loc_1C007409C
0x1c007407d  mov     rcx, [rdi+10h]; P
0x1c0074081  test    rcx, rcx
0x1c0074084  jz      short loc_1C0074094
0x1c0074086  xor     edx, edx; Tag
0x1c0074088  call    cs:__imp_ExFreePoolWithTag
0x1c007408f  nop     dword ptr [rax+rax+00h]
0x1c0074094  mov     rcx, [rdi]; this
0x1c0074097  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1c007409c  mov     rcx, [rbx+28h]
0x1c00740a0  xor     edx, edx
0x1c00740a2  add     rcx, 88h
0x1c00740a9  call    cs:__imp_ExReleasePushLockEx
0x1c00740b0  nop     dword ptr [rax+rax+00h]
0x1c00740b5  nop
0x1c00740b6  jmp     loc_1C0012322; jumptable 00000001C0012199 case 18
0x1c00740bb  mov     rcx, [rbx+28h]; jumptable 00000001C0012199 case 19
0x1c00740bf  xor     edx, edx
0x1c00740c1  add     rcx, 88h
0x1c00740c8  call    cs:__imp_ExReleasePushLockEx
0x1c00740cf  nop     dword ptr [rax+rax+00h]
0x1c00740d4  nop
0x1c00740d5  jmp     loc_1C00120EB
0x1c00740da  movups  xmm0, xmmword ptr [rdi]
0x1c00740dd  mov     rcx, [r15+0BE8h]
0x1c00740e4  lea     r9, [rsp+88h+arg_8]
0x1c00740ec  lea     r8, [rsp+88h+var_48]
0x1c00740f1  mov     rdx, rsi
0x1c00740f4  movaps  [rsp+88h+var_48], xmm0
0x1c00740f9  call    ?GetContainerIdFromRealRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@PEA_K@Z; CmsVolumeContainer::GetContainerIdFromRealRange(CmsTransactionContext *,_RANGE,unsigned __int64 *)
0x1c00740fe  mov     r10, [r15+0BE8h]
0x1c0074105  mov     r8, [rsp+88h+arg_8]
0x1c007410d  jmp     loc_1C001227A
0x1c0074112  mov     rax, cs:KdDebuggerEnabled
0x1c0074119  cmp     byte ptr [rax], 0
0x1c007411c  jz      loc_1C00122B7
0x1c0074122  int     3; Trap to Debugger
0x1c0074123  jmp     loc_1C00122B7
0x1c0074128  mov     rdi, [rbx+18h]; jumptable 00000001C0012199 case 32
0x1c007412c  mov     rax, [rdi]
0x1c007412f  mov     rcx, [rax+20h]
0x1c0074133  or      qword ptr [rcx+10h], 10000000h
0x1c007413b  mov     rax, [rdi]
0x1c007413e  mov     rcx, [rax+20h]
0x1c0074142  mov     rax, [rcx+30h]
0x1c0074146  mov     byte ptr [rax+70h], 1
0x1c007414a  mov     rax, [rdi]
0x1c007414d  mov     rcx, [rax+20h]
0x1c0074151  mov     rax, cs:qword_1C0136A38
0x1c0074158  mov     rcx, [rcx+30h]
0x1c007415c  mov     rcx, [rcx+48h]
0x1c0074160  call    cs:__guard_dispatch_icall_fptr
0x1c0074166  mov     rcx, [rsi+20h]
0x1c007416a  mov     r8b, 1; unsigned __int8
0x1c007416d  mov     rdx, [rdi]; struct _SmsTrashCleanerEntry *
0x1c0074170  mov     rcx, [rcx+0C40h]; this
0x1c0074177  call    ?AddTrashCleanerEntry@CmsTrashTable@@QEAAXPEAU_SmsTrashCleanerEntry@@E@Z; CmsTrashTable::AddTrashCleanerEntry(_SmsTrashCleanerEntry *,uchar)
0x1c007417c  nop
0x1c007417d  jmp     loc_1C00120EB
0x1c0074182  mov     rcx, [rbx+18h]; jumptable 00000001C0012199 case 34
0x1c0074186  mov     edx, [rcx+8]
0x1c0074189  mov     r8, [rcx]; unsigned __int64
0x1c007418c  test    edx, edx
0x1c007418e  jz      short loc_1C00741B2
0x1c0074190  cmp     edx, 1
0x1c0074193  jnz     def_1C0012199; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c0074199  mov     rcx, [rsi+20h]
0x1c007419d  mov     rdx, rsi; struct CmsTransactionContext *
0x1c00741a0  mov     rcx, [rcx+0BE8h]; this
0x1c00741a7  call    ?SetContainerStationaryUnsafe@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KE@Z; CmsVolumeContainer::SetContainerStationaryUnsafe(CmsTransactionContext *,unsigned __int64,uchar)
0x1c00741ac  nop
0x1c00741ad  jmp     loc_1C00120EB
0x1c00741b2  mov     rcx, [rsi+20h]
0x1c00741b6  mov     rdx, rsi; struct CmsTransactionContext *
0x1c00741b9  mov     rcx, [rcx+0BE8h]; this
0x1c00741c0  call    ?SetContainerHasGlobalTableDataUnsafe@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KE@Z; CmsVolumeContainer::SetContainerHasGlobalTableDataUnsafe(CmsTransactionContext *,unsigned __int64,uchar)
0x1c00741c5  nop
0x1c00741c6  jmp     def_1C0012199; jumptable 00000001C0012199 default case, cases 2-4,7,8,12,20,22-26,28,30,31,33
0x1c00741cb  lea     rdx, [rbx-8]; Entry
0x1c00741cf  call    ExFreeToNPagedLookasideList
0x1c00741d4  nop
0x1c00741d5  jmp     loc_1C0012158
0x1c00741da  mov     eax, [rdi+50h]
0x1c00741dd  cmp     eax, [rdi+54h]
0x1c00741e0  jl      short loc_1C00741EB
0x1c00741e2  cmp     [rdi+58h], eax
0x1c00741e5  jl      loc_1C00121A8
0x1c00741eb  lea     rcx, [rdi+40h]; ListHead
0x1c00741ef  lea     rdx, [rbx-8]; ListEntry
0x1c00741f3  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c00741fa  nop     dword ptr [rax+rax+00h]
0x1c00741ff  lock inc dword ptr [rdi+50h]
0x1c0074203  jmp     loc_1C0012158
```
