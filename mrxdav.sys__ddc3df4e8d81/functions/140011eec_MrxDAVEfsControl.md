# MrxDAVEfsControl

- ea: `0x140011eec`
- end: `0x14001270e`
- name: `MrxDAVEfsControl`
- size: `2082`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011440`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001948`
- `0x140001978`
- `0x140001b64`
- `0x140001c30`
- `0x140002138`
- `0x1400024b0`
- `0x140011eec`
- `0x140025b9c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400126a6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400126a6`
- `ntoskrnl!ProbeForRead` at `0x1400120b0`
- `ntoskrnl!ProbeForRead` at `0x1400120b0`
- `ntoskrnl!KeInitializeEvent` at `0x1400122f3`
- `ntoskrnl!KeInitializeEvent` at `0x1400122f3`
- `ntoskrnl!IoAllocateMdl` at `0x140012388`
- `ntoskrnl!IoAllocateMdl` at `0x140012388`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140012425`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140012425`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140012438`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001245f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140028f03`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140012438`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001245f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140028f03`
- `ntoskrnl!IofCallDriver` at `0x14001244c`
- `ntoskrnl!IofCallDriver` at `0x14001244c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012494`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012494`
- `ntoskrnl!IoFreeMdl` at `0x14001218b`
- `ntoskrnl!IoFreeMdl` at `0x14001218b`
- `rdbss!RxCeFreeIrp` at `0x14001219a`
- `rdbss!RxCeFreeIrp` at `0x14001219a`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14001216c`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14001216c`
- `rdbss!RxCeAllocateIrpWithMDL` at `0x14001230c`
- `rdbss!RxCeAllocateIrpWithMDL` at `0x14001230c`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140011f7f`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140011f7f`

## pseudocode

```c
__int64 __fastcall MrxDAVEfsControl(__int64 a1)
{
  __int64 v2; // r15
  __int64 v3; // r14
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r13
  int v8; // r8d
  NTSTATUS Status; // edi
  int v10; // eax
  __int64 v11; // rax
  _DWORD *v12; // rcx
  SIZE_T v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  char v17; // al
  char v18; // bl
  struct _MDL *MdlAddress; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  PIRP IrpWithMDL; // rdi
  void *v24; // rcx
  __int64 v25; // rdx
  ULONG v26; // edx
  PMDL Mdl; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *v29; // rax
  int v30; // ecx
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rbx
  HANDLE CurrentThreadId; // rax
  int v35; // [rsp+30h] [rbp-B8h]
  int v36; // [rsp+38h] [rbp-B0h]
  _DWORD *v37; // [rsp+38h] [rbp-B0h]
  PIRP pIrp; // [rsp+40h] [rbp-A8h]
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-A0h] BYREF
  PIRP TopLevelIrp; // [rsp+58h] [rbp-90h]
  __int64 v41; // [rsp+60h] [rbp-88h]
  PDEVICE_OBJECT DeviceObject; // [rsp+68h] [rbp-80h]
  __int64 v43; // [rsp+70h] [rbp-78h]
  int v44; // [rsp+78h] [rbp-70h]
  __int64 v45; // [rsp+80h] [rbp-68h]
  __int64 v46; // [rsp+88h] [rbp-60h]
  struct _KEVENT Event; // [rsp+90h] [rbp-58h] BYREF
  char v48; // [rsp+F8h] [rbp+10h]

  pIrp = 0;
  v45 = 0;
  memset(&Event, 0, sizeof(Event));
  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a1 + 56);
  *(_QWORD *)&ValueName.Length = v3;
  v35 = *(_DWORD *)(a1 + 540);
  v46 = a1 + 72;
  v4 = *(_QWORD *)(a1 + 72);
  if ( v4 )
    v5 = *(_QWORD *)(v4 + 48);
  else
    v5 = 0;
  v41 = v5;
  v6 = *(_QWORD *)(v4 + 32);
  if ( v6 )
    v7 = *(_QWORD *)(v6 + 136);
  else
    v7 = 0;
  v43 = v7;
  DeviceObject = *(PDEVICE_OBJECT *)(v5 + 32);
  RxAcquireExclusiveFcbResourceInMRx(0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      11,
      WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids,
      *(_QWORD *)(a1 + 40),
      v3,
      v2);
  v8 = v35;
  if ( v35 != 590228 && (*(_DWORD *)(v3 + 232) & 0x4004) == 4 )
  {
    Status = -1073741790;
    goto LABEL_43;
  }
  if ( DisableEFS && !*(_DWORD *)(v7 + 2228) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids);
    Status = -1073741822;
    goto LABEL_43;
  }
  v48 = 0;
  if ( v35 == 590039 || (v10 = 0, v36 = 0, v35 == 590043) )
  {
    v11 = *(_QWORD *)(a1 + 48);
    v12 = *(_DWORD **)(v11 + 32);
    v37 = v12;
    if ( !v12 )
    {
      Status = -1073741811;
      goto LABEL_43;
    }
    v13 = *(unsigned int *)(v11 + 16);
    if ( (unsigned int)v13 < 8 )
    {
      Status = -1073741789;
      goto LABEL_43;
    }
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 40) + 64LL) )
    {
      ProbeForRead(v12, v13, 1u);
      v12 = v37;
      v8 = v35;
    }
    v10 = *v12;
    v36 = *v12;
    v44 = *v12;
  }
  if ( *(_WORD *)v3 != 0xEC21 )
  {
    if ( *(_WORD *)v3 != 0xEC22 )
    {
LABEL_63:
      Status = -1073741637;
      goto LABEL_43;
    }
    if ( !*(_QWORD *)v5 || !*(_QWORD *)(v5 + 24) || !*(_QWORD *)(v5 + 32) )
    {
      Status = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        CurrentThreadId = PsGetCurrentThreadId();
        WPP_SF_q(v33, 16, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, CurrentThreadId);
      }
      goto LABEL_35;
    }
    KeInitializeEvent(&Event, NotificationEvent, 0);
    IrpWithMDL = RxCeAllocateIrpWithMDL(DeviceObject->StackSize, 0, 0);
    pIrp = IrpWithMDL;
    if ( !IrpWithMDL )
      goto LABEL_69;
    IrpWithMDL->Tail.Overlay.Thread = KeGetCurrentThread();
    IrpWithMDL->RequestorMode = *(_BYTE *)(*(_QWORD *)(a1 + 40) + 64LL);
    v24 = *(void **)(*(_QWORD *)(a1 + 40) + 112LL);
    IrpWithMDL->UserBuffer = v24;
    IrpWithMDL->AssociatedIrp.MasterIrp = *(struct _IRP **)(*(_QWORD *)(a1 + 40) + 24LL);
    v25 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL);
    if ( v25 )
    {
      v26 = *(_DWORD *)(v25 + 40);
      if ( v26 )
      {
        Mdl = IoAllocateMdl(v24, v26, 0, 0, 0);
        IrpWithMDL->MdlAddress = Mdl;
        if ( !Mdl )
        {
LABEL_69:
          Status = -1073741670;
          goto LABEL_43;
        }
      }
    }
    TopLevelIrp = 0;
    CurrentStackLocation = IrpWithMDL->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = *(_BYTE *)(a1 + 32);
    CurrentStackLocation[-1].MinorFunction = *(_BYTE *)(a1 + 33);
    CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(v41 + 24);
    CurrentStackLocation[-1].Flags = *(_BYTE *)(*(_QWORD *)(a1 + 48) + 2LL);
    CurrentStackLocation[-1].Parameters.Read.Length = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
    CurrentStackLocation[-1].Parameters.Create.Options = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16LL);
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 24LL);
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = *(PNAMED_PIPE_CREATE_PARAMETERS *)(*(_QWORD *)(a1 + 48)
                                                                                                 + 32LL);
    v29 = IrpWithMDL->Tail.Overlay.CurrentStackLocation;
    v29[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&MrxDAVEfsControlCompletion;
    v29[-1].Context = &Event;
    v29[-1].Control = -32;
    TopLevelIrp = IoGetTopLevelIrp();
    IoSetTopLevelIrp(0);
    Status = IofCallDriver(DeviceObject, IrpWithMDL);
    IoSetTopLevelIrp(TopLevelIrp);
    if ( Status != 259 && Status )
      goto LABEL_35;
    Status = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        WPP_SF_L(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          17,
          WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids,
          (unsigned int)Status);
      goto LABEL_35;
    }
    Status = pIrp->IoStatus.Status;
    *(_QWORD *)(a1 + 184) = pIrp->IoStatus.Information;
    v30 = v35;
    if ( !Status && v35 == 590039 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 18, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids);
      switch ( v36 )
      {
        case 1:
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) == 0 )
          {
            goto LABEL_91;
          }
          v32 = 19;
          goto LABEL_90;
        case 2:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids);
          }
          *(_DWORD *)(v3 + 232) &= ~0x4000u;
          goto LABEL_96;
        case 3:
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) == 0 )
          {
            goto LABEL_91;
          }
          v32 = 21;
LABEL_90:
          WPP_SF_(v31[3], v32, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids);
LABEL_91:
          *(_DWORD *)(v3 + 232) |= 0x4000u;
LABEL_96:
          *(_BYTE *)(v7 + 63) = 1;
          v17 = 1;
          v48 = 1;
          v30 = v35;
          goto LABEL_102;
      }
      v30 = v35;
    }
    v17 = 0;
LABEL_102:
    if ( Status || v30 != 590043 )
      goto LABEL_36;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 22, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids);
    if ( v36 != 3 )
    {
LABEL_35:
      v17 = v48;
LABEL_36:
      v18 = v17;
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 23, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids);
    *(_DWORD *)(v3 + 232) |= 0x4000u;
    *(_BYTE *)(v7 + 63) = 1;
    v18 = 1;
    goto LABEL_116;
  }
  ValueName = 0;
  if ( v8 != 590039 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v3, v8);
    goto LABEL_63;
  }
  Status = 0;
  v14 = v10 - 1;
  if ( !v14 )
    goto LABEL_53;
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
      {
        Status = -1073741637;
        goto LABEL_35;
      }
      goto LABEL_48;
    }
LABEL_53:
    *(_DWORD *)(v3 + 232) |= 0x4000u;
    *(_BYTE *)(v7 + 63) = 1;
    MRxDAVGetFullDirectoryPath(a1, 0, &ValueName);
    if ( ValueName.Buffer )
      Status = MRxDAVCreateEncryptedDirectoryKey(&ValueName);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) == 0 )
      goto LABEL_59;
    v22 = 13;
    goto LABEL_58;
  }
LABEL_48:
  *(_DWORD *)(v3 + 232) &= ~0x4000u;
  *(_BYTE *)(v7 + 63) = 1;
  MRxDAVGetFullDirectoryPath(a1, 0, &ValueName);
  if ( ValueName.Buffer )
    Status = MRxDAVRemoveEncryptedDirectoryKey(&ValueName);
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_59;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v22 = 14;
LABEL_58:
    WPP_SF_q(v21[3], v22, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v3);
LABEL_59:
    v17 = 1;
    v18 = 0;
    goto LABEL_37;
  }
  v18 = 0;
LABEL_116:
  v17 = 1;
LABEL_37:
  if ( !Status )
  {
    if ( v17 )
      MRxDAVUpdateBasicFileInfoCache(a1, *(unsigned int *)(v3 + 232), 0);
    if ( v18 && !*(_DWORD *)(v7 + 16) )
    {
      _InterlockedExchange((volatile __int32 *)(v7 + 16), 1);
      *(_DWORD *)(v7 + 28) = 0;
    }
  }
LABEL_43:
  RxReleaseFcbResourceInMRx(0);
  if ( pIrp )
  {
    MdlAddress = pIrp->MdlAddress;
    if ( MdlAddress )
      IoFreeMdl(MdlAddress);
    RxCeFreeIrp(pIrp);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140011eec  mov     r11, rsp
0x140011eef  mov     [r11+8], rcx
0x140011ef3  push    rbx
0x140011ef4  push    rdi
0x140011ef5  push    r12
0x140011ef7  push    r13
0x140011ef9  push    r14
0x140011efb  push    r15
0x140011efd  sub     rsp, 0B8h
0x140011f04  mov     r12, rcx
0x140011f07  xor     eax, eax
0x140011f09  mov     [rsp+0E8h+pIrp], rax
0x140011f0e  mov     [rsp+0E8h+var_68], rax
0x140011f16  xorps   xmm0, xmm0
0x140011f19  movups  xmmword ptr [r11-58h], xmm0
0x140011f1e  mov     [r11-48h], rax
0x140011f22  mov     r15, [rcx+40h]
0x140011f26  mov     r14, [rcx+38h]
0x140011f2a  mov     qword ptr [rsp+0E8h+ValueName.Length], r14
0x140011f2f  mov     eax, [rcx+21Ch]
0x140011f35  mov     [rsp+0E8h+var_B8], eax
0x140011f39  lea     rax, [rcx+48h]
0x140011f3d  mov     [rsp+0E8h+var_60], rax
0x140011f45  mov     rax, [rax]
0x140011f48  test    rax, rax
0x140011f4b  jnz     short loc_140011F51
0x140011f4d  xor     edi, edi
0x140011f4f  jmp     short loc_140011F55
0x140011f51  mov     rdi, [rax+30h]
0x140011f55  mov     [rsp+0E8h+var_88], rdi
0x140011f5a  mov     rdx, [rax+20h]
0x140011f5e  test    rdx, rdx
0x140011f61  jnz     short loc_140011F68
0x140011f63  xor     r13d, r13d
0x140011f66  jmp     short loc_140011F6F
0x140011f68  mov     r13, [rdx+88h]
0x140011f6f  mov     [rsp+0E8h+var_78], r13
0x140011f74  mov     rax, [rdi+20h]
0x140011f78  mov     [rsp+0E8h+DeviceObject], rax
0x140011f7d  xor     ecx, ecx; Fcb
0x140011f7f  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x140011f86  nop     dword ptr [rax+rax+00h]
0x140011f8b  lea     rdx, WPP_GLOBAL_Control
0x140011f92  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f99  mov     ebx, 4000h
0x140011f9e  cmp     rcx, rdx
0x140011fa1  jz      short loc_140011FD3
0x140011fa3  test    [rcx+2Ch], ebx
0x140011fa6  jz      short loc_140011FD3
0x140011fa8  mov     edx, 0Bh
0x140011fad  mov     [rsp+0E8h+var_C0], r15
0x140011fb2  mov     [rsp+0E8h+Irp], r14
0x140011fb7  mov     r9, [r12+28h]
0x140011fbc  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011fc3  mov     rcx, [rcx+18h]
0x140011fc7  call    WPP_SF_qqq
0x140011fcc  lea     rdx, WPP_GLOBAL_Control
0x140011fd3  mov     r8d, [rsp+0E8h+var_B8]
0x140011fd8  cmp     r8d, 90194h
0x140011fdf  jz      short loc_140011FFC
0x140011fe1  mov     eax, [r14+0E8h]
0x140011fe8  and     eax, 4004h
0x140011fed  cmp     eax, 4
0x140011ff0  jnz     short loc_140011FFC
0x140011ff2  mov     edi, 0C0000022h
0x140011ff7  jmp     loc_14001215B
0x140011ffc  cmp     cs:DisableEFS, 0
0x140012003  jz      short loc_14001203F
0x140012005  cmp     dword ptr [r13+8B4h], 0
0x14001200d  jnz     short loc_14001203F
0x14001200f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012016  cmp     rcx, rdx
0x140012019  jz      short loc_140012035
0x14001201b  test    [rcx+2Ch], ebx
0x14001201e  jz      short loc_140012035
0x140012020  mov     edx, 0Ch
0x140012025  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001202c  mov     rcx, [rcx+18h]
0x140012030  call    WPP_SF_
0x140012035  mov     edi, 0C0000002h
0x14001203a  jmp     loc_14001215B
0x14001203f  xor     al, al
0x140012041  mov     [rsp+0E8h+arg_8], al
0x140012048  mov     [rsp+0E8h+arg_10], al
0x14001204f  cmp     r8d, 900D7h
0x140012056  jz      short loc_14001206D
0x140012058  xor     eax, eax
0x14001205a  mov     dword ptr [rsp+0E8h+var_B0], eax
0x14001205e  cmp     r8d, 900DBh
0x140012065  jz      short loc_14001206D
0x140012067  lea     r15d, [rax+1]
0x14001206b  jmp     short loc_1400120D0
0x14001206d  mov     rax, [r12+30h]
0x140012072  mov     rcx, [rax+20h]; Address
0x140012076  mov     [rsp+0E8h+var_B0], rcx
0x14001207b  test    rcx, rcx
0x14001207e  jnz     short loc_14001208A
0x140012080  mov     edi, 0C000000Dh
0x140012085  jmp     loc_14001215B
0x14001208a  mov     edx, [rax+10h]; Length
0x14001208d  cmp     edx, 8
0x140012090  jnb     short loc_14001209C
0x140012092  mov     edi, 0C0000023h
0x140012097  jmp     loc_14001215B
0x14001209c  mov     rax, [r12+28h]
0x1400120a1  mov     r15d, 1
0x1400120a7  cmp     byte ptr [rax+40h], 0
0x1400120ab  jz      short loc_1400120C6
0x1400120ad  mov     r8d, r15d; Alignment
0x1400120b0  call    cs:__imp_ProbeForRead
0x1400120b7  nop     dword ptr [rax+rax+00h]
0x1400120bc  mov     rcx, [rsp+0E8h+var_B0]
0x1400120c1  mov     r8d, [rsp+0E8h+var_B8]
0x1400120c6  mov     eax, [rcx]
0x1400120c8  mov     dword ptr [rsp+0E8h+var_B0], eax
0x1400120cc  mov     [rsp+0E8h+var_70], eax
0x1400120d0  movzx   ecx, word ptr [r14]
0x1400120d4  mov     edx, 0EC21h
0x1400120d9  cmp     cx, dx
0x1400120dc  jnz     loc_1400122BC
0x1400120e2  xorps   xmm0, xmm0
0x1400120e5  movups  xmmword ptr [rsp+0E8h+ValueName.Length], xmm0
0x1400120ea  cmp     r8d, 900D7h
0x1400120f1  jnz     loc_140012279
0x1400120f7  xor     edi, edi
0x1400120f9  sub     eax, 1
0x1400120fc  jz      loc_14001220D
0x140012102  sub     eax, 1
0x140012105  jz      loc_1400121BB
0x14001210b  sub     eax, 1
0x14001210e  jz      loc_14001220D
0x140012114  cmp     eax, 1
0x140012117  jz      loc_1400121BB
0x14001211d  mov     edi, 0C00000BBh
0x140012122  mov     al, [rsp+0E8h+arg_8]
0x140012129  mov     bl, al
0x14001212b  test    edi, edi
0x14001212d  jnz     short loc_14001215B
0x14001212f  test    al, al
0x140012131  jz      short loc_140012145
0x140012133  xor     r8d, r8d
0x140012136  mov     edx, [r14+0E8h]
0x14001213d  mov     rcx, r12
0x140012140  call    MRxDAVUpdateBasicFileInfoCache
0x140012145  test    edi, edi
0x140012147  jnz     short loc_14001215B
0x140012149  test    bl, bl
0x14001214b  jz      short loc_14001215B
0x14001214d  cmp     [r13+10h], edi
0x140012151  jnz     short loc_14001215B
0x140012153  xchg    r15d, [r13+10h]
0x140012157  mov     [r13+1Ch], edi
0x14001215b  mov     rdx, [rsp+0E8h+var_60]
0x140012163  mov     rdx, [rdx]
0x140012166  mov     rdx, [rdx+20h]
0x14001216a  xor     ecx, ecx; Fcb
0x14001216c  call    cs:__imp_RxReleaseFcbResourceInMRx
0x140012173  nop     dword ptr [rax+rax+00h]
0x140012178  mov     rbx, [rsp+0E8h+pIrp]
0x14001217d  test    rbx, rbx
0x140012180  jz      short loc_1400121A6
0x140012182  mov     rcx, [rbx+8]; Mdl
0x140012186  test    rcx, rcx
0x140012189  jz      short loc_140012197
0x14001218b  call    cs:__imp_IoFreeMdl
0x140012192  nop     dword ptr [rax+rax+00h]
0x140012197  mov     rcx, rbx; pIrp
0x14001219a  call    cs:__imp_RxCeFreeIrp
0x1400121a1  nop     dword ptr [rax+rax+00h]
0x1400121a6  mov     eax, edi
0x1400121a8  add     rsp, 0B8h
0x1400121af  pop     r15
0x1400121b1  pop     r14
0x1400121b3  pop     r13
0x1400121b5  pop     r12
0x1400121b7  pop     rdi
0x1400121b8  pop     rbx
0x1400121b9  retn
0x1400121bb  btr     dword ptr [r14+0E8h], 0Eh
0x1400121c4  mov     [r13+3Fh], r15b
0x1400121c8  lea     r8, [rsp+0E8h+ValueName]
0x1400121cd  xor     edx, edx
0x1400121cf  mov     rcx, r12
0x1400121d2  call    MRxDAVGetFullDirectoryPath
0x1400121d7  cmp     [rsp+0E8h+ValueName.Buffer], rdi
0x1400121dc  jz      short loc_1400121EA
0x1400121de  lea     rcx, [rsp+0E8h+ValueName]; ValueName
0x1400121e3  call    MRxDAVRemoveEncryptedDirectoryKey
0x1400121e8  mov     edi, eax
0x1400121ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121f1  lea     rax, WPP_GLOBAL_Control
0x1400121f8  cmp     rcx, rax
0x1400121fb  jz      short loc_14001226A
0x1400121fd  test    [rcx+2Ch], ebx
0x140012200  jz      loc_1400126FF
0x140012206  mov     edx, 0Eh
0x14001220b  jmp     short loc_140012257
0x14001220d  or      [r14+0E8h], ebx
0x140012214  mov     [r13+3Fh], r15b
0x140012218  lea     r8, [rsp+0E8h+ValueName]
0x14001221d  xor     edx, edx
0x14001221f  mov     rcx, r12
0x140012222  call    MRxDAVGetFullDirectoryPath
0x140012227  cmp     [rsp+0E8h+ValueName.Buffer], rdi
0x14001222c  jz      short loc_14001223A
0x14001222e  lea     rcx, [rsp+0E8h+ValueName]; ValueName
0x140012233  call    MRxDAVCreateEncryptedDirectoryKey
0x140012238  mov     edi, eax
0x14001223a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012241  lea     rax, WPP_GLOBAL_Control
0x140012248  cmp     rcx, rax
0x14001224b  jz      short loc_14001226A
0x14001224d  test    [rcx+2Ch], ebx
0x140012250  jz      short loc_14001226A
0x140012252  mov     edx, 0Dh
0x140012257  mov     r9, r14
0x14001225a  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140012261  mov     rcx, [rcx+18h]
0x140012265  call    WPP_SF_q
0x14001226a  mov     al, r15b
0x14001226d  mov     bl, [rsp+0E8h+arg_10]
0x140012274  jmp     loc_14001212B
0x140012279  mov     rcx, cs:WPP_GLOBAL_Control
0x140012280  lea     rax, WPP_GLOBAL_Control
0x140012287  cmp     rcx, rax
0x14001228a  jz      short loc_1400122B2
0x14001228c  test    dword ptr [rcx+2Ch], 2000h
0x140012293  jz      short loc_1400122B2
0x140012295  mov     edx, 0Fh
0x14001229a  mov     dword ptr [rsp+0E8h+Irp], r8d
0x14001229f  mov     r9, r14
0x1400122a2  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x1400122a9  mov     rcx, [rcx+18h]
0x1400122ad  call    WPP_SF_qD
0x1400122b2  mov     edi, 0C00000BBh
0x1400122b7  jmp     loc_14001215B
0x1400122bc  mov     eax, 0EC22h
0x1400122c1  cmp     cx, ax
0x1400122c4  jnz     short loc_1400122B2
0x1400122c6  cmp     qword ptr [rdi], 0
0x1400122ca  jz      loc_140012679
0x1400122d0  cmp     qword ptr [rdi+18h], 0
0x1400122d5  jz      loc_140012679
0x1400122db  cmp     qword ptr [rdi+20h], 0
0x1400122e0  jz      loc_140012679
0x1400122e6  xor     r8d, r8d; State
0x1400122e9  xor     edx, edx; Type
0x1400122eb  lea     rcx, [rsp+0E8h+Event]; Event
0x1400122f3  call    cs:__imp_KeInitializeEvent
0x1400122fa  nop     dword ptr [rax+rax+00h]
0x1400122ff  xor     r8d, r8d; Buffer
0x140012302  xor     edx, edx; ChargeQuota
0x140012304  mov     rcx, [rsp+0E8h+DeviceObject]
0x140012309  mov     cl, [rcx+4Ch]; StackSize
0x14001230c  call    cs:__imp_RxCeAllocateIrpWithMDL
0x140012313  nop     dword ptr [rax+rax+00h]
0x140012318  mov     rdi, rax
0x14001231b  mov     [rsp+0E8h+pIrp], rax
0x140012320  test    rax, rax
0x140012323  jnz     short loc_14001232F
0x140012325  mov     edi, 0C000009Ah
0x14001232a  jmp     loc_14001215B
0x14001232f  mov     rax, gs:188h
0x140012338  mov     [rdi+98h], rax
0x14001233f  mov     rax, [r12+28h]
0x140012344  mov     cl, [rax+40h]
0x140012347  mov     [rdi+40h], cl
0x14001234a  mov     rax, [r12+28h]
0x14001234f  mov     rcx, [rax+70h]; VirtualAddress
0x140012353  mov     [rdi+70h], rcx
0x140012357  mov     rax, [r12+28h]
0x14001235c  mov     rdx, [rax+18h]
0x140012360  mov     [rdi+18h], rdx
0x140012364  mov     rax, [r12+28h]
0x140012369  mov     rdx, [rax+8]
0x14001236d  test    rdx, rdx
0x140012370  jz      short loc_14001239D
0x140012372  mov     edx, [rdx+28h]; Length
0x140012375  test    edx, edx
0x140012377  jz      short loc_14001239D
0x140012379  mov     [rsp+0E8h+Irp], 0; Irp
0x140012382  xor     r9d, r9d; ChargeQuota
0x140012385  xor     r8d, r8d; SecondaryBuffer
0x140012388  call    cs:__imp_IoAllocateMdl
0x14001238f  nop     dword ptr [rax+rax+00h]
0x140012394  mov     [rdi+8], rax
0x140012398  test    rax, rax
0x14001239b  jz      short loc_140012325
0x14001239d  mov     [rsp+0E8h+var_90], 0
0x1400123a6  mov     rdx, [rdi+0B8h]
0x1400123ad  mov     al, [r12+20h]
0x1400123b2  mov     [rdx-48h], al
0x1400123b5  mov     al, [r12+21h]
0x1400123ba  mov     [rdx-47h], al
0x1400123bd  mov     rax, [rsp+0E8h+var_88]
0x1400123c2  mov     rax, [rax+18h]
0x1400123c6  mov     [rdx-18h], rax
0x1400123ca  mov     rax, [r12+30h]
0x1400123cf  mov     cl, [rax+2]
0x1400123d2  mov     [rdx-46h], cl
  ... truncated ...
```
