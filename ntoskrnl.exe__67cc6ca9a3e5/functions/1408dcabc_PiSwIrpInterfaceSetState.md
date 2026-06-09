# PiSwIrpInterfaceSetState

- ea: `0x1408dcabc`
- end: `0x1408dcc87`
- name: `PiSwIrpInterfaceSetState`
- size: `459`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1408dc4f0`

## callees

- `0x140227210`
- `0x1402b1240`
- `0x1402f8270`
- `0x140461498`
- `0x14051e400`
- `0x1408dcabc`
- `0x1408dcc90`
- `0x1408e1ba8`
- `0x1408e2114`
- `0x1408e2680`
- `0x140bae8e0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x1408dcb13`
- `msrpc!MesDecodeBufferHandleCreate` at `0x1408dcb13`
- `msrpc!RpcExceptionFilter` at `0x140b4297a`
- `msrpc!RpcExceptionFilter` at `0x140b4297a`
- `msrpc!MesHandleFree` at `0x1408dcc5a`
- `msrpc!MesHandleFree` at `0x1408dcc5a`
- `msrpc!NdrMesTypeDecode3` at `0x1408dcb55`
- `msrpc!NdrMesTypeDecode3` at `0x1408dcb55`

## pseudocode

```c
__int64 __fastcall PiSwIrpInterfaceSetState(PIRP Irp, __int64 a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext2; // rdi
  struct _IRP *MasterIrp; // rcx
  NTSTATUS v7; // ebx
  __int64 v8; // rcx
  __int64 InterfaceEntry; // rax
  PVOID v10; // r8
  int v11; // ecx
  int v12; // r8d
  __int64 v14; // [rsp+28h] [rbp-20h]
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v16; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v17; // [rsp+68h] [rbp+20h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v17 = FsContext2;
  v16 = 0;
  P = 0;
  if ( (byte_140EDA02C & 0x40) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (_DWORD)Irp,
      (unsigned int)KMPnPEvt_SwDevice_SetInterfaceState_Start,
      a3,
      FsContext2[1],
      FsContext2[2]);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
    goto LABEL_20;
  v7 = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, &v16);
  if ( v7 < 0 )
    goto LABEL_11;
  NdrMesTypeDecode3(v16, "TP 3\a", &off_140B78E48, &off_140E0A520, 3, &P);
  if ( P && *(_QWORD *)P )
  {
    PiSwLock();
    if ( (unsigned __int8)PiSwDeviceOperationsAllowed(FsContext2) )
    {
      InterfaceEntry = PiSwDeviceFindInterfaceEntry(v8, *(_QWORD *)P);
      if ( InterfaceEntry )
      {
        v10 = P;
        LOBYTE(v10) = *((_BYTE *)P + 8);
        v7 = PiSwDeviceInterfaceSetState(FsContext2, InterfaceEntry, v10);
      }
      else
      {
        v7 = -1073741275;
      }
    }
    else
    {
      v7 = -1073741637;
    }
    ExReleaseResourceLite(&PiSwLockObj);
    KeLeaveCriticalRegion();
  }
  else
  {
LABEL_20:
    v7 = -1073741811;
  }
LABEL_11:
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  if ( v16 )
    MesHandleFree();
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140EDA02C & 0x40) != 0 )
  {
    LODWORD(v14) = v7;
    McTemplateK0zzd_EtwWriteTransfer(
      v11,
      (unsigned int)KMPnPEvt_SwDevice_SetInterfaceState_Stop,
      v12,
      FsContext2[1],
      FsContext2[2],
      v14);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1408dcabc  mov     [rsp+arg_0], rcx
0x1408dcac1  push    rbx
0x1408dcac2  push    rsi
0x1408dcac3  push    rdi
0x1408dcac4  sub     rsp, 30h
0x1408dcac8  mov     rsi, rcx
0x1408dcacb  mov     rbx, [rcx+0B8h]
0x1408dcad2  mov     rax, [rbx+30h]
0x1408dcad6  mov     rdi, [rax+20h]
0x1408dcada  mov     [rsp+48h+arg_18], rdi
0x1408dcadf  mov     [rsp+48h+arg_10], 0
0x1408dcae8  mov     [rsp+48h+P], 0
0x1408dcaf1  test    cs:byte_140EDA02C, 40h
0x1408dcaf8  jnz     loc_1408DCC1B
0x1408dcafe  mov     rcx, [rsi+18h]
0x1408dcb02  test    rcx, rcx
0x1408dcb05  jz      loc_1408DCC47
0x1408dcb0b  lea     r8, [rsp+48h+arg_10]
0x1408dcb10  mov     edx, [rbx+10h]
0x1408dcb13  call    cs:__imp_MesDecodeBufferHandleCreate
0x1408dcb1a  nop     dword ptr [rax+rax+00h]
0x1408dcb1f  mov     ebx, eax
0x1408dcb21  test    eax, eax
0x1408dcb23  js      loc_1408DCBE6
0x1408dcb29  lea     rax, [rsp+48h+P]
0x1408dcb2e  mov     [rsp+48h+var_20], rax
0x1408dcb33  mov     dword ptr [rsp+48h+var_28], 3
0x1408dcb3b  lea     r9, off_140E0A520
0x1408dcb42  lea     r8, off_140B78E48
0x1408dcb49  lea     rdx, aTp3_0; "TP 3\a"
0x1408dcb50  mov     rcx, [rsp+48h+arg_10]
0x1408dcb55  call    cs:__imp_NdrMesTypeDecode3
0x1408dcb5c  nop     dword ptr [rax+rax+00h]
0x1408dcb61  jmp     short loc_1408DCB78
0x1408dcb63  mov     ebx, eax
0x1408dcb65  mov     [rsp+48h+P], 0
0x1408dcb6e  mov     rsi, [rsp+48h+arg_0]
0x1408dcb73  mov     rdi, [rsp+48h+arg_18]
0x1408dcb78  test    ebx, ebx
0x1408dcb7a  js      short loc_1408DCBE6
0x1408dcb7c  mov     rcx, [rsp+48h+P]
0x1408dcb81  test    rcx, rcx
0x1408dcb84  jz      loc_1408DCC47
0x1408dcb8a  cmp     qword ptr [rcx], 0
0x1408dcb8e  jz      loc_1408DCC47
0x1408dcb94  call    PiSwLock
0x1408dcb99  mov     rcx, rdi
0x1408dcb9c  call    PiSwDeviceOperationsAllowed
0x1408dcba1  test    al, al
0x1408dcba3  jz      loc_1408DCC39
0x1408dcba9  mov     rdx, [rsp+48h+P]
0x1408dcbae  mov     rdx, [rdx]
0x1408dcbb1  call    PiSwDeviceFindInterfaceEntry
0x1408dcbb6  test    rax, rax
0x1408dcbb9  jz      loc_1408DCC40
0x1408dcbbf  mov     r8, [rsp+48h+P]
0x1408dcbc4  mov     r8b, [r8+8]
0x1408dcbc8  mov     rdx, rax
0x1408dcbcb  mov     rcx, rdi
0x1408dcbce  call    PiSwDeviceInterfaceSetState
0x1408dcbd3  mov     ebx, eax
0x1408dcbd5  lea     rcx, PiSwLockObj; Resource
0x1408dcbdc  call    ExReleaseResourceLite
0x1408dcbe1  call    KeLeaveCriticalRegion
0x1408dcbe6  mov     rcx, [rsp+48h+P]; P
0x1408dcbeb  test    rcx, rcx
0x1408dcbee  jnz     short loc_1408DCC4E
0x1408dcbf0  mov     rcx, [rsp+48h+arg_10]
0x1408dcbf5  test    rcx, rcx
0x1408dcbf8  jnz     short loc_1408DCC5A
0x1408dcbfa  mov     [rsi+30h], ebx
0x1408dcbfd  xor     edx, edx; PriorityBoost
0x1408dcbff  mov     rcx, rsi; Irp
0x1408dcc02  call    IofCompleteRequest
0x1408dcc07  test    cs:byte_140EDA02C, 40h
0x1408dcc0e  jnz     short loc_1408DCC68
0x1408dcc10  mov     eax, ebx
0x1408dcc12  add     rsp, 30h
0x1408dcc16  pop     rdi
0x1408dcc17  pop     rsi
0x1408dcc18  pop     rbx
0x1408dcc19  retn
0x1408dcc1b  mov     rax, [rdi+10h]
0x1408dcc1f  mov     [rsp+48h+var_28], rax
0x1408dcc24  mov     r9, [rdi+8]
0x1408dcc28  lea     rdx, KMPnPEvt_SwDevice_SetInterfaceState_Start
0x1408dcc2f  call    McTemplateK0zz_EtwWriteTransfer
0x1408dcc34  jmp     loc_1408DCAFE
0x1408dcc39  mov     ebx, 0C00000BBh
0x1408dcc3e  jmp     short loc_1408DCBD5
0x1408dcc40  mov     ebx, 0C0000225h
0x1408dcc45  jmp     short loc_1408DCBD5
0x1408dcc47  mov     ebx, 0C000000Dh
0x1408dcc4c  jmp     short loc_1408DCBE6
0x1408dcc4e  mov     edx, 6370726Bh; Tag
0x1408dcc53  call    ExFreePoolWithTag
0x1408dcc58  jmp     short loc_1408DCBF0
0x1408dcc5a  call    cs:__imp_MesHandleFree
0x1408dcc61  nop     dword ptr [rax+rax+00h]
0x1408dcc66  jmp     short loc_1408DCBFA
0x1408dcc68  mov     dword ptr [rsp+48h+var_20], ebx
0x1408dcc6c  mov     rax, [rdi+10h]
0x1408dcc70  mov     [rsp+48h+var_28], rax
0x1408dcc75  mov     r9, [rdi+8]
0x1408dcc79  lea     rdx, KMPnPEvt_SwDevice_SetInterfaceState_Stop
0x1408dcc80  call    McTemplateK0zzd_EtwWriteTransfer
0x1408dcc85  jmp     short loc_1408DCC10
0x140b4296c  push    rbp
0x140b4296e  sub     rsp, 30h
0x140b42972  mov     rbp, rdx
0x140b42975  mov     rcx, [rcx]
0x140b42978  mov     ecx, [rcx]; ExceptionCode
0x140b4297a  call    cs:__imp_RpcExceptionFilter
0x140b42981  nop     dword ptr [rax+rax+00h]
0x140b42986  nop
0x140b42987  add     rsp, 30h
0x140b4298b  pop     rbp
0x140b4298c  retn
```
