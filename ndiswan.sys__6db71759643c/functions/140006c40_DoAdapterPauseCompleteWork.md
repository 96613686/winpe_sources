# DoAdapterPauseCompleteWork

- ea: `0x140006c40`
- end: `0x140006cd4`
- name: `DoAdapterPauseCompleteWork`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006c40`
- `0x14000a290`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140006c8f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006c71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006c71`
- `NDIS!NdisMPauseComplete` at `0x140006c9f`
- `NDIS!NdisMPauseComplete` at `0x140006c9f`

## pseudocode

```c
void __fastcall DoAdapterPauseCompleteWork(__int64 a1)
{
  KIRQL v2; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 136));
  *(_DWORD *)(a1 - 4) = 2;
  *(_BYTE *)(a1 + 144) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 136), v2);
  NdisMPauseComplete(*(NDIS_HANDLE *)(a1 + 16));
}

```

## disassembly

```asm
0x140006c40  mov     [rsp+arg_0], rbx
0x140006c45  push    rdi
0x140006c46  sub     rsp, 20h
0x140006c4a  mov     rdi, rcx
0x140006c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c54  lea     rax, WPP_GLOBAL_Control
0x140006c5b  cmp     rcx, rax
0x140006c5e  jz      short loc_140006C67
0x140006c60  mov     eax, [rcx+2Ch]
0x140006c63  test    al, 2
0x140006c65  jnz     short loc_140006CB7
0x140006c67  lea     rbx, [rdi+88h]
0x140006c6e  mov     rcx, rbx; SpinLock
0x140006c71  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006c78  nop     dword ptr [rax+rax+00h]
0x140006c7d  mov     rcx, rbx; SpinLock
0x140006c80  mov     dword ptr [rdi-4], 2
0x140006c87  mov     dl, al; NewIrql
0x140006c89  mov     [rdi+90h], al
0x140006c8f  call    cs:__imp_KeReleaseSpinLock
0x140006c96  nop     dword ptr [rax+rax+00h]
0x140006c9b  mov     rcx, [rdi+10h]; MiniportAdapterHandle
0x140006c9f  call    cs:__imp_NdisMPauseComplete
0x140006ca6  nop     dword ptr [rax+rax+00h]
0x140006cab  mov     rbx, [rsp+28h+arg_0]
0x140006cb0  add     rsp, 20h
0x140006cb4  pop     rdi
0x140006cb5  retn
0x140006cb7  cmp     byte ptr [rcx+29h], 5
0x140006cbb  jb      short loc_140006C67
0x140006cbd  mov     rcx, [rcx+18h]
0x140006cc1  lea     r8, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x140006cc8  mov     edx, 0Ah
0x140006ccd  call    WPP_SF_
0x140006cd2  jmp     short loc_140006C67
```
