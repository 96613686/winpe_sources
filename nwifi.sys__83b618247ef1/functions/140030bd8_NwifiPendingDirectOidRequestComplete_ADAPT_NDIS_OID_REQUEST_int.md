# NwifiPendingDirectOidRequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)

- ea: `0x140030bd8`
- end: `0x140030da1`
- name: `?NwifiPendingDirectOidRequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z`
- size: `457`
- prototype: `void __fastcall(struct _ADAPT *, struct _NDIS_OID_REQUEST *, NDIS_STATUS Status)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140036170`

## callees

- `0x14000a82c`
- `0x1400208f0`
- `0x1400307e8`
- `0x140030834`
- `0x140030bd8`
- `0x14003113c`
- `0x1400311f8`
- `0x14003c5e0`
- `0x14009a3d0`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030ccb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030ccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030cdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030cdf`
- `NDIS!NdisFDirectOidRequestComplete` at `0x140030d5b`
- `NDIS!NdisFDirectOidRequestComplete` at `0x140030d5b`
- `NDIS!NdisFreeCloneOidRequest` at `0x140030d40`
- `NDIS!NdisFreeCloneOidRequest` at `0x140030d40`

## pseudocode

```c
void __fastcall NwifiPendingDirectOidRequestComplete(
        struct _ADAPT *a1,
        struct _NDIS_OID_REQUEST *a2,
        unsigned int Status)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  unsigned int *p_VPortId; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  void (__fastcall *v13)(struct _ADAPT *, unsigned int *); // rbp
  _VELAN *pActiveVElan; // rbp
  _GUID *p_gDeviceId; // rbp
  int v16; // ecx
  struct _NDIS_OID_REQUEST *v17; // rbp
  PNDIS_OID_REQUEST v18; // rdx
  struct _NDIS_OID_REQUEST *v19; // rdx
  unsigned int v20; // [rsp+28h] [rbp-40h]
  __int128 v21; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)IsNwifiDirectOid(a2->DATA.Oid) )
  {
    p_VPortId = &a2[-1].VPortId;
    if ( p_VPortId )
    {
      if ( (unsigned int)Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline(v7, v6, v8) )
      {
        *p_VPortId = Status;
        v13 = (void (__fastcall *)(struct _ADAPT *, unsigned int *))*((_QWORD *)p_VPortId + 34);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids, p_VPortId);
          v13(a1, p_VPortId);
        }
      }
      pActiveVElan = a1->pActiveVElan;
      v21 = 0;
      if ( pActiveVElan )
        p_gDeviceId = &pActiveVElan->gDeviceId;
      else
        p_gDeviceId = (_GUID *)&v21;
      if ( !(unsigned int)Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline(v11, v10, v12) )
        *p_VPortId = Status;
      if ( (byte_1400AF803 & 8) != 0 )
      {
        v20 = *p_VPortId;
        McTemplateK0pjq_EtwWriteTransfer(
          v16,
          (unsigned int)DirectOidRequestPendingComplete,
          (_DWORD)p_gDeviceId,
          (_DWORD)p_VPortId,
          (__int64)p_gDeviceId,
          v20,
          v21);
      }
      if ( *((_QWORD *)p_VPortId - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)p_VPortId - 2), p_VPortId - 4);
      else
        ExFreePoolWithTag(p_VPortId - 4, *(p_VPortId - 2));
    }
  }
  else
  {
    if ( (unsigned int)Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline(v7, v6, v8) )
    {
      v17 = *(struct _NDIS_OID_REQUEST **)a2->SourceReserved;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_qDq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids);
      CopyOidRequestDataInformationToOriginal(v17, a2);
      NdisFreeCloneOidRequest(a1->hBinding, v18);
      v19 = v17;
    }
    else
    {
      v19 = a2;
    }
    NdisFDirectOidRequestComplete(a1->hBinding, v19, Status);
  }
  _InterlockedDecrement((volatile signed __int32 *)&a1->uOutstandingRequests);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&a1->RefCount, 0xFFFFFFFF) == 1 )
    PtDestroyAdapter(a1);
}

```

## disassembly

```asm
0x140030bd8  mov     [rsp+arg_18], rbx
0x140030bdd  push    rbp
0x140030bde  push    rsi
0x140030bdf  push    rdi
0x140030be0  sub     rsp, 50h
0x140030be4  mov     rax, cs:__security_cookie
0x140030beb  xor     rax, rsp
0x140030bee  mov     [rsp+68h+var_28], rax
0x140030bf3  mov     rdi, rcx
0x140030bf6  mov     esi, r8d
0x140030bf9  mov     ecx, [rdx+20h]; unsigned int
0x140030bfc  mov     rbx, rdx
0x140030bff  call    ?IsNwifiDirectOid@@YAHK@Z; IsNwifiDirectOid(ulong)
0x140030c04  test    eax, eax
0x140030c06  jz      loc_140030CED
0x140030c0c  add     rbx, 0FFFFFFFFFFFFFFF8h
0x140030c10  jz      loc_140030D67
0x140030c16  call    Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline
0x140030c1b  test    eax, eax
0x140030c1d  jz      short loc_140030C66
0x140030c1f  mov     [rbx], esi
0x140030c21  mov     rbp, [rbx+110h]
0x140030c28  test    rbp, rbp
0x140030c2b  jz      short loc_140030C66
0x140030c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c34  lea     rax, WPP_GLOBAL_Control
0x140030c3b  cmp     rcx, rax
0x140030c3e  jz      short loc_140030C58
0x140030c40  mov     rcx, [rcx+18h]
0x140030c44  lea     r8, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids
0x140030c4b  mov     edx, 0Ah
0x140030c50  mov     r9, rbx
0x140030c53  call    WPP_SF_q
0x140030c58  mov     rdx, rbx
0x140030c5b  mov     rcx, rdi
0x140030c5e  mov     rax, rbp
0x140030c61  call    _guard_dispatch_icall
0x140030c66  mov     rbp, [rdi+80h]
0x140030c6d  xorps   xmm0, xmm0
0x140030c70  movups  [rsp+68h+var_38], xmm0
0x140030c75  test    rbp, rbp
0x140030c78  jz      short loc_140030C83
0x140030c7a  add     rbp, 1338h
0x140030c81  jmp     short loc_140030C88
0x140030c83  lea     rbp, [rsp+68h+var_38]
0x140030c88  call    Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline
0x140030c8d  test    eax, eax
0x140030c8f  jnz     short loc_140030C93
0x140030c91  mov     [rbx], esi
0x140030c93  test    cs:byte_1400AF803, 8
0x140030c9a  jz      short loc_140030CB9
0x140030c9c  mov     eax, [rbx]
0x140030c9e  lea     rdx, DirectOidRequestPendingComplete
0x140030ca5  mov     dword ptr [rsp+68h+var_40], eax
0x140030ca9  mov     r9, rbx
0x140030cac  mov     r8, rbp
0x140030caf  mov     [rsp+68h+var_48], rbp
0x140030cb4  call    McTemplateK0pjq_EtwWriteTransfer
0x140030cb9  lea     rcx, [rbx-10h]; P
0x140030cbd  mov     rax, [rcx]
0x140030cc0  test    rax, rax
0x140030cc3  jz      short loc_140030CDC
0x140030cc5  mov     rdx, rcx; Entry
0x140030cc8  mov     rcx, rax; Lookaside
0x140030ccb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140030cd2  nop     dword ptr [rax+rax+00h]
0x140030cd7  jmp     loc_140030D67
0x140030cdc  mov     edx, [rcx+8]; Tag
0x140030cdf  call    cs:__imp_ExFreePoolWithTag
0x140030ce6  nop     dword ptr [rax+rax+00h]
0x140030ceb  jmp     short loc_140030D67
0x140030ced  call    Feature_Bugfix_54236861__private_IsEnabledDeviceUsageNoInline
0x140030cf2  test    eax, eax
0x140030cf4  jz      short loc_140030D51
0x140030cf6  mov     rbp, [rbx+0D8h]
0x140030cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d04  lea     rax, WPP_GLOBAL_Control
0x140030d0b  cmp     rcx, rax
0x140030d0e  jz      short loc_140030D31
0x140030d10  mov     rcx, [rcx+18h]
0x140030d14  lea     r8, WPP_3cf9dad185263daf66abbeae62a822a5_Traceguids
0x140030d1b  mov     edx, 0Bh
0x140030d20  mov     [rsp+68h+var_40], rbp
0x140030d25  mov     r9, rbx
0x140030d28  mov     dword ptr [rsp+68h+var_48], esi
0x140030d2c  call    WPP_SF_qDq
0x140030d31  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140030d34  mov     rcx, rbp; struct _NDIS_OID_REQUEST *
0x140030d37  call    ?CopyOidRequestDataInformationToOriginal@@YAXPEAU_NDIS_OID_REQUEST@@0@Z; CopyOidRequestDataInformationToOriginal(_NDIS_OID_REQUEST *,_NDIS_OID_REQUEST *)
0x140030d3c  mov     rcx, [rdi+50h]; SourceHandle
0x140030d40  call    cs:__imp_NdisFreeCloneOidRequest
0x140030d47  nop     dword ptr [rax+rax+00h]
0x140030d4c  mov     rdx, rbp
0x140030d4f  jmp     short loc_140030D54
0x140030d51  mov     rdx, rbx; OidRequest
0x140030d54  mov     rcx, [rdi+50h]; NdisFilterHandle
0x140030d58  mov     r8d, esi; Status
0x140030d5b  call    cs:__imp_NdisFDirectOidRequestComplete
0x140030d62  nop     dword ptr [rax+rax+00h]
0x140030d67  lock dec dword ptr [rdi+0F0h]
0x140030d6e  or      eax, 0FFFFFFFFh
0x140030d71  lock xadd [rdi+10h], eax
0x140030d76  cmp     eax, 1
0x140030d79  jnz     short loc_140030D83
0x140030d7b  mov     rcx, rdi; struct _ADAPT *
0x140030d7e  call    ?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z; PtDestroyAdapter(_ADAPT *)
0x140030d83  mov     rcx, [rsp+68h+var_28]
0x140030d88  xor     rcx, rsp; StackCookie
0x140030d8b  call    __security_check_cookie
0x140030d90  mov     rbx, [rsp+68h+arg_18]
0x140030d98  add     rsp, 50h
0x140030d9c  pop     rdi
0x140030d9d  pop     rsi
0x140030d9e  pop     rbp
0x140030d9f  retn
```
