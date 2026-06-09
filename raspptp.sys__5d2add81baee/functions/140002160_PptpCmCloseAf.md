# PptpCmCloseAf

- ea: `0x140002160`
- end: `0x14000230f`
- name: `PptpCmCloseAf`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002160`
- `0x140003e08`
- `0x140003e38`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x1400022cf`
- `NDIS!NdisSetEvent` at `0x1400022cf`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x1400021d8`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x1400021d8`

## pseudocode

```c
__int64 __fastcall PptpCmCloseAf(__int64 a1)
{
  unsigned __int32 v2; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 160));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, v2);
  }
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    NdisCmCloseAddressFamilyComplete(0, *(NDIS_HANDLE *)(a1 + 152));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    _InterlockedExchange64((volatile __int64 *)(a1 + 152), 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
      NdisSetEvent((PNDIS_EVENT)(a1 + 168));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  return 259;
}

```

## disassembly

```asm
0x140002160  push    rbx
0x140002162  push    rbp
0x140002163  push    rsi
0x140002164  push    rdi
0x140002165  sub     rsp, 28h
0x140002169  mov     rbx, rcx
0x14000216c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002173  lea     rbp, WPP_GLOBAL_Control
0x14000217a  cmp     rcx, rbp
0x14000217d  jz      short loc_14000218A
0x14000217f  mov     eax, [rcx+2Ch]
0x140002182  test    al, 4
0x140002184  jnz     loc_14000222A
0x14000218a  mov     edi, 0FFFFFFFFh
0x14000218f  mov     esi, edi
0x140002191  lock xadd [rbx+0A0h], esi
0x140002199  dec     esi
0x14000219b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021a2  cmp     rcx, rbp
0x1400021a5  jz      short loc_1400021B4
0x1400021a7  test    dword ptr [rcx+2Ch], 400h
0x1400021ae  jnz     loc_14000224E
0x1400021b4  test    esi, esi
0x1400021b6  jnz     short loc_14000220B
0x1400021b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021bf  cmp     rcx, rbp
0x1400021c2  jz      short loc_1400021CF
0x1400021c4  mov     eax, [rcx+2Ch]
0x1400021c7  test    al, 4
0x1400021c9  jnz     loc_140002275
0x1400021cf  mov     rdx, [rbx+98h]; NdisAfHandle
0x1400021d6  xor     ecx, ecx; Status
0x1400021d8  call    cs:__imp_NdisCmCloseAddressFamilyComplete
0x1400021df  nop     dword ptr [rax+rax+00h]
0x1400021e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021eb  cmp     rcx, rbp
0x1400021ee  jnz     loc_140002299
0x1400021f4  xor     eax, eax
0x1400021f6  xchg    rax, [rbx+98h]
0x1400021fd  lock xadd [rbx+18h], edi
0x140002202  cmp     edi, 1
0x140002205  jz      loc_1400022C8
0x14000220b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002212  cmp     rcx, rbp
0x140002215  jnz     loc_1400022E0
0x14000221b  mov     eax, 103h
0x140002220  add     rsp, 28h
0x140002224  pop     rdi
0x140002225  pop     rsi
0x140002226  pop     rbp
0x140002227  pop     rbx
0x140002228  retn
0x14000222a  cmp     byte ptr [rcx+29h], 2
0x14000222e  jb      loc_14000218A
0x140002234  mov     rcx, [rcx+18h]
0x140002238  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x14000223f  mov     edx, 13h
0x140002244  call    WPP_SF_
0x140002249  jmp     loc_14000218A
0x14000224e  cmp     byte ptr [rcx+29h], 2
0x140002252  jb      loc_1400021B4
0x140002258  mov     rcx, [rcx+18h]
0x14000225c  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002263  mov     edx, 0Bh
0x140002268  mov     r9d, esi
0x14000226b  call    WPP_SF_d
0x140002270  jmp     loc_1400021B4
0x140002275  cmp     byte ptr [rcx+29h], 2
0x140002279  jb      loc_1400021CF
0x14000227f  mov     rcx, [rcx+18h]
0x140002283  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x14000228a  mov     edx, 0Ch
0x14000228f  call    WPP_SF_
0x140002294  jmp     loc_1400021CF
0x140002299  mov     eax, [rcx+2Ch]
0x14000229c  test    al, 4
0x14000229e  jz      loc_1400021F4
0x1400022a4  cmp     byte ptr [rcx+29h], 2
0x1400022a8  jb      loc_1400021F4
0x1400022ae  mov     rcx, [rcx+18h]
0x1400022b2  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400022b9  mov     edx, 0Dh
0x1400022be  call    WPP_SF_
0x1400022c3  jmp     loc_1400021F4
0x1400022c8  lea     rcx, [rbx+0A8h]; Event
0x1400022cf  call    cs:__imp_NdisSetEvent
0x1400022d6  nop     dword ptr [rax+rax+00h]
0x1400022db  jmp     loc_14000220B
0x1400022e0  mov     eax, [rcx+2Ch]
0x1400022e3  test    al, 4
0x1400022e5  jz      loc_14000221B
0x1400022eb  cmp     byte ptr [rcx+29h], 2
0x1400022ef  jb      loc_14000221B
0x1400022f5  mov     rcx, [rcx+18h]
0x1400022f9  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002300  mov     edx, 14h
0x140002305  call    WPP_SF_
0x14000230a  jmp     loc_14000221B
```
