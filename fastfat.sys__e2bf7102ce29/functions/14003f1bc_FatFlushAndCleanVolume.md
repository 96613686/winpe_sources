# FatFlushAndCleanVolume

- ea: `0x14003f1bc`
- end: `0x14003f2b0`
- name: `FatFlushAndCleanVolume`
- size: `244`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x1400053ac`
- `0x14002d0d4`
- `0x1400452a0`
- `0x1400454a0`
- `0x1400455f4`

## callees

- `0x140002b30`
- `0x140006dbc`
- `0x140023cc4`
- `0x14003dae0`
- `0x14003e94c`
- `0x14003ea88`
- `0x14003f1bc`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x14003f213`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003f213`
- `ntoskrnl!KeCancelTimer` at `0x14003f242`
- `ntoskrnl!KeCancelTimer` at `0x14003f242`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003f255`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003f255`

## pseudocode

```c
char __fastcall FatFlushAndCleanVolume(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx

  if ( a4 )
    FatFlushVolume(a1, a3, a4);
  FatCloseEaFile(a1, a3, 0);
  if ( !a4 || (FatHijackIrpAndFlushDevice(v8, a2, *(_QWORD *)(a3 + 136)), a4 != 3) )
  {
    CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(a3 + 736), 0, 0, 0);
    FatPurgeReferencedFileObjects(a1, *(_QWORD *)(a3 + 208), 0);
  }
  v9 = *(_DWORD *)(a3 + 200);
  if ( (v9 & 4) != 0 )
  {
    KeCancelTimer((PKTIMER)(a3 + 952));
    LOBYTE(v9) = KeRemoveQueueDpc((PRKDPC)(a3 + 888));
    if ( a4 )
    {
      if ( (*(_DWORD *)(a3 + 200) & 0x10) == 0 )
      {
        FatMarkVolume(a1, a3, 0);
        _InterlockedAnd((volatile signed __int32 *)(a3 + 200), 0xFFFFFFFB);
      }
      v9 = *(_DWORD *)(a3 + 200);
      if ( (v9 & 2) != 0 )
      {
        v9 = *(_DWORD *)(a3 + 200);
        if ( (v9 & 0x800) == 0 )
          LOBYTE(v9) = FatToggleMediaEjectDisable(v10, a3, 0);
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14003f1bc  push    rbx
0x14003f1be  push    rbp
0x14003f1bf  push    rsi
0x14003f1c0  push    rdi
0x14003f1c1  sub     rsp, 28h
0x14003f1c5  mov     edi, r9d
0x14003f1c8  mov     rbx, r8
0x14003f1cb  mov     rbp, rdx
0x14003f1ce  mov     rsi, rcx
0x14003f1d1  test    r9d, r9d
0x14003f1d4  jz      short loc_14003F1E1
0x14003f1d6  mov     r8d, r9d
0x14003f1d9  mov     rdx, rbx
0x14003f1dc  call    FatFlushVolume
0x14003f1e1  xor     r8d, r8d
0x14003f1e4  mov     rdx, rbx
0x14003f1e7  call    FatCloseEaFile
0x14003f1ec  test    edi, edi
0x14003f1ee  jz      short loc_14003F204
0x14003f1f0  mov     r8, [rbx+88h]
0x14003f1f7  mov     rdx, rbp
0x14003f1fa  call    FatHijackIrpAndFlushDevice
0x14003f1ff  cmp     edi, 3
0x14003f202  jz      short loc_14003F231
0x14003f204  lea     rcx, [rbx+2E0h]; SectionObjectPointer
0x14003f20b  xor     r9d, r9d; Flags
0x14003f20e  xor     r8d, r8d; Length
0x14003f211  xor     edx, edx; FileOffset
0x14003f213  call    cs:__imp_CcPurgeCacheSection
0x14003f21a  nop     dword ptr [rax+rax+00h]
0x14003f21f  mov     rdx, [rbx+0D0h]
0x14003f226  xor     r8d, r8d
0x14003f229  mov     rcx, rsi
0x14003f22c  call    FatPurgeReferencedFileObjects
0x14003f231  mov     eax, [rbx+0C8h]
0x14003f237  test    al, 4
0x14003f239  jz      short loc_14003F2A6
0x14003f23b  lea     rcx, [rbx+3B8h]; PKTIMER
0x14003f242  call    cs:__imp_KeCancelTimer
0x14003f249  nop     dword ptr [rax+rax+00h]
0x14003f24e  lea     rcx, [rbx+378h]; Dpc
0x14003f255  call    cs:__imp_KeRemoveQueueDpc
0x14003f25c  nop     dword ptr [rax+rax+00h]
0x14003f261  test    edi, edi
0x14003f263  jz      short loc_14003F2A6
0x14003f265  mov     eax, [rbx+0C8h]
0x14003f26b  test    al, 10h
0x14003f26d  jnz     short loc_14003F285
0x14003f26f  xor     r8d, r8d
0x14003f272  mov     rdx, rbx
0x14003f275  mov     rcx, rsi
0x14003f278  call    FatMarkVolume
0x14003f27d  lock and dword ptr [rbx+0C8h], 0FFFFFFFBh
0x14003f285  mov     eax, [rbx+0C8h]
0x14003f28b  test    al, 2
0x14003f28d  jz      short loc_14003F2A6
0x14003f28f  mov     eax, [rbx+0C8h]
0x14003f295  bt      eax, 0Bh
0x14003f299  jb      short loc_14003F2A6
0x14003f29b  xor     r8d, r8d
0x14003f29e  mov     rdx, rbx
0x14003f2a1  call    FatToggleMediaEjectDisable
0x14003f2a6  add     rsp, 28h
0x14003f2aa  pop     rdi
0x14003f2ab  pop     rsi
0x14003f2ac  pop     rbp
0x14003f2ad  pop     rbx
0x14003f2ae  retn
```
