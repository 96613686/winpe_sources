# PiSwIrpStartCreate

- ea: `0x1409126a4`
- end: `0x14091280a`
- name: `PiSwIrpStartCreate`
- size: `358`
- prototype: `__int64 __fastcall(__int64 Irp, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1409112d0`

## callees

- `0x1402c0a40`
- `0x140471770`
- `0x1405d48d4`
- `0x1409126a4`
- `0x140912810`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x140912703`
- `msrpc!MesDecodeBufferHandleCreate` at `0x140912703`
- `msrpc!RpcExceptionFilter` at `0x140b44762`
- `msrpc!RpcExceptionFilter` at `0x140b44762`
- `msrpc!MesHandleFree` at `0x14091279c`
- `msrpc!MesHandleFree` at `0x14091279c`
- `msrpc!NdrMesTypeDecode3` at `0x140912741`
- `msrpc!NdrMesTypeDecode3` at `0x140912741`

## pseudocode

```c
__int64 __fastcall PiSwIrpStartCreate(__int64 Irp, __int64 a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *v4; // rbx
  PIRP v5; // rdi
  struct _IRP *v6; // rcx
  int Worker; // ebx
  __int64 v8; // rcx
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h]

  v4 = *(struct _IO_STACK_LOCATION **)(Irp + 184);
  v11 = 0;
  P = 0;
  v5 = (PIRP)Irp;
  v12 = Irp;
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(&MS_KernelPnP_Provider_Context, KMPnPEvt_SwDevice_IrpCreate_Start);
  v6 = *(struct _IRP **)(Irp + 24);
  if ( v6 )
  {
    if ( v4->Parameters.Read.Length < 0xC8 )
    {
      Worker = -1073741789;
    }
    else
    {
      Worker = MesDecodeBufferHandleCreate(v6, v4->Parameters.Create.Options, &v11);
      if ( Worker >= 0 )
      {
        NdrMesTypeDecode3(v11, "TP 3\a", &off_140B7B268, &off_140E0A520, 0, &P);
        Worker = PiSwIrpStartCreateWorker((__int64)P, Irp);
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
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0d_EtwWriteTransfer(v8, KMPnPEvt_SwDevice_IrpCreate_Stop, a3, (unsigned int)Worker);
  return (unsigned int)Worker;
}

```

## disassembly

```asm
0x1409126a4  mov     [rsp+arg_0], rcx
0x1409126a9  push    rbx
0x1409126aa  push    rsi
0x1409126ab  push    rdi
0x1409126ac  sub     rsp, 30h
0x1409126b0  mov     rsi, rcx
0x1409126b3  mov     rbx, [rcx+0B8h]
0x1409126ba  mov     [rsp+48h+arg_10], 0
0x1409126c3  mov     [rsp+48h+P], 0
0x1409126cc  mov     rdi, rcx
0x1409126cf  mov     [rsp+48h+arg_18], rcx
0x1409126d4  test    cs:byte_140ED9FEC, 40h
0x1409126db  jnz     loc_1409127C3
0x1409126e1  mov     rcx, [rsi+18h]
0x1409126e5  test    rcx, rcx
0x1409126e8  jz      loc_1409127BC
0x1409126ee  cmp     dword ptr [rbx+8], 0C8h
0x1409126f5  jb      loc_1409127DB
0x1409126fb  lea     r8, [rsp+48h+arg_10]
0x140912700  mov     edx, [rbx+10h]
0x140912703  call    cs:__imp_MesDecodeBufferHandleCreate
0x14091270a  nop     dword ptr [rax+rax+00h]
0x14091270f  mov     ebx, eax
0x140912711  test    eax, eax
0x140912713  js      short loc_140912779
0x140912715  lea     rax, [rsp+48h+P]
0x14091271a  mov     [rsp+48h+var_20], rax
0x14091271f  mov     [rsp+48h+var_28], 0
0x140912727  lea     r9, off_140E0A520
0x14091272e  lea     r8, off_140B7B268
0x140912735  lea     rdx, aTp3_0; "TP 3\a"
0x14091273c  mov     rcx, [rsp+48h+arg_10]
0x140912741  call    cs:__imp_NdrMesTypeDecode3
0x140912748  nop     dword ptr [rax+rax+00h]
0x14091274d  jmp     short loc_140912764
0x14091274f  mov     ebx, eax
0x140912751  mov     [rsp+48h+P], 0
0x14091275a  mov     rsi, [rsp+48h+arg_0]
0x14091275f  mov     rdi, [rsp+48h+arg_18]
0x140912764  test    ebx, ebx
0x140912766  js      short loc_140912779
0x140912768  mov     rdx, rsi
0x14091276b  mov     rcx, [rsp+48h+P]
0x140912770  call    PiSwIrpStartCreateWorker
0x140912775  mov     ebx, eax
0x140912777  xor     edi, edi
0x140912779  test    rdi, rdi
0x14091277c  jnz     short loc_1409127E2
0x14091277e  mov     rcx, [rsp+48h+P]; P
0x140912783  test    rcx, rcx
0x140912786  jz      short loc_140912792
0x140912788  mov     edx, 6370726Bh; Tag
0x14091278d  call    ExFreePoolWithTag
0x140912792  mov     rcx, [rsp+48h+arg_10]
0x140912797  test    rcx, rcx
0x14091279a  jz      short loc_1409127A8
0x14091279c  call    cs:__imp_MesHandleFree
0x1409127a3  nop     dword ptr [rax+rax+00h]
0x1409127a8  test    cs:byte_140ED9FEC, 40h
0x1409127af  jnz     short loc_1409127F9
0x1409127b1  mov     eax, ebx
0x1409127b3  add     rsp, 30h
0x1409127b7  pop     rdi
0x1409127b8  pop     rsi
0x1409127b9  pop     rbx
0x1409127ba  retn
0x1409127bc  mov     ebx, 0C000000Dh
0x1409127c1  jmp     short loc_140912779
0x1409127c3  lea     rdx, KMPnPEvt_SwDevice_IrpCreate_Start
0x1409127ca  lea     rcx, MS_KernelPnP_Provider_Context
0x1409127d1  call    McTemplateK0_EtwWriteTransfer
0x1409127d6  jmp     loc_1409126E1
0x1409127db  mov     ebx, 0C0000023h
0x1409127e0  jmp     short loc_140912779
0x1409127e2  mov     [rdi+30h], ebx
0x1409127e5  mov     qword ptr [rdi+38h], 0
0x1409127ed  xor     edx, edx; PriorityBoost
0x1409127ef  mov     rcx, rdi; Irp
0x1409127f2  call    IofCompleteRequest
0x1409127f7  jmp     short loc_14091277E
0x1409127f9  mov     r9d, ebx
0x1409127fc  lea     rdx, KMPnPEvt_SwDevice_IrpCreate_Stop
0x140912803  call    McTemplateK0d_EtwWriteTransfer
0x140912808  jmp     short loc_1409127B1
0x140b44754  push    rbp
0x140b44756  sub     rsp, 30h
0x140b4475a  mov     rbp, rdx
0x140b4475d  mov     rcx, [rcx]
0x140b44760  mov     ecx, [rcx]; ExceptionCode
0x140b44762  call    cs:__imp_RpcExceptionFilter
0x140b44769  nop     dword ptr [rax+rax+00h]
0x140b4476e  nop
0x140b4476f  add     rsp, 30h
0x140b44773  pop     rbp
0x140b44774  retn
```
