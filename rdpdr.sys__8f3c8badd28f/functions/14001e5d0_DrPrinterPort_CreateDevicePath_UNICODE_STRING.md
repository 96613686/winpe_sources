# DrPrinterPort::CreateDevicePath(_UNICODE_STRING *)

- ea: `0x14001e5d0`
- end: `0x14001e68d`
- name: `?CreateDevicePath@DrPrinterPort@@MEAAJPEAU_UNICODE_STRING@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(DrPrinterPort *__hidden this, PUNICODE_STRING Destination)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400035a0`
- `0x14001e5d0`
- `0x140029aa8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e5fc`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e5fc`

## pseudocode

```c
__int64 __fastcall DrPrinterPort::CreateDevicePath(DrPrinterPort *this, PUNICODE_STRING Destination)
{
  NTSTATUS appended; // edi
  unsigned __int16 MaximumLength; // cx
  unsigned __int64 Length; // rdx
  struct _UNICODE_STRING v8; // [rsp+20h] [rbp-18h] BYREF

  Destination->Length = 0;
  v8 = 0;
  appended = RtlAppendUnicodeToString(Destination, L"\\Device\\RdpDrPort");
  if ( appended >= 0 )
  {
    MaximumLength = Destination->MaximumLength;
    v8.Length = 0;
    Length = Destination->Length;
    v8.MaximumLength = MaximumLength - Length;
    v8.Buffer = &Destination->Buffer[Length >> 1];
    DrDevice::CreateReferenceString(this, &v8);
    Destination->Length += v8.Length;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids, Destination);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001e5d0  mov     [rsp+arg_0], rbx
0x14001e5d5  mov     [rsp+arg_8], rsi
0x14001e5da  push    rdi
0x14001e5db  sub     rsp, 30h
0x14001e5df  mov     rbx, rdx
0x14001e5e2  xor     eax, eax
0x14001e5e4  mov     [rdx], ax
0x14001e5e7  mov     rsi, rcx
0x14001e5ea  xorps   xmm0, xmm0
0x14001e5ed  lea     rdx, aDeviceRdpdrpor; "\\Device\\RdpDrPort"
0x14001e5f4  mov     rcx, rbx; Destination
0x14001e5f7  movups  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x14001e5fc  call    cs:__imp_RtlAppendUnicodeToString
0x14001e603  nop     dword ptr [rax+rax+00h]
0x14001e608  mov     edi, eax
0x14001e60a  test    eax, eax
0x14001e60c  js      short loc_14001E649
0x14001e60e  movzx   ecx, word ptr [rbx+2]
0x14001e612  xor     edx, edx
0x14001e614  mov     [rsp+38h+var_18.Length], dx
0x14001e619  movzx   edx, word ptr [rbx]
0x14001e61c  sub     cx, dx
0x14001e61f  shr     rdx, 1
0x14001e622  mov     [rsp+38h+var_18.MaximumLength], cx
0x14001e627  mov     rcx, [rbx+8]
0x14001e62b  lea     rdx, [rcx+rdx*2]
0x14001e62f  mov     rcx, rsi; this
0x14001e632  mov     [rsp+38h+var_18.Buffer], rdx
0x14001e637  lea     rdx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x14001e63c  call    ?CreateReferenceString@DrDevice@@QEAAXPEAU_UNICODE_STRING@@@Z; DrDevice::CreateReferenceString(_UNICODE_STRING *)
0x14001e641  movzx   eax, [rsp+38h+var_18.Length]
0x14001e646  add     [rbx], ax
0x14001e649  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e650  lea     rax, WPP_GLOBAL_Control
0x14001e657  cmp     rcx, rax
0x14001e65a  jz      short loc_14001E67A
0x14001e65c  cmp     byte ptr [rcx+29h], 4
0x14001e660  jb      short loc_14001E67A
0x14001e662  mov     rcx, [rcx+18h]
0x14001e666  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x14001e66d  mov     edx, 16h
0x14001e672  mov     r9, rbx
0x14001e675  call    WPP_SF_Z
0x14001e67a  mov     rbx, [rsp+38h+arg_0]
0x14001e67f  mov     eax, edi
0x14001e681  mov     rsi, [rsp+38h+arg_8]
0x14001e686  add     rsp, 30h
0x14001e68a  pop     rdi
0x14001e68b  retn
```
