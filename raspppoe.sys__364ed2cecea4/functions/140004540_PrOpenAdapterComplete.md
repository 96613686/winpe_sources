# PrOpenAdapterComplete

- ea: `0x140004540`
- end: `0x140004615`
- name: `PrOpenAdapterComplete`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ead8`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140004540`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x1400045c9`
- `NDIS!NdisSetEvent` at `0x1400045c9`

## pseudocode

```c
void __fastcall PrOpenAdapterComplete(__int64 a1, unsigned int a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a2);
    }
  }
  *(_DWORD *)(a1 + 24) |= 1u;
  *(_DWORD *)(a1 + 32) = a2;
  NdisSetEvent((PNDIS_EVENT)(a1 + 296));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x140004540  mov     [rsp+arg_0], rbx
0x140004545  mov     [rsp+arg_8], rdi
0x14000454a  push    r14
0x14000454c  sub     rsp, 20h
0x140004550  mov     edi, edx
0x140004552  mov     rbx, rcx
0x140004555  mov     rcx, cs:WPP_GLOBAL_Control
0x14000455c  lea     r14, WPP_GLOBAL_Control
0x140004563  cmp     rcx, r14
0x140004566  jz      short loc_1400045BB
0x140004568  mov     eax, [rcx+2Ch]
0x14000456b  test    al, 4
0x14000456d  jz      short loc_14000458A
0x14000456f  cmp     byte ptr [rcx+29h], 2
0x140004573  jb      short loc_14000458A
0x140004575  mov     rcx, [rcx+18h]
0x140004579  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140004580  mov     edx, 27h ; '''
0x140004585  call    WPP_SF_
0x14000458a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004591  cmp     rcx, r14
0x140004594  jz      short loc_1400045BB
0x140004596  mov     eax, [rcx+2Ch]
0x140004599  test    al, 4
0x14000459b  jz      short loc_1400045BB
0x14000459d  cmp     byte ptr [rcx+29h], 3
0x1400045a1  jb      short loc_1400045BB
0x1400045a3  mov     rcx, [rcx+18h]
0x1400045a7  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x1400045ae  mov     edx, 28h ; '('
0x1400045b3  mov     r9d, edi
0x1400045b6  call    WPP_SF_d
0x1400045bb  or      dword ptr [rbx+18h], 1
0x1400045bf  lea     rcx, [rbx+128h]; Event
0x1400045c6  mov     [rbx+20h], edi
0x1400045c9  call    cs:__imp_NdisSetEvent
0x1400045d0  nop     dword ptr [rax+rax+00h]
0x1400045d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045dc  cmp     rcx, r14
0x1400045df  jz      short loc_140004603
0x1400045e1  mov     eax, [rcx+2Ch]
0x1400045e4  test    al, 4
0x1400045e6  jz      short loc_140004603
0x1400045e8  cmp     byte ptr [rcx+29h], 2
0x1400045ec  jb      short loc_140004603
0x1400045ee  mov     rcx, [rcx+18h]
0x1400045f2  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x1400045f9  mov     edx, 29h ; ')'
0x1400045fe  call    WPP_SF_
0x140004603  mov     rbx, [rsp+28h+arg_0]
0x140004608  mov     rdi, [rsp+28h+arg_8]
0x14000460d  add     rsp, 20h
0x140004611  pop     r14
0x140004613  retn
```
