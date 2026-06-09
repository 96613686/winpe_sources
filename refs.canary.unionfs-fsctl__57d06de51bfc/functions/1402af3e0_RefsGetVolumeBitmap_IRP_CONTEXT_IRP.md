# RefsGetVolumeBitmap(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402af3e0`
- end: `0x1402afd12`
- name: `?RefsGetVolumeBitmap@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `2354`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140320e78`

## callees

- `0x140041b40`
- `0x1400548b0`
- `0x140081670`
- `0x140087ee0`
- `0x14008c400`
- `0x14008dbd0`
- `0x140096fd0`
- `0x1400ca788`
- `0x1400f9854`
- `0x14011524c`
- `0x14028d9b0`
- `0x14028d9ec`
- `0x1402af3e0`
- `0x14031ac80`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1402af662`
- `ntoskrnl!IoAllocateMdl` at `0x1402af662`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402af693`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402af693`
- `ntoskrnl!IoFreeMdl` at `0x1402af716`
- `ntoskrnl!IoFreeMdl` at `0x1402af9e5`
- `ntoskrnl!IoFreeMdl` at `0x140344d19`
- `ntoskrnl!IoFreeMdl` at `0x1402af716`
- `ntoskrnl!IoFreeMdl` at `0x1402af9e5`
- `ntoskrnl!IoFreeMdl` at `0x140344d19`
- `ntoskrnl!MmUnlockPages` at `0x1402af707`
- `ntoskrnl!MmUnlockPages` at `0x1402af9d6`
- `ntoskrnl!MmUnlockPages` at `0x140344d0a`
- `ntoskrnl!MmUnlockPages` at `0x1402af707`
- `ntoskrnl!MmUnlockPages` at `0x1402af9d6`
- `ntoskrnl!MmUnlockPages` at `0x140344d0a`
- `ntoskrnl!ProbeForRead` at `0x1402af5ab`
- `ntoskrnl!ProbeForRead` at `0x1402af5ab`
- `ntoskrnl!ProbeForWrite` at `0x1402af5c4`
- `ntoskrnl!ProbeForWrite` at `0x1402af5c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402af6c3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402af6c3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1402af893`
- `ntoskrnl!RtlInitializeBitMap` at `0x1402af893`

## pseudocode

```c
__int64 __fastcall RefsGetVolumeBitmap(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  unsigned int VolumeBitmap; // edi
  struct _MDL *v5; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v7; // edx
  ULONG *MappedSystemVa; // rbx
  unsigned int v9; // r9d
  __int64 ULong64FromUser; // r13
  char *v11; // rax
  int *v12; // rcx
  int v13; // eax
  bool v14; // zf
  int v15; // eax
  struct _MDL *Mdl; // rax
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  struct _VCB *v19; // rdi
  unsigned int v20; // r9d
  int v21; // eax
  unsigned __int64 v22; // r13
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  struct _VCB *v25; // rdx
  BOOL v26; // eax
  unsigned int v28; // r8d
  SIZE_T *Irpa; // [rsp+20h] [rbp-B8h]
  char v30; // [rsp+40h] [rbp-98h]
  struct _VCB *v31; // [rsp+48h] [rbp-90h] BYREF
  __int64 v32; // [rsp+50h] [rbp-88h]
  unsigned int Length; // [rsp+58h] [rbp-80h]
  int Length_4; // [rsp+5Ch] [rbp-7Ch]
  volatile void *Address; // [rsp+60h] [rbp-78h] BYREF
  ULONG *v36; // [rsp+68h] [rbp-70h]
  unsigned __int64 v37; // [rsp+70h] [rbp-68h]
  PULONG BitMapBuffer; // [rsp+78h] [rbp-60h]
  PMDL MemoryDescriptorList; // [rsp+80h] [rbp-58h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+88h] [rbp-50h] BYREF
  SIZE_T v43; // [rsp+F0h] [rbp+18h] BYREF
  int v44; // [rsp+F8h] [rbp+20h]

  VolumeBitmap = 0;
  v31 = 0;
  v43 = 0;
  v32 = 0;
  v36 = 0;
  BitMapBuffer = 0;
  v5 = 0;
  MemoryDescriptorList = 0;
  v37 = 0;
  BitMapHeader = 0;
  v44 = 0;
  Length_4 = 0;
  *((_QWORD *)a1 + 1) |= 1uLL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irpa = &v43;
  RefsDecodeFileObject(a1, CurrentStackLocation->FileObject, &v31, &Address);
  Length = CurrentStackLocation->Parameters.Create.Options;
  Address = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  LODWORD(v43) = CurrentStackLocation->Parameters.Read.Length;
  MappedSystemVa = (ULONG *)RefsMapUserBuffer(Irp, v7);
  v36 = MappedSystemVa;
  if ( !v32 || !_bittest16((const signed __int16 *)(v32 + 88), 9u) )
  {
    VolumeBitmap = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v9 = 6024;
      goto LABEL_79;
    }
    return VolumeBitmap;
  }
  if ( (unsigned int)v43 < 0x18 )
  {
    VolumeBitmap = -1073741789;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741789);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225507LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v9 = 6029;
LABEL_79:
      RefsStatusDebug(VolumeBitmap, 0, "FsCtrl.c", v9);
      return VolumeBitmap;
    }
    return VolumeBitmap;
  }
  LODWORD(v32) = v43;
  if ( Length >= 8 )
  {
    if ( Irp->RequestorMode
      && (ProbeForRead(Address, Length, 1u), ProbeForWrite(MappedSystemVa, (unsigned int)v43, 1u), Irp->RequestorMode) )
    {
      ULong64FromUser = RtlReadULong64FromUser(Address);
      v11 = (char *)Address;
    }
    else
    {
      v11 = (char *)Address;
      ULong64FromUser = *(_QWORD *)Address;
    }
    v37 = ULong64FromUser;
    BitMapBuffer = MappedSystemVa + 4;
    if ( Length >= 0x10 )
    {
      v12 = (int *)(v11 + 8);
      if ( Irp->RequestorMode )
        LOBYTE(v13) = RtlReadULongFromUser(v12);
      else
        v13 = *v12;
      v14 = (v13 & 1) == 0;
      v15 = v44;
      if ( !v14 )
        v15 = 1;
      v44 = v15;
      Length_4 = v15;
    }
    if ( Irp->RequestorMode )
    {
      Mdl = IoAllocateMdl(MappedSystemVa, v43, 0, 0, 0);
      v5 = Mdl;
      MemoryDescriptorList = Mdl;
      if ( Mdl )
      {
        MmProbeAndLockPages(Mdl, Irp->RequestorMode, IoWriteAccess);
        if ( (v5->MdlFlags & 5) != 0 )
          MappedSystemVa = (ULONG *)v5->MappedSystemVa;
        else
          MappedSystemVa = (ULONG *)MmMapLockedPagesSpecifyCache(v5, 0, MmCached, 0, 0, 0x40000010u);
        v36 = MappedSystemVa;
        if ( MappedSystemVa )
        {
          BitMapBuffer = MappedSystemVa + 4;
          goto LABEL_35;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            101,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "FsCtrl.c", 0x17B8u);
        RefsRaiseStatusInternal(a1, -1073741670, v17);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225626LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741670, a1, "FsCtrl.c", 0x17C2u);
      RefsRaiseStatusInternal(a1, -1073741670, v18);
      goto LABEL_95;
    }
LABEL_35:
    v19 = v31;
    RefsAcquireSharedVcb(a1, v31, 1u);
    v30 = 1;
    if ( (*((_DWORD *)v19 + 6) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        VolumeBitmap = -1073741202;
      }
      else
      {
        VolumeBitmap = -1073741202;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v20 = 6116;
LABEL_58:
        RefsStatusDebug(VolumeBitmap, 0, "FsCtrl.c", v20);
        goto LABEL_59;
      }
      goto LABEL_59;
    }
    if ( ULong64FromUser < 0 || ULong64FromUser >= *((_QWORD *)v19 + 30) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        VolumeBitmap = -1073741811;
      }
      else
      {
        VolumeBitmap = -1073741811;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v20 = 6123;
        goto LABEL_58;
      }
LABEL_59:
      if ( v30 )
        RefsReleaseVcb(a1, v31);
      if ( v5 )
      {
        MmUnlockPages(v5);
        IoFreeMdl(v5);
      }
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, VolumeBitmap);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
LABEL_71:
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v9 = 6232;
          goto LABEL_79;
        }
        return VolumeBitmap;
      }
      if ( (VolumeBitmap & 0x80000000) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
LABEL_70:
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            109,
            WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
            VolumeBitmap);
          goto LABEL_71;
        }
        v26 = 0;
      }
      else
      {
        v26 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      }
      if ( !v26 )
        goto LABEL_71;
      goto LABEL_70;
    }
    v21 = v43 - 16;
    if ( (unsigned int)(v43 - 16) > 0x1FFFFFFF )
      v21 = 0x1FFFFFFF;
    LODWORD(v43) = v21;
    v22 = ULong64FromUser & 0xFFFFFFFFFFFFFFF8uLL;
    v37 = v22;
    LODWORD(v32) = 8 * v21;
    RtlInitializeBitMap(&BitMapHeader, BitMapBuffer, 8 * v21);
    VolumeBitmap = RefsBindMinstoreTransactionNoRaise(a1);
    if ( (VolumeBitmap & 0x80000000) != 0 )
      goto LABEL_59;
    VolumeBitmap = MsQueryVolumeBitmap(
                     *((struct CmsTransactionContext **)a1 + 3),
                     *((CmsVolume **)v31 + 14),
                     (_DWORD)Irpa,
                     v44);
    if ( (VolumeBitmap & 0x80000000) == 0 )
    {
      RefsReleaseVcb(a1, v31);
      v30 = 0;
      *(_QWORD *)MappedSystemVa = v22;
      v25 = v31;
      *((_QWORD *)MappedSystemVa + 1) = *((_QWORD *)v31 + 30) - v22;
      Irp->IoStatus.Information = (unsigned int)(v43 + 16);
      if ( *((_QWORD *)v25 + 30) <= (signed __int64)(v22 + (unsigned int)v32) )
        goto LABEL_59;
LABEL_102:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 2147483653LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-2147483643, a1, "FsCtrl.c", 0x1846u);
      RefsRaiseStatusInternal(a1, -2147483643, v24);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225704LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741592, a1, "FsCtrl.c", 0x183Cu);
      RefsRaiseStatusInternal(a1, -1073741592, v28);
      JUMPOUT(0x1402AFD12LL);
    }
LABEL_95:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, VolumeBitmap);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(VolumeBitmap, a1, "FsCtrl.c", 0x1817u);
    RefsRaiseStatusInternal(a1, VolumeBitmap, v23);
    goto LABEL_102;
  }
  VolumeBitmap = -1073741811;
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741811);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v9 = 6034;
    goto LABEL_79;
  }
  return VolumeBitmap;
}

```

## disassembly

```asm
0x1402af3e0  mov     r11, rsp
0x1402af3e3  mov     [r11+10h], rdx
0x1402af3e7  mov     [r11+8], rcx
0x1402af3eb  push    rbx
0x1402af3ec  push    rsi
0x1402af3ed  push    rdi
0x1402af3ee  push    r12
0x1402af3f0  push    r13
0x1402af3f2  push    r14
0x1402af3f4  push    r15
0x1402af3f6  sub     rsp, 0A0h
0x1402af3fd  mov     r13, rdx
0x1402af400  mov     r14, rcx
0x1402af403  xor     esi, esi
0x1402af405  mov     edi, esi
0x1402af407  mov     [rsp+0D8h+var_90], rsi
0x1402af40c  mov     [r11+18h], rsi
0x1402af410  mov     [rsp+0D8h+var_88], rsi
0x1402af415  mov     [r11-70h], rsi
0x1402af419  mov     [r11-60h], rsi
0x1402af41d  mov     r15d, esi
0x1402af420  mov     [r11-58h], rsi
0x1402af424  mov     [r11-68h], rsi
0x1402af428  xorps   xmm0, xmm0
0x1402af42b  movups  xmmword ptr [r11-50h], xmm0
0x1402af430  mov     eax, esi
0x1402af432  mov     [r11+20h], eax
0x1402af436  mov     dword ptr [rsp+0D8h+Length+4], eax
0x1402af43a  lea     r12d, [rsi+1]
0x1402af43e  or      [rcx+8], r12
0x1402af442  mov     rbx, [rdx+0B8h]
0x1402af449  mov     [rsp+0D8h+var_A8], sil
0x1402af44e  lea     rax, [rsp+0D8h+var_88]
0x1402af453  mov     qword ptr [rsp+0D8h+Priority], rax
0x1402af458  lea     rax, [r11+18h]
0x1402af45c  mov     [rsp+0D8h+Irp], rax
0x1402af461  lea     r9, [r11-78h]
0x1402af465  lea     r8, [rsp+0D8h+var_90]
0x1402af46a  mov     rdx, [rbx+30h]
0x1402af46e  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402af473  mov     ecx, [rbx+10h]
0x1402af476  mov     dword ptr [rsp+0D8h+Length], ecx
0x1402af47a  mov     rax, [rbx+20h]
0x1402af47e  mov     [rsp+0D8h+Address], rax
0x1402af483  mov     eax, [rbx+8]
0x1402af486  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1402af48d  mov     rcx, r13; struct _IRP *
0x1402af490  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x1402af495  mov     rbx, rax
0x1402af498  mov     [rsp+0D8h+var_70], rax
0x1402af49d  mov     rax, [rsp+0D8h+var_88]
0x1402af4a2  test    rax, rax
0x1402af4a5  jz      loc_1402AFA67
0x1402af4ab  bt      word ptr [rax+58h], 9
0x1402af4b1  jnb     loc_1402AFA67
0x1402af4b7  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x1402af4be  cmp     eax, 18h
0x1402af4c1  jnb     short loc_1402AF527
0x1402af4c3  mov     edi, 0C0000023h
0x1402af4c8  mov     r8d, edi; Status
0x1402af4cb  mov     rdx, r13; Irp
0x1402af4ce  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402af4d1  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402af4d6  lea     rbx, WPP_GLOBAL_Control
0x1402af4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1402af4e4  cmp     rcx, rbx
0x1402af4e7  jz      short loc_1402AF50E
0x1402af4e9  test    dword ptr [rcx+2Ch], 100h
0x1402af4f0  jz      short loc_1402AF50E
0x1402af4f2  cmp     byte ptr [rcx+29h], 4
0x1402af4f6  jb      short loc_1402AF50E
0x1402af4f8  lea     edx, [rsi+63h]
0x1402af4fb  mov     r9d, edi
0x1402af4fe  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402af505  mov     rcx, [rcx+18h]
0x1402af509  call    WPP_SF_d
0x1402af50e  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402af514  test    al, al
0x1402af516  jz      loc_1402AFAD4
0x1402af51c  mov     r9d, 178Dh
0x1402af522  jmp     loc_1402AFAC4
0x1402af527  mov     dword ptr [rsp+0D8h+var_88], eax
0x1402af52b  mov     eax, dword ptr [rsp+0D8h+Length]
0x1402af52f  cmp     eax, 8
0x1402af532  jnb     short loc_1402AF59A
0x1402af534  mov     edi, 0C000000Dh
0x1402af539  mov     r8d, edi; Status
0x1402af53c  mov     rdx, r13; Irp
0x1402af53f  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402af542  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402af547  lea     rbx, WPP_GLOBAL_Control
0x1402af54e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402af555  cmp     rcx, rbx
0x1402af558  jz      short loc_1402AF581
0x1402af55a  test    dword ptr [rcx+2Ch], 100h
0x1402af561  jz      short loc_1402AF581
0x1402af563  cmp     byte ptr [rcx+29h], 4
0x1402af567  jb      short loc_1402AF581
0x1402af569  mov     edx, 64h ; 'd'
0x1402af56e  mov     r9d, edi
0x1402af571  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402af578  mov     rcx, [rcx+18h]
0x1402af57c  call    WPP_SF_d
0x1402af581  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402af587  test    al, al
0x1402af589  jz      loc_1402AFAD4
0x1402af58f  mov     r9d, 1792h
0x1402af595  jmp     loc_1402AFAC4
0x1402af59a  cmp     [r13+40h], sil
0x1402af59e  jz      short loc_1402AF5EA
0x1402af5a0  mov     rdx, rax; Length
0x1402af5a3  mov     r8d, r12d; Alignment
0x1402af5a6  mov     rcx, [rsp+0D8h+Address]; Address
0x1402af5ab  call    cs:__imp_ProbeForRead
0x1402af5b2  nop     dword ptr [rax+rax+00h]
0x1402af5b7  mov     edx, dword ptr [rsp+0D8h+arg_10]; Length
0x1402af5be  mov     r8d, r12d; Alignment
0x1402af5c1  mov     rcx, rbx; Address
0x1402af5c4  call    cs:__imp_ProbeForWrite
0x1402af5cb  nop     dword ptr [rax+rax+00h]
0x1402af5d0  cmp     [r13+40h], sil
0x1402af5d4  jz      short loc_1402AF5EA
0x1402af5d6  mov     rcx, [rsp+0D8h+Address]
0x1402af5db  call    RtlReadULong64FromUser
0x1402af5e0  mov     r13, rax
0x1402af5e3  mov     rax, [rsp+0D8h+Address]
0x1402af5e8  jmp     short loc_1402AF5F2
0x1402af5ea  mov     rax, [rsp+0D8h+Address]
0x1402af5ef  mov     r13, [rax]
0x1402af5f2  mov     [rsp+0D8h+var_68], r13
0x1402af5f7  lea     rcx, [rbx+10h]
0x1402af5fb  mov     [rsp+0D8h+BitMapBuffer], rcx
0x1402af600  cmp     dword ptr [rsp+0D8h+Length], 10h
0x1402af605  jb      short loc_1402AF63B
0x1402af607  lea     rcx, [rax+8]
0x1402af60b  mov     rax, [rsp+0D8h+arg_8]
0x1402af613  cmp     [rax+40h], sil
0x1402af617  jz      short loc_1402AF620
0x1402af619  call    RtlReadULongFromUser
0x1402af61e  jmp     short loc_1402AF622
0x1402af620  mov     eax, [rcx]
0x1402af622  test    r12b, al
0x1402af625  mov     eax, [rsp+0D8h+arg_18]
0x1402af62c  cmovnz  eax, r12d
0x1402af630  mov     [rsp+0D8h+arg_18], eax
0x1402af637  mov     dword ptr [rsp+0D8h+Length+4], eax
0x1402af63b  mov     rax, [rsp+0D8h+arg_8]
0x1402af643  cmp     [rax+40h], sil
0x1402af647  jz      loc_1402AF6E9
0x1402af64d  mov     [rsp+0D8h+Irp], rsi; Irp
0x1402af652  xor     r9d, r9d; ChargeQuota
0x1402af655  xor     r8d, r8d; SecondaryBuffer
0x1402af658  mov     edx, dword ptr [rsp+0D8h+arg_10]; Length
0x1402af65f  mov     rcx, rbx; VirtualAddress
0x1402af662  call    cs:__imp_IoAllocateMdl
0x1402af669  nop     dword ptr [rax+rax+00h]
0x1402af66e  mov     r15, rax
0x1402af671  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x1402af679  test    rax, rax
0x1402af67c  jz      loc_1402AFAEA
0x1402af682  mov     r8d, r12d; Operation
0x1402af685  mov     rax, [rsp+0D8h+arg_8]
0x1402af68d  mov     dl, [rax+40h]; AccessMode
0x1402af690  mov     rcx, r15; MemoryDescriptorList
0x1402af693  call    cs:__imp_MmProbeAndLockPages
0x1402af69a  nop     dword ptr [rax+rax+00h]
0x1402af69f  test    byte ptr [r15+0Ah], 5
0x1402af6a4  jz      short loc_1402AF6AC
0x1402af6a6  mov     rbx, [r15+18h]
0x1402af6aa  jmp     short loc_1402AF6D2
0x1402af6ac  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x1402af6b4  mov     dword ptr [rsp+0D8h+Irp], esi; BugCheckOnFailure
0x1402af6b8  xor     r9d, r9d; RequestedAddress
0x1402af6bb  mov     r8d, r12d; CacheType
0x1402af6be  xor     edx, edx; AccessMode
0x1402af6c0  mov     rcx, r15; MemoryDescriptorList
0x1402af6c3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1402af6ca  nop     dword ptr [rax+rax+00h]
0x1402af6cf  mov     rbx, rax
0x1402af6d2  mov     [rsp+0D8h+var_70], rbx
0x1402af6d7  test    rbx, rbx
0x1402af6da  jz      loc_1402AFB56
0x1402af6e0  lea     rax, [rbx+10h]
0x1402af6e4  mov     [rsp+0D8h+BitMapBuffer], rax
0x1402af6e9  jmp     loc_1402AF7B6
0x1402af6ee  mov     edi, eax
0x1402af6f0  mov     r15, [rsp+0D8h+MemoryDescriptorList]
0x1402af6f8  test    r15, r15
0x1402af6fb  jz      short loc_1402AF722
0x1402af6fd  test    byte ptr [r15+0Ah], 2
0x1402af702  jz      short loc_1402AF713
0x1402af704  mov     rcx, r15; MemoryDescriptorList
0x1402af707  call    cs:__imp_MmUnlockPages
0x1402af70e  nop     dword ptr [rax+rax+00h]
0x1402af713  mov     rcx, r15; Mdl
0x1402af716  call    cs:__imp_IoFreeMdl
0x1402af71d  nop     dword ptr [rax+rax+00h]
0x1402af722  lea     rax, WPP_GLOBAL_Control
0x1402af729  mov     rcx, cs:WPP_GLOBAL_Control
0x1402af730  cmp     rcx, rax
0x1402af733  jz      short loc_1402AF768
0x1402af735  test    dword ptr [rcx+2Ch], 100h
0x1402af73c  jz      short loc_1402AF768
0x1402af73e  test    edi, edi
0x1402af740  js      short loc_1402AF74A
0x1402af742  cmp     byte ptr [rcx+29h], 5
0x1402af746  jnb     short loc_1402AF750
0x1402af748  jmp     short loc_1402AF768
0x1402af74a  cmp     byte ptr [rcx+29h], 4
0x1402af74e  jb      short loc_1402AF768
0x1402af750  mov     r9d, edi
0x1402af753  mov     edx, 67h ; 'g'
0x1402af758  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402af75f  mov     rcx, [rcx+18h]
0x1402af763  call    WPP_SF_d
0x1402af768  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402af76e  test    al, al
0x1402af770  jz      short loc_1402AF788
0x1402af772  mov     ecx, edi; Status
0x1402af774  mov     r9d, 17D0h; unsigned int
0x1402af77a  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402af781  xor     edx, edx; struct _IRP_CONTEXT *
0x1402af783  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402af788  xor     esi, esi
0x1402af78a  lea     r12d, [rsi+1]
0x1402af78e  mov     r14, [rsp+0D8h+arg_0]
0x1402af796  mov     rbx, [rsp+0D8h+var_70]
0x1402af79b  mov     eax, dword ptr [rsp+0D8h+var_88]
0x1402af79f  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1402af7a6  mov     r13, [rsp+0D8h+var_68]
0x1402af7ab  mov     eax, dword ptr [rsp+0D8h+Length+4]
0x1402af7af  mov     [rsp+0D8h+arg_18], eax
0x1402af7b6  test    edi, edi
0x1402af7b8  js      loc_1402AF9F3
0x1402af7be  mov     [rsp+0D8h+var_97], sil
0x1402af7c3  mov     r8b, r12b; unsigned __int8
0x1402af7c6  mov     rdi, [rsp+0D8h+var_90]
0x1402af7cb  mov     rdx, rdi; struct _VCB *
0x1402af7ce  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402af7d1  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1402af7d6  mov     [rsp+0D8h+var_98], r12b
0x1402af7db  mov     eax, [rdi+18h]
0x1402af7de  test    r12b, al
0x1402af7e1  jnz     short loc_1402AF842
0x1402af7e3  lea     rbx, WPP_GLOBAL_Control
0x1402af7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1402af7f1  cmp     rcx, rbx
0x1402af7f4  jz      short loc_1402AF824
0x1402af7f6  mov     eax, [rcx+2Ch]
0x1402af7f9  bt      eax, 8
0x1402af7fd  jnb     short loc_1402AF824
0x1402af7ff  mov     edi, 0C000026Eh
0x1402af804  cmp     byte ptr [rcx+29h], 4
0x1402af808  jb      short loc_1402AF829
0x1402af80a  mov     edx, 68h ; 'h'
0x1402af80f  mov     r9d, edi
0x1402af812  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402af819  mov     rcx, [rcx+18h]
0x1402af81d  call    WPP_SF_d
0x1402af822  jmp     short loc_1402AF829
0x1402af824  mov     edi, 0C000026Eh
0x1402af829  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402af82f  test    al, al
0x1402af831  jz      loc_1402AF9B6
0x1402af837  mov     r9d, 17E4h
0x1402af83d  jmp     loc_1402AF9A6
0x1402af842  test    r13, r13
0x1402af845  js      loc_1402AF950
0x1402af84b  cmp     r13, [rdi+0F0h]
0x1402af852  jge     loc_1402AF950
0x1402af858  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x1402af85f  add     eax, 0FFFFFFF0h
0x1402af862  mov     ecx, 1FFFFFFFh
0x1402af867  cmp     eax, ecx
0x1402af869  cmova   eax, ecx
0x1402af86c  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1402af873  and     r13, 0FFFFFFFFFFFFFFF8h
0x1402af877  mov     [rsp+0D8h+var_68], r13
0x1402af87c  shl     eax, 3
0x1402af87f  mov     dword ptr [rsp+0D8h+var_88], eax
0x1402af883  mov     r8d, eax; SizeOfBitMap
0x1402af886  mov     rdx, [rsp+0D8h+BitMapBuffer]; BitMapBuffer
0x1402af88b  lea     rcx, [rsp+0D8h+BitMapHeader]; BitMapHeader
0x1402af893  call    cs:__imp_RtlInitializeBitMap
0x1402af89a  nop     dword ptr [rax+rax+00h]
0x1402af89f  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402af8a2  call    ?RefsBindMinstoreTransactionNoRaise@@YAJPEAU_IRP_CONTEXT@@@Z; RefsBindMinstoreTransactionNoRaise(_IRP_CONTEXT *)
0x1402af8a7  mov     edi, eax
0x1402af8a9  mov     [rsp+0D8h+var_94], eax
0x1402af8ad  test    eax, eax
0x1402af8af  js      loc_1402AF947
0x1402af8b5  mov     eax, [rsp+0D8h+arg_18]
0x1402af8bc  mov     [rsp+0D8h+Priority], eax
0x1402af8c0  lea     r9, [rsp+0D8h+BitMapHeader]
0x1402af8c8  mov     r8, r13
0x1402af8cb  mov     rdx, [rsp+0D8h+var_90]
0x1402af8d0  mov     rdx, [rdx+70h]
0x1402af8d4  mov     rcx, [r14+18h]
0x1402af8d8  call    MsQueryVolumeBitmap
0x1402af8dd  mov     edi, eax
  ... truncated ...
```
