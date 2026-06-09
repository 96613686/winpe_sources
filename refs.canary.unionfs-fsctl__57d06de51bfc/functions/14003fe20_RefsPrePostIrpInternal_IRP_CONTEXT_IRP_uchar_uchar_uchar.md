# RefsPrePostIrpInternal(_IRP_CONTEXT *,_IRP *,uchar,uchar,uchar)

- ea: `0x14003fe20`
- end: `0x1400403fd`
- name: `?RefsPrePostIrpInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EEE@Z`
- size: `1501`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _IRP *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003e750`
- `0x14003fbe0`
- `0x1400b0470`
- `0x140106600`
- `0x140106660`
- `0x1402a42d0`
- `0x1402a5700`
- `0x1402e3ca8`

## callees

- `0x14003fe20`
- `0x140040410`
- `0x1400409a0`
- `0x140081670`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1402e2ea4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140040065`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400400a4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140040065`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400400a4`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004007d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400400bc`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004007d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400400bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ff9c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004028d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ff9c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004028d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004033f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004033f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400401db`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400401db`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400401ea`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400401ea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004022a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004022a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140040236`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140040236`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040054`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004031b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040354`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040367`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040054`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004031b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040354`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040367`

## pseudocode

```c
__int64 __fastcall RefsPrePostIrpInternal(
        PSECURITY_SUBJECT_CONTEXT *a1,
        struct _SECURITY_SUBJECT_CONTEXT *a2,
        char a3,
        char a4,
        unsigned __int8 a5)
{
  struct _IRP_CONTEXT *v9; // r14
  struct _IRP_CONTEXT *v10; // rax
  PSECURITY_SUBJECT_CONTEXT *v11; // rbp
  PSECURITY_SUBJECT_CONTEXT *j; // rcx
  int v13; // ecx
  unsigned __int64 v14; // rax
  _QWORD **v15; // rdi
  _QWORD *v16; // rcx
  bool v17; // zf
  int v18; // eax
  PSECURITY_SUBJECT_CONTEXT v19; // rcx
  unsigned int v20; // eax
  struct _NPAGED_LOOKASIDE_LIST *v21; // r9
  NTSTATUS v22; // edi
  struct _IRP_CONTEXT *v23; // rcx
  struct _IO_STACK_LOCATION *ProcessAuditId; // r9
  unsigned int v25; // r8d
  _QWORD *v27; // rax
  PIRP v28; // rax
  IRP *v29; // rcx
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  unsigned int v32; // r8d
  PSECURITY_SUBJECT_CONTEXT *v33; // r13
  struct _IRP_CONTEXT **v34; // r12
  struct _IRP_CONTEXT *i; // rax
  PSECURITY_SUBJECT_CONTEXT v36; // rcx
  struct _FAST_MUTEX *PrimaryToken; // rdi
  struct _IRP_CONTEXT *v38; // rcx
  struct _IRP_CONTEXT **v39; // rax
  unsigned int v40; // eax
  DWORD LowPart; // eax
  unsigned int v42; // r8d
  unsigned int Options; // r9d
  unsigned int v44; // r8d

  if ( a1[3] )
    RefsCleanupFailedTransaction((struct _IRP_CONTEXT *)a1, 1u);
  if ( !a4 && ((_DWORD)a1[1] & 0x100000) != 0 )
  {
    TopLevelIrp = IoGetTopLevelIrp();
    MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
    *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
    *(_QWORD *)&TopLevelIrp->Flags = 0;
    IoSetTopLevelIrp(MdlAddress);
    a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
  }
  *((_DWORD *)a1 + 1) |= 0x400u;
  RefsReleaseAllResources((struct _IRP_CONTEXT *)a1);
  v9 = (struct _IRP_CONTEXT *)(a1 + 80);
  v10 = (struct _IRP_CONTEXT *)a1[80];
  if ( v10 != (struct _IRP_CONTEXT *)(a1 + 80) )
  {
    v11 = 0;
    while ( v10 != v9 )
    {
      if ( *((_WORD *)v10 - 4) == 2087 )
      {
        v11 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v10 - 8);
        break;
      }
      v10 = *(struct _IRP_CONTEXT **)v10;
    }
    if ( v11 )
    {
      while ( 1 )
      {
        v33 = 0;
        v34 = (struct _IRP_CONTEXT **)(v11 + 1);
        if ( *(struct _IRP_CONTEXT **)v9 != v9 )
        {
          for ( i = *v34; ; i = *(struct _IRP_CONTEXT **)i )
          {
            v34 = (struct _IRP_CONTEXT **)(v11 + 1);
            if ( i == v9 )
              break;
            if ( *((_WORD *)i - 4) == 2087 )
            {
              v33 = (PSECURITY_SUBJECT_CONTEXT *)((char *)i - 8);
              break;
            }
          }
        }
        v36 = v11[6];
        if ( v36 )
        {
          if ( ((__int64)v36[4].ProcessAuditId & 0x2000) != 0 )
            _InterlockedAnd((volatile signed __int32 *)&v36[4].ProcessAuditId, 0xFFFFDFFF);
          PrimaryToken = (struct _FAST_MUTEX *)v11[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(PrimaryToken);
          _InterlockedIncrement((volatile signed __int32 *)&v11[6][5].ImpersonationLevel + 1);
          v11[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v11[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v11[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v38 = *v34;
        if ( *((struct _IRP_CONTEXT ***)*v34 + 1) != v34
          || (v39 = (struct _IRP_CONTEXT **)v11[2], *v39 != (struct _IRP_CONTEXT *)v34) )
        {
LABEL_74:
          __fastfail(3u);
        }
        *v39 = v38;
        *((_QWORD *)v38 + 1) = v39;
        if ( v11 != a1 + 91 )
        {
          v40 = *((_DWORD *)v11 - 2);
          if ( v40 >= RefsNumberProcessors )
            v40 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v40], v11 - 1);
        }
        if ( !v33 )
          break;
        v11 = v33;
      }
    }
  }
  for ( j = (PSECURITY_SUBJECT_CONTEXT *)a1[75]; j; j = (PSECURITY_SUBJECT_CONTEXT *)a1[75] )
  {
    a1[75] = *j;
    ExFreePoolWithTag(j, 0);
  }
  v13 = *((_DWORD *)a1 + 1);
  if ( (v13 & 0x400) != 0 || (v14 = (unsigned __int64)a1[1], (v14 & 0x10000) != 0) )
  {
    if ( (v13 & 0x40000) != 0 )
    {
      *((_DWORD *)a1 + 1) = v13 & 0xFFFBFBFF;
    }
    else
    {
      *((_DWORD *)a1 + 1) = v13 & 0xF779C0CD;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFFFFBFFuLL);
    }
    *((_DWORD *)a1 + 4) = 0;
  }
  else
  {
    if ( (v14 & 0x20000000000LL) != 0 )
    {
      *((_DWORD *)a1 + 59) &= ~1u;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)(v14 & 0xFFFFFDFFFFFFFFFFuLL);
    }
    if ( a1[42] )
    {
      *((_DWORD *)a1 + 81) &= ~1u;
      a1[42] = 0;
    }
    v15 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v16 = *v15;
      if ( *v15 == v15 )
        break;
      if ( (_QWORD **)v16[1] != v15 )
        goto LABEL_74;
      v27 = (_QWORD *)*v16;
      if ( *(_QWORD **)(*v16 + 8LL) != v16 )
        goto LABEL_74;
      *v15 = v27;
      v27[1] = v15;
      ExFreePoolWithTag(v16 - 12, 0);
    }
    a1[44] = 0;
    a1[58] = 0;
    v17 = ((_BYTE)a1[1] & 0x20) == 0;
    *((_DWORD *)a1 + 148) = 0;
    if ( !v17 )
    {
      SeReleaseSubjectContext(a1[18]);
      ExFreePoolWithTag(a1[18], 0);
    }
    v18 = *((_DWORD *)a1 + 2);
    a1[18] = 0;
    if ( (*(_QWORD *)&v18 & 0x100000LL) != 0 )
    {
      v28 = IoGetTopLevelIrp();
      v29 = (IRP *)v28->MdlAddress;
      *(_DWORD *)(&v28->Size + 1) = 0;
      *(_QWORD *)&v28->Flags = 0;
      IoSetTopLevelIrp(v29);
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
    }
    v19 = a1[89];
    if ( v19 )
    {
      ExFreePoolWithTag(v19, 0);
      a1[89] = 0;
    }
    if ( ((_DWORD)a1[1] & 0x80000) != 0 )
    {
      v20 = *((_DWORD *)a1 - 2);
      if ( *((_WORD *)a1 + 1) == 1664 )
      {
        v21 = RefsIrpAndIoContextLookasideList;
        if ( v20 < RefsNumberProcessors )
          goto LABEL_28;
      }
      else
      {
        v21 = RefsIrpContextLookasideList;
        if ( v20 < RefsNumberProcessors )
        {
LABEL_28:
          ExFreeToNPagedLookasideList(&v21[(unsigned __int64)v20], a1 - 1);
          goto LABEL_29;
        }
      }
      v20 %= RefsNumberProcessors;
      goto LABEL_28;
    }
  }
LABEL_29:
  a1[9] = a2;
  v22 = 0;
  if ( a2 && LOWORD(a2->ClientToken) == 6 )
  {
    v23 = (struct _IRP_CONTEXT *)*((unsigned __int8 *)a1 + 40);
    ProcessAuditId = (struct _IO_STACK_LOCATION *)a2[5].ProcessAuditId;
    if ( (unsigned __int8)((_BYTE)v23 - 3) > 1u )
    {
      switch ( (_BYTE)v23 )
      {
        case 0xC:
          if ( *((_BYTE *)a1 + 41) == 1 )
          {
            v22 = RefsLockUserBuffer(v23, (struct _IRP *)a2, IoWriteAccess, ProcessAuditId->Parameters.Read.Length);
            if ( v22 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  13,
                  WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                  (unsigned int)v22);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x1F1u);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v32);
              __debugbreak();
            }
          }
          break;
        case 0xD:
          if ( !*((_BYTE *)a1 + 41) )
          {
            LowPart = ProcessAuditId->Parameters.Read.ByteOffset.LowPart;
            if ( LowPart == 590011 || LowPart == 589939 )
            {
              v22 = RefsLockUserBuffer(v23, (struct _IRP *)a2, IoWriteAccess, ProcessAuditId->Parameters.Read.Length);
              if ( v22 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    14,
                    WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                    (unsigned int)v22);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x202u);
                RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v42);
                __debugbreak();
              }
            }
          }
          break;
        case 0x14:
          Options = ProcessAuditId->Parameters.Create.Options;
          if ( Options )
          {
            v22 = RefsLockUserBuffer(v23, (struct _IRP *)a2, IoWriteAccess, Options);
            if ( v22 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                  (unsigned int)v22);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x211u);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v44);
              __debugbreak();
            }
          }
          break;
      }
    }
    else
    {
      *((_BYTE *)a1 + 41) &= ~1u;
      if ( (*((_BYTE *)a1 + 41) & 2) == 0 )
      {
        if ( a5 )
        {
          v22 = RefsLockUserBuffer(
                  v23,
                  (struct _IRP *)a2,
                  (enum _LOCK_OPERATION)((_BYTE)v23 == 3),
                  ProcessAuditId->Parameters.Read.Length);
          if ( v22 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                12,
                WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                (unsigned int)v22);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x1E0u);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v25);
            __debugbreak();
          }
        }
      }
    }
    if ( a3 )
      *((_BYTE *)a2[5].ProcessAuditId + 3) |= 1u;
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x14003fe20  mov     [rsp+arg_10], rbx
0x14003fe25  push    rsi
0x14003fe26  push    rdi
0x14003fe27  push    r12
0x14003fe29  push    r14
0x14003fe2b  push    r15
0x14003fe2d  sub     rsp, 20h
0x14003fe31  cmp     qword ptr [rcx+18h], 0
0x14003fe36  movzx   edi, r9b
0x14003fe3a  movzx   r15d, r8b
0x14003fe3e  mov     rsi, rdx
0x14003fe41  mov     rbx, rcx
0x14003fe44  jnz     loc_1400402F8
0x14003fe4a  xor     r12d, r12d
0x14003fe4d  test    dil, dil
0x14003fe50  jz      loc_140040096
0x14003fe56  or      dword ptr [rbx+4], 400h
0x14003fe5d  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14003fe60  mov     [rsp+48h+arg_0], rbp
0x14003fe65  mov     [rsp+48h+arg_8], r13
0x14003fe6a  call    ?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseAllResources(_IRP_CONTEXT *)
0x14003fe6f  lea     r14, [rbx+280h]
0x14003fe76  mov     rax, [r14]
0x14003fe79  cmp     rax, r14
0x14003fe7c  jz      short loc_14003FEA4
0x14003fe7e  mov     rbp, r12
0x14003fe81  mov     r8d, 827h
0x14003fe87  cmp     rax, r14
0x14003fe8a  jz      short loc_14003FE9B
0x14003fe8c  cmp     [rax-8], r8w
0x14003fe91  jnz     loc_1400402C1
0x14003fe97  lea     rbp, [rax-8]
0x14003fe9b  test    rbp, rbp
0x14003fe9e  jnz     loc_140040190
0x14003fea4  mov     rcx, [rbx+258h]; P
0x14003feab  test    rcx, rcx
0x14003feae  jnz     loc_14004030F
0x14003feb4  mov     ecx, [rbx+4]
0x14003feb7  bt      ecx, 0Ah
0x14003febb  jb      loc_1400400D5
0x14003fec1  mov     rax, [rbx+8]
0x14003fec5  bt      rax, 10h
0x14003feca  jb      loc_1400400D5
0x14003fed0  bt      rax, 29h ; ')'
0x14003fed5  jnb     short loc_14003FEEF
0x14003fed7  and     dword ptr [rbx+0ECh], 0FFFFFFFEh
0x14003fede  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x14003fee8  and     rax, rcx
0x14003feeb  mov     [rbx+8], rax
0x14003feef  cmp     qword ptr [rbx+150h], 0
0x14003fef7  jz      short loc_14003FF07
0x14003fef9  and     dword ptr [rbx+144h], 0FFFFFFFEh
0x14003ff00  mov     [rbx+150h], r12
0x14003ff07  lea     rdi, [rbx+240h]
0x14003ff0e  mov     rcx, [rdi]
0x14003ff11  cmp     rcx, rdi
0x14003ff14  jnz     loc_140040030
0x14003ff1a  mov     [rbx+160h], r12
0x14003ff21  mov     [rbx+1D0h], r12
0x14003ff28  test    byte ptr [rbx+8], 20h
0x14003ff2c  mov     [rbx+250h], r12d
0x14003ff33  jnz     loc_140040338
0x14003ff39  mov     eax, [rbx+8]
0x14003ff3c  mov     [rbx+90h], r12
0x14003ff43  bt      rax, 14h
0x14003ff48  jb      loc_140040065
0x14003ff4e  mov     rcx, [rbx+2C8h]; P
0x14003ff55  test    rcx, rcx
0x14003ff58  jnz     loc_140040365
0x14003ff5e  mov     eax, [rbx+8]
0x14003ff61  bt      rax, 13h
0x14003ff66  jnb     short loc_14003FFA8
0x14003ff68  mov     eax, [rbx-8]
0x14003ff6b  mov     ecx, 680h
0x14003ff70  cmp     [rbx+2], cx
0x14003ff74  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14003ff7a  jz      loc_1400400F9
0x14003ff80  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x14003ff87  cmp     eax, ecx
0x14003ff89  jnb     loc_140040108
0x14003ff8f  mov     ecx, eax
0x14003ff91  lea     rdx, [rbx-8]; Entry
0x14003ff95  shl     rcx, 7
0x14003ff99  add     rcx, r9; Lookaside
0x14003ff9c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003ffa3  nop     dword ptr [rax+rax+00h]
0x14003ffa8  mov     [rbx+48h], rsi
0x14003ffac  mov     edi, r12d
0x14003ffaf  test    rsi, rsi
0x14003ffb2  jz      short loc_140040011
0x14003ffb4  cmp     word ptr [rsi], 6
0x14003ffb8  jnz     short loc_140040011
0x14003ffba  movzx   ecx, byte ptr [rbx+28h]; struct _IRP_CONTEXT *
0x14003ffbe  mov     r9, [rsi+0B8h]
0x14003ffc5  lea     eax, [rcx-3]
0x14003ffc8  cmp     al, 1
0x14003ffca  ja      loc_140040113
0x14003ffd0  and     byte ptr [rbx+29h], 0FEh
0x14003ffd4  test    byte ptr [rbx+29h], 2
0x14003ffd8  jnz     short loc_140040001
0x14003ffda  cmp     [rsp+48h+arg_20], 0
0x14003ffdf  jz      short loc_140040001
0x14003ffe1  mov     r9d, [r9+8]; unsigned int
0x14003ffe5  cmp     cl, 3
0x14003ffe8  mov     r8d, r12d
0x14003ffeb  mov     rdx, rsi; struct _IRP *
0x14003ffee  setz    r8b; enum _LOCK_OPERATION
0x14003fff2  call    ?RefsLockUserBuffer@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@W4_LOCK_OPERATION@@K@Z; RefsLockUserBuffer(_IRP_CONTEXT *,_IRP *,_LOCK_OPERATION,ulong)
0x14003fff7  mov     edi, eax
0x14003fff9  test    eax, eax
0x14003fffb  js      loc_1400403B1
0x140040001  test    r15b, r15b
0x140040004  jz      short loc_140040011
0x140040006  mov     rax, [rsi+0B8h]
0x14004000d  or      byte ptr [rax+3], 1
0x140040011  mov     r13, [rsp+48h+arg_8]
0x140040016  mov     eax, edi
0x140040018  mov     rbp, [rsp+48h+arg_0]
0x14004001d  mov     rbx, [rsp+48h+arg_10]
0x140040022  add     rsp, 20h
0x140040026  pop     r15
0x140040028  pop     r14
0x14004002a  pop     r12
0x14004002c  pop     rdi
0x14004002d  pop     rsi
0x14004002e  retn
0x140040030  cmp     [rcx+8], rdi
0x140040034  jnz     loc_1400402C9
0x14004003a  mov     rax, [rcx]
0x14004003d  cmp     [rax+8], rcx
0x140040041  jnz     loc_1400402C9
0x140040047  mov     [rdi], rax
0x14004004a  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14004004e  xor     edx, edx; Tag
0x140040050  mov     [rax+8], rdi
0x140040054  call    cs:__imp_ExFreePoolWithTag
0x14004005b  nop     dword ptr [rax+rax+00h]
0x140040060  jmp     loc_14003FF0E
0x140040065  call    cs:__imp_IoGetTopLevelIrp
0x14004006c  nop     dword ptr [rax+rax+00h]
0x140040071  mov     rcx, [rax+8]; Irp
0x140040075  mov     [rax+4], r12d
0x140040079  mov     [rax+10h], r12
0x14004007d  call    cs:__imp_IoSetTopLevelIrp
0x140040084  nop     dword ptr [rax+rax+00h]
0x140040089  and     qword ptr [rbx+8], 0FFFFFFFFFFEFFFFFh
0x140040091  jmp     loc_14003FF4E
0x140040096  mov     eax, [rbx+8]
0x140040099  bt      rax, 14h
0x14004009e  jnb     loc_14003FE56
0x1400400a4  call    cs:__imp_IoGetTopLevelIrp
0x1400400ab  nop     dword ptr [rax+rax+00h]
0x1400400b0  mov     rcx, [rax+8]; Irp
0x1400400b4  mov     [rax+4], r12d
0x1400400b8  mov     [rax+10h], r12
0x1400400bc  call    cs:__imp_IoSetTopLevelIrp
0x1400400c3  nop     dword ptr [rax+rax+00h]
0x1400400c8  and     qword ptr [rbx+8], 0FFFFFFFFFFEFFFFFh
0x1400400d0  jmp     loc_14003FE56
0x1400400d5  bt      ecx, 12h
0x1400400d9  jb      loc_1400402B3
0x1400400df  and     ecx, 0F779C0CDh
0x1400400e5  mov     [rbx+4], ecx
0x1400400e8  and     qword ptr [rbx+8], 0FFFFFFFFFFFFFBFFh
0x1400400f0  mov     [rbx+10h], r12d
0x1400400f4  jmp     loc_14003FFA8
0x1400400f9  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x140040100  cmp     eax, ecx
0x140040102  jb      loc_14003FF8F
0x140040108  xor     edx, edx
0x14004010a  div     ecx
0x14004010c  mov     eax, edx
0x14004010e  jmp     loc_14003FF8F
0x140040113  cmp     cl, 0Ch
0x140040116  jnz     loc_14004037F
0x14004011c  cmp     byte ptr [rbx+29h], 1
0x140040120  jnz     loc_140040001
0x140040126  mov     r9d, [r9+8]; unsigned int
0x14004012a  mov     r8d, 1; enum _LOCK_OPERATION
0x140040130  mov     rdx, rsi; struct _IRP *
0x140040133  call    ?RefsLockUserBuffer@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@W4_LOCK_OPERATION@@K@Z; RefsLockUserBuffer(_IRP_CONTEXT *,_IRP *,_LOCK_OPERATION,ulong)
0x140040138  mov     edi, eax
0x14004013a  test    eax, eax
0x14004013c  jns     loc_140040001
0x140040142  mov     rcx, cs:WPP_GLOBAL_Control
0x140040149  lea     rax, WPP_GLOBAL_Control
0x140040150  cmp     rcx, rax
0x140040153  jz      loc_1401F213A
0x140040159  test    dword ptr [rcx+2Ch], 100h
0x140040160  jz      loc_1401F213A
0x140040166  cmp     byte ptr [rcx+29h], 4
0x14004016a  jb      loc_1401F213A
0x140040170  mov     rcx, [rcx+18h]
0x140040174  lea     r8, WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids
0x14004017b  mov     edx, 0Dh
0x140040180  mov     r9d, edi
0x140040183  call    WPP_SF_d
0x140040188  nop
0x140040189  jmp     loc_1401F213A
0x140040190  mov     r13, r12
0x140040193  lea     r12, [rbp+8]
0x140040197  cmp     [r14], r14
0x14004019a  jz      short loc_1400401BA
0x14004019c  mov     rax, [r12]
0x1400401a0  mov     rdx, r12
0x1400401a3  mov     r12, rdx
0x1400401a6  cmp     rax, r14
0x1400401a9  jz      short loc_1400401BA
0x1400401ab  cmp     [rax-8], r8w
0x1400401b0  jnz     loc_1400402F0
0x1400401b6  lea     r13, [rax-8]
0x1400401ba  mov     rcx, [rbp+30h]
0x1400401be  test    rcx, rcx
0x1400401c1  jz      short loc_140040242
0x1400401c3  test    dword ptr [rcx+98h], 2000h
0x1400401cd  jnz     loc_1400402D0
0x1400401d3  mov     rax, [rbp+30h]
0x1400401d7  mov     rdi, [rax+30h]
0x1400401db  call    cs:__imp_KeEnterGuardedRegion
0x1400401e2  nop     dword ptr [rax+rax+00h]
0x1400401e7  mov     rcx, rdi; FastMutex
0x1400401ea  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400401f1  nop     dword ptr [rax+rax+00h]
0x1400401f6  mov     rax, [rbp+30h]
0x1400401fa  lock inc dword ptr [rax+0ACh]
0x140040201  mov     rax, [rbp+30h]
0x140040205  mov     qword ptr [rax+118h], 0
0x140040210  mov     rcx, [rbp+30h]
0x140040214  mov     eax, [rcx+0ACh]
0x14004021a  inc     eax
0x14004021c  mov     [rcx+0ACh], eax
0x140040222  mov     rcx, [rbp+30h]
0x140040226  mov     rcx, [rcx+30h]; FastMutex
0x14004022a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140040231  nop     dword ptr [rax+rax+00h]
0x140040236  call    cs:__imp_KeLeaveGuardedRegion
0x14004023d  nop     dword ptr [rax+rax+00h]
0x140040242  mov     rcx, [r12]
0x140040246  cmp     [rcx+8], r12
0x14004024a  jnz     short loc_1400402C9
0x14004024c  mov     rax, [rbp+10h]
0x140040250  cmp     [rax], r12
0x140040253  jnz     short loc_1400402C9
0x140040255  mov     [rax], rcx
0x140040258  mov     [rcx+8], rax
0x14004025c  lea     rax, [rbx+2D8h]
0x140040263  cmp     rbp, rax
0x140040266  jz      short loc_140040299
0x140040268  mov     eax, [rbp-8]
0x14004026b  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140040271  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x140040278  cmp     eax, ecx
0x14004027a  jnb     loc_140040304
0x140040280  mov     ecx, eax
0x140040282  lea     rdx, [rbp-8]; Entry
0x140040286  shl     rcx, 7
0x14004028a  add     rcx, r8; Lookaside
0x14004028d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140040294  nop     dword ptr [rax+rax+00h]
0x140040299  xor     r12d, r12d
0x14004029c  test    r13, r13
0x14004029f  jz      loc_14003FEA4
0x1400402a5  mov     rbp, r13
0x1400402a8  mov     r8d, 827h
0x1400402ae  jmp     loc_140040190
0x1400402b3  and     ecx, 0FFFBFBFFh
0x1400402b9  mov     [rbx+4], ecx
0x1400402bc  jmp     loc_1400400F0
0x1400402c1  mov     rax, [rax]
0x1400402c4  jmp     loc_14003FE87
0x1400402c9  mov     ecx, 3; struct _IRP_CONTEXT *
0x1400402ce  int     29h; Win8: RtlFailFast(ecx)
0x1400402d0  mov     eax, [rcx+98h]
0x1400402d6  bt      eax, 0Dh
0x1400402da  jnb     loc_1400401D3
0x1400402e0  lock and dword ptr [rcx+98h], 0FFFFDFFFh
0x1400402eb  jmp     loc_1400401D3
0x1400402f0  mov     rax, [rax]
0x1400402f3  jmp     loc_1400401A3
0x1400402f8  mov     dl, 1; unsigned __int8
0x1400402fa  call    ?RefsCleanupFailedTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCleanupFailedTransaction(_IRP_CONTEXT *,uchar)
0x1400402ff  jmp     loc_14003FE4A
0x140040304  xor     edx, edx
0x140040306  div     ecx
0x140040308  mov     eax, edx
0x14004030a  jmp     loc_140040280
0x14004030f  mov     rax, [rcx]
0x140040312  xor     edx, edx; Tag
0x140040314  mov     [rbx+258h], rax
0x14004031b  call    cs:__imp_ExFreePoolWithTag
0x140040322  nop     dword ptr [rax+rax+00h]
0x140040327  mov     rcx, [rbx+258h]
0x14004032e  test    rcx, rcx
0x140040331  jnz     short loc_14004030F
0x140040333  jmp     loc_14003FEB4
0x140040338  mov     rcx, [rbx+90h]; SubjectContext
0x14004033f  call    cs:__imp_SeReleaseSubjectContext
0x140040346  nop     dword ptr [rax+rax+00h]
0x14004034b  mov     rcx, [rbx+90h]; P
0x140040352  xor     edx, edx; Tag
  ... truncated ...
```
