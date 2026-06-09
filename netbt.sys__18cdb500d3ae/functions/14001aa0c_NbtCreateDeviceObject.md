# NbtCreateDeviceObject

- ea: `0x14001aa0c`
- end: `0x14001b2ee`
- name: `NbtCreateDeviceObject`
- size: `2274`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, PCUNICODE_STRING@<rdx>, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c70c`
- `0x140045254`
- `0x140047630`

## callees

- `0x140014298`
- `0x14001aa0c`
- `0x14001b2f4`
- `0x140029108`
- `0x140030f40`
- `0x1400400a4`
- `0x140040294`
- `0x140041c38`
- `0x140042330`
- `0x14004256c`
- `0x140042aa0`
- `0x140042b24`
- `0x140042c90`
- `0x14004420c`
- `0x1400456f4`
- `0x14004bf14`
- `0x14005059c`
- `0x140050ce4`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001b1ac`
- `ntoskrnl!IoFreeIrp` at `0x14001b1ac`
- `ntoskrnl!IoDeleteDevice` at `0x14001ac5d`
- `ntoskrnl!IoDeleteDevice` at `0x14001ac5d`
- `ntoskrnl!IoAllocateIrp` at `0x14001b166`
- `ntoskrnl!IoAllocateIrp` at `0x14001b166`
- `ntoskrnl!RtlGUIDFromString` at `0x14001aab8`
- `ntoskrnl!RtlGUIDFromString` at `0x14001aab8`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b26d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b26d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001b145`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001b2a2`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001b145`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001b2a2`
- `ntoskrnl!KeStackAttachProcess` at `0x14001ab9c`
- `ntoskrnl!KeStackAttachProcess` at `0x14001b257`
- `ntoskrnl!KeStackAttachProcess` at `0x14001ab9c`
- `ntoskrnl!KeStackAttachProcess` at `0x14001b257`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001ab7c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b23b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001ab7c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b23b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001aae2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ac00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001addc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001aeff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001af66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001aae2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ac00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001addc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001aeff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001af66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ab26`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ac32`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001aebe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001af26`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001af4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b002`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b051`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ab26`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ac32`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001aebe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001af26`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001af4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b002`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b051`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac4e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b18d`
- `ntoskrnl!ExAllocatePool2` at `0x14001b18d`

## pseudocode

```c
__int64 __fastcall NbtCreateDeviceObject(
        PCUNICODE_STRING SourceString,
        UNICODE_STRING *a2,
        __int64 a3,
        PDEVICE_OBJECT *a4,
        LONG a5)
{
  PDEVICE_OBJECT *v5; // r15
  wchar_t **p_Buffer; // rdi
  int Length; // r8d
  __int64 v11; // rdx
  NTSTATUS v12; // ebx
  KIRQL v13; // bl
  __int16 v14; // ax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  PDEVICE_OBJECT v18; // rbx
  char v19; // r14
  int NewDeviceInfo; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  int v24; // edi
  char v25; // si
  __int64 v26; // rcx
  KIRQL v27; // si
  __int64 v29; // rdx
  CCHAR v30; // dl
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  KIRQL v33; // di
  int v34; // r9d
  unsigned __int64 v35; // r8
  __int64 *v36; // rdx
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  KIRQL v39; // di
  unsigned int inited; // r15d
  __int64 v41; // rcx
  struct _DEVICE_OBJECT *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // rcx
  bool v48; // zf
  __int16 v49; // ax
  int v50; // [rsp+20h] [rbp-81h]
  int v51; // [rsp+28h] [rbp-79h]
  UNICODE_STRING GuidString; // [rsp+50h] [rbp-51h] BYREF
  GUID Guid; // [rsp+60h] [rbp-41h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+70h] [rbp-31h] BYREF

  v5 = a4;
  memset(&ApcState, 0, sizeof(ApcState));
  GuidString = 0;
  Guid = 0;
  if ( a5 != 1 )
  {
    p_Buffer = &SourceString->Buffer;
    if ( a5 != 2 )
    {
      Length = SourceString->Length;
      v11 = 0;
      v12 = -1073741811;
      while ( (unsigned int)v11 < SourceString->Length >> 1 )
      {
        if ( (*p_Buffer)[v11] == 123 )
        {
          GuidString.Buffer = &(*p_Buffer)[v11];
          GuidString.Length = Length - 2 * v11;
          GuidString.MaximumLength = GuidString.Length;
          v12 = RtlGUIDFromString(&GuidString, &Guid);
          break;
        }
        v11 = (unsigned int)(v11 + 1);
      }
      if ( (xmmword_140038420 & 8) != 0 )
        WPP_SF_ZZ_guid_((_DWORD)SourceString, v11, Length, (_DWORD)SourceString, (__int64)&GuidString, (__int64)&Guid);
      if ( v12 < 0 )
      {
        if ( (BYTE3(xmmword_140038420) & 1) != 0 )
          WPP_SF_Z(1048, 18, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, SourceString);
        return (unsigned int)v12;
      }
    }
    v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v14 = word_1400395BA;
    if ( (unsigned __int16)word_1400395BA >= 0x40u )
    {
      KeReleaseSpinLock(&SpinLock, v13);
      if ( (BYTE3(xmmword_140038420) & 1) != 0 )
        WPP_SF_Sd(v44, v43, v45, *p_Buffer);
      return 3221225626LL;
    }
    ++word_1400395BA;
    if ( !v14 )
    {
      KeReleaseSpinLock(&SpinLock, v13);
      inited = InitTimersNotOs();
      v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      if ( inited )
      {
        if ( !--word_1400395BA )
        {
          LOBYTE(v41) = 1;
          StopInitTimers(v41);
          KeReleaseSpinLock(&SpinLock, v13);
          if ( (BYTE3(xmmword_140038420) & 1) != 0 )
            WPP_SF_S(1048, 20, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, *p_Buffer);
          LOWORD(v51) = 0;
          LOWORD(v50) = 0;
          NbtLogEventDetailed(3221229782LL, inited, 274, 0, v50, v51);
          return inited;
        }
      }
      v5 = a4;
    }
    KeReleaseSpinLock(&SpinLock, v13);
  }
  v15 = NbtAllocAndInitDevice(SourceString, a2, v5, a5);
  v12 = v15;
  if ( v15 < 0 )
  {
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      WPP_SF_d(1048, 21, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, (unsigned int)v15);
    v39 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    if ( a5 != 1 )
    {
      v46 = 0xFFFF;
      if ( !--word_1400395BA )
      {
        LOBYTE(v46) = 1;
        StopInitTimers(v46);
      }
    }
    KeReleaseSpinLock(&SpinLock, v39);
    return (unsigned int)v12;
  }
  v18 = *v5;
  if ( a3 )
  {
    v16 = 0;
    LODWORD(v18[1].DeviceQueue.DeviceListHead.Flink) = *(_DWORD *)a3;
    HIDWORD(v18[1].DeviceQueue.DeviceListHead.Flink) = *(_DWORD *)(a3 + 4);
    LOWORD(v18[2].DeviceQueue.Lock) = 0;
    LODWORD(v18[1].Dpc.ProcessorHistory) = *(unsigned __int16 *)(a3 + 48);
    if ( *(_WORD *)(a3 + 48) )
    {
      do
      {
        v47 = (int)v16;
        v16 = (unsigned int)(v16 + 1);
        *((_DWORD *)&v18[1].DeviceQueue.DeviceListHead.Blink + v47) = *(_DWORD *)(a3 + 4 * v47 + 8);
      }
      while ( (int)v16 < *(unsigned __int16 *)(a3 + 48) );
    }
    v17 = *(unsigned __int8 *)(a3 + 52);
    v18[2].DeviceQueue.Busy = v17;
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      WPP_SF_Zd(1048, 22, (unsigned int)WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, (_DWORD)v18 + 472, v17);
    *((_DWORD *)&v18[2].DeviceQueue.1 + 1) = *(_DWORD *)(a3 + 56);
    BYTE4(v18[2].Dpc.DeferredContext) = *(_BYTE *)(a3 + 60);
    if ( (NodeType & 0x1000) != 0 && (*(_DWORD *)a3 || *(_DWORD *)(a3 + 4)) )
      NodeType = NodeType & 0x10 | 8;
  }
  else
  {
    v18[2].DeviceQueue.Busy = 1;
    *((_DWORD *)&v18[2].DeviceQueue.1 + 1) = 0;
    BYTE4(v18[2].Dpc.DeferredContext) = 0;
  }
  if ( (PRKPROCESS)PsGetCurrentProcess(v17, v16, 0) == NbtFspProcess )
  {
    v19 = 0;
  }
  else
  {
    KeStackAttachProcess(NbtFspProcess, &ApcState);
    v19 = 1;
  }
  NewDeviceInfo = NbtTdiOpenControl(v18);
  v24 = NewDeviceInfo;
  if ( NewDeviceInfo >= 0 )
  {
    NewDeviceInfo = NbtGetNewDeviceInfo(v18, &Guid);
    v24 = NewDeviceInfo;
    if ( NewDeviceInfo >= 0 || (BYTE3(xmmword_140038420) & 1) == 0 )
      goto LABEL_21;
    v29 = 23;
    goto LABEL_31;
  }
  if ( (BYTE3(xmmword_140038420) & 1) != 0 )
  {
    v29 = 24;
LABEL_31:
    WPP_SF_d(1048, v29, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, (unsigned int)NewDeviceInfo);
  }
LABEL_21:
  if ( v19 )
    KeUnstackDetachProcess(&ApcState);
  if ( v24 < 0 )
  {
LABEL_24:
    v25 = 0;
    if ( v18[1].DeviceObjectExtension )
    {
      if ( (PRKPROCESS)PsGetCurrentProcess(v22, v21, v23) != NbtFspProcess )
      {
        KeStackAttachProcess(NbtFspProcess, &ApcState);
        v25 = 1;
      }
      ObfDereferenceObject(*(&v18[1].Reserved + 1));
      NTZwCloseFile(v18[1].DeviceObjectExtension);
      *((_QWORD *)&v18[1].Reserved + 1) = 0;
      v18[1].DeviceObjectExtension = 0;
      if ( v25 )
        KeUnstackDetachProcess(&ApcState);
    }
    v27 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    if ( a5 == 1 )
    {
      if ( word_1400395BA )
      {
LABEL_27:
        KeReleaseSpinLock(&SpinLock, v27);
        *v5 = 0;
        ExFreePoolWithTag(v18[1].Queue.Wcb.BufferChainingDpc, 0);
        IoDeleteDevice(v18);
        NbtLogDeviceCreationFailure((unsigned int)v24, 275, SourceString->Buffer);
        return (unsigned int)v24;
      }
    }
    else
    {
      v26 = 0xFFFF;
      v48 = word_1400395BA == 1;
      v49 = --word_1400395BA;
      if ( !v48 )
      {
        if ( v49 == 1 )
          LOBYTE(word_140039670) = 0;
        goto LABEL_27;
      }
    }
    LOBYTE(v26) = 1;
    StopInitTimers(v26);
    goto LABEL_27;
  }
  v30 = *((_BYTE *)v18[1].Reserved + 76) + 1;
  v18->StackSize = v30;
  if ( (unsigned __int8)StackSize < v30 )
    StackSize = v30;
  if ( !Irp )
  {
    Irp = IoAllocateIrp(v18->StackSize, 0);
    if ( Irp )
    {
      Dpc = (PVOID)ExAllocatePool2(64, 64, 1635017294);
      if ( !Dpc )
      {
        IoFreeIrp(Irp);
        Irp = 0;
      }
    }
    if ( !Irp || !Dpc )
    {
      if ( (BYTE3(xmmword_140038420) & 1) != 0 )
        WPP_SF_(1048, 25, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids);
      v24 = -1073741670;
      goto LABEL_24;
    }
  }
  v18->Flags &= ~0x80u;
  v18[2].Dpc.TargetInfoAsUlong = 8978571;
  *((_WORD *)&v18[2].Dpc.0 + 2) = 138;
  *(_OWORD *)((char *)&v18[2].Dpc.0 + 6) = 0;
  v31 = -MEMORY[0xFFFFF78000000014];
  if ( MEMORY[0xFFFFF78000000014] > 0 )
    v31 = MEMORY[0xFFFFF78000000014];
  v32 = v31 / 0x2710;
  if ( MEMORY[0xFFFFF78000000014] < 0 )
    v32 = -(__int64)v32;
  LODWORD(v18[1].Dpc.DpcData) = v32;
  v33 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( v18[1].ReferenceCount == 1 )
  {
    v34 = 0;
    v35 = -1;
  }
  else
  {
    if ( a5 != 2 )
      *(GUID *)&v18[2].Queue.Wcb.DeviceRoutine = Guid;
    v34 = 1;
    v35 = 1;
    if ( (__int64 *)NbtConfig != &NbtConfig )
    {
      v36 = &NbtConfig;
      while ( 1 )
      {
        v36 = (__int64 *)*v36;
        if ( v36 == &NbtConfig )
          break;
        v37 = v36[27];
        if ( v37 > v35 )
        {
          v18[1].DriverObject = (struct _DRIVER_OBJECT *)v36;
          v18[1].NextDevice = (struct _DEVICE_OBJECT *)v36[1];
          *(_QWORD *)v36[1] = (char *)v18 + 344;
          v36[1] = (__int64)&v18[1].DriverObject;
          goto LABEL_55;
        }
        ++v34;
        v35 = 2 * v37;
      }
    }
    v42 = (struct _DEVICE_OBJECT *)qword_140039448;
    if ( *(__int64 **)qword_140039448 != &NbtConfig )
      __fastfail(3u);
    v18[1].DriverObject = (struct _DRIVER_OBJECT *)&NbtConfig;
    v18[1].NextDevice = v42;
    *(_QWORD *)&v42->Type = (char *)v18 + 344;
    qword_140039448 = (__int64)&v18[1].DriverObject;
LABEL_55:
    qword_1400395C8 |= v35;
  }
  v38 = (unsigned __int16)word_1400395D0;
  if ( (unsigned int)(unsigned __int16)word_1400395BA + 1 > (unsigned __int16)word_1400395D0 )
  {
    LOWORD(v38) = word_1400395D0 + 4;
    word_1400395D0 += 4;
  }
  v18[1].Dpc.DeferredRoutine = (PKDEFERRED_ROUTINE)v35;
  LODWORD(v18[2].AttachedDevice) = v34;
  if ( (BYTE3(xmmword_140038420) & 1) != 0 )
    WPP_SF_qdLL(HIDWORD(v35), v38, v35, v18, (unsigned __int16)word_1400395BA, HIDWORD(v35), v35);
  if ( (unsigned __int16)word_1400395BA > 1u )
    LOBYTE(word_140039670) = 1;
  KeReleaseSpinLock(&SpinLock, v33);
  return 0;
}

```

## disassembly

```asm
0x14001aa0c  push    rbp
0x14001aa0e  push    rbx
0x14001aa0f  push    rsi
0x14001aa10  push    rdi
0x14001aa11  push    r13
0x14001aa13  push    r14
0x14001aa15  push    r15
0x14001aa17  lea     rbp, [rsp-0Fh]
0x14001aa1c  sub     rsp, 0B0h
0x14001aa23  mov     rax, cs:__security_cookie
0x14001aa2a  xor     rax, rsp
0x14001aa2d  mov     [rbp+3Fh+var_40], rax
0x14001aa31  xorps   xmm0, xmm0
0x14001aa34  mov     [rbp+3Fh+var_98], r9
0x14001aa38  mov     edi, 1
0x14001aa3d  xorps   xmm1, xmm1
0x14001aa40  mov     r15, r9
0x14001aa43  mov     r14, r8
0x14001aa46  mov     rsi, rdx
0x14001aa49  mov     r13, rcx
0x14001aa4c  movups  xmmword ptr [rbp+3Fh+ApcState.ApcListHead.Flink], xmm0
0x14001aa50  movups  xmmword ptr [rbp+3Fh+ApcState.ApcListHead.Flink+10h], xmm0
0x14001aa54  movups  xmmword ptr [rbp+3Fh+ApcState.Process], xmm0
0x14001aa58  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm0
0x14001aa5c  movups  xmmword ptr [rbp+3Fh+Guid.Data1], xmm1
0x14001aa60  cmp     [rbp+3Fh+arg_20], edi
0x14001aa63  jz      loc_14001AB37
0x14001aa69  cmp     [rbp+3Fh+arg_20], 2
0x14001aa6d  lea     rdi, [rcx+8]
0x14001aa71  jz      short loc_14001AADB
0x14001aa73  movzx   r8d, word ptr [rcx]
0x14001aa77  xor     edx, edx
0x14001aa79  mov     r9d, r8d
0x14001aa7c  mov     ebx, 0C000000Dh
0x14001aa81  shr     r9d, 1
0x14001aa84  cmp     edx, r9d
0x14001aa87  jnb     short loc_14001AAC6
0x14001aa89  mov     rax, [rdi]
0x14001aa8c  lea     r10, [rax+rdx*2]
0x14001aa90  cmp     word ptr [r10], 7Bh ; '{'
0x14001aa95  jz      short loc_14001AA9B
0x14001aa97  inc     edx
0x14001aa99  jmp     short loc_14001AA84
0x14001aa9b  add     dx, dx
0x14001aa9e  mov     [rbp+3Fh+GuidString.Buffer], r10
0x14001aaa2  sub     r8w, dx
0x14001aaa6  lea     rcx, [rbp+3Fh+GuidString]; GuidString
0x14001aaaa  lea     rdx, [rbp+3Fh+Guid]; Guid
0x14001aaae  mov     [rbp+3Fh+GuidString.Length], r8w
0x14001aab3  mov     [rbp+3Fh+GuidString.MaximumLength], r8w
0x14001aab8  call    cs:__imp_RtlGUIDFromString
0x14001aabf  nop     dword ptr [rax+rax+00h]
0x14001aac4  mov     ebx, eax
0x14001aac6  test    byte ptr cs:xmmword_140038420, 8
0x14001aacd  jnz     loc_14001AFDA
0x14001aad3  test    ebx, ebx
0x14001aad5  js      loc_14001AF86
0x14001aadb  lea     rcx, SpinLock; SpinLock
0x14001aae2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001aae9  nop     dword ptr [rax+rax+00h]
0x14001aaee  mov     bl, al
0x14001aaf0  mov     ecx, 40h ; '@'
0x14001aaf5  movzx   eax, cs:word_1400395BA
0x14001aafc  cmp     ax, cx
0x14001aaff  jnb     loc_14001AFF9
0x14001ab05  mov     ecx, 1
0x14001ab0a  add     ax, cx
0x14001ab0d  mov     cs:word_1400395BA, ax
0x14001ab14  cmp     ax, cx
0x14001ab17  jz      loc_14001AF42
0x14001ab1d  mov     dl, bl; NewIrql
0x14001ab1f  lea     rcx, SpinLock; SpinLock
0x14001ab26  call    cs:__imp_KeReleaseSpinLock
0x14001ab2d  nop     dword ptr [rax+rax+00h]
0x14001ab32  mov     edi, 1
0x14001ab37  mov     r9d, [rbp+3Fh+arg_20]
0x14001ab3b  mov     r8, r15
0x14001ab3e  mov     rdx, rsi; PCUNICODE_STRING
0x14001ab41  mov     rcx, r13; SourceString
0x14001ab44  call    NbtAllocAndInitDevice
0x14001ab49  xor     r8d, r8d
0x14001ab4c  mov     ebx, eax
0x14001ab4e  test    eax, eax
0x14001ab50  js      loc_14001AEEB
0x14001ab56  mov     rbx, [r15]
0x14001ab59  mov     esi, 418h
0x14001ab5e  test    r14, r14
0x14001ab61  jnz     loc_14001ACB0
0x14001ab67  mov     [rbx+360h], dil
0x14001ab6e  mov     [rbx+364h], r8d
0x14001ab75  mov     [rbx+38Ch], r8b
0x14001ab7c  call    cs:__imp_PsGetCurrentProcess
0x14001ab83  nop     dword ptr [rax+rax+00h]
0x14001ab88  mov     rcx, cs:NbtFspProcess; PROCESS
0x14001ab8f  cmp     rax, rcx
0x14001ab92  jz      loc_14001AC80
0x14001ab98  lea     rdx, [rbp+3Fh+ApcState]; ApcState
0x14001ab9c  call    cs:__imp_KeStackAttachProcess
0x14001aba3  nop     dword ptr [rax+rax+00h]
0x14001aba8  mov     r14b, dil
0x14001abab  mov     rcx, rbx
0x14001abae  call    NbtTdiOpenControl
0x14001abb3  mov     edi, eax
0x14001abb5  test    eax, eax
0x14001abb7  js      loc_14001AC88
0x14001abbd  lea     rdx, [rbp+3Fh+Guid]
0x14001abc1  mov     rcx, rbx
0x14001abc4  call    NbtGetNewDeviceInfo
0x14001abc9  mov     edi, eax
0x14001abcb  test    eax, eax
0x14001abcd  js      loc_14001B12A
0x14001abd3  test    r14b, r14b
0x14001abd6  jnz     loc_14001B141
0x14001abdc  mov     r14d, 1
0x14001abe2  test    edi, edi
0x14001abe4  jns     loc_14001AD4E
0x14001abea  xor     esi, esi
0x14001abec  cmp     [rbx+288h], rsi
0x14001abf3  jnz     loc_14001B23B
0x14001abf9  lea     rcx, SpinLock; SpinLock
0x14001ac00  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ac07  nop     dword ptr [rax+rax+00h]
0x14001ac0c  mov     sil, al
0x14001ac0f  cmp     [rbp+3Fh+arg_20], r14d
0x14001ac13  jnz     loc_14001B2B3
0x14001ac19  xor     eax, eax
0x14001ac1b  cmp     cs:word_1400395BA, ax
0x14001ac22  jz      loc_14001B2E1
0x14001ac28  mov     dl, sil; NewIrql
0x14001ac2b  lea     rcx, SpinLock; SpinLock
0x14001ac32  call    cs:__imp_KeReleaseSpinLock
0x14001ac39  nop     dword ptr [rax+rax+00h]
0x14001ac3e  mov     qword ptr [r15], 0
0x14001ac45  xor     edx, edx; Tag
0x14001ac47  mov     rcx, [rbx+1E0h]; P
0x14001ac4e  call    cs:__imp_ExFreePoolWithTag
0x14001ac55  nop     dword ptr [rax+rax+00h]
0x14001ac5a  mov     rcx, rbx; DeviceObject
0x14001ac5d  call    cs:__imp_IoDeleteDevice
0x14001ac64  nop     dword ptr [rax+rax+00h]
0x14001ac69  mov     r8, [r13+8]
0x14001ac6d  mov     edx, 113h
0x14001ac72  mov     ecx, edi
0x14001ac74  call    NbtLogDeviceCreationFailure
0x14001ac79  mov     eax, edi
0x14001ac7b  jmp     loc_14001AECC
0x14001ac80  xor     r14b, r14b
0x14001ac83  jmp     loc_14001ABAB
0x14001ac88  test    byte ptr cs:xmmword_140038420+3, 1
0x14001ac8f  jz      loc_14001ABD3
0x14001ac95  mov     edx, 18h
0x14001ac9a  mov     r9d, eax
0x14001ac9d  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x14001aca4  mov     ecx, esi
0x14001aca6  call    WPP_SF_d
0x14001acab  jmp     loc_14001ABD3
0x14001acb0  mov     eax, [r14]
0x14001acb3  mov     edx, r8d
0x14001acb6  mov     [rbx+1F8h], eax
0x14001acbc  mov     eax, [r14+4]
0x14001acc0  mov     [rbx+1FCh], eax
0x14001acc6  mov     [rbx+358h], r8w
0x14001acce  movzx   eax, word ptr [r14+30h]
0x14001acd3  mov     [rbx+228h], ax
0x14001acda  mov     [rbx+22Ah], r8w
0x14001ace2  cmp     r8w, [r14+30h]
0x14001ace7  jb      loc_14001B0E3
0x14001aced  movzx   ecx, byte ptr [r14+34h]
0x14001acf2  mov     [rbx+360h], cl
0x14001acf8  test    byte ptr cs:xmmword_140038420+3, dil
0x14001acff  jnz     loc_14001B102
0x14001ad05  mov     eax, [r14+38h]
0x14001ad09  mov     [rbx+364h], eax
0x14001ad0f  mov     al, [r14+3Ch]
0x14001ad13  mov     [rbx+38Ch], al
0x14001ad19  movzx   eax, cs:NodeType
0x14001ad20  bt      ax, 0Ch
0x14001ad25  jnb     loc_14001AB7C
0x14001ad2b  cmp     [r14], r8d
0x14001ad2e  jnz     short loc_14001AD3A
0x14001ad30  cmp     [r14+4], r8d
0x14001ad34  jz      loc_14001AB7C
0x14001ad3a  and     ax, 10h
0x14001ad3e  or      ax, 8
0x14001ad42  mov     cs:NodeType, ax
0x14001ad49  jmp     loc_14001AB7C
0x14001ad4e  mov     rax, [rbx+290h]
0x14001ad55  mov     dl, [rax+4Ch]
0x14001ad58  add     dl, r14b
0x14001ad5b  mov     [rbx+4Ch], dl
0x14001ad5e  movzx   eax, cs:StackSize
0x14001ad65  movsx   ecx, dl
0x14001ad68  cmp     eax, ecx
0x14001ad6a  jl      loc_14001B156
0x14001ad70  xor     edi, edi
0x14001ad72  cmp     cs:Irp, rdi
0x14001ad79  jz      loc_14001B161
0x14001ad7f  btr     dword ptr [rbx+30h], 7
0x14001ad84  mov     r8, 0FFFFF78000000014h
0x14001ad8e  mov     dword ptr [rbx+368h], 89008Bh
0x14001ad98  xorps   xmm0, xmm0
0x14001ad9b  mov     word ptr [rbx+36Ch], 8Ah
0x14001ada4  movups  xmmword ptr [rbx+36Eh], xmm0
0x14001adab  mov     r8, [r8]
0x14001adae  mov     rax, cs:qword_140034258
0x14001adb5  mov     rcx, r8
0x14001adb8  neg     rcx
0x14001adbb  cmovs   rcx, r8
0x14001adbf  mul     rcx
0x14001adc2  shr     rdx, 0Dh
0x14001adc6  test    r8, r8
0x14001adc9  js      loc_14001B1FB
0x14001adcf  lea     rcx, SpinLock; SpinLock
0x14001add6  mov     [rbx+250h], edx
0x14001addc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ade3  nop     dword ptr [rax+rax+00h]
0x14001ade8  mov     dil, al
0x14001adeb  cmp     [rbx+154h], r14d
0x14001adf2  jz      loc_14001AF36
0x14001adf8  cmp     [rbp+3Fh+arg_20], 2
0x14001adfc  jz      short loc_14001AE0A
0x14001adfe  movups  xmm0, xmmword ptr [rbp+3Fh+Guid.Data1]
0x14001ae02  movdqu  xmmword ptr [rbx+308h], xmm0
0x14001ae0a  lea     r10, NbtConfig
0x14001ae11  mov     r9d, r14d
0x14001ae14  cmp     cs:NbtConfig, r10
0x14001ae1b  mov     r8, r14
0x14001ae1e  jz      loc_14001AFAA
0x14001ae24  mov     rdx, r10
0x14001ae27  mov     rdx, [rdx]
0x14001ae2a  cmp     rdx, r10
0x14001ae2d  jz      loc_14001AFAA
0x14001ae33  mov     rax, [rdx+0D8h]
0x14001ae3a  cmp     rax, r8
0x14001ae3d  ja      short loc_14001AE48
0x14001ae3f  add     r9d, r14d
0x14001ae42  lea     r8, [rax+rax]
0x14001ae46  jmp     short loc_14001AE27
0x14001ae48  lea     rcx, [rbx+158h]
0x14001ae4f  mov     [rcx], rdx
0x14001ae52  mov     rax, [rdx+8]
0x14001ae56  mov     [rbx+160h], rax
0x14001ae5d  mov     rax, [rdx+8]
0x14001ae61  mov     [rax], rcx
0x14001ae64  mov     [rdx+8], rcx
0x14001ae68  or      cs:qword_1400395C8, r8
0x14001ae6f  movzx   ecx, cs:word_1400395BA
0x14001ae76  movzx   edx, cs:word_1400395D0
0x14001ae7d  add     ecx, r14d
0x14001ae80  cmp     ecx, edx
0x14001ae82  ja      loc_14001B203
0x14001ae88  mov     [rbx+230h], r8
0x14001ae8f  mov     [rbx+2B8h], r9d
0x14001ae96  test    byte ptr cs:xmmword_140038420+3, r14b
0x14001ae9d  jnz     loc_14001B213
0x14001aea3  cmp     cs:word_1400395BA, r14w
0x14001aeab  jbe     short loc_14001AEB4
0x14001aead  mov     byte ptr cs:word_140039670, r14b
0x14001aeb4  mov     dl, dil; NewIrql
0x14001aeb7  lea     rcx, SpinLock; SpinLock
0x14001aebe  call    cs:__imp_KeReleaseSpinLock
0x14001aec5  nop     dword ptr [rax+rax+00h]
0x14001aeca  xor     eax, eax
0x14001aecc  mov     rcx, [rbp+3Fh+var_40]
0x14001aed0  xor     rcx, rsp; StackCookie
0x14001aed3  call    __security_check_cookie
0x14001aed8  add     rsp, 0B0h
0x14001aedf  pop     r15
0x14001aee1  pop     r14
0x14001aee3  pop     r13
0x14001aee5  pop     rdi
0x14001aee6  pop     rsi
0x14001aee7  pop     rbx
0x14001aee8  pop     rbp
0x14001aee9  retn
0x14001aeeb  test    byte ptr cs:xmmword_140038420+3, dil
0x14001aef2  jnz     loc_14001B0A7
0x14001aef8  lea     rcx, SpinLock; SpinLock
0x14001aeff  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001af06  nop     dword ptr [rax+rax+00h]
0x14001af0b  mov     dil, al
0x14001af0e  mov     eax, 1
0x14001af13  cmp     [rbp+3Fh+arg_20], eax
0x14001af16  jnz     loc_14001B0C5
0x14001af1c  mov     dl, dil; NewIrql
0x14001af1f  lea     rcx, SpinLock; SpinLock
0x14001af26  call    cs:__imp_KeReleaseSpinLock
0x14001af2d  nop     dword ptr [rax+rax+00h]
0x14001af32  mov     eax, ebx
0x14001af34  jmp     short loc_14001AECC
0x14001af36  xor     r9d, r9d
0x14001af39  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001af3d  jmp     loc_14001AE6F
0x14001af42  mov     dl, bl; NewIrql
0x14001af44  lea     rcx, SpinLock; SpinLock
0x14001af4b  call    cs:__imp_KeReleaseSpinLock
0x14001af52  nop     dword ptr [rax+rax+00h]
0x14001af57  call    InitTimersNotOs
0x14001af5c  lea     rcx, SpinLock; SpinLock
0x14001af63  mov     r15d, eax
  ... truncated ...
```
