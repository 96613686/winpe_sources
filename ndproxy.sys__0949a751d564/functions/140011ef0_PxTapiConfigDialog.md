# PxTapiConfigDialog

- ea: `0x140011ef0`
- end: `0x140011f54`
- name: `PxTapiConfigDialog`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140001b54`
- `0x140011ef0`

## pseudocode

```c
__int64 PxTapiConfigDialog()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140011ef0  push    rbx
0x140011ef2  sub     rsp, 20h
0x140011ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x140011efd  lea     rbx, WPP_GLOBAL_Control
0x140011f04  cmp     rcx, rbx
0x140011f07  jz      short loc_140011F4B
0x140011f09  cmp     byte ptr [rcx+29h], 4
0x140011f0d  jb      short loc_140011F24
0x140011f0f  mov     rcx, [rcx+18h]
0x140011f13  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011f1a  mov     edx, 2Fh ; '/'
0x140011f1f  call    WPP_SF_
0x140011f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f2b  cmp     rcx, rbx
0x140011f2e  jz      short loc_140011F4B
0x140011f30  cmp     byte ptr [rcx+29h], 4
0x140011f34  jb      short loc_140011F4B
0x140011f36  mov     rcx, [rcx+18h]
0x140011f3a  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011f41  mov     edx, 30h ; '0'
0x140011f46  call    WPP_SF_
0x140011f4b  xor     eax, eax
0x140011f4d  add     rsp, 20h
0x140011f51  pop     rbx
0x140011f52  retn
```
