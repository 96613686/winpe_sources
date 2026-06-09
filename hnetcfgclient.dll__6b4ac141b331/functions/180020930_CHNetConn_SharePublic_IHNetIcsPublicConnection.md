# CHNetConn::SharePublic(IHNetIcsPublicConnection * *)

- ea: `0x180020930`
- end: `0x180020ee6`
- name: `?SharePublic@CHNetConn@@UEAAJPEAPEAUIHNetIcsPublicConnection@@@Z`
- size: `1462`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct IHNetIcsPublicConnection **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000fd70`
- `0x18001b1e8`
- `0x18001e004`
- `0x18001e130`
- `0x18001e7f0`
- `0x18001e954`
- `0x180020930`
- `0x180021458`
- `0x180029c80`
- `0x18002a61c`
- `0x18002ab30`
- `0x18002ae2c`
- `0x18002d1d2`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e80`
- `WININET!InternetQueryOptionW` at `0x180020dae`
- `WININET!InternetQueryOptionW` at `0x180020dae`
- `WININET!InternetSetOptionW` at `0x180020dd7`
- `WININET!InternetSetOptionW` at `0x180020dd7`
- `RASAPI32!RasSetAutodialAddressW` at `0x180020e75`
- `RASAPI32!RasSetAutodialAddressW` at `0x180020e75`

## pseudocode

```c
__int64 __fastcall CHNetConn::SharePublic(CHNetConn *this, struct IHNetIcsPublicConnection **a2)
{
  PVOID *v4; // rcx
  unsigned int updated; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // ecx
  int ConnectionPropertiesObject; // eax
  int Properties; // eax
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // esi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  bool v19; // sf
  __int64 v20; // rax
  WCHAR *v21; // rcx
  WCHAR *szEntry; // rax
  __int64 v23; // rdx
  WCHAR *v24; // rcx
  int Buffer; // [rsp+30h] [rbp-D0h] BYREF
  struct IWbemClassObject *v27; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwBufferLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  tagRASAUTODIALENTRYW v31; // [rsp+60h] [rbp-A0h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v29 = 0;
  v30 = 0;
  v27 = 0;
  if ( a2 )
  {
    *a2 = 0;
    updated = 0;
    if ( CHNetConn::ProhibitedByPolicy(this, 0x32u) )
    {
      updated = -2147024891;
      v8 = (unsigned int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          2147942405LL);
      }
    }
    if ( IsRoutingProtocolInstalled(v8) )
    {
      updated = -2147024114;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return updated;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_94;
      v6 = 120;
      goto LABEL_10;
    }
    if ( updated )
      goto LABEL_93;
    ConnectionPropertiesObject = CHNetConn::GetConnectionPropertiesObject(this, &v27);
    updated = ConnectionPropertiesObject;
    if ( ConnectionPropertiesObject < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return updated;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_94;
      v6 = 121;
LABEL_28:
      v7 = (unsigned int)ConnectionPropertiesObject;
      goto LABEL_11;
    }
    if ( ConnectionPropertiesObject )
      goto LABEL_93;
    Properties = CHNetConn::InternalGetProperties(this, v27, (struct tagHNET_CONN_PROPERTIES *)&v29);
    updated = Properties;
    if ( Properties < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)Properties);
    }
    UpdatePropertiesWithNetcon2(this, (struct tagHNET_CONN_PROPERTIES *)&v29);
    if ( !updated )
    {
      if ( !(_BYTE)v30 || BYTE2(v29) == 1 )
      {
        updated = -2147418113;
      }
      else
      {
        v11 = SetBooleanValue(v27, L"IsIcsPublic", 1u);
        updated = v11;
        if ( v11 >= 0 )
        {
          if ( v11 )
            goto LABEL_53;
          v11 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64))(**((_QWORD **)this + 8) + 112LL))(
                  *((_QWORD *)this + 8),
                  v27,
                  1);
          updated = v11;
          if ( v11 >= 0 )
          {
            if ( !v11 )
              CHNetConn::UpdateNetman(this);
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v13 = 124;
              goto LABEL_49;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 123;
LABEL_49:
            WPP_SF_d(v12[2], v13, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v11);
          }
        }
      }
    }
LABEL_53:
    ((void (__fastcall *)(struct IWbemClassObject *))v27->lpVtbl->Release)(v27);
    if ( updated )
      goto LABEL_93;
    *(_QWORD *)dwBufferLength = 0;
    ConnectionPropertiesObject = ATL::CComObject<CHNIcsPublicConn>::CreateInstance(dwBufferLength);
    updated = ConnectionPropertiesObject;
    if ( ConnectionPropertiesObject < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return updated;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_94;
      v6 = 125;
      goto LABEL_28;
    }
    v14 = *(_QWORD *)dwBufferLength;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)dwBufferLength + 8LL))(*(_QWORD *)dwBufferLength);
    v15 = CHNetConn::InitializeFull(
            (CHNetConn *)(v14 + 8),
            *((struct IWbemServices **)this + 8),
            *((unsigned __int16 **)this + 9),
            *((unsigned __int16 **)this + 10),
            *((_BYTE *)this + 96));
    v16 = v15;
    if ( v15 >= 0 )
    {
      v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IHNetIcsPublicConnection **))v14)(
              v14,
              &GUID_85d18b73_3032_11d4_9348_00c04f8eeb71,
              a2);
      v16 = v15;
      if ( v15 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 127;
          goto LABEL_69;
        }
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 126;
LABEL_69:
        WPP_SF_d(v17[2], v18, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v15);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v16 )
    {
      updated = v16;
    }
    else
    {
      *(_OWORD *)dwBufferLength = *(_OWORD *)*((_QWORD *)this + 13);
      updated = UpdateSharingSettingsFromStorage((struct _GUID *)dwBufferLength, 1);
      if ( updated )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 24LL))(*a2);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
        *a2 = 0;
        v19 = (updated & 0x80000000) != 0;
        if ( (int)updated > 0 )
        {
          updated = (unsigned __int16)updated | 0x80070000;
          v19 = (updated & 0x80000000) != 0;
        }
        if ( v19
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, updated);
        }
      }
      else
      {
        updated = 0;
      }
      CHNetConn::RefreshNetConnectionsUI(this, 0);
      if ( !updated )
      {
        if ( *((_BYTE *)this + 96) )
        {
          Buffer = 0;
          dwBufferLength[0] = 4;
          if ( InternetQueryOptionW(0, 0x52u, &Buffer, dwBufferLength) && Buffer == 2 )
          {
            Buffer = 4;
            InternetSetOptionW(0, 0x52u, &Buffer, 4u);
          }
        }
        else
        {
          memset_0(&v31, 0, sizeof(v31));
          v20 = *(_QWORD *)this;
          *(_QWORD *)dwBufferLength = 0;
          if ( !(*(unsigned int (__fastcall **)(CHNetConn *, DWORD *))(v20 + 40))(this, dwBufferLength) )
          {
            memset_0(&v31.dwFlags, 0, 0x20Cu);
            v21 = *(WCHAR **)dwBufferLength;
            szEntry = v31.szEntry;
            v23 = 257;
            v31.dwSize = 528;
            do
            {
              if ( !*v21 )
                break;
              *szEntry++ = *v21++;
              --v23;
            }
            while ( v23 );
            v24 = szEntry - 1;
            if ( v23 )
              v24 = szEntry;
            *v24 = 0;
            RasSetAutodialAddressW(0, 0, &v31, 0x210u, 1u);
            CoTaskMemFree(*(LPVOID *)dwBufferLength);
          }
        }
      }
    }
    goto LABEL_93;
  }
  updated = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return updated;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v6 = 118;
LABEL_10:
    v7 = updated;
LABEL_11:
    WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
LABEL_93:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_94:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 130, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, updated);
  return updated;
}

```

## disassembly

```asm
0x180020930  mov     [rsp-8+arg_10], rbx
0x180020935  push    rbp
0x180020936  push    rsi
0x180020937  push    rdi
0x180020938  push    r12
0x18002093a  push    r13
0x18002093c  push    r14
0x18002093e  push    r15
0x180020940  lea     rbp, [rsp-180h]
0x180020948  sub     rsp, 280h
0x18002094f  mov     rax, cs:__security_cookie
0x180020956  xor     rax, rsp
0x180020959  mov     [rbp+1B0h+var_40], rax
0x180020960  mov     r14, rdx
0x180020963  mov     rdi, rcx
0x180020966  mov     rcx, cs:WPP_GLOBAL_Control
0x18002096d  lea     r13, WPP_GLOBAL_Control
0x180020974  lea     rsi, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002097b  mov     r12b, 8
0x18002097e  cmp     rcx, r13
0x180020981  jz      short loc_1800209A7
0x180020983  test    [rcx+1Ch], r12b
0x180020987  jz      short loc_1800209A7
0x180020989  cmp     byte ptr [rcx+19h], 6
0x18002098d  jb      short loc_1800209A7
0x18002098f  mov     rcx, [rcx+10h]
0x180020993  mov     edx, 75h ; 'u'
0x180020998  mov     r8, rsi
0x18002099b  call    WPP_SF_
0x1800209a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209a7  xor     eax, eax
0x1800209a9  xor     r15d, r15d
0x1800209ac  mov     [rsp+2B0h+var_260], rax
0x1800209b1  mov     [rsp+2B0h+var_258], eax
0x1800209b5  mov     [rsp+2B0h+var_278], r15
0x1800209ba  test    r14, r14
0x1800209bd  jnz     short loc_1800209F8
0x1800209bf  mov     ebx, 80004003h
0x1800209c4  cmp     rcx, r13
0x1800209c7  jz      loc_180020EBA
0x1800209cd  test    [rcx+1Ch], r12b
0x1800209d1  jz      loc_180020E91
0x1800209d7  cmp     byte ptr [rcx+19h], 2
0x1800209db  jb      loc_180020E91
0x1800209e1  lea     edx, [rax+76h]
0x1800209e4  mov     r9d, ebx
0x1800209e7  mov     rcx, [rcx+10h]
0x1800209eb  mov     r8, rsi
0x1800209ee  call    WPP_SF_d
0x1800209f3  jmp     loc_180020E8A
0x1800209f8  mov     edx, 32h ; '2'; unsigned int
0x1800209fd  mov     [r14], r15
0x180020a00  mov     rcx, rdi; this
0x180020a03  mov     ebx, r15d
0x180020a06  call    ?ProhibitedByPolicy@CHNetConn@@IEAAEK@Z; CHNetConn::ProhibitedByPolicy(ulong)
0x180020a0b  test    al, al
0x180020a0d  jz      short loc_180020A40
0x180020a0f  mov     ebx, 80070005h
0x180020a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a1b  cmp     rcx, r13
0x180020a1e  jz      short loc_180020A40
0x180020a20  test    [rcx+1Ch], r12b
0x180020a24  jz      short loc_180020A40
0x180020a26  cmp     byte ptr [rcx+19h], 2
0x180020a2a  jb      short loc_180020A40
0x180020a2c  mov     rcx, [rcx+10h]
0x180020a30  mov     edx, 77h ; 'w'
0x180020a35  mov     r9d, ebx
0x180020a38  mov     r8, rsi
0x180020a3b  call    WPP_SF_d
0x180020a40  call    ?IsRoutingProtocolInstalled@@YAEK@Z; IsRoutingProtocolInstalled(ulong)
0x180020a45  test    al, al
0x180020a47  jz      short loc_180020A7C
0x180020a49  mov     ebx, 8007030Eh
0x180020a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a55  cmp     rcx, r13
0x180020a58  jz      loc_180020EBA
0x180020a5e  test    [rcx+1Ch], r12b
0x180020a62  jz      loc_180020E91
0x180020a68  cmp     byte ptr [rcx+19h], 2
0x180020a6c  jb      loc_180020E91
0x180020a72  mov     edx, 78h ; 'x'
0x180020a77  jmp     loc_1800209E4
0x180020a7c  test    ebx, ebx
0x180020a7e  jnz     loc_180020E8A
0x180020a84  lea     rdx, [rsp+2B0h+var_278]; struct IWbemClassObject **
0x180020a89  mov     rcx, rdi; this
0x180020a8c  call    ?GetConnectionPropertiesObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionPropertiesObject(IWbemClassObject * *)
0x180020a91  mov     ebx, eax
0x180020a93  test    eax, eax
0x180020a95  jns     short loc_180020AC8
0x180020a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a9e  cmp     rcx, r13
0x180020aa1  jz      loc_180020EBA
0x180020aa7  test    [rcx+1Ch], r12b
0x180020aab  jz      loc_180020E91
0x180020ab1  cmp     byte ptr [rcx+19h], 2
0x180020ab5  jb      loc_180020E91
0x180020abb  mov     edx, 79h ; 'y'
0x180020ac0  mov     r9d, eax
0x180020ac3  jmp     loc_1800209E7
0x180020ac8  jnz     loc_180020E8A
0x180020ace  mov     rdx, [rsp+2B0h+var_278]; struct IWbemClassObject *
0x180020ad3  lea     r8, [rsp+2B0h+var_260]; struct tagHNET_CONN_PROPERTIES *
0x180020ad8  mov     rcx, rdi; this
0x180020adb  call    ?InternalGetProperties@CHNetConn@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_CONN_PROPERTIES@@@Z; CHNetConn::InternalGetProperties(IWbemClassObject *,tagHNET_CONN_PROPERTIES *)
0x180020ae0  mov     ebx, eax
0x180020ae2  test    eax, eax
0x180020ae4  jns     short loc_180020B12
0x180020ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aed  cmp     rcx, r13
0x180020af0  jz      short loc_180020B12
0x180020af2  test    [rcx+1Ch], r12b
0x180020af6  jz      short loc_180020B12
0x180020af8  cmp     byte ptr [rcx+19h], 2
0x180020afc  jb      short loc_180020B12
0x180020afe  mov     rcx, [rcx+10h]
0x180020b02  mov     edx, 7Ah ; 'z'
0x180020b07  mov     r9d, eax
0x180020b0a  mov     r8, rsi
0x180020b0d  call    WPP_SF_d
0x180020b12  lea     rdx, [rsp+2B0h+var_260]; struct tagHNET_CONN_PROPERTIES *
0x180020b17  mov     rcx, rdi; struct IHNetConnection *
0x180020b1a  call    ?UpdatePropertiesWithNetcon2@@YAJPEAUIHNetConnection@@PEAUtagHNET_CONN_PROPERTIES@@@Z; UpdatePropertiesWithNetcon2(IHNetConnection *,tagHNET_CONN_PROPERTIES *)
0x180020b1f  test    ebx, ebx
0x180020b21  jnz     loc_180020BDE
0x180020b27  cmp     byte ptr [rsp+2B0h+var_258], r15b
0x180020b2c  jz      loc_180020BD9
0x180020b32  cmp     byte ptr [rsp+2B0h+var_260+2], 1
0x180020b37  jz      loc_180020BD9
0x180020b3d  mov     rcx, [rsp+2B0h+var_278]; struct IWbemClassObject *
0x180020b42  lea     rdx, ?c_wszIsIcsPublic@@3QBGB; "IsIcsPublic"
0x180020b49  mov     r8b, 1; unsigned __int8
0x180020b4c  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180020b51  mov     ebx, eax
0x180020b53  test    eax, eax
0x180020b55  jns     short loc_180020B76
0x180020b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b5e  cmp     rcx, r13
0x180020b61  jz      short loc_180020BDE
0x180020b63  test    [rcx+1Ch], r12b
0x180020b67  jz      short loc_180020BDE
0x180020b69  cmp     byte ptr [rcx+19h], 2
0x180020b6d  jb      short loc_180020BDE
0x180020b6f  mov     edx, 7Bh ; '{'
0x180020b74  jmp     short loc_180020BBC
0x180020b76  jnz     short loc_180020BDE
0x180020b78  mov     rcx, [rdi+40h]
0x180020b7c  xor     r9d, r9d
0x180020b7f  mov     rdx, [rsp+2B0h+var_278]
0x180020b84  mov     qword ptr [rsp+2B0h+var_290], r15
0x180020b89  mov     rax, [rcx]
0x180020b8c  lea     r8d, [r9+1]
0x180020b90  mov     rax, [rax+70h]
0x180020b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b99  mov     ebx, eax
0x180020b9b  test    eax, eax
0x180020b9d  jns     short loc_180020BCD
0x180020b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ba6  cmp     rcx, r13
0x180020ba9  jz      short loc_180020BDE
0x180020bab  test    [rcx+1Ch], r12b
0x180020baf  jz      short loc_180020BDE
0x180020bb1  cmp     byte ptr [rcx+19h], 2
0x180020bb5  jb      short loc_180020BDE
0x180020bb7  mov     edx, 7Ch ; '|'
0x180020bbc  mov     rcx, [rcx+10h]
0x180020bc0  mov     r9d, eax
0x180020bc3  mov     r8, rsi
0x180020bc6  call    WPP_SF_d
0x180020bcb  jmp     short loc_180020BDE
0x180020bcd  jnz     short loc_180020BDE
0x180020bcf  mov     rcx, rdi; this
0x180020bd2  call    ?UpdateNetman@CHNetConn@@IEAAJXZ; CHNetConn::UpdateNetman(void)
0x180020bd7  jmp     short loc_180020BDE
0x180020bd9  mov     ebx, 8000FFFFh
0x180020bde  mov     rcx, [rsp+2B0h+var_278]
0x180020be3  mov     rax, [rcx]
0x180020be6  mov     rax, [rax+10h]
0x180020bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bef  test    ebx, ebx
0x180020bf1  jnz     loc_180020E8A
0x180020bf7  lea     rcx, [rsp+2B0h+dwBufferLength]
0x180020bfc  mov     qword ptr [rsp+2B0h+dwBufferLength], r15
0x180020c01  call    ?CreateInstance@?$CComObject@VCHNIcsPublicConn@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNIcsPublicConn>::CreateInstance(ATL::CComObject<CHNIcsPublicConn> * *)
0x180020c06  mov     ebx, eax
0x180020c08  test    eax, eax
0x180020c0a  jns     short loc_180020C3A
0x180020c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c13  cmp     rcx, r13
0x180020c16  jz      loc_180020EBA
0x180020c1c  test    [rcx+1Ch], r12b
0x180020c20  jz      loc_180020E91
0x180020c26  cmp     byte ptr [rcx+19h], 2
0x180020c2a  jb      loc_180020E91
0x180020c30  mov     edx, 7Dh ; '}'
0x180020c35  jmp     loc_180020AC0
0x180020c3a  mov     rbx, qword ptr [rsp+2B0h+dwBufferLength]
0x180020c3f  mov     rcx, rbx
0x180020c42  mov     rax, [rbx]
0x180020c45  mov     rax, [rax+8]
0x180020c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c4e  mov     al, [rdi+60h]
0x180020c51  lea     rcx, [rbx+8]; this
0x180020c55  mov     r9, [rdi+50h]; unsigned __int16 *
0x180020c59  mov     r8, [rdi+48h]; unsigned __int16 *
0x180020c5d  mov     rdx, [rdi+40h]; struct IWbemServices *
0x180020c61  mov     byte ptr [rsp+2B0h+var_290], al; unsigned __int8
0x180020c65  call    ?InitializeFull@CHNetConn@@QEAAJPEAUIWbemServices@@PEAG1E@Z; CHNetConn::InitializeFull(IWbemServices *,ushort *,ushort *,uchar)
0x180020c6a  mov     esi, eax
0x180020c6c  test    eax, eax
0x180020c6e  jns     short loc_180020C8F
0x180020c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c77  cmp     rcx, r13
0x180020c7a  jz      short loc_180020CDD
0x180020c7c  test    [rcx+1Ch], r12b
0x180020c80  jz      short loc_180020CDD
0x180020c82  cmp     byte ptr [rcx+19h], 2
0x180020c86  jb      short loc_180020CDD
0x180020c88  mov     edx, 7Eh ; '~'
0x180020c8d  jmp     short loc_180020CCA
0x180020c8f  mov     rax, [rbx]
0x180020c92  lea     rdx, _GUID_85d18b73_3032_11d4_9348_00c04f8eeb71
0x180020c99  mov     r8, r14
0x180020c9c  mov     rcx, rbx
0x180020c9f  mov     rax, [rax]
0x180020ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ca7  mov     esi, eax
0x180020ca9  test    eax, eax
0x180020cab  jns     short loc_180020CDD
0x180020cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cb4  cmp     rcx, r13
0x180020cb7  jz      short loc_180020CDD
0x180020cb9  test    [rcx+1Ch], r12b
0x180020cbd  jz      short loc_180020CDD
0x180020cbf  cmp     byte ptr [rcx+19h], 2
0x180020cc3  jb      short loc_180020CDD
0x180020cc5  mov     edx, 7Fh
0x180020cca  mov     rcx, [rcx+10h]
0x180020cce  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180020cd5  mov     r9d, eax
0x180020cd8  call    WPP_SF_d
0x180020cdd  mov     rax, [rbx]
0x180020ce0  mov     rcx, rbx
0x180020ce3  mov     rax, [rax+10h]
0x180020ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cec  test    esi, esi
0x180020cee  jnz     loc_180020E88
0x180020cf4  mov     rax, [rdi+68h]
0x180020cf8  lea     rcx, [rsp+2B0h+dwBufferLength]; struct _GUID
0x180020cfd  mov     dl, 1; bool
0x180020cff  movups  xmm0, xmmword ptr [rax]
0x180020d02  movdqu  xmmword ptr [rsp+2B0h+dwBufferLength], xmm0
0x180020d08  call    ?UpdateSharingSettingsFromStorage@@YAKU_GUID@@_N@Z; UpdateSharingSettingsFromStorage(_GUID,bool)
0x180020d0d  mov     ebx, eax
0x180020d0f  test    eax, eax
0x180020d11  jz      short loc_180020D77
0x180020d13  mov     rcx, [r14]
0x180020d16  mov     rax, [rcx]
0x180020d19  mov     rax, [rax+18h]
0x180020d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d22  mov     rcx, [r14]
0x180020d25  mov     rax, [rcx]
0x180020d28  mov     rax, [rax+10h]
0x180020d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d31  mov     [r14], r15
0x180020d34  test    ebx, ebx
0x180020d36  jle     short loc_180020D43
0x180020d38  movzx   ebx, bx
0x180020d3b  or      ebx, 80070000h
0x180020d41  test    ebx, ebx
0x180020d43  jns     short loc_180020D79
0x180020d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d4c  cmp     rcx, r13
0x180020d4f  jz      short loc_180020D79
0x180020d51  test    [rcx+1Ch], r12b
0x180020d55  jz      short loc_180020D79
0x180020d57  cmp     byte ptr [rcx+19h], 2
0x180020d5b  jb      short loc_180020D79
0x180020d5d  mov     rcx, [rcx+10h]
0x180020d61  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180020d68  mov     edx, 80h
0x180020d6d  mov     r9d, ebx
0x180020d70  call    WPP_SF_d
0x180020d75  jmp     short loc_180020D79
0x180020d77  mov     ebx, esi
0x180020d79  xor     edx, edx; int
0x180020d7b  mov     rcx, rdi; this
0x180020d7e  call    ?RefreshNetConnectionsUI@CHNetConn@@IEAAJH@Z; CHNetConn::RefreshNetConnectionsUI(int)
0x180020d83  test    ebx, ebx
0x180020d85  jnz     loc_180020E8A
0x180020d8b  cmp     [rdi+60h], r15b
0x180020d8f  jz      short loc_180020DE2
0x180020d91  lea     esi, [rbx+52h]
0x180020d94  mov     [rsp+2B0h+Buffer], r15d
0x180020d99  lea     edi, [rbx+4]
0x180020d9c  mov     edx, esi; dwOption
0x180020d9e  lea     r9, [rsp+2B0h+dwBufferLength]; lpdwBufferLength
0x180020da3  mov     [rsp+2B0h+dwBufferLength], edi
0x180020da7  lea     r8, [rsp+2B0h+Buffer]; lpBuffer
  ... truncated ...
```
