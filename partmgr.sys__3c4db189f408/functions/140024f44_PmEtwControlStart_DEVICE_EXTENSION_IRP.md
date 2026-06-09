# PmEtwControlStart(_DEVICE_EXTENSION *,_IRP *)

- ea: `0x140024f44`
- end: `0x140024fcb`
- name: `?PmEtwControlStart@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z`
- size: `135`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400068b0`

## callees

- `0x14000c238`
- `0x140010f20`
- `0x140024f44`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140024f7a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140024f7a`

## pseudocode

```c
void __fastcall PmEtwControlStart(struct _DEVICE_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v4; // rcx
  __int128 v5; // [rsp+30h] [rbp-28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = 0;
  if ( (int)IoGetActivityIdIrp(a2, &v5) >= 0 && (Microsoft_Windows_PartitionEnableBits & 1) != 0 )
    McTemplateK0qq_EtwWriteTransfer(
      v4,
      ControlStart,
      &v5,
      *((unsigned int *)a1 + 42),
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
}

```

## disassembly

```asm
0x140024f44  mov     [rsp+arg_10], rbx
0x140024f49  push    rdi
0x140024f4a  sub     rsp, 50h
0x140024f4e  mov     rax, cs:__security_cookie
0x140024f55  xor     rax, rsp
0x140024f58  mov     [rsp+58h+var_18], rax
0x140024f5d  mov     rdi, [rdx+0B8h]
0x140024f64  mov     rax, rdx
0x140024f67  mov     rbx, rcx
0x140024f6a  lea     rdx, [rsp+58h+var_28]
0x140024f6f  xorps   xmm0, xmm0
0x140024f72  mov     rcx, rax
0x140024f75  movups  [rsp+58h+var_28], xmm0
0x140024f7a  call    cs:__imp_IoGetActivityIdIrp
0x140024f81  nop     dword ptr [rax+rax+00h]
0x140024f86  test    eax, eax
0x140024f88  js      short loc_140024FB2
0x140024f8a  test    cs:Microsoft_Windows_PartitionEnableBits, 1
0x140024f91  jz      short loc_140024FB2
0x140024f93  mov     eax, [rdi+18h]
0x140024f96  lea     r8, [rsp+58h+var_28]
0x140024f9b  mov     r9d, [rbx+0A8h]
0x140024fa2  lea     rdx, ControlStart
0x140024fa9  mov     [rsp+58h+var_38], eax
0x140024fad  call    McTemplateK0qq_EtwWriteTransfer
0x140024fb2  mov     rcx, [rsp+58h+var_18]
0x140024fb7  xor     rcx, rsp; StackCookie
0x140024fba  call    __security_check_cookie
0x140024fbf  mov     rbx, [rsp+58h+arg_10]
0x140024fc4  add     rsp, 50h
0x140024fc8  pop     rdi
0x140024fc9  retn
```
