# DPReceiveCallback

- ea: `0x140019520`
- end: `0x14001974e`
- name: `DPReceiveCallback`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002c08`
- `0x140003a64`
- `0x140019520`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019545`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400195be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019545`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400195be`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019596`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001962b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019596`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001962b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400196d9`
- `NDIS!NdisMCoIndicateReceiveNetBufferLists` at `0x140019644`
- `NDIS!NdisMCoIndicateReceiveNetBufferLists` at `0x140019644`
- `fwpkclnt!DPReceiveNetBufferListComplete0` at `0x140019697`
- `fwpkclnt!DPReceiveNetBufferListComplete0` at `0x1400196eb`
- `fwpkclnt!DPReceiveNetBufferListComplete0` at `0x140019697`
- `fwpkclnt!DPReceiveNetBufferListComplete0` at `0x1400196eb`

## pseudocode

```c
void __fastcall DPReceiveCallback(ULONGLONG a1, struct _NET_BUFFER_LIST *a2)
{
  _QWORD *v4; // rbx
  KIRQL v5; // al
  _QWORD *i; // r8
  KIRQL v7; // r14
  SLIST_HEADER *Alignment; // rcx
  ULONG v9; // edi

  v4 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
  for ( i = (_QWORD *)*((_QWORD *)SstpGlobals + 60); i != (_QWORD *)((char *)SstpGlobals + 480); v4 = 0 )
  {
    v4 = i - 2;
    if ( *((_BYTE *)i + 21116) && a1 == v4[2642] )
      break;
    i = (_QWORD *)*i;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 59, v5);
  if ( v4 )
  {
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 25);
    if ( *((_DWORD *)SstpGlobals + 40) == 2 )
    {
      Alignment = (SLIST_HEADER *)a2;
      v9 = 0;
      if ( a2 )
      {
        do
        {
          _InterlockedIncrement((volatile signed __int32 *)SstpGlobals + 36);
          ++v9;
          Alignment[7].Region = v4[5];
          Alignment[7].Alignment = a1;
          Alignment = (SLIST_HEADER *)Alignment->Alignment;
        }
        while ( Alignment );
      }
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 25, v7);
      NdisMCoIndicateReceiveNetBufferLists((NDIS_HANDLE)v4[5], a2, v9, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 25, v7);
      DPReceiveNetBufferListComplete0(a1, a2);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, a1);
    }
    DPReceiveNetBufferListComplete0(a1, a2);
  }
}

```

## disassembly

```asm
0x140019520  mov     [rsp+arg_10], rbx
0x140019525  mov     [rsp+arg_18], rbp
0x14001952a  push    rsi
0x14001952b  sub     rsp, 20h
0x14001952f  mov     rbp, rcx
0x140019532  mov     rsi, rdx
0x140019535  mov     rcx, cs:SstpGlobals
0x14001953c  xor     ebx, ebx
0x14001953e  add     rcx, 1D8h; SpinLock
0x140019545  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001954c  nop     dword ptr [rax+rax+00h]
0x140019551  mov     rdx, cs:SstpGlobals
0x140019558  add     rdx, 1E0h
0x14001955f  mov     r8, [rdx]
0x140019562  cmp     r8, rdx
0x140019565  jz      short loc_140019585
0x140019567  lea     rbx, [r8-10h]
0x14001956b  cmp     byte ptr [rbx+528Ch], 0
0x140019572  jz      loc_14001966B
0x140019578  cmp     rbp, [rbx+5290h]
0x14001957f  jnz     loc_14001966B
0x140019585  mov     rcx, cs:SstpGlobals
0x14001958c  movzx   edx, al; NewIrql
0x14001958f  add     rcx, 1D8h; SpinLock
0x140019596  call    cs:__imp_KeReleaseSpinLock
0x14001959d  nop     dword ptr [rax+rax+00h]
0x1400195a2  test    rbx, rbx
0x1400195a5  jz      loc_14001967E
0x1400195ab  mov     rcx, cs:SstpGlobals
0x1400195b2  add     rcx, 0C8h; SpinLock
0x1400195b9  mov     [rsp+28h+arg_8], r14
0x1400195be  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400195c5  nop     dword ptr [rax+rax+00h]
0x1400195ca  mov     rcx, cs:SstpGlobals
0x1400195d1  movzx   r14d, al
0x1400195d5  mov     r9d, [rcx+0A0h]
0x1400195dc  cmp     r9d, 2
0x1400195e0  jnz     loc_1400196B4
0x1400195e6  mov     [rsp+28h+arg_0], rdi
0x1400195eb  mov     rcx, rsi
0x1400195ee  xor     edi, edi
0x1400195f0  test    rsi, rsi
0x1400195f3  jz      short loc_140019619
0x1400195f5  mov     rax, cs:SstpGlobals
0x1400195fc  lock inc dword ptr [rax+90h]
0x140019603  mov     rax, [rbx+28h]
0x140019607  inc     edi
0x140019609  mov     [rcx+78h], rax
0x14001960d  mov     [rcx+70h], rbp
0x140019611  mov     rcx, [rcx]
0x140019614  test    rcx, rcx
0x140019617  jnz     short loc_1400195F5
0x140019619  mov     rcx, cs:SstpGlobals
0x140019620  movzx   edx, r14b; NewIrql
0x140019624  add     rcx, 0C8h; SpinLock
0x14001962b  call    cs:__imp_KeReleaseSpinLock
0x140019632  nop     dword ptr [rax+rax+00h]
0x140019637  mov     rcx, [rbx+28h]; NdisVcHandle
0x14001963b  xor     r9d, r9d; CoReceiveFlags
0x14001963e  mov     r8d, edi; NumberOfNetBufferLists
0x140019641  mov     rdx, rsi; NetBufferLists
0x140019644  call    cs:__imp_NdisMCoIndicateReceiveNetBufferLists
0x14001964b  nop     dword ptr [rax+rax+00h]
0x140019650  mov     rdi, [rsp+28h+arg_0]
0x140019655  mov     r14, [rsp+28h+arg_8]
0x14001965a  mov     rbx, [rsp+28h+arg_10]
0x14001965f  mov     rbp, [rsp+28h+arg_18]
0x140019664  add     rsp, 20h
0x140019668  pop     rsi
0x140019669  retn
0x14001966b  mov     r8, [r8]
0x14001966e  xor     ebx, ebx
0x140019670  cmp     r8, rdx
0x140019673  jz      loc_140019585
0x140019679  jmp     loc_140019567
0x14001967e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019685  lea     rax, WPP_GLOBAL_Control
0x14001968c  cmp     rcx, rax
0x14001968f  jnz     short loc_1400196FC
0x140019691  mov     rdx, rsi
0x140019694  mov     rcx, rbp
0x140019697  call    cs:__imp_DPReceiveNetBufferListComplete0
0x14001969e  nop     dword ptr [rax+rax+00h]
0x1400196a3  mov     rbx, [rsp+28h+arg_10]
0x1400196a8  mov     rbp, [rsp+28h+arg_18]
0x1400196ad  add     rsp, 20h
0x1400196b1  pop     rsi
0x1400196b2  retn
0x1400196b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196bb  lea     rax, WPP_GLOBAL_Control
0x1400196c2  cmp     rcx, rax
0x1400196c5  jnz     short loc_140019726
0x1400196c7  mov     rcx, cs:SstpGlobals
0x1400196ce  movzx   edx, r14b; NewIrql
0x1400196d2  add     rcx, 0C8h; SpinLock
0x1400196d9  call    cs:__imp_KeReleaseSpinLock
0x1400196e0  nop     dword ptr [rax+rax+00h]
0x1400196e5  mov     rdx, rsi
0x1400196e8  mov     rcx, rbp
0x1400196eb  call    cs:__imp_DPReceiveNetBufferListComplete0
0x1400196f2  nop     dword ptr [rax+rax+00h]
0x1400196f7  jmp     loc_140019655
0x1400196fc  mov     eax, [rcx+2Ch]
0x1400196ff  test    al, 1
0x140019701  jz      short loc_140019691
0x140019703  cmp     byte ptr [rcx+29h], 1
0x140019707  jb      short loc_140019691
0x140019709  mov     rcx, [rcx+18h]
0x14001970d  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140019714  mov     edx, 5Eh ; '^'
0x140019719  mov     r9, rbp
0x14001971c  call    WPP_SF_q
0x140019721  jmp     loc_140019691
0x140019726  mov     edx, [rcx+2Ch]
0x140019729  test    dl, 1
0x14001972c  jz      short loc_1400196C7
0x14001972e  cmp     byte ptr [rcx+29h], 1
0x140019732  jb      short loc_1400196C7
0x140019734  mov     rcx, [rcx+18h]
0x140019738  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001973f  mov     edx, 5Fh ; '_'
0x140019744  call    WPP_SF_d
0x140019749  jmp     loc_1400196C7
```
