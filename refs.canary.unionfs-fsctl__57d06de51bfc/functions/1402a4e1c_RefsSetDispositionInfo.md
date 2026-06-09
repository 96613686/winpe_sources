# RefsSetDispositionInfo

- ea: `0x1402a4e1c`
- end: `0x1402a56a3`
- name: `RefsSetDispositionInfo`
- size: `2183`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140319a38`

## callees

- `0x14008dbd0`
- `0x1400ca788`
- `0x140286a28`
- `0x1402a4e1c`
- `0x140308080`
- `0x14031c8e0`

## import_xrefs

- `ntoskrnl!MmFlushImageSection` at `0x1402a5211`
- `ntoskrnl!MmFlushImageSection` at `0x1402a5245`
- `ntoskrnl!MmFlushImageSection` at `0x1402a5481`
- `ntoskrnl!MmFlushImageSection` at `0x1402a5211`
- `ntoskrnl!MmFlushImageSection` at `0x1402a5245`
- `ntoskrnl!MmFlushImageSection` at `0x1402a5481`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1402a557d`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1402a557d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402a5113`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402a5113`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402a511f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402a511f`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x1402a5338`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x1402a5338`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x1402a561f`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x1402a561f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a50f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a50f8`

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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5381;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return v11;
      v12 = 5413;
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
              WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
              3221225659LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            return v11;
          v12 = 5423;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225761LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return v11;
      v12 = 5468;
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
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225761LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v11;
        v12 = 5513;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225761LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5548;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225480LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5567;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225761LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return v11;
      v12 = 5614;
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
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225761LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v11;
        v12 = 5619;
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
              WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
              3221225761LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            return v11;
          v12 = 5634;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225729LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v11;
    v12 = 5683;
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x1402a4e1c  mov     rax, rsp
0x1402a4e1f  mov     [rax+20h], rbx
0x1402a4e23  mov     [rax+10h], rdx
0x1402a4e27  mov     [rax+8], rcx
0x1402a4e2b  push    rbp
0x1402a4e2c  push    rsi
0x1402a4e2d  push    rdi
0x1402a4e2e  push    r12
0x1402a4e30  push    r13
0x1402a4e32  push    r14
0x1402a4e34  push    r15
0x1402a4e36  sub     rsp, 90h
0x1402a4e3d  mov     rsi, [rsp+0C8h+arg_20]
0x1402a4e45  mov     r14, r9
0x1402a4e48  mov     r13, rcx
0x1402a4e4b  mov     byte ptr [rax+18h], 0
0x1402a4e4f  mov     r9, rdx
0x1402a4e52  mov     ecx, 2
0x1402a4e57  mov     rbx, [rsi+48h]
0x1402a4e5b  lea     r12, [rsi+4]
0x1402a4e5f  mov     [rsp+0C8h+var_50], rbx
0x1402a4e64  test    rbx, rbx
0x1402a4e67  jnz     short loc_1402A4ED5
0x1402a4e69  mov     eax, [r12]
0x1402a4e6d  test    cl, al
0x1402a4e6f  jz      short loc_1402A4ED5
0x1402a4e71  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a4e78  lea     rax, WPP_GLOBAL_Control
0x1402a4e7f  mov     ebx, 0C000000Dh
0x1402a4e84  cmp     rcx, rax
0x1402a4e87  jz      short loc_1402A4EAE
0x1402a4e89  bt      dword ptr [rcx+2Ch], 8
0x1402a4e8e  jnb     short loc_1402A4EAE
0x1402a4e90  cmp     byte ptr [rcx+29h], 4
0x1402a4e94  jb      short loc_1402A4EAE
0x1402a4e96  mov     rcx, [rcx+18h]
0x1402a4e9a  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a4ea1  mov     edx, 48h ; 'H'
0x1402a4ea6  mov     r9d, ebx
0x1402a4ea9  call    WPP_SF_d
0x1402a4eae  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a4eb4  test    cl, cl
0x1402a4eb6  jz      short loc_1402A4ECE
0x1402a4eb8  mov     r9d, 1505h; unsigned int
0x1402a4ebe  lea     r8, aFileinfoC; "FileInfo.c"
0x1402a4ec5  xor     edx, edx; struct _IRP_CONTEXT *
0x1402a4ec7  mov     ecx, ebx; Status
0x1402a4ec9  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a4ece  mov     eax, ebx
0x1402a4ed0  jmp     loc_1402A5687
0x1402a4ed5  mov     rdx, [r8+0B8h]; struct _IO_STACK_LOCATION *
0x1402a4edc  mov     rbp, [r8+18h]
0x1402a4ee0  cmp     dword ptr [rdx+10h], 0Dh
0x1402a4ee4  jnz     loc_1402A4FA6
0x1402a4eea  mov     al, [rbp+0]
0x1402a4eed  neg     al
0x1402a4eef  sbb     ebp, ebp
0x1402a4ef1  neg     ebp
0x1402a4ef3  add     ebp, 4
0x1402a4ef6  cmp     dword ptr [rsi+8], 0
0x1402a4efa  mov     r10d, 0FFFFFFFBh
0x1402a4f00  jge     short loc_1402A4F07
0x1402a4f02  and     ebp, r10d
0x1402a4f05  or      ebp, ecx
0x1402a4f07  mov     r15d, 1
0x1402a4f0d  test    r15b, bpl
0x1402a4f10  jz      loc_1402A5637
0x1402a4f16  mov     rax, [rdx+20h]
0x1402a4f1a  mov     edi, 100h
0x1402a4f1f  mov     [rsp+0C8h+Handle], rax
0x1402a4f27  mov     rax, [r14+88h]
0x1402a4f2e  mov     ecx, [rax+98h]
0x1402a4f34  test    r15b, cl
0x1402a4f37  jz      loc_1402A51DA
0x1402a4f3d  test    byte ptr [rdx+2], 40h
0x1402a4f41  jnz     loc_1402A51DA
0x1402a4f47  test    bpl, 10h
0x1402a4f4b  jnz     loc_1402A50AA
0x1402a4f51  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a4f58  lea     rax, WPP_GLOBAL_Control
0x1402a4f5f  mov     ebx, 0C0000121h
0x1402a4f64  cmp     rcx, rax
0x1402a4f67  jz      short loc_1402A4F8D
0x1402a4f69  bt      dword ptr [rcx+2Ch], 8
0x1402a4f6e  jnb     short loc_1402A4F8D
0x1402a4f70  cmp     byte ptr [rcx+29h], 4
0x1402a4f74  jb      short loc_1402A4F8D
0x1402a4f76  mov     rcx, [rcx+18h]
0x1402a4f7a  lea     edx, [r15+4Ah]
0x1402a4f7e  mov     r9d, ebx
0x1402a4f81  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a4f88  call    WPP_SF_d
0x1402a4f8d  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a4f93  test    al, al
0x1402a4f95  jz      loc_1402A4ECE
0x1402a4f9b  mov     r9d, 155Ch
0x1402a4fa1  jmp     loc_1402A4EBE
0x1402a4fa6  mov     ebp, [rbp+0]
0x1402a4fa9  test    ebp, 0FFFFFFE0h
0x1402a4faf  jz      short loc_1402A5007
0x1402a4fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a4fb8  lea     rax, WPP_GLOBAL_Control
0x1402a4fbf  mov     ebx, 0C00000BBh
0x1402a4fc4  cmp     rcx, rax
0x1402a4fc7  jz      short loc_1402A4FEE
0x1402a4fc9  bt      dword ptr [rcx+2Ch], 8
0x1402a4fce  jnb     short loc_1402A4FEE
0x1402a4fd0  cmp     byte ptr [rcx+29h], 4
0x1402a4fd4  jb      short loc_1402A4FEE
0x1402a4fd6  mov     rcx, [rcx+18h]
0x1402a4fda  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a4fe1  mov     edx, 49h ; 'I'
0x1402a4fe6  mov     r9d, ebx
0x1402a4fe9  call    WPP_SF_d
0x1402a4fee  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a4ff4  test    al, al
0x1402a4ff6  jz      loc_1402A4ECE
0x1402a4ffc  mov     r9d, 1525h
0x1402a5002  jmp     loc_1402A4EBE
0x1402a5007  test    bpl, 8
0x1402a500b  jz      loc_1402A4EF6
0x1402a5011  mov     r15d, 1
0x1402a5017  test    r15b, bpl
0x1402a501a  jz      short loc_1402A509B
0x1402a501c  mov     eax, [r12]
0x1402a5020  bt      eax, 12h
0x1402a5024  jb      short loc_1402A507B
0x1402a5026  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a502d  lea     rax, WPP_GLOBAL_Control
0x1402a5034  mov     ebx, 0C00000BBh
0x1402a5039  cmp     rcx, rax
0x1402a503c  jz      short loc_1402A5062
0x1402a503e  bt      dword ptr [rcx+2Ch], 8
0x1402a5043  jnb     short loc_1402A5062
0x1402a5045  cmp     byte ptr [rcx+29h], 4
0x1402a5049  jb      short loc_1402A5062
0x1402a504b  mov     rcx, [rcx+18h]
0x1402a504f  lea     edx, [r15+49h]
0x1402a5053  mov     r9d, ebx
0x1402a5056  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a505d  call    WPP_SF_d
0x1402a5062  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5068  test    cl, cl
0x1402a506a  jz      loc_1402A4ECE
0x1402a5070  mov     r9d, 152Fh
0x1402a5076  jmp     loc_1402A4EBE
0x1402a507b  test    cl, al
0x1402a507d  jz      loc_1402A5685
0x1402a5083  mov     eax, [rsi+8]
0x1402a5086  test    cl, bpl
0x1402a5089  jz      short loc_1402A5096
0x1402a508b  or      eax, 8
0x1402a508e  mov     [rsi+8], eax
0x1402a5091  jmp     loc_1402A5685
0x1402a5096  and     eax, 0FFFFFFF7h
0x1402a5099  jmp     short loc_1402A508E
0x1402a509b  btr     dword ptr [r12], 12h
0x1402a50a1  and     dword ptr [rsi+8], 0FFFFFFF7h
0x1402a50a5  jmp     loc_1402A5685
0x1402a50aa  mov     rcx, r8; struct _IRP *
0x1402a50ad  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402a50b2  cmp     al, r15b
0x1402a50b5  jnz     loc_1402A51DA
0x1402a50bb  mov     ecx, 310h
0x1402a50c0  test    [rsi+58h], cx
0x1402a50c4  jnz     loc_1402A51DA
0x1402a50ca  test    byte ptr [r13+8], 20h
0x1402a50cf  mov     [rsp+0C8h+var_58], 0
0x1402a50d7  mov     dword ptr [rsp+0C8h+arg_20], 0
0x1402a50e2  jnz     short loc_1402A511F
0x1402a50e4  mov     ecx, cs:PoolType
0x1402a50ea  mov     edx, 20h ; ' '; NumberOfBytes
0x1402a50ef  or      ecx, 10h; PoolType
0x1402a50f2  mov     r8d, 46466552h; Tag
0x1402a50f8  call    cs:__imp_ExAllocatePoolWithTag
0x1402a50ff  nop     dword ptr [rax+rax+00h]
0x1402a5104  mov     [r13+90h], rax
0x1402a510b  mov     rcx, rax; SubjectContext
0x1402a510e  or      qword ptr [r13+8], 20h
0x1402a5113  call    cs:__imp_SeCaptureSubjectContext
0x1402a511a  nop     dword ptr [rax+rax+00h]
0x1402a511f  call    cs:__imp_IoGetFileObjectGenericMapping
0x1402a5126  nop     dword ptr [rax+rax+00h]
0x1402a512b  mov     r8, [r13+90h]; struct _SECURITY_SUBJECT_CONTEXT *
0x1402a5132  lea     rcx, [rsp+0C8h+arg_20]
0x1402a513a  xor     edx, edx
0x1402a513c  xor     r9d, r9d; unsigned __int8
0x1402a513f  mov     [rsp+0C8h+var_60], rdx; struct _ACCESS_STATE *
0x1402a5144  mov     [rsp+0C8h+var_68], rcx; int *
0x1402a5149  lea     rcx, [rsp+0C8h+var_58]
0x1402a514e  mov     [rsp+0C8h+var_70], rdx; struct _ACCESS_REASONS *
0x1402a5153  mov     [rsp+0C8h+FilterCallback], rcx; unsigned int *
0x1402a5158  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402a515b  mov     byte ptr [rsp+0C8h+SubjectContext], r15b; char
0x1402a5160  mov     [rsp+0C8h+TraverseCallback], rax; struct _GENERIC_MAPPING *
0x1402a5165  mov     [rsp+0C8h+NotifyIrp], rdx; struct _PRIVILEGE_SET **
0x1402a516a  mov     [rsp+0C8h+CompletionFilter], edx; unsigned int
0x1402a516e  mov     dword ptr [rsp+0C8h+IgnoreBuffer], edi; unsigned int
0x1402a5172  mov     [rsp+0C8h+WatchTree], dl; char
0x1402a5176  mov     rdx, [r14+88h]; struct _FCB *
0x1402a517d  call    ?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z; RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)
0x1402a5182  test    al, al
0x1402a5184  jnz     short loc_1402A51DA
0x1402a5186  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a518d  lea     rax, WPP_GLOBAL_Control
0x1402a5194  mov     ebx, 0C0000121h
0x1402a5199  cmp     rcx, rax
0x1402a519c  jz      short loc_1402A51C1
0x1402a519e  test    [rcx+2Ch], edi
0x1402a51a1  jz      short loc_1402A51C1
0x1402a51a3  cmp     byte ptr [rcx+29h], 4
0x1402a51a7  jb      short loc_1402A51C1
0x1402a51a9  mov     rcx, [rcx+18h]
0x1402a51ad  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a51b4  mov     edx, 4Ch ; 'L'
0x1402a51b9  mov     r9d, ebx
0x1402a51bc  call    WPP_SF_d
0x1402a51c1  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a51c7  test    al, al
0x1402a51c9  jz      loc_1402A4ECE
0x1402a51cf  mov     r9d, 1589h
0x1402a51d5  jmp     loc_1402A4EBE
0x1402a51da  mov     eax, [rsi+4]
0x1402a51dd  xor     r13b, r13b
0x1402a51e0  test    al, 2
0x1402a51e2  jz      short loc_1402A5238
0x1402a51e4  mov     rax, [r14+88h]
0x1402a51eb  add     rax, 30h ; '0'
0x1402a51ef  mov     [rsp+0C8h+arg_20], rax
0x1402a51f7  mov     rbx, [rax]
0x1402a51fa  cmp     rbx, rax
0x1402a51fd  jz      short loc_1402A525D
0x1402a51ff  lock add [rbx+2Ch], r15d
0x1402a5204  mov     rcx, [rbx+80h]
0x1402a520b  xor     edx, edx; FlushType
0x1402a520d  add     rcx, 8; SectionObjectPointer
0x1402a5211  call    cs:__imp_MmFlushImageSection
0x1402a5218  nop     dword ptr [rax+rax+00h]
0x1402a521d  test    al, al
0x1402a521f  setz    r13b
0x1402a5223  lock dec dword ptr [rbx+2Ch]
0x1402a5227  test    al, al
0x1402a5229  jz      short loc_1402A525D
0x1402a522b  mov     rbx, [rbx]
0x1402a522e  mov     rax, [rsp+0C8h+arg_20]
0x1402a5236  jmp     short loc_1402A51FA
0x1402a5238  mov     rcx, [r14+0F8h]
0x1402a523f  xor     edx, edx; FlushType
0x1402a5241  add     rcx, 8; SectionObjectPointer
0x1402a5245  call    cs:__imp_MmFlushImageSection
0x1402a524c  nop     dword ptr [rax+rax+00h]
0x1402a5251  test    al, al
0x1402a5253  movzx   r13d, r13b
0x1402a5257  cmovz   r13d, r15d
0x1402a525b  jmp     short loc_1402A5262
0x1402a525d  mov     rbx, [rsp+0C8h+var_50]
0x1402a5262  mov     rax, [r14+88h]
0x1402a5269  mov     ecx, [rax+8]
0x1402a526c  test    rdi, rcx
0x1402a526f  jz      short loc_1402A52C5
0x1402a5271  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5278  lea     rax, WPP_GLOBAL_Control
0x1402a527f  mov     ebx, 0C0000121h
0x1402a5284  cmp     rcx, rax
0x1402a5287  jz      short loc_1402A52AC
0x1402a5289  test    [rcx+2Ch], edi
0x1402a528c  jz      short loc_1402A52AC
0x1402a528e  cmp     byte ptr [rcx+29h], 4
0x1402a5292  jb      short loc_1402A52AC
0x1402a5294  mov     rcx, [rcx+18h]
0x1402a5298  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a529f  mov     edx, 4Dh ; 'M'
0x1402a52a4  mov     r9d, ebx
0x1402a52a7  call    WPP_SF_d
0x1402a52ac  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a52b2  test    al, al
0x1402a52b4  jz      loc_1402A4ECE
0x1402a52ba  mov     r9d, 15ACh
0x1402a52c0  jmp     loc_1402A4EBE
0x1402a52c5  mov     rcx, [rsp+0C8h+Handle]; Handle
0x1402a52cd  test    rcx, rcx
0x1402a52d0  jz      short loc_1402A534C
0x1402a52d2  test    dword ptr [r12], 8000h
0x1402a52da  jz      short loc_1402A5330
0x1402a52dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a52e3  lea     rax, WPP_GLOBAL_Control
0x1402a52ea  mov     ebx, 0C0000008h
0x1402a52ef  cmp     rcx, rax
0x1402a52f2  jz      short loc_1402A5317
0x1402a52f4  test    [rcx+2Ch], edi
0x1402a52f7  jz      short loc_1402A5317
0x1402a52f9  cmp     byte ptr [rcx+29h], 4
0x1402a52fd  jb      short loc_1402A5317
0x1402a52ff  mov     rcx, [rcx+18h]
0x1402a5303  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a530a  mov     edx, 4Eh ; 'N'
0x1402a530f  mov     r9d, ebx
0x1402a5312  call    WPP_SF_d
0x1402a5317  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a531d  test    cl, cl
  ... truncated ...
```
