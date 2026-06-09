# ExtAPScanCompletion(_ADAPT *,int,void *,_EXTAP_VELAN *,_EXTAP_SCAN_CONTEXT *)

- ea: `0x140070ed0`
- end: `0x140071007`
- name: `?ExtAPScanCompletion@@YAXPEAU_ADAPT@@HPEAXPEAU_EXTAP_VELAN@@PEAU_EXTAP_SCAN_CONTEXT@@@Z`
- size: `311`
- prototype: `void __fastcall(struct _ADAPT *, int, void *, struct _EXTAP_VELAN *, struct _EXTAP_SCAN_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006e938`

## callees

- `0x14000d22c`
- `0x140070ed0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140070f5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140070fae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140070f5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140070fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070f6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070fbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070f6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070fbf`
- `ntoskrnl!IofCompleteRequest` at `0x140070f8e`
- `ntoskrnl!IofCompleteRequest` at `0x140070f8e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140070f0e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140070f0e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070f3d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070fcf`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070f3d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140070fcf`

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
0x140070ed0  push    rbx
0x140070ed2  push    rsi
0x140070ed3  push    rdi
0x140070ed4  push    r14
0x140070ed6  sub     rsp, 38h
0x140070eda  mov     esi, edx
0x140070edc  mov     [rsp+58h+Irql], 0
0x140070ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x140070ee8  lea     r14, WPP_GLOBAL_Control
0x140070eef  cmp     rcx, r14
0x140070ef2  jz      short loc_140070F09
0x140070ef4  mov     rcx, [rcx+18h]
0x140070ef8  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x140070eff  mov     edx, 6Bh ; 'k'
0x140070f04  call    WPP_SF_
0x140070f09  lea     rcx, [rsp+58h+Irql]; Irql
0x140070f0e  call    cs:__imp_IoAcquireCancelSpinLock
0x140070f15  nop     dword ptr [rax+rax+00h]
0x140070f1a  mov     rdi, [rsp+58h+arg_20]
0x140070f22  mov     rbx, [rdi]
0x140070f25  test    rbx, rbx
0x140070f28  jz      short loc_140070F9C
0x140070f2a  cmp     qword ptr [rbx+78h], 0
0x140070f2f  jz      short loc_140070F9C
0x140070f31  mov     qword ptr [rbx+78h], 0
0x140070f39  mov     cl, [rsp+58h+Irql]; Irql
0x140070f3d  call    cs:__imp_IoReleaseCancelSpinLock
0x140070f44  nop     dword ptr [rax+rax+00h]
0x140070f49  lea     rcx, [rdi-10h]; P
0x140070f4d  mov     rax, [rcx]
0x140070f50  test    rax, rax
0x140070f53  jz      short loc_140070F69
0x140070f55  mov     rdx, rcx; Entry
0x140070f58  mov     rcx, rax; Lookaside
0x140070f5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140070f62  nop     dword ptr [rax+rax+00h]
0x140070f67  jmp     short loc_140070F78
0x140070f69  mov     edx, [rcx+8]; Tag
0x140070f6c  call    cs:__imp_ExFreePoolWithTag
0x140070f73  nop     dword ptr [rax+rax+00h]
0x140070f78  xor     eax, eax
0x140070f7a  mov     [rbx+30h], esi
0x140070f7d  mov     qword ptr [rbx+38h], 0
0x140070f85  mov     dl, 2; PriorityBoost
0x140070f87  xchg    rax, [rbx+68h]
0x140070f8b  mov     rcx, rbx; Irp
0x140070f8e  call    cs:__imp_IofCompleteRequest
0x140070f95  nop     dword ptr [rax+rax+00h]
0x140070f9a  jmp     short loc_140070FDB
0x140070f9c  lea     rcx, [rdi-10h]; P
0x140070fa0  mov     rax, [rcx]
0x140070fa3  test    rax, rax
0x140070fa6  jz      short loc_140070FBC
0x140070fa8  mov     rdx, rcx; Entry
0x140070fab  mov     rcx, rax; Lookaside
0x140070fae  call    cs:__imp_ExFreeToNPagedLookasideList
0x140070fb5  nop     dword ptr [rax+rax+00h]
0x140070fba  jmp     short loc_140070FCB
0x140070fbc  mov     edx, [rcx+8]; Tag
0x140070fbf  call    cs:__imp_ExFreePoolWithTag
0x140070fc6  nop     dword ptr [rax+rax+00h]
0x140070fcb  mov     cl, [rsp+58h+Irql]; Irql
0x140070fcf  call    cs:__imp_IoReleaseCancelSpinLock
0x140070fd6  nop     dword ptr [rax+rax+00h]
0x140070fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140070fe2  cmp     rcx, r14
0x140070fe5  jz      short loc_140070FFC
0x140070fe7  mov     rcx, [rcx+18h]
0x140070feb  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x140070ff2  mov     edx, 6Ch ; 'l'
0x140070ff7  call    WPP_SF_
0x140070ffc  add     rsp, 38h
0x140071000  pop     r14
0x140071002  pop     rdi
0x140071003  pop     rsi
0x140071004  pop     rbx
0x140071005  retn
```
