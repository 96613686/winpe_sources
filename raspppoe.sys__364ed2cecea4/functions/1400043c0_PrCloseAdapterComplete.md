# PrCloseAdapterComplete

- ea: `0x1400043c0`
- end: `0x140004453`
- name: `PrCloseAdapterComplete`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e958`

## callees

- `0x14000110c`
- `0x1400043c0`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x14000440d`
- `NDIS!NdisSetEvent` at `0x14000440d`

## pseudocode

```c
void __fastcall PrCloseAdapterComplete(__int64 a1)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  *(_DWORD *)(a1 + 24) |= 0x20u;
  NdisSetEvent((PNDIS_EVENT)(a1 + 296));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x1400043c0  mov     [rsp+arg_0], rbx
0x1400043c5  push    rdi
0x1400043c6  sub     rsp, 20h
0x1400043ca  mov     rbx, rcx
0x1400043cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043d4  lea     rdi, WPP_GLOBAL_Control
0x1400043db  cmp     rcx, rdi
0x1400043de  jz      short loc_140004402
0x1400043e0  mov     eax, [rcx+2Ch]
0x1400043e3  test    al, 4
0x1400043e5  jz      short loc_140004402
0x1400043e7  cmp     byte ptr [rcx+29h], 2
0x1400043eb  jb      short loc_140004402
0x1400043ed  mov     rcx, [rcx+18h]
0x1400043f1  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x1400043f8  mov     edx, 43h ; 'C'
0x1400043fd  call    WPP_SF_
0x140004402  or      dword ptr [rbx+18h], 20h
0x140004406  lea     rcx, [rbx+128h]; Event
0x14000440d  call    cs:__imp_NdisSetEvent
0x140004414  nop     dword ptr [rax+rax+00h]
0x140004419  mov     rcx, cs:WPP_GLOBAL_Control
0x140004420  cmp     rcx, rdi
0x140004423  jz      short loc_140004447
0x140004425  mov     eax, [rcx+2Ch]
0x140004428  test    al, 4
0x14000442a  jz      short loc_140004447
0x14000442c  cmp     byte ptr [rcx+29h], 2
0x140004430  jb      short loc_140004447
0x140004432  mov     rcx, [rcx+18h]
0x140004436  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000443d  mov     edx, 44h ; 'D'
0x140004442  call    WPP_SF_
0x140004447  mov     rbx, [rsp+28h+arg_0]
0x14000444c  add     rsp, 20h
0x140004450  pop     rdi
0x140004451  retn
```
