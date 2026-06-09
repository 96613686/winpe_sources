# PmEtwControlComplete(_DEVICE_EXTENSION *,_IRP *,long)

- ea: `0x14001fb44`
- end: `0x14001fbd5`
- name: `?PmEtwControlComplete@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@J@Z`
- size: `145`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _IRP *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400068b0`

## callees

- `0x14000c2a0`
- `0x140010f20`
- `0x14001fb44`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14001fb82`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001fb82`

## pseudocode

```c
void __fastcall PmEtwControlComplete(struct _DEVICE_EXTENSION *a1, struct _IRP *a2, char a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v6; // edx
  int v7; // ecx
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v8 = 0;
  if ( (int)IoGetActivityIdIrp(a2, &v8) >= 0 && (Microsoft_Windows_PartitionEnableBits & 1) != 0 )
    McTemplateK0qqq_EtwWriteTransfer(
      v7,
      v6,
      (unsigned int)&v8,
      *((_DWORD *)a1 + 42),
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart,
      a3);
}

```

## disassembly

```asm
0x14001fb44  mov     [rsp+arg_10], rbx
0x14001fb49  mov     [rsp+arg_18], rsi
0x14001fb4e  push    rdi
0x14001fb4f  sub     rsp, 50h
0x14001fb53  mov     rax, cs:__security_cookie
0x14001fb5a  xor     rax, rsp
0x14001fb5d  mov     [rsp+58h+var_18], rax
0x14001fb62  mov     rsi, [rdx+0B8h]
0x14001fb69  mov     rax, rdx
0x14001fb6c  mov     rdi, rcx
0x14001fb6f  lea     rdx, [rsp+58h+var_28]
0x14001fb74  xorps   xmm0, xmm0
0x14001fb77  mov     rcx, rax
0x14001fb7a  mov     ebx, r8d
0x14001fb7d  movups  [rsp+58h+var_28], xmm0
0x14001fb82  call    cs:__imp_IoGetActivityIdIrp
0x14001fb89  nop     dword ptr [rax+rax+00h]
0x14001fb8e  test    eax, eax
0x14001fb90  js      short loc_14001FBB7
0x14001fb92  test    cs:Microsoft_Windows_PartitionEnableBits, 1
0x14001fb99  jz      short loc_14001FBB7
0x14001fb9b  mov     eax, [rsi+18h]
0x14001fb9e  lea     r8, [rsp+58h+var_28]
0x14001fba3  mov     r9d, [rdi+0A8h]
0x14001fbaa  mov     [rsp+58h+var_30], ebx
0x14001fbae  mov     [rsp+58h+var_38], eax
0x14001fbb2  call    McTemplateK0qqq_EtwWriteTransfer
0x14001fbb7  mov     rcx, [rsp+58h+var_18]
0x14001fbbc  xor     rcx, rsp; StackCookie
0x14001fbbf  call    __security_check_cookie
0x14001fbc4  mov     rbx, [rsp+58h+arg_10]
0x14001fbc9  mov     rsi, [rsp+58h+arg_18]
0x14001fbce  add     rsp, 50h
0x14001fbd2  pop     rdi
0x14001fbd3  retn
```
