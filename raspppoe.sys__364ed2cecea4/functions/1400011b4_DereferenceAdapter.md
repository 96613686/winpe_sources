# DereferenceAdapter

- ea: `0x1400011b4`
- end: `0x14000126f`
- name: `DereferenceAdapter`
- size: `187`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400014e0`
- `0x140002794`
- `0x140002e0c`
- `0x140005b10`
- `0x140005f90`
- `0x14000e290`
- `0x14000e7b0`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400011b4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001214`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001214`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400011f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400011f9`
- `NDIS!NdisSetEvent` at `0x140001228`
- `NDIS!NdisSetEvent` at `0x140001228`

## pseudocode

```c
void __fastcall DereferenceAdapter(__int64 a1)
{
  KIRQL v2; // al
  int v3; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x10u,
      (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v3 = --*(_DWORD *)(a1 + 4);
  *(_BYTE *)(a1 + 16) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v2);
  if ( !v3 )
    NdisSetEvent((PNDIS_EVENT)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x11u,
      (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids,
      v3);
  }
}

```

## disassembly

```asm
0x1400011b4  push    rbx
0x1400011b6  push    rbp
0x1400011b7  push    rsi
0x1400011b8  push    rdi
0x1400011b9  sub     rsp, 28h
0x1400011bd  mov     rdi, rcx
0x1400011c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011c7  lea     rbp, WPP_GLOBAL_Control
0x1400011ce  cmp     rcx, rbp
0x1400011d1  jz      short loc_1400011F5
0x1400011d3  mov     eax, [rcx+2Ch]
0x1400011d6  test    al, 1
0x1400011d8  jz      short loc_1400011F5
0x1400011da  cmp     byte ptr [rcx+29h], 4
0x1400011de  jb      short loc_1400011F5
0x1400011e0  mov     rcx, [rcx+18h]
0x1400011e4  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400011eb  mov     edx, 10h
0x1400011f0  call    WPP_SF_
0x1400011f5  lea     rcx, [rdi+8]; SpinLock
0x1400011f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001200  nop     dword ptr [rax+rax+00h]
0x140001205  dec     dword ptr [rdi+4]
0x140001208  lea     rcx, [rdi+8]; SpinLock
0x14000120c  mov     esi, [rdi+4]
0x14000120f  mov     dl, al; NewIrql
0x140001211  mov     [rdi+10h], al
0x140001214  call    cs:__imp_KeReleaseSpinLock
0x14000121b  nop     dword ptr [rax+rax+00h]
0x140001220  test    esi, esi
0x140001222  jnz     short loc_140001234
0x140001224  lea     rcx, [rdi+18h]; Event
0x140001228  call    cs:__imp_NdisSetEvent
0x14000122f  nop     dword ptr [rax+rax+00h]
0x140001234  mov     rcx, cs:WPP_GLOBAL_Control
0x14000123b  cmp     rcx, rbp
0x14000123e  jz      short loc_140001265
0x140001240  mov     eax, [rcx+2Ch]
0x140001243  test    al, 1
0x140001245  jz      short loc_140001265
0x140001247  cmp     byte ptr [rcx+29h], 4
0x14000124b  jb      short loc_140001265
0x14000124d  mov     rcx, [rcx+18h]
0x140001251  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140001258  mov     edx, 11h
0x14000125d  mov     r9d, esi
0x140001260  call    WPP_SF_d
0x140001265  add     rsp, 28h
0x140001269  pop     rdi
0x14000126a  pop     rsi
0x14000126b  pop     rbp
0x14000126c  pop     rbx
0x14000126d  retn
```
