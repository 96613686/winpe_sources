# PiSwIrpPropertySet

- ea: `0x140aa0dec`
- end: `0x140aa1022`
- name: `PiSwIrpPropertySet`
- size: `566`
- prototype: `__int64 __fastcall(PIRP Irp)`
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
- `0x140903360`
- `0x140907f10`
- `0x140909564`
- `0x140916968`
- `0x140916ed4`
- `0x140917488`
- `0x140aa0dec`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x140aa0e4b`
- `msrpc!MesDecodeBufferHandleCreate` at `0x140aa0e4b`
- `msrpc!RpcExceptionFilter` at `0x140b4a888`
- `msrpc!RpcExceptionFilter` at `0x140b4a888`
- `msrpc!MesHandleFree` at `0x140aa0fae`
- `msrpc!MesHandleFree` at `0x140aa0fae`
- `msrpc!NdrMesTypeDecode3` at `0x140aa0e8d`
- `msrpc!NdrMesTypeDecode3` at `0x140aa0e8d`

## pseudocode

```c
__int64 __fastcall PiSwIrpPropertySet(PIRP Irp, __int64 a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext2; // rdi
  struct _IRP *MasterIrp; // rcx
  NTSTATUS updated; // ebx
  int v8; // ecx
  int v9; // r8d
  __int64 v11; // [rsp+28h] [rbp-30h]
  PVOID v12; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v14 = 0;
  v12 = 0;
  P = 0;
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (_DWORD)Irp,
      (unsigned int)KMPnPEvt_SwDevice_SetDeviceProperty_Start,
      a3,
      FsContext2[1],
      FsContext2[2]);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
    goto LABEL_14;
  updated = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, &v14);
  if ( updated < 0 )
    goto LABEL_15;
  NdrMesTypeDecode3(v14, "TP 3\a", &off_140B7B268, &off_140E0A520, 1, &v12);
  if ( v12 && *((_QWORD *)v12 + 1) && *(_DWORD *)v12 )
  {
    updated = PiSwValidatePropertyArray(*((_QWORD *)v12 + 1));
    if ( updated >= 0 )
    {
      PiSwLock();
      if ( (unsigned __int8)PiSwDeviceOperationsAllowed(FsContext2) )
      {
        updated = PnpAllocatePWSTR(FsContext2[10], 200, 1466986064, &P);
        if ( updated >= 0 )
          updated = PiSwUpdateArrayProperties(
                      FsContext2[21],
                      *((unsigned int *)FsContext2 + 44),
                      *((_QWORD *)v12 + 1),
                      *(unsigned int *)v12);
      }
      else
      {
        updated = -1073741637;
      }
      ExReleaseResourceLite(&PiSwLockObj);
      KeLeaveCriticalRegion();
      if ( updated >= 0 )
        updated = PiSwPropertySet(P, 1, *((_QWORD *)v12 + 1), *(unsigned int *)v12);
    }
  }
  else
  {
LABEL_14:
    updated = -1073741811;
  }
LABEL_15:
  if ( P )
    ExFreePoolWithTag(P, 0x57706E50u);
  if ( v12 )
    ExFreePoolWithTag(v12, 0x6370726Bu);
  if ( v14 )
    MesHandleFree();
  Irp->IoStatus.Status = updated;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140ED9FEC & 0x40) != 0 )
  {
    LODWORD(v11) = updated;
    McTemplateK0zzd_EtwWriteTransfer(
      v8,
      (unsigned int)KMPnPEvt_SwDevice_SetDeviceProperty_Stop,
      v9,
      FsContext2[1],
      FsContext2[2],
      v11,
      FsContext2);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140aa0dec  mov     r11, rsp
0x140aa0def  mov     [r11+8], rcx
0x140aa0df3  push    rbx
0x140aa0df4  push    rsi
0x140aa0df5  push    rdi
0x140aa0df6  sub     rsp, 40h
0x140aa0dfa  mov     rsi, rcx
0x140aa0dfd  mov     rbx, [rcx+0B8h]
0x140aa0e04  mov     rax, [rbx+30h]
0x140aa0e08  mov     rdi, [rax+20h]
0x140aa0e0c  mov     [rsp+58h+var_28], rdi
0x140aa0e11  mov     qword ptr [r11+20h], 0
0x140aa0e19  mov     qword ptr [r11+10h], 0
0x140aa0e21  mov     qword ptr [r11+18h], 0
0x140aa0e29  test    cs:byte_140ED9FEC, 40h
0x140aa0e30  jnz     loc_140AA0FE5
0x140aa0e36  mov     rcx, [rsi+18h]
0x140aa0e3a  test    rcx, rcx
0x140aa0e3d  jz      loc_140AA0F77
0x140aa0e43  lea     r8, [rsp+58h+arg_18]
0x140aa0e48  mov     edx, [rbx+10h]
0x140aa0e4b  call    cs:__imp_MesDecodeBufferHandleCreate
0x140aa0e52  nop     dword ptr [rax+rax+00h]
0x140aa0e57  mov     ebx, eax
0x140aa0e59  test    eax, eax
0x140aa0e5b  js      loc_140AA0F7C
0x140aa0e61  lea     rax, [rsp+58h+arg_8]
0x140aa0e66  mov     [rsp+58h+var_30], rax
0x140aa0e6b  mov     dword ptr [rsp+58h+var_38], 1
0x140aa0e73  lea     r9, off_140E0A520
0x140aa0e7a  lea     r8, off_140B7B268
0x140aa0e81  lea     rdx, aTp3_0; "TP 3\a"
0x140aa0e88  mov     rcx, [rsp+58h+arg_18]
0x140aa0e8d  call    cs:__imp_NdrMesTypeDecode3
0x140aa0e94  nop     dword ptr [rax+rax+00h]
0x140aa0e99  jmp     short loc_140AA0EB0
0x140aa0e9b  mov     ebx, eax
0x140aa0e9d  mov     [rsp+58h+arg_8], 0
0x140aa0ea6  mov     rsi, [rsp+58h+arg_0]
0x140aa0eab  mov     rdi, [rsp+58h+var_28]
0x140aa0eb0  test    ebx, ebx
0x140aa0eb2  js      loc_140AA0F7C
0x140aa0eb8  mov     rcx, [rsp+58h+arg_8]
0x140aa0ebd  test    rcx, rcx
0x140aa0ec0  jz      loc_140AA0F77
0x140aa0ec6  mov     rax, [rcx+8]
0x140aa0eca  test    rax, rax
0x140aa0ecd  jz      loc_140AA0F77
0x140aa0ed3  mov     edx, [rcx]
0x140aa0ed5  test    edx, edx
0x140aa0ed7  jz      loc_140AA0F77
0x140aa0edd  mov     rcx, rax
0x140aa0ee0  call    PiSwValidatePropertyArray
0x140aa0ee5  mov     ebx, eax
0x140aa0ee7  test    eax, eax
0x140aa0ee9  js      loc_140AA0F7C
0x140aa0eef  call    PiSwLock
0x140aa0ef4  mov     rcx, rdi
0x140aa0ef7  call    PiSwDeviceOperationsAllowed
0x140aa0efc  test    al, al
0x140aa0efe  jz      loc_140AA0FDB
0x140aa0f04  lea     r9, [rsp+58h+P]
0x140aa0f09  mov     edx, 0C8h
0x140aa0f0e  mov     r8d, 57706E50h
0x140aa0f14  mov     rcx, [rdi+50h]
0x140aa0f18  call    PnpAllocatePWSTR
0x140aa0f1d  mov     ebx, eax
0x140aa0f1f  test    eax, eax
0x140aa0f21  js      short loc_140AA0F43
0x140aa0f23  mov     r8, [rsp+58h+arg_8]
0x140aa0f28  mov     r9d, [r8]
0x140aa0f2b  mov     r8, [r8+8]
0x140aa0f2f  mov     edx, [rdi+0B0h]
0x140aa0f35  mov     rcx, [rdi+0A8h]
0x140aa0f3c  call    PiSwUpdateArrayProperties
0x140aa0f41  mov     ebx, eax
0x140aa0f43  lea     rcx, PiSwLockObj; Resource
0x140aa0f4a  call    ExReleaseResourceLite
0x140aa0f4f  call    KeLeaveCriticalRegion
0x140aa0f54  test    ebx, ebx
0x140aa0f56  js      short loc_140AA0F7C
0x140aa0f58  mov     r8, [rsp+58h+arg_8]
0x140aa0f5d  mov     r9d, [r8]
0x140aa0f60  mov     r8, [r8+8]
0x140aa0f64  mov     edx, 1
0x140aa0f69  mov     rcx, [rsp+58h+P]
0x140aa0f6e  call    PiSwPropertySet
0x140aa0f73  mov     ebx, eax
0x140aa0f75  jmp     short loc_140AA0F7C
0x140aa0f77  mov     ebx, 0C000000Dh
0x140aa0f7c  mov     rcx, [rsp+58h+P]; P
0x140aa0f81  test    rcx, rcx
0x140aa0f84  jz      short loc_140AA0F90
0x140aa0f86  mov     edx, 57706E50h; Tag
0x140aa0f8b  call    ExFreePoolWithTag
0x140aa0f90  mov     rcx, [rsp+58h+arg_8]; P
0x140aa0f95  test    rcx, rcx
0x140aa0f98  jz      short loc_140AA0FA4
0x140aa0f9a  mov     edx, 6370726Bh; Tag
0x140aa0f9f  call    ExFreePoolWithTag
0x140aa0fa4  mov     rcx, [rsp+58h+arg_18]
0x140aa0fa9  test    rcx, rcx
0x140aa0fac  jz      short loc_140AA0FBA
0x140aa0fae  call    cs:__imp_MesHandleFree
0x140aa0fb5  nop     dword ptr [rax+rax+00h]
0x140aa0fba  mov     [rsi+30h], ebx
0x140aa0fbd  xor     edx, edx; PriorityBoost
0x140aa0fbf  mov     rcx, rsi; Irp
0x140aa0fc2  call    IofCompleteRequest
0x140aa0fc7  test    cs:byte_140ED9FEC, 40h
0x140aa0fce  jnz     short loc_140AA1003
0x140aa0fd0  mov     eax, ebx
0x140aa0fd2  add     rsp, 40h
0x140aa0fd6  pop     rdi
0x140aa0fd7  pop     rsi
0x140aa0fd8  pop     rbx
0x140aa0fd9  retn
0x140aa0fdb  mov     ebx, 0C00000BBh
0x140aa0fe0  jmp     loc_140AA0F43
0x140aa0fe5  mov     rax, [rdi+10h]
0x140aa0fe9  mov     [rsp+58h+var_38], rax
0x140aa0fee  mov     r9, [rdi+8]
0x140aa0ff2  lea     rdx, KMPnPEvt_SwDevice_SetDeviceProperty_Start
0x140aa0ff9  call    McTemplateK0zz_EtwWriteTransfer
0x140aa0ffe  jmp     loc_140AA0E36
0x140aa1003  mov     dword ptr [rsp+58h+var_30], ebx
0x140aa1007  mov     rax, [rdi+10h]
0x140aa100b  mov     [rsp+58h+var_38], rax
0x140aa1010  mov     r9, [rdi+8]
0x140aa1014  lea     rdx, KMPnPEvt_SwDevice_SetDeviceProperty_Stop
0x140aa101b  call    McTemplateK0zzd_EtwWriteTransfer
0x140aa1020  jmp     short loc_140AA0FD0
0x140b4a87a  push    rbp
0x140b4a87c  sub     rsp, 30h
0x140b4a880  mov     rbp, rdx
0x140b4a883  mov     rcx, [rcx]
0x140b4a886  mov     ecx, [rcx]; ExceptionCode
0x140b4a888  call    cs:__imp_RpcExceptionFilter
0x140b4a88f  nop     dword ptr [rax+rax+00h]
0x140b4a894  nop
0x140b4a895  add     rsp, 30h
0x140b4a899  pop     rbp
0x140b4a89a  retn
```
