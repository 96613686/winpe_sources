# DpiPdoDispatchPnp

- ea: `0x1403e8a70`
- end: `0x1403e906d`
- name: `DpiPdoDispatchPnp`
- size: `1533`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140022264`
- `0x14004546c`
- `0x14004bd5c`
- `0x1400a01e0`
- `0x1401887bc`
- `0x14018fd6c`
- `0x140191264`
- `0x1402bd6f8`
- `0x1402be090`
- `0x1402bef00`
- `0x1403668f8`
- `0x140367514`
- `0x1403676e0`
- `0x1403e8a70`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8b07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8ba3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8c06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8cfe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8fa4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8b07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8ba3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8c06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8cfe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403e8fa4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403e8b92`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403e8b92`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8b2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8bc9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8c2c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8d24`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8fca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8b2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8bc9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8c2c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8d24`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403e8fca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403e8b86`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403e8b86`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1403e8e7c`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1403e8e7c`
- `ntoskrnl!IofCompleteRequest` at `0x1403e904d`
- `ntoskrnl!IofCompleteRequest` at `0x1403e904d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403e8c9a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403e8c9a`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e8f00`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e8f93`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e8f00`
- `ntoskrnl!IoSetDevicePropertyData` at `0x1403e8f93`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1403e8c6b`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1403e8c6b`
- `ntoskrnl!IoQueueWorkItem` at `0x1403e8c8c`
- `ntoskrnl!IoQueueWorkItem` at `0x1403e8c8c`
- `watchdog!WdLogSingleEntry1` at `0x1403e8ce0`
- `watchdog!WdLogSingleEntry1` at `0x1403e9013`
- `watchdog!WdLogSingleEntry1` at `0x1403e8ce0`
- `watchdog!WdLogSingleEntry1` at `0x1403e9013`

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
    WdLogSingleEntry1(4);
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
    WdLogSingleEntry1(4);
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
0x1403e8a70  push    rbp
0x1403e8a72  push    rbx
0x1403e8a73  push    rsi
0x1403e8a74  push    rdi
0x1403e8a75  push    r12
0x1403e8a77  push    r13
0x1403e8a79  push    r14
0x1403e8a7b  push    r15
0x1403e8a7d  mov     rbp, rsp
0x1403e8a80  sub     rsp, 78h
0x1403e8a84  mov     r15, [rdx+0B8h]
0x1403e8a8b  mov     rsi, rcx
0x1403e8a8e  mov     rbx, [rcx+40h]
0x1403e8a92  xor     r12d, r12d
0x1403e8a95  mov     r14, rdx
0x1403e8a98  mov     edi, 0C00000BBh
0x1403e8a9d  movzx   ecx, byte ptr [r15+1]
0x1403e8aa2  cmp     cl, 18h
0x1403e8aa5  jnb     short loc_1403E8AC3
0x1403e8aa7  mov     rax, [rbx+rcx*8+120h]
0x1403e8aaf  test    rax, rax
0x1403e8ab2  jz      short loc_1403E8AC3
0x1403e8ab4  mov     rcx, rsi
0x1403e8ab7  call    _guard_dispatch_icall
0x1403e8abc  mov     edi, eax
0x1403e8abe  jmp     loc_1403E9038
0x1403e8ac3  mov     rax, [rbx+20h]
0x1403e8ac7  mov     r13, [rax+40h]
0x1403e8acb  cmp     ecx, 8
0x1403e8ace  ja      loc_1403E8E38
0x1403e8ad4  jz      loc_1403E8D61
0x1403e8ada  sub     ecx, 1
0x1403e8add  jz      loc_1403E8CFE
0x1403e8ae3  sub     ecx, 1
0x1403e8ae6  jz      loc_1403E8C44
0x1403e8aec  sub     ecx, 1
0x1403e8aef  jz      loc_1403E8C06
0x1403e8af5  sub     ecx, 2
0x1403e8af8  jz      loc_1403E8BA3
0x1403e8afe  cmp     ecx, 1
0x1403e8b01  jnz     loc_1403E9035
0x1403e8b07  call    cs:__imp_KeEnterCriticalRegion
0x1403e8b0e  nop     dword ptr [rax+rax+00h]
0x1403e8b13  cmp     [rbx+1E4h], r12b
0x1403e8b1a  jz      short loc_1403E8B24
0x1403e8b1c  mov     rcx, rbx
0x1403e8b1f  call    DpiCheckForOutstandingD3Requests
0x1403e8b24  mov     rcx, [rbx+0A8h]; Resource
0x1403e8b2b  mov     dl, 1; Wait
0x1403e8b2d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8b34  nop     dword ptr [rax+rax+00h]
0x1403e8b39  cmp     dword ptr [rbx+0ECh], 3
0x1403e8b40  jnz     short loc_1403E8B6A
0x1403e8b42  mov     eax, [rbx+0F0h]
0x1403e8b48  dec     dword ptr [rbx+114h]
0x1403e8b4e  mov     [rbx+0ECh], eax
0x1403e8b54  mov     eax, [rbx+114h]
0x1403e8b5a  and     eax, 7
0x1403e8b5d  mov     eax, [rbx+rax*4+0F4h]
0x1403e8b64  mov     [rbx+0F0h], eax
0x1403e8b6a  mov     edi, r12d
0x1403e8b6d  cmp     [rbx+1E4h], r12b
0x1403e8b74  jz      short loc_1403E8B7F
0x1403e8b76  mov     rcx, [rbx+18h]
0x1403e8b7a  call    DpiEnableD3Requests
0x1403e8b7f  mov     rcx, [rbx+0A8h]; Resource
0x1403e8b86  call    cs:__imp_ExReleaseResourceLite
0x1403e8b8d  nop     dword ptr [rax+rax+00h]
0x1403e8b92  call    cs:__imp_KeLeaveCriticalRegion
0x1403e8b99  nop     dword ptr [rax+rax+00h]
0x1403e8b9e  jmp     loc_1403E9044
0x1403e8ba3  call    cs:__imp_KeEnterCriticalRegion
0x1403e8baa  nop     dword ptr [rax+rax+00h]
0x1403e8baf  cmp     [rbx+1E4h], r12b
0x1403e8bb6  jz      short loc_1403E8BC0
0x1403e8bb8  mov     rcx, rbx
0x1403e8bbb  call    DpiCheckForOutstandingD3Requests
0x1403e8bc0  mov     rcx, [rbx+0A8h]; Resource
0x1403e8bc7  mov     dl, 1; Wait
0x1403e8bc9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8bd0  nop     dword ptr [rax+rax+00h]
0x1403e8bd5  mov     ecx, [rbx+114h]
0x1403e8bdb  mov     eax, [rbx+0F0h]
0x1403e8be1  and     ecx, 7
0x1403e8be4  mov     [rbx+rcx*4+0F4h], eax
0x1403e8beb  mov     eax, [rbx+0ECh]
0x1403e8bf1  inc     dword ptr [rbx+114h]
0x1403e8bf7  mov     dword ptr [rbx+0ECh], 3
0x1403e8c01  jmp     loc_1403E8B64
0x1403e8c06  call    cs:__imp_KeEnterCriticalRegion
0x1403e8c0d  nop     dword ptr [rax+rax+00h]
0x1403e8c12  cmp     [rbx+1E4h], r12b
0x1403e8c19  jz      short loc_1403E8C23
0x1403e8c1b  mov     rcx, rbx
0x1403e8c1e  call    DpiCheckForOutstandingD3Requests
0x1403e8c23  mov     rcx, [rbx+0A8h]; Resource
0x1403e8c2a  mov     dl, 1; Wait
0x1403e8c2c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8c33  nop     dword ptr [rax+rax+00h]
0x1403e8c38  cmp     dword ptr [rbx+0ECh], 5
0x1403e8c3f  jmp     loc_1403E8B40
0x1403e8c44  cmp     dword ptr [rbx+0F0h], 2
0x1403e8c4b  jnz     short loc_1403E8C55
0x1403e8c4d  mov     rcx, rsi
0x1403e8c50  call    DpiPdoHandleStopDevice
0x1403e8c55  lea     rcx, [rbx+40h]; RemoveLock
0x1403e8c59  mov     r8d, 20h ; ' '; RemlockSize
0x1403e8c5f  mov     rdx, r14; Tag
0x1403e8c62  cmp     [rbx+1FDh], r12b
0x1403e8c69  jnz     short loc_1403E8C9A
0x1403e8c6b  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1403e8c72  nop     dword ptr [rax+rax+00h]
0x1403e8c77  mov     rcx, [rbx+3B8h]; IoWorkItem
0x1403e8c7e  lea     rdx, DpiPdoDestroyPdo; WorkerRoutine
0x1403e8c85  xor     r9d, r9d; Context
0x1403e8c88  lea     r8d, [r9+1]; QueueType
0x1403e8c8c  call    cs:__imp_IoQueueWorkItem
0x1403e8c93  nop     dword ptr [rax+rax+00h]
0x1403e8c98  jmp     short loc_1403E8CA6
0x1403e8c9a  call    cs:__imp_IoReleaseRemoveLockEx
0x1403e8ca1  nop     dword ptr [rax+rax+00h]
0x1403e8ca6  mov     ecx, [rbx+114h]
0x1403e8cac  mov     eax, [rbx+0F0h]
0x1403e8cb2  and     ecx, 7
0x1403e8cb5  mov     [rbx+rcx*4+0F4h], eax
0x1403e8cbc  mov     eax, [rbx+0ECh]
0x1403e8cc2  inc     dword ptr [rbx+114h]
0x1403e8cc8  mov     [rbx+0F0h], eax
0x1403e8cce  mov     dword ptr [rbx+0ECh], 7
0x1403e8cd8  mov     rdx, rsi
0x1403e8cdb  mov     ecx, 4
0x1403e8ce0  call    cs:__imp_WdLogSingleEntry1
0x1403e8ce7  nop     dword ptr [rax+rax+00h]
0x1403e8cec  mov     cs:WdLogGlobalForLineNumber, 90Ah
0x1403e8cf6  mov     edi, r12d
0x1403e8cf9  jmp     loc_1403E9044
0x1403e8cfe  call    cs:__imp_KeEnterCriticalRegion
0x1403e8d05  nop     dword ptr [rax+rax+00h]
0x1403e8d0a  cmp     [rbx+1E4h], r12b
0x1403e8d11  jz      short loc_1403E8D1B
0x1403e8d13  mov     rcx, rbx
0x1403e8d16  call    DpiCheckForOutstandingD3Requests
0x1403e8d1b  mov     rcx, [rbx+0A8h]; Resource
0x1403e8d22  mov     dl, 1; Wait
0x1403e8d24  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8d2b  nop     dword ptr [rax+rax+00h]
0x1403e8d30  mov     ecx, [rbx+114h]
0x1403e8d36  mov     eax, [rbx+0F0h]
0x1403e8d3c  and     ecx, 7
0x1403e8d3f  mov     [rbx+rcx*4+0F4h], eax
0x1403e8d46  mov     eax, [rbx+0ECh]
0x1403e8d4c  inc     dword ptr [rbx+114h]
0x1403e8d52  mov     dword ptr [rbx+0ECh], 5
0x1403e8d5c  jmp     loc_1403E8B64
0x1403e8d61  cmp     [rdx+30h], edi
0x1403e8d64  jnz     loc_1403E9040
0x1403e8d6a  mov     rax, [r15+8]
0x1403e8d6e  mov     rdi, [rbx+28h]
0x1403e8d72  mov     [rbp+var_38], rax
0x1403e8d76  movzx   eax, word ptr [r15+10h]
0x1403e8d7b  mov     [rbp+var_30], ax
0x1403e8d7f  movzx   eax, word ptr [r15+12h]
0x1403e8d84  mov     [rbp+var_2E], ax
0x1403e8d88  mov     rax, [r15+18h]
0x1403e8d8c  mov     [rbp+var_28], rax
0x1403e8d90  mov     rax, [r15+20h]
0x1403e8d94  mov     [rbp+var_20], rax
0x1403e8d98  mov     eax, [rbx+1F8h]
0x1403e8d9e  mov     [rbp+var_18], eax
0x1403e8da1  mov     [rbp+var_2C], r12d
0x1403e8da5  mov     [rbp+var_14], r12d
0x1403e8da9  cmp     [rdi+100h], r12
0x1403e8db0  jz      loc_1403E9040
0x1403e8db6  mov     dl, 1
0x1403e8db8  mov     rcx, rsi
0x1403e8dbb  call    DpiAcquireCoreSyncAccessSafe
0x1403e8dc0  test    eax, eax
0x1403e8dc2  js      loc_1403E9040
0x1403e8dc8  mov     rcx, [r13+0FC0h]
0x1403e8dcf  mov     edx, 1
0x1403e8dd4  call    DxgkAcquireAdapterDdiSync
0x1403e8dd9  mov     rdx, [rbx+30h]
0x1403e8ddd  lea     r8, [rbp+var_38]
0x1403e8de1  mov     rcx, rdi
0x1403e8de4  call    DpiDxgkDdiQueryInterface
0x1403e8de9  mov     rcx, [r13+0FC0h]
0x1403e8df0  mov     edi, eax
0x1403e8df2  call    DxgkReleaseAdapterDdiSync
0x1403e8df7  mov     dl, 1
0x1403e8df9  mov     rcx, rsi
0x1403e8dfc  call    DpiReleaseCoreSyncAccessSafe
0x1403e8e01  test    edi, edi
0x1403e8e03  js      loc_1403E9038
0x1403e8e09  mov     rax, [rbp+var_38]
0x1403e8e0d  mov     [r15+8], rax
0x1403e8e11  movzx   eax, [rbp+var_30]
0x1403e8e15  mov     [r15+10h], ax
0x1403e8e1a  movzx   eax, [rbp+var_2E]
0x1403e8e1e  mov     [r15+12h], ax
0x1403e8e23  mov     rax, [rbp+var_28]
0x1403e8e27  mov     [r15+18h], rax
0x1403e8e2b  mov     rax, [rbp+var_20]
0x1403e8e2f  mov     [r15+20h], rax
0x1403e8e33  jmp     loc_1403E9044
0x1403e8e38  sub     ecx, 0Ah
0x1403e8e3b  jz      loc_1403E9035
0x1403e8e41  sub     ecx, 1
0x1403e8e44  jz      loc_1403E8CF6
0x1403e8e4a  sub     ecx, 0Bh
0x1403e8e4d  jz      loc_1403E902E
0x1403e8e53  sub     ecx, 1
0x1403e8e56  jz      loc_1403E8FA4
0x1403e8e5c  cmp     ecx, 2
0x1403e8e5f  jnz     loc_1403E9035
0x1403e8e65  cmp     [rbx+1FEh], r12b
0x1403e8e6c  jnz     short loc_1403E8E88
0x1403e8e6e  cmp     [r13+0B18h], ecx
0x1403e8e75  jb      short loc_1403E8E88
0x1403e8e77  mov     edx, ecx; Type
0x1403e8e79  mov     rcx, rsi; DeviceObject
0x1403e8e7c  call    cs:__imp_IoInvalidateDeviceRelations
0x1403e8e83  nop     dword ptr [rax+rax+00h]
0x1403e8e88  mov     byte ptr [rbx+1FEh], 1
0x1403e8e8f  cmp     [rbx+3B0h], r12b
0x1403e8e96  jnz     loc_1403E9040
0x1403e8e9c  mov     eax, [rbx+1F0h]
0x1403e8ea2  cmp     eax, 1
0x1403e8ea5  jnz     loc_1403E8F56
0x1403e8eab  mov     dl, al
0x1403e8ead  mov     rcx, rsi
0x1403e8eb0  call    DpiAcquireCoreSyncAccessSafe
0x1403e8eb5  mov     edi, eax
0x1403e8eb7  test    eax, eax
0x1403e8eb9  js      loc_1403E9038
0x1403e8ebf  mov     rcx, [r13+0FC0h]; this
0x1403e8ec6  lea     r8, [rbp+arg_0]; unsigned int *
0x1403e8eca  xor     r9d, r9d; unsigned __int64 *
0x1403e8ecd  mov     [rbp+arg_0], r12d
0x1403e8ed1  call    ?IsAdapterSessionized@DXGADAPTER@@QEBA_NPEAU_LUID@@PEAIPEA_K@Z; DXGADAPTER::IsAdapterSessionized(_LUID *,uint *,unsigned __int64 *)
0x1403e8ed6  test    al, al
0x1403e8ed8  jz      short loc_1403E8F0C
0x1403e8eda  lea     rax, [rbp+arg_0]
0x1403e8ede  xor     r8d, r8d; Lcid
0x1403e8ee1  mov     [rsp+78h+Data], rax; Data
0x1403e8ee6  lea     rdx, DEVPKEY_Device_SessionId; PropertyKey
0x1403e8eed  mov     [rsp+78h+Size], 4; Size
0x1403e8ef5  mov     rcx, rsi; Pdo
0x1403e8ef8  mov     [rsp+78h+Type], 7; Type
0x1403e8f00  call    cs:__imp_IoSetDevicePropertyData
0x1403e8f07  nop     dword ptr [rax+rax+00h]
0x1403e8f0c  mov     edx, [rbx+1F8h]; unsigned int
0x1403e8f12  mov     r8, rsi; struct _DEVICE_OBJECT *
0x1403e8f15  mov     rcx, [r13+0FC0h]; this
0x1403e8f1c  call    ?MonitorNotifyDeviceNodeReady@@YAJPEAXIPEAU_DEVICE_OBJECT@@@Z; MonitorNotifyDeviceNodeReady(void *,uint,_DEVICE_OBJECT *)
0x1403e8f21  mov     dl, 1
0x1403e8f23  mov     byte ptr [rbx+3B0h], 1
0x1403e8f2a  mov     rcx, rsi
0x1403e8f2d  call    DpiReleaseCoreSyncAccessSafe
0x1403e8f32  mov     rcx, [rbx+3A8h]
0x1403e8f39  mov     ecx, [rcx+4]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1403e8f3c  call    ?IsInternalVideoOutput@@YAEW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@@Z; IsInternalVideoOutput(_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY)
0x1403e8f41  test    al, al
0x1403e8f43  jz      loc_1403E9044
0x1403e8f49  mov     rcx, rsi
0x1403e8f4c  call    DpiPdoEnableDisableConnectSound
0x1403e8f51  jmp     loc_1403E9044
0x1403e8f56  cmp     eax, 4
0x1403e8f59  jnz     loc_1403E9040
0x1403e8f5f  mov     rax, [rbx+20h]
0x1403e8f63  lea     rdx, DEVPKEY_Gpu_Parent_Luid; PropertyKey
0x1403e8f6a  xor     r9d, r9d; Flags
0x1403e8f6d  xor     r8d, r8d; Lcid
0x1403e8f70  mov     rcx, [rax+40h]
0x1403e8f74  add     rcx, 0A88h
0x1403e8f7b  mov     [rsp+78h+Data], rcx; Data
0x1403e8f80  mov     rcx, rsi; Pdo
0x1403e8f83  mov     [rsp+78h+Size], 8; Size
0x1403e8f8b  mov     [rsp+78h+Type], 8; Type
0x1403e8f93  call    cs:__imp_IoSetDevicePropertyData
0x1403e8f9a  nop     dword ptr [rax+rax+00h]
0x1403e8f9f  jmp     loc_1403E9038
0x1403e8fa4  call    cs:__imp_KeEnterCriticalRegion
0x1403e8fab  nop     dword ptr [rax+rax+00h]
0x1403e8fb0  cmp     [rbx+1E4h], r12b
0x1403e8fb7  jz      short loc_1403E8FC1
0x1403e8fb9  mov     rcx, rbx
0x1403e8fbc  call    DpiCheckForOutstandingD3Requests
0x1403e8fc1  mov     rcx, [rbx+0A8h]; Resource
0x1403e8fc8  mov     dl, 1; Wait
0x1403e8fca  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403e8fd1  nop     dword ptr [rax+rax+00h]
0x1403e8fd6  mov     ecx, [rbx+114h]
0x1403e8fdc  mov     edi, r12d
0x1403e8fdf  mov     eax, [rbx+0F0h]
0x1403e8fe5  and     ecx, 7
0x1403e8fe8  mov     [rbx+rcx*4+0F4h], eax
0x1403e8fef  mov     eax, [rbx+0ECh]
0x1403e8ff5  inc     dword ptr [rbx+114h]
0x1403e8ffb  mov     [rbx+0F0h], eax
0x1403e9001  mov     dword ptr [rbx+0ECh], 6
  ... truncated ...
```
