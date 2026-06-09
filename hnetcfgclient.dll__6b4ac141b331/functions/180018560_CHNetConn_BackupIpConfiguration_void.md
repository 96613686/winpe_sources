# CHNetConn::BackupIpConfiguration(void)

- ea: `0x180018560`
- end: `0x180018a84`
- name: `?BackupIpConfiguration@CHNetConn@@IEAAJXZ`
- size: `1316`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x1800203b0`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x1800181b8`
- `0x180018560`
- `0x18001be10`
- `0x18001c9c4`
- `0x18001d5fc`
- `0x18001d948`
- `0x18002a7d4`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800188c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188f4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188f4`
- `OLEAUT32!__imp_VariantInit` at `0x1800185d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800185de`
- `OLEAUT32!__imp_VariantInit` at `0x1800185ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800185f6`
- `OLEAUT32!__imp_VariantInit` at `0x180018727`
- `OLEAUT32!__imp_VariantInit` at `0x180018795`
- `OLEAUT32!__imp_VariantInit` at `0x1800185d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800185de`
- `OLEAUT32!__imp_VariantInit` at `0x1800185ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800185f6`
- `OLEAUT32!__imp_VariantInit` at `0x180018727`
- `OLEAUT32!__imp_VariantInit` at `0x180018795`
- `OLEAUT32!__imp_VariantClear` at `0x1800187a0`
- `OLEAUT32!__imp_VariantClear` at `0x180018a3a`
- `OLEAUT32!__imp_VariantClear` at `0x180018a46`
- `OLEAUT32!__imp_VariantClear` at `0x180018a51`
- `OLEAUT32!__imp_VariantClear` at `0x180018a5c`
- `OLEAUT32!__imp_VariantClear` at `0x1800187a0`
- `OLEAUT32!__imp_VariantClear` at `0x180018a3a`
- `OLEAUT32!__imp_VariantClear` at `0x180018a46`
- `OLEAUT32!__imp_VariantClear` at `0x180018a51`
- `OLEAUT32!__imp_VariantClear` at `0x180018a5c`

## string_xrefs

- `0x1800186df`: `HNet_BackupIpConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHNetConn::BackupIpConfiguration(CHNetConn *this)
{
  int GuidInternal; // eax
  int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  struct _IP_ADAPTER_ADDRESSES_LH **v10; // rdx
  LONG v11; // ebx
  unsigned int v12; // edi
  int IpAdapterAddress; // eax
  int StaticIpSettings; // eax
  struct IWbemClassObject *v16; // [rsp+30h] [rbp-A9h] BYREF
  struct _GUID *v17; // [rsp+38h] [rbp-A1h] BYREF
  VARIANTARG v18; // [rsp+40h] [rbp-99h] BYREF
  VARIANTARG v19; // [rsp+58h] [rbp-81h] BYREF
  VARIANTARG v20; // [rsp+70h] [rbp-69h] BYREF
  VARIANTARG v21; // [rsp+88h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-39h] BYREF
  _OWORD v23[2]; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-1h]
  __int16 v25; // [rsp+E0h] [rbp+7h]
  char v26; // [rsp+E2h] [rbp+9h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v16 = 0;
  VariantInit(&pvarg);
  VariantInit(&v20);
  VariantInit(&v19);
  VariantInit(&v18);
  memset(v23, 0, sizeof(v23));
  v25 = 1;
  v24 = 0;
  v26 = 0;
  v17 = 0;
  GuidInternal = CHNetConn::GetGuidInternal(this, &v17);
  v3 = GuidInternal;
  if ( GuidInternal < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_69;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v5 = 274;
    goto LABEL_16;
  }
  if ( v17 )
  {
    GuidInternal = CAdapterIpSettings::Initialize((CAdapterIpSettings *)v23, v17);
    v3 = GuidInternal;
    if ( GuidInternal < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_17;
      v5 = 275;
LABEL_16:
      WPP_SF_d(v4[2], v5, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)GuidInternal);
      v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 276;
LABEL_68:
        WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v3);
        goto LABEL_69;
      }
      goto LABEL_69;
    }
  }
  v20.vt = 8;
  v19.vt = 8;
  v18.vt = 8;
  v7 = SpawnNewInstance(*((struct IWbemServices **)this + 8), L"HNet_BackupIpConfiguration", &v16);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 277;
LABEL_60:
      WPP_SF_d(v4[2], v8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v7);
LABEL_61:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  VariantInit(&v21);
  v21.vt = 8;
  v21.llVal = *((_QWORD *)this + 9);
  v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
         v16,
         L"Connection",
         0,
         &v21,
         0);
  v3 = v9;
  if ( v9 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      278,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)v9);
  }
  VariantInit(&v21);
  VariantClear(&v21);
  if ( v3 < 0 )
    goto LABEL_61;
  if ( HIBYTE(v25) )
  {
    IpAdapterAddress = CAdapterIpSettings::GetIpAdapterAddress((CAdapterIpSettings *)v23, v10);
    v12 = IpAdapterAddress;
    if ( IpAdapterAddress >= 0 && *((_QWORD *)&v23[0] + 1) )
    {
      v11 = (*(_DWORD *)(*((_QWORD *)&v23[0] + 1) + 92LL) >> 2) & 1;
    }
    else
    {
      v11 = 1;
      if ( IpAdapterAddress < 0 )
        goto LABEL_45;
    }
    pvarg.vt = 3;
    pvarg.lVal = v11;
    ((void (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
      v16,
      L"EnableDHCP",
      0,
      &pvarg,
      0);
    goto LABEL_38;
  }
  v11 = 1;
  v12 = -2147024891;
LABEL_45:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v12);
  }
LABEL_38:
  if ( !v11 )
  {
    StaticIpSettings = CAdapterIpSettings::GetStaticIpSettings(
                         (CAdapterIpSettings *)v23,
                         &v20.bstrVal,
                         &v19.bstrVal,
                         &v18.bstrVal);
    if ( StaticIpSettings >= 0 )
      goto LABEL_52;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        280,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)StaticIpSettings);
    }
  }
  v3 = -2147024882;
  v20.llVal = (LONGLONG)SysAllocString(L"0.0.0.0");
  if ( !v20.llVal )
    goto LABEL_61;
  v19.llVal = (LONGLONG)SysAllocString(L"0.0.0.0");
  if ( !v19.llVal )
    goto LABEL_61;
  v18.llVal = (LONGLONG)SysAllocString(L"0.0.0.0");
  if ( !v18.llVal )
    goto LABEL_61;
LABEL_52:
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
         v16,
         L"IPAddress",
         0,
         &v20,
         0);
  if ( v3 < 0 )
    goto LABEL_61;
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
         v16,
         L"SubnetMask",
         0,
         &v19,
         0);
  if ( v3 < 0 )
    goto LABEL_61;
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v16->lpVtbl->Put)(
         v16,
         L"DefaultGateway",
         0,
         &v18,
         0);
  if ( v3 < 0 )
    goto LABEL_61;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8)
                                                                                            + 112LL))(
         *((_QWORD *)this + 8),
         v16,
         0,
         0,
         0);
  v3 = v7;
  if ( v7 >= 0 )
    goto LABEL_61;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 281;
    goto LABEL_60;
  }
LABEL_62:
  if ( v16 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 282;
    goto LABEL_68;
  }
LABEL_69:
  CAdapterIpSettings::~CAdapterIpSettings((CAdapterIpSettings *)v23);
  VariantClear(&v18);
  VariantClear(&v19);
  VariantClear(&v20);
  VariantClear(&pvarg);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018560  push    rbp
0x180018562  push    rbx
0x180018563  push    rsi
0x180018564  push    rdi
0x180018565  push    r12
0x180018567  push    r13
0x180018569  push    r14
0x18001856b  push    r15
0x18001856d  lea     rbp, [rsp-1Fh]
0x180018572  sub     rsp, 0F8h
0x180018579  mov     rax, cs:__security_cookie
0x180018580  xor     rax, rsp
0x180018583  mov     [rbp+57h+var_48], rax
0x180018587  mov     rsi, rcx
0x18001858a  lea     r12, WPP_GLOBAL_Control
0x180018591  lea     r13, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180018598  mov     r15d, 8
0x18001859e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185a5  cmp     rcx, r12
0x1800185a8  jz      short loc_1800185C7
0x1800185aa  test    [rcx+1Ch], r15b
0x1800185ae  jz      short loc_1800185C7
0x1800185b0  cmp     byte ptr [rcx+19h], 6
0x1800185b4  jb      short loc_1800185C7
0x1800185b6  mov     edx, 111h
0x1800185bb  mov     r8, r13
0x1800185be  mov     rcx, [rcx+10h]
0x1800185c2  call    WPP_SF_
0x1800185c7  xor     r14d, r14d
0x1800185ca  mov     [rsp+130h+var_100], r14
0x1800185cf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800185d3  call    cs:__imp_VariantInit
0x1800185d9  nop
0x1800185da  lea     rcx, [rbp+57h+var_C0]; pvarg
0x1800185de  call    cs:__imp_VariantInit
0x1800185e4  nop
0x1800185e5  lea     rcx, [rsp+130h+var_D8]; pvarg
0x1800185ea  call    cs:__imp_VariantInit
0x1800185f0  nop
0x1800185f1  lea     rcx, [rsp+130h+var_F0]; pvarg
0x1800185f6  call    cs:__imp_VariantInit
0x1800185fc  nop
0x1800185fd  xorps   xmm0, xmm0
0x180018600  movdqu  [rbp+57h+var_78], xmm0
0x180018605  mov     [rbp+57h+var_50], 1
0x18001860b  mov     [rbp+57h+var_58], r14
0x18001860f  mov     [rbp+57h+var_4E], r14b
0x180018613  movups  [rbp+57h+var_68], xmm0
0x180018617  mov     [rsp+130h+var_F8], r14
0x18001861c  lea     rdx, [rsp+130h+var_F8]; struct _GUID **
0x180018621  mov     rcx, rsi; this
0x180018624  call    ?GetGuidInternal@CHNetConn@@IEAAJPEAPEAU_GUID@@@Z; CHNetConn::GetGuidInternal(_GUID * *)
0x180018629  mov     ebx, eax
0x18001862b  test    eax, eax
0x18001862d  jns     short loc_180018652
0x18001862f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018636  cmp     rcx, r12
0x180018639  jz      loc_180018A2B
0x18001863f  test    [rcx+1Ch], r15b
0x180018643  jz      short loc_1800186A2
0x180018645  cmp     byte ptr [rcx+19h], 2
0x180018649  jb      short loc_1800186A2
0x18001864b  mov     edx, 112h
0x180018650  jmp     short loc_18001868C
0x180018652  mov     rdx, [rsp+130h+var_F8]; struct _GUID *
0x180018657  test    rdx, rdx
0x18001865a  jz      short loc_1800186C9
0x18001865c  lea     rcx, [rbp+57h+var_78]; this
0x180018660  call    ?Initialize@CAdapterIpSettings@@QEAAJPEAU_GUID@@@Z; CAdapterIpSettings::Initialize(_GUID *)
0x180018665  mov     ebx, eax
0x180018667  test    eax, eax
0x180018669  jns     short loc_1800186C9
0x18001866b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018672  cmp     rcx, r12
0x180018675  jz      loc_180018A2B
0x18001867b  test    [rcx+1Ch], r15b
0x18001867f  jz      short loc_1800186A2
0x180018681  cmp     byte ptr [rcx+19h], 2
0x180018685  jb      short loc_1800186A2
0x180018687  mov     edx, 113h
0x18001868c  mov     r9d, eax
0x18001868f  mov     r8, r13
0x180018692  mov     rcx, [rcx+10h]
0x180018696  call    WPP_SF_d
0x18001869b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186a2  cmp     rcx, r12
0x1800186a5  jz      loc_180018A2B
0x1800186ab  test    [rcx+1Ch], r15b
0x1800186af  jz      loc_180018A2B
0x1800186b5  cmp     byte ptr [rcx+19h], 6
0x1800186b9  jb      loc_180018A2B
0x1800186bf  mov     edx, 114h
0x1800186c4  jmp     loc_180018A1B
0x1800186c9  mov     word ptr [rbp+57h+var_C0], r15w
0x1800186ce  mov     word ptr [rsp+130h+var_D8], r15w
0x1800186d4  mov     word ptr [rsp+130h+var_F0], r15w
0x1800186da  lea     r8, [rsp+130h+var_100]; struct IWbemClassObject **
0x1800186df  lea     rdx, ?c_wszBackupIpConfiguration@@3QBGB; "HNet_BackupIpConfiguration"
0x1800186e6  mov     rcx, [rsi+40h]; struct IWbemServices *
0x1800186ea  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x1800186ef  mov     ebx, eax
0x1800186f1  test    eax, eax
0x1800186f3  jns     short loc_180018723
0x1800186f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186fc  cmp     rcx, r12
0x1800186ff  jz      loc_1800189E5
0x180018705  test    [rcx+1Ch], r15b
0x180018709  jz      loc_1800189E5
0x18001870f  cmp     byte ptr [rcx+19h], 2
0x180018713  jb      loc_1800189E5
0x180018719  mov     edx, 115h
0x18001871e  jmp     loc_1800189CF
0x180018723  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180018727  call    cs:__imp_VariantInit
0x18001872d  nop
0x18001872e  mov     word ptr [rbp+57h+var_A8], r15w
0x180018733  mov     rax, [rsi+48h]
0x180018737  mov     qword ptr [rbp+57h+var_A8+8], rax
0x18001873b  mov     rcx, [rsp+130h+var_100]
0x180018740  mov     rax, [rcx]
0x180018743  mov     dword ptr [rsp+130h+var_110], r14d
0x180018748  lea     r9, [rbp+57h+var_A8]
0x18001874c  xor     r8d, r8d
0x18001874f  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x180018756  mov     rax, [rax+28h]
0x18001875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001875f  mov     ebx, eax
0x180018761  test    eax, eax
0x180018763  jns     short loc_180018791
0x180018765  mov     rcx, cs:WPP_GLOBAL_Control
0x18001876c  cmp     rcx, r12
0x18001876f  jz      short loc_180018791
0x180018771  test    [rcx+1Ch], r15b
0x180018775  jz      short loc_180018791
0x180018777  cmp     byte ptr [rcx+19h], 2
0x18001877b  jb      short loc_180018791
0x18001877d  mov     edx, 116h
0x180018782  mov     r9d, eax
0x180018785  mov     r8, r13
0x180018788  mov     rcx, [rcx+10h]
0x18001878c  call    WPP_SF_d
0x180018791  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180018795  call    cs:__imp_VariantInit
0x18001879b  nop
0x18001879c  lea     rcx, [rbp+57h+var_A8]; pvarg
0x1800187a0  call    cs:__imp_VariantClear
0x1800187a6  test    ebx, ebx
0x1800187a8  js      loc_1800189DE
0x1800187ae  cmp     byte ptr [rbp+57h+var_50+1], r14b
0x1800187b2  jnz     short loc_1800187C3
0x1800187b4  mov     ebx, 1
0x1800187b9  mov     edi, 80070005h
0x1800187be  jmp     loc_18001887F
0x1800187c3  lea     rcx, [rbp+57h+var_78]; this
0x1800187c7  call    ?GetIpAdapterAddress@CAdapterIpSettings@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; CAdapterIpSettings::GetIpAdapterAddress(_IP_ADAPTER_ADDRESSES_LH * *)
0x1800187cc  mov     edi, eax
0x1800187ce  test    eax, eax
0x1800187d0  js      loc_180018872
0x1800187d6  mov     rbx, qword ptr [rbp+57h+var_78+8]
0x1800187da  test    rbx, rbx
0x1800187dd  jz      loc_180018872
0x1800187e3  mov     ebx, [rbx+5Ch]
0x1800187e6  shr     ebx, 2
0x1800187e9  and     ebx, 1
0x1800187ec  mov     eax, 3
0x1800187f1  mov     word ptr [rbp+57h+pvarg], ax
0x1800187f5  mov     dword ptr [rbp+57h+pvarg+8], ebx
0x1800187f8  mov     rcx, [rsp+130h+var_100]
0x1800187fd  mov     rax, [rcx]
0x180018800  mov     dword ptr [rsp+130h+var_110], r14d
0x180018805  lea     r9, [rbp+57h+pvarg]
0x180018809  xor     r8d, r8d
0x18001880c  lea     rdx, ?c_wszEnableDHCP@@3QBGB; "EnableDHCP"
0x180018813  mov     rax, [rax+28h]
0x180018817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001881c  mov     edi, eax
0x18001881e  test    ebx, ebx
0x180018820  jnz     loc_1800188B0
0x180018826  lea     r9, [rsp+130h+var_F0+8]; unsigned __int16 **
0x18001882b  lea     r8, [rbp+57h+var_D8+8]; unsigned __int16 **
0x18001882f  lea     rdx, [rbp+57h+var_C0+8]; unsigned __int16 **
0x180018833  lea     rcx, [rbp+57h+var_78]; this
0x180018837  call    ?GetStaticIpSettings@CAdapterIpSettings@@QEAAJPEAPEAG00@Z; CAdapterIpSettings::GetStaticIpSettings(ushort * *,ushort * *,ushort * *)
0x18001883c  test    eax, eax
0x18001883e  jns     loc_180018908
0x180018844  mov     rcx, cs:WPP_GLOBAL_Control
0x18001884b  cmp     rcx, r12
0x18001884e  jz      short loc_1800188B9
0x180018850  test    [rcx+1Ch], r15b
0x180018854  jz      short loc_1800188B9
0x180018856  cmp     byte ptr [rcx+19h], 2
0x18001885a  jb      short loc_1800188B9
0x18001885c  mov     edx, 118h
0x180018861  mov     r9d, eax
0x180018864  mov     r8, r13
0x180018867  mov     rcx, [rcx+10h]
0x18001886b  call    WPP_SF_d
0x180018870  jmp     short loc_1800188B9
0x180018872  mov     ebx, 1
0x180018877  test    eax, eax
0x180018879  jns     loc_1800187EC
0x18001887f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018886  cmp     rcx, r12
0x180018889  jz      short loc_18001881E
0x18001888b  test    [rcx+1Ch], r15b
0x18001888f  jz      short loc_18001881E
0x180018891  cmp     byte ptr [rcx+19h], 2
0x180018895  jb      short loc_18001881E
0x180018897  mov     edx, 117h
0x18001889c  mov     r9d, edi
0x18001889f  mov     r8, r13
0x1800188a2  mov     rcx, [rcx+10h]
0x1800188a6  call    WPP_SF_d
0x1800188ab  jmp     loc_18001881E
0x1800188b0  test    edi, edi
0x1800188b2  js      short loc_1800188B9
0x1800188b4  cmp     ebx, 1
0x1800188b7  jnz     short loc_180018908
0x1800188b9  mov     ebx, 8007000Eh
0x1800188be  lea     rdi, psz; "0.0.0.0"
0x1800188c5  mov     rcx, rdi; psz
0x1800188c8  call    cs:__imp_SysAllocString
0x1800188ce  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1800188d2  test    rax, rax
0x1800188d5  jz      loc_1800189DE
0x1800188db  mov     rcx, rdi; psz
0x1800188de  call    cs:__imp_SysAllocString
0x1800188e4  mov     qword ptr [rbp+57h+var_D8+8], rax
0x1800188e8  test    rax, rax
0x1800188eb  jz      loc_1800189DE
0x1800188f1  mov     rcx, rdi; psz
0x1800188f4  call    cs:__imp_SysAllocString
0x1800188fa  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1800188ff  test    rax, rax
0x180018902  jz      loc_1800189DE
0x180018908  mov     rcx, [rsp+130h+var_100]
0x18001890d  mov     rax, [rcx]
0x180018910  mov     dword ptr [rsp+130h+var_110], r14d
0x180018915  lea     r9, [rbp+57h+var_C0]
0x180018919  xor     r8d, r8d
0x18001891c  lea     rdx, ?c_wszIPAddress@@3QBGB; "IPAddress"
0x180018923  mov     rax, [rax+28h]
0x180018927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001892c  mov     ebx, eax
0x18001892e  test    eax, eax
0x180018930  js      loc_1800189DE
0x180018936  mov     rcx, [rsp+130h+var_100]
0x18001893b  mov     rax, [rcx]
0x18001893e  mov     dword ptr [rsp+130h+var_110], r14d
0x180018943  lea     r9, [rsp+130h+var_D8]
0x180018948  xor     r8d, r8d
0x18001894b  lea     rdx, ?c_wszSubnetMask@@3QBGB; "SubnetMask"
0x180018952  mov     rax, [rax+28h]
0x180018956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001895b  mov     ebx, eax
0x18001895d  test    eax, eax
0x18001895f  js      short loc_1800189DE
0x180018961  mov     rcx, [rsp+130h+var_100]
0x180018966  mov     rax, [rcx]
0x180018969  mov     dword ptr [rsp+130h+var_110], r14d
0x18001896e  lea     r9, [rsp+130h+var_F0]
0x180018973  xor     r8d, r8d
0x180018976  lea     rdx, ?c_wszDefaultGateway@@3QBGB; "DefaultGateway"
0x18001897d  mov     rax, [rax+28h]
0x180018981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018986  mov     ebx, eax
0x180018988  test    eax, eax
0x18001898a  js      short loc_1800189DE
0x18001898c  mov     rcx, [rsi+40h]
0x180018990  mov     rax, [rcx]
0x180018993  mov     [rsp+130h+var_110], r14
0x180018998  xor     r9d, r9d
0x18001899b  xor     r8d, r8d
0x18001899e  mov     rdx, [rsp+130h+var_100]
0x1800189a3  mov     rax, [rax+70h]
0x1800189a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189ac  mov     ebx, eax
0x1800189ae  test    eax, eax
0x1800189b0  jns     short loc_1800189DE
0x1800189b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189b9  cmp     rcx, r12
0x1800189bc  jz      short loc_1800189E5
0x1800189be  test    [rcx+1Ch], r15b
0x1800189c2  jz      short loc_1800189E5
0x1800189c4  cmp     byte ptr [rcx+19h], 2
0x1800189c8  jb      short loc_1800189E5
0x1800189ca  mov     edx, 119h
0x1800189cf  mov     r9d, eax
0x1800189d2  mov     r8, r13
0x1800189d5  mov     rcx, [rcx+10h]
0x1800189d9  call    WPP_SF_d
0x1800189de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189e5  mov     rdx, [rsp+130h+var_100]
0x1800189ea  test    rdx, rdx
0x1800189ed  jz      short loc_180018A05
0x1800189ef  mov     rax, [rdx]
0x1800189f2  mov     rcx, rdx
0x1800189f5  mov     rax, [rax+10h]
0x1800189f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189fe  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
