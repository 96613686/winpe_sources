# CKSAutomationThunk::HandleProperty(_IRP *,KSIDENTIFIER *,uint *)

- ea: `0x1400029a0`
- end: `0x140002a33`
- name: `?HandleProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAI@Z`
- size: `147`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1400029a0`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140002a09`
- `ks!KsSynchronousIoControlDevice` at `0x140002a09`

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
0x1400029a0  mov     [rsp+arg_10], rbx
0x1400029a5  push    rdi
0x1400029a6  sub     rsp, 40h
0x1400029aa  mov     eax, [rdx+14h]
0x1400029ad  mov     rdi, r8
0x1400029b0  mov     rcx, [rcx+0B8h]
0x1400029b7  mov     rbx, rdx
0x1400029ba  mov     [rsp+48h+arg_8], 0
0x1400029c3  mov     [rsp+48h+arg_0], 0
0x1400029cb  test    al, 2
0x1400029cd  jz      short loc_1400029D7
0x1400029cf  mov     eax, [r8]
0x1400029d2  mov     [rsp+48h+arg_8], rax
0x1400029d7  lea     rax, [rsp+48h+arg_0]
0x1400029dc  mov     r9, rbx; InBuffer
0x1400029df  mov     [rsp+48h+BytesReturned], rax; BytesReturned
0x1400029e4  xor     edx, edx; RequestorMode
0x1400029e6  lea     rax, [rsp+48h+arg_8]
0x1400029eb  mov     [rsp+48h+OutSize], 8; OutSize
0x1400029f3  mov     [rsp+48h+OutBuffer], rax; OutBuffer
0x1400029f8  mov     r8d, 2F0003h; IoControl
0x1400029fe  mov     eax, [rcx+10h]
0x140002a01  mov     rcx, [rcx+30h]; FileObject
0x140002a05  mov     [rsp+48h+InSize], eax; InSize
0x140002a09  call    cs:__imp_KsSynchronousIoControlDevice
0x140002a10  nop     dword ptr [rax+rax+00h]
0x140002a15  test    eax, eax
0x140002a17  js      short loc_140002A27
0x140002a19  mov     ecx, [rbx+14h]
0x140002a1c  test    cl, 1
0x140002a1f  jz      short loc_140002A27
0x140002a21  mov     ecx, dword ptr [rsp+48h+arg_8]
0x140002a25  mov     [rdi], ecx
0x140002a27  mov     rbx, [rsp+48h+arg_10]
0x140002a2c  add     rsp, 40h
0x140002a30  pop     rdi
0x140002a31  retn
```
