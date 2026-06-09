# PxTapiGetExtensionID

- ea: `0x1400135a0`
- end: `0x140013607`
- name: `PxTapiGetExtensionID`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140001b54`
- `0x1400135a0`

## pseudocode

```c
__int64 PxTapiGetExtensionID()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  }
  return 3221299222LL;
}

```

## disassembly

```asm
0x1400135a0  push    rbx
0x1400135a2  sub     rsp, 20h
0x1400135a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135ad  lea     rbx, WPP_GLOBAL_Control
0x1400135b4  cmp     rcx, rbx
0x1400135b7  jz      short loc_1400135FB
0x1400135b9  cmp     byte ptr [rcx+29h], 4
0x1400135bd  jb      short loc_1400135D4
0x1400135bf  mov     rcx, [rcx+18h]
0x1400135c3  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400135ca  mov     edx, 4Eh ; 'N'
0x1400135cf  call    WPP_SF_
0x1400135d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135db  cmp     rcx, rbx
0x1400135de  jz      short loc_1400135FB
0x1400135e0  cmp     byte ptr [rcx+29h], 4
0x1400135e4  jb      short loc_1400135FB
0x1400135e6  mov     rcx, [rcx+18h]
0x1400135ea  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400135f1  mov     edx, 4Fh ; 'O'
0x1400135f6  call    WPP_SF_
0x1400135fb  mov     eax, 0C0012016h
0x140013600  add     rsp, 20h
0x140013604  pop     rbx
0x140013605  retn
```
