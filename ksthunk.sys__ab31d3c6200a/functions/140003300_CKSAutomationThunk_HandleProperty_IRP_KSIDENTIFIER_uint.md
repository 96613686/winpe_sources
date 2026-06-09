# CKSAutomationThunk::HandleProperty(_IRP *,KSIDENTIFIER *,uint *)

- ea: `0x140003300`
- end: `0x140003393`
- name: `?HandleProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAI@Z`
- size: `147`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003300`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140003369`
- `ks!KsSynchronousIoControlDevice` at `0x140003369`

## pseudocode

```c
NTSTATUS __fastcall CKSAutomationThunk::HandleProperty(struct _IRP *a1, struct KSIDENTIFIER *a2, unsigned int *a3)
{
  ULONG Flags; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  NTSTATUS result; // eax
  ULONG BytesReturned; // [rsp+50h] [rbp+8h] BYREF
  __int64 OutBuffer; // [rsp+58h] [rbp+10h] BYREF

  Flags = a2->Flags;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  OutBuffer = 0;
  BytesReturned = 0;
  if ( (Flags & 2) != 0 )
    OutBuffer = *a3;
  result = KsSynchronousIoControlDevice(
             CurrentStackLocation->FileObject,
             0,
             0x2F0003u,
             a2,
             CurrentStackLocation->Parameters.Create.Options,
             &OutBuffer,
             8u,
             &BytesReturned);
  if ( result >= 0 && (a2->Flags & 1) != 0 )
    *a3 = OutBuffer;
  return result;
}

```

## disassembly

```asm
0x140003300  mov     [rsp+arg_10], rbx
0x140003305  push    rdi
0x140003306  sub     rsp, 40h
0x14000330a  mov     eax, [rdx+14h]
0x14000330d  mov     rdi, r8
0x140003310  mov     rcx, [rcx+0B8h]
0x140003317  mov     rbx, rdx
0x14000331a  mov     [rsp+48h+arg_8], 0
0x140003323  mov     [rsp+48h+arg_0], 0
0x14000332b  test    al, 2
0x14000332d  jz      short loc_140003337
0x14000332f  mov     eax, [r8]
0x140003332  mov     [rsp+48h+arg_8], rax
0x140003337  lea     rax, [rsp+48h+arg_0]
0x14000333c  mov     r9, rbx; InBuffer
0x14000333f  mov     [rsp+48h+BytesReturned], rax; BytesReturned
0x140003344  xor     edx, edx; RequestorMode
0x140003346  lea     rax, [rsp+48h+arg_8]
0x14000334b  mov     [rsp+48h+OutSize], 8; OutSize
0x140003353  mov     [rsp+48h+OutBuffer], rax; OutBuffer
0x140003358  mov     r8d, 2F0003h; IoControl
0x14000335e  mov     eax, [rcx+10h]
0x140003361  mov     rcx, [rcx+30h]; FileObject
0x140003365  mov     [rsp+48h+InSize], eax; InSize
0x140003369  call    cs:__imp_KsSynchronousIoControlDevice
0x140003370  nop     dword ptr [rax+rax+00h]
0x140003375  test    eax, eax
0x140003377  js      short loc_140003387
0x140003379  mov     ecx, [rbx+14h]
0x14000337c  test    cl, 1
0x14000337f  jz      short loc_140003387
0x140003381  mov     ecx, dword ptr [rsp+48h+arg_8]
0x140003385  mov     [rdi], ecx
0x140003387  mov     rbx, [rsp+48h+arg_10]
0x14000338c  add     rsp, 40h
0x140003390  pop     rdi
0x140003391  retn
```
