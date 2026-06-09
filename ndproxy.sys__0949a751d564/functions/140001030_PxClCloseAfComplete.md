# PxClCloseAfComplete

- ea: `0x140001030`
- end: `0x1400011a4`
- name: `PxClCloseAfComplete`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002fd0`
- `0x1400078f0`

## callees

- `0x140001030`
- `0x140001c0c`
- `0x140006f68`
- `0x140007b44`
- `0x140007bf8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001087`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400010f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000113a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001087`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400010f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000113a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010df`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000111f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000115d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010df`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000111f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000115d`
- `NDIS!NdisClNotifyCloseAddressFamilyComplete` at `0x140001178`
- `NDIS!NdisClNotifyCloseAddressFamilyComplete` at `0x140001178`

## pseudocode

```c
__int64 __fastcall PxClCloseAfComplete(int a1, void *a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // rcx
  void **v5; // rax
  KSPIN_LOCK *v6; // rcx
  bool v7; // zf
  KIRQL v8; // dl
  KIRQL v9; // al
  __int64 v10; // rsi

  v2 = *((_QWORD *)a2 + 4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2, a1);
  *(_BYTE *)(v2 + 632) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 624));
  v4 = *(_QWORD **)a2;
  if ( *(void **)(*(_QWORD *)a2 + 8LL) != a2 || (v5 = (void **)*((_QWORD *)a2 + 1), *v5 != a2) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = v5;
  v6 = (KSPIN_LOCK *)(v2 + 624);
  v7 = (*(_DWORD *)(v2 + 24))-- == 1;
  v8 = *(_BYTE *)(v2 + 632);
  if ( v7 )
  {
    KeReleaseSpinLock(v6, v8);
    PxFreeAdapter((PVOID)v2);
  }
  else
  {
    KeReleaseSpinLock(v6, v8);
  }
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a2 + 23);
  v10 = *((_QWORD *)a2 + 13);
  *((_BYTE *)a2 + 192) = v9;
  *((_DWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 13) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)a2 + 23, v9);
  if ( v10 )
  {
    *(_BYTE *)(v10 + 144) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 136));
    MarkProviderOffline(v10);
    KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 136), *(_BYTE *)(v10 + 144));
  }
  if ( *((_BYTE *)a2 + 200) )
    NdisClNotifyCloseAddressFamilyComplete(*((NDIS_HANDLE *)a2 + 3), 0);
  return PxFreeClAf(a2);
}

```

## disassembly

```asm
0x140001030  mov     [rsp+arg_0], rbx
0x140001035  mov     [rsp+arg_10], rsi
0x14000103a  push    rdi
0x14000103b  sub     rsp, 30h
0x14000103f  mov     rbx, [rdx+20h]
0x140001043  mov     rdi, rdx
0x140001046  mov     eax, ecx
0x140001048  mov     rcx, cs:WPP_GLOBAL_Control
0x14000104f  lea     rdx, WPP_GLOBAL_Control
0x140001056  cmp     rcx, rdx
0x140001059  jz      short loc_14000107D
0x14000105b  cmp     byte ptr [rcx+29h], 5
0x14000105f  jb      short loc_14000107D
0x140001061  mov     rcx, [rcx+18h]
0x140001065  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000106c  mov     edx, 16h
0x140001071  mov     [rsp+38h+var_18], eax
0x140001075  mov     r9, rdi
0x140001078  call    WPP_SF_qD
0x14000107d  lea     rsi, [rbx+270h]
0x140001084  mov     rcx, rsi; SpinLock
0x140001087  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000108e  nop     dword ptr [rax+rax+00h]
0x140001093  mov     [rbx+278h], al
0x140001099  mov     rcx, [rdi]
0x14000109c  cmp     [rcx+8], rdi
0x1400010a0  jnz     loc_14000119D
0x1400010a6  mov     rax, [rdi+8]
0x1400010aa  cmp     [rax], rdi
0x1400010ad  jnz     loc_14000119D
0x1400010b3  mov     [rax], rcx
0x1400010b6  mov     [rcx+8], rax
0x1400010ba  mov     rcx, rsi; SpinLock
0x1400010bd  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x1400010c1  mov     dl, [rbx+278h]; NewIrql
0x1400010c7  jnz     short loc_1400010DF
0x1400010c9  call    cs:__imp_KeReleaseSpinLock
0x1400010d0  nop     dword ptr [rax+rax+00h]
0x1400010d5  mov     rcx, rbx; P
0x1400010d8  call    PxFreeAdapter
0x1400010dd  jmp     short loc_1400010EB
0x1400010df  call    cs:__imp_KeReleaseSpinLock
0x1400010e6  nop     dword ptr [rax+rax+00h]
0x1400010eb  lea     rbx, [rdi+0B8h]
0x1400010f2  mov     rcx, rbx; SpinLock
0x1400010f5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400010fc  nop     dword ptr [rax+rax+00h]
0x140001101  mov     rsi, [rdi+68h]
0x140001105  mov     rcx, rbx; SpinLock
0x140001108  mov     dl, al; NewIrql
0x14000110a  mov     [rdi+0C0h], al
0x140001110  mov     dword ptr [rdi+10h], 0
0x140001117  mov     qword ptr [rdi+68h], 0
0x14000111f  call    cs:__imp_KeReleaseSpinLock
0x140001126  nop     dword ptr [rax+rax+00h]
0x14000112b  test    rsi, rsi
0x14000112e  jz      short loc_140001169
0x140001130  lea     rbx, [rsi+88h]
0x140001137  mov     rcx, rbx; SpinLock
0x14000113a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001141  nop     dword ptr [rax+rax+00h]
0x140001146  mov     rcx, rsi
0x140001149  mov     [rsi+90h], al
0x14000114f  call    MarkProviderOffline
0x140001154  mov     dl, [rsi+90h]; NewIrql
0x14000115a  mov     rcx, rbx; SpinLock
0x14000115d  call    cs:__imp_KeReleaseSpinLock
0x140001164  nop     dword ptr [rax+rax+00h]
0x140001169  cmp     byte ptr [rdi+0C8h], 0
0x140001170  jz      short loc_140001184
0x140001172  mov     rcx, [rdi+18h]; NdisAfHandle
0x140001176  xor     edx, edx; Status
0x140001178  call    cs:__imp_NdisClNotifyCloseAddressFamilyComplete
0x14000117f  nop     dword ptr [rax+rax+00h]
0x140001184  mov     rcx, rdi; P
0x140001187  call    PxFreeClAf
0x14000118c  mov     rbx, [rsp+38h+arg_0]
0x140001191  mov     rsi, [rsp+38h+arg_10]
0x140001196  add     rsp, 30h
0x14000119a  pop     rdi
0x14000119b  retn
0x14000119d  mov     ecx, 3
0x1400011a2  int     29h; Win8: RtlFailFast(ecx)
```
