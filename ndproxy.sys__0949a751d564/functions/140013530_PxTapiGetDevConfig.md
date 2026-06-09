# PxTapiGetDevConfig

- ea: `0x140013530`
- end: `0x140013597`
- name: `PxTapiGetDevConfig`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140001b54`
- `0x140013530`

## pseudocode

```c
__int64 PxTapiGetDevConfig()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  }
  return 3221299222LL;
}

```

## disassembly

```asm
0x140013530  push    rbx
0x140013532  sub     rsp, 20h
0x140013536  mov     rcx, cs:WPP_GLOBAL_Control
0x14001353d  lea     rbx, WPP_GLOBAL_Control
0x140013544  cmp     rcx, rbx
0x140013547  jz      short loc_14001358B
0x140013549  cmp     byte ptr [rcx+29h], 4
0x14001354d  jb      short loc_140013564
0x14001354f  mov     rcx, [rcx+18h]
0x140013553  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14001355a  mov     edx, 4Ch ; 'L'
0x14001355f  call    WPP_SF_
0x140013564  mov     rcx, cs:WPP_GLOBAL_Control
0x14001356b  cmp     rcx, rbx
0x14001356e  jz      short loc_14001358B
0x140013570  cmp     byte ptr [rcx+29h], 4
0x140013574  jb      short loc_14001358B
0x140013576  mov     rcx, [rcx+18h]
0x14001357a  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013581  mov     edx, 4Dh ; 'M'
0x140013586  call    WPP_SF_
0x14001358b  mov     eax, 0C0012016h
0x140013590  add     rsp, 20h
0x140013594  pop     rbx
0x140013595  retn
```
