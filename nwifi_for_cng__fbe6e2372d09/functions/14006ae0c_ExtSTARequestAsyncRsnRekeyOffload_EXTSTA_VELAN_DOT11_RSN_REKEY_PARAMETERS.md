# ExtSTARequestAsyncRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *)

- ea: `0x14006ae0c`
- end: `0x14006afee`
- name: `?ExtSTARequestAsyncRsnRekeyOffload@@YAHPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, struct DOT11_RSN_REKEY_PARAMETERS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006a410`

## callees

- `0x14000d21c`
- `0x1400160d0`
- `0x14001650c`
- `0x14001a320`
- `0x140020dc0`
- `0x14006a324`
- `0x14006ae0c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ae28`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ae28`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006aec0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006aeed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006aec0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006aeed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aed1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006af01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aed1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006af01`

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
0x14006ae0c  mov     [rsp+arg_0], rbx
0x14006ae11  push    rbp
0x14006ae12  push    rsi
0x14006ae13  push    rdi
0x14006ae14  sub     rsp, 40h
0x14006ae18  mov     rdi, rcx
0x14006ae1b  lea     rbp, Lookaside
0x14006ae22  mov     rcx, rbp; Lookaside
0x14006ae25  mov     rsi, rdx
0x14006ae28  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006ae2f  nop     dword ptr [rax+rax+00h]
0x14006ae34  mov     rbx, rax
0x14006ae37  test    rax, rax
0x14006ae3a  jz      loc_14006AFDB
0x14006ae40  mov     [rax], rbp
0x14006ae43  mov     rdx, rsi; struct DOT11_RSN_REKEY_PARAMETERS *
0x14006ae46  lea     rbp, [rax+10h]
0x14006ae4a  mov     dword ptr [rax+8], 32697377h
0x14006ae51  mov     r8, rbp; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x14006ae54  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14006ae57  call    ?CreateRsnRekeyOffload@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; CreateRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x14006ae5c  lea     rax, ?ExtSTAGTKReKeyOffloadCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; ExtSTAGTKReKeyOffloadCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x14006ae63  mov     [rsp+58h+var_28], rdi; void *
0x14006ae68  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14006ae6d  lea     rcx, [rsp+58h+arg_18]; struct DOT11_NDIS_REQUEST **
0x14006ae72  mov     edx, 1; unsigned int
0x14006ae77  mov     [rsp+58h+var_38], rbp; void *
0x14006ae7c  mov     r9d, 100h; unsigned int
0x14006ae82  mov     [rsp+58h+arg_18], 0
0x14006ae8b  mov     r8d, 0FD01010Dh; unsigned int
0x14006ae91  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14006ae96  mov     [rsp+58h+arg_10], eax
0x14006ae9a  mov     esi, eax
0x14006ae9c  test    eax, eax
0x14006ae9e  jz      loc_14006AF3F
0x14006aea4  mov     rcx, [rsp+58h+arg_18]
0x14006aea9  test    rcx, rcx
0x14006aeac  jz      short loc_14006AEDD
0x14006aeae  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14006aeb2  mov     rax, [rcx]
0x14006aeb5  test    rax, rax
0x14006aeb8  jz      short loc_14006AECE
0x14006aeba  mov     rdx, rcx; Entry
0x14006aebd  mov     rcx, rax; Lookaside
0x14006aec0  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006aec7  nop     dword ptr [rax+rax+00h]
0x14006aecc  jmp     short loc_14006AEDD
0x14006aece  mov     edx, [rcx+8]; Tag
0x14006aed1  call    cs:__imp_ExFreePoolWithTag
0x14006aed8  nop     dword ptr [rax+rax+00h]
0x14006aedd  test    rbp, rbp
0x14006aee0  jz      short loc_14006AF0D
0x14006aee2  mov     rcx, [rbx]; Lookaside
0x14006aee5  test    rcx, rcx
0x14006aee8  jz      short loc_14006AEFB
0x14006aeea  mov     rdx, rbx; Entry
0x14006aeed  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006aef4  nop     dword ptr [rax+rax+00h]
0x14006aef9  jmp     short loc_14006AF0D
0x14006aefb  mov     edx, [rbx+8]; Tag
0x14006aefe  mov     rcx, rbx; P
0x14006af01  call    cs:__imp_ExFreePoolWithTag
0x14006af08  nop     dword ptr [rax+rax+00h]
0x14006af0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006af14  lea     rax, WPP_GLOBAL_Control
0x14006af1b  cmp     rcx, rax
0x14006af1e  jz      short loc_14006AF38
0x14006af20  mov     rcx, [rcx+18h]
0x14006af24  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006af2b  mov     edx, 21h ; '!'
0x14006af30  mov     r9d, esi
0x14006af33  call    WPP_SF_d
0x14006af38  mov     eax, esi
0x14006af3a  jmp     loc_14006AFE0
0x14006af3f  mov     rdx, [rdi+0A38h]
0x14006af46  lea     rcx, [rsp+58h+arg_10]; int *
0x14006af4b  mov     rsi, [rsp+58h+arg_18]
0x14006af50  mov     rdx, [rdx+10h]; struct _ADAPT *
0x14006af54  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x14006af58  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14006af5d  mov     ebx, [rsp+58h+arg_10]
0x14006af61  cmp     ebx, 103h
0x14006af67  jz      short loc_14006AFAD
0x14006af69  mov     rcx, cs:WPP_GLOBAL_Control
0x14006af70  lea     rax, WPP_GLOBAL_Control
0x14006af77  cmp     rcx, rax
0x14006af7a  jz      short loc_14006AF94
0x14006af7c  mov     rcx, [rcx+18h]
0x14006af80  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006af87  mov     edx, 22h ; '"'
0x14006af8c  mov     r9d, ebx
0x14006af8f  call    WPP_SF_d
0x14006af94  mov     rcx, [rdi+0A38h]
0x14006af9b  mov     r8d, ebx; int
0x14006af9e  mov     rdx, [rsi+8]; struct _NDIS_OID_REQUEST *
0x14006afa2  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006afa6  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14006afab  jmp     short loc_14006AFD7
0x14006afad  mov     rcx, cs:WPP_GLOBAL_Control
0x14006afb4  lea     rax, WPP_GLOBAL_Control
0x14006afbb  cmp     rcx, rax
0x14006afbe  jz      short loc_14006AFD5
0x14006afc0  mov     rcx, [rcx+18h]
0x14006afc4  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006afcb  mov     edx, 23h ; '#'
0x14006afd0  call    WPP_SF_
0x14006afd5  xor     ebx, ebx
0x14006afd7  mov     eax, ebx
0x14006afd9  jmp     short loc_14006AFE0
0x14006afdb  mov     eax, 0C000009Ah
0x14006afe0  mov     rbx, [rsp+58h+arg_0]
0x14006afe5  add     rsp, 40h
0x14006afe9  pop     rdi
0x14006afea  pop     rsi
0x14006afeb  pop     rbp
0x14006afec  retn
```
