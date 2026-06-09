# DoDerefMiniportAdapterBlockWork

- ea: `0x140001280`
- end: `0x140001342`
- name: `DoDerefMiniportAdapterBlockWork`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000110c`
- `0x140001280`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400012e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400012e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400012cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400012cb`
- `NDIS!NdisMPauseComplete` at `0x1400012f7`
- `NDIS!NdisMPauseComplete` at `0x1400012f7`

## pseudocode

```c
void __fastcall DoDerefMiniportAdapterBlockWork(__int64 a1)
{
  KIRQL v2; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 - 40));
  *(_DWORD *)(a1 + 16) = 1;
  *(_BYTE *)(a1 - 32) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 - 40), v2);
  NdisMPauseComplete(*(NDIS_HANDLE *)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
}

```

## disassembly

```asm
0x140001280  mov     [rsp+arg_0], rbx
0x140001285  mov     [rsp+arg_8], rsi
0x14000128a  push    rdi
0x14000128b  sub     rsp, 20h
0x14000128f  mov     rdi, rcx
0x140001292  mov     rcx, cs:WPP_GLOBAL_Control
0x140001299  lea     rsi, WPP_GLOBAL_Control
0x1400012a0  cmp     rcx, rsi
0x1400012a3  jz      short loc_1400012C7
0x1400012a5  mov     eax, [rcx+2Ch]
0x1400012a8  test    al, 1
0x1400012aa  jz      short loc_1400012C7
0x1400012ac  cmp     byte ptr [rcx+29h], 4
0x1400012b0  jb      short loc_1400012C7
0x1400012b2  mov     rcx, [rcx+18h]
0x1400012b6  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400012bd  mov     edx, 0Ah
0x1400012c2  call    WPP_SF_
0x1400012c7  lea     rcx, [rdi-28h]; SpinLock
0x1400012cb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400012d2  nop     dword ptr [rax+rax+00h]
0x1400012d7  lea     rcx, [rdi-28h]; SpinLock
0x1400012db  mov     dword ptr [rdi+10h], 1
0x1400012e2  mov     dl, al; NewIrql
0x1400012e4  mov     [rdi-20h], al
0x1400012e7  call    cs:__imp_KeReleaseSpinLock
0x1400012ee  nop     dword ptr [rax+rax+00h]
0x1400012f3  mov     rcx, [rdi+18h]; MiniportAdapterHandle
0x1400012f7  call    cs:__imp_NdisMPauseComplete
0x1400012fe  nop     dword ptr [rax+rax+00h]
0x140001303  mov     rcx, cs:WPP_GLOBAL_Control
0x14000130a  cmp     rcx, rsi
0x14000130d  jz      short loc_140001331
0x14000130f  mov     eax, [rcx+2Ch]
0x140001312  test    al, 1
0x140001314  jz      short loc_140001331
0x140001316  cmp     byte ptr [rcx+29h], 4
0x14000131a  jb      short loc_140001331
0x14000131c  mov     rcx, [rcx+18h]
0x140001320  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140001327  mov     edx, 0Bh
0x14000132c  call    WPP_SF_
0x140001331  mov     rbx, [rsp+28h+arg_0]
0x140001336  mov     rsi, [rsp+28h+arg_8]
0x14000133b  add     rsp, 20h
0x14000133f  pop     rdi
0x140001340  retn
```
