# ExtSTARequestAsyncRemoveGTKReKeyOffload(EXTSTA_VELAN *,ulong)

- ea: `0x1400693fc`
- end: `0x1400695d5`
- name: `?ExtSTARequestAsyncRemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@K@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140068f14`
- `0x140069274`

## callees

- `0x1400160e0`
- `0x14001651c`
- `0x14001a320`
- `0x140020dc0`
- `0x140020f20`
- `0x1400693fc`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140069417`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140069417`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400694a1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400694c9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400694a1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400694c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400694b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400694dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400694b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400694dd`

## pseudocode

```c
__int64 __fastcall ExtSTARequestAsyncRemoveGTKReKeyOffload(struct EXTSTA_VELAN *a1, unsigned int a2)
{
  PNPAGED_LOOKASIDE_LIST *v4; // rax
  PNPAGED_LOOKASIDE_LIST *v5; // rbx
  unsigned int v6; // ebp
  ULONG *p_pCompletion; // rcx
  struct DOT11_NDIS_REQUEST *v9; // rbp
  unsigned int v10; // ebx
  void *v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+70h] [rbp+18h] BYREF
  struct DOT11_NDIS_REQUEST *v13; // [rsp+78h] [rbp+20h] BYREF

  v4 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
  v5 = v4;
  if ( !v4 )
    return 3221225626LL;
  *v4 = (PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue;
  *((_DWORD *)v4 + 2) = 845771639;
  *((_DWORD *)v4 + 4) = a2;
  v13 = 0;
  v12 = Dot11AllocAndBuildNdisRequest(
          &v13,
          1u,
          0xFD01010F,
          4u,
          v4 + 2,
          ExtSTARemoveGTKReKeyParametersCompletion,
          a1,
          v11);
  v6 = v12;
  if ( v12 )
  {
    if ( v13 )
    {
      p_pCompletion = (ULONG *)&v13[-1].pCompletion;
      if ( v13[-1].pCompletion )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_pCompletion, p_pCompletion);
      else
        ExFreePoolWithTag(p_pCompletion, p_pCompletion[2]);
    }
    if ( *v5 )
      ExFreeToNPagedLookasideList(*v5, v5);
    else
      ExFreePoolWithTag(v5, *((_DWORD *)v5 + 2));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, a2, v6);
    return v6;
  }
  else
  {
    v9 = v13;
    Dot11Request(&v12, a1->pGenVElan->pAdapt, v13->Request);
    v10 = v12;
    if ( v12 == 259 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, a2);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, a2, v12);
      Dot11RequestComplete(a1->pGenVElan->pAdapt, v9->Request, v10);
    }
    return v10;
  }
}

```

## disassembly

```asm
0x1400693fc  mov     [rsp+arg_0], rbx
0x140069401  push    rbp
0x140069402  push    rsi
0x140069403  push    rdi
0x140069404  sub     rsp, 40h
0x140069408  mov     rsi, rcx
0x14006940b  lea     rbp, WPP_MAIN_CB.DeviceQueue
0x140069412  mov     rcx, rbp; Lookaside
0x140069415  mov     edi, edx
0x140069417  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006941e  nop     dword ptr [rax+rax+00h]
0x140069423  mov     rbx, rax
0x140069426  test    rax, rax
0x140069429  jz      loc_1400695C2
0x14006942f  lea     rdx, [rax+10h]
0x140069433  mov     [rax], rbp
0x140069436  mov     dword ptr [rax+8], 32697377h
0x14006943d  lea     rcx, [rsp+58h+arg_18]; struct DOT11_NDIS_REQUEST **
0x140069442  lea     rax, ?ExtSTARemoveGTKReKeyParametersCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; ExtSTARemoveGTKReKeyParametersCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140069449  mov     [rsp+58h+var_28], rsi; void *
0x14006944e  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x140069453  mov     r8d, 0FD01010Fh; unsigned int
0x140069459  mov     [rsp+58h+var_38], rdx; void *
0x14006945e  mov     [rdx], edi
0x140069460  mov     edx, 1; unsigned int
0x140069465  mov     [rsp+58h+arg_18], 0
0x14006946e  lea     r9d, [rdx+3]; unsigned int
0x140069472  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140069477  mov     [rsp+58h+arg_10], eax
0x14006947b  mov     ebp, eax
0x14006947d  test    eax, eax
0x14006947f  jz      loc_14006951F
0x140069485  mov     rcx, [rsp+58h+arg_18]
0x14006948a  test    rcx, rcx
0x14006948d  jz      short loc_1400694BE
0x14006948f  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140069493  mov     rax, [rcx]
0x140069496  test    rax, rax
0x140069499  jz      short loc_1400694AF
0x14006949b  mov     rdx, rcx; Entry
0x14006949e  mov     rcx, rax; Lookaside
0x1400694a1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400694a8  nop     dword ptr [rax+rax+00h]
0x1400694ad  jmp     short loc_1400694BE
0x1400694af  mov     edx, [rcx+8]; Tag
0x1400694b2  call    cs:__imp_ExFreePoolWithTag
0x1400694b9  nop     dword ptr [rax+rax+00h]
0x1400694be  mov     rcx, [rbx]; Lookaside
0x1400694c1  test    rcx, rcx
0x1400694c4  jz      short loc_1400694D7
0x1400694c6  mov     rdx, rbx; Entry
0x1400694c9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400694d0  nop     dword ptr [rax+rax+00h]
0x1400694d5  jmp     short loc_1400694E9
0x1400694d7  mov     edx, [rbx+8]; Tag
0x1400694da  mov     rcx, rbx; P
0x1400694dd  call    cs:__imp_ExFreePoolWithTag
0x1400694e4  nop     dword ptr [rax+rax+00h]
0x1400694e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400694f0  lea     rax, WPP_GLOBAL_Control
0x1400694f7  cmp     rcx, rax
0x1400694fa  jz      short loc_140069518
0x1400694fc  mov     rcx, [rcx+18h]
0x140069500  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069507  mov     edx, 0Bh
0x14006950c  mov     dword ptr [rsp+58h+var_38], ebp
0x140069510  mov     r9d, edi
0x140069513  call    WPP_SF_Dd
0x140069518  mov     eax, ebp
0x14006951a  jmp     loc_1400695C7
0x14006951f  mov     rdx, [rsi+0A38h]
0x140069526  lea     rcx, [rsp+58h+arg_10]; int *
0x14006952b  mov     rbp, [rsp+58h+arg_18]
0x140069530  mov     rdx, [rdx+10h]; struct _ADAPT *
0x140069534  mov     r8, [rbp+8]; struct _NDIS_OID_REQUEST *
0x140069538  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14006953d  mov     ebx, [rsp+58h+arg_10]
0x140069541  cmp     ebx, 103h
0x140069547  jz      short loc_140069591
0x140069549  mov     rcx, cs:WPP_GLOBAL_Control
0x140069550  lea     rax, WPP_GLOBAL_Control
0x140069557  cmp     rcx, rax
0x14006955a  jz      short loc_140069578
0x14006955c  mov     rcx, [rcx+18h]
0x140069560  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069567  mov     edx, 0Ch
0x14006956c  mov     dword ptr [rsp+58h+var_38], ebx
0x140069570  mov     r9d, edi
0x140069573  call    WPP_SF_Dd
0x140069578  mov     rcx, [rsi+0A38h]
0x14006957f  mov     r8d, ebx; int
0x140069582  mov     rdx, [rbp+8]; struct _NDIS_OID_REQUEST *
0x140069586  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006958a  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14006958f  jmp     short loc_1400695BE
0x140069591  mov     rcx, cs:WPP_GLOBAL_Control
0x140069598  lea     rax, WPP_GLOBAL_Control
0x14006959f  cmp     rcx, rax
0x1400695a2  jz      short loc_1400695BC
0x1400695a4  mov     rcx, [rcx+18h]
0x1400695a8  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x1400695af  mov     edx, 0Dh
0x1400695b4  mov     r9d, edi
0x1400695b7  call    WPP_SF_d
0x1400695bc  xor     ebx, ebx
0x1400695be  mov     eax, ebx
0x1400695c0  jmp     short loc_1400695C7
0x1400695c2  mov     eax, 0C000009Ah
0x1400695c7  mov     rbx, [rsp+58h+arg_0]
0x1400695cc  add     rsp, 40h
0x1400695d0  pop     rdi
0x1400695d1  pop     rsi
0x1400695d2  pop     rbp
0x1400695d3  retn
```
