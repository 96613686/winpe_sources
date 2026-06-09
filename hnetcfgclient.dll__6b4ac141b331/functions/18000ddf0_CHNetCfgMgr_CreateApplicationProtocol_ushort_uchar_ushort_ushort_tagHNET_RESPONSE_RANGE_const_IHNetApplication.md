# CHNetCfgMgr::CreateApplicationProtocol(ushort *,uchar,ushort,ushort,tagHNET_RESPONSE_RANGE * const,IHNetApplicationProtocol * *)

- ea: `0x18000ddf0`
- end: `0x18000e8f7`
- name: `?CreateApplicationProtocol@CHNetCfgMgr@@UEAAJPEAGEGGQEAUtagHNET_RESPONSE_RANGE@@PEAPEAUIHNetApplicationProtocol@@@Z`
- size: `2823`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, unsigned __int16 *, __int64, unsigned __int16, unsigned __int16, struct tagHNET_RESPONSE_RANGE *const, struct IHNetApplicationProtocol **)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005698`
- `0x18000a45c`
- `0x18000a484`
- `0x18000ddf0`
- `0x18000feb4`
- `0x180018024`
- `0x180022fe0`
- `0x180027ca4`
- `0x1800283f8`
- `0x180029a3c`
- `0x18002a61c`
- `0x18002a7d4`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000e336`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e336`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e71c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e71c`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3b6`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3b6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000e886`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000e886`

## string_xrefs

- `0x18000e4c9`: `OutgoingIPProtocol`
- `0x18000e22b`: `HNet_ApplicationProtocol`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::CreateApplicationProtocol(
        CHNetCfgMgr *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        struct tagHNET_RESPONSE_RANGE *const a6,
        struct IHNetApplicationProtocol **a7)
{
  struct IHNetApplicationProtocol **v7; // rax
  unsigned __int8 v8; // r12
  PVOID *v11; // rcx
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r9
  int v22; // eax
  int WmiObjectFromPath; // eax
  int v24; // eax
  CHNetAppProtocol *v25; // rsi
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 v29; // [rsp+30h] [rbp-D0h]
  struct IWbemClassObject *v30; // [rsp+38h] [rbp-C8h] BYREF
  CHNetAppProtocol *v31; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  SAFEARRAY *psa; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  struct IHNetApplicationProtocol **v35; // [rsp+70h] [rbp-90h]
  OLECHAR psz[256]; // [rsp+80h] [rbp-80h] BYREF

  v7 = a7;
  v8 = a3;
  v35 = a7;
  v29 = a4;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    a4 = v29;
    v7 = v35;
  }
  v12 = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  psa = 0;
  v30 = 0;
  if ( !*((_QWORD *)this + 8) )
  {
    v13 = -2147467261;
    if ( v11 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      {
        WPP_SF_d(v11[2], 243, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 6u )
      {
        v14 = 244;
LABEL_170:
        WPP_SF_d(v11[2], v14, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v13);
        return (unsigned int)v13;
      }
    }
    return (unsigned int)v13;
  }
  if ( !v7 )
  {
    v13 = -2147467261;
    if ( v11 == &WPP_GLOBAL_Control )
      return (unsigned int)v13;
    if ( (*((_BYTE *)v11 + 28) & 8) == 0 || *((_BYTE *)v11 + 25) < 2u )
      goto LABEL_166;
    v15 = 245;
LABEL_56:
    v16 = (unsigned int)v13;
LABEL_57:
    WPP_SF_d(v11[2], v15, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v16);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_166;
  }
  *v7 = 0;
  if ( a2 )
  {
    if ( v8 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          v13 = 0;
          if ( a6 )
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_25;
          }
        }
      }
    }
  }
  v13 = -2147024809;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942487LL);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
LABEL_25:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    {
      WPP_SF_S(v11[2], v12, a3, a2);
LABEL_29:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 2u )
  {
    WPP_SF_d(v11[2], 247, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942487LL);
    goto LABEL_29;
  }
LABEL_30:
  if ( !v8 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    WPP_SF_(v11[2], 249, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v29 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    WPP_SF_(v11[2], 250, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a5 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    WPP_SF_(v11[2], 251, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a6 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 5u )
  {
    WPP_SF_(v11[2], 252, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v13 )
  {
    if ( ApplicationProtocolExists(*((struct IWbemServices **)this + 8), *((unsigned __int16 **)this + 11), v29, v8) )
    {
      v13 = -2147019886;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_166;
      v15 = 253;
      goto LABEL_56;
    }
    v17 = ConvertResponseRangeArrayToInstanceSafearray(*((struct IWbemServices **)this + 8), a5, a6, &psa);
    v13 = v17;
    if ( v17 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_166;
      v15 = 254;
      v16 = (unsigned int)v17;
      goto LABEL_57;
    }
    if ( v17 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_166;
    }
    v13 = SpawnNewInstance(*((struct IWbemServices **)this + 8), L"HNet_ApplicationProtocol", &v30);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          255,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v13);
      }
      goto LABEL_164;
    }
    if ( v13 )
    {
LABEL_164:
      SafeArrayDestroy(psa);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_166;
    }
    pvarg.vt = 8205;
    pvarg.llVal = (LONGLONG)psa;
    v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v30->lpVtbl->Put)(
            v30,
            L"ResponseArray",
            0,
            &pvarg,
            0);
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        256,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v13);
    }
    if ( v13 )
      goto LABEL_162;
    StringCchCopyW(psz, 0x100u, a2);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( pvarg.llVal )
    {
      v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v30->lpVtbl->Put)(
              v30,
              L"Name",
              0,
              &pvarg,
              0);
      if ( v13 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          257,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v13);
      }
      VariantClear(&pvarg);
      if ( v13 )
        goto LABEL_162;
    }
    pvarg.lVal = a5;
    pvarg.vt = 3;
    v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v30->lpVtbl->Put)(
            v30,
            L"ResponseCount",
            0,
            &pvarg,
            0);
    if ( v13 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 258;
LABEL_127:
        v21 = (unsigned int)v13;
LABEL_147:
        WPP_SF_d(v18[2], v19, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v21);
        goto LABEL_162;
      }
      goto LABEL_162;
    }
    if ( v13 )
      goto LABEL_162;
    pvarg.vt = 3;
    pvarg.lVal = v29;
    v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v30->lpVtbl->Put)(
            v30,
            L"OutgoingPort",
            0,
            &pvarg,
            0);
    if ( v13 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 259;
        goto LABEL_127;
      }
LABEL_162:
      if ( v30 )
        ((void (__fastcall *)(struct IWbemClassObject *))v30->lpVtbl->Release)(v30);
      goto LABEL_164;
    }
    if ( v13 )
      goto LABEL_162;
    pvarg.vt = 17;
    pvarg.bVal = v8;
    v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v30->lpVtbl->Put)(
            v30,
            L"OutgoingIPProtocol",
            0,
            &pvarg,
            0);
    if ( v13 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 260;
        goto LABEL_127;
      }
      goto LABEL_162;
    }
    if ( v13 )
      goto LABEL_162;
    v13 = SetBooleanValue(v30, L"BuiltIn", 0);
    if ( v13 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 261;
        goto LABEL_127;
      }
      goto LABEL_162;
    }
    if ( v13 )
      goto LABEL_162;
    v13 = SetBooleanValue(v30, L"Enabled", 0);
    if ( v13 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 262;
        goto LABEL_127;
      }
      goto LABEL_162;
    }
    if ( v13 )
      goto LABEL_162;
    v20 = *((_QWORD *)this + 8);
    v31 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, struct IWbemClassObject *, __int64, _QWORD, CHNetAppProtocol **))(*(_QWORD *)v20 + 112LL))(
            v20,
            v30,
            18,
            0,
            &v31);
    if ( v13 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 263;
        goto LABEL_127;
      }
      goto LABEL_162;
    }
    if ( v13 )
      goto LABEL_162;
    ((void (__fastcall *)(struct IWbemClassObject *))v30->lpVtbl->Release)(v30);
    v30 = 0;
    v22 = (*(__int64 (__fastcall **)(CHNetAppProtocol *, __int64, BSTR *))(*(_QWORD *)v31 + 32LL))(
            v31,
            0xFFFFFFFFLL,
            &bstrString);
    v13 = v22;
    if ( v22 >= 0 )
    {
      if ( !v22 )
      {
        WmiObjectFromPath = GetWmiObjectFromPath(*((struct IWbemServices **)this + 8), bstrString, &v30);
        v13 = WmiObjectFromPath;
        if ( WmiObjectFromPath < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            265,
            &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
            (unsigned int)WmiObjectFromPath);
        }
        SysFreeString(bstrString);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        264,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v22);
    }
    (*(void (__fastcall **)(CHNetAppProtocol *))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v13 )
      goto LABEL_162;
    v31 = 0;
    v24 = ATL::CComObject<CHNetAppProtocol>::CreateInstance(&v31);
    v13 = v24;
    if ( v24 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 266;
        v21 = (unsigned int)v24;
        goto LABEL_147;
      }
      goto LABEL_162;
    }
    if ( v24 )
      goto LABEL_162;
    v25 = v31;
    (*(void (__fastcall **)(CHNetAppProtocol *))(*(_QWORD *)v31 + 8LL))(v31);
    v13 = CHNetAppProtocol::Initialize(v25, *((struct IWbemServices **)this + 8), v30);
    if ( v13 >= 0 )
    {
      if ( v13 )
        goto LABEL_161;
      v13 = (**(__int64 (__fastcall ***)(CHNetAppProtocol *, GUID *, struct IHNetApplicationProtocol **))v25)(
              v25,
              &GUID_85d18b7f_3032_11d4_9348_00c04f8eeb71,
              v35);
      if ( v13 >= 0 )
        goto LABEL_161;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_161;
      }
      v27 = 268;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_161;
      }
      v27 = 267;
    }
    WPP_SF_d(v26[2], v27, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v13);
LABEL_161:
    (*(void (__fastcall **)(CHNetAppProtocol *))(*(_QWORD *)v25 + 16LL))(v25);
    goto LABEL_162;
  }
LABEL_166:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 6u )
  {
    v14 = 269;
    goto LABEL_170;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000ddf0  push    rbp
0x18000ddf2  push    rbx
0x18000ddf3  push    rsi
0x18000ddf4  push    rdi
0x18000ddf5  push    r12
0x18000ddf7  push    r13
0x18000ddf9  push    r14
0x18000ddfb  push    r15
0x18000ddfd  lea     rbp, [rsp-198h]
0x18000de05  sub     rsp, 298h
0x18000de0c  mov     rax, cs:__security_cookie
0x18000de13  xor     rax, rsp
0x18000de16  mov     [rbp+1D0h+var_50], rax
0x18000de1d  mov     rax, [rbp+1D0h+arg_30]
0x18000de24  mov     r12b, r8b
0x18000de27  mov     rsi, [rbp+1D0h+arg_28]
0x18000de2e  mov     r14, rdx
0x18000de31  mov     [rsp+2D0h+var_260], rax
0x18000de36  mov     r13, rcx
0x18000de39  mov     [rsp+2D0h+var_2A0], r9w
0x18000de3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de46  lea     rdx, WPP_GLOBAL_Control
0x18000de4d  cmp     rcx, rdx
0x18000de50  jz      short loc_18000DE85
0x18000de52  test    byte ptr [rcx+1Ch], 8
0x18000de56  jz      short loc_18000DE85
0x18000de58  cmp     byte ptr [rcx+19h], 6
0x18000de5c  jb      short loc_18000DE85
0x18000de5e  mov     rcx, [rcx+10h]
0x18000de62  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000de69  mov     edx, 0F2h
0x18000de6e  call    WPP_SF_
0x18000de73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de7a  movzx   r9d, [rsp+2D0h+var_2A0]
0x18000de80  mov     rax, [rsp+2D0h+var_260]
0x18000de85  xor     edx, edx
0x18000de87  mov     [rsp+2D0h+bstrString], 0
0x18000de90  xorps   xmm0, xmm0
0x18000de93  mov     qword ptr [rsp+2D0h+pvarg+10h], rdx
0x18000de98  movups  xmmword ptr [rsp+2D0h+pvarg], xmm0
0x18000de9d  mov     [rsp+2D0h+psa], rdx
0x18000dea2  mov     [rsp+2D0h+var_298], rdx
0x18000dea7  cmp     [r13+40h], rdx
0x18000deab  jnz     short loc_18000DF17
0x18000dead  lea     rsi, WPP_GLOBAL_Control
0x18000deb4  mov     ebx, 80004003h
0x18000deb9  cmp     rcx, rsi
0x18000debc  jz      loc_18000E8D2
0x18000dec2  test    byte ptr [rcx+1Ch], 8
0x18000dec6  jz      short loc_18000DEF0
0x18000dec8  mov     dil, 2
0x18000decb  cmp     [rcx+19h], dil
0x18000decf  jb      short loc_18000DEF0
0x18000ded1  mov     rcx, [rcx+10h]
0x18000ded5  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000dedc  mov     edx, 0F3h
0x18000dee1  mov     r9d, ebx
0x18000dee4  call    WPP_SF_d
0x18000dee9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000def0  cmp     rcx, rsi
0x18000def3  jz      loc_18000E8D2
0x18000def9  test    byte ptr [rcx+1Ch], 8
0x18000defd  jz      loc_18000E8D2
0x18000df03  cmp     byte ptr [rcx+19h], 6
0x18000df07  jb      loc_18000E8D2
0x18000df0d  mov     edx, 0F4h
0x18000df12  jmp     loc_18000E8BF
0x18000df17  test    rax, rax
0x18000df1a  jnz     short loc_18000DF56
0x18000df1c  mov     ebx, 80004003h
0x18000df21  lea     rsi, WPP_GLOBAL_Control
0x18000df28  cmp     rcx, rsi
0x18000df2b  jz      loc_18000E8D2
0x18000df31  lea     r14d, [rax+8]
0x18000df35  test    [rcx+1Ch], r14b
0x18000df39  jz      loc_18000E8A9
0x18000df3f  mov     dil, 2
0x18000df42  cmp     [rcx+19h], dil
0x18000df46  jb      loc_18000E8A9
0x18000df4c  mov     edx, 0F5h
0x18000df51  jmp     loc_18000E115
0x18000df56  movzx   r15d, [rbp+1D0h+arg_20]
0x18000df5e  mov     dil, 2
0x18000df61  mov     [rax], rdx
0x18000df64  test    r14, r14
0x18000df67  jz      loc_18000E134
0x18000df6d  test    r12b, r12b
0x18000df70  jz      loc_18000E134
0x18000df76  xor     eax, eax
0x18000df78  cmp     ax, r9w
0x18000df7c  jz      loc_18000E134
0x18000df82  cmp     ax, r15w
0x18000df86  jz      loc_18000E134
0x18000df8c  xor     ebx, ebx
0x18000df8e  test    rsi, rsi
0x18000df91  jz      loc_18000E134
0x18000df97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df9e  lea     rax, WPP_GLOBAL_Control
0x18000dfa5  cmp     rcx, rax
0x18000dfa8  jz      short loc_18000DFD0
0x18000dfaa  test    byte ptr [rcx+1Ch], 8
0x18000dfae  jz      short loc_18000DFD0
0x18000dfb0  cmp     byte ptr [rcx+19h], 5
0x18000dfb4  jb      short loc_18000DFD0
0x18000dfb6  mov     rcx, [rcx+10h]
0x18000dfba  mov     r9, r14
0x18000dfbd  call    WPP_SF_S
0x18000dfc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfc9  lea     rax, WPP_GLOBAL_Control
0x18000dfd0  test    r12b, r12b
0x18000dfd3  jnz     short loc_18000E002
0x18000dfd5  cmp     rcx, rax
0x18000dfd8  jz      short loc_18000E002
0x18000dfda  test    byte ptr [rcx+1Ch], 8
0x18000dfde  jz      short loc_18000E002
0x18000dfe0  cmp     byte ptr [rcx+19h], 5
0x18000dfe4  jb      short loc_18000E002
0x18000dfe6  mov     rcx, [rcx+10h]
0x18000dfea  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000dff1  mov     edx, 0F9h
0x18000dff6  call    WPP_SF_
0x18000dffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e002  xor     eax, eax
0x18000e004  cmp     ax, [rsp+2D0h+var_2A0]
0x18000e009  jnz     short loc_18000E03F
0x18000e00b  lea     rax, WPP_GLOBAL_Control
0x18000e012  cmp     rcx, rax
0x18000e015  jz      short loc_18000E03F
0x18000e017  test    byte ptr [rcx+1Ch], 8
0x18000e01b  jz      short loc_18000E03F
0x18000e01d  cmp     byte ptr [rcx+19h], 5
0x18000e021  jb      short loc_18000E03F
0x18000e023  mov     rcx, [rcx+10h]
0x18000e027  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e02e  mov     edx, 0FAh
0x18000e033  call    WPP_SF_
0x18000e038  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e03f  xor     eax, eax
0x18000e041  cmp     ax, r15w
0x18000e045  jnz     short loc_18000E07B
0x18000e047  lea     rax, WPP_GLOBAL_Control
0x18000e04e  cmp     rcx, rax
0x18000e051  jz      short loc_18000E082
0x18000e053  test    byte ptr [rcx+1Ch], 8
0x18000e057  jz      short loc_18000E082
0x18000e059  cmp     byte ptr [rcx+19h], 5
0x18000e05d  jb      short loc_18000E082
0x18000e05f  mov     rcx, [rcx+10h]
0x18000e063  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e06a  mov     edx, 0FBh
0x18000e06f  call    WPP_SF_
0x18000e074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e07b  lea     rax, WPP_GLOBAL_Control
0x18000e082  test    rsi, rsi
0x18000e085  jnz     short loc_18000E0B4
0x18000e087  cmp     rcx, rax
0x18000e08a  jz      short loc_18000E0B4
0x18000e08c  test    byte ptr [rcx+1Ch], 8
0x18000e090  jz      short loc_18000E0B4
0x18000e092  cmp     byte ptr [rcx+19h], 5
0x18000e096  jb      short loc_18000E0B4
0x18000e098  mov     rcx, [rcx+10h]
0x18000e09c  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e0a3  mov     edx, 0FCh
0x18000e0a8  call    WPP_SF_
0x18000e0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0b4  test    ebx, ebx
0x18000e0b6  jnz     loc_18000E89C
0x18000e0bc  movzx   r8d, [rsp+2D0h+var_2A0]; unsigned __int16
0x18000e0c2  mov     r9b, r12b; unsigned __int8
0x18000e0c5  mov     rdx, [r13+58h]; unsigned __int16 *
0x18000e0c9  mov     rcx, [r13+40h]; struct IWbemServices *
0x18000e0cd  call    ?ApplicationProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z; ApplicationProtocolExists(IWbemServices *,ushort *,ushort,uchar)
0x18000e0d2  test    al, al
0x18000e0d4  jz      loc_18000E1C1
0x18000e0da  mov     ebx, 80071392h
0x18000e0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0e6  lea     rsi, WPP_GLOBAL_Control
0x18000e0ed  cmp     rcx, rsi
0x18000e0f0  jz      loc_18000E8D2
0x18000e0f6  mov     r14d, 8
0x18000e0fc  test    [rcx+1Ch], r14b
0x18000e100  jz      loc_18000E8A9
0x18000e106  cmp     [rcx+19h], dil
0x18000e10a  jb      loc_18000E8A9
0x18000e110  mov     edx, 0FDh
0x18000e115  mov     r9d, ebx
0x18000e118  mov     rcx, [rcx+10h]
0x18000e11c  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e123  call    WPP_SF_d
0x18000e128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e12f  jmp     loc_18000E8A9
0x18000e134  mov     ebx, 80070057h
0x18000e139  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e140  lea     rax, WPP_GLOBAL_Control
0x18000e147  cmp     rcx, rax
0x18000e14a  jz      short loc_18000E17E
0x18000e14c  test    byte ptr [rcx+1Ch], 8
0x18000e150  jz      short loc_18000E17E
0x18000e152  cmp     [rcx+19h], dil
0x18000e156  jb      short loc_18000E17E
0x18000e158  mov     rcx, [rcx+10h]
0x18000e15c  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e163  mov     edx, 0F6h
0x18000e168  mov     r9d, ebx
0x18000e16b  call    WPP_SF_d
0x18000e170  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e177  lea     rax, WPP_GLOBAL_Control
0x18000e17e  test    r14, r14
0x18000e181  jnz     loc_18000DFA5
0x18000e187  cmp     rcx, rax
0x18000e18a  jz      loc_18000DFD0
0x18000e190  test    byte ptr [rcx+1Ch], 8
0x18000e194  jz      loc_18000DFD0
0x18000e19a  cmp     [rcx+19h], dil
0x18000e19e  jb      loc_18000DFD0
0x18000e1a4  mov     rcx, [rcx+10h]
0x18000e1a8  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e1af  mov     edx, 0F7h
0x18000e1b4  mov     r9d, ebx
0x18000e1b7  call    WPP_SF_d
0x18000e1bc  jmp     loc_18000DFC2
0x18000e1c1  mov     rcx, [r13+40h]; struct IWbemServices *
0x18000e1c5  lea     r9, [rsp+2D0h+psa]; struct tagSAFEARRAY **
0x18000e1ca  mov     r8, rsi; struct tagHNET_RESPONSE_RANGE *
0x18000e1cd  movzx   edx, r15w; unsigned __int16
0x18000e1d1  call    ?ConvertResponseRangeArrayToInstanceSafearray@@YAJPEAUIWbemServices@@GQEAUtagHNET_RESPONSE_RANGE@@PEAPEAUtagSAFEARRAY@@@Z; ConvertResponseRangeArrayToInstanceSafearray(IWbemServices *,ushort,tagHNET_RESPONSE_RANGE * const,tagSAFEARRAY * *)
0x18000e1d6  xor     esi, esi
0x18000e1d8  mov     ebx, eax
0x18000e1da  test    eax, eax
0x18000e1dc  jns     short loc_18000E21C
0x18000e1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1e5  lea     rsi, WPP_GLOBAL_Control
0x18000e1ec  mov     r14d, 8
0x18000e1f2  cmp     rcx, rsi
0x18000e1f5  jz      loc_18000E8D2
0x18000e1fb  test    [rcx+1Ch], r14b
0x18000e1ff  jz      loc_18000E8A9
0x18000e205  cmp     [rcx+19h], dil
0x18000e209  jb      loc_18000E8A9
0x18000e20f  mov     edx, 0FEh
0x18000e214  mov     r9d, eax
0x18000e217  jmp     loc_18000E118
0x18000e21c  jnz     loc_18000E895
0x18000e222  mov     rcx, [r13+40h]; struct IWbemServices *
0x18000e226  lea     r8, [rsp+2D0h+var_298]; struct IWbemClassObject **
0x18000e22b  lea     rdx, ?c_wszHnetApplicationProtocol@@3QBGB; "HNet_ApplicationProtocol"
0x18000e232  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x18000e237  mov     ebx, eax
0x18000e239  test    eax, eax
0x18000e23b  jns     short loc_18000E28B
0x18000e23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e244  lea     rax, WPP_GLOBAL_Control
0x18000e24b  mov     r14d, 8
0x18000e251  cmp     rcx, rax
0x18000e254  jz      loc_18000E881
0x18000e25a  test    [rcx+1Ch], r14b
0x18000e25e  jz      loc_18000E881
0x18000e264  cmp     [rcx+19h], dil
0x18000e268  jb      loc_18000E881
0x18000e26e  mov     rcx, [rcx+10h]
0x18000e272  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e279  mov     edx, 0FFh
0x18000e27e  mov     r9d, ebx
0x18000e281  call    WPP_SF_d
0x18000e286  jmp     loc_18000E881
0x18000e28b  test    ebx, ebx
0x18000e28d  jnz     loc_18000E87B
0x18000e293  mov     rcx, [rsp+2D0h+var_298]
0x18000e298  lea     r9, [rsp+2D0h+pvarg]
0x18000e29d  mov     eax, 200Dh
0x18000e2a2  mov     dword ptr [rsp+2D0h+var_2B0], esi
0x18000e2a6  mov     word ptr [rsp+2D0h+pvarg], ax
0x18000e2ab  lea     rdx, ?c_wszResponseArray@@3QBGB; "ResponseArray"
0x18000e2b2  mov     rax, [rsp+2D0h+psa]
0x18000e2b7  xor     r8d, r8d
0x18000e2ba  mov     dword ptr [rsp+2D0h+pvarg+8], eax
0x18000e2be  mov     eax, dword ptr [rsp+2D0h+psa+4]
0x18000e2c2  mov     dword ptr [rsp+2D0h+pvarg+0Ch], eax
0x18000e2c6  mov     rax, [rcx]
0x18000e2c9  mov     rax, [rax+28h]
0x18000e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d2  mov     ebx, eax
0x18000e2d4  test    eax, eax
0x18000e2d6  jns     short loc_18000E30F
0x18000e2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2df  lea     rax, WPP_GLOBAL_Control
0x18000e2e6  cmp     rcx, rax
0x18000e2e9  jz      short loc_18000E30F
0x18000e2eb  test    byte ptr [rcx+1Ch], 8
0x18000e2ef  jz      short loc_18000E30F
0x18000e2f1  cmp     [rcx+19h], dil
0x18000e2f5  jb      short loc_18000E30F
0x18000e2f7  mov     rcx, [rcx+10h]
0x18000e2fb  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000e302  mov     edx, 100h
0x18000e307  mov     r9d, ebx
0x18000e30a  call    WPP_SF_d
0x18000e30f  test    ebx, ebx
0x18000e311  jnz     loc_18000E85D
  ... truncated ...
```
