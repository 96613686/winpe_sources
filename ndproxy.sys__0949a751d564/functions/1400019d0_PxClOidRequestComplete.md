# PxClOidRequestComplete

- ea: `0x1400019d0`
- end: `0x140001ac4`
- name: `PxClOidRequestComplete`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400019d0`
- `0x140001da8`
- `0x140006e08`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a51`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001aae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001aae`
- `NDIS!NdisSetEvent` at `0x140001a6c`
- `NDIS!NdisSetEvent` at `0x140001a6c`

## pseudocode

```c
void __fastcall PxClOidRequestComplete(__int64 a1, unsigned __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // esi
  KSPIN_LOCK *v10; // rbx
  int v11; // eax
  KIRQL v12; // al
  PVOID Entry; // [rsp+70h] [rbp+8h] BYREF

  Entry = 0;
  GetVcFromCtx(a2, &Entry);
  v9 = a5;
  v10 = (KSPIN_LOCK *)Entry;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qqDd(WPP_GLOBAL_Control->AttachedDevice, v7, v8, a1, Entry, *(_DWORD *)(a4 + 32), a5);
  v11 = *(_DWORD *)(a4 + 240);
  if ( (v11 & 1) != 0 )
  {
    *(_DWORD *)(a4 + 240) = v11 & 0xFFFFFFFE;
    ExFreePoolWithTag((PVOID)a4, 0);
  }
  else
  {
    *(_DWORD *)(a4 + 272) = v9;
    NdisSetEvent((PNDIS_EVENT)(a4 + 248));
  }
  if ( v10 )
  {
    v12 = KeAcquireSpinLockRaiseToDpc(v10 + 64);
    *((_BYTE *)v10 + 520) = v12;
    if ( (*((_DWORD *)v10 + 7))-- == 1 )
      DoDerefVcWork(v10);
    else
      KeReleaseSpinLock(v10 + 64, v12);
  }
}

```

## disassembly

```asm
0x1400019d0  push    rbx
0x1400019d2  push    rbp
0x1400019d3  push    rsi
0x1400019d4  push    rdi
0x1400019d5  sub     rsp, 48h
0x1400019d9  mov     rax, rdx
0x1400019dc  mov     [rsp+68h+Entry], 0
0x1400019e5  mov     rbp, rcx
0x1400019e8  lea     rdx, [rsp+68h+Entry]
0x1400019ed  mov     rcx, rax
0x1400019f0  mov     rdi, r9
0x1400019f3  call    GetVcFromCtx
0x1400019f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019ff  lea     rax, WPP_GLOBAL_Control
0x140001a06  mov     esi, [rsp+68h+arg_20]
0x140001a0d  mov     rbx, [rsp+68h+Entry]
0x140001a12  cmp     rcx, rax
0x140001a15  jz      short loc_140001A39
0x140001a17  cmp     byte ptr [rcx+29h], 5
0x140001a1b  jb      short loc_140001A39
0x140001a1d  mov     eax, [rdi+20h]
0x140001a20  mov     r9, rbp
0x140001a23  mov     rcx, [rcx+18h]
0x140001a27  mov     [rsp+68h+var_38], esi
0x140001a2b  mov     [rsp+68h+var_40], eax
0x140001a2f  mov     [rsp+68h+var_48], rbx
0x140001a34  call    WPP_SF_qqDd
0x140001a39  mov     eax, [rdi+0F0h]
0x140001a3f  test    al, 1
0x140001a41  jz      short loc_140001A5F
0x140001a43  and     eax, 0FFFFFFFEh
0x140001a46  xor     edx, edx; Tag
0x140001a48  mov     rcx, rdi; P
0x140001a4b  mov     [rdi+0F0h], eax
0x140001a51  call    cs:__imp_ExFreePoolWithTag
0x140001a58  nop     dword ptr [rax+rax+00h]
0x140001a5d  jmp     short loc_140001A78
0x140001a5f  lea     rcx, [rdi+0F8h]; Event
0x140001a66  mov     [rdi+110h], esi
0x140001a6c  call    cs:__imp_NdisSetEvent
0x140001a73  nop     dword ptr [rax+rax+00h]
0x140001a78  test    rbx, rbx
0x140001a7b  jz      short loc_140001ABA
0x140001a7d  lea     rdi, [rbx+200h]
0x140001a84  mov     rcx, rdi; SpinLock
0x140001a87  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001a8e  nop     dword ptr [rax+rax+00h]
0x140001a93  mov     [rbx+208h], al
0x140001a99  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x140001a9d  jnz     short loc_140001AA9
0x140001a9f  mov     rcx, rbx; Entry
0x140001aa2  call    DoDerefVcWork
0x140001aa7  jmp     short loc_140001ABA
0x140001aa9  mov     dl, al; NewIrql
0x140001aab  mov     rcx, rdi; SpinLock
0x140001aae  call    cs:__imp_KeReleaseSpinLock
0x140001ab5  nop     dword ptr [rax+rax+00h]
0x140001aba  add     rsp, 48h
0x140001abe  pop     rdi
0x140001abf  pop     rsi
0x140001ac0  pop     rbp
0x140001ac1  pop     rbx
0x140001ac2  retn
```
