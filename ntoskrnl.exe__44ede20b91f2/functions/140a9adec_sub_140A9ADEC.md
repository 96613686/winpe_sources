# sub_140A9ADEC

- ea: `0x140a9adec`
- end: `0x140a9b022`
- name: `sub_140A9ADEC`
- size: `566`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1408dc4f0`

## callees

- `0x140227210`
- `0x1402b1240`
- `0x1402f8270`
- `0x140461498`
- `0x14051e400`
- `0x1408ce580`
- `0x1408d3130`
- `0x1408d4784`
- `0x1408e1ba8`
- `0x1408e2114`
- `0x1408e26c8`
- `0x140a9adec`
- `0x140bae8e0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x140a9ae4b`
- `msrpc!MesDecodeBufferHandleCreate` at `0x140a9ae4b`
- `msrpc!RpcExceptionFilter` at `0x140b49030`
- `msrpc!RpcExceptionFilter` at `0x140b49030`
- `msrpc!MesHandleFree` at `0x140a9afae`
- `msrpc!MesHandleFree` at `0x140a9afae`
- `msrpc!NdrMesTypeDecode3` at `0x140a9ae8d`
- `msrpc!NdrMesTypeDecode3` at `0x140a9ae8d`

## pseudocode

```c
__int64 __fastcall sub_140A9ADEC(PIRP Irp, __int64 a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext2; // rdi
  struct _IRP *MasterIrp; // rcx
  NTSTATUS v7; // ebx
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
  if ( (byte_140EDA02C & 0x40) != 0 )
    sub_14051E400((_DWORD)Irp, (unsigned int)qword_14002D4C0, a3, FsContext2[1], FsContext2[2]);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
    goto LABEL_14;
  v7 = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, &v14);
  if ( v7 < 0 )
    goto LABEL_15;
  NdrMesTypeDecode3(v14, "TP 3\a", &off_140B78E48, &off_140E0A520, 1, &v12);
  if ( v12 && *((_QWORD *)v12 + 1) && *(_DWORD *)v12 )
  {
    v7 = sub_1408D4784(*((_QWORD *)v12 + 1));
    if ( v7 >= 0 )
    {
      sub_1408E1BA8();
      if ( (unsigned __int8)sub_1408E2114(FsContext2) )
      {
        v7 = sub_1408CE580(FsContext2[10], 200, 1466986064, &P);
        if ( v7 >= 0 )
          v7 = sub_1408E26C8(
                 FsContext2[21],
                 *((unsigned int *)FsContext2 + 44),
                 *((_QWORD *)v12 + 1),
                 *(unsigned int *)v12);
      }
      else
      {
        v7 = -1073741637;
      }
      ExReleaseResourceLite(&stru_140F81740);
      KeLeaveCriticalRegion();
      if ( v7 >= 0 )
        v7 = sub_1408D3130(P, 1, *((_QWORD *)v12 + 1), *(unsigned int *)v12);
    }
  }
  else
  {
LABEL_14:
    v7 = -1073741811;
  }
LABEL_15:
  if ( P )
    ExFreePoolWithTag(P, 0x57706E50u);
  if ( v12 )
    ExFreePoolWithTag(v12, 0x6370726Bu);
  if ( v14 )
    MesHandleFree();
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140EDA02C & 0x40) != 0 )
  {
    LODWORD(v11) = v7;
    sub_140461498(v8, (unsigned int)qword_14002D420, v9, FsContext2[1], FsContext2[2], v11, FsContext2);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140a9adec  mov     r11, rsp
0x140a9adef  mov     [r11+8], rcx
0x140a9adf3  push    rbx
0x140a9adf4  push    rsi
0x140a9adf5  push    rdi
0x140a9adf6  sub     rsp, 40h
0x140a9adfa  mov     rsi, rcx
0x140a9adfd  mov     rbx, [rcx+0B8h]
0x140a9ae04  mov     rax, [rbx+30h]
0x140a9ae08  mov     rdi, [rax+20h]
0x140a9ae0c  mov     [rsp+58h+var_28], rdi
0x140a9ae11  mov     qword ptr [r11+20h], 0
0x140a9ae19  mov     qword ptr [r11+10h], 0
0x140a9ae21  mov     qword ptr [r11+18h], 0
0x140a9ae29  test    cs:byte_140EDA02C, 40h
0x140a9ae30  jnz     loc_140A9AFE5
0x140a9ae36  mov     rcx, [rsi+18h]
0x140a9ae3a  test    rcx, rcx
0x140a9ae3d  jz      loc_140A9AF77
0x140a9ae43  lea     r8, [rsp+58h+arg_18]
0x140a9ae48  mov     edx, [rbx+10h]
0x140a9ae4b  call    cs:MesDecodeBufferHandleCreate
0x140a9ae52  nop     dword ptr [rax+rax+00h]
0x140a9ae57  mov     ebx, eax
0x140a9ae59  test    eax, eax
0x140a9ae5b  js      loc_140A9AF7C
0x140a9ae61  lea     rax, [rsp+58h+arg_8]
0x140a9ae66  mov     [rsp+58h+var_30], rax
0x140a9ae6b  mov     dword ptr [rsp+58h+var_38], 1
0x140a9ae73  lea     r9, off_140E0A520
0x140a9ae7a  lea     r8, off_140B78E48
0x140a9ae81  lea     rdx, aTp3_0; "TP 3\a"
0x140a9ae88  mov     rcx, [rsp+58h+arg_18]
0x140a9ae8d  call    cs:NdrMesTypeDecode3
0x140a9ae94  nop     dword ptr [rax+rax+00h]
0x140a9ae99  jmp     short loc_140A9AEB0
0x140a9ae9b  mov     ebx, eax
0x140a9ae9d  mov     [rsp+58h+arg_8], 0
0x140a9aea6  mov     rsi, [rsp+58h+arg_0]
0x140a9aeab  mov     rdi, [rsp+58h+var_28]
0x140a9aeb0  test    ebx, ebx
0x140a9aeb2  js      loc_140A9AF7C
0x140a9aeb8  mov     rcx, [rsp+58h+arg_8]
0x140a9aebd  test    rcx, rcx
0x140a9aec0  jz      loc_140A9AF77
0x140a9aec6  mov     rax, [rcx+8]
0x140a9aeca  test    rax, rax
0x140a9aecd  jz      loc_140A9AF77
0x140a9aed3  mov     edx, [rcx]
0x140a9aed5  test    edx, edx
0x140a9aed7  jz      loc_140A9AF77
0x140a9aedd  mov     rcx, rax
0x140a9aee0  call    sub_1408D4784
0x140a9aee5  mov     ebx, eax
0x140a9aee7  test    eax, eax
0x140a9aee9  js      loc_140A9AF7C
0x140a9aeef  call    sub_1408E1BA8
0x140a9aef4  mov     rcx, rdi
0x140a9aef7  call    sub_1408E2114
0x140a9aefc  test    al, al
0x140a9aefe  jz      loc_140A9AFDB
0x140a9af04  lea     r9, [rsp+58h+P]
0x140a9af09  mov     edx, 0C8h
0x140a9af0e  mov     r8d, 57706E50h
0x140a9af14  mov     rcx, [rdi+50h]
0x140a9af18  call    sub_1408CE580
0x140a9af1d  mov     ebx, eax
0x140a9af1f  test    eax, eax
0x140a9af21  js      short loc_140A9AF43
0x140a9af23  mov     r8, [rsp+58h+arg_8]
0x140a9af28  mov     r9d, [r8]
0x140a9af2b  mov     r8, [r8+8]
0x140a9af2f  mov     edx, [rdi+0B0h]
0x140a9af35  mov     rcx, [rdi+0A8h]
0x140a9af3c  call    sub_1408E26C8
0x140a9af41  mov     ebx, eax
0x140a9af43  lea     rcx, stru_140F81740; Resource
0x140a9af4a  call    ExReleaseResourceLite
0x140a9af4f  call    KeLeaveCriticalRegion
0x140a9af54  test    ebx, ebx
0x140a9af56  js      short loc_140A9AF7C
0x140a9af58  mov     r8, [rsp+58h+arg_8]
0x140a9af5d  mov     r9d, [r8]
0x140a9af60  mov     r8, [r8+8]
0x140a9af64  mov     edx, 1
0x140a9af69  mov     rcx, [rsp+58h+P]
0x140a9af6e  call    sub_1408D3130
0x140a9af73  mov     ebx, eax
0x140a9af75  jmp     short loc_140A9AF7C
0x140a9af77  mov     ebx, 0C000000Dh
0x140a9af7c  mov     rcx, [rsp+58h+P]; P
0x140a9af81  test    rcx, rcx
0x140a9af84  jz      short loc_140A9AF90
0x140a9af86  mov     edx, 57706E50h; Tag
0x140a9af8b  call    ExFreePoolWithTag
0x140a9af90  mov     rcx, [rsp+58h+arg_8]; P
0x140a9af95  test    rcx, rcx
0x140a9af98  jz      short loc_140A9AFA4
0x140a9af9a  mov     edx, 6370726Bh; Tag
0x140a9af9f  call    ExFreePoolWithTag
0x140a9afa4  mov     rcx, [rsp+58h+arg_18]
0x140a9afa9  test    rcx, rcx
0x140a9afac  jz      short loc_140A9AFBA
0x140a9afae  call    cs:MesHandleFree
0x140a9afb5  nop     dword ptr [rax+rax+00h]
0x140a9afba  mov     [rsi+30h], ebx
0x140a9afbd  xor     edx, edx; PriorityBoost
0x140a9afbf  mov     rcx, rsi; Irp
0x140a9afc2  call    IofCompleteRequest
0x140a9afc7  test    cs:byte_140EDA02C, 40h
0x140a9afce  jnz     short loc_140A9B003
0x140a9afd0  mov     eax, ebx
0x140a9afd2  add     rsp, 40h
0x140a9afd6  pop     rdi
0x140a9afd7  pop     rsi
0x140a9afd8  pop     rbx
0x140a9afd9  retn
0x140a9afdb  mov     ebx, 0C00000BBh
0x140a9afe0  jmp     loc_140A9AF43
0x140a9afe5  mov     rax, [rdi+10h]
0x140a9afe9  mov     [rsp+58h+var_38], rax
0x140a9afee  mov     r9, [rdi+8]
0x140a9aff2  lea     rdx, qword_14002D4C0
0x140a9aff9  call    sub_14051E400
0x140a9affe  jmp     loc_140A9AE36
0x140a9b003  mov     dword ptr [rsp+58h+var_30], ebx
0x140a9b007  mov     rax, [rdi+10h]
0x140a9b00b  mov     [rsp+58h+var_38], rax
0x140a9b010  mov     r9, [rdi+8]
0x140a9b014  lea     rdx, qword_14002D420
0x140a9b01b  call    sub_140461498
0x140a9b020  jmp     short loc_140A9AFD0
0x140b49022  push    rbp
0x140b49024  sub     rsp, 30h
0x140b49028  mov     rbp, rdx
0x140b4902b  mov     rcx, [rcx]
0x140b4902e  mov     ecx, [rcx]; ExceptionCode
0x140b49030  call    cs:RpcExceptionFilter
0x140b49037  nop     dword ptr [rax+rax+00h]
0x140b4903c  nop
0x140b4903d  add     rsp, 30h
0x140b49041  pop     rbp
0x140b49042  retn
```
