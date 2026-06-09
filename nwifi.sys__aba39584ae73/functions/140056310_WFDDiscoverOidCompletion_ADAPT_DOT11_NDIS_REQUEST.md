# WFDDiscoverOidCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)

- ea: `0x140056310`
- end: `0x140056400`
- name: `?WFDDiscoverOidCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z`
- size: `240`
- prototype: `void __fastcall(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140055ee0`
- `0x140056310`
- `0x14009bbb0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056363`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056392`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056363`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056392`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056374`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400563a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056374`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400563a3`

## pseudocode

```c
void __fastcall WFDDiscoverOidCompletion(struct _ADAPT *a1, struct DOT11_NDIS_REQUEST *a2)
{
  int ndisStatus; // ebx
  char *pvContext1; // rcx
  ULONG *v6; // rcx
  _BYTE v7[24]; // [rsp+20h] [rbp-28h] BYREF

  ndisStatus = a2->ndisStatus;
  memset(v7, 0, sizeof(v7));
  pvContext1 = (char *)a2->pvContext1;
  if ( pvContext1 )
  {
    v6 = (ULONG *)(pvContext1 - 16);
    if ( *(_QWORD *)v6 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, v6);
    else
      ExFreePoolWithTag(v6, v6[2]);
  }
  if ( a2[-1].pCompletion )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a2[-1].pCompletion, &a2[-1].pCompletion);
  else
    ExFreePoolWithTag(&a2[-1].pCompletion, (ULONG)a2[-1].pVElan);
  if ( ndisStatus )
  {
    if ( ndisStatus != 1076035585 )
    {
      *(_DWORD *)v7 = 1573248;
      *(_DWORD *)&v7[4] = ndisStatus;
      *(_OWORD *)&v7[8] = 0;
      WFDDiscoverCompletion(a1, (struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *)v7, 24);
    }
  }
}

```

## disassembly

```asm
0x140056310  mov     [rsp+arg_10], rbx
0x140056315  mov     [rsp+arg_18], rsi
0x14005631a  push    rdi
0x14005631b  sub     rsp, 40h
0x14005631f  mov     rax, cs:__security_cookie
0x140056326  xor     rax, rsp
0x140056329  mov     [rsp+48h+var_10], rax
0x14005632e  mov     ebx, [rdx]
0x140056330  xor     eax, eax
0x140056332  xorps   xmm0, xmm0
0x140056335  mov     [rsp+48h+var_18], rax
0x14005633a  movups  [rsp+48h+var_28], xmm0
0x14005633f  mov     rsi, rcx
0x140056342  mov     rdi, rdx
0x140056345  mov     rcx, [rdx+110h]
0x14005634c  test    rcx, rcx
0x14005634f  jz      short loc_140056380
0x140056351  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140056355  mov     rax, [rcx]
0x140056358  test    rax, rax
0x14005635b  jz      short loc_140056371
0x14005635d  mov     rdx, rcx; Entry
0x140056360  mov     rcx, rax; Lookaside
0x140056363  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005636a  nop     dword ptr [rax+rax+00h]
0x14005636f  jmp     short loc_140056380
0x140056371  mov     edx, [rcx+8]; Tag
0x140056374  call    cs:__imp_ExFreePoolWithTag
0x14005637b  nop     dword ptr [rax+rax+00h]
0x140056380  lea     rcx, [rdi-10h]; P
0x140056384  mov     rax, [rcx]
0x140056387  test    rax, rax
0x14005638a  jz      short loc_1400563A0
0x14005638c  mov     rdx, rcx; Entry
0x14005638f  mov     rcx, rax; Lookaside
0x140056392  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056399  nop     dword ptr [rax+rax+00h]
0x14005639e  jmp     short loc_1400563AF
0x1400563a0  mov     edx, [rcx+8]; Tag
0x1400563a3  call    cs:__imp_ExFreePoolWithTag
0x1400563aa  nop     dword ptr [rax+rax+00h]
0x1400563af  test    ebx, ebx
0x1400563b1  jz      short loc_1400563E2
0x1400563b3  cmp     ebx, 40230001h
0x1400563b9  jz      short loc_1400563E2
0x1400563bb  xorps   xmm0, xmm0
0x1400563be  mov     dword ptr [rsp+48h+var_28], 180180h
0x1400563c6  mov     r8d, 18h; unsigned int
0x1400563cc  mov     dword ptr [rsp+48h+var_28+4], ebx
0x1400563d0  lea     rdx, [rsp+48h+var_28]; struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *
0x1400563d5  mov     rcx, rsi; struct _ADAPT *
0x1400563d8  movups  [rsp+48h+var_28+8], xmm0
0x1400563dd  call    ?WFDDiscoverCompletion@@YAXPEAU_ADAPT@@PEAU_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS@@KH@Z; WFDDiscoverCompletion(_ADAPT *,_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *,ulong,int)
0x1400563e2  mov     rcx, [rsp+48h+var_10]
0x1400563e7  xor     rcx, rsp; StackCookie
0x1400563ea  call    __security_check_cookie
0x1400563ef  mov     rbx, [rsp+48h+arg_10]
0x1400563f4  mov     rsi, [rsp+48h+arg_18]
0x1400563f9  add     rsp, 40h
0x1400563fd  pop     rdi
0x1400563fe  retn
```
