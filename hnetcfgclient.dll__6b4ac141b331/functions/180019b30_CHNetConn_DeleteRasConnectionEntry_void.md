# CHNetConn::DeleteRasConnectionEntry(void)

- ea: `0x180019b30`
- end: `0x18001a134`
- name: `?DeleteRasConnectionEntry@CHNetConn@@UEAAJXZ`
- size: `1540`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180019674`
- `0x180019b30`
- `0x18001b1e8`
- `0x18001c61c`
- `0x18001d9f4`
- `0x18001e130`
- `0x180028110`
- `0x180028c48`
- `0x180029a74`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180019ed6`
- `msvcrt!_wcsicmp` at `0x180019ed6`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f04`
- `OLEAUT32!__imp_SysFreeString` at `0x180019fd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f04`
- `OLEAUT32!__imp_SysFreeString` at `0x180019fd5`

## pseudocode

```c
__int64 __fastcall CHNetConn::DeleteRasConnectionEntry(const unsigned __int16 **this)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // r9
  int ConnectionPropertiesObject; // eax
  int Properties; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  CHNetCfgMgrChild *v11; // rdi
  int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  int IcmpSettingsInstance; // eax
  const unsigned __int16 *v17; // r8
  int WmiPathFromObject; // eax
  wchar_t *v19; // rdi
  int v20; // eax
  struct IWbemServices **v21; // rdi
  const unsigned __int16 *v22; // rcx
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  int v25; // r14d
  int v26; // eax
  wchar_t *String1; // [rsp+40h] [rbp-19h] BYREF
  struct IWbemClassObject *v29; // [rsp+48h] [rbp-11h] BYREF
  __int64 v30; // [rsp+50h] [rbp-9h] BYREF
  int v31; // [rsp+58h] [rbp-1h] BYREF
  int v32; // [rsp+5Ch] [rbp+3h] BYREF
  __int64 v33; // [rsp+60h] [rbp+7h] BYREF
  struct IWbemClassObject *v34; // [rsp+68h] [rbp+Fh] BYREF
  CHNetCfgMgrChild *v35; // [rsp+70h] [rbp+17h] BYREF
  __int64 v36; // [rsp+78h] [rbp+1Fh] BYREF
  int v37; // [rsp+80h] [rbp+27h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v36 = 0;
  v37 = 0;
  v33 = 0;
  v30 = 0;
  v29 = 0;
  v34 = 0;
  v32 = 0;
  v31 = 0;
  String1 = 0;
  if ( !*((_BYTE *)this + 96) )
  {
    ConnectionPropertiesObject = CHNetConn::GetConnectionPropertiesObject((CHNetConn *)this, &v34);
    v3 = ConnectionPropertiesObject;
    if ( ConnectionPropertiesObject < 0 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_96;
      v4 = 204;
LABEL_93:
      v5 = (unsigned int)ConnectionPropertiesObject;
      goto LABEL_94;
    }
    Properties = CHNetConn::InternalGetProperties((CHNetConn *)this, v34, (struct tagHNET_CONN_PROPERTIES *)&v36);
    if ( Properties < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v9 = 205;
      goto LABEL_44;
    }
    if ( !BYTE2(v36) )
    {
LABEL_38:
      if ( !BYTE1(v36) )
        goto LABEL_51;
      Properties = (*((__int64 (__fastcall **)(const unsigned __int16 **, GUID *, __int64 *))*this + 8))(
                     this,
                     &GUID_85d18b72_3032_11d4_9348_00c04f8eeb71,
                     &v33);
      if ( Properties >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
        if ( v15 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            210,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v15);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        goto LABEL_51;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_51:
        ((void (__fastcall *)(struct IWbemClassObject *))v34->lpVtbl->Release)(v34);
        IcmpSettingsInstance = CHNetConn::GetIcmpSettingsInstance((CHNetConn *)this, &v29);
        if ( IcmpSettingsInstance >= 0 )
        {
          WmiPathFromObject = GetWmiPathFromObject(v29, &String1);
          if ( WmiPathFromObject >= 0 )
          {
            v19 = String1;
            if ( _wcsicmp(String1, L"HNet_FwIcmpSettings.Name=\"Default\"") )
              (*(void (__fastcall **)(const unsigned __int16 *, wchar_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this[8]
                                                                                                  + 128LL))(
                this[8],
                v19,
                0,
                0,
                0);
            SysFreeString(v19);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              212,
              WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
              (unsigned int)WmiPathFromObject);
          }
          ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            211,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)IcmpSettingsInstance);
        }
        v20 = BuildReferencesQueryBstr(&String1, this[9], v17);
        if ( v20 >= 0 )
        {
          v21 = (struct IWbemServices **)(this + 8);
          v22 = this[8];
          v23 = this[15];
          v30 = 0;
          v24 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, wchar_t *, __int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 160LL))(
                  v22,
                  v23,
                  String1,
                  48,
                  0,
                  &v30);
          v25 = v24;
          if ( v24 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              214,
              WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
              (unsigned int)v24);
          }
          SysFreeString(String1);
          if ( v25 >= 0 )
          {
            LODWORD(String1) = 0;
            while ( 1 )
            {
              v29 = 0;
              v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, wchar_t **))(*(_QWORD *)v30 + 32LL))(
                      v30,
                      0xFFFFFFFFLL,
                      1,
                      &v29,
                      &String1);
              if ( v26 < 0 )
                break;
              if ( !v26 && (_DWORD)String1 == 1 )
              {
                DeleteWmiInstance(*v21, v29);
                ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
                if ( (_DWORD)String1 == 1 )
                  continue;
              }
              goto LABEL_87;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                215,
                WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                (unsigned int)v26);
            }
LABEL_87:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              213,
              WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
              (unsigned int)v20);
          }
          v21 = (struct IWbemServices **)(this + 8);
        }
        ConnectionPropertiesObject = ((__int64 (__fastcall *)(struct IWbemServices *, const unsigned __int16 *, _QWORD, _QWORD, _QWORD))(*v21)->lpVtbl->DeleteInstance)(
                                       *v21,
                                       this[9],
                                       0,
                                       0,
                                       0);
        v3 = ConnectionPropertiesObject;
        if ( ConnectionPropertiesObject >= 0 )
          goto LABEL_95;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_96;
        v4 = 216;
        goto LABEL_93;
      }
      v9 = 209;
LABEL_44:
      WPP_SF_d(v8[2], v9, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)Properties);
      goto LABEL_51;
    }
    v35 = 0;
    v10 = ATL::CComObject<CHNetCfgMgrChild>::CreateInstance(&v35);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          206,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)v10);
      }
      goto LABEL_38;
    }
    v11 = v35;
    (*(void (__fastcall **)(CHNetCfgMgrChild *))(*(_QWORD *)v35 + 8LL))(v35);
    v12 = CHNetCfgMgrChild::Initialize(v11, (struct IWbemServices *)this[8]);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*((_QWORD *)v11 + 3) + 40LL))(
              (__int64)v11 + 24,
              &v32,
              &v31);
      if ( v12 >= 0 )
        goto LABEL_37;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v14 = 208;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v14 = 207;
    }
    WPP_SF_d(v13[2], v14, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v12);
LABEL_37:
    (*(void (__fastcall **)(CHNetCfgMgrChild *))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_38;
  }
  v3 = -2147418113;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 2u )
  {
    v4 = 203;
    v5 = 2147549183LL;
LABEL_94:
    WPP_SF_d(v2[2], v4, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
LABEL_95:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_96:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 217, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180019b30  mov     [rsp-8+arg_8], rsi
0x180019b35  mov     [rsp-8+arg_10], rdi
0x180019b3a  push    rbp
0x180019b3b  push    r12
0x180019b3d  push    r13
0x180019b3f  push    r14
0x180019b41  push    r15
0x180019b43  lea     rbp, [rsp-37h]
0x180019b48  sub     rsp, 90h
0x180019b4f  mov     rax, cs:__security_cookie
0x180019b56  xor     rax, rsp
0x180019b59  mov     [rbp+57h+var_28], rax
0x180019b5d  mov     rsi, rcx
0x180019b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b67  lea     r13, WPP_GLOBAL_Control
0x180019b6e  mov     r12b, 8
0x180019b71  cmp     rcx, r13
0x180019b74  jz      short loc_180019B9E
0x180019b76  test    [rcx+1Ch], r12b
0x180019b7a  jz      short loc_180019B9E
0x180019b7c  cmp     byte ptr [rcx+19h], 6
0x180019b80  jb      short loc_180019B9E
0x180019b82  mov     rcx, [rcx+10h]
0x180019b86  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019b8d  mov     edx, 0CAh
0x180019b92  call    WPP_SF_
0x180019b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b9e  xor     r15d, r15d
0x180019ba1  xor     eax, eax
0x180019ba3  mov     [rbp+57h+var_38], rax
0x180019ba7  mov     [rbp+57h+var_30], eax
0x180019baa  mov     [rbp+57h+var_50], r15
0x180019bae  mov     [rbp+57h+var_60], r15
0x180019bb2  mov     [rbp+57h+var_68], r15
0x180019bb6  mov     [rbp+57h+var_48], r15
0x180019bba  mov     [rbp+57h+var_54], r15d
0x180019bbe  mov     [rbp+57h+var_58], r15d
0x180019bc2  mov     [rbp+57h+String1], r15
0x180019bc6  cmp     [rsi+60h], r15b
0x180019bca  jz      short loc_180019BFB
0x180019bcc  mov     edi, 8000FFFFh
0x180019bd1  cmp     rcx, r13
0x180019bd4  jz      loc_18001A109
0x180019bda  test    [rcx+1Ch], r12b
0x180019bde  jz      loc_18001A0E0
0x180019be4  cmp     byte ptr [rcx+19h], 2
0x180019be8  jb      loc_18001A0E0
0x180019bee  mov     edx, 0CBh
0x180019bf3  mov     r9d, edi
0x180019bf6  jmp     loc_18001A0C9
0x180019bfb  lea     rdx, [rbp+57h+var_48]; struct IWbemClassObject **
0x180019bff  mov     rcx, rsi; this
0x180019c02  call    ?GetConnectionPropertiesObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionPropertiesObject(IWbemClassObject * *)
0x180019c07  mov     edi, eax
0x180019c09  test    eax, eax
0x180019c0b  jns     short loc_180019C3B
0x180019c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c14  cmp     rcx, r13
0x180019c17  jz      loc_18001A109
0x180019c1d  test    [rcx+1Ch], r12b
0x180019c21  jz      loc_18001A0E0
0x180019c27  cmp     byte ptr [rcx+19h], 2
0x180019c2b  jb      loc_18001A0E0
0x180019c31  mov     edx, 0CCh
0x180019c36  jmp     loc_18001A0C6
0x180019c3b  mov     rdx, [rbp+57h+var_48]; struct IWbemClassObject *
0x180019c3f  lea     r8, [rbp+57h+var_38]; struct tagHNET_CONN_PROPERTIES *
0x180019c43  mov     rcx, rsi; this
0x180019c46  call    ?InternalGetProperties@CHNetConn@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_CONN_PROPERTIES@@@Z; CHNetConn::InternalGetProperties(IWbemClassObject *,tagHNET_CONN_PROPERTIES *)
0x180019c4b  test    eax, eax
0x180019c4d  jns     short loc_180019C7D
0x180019c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c56  cmp     rcx, r13
0x180019c59  jz      loc_180019E24
0x180019c5f  test    [rcx+1Ch], r12b
0x180019c63  jz      loc_180019E24
0x180019c69  cmp     byte ptr [rcx+19h], 2
0x180019c6d  jb      loc_180019E24
0x180019c73  mov     edx, 0CDh
0x180019c78  jmp     loc_180019DBB
0x180019c7d  cmp     byte ptr [rbp+57h+var_38+2], r15b
0x180019c81  jz      loc_180019D76
0x180019c87  lea     rcx, [rbp+57h+var_40]
0x180019c8b  mov     [rbp+57h+var_40], r15
0x180019c8f  call    ?CreateInstance@?$CComObject@VCHNetCfgMgrChild@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetCfgMgrChild>::CreateInstance(ATL::CComObject<CHNetCfgMgrChild> * *)
0x180019c94  test    eax, eax
0x180019c96  jns     short loc_180019CD9
0x180019c98  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c9f  cmp     rcx, r13
0x180019ca2  jz      loc_180019D76
0x180019ca8  test    [rcx+1Ch], r12b
0x180019cac  jz      loc_180019D76
0x180019cb2  cmp     byte ptr [rcx+19h], 2
0x180019cb6  jb      loc_180019D76
0x180019cbc  mov     rcx, [rcx+10h]
0x180019cc0  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019cc7  mov     edx, 0CEh
0x180019ccc  mov     r9d, eax
0x180019ccf  call    WPP_SF_d
0x180019cd4  jmp     loc_180019D76
0x180019cd9  mov     rdi, [rbp+57h+var_40]
0x180019cdd  mov     rcx, rdi
0x180019ce0  mov     rax, [rdi]
0x180019ce3  mov     rax, [rax+8]
0x180019ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cec  mov     rdx, [rsi+40h]; struct IWbemServices *
0x180019cf0  mov     rcx, rdi; this
0x180019cf3  call    ?Initialize@CHNetCfgMgrChild@@QEAAJPEAUIWbemServices@@@Z; CHNetCfgMgrChild::Initialize(IWbemServices *)
0x180019cf8  test    eax, eax
0x180019cfa  jns     short loc_180019D1B
0x180019cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d03  cmp     rcx, r13
0x180019d06  jz      short loc_180019D67
0x180019d08  test    [rcx+1Ch], r12b
0x180019d0c  jz      short loc_180019D67
0x180019d0e  cmp     byte ptr [rcx+19h], 2
0x180019d12  jb      short loc_180019D67
0x180019d14  mov     edx, 0CFh
0x180019d19  jmp     short loc_180019D54
0x180019d1b  lea     rcx, [rdi+18h]
0x180019d1f  mov     rax, [rcx]
0x180019d22  lea     r8, [rbp+57h+var_58]
0x180019d26  lea     rdx, [rbp+57h+var_54]
0x180019d2a  mov     rax, [rax+28h]
0x180019d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d33  test    eax, eax
0x180019d35  jns     short loc_180019D67
0x180019d37  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d3e  cmp     rcx, r13
0x180019d41  jz      short loc_180019D67
0x180019d43  test    [rcx+1Ch], r12b
0x180019d47  jz      short loc_180019D67
0x180019d49  cmp     byte ptr [rcx+19h], 2
0x180019d4d  jb      short loc_180019D67
0x180019d4f  mov     edx, 0D0h
0x180019d54  mov     rcx, [rcx+10h]
0x180019d58  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019d5f  mov     r9d, eax
0x180019d62  call    WPP_SF_d
0x180019d67  mov     rax, [rdi]
0x180019d6a  mov     rcx, rdi
0x180019d6d  mov     rax, [rax+10h]
0x180019d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d76  cmp     byte ptr [rbp+57h+var_38+1], r15b
0x180019d7a  jz      loc_180019E24
0x180019d80  mov     rax, [rsi]
0x180019d83  lea     r8, [rbp+57h+var_50]
0x180019d87  lea     rdx, _GUID_85d18b72_3032_11d4_9348_00c04f8eeb71
0x180019d8e  mov     rcx, rsi
0x180019d91  mov     rax, [rax+40h]
0x180019d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d9a  test    eax, eax
0x180019d9c  jns     short loc_180019DD0
0x180019d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019da5  cmp     rcx, r13
0x180019da8  jz      short loc_180019E24
0x180019daa  test    [rcx+1Ch], r12b
0x180019dae  jz      short loc_180019E24
0x180019db0  cmp     byte ptr [rcx+19h], 2
0x180019db4  jb      short loc_180019E24
0x180019db6  mov     edx, 0D1h
0x180019dbb  mov     rcx, [rcx+10h]
0x180019dbf  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019dc6  mov     r9d, eax
0x180019dc9  call    WPP_SF_d
0x180019dce  jmp     short loc_180019E24
0x180019dd0  mov     rcx, [rbp+57h+var_50]
0x180019dd4  mov     rax, [rcx]
0x180019dd7  mov     rax, [rax+18h]
0x180019ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019de0  test    eax, eax
0x180019de2  jns     short loc_180019E14
0x180019de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180019deb  cmp     rcx, r13
0x180019dee  jz      short loc_180019E14
0x180019df0  test    [rcx+1Ch], r12b
0x180019df4  jz      short loc_180019E14
0x180019df6  cmp     byte ptr [rcx+19h], 2
0x180019dfa  jb      short loc_180019E14
0x180019dfc  mov     rcx, [rcx+10h]
0x180019e00  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019e07  mov     edx, 0D2h
0x180019e0c  mov     r9d, eax
0x180019e0f  call    WPP_SF_d
0x180019e14  mov     rcx, [rbp+57h+var_50]
0x180019e18  mov     rax, [rcx]
0x180019e1b  mov     rax, [rax+10h]
0x180019e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e24  mov     rcx, [rbp+57h+var_48]
0x180019e28  mov     rax, [rcx]
0x180019e2b  mov     rax, [rax+10h]
0x180019e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e34  lea     rdx, [rbp+57h+var_68]; struct IWbemClassObject **
0x180019e38  mov     rcx, rsi; this
0x180019e3b  call    ?GetIcmpSettingsInstance@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetIcmpSettingsInstance(IWbemClassObject * *)
0x180019e40  test    eax, eax
0x180019e42  jns     short loc_180019E85
0x180019e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e4b  cmp     rcx, r13
0x180019e4e  jz      loc_180019F1A
0x180019e54  test    [rcx+1Ch], r12b
0x180019e58  jz      loc_180019F1A
0x180019e5e  cmp     byte ptr [rcx+19h], 2
0x180019e62  jb      loc_180019F1A
0x180019e68  mov     rcx, [rcx+10h]
0x180019e6c  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019e73  mov     edx, 0D3h
0x180019e78  mov     r9d, eax
0x180019e7b  call    WPP_SF_d
0x180019e80  jmp     loc_180019F1A
0x180019e85  mov     rcx, [rbp+57h+var_68]; struct IWbemClassObject *
0x180019e89  lea     rdx, [rbp+57h+String1]; unsigned __int16 **
0x180019e8d  call    ?GetWmiPathFromObject@@YAJPEAUIWbemClassObject@@PEAPEAG@Z; GetWmiPathFromObject(IWbemClassObject *,ushort * *)
0x180019e92  test    eax, eax
0x180019e94  jns     short loc_180019EC8
0x180019e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e9d  cmp     rcx, r13
0x180019ea0  jz      short loc_180019F0A
0x180019ea2  test    [rcx+1Ch], r12b
0x180019ea6  jz      short loc_180019F0A
0x180019ea8  cmp     byte ptr [rcx+19h], 2
0x180019eac  jb      short loc_180019F0A
0x180019eae  mov     rcx, [rcx+10h]
0x180019eb2  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019eb9  mov     edx, 0D4h
0x180019ebe  mov     r9d, eax
0x180019ec1  call    WPP_SF_d
0x180019ec6  jmp     short loc_180019F0A
0x180019ec8  mov     rdi, [rbp+57h+String1]
0x180019ecc  lea     rdx, ?c_wszDefaultIcmpSettingsPath@@3QBGB; "HNet_FwIcmpSettings.Name=\"Default\""
0x180019ed3  mov     rcx, rdi; String1
0x180019ed6  call    cs:__imp__wcsicmp
0x180019edc  test    eax, eax
0x180019ede  jz      short loc_180019F01
0x180019ee0  mov     rcx, [rsi+40h]
0x180019ee4  xor     r9d, r9d
0x180019ee7  xor     r8d, r8d
0x180019eea  mov     [rsp+0B0h+var_90], r15
0x180019eef  mov     rdx, rdi
0x180019ef2  mov     rax, [rcx]
0x180019ef5  mov     rax, [rax+80h]
0x180019efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f01  mov     rcx, rdi; bstrString
0x180019f04  call    cs:__imp_SysFreeString
0x180019f0a  mov     rcx, [rbp+57h+var_68]
0x180019f0e  mov     rax, [rcx]
0x180019f11  mov     rax, [rax+10h]
0x180019f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f1a  mov     rdx, [rsi+48h]; unsigned __int16 *
0x180019f1e  lea     rcx, [rbp+57h+String1]; unsigned __int16 **
0x180019f22  call    ?BuildReferencesQueryBstr@@YAJPEAPEAGPEBG1@Z; BuildReferencesQueryBstr(ushort * *,ushort const *,ushort const *)
0x180019f27  test    eax, eax
0x180019f29  jns     short loc_180019F64
0x180019f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f32  cmp     rcx, r13
0x180019f35  jz      short loc_180019F5B
0x180019f37  test    [rcx+1Ch], r12b
0x180019f3b  jz      short loc_180019F5B
0x180019f3d  cmp     byte ptr [rcx+19h], 2
0x180019f41  jb      short loc_180019F5B
0x180019f43  mov     rcx, [rcx+10h]
0x180019f47  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019f4e  mov     edx, 0D5h
0x180019f53  mov     r9d, eax
0x180019f56  call    WPP_SF_d
0x180019f5b  lea     rdi, [rsi+40h]
0x180019f5f  jmp     loc_18001A082
0x180019f64  mov     r8, [rbp+57h+String1]
0x180019f68  lea     rdx, [rbp+57h+var_60]
0x180019f6c  mov     [rsp+0B0h+var_88], rdx
0x180019f71  lea     rdi, [rsi+40h]
0x180019f75  mov     rcx, [rdi]
0x180019f78  mov     r9d, 30h ; '0'
0x180019f7e  mov     rdx, [rsi+78h]
0x180019f82  mov     [rbp+57h+var_60], r15
0x180019f86  mov     [rsp+0B0h+var_90], r15
0x180019f8b  mov     rax, [rcx]
0x180019f8e  mov     rax, [rax+0A0h]
0x180019f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f9a  mov     r14d, eax
0x180019f9d  test    eax, eax
0x180019f9f  jns     short loc_180019FD1
0x180019fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fa8  cmp     rcx, r13
0x180019fab  jz      short loc_180019FD1
0x180019fad  test    [rcx+1Ch], r12b
0x180019fb1  jz      short loc_180019FD1
0x180019fb3  cmp     byte ptr [rcx+19h], 2
0x180019fb7  jb      short loc_180019FD1
0x180019fb9  mov     rcx, [rcx+10h]
0x180019fbd  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019fc4  mov     edx, 0D6h
0x180019fc9  mov     r9d, eax
0x180019fcc  call    WPP_SF_d
0x180019fd1  mov     rcx, [rbp+57h+String1]; bstrString
0x180019fd5  call    cs:__imp_SysFreeString
0x180019fdb  test    r14d, r14d
0x180019fde  js      loc_18001A082
0x180019fe4  mov     dword ptr [rbp+57h+String1], r15d
0x180019fe8  mov     rcx, [rbp+57h+var_60]
  ... truncated ...
```
