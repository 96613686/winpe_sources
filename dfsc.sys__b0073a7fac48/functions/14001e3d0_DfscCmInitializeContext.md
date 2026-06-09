# DfscCmInitializeContext

- ea: `0x14001e3d0`
- end: `0x14001ef12`
- name: `DfscCmInitializeContext`
- size: `2882`
- prototype: `__int64 __fastcall(IRP *, volatile signed __int32 *, __int64, IRP *, IRP **Size, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1400015c0`
- `0x14001d9b0`

## callees

- `0x14000141c`
- `0x140002570`
- `0x1400025f4`
- `0x140003438`
- `0x140003568`
- `0x140005e96`
- `0x140006080`
- `0x140006380`
- `0x14001e3d0`
- `0x14001f040`
- `0x14001f540`
- `0x14001f8a0`
- `0x1400213b0`
- `0x140023410`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001ecbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ecd2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ecbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ecd2`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001e676`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001e688`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001ea09`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001e676`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001e688`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001ea09`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14001e90d`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14001e90d`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001e93f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001e93f`
- `ntoskrnl!PsReferenceSiloContext` at `0x14001eeba`
- `ntoskrnl!PsReferenceSiloContext` at `0x14001eeba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e54c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e54c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e540`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e540`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001e4fe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001e4fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e4e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e4e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ee81`
- `ntoskrnl!ExAllocatePool2` at `0x14001e43b`
- `ntoskrnl!ExAllocatePool2` at `0x14001e4b3`
- `ntoskrnl!ExAllocatePool2` at `0x14001e6f9`
- `ntoskrnl!ExAllocatePool2` at `0x14001e775`
- `ntoskrnl!ExAllocatePool2` at `0x14001ea78`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb1c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e43b`
- `ntoskrnl!ExAllocatePool2` at `0x14001e4b3`
- `ntoskrnl!ExAllocatePool2` at `0x14001e6f9`
- `ntoskrnl!ExAllocatePool2` at `0x14001e775`
- `ntoskrnl!ExAllocatePool2` at `0x14001ea78`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb1c`

## pseudocode

```c
__int64 __fastcall DfscCmInitializeContext(
        IRP *a1,
        volatile signed __int32 *a2,
        __int64 a3,
        IRP *a4,
        IRP **Size,
        __int64 a6,
        _QWORD *a7)
{
  IRP *v10; // r12
  __int64 Pool2; // rax
  IRP *v12; // r15
  IRP *v13; // rax
  _WORD *MdlAddress; // rax
  __int64 v15; // rax
  __int64 v16; // r9
  char *v17; // rbx
  _QWORD *v18; // rcx
  __int64 v19; // rcx
  __int128 v20; // xmm6
  volatile signed __int32 *v21; // r13
  __int64 v22; // r8
  int v23; // edi
  IRP *v24; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned __int16 v26; // r13
  WCHAR *v27; // rax
  unsigned int v28; // eax
  size_t v29; // rax
  volatile signed __int32 *v30; // rax
  struct _UNICODE_STRING v31; // xmm0
  unsigned int Length; // eax
  int v33; // eax
  __int64 v34; // r13
  IRP *v35; // rax
  NTSTATUS v37; // eax
  char *i; // rcx
  unsigned int *v39; // rcx
  unsigned __int16 v40; // cx
  void *v41; // rax
  volatile signed __int32 *v42; // rax
  int v43; // ecx
  size_t v44; // r8
  struct _ECP_LIST *v45; // rdx
  struct _UNICODE_STRING v46; // xmm0
  int v47; // eax
  __int64 v48; // rax
  PMDL v49; // rdx
  int v50; // edx
  int v51; // ecx
  PMDL v52; // rcx
  size_t MappedSystemVa; // [rsp+48h] [rbp-A1h]
  __int16 v54; // [rsp+48h] [rbp-A1h]
  const char *v55; // [rsp+48h] [rbp-A1h]
  size_t v56; // [rsp+48h] [rbp-A1h]
  __int16 v57; // [rsp+48h] [rbp-A1h]
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+50h] [rbp-99h] BYREF
  PVOID EcpContext; // [rsp+58h] [rbp-91h] BYREF
  struct _UNICODE_STRING v60; // [rsp+68h] [rbp-81h]
  size_t v61[2]; // [rsp+78h] [rbp-71h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-61h] BYREF
  void *Src[2]; // [rsp+98h] [rbp-51h] BYREF
  struct _UNICODE_STRING v64; // [rsp+A8h] [rbp-41h] BYREF
  struct _UNICODE_STRING v65; // [rsp+B8h] [rbp-31h] BYREF
  __int128 v66; // [rsp+C8h] [rbp-21h] BYREF
  _OWORD v67[5]; // [rsp+D8h] [rbp-11h] BYREF
  int Sizea; // [rsp+158h] [rbp+6Fh]
  size_t Sizeb; // [rsp+158h] [rbp+6Fh]
  int Sizec; // [rsp+158h] [rbp+6Fh]
  size_t Sized; // [rsp+158h] [rbp+6Fh]
  unsigned __int16 Sizee; // [rsp+158h] [rbp+6Fh]
  int Sizef; // [rsp+158h] [rbp+6Fh]

  v66 = 0;
  *(_OWORD *)Src = 0;
  if ( !Size )
  {
    v10 = 0;
    v12 = 0;
LABEL_9:
    Sizea = 0;
    MappedSystemVa = 0;
    goto LABEL_10;
  }
  v10 = *Size;
  Pool2 = ExAllocatePool2(258, 16, 1195599428);
  v12 = (IRP *)Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, Pool2);
  *(_OWORD *)&v12->Type = 0;
  v13 = Size[2];
  a4 = Size[3];
  Size[11] = v12;
  if ( v13->Type < 8u )
    goto LABEL_9;
  MdlAddress = v13->MdlAddress;
  if ( *MdlAddress != 92 || MdlAddress[1] != 59 || MdlAddress[3] != 58 )
    goto LABEL_9;
  v23 = DfscNetUseIncrementOpenHandleCount(a3, Size[5], v12, *Size);
  if ( (int)(v23 + 0x80000000) >= 0 && v23 != -1073741772 )
  {
    v34 = a3;
    v17 = 0;
LABEL_97:
    v49 = v12->MdlAddress;
    if ( v49 )
    {
      LOBYTE(v16) = 1;
      DfscNetUseRelease(v34, v49, 0, v16);
    }
    DfscCmReleaseHandleContext(v12);
    Size[11] = 0;
    goto LABEL_49;
  }
  v52 = v12->MdlAddress;
  if ( !v52 )
    goto LABEL_9;
  Sizea = HIDWORD(v52[3].Next);
  MappedSystemVa = (size_t)v52[3].MappedSystemVa;
LABEL_10:
  v15 = ExAllocatePool2(258, 384, 1833133636);
  v17 = (char *)v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids);
    }
    v23 = -1073741670;
    goto LABEL_95;
  }
  memset((void *)(v15 + 8), 0, 0x178u);
  *(_DWORD *)v17 = 25198850;
  *((_DWORD *)v17 + 1) = 1;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement, 1u);
  v18 = (_QWORD *)qword_14000C720;
  if ( *(__int64 **)qword_14000C720 != &qword_14000C718 )
    __fastfail(3u);
  *((_QWORD *)v17 + 47) = qword_14000C720;
  *((_QWORD *)v17 + 46) = &qword_14000C718;
  *v18 = v17 + 368;
  qword_14000C720 = (__int64)(v17 + 368);
  ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v17);
  *((_DWORD *)v17 + 79) = 0;
  *((_DWORD *)v17 + 81) = 0;
  *((_QWORD *)v17 + 41) = Size;
  *((_QWORD *)v17 + 42) = v10;
  *((_DWORD *)v17 + 73) = 0;
  if ( v10 )
  {
    ExtraCreateParameter = 0;
    EcpContext = 0;
    if ( IoGetIrpExtraCreateParameter(v10, &ExtraCreateParameter) )
    {
      v23 = -1073741595;
    }
    else
    {
      if ( !ExtraCreateParameter )
        goto LABEL_101;
      EcpContext = 0;
      v37 = FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_NETWORK_OPEN_CONTEXT, &EcpContext, 0);
      v23 = v37;
      if ( v37 == -1073741275 )
      {
        *((_DWORD *)v17 + 60) = 0;
        goto LABEL_16;
      }
      if ( !v37 )
      {
LABEL_101:
        if ( EcpContext )
        {
          v50 = *((_DWORD *)EcpContext + 2);
          if ( v50 == 3 )
          {
            v51 = 6;
          }
          else
          {
            v51 = 0;
            if ( v50 == 2 )
              v51 = 2;
          }
          if ( (*((_DWORD *)EcpContext + 3) & 8) != 0 )
            v51 |= 1u;
          *((_DWORD *)v17 + 60) = v51;
        }
        goto LABEL_16;
      }
    }
LABEL_54:
    v34 = a3;
    goto LABEL_48;
  }
LABEL_16:
  *((_DWORD *)v17 + 60) |= Sizea;
  v19 = MappedSystemVa;
  if ( a6 )
    v19 = a6;
  *((_QWORD *)v17 + 33) = v19;
  v66 = 0;
  v20 = *(_OWORD *)&a4->Type;
  v21 = a2;
  v67[0] = v20;
  if ( a2 )
    _InterlockedIncrement(a2 + 1);
  if ( (unsigned int)DfscGetPathComponents(v67, Src, 0, 0, 0) || !LOWORD(Src[0]) || !Src[1] || !*(_WORD *)Src[1] )
  {
    v23 = -1073741802;
LABEL_95:
    v34 = a3;
    goto LABEL_96;
  }
  if ( a2 )
    goto LABEL_43;
  v23 = -1073741670;
  if ( v10 )
  {
    v24 = v10;
  }
  else
  {
    v24 = a1;
    if ( !a1 )
      goto LABEL_29;
  }
  CurrentStackLocation = v24->Tail.Overlay.CurrentStackLocation;
  v21 = 0;
  ExtraCreateParameter = (struct _ECP_LIST *)v24;
  *(_QWORD *)&v60.Length = CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction || !CurrentStackLocation->Parameters.Create.EaLength )
  {
LABEL_29:
    DestinationString = 0;
    v64 = 0;
    RtlInitUnicodeStringEx(&DestinationString, 0);
    RtlInitUnicodeStringEx(&v64, 0);
    v26 = (unsigned __int16)Src[0];
    v60 = 0;
    if ( LOWORD(Src[0]) )
    {
      v60.MaximumLength = (USHORT)Src[0];
      Sizeb = LOWORD(Src[0]);
      v60.Length = (USHORT)Src[0];
      v61[0] = 2 * ((unsigned __int64)LOWORD(Src[0]) >> 1);
      if ( *(_WORD *)((char *)Src[1] + v61[0] - 2) )
      {
        v26 = LOWORD(Src[0]) + 2;
        v60.MaximumLength = LOWORD(Src[0]) + 2;
        if ( (unsigned __int16)(LOWORD(Src[0]) + 2) < LOWORD(Src[0]) )
          goto LABEL_129;
      }
      v27 = (WCHAR *)ExAllocatePool2(258, v26, 2017683012);
      v60.Buffer = v27;
      if ( !v27 )
        goto LABEL_129;
      memmove(v27, Src[1], Sizeb);
      if ( (unsigned __int16)Sizeb < v26 )
        *(PWSTR)((char *)v60.Buffer + v61[0]) = 0;
      DestinationString = v60;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, 0);
    }
    Sizec = 0;
    v28 = (DestinationString.Length + 23) & 0xFFFFFFFC;
    LODWORD(EcpContext) = v28;
    if ( v28 > 0xFFFF )
    {
      v23 = -1073741811;
    }
    else
    {
      v29 = v28 + 88;
      v54 = v29;
      v61[0] = v29;
      v30 = (volatile signed __int32 *)ExAllocatePool2(66, (unsigned int)v29, 2017683012);
      v21 = v30;
      if ( v30 )
      {
        memset((void *)v30, 0, v61[0]);
        *((_WORD *)v21 + 1) = v54;
        *(_WORD *)v21 = -32508;
        *((_DWORD *)v21 + 1) = 1;
        v31 = DestinationString;
        *((_QWORD *)v21 + 3) = 0;
        *(struct _UNICODE_STRING *)(v21 + 2) = v31;
        qmemcpy((void *)(v21 + 22), "Principal", 9);
        *((_BYTE *)v21 + 85) = 11;
        Length = DestinationString.Length;
        *((_WORD *)v21 + 43) = DestinationString.Length;
        memmove((void *)(v21 + 25), DestinationString.Buffer, Length);
        v33 = (int)EcpContext;
        *((_DWORD *)v21 + 20) = 0;
        *((_DWORD *)v21 + 18) = v33;
        *(struct _UNICODE_STRING *)(v21 + 14) = v64;
        v23 = 0;
        goto LABEL_39;
      }
    }
LABEL_129:
    Sizec = v23;
    if ( DestinationString.Buffer )
    {
      ExFreePoolWithTag(DestinationString.Buffer, 0);
      DestinationString.Buffer = 0;
    }
    if ( v64.Buffer )
    {
      ExFreePoolWithTag(v64.Buffer, 0);
      v64.Buffer = 0;
    }
    v21 = 0;
LABEL_39:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v21);
    }
    if ( !Sizec )
      goto LABEL_43;
    goto LABEL_54;
  }
  for ( i = (char *)v24->AssociatedIrp.MasterIrp; ; i = (char *)v39 + v48 )
  {
    Sized = (size_t)i;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v22, i + 8);
      i = (char *)Sized;
    }
    v55 = i + 8;
    if ( !strcmp_0(i + 8, "Principal")
      || !strcmp_0(v55, "UserName")
      || !strcmp_0(v55, "Password")
      || !strcmp_0(v55, "AuthIdentity") )
    {
      break;
    }
    v39 = (unsigned int *)Sized;
LABEL_91:
    v48 = *v39;
    if ( !(_DWORD)v48 )
      goto LABEL_29;
  }
  v39 = (unsigned int *)Sized;
  if ( !*(_WORD *)(Sized + 6) )
    goto LABEL_91;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids);
  v65 = 0;
  LODWORD(EcpContext) = *(_DWORD *)(*(_QWORD *)&v60.Length + 32LL);
  v64 = 0;
  ExtraCreateParameter = (struct _ECP_LIST *)*((_QWORD *)ExtraCreateParameter + 3);
  RtlInitUnicodeStringEx(&v65, 0);
  v40 = (unsigned __int16)Src[0];
  Sizee = (unsigned __int16)Src[0];
  *(_OWORD *)v61 = 0;
  if ( !LOWORD(Src[0]) )
  {
    RtlInitUnicodeString(&v65, 0);
    goto LABEL_77;
  }
  WORD1(v61[0]) = Src[0];
  v56 = LOWORD(Src[0]);
  LOWORD(v61[0]) = Src[0];
  *(_QWORD *)&v60.Length = 2 * ((unsigned __int64)LOWORD(Src[0]) >> 1);
  if ( *(_WORD *)((char *)Src[1] + *(_QWORD *)&v60.Length - 2)
    && (v40 = LOWORD(Src[0]) + 2,
        Sizee = LOWORD(Src[0]) + 2,
        WORD1(v61[0]) = LOWORD(Src[0]) + 2,
        (unsigned __int16)(LOWORD(Src[0]) + 2) < LOWORD(Src[0])) )
  {
    v47 = -1073741670;
  }
  else
  {
    v41 = (void *)ExAllocatePool2(258, v40, 2017683012);
    v61[1] = (size_t)v41;
    if ( v41 )
    {
      memmove(v41, Src[1], v56);
      if ( (unsigned __int16)v56 < Sizee )
        *(_WORD *)(v61[1] + *(_QWORD *)&v60.Length) = 0;
      v65 = *(struct _UNICODE_STRING *)v61;
LABEL_77:
      Sizef = 0;
      if ( (unsigned int)EcpContext > 0xFFFF
        || (v61[0] = (unsigned int)EcpContext,
            *((unsigned __int8 *)ExtraCreateParameter + 5)
          + (unsigned __int64)*((unsigned __int16 *)ExtraCreateParameter + 3)
          + 9 > (unsigned int)EcpContext)
        || (v57 = (_WORD)EcpContext + 88, (unsigned int)((_DWORD)EcpContext + 88) > 0xFFFF) )
      {
        v47 = -1073741811;
      }
      else
      {
        *(_QWORD *)&DestinationString.Length = (unsigned int)((_DWORD)EcpContext + 88);
        v42 = (volatile signed __int32 *)ExAllocatePool2(66, *(_QWORD *)&DestinationString.Length, 2017683012);
        if ( v42 )
        {
          v21 = v42;
          memset((void *)v42, 0, *(size_t *)&DestinationString.Length);
          v43 = (int)EcpContext;
          v44 = v61[0];
          v45 = ExtraCreateParameter;
          *((_WORD *)v21 + 1) = v57;
          *(_WORD *)v21 = -32508;
          *((_DWORD *)v21 + 1) = 1;
          *((_QWORD *)v21 + 3) = 0;
          v46 = v65;
          *((_DWORD *)v21 + 18) = v43;
          *(struct _UNICODE_STRING *)(v21 + 2) = v46;
          memmove((void *)(v21 + 20), v45, v44);
          v64.MaximumLength = *((_WORD *)ExtraCreateParameter + 3);
          v64.Length = v64.MaximumLength;
          v64.Buffer = (PWSTR)((char *)ExtraCreateParameter + *((unsigned __int8 *)ExtraCreateParameter + 5) + 9);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_ZsZq(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned int)&v64,
              (_DWORD)WPP_GLOBAL_Control,
              (_DWORD)v21 + 8,
              (__int64)ExtraCreateParameter + 8,
              (__int64)&v64,
              (char)v21);
          }
LABEL_84:
          v47 = Sizef;
          goto LABEL_85;
        }
        v47 = -1073741670;
      }
    }
    else
    {
      v47 = -1073741670;
    }
  }
  Sizef = v47;
  if ( v65.Buffer )
  {
    ExFreePoolWithTag(v65.Buffer, 0);
    goto LABEL_84;
  }
LABEL_85:
  if ( v47 )
    goto LABEL_29;
LABEL_43:
  *((_QWORD *)v17 + 29) = v21;
  v34 = a3;
  *((_QWORD *)v17 + 1) = Size;
  *((_QWORD *)v17 + 31) = a3;
  *(_OWORD *)(v17 + 296) = v20;
  if ( a3 )
    PsReferenceSiloContext(a3);
  v35 = a1;
  *((_WORD *)v17 + 112) = -1;
  if ( v10 )
    v35 = v10;
  *((_QWORD *)v17 + 32) = v35;
  v23 = DfscRewritePath(v17, v67, &v66, 0);
LABEL_48:
  if ( v23 < 0 )
  {
LABEL_96:
    if ( !v12 )
      goto LABEL_49;
    goto LABEL_97;
  }
LABEL_49:
  if ( v17 )
  {
    if ( v23 < 0 )
      DfscCmReleaseContext(v17);
    else
      *a7 = v17;
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14001e3d0  mov     rax, rsp
0x14001e3d3  mov     [rax+20h], rbx
0x14001e3d7  mov     [rax+18h], r8
0x14001e3db  mov     [rax+10h], rdx
0x14001e3df  mov     [rax+8], rcx
0x14001e3e3  push    rbp
0x14001e3e4  push    rsi
0x14001e3e5  push    rdi
0x14001e3e6  push    r12
0x14001e3e8  push    r13
0x14001e3ea  push    r14
0x14001e3ec  push    r15
0x14001e3ee  lea     rbp, [rax-47h]
0x14001e3f2  sub     rsp, 0F0h
0x14001e3f9  mov     rsi, [rbp+3Fh+Size]
0x14001e3fd  lea     rdi, WPP_GLOBAL_Control
0x14001e404  xor     r14d, r14d
0x14001e407  movaps  xmmword ptr [rax-48h], xmm6
0x14001e40b  xorps   xmm0, xmm0
0x14001e40e  xorps   xmm1, xmm1
0x14001e411  mov     r13, r9
0x14001e414  mov     rbx, r8
0x14001e417  movups  [rbp+3Fh+var_60], xmm0
0x14001e41b  movups  xmmword ptr [rbp+3Fh+Src], xmm1
0x14001e41f  test    rsi, rsi
0x14001e422  jz      loc_14001EC33
0x14001e428  mov     r12, [rsi]
0x14001e42b  mov     edx, 10h
0x14001e430  mov     ecx, 102h
0x14001e435  mov     r8d, 47436644h
0x14001e43b  call    cs:__imp_ExAllocatePool2
0x14001e442  nop     dword ptr [rax+rax+00h]
0x14001e447  mov     r15, rax
0x14001e44a  test    rax, rax
0x14001e44d  jz      loc_14001ED84
0x14001e453  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e45a  cmp     rcx, rdi
0x14001e45d  jz      short loc_14001E46C
0x14001e45f  test    dword ptr [rcx+2Ch], 400000h
0x14001e466  jnz     loc_14001ED57
0x14001e46c  xorps   xmm0, xmm0
0x14001e46f  movups  xmmword ptr [r15], xmm0
0x14001e473  mov     rax, [rsi+10h]
0x14001e477  mov     r13, [rsi+18h]
0x14001e47b  mov     [rsi+58h], r15
0x14001e47f  cmp     word ptr [rax], 8
0x14001e483  jb      short loc_14001E49A
0x14001e485  mov     rax, [rax+8]
0x14001e489  cmp     word ptr [rax], 5Ch ; '\'
0x14001e48d  jnz     short loc_14001E49A
0x14001e48f  cmp     word ptr [rax+2], 3Bh ; ';'
0x14001e494  jz      loc_14001ED74
0x14001e49a  mov     dword ptr [rbp+3Fh+Size], r14d
0x14001e49e  mov     [rsp+120h+var_E0], r14
0x14001e4a3  mov     edx, 180h
0x14001e4a8  mov     ecx, 102h
0x14001e4ad  mov     r8d, 6D436644h
0x14001e4b3  call    cs:__imp_ExAllocatePool2
0x14001e4ba  nop     dword ptr [rax+rax+00h]
0x14001e4bf  mov     rbx, rax
0x14001e4c2  test    rax, rax
0x14001e4c5  jz      loc_14001E8E1
0x14001e4cb  lea     rcx, [rax+8]; void *
0x14001e4cf  xor     edx, edx; Val
0x14001e4d1  mov     r8d, 178h; Size
0x14001e4d7  call    memset
0x14001e4dc  mov     dword ptr [rbx], 1808102h
0x14001e4e2  mov     dword ptr [rbx+4], 1
0x14001e4e9  call    cs:__imp_KeEnterCriticalRegion
0x14001e4f0  nop     dword ptr [rax+rax+00h]
0x14001e4f5  mov     dl, 1; Wait
0x14001e4f7  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001e4fe  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001e505  nop     dword ptr [rax+rax+00h]
0x14001e50a  mov     rcx, cs:qword_14000C720
0x14001e511  lea     rdx, qword_14000C718
0x14001e518  cmp     [rcx], rdx
0x14001e51b  jnz     loc_14001ED8E
0x14001e521  lea     rax, [rbx+170h]
0x14001e528  mov     [rax+8], rcx
0x14001e52c  mov     [rax], rdx
0x14001e52f  mov     [rcx], rax
0x14001e532  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001e539  mov     cs:qword_14000C720, rax
0x14001e540  call    cs:__imp_ExReleaseResourceLite
0x14001e547  nop     dword ptr [rax+rax+00h]
0x14001e54c  call    cs:__imp_KeLeaveCriticalRegion
0x14001e553  nop     dword ptr [rax+rax+00h]
0x14001e558  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e55f  cmp     rcx, rdi
0x14001e562  jz      short loc_14001E571
0x14001e564  test    dword ptr [rcx+2Ch], 400000h
0x14001e56b  jnz     loc_14001ED95
0x14001e571  mov     [rbx+13Ch], r14d
0x14001e578  mov     [rbx+144h], r14d
0x14001e57f  mov     [rbx+148h], rsi
0x14001e586  mov     [rbx+150h], r12
0x14001e58d  mov     [rbx+124h], r14d
0x14001e594  test    r12, r12
0x14001e597  jnz     loc_14001E8FB
0x14001e59d  mov     eax, dword ptr [rbp+3Fh+Size]
0x14001e5a0  xorps   xmm0, xmm0
0x14001e5a3  or      [rbx+0F0h], eax
0x14001e5a9  mov     rax, [rbp+3Fh+arg_28]
0x14001e5ad  mov     rcx, [rsp+120h+var_E0]
0x14001e5b2  test    rax, rax
0x14001e5b5  cmovnz  rcx, rax
0x14001e5b9  mov     [rbx+108h], rcx
0x14001e5c0  movups  [rbp+3Fh+var_60], xmm0
0x14001e5c4  movups  xmm6, xmmword ptr [r13+0]
0x14001e5c9  mov     r13, [rbp+3Fh+arg_8]
0x14001e5cd  movups  xmmword ptr [rbp-11h], xmm6
0x14001e5d1  test    r13, r13
0x14001e5d4  jnz     loc_14001EDBC
0x14001e5da  xor     r9d, r9d
0x14001e5dd  mov     [rsp+120h+var_100], r14
0x14001e5e2  xor     r8d, r8d
0x14001e5e5  lea     rdx, [rbp+3Fh+Src]
0x14001e5e9  lea     rcx, [rbp+3Fh+var_50]
0x14001e5ed  call    DfscGetPathComponents
0x14001e5f2  test    eax, eax
0x14001e5f4  jnz     loc_14001EC3E
0x14001e5fa  cmp     word ptr [rbp+3Fh+Src], r14w
0x14001e5ff  jz      loc_14001EC3E
0x14001e605  mov     rax, [rbp+3Fh+Src+8]
0x14001e609  test    rax, rax
0x14001e60c  jz      loc_14001EC3E
0x14001e612  cmp     [rax], r14w
0x14001e616  jz      loc_14001EC3E
0x14001e61c  mov     edi, 0FFFFh
0x14001e621  test    r13, r13
0x14001e624  jnz     loc_14001E83E
0x14001e62a  mov     edi, 0C000009Ah
0x14001e62f  test    r12, r12
0x14001e632  jz      loc_14001ECE3
0x14001e638  mov     rax, r12
0x14001e63b  mov     rcx, [rax+0B8h]
0x14001e642  mov     r13, r14
0x14001e645  mov     [rsp+120h+ExtraCreateParameter], rax
0x14001e64a  mov     qword ptr [rsp+120h+var_C8+8], rcx
0x14001e64f  cmp     [rcx], r14b
0x14001e652  jnz     short loc_14001E65E
0x14001e654  cmp     [rcx+20h], r14d
0x14001e658  ja      loc_14001E964
0x14001e65e  xorps   xmm0, xmm0
0x14001e661  mov     [rbp+3Fh+arg_8], r14
0x14001e665  xorps   xmm1, xmm1
0x14001e668  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x14001e66c  xor     edx, edx; SourceString
0x14001e66e  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x14001e672  movups  xmmword ptr [rbp+3Fh+var_80.Length], xmm1
0x14001e676  call    cs:__imp_RtlInitUnicodeStringEx
0x14001e67d  nop     dword ptr [rax+rax+00h]
0x14001e682  xor     edx, edx; SourceString
0x14001e684  lea     rcx, [rbp+3Fh+var_80]; DestinationString
0x14001e688  call    cs:__imp_RtlInitUnicodeStringEx
0x14001e68f  nop     dword ptr [rax+rax+00h]
0x14001e694  movzx   r13d, word ptr [rbp+3Fh+Src]
0x14001e699  xorps   xmm0, xmm0
0x14001e69c  movups  [rsp+120h+var_C8+8], xmm0
0x14001e6a1  test    r13w, r13w
0x14001e6a5  jz      loc_14001ECB5
0x14001e6ab  mov     eax, r13d
0x14001e6ae  mov     word ptr [rbp+3Fh+var_C8+0Ah], r13w
0x14001e6b3  shr     rax, 1
0x14001e6b6  mov     ecx, r13d
0x14001e6b9  mov     [rbp+3Fh+Size], rcx
0x14001e6bd  mov     word ptr [rsp+120h+var_C8+8], r13w
0x14001e6c3  lea     rdx, [rax+rax]
0x14001e6c7  mov     rax, [rbp+3Fh+Src+8]
0x14001e6cb  mov     [rbp+3Fh+var_B0], rdx
0x14001e6cf  cmp     [rdx+rax-2], r14w
0x14001e6d5  jz      short loc_14001E6EA
0x14001e6d7  add     r13d, 2
0x14001e6db  mov     word ptr [rbp+3Fh+var_C8+0Ah], r13w
0x14001e6e0  cmp     r13w, cx
0x14001e6e4  jb      loc_14001EE58
0x14001e6ea  movzx   edx, r13w
0x14001e6ee  mov     ecx, 102h
0x14001e6f3  mov     r8d, 78436644h
0x14001e6f9  call    cs:__imp_ExAllocatePool2
0x14001e700  nop     dword ptr [rax+rax+00h]
0x14001e705  mov     [rbp+3Fh+var_B8], rax
0x14001e709  test    rax, rax
0x14001e70c  jz      loc_14001EE58
0x14001e712  mov     r8, [rbp+3Fh+Size]; Size
0x14001e716  mov     rcx, rax; void *
0x14001e719  mov     rdx, [rbp+3Fh+Src+8]; Src
0x14001e71d  call    memmove
0x14001e722  cmp     word ptr [rbp+3Fh+Size], r13w
0x14001e727  jnb     short loc_14001E736
0x14001e729  mov     rax, [rbp+3Fh+var_B8]
0x14001e72d  mov     rcx, [rbp+3Fh+var_B0]
0x14001e731  mov     [rax+rcx], r14w
0x14001e736  movaps  xmm0, [rsp+120h+var_C8+8]
0x14001e73b  movdqa  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x14001e740  movzx   eax, [rbp+3Fh+DestinationString.Length]
0x14001e744  add     eax, 17h
0x14001e747  mov     dword ptr [rbp+3Fh+Size], r14d
0x14001e74b  and     eax, 0FFFFFFFCh
0x14001e74e  mov     dword ptr [rsp+120h+EcpContext], eax
0x14001e752  cmp     eax, 0FFFFh
0x14001e757  ja      loc_14001EE53
0x14001e75d  add     eax, 58h ; 'X'
0x14001e760  mov     r8d, 78436644h
0x14001e766  mov     edx, eax
0x14001e768  mov     dword ptr [rsp+120h+var_E0], eax
0x14001e76c  mov     ecx, 42h ; 'B'
0x14001e771  mov     [rbp+3Fh+var_B0], rax
0x14001e775  call    cs:__imp_ExAllocatePool2
0x14001e77c  nop     dword ptr [rax+rax+00h]
0x14001e781  mov     r13, rax
0x14001e784  test    rax, rax
0x14001e787  jz      loc_14001EE58
0x14001e78d  mov     r8, [rbp+3Fh+var_B0]; Size
0x14001e791  xor     edx, edx; Val
0x14001e793  mov     rcx, rax; void *
0x14001e796  call    memset
0x14001e79b  mov     eax, dword ptr [rsp+120h+var_E0]
0x14001e79f  lea     rcx, [r13+64h]; void *
0x14001e7a3  mov     [r13+2], ax
0x14001e7a8  mov     word ptr [r13+0], 8104h
0x14001e7af  mov     dword ptr [r13+4], 1
0x14001e7b7  movups  xmm0, xmmword ptr [rbp+3Fh+DestinationString.Length]
0x14001e7bb  mov     [r13+18h], r14
0x14001e7bf  movups  xmmword ptr [r13+8], xmm0
0x14001e7c4  movsd   xmm0, qword ptr cs:Str2; "Principal"
0x14001e7cc  movsd   qword ptr [r13+58h], xmm0
0x14001e7d2  movzx   eax, byte ptr cs:Str2+8; "l"
0x14001e7d9  mov     [r13+60h], al
0x14001e7dd  mov     byte ptr [r13+55h], 0Bh
0x14001e7e2  movzx   eax, [rbp+3Fh+DestinationString.Length]
0x14001e7e6  mov     [r13+56h], ax
0x14001e7eb  mov     r8d, eax; Size
0x14001e7ee  mov     rdx, [rbp+3Fh+DestinationString.Buffer]; Src
0x14001e7f2  call    memmove
0x14001e7f7  mov     eax, dword ptr [rsp+120h+EcpContext]
0x14001e7fb  mov     [r13+50h], r14d
0x14001e7ff  mov     [r13+48h], eax
0x14001e803  movups  xmm0, xmmword ptr [rbp+3Fh+var_80.Length]
0x14001e807  movups  xmmword ptr [r13+38h], xmm0
0x14001e80c  mov     edi, r14d
0x14001e80f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e816  lea     rax, WPP_GLOBAL_Control
0x14001e81d  cmp     rcx, rax
0x14001e820  jz      short loc_14001E82F
0x14001e822  test    dword ptr [rcx+2Ch], 400000h
0x14001e829  jnz     loc_14001EE9A
0x14001e82f  cmp     dword ptr [rbp+3Fh+Size], r14d
0x14001e833  jnz     loc_14001E8DB
0x14001e839  mov     edi, 0FFFFh
0x14001e83e  mov     [rbx+0E8h], r13
0x14001e845  mov     r13, [rbp+3Fh+arg_10]
0x14001e849  mov     [rbx+8], rsi
0x14001e84d  mov     [rbx+0F8h], r13
0x14001e854  movups  xmmword ptr [rbx+128h], xmm6
0x14001e85b  test    r13, r13
0x14001e85e  jnz     loc_14001EEB7
0x14001e864  mov     rax, [rbp+3Fh+arg_0]
0x14001e868  lea     r8, [rbp+3Fh+var_60]
0x14001e86c  test    r12, r12
0x14001e86f  mov     [rbx+0E0h], di
0x14001e876  lea     rdx, [rbp+3Fh+var_50]
0x14001e87a  mov     rcx, rbx
0x14001e87d  cmovnz  rax, r12
0x14001e881  xor     r9d, r9d
0x14001e884  mov     [rbx+100h], rax
0x14001e88b  call    DfscRewritePath
0x14001e890  mov     edi, eax
0x14001e892  test    edi, edi
0x14001e894  js      loc_14001EC47
0x14001e89a  test    rbx, rbx
0x14001e89d  jnz     short loc_14001E8C5
0x14001e89f  mov     rbx, [rsp+120h+arg_18]
0x14001e8a7  mov     eax, edi
0x14001e8a9  movaps  xmm6, [rsp+120h+var_48+8]
0x14001e8b1  add     rsp, 0F0h
0x14001e8b8  pop     r15
0x14001e8ba  pop     r14
0x14001e8bc  pop     r13
0x14001e8be  pop     r12
0x14001e8c0  pop     rdi
0x14001e8c1  pop     rsi
0x14001e8c2  pop     rbp
0x14001e8c3  retn
0x14001e8c5  test    edi, edi
0x14001e8c7  js      loc_14001EF05
0x14001e8cd  mov     rax, [rbp+3Fh+arg_30]
0x14001e8d1  mov     [rax], rbx
0x14001e8d4  jmp     short loc_14001E89F
0x14001e8d6  mov     edi, 0C00000E5h
0x14001e8db  mov     r13, [rbp+3Fh+arg_10]
0x14001e8df  jmp     short loc_14001E892
0x14001e8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e8e8  cmp     rcx, rdi
0x14001e8eb  jnz     loc_14001EECB
0x14001e8f1  mov     edi, 0C000009Ah
0x14001e8f6  jmp     loc_14001EC43
0x14001e8fb  lea     rdx, [rsp+120h+ExtraCreateParameter]; ExtraCreateParameter
0x14001e900  mov     [rsp+120h+ExtraCreateParameter], r14
  ... truncated ...
```
