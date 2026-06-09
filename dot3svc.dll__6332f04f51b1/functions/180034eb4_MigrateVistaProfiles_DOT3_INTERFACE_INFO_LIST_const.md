# MigrateVistaProfiles(_DOT3_INTERFACE_INFO_LIST const *)

- ea: `0x180034eb4`
- end: `0x180035139`
- name: `?MigrateVistaProfiles@@YAJPEBU_DOT3_INTERFACE_INFO_LIST@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(const struct _DOT3_INTERFACE_INFO_LIST *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180035348`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x1800127c0`
- `0x180034560`
- `0x1800348d4`
- `0x180034994`
- `0x180034eb4`
- `0x180036098`
- `0x1800362c8`
- `0x180036e28`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180034fb6`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180034fb6`

## pseudocode

```c
__int64 __fastcall MigrateVistaProfiles(const struct _DOT3_INTERFACE_INFO_LIST *a1)
{
  HRESULT v2; // eax
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  void **v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  int v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+54h] [rbp-ACh]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+6Ch] [rbp-94h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 34, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
  }
  v11 = &CVistaInterfaceCollection::`vftable';
  v12 = 0;
  v13 = 0;
  v14 = 17;
  v18 = 0xFFFFFFFFLL;
  v19 = 0;
  v20 = 0;
  v21 = 10;
  v22 = 0;
  v15 = 1061158912;
  v16 = 1048576000;
  v17 = 1074790400;
  ATL::CAtlMap<_GUID,ATL::CAutoPtr<CVistaInterfaceSettings>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CAutoPtr<CVistaInterfaceSettings>>>::UpdateRehashThresholds(&v12);
  v2 = SHGetFolderPathAndSubDirW(0, 35, 0, 1u, L"Microsoft\\dot3svc\\MigrationData\\Profiles\\Interfaces", pszPath);
  v4 = v2;
  if ( v2 == 1 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    v4 = -2147287037;
    goto LABEL_28;
  }
  if ( v2 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
LABEL_28:
    if ( v5 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( !BYTE1(v5[1].Blink) || (BYTE4(v5[1].Blink) & 1) == 0 )
      goto LABEL_34;
    v8 = 38;
    v9 = v4;
    goto LABEL_32;
  }
  v6 = CVistaInterfaceCollection::CollectMigratedInterfaces((CVistaInterfaceCollection *)&v11, v3, pszPath);
  v4 = v6;
  if ( v6 >= 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control[1].Flink,
        36,
        &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids,
        (unsigned int)v13,
        *(_DWORD *)a1);
      v5 = WPP_GLOBAL_Control;
    }
    if ( !v13 || !*(_DWORD *)a1 )
      goto LABEL_34;
    if ( IsMigrationInPlace((struct CVistaInterfaceCollection *)&v11, a1) )
      v7 = MigrateInPlace((struct CVistaInterfaceCollection *)&v11, a1);
    else
      v7 = ApplySingleVistaSourceToAllTargets((struct CVistaInterfaceCollection *)&v11, a1);
    v4 = v7;
    goto LABEL_33;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    goto LABEL_38;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v8 = 37;
    v9 = (unsigned int)v6;
LABEL_32:
    WPP_SF_d(v5[1].Flink, v8, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v9);
LABEL_33:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v5[1].Blink) >= 4u && (BYTE4(v5[1].Blink) & 1) != 0 )
    WPP_SF_d(v5[1].Flink, 39, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v4);
LABEL_38:
  CVistaInterfaceCollection::~CVistaInterfaceCollection((CVistaInterfaceCollection *)&v11);
  return v4;
}

```

## disassembly

```asm
0x180034eb4  mov     [rsp-8+arg_8], rbx
0x180034eb9  mov     [rsp-8+arg_10], rdi
0x180034ebe  push    rbp
0x180034ebf  push    r12
0x180034ec1  push    r15
0x180034ec3  lea     rbp, [rsp-1A0h]
0x180034ecb  sub     rsp, 2A0h
0x180034ed2  mov     rax, cs:__security_cookie
0x180034ed9  xor     rax, rsp
0x180034edc  mov     [rbp+1B0h+var_20], rax
0x180034ee3  mov     rdi, rcx
0x180034ee6  lea     r15, WPP_GLOBAL_Control
0x180034eed  lea     r12, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x180034ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180034efb  cmp     rcx, r15
0x180034efe  jz      short loc_180034F1D
0x180034f00  cmp     byte ptr [rcx+19h], 4
0x180034f04  jb      short loc_180034F1D
0x180034f06  test    byte ptr [rcx+1Ch], 1
0x180034f0a  jz      short loc_180034F1D
0x180034f0c  mov     edx, 22h ; '"'
0x180034f11  mov     r8, r12
0x180034f14  mov     rcx, [rcx+10h]
0x180034f18  call    WPP_SF_
0x180034f1d  lea     rax, ??_7CVistaInterfaceCollection@@6B@; const CVistaInterfaceCollection::`vftable'
0x180034f24  mov     [rsp+2B0h+var_280], rax
0x180034f29  mov     [rsp+2B0h+var_278], 0
0x180034f32  mov     [rsp+2B0h+var_270], 0
0x180034f3b  mov     [rsp+2B0h+var_268], 11h
0x180034f43  mov     eax, 0FFFFFFFFh
0x180034f48  mov     [rsp+2B0h+var_258], rax
0x180034f4d  mov     [rsp+2B0h+var_250], 0
0x180034f56  mov     [rsp+2B0h+var_248], 0
0x180034f5e  mov     [rsp+2B0h+var_244], 0Ah
0x180034f66  xorps   xmm0, xmm0
0x180034f69  movdqa  [rsp+2B0h+var_240], xmm0
0x180034f6f  mov     [rsp+2B0h+var_264], 3F400000h
0x180034f77  mov     [rsp+2B0h+var_260], 3E800000h
0x180034f7f  mov     [rsp+2B0h+var_25C], 40100000h
0x180034f87  lea     rcx, [rsp+2B0h+var_278]
0x180034f8c  call    ?UpdateRehashThresholds@?$CAtlMap@U_GUID@@V?$CAutoPtr@VCVistaInterfaceSettings@@@ATL@@V?$CElementTraits@U_GUID@@@3@V?$CElementTraits@V?$CAutoPtr@VCVistaInterfaceSettings@@@ATL@@@3@@ATL@@AEAAXXZ; ATL::CAtlMap<_GUID,ATL::CAutoPtr<CVistaInterfaceSettings>,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ATL::CAutoPtr<CVistaInterfaceSettings>>>::UpdateRehashThresholds(void)
0x180034f91  nop
0x180034f92  lea     rax, [rbp+1B0h+var_230]
0x180034f96  mov     [rsp+2B0h+pszPath], rax; pszPath
0x180034f9b  lea     rax, aMicrosoftDot3s_2; "Microsoft\\dot3svc\\MigrationData\\Prof"...
0x180034fa2  mov     [rsp+2B0h+pszSubDir], rax; pszSubDir
0x180034fa7  mov     r9d, 1; dwFlags
0x180034fad  xor     r8d, r8d; hToken
0x180034fb0  lea     edx, [r9+22h]; csidl
0x180034fb4  xor     ecx, ecx; hwnd
0x180034fb6  call    cs:__imp_SHGetFolderPathAndSubDirW
0x180034fbc  mov     ebx, eax
0x180034fbe  cmp     eax, 1
0x180034fc1  jnz     short loc_180034FF9
0x180034fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fca  cmp     rcx, r15
0x180034fcd  jz      short loc_180034FEF
0x180034fcf  cmp     [rcx+19h], al
0x180034fd2  jb      short loc_180034FEF
0x180034fd4  test    [rcx+1Ch], al
0x180034fd7  jz      short loc_180034FEF
0x180034fd9  lea     edx, [rax+22h]
0x180034fdc  mov     r8, r12
0x180034fdf  mov     rcx, [rcx+10h]
0x180034fe3  call    WPP_SF_
0x180034fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fef  mov     ebx, 80030003h
0x180034ff4  jmp     loc_1800350B3
0x180034ff9  test    eax, eax
0x180034ffb  js      loc_1800350AC
0x180035001  lea     r8, [rbp+1B0h+var_230]; unsigned __int16 *
0x180035005  lea     rcx, [rsp+2B0h+var_280]; this
0x18003500a  call    ?CollectMigratedInterfaces@CVistaInterfaceCollection@@QEAAJPEBG0@Z; CVistaInterfaceCollection::CollectMigratedInterfaces(ushort const *,ushort const *)
0x18003500f  mov     ebx, eax
0x180035011  test    eax, eax
0x180035013  js      short loc_18003508A
0x180035015  mov     rcx, cs:WPP_GLOBAL_Control
0x18003501c  cmp     rcx, r15
0x18003501f  jz      short loc_180035050
0x180035021  cmp     byte ptr [rcx+19h], 4
0x180035025  jb      short loc_180035050
0x180035027  test    byte ptr [rcx+1Ch], 1
0x18003502b  jz      short loc_180035050
0x18003502d  mov     edx, 24h ; '$'
0x180035032  mov     eax, [rdi]
0x180035034  mov     dword ptr [rsp+2B0h+pszSubDir], eax
0x180035038  mov     r9d, dword ptr [rsp+2B0h+var_270]
0x18003503d  mov     r8, r12
0x180035040  mov     rcx, [rcx+10h]
0x180035044  call    WPP_SF_DD
0x180035049  mov     rcx, cs:WPP_GLOBAL_Control
0x180035050  cmp     [rsp+2B0h+var_270], 0
0x180035056  jbe     loc_1800350DF
0x18003505c  cmp     dword ptr [rdi], 0
0x18003505f  jbe     short loc_1800350DF
0x180035061  mov     rdx, rdi; struct _DOT3_INTERFACE_INFO_LIST *
0x180035064  lea     rcx, [rsp+2B0h+var_280]; this
0x180035069  call    ?IsMigrationInPlace@@YA_NAEAVCVistaInterfaceCollection@@PEBU_DOT3_INTERFACE_INFO_LIST@@@Z; IsMigrationInPlace(CVistaInterfaceCollection &,_DOT3_INTERFACE_INFO_LIST const *)
0x18003506e  mov     rdx, rdi; struct _DOT3_INTERFACE_INFO_LIST *
0x180035071  lea     rcx, [rsp+2B0h+var_280]; struct CVistaInterfaceCollection *
0x180035076  test    al, al
0x180035078  jz      short loc_180035083
0x18003507a  call    ?MigrateInPlace@@YAJAEAVCVistaInterfaceCollection@@PEBU_DOT3_INTERFACE_INFO_LIST@@@Z; MigrateInPlace(CVistaInterfaceCollection &,_DOT3_INTERFACE_INFO_LIST const *)
0x18003507f  mov     ebx, eax
0x180035081  jmp     short loc_1800350D8
0x180035083  call    ?ApplySingleVistaSourceToAllTargets@@YAJAEAVCVistaInterfaceCollection@@PEBU_DOT3_INTERFACE_INFO_LIST@@@Z; ApplySingleVistaSourceToAllTargets(CVistaInterfaceCollection &,_DOT3_INTERFACE_INFO_LIST const *)
0x180035088  jmp     short loc_18003507F
0x18003508a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035091  cmp     rcx, r15
0x180035094  jz      short loc_180035105
0x180035096  cmp     byte ptr [rcx+19h], 1
0x18003509a  jb      short loc_1800350DF
0x18003509c  test    byte ptr [rcx+1Ch], 1
0x1800350a0  jz      short loc_1800350DF
0x1800350a2  mov     edx, 25h ; '%'
0x1800350a7  mov     r9d, eax
0x1800350aa  jmp     short loc_1800350CC
0x1800350ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350b3  cmp     rcx, r15
0x1800350b6  jz      short loc_180035105
0x1800350b8  cmp     byte ptr [rcx+19h], 1
0x1800350bc  jb      short loc_1800350DF
0x1800350be  test    byte ptr [rcx+1Ch], 1
0x1800350c2  jz      short loc_1800350DF
0x1800350c4  mov     edx, 26h ; '&'
0x1800350c9  mov     r9d, ebx
0x1800350cc  mov     r8, r12
0x1800350cf  mov     rcx, [rcx+10h]
0x1800350d3  call    WPP_SF_d
0x1800350d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350df  cmp     rcx, r15
0x1800350e2  jz      short loc_180035105
0x1800350e4  cmp     byte ptr [rcx+19h], 4
0x1800350e8  jb      short loc_180035105
0x1800350ea  test    byte ptr [rcx+1Ch], 1
0x1800350ee  jz      short loc_180035105
0x1800350f0  mov     edx, 27h ; '''
0x1800350f5  mov     r9d, ebx
0x1800350f8  mov     r8, r12
0x1800350fb  mov     rcx, [rcx+10h]
0x1800350ff  call    WPP_SF_d
0x180035104  nop
0x180035105  lea     rcx, [rsp+2B0h+var_280]; this
0x18003510a  call    ??1CVistaInterfaceCollection@@UEAA@XZ; CVistaInterfaceCollection::~CVistaInterfaceCollection(void)
0x18003510f  mov     eax, ebx
0x180035111  mov     rcx, [rbp+1B0h+var_20]
0x180035118  xor     rcx, rsp; StackCookie
0x18003511b  call    __security_check_cookie
0x180035120  lea     r11, [rsp+2B0h+var_10]
0x180035128  mov     rbx, [r11+28h]
0x18003512c  mov     rdi, [r11+30h]
0x180035130  mov     rsp, r11
0x180035133  pop     r15
0x180035135  pop     r12
0x180035137  pop     rbp
0x180035138  retn
```
