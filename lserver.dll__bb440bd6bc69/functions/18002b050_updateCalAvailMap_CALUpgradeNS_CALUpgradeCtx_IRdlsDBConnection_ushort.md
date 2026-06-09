# updateCalAvailMap(CALUpgradeNS::CALUpgradeCtx *,IRdlsDBConnection *,ushort *)

- ea: `0x18002b050`
- end: `0x18002b877`
- name: `?updateCalAvailMap@@YAKPEAVCALUpgradeCtx@CALUpgradeNS@@PEAVIRdlsDBConnection@@PEAG@Z`
- size: `2087`
- prototype: `unsigned int __fastcall(struct CALUpgradeNS::CALUpgradeCtx *, struct IRdlsDBConnection *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005665`
- `0x18000d060`
- `0x18001ae3c`
- `0x18001aea4`
- `0x18001af24`
- `0x18001b128`
- `0x180022a6c`
- `0x180022d3c`
- `0x180029e60`
- `0x18002a518`
- `0x18002b050`
- `0x180036390`
- `0x1800364bc`
- `0x1800364d0`
- `0x1800662a0`
- `0x18007e360`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18002b20a`
- `msvcrt!wcscat_s` at `0x18002b20a`
- `msvcrt!swscanf_s` at `0x18002b1d0`
- `msvcrt!swscanf_s` at `0x18002b424`
- `msvcrt!swscanf_s` at `0x18002b1d0`
- `msvcrt!swscanf_s` at `0x18002b424`
- `msvcrt!_wcsnicmp` at `0x18002b444`
- `msvcrt!_wcsnicmp` at `0x18002b444`
- `msvcrt!_wcsicmp` at `0x18002b2fd`
- `msvcrt!_wcsicmp` at `0x18002b31b`
- `msvcrt!_wcsicmp` at `0x18002b2fd`
- `msvcrt!_wcsicmp` at `0x18002b31b`
- `KERNEL32!LocalAlloc` at `0x18002b292`
- `KERNEL32!LocalAlloc` at `0x18002b292`
- `KERNEL32!LocalFree` at `0x18002b7c6`
- `KERNEL32!LocalFree` at `0x18002b7c6`

## string_xrefs

- `0x18002b101`: `updateCalAvailMap`
- `0x18002b265`: `updateCalAvailMap`
- `0x18002b340`: `updateCalAvailMap`
- `0x18002b3b4`: `updateCalAvailMap`
- `0x18002b678`: `updateCalAvailMap`
- `0x18002b6ca`: `updateCalAvailMap`
- `0x18002b79d`: `updateCalAvailMap`
- `0x18002b7f6`: `updateCalAvailMap`
- `0x18002b829`: `updateCalAvailMap`
- `0x18002b5da`: `ucKeyPackType: 0x%x\nszCompanyName: [%s]\nszKeyPackId: [%s]\nszProductId: [%s]\nwMajorVersion: 0x%x\nwMinorVersion: 0x%x\ndwPlatformType: 0x%x\nucLicenseType: 0x%x\nucChannelOfPurchase: 0x%x\nszBeginSerialNumber: [%s]\ndwTotalLicenseInKeyPack: 0x%x\ndwProductFlags: 0x%x\ndwKeyPackId: 0x%x\nucKeyPackStatus: 0x%x\ndwActivateDate: 0x%x\ndwExpirationDate: 0x%x\ndwNumberOfLicenses: 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall updateCalAvailMap(
        struct CALUpgradeNS::CALUpgradeCtx *a1,
        struct IRdlsDBConnection *a2,
        unsigned __int16 *a3)
{
  PVOID *v6; // rcx
  CALUpgradeNS::LSState *v7; // r14
  CRdlsDBManager *v8; // rcx
  struct IRdlsDB *DBInstance; // rax
  __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  HLOCAL v13; // rsi
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 CALType; // rax
  int v17; // edi
  unsigned int v18; // ebx
  __int64 v20; // [rsp+38h] [rbp-E8h]
  __int64 v21; // [rsp+40h] [rbp-E0h]
  __int64 v22; // [rsp+48h] [rbp-D8h]
  __int64 v23; // [rsp+50h] [rbp-D0h]
  __int64 v24; // [rsp+58h] [rbp-C8h]
  __int64 v25; // [rsp+68h] [rbp-B8h]
  __int64 v26; // [rsp+70h] [rbp-B0h]
  __int64 v27; // [rsp+78h] [rbp-A8h]
  __int64 v28; // [rsp+80h] [rbp-A0h]
  __int64 v29; // [rsp+88h] [rbp-98h]
  __int64 v30; // [rsp+90h] [rbp-90h]
  __int64 v31; // [rsp+98h] [rbp-88h]
  int v32; // [rsp+A0h] [rbp-80h] BYREF
  int v33; // [rsp+A4h] [rbp-7Ch] BYREF
  int v34; // [rsp+A8h] [rbp-78h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-70h]
  _BYTE v36[4]; // [rsp+C0h] [rbp-60h] BYREF
  int v37; // [rsp+C4h] [rbp-5Ch]
  __int64 v38; // [rsp+C8h] [rbp-58h]
  int v39; // [rsp+D8h] [rbp-48h]
  int v40; // [rsp+DCh] [rbp-44h]
  unsigned int v41; // [rsp+E0h] [rbp-40h]
  char v42; // [rsp+E4h] [rbp-3Ch]
  __int64 v43; // [rsp+E8h] [rbp-38h]
  int v44; // [rsp+F0h] [rbp-30h]
  wchar_t String1[256]; // [rsp+6F4h] [rbp+5D4h] BYREF
  char v46; // [rsp+8F4h] [rbp+7D4h]
  _BYTE v47[512]; // [rsp+8F6h] [rbp+7D6h] BYREF
  wchar_t Destination[256]; // [rsp+AF6h] [rbp+9D6h] BYREF
  unsigned __int16 v49; // [rsp+CF6h] [rbp+BD6h]
  unsigned __int16 v50; // [rsp+CF8h] [rbp+BD8h]
  int v51; // [rsp+CFCh] [rbp+BDCh]
  unsigned __int8 v52; // [rsp+D00h] [rbp+BE0h]
  unsigned __int8 v53; // [rsp+D01h] [rbp+BE1h]
  _BYTE v54[514]; // [rsp+D02h] [rbp+BE2h] BYREF
  unsigned int v55; // [rsp+F04h] [rbp+DE4h]
  int v56; // [rsp+F08h] [rbp+DE8h]
  __int16 v57; // [rsp+F10h] [rbp+DF0h] BYREF
  _BYTE v58[510]; // [rsp+F12h] [rbp+DF2h] BYREF
  wchar_t v59; // [rsp+1110h] [rbp+FF0h] BYREF
  _BYTE v60[510]; // [rsp+1112h] [rbp+FF2h] BYREF

  v59 = 0;
  memset_0(v60, 0, sizeof(v60));
  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  v33 = 0;
  v32 = 0;
  v38 = 0;
  v43 = 0;
  v44 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
      L"updateCalAvailMap");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v35 = *((_QWORD *)a1 + 5);
  v7 = (struct CALUpgradeNS::CALUpgradeCtx *)((char *)a1 + 48);
  if ( !a2 || !a3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 )
    {
      WPP_SF_S(v6[2], 60, &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids, L"updateCalAvailMap");
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v12 = 87;
    goto LABEL_85;
  }
  std::_Tree<std::_Tmap_traits<unsigned long,unsigned long,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::clear((char *)a1 + 48);
  if ( *((_DWORD *)a1 + 2) == 2 )
    CALUpgradeNS::LSState::addKeyPack((struct CALUpgradeNS::CALUpgradeCtx *)((char *)a1 + 48), 0x50000u, 0xFFFFFFFF);
  memset_0(v36, 0, 0xE50u);
  DBInstance = CRdlsDBManager::GetDBInstance(v8);
  if ( (*(unsigned int (__fastcall **)(struct IRdlsDB *))(*(_QWORD *)DBInstance + 40LL))(DBInstance) )
  {
    v43 = 0;
    swscanf_s(a3, L"%3s-%ld.%02ld-%9s", Destination, 256, &v33, &v32, &v57, 256);
    v49 = v33;
    v50 = v32;
    v32 = 0;
    v33 = 0;
    wcscat_s(Destination, 0x100u, L"%");
    v10 = 1;
    v11 = 1610612740;
  }
  else
  {
    v10 = 0;
    v11 = -1610612737;
  }
  v12 = TLSDBKeyPackEnumBegin((__int64 *)a2, v10, v11, (__int64)v36, 1);
  if ( v12 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
          L"updateCalAvailMap");
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    goto LABEL_88;
  }
  v13 = LocalAlloc(0x40u, 0x4000u);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v15 = 62;
LABEL_65:
    WPP_SF_S(v14[2], v15, &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids, L"updateCalAvailMap");
  }
  while ( 1 )
  {
    memset_0(v36, 0, 0xE50u);
    v12 = TLSDBKeyPackEnumNext(a2, v36);
    if ( v12 )
      break;
    if ( _wcsicmp(String1, L"3d267954-eeb7-11d1-b94e-00c04fa3080d")
      || _wcsicmp(Destination, L"3d267954-eeb7-11d1-b94e-00c04fa3080d") )
    {
      if ( v46 >= 0 )
      {
        if ( v42 >= 0 )
        {
          v46 &= 0xFu;
          v42 &= 0xFu;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              66,
              (unsigned int)&WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
              (unsigned int)L"updateCalAvailMap",
              0);
          LODWORD(v20) = 256;
          swscanf_s(Destination, L"%3s-%ld.%02ld-%9s", &v59, 256, &v33, &v32, &v57, v20);
          if ( _wcsnicmp(&v59, L"A02", 3u) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                (unsigned int)&WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
                (unsigned int)L"updateCalAvailMap",
                (__int64)Destination);
          }
          else
          {
            CALType = GetCALType(Destination);
            if ( !CALType )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  68,
                  (unsigned int)&WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
                  (unsigned int)L"updateCalAvailMap",
                  (__int64)Destination);
              goto LABEL_72;
            }
            v34 = 0;
            if ( (unsigned int)CanSatisfy(CALType, HIDWORD(v35), &v34) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  69,
                  &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
                  L"updateCalAvailMap");
LABEL_72:
              v12 = -1073217523;
              goto LABEL_78;
            }
            if ( v34 )
            {
              if ( v13 )
              {
                memset_0(v13, 0, 0x4000u);
                v14 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
                  goto LABEL_51;
                LODWORD(v31) = v41;
                LODWORD(v30) = v40;
                LODWORD(v29) = v39;
                LODWORD(v28) = (unsigned __int8)v42;
                LODWORD(v27) = v37;
                LODWORD(v26) = v56;
                LODWORD(v25) = v55;
                LODWORD(v24) = v53;
                LODWORD(v23) = v52;
                LODWORD(v22) = v51;
                LODWORD(v21) = v50;
                LODWORD(v20) = v49;
                StringCchPrintfW(
                  (unsigned __int16 *)v13,
                  0x2000u,
                  L"ucKeyPackType: 0x%x\r\n"
                   "szCompanyName: [%s]\r\n"
                   "szKeyPackId: [%s]\r\n"
                   "szProductId: [%s]\r\n"
                   "wMajorVersion: 0x%x\r\n"
                   "wMinorVersion: 0x%x\r\n"
                   "dwPlatformType: 0x%x\r\n"
                   "ucLicenseType: 0x%x\r\n"
                   "ucChannelOfPurchase: 0x%x\r\n"
                   "szBeginSerialNumber: [%s]\r\n"
                   "dwTotalLicenseInKeyPack: 0x%x\r\n"
                   "dwProductFlags: 0x%x\r\n"
                   "dwKeyPackId: 0x%x\r\n"
                   "ucKeyPackStatus: 0x%x\r\n"
                   "dwActivateDate: 0x%x\r\n"
                   "dwExpirationDate: 0x%x\r\n"
                   "dwNumberOfLicenses: 0x%x\r\n",
                  (unsigned __int8)v46,
                  v47,
                  String1,
                  Destination,
                  v20,
                  v21,
                  v22,
                  v23,
                  v24,
                  v54,
                  v25,
                  v26,
                  v27,
                  v28,
                  v29,
                  v30,
                  v31);
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  71,
                  (unsigned int)&WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
                  (unsigned int)L"updateCalAvailMap",
                  (__int64)v13);
              }
              v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
              v17 = v50 | (v49 << 16);
              if ( ((v46 - 4) & 0xFD) == 0 || v42 == 10 )
              {
                if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x1000) != 0 )
                {
                  v15 = 72;
                  goto LABEL_65;
                }
              }
              else
              {
                if ( v55 < v41 )
                  v18 = 0;
                else
                  v18 = v55 - v41;
                if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x1000) != 0 )
                  WPP_SF_SDD(
                    (unsigned int)v14[2],
                    73,
                    (unsigned int)&WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
                    (unsigned int)L"updateCalAvailMap",
                    v50,
                    v18);
                CALUpgradeNS::LSState::addKeyPack(v7, v17, v18);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                  WPP_SF_SDD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    74,
                    (unsigned int)&WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
                    (unsigned int)L"updateCalAvailMap",
                    v17,
                    v18);
              }
            }
            else
            {
              v14 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              {
                v15 = 70;
                goto LABEL_65;
              }
            }
          }
        }
        else
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            v15 = 65;
            goto LABEL_65;
          }
        }
      }
      else
      {
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          v15 = 64;
          goto LABEL_65;
        }
      }
    }
    else
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v15 = 63;
        goto LABEL_65;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids,
      L"updateCalAvailMap");
  if ( v12 == 1074790400 )
    v12 = 0;
LABEL_78:
  if ( v13 )
    LocalFree(v13);
  TLSDBKeyPackEnumEnd(a2);
LABEL_15:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_85:
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 )
    WPP_SF_S(v6[2], 76, &WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids, L"updateCalAvailMap");
LABEL_88:
  __LicensePack::~__LicensePack((__LicensePack *)v36);
  return v12;
}

```

## disassembly

```asm
0x18002b050  mov     [rsp-8+arg_18], rbx
0x18002b055  push    rbp
0x18002b056  push    rsi
0x18002b057  push    rdi
0x18002b058  push    r12
0x18002b05a  push    r13
0x18002b05c  push    r14
0x18002b05e  push    r15
0x18002b060  lea     rbp, [rsp-1200h]
0x18002b068  mov     eax, 1320h
0x18002b06d  call    _alloca_probe
0x18002b072  sub     rsp, rax
0x18002b075  mov     rax, cs:__security_cookie
0x18002b07c  xor     rax, rsp
0x18002b07f  mov     [rbp+1230h+var_40], rax
0x18002b086  mov     rdi, r8
0x18002b089  mov     r15, rdx
0x18002b08c  mov     rbx, rcx
0x18002b08f  xor     r12d, r12d
0x18002b092  mov     [rbp+1230h+var_240], r12w
0x18002b09a  mov     esi, 1FEh
0x18002b09f  mov     r8d, esi; Size
0x18002b0a2  xor     edx, edx; Val
0x18002b0a4  lea     rcx, [rbp+1230h+var_23E]; void *
0x18002b0ab  call    memset_0
0x18002b0b0  mov     [rbp+1230h+var_440], r12w
0x18002b0b8  mov     r8d, esi; Size
0x18002b0bb  xor     edx, edx; Val
0x18002b0bd  lea     rcx, [rbp+1230h+var_43E]; void *
0x18002b0c4  call    memset_0
0x18002b0c9  mov     [rbp+1230h+var_12AC], r12d
0x18002b0cd  mov     [rbp+1230h+var_12B0], r12d
0x18002b0d1  mov     [rbp+1230h+var_1288], r12
0x18002b0d5  mov     [rbp+1230h+var_1268], r12
0x18002b0d9  mov     [rbp+1230h+var_1260], r12d
0x18002b0dd  lea     rax, WPP_GLOBAL_Control
0x18002b0e4  mov     r13d, 1000h
0x18002b0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0f1  cmp     rcx, rax
0x18002b0f4  jz      short loc_18002B11F
0x18002b0f6  test    [rcx+1Ch], r13d
0x18002b0fa  jz      short loc_18002B11F
0x18002b0fc  lea     edx, [r12+3Bh]
0x18002b101  lea     r9, aUpdatecalavail; "updateCalAvailMap"
0x18002b108  lea     r8, WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids
0x18002b10f  mov     rcx, [rcx+10h]
0x18002b113  call    WPP_SF_S
0x18002b118  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b11f  mov     rax, [rbx+28h]
0x18002b123  mov     [rbp+1230h+var_12A0], rax
0x18002b127  lea     r14, [rbx+30h]
0x18002b12b  test    r15, r15
0x18002b12e  jz      loc_18002B7DF
0x18002b134  test    rdi, rdi
0x18002b137  jz      loc_18002B7DF
0x18002b13d  mov     rcx, r14
0x18002b140  call    ?clear@?$_Tree@V?$_Tmap_traits@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,ulong,std::less<ulong>,std::allocator<std::pair<ulong const,ulong>>,0>>::clear(void)
0x18002b145  cmp     dword ptr [rbx+8], 2
0x18002b149  jnz     short loc_18002B15C
0x18002b14b  or      r8d, 0FFFFFFFFh; unsigned int
0x18002b14f  mov     edx, 50000h; unsigned int
0x18002b154  mov     rcx, r14; this
0x18002b157  call    ?addKeyPack@LSState@CALUpgradeNS@@QEAAXKK@Z; CALUpgradeNS::LSState::addKeyPack(ulong,ulong)
0x18002b15c  xor     edx, edx; Val
0x18002b15e  mov     r8d, 0E50h; Size
0x18002b164  lea     rcx, [rbp+1230h+var_1290]; void *
0x18002b168  call    memset_0
0x18002b16d  call    ?GetDBInstance@CRdlsDBManager@@QEAAPEAVIRdlsDB@@XZ; CRdlsDBManager::GetDBInstance(void)
0x18002b172  mov     rdx, rax
0x18002b175  mov     rcx, [rax]
0x18002b178  mov     rax, [rcx+28h]
0x18002b17c  mov     rcx, rdx
0x18002b17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b184  mov     esi, 100h
0x18002b189  mov     ebx, 1
0x18002b18e  test    eax, eax
0x18002b190  jz      loc_18002B220
0x18002b196  mov     [rbp+1230h+var_1268], r12
0x18002b19a  mov     dword ptr [rsp+1350h+var_1318], esi
0x18002b19e  lea     rax, [rbp+1230h+var_440]
0x18002b1a5  mov     [rsp+1350h+var_1320], rax
0x18002b1aa  lea     rax, [rbp+1230h+var_12B0]
0x18002b1ae  mov     [rsp+1350h+var_1328], rax
0x18002b1b3  lea     rax, [rbp+1230h+var_12AC]
0x18002b1b7  mov     [rsp+1350h+var_1330], rax
0x18002b1bc  mov     r9d, esi
0x18002b1bf  lea     r8, [rbp+1230h+Destination]
0x18002b1c6  lea     rdx, a3sLd02ld9s; "%3s-%ld.%02ld-%9s"
0x18002b1cd  mov     rcx, rdi; Buffer
0x18002b1d0  call    cs:__imp_swscanf_s
0x18002b1d7  nop     dword ptr [rax+rax+00h]
0x18002b1dc  movzx   eax, word ptr [rbp+1230h+var_12AC]
0x18002b1e0  mov     [rbp+1230h+var_65A], ax
0x18002b1e7  movzx   eax, word ptr [rbp+1230h+var_12B0]
0x18002b1eb  mov     [rbp+1230h+var_658], ax
0x18002b1f2  mov     [rbp+1230h+var_12B0], r12d
0x18002b1f6  mov     [rbp+1230h+var_12AC], r12d
0x18002b1fa  lea     r8, Source; "%"
0x18002b201  mov     edx, esi; SizeInWords
0x18002b203  lea     rcx, [rbp+1230h+Destination]; Destination
0x18002b20a  call    cs:__imp_wcscat_s
0x18002b211  nop     dword ptr [rax+rax+00h]
0x18002b216  mov     edx, ebx
0x18002b218  mov     r8d, 60000004h
0x18002b21e  jmp     short loc_18002B229
0x18002b220  mov     edx, r12d
0x18002b223  mov     r8d, 9FFFFFFFh
0x18002b229  mov     dword ptr [rsp+1350h+var_1330], ebx
0x18002b22d  lea     r9, [rbp+1230h+var_1290]
0x18002b231  mov     rcx, r15
0x18002b234  call    TLSDBKeyPackEnumBegin
0x18002b239  mov     ebx, eax
0x18002b23b  test    eax, eax
0x18002b23d  jz      short loc_18002B288
0x18002b23f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b246  lea     rdi, WPP_GLOBAL_Control
0x18002b24d  cmp     rcx, rdi
0x18002b250  jz      loc_18002B841
0x18002b256  test    [rcx+1Ch], r13d
0x18002b25a  jz      loc_18002B819
0x18002b260  mov     edx, 3Dh ; '='
0x18002b265  lea     r9, aUpdatecalavail; "updateCalAvailMap"
0x18002b26c  lea     r8, WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids
0x18002b273  mov     rcx, [rcx+10h]
0x18002b277  call    WPP_SF_S
0x18002b27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b283  jmp     loc_18002B819
0x18002b288  mov     edx, 4000h; uBytes
0x18002b28d  mov     ecx, 40h ; '@'; uFlags
0x18002b292  call    cs:__imp_LocalAlloc
0x18002b299  nop     dword ptr [rax+rax+00h]
0x18002b29e  mov     rsi, rax
0x18002b2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2a8  lea     rdi, WPP_GLOBAL_Control
0x18002b2af  cmp     rcx, rdi
0x18002b2b2  jz      short loc_18002B2C8
0x18002b2b4  test    [rcx+1Ch], r13d
0x18002b2b8  jz      short loc_18002B2C8
0x18002b2ba  mov     edx, 3Eh ; '>'
0x18002b2bf  jmp     short loc_18002B340
0x18002b2c1  lea     rdi, WPP_GLOBAL_Control
0x18002b2c8  xor     edx, edx; Val
0x18002b2ca  mov     r8d, 0E50h; Size
0x18002b2d0  lea     rcx, [rbp+1230h+var_1290]; void *
0x18002b2d4  call    memset_0
0x18002b2d9  lea     rdx, [rbp+1230h+var_1290]
0x18002b2dd  mov     rcx, r15
0x18002b2e0  call    TLSDBKeyPackEnumNext
0x18002b2e5  mov     ebx, eax
0x18002b2e7  test    eax, eax
0x18002b2e9  jnz     loc_18002B786
0x18002b2ef  lea     rdx, a3d267954Eeb711; "3d267954-eeb7-11d1-b94e-00c04fa3080d"
0x18002b2f6  lea     rcx, [rbp+1230h+String1]; String1
0x18002b2fd  call    cs:__imp__wcsicmp
0x18002b304  nop     dword ptr [rax+rax+00h]
0x18002b309  test    eax, eax
0x18002b30b  jnz     short loc_18002B34C
0x18002b30d  lea     rdx, a3d267954Eeb711; "3d267954-eeb7-11d1-b94e-00c04fa3080d"
0x18002b314  lea     rcx, [rbp+1230h+Destination]; String1
0x18002b31b  call    cs:__imp__wcsicmp
0x18002b322  nop     dword ptr [rax+rax+00h]
0x18002b327  test    eax, eax
0x18002b329  jnz     short loc_18002B34C
0x18002b32b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b332  cmp     rcx, rdi
0x18002b335  jz      short loc_18002B2C8
0x18002b337  test    [rcx+1Ch], r13d
0x18002b33b  jz      short loc_18002B2C8
0x18002b33d  lea     edx, [rbx+3Fh]
0x18002b340  lea     r9, aUpdatecalavail; "updateCalAvailMap"
0x18002b347  jmp     loc_18002B708
0x18002b34c  mov     cl, [rbp+1230h+var_A5C]
0x18002b352  test    cl, cl
0x18002b354  jns     short loc_18002B377
0x18002b356  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b35d  cmp     rcx, rdi
0x18002b360  jz      loc_18002B2C8
0x18002b366  test    [rcx+1Ch], r13d
0x18002b36a  jz      loc_18002B2C8
0x18002b370  mov     edx, 40h ; '@'
0x18002b375  jmp     short loc_18002B340
0x18002b377  mov     al, [rbp+1230h+var_126C]
0x18002b37a  test    al, al
0x18002b37c  jns     short loc_18002B39F
0x18002b37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b385  cmp     rcx, rdi
0x18002b388  jz      loc_18002B2C8
0x18002b38e  test    [rcx+1Ch], r13d
0x18002b392  jz      loc_18002B2C8
0x18002b398  mov     edx, 41h ; 'A'
0x18002b39d  jmp     short loc_18002B340
0x18002b39f  and     cl, 0Fh
0x18002b3a2  mov     [rbp+1230h+var_A5C], cl
0x18002b3a8  and     al, 0Fh
0x18002b3aa  mov     [rbp+1230h+var_126C], al
0x18002b3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3b4  lea     rbx, aUpdatecalavail; "updateCalAvailMap"
0x18002b3bb  cmp     rcx, rdi
0x18002b3be  jz      short loc_18002B3E3
0x18002b3c0  test    [rcx+1Ch], r13d
0x18002b3c4  jz      short loc_18002B3E3
0x18002b3c6  mov     edx, 42h ; 'B'
0x18002b3cb  mov     dword ptr [rsp+1350h+var_1330], r12d
0x18002b3d0  mov     r9, rbx
0x18002b3d3  lea     r8, WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids
0x18002b3da  mov     rcx, [rcx+10h]
0x18002b3de  call    WPP_SF_SD
0x18002b3e3  mov     dword ptr [rsp+1350h+var_1318], 100h
0x18002b3eb  lea     rax, [rbp+1230h+var_440]
0x18002b3f2  mov     [rsp+1350h+var_1320], rax
0x18002b3f7  lea     rax, [rbp+1230h+var_12B0]
0x18002b3fb  mov     [rsp+1350h+var_1328], rax
0x18002b400  lea     rax, [rbp+1230h+var_12AC]
0x18002b404  mov     [rsp+1350h+var_1330], rax
0x18002b409  mov     r9d, 100h
0x18002b40f  lea     r8, [rbp+1230h+var_240]
0x18002b416  lea     rdx, a3sLd02ld9s; "%3s-%ld.%02ld-%9s"
0x18002b41d  lea     rcx, [rbp+1230h+Destination]; Buffer
0x18002b424  call    cs:__imp_swscanf_s
0x18002b42b  nop     dword ptr [rax+rax+00h]
0x18002b430  mov     r8d, 3; MaxCount
0x18002b436  lea     rdx, aA02; "A02"
0x18002b43d  lea     rcx, [rbp+1230h+var_240]; String1
0x18002b444  call    cs:__imp__wcsnicmp
0x18002b44b  nop     dword ptr [rax+rax+00h]
0x18002b450  test    eax, eax
0x18002b452  jz      short loc_18002B497
0x18002b454  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b45b  cmp     rcx, rdi
0x18002b45e  jz      loc_18002B2C8
0x18002b464  test    [rcx+1Ch], r13d
0x18002b468  jz      loc_18002B2C8
0x18002b46e  mov     edx, 43h ; 'C'
0x18002b473  lea     rax, [rbp+1230h+Destination]
0x18002b47a  mov     [rsp+1350h+var_1330], rax
0x18002b47f  mov     r9, rbx
0x18002b482  lea     r8, WPP_de30e712609c3379e9ab51af44e3e3a5_Traceguids
0x18002b489  mov     rcx, [rcx+10h]
0x18002b48d  call    WPP_SF_SS
0x18002b492  jmp     loc_18002B2C8
0x18002b497  lea     rcx, [rbp+1230h+Destination]
0x18002b49e  call    GetCALType
0x18002b4a3  test    rax, rax
0x18002b4a6  jz      loc_18002B749
0x18002b4ac  mov     [rbp+1230h+var_12A8], r12d
0x18002b4b0  lea     r8, [rbp+1230h+var_12A8]
0x18002b4b4  mov     edx, dword ptr [rbp+1230h+var_12A0+4]
0x18002b4b7  mov     rcx, rax
0x18002b4ba  call    CanSatisfy
0x18002b4bf  test    eax, eax
0x18002b4c1  jnz     loc_18002B71D
0x18002b4c7  cmp     [rbp+1230h+var_12A8], r12d
0x18002b4cb  jnz     short loc_18002B4EF
0x18002b4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4d4  cmp     rcx, rdi
0x18002b4d7  jz      loc_18002B2C8
0x18002b4dd  test    [rcx+1Ch], r13d
0x18002b4e1  jz      loc_18002B2C8
0x18002b4e7  lea     edx, [rax+46h]
0x18002b4ea  jmp     loc_18002B705
0x18002b4ef  test    rsi, rsi
0x18002b4f2  jz      loc_18002B612
0x18002b4f8  xor     edx, edx; Val
0x18002b4fa  mov     r8d, 4000h; Size
0x18002b500  mov     rcx, rsi; void *
0x18002b503  call    memset_0
0x18002b508  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b50f  cmp     rcx, rdi
0x18002b512  jz      loc_18002B619
0x18002b518  test    [rcx+1Ch], r13d
0x18002b51c  jz      loc_18002B619
0x18002b522  movzx   ecx, [rbp+1230h+var_126C]
0x18002b526  movzx   edx, [rbp+1230h+var_64F]
0x18002b52d  movzx   r8d, [rbp+1230h+var_650]
0x18002b535  movzx   r10d, [rbp+1230h+var_658]
0x18002b53d  movzx   r11d, [rbp+1230h+var_65A]
0x18002b545  movzx   r9d, [rbp+1230h+var_A5C]
0x18002b54d  mov     eax, [rbp+1230h+var_1270]
0x18002b550  mov     dword ptr [rsp+1350h+var_12B8], eax
0x18002b557  mov     eax, [rbp+1230h+var_1274]
0x18002b55a  mov     dword ptr [rsp+1350h+var_12C0], eax
0x18002b561  mov     eax, [rbp+1230h+var_1278]
0x18002b564  mov     dword ptr [rsp+1350h+var_12C8], eax
0x18002b56b  mov     dword ptr [rsp+1350h+var_12D0], ecx
0x18002b572  mov     eax, [rbp+1230h+var_128C]
0x18002b575  mov     dword ptr [rsp+1350h+var_12D8], eax
0x18002b579  mov     eax, [rbp+1230h+var_448]
0x18002b57f  mov     dword ptr [rsp+1350h+var_12E0], eax
0x18002b583  mov     eax, [rbp+1230h+var_44C]
0x18002b589  mov     dword ptr [rsp+1350h+var_12E8], eax
0x18002b58d  lea     rax, [rbp+1230h+var_64E]
0x18002b594  mov     [rsp+1350h+var_12F0], rax
0x18002b599  mov     dword ptr [rsp+1350h+var_12F8], edx
0x18002b59d  mov     dword ptr [rsp+1350h+var_1300], r8d
0x18002b5a2  mov     eax, [rbp+1230h+var_654]
0x18002b5a8  mov     dword ptr [rsp+1350h+var_1308], eax
0x18002b5ac  mov     dword ptr [rsp+1350h+var_1310], r10d
0x18002b5b1  mov     dword ptr [rsp+1350h+var_1318], r11d
0x18002b5b6  lea     rax, [rbp+1230h+Destination]
0x18002b5bd  mov     [rsp+1350h+var_1320], rax
  ... truncated ...
```
