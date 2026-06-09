# ExtAPScanCompletion(_ADAPT *,int,void *,_EXTAP_VELAN *,_EXTAP_SCAN_CONTEXT *)

- ea: `0x140072700`
- end: `0x140072837`
- name: `?ExtAPScanCompletion@@YAXPEAU_ADAPT@@HPEAXPEAU_EXTAP_VELAN@@PEAU_EXTAP_SCAN_CONTEXT@@@Z`
- size: `311`
- prototype: `void __fastcall(struct _ADAPT *, int, void *, struct _EXTAP_VELAN *, struct _EXTAP_SCAN_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140070168`

## callees

- `0x14000d21c`
- `0x140072700`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007278b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400727de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007278b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400727de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007279c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400727ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007279c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400727ef`
- `ntoskrnl!IofCompleteRequest` at `0x1400727be`
- `ntoskrnl!IofCompleteRequest` at `0x1400727be`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14007273e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14007273e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14007276d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400727ff`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14007276d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400727ff`

## pseudocode

```c
void __fastcall ExtAPScanCompletion(
        struct _ADAPT *a1,
        int a2,
        void *a3,
        struct _EXTAP_VELAN *a4,
        PNPAGED_LOOKASIDE_LIST *a5)
{
  PNPAGED_LOOKASIDE_LIST v6; // rbx
  KIRQL Irql[56]; // [rsp+20h] [rbp-38h] BYREF

  Irql[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
  IoAcquireCancelSpinLock(Irql);
  v6 = *a5;
  if ( *a5 && *(_QWORD *)&v6->L.Future[8] )
  {
    *(_QWORD *)&v6->L.Future[8] = 0;
    IoReleaseCancelSpinLock(Irql[0]);
    if ( *(a5 - 2) )
      ExFreeToNPagedLookasideList(*(a5 - 2), a5 - 2);
    else
      ExFreePoolWithTag(a5 - 2, *((_DWORD *)a5 - 2));
    LODWORD(v6->L.AllocateEx) = a2;
    v6->L.FreeEx = 0;
    _InterlockedExchange64((volatile __int64 *)&v6->L.Future[4], 0);
    IofCompleteRequest((PIRP)v6, 2);
  }
  else
  {
    if ( *(a5 - 2) )
      ExFreeToNPagedLookasideList(*(a5 - 2), a5 - 2);
    else
      ExFreePoolWithTag(a5 - 2, *((_DWORD *)a5 - 2));
    IoReleaseCancelSpinLock(Irql[0]);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
}

```

## disassembly

```asm
0x140072700  push    rbx
0x140072702  push    rsi
0x140072703  push    rdi
0x140072704  push    r14
0x140072706  sub     rsp, 38h
0x14007270a  mov     esi, edx
0x14007270c  mov     [rsp+58h+Irql], 0
0x140072711  mov     rcx, cs:WPP_GLOBAL_Control
0x140072718  lea     r14, WPP_GLOBAL_Control
0x14007271f  cmp     rcx, r14
0x140072722  jz      short loc_140072739
0x140072724  mov     rcx, [rcx+18h]
0x140072728  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14007272f  mov     edx, 6Bh ; 'k'
0x140072734  call    WPP_SF_
0x140072739  lea     rcx, [rsp+58h+Irql]; Irql
0x14007273e  call    cs:__imp_IoAcquireCancelSpinLock
0x140072745  nop     dword ptr [rax+rax+00h]
0x14007274a  mov     rdi, [rsp+58h+arg_20]
0x140072752  mov     rbx, [rdi]
0x140072755  test    rbx, rbx
0x140072758  jz      short loc_1400727CC
0x14007275a  cmp     qword ptr [rbx+78h], 0
0x14007275f  jz      short loc_1400727CC
0x140072761  mov     qword ptr [rbx+78h], 0
0x140072769  mov     cl, [rsp+58h+Irql]; Irql
0x14007276d  call    cs:__imp_IoReleaseCancelSpinLock
0x140072774  nop     dword ptr [rax+rax+00h]
0x140072779  lea     rcx, [rdi-10h]; P
0x14007277d  mov     rax, [rcx]
0x140072780  test    rax, rax
0x140072783  jz      short loc_140072799
0x140072785  mov     rdx, rcx; Entry
0x140072788  mov     rcx, rax; Lookaside
0x14007278b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140072792  nop     dword ptr [rax+rax+00h]
0x140072797  jmp     short loc_1400727A8
0x140072799  mov     edx, [rcx+8]; Tag
0x14007279c  call    cs:__imp_ExFreePoolWithTag
0x1400727a3  nop     dword ptr [rax+rax+00h]
0x1400727a8  xor     eax, eax
0x1400727aa  mov     [rbx+30h], esi
0x1400727ad  mov     qword ptr [rbx+38h], 0
0x1400727b5  mov     dl, 2; PriorityBoost
0x1400727b7  xchg    rax, [rbx+68h]
0x1400727bb  mov     rcx, rbx; Irp
0x1400727be  call    cs:__imp_IofCompleteRequest
0x1400727c5  nop     dword ptr [rax+rax+00h]
0x1400727ca  jmp     short loc_14007280B
0x1400727cc  lea     rcx, [rdi-10h]; P
0x1400727d0  mov     rax, [rcx]
0x1400727d3  test    rax, rax
0x1400727d6  jz      short loc_1400727EC
0x1400727d8  mov     rdx, rcx; Entry
0x1400727db  mov     rcx, rax; Lookaside
0x1400727de  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400727e5  nop     dword ptr [rax+rax+00h]
0x1400727ea  jmp     short loc_1400727FB
0x1400727ec  mov     edx, [rcx+8]; Tag
0x1400727ef  call    cs:__imp_ExFreePoolWithTag
0x1400727f6  nop     dword ptr [rax+rax+00h]
0x1400727fb  mov     cl, [rsp+58h+Irql]; Irql
0x1400727ff  call    cs:__imp_IoReleaseCancelSpinLock
0x140072806  nop     dword ptr [rax+rax+00h]
0x14007280b  mov     rcx, cs:WPP_GLOBAL_Control
0x140072812  cmp     rcx, r14
0x140072815  jz      short loc_14007282C
0x140072817  mov     rcx, [rcx+18h]
0x14007281b  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x140072822  mov     edx, 6Ch ; 'l'
0x140072827  call    WPP_SF_
0x14007282c  add     rsp, 38h
0x140072830  pop     r14
0x140072832  pop     rdi
0x140072833  pop     rsi
0x140072834  pop     rbx
0x140072835  retn
```
