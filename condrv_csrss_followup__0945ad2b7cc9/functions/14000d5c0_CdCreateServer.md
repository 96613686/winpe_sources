# CdCreateServer

- ea: `0x14000d5c0`
- end: `0x14000d6a0`
- name: `CdCreateServer`
- size: `224`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000b020`
- `0x14000bb50`
- `0x14000c500`
- `0x14000d5c0`
- `0x14000d930`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d655`
- `ntoskrnl!IofCompleteRequest` at `0x14000d67e`
- `ntoskrnl!IofCompleteRequest` at `0x14000d655`
- `ntoskrnl!IofCompleteRequest` at `0x14000d67e`

## pseudocode

```c
__int64 __fastcall CdCreateServer(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int SecurityDescriptor; // edi
  struct _IRP *MasterIrp; // rax
  int v5; // eax
  PVOID v6; // rbp
  _QWORD *v7; // rcx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  P = 0;
  if ( CdpGetRequestorProcess(Irp) )
  {
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    if ( !MasterIrp || *(&MasterIrp->Size + 2) == 16 )
    {
      v5 = CdpAllocateServer(&P);
      v6 = P;
      SecurityDescriptor = v5;
      if ( v5 >= 0 )
      {
        v7 = (char *)P + 56;
        *((_QWORD *)P + 4) = CurrentStackLocation->FileObject;
        CurrentStackLocation->FileObject->FsContext = v6;
        SecurityDescriptor = CdCreateSecurityDescriptor(
                               v7,
                               *(struct _SECURITY_SUBJECT_CONTEXT **)(CurrentStackLocation->Parameters.WMI.ProviderId + 8));
        if ( SecurityDescriptor >= 0 )
        {
          Irp->IoStatus.Status = 0;
          Irp->IoStatus.Information = 0;
          IofCompleteRequest(Irp, 0);
          return 0;
        }
      }
      if ( v6 )
        CdDereferenceServer(v6);
    }
    else
    {
      SecurityDescriptor = -1073741306;
    }
  }
  else
  {
    SecurityDescriptor = -1073741813;
  }
  Irp->IoStatus.Status = SecurityDescriptor;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14000d5c0  mov     [rsp+arg_8], rbx
0x14000d5c5  mov     [rsp+arg_10], rbp
0x14000d5ca  push    rsi
0x14000d5cb  push    rdi
0x14000d5cc  push    r14
0x14000d5ce  sub     rsp, 20h
0x14000d5d2  mov     rsi, [rcx+0B8h]
0x14000d5d9  xor     r14d, r14d
0x14000d5dc  mov     [rsp+38h+P], r14
0x14000d5e1  mov     rbx, rcx
0x14000d5e4  call    CdpGetRequestorProcess
0x14000d5e9  test    rax, rax
0x14000d5ec  jnz     short loc_14000D5F5
0x14000d5ee  mov     edi, 0C000000Bh
0x14000d5f3  jmp     short loc_14000D672
0x14000d5f5  mov     rax, [rbx+18h]
0x14000d5f9  test    rax, rax
0x14000d5fc  jz      short loc_14000D60C
0x14000d5fe  cmp     word ptr [rax+6], 10h
0x14000d603  jz      short loc_14000D60C
0x14000d605  mov     edi, 0C0000206h
0x14000d60a  jmp     short loc_14000D672
0x14000d60c  lea     rcx, [rsp+38h+P]
0x14000d611  call    CdpAllocateServer
0x14000d616  mov     rbp, [rsp+38h+P]
0x14000d61b  mov     edi, eax
0x14000d61d  test    eax, eax
0x14000d61f  js      short loc_14000D665
0x14000d621  mov     rax, [rsi+30h]
0x14000d625  lea     rcx, [rbp+38h]
0x14000d629  mov     [rbp+20h], rax
0x14000d62d  mov     rax, [rsi+30h]
0x14000d631  mov     [rax+18h], rbp
0x14000d635  mov     rdx, [rsi+8]
0x14000d639  mov     rdx, [rdx+8]
0x14000d63d  call    CdCreateSecurityDescriptor
0x14000d642  mov     edi, eax
0x14000d644  test    eax, eax
0x14000d646  js      short loc_14000D665
0x14000d648  xor     edx, edx; PriorityBoost
0x14000d64a  mov     [rbx+30h], r14d
0x14000d64e  mov     rcx, rbx; Irp
0x14000d651  mov     [rbx+38h], r14
0x14000d655  call    cs:__imp_IofCompleteRequest
0x14000d65c  nop     dword ptr [rax+rax+00h]
0x14000d661  xor     eax, eax
0x14000d663  jmp     short loc_14000D68C
0x14000d665  test    rbp, rbp
0x14000d668  jz      short loc_14000D672
0x14000d66a  mov     rcx, rbp; P
0x14000d66d  call    CdDereferenceServer
0x14000d672  xor     edx, edx; PriorityBoost
0x14000d674  mov     [rbx+30h], edi
0x14000d677  mov     rcx, rbx; Irp
0x14000d67a  mov     [rbx+38h], r14
0x14000d67e  call    cs:__imp_IofCompleteRequest
0x14000d685  nop     dword ptr [rax+rax+00h]
0x14000d68a  mov     eax, edi
0x14000d68c  mov     rbx, [rsp+38h+arg_8]
0x14000d691  mov     rbp, [rsp+38h+arg_10]
0x14000d696  add     rsp, 20h
0x14000d69a  pop     r14
0x14000d69c  pop     rdi
0x14000d69d  pop     rsi
0x14000d69e  retn
```
