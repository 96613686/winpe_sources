# RxDeregisterSrvOpenWithBufferingManager

- ea: `0x14006a960`
- end: `0x14006aa3a`
- name: `RxDeregisterSrvOpenWithBufferingManager`
- size: `218`
- prototype: `__int64 __fastcall(PSRV_CALL SrvCall)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14004cac0`
- `0x14006a840`

## callees

- `0x14000c1c0`
- `0x140017190`
- `0x14006a960`
- `0x140074ec0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14006a9ad`
- `ntoskrnl!ExAcquireFastMutex` at `0x14006a9ad`
- `ntoskrnl!ExReleaseFastMutex` at `0x14006a9fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14006a9fb`

## pseudocode

```c
void __fastcall RxDeregisterSrvOpenWithBufferingManager(PSRV_CALL SrvCall)
{
  bool v1; // zf
  __int64 v3; // rdi
  PLIST_ENTRY v4; // r8
  LIST_ENTRY *p_ScavengerFinalizationList; // rax
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v8; // rdi
  struct _LIST_ENTRY DiscardedRequests; // [rsp+20h] [rbp-18h] BYREF

  v1 = (*(_DWORD *)&SrvCall->UpperFinalizationDone & 0x100) == 0;
  DiscardedRequests = 0;
  if ( !v1 )
  {
    v3 = *(_QWORD *)(*(_QWORD *)&SrvCall->pPrincipalName[2].Length + 32LL);
    DiscardedRequests.Blink = &DiscardedRequests;
    DiscardedRequests.Flink = &DiscardedRequests;
    ExAcquireFastMutex((PFAST_MUTEX)(v3 + 520));
    RxGatherRequestsForSrvOpen(SrvCall, (PSRV_OPEN)&DiscardedRequests, v4);
    p_ScavengerFinalizationList = &SrvCall->ScavengerFinalizationList;
    Flink = SrvCall->ScavengerFinalizationList.Flink;
    if ( Flink->Blink != &SrvCall->ScavengerFinalizationList
      || (Blink = SrvCall->ScavengerFinalizationList.Blink, Blink->Flink != p_ScavengerFinalizationList) )
    {
      __fastfail(3u);
    }
    Blink->Flink = Flink;
    Flink->Blink = Blink;
    SrvCall->ScavengerFinalizationList.Blink = &SrvCall->ScavengerFinalizationList;
    p_ScavengerFinalizationList->Flink = p_ScavengerFinalizationList;
    *(_DWORD *)&SrvCall->UpperFinalizationDone &= ~0x100u;
    ExReleaseFastMutex((PFAST_MUTEX)(v3 + 520));
    v8 = DiscardedRequests.Flink;
    if ( DiscardedRequests.Flink != &DiscardedRequests )
    {
      do
      {
        RxDecrementOutstandingBufferingChangesOnFcb(SrvCall->pSrvCallName);
        v8 = v8->Flink;
      }
      while ( v8 != &DiscardedRequests );
      RxpDiscardChangeBufferingStateRequests(&DiscardedRequests);
    }
  }
}

```

## disassembly

```asm
0x14006a960  push    rbx
0x14006a962  sub     rsp, 30h
0x14006a966  test    dword ptr [rcx+48h], 100h
0x14006a96d  xorps   xmm0, xmm0
0x14006a970  movups  xmmword ptr [rsp+38h+DiscardedRequests.Flink], xmm0
0x14006a975  mov     rbx, rcx
0x14006a978  jnz     short loc_14006A981
0x14006a97a  add     rsp, 30h
0x14006a97e  pop     rbx
0x14006a97f  retn
0x14006a981  mov     rax, [rcx+28h]
0x14006a985  mov     [rsp+38h+arg_0], rdi
0x14006a98a  mov     rcx, [rax+20h]
0x14006a98e  mov     rdi, [rcx+20h]
0x14006a992  lea     rcx, [rsp+38h+DiscardedRequests]
0x14006a997  mov     [rsp+38h+DiscardedRequests.Blink], rcx
0x14006a99c  lea     rcx, [rsp+38h+DiscardedRequests]
0x14006a9a1  mov     [rsp+38h+DiscardedRequests.Flink], rcx
0x14006a9a6  lea     rcx, [rdi+208h]; FastMutex
0x14006a9ad  call    cs:__imp_ExAcquireFastMutex
0x14006a9b4  nop     dword ptr [rax+rax+00h]
0x14006a9b9  lea     rdx, [rsp+38h+DiscardedRequests]; SrvOpen
0x14006a9be  mov     rcx, rbx; SrvCall
0x14006a9c1  call    RxGatherRequestsForSrvOpen
0x14006a9c6  lea     rax, [rbx+0D0h]
0x14006a9cd  mov     r8, [rax]
0x14006a9d0  cmp     [r8+8], rax
0x14006a9d4  jnz     short loc_14006AA20
0x14006a9d6  mov     rdx, [rax+8]
0x14006a9da  cmp     [rdx], rax
0x14006a9dd  jnz     short loc_14006AA20
0x14006a9df  mov     [rdx], r8
0x14006a9e2  lea     rcx, [rdi+208h]; FastMutex
0x14006a9e9  mov     [r8+8], rdx
0x14006a9ed  mov     [rax+8], rax
0x14006a9f1  mov     [rax], rax
0x14006a9f4  and     dword ptr [rbx+48h], 0FFFFFEFFh
0x14006a9fb  call    cs:__imp_ExReleaseFastMutex
0x14006aa02  nop     dword ptr [rax+rax+00h]
0x14006aa07  mov     rdi, [rsp+38h+DiscardedRequests.Flink]
0x14006aa0c  lea     rax, [rsp+38h+DiscardedRequests]
0x14006aa11  cmp     rdi, rax
0x14006aa14  jnz     short loc_14006AA27
0x14006aa16  mov     rdi, [rsp+38h+arg_0]
0x14006aa1b  jmp     loc_14006A97A
0x14006aa20  mov     ecx, 3
0x14006aa25  int     29h; Win8: RtlFailFast(ecx)
0x14006aa27  lea     rax, [rsp+38h+DiscardedRequests]
0x14006aa2c  cmp     rdi, rax
0x14006aa2f  jnz     loc_14007EB68
0x14006aa35  jmp     loc_14007EB7E
0x14007eb68  mov     rcx, [rbx+20h]
0x14007eb6c  call    RxDecrementOutstandingBufferingChangesOnFcb
0x14007eb71  mov     rdi, [rdi]
0x14007eb74  lea     rax, [rsp+38h+DiscardedRequests]
0x14007eb79  cmp     rdi, rax
0x14007eb7c  jnz     short loc_14007EB68
0x14007eb7e  lea     rcx, [rsp+38h+DiscardedRequests]; DiscardedRequests
0x14007eb83  call    RxpDiscardChangeBufferingStateRequests
0x14007eb88  nop
0x14007eb89  jmp     loc_14006AA16
```
