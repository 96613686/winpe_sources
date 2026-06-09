# PxCloseCallWithCm

- ea: `0x140016450`
- end: `0x140016512`
- name: `PxCloseCallWithCm`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000fcb0`
- `0x140010240`
- `0x140013770`
- `0x140015290`

## callees

- `0x140007d0c`
- `0x14000f250`
- `0x140016450`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400164f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400164f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400164b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400164b5`
- `NDIS!NdisClCloseCall` at `0x1400164cd`
- `NDIS!NdisClCloseCall` at `0x1400164cd`

## pseudocode

```c
KIRQL __fastcall PxCloseCallWithCm(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL v4; // dl
  NDIS_STATUS v5; // eax
  KIRQL result; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      a3,
      a1,
      *(_DWORD *)(a1 + 16),
      *(_DWORD *)(a1 + 24),
      *(_DWORD *)(a1 + 32));
  v4 = *(_BYTE *)(a1 + 520);
  *(_DWORD *)(a1 + 32) &= ~8u;
  *(_DWORD *)(a1 + 36) |= 0x100u;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), v4);
  v5 = NdisClCloseCall(*(NDIS_HANDLE *)(a1 + 40), 0, 0, 0);
  if ( v5 != 259 )
    PxClCloseCallComplete(v5, *(_QWORD *)(a1 + 280));
  result = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
  *(_BYTE *)(a1 + 520) = result;
  return result;
}

```

## disassembly

```asm
0x140016450  mov     [rsp+arg_0], rbx
0x140016455  push    rdi
0x140016456  sub     rsp, 40h
0x14001645a  mov     rbx, rcx
0x14001645d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016464  lea     rax, WPP_GLOBAL_Control
0x14001646b  cmp     rcx, rax
0x14001646e  jz      short loc_14001649C
0x140016470  cmp     byte ptr [rcx+29h], 5
0x140016474  jb      short loc_14001649C
0x140016476  mov     eax, [rbx+20h]
0x140016479  mov     edx, 24h ; '$'
0x14001647e  mov     rcx, [rcx+18h]
0x140016482  mov     r9, rbx
0x140016485  mov     [rsp+48h+var_18], eax
0x140016489  mov     eax, [rbx+18h]
0x14001648c  mov     [rsp+48h+var_20], eax
0x140016490  mov     eax, [rbx+10h]
0x140016493  mov     [rsp+48h+var_28], eax
0x140016497  call    WPP_SF_qLLL
0x14001649c  mov     dl, [rbx+208h]; NewIrql
0x1400164a2  lea     rdi, [rbx+200h]
0x1400164a9  and     dword ptr [rbx+20h], 0FFFFFFF7h
0x1400164ad  mov     rcx, rdi; SpinLock
0x1400164b0  bts     dword ptr [rbx+24h], 8
0x1400164b5  call    cs:__imp_KeReleaseSpinLock
0x1400164bc  nop     dword ptr [rax+rax+00h]
0x1400164c1  mov     rcx, [rbx+28h]; NdisVcHandle
0x1400164c5  xor     r9d, r9d; Size
0x1400164c8  xor     r8d, r8d; Buffer
0x1400164cb  xor     edx, edx; NdisPartyHandle
0x1400164cd  call    cs:__imp_NdisClCloseCall
0x1400164d4  nop     dword ptr [rax+rax+00h]
0x1400164d9  cmp     eax, 103h
0x1400164de  jz      short loc_1400164F1
0x1400164e0  mov     rdx, [rbx+118h]
0x1400164e7  xor     r8d, r8d
0x1400164ea  mov     ecx, eax
0x1400164ec  call    PxClCloseCallComplete
0x1400164f1  mov     rcx, rdi; SpinLock
0x1400164f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400164fb  nop     dword ptr [rax+rax+00h]
0x140016500  mov     [rbx+208h], al
0x140016506  mov     rbx, [rsp+48h+arg_0]
0x14001650b  add     rsp, 40h
0x14001650f  pop     rdi
0x140016510  retn
```
