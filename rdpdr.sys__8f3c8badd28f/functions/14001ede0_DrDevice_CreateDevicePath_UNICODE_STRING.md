# DrDevice::CreateDevicePath(_UNICODE_STRING *)

- ea: `0x14001ede0`
- end: `0x14001ee9d`
- name: `?CreateDevicePath@DrDevice@@MEAAJPEAU_UNICODE_STRING@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(DrDevice *__hidden this, PUNICODE_STRING Destination)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400035a0`
- `0x14001ede0`
- `0x140029aa8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001ee0c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001ee0c`

## pseudocode

```c
__int64 __fastcall DrDevice::CreateDevicePath(DrDevice *this, PUNICODE_STRING Destination)
{
  NTSTATUS appended; // edi
  unsigned __int16 MaximumLength; // cx
  unsigned __int64 Length; // rdx
  struct _UNICODE_STRING v8; // [rsp+20h] [rbp-18h] BYREF

  Destination->Length = 0;
  v8 = 0;
  appended = RtlAppendUnicodeToString(Destination, L"\\Device\\RdpDr");
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
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, Destination);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001ede0  mov     [rsp+arg_0], rbx
0x14001ede5  mov     [rsp+arg_8], rsi
0x14001edea  push    rdi
0x14001edeb  sub     rsp, 30h
0x14001edef  mov     rbx, rdx
0x14001edf2  xor     eax, eax
0x14001edf4  mov     [rdx], ax
0x14001edf7  mov     rsi, rcx
0x14001edfa  xorps   xmm0, xmm0
0x14001edfd  lea     rdx, aDeviceRdpdr; "\\Device\\RdpDr"
0x14001ee04  mov     rcx, rbx; Destination
0x14001ee07  movups  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x14001ee0c  call    cs:__imp_RtlAppendUnicodeToString
0x14001ee13  nop     dword ptr [rax+rax+00h]
0x14001ee18  mov     edi, eax
0x14001ee1a  test    eax, eax
0x14001ee1c  js      short loc_14001EE59
0x14001ee1e  movzx   ecx, word ptr [rbx+2]
0x14001ee22  xor     edx, edx
0x14001ee24  mov     [rsp+38h+var_18.Length], dx
0x14001ee29  movzx   edx, word ptr [rbx]
0x14001ee2c  sub     cx, dx
0x14001ee2f  shr     rdx, 1
0x14001ee32  mov     [rsp+38h+var_18.MaximumLength], cx
0x14001ee37  mov     rcx, [rbx+8]
0x14001ee3b  lea     rdx, [rcx+rdx*2]
0x14001ee3f  mov     rcx, rsi; this
0x14001ee42  mov     [rsp+38h+var_18.Buffer], rdx
0x14001ee47  lea     rdx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x14001ee4c  call    ?CreateReferenceString@DrDevice@@QEAAXPEAU_UNICODE_STRING@@@Z; DrDevice::CreateReferenceString(_UNICODE_STRING *)
0x14001ee51  movzx   eax, [rsp+38h+var_18.Length]
0x14001ee56  add     [rbx], ax
0x14001ee59  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee60  lea     rax, WPP_GLOBAL_Control
0x14001ee67  cmp     rcx, rax
0x14001ee6a  jz      short loc_14001EE8A
0x14001ee6c  cmp     byte ptr [rcx+29h], 4
0x14001ee70  jb      short loc_14001EE8A
0x14001ee72  mov     rcx, [rcx+18h]
0x14001ee76  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001ee7d  mov     edx, 0Eh
0x14001ee82  mov     r9, rbx
0x14001ee85  call    WPP_SF_Z
0x14001ee8a  mov     rbx, [rsp+38h+arg_0]
0x14001ee8f  mov     eax, edi
0x14001ee91  mov     rsi, [rsp+38h+arg_8]
0x14001ee96  add     rsp, 30h
0x14001ee9a  pop     rdi
0x14001ee9b  retn
```
