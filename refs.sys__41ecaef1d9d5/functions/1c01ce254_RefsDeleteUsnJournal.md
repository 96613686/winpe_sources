# RefsDeleteUsnJournal

- ea: `0x1c01ce254`
- end: `0x1c01ceaf5`
- name: `RefsDeleteUsnJournal`
- size: `2209`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c00049a0`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003f35c`
- `0x1c0068168`
- `0x1c009deb8`
- `0x1c00a9ccc`
- `0x1c016d3c4`
- `0x1c01ce254`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ce935`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ceae1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ce935`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ceae1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01ce76c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01ce7c6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01ce76c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01ce7c6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01ce903`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01ce922`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01ceac0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01ce903`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01ce922`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01ceac0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c01ce2c7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c01ce2c7`

## pseudocode

```c
__int64 __fastcall RefsDeleteUsnJournal(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  IRP *v6; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _DWORD *p_Type; // rsi
  PMDL MdlAddress; // rcx
  unsigned int v10; // esi
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  __int64 v15; // rbx
  int v16; // ecx
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *v18; // rcx
  struct _LIST_ENTRY *v19; // rdx
  __int64 v20; // r9
  char v21; // [rsp+40h] [rbp-38h]
  char v22; // [rsp+48h] [rbp-30h] BYREF
  unsigned int Status; // [rsp+80h] [rbp+8h]
  __int64 v24; // [rsp+88h] [rbp+10h] BYREF
  __int64 v25; // [rsp+90h] [rbp+18h] BYREF
  __int64 v26; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  Status = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  v21 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_DWORD *)(a1 + 8) |= 1u;
  p_Type = &a2->AssociatedIrp.MasterIrp->Type;
  if ( !p_Type )
  {
    MdlAddress = a2->MdlAddress;
    if ( !MdlAddress )
    {
      v10 = -1073741592;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741592);
      RefsExtendedCompleteRequestInternal(a1, a2, -1073741592, a4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225704LL);
      }
      if ( !RefsStatusDebugEnabled )
        return v10;
LABEL_124:
      RefsStatusDebug(v10);
      return v10;
    }
    if ( (MdlAddress->MdlFlags & 5) != 0 )
      p_Type = MdlAddress->MappedSystemVa;
    else
      p_Type = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    if ( !p_Type )
    {
      v10 = -1073741670;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741670);
      RefsExtendedCompleteRequestInternal(a1, a2, -1073741670, a4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225626LL);
      }
      if ( !RefsStatusDebugEnabled )
        return v10;
      goto LABEL_124;
    }
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
  {
    v10 = -1073741592;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592);
    RefsExtendedCompleteRequestInternal(a1, a2, -1073741592, a4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225704LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v10;
    goto LABEL_124;
  }
  RefsDecodeFileObject(
    a1,
    CurrentStackLocation->FileObject,
    (unsigned int)&v24,
    (unsigned int)&v22,
    (__int64)&v26,
    (__int64)&v25,
    1);
  if ( !v25 || (*(_WORD *)(v25 + 88) & 0x200) == 0 )
  {
    v10 = -1073741790;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    RefsExtendedCompleteRequestInternal(a1, a2, -1073741790, v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225506LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v10;
    goto LABEL_124;
  }
  v13 = p_Type[2];
  if ( !v13 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    RefsExtendedCompleteRequestInternal(a1, a2, 0, v12);
    return 0;
  }
  if ( (v13 & 0xFFFFFFFC) != 0 )
  {
    v10 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, -1073741811, v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v10;
    goto LABEL_124;
  }
  v15 = v24;
  if ( (*(_DWORD *)(v24 + 4) & 0x2000000) != 0 )
  {
    v10 = -1073741662;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741662);
    RefsExtendedCompleteRequestInternal(a1, a2, -1073741662, v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225634LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v10;
    goto LABEL_124;
  }
  LOBYTE(v11) = 1;
  RefsAcquireExclusiveVcb(a1, v24, v11, v12);
  v16 = *(_DWORD *)(v15 + 4);
  if ( (v16 & 1) != 0 )
  {
    if ( (p_Type[2] & 1) != 0 )
    {
      if ( (v16 & 0x100000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            56,
            WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids,
            3221226167LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741129);
        Status = -1073741129;
        goto LABEL_56;
      }
      if ( (v16 & 0x200000) != 0 || *(_QWORD *)(v15 + 40) )
      {
        if ( *(_QWORD *)(v15 + 40) && *(_QWORD *)p_Type != *(_QWORD *)(v15 + 864) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              57,
              WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids,
              3221225485LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741811);
          Status = -1073741811;
          goto LABEL_56;
        }
        RefsDeactivateUsnJournal(a1, v15);
        if ( (p_Type[2] & 2) != 0 )
        {
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v15 + 480));
          v21 = 1;
        }
        RefsPostSpecial(a1, v15, (unsigned int)RefsDeleteUsnSpecial, v15 + 1160, 1, 0);
        v16 = *(_DWORD *)(v15 + 4);
      }
    }
    if ( (v16 & 0x100000) != 0 && (p_Type[2] & 2) != 0 )
    {
      if ( !v21 )
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v15 + 480));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 259);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(259);
      Status = 259;
      if ( (unsigned __int8)RefsSetCancelRoutine(a2, RefsCancelDeleteUsnJournal, 0, 1) )
      {
        p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
        v15 = v24;
        v18 = (struct _LIST_ENTRY *)(v24 + 912);
        v19 = *(struct _LIST_ENTRY **)(v24 + 920);
        if ( v19->Flink != (struct _LIST_ENTRY *)(v24 + 912) )
          __fastfail(3u);
        p_ListEntry->ListEntry.Flink = v18;
        a2->Tail.Overlay.ListEntry.Blink = v19;
        v19->Flink = &p_ListEntry->ListEntry;
        v18->Blink = &p_ListEntry->ListEntry;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids,
            3221225760LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741536);
        Status = -1073741536;
        v15 = v24;
      }
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v15 + 480));
      v21 = 0;
    }
    goto LABEL_102;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221226094LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741202);
  Status = -1073741202;
LABEL_56:
  v15 = v24;
LABEL_102:
  if ( v21 )
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v15 + 480));
  ExReleaseResourceLite((PERESOURCE)(v15 + 1424));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  if ( Status != 259 )
    v6 = a2;
  RefsExtendedCompleteRequestInternal(a1, v6, Status, v20);
  return Status;
}

```

## disassembly

```asm
0x1c01ce254  mov     rax, rsp
0x1c01ce257  push    rbx
0x1c01ce258  push    rsi
0x1c01ce259  push    rdi
0x1c01ce25a  push    r14
0x1c01ce25c  push    r15
0x1c01ce25e  sub     rsp, 50h
0x1c01ce262  mov     r14, rdx
0x1c01ce265  mov     r15, rcx
0x1c01ce268  xor     edi, edi
0x1c01ce26a  mov     [rax+8], edi
0x1c01ce26d  mov     [rax+10h], rdi
0x1c01ce271  mov     [rax+20h], rdi
0x1c01ce275  mov     [rax+18h], rdi
0x1c01ce279  mov     [rax-37h], dil
0x1c01ce27d  mov     [rax-38h], dil
0x1c01ce281  mov     rbx, [rdx+0B8h]
0x1c01ce288  or      dword ptr [rcx+8], 1
0x1c01ce28c  mov     rsi, [rdx+18h]
0x1c01ce290  test    rsi, rsi
0x1c01ce293  jnz     loc_1C01CE363
0x1c01ce299  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1c01ce29d  test    rcx, rcx
0x1c01ce2a0  jz      loc_1C01CEA0B
0x1c01ce2a6  test    byte ptr [rcx+0Ah], 5
0x1c01ce2aa  jz      short loc_1C01CE2B2
0x1c01ce2ac  mov     rsi, [rcx+18h]
0x1c01ce2b0  jmp     short loc_1C01CE2D6
0x1c01ce2b2  mov     [rsp+78h+Priority], 40000010h; Priority
0x1c01ce2ba  mov     [rsp+78h+BugCheckOnFailure], edi; BugCheckOnFailure
0x1c01ce2be  xor     r9d, r9d; RequestedAddress
0x1c01ce2c1  xor     edx, edx; AccessMode
0x1c01ce2c3  lea     r8d, [r9+1]; CacheType
0x1c01ce2c7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c01ce2ce  nop     dword ptr [rax+rax+00h]
0x1c01ce2d3  mov     rsi, rax
0x1c01ce2d6  test    rsi, rsi
0x1c01ce2d9  jnz     loc_1C01CE363
0x1c01ce2df  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce2e5  mov     esi, 0C000009Ah
0x1c01ce2ea  test    al, al
0x1c01ce2ec  jz      short loc_1C01CE302
0x1c01ce2ee  mov     r8d, 0EEFh
0x1c01ce2f4  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce2fb  mov     ecx, esi; Status
0x1c01ce2fd  call    RefsStatusDebug
0x1c01ce302  mov     r8d, esi
0x1c01ce305  mov     rdx, r14
0x1c01ce308  mov     rcx, r15
0x1c01ce30b  call    RefsExtendedCompleteRequestInternal
0x1c01ce310  lea     rbx, WPP_GLOBAL_Control
0x1c01ce317  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce31e  cmp     rcx, rbx
0x1c01ce321  jz      short loc_1C01CE34A
0x1c01ce323  test    dword ptr [rcx+2Ch], 100h
0x1c01ce32a  jz      short loc_1C01CE34A
0x1c01ce32c  cmp     byte ptr [rcx+29h], 4
0x1c01ce330  jb      short loc_1C01CE34A
0x1c01ce332  mov     edx, 31h ; '1'
0x1c01ce337  mov     r9d, esi
0x1c01ce33a  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce341  mov     rcx, [rcx+18h]
0x1c01ce345  call    WPP_SF_D
0x1c01ce34a  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ce350  test    cl, cl
0x1c01ce352  jz      loc_1C01CEA94
0x1c01ce358  mov     r8d, 0EF0h
0x1c01ce35e  jmp     loc_1C01CEA86
0x1c01ce363  cmp     dword ptr [rbx+10h], 10h
0x1c01ce367  jnb     loc_1C01CE3F1
0x1c01ce36d  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce373  mov     esi, 0C00000E8h
0x1c01ce378  test    al, al
0x1c01ce37a  jz      short loc_1C01CE390
0x1c01ce37c  mov     r8d, 0EFBh
0x1c01ce382  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce389  mov     ecx, esi; Status
0x1c01ce38b  call    RefsStatusDebug
0x1c01ce390  mov     r8d, esi
0x1c01ce393  mov     rdx, r14
0x1c01ce396  mov     rcx, r15
0x1c01ce399  call    RefsExtendedCompleteRequestInternal
0x1c01ce39e  lea     rbx, WPP_GLOBAL_Control
0x1c01ce3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce3ac  cmp     rcx, rbx
0x1c01ce3af  jz      short loc_1C01CE3D8
0x1c01ce3b1  test    dword ptr [rcx+2Ch], 100h
0x1c01ce3b8  jz      short loc_1C01CE3D8
0x1c01ce3ba  cmp     byte ptr [rcx+29h], 4
0x1c01ce3be  jb      short loc_1C01CE3D8
0x1c01ce3c0  mov     edx, 33h ; '3'
0x1c01ce3c5  mov     r9d, esi
0x1c01ce3c8  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce3cf  mov     rcx, [rcx+18h]
0x1c01ce3d3  call    WPP_SF_D
0x1c01ce3d8  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce3de  test    al, al
0x1c01ce3e0  jz      loc_1C01CEA94
0x1c01ce3e6  mov     r8d, 0EFCh
0x1c01ce3ec  jmp     loc_1C01CEA86
0x1c01ce3f1  mov     [rsp+78h+var_48], 1
0x1c01ce3f6  lea     rax, [rsp+78h+arg_10]
0x1c01ce3fe  mov     qword ptr [rsp+78h+Priority], rax
0x1c01ce403  lea     rax, [rsp+78h+arg_18]
0x1c01ce40b  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1c01ce410  lea     r9, [rsp+78h+var_30]
0x1c01ce415  lea     r8, [rsp+78h+arg_8]
0x1c01ce41d  mov     rdx, [rbx+30h]
0x1c01ce421  mov     rcx, r15
0x1c01ce424  call    RefsDecodeFileObject
0x1c01ce429  mov     rax, [rsp+78h+arg_10]
0x1c01ce431  test    rax, rax
0x1c01ce434  jz      loc_1C01CE98A
0x1c01ce43a  movzx   eax, word ptr [rax+58h]
0x1c01ce43e  mov     ecx, 200h
0x1c01ce443  test    cx, ax
0x1c01ce446  jz      loc_1C01CE98A
0x1c01ce44c  mov     eax, [rsi+8]
0x1c01ce44f  test    eax, eax
0x1c01ce451  jnz     short loc_1C01CE486
0x1c01ce453  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce459  test    al, al
0x1c01ce45b  jz      short loc_1C01CE471
0x1c01ce45d  mov     r8d, 0F17h
0x1c01ce463  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce46a  xor     ecx, ecx; Status
0x1c01ce46c  call    RefsStatusDebug
0x1c01ce471  xor     r8d, r8d
0x1c01ce474  mov     rdx, r14
0x1c01ce477  mov     rcx, r15
0x1c01ce47a  call    RefsExtendedCompleteRequestInternal
0x1c01ce47f  xor     eax, eax
0x1c01ce481  jmp     loc_1C01CEA96
0x1c01ce486  test    eax, 0FFFFFFFCh
0x1c01ce48b  jz      loc_1C01CE515
0x1c01ce491  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce497  mov     esi, 0C000000Dh
0x1c01ce49c  test    al, al
0x1c01ce49e  jz      short loc_1C01CE4B4
0x1c01ce4a0  mov     r8d, 0F1Dh
0x1c01ce4a6  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce4ad  mov     ecx, esi; Status
0x1c01ce4af  call    RefsStatusDebug
0x1c01ce4b4  mov     r8d, esi
0x1c01ce4b7  mov     rdx, r14
0x1c01ce4ba  mov     rcx, r15
0x1c01ce4bd  call    RefsExtendedCompleteRequestInternal
0x1c01ce4c2  lea     rbx, WPP_GLOBAL_Control
0x1c01ce4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce4d0  cmp     rcx, rbx
0x1c01ce4d3  jz      short loc_1C01CE4FC
0x1c01ce4d5  test    dword ptr [rcx+2Ch], 100h
0x1c01ce4dc  jz      short loc_1C01CE4FC
0x1c01ce4de  cmp     byte ptr [rcx+29h], 4
0x1c01ce4e2  jb      short loc_1C01CE4FC
0x1c01ce4e4  mov     edx, 35h ; '5'
0x1c01ce4e9  mov     r9d, esi
0x1c01ce4ec  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce4f3  mov     rcx, [rcx+18h]
0x1c01ce4f7  call    WPP_SF_D
0x1c01ce4fc  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ce502  test    cl, cl
0x1c01ce504  jz      loc_1C01CEA94
0x1c01ce50a  mov     r8d, 0F1Eh
0x1c01ce510  jmp     loc_1C01CEA86
0x1c01ce515  mov     rbx, [rsp+78h+arg_8]
0x1c01ce51d  mov     eax, [rbx+4]
0x1c01ce520  bt      eax, 19h
0x1c01ce524  jnb     loc_1C01CE5AE
0x1c01ce52a  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce530  mov     esi, 0C00000A2h
0x1c01ce535  test    al, al
0x1c01ce537  jz      short loc_1C01CE54D
0x1c01ce539  mov     r8d, 0F23h
0x1c01ce53f  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce546  mov     ecx, esi; Status
0x1c01ce548  call    RefsStatusDebug
0x1c01ce54d  mov     r8d, esi
0x1c01ce550  mov     rdx, r14
0x1c01ce553  mov     rcx, r15
0x1c01ce556  call    RefsExtendedCompleteRequestInternal
0x1c01ce55b  lea     rbx, WPP_GLOBAL_Control
0x1c01ce562  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce569  cmp     rcx, rbx
0x1c01ce56c  jz      short loc_1C01CE595
0x1c01ce56e  test    dword ptr [rcx+2Ch], 100h
0x1c01ce575  jz      short loc_1C01CE595
0x1c01ce577  cmp     byte ptr [rcx+29h], 4
0x1c01ce57b  jb      short loc_1C01CE595
0x1c01ce57d  mov     edx, 36h ; '6'
0x1c01ce582  mov     r9d, esi
0x1c01ce585  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce58c  mov     rcx, [rcx+18h]
0x1c01ce590  call    WPP_SF_D
0x1c01ce595  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ce59b  test    cl, cl
0x1c01ce59d  jz      loc_1C01CEA94
0x1c01ce5a3  mov     r8d, 0F24h
0x1c01ce5a9  jmp     loc_1C01CEA86
0x1c01ce5ae  mov     r8b, 1
0x1c01ce5b1  mov     rdx, rbx
0x1c01ce5b4  mov     rcx, r15
0x1c01ce5b7  call    RefsAcquireExclusiveVcb
0x1c01ce5bc  mov     [rsp+78h+var_37], 1
0x1c01ce5c1  mov     ecx, [rbx+4]
0x1c01ce5c4  test    cl, 1
0x1c01ce5c7  jnz     short loc_1C01CE63F
0x1c01ce5c9  lea     rbx, WPP_GLOBAL_Control
0x1c01ce5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce5d7  cmp     rcx, rbx
0x1c01ce5da  jz      short loc_1C01CE606
0x1c01ce5dc  mov     eax, [rcx+2Ch]
0x1c01ce5df  bt      eax, 8
0x1c01ce5e3  jnb     short loc_1C01CE606
0x1c01ce5e5  cmp     byte ptr [rcx+29h], 4
0x1c01ce5e9  jb      short loc_1C01CE606
0x1c01ce5eb  mov     edx, 37h ; '7'
0x1c01ce5f0  mov     r9d, 0C000026Eh
0x1c01ce5f6  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce5fd  mov     rcx, [rcx+18h]
0x1c01ce601  call    WPP_SF_D
0x1c01ce606  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce60c  test    al, al
0x1c01ce60e  jz      short loc_1C01CE627
0x1c01ce610  mov     r8d, 0F3Bh
0x1c01ce616  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce61d  mov     ecx, 0C000026Eh; Status
0x1c01ce622  call    RefsStatusDebug
0x1c01ce627  mov     [rsp+78h+Status], 0C000026Eh
0x1c01ce632  mov     rbx, [rsp+78h+arg_8]
0x1c01ce63a  jmp     loc_1C01CE914
0x1c01ce63f  mov     eax, [rsi+8]
0x1c01ce642  test    al, 1
0x1c01ce644  jz      loc_1C01CE7A3
0x1c01ce64a  bt      ecx, 14h
0x1c01ce64e  jnb     short loc_1C01CE6BE
0x1c01ce650  lea     rbx, WPP_GLOBAL_Control
0x1c01ce657  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce65e  cmp     rcx, rbx
0x1c01ce661  jz      short loc_1C01CE68D
0x1c01ce663  mov     eax, [rcx+2Ch]
0x1c01ce666  bt      eax, 8
0x1c01ce66a  jnb     short loc_1C01CE68D
0x1c01ce66c  cmp     byte ptr [rcx+29h], 4
0x1c01ce670  jb      short loc_1C01CE68D
0x1c01ce672  mov     edx, 38h ; '8'
0x1c01ce677  mov     r9d, 0C00002B7h
0x1c01ce67d  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce684  mov     rcx, [rcx+18h]
0x1c01ce688  call    WPP_SF_D
0x1c01ce68d  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce693  test    al, al
0x1c01ce695  jz      short loc_1C01CE6AE
0x1c01ce697  mov     r8d, 0F4Dh
0x1c01ce69d  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce6a4  mov     ecx, 0C00002B7h; Status
0x1c01ce6a9  call    RefsStatusDebug
0x1c01ce6ae  mov     [rsp+78h+Status], 0C00002B7h
0x1c01ce6b9  jmp     loc_1C01CE632
0x1c01ce6be  bt      ecx, 15h
0x1c01ce6c2  jb      short loc_1C01CE6CE
0x1c01ce6c4  cmp     [rbx+28h], rdi
0x1c01ce6c8  jz      loc_1C01CE7A3
0x1c01ce6ce  mov     r8, [rbx+28h]
0x1c01ce6d2  test    r8, r8
0x1c01ce6d5  jz      short loc_1C01CE753
0x1c01ce6d7  mov     rax, [rbx+360h]
0x1c01ce6de  cmp     [rsi], rax
0x1c01ce6e1  jz      short loc_1C01CE753
0x1c01ce6e3  lea     rbx, WPP_GLOBAL_Control
0x1c01ce6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ce6f1  cmp     rcx, rbx
0x1c01ce6f4  jz      short loc_1C01CE724
0x1c01ce6f6  mov     eax, [rcx+2Ch]
0x1c01ce6f9  bt      eax, 8
0x1c01ce6fd  jnb     short loc_1C01CE724
0x1c01ce6ff  cmp     byte ptr [rcx+29h], 4
0x1c01ce703  jb      short loc_1C01CE724
0x1c01ce705  mov     edx, 39h ; '9'
0x1c01ce70a  mov     esi, 0C000000Dh
0x1c01ce70f  mov     r9d, esi
0x1c01ce712  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01ce719  mov     rcx, [rcx+18h]
0x1c01ce71d  call    WPP_SF_D
0x1c01ce722  jmp     short loc_1C01CE729
0x1c01ce724  mov     esi, 0C000000Dh
0x1c01ce729  mov     al, cs:RefsStatusDebugEnabled
0x1c01ce72f  test    al, al
0x1c01ce731  jz      short loc_1C01CE747
0x1c01ce733  mov     r8d, 0F5Fh
0x1c01ce739  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01ce740  mov     ecx, esi; Status
0x1c01ce742  call    RefsStatusDebug
0x1c01ce747  mov     [rsp+78h+Status], esi
0x1c01ce74e  jmp     loc_1C01CE632
0x1c01ce753  mov     rdx, rbx
0x1c01ce756  mov     rcx, r15
0x1c01ce759  call    RefsDeactivateUsnJournal
0x1c01ce75e  mov     eax, [rsi+8]
0x1c01ce761  test    al, 2
  ... truncated ...
```
