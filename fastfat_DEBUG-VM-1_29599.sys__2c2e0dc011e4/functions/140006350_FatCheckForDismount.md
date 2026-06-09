# FatCheckForDismount

- ea: `0x140006350`
- end: `0x1400064b1`
- name: `FatCheckForDismount`
- size: `353`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x140005604`
- `0x140024bd4`
- `0x140025bb8`
- `0x140040674`
- `0x140042740`
- `0x1400452a0`
- `0x1400454a0`
- `0x1400455f4`
- `0x140046cb0`
- `0x140049d44`

## callees

- `0x140006350`
- `0x1400065d0`
- `0x140026390`
- `0x140048424`
- `0x140048fd0`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x14000638d`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140006400`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x14000638d`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140006400`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400063d4`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x14000642e`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140006461`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x14000648e`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400063d4`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x14000642e`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140006461`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x14000648e`
- `ntoskrnl!IoDeleteDevice` at `0x14000644c`
- `ntoskrnl!IoDeleteDevice` at `0x14000644c`

## pseudocode

```c
char __fastcall FatCheckForDismount(__int64 a1, __int64 a2, char a3)
{
  bool v3; // zf
  char v8; // r14
  __int64 v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  KIRQL Irql; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a2 + 204) == 1;
  Irql = 0;
  if ( v3 && !a3 )
    return 0;
  v8 = 0;
  IoAcquireVpbSpinLock(&Irql);
  v9 = *(_QWORD *)(a2 + 192);
  if ( *(_DWORD *)(v9 + 28) != *(_DWORD *)(a2 + 284) || *(_DWORD *)(a2 + 272) )
  {
    if ( a3 )
      FatSwapVpb(a1, a2);
    IoReleaseVpbSpinLock(Irql);
  }
  else
  {
    FatSwapVpb(a1, a2);
    *(_WORD *)(v9 + 4) &= 0xFFDCu;
    IoReleaseVpbSpinLock(Irql);
    _InterlockedOr((volatile signed __int32 *)(a2 + 200), 0x80000u);
    FatTearDownVcb(v10, a2);
    FatFspClose(a2, v11, v12, v13);
    IoAcquireVpbSpinLock(&Irql);
    if ( *(_DWORD *)(*(_QWORD *)(a2 + 192) + 28LL) || *(_DWORD *)(a2 + 280) )
    {
      IoReleaseVpbSpinLock(Irql);
      _InterlockedAnd((volatile signed __int32 *)(a2 + 200), 0xFFF7FFFF);
    }
    else
    {
      *(_QWORD *)(v9 + 8) = 0;
      IoReleaseVpbSpinLock(Irql);
      FatDeleteVcb(a1, a2);
      IoDeleteDevice((PDEVICE_OBJECT)(a2 - 416));
      return 1;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140006350  mov     [rsp+arg_0], rbx
0x140006355  mov     [rsp+arg_10], rbp
0x14000635a  push    rsi
0x14000635b  push    rdi
0x14000635c  push    r14
0x14000635e  sub     rsp, 20h
0x140006362  cmp     dword ptr [rdx+0CCh], 1
0x140006369  mov     dil, r8b
0x14000636c  mov     rbx, rdx
0x14000636f  mov     [rsp+38h+Irql], 0
0x140006374  mov     rbp, rcx
0x140006377  jnz     short loc_140006385
0x140006379  test    r8b, r8b
0x14000637c  jnz     short loc_140006385
0x14000637e  xor     al, al
0x140006380  jmp     loc_14000649D
0x140006385  lea     rcx, [rsp+38h+Irql]; Irql
0x14000638a  xor     r14b, r14b
0x14000638d  call    cs:__imp_IoAcquireVpbSpinLock
0x140006394  nop     dword ptr [rax+rax+00h]
0x140006399  mov     rsi, [rbx+0C0h]
0x1400063a0  mov     eax, [rbx+11Ch]
0x1400063a6  cmp     [rsi+1Ch], eax
0x1400063a9  jnz     loc_14000647A
0x1400063af  cmp     dword ptr [rbx+110h], 0
0x1400063b6  jnz     loc_14000647A
0x1400063bc  mov     rdx, rbx
0x1400063bf  mov     rcx, rbp
0x1400063c2  call    FatSwapVpb
0x1400063c7  mov     eax, 0FFDCh
0x1400063cc  and     [rsi+4], ax
0x1400063d0  mov     cl, [rsp+38h+Irql]; Irql
0x1400063d4  call    cs:__imp_IoReleaseVpbSpinLock
0x1400063db  nop     dword ptr [rax+rax+00h]
0x1400063e0  lock or dword ptr [rbx+0C8h], 80000h
0x1400063eb  mov     rdx, rbx
0x1400063ee  call    FatTearDownVcb
0x1400063f3  mov     rcx, rbx
0x1400063f6  call    FatFspClose
0x1400063fb  lea     rcx, [rsp+38h+Irql]; Irql
0x140006400  call    cs:__imp_IoAcquireVpbSpinLock
0x140006407  nop     dword ptr [rax+rax+00h]
0x14000640c  mov     rax, [rbx+0C0h]
0x140006413  cmp     dword ptr [rax+1Ch], 0
0x140006417  jnz     short loc_14000645D
0x140006419  cmp     dword ptr [rbx+118h], 0
0x140006420  jnz     short loc_14000645D
0x140006422  mov     qword ptr [rsi+8], 0
0x14000642a  mov     cl, [rsp+38h+Irql]; Irql
0x14000642e  call    cs:__imp_IoReleaseVpbSpinLock
0x140006435  nop     dword ptr [rax+rax+00h]
0x14000643a  mov     rdx, rbx
0x14000643d  mov     rcx, rbp
0x140006440  call    FatDeleteVcb
0x140006445  lea     rcx, [rbx-1A0h]; DeviceObject
0x14000644c  call    cs:__imp_IoDeleteDevice
0x140006453  nop     dword ptr [rax+rax+00h]
0x140006458  mov     r14b, 1
0x14000645b  jmp     short loc_14000649A
0x14000645d  mov     cl, [rsp+38h+Irql]; Irql
0x140006461  call    cs:__imp_IoReleaseVpbSpinLock
0x140006468  nop     dword ptr [rax+rax+00h]
0x14000646d  lock and dword ptr [rbx+0C8h], 0FFF7FFFFh
0x140006478  jmp     short loc_14000649A
0x14000647a  test    dil, dil
0x14000647d  jz      short loc_14000648A
0x14000647f  mov     rdx, rbx
0x140006482  mov     rcx, rbp
0x140006485  call    FatSwapVpb
0x14000648a  mov     cl, [rsp+38h+Irql]; Irql
0x14000648e  call    cs:__imp_IoReleaseVpbSpinLock
0x140006495  nop     dword ptr [rax+rax+00h]
0x14000649a  mov     al, r14b
0x14000649d  mov     rbx, [rsp+38h+arg_0]
0x1400064a2  mov     rbp, [rsp+38h+arg_10]
0x1400064a7  add     rsp, 20h
0x1400064ab  pop     r14
0x1400064ad  pop     rdi
0x1400064ae  pop     rsi
0x1400064af  retn
```
