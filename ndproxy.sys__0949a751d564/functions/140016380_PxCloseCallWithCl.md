# PxCloseCallWithCl

- ea: `0x140016380`
- end: `0x140016449`
- name: `PxCloseCallWithCl`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013770`
- `0x140015290`

## callees

- `0x140007d0c`
- `0x140016380`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016420`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016420`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400163f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400163f9`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140016411`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140016411`

## pseudocode

```c
__int64 __fastcall PxCloseCallWithCl(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // esi
  KIRQL v6; // dl

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      a3,
      a1,
      *(_DWORD *)(a1 + 16),
      *(_DWORD *)(a1 + 24),
      *(_DWORD *)(a1 + 32));
  v4 = *(_DWORD *)(a1 + 24);
  if ( v4 )
  {
    v5 = 259;
    if ( v4 == 3 )
    {
      v6 = *(_BYTE *)(a1 + 520);
      *(_DWORD *)(a1 + 24) = 2;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), v6);
      NdisCmDispatchIncomingCloseCall(0, *(NDIS_HANDLE *)(a1 + 64), 0, 0);
      *(_BYTE *)(a1 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
    }
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140016380  mov     [rsp+arg_0], rbx
0x140016385  mov     [rsp+arg_8], rsi
0x14001638a  push    rdi
0x14001638b  sub     rsp, 40h
0x14001638f  mov     rdi, rcx
0x140016392  mov     rcx, cs:WPP_GLOBAL_Control
0x140016399  lea     rax, WPP_GLOBAL_Control
0x1400163a0  cmp     rcx, rax
0x1400163a3  jz      short loc_1400163D1
0x1400163a5  cmp     byte ptr [rcx+29h], 5
0x1400163a9  jb      short loc_1400163D1
0x1400163ab  mov     eax, [rdi+20h]
0x1400163ae  mov     edx, 25h ; '%'
0x1400163b3  mov     rcx, [rcx+18h]
0x1400163b7  mov     r9, rdi
0x1400163ba  mov     [rsp+48h+var_18], eax
0x1400163be  mov     eax, [rdi+18h]
0x1400163c1  mov     [rsp+48h+var_20], eax
0x1400163c5  mov     eax, [rdi+10h]
0x1400163c8  mov     [rsp+48h+var_28], eax
0x1400163cc  call    WPP_SF_qLLL
0x1400163d1  mov     eax, [rdi+18h]
0x1400163d4  test    eax, eax
0x1400163d6  jz      short loc_140016434
0x1400163d8  mov     esi, 103h
0x1400163dd  cmp     eax, 3
0x1400163e0  jnz     short loc_140016436
0x1400163e2  mov     dl, [rdi+208h]; NewIrql
0x1400163e8  lea     rbx, [rdi+200h]
0x1400163ef  mov     rcx, rbx; SpinLock
0x1400163f2  mov     dword ptr [rdi+18h], 2
0x1400163f9  call    cs:__imp_KeReleaseSpinLock
0x140016400  nop     dword ptr [rax+rax+00h]
0x140016405  mov     rdx, [rdi+40h]; NdisVcHandle
0x140016409  xor     r9d, r9d; Size
0x14001640c  xor     r8d, r8d; Buffer
0x14001640f  xor     ecx, ecx; CloseStatus
0x140016411  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x140016418  nop     dword ptr [rax+rax+00h]
0x14001641d  mov     rcx, rbx; SpinLock
0x140016420  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016427  nop     dword ptr [rax+rax+00h]
0x14001642c  mov     [rdi+208h], al
0x140016432  jmp     short loc_140016436
0x140016434  xor     esi, esi
0x140016436  mov     rbx, [rsp+48h+arg_0]
0x14001643b  mov     eax, esi
0x14001643d  mov     rsi, [rsp+48h+arg_8]
0x140016442  add     rsp, 40h
0x140016446  pop     rdi
0x140016447  retn
```
