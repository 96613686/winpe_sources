# PiSwIrpStartCreate

- ea: `0x1408dd8e4`
- end: `0x1408dda4a`
- name: `PiSwIrpStartCreate`
- size: `358`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1408dc4f0`

## callees

- `0x1402b1240`
- `0x140461580`
- `0x1405cdbd4`
- `0x1408dd8e4`
- `0x1408dda50`
- `0x140bae8e0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x1408dd943`
- `msrpc!MesDecodeBufferHandleCreate` at `0x1408dd943`
- `msrpc!RpcExceptionFilter` at `0x140b429a2`
- `msrpc!RpcExceptionFilter` at `0x140b429a2`
- `msrpc!MesHandleFree` at `0x1408dd9dc`
- `msrpc!MesHandleFree` at `0x1408dd9dc`
- `msrpc!NdrMesTypeDecode3` at `0x1408dd981`
- `msrpc!NdrMesTypeDecode3` at `0x1408dd981`

## pseudocode

```c
__int64 __fastcall PiSwIrpStartCreate(PIRP Irp, __int64 a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PIRP v5; // rdi
  struct _IRP *MasterIrp; // rcx
  int Worker; // ebx
  __int64 v8; // rcx
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  PIRP v12; // [rsp+68h] [rbp+20h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v11 = 0;
  P = 0;
  v5 = Irp;
  v12 = Irp;
  if ( (byte_140EDA02C & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(&MS_KernelPnP_Provider_Context, KMPnPEvt_SwDevice_IrpCreate_Start);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( MasterIrp )
  {
    if ( CurrentStackLocation->Parameters.Read.Length < 0xC8 )
    {
      Worker = -1073741789;
    }
    else
    {
      Worker = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, &v11);
      if ( Worker >= 0 )
      {
        NdrMesTypeDecode3(v11, "TP 3\a", &off_140B78E48, &off_140E0A520, 0, &P);
        Worker = PiSwIrpStartCreateWorker(P, Irp);
        v5 = 0;
      }
    }
  }
  else
  {
    Worker = -1073741811;
  }
  if ( v5 )
  {
    v5->IoStatus.Status = Worker;
    v5->IoStatus.Information = 0;
    IofCompleteRequest(v5, 0);
  }
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  v8 = v11;
  if ( v11 )
    MesHandleFree();
  if ( (byte_140EDA02C & 0x40) != 0 )
    McTemplateK0d_EtwWriteTransfer(v8, KMPnPEvt_SwDevice_IrpCreate_Stop, a3, (unsigned int)Worker);
  return (unsigned int)Worker;
}

```

## disassembly

```asm
0x1408dd8e4  mov     [rsp+arg_0], rcx
0x1408dd8e9  push    rbx
0x1408dd8ea  push    rsi
0x1408dd8eb  push    rdi
0x1408dd8ec  sub     rsp, 30h
0x1408dd8f0  mov     rsi, rcx
0x1408dd8f3  mov     rbx, [rcx+0B8h]
0x1408dd8fa  mov     [rsp+48h+arg_10], 0
0x1408dd903  mov     [rsp+48h+P], 0
0x1408dd90c  mov     rdi, rcx
0x1408dd90f  mov     [rsp+48h+arg_18], rcx
0x1408dd914  test    cs:byte_140EDA02C, 40h
0x1408dd91b  jnz     loc_1408DDA03
0x1408dd921  mov     rcx, [rsi+18h]
0x1408dd925  test    rcx, rcx
0x1408dd928  jz      loc_1408DD9FC
0x1408dd92e  cmp     dword ptr [rbx+8], 0C8h
0x1408dd935  jb      loc_1408DDA1B
0x1408dd93b  lea     r8, [rsp+48h+arg_10]
0x1408dd940  mov     edx, [rbx+10h]
0x1408dd943  call    cs:__imp_MesDecodeBufferHandleCreate
0x1408dd94a  nop     dword ptr [rax+rax+00h]
0x1408dd94f  mov     ebx, eax
0x1408dd951  test    eax, eax
0x1408dd953  js      short loc_1408DD9B9
0x1408dd955  lea     rax, [rsp+48h+P]
0x1408dd95a  mov     [rsp+48h+var_20], rax
0x1408dd95f  mov     [rsp+48h+var_28], 0
0x1408dd967  lea     r9, off_140E0A520
0x1408dd96e  lea     r8, off_140B78E48
0x1408dd975  lea     rdx, aTp3_0; "TP 3\a"
0x1408dd97c  mov     rcx, [rsp+48h+arg_10]
0x1408dd981  call    cs:__imp_NdrMesTypeDecode3
0x1408dd988  nop     dword ptr [rax+rax+00h]
0x1408dd98d  jmp     short loc_1408DD9A4
0x1408dd98f  mov     ebx, eax
0x1408dd991  mov     [rsp+48h+P], 0
0x1408dd99a  mov     rsi, [rsp+48h+arg_0]
0x1408dd99f  mov     rdi, [rsp+48h+arg_18]
0x1408dd9a4  test    ebx, ebx
0x1408dd9a6  js      short loc_1408DD9B9
0x1408dd9a8  mov     rdx, rsi
0x1408dd9ab  mov     rcx, [rsp+48h+P]
0x1408dd9b0  call    PiSwIrpStartCreateWorker
0x1408dd9b5  mov     ebx, eax
0x1408dd9b7  xor     edi, edi
0x1408dd9b9  test    rdi, rdi
0x1408dd9bc  jnz     short loc_1408DDA22
0x1408dd9be  mov     rcx, [rsp+48h+P]; P
0x1408dd9c3  test    rcx, rcx
0x1408dd9c6  jz      short loc_1408DD9D2
0x1408dd9c8  mov     edx, 6370726Bh; Tag
0x1408dd9cd  call    ExFreePoolWithTag
0x1408dd9d2  mov     rcx, [rsp+48h+arg_10]
0x1408dd9d7  test    rcx, rcx
0x1408dd9da  jz      short loc_1408DD9E8
0x1408dd9dc  call    cs:__imp_MesHandleFree
0x1408dd9e3  nop     dword ptr [rax+rax+00h]
0x1408dd9e8  test    cs:byte_140EDA02C, 40h
0x1408dd9ef  jnz     short loc_1408DDA39
0x1408dd9f1  mov     eax, ebx
0x1408dd9f3  add     rsp, 30h
0x1408dd9f7  pop     rdi
0x1408dd9f8  pop     rsi
0x1408dd9f9  pop     rbx
0x1408dd9fa  retn
0x1408dd9fc  mov     ebx, 0C000000Dh
0x1408dda01  jmp     short loc_1408DD9B9
0x1408dda03  lea     rdx, KMPnPEvt_SwDevice_IrpCreate_Start
0x1408dda0a  lea     rcx, MS_KernelPnP_Provider_Context
0x1408dda11  call    McTemplateK0_EtwWriteTransfer
0x1408dda16  jmp     loc_1408DD921
0x1408dda1b  mov     ebx, 0C0000023h
0x1408dda20  jmp     short loc_1408DD9B9
0x1408dda22  mov     [rdi+30h], ebx
0x1408dda25  mov     qword ptr [rdi+38h], 0
0x1408dda2d  xor     edx, edx; PriorityBoost
0x1408dda2f  mov     rcx, rdi; Irp
0x1408dda32  call    IofCompleteRequest
0x1408dda37  jmp     short loc_1408DD9BE
0x1408dda39  mov     r9d, ebx
0x1408dda3c  lea     rdx, KMPnPEvt_SwDevice_IrpCreate_Stop
0x1408dda43  call    McTemplateK0d_EtwWriteTransfer
0x1408dda48  jmp     short loc_1408DD9F1
0x140b42994  push    rbp
0x140b42996  sub     rsp, 30h
0x140b4299a  mov     rbp, rdx
0x140b4299d  mov     rcx, [rcx]
0x140b429a0  mov     ecx, [rcx]; ExceptionCode
0x140b429a2  call    cs:__imp_RpcExceptionFilter
0x140b429a9  nop     dword ptr [rax+rax+00h]
0x140b429ae  nop
0x140b429af  add     rsp, 30h
0x140b429b3  pop     rbp
0x140b429b4  retn
```
