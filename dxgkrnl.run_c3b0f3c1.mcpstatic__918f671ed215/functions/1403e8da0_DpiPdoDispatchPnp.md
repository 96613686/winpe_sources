# DpiPdoDispatchPnp

- ea: `0x1403e8da0`
- end: `0x1403e939d`
- name: `DpiPdoDispatchPnp`
- size: `1533`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140022434`
- `0x1400456cc`
- `0x14004bf5c`
- `0x1400a0cb0`
- `0x14018c7bc`
- `0x140193d6c`
- `0x140195264`
- `0x1402c4148`
- `0x1402c4ae0`
- `0x1402c5950`
- `0x140366938`
- `0x140367554`
- `0x140367720`
- `0x1403e8da0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8e37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8ed3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8f36`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e902e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e92d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8e37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8ed3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8f36`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e902e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e92d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403e8ec2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403e8ec2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8e5d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8ef9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8f5c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e9054`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e92fa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8e5d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8ef9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8f5c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e9054`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e92fa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403e8eb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403e8eb6`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1403e91ac`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1403e91ac`
- `ntoskrnl!IofCompleteRequest` at `0x1403e937d`
- `ntoskrnl!IofCompleteRequest` at `0x1403e937d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403e8fca`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403e8fca`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e9230`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e92c3`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e9230`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e92c3`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1403e8f9b`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1403e8f9b`
- `ntoskrnl!IoQueueWorkItem` at `0x1403e8fbc`
- `ntoskrnl!IoQueueWorkItem` at `0x1403e8fbc`
- `watchdog!WdLogSingleEntry1` at `0x1403e9010`
- `watchdog!WdLogSingleEntry1` at `0x1403e9343`
- `watchdog!WdLogSingleEntry1` at `0x1403e9010`
- `watchdog!WdLogSingleEntry1` at `0x1403e9343`

## pseudocode

```c
__int64 __fastcall DpiPdoDispatchPnp(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  char *DeviceExtension; // rbx
  PIRP v5; // r14
  NTSTATUS Status; // edi
  __int64 MinorFunction; // rcx
  __int64 (__fastcall *v8)(struct _DEVICE_OBJECT *); // rax
  __int64 v9; // r13
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  bool v14; // zf
  int v15; // eax
  int v16; // eax
  struct _IO_REMOVE_LOCK *v17; // rcx
  int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // eax
  struct _LUID *v26; // rdx
  DXGADAPTER *v27; // rcx
  ULONG v28; // r9d
  __int64 v29; // rdx
  int v30; // eax
  PIO_SECURITY_CONTEXT SecurityContext; // [rsp+40h] [rbp-38h] BYREF
  USHORT Size; // [rsp+48h] [rbp-30h]
  USHORT Version; // [rsp+4Ah] [rbp-2Eh]
  int v35; // [rsp+4Ch] [rbp-2Ch]
  LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-28h]
  struct _NAMED_PIPE_CREATE_PARAMETERS *Parameters; // [rsp+58h] [rbp-20h]
  int v38; // [rsp+60h] [rbp-18h]
  int v39; // [rsp+64h] [rbp-14h]
  unsigned int Data; // [rsp+C0h] [rbp+48h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (char *)a1->DeviceExtension;
  v5 = Irp;
  Status = -1073741637;
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( (unsigned __int8)MinorFunction < 0x18u )
  {
    v8 = *(__int64 (__fastcall **)(struct _DEVICE_OBJECT *))&DeviceExtension[8 * MinorFunction + 288];
    if ( v8 )
    {
      Status = v8(a1);
      goto LABEL_64;
    }
  }
  v9 = *(_QWORD *)(*((_QWORD *)DeviceExtension + 4) + 64LL);
  if ( (unsigned int)MinorFunction <= 8 )
  {
    if ( (_DWORD)MinorFunction == 8 )
    {
      if ( Irp->IoStatus.Status != -1073741637 )
        goto LABEL_65;
      v19 = *((_QWORD *)DeviceExtension + 5);
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      Size = CurrentStackLocation->Parameters.QueryInterface.Size;
      Version = CurrentStackLocation->Parameters.QueryInterface.Version;
      ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      v38 = *((_DWORD *)DeviceExtension + 126);
      v35 = 0;
      v39 = 0;
      if ( !*(_QWORD *)(v19 + 256) )
        goto LABEL_65;
      LOBYTE(Irp) = 1;
      if ( (int)DpiAcquireCoreSyncAccessSafe(a1, Irp) < 0 )
        goto LABEL_65;
      DxgkAcquireAdapterDdiSync(*(_QWORD *)(v9 + 4032), 1);
      Status = DpiDxgkDdiQueryInterface(v19, *((_QWORD *)DeviceExtension + 6), &SecurityContext);
      DxgkReleaseAdapterDdiSync(*(_QWORD *)(v9 + 4032));
      LOBYTE(v20) = 1;
      DpiReleaseCoreSyncAccessSafe(a1, v20);
      if ( Status >= 0 )
      {
        CurrentStackLocation->Parameters.WMI.ProviderId = (ULONG_PTR)SecurityContext;
        CurrentStackLocation->Parameters.QueryInterface.Size = Size;
        CurrentStackLocation->Parameters.QueryInterface.Version = Version;
        CurrentStackLocation->Parameters.Read.ByteOffset = ByteOffset;
        CurrentStackLocation->Parameters.CreatePipe.Parameters = Parameters;
        goto LABEL_66;
      }
      goto LABEL_64;
    }
    v10 = MinorFunction - 1;
    if ( !v10 )
    {
      KeEnterCriticalRegion();
      if ( DeviceExtension[484] )
        DpiCheckForOutstandingD3Requests(DeviceExtension);
      ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
      *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244] = *((_DWORD *)DeviceExtension + 60);
      v16 = *((_DWORD *)DeviceExtension + 59);
      ++*((_DWORD *)DeviceExtension + 69);
      *((_DWORD *)DeviceExtension + 59) = 5;
      goto LABEL_16;
    }
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
      {
        KeEnterCriticalRegion();
        if ( DeviceExtension[484] )
          DpiCheckForOutstandingD3Requests(DeviceExtension);
        ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
        v14 = *((_DWORD *)DeviceExtension + 59) == 5;
        goto LABEL_14;
      }
      v13 = v12 - 2;
      if ( !v13 )
      {
        KeEnterCriticalRegion();
        if ( DeviceExtension[484] )
          DpiCheckForOutstandingD3Requests(DeviceExtension);
        ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
        *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244] = *((_DWORD *)DeviceExtension + 60);
        v16 = *((_DWORD *)DeviceExtension + 59);
        ++*((_DWORD *)DeviceExtension + 69);
        *((_DWORD *)DeviceExtension + 59) = 3;
        goto LABEL_16;
      }
      if ( v13 == 1 )
      {
        KeEnterCriticalRegion();
        if ( DeviceExtension[484] )
          DpiCheckForOutstandingD3Requests(DeviceExtension);
        ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
        v14 = *((_DWORD *)DeviceExtension + 59) == 3;
LABEL_14:
        if ( !v14 )
        {
LABEL_17:
          Status = 0;
LABEL_18:
          if ( DeviceExtension[484] )
            DpiEnableD3Requests(*((_QWORD *)DeviceExtension + 3));
          ExReleaseResourceLite(*((PERESOURCE *)DeviceExtension + 21));
          KeLeaveCriticalRegion();
          goto LABEL_66;
        }
        v15 = *((_DWORD *)DeviceExtension + 60);
        --*((_DWORD *)DeviceExtension + 69);
        *((_DWORD *)DeviceExtension + 59) = v15;
        v16 = *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244];
LABEL_16:
        *((_DWORD *)DeviceExtension + 60) = v16;
        goto LABEL_17;
      }
      goto LABEL_63;
    }
    if ( *((_DWORD *)DeviceExtension + 60) == 2 )
      DpiPdoHandleStopDevice(a1);
    v17 = (struct _IO_REMOVE_LOCK *)(DeviceExtension + 64);
    if ( DeviceExtension[509] )
    {
      IoReleaseRemoveLockEx(v17, v5, 0x20u);
    }
    else
    {
      IoReleaseRemoveLockAndWaitEx(v17, v5, 0x20u);
      IoQueueWorkItem(*((PIO_WORKITEM *)DeviceExtension + 119), DpiPdoDestroyPdo, DelayedWorkQueue, 0);
    }
    *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244] = *((_DWORD *)DeviceExtension + 60);
    v18 = *((_DWORD *)DeviceExtension + 59);
    ++*((_DWORD *)DeviceExtension + 69);
    *((_DWORD *)DeviceExtension + 60) = v18;
    *((_DWORD *)DeviceExtension + 59) = 7;
    WdLogSingleEntry1(4, a1);
    WdLogGlobalForLineNumber = 2314;
LABEL_33:
    Status = 0;
    goto LABEL_66;
  }
  v21 = MinorFunction - 10;
  if ( !v21 )
    goto LABEL_63;
  v22 = v21 - 1;
  if ( !v22 )
    goto LABEL_33;
  v23 = v22 - 11;
  if ( !v23 )
  {
    Status = -1073741823;
    goto LABEL_66;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    KeEnterCriticalRegion();
    if ( DeviceExtension[484] )
      DpiCheckForOutstandingD3Requests(DeviceExtension);
    ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
    Status = 0;
    *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244] = *((_DWORD *)DeviceExtension + 60);
    v30 = *((_DWORD *)DeviceExtension + 59);
    ++*((_DWORD *)DeviceExtension + 69);
    *((_DWORD *)DeviceExtension + 60) = v30;
    *((_DWORD *)DeviceExtension + 59) = 6;
    WdLogSingleEntry1(4, a1);
    WdLogGlobalForLineNumber = 2256;
    goto LABEL_18;
  }
  if ( v24 != 2 )
  {
LABEL_63:
    Status = Irp->IoStatus.Status;
    goto LABEL_64;
  }
  if ( !DeviceExtension[510] && *(_DWORD *)(v9 + 2840) >= 2u )
    IoInvalidateDeviceRelations(a1, PowerRelations);
  DeviceExtension[510] = 1;
  if ( DeviceExtension[944] )
    goto LABEL_65;
  v25 = *((_DWORD *)DeviceExtension + 124);
  if ( v25 == 1 )
  {
    LOBYTE(Irp) = 1;
    Status = DpiAcquireCoreSyncAccessSafe(a1, Irp);
    if ( Status >= 0 )
    {
      v27 = *(DXGADAPTER **)(v9 + 4032);
      Data = 0;
      if ( DXGADAPTER::IsAdapterSessionized(v27, v26, &Data, 0) )
        IoSetDevicePropertyData(a1, &DEVPKEY_Device_SessionId, 0, v28, 7u, 4u, &Data);
      MonitorNotifyDeviceNodeReady(*(DXGADAPTER **)(v9 + 4032), *((_DWORD *)DeviceExtension + 126), a1);
      LOBYTE(v29) = 1;
      DeviceExtension[944] = 1;
      DpiReleaseCoreSyncAccessSafe(a1, v29);
      if ( IsInternalVideoOutput(*(enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)(*((_QWORD *)DeviceExtension + 117) + 4LL)) )
        DpiPdoEnableDisableConnectSound(a1);
      goto LABEL_66;
    }
  }
  else
  {
    if ( v25 != 4 )
    {
LABEL_65:
      Status = v5->IoStatus.Status;
      goto LABEL_66;
    }
    IoSetDevicePropertyData(
      a1,
      &DEVPKEY_Gpu_Parent_Luid,
      0,
      0,
      8u,
      8u,
      (PVOID)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 4) + 64LL) + 2696LL));
  }
LABEL_64:
  if ( Status == -1073741637 )
    goto LABEL_65;
LABEL_66:
  v5->IoStatus.Status = Status;
  IofCompleteRequest(v5, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1403e8da0  push    rbp
0x1403e8da2  push    rbx
0x1403e8da3  push    rsi
0x1403e8da4  push    rdi
0x1403e8da5  push    r12
0x1403e8da7  push    r13
0x1403e8da9  push    r14
0x1403e8dab  push    r15
0x1403e8dad  mov     rbp, rsp
0x1403e8db0  sub     rsp, 78h
0x1403e8db4  mov     r15, [rdx+0B8h]
0x1403e8dbb  mov     rsi, rcx
0x1403e8dbe  mov     rbx, [rcx+40h]
0x1403e8dc2  xor     r12d, r12d
0x1403e8dc5  mov     r14, rdx
0x1403e8dc8  mov     edi, 0C00000BBh
0x1403e8dcd  movzx   ecx, byte ptr [r15+1]
0x1403e8dd2  cmp     cl, 18h
0x1403e8dd5  jnb     short loc_1403E8DF3
0x1403e8dd7  mov     rax, [rbx+rcx*8+120h]
0x1403e8ddf  test    rax, rax
0x1403e8de2  jz      short loc_1403E8DF3
0x1403e8de4  mov     rcx, rsi
0x1403e8de7  call    _guard_dispatch_icall
0x1403e8dec  mov     edi, eax
0x1403e8dee  jmp     loc_1403E9368
0x1403e8df3  mov     rax, [rbx+20h]
0x1403e8df7  mov     r13, [rax+40h]
0x1403e8dfb  cmp     ecx, 8
0x1403e8dfe  ja      loc_1403E9168
0x1403e8e04  jz      loc_1403E9091
0x1403e8e0a  sub     ecx, 1
0x1403e8e0d  jz      loc_1403E902E
0x1403e8e13  sub     ecx, 1
0x1403e8e16  jz      loc_1403E8F74
0x1403e8e1c  sub     ecx, 1
0x1403e8e1f  jz      loc_1403E8F36
0x1403e8e25  sub     ecx, 2
0x1403e8e28  jz      loc_1403E8ED3
0x1403e8e2e  cmp     ecx, 1
0x1403e8e31  jnz     loc_1403E9365
0x1403e8e37  call    cs:__imp_KeEnterCriticalRegion
0x1403e8e3e  nop     dword ptr [rax+rax+00h]
0x1403e8e43  cmp     [rbx+1E4h], r12b
0x1403e8e4a  jz      short loc_1403E8E54
0x1403e8e4c  mov     rcx, rbx
0x1403e8e4f  call    DpiCheckForOutstandingD3Requests
0x1403e8e54  mov     rcx, [rbx+0A8h]; Resource
0x1403e8e5b  mov     dl, 1; Wait
0x1403e8e5d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8e64  nop     dword ptr [rax+rax+00h]
0x1403e8e69  cmp     dword ptr [rbx+0ECh], 3
0x1403e8e70  jnz     short loc_1403E8E9A
0x1403e8e72  mov     eax, [rbx+0F0h]
0x1403e8e78  dec     dword ptr [rbx+114h]
0x1403e8e7e  mov     [rbx+0ECh], eax
0x1403e8e84  mov     eax, [rbx+114h]
0x1403e8e8a  and     eax, 7
0x1403e8e8d  mov     eax, [rbx+rax*4+0F4h]
0x1403e8e94  mov     [rbx+0F0h], eax
0x1403e8e9a  mov     edi, r12d
0x1403e8e9d  cmp     [rbx+1E4h], r12b
0x1403e8ea4  jz      short loc_1403E8EAF
0x1403e8ea6  mov     rcx, [rbx+18h]
0x1403e8eaa  call    DpiEnableD3Requests
0x1403e8eaf  mov     rcx, [rbx+0A8h]; Resource
0x1403e8eb6  call    cs:__imp_ExReleaseResourceLite
0x1403e8ebd  nop     dword ptr [rax+rax+00h]
0x1403e8ec2  call    cs:__imp_KeLeaveCriticalRegion
0x1403e8ec9  nop     dword ptr [rax+rax+00h]
0x1403e8ece  jmp     loc_1403E9374
0x1403e8ed3  call    cs:__imp_KeEnterCriticalRegion
0x1403e8eda  nop     dword ptr [rax+rax+00h]
0x1403e8edf  cmp     [rbx+1E4h], r12b
0x1403e8ee6  jz      short loc_1403E8EF0
0x1403e8ee8  mov     rcx, rbx
0x1403e8eeb  call    DpiCheckForOutstandingD3Requests
0x1403e8ef0  mov     rcx, [rbx+0A8h]; Resource
0x1403e8ef7  mov     dl, 1; Wait
0x1403e8ef9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8f00  nop     dword ptr [rax+rax+00h]
0x1403e8f05  mov     ecx, [rbx+114h]
0x1403e8f0b  mov     eax, [rbx+0F0h]
0x1403e8f11  and     ecx, 7
0x1403e8f14  mov     [rbx+rcx*4+0F4h], eax
0x1403e8f1b  mov     eax, [rbx+0ECh]
0x1403e8f21  inc     dword ptr [rbx+114h]
0x1403e8f27  mov     dword ptr [rbx+0ECh], 3
0x1403e8f31  jmp     loc_1403E8E94
0x1403e8f36  call    cs:__imp_KeEnterCriticalRegion
0x1403e8f3d  nop     dword ptr [rax+rax+00h]
0x1403e8f42  cmp     [rbx+1E4h], r12b
0x1403e8f49  jz      short loc_1403E8F53
0x1403e8f4b  mov     rcx, rbx
0x1403e8f4e  call    DpiCheckForOutstandingD3Requests
0x1403e8f53  mov     rcx, [rbx+0A8h]; Resource
0x1403e8f5a  mov     dl, 1; Wait
0x1403e8f5c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8f63  nop     dword ptr [rax+rax+00h]
0x1403e8f68  cmp     dword ptr [rbx+0ECh], 5
0x1403e8f6f  jmp     loc_1403E8E70
0x1403e8f74  cmp     dword ptr [rbx+0F0h], 2
0x1403e8f7b  jnz     short loc_1403E8F85
0x1403e8f7d  mov     rcx, rsi
0x1403e8f80  call    DpiPdoHandleStopDevice
0x1403e8f85  lea     rcx, [rbx+40h]; RemoveLock
0x1403e8f89  mov     r8d, 20h ; ' '; RemlockSize
0x1403e8f8f  mov     rdx, r14; Tag
0x1403e8f92  cmp     [rbx+1FDh], r12b
0x1403e8f99  jnz     short loc_1403E8FCA
0x1403e8f9b  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1403e8fa2  nop     dword ptr [rax+rax+00h]
0x1403e8fa7  mov     rcx, [rbx+3B8h]; IoWorkItem
0x1403e8fae  lea     rdx, DpiPdoDestroyPdo; WorkerRoutine
0x1403e8fb5  xor     r9d, r9d; Context
0x1403e8fb8  lea     r8d, [r9+1]; QueueType
0x1403e8fbc  call    cs:__imp_IoQueueWorkItem
0x1403e8fc3  nop     dword ptr [rax+rax+00h]
0x1403e8fc8  jmp     short loc_1403E8FD6
0x1403e8fca  call    cs:__imp_IoReleaseRemoveLockEx
0x1403e8fd1  nop     dword ptr [rax+rax+00h]
0x1403e8fd6  mov     ecx, [rbx+114h]
0x1403e8fdc  mov     eax, [rbx+0F0h]
0x1403e8fe2  and     ecx, 7
0x1403e8fe5  mov     [rbx+rcx*4+0F4h], eax
0x1403e8fec  mov     eax, [rbx+0ECh]
0x1403e8ff2  inc     dword ptr [rbx+114h]
0x1403e8ff8  mov     [rbx+0F0h], eax
0x1403e8ffe  mov     dword ptr [rbx+0ECh], 7
0x1403e9008  mov     rdx, rsi
0x1403e900b  mov     ecx, 4
0x1403e9010  call    cs:__imp_WdLogSingleEntry1
0x1403e9017  nop     dword ptr [rax+rax+00h]
0x1403e901c  mov     cs:WdLogGlobalForLineNumber, 90Ah
0x1403e9026  mov     edi, r12d
0x1403e9029  jmp     loc_1403E9374
0x1403e902e  call    cs:__imp_KeEnterCriticalRegion
0x1403e9035  nop     dword ptr [rax+rax+00h]
0x1403e903a  cmp     [rbx+1E4h], r12b
0x1403e9041  jz      short loc_1403E904B
0x1403e9043  mov     rcx, rbx
0x1403e9046  call    DpiCheckForOutstandingD3Requests
0x1403e904b  mov     rcx, [rbx+0A8h]; Resource
0x1403e9052  mov     dl, 1; Wait
0x1403e9054  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e905b  nop     dword ptr [rax+rax+00h]
0x1403e9060  mov     ecx, [rbx+114h]
0x1403e9066  mov     eax, [rbx+0F0h]
0x1403e906c  and     ecx, 7
0x1403e906f  mov     [rbx+rcx*4+0F4h], eax
0x1403e9076  mov     eax, [rbx+0ECh]
0x1403e907c  inc     dword ptr [rbx+114h]
0x1403e9082  mov     dword ptr [rbx+0ECh], 5
0x1403e908c  jmp     loc_1403E8E94
0x1403e9091  cmp     [rdx+30h], edi
0x1403e9094  jnz     loc_1403E9370
0x1403e909a  mov     rax, [r15+8]
0x1403e909e  mov     rdi, [rbx+28h]
0x1403e90a2  mov     [rbp+var_38], rax
0x1403e90a6  movzx   eax, word ptr [r15+10h]
0x1403e90ab  mov     [rbp+var_30], ax
0x1403e90af  movzx   eax, word ptr [r15+12h]
0x1403e90b4  mov     [rbp+var_2E], ax
0x1403e90b8  mov     rax, [r15+18h]
0x1403e90bc  mov     [rbp+var_28], rax
0x1403e90c0  mov     rax, [r15+20h]
0x1403e90c4  mov     [rbp+var_20], rax
0x1403e90c8  mov     eax, [rbx+1F8h]
0x1403e90ce  mov     [rbp+var_18], eax
0x1403e90d1  mov     [rbp+var_2C], r12d
0x1403e90d5  mov     [rbp+var_14], r12d
0x1403e90d9  cmp     [rdi+100h], r12
0x1403e90e0  jz      loc_1403E9370
0x1403e90e6  mov     dl, 1
0x1403e90e8  mov     rcx, rsi
0x1403e90eb  call    DpiAcquireCoreSyncAccessSafe
0x1403e90f0  test    eax, eax
0x1403e90f2  js      loc_1403E9370
0x1403e90f8  mov     rcx, [r13+0FC0h]
0x1403e90ff  mov     edx, 1
0x1403e9104  call    DxgkAcquireAdapterDdiSync
0x1403e9109  mov     rdx, [rbx+30h]
0x1403e910d  lea     r8, [rbp+var_38]
0x1403e9111  mov     rcx, rdi
0x1403e9114  call    DpiDxgkDdiQueryInterface
0x1403e9119  mov     rcx, [r13+0FC0h]
0x1403e9120  mov     edi, eax
0x1403e9122  call    DxgkReleaseAdapterDdiSync
0x1403e9127  mov     dl, 1
0x1403e9129  mov     rcx, rsi
0x1403e912c  call    DpiReleaseCoreSyncAccessSafe
0x1403e9131  test    edi, edi
0x1403e9133  js      loc_1403E9368
0x1403e9139  mov     rax, [rbp+var_38]
0x1403e913d  mov     [r15+8], rax
0x1403e9141  movzx   eax, [rbp+var_30]
0x1403e9145  mov     [r15+10h], ax
0x1403e914a  movzx   eax, [rbp+var_2E]
0x1403e914e  mov     [r15+12h], ax
0x1403e9153  mov     rax, [rbp+var_28]
0x1403e9157  mov     [r15+18h], rax
0x1403e915b  mov     rax, [rbp+var_20]
0x1403e915f  mov     [r15+20h], rax
0x1403e9163  jmp     loc_1403E9374
0x1403e9168  sub     ecx, 0Ah
0x1403e916b  jz      loc_1403E9365
0x1403e9171  sub     ecx, 1
0x1403e9174  jz      loc_1403E9026
0x1403e917a  sub     ecx, 0Bh
0x1403e917d  jz      loc_1403E935E
0x1403e9183  sub     ecx, 1
0x1403e9186  jz      loc_1403E92D4
0x1403e918c  cmp     ecx, 2
0x1403e918f  jnz     loc_1403E9365
0x1403e9195  cmp     [rbx+1FEh], r12b
0x1403e919c  jnz     short loc_1403E91B8
0x1403e919e  cmp     [r13+0B18h], ecx
0x1403e91a5  jb      short loc_1403E91B8
0x1403e91a7  mov     edx, ecx; Type
0x1403e91a9  mov     rcx, rsi; DeviceObject
0x1403e91ac  call    cs:__imp_IoInvalidateDeviceRelations
0x1403e91b3  nop     dword ptr [rax+rax+00h]
0x1403e91b8  mov     byte ptr [rbx+1FEh], 1
0x1403e91bf  cmp     [rbx+3B0h], r12b
0x1403e91c6  jnz     loc_1403E9370
0x1403e91cc  mov     eax, [rbx+1F0h]
0x1403e91d2  cmp     eax, 1
0x1403e91d5  jnz     loc_1403E9286
0x1403e91db  mov     dl, al
0x1403e91dd  mov     rcx, rsi
0x1403e91e0  call    DpiAcquireCoreSyncAccessSafe
0x1403e91e5  mov     edi, eax
0x1403e91e7  test    eax, eax
0x1403e91e9  js      loc_1403E9368
0x1403e91ef  mov     rcx, [r13+0FC0h]; this
0x1403e91f6  lea     r8, [rbp+arg_0]; unsigned int *
0x1403e91fa  xor     r9d, r9d; unsigned __int64 *
0x1403e91fd  mov     [rbp+arg_0], r12d
0x1403e9201  call    ?IsAdapterSessionized@DXGADAPTER@@QEBA_NPEAU_LUID@@PEAIPEA_K@Z; DXGADAPTER::IsAdapterSessionized(_LUID *,uint *,unsigned __int64 *)
0x1403e9206  test    al, al
0x1403e9208  jz      short loc_1403E923C
0x1403e920a  lea     rax, [rbp+arg_0]
0x1403e920e  xor     r8d, r8d; Lcid
0x1403e9211  mov     [rsp+78h+Data], rax; Data
0x1403e9216  lea     rdx, DEVPKEY_Device_SessionId; PropertyKey
0x1403e921d  mov     [rsp+78h+Size], 4; Size
0x1403e9225  mov     rcx, rsi; Pdo
0x1403e9228  mov     [rsp+78h+Type], 7; Type
0x1403e9230  call    cs:__imp_IoSetDevicePropertyData
0x1403e9237  nop     dword ptr [rax+rax+00h]
0x1403e923c  mov     edx, [rbx+1F8h]; unsigned int
0x1403e9242  mov     r8, rsi; struct _DEVICE_OBJECT *
0x1403e9245  mov     rcx, [r13+0FC0h]; this
0x1403e924c  call    ?MonitorNotifyDeviceNodeReady@@YAJPEAXIPEAU_DEVICE_OBJECT@@@Z; MonitorNotifyDeviceNodeReady(void *,uint,_DEVICE_OBJECT *)
0x1403e9251  mov     dl, 1
0x1403e9253  mov     byte ptr [rbx+3B0h], 1
0x1403e925a  mov     rcx, rsi
0x1403e925d  call    DpiReleaseCoreSyncAccessSafe
0x1403e9262  mov     rcx, [rbx+3A8h]
0x1403e9269  mov     ecx, [rcx+4]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1403e926c  call    ?IsInternalVideoOutput@@YAEW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@@Z; IsInternalVideoOutput(_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY)
0x1403e9271  test    al, al
0x1403e9273  jz      loc_1403E9374
0x1403e9279  mov     rcx, rsi
0x1403e927c  call    DpiPdoEnableDisableConnectSound
0x1403e9281  jmp     loc_1403E9374
0x1403e9286  cmp     eax, 4
0x1403e9289  jnz     loc_1403E9370
0x1403e928f  mov     rax, [rbx+20h]
0x1403e9293  lea     rdx, DEVPKEY_Gpu_Parent_Luid; PropertyKey
0x1403e929a  xor     r9d, r9d; Flags
0x1403e929d  xor     r8d, r8d; Lcid
0x1403e92a0  mov     rcx, [rax+40h]
0x1403e92a4  add     rcx, 0A88h
0x1403e92ab  mov     [rsp+78h+Data], rcx; Data
0x1403e92b0  mov     rcx, rsi; Pdo
0x1403e92b3  mov     [rsp+78h+Size], 8; Size
0x1403e92bb  mov     [rsp+78h+Type], 8; Type
0x1403e92c3  call    cs:__imp_IoSetDevicePropertyData
0x1403e92ca  nop     dword ptr [rax+rax+00h]
0x1403e92cf  jmp     loc_1403E9368
0x1403e92d4  call    cs:__imp_KeEnterCriticalRegion
0x1403e92db  nop     dword ptr [rax+rax+00h]
0x1403e92e0  cmp     [rbx+1E4h], r12b
0x1403e92e7  jz      short loc_1403E92F1
0x1403e92e9  mov     rcx, rbx
0x1403e92ec  call    DpiCheckForOutstandingD3Requests
0x1403e92f1  mov     rcx, [rbx+0A8h]; Resource
0x1403e92f8  mov     dl, 1; Wait
0x1403e92fa  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e9301  nop     dword ptr [rax+rax+00h]
0x1403e9306  mov     ecx, [rbx+114h]
0x1403e930c  mov     edi, r12d
0x1403e930f  mov     eax, [rbx+0F0h]
0x1403e9315  and     ecx, 7
0x1403e9318  mov     [rbx+rcx*4+0F4h], eax
0x1403e931f  mov     eax, [rbx+0ECh]
0x1403e9325  inc     dword ptr [rbx+114h]
0x1403e932b  mov     [rbx+0F0h], eax
0x1403e9331  mov     dword ptr [rbx+0ECh], 6
  ... truncated ...
```
