# CSNOCplCore::OnWMProfilePropertyChange(tagNETPROFILE_EVENT_DATA * const)

- ea: `0x18000ef50`
- end: `0x18000f1e0`
- name: `?OnWMProfilePropertyChange@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z`
- size: `656`
- prototype: `void __fastcall(CSNOCplCore *__hidden this, struct tagNETPROFILE_EVENT_DATA *const)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006b70`
- `0x18000a2e0`
- `0x18000b384`
- `0x18000b8bc`
- `0x18000ef50`
- `0x180012ec4`
- `0x180013df4`
- `0x180014274`
- `0x180014448`
- `0x180020444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f198`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f033`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000f08d`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000f08d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSNOCplCore::OnWMProfilePropertyChange(CSNOCplCore *this, struct tagNETPROFILE_EVENT_DATA *const a2)
{
  unsigned int v4; // edi
  int ProfileProperty; // r13d
  __int64 v6; // rbx
  __int16 v7; // r12
  unsigned __int16 v8; // si
  int v9; // r8d
  int v10; // ecx
  _QWORD *v11; // rcx
  int v12; // edx
  const char *v13; // rax
  DirectUI::Element *v14; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v15[16]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v16; // [rsp+88h] [rbp+10h] BYREF
  struct _GUID *v17; // [rsp+90h] [rbp+18h]

  v4 = *((_DWORD *)a2 + 9);
  if ( (v4 & 0x3D) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    return;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  ProfileProperty = 0;
  v17 = (struct _GUID *)((char *)a2 + 4);
  std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::find(
    *((_QWORD *)this + 19),
    &v16,
    (char *)a2 + 4);
  if ( v16 != **((_QWORD **)this + 19) )
  {
    v6 = *(_QWORD *)(v16 + 48);
    v7 = 0;
    if ( (v4 & 4) != 0 )
    {
      CoTaskMemFree(*(LPVOID *)(v6 + 16));
      *(_QWORD *)(v6 + 16) = 0;
      v7 = 2;
    }
    if ( (v4 & 8) != 0 )
    {
      CoTaskMemFree(*(LPVOID *)(v6 + 40));
      *(_QWORD *)(v6 + 40) = 0;
      *(_DWORD *)(v6 + 32) = 0;
      v7 |= 8u;
    }
    LODWORD(v16) = v4 & 0x20;
    v8 = v7 | 0x220;
    if ( (v4 & 0x20) == 0 )
      v8 = v7;
    if ( (v4 & 0x10) != 0 )
    {
      *(_DWORD *)(v6 + 56) = 0;
      v8 |= 0x10u;
    }
    v14 = (DirectUI::Element *)*((_QWORD *)this + 40);
    v15[0] = 0;
    DirectUI::Element::StartDefer(v14, v15);
    if ( !v8 )
      goto LABEL_31;
    ProfileProperty = CProfileMgr::GetProfileProperty(this, (struct _GUID *)v6, v8, (struct CProfileData *)v6);
    if ( ProfileProperty < 0 )
      goto LABEL_31;
    ProfileProperty = CSNOCplCore::UpdateProfileDUI(this, v6, v6, v4);
    if ( ProfileProperty < 0 )
      goto LABEL_31;
    if ( (v4 & 0x2C) == 0 )
      goto LABEL_31;
    CSNOCplCore::HandleConnectivityChange(this);
    if ( !(_DWORD)v16 )
      goto LABEL_31;
    v10 = *(_DWORD *)(v6 + 48);
    if ( (v10 & 0x28) != 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_31;
      v12 = 83;
      v13 = "INTERNET_CONN";
    }
    else if ( (v10 & 0x14) != 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_31;
      v12 = 84;
      v13 = "LOCAL_CONN";
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_31;
      v12 = 85;
      v13 = "NO_CONN";
    }
    WPP_SF_Ss(v11[2], v12, v9, *(_QWORD *)(v6 + 16), (__int64)v13);
LABEL_31:
    if ( (v4 & 1) != 0 )
      ProfileProperty = CSNOCplCore::HandleSignatureListChange(this, v17);
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v14);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)ProfileProperty);
}

```

## disassembly

```asm
0x18000ef50  mov     [rsp+arg_0], rbx
0x18000ef55  push    rbp
0x18000ef56  push    rsi
0x18000ef57  push    rdi
0x18000ef58  push    r12
0x18000ef5a  push    r13
0x18000ef5c  push    r14
0x18000ef5e  push    r15
0x18000ef60  sub     rsp, 40h
0x18000ef64  mov     rbx, rdx
0x18000ef67  mov     r14, rcx
0x18000ef6a  mov     edi, [rdx+24h]
0x18000ef6d  xor     esi, esi
0x18000ef6f  test    dil, 3Dh
0x18000ef73  jnz     short loc_18000EFB2
0x18000ef75  lea     rbp, WPP_GLOBAL_Control
0x18000ef7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef83  cmp     rcx, rbp
0x18000ef86  jz      loc_18000F1C8
0x18000ef8c  lea     r15d, [rsi+8]
0x18000ef90  test    [rcx+1Ch], r15b
0x18000ef94  jz      loc_18000F1C8
0x18000ef9a  lea     edx, [rsi+52h]
0x18000ef9d  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000efa4  mov     rcx, [rcx+10h]
0x18000efa8  call    WPP_SF_
0x18000efad  jmp     loc_18000F1C8
0x18000efb2  add     rcx, 70h ; 'p'; lpCriticalSection
0x18000efb6  call    cs:__imp_EnterCriticalSection
0x18000efbc  mov     r13d, esi
0x18000efbf  lea     rax, [rbx+4]
0x18000efc3  mov     [rsp+78h+arg_10], rax
0x18000efcb  mov     r8, rax
0x18000efce  lea     rdx, [rsp+78h+arg_8]
0x18000efd6  mov     rcx, [r14+98h]
0x18000efdd  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::find(_GUID const &)
0x18000efe2  mov     rcx, [r14+98h]
0x18000efe9  lea     rbp, WPP_GLOBAL_Control
0x18000eff0  mov     r15d, 8
0x18000eff6  mov     rax, [rsp+78h+arg_8]
0x18000effe  cmp     rax, [rcx]
0x18000f001  jz      loc_18000F194
0x18000f007  mov     rbx, [rax+30h]
0x18000f00b  mov     r12d, esi
0x18000f00e  test    dil, 4
0x18000f012  jz      short loc_18000F026
0x18000f014  mov     rcx, [rbx+10h]; pv
0x18000f018  call    cs:__imp_CoTaskMemFree
0x18000f01e  mov     [rbx+10h], rsi
0x18000f022  lea     r12d, [r15-6]
0x18000f026  mov     eax, edi
0x18000f028  and     eax, r15d
0x18000f02b  test    al, al
0x18000f02d  jz      short loc_18000F044
0x18000f02f  mov     rcx, [rbx+28h]; pv
0x18000f033  call    cs:__imp_CoTaskMemFree
0x18000f039  mov     [rbx+28h], rsi
0x18000f03d  mov     [rbx+20h], esi
0x18000f040  or      r12w, r15w
0x18000f044  mov     eax, edi
0x18000f046  and     eax, 20h
0x18000f049  mov     dword ptr [rsp+78h+arg_8], eax
0x18000f050  movzx   esi, r12w
0x18000f054  or      si, 220h
0x18000f059  test    eax, eax
0x18000f05b  cmovz   si, r12w
0x18000f060  mov     eax, edi
0x18000f062  mov     ecx, 10h
0x18000f067  and     eax, ecx
0x18000f069  xor     r12d, r12d
0x18000f06c  test    al, al
0x18000f06e  jz      short loc_18000F077
0x18000f070  mov     [rbx+38h], r12d
0x18000f074  or      si, cx
0x18000f077  mov     rcx, [r14+140h]
0x18000f07e  mov     [rsp+78h+var_48], rcx
0x18000f083  mov     [rsp+78h+var_40], r12d
0x18000f088  lea     rdx, [rsp+78h+var_40]
0x18000f08d  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x18000f093  nop
0x18000f094  cmp     r12w, si
0x18000f098  jz      loc_18000F170
0x18000f09e  mov     r9, rbx; struct CProfileData *
0x18000f0a1  movzx   r8d, si; unsigned __int16
0x18000f0a5  mov     rdx, rbx; struct _GUID *
0x18000f0a8  mov     rcx, r14; this
0x18000f0ab  call    ?GetProfileProperty@CProfileMgr@@QEAAJPEAU_GUID@@GPEAVCProfileData@@@Z; CProfileMgr::GetProfileProperty(_GUID *,ushort,CProfileData *)
0x18000f0b0  mov     r13d, eax
0x18000f0b3  test    eax, eax
0x18000f0b5  js      loc_18000F170
0x18000f0bb  mov     r9d, edi
0x18000f0be  mov     r8, rbx
0x18000f0c1  mov     rdx, rbx
0x18000f0c4  mov     rcx, r14
0x18000f0c7  call    ?UpdateProfileDUI@CSNOCplCore@@AEAAJPEAVCProfileData@@0W4tagNP_NETWORK_PROPERTY_CHANGE@@@Z; CSNOCplCore::UpdateProfileDUI(CProfileData *,CProfileData *,tagNP_NETWORK_PROPERTY_CHANGE)
0x18000f0cc  mov     r13d, eax
0x18000f0cf  test    eax, eax
0x18000f0d1  js      loc_18000F170
0x18000f0d7  test    dil, 2Ch
0x18000f0db  jz      loc_18000F170
0x18000f0e1  mov     rcx, r14; this
0x18000f0e4  call    ?HandleConnectivityChange@CSNOCplCore@@AEAAXXZ; CSNOCplCore::HandleConnectivityChange(void)
0x18000f0e9  cmp     dword ptr [rsp+78h+arg_8], r12d
0x18000f0f1  jz      short loc_18000F170
0x18000f0f3  mov     ecx, [rbx+30h]
0x18000f0f6  test    cl, 28h
0x18000f0f9  jz      short loc_18000F11B
0x18000f0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f102  cmp     rcx, rbp
0x18000f105  jz      short loc_18000F170
0x18000f107  test    byte ptr [rcx+1Ch], 4
0x18000f10b  jz      short loc_18000F170
0x18000f10d  mov     edx, 53h ; 'S'
0x18000f112  lea     rax, aInternetConn; "INTERNET_CONN"
0x18000f119  jmp     short loc_18000F15E
0x18000f11b  test    cl, 14h
0x18000f11e  jz      short loc_18000F140
0x18000f120  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f127  cmp     rcx, rbp
0x18000f12a  jz      short loc_18000F170
0x18000f12c  test    byte ptr [rcx+1Ch], 4
0x18000f130  jz      short loc_18000F170
0x18000f132  mov     edx, 54h ; 'T'
0x18000f137  lea     rax, aLocalConn; "LOCAL_CONN"
0x18000f13e  jmp     short loc_18000F15E
0x18000f140  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f147  cmp     rcx, rbp
0x18000f14a  jz      short loc_18000F170
0x18000f14c  test    byte ptr [rcx+1Ch], 4
0x18000f150  jz      short loc_18000F170
0x18000f152  mov     edx, 55h ; 'U'
0x18000f157  lea     rax, aNoConn; "NO_CONN"
0x18000f15e  mov     [rsp+78h+var_58], rax
0x18000f163  mov     r9, [rbx+10h]
0x18000f167  mov     rcx, [rcx+10h]
0x18000f16b  call    WPP_SF_Ss
0x18000f170  test    dil, 1
0x18000f174  jz      short loc_18000F189
0x18000f176  mov     rdx, [rsp+78h+arg_10]; struct _GUID *
0x18000f17e  mov     rcx, r14; this
0x18000f181  call    ?HandleSignatureListChange@CSNOCplCore@@AEAAJAEBU_GUID@@@Z; CSNOCplCore::HandleSignatureListChange(_GUID const &)
0x18000f186  mov     r13d, eax
0x18000f189  lea     rcx, [rsp+78h+var_48]; this
0x18000f18e  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x18000f193  nop
0x18000f194  lea     rcx, [r14+70h]; lpCriticalSection
0x18000f198  call    cs:__imp_LeaveCriticalSection
0x18000f19e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1a5  cmp     rcx, rbp
0x18000f1a8  jz      short loc_18000F1C8
0x18000f1aa  test    [rcx+1Ch], r15b
0x18000f1ae  jz      short loc_18000F1C8
0x18000f1b0  mov     edx, 56h ; 'V'
0x18000f1b5  mov     r9d, r13d
0x18000f1b8  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000f1bf  mov     rcx, [rcx+10h]
0x18000f1c3  call    WPP_SF_d
0x18000f1c8  mov     rbx, [rsp+78h+arg_0]
0x18000f1d0  add     rsp, 40h
0x18000f1d4  pop     r15
0x18000f1d6  pop     r14
0x18000f1d8  pop     r13
0x18000f1da  pop     r12
0x18000f1dc  pop     rdi
0x18000f1dd  pop     rsi
0x18000f1de  pop     rbp
0x18000f1df  retn
```
