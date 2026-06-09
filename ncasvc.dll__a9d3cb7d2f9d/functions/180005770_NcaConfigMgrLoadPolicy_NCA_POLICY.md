# NcaConfigMgrLoadPolicy(NCA_POLICY_ *)

- ea: `0x180005770`
- end: `0x180005bcc`
- name: `?NcaConfigMgrLoadPolicy@@YAJPEAUNCA_POLICY_@@@Z`
- size: `1116`
- prototype: `__int64 __fastcall(struct NCA_POLICY_ *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006190`
- `0x1800067e0`

## callees

- `0x180002d50`
- `0x1800037b0`
- `0x180004f34`
- `0x180005260`
- `0x1800052c8`
- `0x180005770`
- `0x180005bd4`
- `0x180005df8`
- `0x1800197ac`
- `0x18001ac78`
- `0x18001cc3e`

## string_xrefs

- `0x1800059c3`: `CustomCommands`
- `0x180005824`: `SOFTWARE\Policies\Microsoft\DirectAccessConnectivityAssistant`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrLoadPolicy(struct NCA_POLICY_ *a1)
{
  _DWORD *v2; // r14
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  HKEY v8; // rsi
  int v9; // eax
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int DteList; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  DWORD v21; // [rsp+28h] [rbp-40h]
  DWORD v22; // [rsp+28h] [rbp-40h]
  __int64 v23; // [rsp+70h] [rbp+8h] BYREF
  HKEY v24; // [rsp+78h] [rbp+10h]

  v24 = 0;
  LODWORD(v23) = 1;
  memset_0(a1, 0, 0x68u);
  v2 = (_DWORD *)((char *)a1 + 84);
  v3 = NcaRegOpenKey(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\NetworkConnectivityAssistant",
         9u,
         (__int64)a1 + 84);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_7;
    v6 = 48;
    goto LABEL_5;
  }
  if ( !*v2 )
  {
    v3 = NcaRegOpenKey(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Policies\\Microsoft\\DirectAccessConnectivityAssistant",
           9u,
           (__int64)&v23);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_7;
      v6 = 49;
LABEL_5:
      v7 = (unsigned int)v3;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v7);
LABEL_7:
      v8 = v24;
      goto LABEL_67;
    }
    if ( !(_DWORD)v23 && !*v2 )
    {
      v4 = 0;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_7;
      v6 = 50;
      v7 = 0;
      goto LABEL_6;
    }
  }
  v8 = v24;
  v9 = NcaArrayCreateFromRegistry(
         (int)v24,
         (int)L"Probes",
         24,
         (int)NcaProbeConstruct,
         (__int64)NcaProbeEmpty,
         v21,
         (__int64)a1);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
          (unsigned int)v9);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      {
        v11 = 51;
LABEL_25:
        v12 = v4;
LABEL_26:
        WPP_SF_d(v10[2], v11, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v12);
        goto LABEL_67;
      }
    }
    goto LABEL_67;
  }
  DteList = NcaConfigMgrLoadDteList(v8, (struct NCA_POLICY_ *)((char *)a1 + 16));
  v4 = DteList;
  if ( DteList < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_67;
    v11 = 52;
    goto LABEL_31;
  }
  DteList = NcaConfigMgrSortDteList(a1);
  v4 = DteList;
  if ( DteList < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_67;
    v11 = 53;
    goto LABEL_31;
  }
  v14 = NcaArrayCreateFromRegistry(
          (int)v8,
          (int)L"CustomCommands",
          8,
          (int)NcaCustomCommandConstruct,
          (__int64)NcaCustomCommandEmpty,
          v22,
          (__int64)a1 + 32);
  v4 = v14;
  if ( v14 >= 0 )
  {
    DteList = NcaConfigMgrLoadString(v8, L"SupportEmail", v15, (unsigned __int16 **)a1 + 6);
    v4 = DteList;
    if ( DteList >= 0 )
    {
      DteList = NcaConfigMgrLoadBool(v8, L"PassiveMode", v16, (int *)a1 + 14);
      v4 = DteList;
      if ( DteList >= 0 )
      {
        DteList = NcaConfigMgrLoadBool(v8, L"NamePreferenceAllowed", v17, (int *)a1 + 15);
        v4 = DteList;
        if ( DteList >= 0 )
        {
          if ( !*v2 )
          {
            *((_DWORD *)a1 + 20) = 1;
            NcaLoadMuiString(0xBC2u);
            goto LABEL_67;
          }
          DteList = NcaConfigMgrLoadString(v8, L"FriendlyName", v18, (unsigned __int16 **)a1 + 9);
          v4 = DteList;
          if ( DteList >= 0 )
          {
            if ( !*((_QWORD *)a1 + 9) )
            {
              *((_DWORD *)a1 + 22) = 1;
              NcaLoadMuiString(0xBC2u);
            }
            DteList = NcaConfigMgrLoadBool(v8, L"ShowUI", v19, (int *)a1 + 20);
            v4 = DteList;
            if ( DteList >= 0 )
              goto LABEL_67;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_67;
            v11 = 59;
          }
          else
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_67;
            v11 = 58;
          }
        }
        else
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_67;
          v11 = 57;
        }
      }
      else
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v11 = 56;
      }
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      v11 = 55;
    }
LABEL_31:
    v12 = (unsigned int)DteList;
    goto LABEL_26;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
        (unsigned int)v14);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v11 = 54;
      goto LABEL_25;
    }
  }
LABEL_67:
  NcaRegCloseKey(v8);
  return v4;
}

```

## disassembly

```asm
0x180005770  mov     [rsp+arg_10], rbx
0x180005775  push    rbp
0x180005776  push    rsi
0x180005777  push    rdi
0x180005778  push    r14
0x18000577a  push    r15
0x18000577c  sub     rsp, 40h
0x180005780  mov     r15d, 1
0x180005786  mov     [rsp+68h+arg_8], 0
0x18000578f  xor     edx, edx; Val
0x180005791  mov     dword ptr [rsp+68h+arg_0], r15d
0x180005796  mov     rdi, rcx
0x180005799  lea     r8d, [r15+67h]; Size
0x18000579d  call    memset_0
0x1800057a2  lea     esi, [r15+8]
0x1800057a6  mov     rbp, 0FFFFFFFF80000002h
0x1800057ad  lea     r14, [rdi+54h]
0x1800057b1  mov     r8d, esi; samDesired
0x1800057b4  mov     rcx, rbp; hKey
0x1800057b7  mov     [rsp+68h+var_48], r14; __int64
0x1800057bc  lea     r9, [rsp+68h+arg_8]
0x1800057c1  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800057c8  call    NcaRegOpenKey
0x1800057cd  mov     ebx, eax
0x1800057cf  test    eax, eax
0x1800057d1  jns     short loc_18000580C
0x1800057d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057da  lea     rdi, WPP_GLOBAL_Control
0x1800057e1  cmp     rcx, rdi
0x1800057e4  jz      short loc_180005802
0x1800057e6  test    [rcx+1Ch], r15b
0x1800057ea  jz      short loc_180005802
0x1800057ec  lea     edx, [rsi+27h]
0x1800057ef  mov     r9d, eax
0x1800057f2  mov     rcx, [rcx+10h]
0x1800057f6  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800057fd  call    WPP_SF_d
0x180005802  mov     rsi, [rsp+68h+arg_8]
0x180005807  jmp     loc_180005BAD
0x18000580c  cmp     dword ptr [r14], 0
0x180005810  jnz     short loc_18000588C
0x180005812  lea     rax, [rsp+68h+arg_0]
0x180005817  mov     r8d, esi; samDesired
0x18000581a  lea     r9, [rsp+68h+arg_8]
0x18000581f  mov     [rsp+68h+var_48], rax; __int64
0x180005824  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\DirectAc"...
0x18000582b  mov     rcx, rbp; hKey
0x18000582e  call    NcaRegOpenKey
0x180005833  mov     ebx, eax
0x180005835  test    eax, eax
0x180005837  jns     short loc_180005859
0x180005839  mov     rcx, cs:WPP_GLOBAL_Control
0x180005840  lea     rdi, WPP_GLOBAL_Control
0x180005847  cmp     rcx, rdi
0x18000584a  jz      short loc_180005802
0x18000584c  test    [rcx+1Ch], r15b
0x180005850  jz      short loc_180005802
0x180005852  mov     edx, 31h ; '1'
0x180005857  jmp     short loc_1800057EF
0x180005859  cmp     dword ptr [rsp+68h+arg_0], 0
0x18000585e  jnz     short loc_18000588C
0x180005860  cmp     dword ptr [r14], 0
0x180005864  jnz     short loc_18000588C
0x180005866  xor     ebx, ebx
0x180005868  mov     rcx, cs:WPP_GLOBAL_Control
0x18000586f  lea     rdi, WPP_GLOBAL_Control
0x180005876  cmp     rcx, rdi
0x180005879  jz      short loc_180005802
0x18000587b  test    [rcx+1Ch], r15b
0x18000587f  jz      short loc_180005802
0x180005881  lea     edx, [rbx+32h]
0x180005884  xor     r9d, r9d
0x180005887  jmp     loc_1800057F2
0x18000588c  mov     rsi, [rsp+68h+arg_8]
0x180005891  lea     rax, NcaProbeEmpty
0x180005898  mov     rcx, rsi; int
0x18000589b  mov     [rsp+68h+var_38], rdi; __int64
0x1800058a0  lea     r9, ?NcaProbeConstruct@@YAJPEAXPEAUHKEY__@@PEBG20PEAH@Z; int
0x1800058a7  mov     [rsp+68h+var_48], rax; __int64
0x1800058ac  mov     r8d, 18h; int
0x1800058b2  lea     rdx, aProbes; "Probes"
0x1800058b9  call    NcaArrayCreateFromRegistry
0x1800058be  mov     ebx, eax
0x1800058c0  test    eax, eax
0x1800058c2  jns     short loc_180005930
0x1800058c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058cb  lea     rdi, WPP_GLOBAL_Control
0x1800058d2  cmp     rcx, rdi
0x1800058d5  jz      loc_180005BAD
0x1800058db  test    [rcx+1Ch], r15b
0x1800058df  jz      short loc_180005900
0x1800058e1  mov     rcx, [rcx+10h]
0x1800058e5  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800058ec  mov     edx, 20h ; ' '
0x1800058f1  mov     r9d, eax
0x1800058f4  call    WPP_SF_d
0x1800058f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005900  cmp     rcx, rdi
0x180005903  jz      loc_180005BAD
0x180005909  test    [rcx+1Ch], r15b
0x18000590d  jz      loc_180005BAD
0x180005913  mov     edx, 33h ; '3'
0x180005918  mov     r9d, ebx
0x18000591b  mov     rcx, [rcx+10h]
0x18000591f  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005926  call    WPP_SF_d
0x18000592b  jmp     loc_180005BAD
0x180005930  lea     rdx, [rdi+10h]; struct NCA_PROBE_LIST_ *
0x180005934  mov     rcx, rsi; HKEY
0x180005937  call    ?NcaConfigMgrLoadDteList@@YAJPEAUHKEY__@@PEAUNCA_PROBE_LIST_@@@Z; NcaConfigMgrLoadDteList(HKEY__ *,NCA_PROBE_LIST_ *)
0x18000593c  mov     ebx, eax
0x18000593e  test    eax, eax
0x180005940  jns     short loc_18000596D
0x180005942  mov     rcx, cs:WPP_GLOBAL_Control
0x180005949  lea     rdi, WPP_GLOBAL_Control
0x180005950  cmp     rcx, rdi
0x180005953  jz      loc_180005BAD
0x180005959  test    [rcx+1Ch], r15b
0x18000595d  jz      loc_180005BAD
0x180005963  mov     edx, 34h ; '4'
0x180005968  mov     r9d, eax
0x18000596b  jmp     short loc_18000591B
0x18000596d  mov     rcx, rdi; struct NCA_POLICY_ *
0x180005970  call    ?NcaConfigMgrSortDteList@@YAJPEAUNCA_POLICY_@@@Z; NcaConfigMgrSortDteList(NCA_POLICY_ *)
0x180005975  mov     ebx, eax
0x180005977  test    eax, eax
0x180005979  jns     short loc_1800059A3
0x18000597b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005982  lea     rdi, WPP_GLOBAL_Control
0x180005989  cmp     rcx, rdi
0x18000598c  jz      loc_180005BAD
0x180005992  test    [rcx+1Ch], r15b
0x180005996  jz      loc_180005BAD
0x18000599c  mov     edx, 35h ; '5'
0x1800059a1  jmp     short loc_180005968
0x1800059a3  lea     rax, [rdi+20h]
0x1800059a7  mov     r8d, 8; int
0x1800059ad  mov     [rsp+68h+var_38], rax; __int64
0x1800059b2  lea     r9, ?NcaCustomCommandConstruct@@YAJPEAXPEAUHKEY__@@PEBG20PEAH@Z; int
0x1800059b9  lea     rax, NcaCustomCommandEmpty
0x1800059c0  mov     rcx, rsi; int
0x1800059c3  lea     rdx, aCustomcommands; "CustomCommands"
0x1800059ca  mov     [rsp+68h+var_48], rax; __int64
0x1800059cf  call    NcaArrayCreateFromRegistry
0x1800059d4  mov     ebx, eax
0x1800059d6  test    eax, eax
0x1800059d8  jns     short loc_180005A33
0x1800059da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059e1  lea     rdi, WPP_GLOBAL_Control
0x1800059e8  cmp     rcx, rdi
0x1800059eb  jz      loc_180005BAD
0x1800059f1  test    [rcx+1Ch], r15b
0x1800059f5  jz      short loc_180005A16
0x1800059f7  mov     rcx, [rcx+10h]
0x1800059fb  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005a02  mov     edx, 2Fh ; '/'
0x180005a07  mov     r9d, eax
0x180005a0a  call    WPP_SF_d
0x180005a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a16  cmp     rcx, rdi
0x180005a19  jz      loc_180005BAD
0x180005a1f  test    [rcx+1Ch], r15b
0x180005a23  jz      loc_180005BAD
0x180005a29  mov     edx, 36h ; '6'
0x180005a2e  jmp     loc_180005918
0x180005a33  lea     r9, [rdi+30h]; unsigned __int16 **
0x180005a37  mov     rcx, rsi; HKEY
0x180005a3a  lea     rdx, aSupportemail; "SupportEmail"
0x180005a41  call    ?NcaConfigMgrLoadString@@YAJPEAUHKEY__@@PEBGHPEAPEAG@Z; NcaConfigMgrLoadString(HKEY__ *,ushort const *,int,ushort * *)
0x180005a46  mov     ebx, eax
0x180005a48  test    eax, eax
0x180005a4a  jns     short loc_180005A77
0x180005a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a53  lea     rdi, WPP_GLOBAL_Control
0x180005a5a  cmp     rcx, rdi
0x180005a5d  jz      loc_180005BAD
0x180005a63  test    [rcx+1Ch], r15b
0x180005a67  jz      loc_180005BAD
0x180005a6d  mov     edx, 37h ; '7'
0x180005a72  jmp     loc_180005968
0x180005a77  lea     r9, [rdi+38h]; int *
0x180005a7b  mov     rcx, rsi; HKEY
0x180005a7e  lea     rdx, aPassivemode; "PassiveMode"
0x180005a85  call    ?NcaConfigMgrLoadBool@@YAJPEAUHKEY__@@PEBGHPEAH@Z; NcaConfigMgrLoadBool(HKEY__ *,ushort const *,int,int *)
0x180005a8a  mov     ebx, eax
0x180005a8c  test    eax, eax
0x180005a8e  jns     short loc_180005ABB
0x180005a90  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a97  lea     rdi, WPP_GLOBAL_Control
0x180005a9e  cmp     rcx, rdi
0x180005aa1  jz      loc_180005BAD
0x180005aa7  test    [rcx+1Ch], r15b
0x180005aab  jz      loc_180005BAD
0x180005ab1  mov     edx, 38h ; '8'
0x180005ab6  jmp     loc_180005968
0x180005abb  lea     r9, [rdi+3Ch]; int *
0x180005abf  mov     rcx, rsi; HKEY
0x180005ac2  lea     rdx, aNamepreference; "NamePreferenceAllowed"
0x180005ac9  call    ?NcaConfigMgrLoadBool@@YAJPEAUHKEY__@@PEBGHPEAH@Z; NcaConfigMgrLoadBool(HKEY__ *,ushort const *,int,int *)
0x180005ace  mov     ebx, eax
0x180005ad0  test    eax, eax
0x180005ad2  jns     short loc_180005AFF
0x180005ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005adb  lea     rdi, WPP_GLOBAL_Control
0x180005ae2  cmp     rcx, rdi
0x180005ae5  jz      loc_180005BAD
0x180005aeb  test    [rcx+1Ch], r15b
0x180005aef  jz      loc_180005BAD
0x180005af5  mov     edx, 39h ; '9'
0x180005afa  jmp     loc_180005968
0x180005aff  cmp     dword ptr [r14], 0
0x180005b03  lea     rbp, [rdi+48h]
0x180005b07  jz      loc_180005B9C
0x180005b0d  mov     r9, rbp; unsigned __int16 **
0x180005b10  lea     rdx, aFriendlyname; "FriendlyName"
0x180005b17  mov     rcx, rsi; HKEY
0x180005b1a  call    ?NcaConfigMgrLoadString@@YAJPEAUHKEY__@@PEBGHPEAPEAG@Z; NcaConfigMgrLoadString(HKEY__ *,ushort const *,int,ushort * *)
0x180005b1f  mov     ebx, eax
0x180005b21  test    eax, eax
0x180005b23  jns     short loc_180005B48
0x180005b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b2c  lea     rdi, WPP_GLOBAL_Control
0x180005b33  cmp     rcx, rdi
0x180005b36  jz      short loc_180005BAD
0x180005b38  test    [rcx+1Ch], r15b
0x180005b3c  jz      short loc_180005BAD
0x180005b3e  mov     edx, 3Ah ; ':'
0x180005b43  jmp     loc_180005968
0x180005b48  cmp     qword ptr [rbp+0], 0
0x180005b4d  jnz     short loc_180005B60
0x180005b4f  mov     rdx, rbp
0x180005b52  mov     [rdi+58h], r15d
0x180005b56  mov     ecx, 0BC2h; uID
0x180005b5b  call    NcaLoadMuiString
0x180005b60  lea     r9, [rdi+50h]; int *
0x180005b64  mov     rcx, rsi; HKEY
0x180005b67  lea     rdx, aShowui; "ShowUI"
0x180005b6e  call    ?NcaConfigMgrLoadBool@@YAJPEAUHKEY__@@PEBGHPEAH@Z; NcaConfigMgrLoadBool(HKEY__ *,ushort const *,int,int *)
0x180005b73  mov     ebx, eax
0x180005b75  test    eax, eax
0x180005b77  jns     short loc_180005BAD
0x180005b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b80  lea     rdi, WPP_GLOBAL_Control
0x180005b87  cmp     rcx, rdi
0x180005b8a  jz      short loc_180005BAD
0x180005b8c  test    [rcx+1Ch], r15b
0x180005b90  jz      short loc_180005BAD
0x180005b92  mov     edx, 3Bh ; ';'
0x180005b97  jmp     loc_180005968
0x180005b9c  mov     rdx, rbp
0x180005b9f  mov     [rdi+50h], r15d
0x180005ba3  mov     ecx, 0BC2h; uID
0x180005ba8  call    NcaLoadMuiString
0x180005bad  mov     rcx, rsi
0x180005bb0  call    NcaRegCloseKey
0x180005bb5  mov     eax, ebx
0x180005bb7  mov     rbx, [rsp+68h+arg_10]
0x180005bbf  add     rsp, 40h
0x180005bc3  pop     r15
0x180005bc5  pop     r14
0x180005bc7  pop     rdi
0x180005bc8  pop     rsi
0x180005bc9  pop     rbp
0x180005bca  retn
```
