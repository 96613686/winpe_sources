# FatSetDirtyBcb

- ea: `0x1400019b8`
- end: `0x140001b47`
- name: `FatSetDirtyBcb`
- size: `399`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x14000363c`
- `0x140003e9c`
- `0x140004554`
- `0x140020458`
- `0x140023ad4`
- `0x140024228`
- `0x1400244bc`
- `0x14002cbe4`
- `0x14003062c`
- `0x140033270`
- `0x140034054`
- `0x140034678`
- `0x1400356f0`
- `0x14003b00c`
- `0x14003b698`
- `0x14003b9d0`
- `0x1400412a8`
- `0x14004ab20`

## callees

- `0x1400019b8`
- `0x140002b30`
- `0x140006dbc`
- `0x14002475c`

## import_xrefs

- `ntoskrnl!CcSetDirtyPinnedData` at `0x1400019db`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x1400019db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a1c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001af0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a1c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001af0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a51`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a51`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b16`
- `ntoskrnl!KeCancelTimer` at `0x140001a85`
- `ntoskrnl!KeCancelTimer` at `0x140001a85`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140001a9b`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140001a9b`
- `ntoskrnl!KeSetTimer` at `0x140001b2f`
- `ntoskrnl!KeSetTimer` at `0x140001b2f`

## pseudocode

```c
void __fastcall FatSetDirtyBcb(__int64 a1, void *a2, __int64 a3, char a4)
{
  __int64 v7; // rbx
  KIRQL v8; // al
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // r8
  KIRQL v12; // al

  if ( a4 )
    FatRepinBcb(a1);
  CcSetDirtyPinnedData(a2, 0);
  if ( (*(_DWORD *)(a1 + 68) & 1) == 0 )
  {
    if ( a3 )
    {
      if ( *(_BYTE *)(a3 + 376) != 12 )
      {
        v7 = MEMORY[0xFFFFF78000000014];
        v8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
        LOBYTE(v7) = (unsigned __int64)(v7 - *(_QWORD *)(a3 + 1016)) > 0x989680;
        KeReleaseSpinLock(&SpinLock, v8);
        if ( (_BYTE)v7 )
        {
          v9 = (*(_DWORD *)(a3 + 200) & 0x1000) != 0 ? 0x3DFD240 : 0;
          KeCancelTimer((PKTIMER)(a3 + 952));
          KeRemoveQueueDpc((PRKDPC)(a3 + 888));
          if ( (*(_DWORD *)(a3 + 200) & 4) == 0 )
          {
            if ( (*(_DWORD *)(a3 + 200) & 0x10) == 0 )
              FatMarkVolume(a1, a3, 1);
            _InterlockedOr((volatile signed __int32 *)(a3 + 200), 4u);
            if ( (*(_DWORD *)(a3 + 200) & 2) != 0 )
            {
              LOBYTE(v11) = 1;
              FatToggleMediaEjectDisable(v10, a3, v11);
            }
          }
          v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
          *(_QWORD *)(a3 + 1016) = MEMORY[0xFFFFF78000000014];
          KeReleaseSpinLock(&SpinLock, v12);
          KeSetTimer((PKTIMER)(a3 + 952), (LARGE_INTEGER)(v9 - 80000000), (PKDPC)(a3 + 888));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400019b8  push    rbx
0x1400019ba  push    rbp
0x1400019bb  push    rsi
0x1400019bc  push    rdi
0x1400019bd  push    r14
0x1400019bf  sub     rsp, 20h
0x1400019c3  mov     rdi, r8
0x1400019c6  mov     rbx, rdx
0x1400019c9  mov     rsi, rcx
0x1400019cc  test    r9b, r9b
0x1400019cf  jz      short loc_1400019D6
0x1400019d1  call    FatRepinBcb
0x1400019d6  xor     edx, edx; Lsn
0x1400019d8  mov     rcx, rbx; BcbVoid
0x1400019db  call    cs:__imp_CcSetDirtyPinnedData
0x1400019e2  nop     dword ptr [rax+rax+00h]
0x1400019e7  mov     eax, [rsi+44h]
0x1400019ea  test    al, 1
0x1400019ec  jnz     loc_140001B3B
0x1400019f2  test    rdi, rdi
0x1400019f5  jz      loc_140001B3B
0x1400019fb  cmp     byte ptr [rdi+178h], 0Ch
0x140001a02  jz      loc_140001B3B
0x140001a08  mov     rbx, 0FFFFF78000000014h
0x140001a12  lea     rcx, SpinLock; SpinLock
0x140001a19  mov     rbx, [rbx]
0x140001a1c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001a23  nop     dword ptr [rax+rax+00h]
0x140001a28  sub     rbx, [rdi+3F8h]
0x140001a2f  mov     rcx, rbx
0x140001a32  shr     rcx, 20h
0x140001a36  test    ecx, ecx
0x140001a38  jnz     short loc_140001A46
0x140001a3a  cmp     ebx, 989680h
0x140001a40  ja      short loc_140001A46
0x140001a42  xor     bl, bl
0x140001a44  jmp     short loc_140001A48
0x140001a46  mov     bl, 1
0x140001a48  mov     dl, al; NewIrql
0x140001a4a  lea     rcx, SpinLock; SpinLock
0x140001a51  call    cs:__imp_KeReleaseSpinLock
0x140001a58  nop     dword ptr [rax+rax+00h]
0x140001a5d  test    bl, bl
0x140001a5f  jz      loc_140001B3B
0x140001a65  mov     eax, [rdi+0C8h]
0x140001a6b  lea     rbp, [rdi+3B8h]
0x140001a72  and     eax, 1000h
0x140001a77  mov     rcx, rbp; PKTIMER
0x140001a7a  neg     eax
0x140001a7c  sbb     rbx, rbx
0x140001a7f  and     ebx, 3DFD240h
0x140001a85  call    cs:__imp_KeCancelTimer
0x140001a8c  nop     dword ptr [rax+rax+00h]
0x140001a91  lea     r14, [rdi+378h]
0x140001a98  mov     rcx, r14; Dpc
0x140001a9b  call    cs:__imp_KeRemoveQueueDpc
0x140001aa2  nop     dword ptr [rax+rax+00h]
0x140001aa7  mov     eax, [rdi+0C8h]
0x140001aad  test    al, 4
0x140001aaf  jnz     short loc_140001AE9
0x140001ab1  mov     eax, [rdi+0C8h]
0x140001ab7  test    al, 10h
0x140001ab9  jnz     short loc_140001ACC
0x140001abb  mov     r8d, 1
0x140001ac1  mov     rdx, rdi
0x140001ac4  mov     rcx, rsi
0x140001ac7  call    FatMarkVolume
0x140001acc  lock or dword ptr [rdi+0C8h], 4
0x140001ad4  mov     eax, [rdi+0C8h]
0x140001ada  test    al, 2
0x140001adc  jz      short loc_140001AE9
0x140001ade  mov     r8b, 1
0x140001ae1  mov     rdx, rdi
0x140001ae4  call    FatToggleMediaEjectDisable
0x140001ae9  lea     rcx, SpinLock; SpinLock
0x140001af0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001af7  nop     dword ptr [rax+rax+00h]
0x140001afc  mov     dl, al; NewIrql
0x140001afe  lea     rcx, SpinLock; SpinLock
0x140001b05  mov     rax, ds:0FFFFF78000000014h
0x140001b0f  mov     [rdi+3F8h], rax
0x140001b16  call    cs:__imp_KeReleaseSpinLock
0x140001b1d  nop     dword ptr [rax+rax+00h]
0x140001b22  mov     r8, r14; Dpc
0x140001b25  lea     rdx, [rbx-4C4B400h]; DueTime
0x140001b2c  mov     rcx, rbp; Timer
0x140001b2f  call    cs:__imp_KeSetTimer
0x140001b36  nop     dword ptr [rax+rax+00h]
0x140001b3b  add     rsp, 20h
0x140001b3f  pop     r14
0x140001b41  pop     rdi
0x140001b42  pop     rsi
0x140001b43  pop     rbp
0x140001b44  pop     rbx
0x140001b45  retn
```
