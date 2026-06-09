# DereferenceAf

- ea: `0x140002320`
- end: `0x140002424`
- name: `DereferenceAf`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005d00`

## callees

- `0x140002320`
- `0x140003e08`
- `0x140003e38`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x140002416`
- `NDIS!NdisSetEvent` at `0x140002416`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x140002379`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x140002379`

## pseudocode

```c
void __fastcall DereferenceAf(__int64 a1)
{
  unsigned __int32 v2; // esi

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
}

```

## disassembly

```asm
0x140002320  push    rbx
0x140002322  push    rbp
0x140002323  push    rsi
0x140002324  push    rdi
0x140002325  sub     rsp, 28h
0x140002329  mov     edi, 0FFFFFFFFh
0x14000232e  mov     rbx, rcx
0x140002331  mov     esi, edi
0x140002333  lock xadd [rcx+0A0h], esi
0x14000233b  dec     esi
0x14000233d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002344  lea     rbp, WPP_GLOBAL_Control
0x14000234b  cmp     rcx, rbp
0x14000234e  jz      short loc_140002359
0x140002350  test    dword ptr [rcx+2Ch], 400h
0x140002357  jnz     short loc_1400023AE
0x140002359  test    esi, esi
0x14000235b  jnz     short loc_1400023A4
0x14000235d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002364  cmp     rcx, rbp
0x140002367  jz      short loc_140002370
0x140002369  mov     eax, [rcx+2Ch]
0x14000236c  test    al, 4
0x14000236e  jnz     short loc_1400023CE
0x140002370  mov     rdx, [rbx+98h]; NdisAfHandle
0x140002377  xor     ecx, ecx; Status
0x140002379  call    cs:__imp_NdisCmCloseAddressFamilyComplete
0x140002380  nop     dword ptr [rax+rax+00h]
0x140002385  mov     rcx, cs:WPP_GLOBAL_Control
0x14000238c  cmp     rcx, rbp
0x14000238f  jnz     short loc_1400023EB
0x140002391  xor     eax, eax
0x140002393  xchg    rax, [rbx+98h]
0x14000239a  lock xadd [rbx+18h], edi
0x14000239f  cmp     edi, 1
0x1400023a2  jz      short loc_14000240F
0x1400023a4  add     rsp, 28h
0x1400023a8  pop     rdi
0x1400023a9  pop     rsi
0x1400023aa  pop     rbp
0x1400023ab  pop     rbx
0x1400023ac  retn
0x1400023ae  cmp     byte ptr [rcx+29h], 2
0x1400023b2  jb      short loc_140002359
0x1400023b4  mov     rcx, [rcx+18h]
0x1400023b8  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400023bf  mov     edx, 0Bh
0x1400023c4  mov     r9d, esi
0x1400023c7  call    WPP_SF_d
0x1400023cc  jmp     short loc_140002359
0x1400023ce  cmp     byte ptr [rcx+29h], 2
0x1400023d2  jb      short loc_140002370
0x1400023d4  mov     rcx, [rcx+18h]
0x1400023d8  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400023df  mov     edx, 0Ch
0x1400023e4  call    WPP_SF_
0x1400023e9  jmp     short loc_140002370
0x1400023eb  mov     eax, [rcx+2Ch]
0x1400023ee  test    al, 4
0x1400023f0  jz      short loc_140002391
0x1400023f2  cmp     byte ptr [rcx+29h], 2
0x1400023f6  jb      short loc_140002391
0x1400023f8  mov     rcx, [rcx+18h]
0x1400023fc  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002403  mov     edx, 0Dh
0x140002408  call    WPP_SF_
0x14000240d  jmp     short loc_140002391
0x14000240f  lea     rcx, [rbx+0A8h]; Event
0x140002416  call    cs:__imp_NdisSetEvent
0x14000241d  nop     dword ptr [rax+rax+00h]
0x140002422  jmp     short loc_1400023A4
```
