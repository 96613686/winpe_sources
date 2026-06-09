# NatCreateExternalNaming

- ea: `0x140042008`
- end: `0x1400420b8`
- name: `NatCreateExternalNaming`
- size: `176`
- prototype: `__int64 __fastcall(PUNICODE_STRING DeviceName)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140045078`

## callees

- `0x14000218c`
- `0x140042008`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x140042072`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140042072`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004205e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004205e`

## pseudocode

```c
NTSTATUS __fastcall NatCreateExternalNaming(PUNICODE_STRING DeviceName)
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, ExternalName);
  result = IoCreateSymbolicLink(&DestinationString, DeviceName);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140042008  mov     [rsp+arg_0], rbx
0x14004200d  push    rdi
0x14004200e  sub     rsp, 30h
0x140042012  mov     rbx, rcx
0x140042015  mov     rcx, cs:WPP_GLOBAL_Control
0x14004201c  lea     rdi, WPP_GLOBAL_Control
0x140042023  cmp     rcx, rdi
0x140042026  jz      short loc_14004204A
0x140042028  mov     eax, [rcx+2Ch]
0x14004202b  test    al, 1
0x14004202d  jz      short loc_14004204A
0x14004202f  cmp     byte ptr [rcx+29h], 6
0x140042033  jb      short loc_14004204A
0x140042035  mov     rcx, [rcx+18h]
0x140042039  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140042040  mov     edx, 1Bh
0x140042045  call    WPP_SF_
0x14004204a  xorps   xmm0, xmm0
0x14004204d  lea     rdx, ExternalName; "\\DosDevices\\IPNAT"
0x140042054  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140042059  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14004205e  call    cs:__imp_RtlInitUnicodeString
0x140042065  nop     dword ptr [rax+rax+00h]
0x14004206a  mov     rdx, rbx; DeviceName
0x14004206d  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x140042072  call    cs:__imp_IoCreateSymbolicLink
0x140042079  nop     dword ptr [rax+rax+00h]
0x14004207e  mov     rcx, cs:WPP_GLOBAL_Control
0x140042085  cmp     rcx, rdi
0x140042088  jz      short loc_1400420AC
0x14004208a  mov     eax, [rcx+2Ch]
0x14004208d  test    al, 1
0x14004208f  jz      short loc_1400420AC
0x140042091  cmp     byte ptr [rcx+29h], 6
0x140042095  jb      short loc_1400420AC
0x140042097  mov     rcx, [rcx+18h]
0x14004209b  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x1400420a2  mov     edx, 1Ch
0x1400420a7  call    WPP_SF_
0x1400420ac  mov     rbx, [rsp+38h+arg_0]
0x1400420b1  add     rsp, 30h
0x1400420b5  pop     rdi
0x1400420b6  retn
```
