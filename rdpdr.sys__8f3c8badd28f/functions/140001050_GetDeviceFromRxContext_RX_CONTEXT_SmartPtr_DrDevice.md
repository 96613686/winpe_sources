# GetDeviceFromRxContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)

- ea: `0x140001050`
- end: `0x1400010f3`
- name: `?GetDeviceFromRxContext@@YAHPEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140016fb0`
- `0x140017040`
- `0x1400170d0`
- `0x140017190`
- `0x140017220`
- `0x1400172d0`
- `0x1400173c0`
- `0x140017450`
- `0x140017bf0`
- `0x140017f90`
- `0x140026380`
- `0x140029f80`
- `0x14002c310`

## callees

- `0x140001050`
- `0x140001660`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000107e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000107e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010b0`

## pseudocode

```c
_BOOL8 __fastcall GetDeviceFromRxContext(__int64 a1, RefCount **a2)
{
  __int64 v2; // rax
  __int64 v4; // rbx
  KIRQL v5; // si
  volatile signed __int32 *v6; // rbx

  v2 = *(_QWORD *)(a1 + 72);
  if ( !v2 )
    return 0;
  v4 = *(_QWORD *)(v2 + 40);
  if ( !v4 )
    return 0;
  v5 = KeAcquireSpinLockRaiseToDpc(&DrSpinLock);
  v6 = *(volatile signed __int32 **)(v4 + 40);
  if ( *a2 )
    RefCount::Release(*a2);
  *a2 = (RefCount *)v6;
  if ( v6 )
    _InterlockedIncrement(v6 + 4);
  KeReleaseSpinLock(&DrSpinLock, v5);
  return *a2 != 0;
}

```

## disassembly

```asm
0x140001050  push    rdi
0x140001052  sub     rsp, 20h
0x140001056  mov     rax, [rcx+48h]
0x14000105a  mov     rdi, rdx
0x14000105d  xor     edx, edx
0x14000105f  test    rax, rax
0x140001062  jz      short loc_1400010D5
0x140001064  mov     [rsp+28h+arg_0], rbx
0x140001069  mov     rbx, [rax+28h]
0x14000106d  test    rbx, rbx
0x140001070  jz      short loc_1400010DE
0x140001072  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x140001079  mov     [rsp+28h+arg_8], rsi
0x14000107e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001085  nop     dword ptr [rax+rax+00h]
0x14000108a  mov     rcx, [rdi]; this
0x14000108d  movzx   esi, al
0x140001090  mov     rbx, [rbx+28h]
0x140001094  test    rcx, rcx
0x140001097  jnz     short loc_1400010EC
0x140001099  mov     [rdi], rbx
0x14000109c  test    rbx, rbx
0x14000109f  jz      short loc_1400010A5
0x1400010a1  lock inc dword ptr [rbx+10h]
0x1400010a5  movzx   edx, sil; NewIrql
0x1400010a9  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x1400010b0  call    cs:__imp_KeReleaseSpinLock
0x1400010b7  nop     dword ptr [rax+rax+00h]
0x1400010bc  mov     rsi, [rsp+28h+arg_8]
0x1400010c1  xor     eax, eax
0x1400010c3  cmp     [rdi], rax
0x1400010c6  mov     rbx, [rsp+28h+arg_0]
0x1400010cb  setnz   al
0x1400010ce  add     rsp, 20h
0x1400010d2  pop     rdi
0x1400010d3  retn
0x1400010d5  mov     eax, edx
0x1400010d7  add     rsp, 20h
0x1400010db  pop     rdi
0x1400010dc  retn
0x1400010de  mov     rbx, [rsp+28h+arg_0]
0x1400010e3  mov     eax, edx
0x1400010e5  add     rsp, 20h
0x1400010e9  pop     rdi
0x1400010ea  retn
0x1400010ec  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400010f1  jmp     short loc_140001099
```
