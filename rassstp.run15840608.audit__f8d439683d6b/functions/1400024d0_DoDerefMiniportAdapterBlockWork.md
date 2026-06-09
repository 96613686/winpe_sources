# DoDerefMiniportAdapterBlockWork

- ea: `0x1400024d0`
- end: `0x140002595`
- name: `DoDerefMiniportAdapterBlockWork`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400024d0`
- `0x140002bd8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002513`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002513`
- `NDIS!NdisMPauseComplete` at `0x140002523`
- `NDIS!NdisMPauseComplete` at `0x140002523`

## pseudocode

```c
void __fastcall DoDerefMiniportAdapterBlockWork(__int64 a1)
{
  KIRQL v2; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_DWORD *)(a1 + 16) = 1;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v2);
  NdisMPauseComplete(*(NDIS_HANDLE *)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
}

```

## disassembly

```asm
0x1400024d0  mov     [rsp+arg_0], rbx
0x1400024d5  mov     [rsp+arg_8], rsi
0x1400024da  push    rdi
0x1400024db  sub     rsp, 20h
0x1400024df  mov     rbx, rcx
0x1400024e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024e9  lea     rsi, WPP_GLOBAL_Control
0x1400024f0  cmp     rcx, rsi
0x1400024f3  jnz     short loc_140002558
0x1400024f5  lea     rcx, [rbx+38h]; SpinLock
0x1400024f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002500  nop     dword ptr [rax+rax+00h]
0x140002505  lea     rcx, [rbx+38h]; SpinLock
0x140002509  mov     dword ptr [rbx+10h], 1
0x140002510  movzx   edx, al; NewIrql
0x140002513  call    cs:__imp_KeReleaseSpinLock
0x14000251a  nop     dword ptr [rax+rax+00h]
0x14000251f  mov     rcx, [rbx+18h]; MiniportAdapterHandle
0x140002523  call    cs:__imp_NdisMPauseComplete
0x14000252a  nop     dword ptr [rax+rax+00h]
0x14000252f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002536  cmp     rcx, rsi
0x140002539  jz      short loc_140002547
0x14000253b  mov     eax, [rcx+2Ch]
0x14000253e  and     eax, 81h
0x140002543  cmp     al, 81h
0x140002545  jz      short loc_14000257E
0x140002547  mov     rbx, [rsp+28h+arg_0]
0x14000254c  mov     rsi, [rsp+28h+arg_8]
0x140002551  add     rsp, 20h
0x140002555  pop     rdi
0x140002556  retn
0x140002558  mov     eax, [rcx+2Ch]
0x14000255b  and     eax, 81h
0x140002560  cmp     al, 81h
0x140002562  jnz     short loc_1400024F5
0x140002564  mov     rcx, [rcx+18h]
0x140002568  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x14000256f  mov     edx, 0Ah
0x140002574  call    WPP_SF_
0x140002579  jmp     loc_1400024F5
0x14000257e  mov     rcx, [rcx+18h]
0x140002582  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x140002589  mov     edx, 0Bh
0x14000258e  call    WPP_SF_
0x140002593  jmp     short loc_140002547
```
