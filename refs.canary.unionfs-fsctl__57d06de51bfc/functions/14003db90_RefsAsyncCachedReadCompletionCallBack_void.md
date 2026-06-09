# RefsAsyncCachedReadCompletionCallBack(void *)

- ea: `0x14003db90`
- end: `0x14003e084`
- name: `?RefsAsyncCachedReadCompletionCallBack@@YAEPEAX@Z`
- size: `1268`
- prototype: `unsigned __int8 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14003db90`
- `0x14003fbe0`
- `0x140040410`
- `0x140042af0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14003dd94`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14003dd94`
- `ntoskrnl!IofCompleteRequest` at `0x14003dc8b`
- `ntoskrnl!IofCompleteRequest` at `0x14003dc8b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14003ddac`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14003ddac`
- `ntoskrnl!IoFreeMdl` at `0x14003dff5`
- `ntoskrnl!IoFreeMdl` at `0x14003dff5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003dc0e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003dc7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003df1d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003dc0e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003dc7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003df1d`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x14003dbd9`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x14003dbd9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003e039`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003e039`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003de68`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14003de68`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003de77`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003de77`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003deb3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003deb3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003debf`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14003debf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003de05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e021`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e04e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e061`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003de05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e021`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e04e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e061`

## pseudocode

```c
unsigned __int8 __fastcall RefsAsyncCachedReadCompletionCallBack(_QWORD *a1)
{
  __int64 v1; // r9
  int v2; // esi
  __int64 v4; // rdi
  IRP *v5; // rbp
  __int64 v6; // rcx
  bool v7; // zf
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *v9; // r9
  unsigned int v10; // eax
  _QWORD *v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  _QWORD *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  _QWORD **v18; // rbx
  _QWORD *v19; // rcx
  __int64 j; // rcx
  __int64 v21; // rax
  int v22; // eax
  PIRP TopLevelIrp; // rax
  IRP *v24; // rcx
  void *v25; // rcx
  _QWORD *v26; // rax
  _QWORD *v27; // r14
  _QWORD *v28; // r12
  __int64 v29; // rcx
  struct _FAST_MUTEX *v30; // rbx
  _QWORD *v31; // rax
  _QWORD *v32; // rcx
  unsigned int v33; // eax
  _QWORD *i; // rax
  PMDL MdlAddress; // rcx

  v1 = a1[1];
  v2 = *((_DWORD *)a1 + 36);
  v4 = *(_QWORD *)(v1 + 64);
  v5 = *(IRP **)(v4 + 72);
  if ( v5->IoStatus.Status >= 0 && *(_BYTE *)(*(_QWORD *)(v4 + 64) + 10496LL) )
    RefsIoPerfCollectReadWriteData(
      *(struct _VCB **)(v4 + 64),
      *(struct _IRP **)(v4 + 72),
      *(struct _IRP_CONTEXT **)(v1 + 64),
      (struct REFS_IO_CONTEXT *)v1);
  v6 = a1[2];
  v7 = (*((_DWORD *)a1 + 24))-- == 1;
  if ( v7 )
    *((_DWORD *)a1 + 25) &= ~2u;
  *((_DWORD *)a1 + 25) &= ~4u;
  ExReleaseDisownedFastResource(v6);
  *((_DWORD *)a1 + 25) &= ~1u;
  v8 = *((_DWORD *)a1 - 2);
  if ( v8 >= RefsNumberProcessors )
    v8 %= RefsNumberProcessors;
  ExFreeToNPagedLookasideList(&RefsAsyncCachedReadCtxLookasideList[(unsigned __int64)v8], a1 - 1);
  if ( v5->IoStatus.Status < 0 )
  {
    MdlAddress = v5->MdlAddress;
    if ( MdlAddress )
    {
      if ( (MdlAddress->MdlFlags & 2) == 0 && (v2 & 1) != 0 )
      {
        IoFreeMdl(MdlAddress);
        v5->MdlAddress = 0;
      }
    }
  }
  if ( v5->IoStatus.Status == -1073739768 )
  {
    RefsPostRequest((struct _IRP_CONTEXT *)v4, v5, 0, 0);
  }
  else
  {
    RefsReleaseAllResources((struct _IRP_CONTEXT *)v4);
    v12 = (_QWORD *)(v4 + 640);
    v13 = *(_QWORD **)(v4 + 640);
    if ( v13 != (_QWORD *)(v4 + 640) )
    {
      v14 = 0;
      while ( v13 != v12 )
      {
        if ( *((_WORD *)v13 - 4) == 2087 )
        {
          v14 = v13 - 1;
          break;
        }
        v13 = (_QWORD *)*v13;
      }
      if ( v14 )
      {
        while ( 1 )
        {
          v27 = v14 + 1;
          v28 = 0;
          if ( (_QWORD *)*v12 != v12 )
          {
            for ( i = (_QWORD *)*v27; ; i = (_QWORD *)*i )
            {
              v27 = v14 + 1;
              if ( i == v12 )
                break;
              if ( *((_WORD *)i - 4) == 2087 )
              {
                v28 = i - 1;
                break;
              }
            }
          }
          v29 = v14[6];
          if ( v29 )
          {
            if ( (*(_DWORD *)(v29 + 152) & 0x2000) != 0 )
              _InterlockedAnd((volatile signed __int32 *)(v29 + 152), 0xFFFFDFFF);
            v30 = *(struct _FAST_MUTEX **)(v14[6] + 48LL);
            KeEnterGuardedRegion();
            ExAcquireFastMutexUnsafe(v30);
            _InterlockedIncrement((volatile signed __int32 *)(v14[6] + 172LL));
            *(_QWORD *)(v14[6] + 280LL) = 0;
            ++*(_DWORD *)(v14[6] + 172LL);
            ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v14[6] + 48LL));
            KeLeaveGuardedRegion();
          }
          v31 = (_QWORD *)*v27;
          if ( *(_QWORD **)(*v27 + 8LL) != v27 || (v32 = (_QWORD *)v14[2], (_QWORD *)*v32 != v27) )
LABEL_65:
            __fastfail(3u);
          *v32 = v31;
          v31[1] = v32;
          if ( v14 != (_QWORD *)(v4 + 728) )
          {
            v33 = *((_DWORD *)v14 - 2);
            if ( v33 >= RefsNumberProcessors )
              v33 %= RefsNumberProcessors;
            ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v33], v14 - 1);
          }
          if ( !v28 )
            break;
          v14 = v28;
        }
      }
    }
    while ( 1 )
    {
      v15 = *(_QWORD **)(v4 + 600);
      if ( !v15 )
        break;
      *(_QWORD *)(v4 + 600) = *v15;
      ExFreePoolWithTag(v15, 0);
    }
    v16 = *(_DWORD *)(v4 + 4);
    if ( (v16 & 0x400) != 0 || (v17 = *(_QWORD *)(v4 + 8), (v17 & 0x10000) != 0) )
    {
      if ( (v16 & 0x40000) != 0 )
      {
        *(_DWORD *)(v4 + 4) = v16 & 0xFFFBFBFF;
      }
      else
      {
        *(_DWORD *)(v4 + 4) = v16 & 0xF779C0CD;
        *(_QWORD *)(v4 + 8) &= ~0x400uLL;
      }
      *(_DWORD *)(v4 + 16) = 0;
    }
    else
    {
      if ( (v17 & 0x20000000000LL) != 0 )
      {
        *(_DWORD *)(v4 + 236) &= ~1u;
        *(_QWORD *)(v4 + 8) = v17 & 0xFFFFFDFFFFFFFFFFuLL;
      }
      if ( *(_QWORD *)(v4 + 336) )
      {
        *(_DWORD *)(v4 + 324) &= ~1u;
        *(_QWORD *)(v4 + 336) = 0;
      }
      v18 = (_QWORD **)(v4 + 576);
      while ( 1 )
      {
        v19 = *v18;
        if ( *v18 == v18 )
          break;
        if ( (_QWORD **)v19[1] != v18 )
          goto LABEL_65;
        v26 = (_QWORD *)*v19;
        if ( *(_QWORD **)(*v19 + 8LL) != v19 )
          goto LABEL_65;
        *v18 = v26;
        v26[1] = v18;
        ExFreePoolWithTag(v19 - 12, 0);
      }
      for ( j = 0; j != 2; ++j )
      {
        v21 = 112 * j;
        *(_QWORD *)(v21 + v4 + 352) = 0;
      }
      v7 = (*(_BYTE *)(v4 + 8) & 0x20) == 0;
      *(_DWORD *)(v4 + 592) = 0;
      if ( !v7 )
      {
        SeReleaseSubjectContext(*(PSECURITY_SUBJECT_CONTEXT *)(v4 + 144));
        ExFreePoolWithTag(*(PVOID *)(v4 + 144), 0);
      }
      v22 = *(_DWORD *)(v4 + 8);
      *(_QWORD *)(v4 + 144) = 0;
      if ( (*(_QWORD *)&v22 & 0x100000LL) != 0 )
      {
        TopLevelIrp = IoGetTopLevelIrp();
        v24 = (IRP *)TopLevelIrp->MdlAddress;
        *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
        *(_QWORD *)&TopLevelIrp->Flags = 0;
        IoSetTopLevelIrp(v24);
        *(_QWORD *)(v4 + 8) &= ~0x100000uLL;
      }
      v25 = *(void **)(v4 + 712);
      if ( v25 )
      {
        ExFreePoolWithTag(v25, 0);
        *(_QWORD *)(v4 + 712) = 0;
      }
      if ( (*(_DWORD *)(v4 + 8) & 0x80000) != 0 )
      {
        v9 = RefsIrpAndIoContextLookasideList;
        v10 = *(_DWORD *)(v4 - 8);
        if ( *(_WORD *)(v4 + 2) != 1664 )
          v9 = RefsIrpContextLookasideList;
        if ( v10 >= RefsNumberProcessors )
          v10 %= RefsNumberProcessors;
        ExFreeToNPagedLookasideList(&v9[(unsigned __int64)v10], (PVOID)(v4 - 8));
      }
    }
    IofCompleteRequest(v5, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x14003db90  push    rbx
0x14003db92  push    rbp
0x14003db93  push    rsi
0x14003db94  push    rdi
0x14003db95  push    r12
0x14003db97  push    r13
0x14003db99  push    r14
0x14003db9b  push    r15
0x14003db9d  sub     rsp, 28h
0x14003dba1  mov     r9, [rcx+8]; struct REFS_IO_CONTEXT *
0x14003dba5  xor     r13d, r13d
0x14003dba8  mov     esi, [rcx+90h]
0x14003dbae  mov     rbx, rcx
0x14003dbb1  mov     rdi, [r9+40h]
0x14003dbb5  mov     rbp, [rdi+48h]
0x14003dbb9  cmp     [rbp+30h], r13d
0x14003dbbd  jge     loc_14003DFA3
0x14003dbc3  mov     rcx, [rbx+10h]
0x14003dbc7  lea     rdx, [rbx+18h]
0x14003dbcb  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x14003dbcf  jnz     short loc_14003DBD5
0x14003dbd1  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x14003dbd5  and     dword ptr [rdx+4Ch], 0FFFFFFFBh
0x14003dbd9  call    cs:__imp_ExReleaseDisownedFastResource
0x14003dbe0  nop     dword ptr [rax+rax+00h]
0x14003dbe5  and     dword ptr [rbx+64h], 0FFFFFFFEh
0x14003dbe9  mov     eax, [rbx-8]
0x14003dbec  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14003dbf2  mov     r8, cs:?RefsAsyncCachedReadCtxLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsAsyncCachedReadCtxLookasideList
0x14003dbf9  cmp     eax, ecx
0x14003dbfb  jnb     loc_14003DFC9
0x14003dc01  mov     ecx, eax
0x14003dc03  lea     rdx, [rbx-8]; Entry
0x14003dc07  shl     rcx, 7
0x14003dc0b  add     rcx, r8; Lookaside
0x14003dc0e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003dc15  nop     dword ptr [rax+rax+00h]
0x14003dc1a  cmp     [rbp+30h], r13d
0x14003dc1e  jl      loc_14003DFD4
0x14003dc24  cmp     dword ptr [rbp+30h], 0C0000808h
0x14003dc2b  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14003dc2e  jnz     short loc_14003DCAB
0x14003dc30  xor     r9d, r9d; unsigned __int8
0x14003dc33  xor     r8d, r8d; unsigned __int8
0x14003dc36  mov     rdx, rbp; struct _IRP *
0x14003dc39  call    ?RefsPostRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z; RefsPostRequest(_IRP_CONTEXT *,_IRP *,uchar,uchar)
0x14003dc3e  jmp     short loc_14003DC97
0x14003dc40  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x14003dc47  lea     r8, [rdi-8]
0x14003dc4b  mov     eax, [r8]
0x14003dc4e  mov     ecx, 680h
0x14003dc53  cmp     [rdi+2], cx
0x14003dc57  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14003dc5d  jz      short loc_14003DC66
0x14003dc5f  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x14003dc66  cmp     eax, ecx
0x14003dc68  jnb     loc_14003E079
0x14003dc6e  mov     ecx, eax
0x14003dc70  mov     rdx, r8; Entry
0x14003dc73  shl     rcx, 7
0x14003dc77  add     rcx, r9; Lookaside
0x14003dc7a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003dc81  nop     dword ptr [rax+rax+00h]
0x14003dc86  mov     dl, 1; PriorityBoost
0x14003dc88  mov     rcx, rbp; Irp
0x14003dc8b  call    cs:__imp_IofCompleteRequest
0x14003dc92  nop     dword ptr [rax+rax+00h]
0x14003dc97  mov     al, 1
0x14003dc99  add     rsp, 28h
0x14003dc9d  pop     r15
0x14003dc9f  pop     r14
0x14003dca1  pop     r13
0x14003dca3  pop     r12
0x14003dca5  pop     rdi
0x14003dca6  pop     rsi
0x14003dca7  pop     rbp
0x14003dca8  pop     rbx
0x14003dca9  retn
0x14003dcab  call    ?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseAllResources(_IRP_CONTEXT *)
0x14003dcb0  lea     r15, [rdi+280h]
0x14003dcb7  mov     rax, [r15]
0x14003dcba  cmp     rax, r15
0x14003dcbd  jz      short loc_14003DCE5
0x14003dcbf  mov     rsi, r13
0x14003dcc2  mov     r8d, 827h
0x14003dcc8  cmp     rax, r15
0x14003dccb  jz      short loc_14003DCDC
0x14003dccd  cmp     [rax-8], r8w
0x14003dcd2  jnz     loc_14003DF76
0x14003dcd8  lea     rsi, [rax-8]
0x14003dcdc  test    rsi, rsi
0x14003dcdf  jnz     loc_14003DE37
0x14003dce5  mov     rcx, [rdi+258h]; P
0x14003dcec  test    rcx, rcx
0x14003dcef  jnz     loc_14003E015
0x14003dcf5  mov     eax, [rdi+4]
0x14003dcf8  bt      eax, 0Ah
0x14003dcfc  jb      loc_14003DE16
0x14003dd02  mov     rcx, [rdi+8]
0x14003dd06  bt      rcx, 10h
0x14003dd0b  jb      loc_14003DE16
0x14003dd11  bt      rcx, 29h ; ')'
0x14003dd16  jnb     short loc_14003DD30
0x14003dd18  and     dword ptr [rdi+0ECh], 0FFFFFFFEh
0x14003dd1f  mov     rax, 0FFFFFDFFFFFFFFFFh
0x14003dd29  and     rcx, rax
0x14003dd2c  mov     [rdi+8], rcx
0x14003dd30  cmp     [rdi+150h], r13
0x14003dd37  jz      short loc_14003DD47
0x14003dd39  and     dword ptr [rdi+144h], 0FFFFFFFEh
0x14003dd40  mov     [rdi+150h], r13
0x14003dd47  lea     rbx, [rdi+240h]
0x14003dd4e  mov     rcx, [rbx]
0x14003dd51  cmp     rcx, rbx
0x14003dd54  jnz     loc_14003DDE1
0x14003dd5a  mov     rcx, r13
0x14003dd5d  imul    rax, rcx, 70h ; 'p'
0x14003dd61  inc     rcx
0x14003dd64  mov     [rax+rdi+160h], r13
0x14003dd6c  cmp     rcx, 2
0x14003dd70  jnz     short loc_14003DD5D
0x14003dd72  test    byte ptr [rdi+8], 20h
0x14003dd76  mov     [rdi+250h], r13d
0x14003dd7d  jnz     loc_14003E032
0x14003dd83  mov     eax, [rdi+8]
0x14003dd86  mov     [rdi+90h], r13
0x14003dd8d  bt      rax, 14h
0x14003dd92  jnb     short loc_14003DDBE
0x14003dd94  call    cs:__imp_IoGetTopLevelIrp
0x14003dd9b  nop     dword ptr [rax+rax+00h]
0x14003dda0  mov     rcx, [rax+8]; Irp
0x14003dda4  mov     [rax+4], r13d
0x14003dda8  mov     [rax+10h], r13
0x14003ddac  call    cs:__imp_IoSetTopLevelIrp
0x14003ddb3  nop     dword ptr [rax+rax+00h]
0x14003ddb8  btr     qword ptr [rdi+8], 14h
0x14003ddbe  mov     rcx, [rdi+2C8h]; P
0x14003ddc5  test    rcx, rcx
0x14003ddc8  jnz     loc_14003E05F
0x14003ddce  mov     eax, [rdi+8]
0x14003ddd1  bt      rax, 13h
0x14003ddd6  jnb     loc_14003DC86
0x14003dddc  jmp     loc_14003DC40
0x14003dde1  cmp     [rcx+8], rbx
0x14003dde5  jnz     loc_14003DF6F
0x14003ddeb  mov     rax, [rcx]
0x14003ddee  cmp     [rax+8], rcx
0x14003ddf2  jnz     loc_14003DF6F
0x14003ddf8  mov     [rbx], rax
0x14003ddfb  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14003ddff  xor     edx, edx; Tag
0x14003de01  mov     [rax+8], rbx
0x14003de05  call    cs:__imp_ExFreePoolWithTag
0x14003de0c  nop     dword ptr [rax+rax+00h]
0x14003de11  jmp     loc_14003DD4E
0x14003de16  bt      eax, 12h
0x14003de1a  jb      loc_14003DF62
0x14003de20  and     eax, 0F779C0CDh
0x14003de25  mov     [rdi+4], eax
0x14003de28  btr     qword ptr [rdi+8], 0Ah
0x14003de2e  mov     [rdi+10h], r13d
0x14003de32  jmp     loc_14003DC86
0x14003de37  lea     r14, [rsi+8]
0x14003de3b  mov     r12, r13
0x14003de3e  cmp     [r15], r15
0x14003de41  jnz     loc_14003DF40
0x14003de47  mov     rcx, [rsi+30h]
0x14003de4b  test    rcx, rcx
0x14003de4e  jz      short loc_14003DECB
0x14003de50  test    dword ptr [rcx+98h], 2000h
0x14003de5a  jnz     loc_14003DF83
0x14003de60  mov     rax, [rsi+30h]
0x14003de64  mov     rbx, [rax+30h]
0x14003de68  call    cs:__imp_KeEnterGuardedRegion
0x14003de6f  nop     dword ptr [rax+rax+00h]
0x14003de74  mov     rcx, rbx; FastMutex
0x14003de77  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003de7e  nop     dword ptr [rax+rax+00h]
0x14003de83  mov     rax, [rsi+30h]
0x14003de87  lock inc dword ptr [rax+0ACh]
0x14003de8e  mov     rax, [rsi+30h]
0x14003de92  mov     [rax+118h], r13
0x14003de99  mov     rcx, [rsi+30h]
0x14003de9d  mov     eax, [rcx+0ACh]
0x14003dea3  inc     eax
0x14003dea5  mov     [rcx+0ACh], eax
0x14003deab  mov     rcx, [rsi+30h]
0x14003deaf  mov     rcx, [rcx+30h]; FastMutex
0x14003deb3  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003deba  nop     dword ptr [rax+rax+00h]
0x14003debf  call    cs:__imp_KeLeaveGuardedRegion
0x14003dec6  nop     dword ptr [rax+rax+00h]
0x14003decb  mov     rax, [r14]
0x14003dece  cmp     [rax+8], r14
0x14003ded2  jnz     loc_14003DF6F
0x14003ded8  mov     rcx, [rsi+10h]
0x14003dedc  cmp     [rcx], r14
0x14003dedf  jnz     loc_14003DF6F
0x14003dee5  mov     [rcx], rax
0x14003dee8  mov     [rax+8], rcx
0x14003deec  lea     rax, [rdi+2D8h]
0x14003def3  cmp     rsi, rax
0x14003def6  jz      short loc_14003DF29
0x14003def8  mov     eax, [rsi-8]
0x14003defb  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14003df01  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x14003df08  cmp     eax, ecx
0x14003df0a  jnb     loc_14003E00A
0x14003df10  mov     ecx, eax
0x14003df12  lea     rdx, [rsi-8]; Entry
0x14003df16  shl     rcx, 7
0x14003df1a  add     rcx, r8; Lookaside
0x14003df1d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003df24  nop     dword ptr [rax+rax+00h]
0x14003df29  test    r12, r12
0x14003df2c  jz      loc_14003DCE5
0x14003df32  mov     rsi, r12
0x14003df35  mov     r8d, 827h
0x14003df3b  jmp     loc_14003DE37
0x14003df40  mov     rax, [r14]
0x14003df43  mov     rdx, r14
0x14003df46  mov     r14, rdx
0x14003df49  cmp     rax, r15
0x14003df4c  jz      loc_14003DE47
0x14003df52  cmp     [rax-8], r8w
0x14003df57  jnz     short loc_14003DF7E
0x14003df59  lea     r12, [rax-8]
0x14003df5d  jmp     loc_14003DE47
0x14003df62  and     eax, 0FFFBFBFFh
0x14003df67  mov     [rdi+4], eax
0x14003df6a  jmp     loc_14003DE2E
0x14003df6f  mov     ecx, 3
0x14003df74  int     29h; Win8: RtlFailFast(ecx)
0x14003df76  mov     rax, [rax]
0x14003df79  jmp     loc_14003DCC8
0x14003df7e  mov     rax, [rax]
0x14003df81  jmp     short loc_14003DF46
0x14003df83  mov     eax, [rcx+98h]
0x14003df89  bt      eax, 0Dh
0x14003df8d  jnb     loc_14003DE60
0x14003df93  lock and dword ptr [rcx+98h], 0FFFFDFFFh
0x14003df9e  jmp     loc_14003DE60
0x14003dfa3  mov     rax, [rdi+40h]
0x14003dfa7  mov     dl, [rax+2900h]
0x14003dfad  test    dl, dl
0x14003dfaf  jz      loc_14003DBC3
0x14003dfb5  mov     rcx, [rdi+40h]; struct _VCB *
0x14003dfb9  mov     r8, rdi; struct _IRP_CONTEXT *
0x14003dfbc  mov     rdx, rbp; struct _IRP *
0x14003dfbf  call    ?RefsIoPerfCollectReadWriteData@@YAXPEAU_VCB@@PEAU_IRP@@PEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@@Z; RefsIoPerfCollectReadWriteData(_VCB *,_IRP *,_IRP_CONTEXT *,REFS_IO_CONTEXT *)
0x14003dfc4  jmp     loc_14003DBC3
0x14003dfc9  xor     edx, edx
0x14003dfcb  div     ecx
0x14003dfcd  mov     eax, edx
0x14003dfcf  jmp     loc_14003DC01
0x14003dfd4  mov     rcx, [rbp+8]; Mdl
0x14003dfd8  test    rcx, rcx
0x14003dfdb  jz      loc_14003DC24
0x14003dfe1  test    byte ptr [rcx+0Ah], 2
0x14003dfe5  jnz     loc_14003DC24
0x14003dfeb  test    sil, 1
0x14003dfef  jz      loc_14003DC24
0x14003dff5  call    cs:__imp_IoFreeMdl
0x14003dffc  nop     dword ptr [rax+rax+00h]
0x14003e001  mov     [rbp+8], r13
0x14003e005  jmp     loc_14003DC24
0x14003e00a  xor     edx, edx
0x14003e00c  div     ecx
0x14003e00e  mov     eax, edx
0x14003e010  jmp     loc_14003DF10
0x14003e015  mov     rax, [rcx]
0x14003e018  xor     edx, edx; Tag
0x14003e01a  mov     [rdi+258h], rax
0x14003e021  call    cs:__imp_ExFreePoolWithTag
0x14003e028  nop     dword ptr [rax+rax+00h]
0x14003e02d  jmp     loc_14003DCE5
0x14003e032  mov     rcx, [rdi+90h]; SubjectContext
0x14003e039  call    cs:__imp_SeReleaseSubjectContext
0x14003e040  nop     dword ptr [rax+rax+00h]
0x14003e045  mov     rcx, [rdi+90h]; P
0x14003e04c  xor     edx, edx; Tag
0x14003e04e  call    cs:__imp_ExFreePoolWithTag
0x14003e055  nop     dword ptr [rax+rax+00h]
0x14003e05a  jmp     loc_14003DD83
0x14003e05f  xor     edx, edx; Tag
0x14003e061  call    cs:__imp_ExFreePoolWithTag
0x14003e068  nop     dword ptr [rax+rax+00h]
0x14003e06d  mov     [rdi+2C8h], r13
0x14003e074  jmp     loc_14003DDCE
0x14003e079  xor     edx, edx
0x14003e07b  div     ecx
0x14003e07d  mov     eax, edx
0x14003e07f  jmp     loc_14003DC6E
```
