# LldpSetDeviceDacl

- ea: `0x140004b44`
- end: `0x140004c1c`
- name: `LldpSetDeviceDacl`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e008`

## callees

- `0x140004b00`
- `0x140004b44`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140004c07`
- `ntoskrnl!ZwClose` at `0x140004c07`
- `ntoskrnl!ZwSetSecurityObject` at `0x140004bba`
- `ntoskrnl!ZwSetSecurityObject` at `0x140004bba`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004b77`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004b77`

## pseudocode

```c
__int64 __fastcall LldpSetDeviceDacl(void *a1)
{
  NTSTATUS v1; // ebx
  PDEVICE_OBJECT v2; // rcx
  __int64 v3; // rdx
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF

  Handle = 0;
  v1 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( v1 >= 0 )
  {
    v1 = ZwSetSecurityObject(Handle, 4u, qword_140009640);
    if ( v1 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v3 = 12;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v3 = 11;
LABEL_9:
      WPP_SF_d(v2->AttachedDevice, v3, WPP_ea1b45b0a6943981c34a08d8d3c26e2c_Traceguids, (unsigned int)v1);
    }
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140004b44  mov     r11, rsp
0x140004b47  push    rbx
0x140004b48  sub     rsp, 40h
0x140004b4c  lea     rax, [r11+10h]
0x140004b50  mov     qword ptr [r11+10h], 0
0x140004b58  mov     [r11-18h], rax
0x140004b5c  mov     r9d, 40000h; DesiredAccess
0x140004b62  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140004b67  xor     r8d, r8d; PassedAccessState
0x140004b6a  mov     edx, 200h; HandleAttributes
0x140004b6f  mov     qword ptr [r11-28h], 0
0x140004b77  call    cs:__imp_ObOpenObjectByPointer
0x140004b7e  nop     dword ptr [rax+rax+00h]
0x140004b83  mov     ebx, eax
0x140004b85  test    eax, eax
0x140004b87  jns     short loc_140004BA9
0x140004b89  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b90  lea     rax, WPP_GLOBAL_Control
0x140004b97  cmp     rcx, rax
0x140004b9a  jz      short loc_140004BFD
0x140004b9c  cmp     byte ptr [rcx+29h], 2
0x140004ba0  jb      short loc_140004BFD
0x140004ba2  mov     edx, 0Bh
0x140004ba7  jmp     short loc_140004BEA
0x140004ba9  mov     rcx, [rsp+48h+Handle]; Handle
0x140004bae  lea     r8, qword_140009640; SecurityDescriptor
0x140004bb5  mov     edx, 4; SecurityInformation
0x140004bba  call    cs:__imp_ZwSetSecurityObject
0x140004bc1  nop     dword ptr [rax+rax+00h]
0x140004bc6  mov     ebx, eax
0x140004bc8  test    eax, eax
0x140004bca  jns     short loc_140004BFD
0x140004bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bd3  lea     rax, WPP_GLOBAL_Control
0x140004bda  cmp     rcx, rax
0x140004bdd  jz      short loc_140004BFD
0x140004bdf  cmp     byte ptr [rcx+29h], 2
0x140004be3  jb      short loc_140004BFD
0x140004be5  mov     edx, 0Ch
0x140004bea  mov     rcx, [rcx+18h]
0x140004bee  lea     r8, WPP_ea1b45b0a6943981c34a08d8d3c26e2c_Traceguids
0x140004bf5  mov     r9d, ebx
0x140004bf8  call    WPP_SF_d
0x140004bfd  mov     rcx, [rsp+48h+Handle]; Handle
0x140004c02  test    rcx, rcx
0x140004c05  jz      short loc_140004C13
0x140004c07  call    cs:__imp_ZwClose
0x140004c0e  nop     dword ptr [rax+rax+00h]
0x140004c13  mov     eax, ebx
0x140004c15  add     rsp, 40h
0x140004c19  pop     rbx
0x140004c1a  retn
```
