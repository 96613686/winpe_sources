# CHNetCfgMgr::GetIHNetConnectionForINetConnection(INetConnection *,IHNetConnection * *)

- ea: `0x180014bc0`
- end: `0x1800151f3`
- name: `?GetIHNetConnectionForINetConnection@CHNetCfgMgr@@UEAAJPEAUINetConnection@@PEAPEAUIHNetConnection@@@Z`
- size: `1587`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, struct INetConnection *, struct IHNetConnection **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000ffc8`
- `0x180014bc0`
- `0x18001de9c`
- `0x18001f4e4`
- `0x18002886c`
- `0x180028c48`
- `0x18002914c`
- `0x180029440`
- `0x18002aef4`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180014f12`
- `OLEAUT32!__imp_SysAllocString` at `0x180014f12`
- `OLEAUT32!__imp_VariantClear` at `0x180014f5d`
- `OLEAUT32!__imp_VariantClear` at `0x180014f5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014f20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014f20`

## string_xrefs

- `0x180014f44`: `PhonebookPath`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::GetIHNetConnectionForINetConnection(
        CHNetCfgMgr *this,
        struct INetConnection *a2,
        struct IHNetConnection **a3)
{
  PVOID *v6; // rcx
  bool v7; // zf
  int ConnAndPropInstancesByGuid; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  NETCON_MEDIATYPE MediaType; // ecx
  unsigned __int8 v14; // si
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  struct IWbemServices *v19; // rcx
  OLECHAR *v20; // rsi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  NETCON_PROPERTIES *pProps; // [rsp+30h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  struct IWbemClassObject *v27; // [rsp+90h] [rbp+30h] BYREF
  struct IWbemClassObject *v28; // [rsp+A8h] [rbp+48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)this + 12) == 0;
  pProps = 0;
  v27 = 0;
  v28 = 0;
  if ( v7 )
  {
    ConnAndPropInstancesByGuid = -2147467261;
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_d(v6[2], 20, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v9 = 21;
LABEL_99:
        WPP_SF_d(v6[2], v9, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)ConnAndPropInstancesByGuid);
        return (unsigned int)ConnAndPropInstancesByGuid;
      }
    }
    return (unsigned int)ConnAndPropInstancesByGuid;
  }
  if ( a3 )
  {
    *a3 = 0;
    if ( !a2 )
    {
      ConnAndPropInstancesByGuid = -2147024809;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)ConnAndPropInstancesByGuid;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_95;
      v10 = 23;
      goto LABEL_19;
    }
    v12 = ((__int64 (__fastcall *)(struct INetConnection *, NETCON_PROPERTIES **))a2->lpVtbl->GetProperties)(
            a2,
            &pProps);
    ConnAndPropInstancesByGuid = v12;
    if ( v12 < 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)ConnAndPropInstancesByGuid;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_95;
      v10 = 24;
      v11 = (unsigned int)v12;
      goto LABEL_20;
    }
    ConnAndPropInstancesByGuid = GetConnAndPropInstancesByGuid(
                                   *((struct IWbemServices **)this + 12),
                                   &pProps->guidId,
                                   &v27,
                                   &v28);
    if ( ConnAndPropInstancesByGuid >= 0 )
      goto LABEL_68;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)ConnAndPropInstancesByGuid);
    }
    MediaType = pProps->MediaType;
    v14 = ((MediaType - 3) & 0xFFFFFFFA) == 0 && MediaType != NCM_PHONE;
    ConnAndPropInstancesByGuid = CreateConnectionAndPropertyInstances(
                                   *((struct IWbemServices **)this + 12),
                                   &pProps->guidId,
                                   v14,
                                   pProps->pszwName,
                                   &v27,
                                   &v28);
    if ( ConnAndPropInstancesByGuid < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 26;
LABEL_63:
        WPP_SF_d(
          v15[2],
          v16,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)ConnAndPropInstancesByGuid);
        goto LABEL_68;
      }
      goto LABEL_68;
    }
    if ( ConnAndPropInstancesByGuid || v14 )
      goto LABEL_68;
    psz = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    ConnAndPropInstancesByGuid = GetPhonebookPathFromRasNetcon(a2, &psz);
    if ( ConnAndPropInstancesByGuid < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v18 = 27;
LABEL_52:
      WPP_SF_d(v17[2], v18, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)ConnAndPropInstancesByGuid);
LABEL_53:
      v19 = (struct IWbemServices *)*((_QWORD *)this + 12);
      goto LABEL_54;
    }
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    CoTaskMemFree(psz);
    if ( pvarg.llVal )
    {
      ConnAndPropInstancesByGuid = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v27->lpVtbl->Put)(
                                     v27,
                                     L"PhonebookPath",
                                     0,
                                     &pvarg,
                                     0);
      VariantClear(&pvarg);
    }
    else
    {
      ConnAndPropInstancesByGuid = -2147024882;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 28;
        goto LABEL_52;
      }
    }
    v19 = (struct IWbemServices *)*((_QWORD *)this + 12);
    if ( ConnAndPropInstancesByGuid >= 0 )
    {
      ConnAndPropInstancesByGuid = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, _QWORD, _QWORD, _QWORD))v19->lpVtbl->PutInstance)(
                                     v19,
                                     v27,
                                     0,
                                     0,
                                     0);
      if ( ConnAndPropInstancesByGuid < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 29;
          goto LABEL_63;
        }
      }
LABEL_68:
      NcFreeNetconProperties(pProps);
      if ( ConnAndPropInstancesByGuid )
        goto LABEL_94;
      psz = 0;
      ConnAndPropInstancesByGuid = ATL::CComObject<CHNetConn>::CreateInstance(&psz);
      if ( ConnAndPropInstancesByGuid < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
            (unsigned int)ConnAndPropInstancesByGuid);
        }
        goto LABEL_93;
      }
      v20 = psz;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 8LL))(psz);
      ConnAndPropInstancesByGuid = CHNetConn::SetINetConnection((CHNetConn *)v20, a2);
      if ( ConnAndPropInstancesByGuid >= 0 )
      {
        if ( ConnAndPropInstancesByGuid )
        {
LABEL_92:
          (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_93:
          ((void (__fastcall *)(struct IWbemClassObject *))v27->lpVtbl->Release)(v27);
          ((void (__fastcall *)(struct IWbemClassObject *))v28->lpVtbl->Release)(v28);
          goto LABEL_94;
        }
        ConnAndPropInstancesByGuid = CHNetConn::InitializeFromInstances(
                                       (CHNetConn *)v20,
                                       *((struct IWbemServices **)this + 12),
                                       v27,
                                       v28);
        if ( ConnAndPropInstancesByGuid >= 0 )
        {
          if ( ConnAndPropInstancesByGuid )
            goto LABEL_92;
          ConnAndPropInstancesByGuid = (**(__int64 (__fastcall ***)(OLECHAR *, GUID *, struct IHNetConnection **))v20)(
                                         v20,
                                         &GUID_85d18b71_3032_11d4_9348_00c04f8eeb71,
                                         a3);
          if ( ConnAndPropInstancesByGuid >= 0 )
            goto LABEL_92;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_92;
          }
          v22 = 33;
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_92;
          }
          v22 = 32;
        }
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v22 = 31;
      }
      WPP_SF_d(v21[2], v22, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)ConnAndPropInstancesByGuid);
      goto LABEL_92;
    }
LABEL_54:
    DeleteWmiInstance(v19, v27);
    DeleteWmiInstance(*((struct IWbemServices **)this + 12), v28);
    ((void (__fastcall *)(struct IWbemClassObject *))v27->lpVtbl->Release)(v27);
    ((void (__fastcall *)(struct IWbemClassObject *))v28->lpVtbl->Release)(v28);
    goto LABEL_68;
  }
  ConnAndPropInstancesByGuid = -2147467261;
  if ( v6 == &WPP_GLOBAL_Control )
    return (unsigned int)ConnAndPropInstancesByGuid;
  if ( (*((_BYTE *)v6 + 28) & 8) == 0 || *((_BYTE *)v6 + 25) < 2u )
    goto LABEL_95;
  v10 = 22;
LABEL_19:
  v11 = (unsigned int)ConnAndPropInstancesByGuid;
LABEL_20:
  WPP_SF_d(v6[2], v10, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v11);
LABEL_94:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_95:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v9 = 34;
    goto LABEL_99;
  }
  return (unsigned int)ConnAndPropInstancesByGuid;
}

```

## disassembly

```asm
0x180014bc0  mov     [rsp-28h+arg_8], rbx
0x180014bc5  push    rbp
0x180014bc6  push    rsi
0x180014bc7  push    r12
0x180014bc9  push    r14
0x180014bcb  push    r15
0x180014bcd  mov     rbp, rsp
0x180014bd0  sub     rsp, 60h
0x180014bd4  mov     r12, r8
0x180014bd7  mov     r15, rdx
0x180014bda  mov     r14, rcx
0x180014bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180014be4  lea     rbx, WPP_GLOBAL_Control
0x180014beb  mov     esi, 8
0x180014bf0  cmp     rcx, rbx
0x180014bf3  jz      short loc_180014C1B
0x180014bf5  test    [rcx+1Ch], sil
0x180014bf9  jz      short loc_180014C1B
0x180014bfb  cmp     byte ptr [rcx+19h], 6
0x180014bff  jb      short loc_180014C1B
0x180014c01  mov     rcx, [rcx+10h]
0x180014c05  lea     edx, [rsi+0Bh]
0x180014c08  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014c0f  call    WPP_SF_
0x180014c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c1b  cmp     qword ptr [r14+60h], 0
0x180014c20  mov     [rbp+pProps], 0
0x180014c28  mov     [rbp+arg_0], 0
0x180014c30  mov     [rbp+arg_18], 0
0x180014c38  jnz     short loc_180014CA1
0x180014c3a  lea     r14, WPP_GLOBAL_Control
0x180014c41  mov     ebx, 80004003h
0x180014c46  cmp     rcx, r14
0x180014c49  jz      loc_1800151DC
0x180014c4f  test    [rcx+1Ch], sil
0x180014c53  jz      short loc_180014C7A
0x180014c55  cmp     byte ptr [rcx+19h], 2
0x180014c59  jb      short loc_180014C7A
0x180014c5b  mov     rcx, [rcx+10h]
0x180014c5f  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014c66  mov     edx, 14h
0x180014c6b  mov     r9d, ebx
0x180014c6e  call    WPP_SF_d
0x180014c73  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c7a  cmp     rcx, r14
0x180014c7d  jz      loc_1800151DC
0x180014c83  test    [rcx+1Ch], sil
0x180014c87  jz      loc_1800151DC
0x180014c8d  cmp     byte ptr [rcx+19h], 6
0x180014c91  jb      loc_1800151DC
0x180014c97  mov     edx, 15h
0x180014c9c  jmp     loc_1800151C9
0x180014ca1  test    r12, r12
0x180014ca4  jnz     short loc_180014CEC
0x180014ca6  mov     ebx, 80004003h
0x180014cab  lea     r14, WPP_GLOBAL_Control
0x180014cb2  cmp     rcx, r14
0x180014cb5  jz      loc_1800151DC
0x180014cbb  test    [rcx+1Ch], sil
0x180014cbf  jz      loc_1800151B3
0x180014cc5  cmp     byte ptr [rcx+19h], 2
0x180014cc9  jb      loc_1800151B3
0x180014ccf  lea     edx, [r12+16h]
0x180014cd4  mov     r9d, ebx
0x180014cd7  mov     rcx, [rcx+10h]
0x180014cdb  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014ce2  call    WPP_SF_d
0x180014ce7  jmp     loc_1800151AC
0x180014cec  mov     qword ptr [r12], 0
0x180014cf4  test    r15, r15
0x180014cf7  jnz     short loc_180014D2F
0x180014cf9  mov     ebx, 80070057h
0x180014cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d05  lea     r14, WPP_GLOBAL_Control
0x180014d0c  cmp     rcx, r14
0x180014d0f  jz      loc_1800151DC
0x180014d15  test    [rcx+1Ch], sil
0x180014d19  jz      loc_1800151B3
0x180014d1f  cmp     byte ptr [rcx+19h], 2
0x180014d23  jb      loc_1800151B3
0x180014d29  lea     edx, [r15+17h]
0x180014d2d  jmp     short loc_180014CD4
0x180014d2f  mov     rax, [r15]
0x180014d32  lea     rdx, [rbp+pProps]
0x180014d36  mov     rcx, r15
0x180014d39  mov     rax, [rax+38h]
0x180014d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d42  mov     ebx, eax
0x180014d44  test    eax, eax
0x180014d46  jns     short loc_180014D80
0x180014d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d4f  lea     r14, WPP_GLOBAL_Control
0x180014d56  cmp     rcx, r14
0x180014d59  jz      loc_1800151DC
0x180014d5f  test    [rcx+1Ch], sil
0x180014d63  jz      loc_1800151B3
0x180014d69  cmp     byte ptr [rcx+19h], 2
0x180014d6d  jb      loc_1800151B3
0x180014d73  mov     edx, 18h
0x180014d78  mov     r9d, eax
0x180014d7b  jmp     loc_180014CD7
0x180014d80  mov     rdx, [rbp+pProps]; struct _GUID *
0x180014d84  lea     r9, [rbp+arg_18]; struct IWbemClassObject **
0x180014d88  mov     rcx, [r14+60h]; struct IWbemServices *
0x180014d8c  lea     r8, [rbp+arg_0]; struct IWbemClassObject **
0x180014d90  call    ?GetConnAndPropInstancesByGuid@@YAJPEAUIWbemServices@@PEAU_GUID@@PEAPEAUIWbemClassObject@@2@Z; GetConnAndPropInstancesByGuid(IWbemServices *,_GUID *,IWbemClassObject * *,IWbemClassObject * *)
0x180014d95  mov     ebx, eax
0x180014d97  test    eax, eax
0x180014d99  jns     loc_18001500C
0x180014d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014da6  lea     rax, WPP_GLOBAL_Control
0x180014dad  cmp     rcx, rax
0x180014db0  jz      short loc_180014DD6
0x180014db2  test    [rcx+1Ch], sil
0x180014db6  jz      short loc_180014DD6
0x180014db8  cmp     byte ptr [rcx+19h], 2
0x180014dbc  jb      short loc_180014DD6
0x180014dbe  mov     rcx, [rcx+10h]
0x180014dc2  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014dc9  mov     edx, 19h
0x180014dce  mov     r9d, ebx
0x180014dd1  call    WPP_SF_d
0x180014dd6  mov     rdx, [rbp+pProps]; rclsid
0x180014dda  mov     ecx, [rdx+24h]
0x180014ddd  lea     eax, [rcx-3]
0x180014de0  test    eax, 0FFFFFFFAh
0x180014de5  jnz     short loc_180014DF1
0x180014de7  cmp     ecx, 4
0x180014dea  jz      short loc_180014DF1
0x180014dec  mov     sil, 1
0x180014def  jmp     short loc_180014DF4
0x180014df1  xor     sil, sil
0x180014df4  mov     r9, [rdx+10h]; psz
0x180014df8  lea     rax, [rbp+arg_18]
0x180014dfc  mov     rcx, [r14+60h]; struct IWbemServices *
0x180014e00  mov     r8b, sil; unsigned __int8
0x180014e03  mov     [rsp+60h+var_38], rax; struct IWbemClassObject **
0x180014e08  lea     rax, [rbp+arg_0]
0x180014e0c  mov     [rsp+60h+var_40], rax; struct IWbemClassObject **
0x180014e11  call    ?CreateConnectionAndPropertyInstances@@YAJPEAUIWbemServices@@PEAU_GUID@@EPEBGPEAPEAUIWbemClassObject@@3@Z; CreateConnectionAndPropertyInstances(IWbemServices *,_GUID *,uchar,ushort const *,IWbemClassObject * *,IWbemClassObject * *)
0x180014e16  mov     ebx, eax
0x180014e18  test    eax, eax
0x180014e1a  jns     short loc_180014E54
0x180014e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e23  lea     rax, WPP_GLOBAL_Control
0x180014e2a  mov     esi, 8
0x180014e2f  cmp     rcx, rax
0x180014e32  jz      loc_18001500C
0x180014e38  test    [rcx+1Ch], sil
0x180014e3c  jz      loc_18001500C
0x180014e42  cmp     byte ptr [rcx+19h], 2
0x180014e46  jb      loc_18001500C
0x180014e4c  lea     edx, [rsi+12h]
0x180014e4f  jmp     loc_180014FB8
0x180014e54  test    ebx, ebx
0x180014e56  jnz     loc_180015007
0x180014e5c  test    sil, sil
0x180014e5f  jnz     loc_180015007
0x180014e65  xorps   xmm0, xmm0
0x180014e68  mov     [rbp+psz], 0
0x180014e70  xor     eax, eax
0x180014e72  lea     rdx, [rbp+psz]; unsigned __int16 **
0x180014e76  mov     rcx, r15; struct INetConnection *
0x180014e79  mov     qword ptr [rbp+pvarg+10h], rax
0x180014e7d  movups  xmmword ptr [rbp+pvarg], xmm0
0x180014e81  call    ?GetPhonebookPathFromRasNetcon@@YAJPEAUINetConnection@@PEAPEAG@Z; GetPhonebookPathFromRasNetcon(INetConnection *,ushort * *)
0x180014e86  mov     ebx, eax
0x180014e88  test    eax, eax
0x180014e8a  jns     short loc_180014F05
0x180014e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e93  lea     rax, WPP_GLOBAL_Control
0x180014e9a  mov     esi, 8
0x180014e9f  cmp     rcx, rax
0x180014ea2  jz      short loc_180014EC6
0x180014ea4  test    [rcx+1Ch], sil
0x180014ea8  jz      short loc_180014EC6
0x180014eaa  cmp     byte ptr [rcx+19h], 2
0x180014eae  jb      short loc_180014EC6
0x180014eb0  lea     edx, [rsi+13h]
0x180014eb3  mov     rcx, [rcx+10h]
0x180014eb7  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014ebe  mov     r9d, ebx
0x180014ec1  call    WPP_SF_d
0x180014ec6  mov     rcx, [r14+60h]; struct IWbemServices *
0x180014eca  mov     rdx, [rbp+arg_0]; struct IWbemClassObject *
0x180014ece  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x180014ed3  mov     rdx, [rbp+arg_18]; struct IWbemClassObject *
0x180014ed7  mov     rcx, [r14+60h]; struct IWbemServices *
0x180014edb  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x180014ee0  mov     rcx, [rbp+arg_0]
0x180014ee4  mov     rax, [rcx]
0x180014ee7  mov     rax, [rax+10h]
0x180014eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ef0  mov     rcx, [rbp+arg_18]
0x180014ef4  mov     rax, [rcx]
0x180014ef7  mov     rax, [rax+10h]
0x180014efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f00  jmp     loc_18001500C
0x180014f05  mov     rcx, [rbp+psz]; psz
0x180014f09  mov     esi, 8
0x180014f0e  mov     word ptr [rbp+pvarg], si
0x180014f12  call    cs:__imp_SysAllocString
0x180014f18  mov     rcx, [rbp+psz]; pv
0x180014f1c  mov     qword ptr [rbp+pvarg+8], rax
0x180014f20  call    cs:__imp_CoTaskMemFree
0x180014f26  cmp     qword ptr [rbp+pvarg+8], 0
0x180014f2b  jz      loc_180014FCD
0x180014f31  mov     rcx, [rbp+arg_0]
0x180014f35  lea     r9, [rbp+pvarg]
0x180014f39  xor     r8d, r8d
0x180014f3c  mov     dword ptr [rsp+60h+var_40], 0
0x180014f44  lea     rdx, ?c_wszPhonebookPath@@3QBGB; "PhonebookPath"
0x180014f4b  mov     rax, [rcx]
0x180014f4e  mov     rax, [rax+28h]
0x180014f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f57  lea     rcx, [rbp+pvarg]; pvarg
0x180014f5b  mov     ebx, eax
0x180014f5d  call    cs:__imp_VariantClear
0x180014f63  mov     rcx, [r14+60h]
0x180014f67  test    ebx, ebx
0x180014f69  js      loc_180014ECA
0x180014f6f  mov     rax, [rcx]
0x180014f72  xor     r9d, r9d
0x180014f75  mov     rdx, [rbp+arg_0]
0x180014f79  xor     r8d, r8d
0x180014f7c  mov     [rsp+60h+var_40], 0
0x180014f85  mov     rax, [rax+70h]
0x180014f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f8e  mov     ebx, eax
0x180014f90  test    eax, eax
0x180014f92  jns     short loc_18001500C
0x180014f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f9b  lea     rax, WPP_GLOBAL_Control
0x180014fa2  cmp     rcx, rax
0x180014fa5  jz      short loc_18001500C
0x180014fa7  test    [rcx+1Ch], sil
0x180014fab  jz      short loc_18001500C
0x180014fad  cmp     byte ptr [rcx+19h], 2
0x180014fb1  jb      short loc_18001500C
0x180014fb3  mov     edx, 1Dh
0x180014fb8  mov     rcx, [rcx+10h]
0x180014fbc  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014fc3  mov     r9d, ebx
0x180014fc6  call    WPP_SF_d
0x180014fcb  jmp     short loc_18001500C
0x180014fcd  mov     ebx, 8007000Eh
0x180014fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fd9  lea     rax, WPP_GLOBAL_Control
0x180014fe0  cmp     rcx, rax
0x180014fe3  jz      loc_180014F63
0x180014fe9  test    [rcx+1Ch], sil
0x180014fed  jz      loc_180014F63
0x180014ff3  cmp     byte ptr [rcx+19h], 2
0x180014ff7  jb      loc_180014F63
0x180014ffd  mov     edx, 1Ch
0x180015002  jmp     loc_180014EB3
0x180015007  mov     esi, 8
0x18001500c  mov     rcx, [rbp+pProps]; pProps
0x180015010  call    NcFreeNetconProperties
0x180015015  test    ebx, ebx
0x180015017  jnz     loc_1800151A5
0x18001501d  lea     rcx, [rbp+psz]
0x180015021  mov     [rbp+psz], 0
0x180015029  call    ?CreateInstance@?$CComObject@VCHNetConn@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetConn>::CreateInstance(ATL::CComObject<CHNetConn> * *)
0x18001502e  mov     ebx, eax
0x180015030  test    eax, eax
0x180015032  jns     short loc_18001507C
0x180015034  mov     rcx, cs:WPP_GLOBAL_Control
0x18001503b  lea     rax, WPP_GLOBAL_Control
0x180015042  cmp     rcx, rax
0x180015045  jz      loc_180015185
0x18001504b  test    [rcx+1Ch], sil
0x18001504f  jz      loc_180015185
0x180015055  cmp     byte ptr [rcx+19h], 2
0x180015059  jb      loc_180015185
0x18001505f  mov     rcx, [rcx+10h]
0x180015063  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001506a  mov     edx, 1Eh
0x18001506f  mov     r9d, ebx
0x180015072  call    WPP_SF_d
0x180015077  jmp     loc_180015185
0x18001507c  mov     rsi, [rbp+psz]
0x180015080  mov     rcx, rsi
0x180015083  mov     rax, [rsi]
0x180015086  mov     rax, [rax+8]
0x18001508a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001508f  mov     rdx, r15; struct INetConnection *
0x180015092  mov     rcx, rsi; this
0x180015095  call    ?SetINetConnection@CHNetConn@@QEAAJPEAUINetConnection@@@Z; CHNetConn::SetINetConnection(INetConnection *)
0x18001509a  mov     ebx, eax
0x18001509c  test    eax, eax
0x18001509e  jns     short loc_1800150D5
0x1800150a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150a7  lea     rax, WPP_GLOBAL_Control
0x1800150ae  cmp     rcx, rax
0x1800150b1  jz      loc_180015176
0x1800150b7  test    byte ptr [rcx+1Ch], 8
0x1800150bb  jz      loc_180015176
0x1800150c1  cmp     byte ptr [rcx+19h], 2
0x1800150c5  jb      loc_180015176
  ... truncated ...
```
