# NwifiPendingDirectOidRequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)

- ea: `0x140030e68`
- end: `0x140031031`
- name: `?NwifiPendingDirectOidRequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z`
- size: `457`
- prototype: `void __fastcall(struct _ADAPT *, struct _NDIS_OID_REQUEST *, NDIS_STATUS Status)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140036390`

## callees

- `0x14000a81c`
- `0x1400208f0`
- `0x140030a78`
- `0x140030ac4`
- `0x140030e68`
- `0x1400313cc`
- `0x140031488`
- `0x14003c800`
- `0x14009bbb0`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030f5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030f6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030f6f`
- `NDIS!NdisFDirectOidRequestComplete` at `0x140030feb`
- `NDIS!NdisFDirectOidRequestComplete` at `0x140030feb`
- `NDIS!NdisFreeCloneOidRequest` at `0x140030fd0`
- `NDIS!NdisFreeCloneOidRequest` at `0x140030fd0`

## pseudocode

```c
void __fastcall NwifiPendingDirectOidRequestComplete(
        struct _ADAPT *a1,
        struct _NDIS_OID_REQUEST *a2,
        unsigned int Status)
{
  unsigned int *p_VPortId; // rbx
  void (__fastcall *v7)(struct _ADAPT *, unsigned int *); // rbp
  _VELAN *pActiveVElan; // rbp
  _GUID *p_gDeviceId; // rbp
  int v10; // ecx
  struct _NDIS_OID_REQUEST *v11; // rbp
  PNDIS_OID_REQUEST v12; // rdx
  struct _NDIS_OID_REQUEST *v13; // rdx
  __int128 v14; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)IsNwifiDirectOid(a2->DATA.Oid) )
  {
    p_VPortId = &a2[-1].VPortId;
    if ( p_VPortId )
    {
      if ( (unsigned int)Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline() )
      {
        *p_VPortId = Status;
        v7 = (void (__fastcall *)(struct _ADAPT *, unsigned int *))*((_QWORD *)p_VPortId + 34);
        if ( v7 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids, p_VPortId);
          v7(a1, p_VPortId);
        }
      }
      pActiveVElan = a1->pActiveVElan;
      v14 = 0;
      if ( pActiveVElan )
        p_gDeviceId = &pActiveVElan->gDeviceId;
      else
        p_gDeviceId = (_GUID *)&v14;
      if ( !(unsigned int)Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline() )
        *p_VPortId = Status;
      if ( (byte_1400B2803 & 8) != 0 )
        McTemplateK0pjq_EtwWriteTransfer(
          v10,
          (unsigned int)DirectOidRequestPendingComplete,
          (_DWORD)p_gDeviceId,
          (_DWORD)p_VPortId,
          (__int64)p_gDeviceId,
          *p_VPortId);
      if ( *((_QWORD *)p_VPortId - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)p_VPortId - 2), p_VPortId - 4);
      else
        ExFreePoolWithTag(p_VPortId - 4, *(p_VPortId - 2));
    }
  }
  else
  {
    if ( (unsigned int)Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline() )
    {
      v11 = *(struct _NDIS_OID_REQUEST **)a2->SourceReserved;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_qDq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids);
      CopyOidRequestDataInformationToOriginal(v11, a2);
      NdisFreeCloneOidRequest(a1->hBinding, v12);
      v13 = v11;
    }
    else
    {
      v13 = a2;
    }
    NdisFDirectOidRequestComplete(a1->hBinding, v13, Status);
  }
  _InterlockedDecrement((volatile signed __int32 *)&a1->uOutstandingRequests);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&a1->RefCount, 0xFFFFFFFF) == 1 )
    PtDestroyAdapter(a1);
}

```

## disassembly

```asm
0x140030e68  mov     [rsp+arg_18], rbx
0x140030e6d  push    rbp
0x140030e6e  push    rsi
0x140030e6f  push    rdi
0x140030e70  sub     rsp, 50h
0x140030e74  mov     rax, cs:__security_cookie
0x140030e7b  xor     rax, rsp
0x140030e7e  mov     [rsp+68h+var_28], rax
0x140030e83  mov     rdi, rcx
0x140030e86  mov     esi, r8d
0x140030e89  mov     ecx, [rdx+20h]; unsigned int
0x140030e8c  mov     rbx, rdx
0x140030e8f  call    ?IsNwifiDirectOid@@YAHK@Z; IsNwifiDirectOid(ulong)
0x140030e94  test    eax, eax
0x140030e96  jz      loc_140030F7D
0x140030e9c  add     rbx, 0FFFFFFFFFFFFFFF8h
0x140030ea0  jz      loc_140030FF7
0x140030ea6  call    Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline
0x140030eab  test    eax, eax
0x140030ead  jz      short loc_140030EF6
0x140030eaf  mov     [rbx], esi
0x140030eb1  mov     rbp, [rbx+110h]
0x140030eb8  test    rbp, rbp
0x140030ebb  jz      short loc_140030EF6
0x140030ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ec4  lea     rax, WPP_GLOBAL_Control
0x140030ecb  cmp     rcx, rax
0x140030ece  jz      short loc_140030EE8
0x140030ed0  mov     rcx, [rcx+18h]
0x140030ed4  lea     r8, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids
0x140030edb  mov     edx, 0Ah
0x140030ee0  mov     r9, rbx
0x140030ee3  call    WPP_SF_q
0x140030ee8  mov     rdx, rbx
0x140030eeb  mov     rcx, rdi
0x140030eee  mov     rax, rbp
0x140030ef1  call    _guard_dispatch_icall
0x140030ef6  mov     rbp, [rdi+80h]
0x140030efd  xorps   xmm0, xmm0
0x140030f00  movups  [rsp+68h+var_38], xmm0
0x140030f05  test    rbp, rbp
0x140030f08  jz      short loc_140030F13
0x140030f0a  add     rbp, 1338h
0x140030f11  jmp     short loc_140030F18
0x140030f13  lea     rbp, [rsp+68h+var_38]
0x140030f18  call    Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline
0x140030f1d  test    eax, eax
0x140030f1f  jnz     short loc_140030F23
0x140030f21  mov     [rbx], esi
0x140030f23  test    cs:byte_1400B2803, 8
0x140030f2a  jz      short loc_140030F49
0x140030f2c  mov     eax, [rbx]
0x140030f2e  lea     rdx, DirectOidRequestPendingComplete
0x140030f35  mov     dword ptr [rsp+68h+var_40], eax
0x140030f39  mov     r9, rbx
0x140030f3c  mov     r8, rbp
0x140030f3f  mov     [rsp+68h+var_48], rbp
0x140030f44  call    McTemplateK0pjq_EtwWriteTransfer
0x140030f49  lea     rcx, [rbx-10h]; P
0x140030f4d  mov     rax, [rcx]
0x140030f50  test    rax, rax
0x140030f53  jz      short loc_140030F6C
0x140030f55  mov     rdx, rcx; Entry
0x140030f58  mov     rcx, rax; Lookaside
0x140030f5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140030f62  nop     dword ptr [rax+rax+00h]
0x140030f67  jmp     loc_140030FF7
0x140030f6c  mov     edx, [rcx+8]; Tag
0x140030f6f  call    cs:__imp_ExFreePoolWithTag
0x140030f76  nop     dword ptr [rax+rax+00h]
0x140030f7b  jmp     short loc_140030FF7
0x140030f7d  call    Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline
0x140030f82  test    eax, eax
0x140030f84  jz      short loc_140030FE1
0x140030f86  mov     rbp, [rbx+0D8h]
0x140030f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f94  lea     rax, WPP_GLOBAL_Control
0x140030f9b  cmp     rcx, rax
0x140030f9e  jz      short loc_140030FC1
0x140030fa0  mov     rcx, [rcx+18h]
0x140030fa4  lea     r8, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids
0x140030fab  mov     edx, 0Bh
0x140030fb0  mov     [rsp+68h+var_40], rbp
0x140030fb5  mov     r9, rbx
0x140030fb8  mov     dword ptr [rsp+68h+var_48], esi
0x140030fbc  call    WPP_SF_qDq
0x140030fc1  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140030fc4  mov     rcx, rbp; struct _NDIS_OID_REQUEST *
0x140030fc7  call    ?CopyOidRequestDataInformationToOriginal@@YAXPEAU_NDIS_OID_REQUEST@@0@Z; CopyOidRequestDataInformationToOriginal(_NDIS_OID_REQUEST *,_NDIS_OID_REQUEST *)
0x140030fcc  mov     rcx, [rdi+50h]; SourceHandle
0x140030fd0  call    cs:__imp_NdisFreeCloneOidRequest
0x140030fd7  nop     dword ptr [rax+rax+00h]
0x140030fdc  mov     rdx, rbp
0x140030fdf  jmp     short loc_140030FE4
0x140030fe1  mov     rdx, rbx; OidRequest
0x140030fe4  mov     rcx, [rdi+50h]; NdisFilterHandle
0x140030fe8  mov     r8d, esi; Status
0x140030feb  call    cs:__imp_NdisFDirectOidRequestComplete
0x140030ff2  nop     dword ptr [rax+rax+00h]
0x140030ff7  lock dec dword ptr [rdi+0F0h]
0x140030ffe  or      eax, 0FFFFFFFFh
0x140031001  lock xadd [rdi+10h], eax
0x140031006  cmp     eax, 1
0x140031009  jnz     short loc_140031013
0x14003100b  mov     rcx, rdi; struct _ADAPT *
0x14003100e  call    ?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z; PtDestroyAdapter(_ADAPT *)
0x140031013  mov     rcx, [rsp+68h+var_28]
0x140031018  xor     rcx, rsp; StackCookie
0x14003101b  call    __security_check_cookie
0x140031020  mov     rbx, [rsp+68h+arg_18]
0x140031028  add     rsp, 50h
0x14003102c  pop     rdi
0x14003102d  pop     rsi
0x14003102e  pop     rbp
0x14003102f  retn
```
