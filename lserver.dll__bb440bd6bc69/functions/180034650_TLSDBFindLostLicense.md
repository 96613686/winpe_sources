# TLSDBFindLostLicense

- ea: `0x180034650`
- end: `0x180034c33`
- name: `TLSDBFindLostLicense`
- size: `1507`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028ab4`

## callees

- `0x180005665`
- `0x18001ad48`
- `0x18001ebc0`
- `0x180022910`
- `0x180030a20`
- `0x1800340f0`
- `0x180034650`
- `0x1800662a0`
- `0x1800a0fb0`
- `0x1800a1070`

## import_xrefs

- `msvcrt!time` at `0x1800349e5`
- `msvcrt!time` at `0x1800349e5`
- `KERNEL32!CompareFileTime` at `0x180034943`
- `KERNEL32!CompareFileTime` at `0x180034943`
- `KERNEL32!LocalAlloc` at `0x18003484c`
- `KERNEL32!LocalAlloc` at `0x18003484c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TLSDBFindLostLicense(
        struct IRdlsDBConnection *a1,
        __int64 a2,
        struct _HWID *a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v9; // r13d
  unsigned int v10; // r12d
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned __int64 v13; // rbx
  __int128 v14; // rdi
  const FILETIME *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int *v22; // rax
  __int64 v23; // rcx
  int v24; // ecx
  char v25; // al
  void *v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-C8h]
  __int128 v29; // [rsp+40h] [rbp-C0h]
  struct _EVENT_DESCRIPTOR v30; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int128 v33; // [rsp+80h] [rbp-80h]
  _QWORD v34[3]; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+ACh] [rbp-54h]
  int v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+B4h] [rbp-4Ch]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  _BYTE v40[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+C4h] [rbp-3Ch]
  _QWORD *v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+ECh] [rbp-14h]
  unsigned __int16 *v47; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v48; // [rsp+F8h] [rbp-8h]
  _BYTE v49[4]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v50; // [rsp+114h] [rbp+14h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  __int64 v52; // [rsp+138h] [rbp+38h]
  int v53; // [rsp+140h] [rbp+40h]
  unsigned __int8 v54; // [rsp+944h] [rbp+844h]
  unsigned __int16 v55[256]; // [rsp+946h] [rbp+846h] BYREF
  unsigned __int16 v56[256]; // [rsp+B46h] [rbp+A46h] BYREF
  unsigned __int16 v57; // [rsp+D46h] [rbp+C46h]
  unsigned __int16 v58; // [rsp+D48h] [rbp+C48h]
  int v59; // [rsp+D4Ch] [rbp+C4Ch]
  _BYTE v60[4]; // [rsp+F60h] [rbp+E60h] BYREF
  unsigned int v61; // [rsp+F64h] [rbp+E64h]
  int v62; // [rsp+F6Ch] [rbp+E6Ch]
  unsigned __int16 v63[32]; // [rsp+F78h] [rbp+E78h] BYREF
  unsigned __int16 v64[256]; // [rsp+FB8h] [rbp+EB8h] BYREF
  int v65; // [rsp+11B8h] [rbp+10B8h]
  unsigned int v66; // [rsp+11BCh] [rbp+10BCh]
  int v67; // [rsp+11C4h] [rbp+10C4h]
  int v68; // [rsp+11C8h] [rbp+10C8h]
  int v69; // [rsp+11CCh] [rbp+10CCh]
  int v70; // [rsp+11D0h] [rbp+10D0h]
  int v71; // [rsp+11D4h] [rbp+10D4h]
  int v72; // [rsp+11D8h] [rbp+10D8h]

  *(_QWORD *)&v30.Id = a5;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  memset_0(v60, 0, 0x288u);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v27 = 0;
  memset_0(v40, 0, 0x48u);
  v34[0] = 0;
  v39 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids);
  v52 = 0;
  v34[1] = *(_QWORD *)(a2 + 24);
  v34[2] = *(_QWORD *)(a2 + 32);
  v35 = *(_DWORD *)(a2 + 16);
  v36 = *(_DWORD *)(a2 + 44);
  v37 = *(_DWORD *)(a2 + 40);
  v38 = 1;
  v10 = DBFindLostLicenseExact(
          a1,
          (struct __AllocateRequest *)v34,
          a3,
          (struct __LicensePack *)v49,
          (struct __ReplLicenseClient *)v60);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v12 = 11;
LABEL_50:
      WPP_SF_(v11[2], v12, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids);
  *(_QWORD *)&v29 = 10000000 * (v65 + 0x2B6109100LL);
  *((_QWORD *)&v29 + 1) = 10000000 * ((int)v66 + 0x2B6109100LL);
  v28 = __PAIR64__(v50, v61);
  v41 = v58 | (v57 << 16);
  v42 = LocalAlloc(0x40u, 8u);
  *v42 = v56;
  v43 = 1;
  v44 = v55;
  v45 = *(_DWORD *)(a2 + 40);
  v46 = v59;
  v47 = v63;
  v48 = v64;
  *(_QWORD *)&v31 = v40;
  DWORD2(v31) = v54;
  HIDWORD(v31) = v50;
  LODWORD(v32) = v62;
  v13 = v28;
  *((_QWORD *)&v32 + 1) = v28;
  v14 = v29;
  v33 = v29;
  v10 = CTLSPolicy::PMLicenseRequest(*(CTLSPolicy **)a2, *(void **)(a2 + 8), 6u, &v31, &v27, 1);
  if ( v10 )
    goto LABEL_51;
  v15 = (const FILETIME *)v27;
  if ( v27 )
  {
    if ( *((_QWORD *)v27 + 1) )
    {
      if ( *(_DWORD *)v27 )
      {
LABEL_18:
        if ( CompareFileTime(v15 + 2, v15 + 3) > 0 )
        {
          v16 = *(_QWORD *)a2 + 600LL;
          v17 = *(_QWORD *)a2 + 88LL;
          v10 = -939524081;
          v30 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
          TLSLogEvent(&v30, 0xC800000F, v17, v16);
          goto LABEL_51;
        }
        goto LABEL_20;
      }
    }
    else if ( !*(_DWORD *)v27 )
    {
      goto LABEL_18;
    }
    *(_DWORD *)v27 = 0;
    *((_QWORD *)v27 + 1) = 0;
    v15 = (const FILETIME *)v27;
    goto LABEL_18;
  }
LABEL_20:
  if ( v54 == 4 )
  {
    v9 = 1074266114;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v19 = 13;
LABEL_27:
      WPP_SF_(v18[2], v19, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids);
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v19 = 14;
      goto LABEL_27;
    }
  }
  if ( v66 >= time(0) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_36;
    v21 = 16;
  }
  else
  {
    v9 = -1073217526;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_36;
    v21 = 15;
  }
  WPP_SF_(v20[2], v21, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids);
LABEL_36:
  *(_QWORD *)(a4 + 2664) = 0;
  *(_DWORD *)a4 = v67;
  *(_QWORD *)(a4 + 8) = v13;
  *(_DWORD *)(a4 + 16) = v50;
  *(_DWORD *)(a4 + 20) = v61;
  *(_DWORD *)(a4 + 24) = v62;
  *(_DWORD *)(a4 + 32) = v68;
  *(_DWORD *)(a4 + 36) = v69;
  *(_DWORD *)(a4 + 40) = v70;
  *(_DWORD *)(a4 + 44) = v71;
  *(_DWORD *)(a4 + 48) = v72;
  *(_DWORD *)(a4 + 68) = v54 == 4;
  *(_OWORD *)(a4 + 52) = v14;
  *(_DWORD *)(a4 + 72) = v58 | (v57 << 16);
  StringCbCopyW((unsigned __int16 *)(a4 + 76), 0x200u, v55);
  StringCbCopyW((unsigned __int16 *)(a4 + 588), 0x200u, v56);
  StringCbCopyW((unsigned __int16 *)(a4 + 1100), 0x200u, **(const unsigned __int16 ***)(*(_QWORD *)(a2 + 696) + 8LL));
  StringCbCopyW((unsigned __int16 *)(a4 + 1612), 0x200u, v64);
  StringCbCopyW((unsigned __int16 *)(a4 + 2124), 0x200u, v63);
  *(_DWORD *)(a4 + 2636) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a4 + 2640) = *(_DWORD *)(a2 + 44);
  v22 = (int *)v27;
  if ( v27 )
    v23 = *((_QWORD *)v27 + 1);
  else
    v23 = 0;
  *(_QWORD *)(a4 + 2648) = v23;
  if ( v22 )
    v24 = *v22;
  else
    v24 = 0;
  *(_DWORD *)(a4 + 2656) = v24;
  if ( !*(_QWORD *)&v30.Id )
    goto LABEL_51;
  v25 = v60[0];
  **(_BYTE **)&v30.Id = v60[0];
  if ( v25 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v12 = 17;
      goto LABEL_50;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v12 = 18;
      goto LABEL_50;
    }
  }
LABEL_51:
  if ( v10 )
    v9 = v10;
  __LicensePack::~__LicensePack((__LicensePack *)v49);
  return v9;
}

```

## disassembly

```asm
0x180034650  push    rbp
0x180034652  push    rbx
0x180034653  push    rsi
0x180034654  push    rdi
0x180034655  push    r12
0x180034657  push    r13
0x180034659  push    r14
0x18003465b  push    r15
0x18003465d  lea     rbp, [rsp-1108h]
0x180034665  mov     eax, 1208h
0x18003466a  call    _alloca_probe
0x18003466f  sub     rsp, rax
0x180034672  mov     rax, cs:__security_cookie
0x180034679  xor     rax, rsp
0x18003467c  mov     [rbp+1140h+var_50], rax
0x180034683  mov     r14, r9
0x180034686  mov     rdi, r8
0x180034689  mov     r15, rdx
0x18003468c  mov     rbx, rcx
0x18003468f  mov     rax, [rbp+1140h+arg_20]
0x180034696  mov     qword ptr [rsp+1240h+var_11F0.Id], rax
0x18003469b  xor     r12d, r12d
0x18003469e  mov     [rbp+1140h+var_1128], r12
0x1800346a2  mov     [rbp+1140h+var_1108], r12
0x1800346a6  mov     [rbp+1140h+var_1100], r12d
0x1800346aa  xor     edx, edx; Val
0x1800346ac  mov     r8d, 288h; Size
0x1800346b2  lea     rcx, [rbp+1140h+var_2E0]; void *
0x1800346b9  call    memset_0
0x1800346be  xorps   xmm0, xmm0
0x1800346c1  movups  [rsp+1240h+var_11E0], xmm0
0x1800346c6  movups  [rsp+1240h+var_11D0], xmm0
0x1800346cb  movups  [rbp+1140h+var_11C0], xmm0
0x1800346cf  mov     [rsp+1240h+var_1210], r12
0x1800346d4  xor     edx, edx; Val
0x1800346d6  lea     r8d, [r12+48h]; Size
0x1800346db  lea     rcx, [rbp+1140h+var_1180]; void *
0x1800346df  call    memset_0
0x1800346e4  mov     [rbp+1140h+var_11B0], r12
0x1800346e8  mov     [rbp+1140h+var_1188], r12
0x1800346ec  mov     r13d, r12d
0x1800346ef  lea     rax, WPP_GLOBAL_Control
0x1800346f6  mov     sil, 20h ; ' '
0x1800346f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180034700  cmp     rcx, rax
0x180034703  jz      short loc_180034720
0x180034705  test    [rcx+1Ch], sil
0x180034709  jz      short loc_180034720
0x18003470b  lea     edx, [r12+0Ah]
0x180034710  lea     r8, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids
0x180034717  mov     rcx, [rcx+10h]
0x18003471b  call    WPP_SF_
0x180034720  mov     [rbp+1140h+var_1108], r12
0x180034724  mov     rax, [r15+18h]
0x180034728  mov     [rbp+1140h+var_11A8], rax
0x18003472c  mov     rax, [r15+20h]
0x180034730  mov     [rbp+1140h+var_11A0], rax
0x180034734  mov     eax, [r15+10h]
0x180034738  mov     [rbp+1140h+var_1198], eax
0x18003473b  mov     eax, [r15+2Ch]
0x18003473f  mov     [rbp+1140h+var_1194], eax
0x180034742  mov     eax, [r15+28h]
0x180034746  mov     [rbp+1140h+var_1190], eax
0x180034749  mov     [rbp+1140h+var_118C], 1
0x180034750  lea     rax, [rbp+1140h+var_2E0]
0x180034757  mov     [rsp+1240h+var_1220], rax; struct __ReplLicenseClient *
0x18003475c  lea     r9, [rbp+1140h+var_1130]; struct __LicensePack *
0x180034760  mov     r8, rdi; struct _HWID *
0x180034763  lea     rdx, [rbp+1140h+var_11B0]; struct __AllocateRequest *
0x180034767  mov     rcx, rbx; struct IRdlsDBConnection *
0x18003476a  call    ?DBFindLostLicenseExact@@YAKPEAVIRdlsDBConnection@@PEAU__AllocateRequest@@PEAU_HWID@@PEAU__LicensePack@@PEAU__ReplLicenseClient@@@Z; DBFindLostLicenseExact(IRdlsDBConnection *,__AllocateRequest *,_HWID *,__LicensePack *,__ReplLicenseClient *)
0x18003476f  mov     r12d, eax
0x180034772  test    eax, eax
0x180034774  jz      short loc_1800347A1
0x180034776  mov     rcx, cs:WPP_GLOBAL_Control
0x18003477d  lea     rax, WPP_GLOBAL_Control
0x180034784  cmp     rcx, rax
0x180034787  jz      loc_180034BFC
0x18003478d  test    [rcx+1Ch], sil
0x180034791  jz      loc_180034BFC
0x180034797  mov     edx, 0Bh
0x18003479c  jmp     loc_180034BEB
0x1800347a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800347a8  lea     rax, WPP_GLOBAL_Control
0x1800347af  cmp     rcx, rax
0x1800347b2  jz      short loc_1800347CF
0x1800347b4  test    [rcx+1Ch], sil
0x1800347b8  jz      short loc_1800347CF
0x1800347ba  mov     edx, 0Ch
0x1800347bf  lea     r8, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids
0x1800347c6  mov     rcx, [rcx+10h]
0x1800347ca  call    WPP_SF_
0x1800347cf  mov     eax, [rbp+1140h+var_88]
0x1800347d5  movsxd  rcx, eax
0x1800347d8  mov     rdx, 2B6109100h
0x1800347e2  add     rcx, rdx
0x1800347e5  imul    rax, rcx, 989680h
0x1800347ec  mov     rcx, rax
0x1800347ef  shr     rcx, 20h
0x1800347f3  mov     dword ptr [rsp+1240h+var_1200+4], ecx
0x1800347f7  mov     dword ptr [rsp+1240h+var_1200], eax
0x1800347fb  mov     eax, [rbp+1140h+var_84]
0x180034801  movsxd  rcx, eax
0x180034804  add     rcx, rdx
0x180034807  imul    rax, rcx, 989680h
0x18003480e  mov     rcx, rax
0x180034811  shr     rcx, 20h
0x180034815  mov     dword ptr [rsp+1240h+var_1200+0Ch], ecx
0x180034819  mov     dword ptr [rsp+1240h+var_1200+8], eax
0x18003481d  mov     eax, [rbp+1140h+var_2DC]
0x180034823  mov     dword ptr [rsp+1240h+var_1208], eax
0x180034827  mov     eax, [rbp+1140h+var_112C]
0x18003482a  mov     dword ptr [rsp+1240h+var_1208+4], eax
0x18003482e  movzx   ecx, [rbp+1140h+var_4FA]
0x180034835  shl     ecx, 10h
0x180034838  movzx   eax, [rbp+1140h+var_4F8]
0x18003483f  or      ecx, eax
0x180034841  mov     [rbp+1140h+var_117C], ecx
0x180034844  mov     edx, 8; uBytes
0x180034849  lea     ecx, [rdx+38h]; uFlags
0x18003484c  call    cs:__imp_LocalAlloc
0x180034853  nop     dword ptr [rax+rax+00h]
0x180034858  mov     [rbp+1140h+var_1178], rax
0x18003485c  lea     rcx, [rbp+1140h+var_6FA]
0x180034863  mov     [rax], rcx
0x180034866  mov     ecx, 1
0x18003486b  mov     [rbp+1140h+var_1170], ecx
0x18003486e  lea     rax, [rbp+1140h+var_8FA]
0x180034875  mov     [rbp+1140h+var_1160], rax
0x180034879  mov     eax, [r15+28h]
0x18003487d  mov     [rbp+1140h+var_1158], eax
0x180034880  mov     eax, [rbp+1140h+var_4F4]
0x180034886  mov     [rbp+1140h+var_1154], eax
0x180034889  lea     rax, [rbp+1140h+var_2C8]
0x180034890  mov     [rbp+1140h+var_1150], rax
0x180034894  lea     rax, [rbp+1140h+var_288]
0x18003489b  mov     [rbp+1140h+var_1148], rax
0x18003489f  lea     rax, [rbp+1140h+var_1180]
0x1800348a3  mov     qword ptr [rsp+1240h+var_11E0], rax
0x1800348a8  movzx   eax, [rbp+1140h+var_8FC]
0x1800348af  mov     dword ptr [rsp+1240h+var_11E0+8], eax
0x1800348b3  mov     eax, [rbp+1140h+var_112C]
0x1800348b6  mov     dword ptr [rsp+1240h+var_11E0+0Ch], eax
0x1800348ba  mov     eax, [rbp+1140h+var_2D4]
0x1800348c0  mov     dword ptr [rsp+1240h+var_11D0], eax
0x1800348c4  mov     rbx, [rsp+1240h+var_1208]
0x1800348c9  mov     qword ptr [rsp+1240h+var_11D0+8], rbx
0x1800348ce  mov     rdi, qword ptr [rsp+1240h+var_1200]
0x1800348d3  mov     qword ptr [rbp+1140h+var_11C0], rdi
0x1800348d7  mov     rsi, qword ptr [rsp+1240h+var_1200+8]
0x1800348dc  mov     qword ptr [rbp+1140h+var_11C0+8], rsi
0x1800348e0  mov     [rsp+1240h+var_1218], ecx; int
0x1800348e4  lea     rax, [rsp+1240h+var_1210]
0x1800348e9  mov     [rsp+1240h+var_1220], rax; void **
0x1800348ee  lea     r9, [rsp+1240h+var_11E0]; void *
0x1800348f3  lea     r8d, [rcx+5]; unsigned int
0x1800348f7  mov     rdx, [r15+8]; void *
0x1800348fb  mov     rcx, [r15]; this
0x1800348fe  call    ?PMLicenseRequest@CTLSPolicy@@QEAAKPEAXKQEAXPEAPEAXH@Z; CTLSPolicy::PMLicenseRequest(void *,ulong,void * const,void * *,int)
0x180034903  mov     r12d, eax
0x180034906  test    eax, eax
0x180034908  jnz     loc_180034BFC
0x18003490e  mov     rcx, [rsp+1240h+var_1210]
0x180034913  test    rcx, rcx
0x180034916  jz      short loc_180034986
0x180034918  cmp     [rcx+8], r13
0x18003491c  jz      short loc_180034925
0x18003491e  cmp     [rcx], r13d
0x180034921  jz      short loc_18003492A
0x180034923  jmp     short loc_18003493B
0x180034925  cmp     [rcx], r13d
0x180034928  jz      short loc_18003493B
0x18003492a  and     [rcx], r13d
0x18003492d  mov     rax, [rsp+1240h+var_1210]
0x180034932  and     [rax+8], r13
0x180034936  mov     rcx, [rsp+1240h+var_1210]
0x18003493b  lea     rdx, [rcx+18h]; lpFileTime2
0x18003493f  add     rcx, 10h; lpFileTime1
0x180034943  call    cs:__imp_CompareFileTime
0x18003494a  nop     dword ptr [rax+rax+00h]
0x18003494f  test    eax, eax
0x180034951  jle     short loc_180034986
0x180034953  mov     rax, [r15]
0x180034956  lea     r9, [rax+258h]
0x18003495d  lea     r8, [rax+58h]
0x180034961  mov     r12d, 0C800000Fh
0x180034967  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x18003496e  movdqu  xmmword ptr [rsp+1240h+var_11F0.Id], xmm0
0x180034974  mov     edx, r12d; unsigned int
0x180034977  lea     rcx, [rsp+1240h+var_11F0]; struct _EVENT_DESCRIPTOR
0x18003497c  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180034981  jmp     loc_180034BFC
0x180034986  cmp     [rbp+1140h+var_8FC], 4
0x18003498d  jnz     short loc_1800349B5
0x18003498f  mov     r13d, 40080002h
0x180034995  mov     rcx, cs:WPP_GLOBAL_Control
0x18003499c  lea     rax, WPP_GLOBAL_Control
0x1800349a3  cmp     rcx, rax
0x1800349a6  jz      short loc_1800349E3
0x1800349a8  test    byte ptr [rcx+1Ch], 20h
0x1800349ac  jz      short loc_1800349E3
0x1800349ae  mov     edx, 0Dh
0x1800349b3  jmp     short loc_1800349D3
0x1800349b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800349bc  lea     rax, WPP_GLOBAL_Control
0x1800349c3  cmp     rcx, rax
0x1800349c6  jz      short loc_1800349E3
0x1800349c8  test    byte ptr [rcx+1Ch], 20h
0x1800349cc  jz      short loc_1800349E3
0x1800349ce  mov     edx, 0Eh
0x1800349d3  lea     r8, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids
0x1800349da  mov     rcx, [rcx+10h]
0x1800349de  call    WPP_SF_
0x1800349e3  xor     ecx, ecx; Time
0x1800349e5  call    cs:__imp_time
0x1800349ec  nop     dword ptr [rax+rax+00h]
0x1800349f1  mov     rcx, rax
0x1800349f4  mov     eax, [rbp+1140h+var_84]
0x1800349fa  cmp     rax, rcx
0x1800349fd  jge     short loc_180034A25
0x1800349ff  mov     r13d, 0C008000Ah
0x180034a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a0c  lea     rax, WPP_GLOBAL_Control
0x180034a13  cmp     rcx, rax
0x180034a16  jz      short loc_180034A53
0x180034a18  test    byte ptr [rcx+1Ch], 20h
0x180034a1c  jz      short loc_180034A53
0x180034a1e  mov     edx, 0Fh
0x180034a23  jmp     short loc_180034A43
0x180034a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a2c  lea     rax, WPP_GLOBAL_Control
0x180034a33  cmp     rcx, rax
0x180034a36  jz      short loc_180034A53
0x180034a38  test    byte ptr [rcx+1Ch], 20h
0x180034a3c  jz      short loc_180034A53
0x180034a3e  mov     edx, 10h
0x180034a43  lea     r8, WPP_71dc0b7eee3c376159eb9c1f83dc77c8_Traceguids
0x180034a4a  mov     rcx, [rcx+10h]
0x180034a4e  call    WPP_SF_
0x180034a53  and     qword ptr [r14+0A68h], 0
0x180034a5b  mov     eax, [rbp+1140h+var_7C]
0x180034a61  mov     [r14], eax
0x180034a64  mov     [r14+8], rbx
0x180034a68  mov     eax, [rbp+1140h+var_112C]
0x180034a6b  mov     [r14+10h], eax
0x180034a6f  mov     eax, [rbp+1140h+var_2DC]
0x180034a75  mov     [r14+14h], eax
0x180034a79  mov     eax, [rbp+1140h+var_2D4]
0x180034a7f  mov     [r14+18h], eax
0x180034a83  mov     eax, [rbp+1140h+var_78]
0x180034a89  mov     [r14+20h], eax
0x180034a8d  mov     eax, [rbp+1140h+var_74]
0x180034a93  mov     [r14+24h], eax
0x180034a97  mov     eax, [rbp+1140h+var_70]
0x180034a9d  mov     [r14+28h], eax
0x180034aa1  mov     eax, [rbp+1140h+var_6C]
0x180034aa7  mov     [r14+2Ch], eax
0x180034aab  mov     eax, [rbp+1140h+var_68]
0x180034ab1  mov     [r14+30h], eax
0x180034ab5  xor     eax, eax
0x180034ab7  cmp     [rbp+1140h+var_8FC], 4
0x180034abe  setz    al
0x180034ac1  mov     [r14+44h], eax
0x180034ac5  mov     [r14+34h], rdi
0x180034ac9  mov     [r14+3Ch], rsi
0x180034acd  movzx   ecx, [rbp+1140h+var_4FA]
0x180034ad4  shl     ecx, 10h
0x180034ad7  movzx   eax, [rbp+1140h+var_4F8]
0x180034ade  or      ecx, eax
0x180034ae0  mov     [r14+48h], ecx
0x180034ae4  lea     rcx, [r14+4Ch]; unsigned __int16 *
0x180034ae8  lea     r8, [rbp+1140h+var_8FA]; unsigned __int16 *
0x180034aef  mov     ebx, 200h
0x180034af4  mov     edx, ebx; unsigned __int64
0x180034af6  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180034afb  lea     rcx, [r14+24Ch]; unsigned __int16 *
0x180034b02  lea     r8, [rbp+1140h+var_6FA]; unsigned __int16 *
0x180034b09  mov     edx, ebx; unsigned __int64
0x180034b0b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180034b10  mov     r11, [r15+2B8h]
0x180034b17  mov     r8, [r11+8]
0x180034b1b  lea     rcx, [r14+44Ch]; unsigned __int16 *
0x180034b22  mov     r8, [r8]; unsigned __int16 *
0x180034b25  mov     edx, ebx; unsigned __int64
0x180034b27  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180034b2c  lea     rcx, [r14+64Ch]; unsigned __int16 *
0x180034b33  lea     r8, [rbp+1140h+var_288]; unsigned __int16 *
0x180034b3a  mov     edx, ebx; unsigned __int64
0x180034b3c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180034b41  lea     rcx, [r14+84Ch]; unsigned __int16 *
0x180034b48  lea     r8, [rbp+1140h+var_2C8]; unsigned __int16 *
0x180034b4f  mov     edx, ebx; unsigned __int64
0x180034b51  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180034b56  mov     r11d, [r15+28h]
0x180034b5a  mov     [r14+0A4Ch], r11d
0x180034b61  mov     eax, [r15+2Ch]
0x180034b65  mov     [r14+0A50h], eax
0x180034b6c  mov     rax, [rsp+1240h+var_1210]
0x180034b71  test    rax, rax
0x180034b74  jz      short loc_180034B7C
  ... truncated ...
```
