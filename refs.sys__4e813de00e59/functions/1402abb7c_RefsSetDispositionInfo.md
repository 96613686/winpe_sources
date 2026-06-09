# RefsSetDispositionInfo

- ea: `0x1402abb7c`
- end: `0x1402ac403`
- name: `RefsSetDispositionInfo`
- size: `2183`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14031cca8`

## callees

- `0x1400862c0`
- `0x1400d0fd8`
- `0x14028da28`
- `0x1402abb7c`
- `0x14030b700`
- `0x14031f9c0`

## import_xrefs

- `ntoskrnl!MmFlushImageSection` at `0x1402abf71`
- `ntoskrnl!MmFlushImageSection` at `0x1402abfa5`
- `ntoskrnl!MmFlushImageSection` at `0x1402ac1e1`
- `ntoskrnl!MmFlushImageSection` at `0x1402abf71`
- `ntoskrnl!MmFlushImageSection` at `0x1402abfa5`
- `ntoskrnl!MmFlushImageSection` at `0x1402ac1e1`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1402ac2dd`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1402ac2dd`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402abe73`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402abe73`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402abe7f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402abe7f`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x1402ac098`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x1402ac098`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x1402ac37f`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x1402ac37f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402abe58`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402abe58`

## pseudocode

```c
NTSTATUS __fastcall RefsSetDispositionInfo(
        struct _IRP_CONTEXT *a1,
        __int64 a2,
        struct _IRP *a3,
        __int64 a4,
        volatile signed __int32 *a5)
{
  volatile signed __int32 *v5; // rsi
  __int64 v9; // rbx
  _DWORD *v10; // r12
  NTSTATUS v11; // ebx
  unsigned int v12; // r9d
  NTSTATUS result; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IRP *MasterIrp; // rbp
  int v16; // eax
  unsigned int v17; // eax
  bool v18; // zf
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  bool v21; // r13
  volatile signed __int32 *v22; // rax
  volatile signed __int32 *v23; // rbx
  BOOLEAN v24; // al
  int v25; // eax
  __int64 v26; // rdx
  unsigned __int8 IsLinkDeleteable; // al
  __int64 v28; // rcx
  _BYTE *v29; // rbx
  HANDLE v30; // rax
  int v31; // eax
  unsigned int v32; // [rsp+70h] [rbp-58h] BYREF
  __int64 v33; // [rsp+78h] [rbp-50h]
  HANDLE Handle; // [rsp+80h] [rbp-48h]
  unsigned __int8 GenerateOnClose; // [rsp+E0h] [rbp+18h] BYREF

  v5 = a5;
  GenerateOnClose = 0;
  v9 = *((_QWORD *)a5 + 9);
  v10 = a5 + 1;
  v33 = v9;
  if ( !v9 && (*v10 & 2) != 0 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5374;
LABEL_9:
    RefsStatusDebug(v11, 0, "FileInfo.c", v12);
    return v11;
  }
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a3->AssociatedIrp.MasterIrp;
  if ( CurrentStackLocation->Parameters.Create.Options == 13 )
  {
    LOBYTE(MasterIrp) = (LOBYTE(MasterIrp->Type) != 0) + 4;
  }
  else
  {
    LODWORD(MasterIrp) = *(_DWORD *)&MasterIrp->Type;
    if ( ((unsigned int)MasterIrp & 0xFFFFFFE0) != 0 )
    {
      v11 = -1073741637;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return v11;
      v12 = 5406;
      goto LABEL_9;
    }
    if ( ((unsigned __int8)MasterIrp & 8) != 0 )
    {
      if ( ((unsigned __int8)MasterIrp & 1) != 0 )
      {
        if ( (*v10 & 0x40000) == 0 )
        {
          v11 = -1073741637;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              74,
              WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
              3221225659LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            return v11;
          v12 = 5416;
          goto LABEL_9;
        }
        if ( (*v10 & 2) != 0 )
        {
          v16 = *((_DWORD *)a5 + 2);
          if ( ((unsigned __int8)MasterIrp & 2) != 0 )
            v17 = v16 | 8;
          else
            v17 = v16 & 0xFFFFFFF7;
          *((_DWORD *)a5 + 2) = v17;
        }
      }
      else
      {
        *v10 &= ~0x40000u;
        *((_DWORD *)v5 + 2) &= ~8u;
      }
      return 0;
    }
  }
  if ( *((int *)a5 + 2) < 0 )
    LOBYTE(MasterIrp) = (unsigned __int8)MasterIrp & 0xF9 | 2;
  if ( ((unsigned __int8)MasterIrp & 1) == 0 )
  {
    if ( (*v10 & 2) != 0 )
    {
      v31 = *(_DWORD *)(v9 + 4);
      if ( (v31 & 1) != 0 )
      {
        if ( (v31 & 0x80u) != 0 )
          return -1073741738;
        *(_DWORD *)(v9 + 4) = v31 & 0xFFFFFFBE;
        *((_DWORD *)v5 + 2) &= ~4u;
        ++*(_DWORD *)(*(_QWORD *)(a4 + 136) + 176LL);
      }
    }
    else if ( (*(_DWORD *)(a4 + 152) & 2) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a4 + 152), 0xFFFFFFFD);
    }
    *(_BYTE *)(a2 + 73) = 0;
    return 0;
  }
  Handle = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 136) + 152LL) & 1) != 0 && (CurrentStackLocation->Flags & 0x40) == 0 )
  {
    if ( ((unsigned __int8)MasterIrp & 0x10) == 0 )
    {
      v11 = -1073741535;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225761LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return v11;
      v12 = 5461;
      goto LABEL_9;
    }
    if ( RefsEffectiveMode(a3, CurrentStackLocation) == 1 && (v5[22] & 0x310) == 0 )
    {
      v18 = (*((_BYTE *)a1 + 8) & 0x20) == 0;
      v32 = 0;
      LODWORD(a5) = 0;
      if ( v18 )
      {
        PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                            (POOL_TYPE)(PoolType | 0x10),
                                                            0x20u,
                                                            0x46466552u);
        *((_QWORD *)a1 + 18) = PoolWithTag;
        *((_QWORD *)a1 + 1) |= 0x20uLL;
        SeCaptureSubjectContext(PoolWithTag);
      }
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( !(unsigned __int8)RefsSeAccessCheck(
                               a1,
                               *(struct _FCB **)(a4 + 136),
                               *((struct _SECURITY_SUBJECT_CONTEXT **)a1 + 18),
                               0,
                               0,
                               0x100u,
                               0,
                               0,
                               FileObjectGenericMapping,
                               1,
                               &v32,
                               0,
                               (int *)&a5,
                               0) )
      {
        v11 = -1073741535;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            76,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225761LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v11;
        v12 = 5506;
        goto LABEL_9;
      }
    }
  }
  v21 = 0;
  if ( (v5[1] & 2) != 0 )
  {
    v22 = (volatile signed __int32 *)(*(_QWORD *)(a4 + 136) + 48LL);
    a5 = v22;
    v23 = *(volatile signed __int32 **)v22;
    while ( v23 != v22 )
    {
      _InterlockedAdd(v23 + 11, 1u);
      v24 = MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v23 + 16) + 8LL), MmFlushForDelete);
      v21 = v24 == 0;
      _InterlockedDecrement(v23 + 11);
      if ( !v24 )
        break;
      v23 = *(volatile signed __int32 **)v23;
      v22 = a5;
    }
    v9 = v33;
  }
  else
  {
    v21 = MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a4 + 248) + 8LL), MmFlushForDelete) == 0;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 136) + 8LL) & 0x100LL) != 0 )
  {
    v11 = -1073741535;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225761LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5541;
    goto LABEL_9;
  }
  if ( !Handle )
    goto LABEL_81;
  if ( (*v10 & 0x8000) != 0 )
  {
    v11 = -1073741816;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225480LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5560;
    goto LABEL_9;
  }
  result = ObQueryObjectAuditingByHandle(Handle, &GenerateOnClose);
  if ( result >= 0 )
  {
LABEL_81:
    if ( (*v10 & 2) == 0 )
    {
      v29 = (_BYTE *)a2;
      if ( (*(_DWORD *)(a4 + 152) & 2) == 0 )
        _InterlockedOr((volatile signed __int32 *)(a4 + 152), 2u);
      goto LABEL_124;
    }
    v25 = *(_DWORD *)(v9 + 4);
    LOBYTE(a5) = 0;
    if ( (v25 & 1) != 0 )
      goto LABEL_127;
    if ( (v25 & 2) != 0 )
      goto LABEL_127;
    v26 = *(_QWORD *)(a4 + 136);
    if ( (*(_BYTE *)(v26 + 8) & 1) != 0 )
      goto LABEL_127;
    IsLinkDeleteable = RefsIsLinkDeleteable(a1, (struct _FCB *)v26, (unsigned __int8 *)&a5);
    if ( !v21 )
      goto LABEL_109;
    if ( ((unsigned __int8)MasterIrp & 4) != 0 )
    {
      v11 = -1073741535;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225761LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return v11;
      v12 = 5607;
      goto LABEL_9;
    }
    if ( (_BYTE)a5 )
    {
      if ( ((unsigned __int8)MasterIrp & 2) == 0 )
      {
        v11 = -1073741535;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            80,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225761LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v11;
        v12 = 5612;
        goto LABEL_9;
      }
      if ( IsLinkDeleteable )
      {
        if ( !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a4 + 248) + 8LL), MmFlushForWrite) )
        {
          v11 = -1073741535;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              81,
              WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
              3221225761LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            return v11;
          v12 = 5627;
          goto LABEL_9;
        }
LABEL_110:
        --*(_DWORD *)(*(_QWORD *)(a4 + 136) + 176LL);
        *(_DWORD *)(v33 + 4) |= 1u;
        if ( ((unsigned __int8)MasterIrp & 2) != 0 )
          *((_DWORD *)v5 + 2) |= 4u;
        else
          *((_DWORD *)v5 + 2) &= ~4u;
        v28 = *(_QWORD *)(*(_QWORD *)(a4 + 136) + 88LL);
        if ( !*(_QWORD *)(v28 + 248) )
        {
          v29 = (_BYTE *)a2;
          if ( *(_QWORD *)(v28 + 256) )
            FsRtlNotifyFilterChangeDirectory(
              *(PNOTIFY_SYNC *)(*(_QWORD *)(a4 + 144) + 864LL),
              (PLIST_ENTRY)(*(_QWORD *)(a4 + 144) + 848LL),
              *(PVOID *)(a2 + 24),
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              0);
          goto LABEL_124;
        }
LABEL_127:
        v29 = (_BYTE *)a2;
LABEL_124:
        v30 = Handle;
        v29[73] = 1;
        if ( v30 && GenerateOnClose )
          SeDeleteObjectAuditAlarm(v29, v30);
        return 0;
      }
    }
    else
    {
LABEL_109:
      if ( IsLinkDeleteable )
        goto LABEL_110;
    }
    v11 = -1073741567;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225729LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5676;
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x1402abb7c  mov     rax, rsp
0x1402abb7f  mov     [rax+20h], rbx
0x1402abb83  mov     [rax+10h], rdx
0x1402abb87  mov     [rax+8], rcx
0x1402abb8b  push    rbp
0x1402abb8c  push    rsi
0x1402abb8d  push    rdi
0x1402abb8e  push    r12
0x1402abb90  push    r13
0x1402abb92  push    r14
0x1402abb94  push    r15
0x1402abb96  sub     rsp, 90h
0x1402abb9d  mov     rsi, [rsp+0C8h+arg_20]
0x1402abba5  mov     r14, r9
0x1402abba8  mov     r13, rcx
0x1402abbab  mov     byte ptr [rax+18h], 0
0x1402abbaf  mov     r9, rdx
0x1402abbb2  mov     ecx, 2
0x1402abbb7  mov     rbx, [rsi+48h]
0x1402abbbb  lea     r12, [rsi+4]
0x1402abbbf  mov     [rsp+0C8h+var_50], rbx
0x1402abbc4  test    rbx, rbx
0x1402abbc7  jnz     short loc_1402ABC35
0x1402abbc9  mov     eax, [r12]
0x1402abbcd  test    cl, al
0x1402abbcf  jz      short loc_1402ABC35
0x1402abbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1402abbd8  lea     rax, WPP_GLOBAL_Control
0x1402abbdf  mov     ebx, 0C000000Dh
0x1402abbe4  cmp     rcx, rax
0x1402abbe7  jz      short loc_1402ABC0E
0x1402abbe9  bt      dword ptr [rcx+2Ch], 8
0x1402abbee  jnb     short loc_1402ABC0E
0x1402abbf0  cmp     byte ptr [rcx+29h], 4
0x1402abbf4  jb      short loc_1402ABC0E
0x1402abbf6  mov     rcx, [rcx+18h]
0x1402abbfa  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402abc01  mov     edx, 48h ; 'H'
0x1402abc06  mov     r9d, ebx
0x1402abc09  call    WPP_SF_d
0x1402abc0e  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402abc14  test    cl, cl
0x1402abc16  jz      short loc_1402ABC2E
0x1402abc18  mov     r9d, 14FEh; unsigned int
0x1402abc1e  lea     r8, aFileinfoC; "FileInfo.c"
0x1402abc25  xor     edx, edx; struct _IRP_CONTEXT *
0x1402abc27  mov     ecx, ebx; Status
0x1402abc29  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402abc2e  mov     eax, ebx
0x1402abc30  jmp     loc_1402AC3E7
0x1402abc35  mov     rdx, [r8+0B8h]; struct _IO_STACK_LOCATION *
0x1402abc3c  mov     rbp, [r8+18h]
0x1402abc40  cmp     dword ptr [rdx+10h], 0Dh
0x1402abc44  jnz     loc_1402ABD06
0x1402abc4a  mov     al, [rbp+0]
0x1402abc4d  neg     al
0x1402abc4f  sbb     ebp, ebp
0x1402abc51  neg     ebp
0x1402abc53  add     ebp, 4
0x1402abc56  cmp     dword ptr [rsi+8], 0
0x1402abc5a  mov     r10d, 0FFFFFFFBh
0x1402abc60  jge     short loc_1402ABC67
0x1402abc62  and     ebp, r10d
0x1402abc65  or      ebp, ecx
0x1402abc67  mov     r15d, 1
0x1402abc6d  test    r15b, bpl
0x1402abc70  jz      loc_1402AC397
0x1402abc76  mov     rax, [rdx+20h]
0x1402abc7a  mov     edi, 100h
0x1402abc7f  mov     [rsp+0C8h+Handle], rax
0x1402abc87  mov     rax, [r14+88h]
0x1402abc8e  mov     ecx, [rax+98h]
0x1402abc94  test    r15b, cl
0x1402abc97  jz      loc_1402ABF3A
0x1402abc9d  test    byte ptr [rdx+2], 40h
0x1402abca1  jnz     loc_1402ABF3A
0x1402abca7  test    bpl, 10h
0x1402abcab  jnz     loc_1402ABE0A
0x1402abcb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1402abcb8  lea     rax, WPP_GLOBAL_Control
0x1402abcbf  mov     ebx, 0C0000121h
0x1402abcc4  cmp     rcx, rax
0x1402abcc7  jz      short loc_1402ABCED
0x1402abcc9  bt      dword ptr [rcx+2Ch], 8
0x1402abcce  jnb     short loc_1402ABCED
0x1402abcd0  cmp     byte ptr [rcx+29h], 4
0x1402abcd4  jb      short loc_1402ABCED
0x1402abcd6  mov     rcx, [rcx+18h]
0x1402abcda  lea     edx, [r15+4Ah]
0x1402abcde  mov     r9d, ebx
0x1402abce1  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402abce8  call    WPP_SF_d
0x1402abced  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402abcf3  test    al, al
0x1402abcf5  jz      loc_1402ABC2E
0x1402abcfb  mov     r9d, 1555h
0x1402abd01  jmp     loc_1402ABC1E
0x1402abd06  mov     ebp, [rbp+0]
0x1402abd09  test    ebp, 0FFFFFFE0h
0x1402abd0f  jz      short loc_1402ABD67
0x1402abd11  mov     rcx, cs:WPP_GLOBAL_Control
0x1402abd18  lea     rax, WPP_GLOBAL_Control
0x1402abd1f  mov     ebx, 0C00000BBh
0x1402abd24  cmp     rcx, rax
0x1402abd27  jz      short loc_1402ABD4E
0x1402abd29  bt      dword ptr [rcx+2Ch], 8
0x1402abd2e  jnb     short loc_1402ABD4E
0x1402abd30  cmp     byte ptr [rcx+29h], 4
0x1402abd34  jb      short loc_1402ABD4E
0x1402abd36  mov     rcx, [rcx+18h]
0x1402abd3a  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402abd41  mov     edx, 49h ; 'I'
0x1402abd46  mov     r9d, ebx
0x1402abd49  call    WPP_SF_d
0x1402abd4e  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402abd54  test    al, al
0x1402abd56  jz      loc_1402ABC2E
0x1402abd5c  mov     r9d, 151Eh
0x1402abd62  jmp     loc_1402ABC1E
0x1402abd67  test    bpl, 8
0x1402abd6b  jz      loc_1402ABC56
0x1402abd71  mov     r15d, 1
0x1402abd77  test    r15b, bpl
0x1402abd7a  jz      short loc_1402ABDFB
0x1402abd7c  mov     eax, [r12]
0x1402abd80  bt      eax, 12h
0x1402abd84  jb      short loc_1402ABDDB
0x1402abd86  mov     rcx, cs:WPP_GLOBAL_Control
0x1402abd8d  lea     rax, WPP_GLOBAL_Control
0x1402abd94  mov     ebx, 0C00000BBh
0x1402abd99  cmp     rcx, rax
0x1402abd9c  jz      short loc_1402ABDC2
0x1402abd9e  bt      dword ptr [rcx+2Ch], 8
0x1402abda3  jnb     short loc_1402ABDC2
0x1402abda5  cmp     byte ptr [rcx+29h], 4
0x1402abda9  jb      short loc_1402ABDC2
0x1402abdab  mov     rcx, [rcx+18h]
0x1402abdaf  lea     edx, [r15+49h]
0x1402abdb3  mov     r9d, ebx
0x1402abdb6  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402abdbd  call    WPP_SF_d
0x1402abdc2  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402abdc8  test    cl, cl
0x1402abdca  jz      loc_1402ABC2E
0x1402abdd0  mov     r9d, 1528h
0x1402abdd6  jmp     loc_1402ABC1E
0x1402abddb  test    cl, al
0x1402abddd  jz      loc_1402AC3E5
0x1402abde3  mov     eax, [rsi+8]
0x1402abde6  test    cl, bpl
0x1402abde9  jz      short loc_1402ABDF6
0x1402abdeb  or      eax, 8
0x1402abdee  mov     [rsi+8], eax
0x1402abdf1  jmp     loc_1402AC3E5
0x1402abdf6  and     eax, 0FFFFFFF7h
0x1402abdf9  jmp     short loc_1402ABDEE
0x1402abdfb  btr     dword ptr [r12], 12h
0x1402abe01  and     dword ptr [rsi+8], 0FFFFFFF7h
0x1402abe05  jmp     loc_1402AC3E5
0x1402abe0a  mov     rcx, r8; struct _IRP *
0x1402abe0d  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402abe12  cmp     al, r15b
0x1402abe15  jnz     loc_1402ABF3A
0x1402abe1b  mov     ecx, 310h
0x1402abe20  test    [rsi+58h], cx
0x1402abe24  jnz     loc_1402ABF3A
0x1402abe2a  test    byte ptr [r13+8], 20h
0x1402abe2f  mov     [rsp+0C8h+var_58], 0
0x1402abe37  mov     dword ptr [rsp+0C8h+arg_20], 0
0x1402abe42  jnz     short loc_1402ABE7F
0x1402abe44  mov     ecx, cs:PoolType
0x1402abe4a  mov     edx, 20h ; ' '; NumberOfBytes
0x1402abe4f  or      ecx, 10h; PoolType
0x1402abe52  mov     r8d, 46466552h; Tag
0x1402abe58  call    cs:__imp_ExAllocatePoolWithTag
0x1402abe5f  nop     dword ptr [rax+rax+00h]
0x1402abe64  mov     [r13+90h], rax
0x1402abe6b  mov     rcx, rax; SubjectContext
0x1402abe6e  or      qword ptr [r13+8], 20h
0x1402abe73  call    cs:__imp_SeCaptureSubjectContext
0x1402abe7a  nop     dword ptr [rax+rax+00h]
0x1402abe7f  call    cs:__imp_IoGetFileObjectGenericMapping
0x1402abe86  nop     dword ptr [rax+rax+00h]
0x1402abe8b  mov     r8, [r13+90h]; struct _SECURITY_SUBJECT_CONTEXT *
0x1402abe92  lea     rcx, [rsp+0C8h+arg_20]
0x1402abe9a  xor     edx, edx
0x1402abe9c  xor     r9d, r9d; unsigned __int8
0x1402abe9f  mov     [rsp+0C8h+var_60], rdx; struct _ACCESS_STATE *
0x1402abea4  mov     [rsp+0C8h+var_68], rcx; int *
0x1402abea9  lea     rcx, [rsp+0C8h+var_58]
0x1402abeae  mov     [rsp+0C8h+var_70], rdx; struct _ACCESS_REASONS *
0x1402abeb3  mov     [rsp+0C8h+FilterCallback], rcx; unsigned int *
0x1402abeb8  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402abebb  mov     byte ptr [rsp+0C8h+SubjectContext], r15b; char
0x1402abec0  mov     [rsp+0C8h+TraverseCallback], rax; struct _GENERIC_MAPPING *
0x1402abec5  mov     [rsp+0C8h+NotifyIrp], rdx; struct _PRIVILEGE_SET **
0x1402abeca  mov     [rsp+0C8h+CompletionFilter], edx; unsigned int
0x1402abece  mov     dword ptr [rsp+0C8h+IgnoreBuffer], edi; unsigned int
0x1402abed2  mov     [rsp+0C8h+WatchTree], dl; char
0x1402abed6  mov     rdx, [r14+88h]; struct _FCB *
0x1402abedd  call    ?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z; RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)
0x1402abee2  test    al, al
0x1402abee4  jnz     short loc_1402ABF3A
0x1402abee6  mov     rcx, cs:WPP_GLOBAL_Control
0x1402abeed  lea     rax, WPP_GLOBAL_Control
0x1402abef4  mov     ebx, 0C0000121h
0x1402abef9  cmp     rcx, rax
0x1402abefc  jz      short loc_1402ABF21
0x1402abefe  test    [rcx+2Ch], edi
0x1402abf01  jz      short loc_1402ABF21
0x1402abf03  cmp     byte ptr [rcx+29h], 4
0x1402abf07  jb      short loc_1402ABF21
0x1402abf09  mov     rcx, [rcx+18h]
0x1402abf0d  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402abf14  mov     edx, 4Ch ; 'L'
0x1402abf19  mov     r9d, ebx
0x1402abf1c  call    WPP_SF_d
0x1402abf21  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402abf27  test    al, al
0x1402abf29  jz      loc_1402ABC2E
0x1402abf2f  mov     r9d, 1582h
0x1402abf35  jmp     loc_1402ABC1E
0x1402abf3a  mov     eax, [rsi+4]
0x1402abf3d  xor     r13b, r13b
0x1402abf40  test    al, 2
0x1402abf42  jz      short loc_1402ABF98
0x1402abf44  mov     rax, [r14+88h]
0x1402abf4b  add     rax, 30h ; '0'
0x1402abf4f  mov     [rsp+0C8h+arg_20], rax
0x1402abf57  mov     rbx, [rax]
0x1402abf5a  cmp     rbx, rax
0x1402abf5d  jz      short loc_1402ABFBD
0x1402abf5f  lock add [rbx+2Ch], r15d
0x1402abf64  mov     rcx, [rbx+80h]
0x1402abf6b  xor     edx, edx; FlushType
0x1402abf6d  add     rcx, 8; SectionObjectPointer
0x1402abf71  call    cs:__imp_MmFlushImageSection
0x1402abf78  nop     dword ptr [rax+rax+00h]
0x1402abf7d  test    al, al
0x1402abf7f  setz    r13b
0x1402abf83  lock dec dword ptr [rbx+2Ch]
0x1402abf87  test    al, al
0x1402abf89  jz      short loc_1402ABFBD
0x1402abf8b  mov     rbx, [rbx]
0x1402abf8e  mov     rax, [rsp+0C8h+arg_20]
0x1402abf96  jmp     short loc_1402ABF5A
0x1402abf98  mov     rcx, [r14+0F8h]
0x1402abf9f  xor     edx, edx; FlushType
0x1402abfa1  add     rcx, 8; SectionObjectPointer
0x1402abfa5  call    cs:__imp_MmFlushImageSection
0x1402abfac  nop     dword ptr [rax+rax+00h]
0x1402abfb1  test    al, al
0x1402abfb3  movzx   r13d, r13b
0x1402abfb7  cmovz   r13d, r15d
0x1402abfbb  jmp     short loc_1402ABFC2
0x1402abfbd  mov     rbx, [rsp+0C8h+var_50]
0x1402abfc2  mov     rax, [r14+88h]
0x1402abfc9  mov     ecx, [rax+8]
0x1402abfcc  test    rdi, rcx
0x1402abfcf  jz      short loc_1402AC025
0x1402abfd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1402abfd8  lea     rax, WPP_GLOBAL_Control
0x1402abfdf  mov     ebx, 0C0000121h
0x1402abfe4  cmp     rcx, rax
0x1402abfe7  jz      short loc_1402AC00C
0x1402abfe9  test    [rcx+2Ch], edi
0x1402abfec  jz      short loc_1402AC00C
0x1402abfee  cmp     byte ptr [rcx+29h], 4
0x1402abff2  jb      short loc_1402AC00C
0x1402abff4  mov     rcx, [rcx+18h]
0x1402abff8  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402abfff  mov     edx, 4Dh ; 'M'
0x1402ac004  mov     r9d, ebx
0x1402ac007  call    WPP_SF_d
0x1402ac00c  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac012  test    al, al
0x1402ac014  jz      loc_1402ABC2E
0x1402ac01a  mov     r9d, 15A5h
0x1402ac020  jmp     loc_1402ABC1E
0x1402ac025  mov     rcx, [rsp+0C8h+Handle]; Handle
0x1402ac02d  test    rcx, rcx
0x1402ac030  jz      short loc_1402AC0AC
0x1402ac032  test    dword ptr [r12], 8000h
0x1402ac03a  jz      short loc_1402AC090
0x1402ac03c  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac043  lea     rax, WPP_GLOBAL_Control
0x1402ac04a  mov     ebx, 0C0000008h
0x1402ac04f  cmp     rcx, rax
0x1402ac052  jz      short loc_1402AC077
0x1402ac054  test    [rcx+2Ch], edi
0x1402ac057  jz      short loc_1402AC077
0x1402ac059  cmp     byte ptr [rcx+29h], 4
0x1402ac05d  jb      short loc_1402AC077
0x1402ac05f  mov     rcx, [rcx+18h]
0x1402ac063  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac06a  mov     edx, 4Eh ; 'N'
0x1402ac06f  mov     r9d, ebx
0x1402ac072  call    WPP_SF_d
0x1402ac077  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac07d  test    cl, cl
  ... truncated ...
```
