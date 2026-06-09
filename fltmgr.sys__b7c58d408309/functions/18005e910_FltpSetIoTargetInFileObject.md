# FltpSetIoTargetInFileObject

- ea: `0x18005e910`
- end: `0x18005ecf5`
- name: `FltpSetIoTargetInFileObject`
- size: `997`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180007500`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x1800148b0`
- `0x18005dc10`
- `0x18005e910`
- `0x180060330`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x18005ebac`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ebac`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005eb6d`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005eb6d`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x18005ea58`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x18005ea58`
- `ntoskrnl!ObfDereferenceObject` at `0x18005eae4`
- `ntoskrnl!ObfDereferenceObject` at `0x18005ec09`
- `ntoskrnl!ObfDereferenceObject` at `0x18005ec32`
- `ntoskrnl!ObfDereferenceObject` at `0x18005eae4`
- `ntoskrnl!ObfDereferenceObject` at `0x18005ec09`
- `ntoskrnl!ObfDereferenceObject` at `0x18005ec32`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x18005ebf7`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x18005ebf7`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18005ea1a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18005ea1a`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005ecb6`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005ecb6`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005e979`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005e979`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x18005e934`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x18005e934`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x18005e9ae`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x18005e9ae`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18005ea49`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18005ea49`
- `ntoskrnl!FsRtlInsertPerFileObjectContext` at `0x18005eb1b`
- `ntoskrnl!FsRtlInsertPerFileObjectContext` at `0x18005eb1b`
- `ntoskrnl!IoCancelFileOpen` at `0x18005ec64`
- `ntoskrnl!IoCancelFileOpen` at `0x18005ec64`

## pseudocode

```c
int __fastcall FltpSetIoTargetInFileObject(__int64 a1)
{
  IRP *v2; // rcx
  NTSTATUS EcpListFromIrp; // eax
  __int64 v4; // rax
  NTSTATUS v5; // eax
  char *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r13
  struct _FILE_OBJECT *v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rbp
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  PDEVICE_OBJECT i; // rsi
  __int64 DeviceExtension; // rcx
  void *v15; // rcx
  NTSTATUS inserted; // ebp
  struct _FAST_MUTEX *v17; // rsi
  struct _FAST_MUTEX **Owner; // rcx
  struct _FAST_MUTEX *v19; // rbx
  PDEVICE_OBJECT LowerDeviceObject; // r15
  __int64 v21; // r8
  __int64 *v22; // rdx
  ULONG EcpContextSize; // [rsp+70h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+80h] [rbp+18h] BYREF

  EcpList = 0;
  v2 = *(IRP **)(a1 + 48);
  EcpContext = 0;
  EcpContextSize = 0;
  EcpListFromIrp = FsRtlGetEcpListFromIrp(v2, &EcpList);
  LODWORD(v4) = FltpDbgStatus(EcpListFromIrp);
  if ( (int)v4 < 0 )
    return v4;
  if ( !EcpList )
    return v4;
  v5 = FsRtlRemoveExtraCreateParameter(EcpList, &FLTMGR_TIOCTRL_ECP_GUID, &EcpContext, &EcpContextSize);
  LODWORD(v4) = FltpDbgStatus(v5);
  if ( (int)v4 < 0 )
    return v4;
  if ( FsRtlIsEcpFromUserMode(EcpContext) )
  {
    LODWORD(v4) = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
    return v4;
  }
  *((_WORD *)EcpContext + 3) &= ~0x10u;
  v6 = (char *)EcpContext;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 184LL);
  v8 = *(_QWORD *)(v7 + 40);
  v9 = *(struct _FILE_OBJECT **)(v7 + 48);
  v10 = *((_QWORD *)EcpContext + 2);
  if ( v10 )
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v10 + 16) + 56LL), 1u);
  *((_WORD *)v6 + 3) |= 1u;
  v11 = *((_QWORD *)v6 + 1);
  *((_QWORD *)v6 + 2) = v9;
  *((_QWORD *)v6 + 6) = DriverObject;
  *((_QWORD *)v6 + 7) = 0;
  *((_QWORD *)v6 + 3) = 0;
  RelatedDeviceObject = IoGetRelatedDeviceObject(v9);
  for ( i = IoGetAttachedDeviceReference(RelatedDeviceObject); ; i = LowerDeviceObject )
  {
    if ( i && i->DriverObject == DriverObject )
    {
      DeviceExtension = (__int64)i->DeviceExtension;
      if ( !DeviceExtension )
      {
        if ( (byte_1800404C1 & 0x40) == 0 )
          goto LABEL_30;
        v22 = EnumerationSup_c1102;
        goto LABEL_39;
      }
      if ( *(_QWORD *)(DeviceExtension + 16) == v11 )
        break;
    }
    LowerDeviceObject = IoGetLowerDeviceObject(i);
    ObfDereferenceObject(i);
    if ( !LowerDeviceObject )
      goto LABEL_31;
  }
  if ( *(_WORD *)DeviceExtension != 0xF107 )
  {
    if ( (byte_1800404C1 & 0x40) == 0 )
    {
LABEL_30:
      ObfDereferenceObject(i);
LABEL_31:
      inserted = -1073741811;
      goto LABEL_17;
    }
    v22 = EnumerationSup_c1144;
LABEL_39:
    McTemplateU0sp_EtwWriteTransfer(DeviceExtension, (__int64)v22, "FltpGetVolumeFromDeviceObject", i);
    goto LABEL_30;
  }
  v15 = *(void **)(DeviceExtension + 80);
  *((_QWORD *)v6 + 3) = v15;
  inserted = FltObjectReference(v15);
  if ( (int)FltpDbgStatus(inserted) < 0 )
    *((_QWORD *)v6 + 3) = 0;
  ObfDereferenceObject(i);
LABEL_17:
  if ( (int)FltpDbgStatus(inserted) >= 0 )
  {
    inserted = FsRtlInsertPerFileObjectContext(v9, (PFSRTL_PER_FILEOBJECT_CONTEXT)v6 + 1);
    if ( (int)FltpDbgStatus(inserted) >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v6 + 3) + 88LL) + 2032LL));
      *((_WORD *)v6 + 3) |= 4u;
      if ( !*((_WORD *)v6 + 2) )
      {
        v17 = (struct _FAST_MUTEX *)(*((_QWORD *)v6 + 8) + 448LL);
        ExAcquireFastMutex(v17);
        if ( (v17[1].Contention & 1) == 0 )
        {
          v17[1].Contention += 2;
          Owner = (struct _FAST_MUTEX **)v17[1].Owner;
          if ( *Owner != &v17[1] )
            __fastfail(3u);
          v19 = (struct _FAST_MUTEX *)(v6 + 80);
          *(_QWORD *)&v19->Count = v17 + 1;
          v19->Owner = Owner;
          *Owner = v19;
          v17[1].Owner = v19;
        }
        ExReleaseFastMutex(v17);
      }
    }
  }
  LODWORD(v4) = FltpDbgStatus(inserted);
  if ( (int)v4 < 0 )
  {
    FreeTargetedIoCtrl(EcpContext);
    if ( (*(_DWORD *)(a1 + 4) & 0x80u) != 0 )
    {
      LOBYTE(v21) = 1;
      LODWORD(v4) = FltpCancelFileOpen(*(_QWORD *)(*(_QWORD *)(a1 + 248) + 16LL), v9, v21);
      *(_DWORD *)(a1 + 256) = inserted;
      *(_QWORD *)(a1 + 264) = 0;
    }
    else
    {
      IoCancelFileOpen(*(PDEVICE_OBJECT *)(*(_QWORD *)(v8 + 64) + 8LL), v9);
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 48LL) = inserted;
      v4 = *(_QWORD *)(a1 + 48);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18005e910  mov     rax, rsp
0x18005e913  push    rdi
0x18005e914  push    r12
0x18005e916  sub     rsp, 58h
0x18005e91a  xor     r12d, r12d
0x18005e91d  lea     rdx, [rax+18h]; EcpList
0x18005e921  mov     rdi, rcx
0x18005e924  mov     [rax+18h], r12
0x18005e928  mov     rcx, [rcx+30h]; Irp
0x18005e92c  mov     [rax+10h], r12
0x18005e930  mov     [rax+8], r12d
0x18005e934  call    cs:__imp_FsRtlGetEcpListFromIrp
0x18005e93b  nop     dword ptr [rax+rax+00h]
0x18005e940  mov     r8d, 663h
0x18005e946  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005e94d  mov     ecx, eax
0x18005e94f  xor     r9d, r9d
0x18005e952  call    FltpDbgStatus
0x18005e957  test    eax, eax
0x18005e959  js      short loc_18005E9A0
0x18005e95b  mov     rcx, [rsp+68h+EcpList]; EcpList
0x18005e963  test    rcx, rcx
0x18005e966  jz      short loc_18005E9A0
0x18005e968  lea     r9, [rsp+68h+EcpContextSize]; EcpContextSize
0x18005e96d  lea     r8, [rsp+68h+EcpContext]; EcpContext
0x18005e972  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18005e979  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x18005e980  nop     dword ptr [rax+rax+00h]
0x18005e985  mov     r8d, 673h
0x18005e98b  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005e992  mov     ecx, eax
0x18005e994  xor     r9d, r9d
0x18005e997  call    FltpDbgStatus
0x18005e99c  test    eax, eax
0x18005e99e  jns     short loc_18005E9A9
0x18005e9a0  add     rsp, 58h
0x18005e9a4  pop     r12
0x18005e9a6  pop     rdi
0x18005e9a7  retn
0x18005e9a9  mov     rcx, [rsp+68h+EcpContext]; EcpContext
0x18005e9ae  call    cs:__imp_FsRtlIsEcpFromUserMode
0x18005e9b5  nop     dword ptr [rax+rax+00h]
0x18005e9ba  test    al, al
0x18005e9bc  jnz     loc_18005ECA9
0x18005e9c2  mov     rax, [rsp+68h+EcpContext]
0x18005e9c7  mov     ecx, 0FFEFh
0x18005e9cc  mov     [rsp+68h+arg_18], rbx
0x18005e9d4  mov     [rsp+68h+var_18], rbp
0x18005e9d9  mov     [rsp+68h+var_20], rsi
0x18005e9de  and     [rax+6], cx
0x18005e9e2  mov     rax, [rdi+30h]
0x18005e9e6  mov     rbx, [rsp+68h+EcpContext]
0x18005e9eb  mov     [rsp+68h+var_28], r13
0x18005e9f0  mov     [rsp+68h+var_30], r14
0x18005e9f5  mov     rcx, [rax+0B8h]
0x18005e9fc  mov     r13, [rcx+28h]
0x18005ea00  mov     r14, [rcx+30h]
0x18005ea04  mov     rcx, [rbx+10h]
0x18005ea08  test    rcx, rcx
0x18005ea0b  jz      short loc_18005EA26
0x18005ea0d  mov     rcx, [rcx+10h]
0x18005ea11  mov     edx, 1; Count
0x18005ea16  mov     rcx, [rcx+38h]; RunRef
0x18005ea1a  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18005ea21  nop     dword ptr [rax+rax+00h]
0x18005ea26  or      word ptr [rbx+6], 1
0x18005ea2b  mov     rcx, r14; FileObject
0x18005ea2e  mov     rbp, [rbx+8]
0x18005ea32  mov     [rbx+10h], r14
0x18005ea36  mov     rax, cs:DriverObject
0x18005ea3d  mov     [rbx+30h], rax
0x18005ea41  mov     [rbx+38h], r12
0x18005ea45  mov     [rbx+18h], r12
0x18005ea49  call    cs:__imp_IoGetRelatedDeviceObject
0x18005ea50  nop     dword ptr [rax+rax+00h]
0x18005ea55  mov     rcx, rax; DeviceObject
0x18005ea58  call    cs:__imp_IoGetAttachedDeviceReference
0x18005ea5f  nop     dword ptr [rax+rax+00h]
0x18005ea64  mov     rsi, rax
0x18005ea67  mov     [rsp+68h+var_38], r15
0x18005ea6c  test    rsi, rsi
0x18005ea6f  jz      loc_18005EBF4
0x18005ea75  mov     rcx, cs:DriverObject
0x18005ea7c  cmp     [rsi+8], rcx
0x18005ea80  jnz     loc_18005EBF4
0x18005ea86  mov     rcx, [rsi+40h]
0x18005ea8a  test    rcx, rcx
0x18005ea8d  jz      loc_18005ECDC
0x18005ea93  cmp     [rcx+10h], rbp
0x18005ea97  jnz     loc_18005EBF4
0x18005ea9d  mov     eax, 0F107h
0x18005eaa2  cmp     [rcx], ax
0x18005eaa5  jnz     loc_18005EC22
0x18005eaab  mov     rcx, [rcx+50h]; FltObject
0x18005eaaf  mov     [rbx+18h], rcx
0x18005eab3  call    FltObjectReference
0x18005eab8  mov     r8d, 46Dh
0x18005eabe  mov     [rsp+68h+var_48], r12
0x18005eac3  mov     r9d, 0C01C000Bh
0x18005eac9  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x18005ead0  mov     ecx, eax
0x18005ead2  mov     ebp, eax
0x18005ead4  call    FltpDbgStatus
0x18005ead9  test    eax, eax
0x18005eadb  js      loc_18005ECC7
0x18005eae1  mov     rcx, rsi; Object
0x18005eae4  call    cs:__imp_ObfDereferenceObject
0x18005eaeb  nop     dword ptr [rax+rax+00h]
0x18005eaf0  mov     r8d, 21Ch
0x18005eaf6  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005eafd  xor     r9d, r9d
0x18005eb00  mov     ecx, ebp
0x18005eb02  call    FltpDbgStatus
0x18005eb07  mov     r15, [rsp+68h+var_38]
0x18005eb0c  test    eax, eax
0x18005eb0e  js      loc_18005EBB8
0x18005eb14  lea     rdx, [rbx+20h]; Ptr
0x18005eb18  mov     rcx, r14; FileObject
0x18005eb1b  call    cs:__imp_FsRtlInsertPerFileObjectContext
0x18005eb22  nop     dword ptr [rax+rax+00h]
0x18005eb27  mov     r8d, 22Fh
0x18005eb2d  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005eb34  mov     ecx, eax
0x18005eb36  xor     r9d, r9d
0x18005eb39  mov     ebp, eax
0x18005eb3b  call    FltpDbgStatus
0x18005eb40  test    eax, eax
0x18005eb42  js      short loc_18005EBB8
0x18005eb44  mov     rax, [rbx+18h]
0x18005eb48  mov     rcx, [rax+58h]
0x18005eb4c  lock inc dword ptr [rcx+7F0h]
0x18005eb53  or      word ptr [rbx+6], 4
0x18005eb58  cmp     [rbx+4], r12w
0x18005eb5d  jnz     short loc_18005EBB8
0x18005eb5f  mov     rsi, [rbx+40h]
0x18005eb63  add     rsi, 1C0h
0x18005eb6a  mov     rcx, rsi; FastMutex
0x18005eb6d  call    cs:__imp_ExAcquireFastMutex
0x18005eb74  nop     dword ptr [rax+rax+00h]
0x18005eb79  test    byte ptr [rsi+48h], 1
0x18005eb7d  jnz     short loc_18005EBA9
0x18005eb7f  add     dword ptr [rsi+48h], 2
0x18005eb83  lea     rax, [rsi+38h]
0x18005eb87  mov     rcx, [rax+8]
0x18005eb8b  cmp     [rcx], rax
0x18005eb8e  jz      short loc_18005EB97
0x18005eb90  mov     ecx, 3
0x18005eb95  int     29h; Win8: RtlFailFast(ecx)
0x18005eb97  add     rbx, 50h ; 'P'
0x18005eb9b  mov     [rbx], rax
0x18005eb9e  mov     [rbx+8], rcx
0x18005eba2  mov     [rcx], rbx
0x18005eba5  mov     [rax+8], rbx
0x18005eba9  mov     rcx, rsi; FastMutex
0x18005ebac  call    cs:__imp_ExReleaseFastMutex
0x18005ebb3  nop     dword ptr [rax+rax+00h]
0x18005ebb8  mov     r8d, 69Ch
0x18005ebbe  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005ebc5  xor     r9d, r9d
0x18005ebc8  mov     ecx, ebp
0x18005ebca  call    FltpDbgStatus
0x18005ebcf  test    eax, eax
0x18005ebd1  js      short loc_18005EC48
0x18005ebd3  mov     r13, [rsp+68h+var_28]
0x18005ebd8  mov     rsi, [rsp+68h+var_20]
0x18005ebdd  mov     rbp, [rsp+68h+var_18]
0x18005ebe2  mov     rbx, [rsp+68h+arg_18]
0x18005ebea  mov     r14, [rsp+68h+var_30]
0x18005ebef  jmp     loc_18005E9A0
0x18005ebf4  mov     rcx, rsi; DeviceObject
0x18005ebf7  call    cs:__imp_IoGetLowerDeviceObject
0x18005ebfe  nop     dword ptr [rax+rax+00h]
0x18005ec03  mov     rcx, rsi; Object
0x18005ec06  mov     r15, rax
0x18005ec09  call    cs:__imp_ObfDereferenceObject
0x18005ec10  nop     dword ptr [rax+rax+00h]
0x18005ec15  test    r15, r15
0x18005ec18  jz      short loc_18005EC3E
0x18005ec1a  mov     rsi, r15
0x18005ec1d  jmp     loc_18005EA6C
0x18005ec22  test    cs:byte_1800404C1, 40h
0x18005ec29  jnz     loc_18005ECD0
0x18005ec2f  mov     rcx, rsi; Object
0x18005ec32  call    cs:__imp_ObfDereferenceObject
0x18005ec39  nop     dword ptr [rax+rax+00h]
0x18005ec3e  mov     ebp, 0C000000Dh
0x18005ec43  jmp     loc_18005EAF0
0x18005ec48  mov     rcx, [rsp+68h+EcpContext]; EcpContext
0x18005ec4d  call    FreeTargetedIoCtrl
0x18005ec52  mov     eax, [rdi+4]
0x18005ec55  mov     rdx, r14; FileObject
0x18005ec58  test    al, al
0x18005ec5a  js      short loc_18005EC84
0x18005ec5c  mov     rcx, [r13+40h]
0x18005ec60  mov     rcx, [rcx+8]; DeviceObject
0x18005ec64  call    cs:__imp_IoCancelFileOpen
0x18005ec6b  nop     dword ptr [rax+rax+00h]
0x18005ec70  mov     rax, [rdi+30h]
0x18005ec74  mov     [rax+30h], ebp
0x18005ec77  mov     rax, [rdi+30h]
0x18005ec7b  mov     [rax+38h], r12
0x18005ec7f  jmp     loc_18005EBD3
0x18005ec84  mov     rcx, [rdi+0F8h]
0x18005ec8b  mov     r8b, 1
0x18005ec8e  mov     rcx, [rcx+10h]
0x18005ec92  call    FltpCancelFileOpen
0x18005ec97  mov     [rdi+100h], ebp
0x18005ec9d  mov     [rdi+108h], r12
0x18005eca4  jmp     loc_18005EBD3
0x18005eca9  mov     rdx, [rsp+68h+EcpContext]; EcpContext
0x18005ecae  mov     rcx, [rsp+68h+EcpList]; EcpList
0x18005ecb6  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18005ecbd  nop     dword ptr [rax+rax+00h]
0x18005ecc2  jmp     loc_18005E9A0
0x18005ecc7  mov     [rbx+18h], r12
0x18005eccb  jmp     loc_18005EAE1
0x18005ecd0  lea     rdx, EnumerationSup_c1144
0x18005ecd7  jmp     loc_180079B18
0x18005ecdc  test    cs:byte_1800404C1, 40h
0x18005ece3  jz      loc_18005EC2F
0x18005ece9  lea     rdx, EnumerationSup_c1102
0x18005ecf0  jmp     loc_180079B18
0x180079b18  mov     r9, rsi
0x180079b1b  lea     r8, aFltpgetvolumef; "FltpGetVolumeFromDeviceObject"
0x180079b22  call    McTemplateU0sp_EtwWriteTransfer
0x180079b27  nop
0x180079b28  jmp     loc_18005EC2F
```
