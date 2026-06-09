# PiSwIrpInterfacePropertySet

- ea: `0x1409153a0`
- end: `0x1409155bc`
- name: `PiSwIrpInterfacePropertySet`
- size: `540`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1409112d0`

## callees

- `0x140216db0`
- `0x1402c0a40`
- `0x14036f270`
- `0x140471688`
- `0x140524cb4`
- `0x140907f10`
- `0x140909564`
- `0x1409153a0`
- `0x140916968`
- `0x140916ed4`
- `0x140917440`
- `0x140917488`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x1409153f7`
- `msrpc!MesDecodeBufferHandleCreate` at `0x1409153f7`
- `msrpc!RpcExceptionFilter` at `0x140b447b2`
- `msrpc!RpcExceptionFilter` at `0x140b447b2`
- `msrpc!MesHandleFree` at `0x140915537`
- `msrpc!MesHandleFree` at `0x140915537`
- `msrpc!NdrMesTypeDecode3` at `0x140915439`
- `msrpc!NdrMesTypeDecode3` at `0x140915439`

## pseudocode

```c
__int64 __fastcall PiSwIrpInterfacePropertySet(PIRP Irp, __int64 a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext2; // rdi
  struct _IRP *MasterIrp; // rcx
  int v7; // ebx
  unsigned int v8; // edx
  __int64 v9; // rcx
  __int64 InterfaceEntry; // rax
  int v11; // ecx
  int v12; // r8d
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp+20h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v16 = FsContext2;
  v15 = 0;
  P = 0;
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (_DWORD)Irp,
      (unsigned int)KMPnPEvt_SwDevice_SetInterfaceProperty_Start,
      a3,
      FsContext2[1],
      FsContext2[2]);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
    goto LABEL_23;
  v7 = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, &v15);
  if ( v7 < 0 )
    goto LABEL_15;
  NdrMesTypeDecode3(v15, "TP 3\a", &off_140B7B268, &off_140E0A520, 4, &P);
  if ( P && *(_QWORD *)P && *((_QWORD *)P + 2) && (v8 = *((_DWORD *)P + 2)) != 0 )
  {
    v7 = PiSwValidatePropertyArray(*((_QWORD *)P + 2), v8);
    if ( v7 >= 0 )
    {
      PiSwLock();
      if ( (unsigned __int8)PiSwDeviceOperationsAllowed(FsContext2) )
      {
        InterfaceEntry = PiSwDeviceFindInterfaceEntry(v9, *(_QWORD *)P);
        v7 = InterfaceEntry
           ? PiSwUpdateArrayProperties(
               *(_QWORD *)(InterfaceEntry + 24),
               *(_DWORD *)(InterfaceEntry + 32),
               *((_QWORD *)P + 2),
               *((_DWORD *)P + 2))
           : -1073741275;
      }
      else
      {
        v7 = -1073741637;
      }
      ExReleaseResourceLite(&PiSwLockObj);
      KeLeaveCriticalRegion();
      if ( v7 >= 0 )
        v7 = PiSwPropertySet(*(_QWORD *)P, 3, *((_QWORD *)P + 2), *((unsigned int *)P + 2));
    }
  }
  else
  {
LABEL_23:
    v7 = -1073741811;
  }
LABEL_15:
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  if ( v15 )
    MesHandleFree();
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0zzd_EtwWriteTransfer(
      v11,
      (unsigned int)KMPnPEvt_SwDevice_SetInterfaceProperty_Stop,
      v12,
      FsContext2[1],
      FsContext2[2],
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1409153a0  mov     [rsp+arg_0], rcx
0x1409153a5  push    rbx
0x1409153a6  push    rsi
0x1409153a7  push    rdi
0x1409153a8  sub     rsp, 30h
0x1409153ac  mov     rsi, rcx
0x1409153af  mov     rbx, [rcx+0B8h]
0x1409153b6  mov     rax, [rbx+30h]
0x1409153ba  mov     rdi, [rax+20h]
0x1409153be  mov     [rsp+48h+arg_18], rdi
0x1409153c3  mov     [rsp+48h+arg_10], 0
0x1409153cc  mov     [rsp+48h+P], 0
0x1409153d5  test    cs:byte_140ED9FEC, 40h
0x1409153dc  jnz     loc_140915575
0x1409153e2  mov     rcx, [rsi+18h]
0x1409153e6  test    rcx, rcx
0x1409153e9  jz      loc_14091556E
0x1409153ef  lea     r8, [rsp+48h+arg_10]
0x1409153f4  mov     edx, [rbx+10h]
0x1409153f7  call    cs:__imp_MesDecodeBufferHandleCreate
0x1409153fe  nop     dword ptr [rax+rax+00h]
0x140915403  mov     ebx, eax
0x140915405  test    eax, eax
0x140915407  js      loc_140915519
0x14091540d  lea     rax, [rsp+48h+P]
0x140915412  mov     [rsp+48h+var_20], rax
0x140915417  mov     dword ptr [rsp+48h+var_28], 4
0x14091541f  lea     r9, off_140E0A520
0x140915426  lea     r8, off_140B7B268
0x14091542d  lea     rdx, aTp3_0; "TP 3\a"
0x140915434  mov     rcx, [rsp+48h+arg_10]
0x140915439  call    cs:__imp_NdrMesTypeDecode3
0x140915440  nop     dword ptr [rax+rax+00h]
0x140915445  jmp     short loc_14091545C
0x140915447  mov     ebx, eax
0x140915449  mov     [rsp+48h+P], 0
0x140915452  mov     rsi, [rsp+48h+arg_0]
0x140915457  mov     rdi, [rsp+48h+arg_18]
0x14091545c  test    ebx, ebx
0x14091545e  js      loc_140915519
0x140915464  mov     rcx, [rsp+48h+P]
0x140915469  test    rcx, rcx
0x14091546c  jz      loc_14091556E
0x140915472  cmp     qword ptr [rcx], 0
0x140915476  jz      loc_14091556E
0x14091547c  mov     rax, [rcx+10h]
0x140915480  test    rax, rax
0x140915483  jz      loc_14091556E
0x140915489  mov     edx, [rcx+8]
0x14091548c  test    edx, edx
0x14091548e  jz      loc_14091556E
0x140915494  mov     rcx, rax
0x140915497  call    PiSwValidatePropertyArray
0x14091549c  mov     ebx, eax
0x14091549e  test    eax, eax
0x1409154a0  js      short loc_140915519
0x1409154a2  call    PiSwLock
0x1409154a7  mov     rcx, rdi
0x1409154aa  call    PiSwDeviceOperationsAllowed
0x1409154af  test    al, al
0x1409154b1  jz      loc_140915564
0x1409154b7  mov     rdx, [rsp+48h+P]
0x1409154bc  mov     rdx, [rdx]
0x1409154bf  call    PiSwDeviceFindInterfaceEntry
0x1409154c4  test    rax, rax
0x1409154c7  jz      loc_1409155B2
0x1409154cd  mov     r8, [rsp+48h+P]
0x1409154d2  mov     r9d, [r8+8]
0x1409154d6  mov     r8, [r8+10h]
0x1409154da  mov     edx, [rax+20h]
0x1409154dd  mov     rcx, [rax+18h]
0x1409154e1  call    PiSwUpdateArrayProperties
0x1409154e6  mov     ebx, eax
0x1409154e8  lea     rcx, PiSwLockObj; Resource
0x1409154ef  call    ExReleaseResourceLite
0x1409154f4  call    KeLeaveCriticalRegion
0x1409154f9  test    ebx, ebx
0x1409154fb  js      short loc_140915519
0x1409154fd  mov     rcx, [rsp+48h+P]
0x140915502  mov     r9d, [rcx+8]
0x140915506  mov     r8, [rcx+10h]
0x14091550a  mov     edx, 3
0x14091550f  mov     rcx, [rcx]
0x140915512  call    PiSwPropertySet
0x140915517  mov     ebx, eax
0x140915519  mov     rcx, [rsp+48h+P]; P
0x14091551e  test    rcx, rcx
0x140915521  jz      short loc_14091552D
0x140915523  mov     edx, 6370726Bh; Tag
0x140915528  call    ExFreePoolWithTag
0x14091552d  mov     rcx, [rsp+48h+arg_10]
0x140915532  test    rcx, rcx
0x140915535  jz      short loc_140915543
0x140915537  call    cs:__imp_MesHandleFree
0x14091553e  nop     dword ptr [rax+rax+00h]
0x140915543  mov     [rsi+30h], ebx
0x140915546  xor     edx, edx; PriorityBoost
0x140915548  mov     rcx, rsi; Irp
0x14091554b  call    IofCompleteRequest
0x140915550  test    cs:byte_140ED9FEC, 40h
0x140915557  jnz     short loc_140915593
0x140915559  mov     eax, ebx
0x14091555b  add     rsp, 30h
0x14091555f  pop     rdi
0x140915560  pop     rsi
0x140915561  pop     rbx
0x140915562  retn
0x140915564  mov     ebx, 0C00000BBh
0x140915569  jmp     loc_1409154E8
0x14091556e  mov     ebx, 0C000000Dh
0x140915573  jmp     short loc_140915519
0x140915575  mov     rax, [rdi+10h]
0x140915579  mov     [rsp+48h+var_28], rax
0x14091557e  mov     r9, [rdi+8]
0x140915582  lea     rdx, KMPnPEvt_SwDevice_SetInterfaceProperty_Start
0x140915589  call    McTemplateK0zz_EtwWriteTransfer
0x14091558e  jmp     loc_1409153E2
0x140915593  mov     dword ptr [rsp+48h+var_20], ebx
0x140915597  mov     rax, [rdi+10h]
0x14091559b  mov     [rsp+48h+var_28], rax
0x1409155a0  mov     r9, [rdi+8]
0x1409155a4  lea     rdx, KMPnPEvt_SwDevice_SetInterfaceProperty_Stop
0x1409155ab  call    McTemplateK0zzd_EtwWriteTransfer
0x1409155b0  jmp     short loc_140915559
0x1409155b2  mov     ebx, 0C0000225h
0x1409155b7  jmp     loc_1409154E8
0x140b447a4  push    rbp
0x140b447a6  sub     rsp, 30h
0x140b447aa  mov     rbp, rdx
0x140b447ad  mov     rcx, [rcx]
0x140b447b0  mov     ecx, [rcx]; ExceptionCode
0x140b447b2  call    cs:__imp_RpcExceptionFilter
0x140b447b9  nop     dword ptr [rax+rax+00h]
0x140b447be  nop
0x140b447bf  add     rsp, 30h
0x140b447c3  pop     rbp
0x140b447c4  retn
```
