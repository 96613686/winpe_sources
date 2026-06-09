# ReferenceAdapter

- ea: `0x1400023c0`
- end: `0x140002479`
- name: `ReferenceAdapter`
- size: `185`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140005c90`
- `0x140006420`
- `0x14000d5e0`
- `0x14000e3d8`
- `0x140014884`
- `0x140014d2c`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400023c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002430`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002430`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000240f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000240f`

## pseudocode

```c
void __fastcall ReferenceAdapter(__int64 a1, char a2)
{
  int v4; // ebp

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xEu, (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  if ( a2 )
    *(_BYTE *)(a1 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v4 = ++*(_DWORD *)(a1 + 4);
  if ( a2 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xFu,
      (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids,
      v4);
  }
}

```

## disassembly

```asm
0x1400023c0  push    rbx
0x1400023c2  push    rbp
0x1400023c3  push    rsi
0x1400023c4  push    rdi
0x1400023c5  push    r14
0x1400023c7  sub     rsp, 20h
0x1400023cb  mov     sil, dl
0x1400023ce  mov     rbx, rcx
0x1400023d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023d8  lea     r14, WPP_GLOBAL_Control
0x1400023df  cmp     rcx, r14
0x1400023e2  jz      short loc_140002406
0x1400023e4  mov     eax, [rcx+2Ch]
0x1400023e7  test    al, 1
0x1400023e9  jz      short loc_140002406
0x1400023eb  cmp     byte ptr [rcx+29h], 4
0x1400023ef  jb      short loc_140002406
0x1400023f1  mov     rcx, [rcx+18h]
0x1400023f5  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400023fc  mov     edx, 0Eh
0x140002401  call    WPP_SF_
0x140002406  test    sil, sil
0x140002409  jz      short loc_14000241E
0x14000240b  lea     rcx, [rbx+8]; SpinLock
0x14000240f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002416  nop     dword ptr [rax+rax+00h]
0x14000241b  mov     [rbx+10h], al
0x14000241e  inc     dword ptr [rbx+4]
0x140002421  mov     ebp, [rbx+4]
0x140002424  test    sil, sil
0x140002427  jz      short loc_14000243C
0x140002429  mov     dl, [rbx+10h]; NewIrql
0x14000242c  lea     rcx, [rbx+8]; SpinLock
0x140002430  call    cs:__imp_KeReleaseSpinLock
0x140002437  nop     dword ptr [rax+rax+00h]
0x14000243c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002443  cmp     rcx, r14
0x140002446  jz      short loc_14000246D
0x140002448  mov     eax, [rcx+2Ch]
0x14000244b  test    al, 1
0x14000244d  jz      short loc_14000246D
0x14000244f  cmp     byte ptr [rcx+29h], 4
0x140002453  jb      short loc_14000246D
0x140002455  mov     rcx, [rcx+18h]
0x140002459  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140002460  mov     edx, 0Fh
0x140002465  mov     r9d, ebp
0x140002468  call    WPP_SF_d
0x14000246d  add     rsp, 20h
0x140002471  pop     r14
0x140002473  pop     rdi
0x140002474  pop     rsi
0x140002475  pop     rbp
0x140002476  pop     rbx
0x140002477  retn
```
