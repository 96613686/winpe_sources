# PiSwIrpInterfaceSetState

- ea: `0x140911888`
- end: `0x140911a53`
- name: `PiSwIrpInterfaceSetState`
- size: `459`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1409112d0`

## callees

- `0x140216db0`
- `0x1402c0a40`
- `0x14036f270`
- `0x140471688`
- `0x140524cb4`
- `0x140911888`
- `0x140911a5c`
- `0x140916968`
- `0x140916ed4`
- `0x140917440`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x1409118df`
- `msrpc!MesDecodeBufferHandleCreate` at `0x1409118df`
- `msrpc!RpcExceptionFilter` at `0x140b4473a`
- `msrpc!RpcExceptionFilter` at `0x140b4473a`
- `msrpc!MesHandleFree` at `0x140911a26`
- `msrpc!MesHandleFree` at `0x140911a26`
- `msrpc!NdrMesTypeDecode3` at `0x140911921`
- `msrpc!NdrMesTypeDecode3` at `0x140911921`

## pseudocode

```c
__int64 __fastcall PiSwIrpInterfaceSetState(PIRP Irp, __int64 a2, __int64 a3, __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext2; // rdi
  struct _IRP *MasterIrp; // rcx
  NTSTATUS v8; // ebx
  __int64 v9; // rcx
  __int64 InterfaceEntry; // rax
  PVOID v11; // r8
  int v12; // ecx
  int v13; // r8d
  __int64 v15; // [rsp+20h] [rbp-28h]
  __int64 v16; // [rsp+28h] [rbp-20h]
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v18; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp+20h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v19 = FsContext2;
  v18 = 0;
  P = 0;
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (_DWORD)Irp,
      (unsigned int)KMPnPEvt_SwDevice_SetInterfaceState_Start,
      a3,
      FsContext2[1],
      FsContext2[2]);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
    goto LABEL_20;
  v8 = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, &v18);
  if ( v8 < 0 )
    goto LABEL_11;
  NdrMesTypeDecode3(v18, "TP 3\a", &off_140B7B268, &off_140E0A520, 3, &P);
  if ( P && *(_QWORD *)P )
  {
    PiSwLock();
    if ( (unsigned __int8)PiSwDeviceOperationsAllowed(FsContext2) )
    {
      InterfaceEntry = PiSwDeviceFindInterfaceEntry(v9, *(_QWORD *)P);
      if ( InterfaceEntry )
      {
        v11 = P;
        LOBYTE(v11) = *((_BYTE *)P + 8);
        v8 = PiSwDeviceInterfaceSetState(FsContext2, InterfaceEntry, v11);
      }
      else
      {
        v8 = -1073741275;
      }
    }
    else
    {
      v8 = -1073741637;
    }
    ExReleaseResourceLite(&PiSwLockObj);
    KeLeaveCriticalRegion();
  }
  else
  {
LABEL_20:
    v8 = -1073741811;
  }
LABEL_11:
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  if ( v18 )
    MesHandleFree(v18, a2, a3, a4, v15, v16);
  Irp->IoStatus.Status = v8;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140ED9FEC & 0x40) != 0 )
  {
    LODWORD(v16) = v8;
    McTemplateK0zzd_EtwWriteTransfer(
      v12,
      (unsigned int)KMPnPEvt_SwDevice_SetInterfaceState_Stop,
      v13,
      FsContext2[1],
      FsContext2[2],
      v16);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140911888  mov     [rsp+arg_0], rcx
0x14091188d  push    rbx
0x14091188e  push    rsi
0x14091188f  push    rdi
0x140911890  sub     rsp, 30h
0x140911894  mov     rsi, rcx
0x140911897  mov     rbx, [rcx+0B8h]
0x14091189e  mov     rax, [rbx+30h]
0x1409118a2  mov     rdi, [rax+20h]
0x1409118a6  mov     [rsp+48h+arg_18], rdi
0x1409118ab  mov     [rsp+48h+arg_10], 0
0x1409118b4  mov     [rsp+48h+P], 0
0x1409118bd  test    cs:byte_140ED9FEC, 40h
0x1409118c4  jnz     loc_1409119E7
0x1409118ca  mov     rcx, [rsi+18h]
0x1409118ce  test    rcx, rcx
0x1409118d1  jz      loc_140911A13
0x1409118d7  lea     r8, [rsp+48h+arg_10]
0x1409118dc  mov     edx, [rbx+10h]
0x1409118df  call    cs:__imp_MesDecodeBufferHandleCreate
0x1409118e6  nop     dword ptr [rax+rax+00h]
0x1409118eb  mov     ebx, eax
0x1409118ed  test    eax, eax
0x1409118ef  js      loc_1409119B2
0x1409118f5  lea     rax, [rsp+48h+P]
0x1409118fa  mov     [rsp+48h+var_20], rax
0x1409118ff  mov     dword ptr [rsp+48h+var_28], 3
0x140911907  lea     r9, off_140E0A520
0x14091190e  lea     r8, off_140B7B268
0x140911915  lea     rdx, aTp3_0; "TP 3\a"
0x14091191c  mov     rcx, [rsp+48h+arg_10]
0x140911921  call    cs:__imp_NdrMesTypeDecode3
0x140911928  nop     dword ptr [rax+rax+00h]
0x14091192d  jmp     short loc_140911944
0x14091192f  mov     ebx, eax
0x140911931  mov     [rsp+48h+P], 0
0x14091193a  mov     rsi, [rsp+48h+arg_0]
0x14091193f  mov     rdi, [rsp+48h+arg_18]
0x140911944  test    ebx, ebx
0x140911946  js      short loc_1409119B2
0x140911948  mov     rcx, [rsp+48h+P]
0x14091194d  test    rcx, rcx
0x140911950  jz      loc_140911A13
0x140911956  cmp     qword ptr [rcx], 0
0x14091195a  jz      loc_140911A13
0x140911960  call    PiSwLock
0x140911965  mov     rcx, rdi
0x140911968  call    PiSwDeviceOperationsAllowed
0x14091196d  test    al, al
0x14091196f  jz      loc_140911A05
0x140911975  mov     rdx, [rsp+48h+P]
0x14091197a  mov     rdx, [rdx]
0x14091197d  call    PiSwDeviceFindInterfaceEntry
0x140911982  test    rax, rax
0x140911985  jz      loc_140911A0C
0x14091198b  mov     r8, [rsp+48h+P]
0x140911990  mov     r8b, [r8+8]
0x140911994  mov     rdx, rax
0x140911997  mov     rcx, rdi
0x14091199a  call    PiSwDeviceInterfaceSetState
0x14091199f  mov     ebx, eax
0x1409119a1  lea     rcx, PiSwLockObj; Resource
0x1409119a8  call    ExReleaseResourceLite
0x1409119ad  call    KeLeaveCriticalRegion
0x1409119b2  mov     rcx, [rsp+48h+P]; P
0x1409119b7  test    rcx, rcx
0x1409119ba  jnz     short loc_140911A1A
0x1409119bc  mov     rcx, [rsp+48h+arg_10]
0x1409119c1  test    rcx, rcx
0x1409119c4  jnz     short loc_140911A26
0x1409119c6  mov     [rsi+30h], ebx
0x1409119c9  xor     edx, edx; PriorityBoost
0x1409119cb  mov     rcx, rsi; Irp
0x1409119ce  call    IofCompleteRequest
0x1409119d3  test    cs:byte_140ED9FEC, 40h
0x1409119da  jnz     short loc_140911A34
0x1409119dc  mov     eax, ebx
0x1409119de  add     rsp, 30h
0x1409119e2  pop     rdi
0x1409119e3  pop     rsi
0x1409119e4  pop     rbx
0x1409119e5  retn
0x1409119e7  mov     rax, [rdi+10h]
0x1409119eb  mov     [rsp+48h+var_28], rax
0x1409119f0  mov     r9, [rdi+8]
0x1409119f4  lea     rdx, KMPnPEvt_SwDevice_SetInterfaceState_Start
0x1409119fb  call    McTemplateK0zz_EtwWriteTransfer
0x140911a00  jmp     loc_1409118CA
0x140911a05  mov     ebx, 0C00000BBh
0x140911a0a  jmp     short loc_1409119A1
0x140911a0c  mov     ebx, 0C0000225h
0x140911a11  jmp     short loc_1409119A1
0x140911a13  mov     ebx, 0C000000Dh
0x140911a18  jmp     short loc_1409119B2
0x140911a1a  mov     edx, 6370726Bh; Tag
0x140911a1f  call    ExFreePoolWithTag
0x140911a24  jmp     short loc_1409119BC
0x140911a26  call    cs:__imp_MesHandleFree
0x140911a2d  nop     dword ptr [rax+rax+00h]
0x140911a32  jmp     short loc_1409119C6
0x140911a34  mov     dword ptr [rsp+48h+var_20], ebx
0x140911a38  mov     rax, [rdi+10h]
0x140911a3c  mov     [rsp+48h+var_28], rax
0x140911a41  mov     r9, [rdi+8]
0x140911a45  lea     rdx, KMPnPEvt_SwDevice_SetInterfaceState_Stop
0x140911a4c  call    McTemplateK0zzd_EtwWriteTransfer
0x140911a51  jmp     short loc_1409119DC
0x140b4472c  push    rbp
0x140b4472e  sub     rsp, 30h
0x140b44732  mov     rbp, rdx
0x140b44735  mov     rcx, [rcx]
0x140b44738  mov     ecx, [rcx]; ExceptionCode
0x140b4473a  call    cs:__imp_RpcExceptionFilter
0x140b44741  nop     dword ptr [rax+rax+00h]
0x140b44746  nop
0x140b44747  add     rsp, 30h
0x140b4474b  pop     rbp
0x140b4474c  retn
```
