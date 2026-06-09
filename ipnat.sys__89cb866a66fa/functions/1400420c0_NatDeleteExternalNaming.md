# NatDeleteExternalNaming

- ea: `0x1400420c0`
- end: `0x140042161`
- name: `NatDeleteExternalNaming`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140007ca0`

## callees

- `0x14000218c`
- `0x1400420c0`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140042120`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140042120`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004210f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004210f`

## pseudocode

```c
NTSTATUS NatDeleteExternalNaming()
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, ExternalName);
  result = IoDeleteSymbolicLink(&DestinationString);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1400420c0  push    rbx
0x1400420c2  sub     rsp, 30h
0x1400420c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400420cd  lea     rbx, WPP_GLOBAL_Control
0x1400420d4  cmp     rcx, rbx
0x1400420d7  jz      short loc_1400420FB
0x1400420d9  mov     eax, [rcx+2Ch]
0x1400420dc  test    al, 1
0x1400420de  jz      short loc_1400420FB
0x1400420e0  cmp     byte ptr [rcx+29h], 6
0x1400420e4  jb      short loc_1400420FB
0x1400420e6  mov     rcx, [rcx+18h]
0x1400420ea  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x1400420f1  mov     edx, 1Dh
0x1400420f6  call    WPP_SF_
0x1400420fb  xorps   xmm0, xmm0
0x1400420fe  lea     rdx, ExternalName; "\\DosDevices\\IPNAT"
0x140042105  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14004210a  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14004210f  call    cs:__imp_RtlInitUnicodeString
0x140042116  nop     dword ptr [rax+rax+00h]
0x14004211b  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x140042120  call    cs:__imp_IoDeleteSymbolicLink
0x140042127  nop     dword ptr [rax+rax+00h]
0x14004212c  mov     rcx, cs:WPP_GLOBAL_Control
0x140042133  cmp     rcx, rbx
0x140042136  jz      short loc_14004215A
0x140042138  mov     eax, [rcx+2Ch]
0x14004213b  test    al, 1
0x14004213d  jz      short loc_14004215A
0x14004213f  cmp     byte ptr [rcx+29h], 6
0x140042143  jb      short loc_14004215A
0x140042145  mov     rcx, [rcx+18h]
0x140042149  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140042150  mov     edx, 1Eh
0x140042155  call    WPP_SF_
0x14004215a  add     rsp, 30h
0x14004215e  pop     rbx
0x14004215f  retn
```
