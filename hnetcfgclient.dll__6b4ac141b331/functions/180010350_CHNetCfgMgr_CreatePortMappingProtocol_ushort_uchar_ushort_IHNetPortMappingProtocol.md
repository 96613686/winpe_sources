# CHNetCfgMgr::CreatePortMappingProtocol(ushort *,uchar,ushort,IHNetPortMappingProtocol * *)

- ea: `0x180010350`
- end: `0x180010bd8`
- name: `?CreatePortMappingProtocol@CHNetCfgMgr@@UEAAJPEAGEGPEAPEAUIHNetPortMappingProtocol@@@Z`
- size: `2184`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, unsigned __int16 *, unsigned __int8, unsigned __int16, struct IHNetPortMappingProtocol **)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180005698`
- `0x18000a45c`
- `0x18000a484`
- `0x180010218`
- `0x180010350`
- `0x180023db8`
- `0x180029a3c`
- `0x18002a07c`
- `0x18002a61c`
- `0x18002a7d4`
- `0x18002ac5c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800106cb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109e6`
- `OLEAUT32!__imp_VariantClear` at `0x180010751`
- `OLEAUT32!__imp_VariantClear` at `0x180010751`

## string_xrefs

- `0x1800107ea`: `IPProtocol`
- `0x18001064a`: `HNet_PortMappingProtocol`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::CreatePortMappingProtocol(
        CHNetCfgMgr *this,
        unsigned __int16 *a2,
        unsigned __int8 a3,
        unsigned __int16 a4,
        struct IHNetPortMappingProtocol **a5)
{
  LONG v6; // r12d
  PVOID *v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  int v13; // eax
  VARTYPE v14; // r11
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  int WmiObjectFromPath; // eax
  int v19; // eax
  __int64 v20; // r9
  CHNetPortMappingProtocol *v21; // rsi
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  struct IWbemClassObject *v26; // [rsp+30h] [rbp-D0h] BYREF
  CHNetPortMappingProtocol *v27; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR psz[256]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v26 = 0;
  if ( !*((_QWORD *)this + 8) )
  {
    v10 = -2147467261;
    if ( v9 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      {
        WPP_SF_d(v9[2], 281, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 6u )
      {
        v11 = 282;
LABEL_134:
        WPP_SF_d(v9[2], v11, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v10);
        return (unsigned int)v10;
      }
    }
    return (unsigned int)v10;
  }
  if ( !a5 )
  {
    v10 = -2147467261;
    if ( v9 == &WPP_GLOBAL_Control )
      return (unsigned int)v10;
    if ( (*((_BYTE *)v9 + 28) & 8) == 0 || *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_130;
    v12 = 283;
LABEL_48:
    WPP_SF_d(v9[2], v12, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v10);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_130;
  }
  *a5 = 0;
  if ( a2 )
  {
    if ( a3 )
    {
      v10 = 0;
      if ( (_WORD)v6 )
        goto LABEL_36;
    }
  }
  v10 = -2147024809;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942487LL);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 && v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 2u )
  {
    WPP_SF_d(v9[2], 285, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942487LL);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 && v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
  {
    WPP_SF_(v9[2], 286, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
LABEL_36:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !(_WORD)v6 && v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
  {
    WPP_SF_(v9[2], 287, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v10 )
  {
    if ( PortMappingProtocolExists(*((struct IWbemServices **)this + 8), *((unsigned __int16 **)this + 11), v6, a3) )
    {
      v10 = -2147019886;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_130;
      v12 = 288;
      goto LABEL_48;
    }
    v13 = SpawnNewInstance(*((struct IWbemServices **)this + 8), L"HNet_PortMappingProtocol", &v26);
    v10 = v13;
    if ( v13 < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_55:
        if ( v10 )
          goto LABEL_130;
        StringCchCopyW(psz, 0x100u, a2);
        pvarg.vt = v14;
        pvarg.llVal = (LONGLONG)SysAllocString(psz);
        if ( !pvarg.llVal )
        {
          v10 = -2147024882;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_126;
          }
          v15 = 291;
LABEL_123:
          v20 = (unsigned int)v10;
LABEL_124:
          WPP_SF_d(v9[2], v15, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v20);
          goto LABEL_125;
        }
        v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v26->lpVtbl->Put)(
                v26,
                L"Name",
                0,
                &pvarg,
                0);
        if ( v10 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            290,
            &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
            (unsigned int)v10);
        }
        VariantClear(&pvarg);
        if ( v10 )
          goto LABEL_125;
        pvarg.vt = 3;
        pvarg.lVal = v6;
        v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v26->lpVtbl->Put)(
                v26,
                L"Port",
                0,
                &pvarg,
                0);
        if ( v10 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_126;
          }
          v15 = 292;
          goto LABEL_123;
        }
        if ( v10 )
          goto LABEL_125;
        pvarg.vt = 17;
        pvarg.bVal = a3;
        v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v26->lpVtbl->Put)(
                v26,
                L"IPProtocol",
                0,
                &pvarg,
                0);
        if ( v10 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_126;
          }
          v15 = 293;
          goto LABEL_123;
        }
        if ( v10 )
          goto LABEL_125;
        v10 = SetBooleanValue(v26, L"BuiltIn", 0);
        if ( v10 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_126;
          }
          v15 = 294;
          goto LABEL_123;
        }
        if ( v10 )
          goto LABEL_125;
        v16 = *((_QWORD *)this + 8);
        v27 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, struct IWbemClassObject *, __int64, _QWORD, CHNetPortMappingProtocol **))(*(_QWORD *)v16 + 112LL))(
                v16,
                v26,
                18,
                0,
                &v27);
        if ( v10 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_126;
          }
          v15 = 295;
          goto LABEL_123;
        }
        if ( v10 )
          goto LABEL_125;
        ((void (__fastcall *)(struct IWbemClassObject *))v26->lpVtbl->Release)(v26);
        v26 = 0;
        v17 = (*(__int64 (__fastcall **)(CHNetPortMappingProtocol *, __int64, BSTR *))(*(_QWORD *)v27 + 32LL))(
                v27,
                0xFFFFFFFFLL,
                &bstrString);
        v10 = v17;
        if ( v17 >= 0 )
        {
          if ( !v17 )
          {
            WmiObjectFromPath = GetWmiObjectFromPath(*((struct IWbemServices **)this + 8), bstrString, &v26);
            v10 = WmiObjectFromPath;
            if ( WmiObjectFromPath < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                297,
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
            296,
            &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
            (unsigned int)v17);
        }
        (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v27 + 16LL))(v27);
        if ( v10 )
          goto LABEL_125;
        v27 = 0;
        v19 = ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance(&v27);
        v10 = v19;
        if ( v19 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_126;
          }
          v15 = 298;
          v20 = (unsigned int)v19;
          goto LABEL_124;
        }
        if ( v19 )
        {
LABEL_125:
          v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_126:
          if ( v26 )
          {
            ((void (__fastcall *)(struct IWbemClassObject *))v26->lpVtbl->Release)(v26);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( !v10 )
          {
            UpdateService(0x87u);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_130;
        }
        v21 = v27;
        (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v27 + 8LL))(v27);
        v22 = CHNetPortMappingProtocol::Initialize(v21, *((struct IWbemServices **)this + 8), v26);
        v10 = v22;
        if ( v22 >= 0 )
        {
          if ( v22 )
            goto LABEL_118;
          v22 = (**(__int64 (__fastcall ***)(CHNetPortMappingProtocol *, GUID *, struct IHNetPortMappingProtocol **))v21)(
                  v21,
                  &GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71,
                  a5);
          v10 = v22;
          if ( v22 >= 0 )
            goto LABEL_118;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_118;
          }
          v24 = 300;
        }
        else
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_118;
          }
          v24 = 299;
        }
        WPP_SF_d(v23[2], v24, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v22);
LABEL_118:
        (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v21 + 16LL))(v21);
        goto LABEL_125;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        289,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v13);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_55;
  }
LABEL_130:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 6u )
  {
    v11 = 301;
    goto LABEL_134;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010350  push    rbp
0x180010352  push    rbx
0x180010353  push    rsi
0x180010354  push    rdi
0x180010355  push    r12
0x180010357  push    r13
0x180010359  push    r14
0x18001035b  push    r15
0x18001035d  lea     rbp, [rsp-178h]
0x180010365  sub     rsp, 278h
0x18001036c  mov     rax, cs:__security_cookie
0x180010373  xor     rax, rsp
0x180010376  mov     [rbp+1B0h+var_50], rax
0x18001037d  mov     r13, [rbp+1B0h+arg_20]
0x180010384  mov     r15b, r8b
0x180010387  movzx   r12d, r9w
0x18001038b  mov     rsi, rdx
0x18001038e  mov     r14, rcx
0x180010391  mov     rcx, cs:WPP_GLOBAL_Control
0x180010398  lea     rax, WPP_GLOBAL_Control
0x18001039f  mov     r11d, 8
0x1800103a5  cmp     rcx, rax
0x1800103a8  jz      short loc_1800103D8
0x1800103aa  test    [rcx+1Ch], r11b
0x1800103ae  jz      short loc_1800103D8
0x1800103b0  cmp     byte ptr [rcx+19h], 6
0x1800103b4  jb      short loc_1800103D8
0x1800103b6  mov     rcx, [rcx+10h]
0x1800103ba  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x1800103c1  mov     edx, 118h
0x1800103c6  call    WPP_SF_
0x1800103cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103d2  mov     r11d, 8
0x1800103d8  xor     eax, eax
0x1800103da  mov     [rsp+2B0h+bstrString], 0
0x1800103e3  xorps   xmm0, xmm0
0x1800103e6  mov     qword ptr [rsp+2B0h+pvarg+10h], rax
0x1800103eb  movups  xmmword ptr [rsp+2B0h+pvarg], xmm0
0x1800103f0  mov     [rsp+2B0h+var_280], rax
0x1800103f5  cmp     [r14+40h], rax
0x1800103f9  jnz     short loc_18001046B
0x1800103fb  lea     rsi, WPP_GLOBAL_Control
0x180010402  mov     ebx, 80004003h
0x180010407  cmp     rcx, rsi
0x18001040a  jz      loc_180010BB3
0x180010410  test    [rcx+1Ch], r11b
0x180010414  jz      short loc_180010444
0x180010416  mov     dil, 2
0x180010419  cmp     [rcx+19h], dil
0x18001041d  jb      short loc_180010444
0x18001041f  mov     rcx, [rcx+10h]
0x180010423  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001042a  mov     edx, 119h
0x18001042f  mov     r9d, ebx
0x180010432  call    WPP_SF_d
0x180010437  mov     rcx, cs:WPP_GLOBAL_Control
0x18001043e  mov     r11d, 8
0x180010444  cmp     rcx, rsi
0x180010447  jz      loc_180010BB3
0x18001044d  test    [rcx+1Ch], r11b
0x180010451  jz      loc_180010BB3
0x180010457  cmp     byte ptr [rcx+19h], 6
0x18001045b  jb      loc_180010BB3
0x180010461  mov     edx, 11Ah
0x180010466  jmp     loc_180010BA0
0x18001046b  test    r13, r13
0x18001046e  jnz     short loc_1800104A6
0x180010470  mov     ebx, 80004003h
0x180010475  lea     rsi, WPP_GLOBAL_Control
0x18001047c  cmp     rcx, rsi
0x18001047f  jz      loc_180010BB3
0x180010485  test    [rcx+1Ch], r11b
0x180010489  jz      loc_180010B8A
0x18001048f  mov     dil, 2
0x180010492  cmp     [rcx+19h], dil
0x180010496  jb      loc_180010B8A
0x18001049c  mov     edx, 11Bh
0x1800104a1  jmp     loc_18001061C
0x1800104a6  mov     [r13+0], rax
0x1800104aa  mov     dil, 2
0x1800104ad  test    rsi, rsi
0x1800104b0  jz      short loc_1800104C3
0x1800104b2  test    r15b, r15b
0x1800104b5  jz      short loc_1800104C3
0x1800104b7  xor     ebx, ebx
0x1800104b9  cmp     ax, r12w
0x1800104bd  jnz     loc_180010574
0x1800104c3  mov     ebx, 80070057h
0x1800104c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104cf  lea     rax, WPP_GLOBAL_Control
0x1800104d6  cmp     rcx, rax
0x1800104d9  jz      short loc_18001050D
0x1800104db  test    [rcx+1Ch], r11b
0x1800104df  jz      short loc_18001050D
0x1800104e1  cmp     [rcx+19h], dil
0x1800104e5  jb      short loc_18001050D
0x1800104e7  mov     rcx, [rcx+10h]
0x1800104eb  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x1800104f2  mov     edx, 11Ch
0x1800104f7  mov     r9d, ebx
0x1800104fa  call    WPP_SF_d
0x1800104ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180010506  lea     rax, WPP_GLOBAL_Control
0x18001050d  test    rsi, rsi
0x180010510  jnz     short loc_180010542
0x180010512  cmp     rcx, rax
0x180010515  jz      short loc_180010542
0x180010517  test    byte ptr [rcx+1Ch], 8
0x18001051b  jz      short loc_180010542
0x18001051d  cmp     [rcx+19h], dil
0x180010521  jb      short loc_180010542
0x180010523  mov     rcx, [rcx+10h]
0x180010527  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001052e  mov     edx, 11Dh
0x180010533  mov     r9d, ebx
0x180010536  call    WPP_SF_d
0x18001053b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010542  test    r15b, r15b
0x180010545  jnz     short loc_18001057B
0x180010547  lea     rdx, WPP_GLOBAL_Control
0x18001054e  cmp     rcx, rdx
0x180010551  jz      short loc_180010582
0x180010553  test    byte ptr [rcx+1Ch], 8
0x180010557  jz      short loc_180010582
0x180010559  cmp     byte ptr [rcx+19h], 5
0x18001055d  jb      short loc_180010582
0x18001055f  mov     rcx, [rcx+10h]
0x180010563  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001056a  mov     edx, 11Eh
0x18001056f  call    WPP_SF_
0x180010574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001057b  lea     rdx, WPP_GLOBAL_Control
0x180010582  xor     eax, eax
0x180010584  cmp     ax, r12w
0x180010588  jnz     short loc_1800105BB
0x18001058a  lea     r11d, [rax+8]
0x18001058e  cmp     rcx, rdx
0x180010591  jz      short loc_1800105C1
0x180010593  test    [rcx+1Ch], r11b
0x180010597  jz      short loc_1800105C1
0x180010599  cmp     byte ptr [rcx+19h], 5
0x18001059d  jb      short loc_1800105C1
0x18001059f  mov     rcx, [rcx+10h]
0x1800105a3  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x1800105aa  mov     edx, 11Fh
0x1800105af  call    WPP_SF_
0x1800105b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105bb  mov     r11d, 8
0x1800105c1  test    ebx, ebx
0x1800105c3  jnz     loc_180010B83
0x1800105c9  mov     rdx, [r14+58h]; unsigned __int16 *
0x1800105cd  mov     r9b, r15b; unsigned __int8
0x1800105d0  mov     rcx, [r14+40h]; struct IWbemServices *
0x1800105d4  movzx   r8d, r12w; unsigned __int16
0x1800105d8  call    ?PortMappingProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z; PortMappingProtocolExists(IWbemServices *,ushort *,ushort,uchar)
0x1800105dd  test    al, al
0x1800105df  jz      short loc_180010641
0x1800105e1  mov     ebx, 80071392h
0x1800105e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105ed  lea     rsi, WPP_GLOBAL_Control
0x1800105f4  cmp     rcx, rsi
0x1800105f7  jz      loc_180010BB3
0x1800105fd  mov     r11d, 8
0x180010603  test    [rcx+1Ch], r11b
0x180010607  jz      loc_180010B8A
0x18001060d  cmp     [rcx+19h], dil
0x180010611  jb      loc_180010B8A
0x180010617  mov     edx, 120h
0x18001061c  mov     rcx, [rcx+10h]
0x180010620  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180010627  mov     r9d, ebx
0x18001062a  call    WPP_SF_d
0x18001062f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010636  mov     r11d, 8
0x18001063c  jmp     loc_180010B8A
0x180010641  mov     rcx, [r14+40h]; struct IWbemServices *
0x180010645  lea     r8, [rsp+2B0h+var_280]; struct IWbemClassObject **
0x18001064a  lea     rdx, ?c_wszHnetPortMappingProtocol@@3QBGB; "HNet_PortMappingProtocol"
0x180010651  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x180010656  mov     ebx, eax
0x180010658  test    eax, eax
0x18001065a  jns     short loc_180010699
0x18001065c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010663  lea     r11, WPP_GLOBAL_Control
0x18001066a  cmp     rcx, r11
0x18001066d  mov     r11d, 8
0x180010673  jz      short loc_1800106A6
0x180010675  test    [rcx+1Ch], r11b
0x180010679  jz      short loc_1800106A6
0x18001067b  cmp     [rcx+19h], dil
0x18001067f  jb      short loc_1800106A6
0x180010681  mov     rcx, [rcx+10h]
0x180010685  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001068c  mov     edx, 121h
0x180010691  mov     r9d, eax
0x180010694  call    WPP_SF_d
0x180010699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106a0  mov     r11d, 8
0x1800106a6  test    ebx, ebx
0x1800106a8  jnz     loc_180010B83
0x1800106ae  mov     r8, rsi; unsigned __int16 *
0x1800106b1  lea     rcx, [rsp+2B0h+psz]; unsigned __int16 *
0x1800106b6  mov     edx, 100h; unsigned __int64
0x1800106bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800106c0  lea     rcx, [rsp+2B0h+psz]; psz
0x1800106c5  mov     word ptr [rsp+2B0h+pvarg], r11w
0x1800106cb  call    cs:__imp_SysAllocString
0x1800106d1  mov     rcx, rax
0x1800106d4  mov     dword ptr [rsp+2B0h+pvarg+8], eax
0x1800106d8  sar     rcx, 20h
0x1800106dc  xor     esi, esi
0x1800106de  mov     dword ptr [rsp+2B0h+pvarg+0Ch], ecx
0x1800106e2  test    rax, rax
0x1800106e5  jz      loc_180010B05
0x1800106eb  mov     rcx, [rsp+2B0h+var_280]
0x1800106f0  lea     r9, [rsp+2B0h+pvarg]
0x1800106f5  xor     r8d, r8d
0x1800106f8  mov     dword ptr [rsp+2B0h+var_290], esi
0x1800106fc  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x180010703  mov     rax, [rcx]
0x180010706  mov     rax, [rax+28h]
0x18001070a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070f  mov     ebx, eax
0x180010711  test    eax, eax
0x180010713  jns     short loc_18001074C
0x180010715  mov     rcx, cs:WPP_GLOBAL_Control
0x18001071c  lea     rax, WPP_GLOBAL_Control
0x180010723  cmp     rcx, rax
0x180010726  jz      short loc_18001074C
0x180010728  test    byte ptr [rcx+1Ch], 8
0x18001072c  jz      short loc_18001074C
0x18001072e  cmp     [rcx+19h], dil
0x180010732  jb      short loc_18001074C
0x180010734  mov     rcx, [rcx+10h]
0x180010738  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001073f  mov     edx, 122h
0x180010744  mov     r9d, ebx
0x180010747  call    WPP_SF_d
0x18001074c  lea     rcx, [rsp+2B0h+pvarg]; pvarg
0x180010751  call    cs:__imp_VariantClear
0x180010757  test    ebx, ebx
0x180010759  jnz     loc_180010B41
0x18001075f  mov     rcx, [rsp+2B0h+var_280]
0x180010764  lea     eax, [rbx+3]
0x180010767  mov     word ptr [rsp+2B0h+pvarg], ax
0x18001076c  lea     r9, [rsp+2B0h+pvarg]
0x180010771  mov     dword ptr [rsp+2B0h+pvarg+8], r12d
0x180010776  lea     rdx, ?c_wszPort@@3QBGB; "Port"
0x18001077d  xor     r8d, r8d
0x180010780  mov     dword ptr [rsp+2B0h+var_290], esi
0x180010784  mov     rax, [rcx]
0x180010787  mov     rax, [rax+28h]
0x18001078b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010790  mov     ebx, eax
0x180010792  test    eax, eax
0x180010794  jns     short loc_1800107CB
0x180010796  mov     rcx, cs:WPP_GLOBAL_Control
0x18001079d  lea     rax, WPP_GLOBAL_Control
0x1800107a4  cmp     rcx, rax
0x1800107a7  jz      loc_180010B48
0x1800107ad  test    byte ptr [rcx+1Ch], 8
0x1800107b1  jz      loc_180010B48
0x1800107b7  cmp     [rcx+19h], dil
0x1800107bb  jb      loc_180010B48
0x1800107c1  mov     edx, 124h
0x1800107c6  jmp     loc_180010B2E
0x1800107cb  test    ebx, ebx
0x1800107cd  jnz     loc_180010B41
0x1800107d3  mov     rcx, [rsp+2B0h+var_280]
0x1800107d8  lea     eax, [rbx+11h]
0x1800107db  mov     word ptr [rsp+2B0h+pvarg], ax
0x1800107e0  lea     r9, [rsp+2B0h+pvarg]
0x1800107e5  mov     byte ptr [rsp+2B0h+pvarg+8], r15b
0x1800107ea  lea     rdx, ?c_wszIPProtocol@@3QBGB; "IPProtocol"
0x1800107f1  xor     r8d, r8d
0x1800107f4  mov     dword ptr [rsp+2B0h+var_290], esi
0x1800107f8  mov     rax, [rcx]
0x1800107fb  mov     rax, [rax+28h]
0x1800107ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010804  mov     ebx, eax
0x180010806  test    eax, eax
0x180010808  jns     short loc_18001083F
0x18001080a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010811  lea     rax, WPP_GLOBAL_Control
0x180010818  cmp     rcx, rax
0x18001081b  jz      loc_180010B48
0x180010821  test    byte ptr [rcx+1Ch], 8
0x180010825  jz      loc_180010B48
0x18001082b  cmp     [rcx+19h], dil
0x18001082f  jb      loc_180010B48
0x180010835  mov     edx, 125h
0x18001083a  jmp     loc_180010B2E
0x18001083f  test    ebx, ebx
0x180010841  jnz     loc_180010B41
0x180010847  mov     rcx, [rsp+2B0h+var_280]; struct IWbemClassObject *
0x18001084c  lea     rdx, ?c_wszBuiltIn@@3QBGB; "BuiltIn"
0x180010853  xor     r8d, r8d; unsigned __int8
0x180010856  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x18001085b  mov     ebx, eax
0x18001085d  test    eax, eax
  ... truncated ...
```
