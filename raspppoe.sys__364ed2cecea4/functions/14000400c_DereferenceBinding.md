# DereferenceBinding

- ea: `0x14000400c`
- end: `0x1400040d4`
- name: `DereferenceBinding`
- size: `200`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140004e10`
- `0x14000e290`
- `0x140014e68`
- `0x140015aec`
- `0x140015bb0`
- `0x140015cf0`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x14000400c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004075`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004075`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004058`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004058`
- `NDIS!NdisSetEvent` at `0x14000408c`
- `NDIS!NdisSetEvent` at `0x14000408c`

## pseudocode

```c
void __fastcall DereferenceBinding(__int64 a1)
{
  KIRQL v2; // al
  int v3; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x15u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 384));
  v3 = --*(_DWORD *)(a1 + 20);
  *(_BYTE *)(a1 + 392) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 384), v2);
  if ( !v3 )
    NdisSetEvent((PNDIS_EVENT)(a1 + 360));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x16u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids,
      v3);
  }
}

```

## disassembly

```asm
0x14000400c  push    rbx
0x14000400e  push    rsi
0x14000400f  push    rdi
0x140004010  push    r14
0x140004012  sub     rsp, 28h
0x140004016  mov     rdi, rcx
0x140004019  mov     rcx, cs:WPP_GLOBAL_Control
0x140004020  lea     r14, WPP_GLOBAL_Control
0x140004027  cmp     rcx, r14
0x14000402a  jz      short loc_14000404E
0x14000402c  mov     eax, [rcx+2Ch]
0x14000402f  test    al, 4
0x140004031  jz      short loc_14000404E
0x140004033  cmp     byte ptr [rcx+29h], 4
0x140004037  jb      short loc_14000404E
0x140004039  mov     rcx, [rcx+18h]
0x14000403d  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140004044  mov     edx, 15h
0x140004049  call    WPP_SF_
0x14000404e  lea     rbx, [rdi+180h]
0x140004055  mov     rcx, rbx; SpinLock
0x140004058  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000405f  nop     dword ptr [rax+rax+00h]
0x140004064  dec     dword ptr [rdi+14h]
0x140004067  mov     rcx, rbx; SpinLock
0x14000406a  mov     esi, [rdi+14h]
0x14000406d  mov     dl, al; NewIrql
0x14000406f  mov     [rdi+188h], al
0x140004075  call    cs:__imp_KeReleaseSpinLock
0x14000407c  nop     dword ptr [rax+rax+00h]
0x140004081  test    esi, esi
0x140004083  jnz     short loc_140004098
0x140004085  lea     rcx, [rdi+168h]; Event
0x14000408c  call    cs:__imp_NdisSetEvent
0x140004093  nop     dword ptr [rax+rax+00h]
0x140004098  mov     rcx, cs:WPP_GLOBAL_Control
0x14000409f  cmp     rcx, r14
0x1400040a2  jz      short loc_1400040C9
0x1400040a4  mov     eax, [rcx+2Ch]
0x1400040a7  test    al, 4
0x1400040a9  jz      short loc_1400040C9
0x1400040ab  cmp     byte ptr [rcx+29h], 4
0x1400040af  jb      short loc_1400040C9
0x1400040b1  mov     rcx, [rcx+18h]
0x1400040b5  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x1400040bc  mov     edx, 16h
0x1400040c1  mov     r9d, esi
0x1400040c4  call    WPP_SF_d
0x1400040c9  add     rsp, 28h
0x1400040cd  pop     r14
0x1400040cf  pop     rdi
0x1400040d0  pop     rsi
0x1400040d1  pop     rbx
0x1400040d2  retn
```
