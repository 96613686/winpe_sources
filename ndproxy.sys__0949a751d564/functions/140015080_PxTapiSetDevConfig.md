# PxTapiSetDevConfig

- ea: `0x140015080`
- end: `0x1400150e7`
- name: `PxTapiSetDevConfig`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140001b54`
- `0x140015080`

## pseudocode

```c
__int64 PxTapiSetDevConfig()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  }
  return 3221299222LL;
}

```

## disassembly

```asm
0x140015080  push    rbx
0x140015082  sub     rsp, 20h
0x140015086  mov     rcx, cs:WPP_GLOBAL_Control
0x14001508d  lea     rbx, WPP_GLOBAL_Control
0x140015094  cmp     rcx, rbx
0x140015097  jz      short loc_1400150DB
0x140015099  cmp     byte ptr [rcx+29h], 4
0x14001509d  jb      short loc_1400150B4
0x14001509f  mov     rcx, [rcx+18h]
0x1400150a3  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400150aa  mov     edx, 65h ; 'e'
0x1400150af  call    WPP_SF_
0x1400150b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150bb  cmp     rcx, rbx
0x1400150be  jz      short loc_1400150DB
0x1400150c0  cmp     byte ptr [rcx+29h], 4
0x1400150c4  jb      short loc_1400150DB
0x1400150c6  mov     rcx, [rcx+18h]
0x1400150ca  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400150d1  mov     edx, 66h ; 'f'
0x1400150d6  call    WPP_SF_
0x1400150db  mov     eax, 0C0012016h
0x1400150e0  add     rsp, 20h
0x1400150e4  pop     rbx
0x1400150e5  retn
```
