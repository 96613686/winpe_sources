# SmpReturnNetBufferListChain

- ea: `0x140019420`
- end: `0x14001950f`
- name: `SmpReturnNetBufferListChain`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400018b0`
- `0x140005ef0`
- `0x140019420`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400194ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400194ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400194ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400194ce`
- `NDIS!NdisFreeNetBufferList` at `0x1400194dd`
- `NDIS!NdisFreeNetBufferList` at `0x1400194dd`
- `fwpkclnt!DPReceiveNetBufferListComplete0` at `0x14001945c`
- `fwpkclnt!DPReceiveNetBufferListComplete0` at `0x14001945c`

## pseudocode

```c
void __fastcall SmpReturnNetBufferListChain(__int64 a1, struct _NET_BUFFER_LIST *a2)
{
  struct _NET_BUFFER_LIST *Alignment; // rbx
  PVOID Scratch; // rcx
  SLIST_HEADER *v4; // rax
  struct _NET_BUFFER_LIST *v5; // rdi
  void (**v6)(void); // rcx
  __int64 v7; // rsi
  KIRQL v8; // al
  bool v9; // zf

  if ( a2 )
  {
    Alignment = a2;
    do
    {
      Scratch = Alignment->Scratch;
      v4 = (SLIST_HEADER *)Alignment;
      v5 = Alignment;
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      v4->Alignment = 0;
      if ( Scratch )
      {
        DPReceiveNetBufferListComplete0(Scratch, v5);
      }
      else
      {
        v7 = (__int64)v5->MiniportReserved[0];
        v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 32));
        v9 = (*(_DWORD *)(v7 + 48))-- == 1;
        if ( v9 && *(_BYTE *)(v7 + 21092) == 1 )
          InitiateSstpContextCleanup(v7, 4, v8);
        else
          KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 32), v8);
        NdisFreeNetBufferList(v5);
      }
      v6 = (void (**)(void))((char *)SstpGlobals + 144);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)SstpGlobals + 36, 0xFFFFFFFF) == 1 )
        v6[1]();
    }
    while ( Alignment );
  }
}

```

## disassembly

```asm
0x140019420  test    rdx, rdx
0x140019423  jz      short locret_1400194A2
0x140019425  push    rbx
0x140019426  sub     rsp, 30h
0x14001942a  mov     [rsp+38h+var_10], rdi
0x14001942f  mov     rbx, rdx
0x140019432  mov     [rsp+38h+var_18], r14
0x140019437  xor     r14d, r14d
0x14001943a  mov     [rsp+38h+arg_0], rbp
0x14001943f  mov     [rsp+38h+arg_10], rsi
0x140019444  mov     rcx, [rbx+70h]
0x140019448  mov     rax, rbx
0x14001944b  mov     rdi, rbx
0x14001944e  mov     rbx, [rbx]
0x140019451  mov     [rax], r14
0x140019454  test    rcx, rcx
0x140019457  jz      short loc_1400194A4
0x140019459  mov     rdx, rdi
0x14001945c  call    cs:__imp_DPReceiveNetBufferListComplete0
0x140019463  nop     dword ptr [rax+rax+00h]
0x140019468  mov     rcx, cs:SstpGlobals
0x14001946f  mov     eax, 0FFFFFFFFh
0x140019474  add     rcx, 90h
0x14001947b  lock xadd [rcx], eax
0x14001947f  cmp     eax, 1
0x140019482  jz      short loc_140019501
0x140019484  test    rbx, rbx
0x140019487  jnz     short loc_140019444
0x140019489  mov     r14, [rsp+38h+var_18]
0x14001948e  mov     rdi, [rsp+38h+var_10]
0x140019493  mov     rsi, [rsp+38h+arg_10]
0x140019498  mov     rbp, [rsp+38h+arg_0]
0x14001949d  add     rsp, 30h
0x1400194a1  pop     rbx
0x1400194a2  retn
0x1400194a4  mov     rsi, [rdi+60h]
0x1400194a8  lea     rcx, [rsi+20h]; SpinLock
0x1400194ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400194b3  nop     dword ptr [rax+rax+00h]
0x1400194b8  add     dword ptr [rsi+30h], 0FFFFFFFFh
0x1400194bc  jnz     short loc_1400194C7
0x1400194be  cmp     byte ptr [rsi+5264h], 1
0x1400194c5  jz      short loc_1400194EE
0x1400194c7  movzx   edx, al; NewIrql
0x1400194ca  lea     rcx, [rsi+20h]; SpinLock
0x1400194ce  call    cs:__imp_KeReleaseSpinLock
0x1400194d5  nop     dword ptr [rax+rax+00h]
0x1400194da  mov     rcx, rdi; NetBufferList
0x1400194dd  call    cs:__imp_NdisFreeNetBufferList
0x1400194e4  nop     dword ptr [rax+rax+00h]
0x1400194e9  jmp     loc_140019468
0x1400194ee  movzx   r8d, al
0x1400194f2  mov     edx, 4
0x1400194f7  mov     rcx, rsi
0x1400194fa  call    InitiateSstpContextCleanup
0x1400194ff  jmp     short loc_1400194DA
0x140019501  mov     rax, [rcx+8]
0x140019505  call    _guard_dispatch_icall
0x14001950a  jmp     loc_140019484
```
