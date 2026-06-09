# CHNetConn::RestoreIpConfiguration(void)

- ea: `0x18001ee3c`
- end: `0x18001f490`
- name: `?RestoreIpConfiguration@CHNetConn@@IEAAJXZ`
- size: `1620`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800203b0`
- `0x1800275a0`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x1800181b8`
- `0x180018b30`
- `0x18001be10`
- `0x18001c8d8`
- `0x18001d948`
- `0x18001e4dc`
- `0x18001ee3c`
- `0x180027fc4`
- `0x180028210`
- `0x180028c48`
- `0x180029ad0`
- `0x18002a2b4`
- `0x18002ae64`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001f03e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001f03e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f0c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f0c2`
- `OLEAUT32!__imp_VariantInit` at `0x18001eeb5`
- `OLEAUT32!__imp_VariantInit` at `0x18001eec0`
- `OLEAUT32!__imp_VariantInit` at `0x18001eecb`
- `OLEAUT32!__imp_VariantInit` at `0x18001eed7`
- `OLEAUT32!__imp_VariantInit` at `0x18001eeb5`
- `OLEAUT32!__imp_VariantInit` at `0x18001eec0`
- `OLEAUT32!__imp_VariantInit` at `0x18001eecb`
- `OLEAUT32!__imp_VariantInit` at `0x18001eed7`
- `OLEAUT32!__imp_VariantClear` at `0x18001f447`
- `OLEAUT32!__imp_VariantClear` at `0x18001f452`
- `OLEAUT32!__imp_VariantClear` at `0x18001f45d`
- `OLEAUT32!__imp_VariantClear` at `0x18001f468`
- `OLEAUT32!__imp_VariantClear` at `0x18001f447`
- `OLEAUT32!__imp_VariantClear` at `0x18001f452`
- `OLEAUT32!__imp_VariantClear` at `0x18001f45d`
- `OLEAUT32!__imp_VariantClear` at `0x18001f468`

## string_xrefs

- `0x18001efeb`: `HNet_BackupIpConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CHNetConn::RestoreIpConfiguration(CHNetConn *this)
{
  int GuidInternal; // eax
  NTSTATUS IcsBackupSetting; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  char v7; // si
  unsigned int v8; // r12d
  unsigned int v9; // r15d
  unsigned int v10; // r14d
  const unsigned __int16 *v11; // rdx
  bool v12; // sf
  int v13; // eax
  __int64 v14; // rdx
  int DhcpScopeSettings; // eax
  __int64 v16; // rdx
  struct _IP_ADAPTER_ADDRESSES_LH **v17; // rdx
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  struct IWbemClassObject *v20; // [rsp+48h] [rbp-B8h] BYREF
  struct IEnumWbemClassObject *v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v23; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v24; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v25; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v26; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v28[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-18h]
  __int16 v30; // [rsp+F0h] [rbp-10h]
  char v31; // [rsp+F2h] [rbp-Eh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v21 = 0;
  v20 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  VariantInit(&v26);
  VariantInit(&v25);
  VariantInit(&v24);
  v22 = 0;
  memset(v28, 0, sizeof(v28));
  v30 = 1;
  v29 = 0;
  v31 = 0;
  v23 = 0;
  GuidInternal = CHNetConn::GetGuidInternal(this, &v23);
  IcsBackupSetting = GuidInternal;
  if ( GuidInternal < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_96;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v5 = 287;
    goto LABEL_16;
  }
  if ( v23 )
  {
    GuidInternal = CAdapterIpSettings::Initialize((CAdapterIpSettings *)v28, v23);
    IcsBackupSetting = GuidInternal;
    if ( GuidInternal < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_96;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_17;
      v5 = 288;
LABEL_16:
      WPP_SF_d(v4[2], v5, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)GuidInternal);
      v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 289;
LABEL_95:
        WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)IcsBackupSetting);
        goto LABEL_96;
      }
      goto LABEL_96;
    }
  }
  v7 = 1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  IcsBackupSetting = BuildEscapedQuotedEqualsString(&v22, L"Connection", *((const unsigned __int16 **)this + 9));
  if ( IcsBackupSetting )
  {
    v12 = IcsBackupSetting < 0;
  }
  else
  {
    IcsBackupSetting = BuildSelectQueryBstr(&bstrString, v11, L"HNet_BackupIpConfiguration", v22);
    if ( IcsBackupSetting < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        290,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)IcsBackupSetting);
    }
    operator delete[](v22);
    v12 = IcsBackupSetting < 0;
    if ( !IcsBackupSetting )
    {
      v21 = 0;
      IcsBackupSetting = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR, __int64, _QWORD, struct IEnumWbemClassObject **))(**((_QWORD **)this + 8) + 160LL))(
                           *((_QWORD *)this + 8),
                           *((_QWORD *)this + 15),
                           bstrString,
                           48,
                           0,
                           &v21);
      if ( IcsBackupSetting < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          291,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)IcsBackupSetting);
      }
      SysFreeString(bstrString);
      v12 = IcsBackupSetting < 0;
      if ( !IcsBackupSetting )
      {
        LODWORD(bstrString) = 0;
        v20 = 0;
        v13 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, BSTR *))v21->lpVtbl->Next)(
                v21,
                0xFFFFFFFFLL,
                1,
                &v20,
                &bstrString);
        if ( v13 >= 0 )
        {
          if ( (_DWORD)bstrString == 1 )
          {
LABEL_41:
            ValidateFinishedWCOEnum(*((struct IWbemServices **)this + 8), v21);
            ((void (__fastcall *)(struct IEnumWbemClassObject *))v21->lpVtbl->Release)(v21);
            goto LABEL_44;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            292,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v13);
        }
        v20 = 0;
        goto LABEL_41;
      }
    }
  }
  if ( v12 )
  {
LABEL_86:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_87;
  }
LABEL_44:
  IcsBackupSetting = GetIcsBackupSetting(v20, L"EnableDHCP", &pvarg);
  if ( IcsBackupSetting < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 293;
LABEL_49:
      WPP_SF_d(v4[2], v14, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)IcsBackupSetting);
      goto LABEL_86;
    }
    goto LABEL_87;
  }
  if ( IcsBackupSetting || pvarg.lVal == 1 )
    goto LABEL_86;
  IcsBackupSetting = GetIcsBackupSetting(v20, L"IPAddress", &v26);
  if ( IcsBackupSetting >= 0 )
  {
    if ( IcsBackupSetting )
      goto LABEL_86;
    v7 = 0;
    LODWORD(bstrString) = 0;
    DhcpScopeSettings = ReadDhcpScopeSettings((unsigned int *)&bstrString, (unsigned int *)&v22, 0);
    if ( DhcpScopeSettings >= 0 )
    {
      v10 = _byteswap_ulong(IpPszToHostAddr(v26.bstrVal));
      if ( v10 == (_DWORD)bstrString || !(unsigned __int8)IsValidIPAddress(v10) )
        v7 = 1;
    }
    else
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_67:
        IcsBackupSetting = 0;
        if ( v7 )
          goto LABEL_87;
        IcsBackupSetting = GetIcsBackupSetting(v20, L"SubnetMask", &v25);
        if ( IcsBackupSetting >= 0 )
        {
          if ( IcsBackupSetting )
          {
LABEL_83:
            v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_84:
            v7 = 1;
            goto LABEL_87;
          }
          v9 = _byteswap_ulong(IpPszToHostAddr(v25.bstrVal));
          if ( !(unsigned __int8)IsValidIPAddress(v9) )
          {
            v7 = 1;
            goto LABEL_86;
          }
          IcsBackupSetting = GetIcsBackupSetting(v20, L"DefaultGateway", &v24);
          if ( IcsBackupSetting >= 0 )
          {
            if ( !IcsBackupSetting )
            {
              v8 = _byteswap_ulong(IpPszToHostAddr(v24.bstrVal));
              goto LABEL_86;
            }
            goto LABEL_83;
          }
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          v16 = 297;
        }
        else
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          v16 = 296;
        }
        WPP_SF_d(v4[2], v16, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)IcsBackupSetting);
        goto LABEL_83;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        295,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)DhcpScopeSettings);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_67;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 294;
    goto LABEL_49;
  }
LABEL_87:
  v17 = (struct _IP_ADAPTER_ADDRESSES_LH **)v20;
  if ( v20 )
  {
    DeleteWmiInstance(*((struct IWbemServices **)this + 8), v20);
    ((void (__fastcall *)(struct IWbemClassObject *))v20->lpVtbl->Release)(v20);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IcsBackupSetting >= 0 )
  {
    LOBYTE(v17) = v7;
    IcsBackupSetting = CAdapterIpSettings::ChangeIPSettings((CAdapterIpSettings *)v28, v17, v10, v9, v8);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 298;
    goto LABEL_95;
  }
LABEL_96:
  CAdapterIpSettings::~CAdapterIpSettings((CAdapterIpSettings *)v28);
  VariantClear(&v24);
  VariantClear(&v25);
  VariantClear(&v26);
  VariantClear(&pvarg);
  return (unsigned int)IcsBackupSetting;
}

```

## disassembly

```asm
0x18001ee3c  push    rbp
0x18001ee3e  push    rbx
0x18001ee3f  push    rsi
0x18001ee40  push    rdi
0x18001ee41  push    r12
0x18001ee43  push    r13
0x18001ee45  push    r14
0x18001ee47  push    r15
0x18001ee49  lea     rbp, [rsp-8]
0x18001ee4e  sub     rsp, 108h
0x18001ee55  mov     rax, cs:__security_cookie
0x18001ee5c  xor     rax, rsp
0x18001ee5f  mov     [rbp+40h+var_48], rax
0x18001ee63  mov     r13, rcx
0x18001ee66  lea     r14, WPP_GLOBAL_Control
0x18001ee6d  lea     r15, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ee74  mov     sil, 8
0x18001ee77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee7e  cmp     rcx, r14
0x18001ee81  jz      short loc_18001EEA0
0x18001ee83  test    [rcx+1Ch], sil
0x18001ee87  jz      short loc_18001EEA0
0x18001ee89  cmp     byte ptr [rcx+19h], 6
0x18001ee8d  jb      short loc_18001EEA0
0x18001ee8f  mov     edx, 11Eh
0x18001ee94  mov     r8, r15
0x18001ee97  mov     rcx, [rcx+10h]
0x18001ee9b  call    WPP_SF_
0x18001eea0  xor     edi, edi
0x18001eea2  mov     [rsp+140h+var_F0], rdi
0x18001eea7  mov     [rsp+140h+var_F8], rdi
0x18001eeac  mov     [rsp+140h+bstrString], rdi
0x18001eeb1  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18001eeb5  call    cs:__imp_VariantInit
0x18001eebb  nop
0x18001eebc  lea     rcx, [rbp+40h+var_A8]; pvarg
0x18001eec0  call    cs:__imp_VariantInit
0x18001eec6  nop
0x18001eec7  lea     rcx, [rbp+40h+var_C0]; pvarg
0x18001eecb  call    cs:__imp_VariantInit
0x18001eed1  nop
0x18001eed2  lea     rcx, [rsp+140h+var_D8]; pvarg
0x18001eed7  call    cs:__imp_VariantInit
0x18001eedd  nop
0x18001eede  mov     [rsp+140h+var_E8], rdi
0x18001eee3  xorps   xmm0, xmm0
0x18001eee6  movdqu  [rbp+40h+var_78], xmm0
0x18001eeeb  mov     [rbp+40h+var_50], 1
0x18001eef1  mov     [rbp+40h+var_58], rdi
0x18001eef5  mov     [rbp+40h+var_4E], dil
0x18001eef9  movups  [rbp+40h+var_68], xmm0
0x18001eefd  mov     [rsp+140h+var_E0], rdi
0x18001ef02  lea     rdx, [rsp+140h+var_E0]; struct _GUID **
0x18001ef07  mov     rcx, r13; this
0x18001ef0a  call    ?GetGuidInternal@CHNetConn@@IEAAJPEAPEAU_GUID@@@Z; CHNetConn::GetGuidInternal(_GUID * *)
0x18001ef0f  mov     ebx, eax
0x18001ef11  test    eax, eax
0x18001ef13  jns     short loc_18001EF3B
0x18001ef15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef1c  cmp     rcx, r14
0x18001ef1f  jz      loc_18001F438
0x18001ef25  test    [rcx+1Ch], sil
0x18001ef29  jz      short loc_18001EF8E
0x18001ef2b  mov     dil, 2
0x18001ef2e  cmp     [rcx+19h], dil
0x18001ef32  jb      short loc_18001EF8E
0x18001ef34  mov     edx, 11Fh
0x18001ef39  jmp     short loc_18001EF78
0x18001ef3b  mov     rdx, [rsp+140h+var_E0]; struct _GUID *
0x18001ef40  test    rdx, rdx
0x18001ef43  jz      short loc_18001EFB8
0x18001ef45  lea     rcx, [rbp+40h+var_78]; this
0x18001ef49  call    ?Initialize@CAdapterIpSettings@@QEAAJPEAU_GUID@@@Z; CAdapterIpSettings::Initialize(_GUID *)
0x18001ef4e  mov     ebx, eax
0x18001ef50  test    eax, eax
0x18001ef52  jns     short loc_18001EFB8
0x18001ef54  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef5b  cmp     rcx, r14
0x18001ef5e  jz      loc_18001F438
0x18001ef64  test    [rcx+1Ch], sil
0x18001ef68  jz      short loc_18001EF8E
0x18001ef6a  mov     dil, 2
0x18001ef6d  cmp     [rcx+19h], dil
0x18001ef71  jb      short loc_18001EF8E
0x18001ef73  mov     edx, 120h
0x18001ef78  mov     r9d, eax
0x18001ef7b  mov     r8, r15
0x18001ef7e  mov     rcx, [rcx+10h]
0x18001ef82  call    WPP_SF_d
0x18001ef87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef8e  cmp     rcx, r14
0x18001ef91  jz      loc_18001F438
0x18001ef97  test    [rcx+1Ch], sil
0x18001ef9b  jz      loc_18001F438
0x18001efa1  cmp     byte ptr [rcx+19h], 6
0x18001efa5  jb      loc_18001F438
0x18001efab  mov     edx, 121h
0x18001efb0  mov     r8, r15
0x18001efb3  jmp     loc_18001F42B
0x18001efb8  mov     sil, 1
0x18001efbb  mov     r12d, edi
0x18001efbe  mov     r15d, edi
0x18001efc1  mov     r14d, edi
0x18001efc4  mov     r8, [r13+48h]; unsigned __int16 *
0x18001efc8  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x18001efcf  lea     rcx, [rsp+140h+var_E8]; unsigned __int16 **
0x18001efd4  call    ?BuildEscapedQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildEscapedQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x18001efd9  mov     ebx, eax
0x18001efdb  mov     dil, 2
0x18001efde  test    eax, eax
0x18001efe0  jnz     loc_18001F16B
0x18001efe6  mov     r9, [rsp+140h+var_E8]; unsigned __int16 *
0x18001efeb  lea     r8, ?c_wszBackupIpConfiguration@@3QBGB; "HNet_BackupIpConfiguration"
0x18001eff2  lea     rcx, [rsp+140h+bstrString]; unsigned __int16 **
0x18001eff7  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x18001effc  mov     ebx, eax
0x18001effe  test    eax, eax
0x18001f000  jns     short loc_18001F039
0x18001f002  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f009  lea     rax, WPP_GLOBAL_Control
0x18001f010  cmp     rcx, rax
0x18001f013  jz      short loc_18001F039
0x18001f015  test    byte ptr [rcx+1Ch], 8
0x18001f019  jz      short loc_18001F039
0x18001f01b  cmp     [rcx+19h], dil
0x18001f01f  jb      short loc_18001F039
0x18001f021  mov     edx, 122h
0x18001f026  mov     r9d, ebx
0x18001f029  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f030  mov     rcx, [rcx+10h]
0x18001f034  call    WPP_SF_d
0x18001f039  mov     rcx, [rsp+140h+var_E8]
0x18001f03e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001f044  test    ebx, ebx
0x18001f046  jnz     loc_18001F16D
0x18001f04c  mov     [rsp+140h+var_F0], r12
0x18001f051  mov     rcx, [r13+40h]
0x18001f055  mov     rax, [rcx]
0x18001f058  lea     rdx, [rsp+140h+var_F0]
0x18001f05d  mov     [rsp+140h+var_118], rdx
0x18001f062  mov     qword ptr [rsp+140h+var_120], r12
0x18001f067  lea     r9d, [rbx+30h]
0x18001f06b  mov     r8, [rsp+140h+bstrString]
0x18001f070  mov     rdx, [r13+78h]
0x18001f074  mov     rax, [rax+0A0h]
0x18001f07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f080  mov     ebx, eax
0x18001f082  test    eax, eax
0x18001f084  jns     short loc_18001F0BD
0x18001f086  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f08d  lea     rax, WPP_GLOBAL_Control
0x18001f094  cmp     rcx, rax
0x18001f097  jz      short loc_18001F0BD
0x18001f099  test    byte ptr [rcx+1Ch], 8
0x18001f09d  jz      short loc_18001F0BD
0x18001f09f  cmp     [rcx+19h], dil
0x18001f0a3  jb      short loc_18001F0BD
0x18001f0a5  mov     edx, 123h
0x18001f0aa  mov     r9d, ebx
0x18001f0ad  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f0b4  mov     rcx, [rcx+10h]
0x18001f0b8  call    WPP_SF_d
0x18001f0bd  mov     rcx, [rsp+140h+bstrString]; bstrString
0x18001f0c2  call    cs:__imp_SysFreeString
0x18001f0c8  test    ebx, ebx
0x18001f0ca  jnz     loc_18001F16D
0x18001f0d0  mov     dword ptr [rsp+140h+bstrString], r12d
0x18001f0d5  mov     [rsp+140h+var_F8], r12
0x18001f0da  mov     rcx, [rsp+140h+var_F0]
0x18001f0df  mov     rax, [rcx]
0x18001f0e2  lea     rdx, [rsp+140h+bstrString]
0x18001f0e7  mov     qword ptr [rsp+140h+var_120], rdx
0x18001f0ec  lea     r9, [rsp+140h+var_F8]
0x18001f0f1  lea     r8d, [rbx+1]
0x18001f0f5  or      edx, 0FFFFFFFFh
0x18001f0f8  mov     rax, [rax+20h]
0x18001f0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f101  test    eax, eax
0x18001f103  jns     short loc_18001F13E
0x18001f105  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f10c  lea     rdx, WPP_GLOBAL_Control
0x18001f113  cmp     rcx, rdx
0x18001f116  jz      short loc_18001F145
0x18001f118  test    byte ptr [rcx+1Ch], 8
0x18001f11c  jz      short loc_18001F145
0x18001f11e  cmp     [rcx+19h], dil
0x18001f122  jb      short loc_18001F145
0x18001f124  mov     edx, 124h
0x18001f129  mov     r9d, eax
0x18001f12c  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f133  mov     rcx, [rcx+10h]
0x18001f137  call    WPP_SF_d
0x18001f13c  jmp     short loc_18001F145
0x18001f13e  cmp     dword ptr [rsp+140h+bstrString], 1
0x18001f143  jz      short loc_18001F14A
0x18001f145  mov     [rsp+140h+var_F8], r12
0x18001f14a  mov     rdx, [rsp+140h+var_F0]; struct IEnumWbemClassObject *
0x18001f14f  mov     rcx, [r13+40h]; struct IWbemServices *
0x18001f153  call    ?ValidateFinishedWCOEnum@@YAXPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; ValidateFinishedWCOEnum(IWbemServices *,IEnumWbemClassObject *)
0x18001f158  mov     rcx, [rsp+140h+var_F0]
0x18001f15d  mov     rax, [rcx]
0x18001f160  mov     rax, [rax+10h]
0x18001f164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f169  jmp     short loc_18001F173
0x18001f16b  test    ebx, ebx
0x18001f16d  js      loc_18001F3B1
0x18001f173  lea     r8, [rbp+40h+pvarg]; struct tagVARIANT *
0x18001f177  lea     rdx, ?c_wszEnableDHCP@@3QBGB; "EnableDHCP"
0x18001f17e  mov     rcx, [rsp+140h+var_F8]; struct IWbemClassObject *
0x18001f183  call    ?GetIcsBackupSetting@@YAJPEAUIWbemClassObject@@PEBGPEAUtagVARIANT@@@Z; GetIcsBackupSetting(IWbemClassObject *,ushort const *,tagVARIANT *)
0x18001f188  mov     ebx, eax
0x18001f18a  test    eax, eax
0x18001f18c  jns     short loc_18001F1D6
0x18001f18e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f195  lea     rax, WPP_GLOBAL_Control
0x18001f19c  cmp     rcx, rax
0x18001f19f  jz      loc_18001F3B8
0x18001f1a5  test    byte ptr [rcx+1Ch], 8
0x18001f1a9  jz      loc_18001F3B8
0x18001f1af  cmp     [rcx+19h], dil
0x18001f1b3  jb      loc_18001F3B8
0x18001f1b9  mov     edx, 125h
0x18001f1be  mov     r9d, ebx
0x18001f1c1  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f1c8  mov     rcx, [rcx+10h]
0x18001f1cc  call    WPP_SF_d
0x18001f1d1  jmp     loc_18001F3B1
0x18001f1d6  test    ebx, ebx
0x18001f1d8  jnz     loc_18001F3B1
0x18001f1de  cmp     dword ptr [rbp+40h+pvarg+8], 1
0x18001f1e2  jz      loc_18001F3B1
0x18001f1e8  lea     r8, [rbp+40h+var_A8]; struct tagVARIANT *
0x18001f1ec  lea     rdx, ?c_wszIPAddress@@3QBGB; "IPAddress"
0x18001f1f3  mov     rcx, [rsp+140h+var_F8]; struct IWbemClassObject *
0x18001f1f8  call    ?GetIcsBackupSetting@@YAJPEAUIWbemClassObject@@PEBGPEAUtagVARIANT@@@Z; GetIcsBackupSetting(IWbemClassObject *,ushort const *,tagVARIANT *)
0x18001f1fd  mov     ebx, eax
0x18001f1ff  test    eax, eax
0x18001f201  jns     short loc_18001F235
0x18001f203  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f20a  lea     rax, WPP_GLOBAL_Control
0x18001f211  cmp     rcx, rax
0x18001f214  jz      loc_18001F3B8
0x18001f21a  test    byte ptr [rcx+1Ch], 8
0x18001f21e  jz      loc_18001F3B8
0x18001f224  cmp     [rcx+19h], dil
0x18001f228  jb      loc_18001F3B8
0x18001f22e  mov     edx, 126h
0x18001f233  jmp     short loc_18001F1BE
0x18001f235  test    ebx, ebx
0x18001f237  jnz     loc_18001F3B1
0x18001f23d  xor     sil, sil
0x18001f240  mov     dword ptr [rsp+140h+bstrString], r12d
0x18001f245  xor     r8d, r8d; int
0x18001f248  lea     rdx, [rsp+140h+var_E8]; unsigned int *
0x18001f24d  lea     rcx, [rsp+140h+bstrString]; unsigned int *
0x18001f252  call    ?ReadDhcpScopeSettings@@YAJPEAK0H@Z; ReadDhcpScopeSettings(ulong *,ulong *,int)
0x18001f257  test    eax, eax
0x18001f259  jns     short loc_18001F294
0x18001f25b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f262  lea     rdx, WPP_GLOBAL_Control
0x18001f269  cmp     rcx, rdx
0x18001f26c  jz      short loc_18001F2C0
0x18001f26e  test    byte ptr [rcx+1Ch], 8
0x18001f272  jz      short loc_18001F2C0
0x18001f274  cmp     [rcx+19h], dil
0x18001f278  jb      short loc_18001F2C0
0x18001f27a  mov     edx, 127h
0x18001f27f  mov     r9d, eax
0x18001f282  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f289  mov     rcx, [rcx+10h]
0x18001f28d  call    WPP_SF_d
0x18001f292  jmp     short loc_18001F2B9
0x18001f294  mov     rcx, qword ptr [rbp+40h+var_A8+8]; unsigned __int16 *
0x18001f298  call    ?IpPszToHostAddr@@YAKPEBG@Z; IpPszToHostAddr(ushort const *)
0x18001f29d  mov     r14d, eax
0x18001f2a0  bswap   r14d
0x18001f2a3  cmp     r14d, dword ptr [rsp+140h+bstrString]
0x18001f2a8  jz      short loc_18001F2B6
0x18001f2aa  mov     ecx, r14d
0x18001f2ad  call    IsValidIPAddress
0x18001f2b2  test    al, al
0x18001f2b4  jnz     short loc_18001F2B9
0x18001f2b6  mov     sil, 1
0x18001f2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2c0  xor     ebx, ebx
0x18001f2c2  test    sil, sil
0x18001f2c5  jnz     loc_18001F3B8
0x18001f2cb  lea     r8, [rbp+40h+var_C0]; struct tagVARIANT *
0x18001f2cf  lea     rdx, ?c_wszSubnetMask@@3QBGB; "SubnetMask"
0x18001f2d6  mov     rcx, [rsp+140h+var_F8]; struct IWbemClassObject *
0x18001f2db  call    ?GetIcsBackupSetting@@YAJPEAUIWbemClassObject@@PEBGPEAUtagVARIANT@@@Z; GetIcsBackupSetting(IWbemClassObject *,ushort const *,tagVARIANT *)
0x18001f2e0  mov     ebx, eax
0x18001f2e2  test    eax, eax
0x18001f2e4  jns     short loc_18001F318
0x18001f2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2ed  lea     rax, WPP_GLOBAL_Control
0x18001f2f4  cmp     rcx, rax
0x18001f2f7  jz      loc_18001F39C
0x18001f2fd  test    byte ptr [rcx+1Ch], 8
0x18001f301  jz      loc_18001F39C
  ... truncated ...
```
