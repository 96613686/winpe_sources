# ExtSTARequestAsyncRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *)

- ea: `0x1400695dc`
- end: `0x1400697be`
- name: `?ExtSTARequestAsyncRsnRekeyOffload@@YAHPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, struct DOT11_RSN_REKEY_PARAMETERS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140068be0`

## callees

- `0x14000d22c`
- `0x1400160e0`
- `0x14001651c`
- `0x14001a320`
- `0x140020dc0`
- `0x140068af4`
- `0x1400695dc`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400695f8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400695f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069690`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400696bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069690`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400696bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696d1`

## pseudocode

```c
__int64 __fastcall ExtSTARequestAsyncRsnRekeyOffload(struct EXTSTA_VELAN *a1, struct DOT11_RSN_REKEY_PARAMETERS *a2)
{
  char *v4; // rax
  ULONG *v5; // rbx
  void *v6; // rbp
  unsigned int v7; // esi
  ULONG *p_pCompletion; // rcx
  struct DOT11_NDIS_REQUEST *v10; // rsi
  unsigned int v11; // ebx
  void *v12; // [rsp+38h] [rbp-20h]
  int v13; // [rsp+70h] [rbp+18h] BYREF
  struct DOT11_NDIS_REQUEST *v14; // [rsp+78h] [rbp+20h] BYREF

  v4 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
  v5 = (ULONG *)v4;
  if ( !v4 )
    return 3221225626LL;
  *(_QWORD *)v4 = &Lookaside;
  v6 = v4 + 16;
  *((_DWORD *)v4 + 2) = 845771639;
  CreateRsnRekeyOffload(a1, a2, (struct _NDIS_PM_PROTOCOL_OFFLOAD *)(v4 + 16));
  v14 = 0;
  v13 = Dot11AllocAndBuildNdisRequest(&v14, 1u, 0xFD01010D, 0x100u, v6, ExtSTAGTKReKeyOffloadCompletion, a1, v12);
  v7 = v13;
  if ( v13 )
  {
    if ( v14 )
    {
      p_pCompletion = (ULONG *)&v14[-1].pCompletion;
      if ( v14[-1].pCompletion )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_pCompletion, p_pCompletion);
      else
        ExFreePoolWithTag(p_pCompletion, p_pCompletion[2]);
    }
    if ( v6 )
    {
      if ( *(_QWORD *)v5 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v5, v5);
      else
        ExFreePoolWithTag(v5, v5[2]);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, v7);
    return v7;
  }
  else
  {
    v10 = v14;
    Dot11Request(&v13, a1->pGenVElan->pAdapt, v14->Request);
    v11 = v13;
    if ( v13 == 259 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids,
          (unsigned int)v13);
      Dot11RequestComplete(a1->pGenVElan->pAdapt, v10->Request, v11);
    }
    return v11;
  }
}

```

## disassembly

```asm
0x1400695dc  mov     [rsp+arg_0], rbx
0x1400695e1  push    rbp
0x1400695e2  push    rsi
0x1400695e3  push    rdi
0x1400695e4  sub     rsp, 40h
0x1400695e8  mov     rdi, rcx
0x1400695eb  lea     rbp, Lookaside
0x1400695f2  mov     rcx, rbp; Lookaside
0x1400695f5  mov     rsi, rdx
0x1400695f8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400695ff  nop     dword ptr [rax+rax+00h]
0x140069604  mov     rbx, rax
0x140069607  test    rax, rax
0x14006960a  jz      loc_1400697AB
0x140069610  mov     [rax], rbp
0x140069613  mov     rdx, rsi; struct DOT11_RSN_REKEY_PARAMETERS *
0x140069616  lea     rbp, [rax+10h]
0x14006961a  mov     dword ptr [rax+8], 32697377h
0x140069621  mov     r8, rbp; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x140069624  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140069627  call    ?CreateRsnRekeyOffload@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; CreateRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x14006962c  lea     rax, ?ExtSTAGTKReKeyOffloadCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; ExtSTAGTKReKeyOffloadCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140069633  mov     [rsp+58h+var_28], rdi; void *
0x140069638  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14006963d  lea     rcx, [rsp+58h+arg_18]; struct DOT11_NDIS_REQUEST **
0x140069642  mov     edx, 1; unsigned int
0x140069647  mov     [rsp+58h+var_38], rbp; void *
0x14006964c  mov     r9d, 100h; unsigned int
0x140069652  mov     [rsp+58h+arg_18], 0
0x14006965b  mov     r8d, 0FD01010Dh; unsigned int
0x140069661  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140069666  mov     [rsp+58h+arg_10], eax
0x14006966a  mov     esi, eax
0x14006966c  test    eax, eax
0x14006966e  jz      loc_14006970F
0x140069674  mov     rcx, [rsp+58h+arg_18]
0x140069679  test    rcx, rcx
0x14006967c  jz      short loc_1400696AD
0x14006967e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140069682  mov     rax, [rcx]
0x140069685  test    rax, rax
0x140069688  jz      short loc_14006969E
0x14006968a  mov     rdx, rcx; Entry
0x14006968d  mov     rcx, rax; Lookaside
0x140069690  call    cs:__imp_ExFreeToNPagedLookasideList
0x140069697  nop     dword ptr [rax+rax+00h]
0x14006969c  jmp     short loc_1400696AD
0x14006969e  mov     edx, [rcx+8]; Tag
0x1400696a1  call    cs:__imp_ExFreePoolWithTag
0x1400696a8  nop     dword ptr [rax+rax+00h]
0x1400696ad  test    rbp, rbp
0x1400696b0  jz      short loc_1400696DD
0x1400696b2  mov     rcx, [rbx]; Lookaside
0x1400696b5  test    rcx, rcx
0x1400696b8  jz      short loc_1400696CB
0x1400696ba  mov     rdx, rbx; Entry
0x1400696bd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400696c4  nop     dword ptr [rax+rax+00h]
0x1400696c9  jmp     short loc_1400696DD
0x1400696cb  mov     edx, [rbx+8]; Tag
0x1400696ce  mov     rcx, rbx; P
0x1400696d1  call    cs:__imp_ExFreePoolWithTag
0x1400696d8  nop     dword ptr [rax+rax+00h]
0x1400696dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400696e4  lea     rax, WPP_GLOBAL_Control
0x1400696eb  cmp     rcx, rax
0x1400696ee  jz      short loc_140069708
0x1400696f0  mov     rcx, [rcx+18h]
0x1400696f4  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x1400696fb  mov     edx, 21h ; '!'
0x140069700  mov     r9d, esi
0x140069703  call    WPP_SF_d
0x140069708  mov     eax, esi
0x14006970a  jmp     loc_1400697B0
0x14006970f  mov     rdx, [rdi+0A38h]
0x140069716  lea     rcx, [rsp+58h+arg_10]; int *
0x14006971b  mov     rsi, [rsp+58h+arg_18]
0x140069720  mov     rdx, [rdx+10h]; struct _ADAPT *
0x140069724  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140069728  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14006972d  mov     ebx, [rsp+58h+arg_10]
0x140069731  cmp     ebx, 103h
0x140069737  jz      short loc_14006977D
0x140069739  mov     rcx, cs:WPP_GLOBAL_Control
0x140069740  lea     rax, WPP_GLOBAL_Control
0x140069747  cmp     rcx, rax
0x14006974a  jz      short loc_140069764
0x14006974c  mov     rcx, [rcx+18h]
0x140069750  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069757  mov     edx, 22h ; '"'
0x14006975c  mov     r9d, ebx
0x14006975f  call    WPP_SF_d
0x140069764  mov     rcx, [rdi+0A38h]
0x14006976b  mov     r8d, ebx; int
0x14006976e  mov     rdx, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140069772  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140069776  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14006977b  jmp     short loc_1400697A7
0x14006977d  mov     rcx, cs:WPP_GLOBAL_Control
0x140069784  lea     rax, WPP_GLOBAL_Control
0x14006978b  cmp     rcx, rax
0x14006978e  jz      short loc_1400697A5
0x140069790  mov     rcx, [rcx+18h]
0x140069794  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006979b  mov     edx, 23h ; '#'
0x1400697a0  call    WPP_SF_
0x1400697a5  xor     ebx, ebx
0x1400697a7  mov     eax, ebx
0x1400697a9  jmp     short loc_1400697B0
0x1400697ab  mov     eax, 0C000009Ah
0x1400697b0  mov     rbx, [rsp+58h+arg_0]
0x1400697b5  add     rsp, 40h
0x1400697b9  pop     rdi
0x1400697ba  pop     rsi
0x1400697bb  pop     rbp
0x1400697bc  retn
```
