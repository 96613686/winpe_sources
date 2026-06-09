# KsRemoveIrpFromCancelableQueue

- ea: `0x180006c40`
- end: `0x180006db0`
- name: `KsRemoveIrpFromCancelableQueue`
- size: `368`
- prototype: `PIRP __stdcall(PLIST_ENTRY QueueHead, PKSPIN_LOCK SpinLock, KSLIST_ENTRY_LOCATION ListLocation, KSIRP_REMOVAL_OPERATION RemovalOperation)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c1dc`
- `0x180010a74`
- `0x180018314`
- `0x18003adc0`
- `0x180041e00`
- `0x180047cd8`
- `0x18005c83c`

## callees

- `0x180006c40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180006c66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180006c66`
- `ntoskrnl!KeReleaseSpinLock` at `0x180006cac`
- `ntoskrnl!KeReleaseSpinLock` at `0x180006cdd`
- `ntoskrnl!KeReleaseSpinLock` at `0x180006cac`
- `ntoskrnl!KeReleaseSpinLock` at `0x180006cdd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180006cfd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180006cfd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180006d54`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180006d54`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180006cee`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180006cee`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180006d65`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180006d65`

## pseudocode

```c
PIRP __stdcall KsRemoveIrpFromCancelableQueue(
        PLIST_ENTRY QueueHead,
        PKSPIN_LOCK SpinLock,
        KSLIST_ENTRY_LOCATION ListLocation,
        KSIRP_REMOVAL_OPERATION RemovalOperation)
{
  PLIST_ENTRY v5; // rbx
  IRP *p_Blink; // rsi
  char v7; // r15
  PLIST_ENTRY v11; // rcx
  PLIST_ENTRY v12; // rdx
  struct _LIST_ENTRY *v13; // rax
  struct _LIST_ENTRY *v14; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rdx
  KIRQL Irql; // [rsp+70h] [rbp+18h] BYREF

  Irql = 0;
  v5 = QueueHead;
  p_Blink = 0;
  v7 = RemovalOperation;
  Irql = KeAcquireSpinLockRaiseToDpc(SpinLock);
  do
  {
    if ( ListLocation == KsListEntryHead )
      v5 = v5->Flink;
    else
      v5 = v5->Blink;
    if ( v5 == QueueHead )
      goto LABEL_8;
    if ( _InterlockedExchange64((volatile __int64 *)&v5[-4], 0) )
    {
      if ( (v7 & 1) == 0 )
      {
LABEL_7:
        p_Blink = (IRP *)&v5[-11].Blink;
LABEL_8:
        KeReleaseSpinLock(SpinLock, Irql);
        return p_Blink;
      }
      Flink = v5->Flink;
      if ( v5->Flink->Blink == v5 )
      {
        Blink = v5->Blink;
        if ( Blink->Flink == v5 )
        {
          Blink->Flink = Flink;
          Flink->Blink = Blink;
          goto LABEL_7;
        }
      }
LABEL_21:
      __fastfail(3u);
    }
  }
  while ( (v7 & 2) == 0 );
  if ( !BYTE4(v5[-7].Blink) )
    goto LABEL_8;
  KeReleaseSpinLock(SpinLock, Irql);
  IoAcquireCancelSpinLock(&Irql);
  KeAcquireSpinLockAtDpcLevel(SpinLock);
  v11 = QueueHead;
  if ( ListLocation != KsListEntryHead )
    v11 = (PLIST_ENTRY)&QueueHead->Blink;
  v12 = v11->Flink;
  if ( v11->Flink == QueueHead || !_InterlockedExchange64((volatile __int64 *)&v12[-4], 0) )
    goto LABEL_20;
  if ( (v7 & 1) == 0 )
    goto LABEL_19;
  v13 = v12->Flink;
  if ( v12->Flink->Blink != v12 )
    goto LABEL_21;
  v14 = v12->Blink;
  if ( v14->Flink != v12 )
    goto LABEL_21;
  v14->Flink = v13;
  v13->Blink = v14;
LABEL_19:
  p_Blink = (IRP *)&v12[-11].Blink;
LABEL_20:
  KeReleaseSpinLockFromDpcLevel(SpinLock);
  IoReleaseCancelSpinLock(Irql);
  return p_Blink;
}

```

## disassembly

```asm
0x180006c40  push    rbx
0x180006c42  push    rbp
0x180006c43  push    rsi
0x180006c44  push    rdi
0x180006c45  push    r14
0x180006c47  push    r15
0x180006c49  sub     rsp, 28h
0x180006c4d  mov     rbp, rcx
0x180006c50  mov     [rsp+58h+Irql], 0
0x180006c55  mov     rbx, rcx
0x180006c58  xor     esi, esi
0x180006c5a  mov     rcx, rdx; SpinLock
0x180006c5d  mov     r15d, r9d
0x180006c60  mov     r14d, r8d
0x180006c63  mov     rdi, rdx
0x180006c66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180006c6d  nop     dword ptr [rax+rax+00h]
0x180006c72  mov     [rsp+58h+Irql], al
0x180006c76  cmp     r14d, 1
0x180006c7a  jnz     loc_180006DA7
0x180006c80  mov     rbx, [rbx]
0x180006c83  cmp     rbx, rbp
0x180006c86  jz      short loc_180006CA4
0x180006c88  xor     eax, eax
0x180006c8a  xchg    rax, [rbx-40h]
0x180006c8e  test    rax, rax
0x180006c91  jz      short loc_180006CC9
0x180006c93  test    r15b, 1
0x180006c97  jnz     loc_180006D89
0x180006c9d  lea     rsi, [rbx-0A8h]
0x180006ca4  movzx   edx, [rsp+58h+Irql]; NewIrql
0x180006ca9  mov     rcx, rdi; SpinLock
0x180006cac  call    cs:__imp_KeReleaseSpinLock
0x180006cb3  nop     dword ptr [rax+rax+00h]
0x180006cb8  mov     rax, rsi
0x180006cbb  add     rsp, 28h
0x180006cbf  pop     r15
0x180006cc1  pop     r14
0x180006cc3  pop     rdi
0x180006cc4  pop     rsi
0x180006cc5  pop     rbp
0x180006cc6  pop     rbx
0x180006cc7  retn
0x180006cc9  test    r15b, 2
0x180006ccd  jz      short loc_180006C76
0x180006ccf  cmp     [rbx-64h], sil
0x180006cd3  jz      short loc_180006CA4
0x180006cd5  movzx   edx, [rsp+58h+Irql]; NewIrql
0x180006cda  mov     rcx, rdi; SpinLock
0x180006cdd  call    cs:__imp_KeReleaseSpinLock
0x180006ce4  nop     dword ptr [rax+rax+00h]
0x180006ce9  lea     rcx, [rsp+58h+Irql]; Irql
0x180006cee  call    cs:__imp_IoAcquireCancelSpinLock
0x180006cf5  nop     dword ptr [rax+rax+00h]
0x180006cfa  mov     rcx, rdi; SpinLock
0x180006cfd  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x180006d04  nop     dword ptr [rax+rax+00h]
0x180006d09  cmp     r14d, 1
0x180006d0d  lea     rax, [rbp+8]
0x180006d11  mov     rcx, rbp
0x180006d14  cmovnz  rcx, rax
0x180006d18  mov     rdx, [rcx]
0x180006d1b  cmp     rdx, rbp
0x180006d1e  jz      short loc_180006D51
0x180006d20  xor     eax, eax
0x180006d22  xchg    rax, [rdx-40h]
0x180006d26  test    rax, rax
0x180006d29  jz      short loc_180006D51
0x180006d2b  test    r15b, 1
0x180006d2f  jz      short loc_180006D4A
0x180006d31  mov     rax, [rdx]
0x180006d34  cmp     [rax+8], rdx
0x180006d38  jnz     short loc_180006D82
0x180006d3a  mov     rcx, [rdx+8]
0x180006d3e  cmp     [rcx], rdx
0x180006d41  jnz     short loc_180006D82
0x180006d43  mov     [rcx], rax
0x180006d46  mov     [rax+8], rcx
0x180006d4a  lea     rsi, [rdx-0A8h]
0x180006d51  mov     rcx, rdi; SpinLock
0x180006d54  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x180006d5b  nop     dword ptr [rax+rax+00h]
0x180006d60  movzx   ecx, [rsp+58h+Irql]; Irql
0x180006d65  call    cs:__imp_IoReleaseCancelSpinLock
0x180006d6c  nop     dword ptr [rax+rax+00h]
0x180006d71  mov     rax, rsi
0x180006d74  add     rsp, 28h
0x180006d78  pop     r15
0x180006d7a  pop     r14
0x180006d7c  pop     rdi
0x180006d7d  pop     rsi
0x180006d7e  pop     rbp
0x180006d7f  pop     rbx
0x180006d80  retn
0x180006d82  mov     ecx, 3
0x180006d87  int     29h; Win8: RtlFailFast(ecx)
0x180006d89  mov     rax, [rbx]
0x180006d8c  cmp     [rax+8], rbx
0x180006d90  jnz     short loc_180006D82
0x180006d92  mov     rdx, [rbx+8]
0x180006d96  cmp     [rdx], rbx
0x180006d99  jnz     short loc_180006D82
0x180006d9b  mov     [rdx], rax
0x180006d9e  mov     [rax+8], rdx
0x180006da2  jmp     loc_180006C9D
0x180006da7  mov     rbx, [rbx+8]
0x180006dab  jmp     loc_180006C83
```
