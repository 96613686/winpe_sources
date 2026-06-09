# ExtSTARequestAsyncRemoveGTKReKeyOffload(EXTSTA_VELAN *,ulong)

- ea: `0x14006ac2c`
- end: `0x14006ae05`
- name: `?ExtSTARequestAsyncRemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@K@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006a744`
- `0x14006aaa4`

## callees

- `0x1400160d0`
- `0x14001650c`
- `0x14001a320`
- `0x140020dc0`
- `0x140020f20`
- `0x14006ac2c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ac47`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ac47`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006acd1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006acf9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006acd1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006acf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ace2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ad0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ace2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ad0d`

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
0x14006ac2c  mov     [rsp+arg_0], rbx
0x14006ac31  push    rbp
0x14006ac32  push    rsi
0x14006ac33  push    rdi
0x14006ac34  sub     rsp, 40h
0x14006ac38  mov     rsi, rcx
0x14006ac3b  lea     rbp, WPP_MAIN_CB.DeviceQueue
0x14006ac42  mov     rcx, rbp; Lookaside
0x14006ac45  mov     edi, edx
0x14006ac47  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006ac4e  nop     dword ptr [rax+rax+00h]
0x14006ac53  mov     rbx, rax
0x14006ac56  test    rax, rax
0x14006ac59  jz      loc_14006ADF2
0x14006ac5f  lea     rdx, [rax+10h]
0x14006ac63  mov     [rax], rbp
0x14006ac66  mov     dword ptr [rax+8], 32697377h
0x14006ac6d  lea     rcx, [rsp+58h+arg_18]; struct DOT11_NDIS_REQUEST **
0x14006ac72  lea     rax, ?ExtSTARemoveGTKReKeyParametersCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; ExtSTARemoveGTKReKeyParametersCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x14006ac79  mov     [rsp+58h+var_28], rsi; void *
0x14006ac7e  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14006ac83  mov     r8d, 0FD01010Fh; unsigned int
0x14006ac89  mov     [rsp+58h+var_38], rdx; void *
0x14006ac8e  mov     [rdx], edi
0x14006ac90  mov     edx, 1; unsigned int
0x14006ac95  mov     [rsp+58h+arg_18], 0
0x14006ac9e  lea     r9d, [rdx+3]; unsigned int
0x14006aca2  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14006aca7  mov     [rsp+58h+arg_10], eax
0x14006acab  mov     ebp, eax
0x14006acad  test    eax, eax
0x14006acaf  jz      loc_14006AD4F
0x14006acb5  mov     rcx, [rsp+58h+arg_18]
0x14006acba  test    rcx, rcx
0x14006acbd  jz      short loc_14006ACEE
0x14006acbf  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14006acc3  mov     rax, [rcx]
0x14006acc6  test    rax, rax
0x14006acc9  jz      short loc_14006ACDF
0x14006accb  mov     rdx, rcx; Entry
0x14006acce  mov     rcx, rax; Lookaside
0x14006acd1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006acd8  nop     dword ptr [rax+rax+00h]
0x14006acdd  jmp     short loc_14006ACEE
0x14006acdf  mov     edx, [rcx+8]; Tag
0x14006ace2  call    cs:__imp_ExFreePoolWithTag
0x14006ace9  nop     dword ptr [rax+rax+00h]
0x14006acee  mov     rcx, [rbx]; Lookaside
0x14006acf1  test    rcx, rcx
0x14006acf4  jz      short loc_14006AD07
0x14006acf6  mov     rdx, rbx; Entry
0x14006acf9  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006ad00  nop     dword ptr [rax+rax+00h]
0x14006ad05  jmp     short loc_14006AD19
0x14006ad07  mov     edx, [rbx+8]; Tag
0x14006ad0a  mov     rcx, rbx; P
0x14006ad0d  call    cs:__imp_ExFreePoolWithTag
0x14006ad14  nop     dword ptr [rax+rax+00h]
0x14006ad19  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad20  lea     rax, WPP_GLOBAL_Control
0x14006ad27  cmp     rcx, rax
0x14006ad2a  jz      short loc_14006AD48
0x14006ad2c  mov     rcx, [rcx+18h]
0x14006ad30  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006ad37  mov     edx, 0Bh
0x14006ad3c  mov     dword ptr [rsp+58h+var_38], ebp
0x14006ad40  mov     r9d, edi
0x14006ad43  call    WPP_SF_Dd
0x14006ad48  mov     eax, ebp
0x14006ad4a  jmp     loc_14006ADF7
0x14006ad4f  mov     rdx, [rsi+0A38h]
0x14006ad56  lea     rcx, [rsp+58h+arg_10]; int *
0x14006ad5b  mov     rbp, [rsp+58h+arg_18]
0x14006ad60  mov     rdx, [rdx+10h]; struct _ADAPT *
0x14006ad64  mov     r8, [rbp+8]; struct _NDIS_OID_REQUEST *
0x14006ad68  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14006ad6d  mov     ebx, [rsp+58h+arg_10]
0x14006ad71  cmp     ebx, 103h
0x14006ad77  jz      short loc_14006ADC1
0x14006ad79  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad80  lea     rax, WPP_GLOBAL_Control
0x14006ad87  cmp     rcx, rax
0x14006ad8a  jz      short loc_14006ADA8
0x14006ad8c  mov     rcx, [rcx+18h]
0x14006ad90  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006ad97  mov     edx, 0Ch
0x14006ad9c  mov     dword ptr [rsp+58h+var_38], ebx
0x14006ada0  mov     r9d, edi
0x14006ada3  call    WPP_SF_Dd
0x14006ada8  mov     rcx, [rsi+0A38h]
0x14006adaf  mov     r8d, ebx; int
0x14006adb2  mov     rdx, [rbp+8]; struct _NDIS_OID_REQUEST *
0x14006adb6  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006adba  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x14006adbf  jmp     short loc_14006ADEE
0x14006adc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006adc8  lea     rax, WPP_GLOBAL_Control
0x14006adcf  cmp     rcx, rax
0x14006add2  jz      short loc_14006ADEC
0x14006add4  mov     rcx, [rcx+18h]
0x14006add8  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006addf  mov     edx, 0Dh
0x14006ade4  mov     r9d, edi
0x14006ade7  call    WPP_SF_d
0x14006adec  xor     ebx, ebx
0x14006adee  mov     eax, ebx
0x14006adf0  jmp     short loc_14006ADF7
0x14006adf2  mov     eax, 0C000009Ah
0x14006adf7  mov     rbx, [rsp+58h+arg_0]
0x14006adfc  add     rsp, 40h
0x14006ae00  pop     rdi
0x14006ae01  pop     rsi
0x14006ae02  pop     rbp
0x14006ae03  retn
```
