# TLSDBIssuePermanentLicense

- ea: `0x180032650`
- end: `0x180032dde`
- name: `TLSDBIssuePermanentLicense`
- size: `1934`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, __int64, __int64, char, ...)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018510`
- `0x180028ab4`
- `0x18005cd54`

## callees

- `0x180005665`
- `0x18000cff0`
- `0x18001ad48`
- `0x18001e2b4`
- `0x18001ebc0`
- `0x18001fdac`
- `0x180022910`
- `0x180022a6c`
- `0x180022c28`
- `0x180022d3c`
- `0x180030a20`
- `0x1800315c4`
- `0x180032264`
- `0x180032650`
- `0x180035408`
- `0x1800662a0`
- `0x18007e438`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `msvcrt!time` at `0x1800328b5`
- `msvcrt!time` at `0x180032951`
- `msvcrt!time` at `0x180032973`
- `msvcrt!time` at `0x1800328b5`
- `msvcrt!time` at `0x180032951`
- `msvcrt!time` at `0x180032973`
- `msvcrt!_wcsnicmp` at `0x18003282a`
- `msvcrt!_wcsnicmp` at `0x18003290e`
- `msvcrt!_wcsnicmp` at `0x18003282a`
- `msvcrt!_wcsnicmp` at `0x18003290e`
- `KERNEL32!CompareFileTime` at `0x180032adc`
- `KERNEL32!CompareFileTime` at `0x180032adc`
- `KERNEL32!GetCurrentThreadId` at `0x180032932`
- `KERNEL32!GetCurrentThreadId` at `0x180032932`
- `KERNEL32!SetLastError` at `0x1800327eb`
- `KERNEL32!SetLastError` at `0x1800327eb`
- `TlsBrand!RDSProductDetailsCreator` at `0x180032d3f`
- `TlsBrand!RDSProductDetailsCreator` at `0x180032d3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 TLSDBIssuePermanentLicense(__int64 a1, __int64 a2, _DWORD a3, int a4, int *a5, __int64 a6, char a7, ...)
{
  int v9; // esi
  PVOID *v10; // rcx
  unsigned int v11; // r14d
  CRdlsDBManager *v12; // rcx
  int v13; // r13d
  unsigned __int8 v14; // dl
  DWORD CurrentThreadId; // eax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // r8d
  char v19; // al
  CTLSPolicy *v20; // rcx
  unsigned __int64 v21; // rsi
  __int64 v22; // rbx
  __int64 v23; // rdi
  const FILETIME *v24; // rcx
  __int64 v25; // r9
  __int64 v26; // r8
  int v27; // eax
  _DWORD *v28; // rax
  __int64 v29; // rcx
  int v30; // ecx
  __int64 CALType; // rax
  __int64 v32; // rdx
  struct IRDSProductDetails *v33; // rax
  int v34; // edx
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned int NextLicenseId; // [rsp+40h] [rbp-C0h] BYREF
  void *v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h]
  struct _EVENT_DESCRIPTOR v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h]
  __int128 v44; // [rsp+88h] [rbp-78h] BYREF
  __int128 v45; // [rsp+98h] [rbp-68h]
  __int128 v46; // [rsp+A8h] [rbp-58h]
  _BYTE v47[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v48; // [rsp+C4h] [rbp-3Ch]
  unsigned int v49; // [rsp+C8h] [rbp-38h]
  int v50; // [rsp+CCh] [rbp-34h]
  unsigned __int16 v51[32]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v52[256]; // [rsp+118h] [rbp+18h] BYREF
  int v53; // [rsp+318h] [rbp+218h] BYREF
  int v54; // [rsp+31Ch] [rbp+21Ch] BYREF
  char v55; // [rsp+320h] [rbp+220h]
  int v56; // [rsp+324h] [rbp+224h]
  __int64 v57; // [rsp+328h] [rbp+228h]
  __int64 v58; // [rsp+330h] [rbp+230h]
  int v59; // [rsp+338h] [rbp+238h]
  _BYTE v60[4]; // [rsp+350h] [rbp+250h] BYREF
  unsigned int v61; // [rsp+354h] [rbp+254h]
  __int64 v62; // [rsp+358h] [rbp+258h]
  int v63; // [rsp+364h] [rbp+264h]
  unsigned int v64; // [rsp+36Ch] [rbp+26Ch]
  unsigned int v65; // [rsp+370h] [rbp+270h]
  char v66; // [rsp+374h] [rbp+274h]
  __int64 v67; // [rsp+378h] [rbp+278h]
  int v68; // [rsp+380h] [rbp+280h]
  unsigned __int8 v69; // [rsp+B84h] [rbp+A84h]
  unsigned __int16 v70[256]; // [rsp+B86h] [rbp+A86h] BYREF
  wchar_t String1[519]; // [rsp+D86h] [rbp+C86h] BYREF
  unsigned int v72; // [rsp+1194h] [rbp+1094h]
  unsigned __int16 v73[256]; // [rsp+11A0h] [rbp+10A0h] BYREF

  v9 = a1;
  v43 = a1;
  *(_QWORD *)&v42.Id = a5;
  v62 = 0;
  v67 = 0;
  v68 = 0;
  memset_0(v47, 0, 0x288u);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v38 = 0;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
      WPP_SF_(v10[2], 11, &WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids);
  }
  v11 = TLSDBGetPermanentLicense(v9, a2, a4, (_DWORD)a5);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids);
    goto LABEL_68;
  }
  v12 = (CRdlsDBManager *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids);
  if ( (unsigned __int8)((v66 & 0xF) - 1) > 1u || (((v69 & 0xF) - 1) & 0xFA) != 0 )
  {
    v11 = 4096;
    SetLastError(0x1000u);
    goto LABEL_68;
  }
  NextLicenseId = CRdlsDBManager::GetNextLicenseId(v12);
  v13 = _wcsnicmp(String1, L"C50", 3u);
  v40 = __PAIR64__(v61, NextLicenseId);
  v48 = NextLicenseId;
  v49 = v61;
  v50 = v63;
  if ( v13 )
  {
    v57 = *(_QWORD *)(a2 + 48);
    v58 = *(_QWORD *)(a2 + 56);
    v59 = *(_DWORD *)(a2 + 64);
  }
  else
  {
    v57 = 0;
    v58 = 0;
    v59 = 0;
  }
  v56 = *a5;
  v53 = time(0);
  StringCbCopyW(v51, 0x40u, (const unsigned __int16 *)(a2 + 84));
  StringCbCopyW(v52, 0x200u, (const unsigned __int16 *)(a2 + 118));
  if ( (a7 & 1) == 0 || _wcsnicmp(String1, L"A02", 3u) )
  {
    v14 = v69;
    goto LABEL_28;
  }
  v14 = v69;
  if ( ((v69 - 1) & 0xFA) != 0 || v69 == 6 )
  {
LABEL_28:
    if ( v13 || ((v14 - 1) & 0xFA) != 0 || v14 == 6 )
      v18 = 0x7FFFFFFF;
    else
      v18 = *(_DWORD *)&g_dwReissueLeasePU + v53;
    goto LABEL_33;
  }
  CurrentThreadId = GetCurrentThreadId();
  v16 = GenerateRandomNumber(CurrentThreadId) % *(_DWORD *)&g_dwReissueLeaseRange;
  v17 = time(0);
  v18 = v64;
  if ( *(_DWORD *)&g_dwReissueLeaseMinimum + v16 + v17 < v64 )
    v18 = *(_DWORD *)&g_dwReissueLeaseMinimum + v16 + time(0);
  v14 = v69;
LABEL_33:
  v54 = v18;
  v19 = 2;
  if ( v66 == 2 )
    v19 = 5;
  v55 = v19;
  v41 = 10000000 * (v53 + 0x2B6109100LL);
  v39 = 10000000 * (v18 + 0x2B6109100LL);
  v20 = *(CTLSPolicy **)a2;
  v21 = v40;
  v22 = v41;
  v23 = v39;
  if ( !*(_QWORD *)a2 )
    goto LABEL_37;
  DWORD2(v44) = v14;
  *(_QWORD *)&v44 = *(_QWORD *)(a2 + 704);
  HIDWORD(v44) = v61;
  LODWORD(v45) = v63;
  *((_QWORD *)&v45 + 1) = v40;
  *(_QWORD *)&v46 = 10000000 * (v53 + 0x2B6109100LL);
  *((_QWORD *)&v46 + 1) = 10000000 * (v18 + 0x2B6109100LL);
  v11 = CTLSPolicy::PMLicenseRequest(v20, *(void **)(a2 + 8), 6u, &v44, &v38, 1);
  if ( !v11 )
  {
LABEL_37:
    v24 = (const FILETIME *)v38;
    if ( !v38 )
    {
LABEL_48:
      v11 = TLSDBLicenseAdd(v43, v47);
      if ( !v11 && v13 )
      {
        *(_QWORD *)(a6 + 2664) = 0;
        *(_DWORD *)a6 = **(_DWORD **)&v42.Id;
        *(_QWORD *)(a6 + 8) = v21;
        *(_DWORD *)(a6 + 16) = v61;
        *(_DWORD *)(a6 + 20) = NextLicenseId;
        *(_DWORD *)(a6 + 24) = v63;
        v27 = v72 < v65 ? 0 : v72 - v65;
        *(_DWORD *)(a6 + 28) = v27;
        *(_OWORD *)(a6 + 32) = *(_OWORD *)(a2 + 48);
        *(_DWORD *)(a6 + 48) = *(_DWORD *)(a2 + 64);
        *(_DWORD *)(a6 + 68) = 0;
        *(_QWORD *)(a6 + 52) = v22;
        *(_QWORD *)(a6 + 60) = v23;
        *(_DWORD *)(a6 + 72) = String1[257] | (String1[256] << 16);
        StringCbCopyW((unsigned __int16 *)(a6 + 1612), 0x200u, (const unsigned __int16 *)(a2 + 118));
        StringCbCopyW((unsigned __int16 *)(a6 + 2124), 0x200u, (const unsigned __int16 *)(a2 + 84));
        StringCbCopyW((unsigned __int16 *)(a6 + 76), 0x200u, v70);
        StringCbCopyW((unsigned __int16 *)(a6 + 588), 0x200u, String1);
        StringCbCopyW(
          (unsigned __int16 *)(a6 + 1100),
          0x200u,
          **(const unsigned __int16 ***)(*(_QWORD *)(a2 + 696) + 8LL));
        *(_DWORD *)(a6 + 2636) = *(_DWORD *)(a2 + 40);
        *(_DWORD *)(a6 + 2640) = *(_DWORD *)(a2 + 44);
        v28 = v38;
        v29 = v38 ? *((_QWORD *)v38 + 1) : 0LL;
        *(_QWORD *)(a6 + 2648) = v29;
        v30 = v28 ? *v28 : 0;
        *(_DWORD *)(a6 + 2656) = v30;
        CALType = GetCALType(a6 + 588);
        if ( CALType )
        {
          v32 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(a2 + 704) + 20LL) | *(_DWORD *)(*(_QWORD *)(a2 + 704) + 24LL));
          NextLicenseId = 1;
          v11 = CanSatisfy(CALType, v32, &NextLicenseId);
          if ( v11 )
          {
            v11 = 0;
          }
          else if ( !NextLicenseId )
          {
            if ( (unsigned int)GetProductDescFromPid((wchar_t *)(a6 + 588), (unsigned __int16 *)(a6 + 76)) )
              StringCchCopyW(v73, 0x100u, (const unsigned __int16 *)(a6 + 588));
            v33 = RDSProductDetailsCreator();
            if ( v33 )
            {
              v39 = 0;
              if ( (*(int (__fastcall **)(struct IRDSProductDetails *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v33 + 16LL))(
                     v33,
                     *(unsigned int *)(*(_QWORD *)(a2 + 704) + 20LL),
                     *(unsigned int *)(*(_QWORD *)(a2 + 704) + 24LL),
                     &v39) >= 0 )
                CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,unsigned short const *,unsigned short *>(
                  (unsigned int)CrimsonHelper::s_instance,
                  v34,
                  (unsigned int)v73,
                  a6 + 2124,
                  v36,
                  v39);
            }
          }
        }
      }
      goto LABEL_68;
    }
    if ( *((_QWORD *)v38 + 1) )
    {
      if ( *(_DWORD *)v38 )
      {
LABEL_43:
        if ( CompareFileTime(v24 + 2, v24 + 3) > 0
          || !(unsigned int)FileTimeToLicenseDate((char *)v38 + 16, &v53)
          || !(unsigned int)FileTimeToLicenseDate((char *)v38 + 24, &v54) )
        {
          v25 = *(_QWORD *)a2 + 600LL;
          v26 = *(_QWORD *)a2 + 88LL;
          v11 = -939524081;
          v42 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
          TLSLogEvent(&v42, 0xC800000F, v26, v25);
          goto LABEL_68;
        }
        v22 = *((_QWORD *)v38 + 2);
        v23 = *((_QWORD *)v38 + 3);
        goto LABEL_48;
      }
    }
    else if ( !*(_DWORD *)v38 )
    {
      goto LABEL_43;
    }
    *(_DWORD *)v38 = 0;
    *((_QWORD *)v38 + 1) = 0;
    v24 = (const FILETIME *)v38;
    goto LABEL_43;
  }
LABEL_68:
  __LicensePack::~__LicensePack((__LicensePack *)v60);
  return v11;
}

```

## disassembly

```asm
0x180032650  mov     [rsp-8+arg_10], rbx
0x180032655  push    rbp
0x180032656  push    rsi
0x180032657  push    rdi
0x180032658  push    r12
0x18003265a  push    r13
0x18003265c  push    r14
0x18003265e  push    r15
0x180032660  lea     rbp, [rsp-12B0h]
0x180032668  mov     eax, 13B0h
0x18003266d  call    _alloca_probe
0x180032672  sub     rsp, rax
0x180032675  mov     rax, cs:__security_cookie
0x18003267c  xor     rax, rsp
0x18003267f  mov     [rbp+12E0h+var_40], rax
0x180032686  mov     ebx, r9d
0x180032689  mov     r12, rdx
0x18003268c  mov     rsi, rcx
0x18003268f  mov     [rbp+12E0h+var_1360], rcx
0x180032693  mov     rdi, [rbp+12E0h+arg_20]
0x18003269a  mov     qword ptr [rsp+13E0h+var_1370.Id], rdi
0x18003269f  mov     r15, [rbp+12E0h+arg_28]
0x1800326a6  xor     r13d, r13d
0x1800326a9  mov     [rbp+12E0h+var_1088], r13
0x1800326b0  mov     [rbp+12E0h+var_1068], r13
0x1800326b7  mov     [rbp+12E0h+var_1060], r13d
0x1800326be  xor     edx, edx; Val
0x1800326c0  mov     r8d, 288h; Size
0x1800326c6  lea     rcx, [rbp+12E0h+var_1320]; void *
0x1800326ca  call    memset_0
0x1800326cf  xorps   xmm0, xmm0
0x1800326d2  movups  [rbp+12E0h+var_1358], xmm0
0x1800326d6  movups  [rbp+12E0h+var_1348], xmm0
0x1800326da  movups  [rbp+12E0h+var_1338], xmm0
0x1800326de  mov     [rsp+13E0h+var_1398], r13
0x1800326e3  lea     r14, WPP_GLOBAL_Control
0x1800326ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326f1  cmp     rcx, r14
0x1800326f4  jz      short loc_180032737
0x1800326f6  test    byte ptr [rcx+1Ch], 20h
0x1800326fa  jz      short loc_180032717
0x1800326fc  lea     edx, [r13+0Ah]
0x180032700  lea     r8, WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids
0x180032707  mov     rcx, [rcx+10h]
0x18003270b  call    WPP_SF_
0x180032710  mov     rcx, cs:WPP_GLOBAL_Control
0x180032717  cmp     rcx, r14
0x18003271a  jz      short loc_180032737
0x18003271c  test    byte ptr [rcx+1Ch], 20h
0x180032720  jz      short loc_180032737
0x180032722  mov     edx, 0Bh
0x180032727  lea     r8, WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids
0x18003272e  mov     rcx, [rcx+10h]
0x180032732  call    WPP_SF_
0x180032737  mov     al, [rbp+12E0h+arg_38]
0x18003273d  mov     [rsp+13E0h+var_13B0], al
0x180032741  lea     rax, [rbp+12E0h+var_1090]
0x180032748  mov     qword ptr [rsp+13E0h+var_13B8], rax
0x18003274d  mov     r9, rdi
0x180032750  mov     r8d, ebx
0x180032753  mov     rdx, r12
0x180032756  mov     rcx, rsi
0x180032759  call    TLSDBGetPermanentLicense
0x18003275e  mov     r14d, eax
0x180032761  test    eax, eax
0x180032763  jz      short loc_1800327A0
0x180032765  mov     rcx, cs:WPP_GLOBAL_Control
0x18003276c  lea     rax, WPP_GLOBAL_Control
0x180032773  cmp     rcx, rax
0x180032776  jz      loc_180032DA4
0x18003277c  test    byte ptr [rcx+1Ch], 20h
0x180032780  jz      loc_180032DA4
0x180032786  mov     edx, 0Ch
0x18003278b  lea     r8, WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids
0x180032792  mov     rcx, [rcx+10h]
0x180032796  call    WPP_SF_
0x18003279b  jmp     loc_180032DA4
0x1800327a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327a7  lea     rax, WPP_GLOBAL_Control
0x1800327ae  cmp     rcx, rax
0x1800327b1  jz      short loc_1800327CE
0x1800327b3  test    byte ptr [rcx+1Ch], 20h
0x1800327b7  jz      short loc_1800327CE
0x1800327b9  mov     edx, 0Dh
0x1800327be  lea     r8, WPP_baaf41334b5d3337294d2cb7944a7947_Traceguids
0x1800327c5  mov     rcx, [rcx+10h]
0x1800327c9  call    WPP_SF_
0x1800327ce  mov     al, [rbp+12E0h+var_106C]
0x1800327d4  and     al, 0Fh
0x1800327d6  mov     esi, 1
0x1800327db  sub     al, sil
0x1800327de  cmp     al, sil
0x1800327e1  jbe     short loc_1800327FC
0x1800327e3  mov     ecx, 1000h; dwErrCode
0x1800327e8  mov     r14d, ecx
0x1800327eb  call    cs:__imp_SetLastError
0x1800327f2  nop     dword ptr [rax+rax+00h]
0x1800327f7  jmp     loc_180032DA4
0x1800327fc  mov     al, [rbp+12E0h+var_85C]
0x180032802  and     al, 0Fh
0x180032804  sub     al, sil
0x180032807  test    al, 0FAh
0x180032809  jnz     short loc_1800327E3
0x18003280b  call    ?GetNextLicenseId@CRdlsDBManager@@QEAAKXZ; CRdlsDBManager::GetNextLicenseId(void)
0x180032810  mov     ebx, eax
0x180032812  mov     [rsp+13E0h+var_13A0], eax
0x180032816  mov     r8d, 3; MaxCount
0x18003281c  lea     rdx, aC50; "C50"
0x180032823  lea     rcx, [rbp+12E0h+String1]; String1
0x18003282a  call    cs:__imp__wcsnicmp
0x180032831  nop     dword ptr [rax+rax+00h]
0x180032836  mov     r13d, eax
0x180032839  mov     dword ptr [rsp+13E0h+var_1388], ebx
0x18003283d  mov     ecx, [rbp+12E0h+var_108C]
0x180032843  mov     dword ptr [rsp+13E0h+var_1388+4], ecx
0x180032847  mov     [rbp+12E0h+var_131C], ebx
0x18003284a  mov     [rbp+12E0h+var_1318], ecx
0x18003284d  mov     ecx, [rbp+12E0h+var_107C]
0x180032853  mov     [rbp+12E0h+var_1314], ecx
0x180032856  xor     r14d, r14d
0x180032859  test    eax, eax
0x18003285b  jz      short loc_180032896
0x18003285d  mov     ecx, [r12+30h]
0x180032862  mov     dword ptr [rbp+12E0h+var_10B8], ecx
0x180032868  mov     ecx, [r12+34h]
0x18003286d  mov     dword ptr [rbp+12E0h+var_10B8+4], ecx
0x180032873  mov     eax, [r12+38h]
0x180032878  mov     dword ptr [rbp+12E0h+var_10B0], eax
0x18003287e  mov     eax, [r12+3Ch]
0x180032883  mov     dword ptr [rbp+12E0h+var_10B0+4], eax
0x180032889  mov     eax, [r12+40h]
0x18003288e  mov     [rbp+12E0h+var_10A8], eax
0x180032894  jmp     short loc_1800328AB
0x180032896  mov     [rbp+12E0h+var_10B8], r14
0x18003289d  mov     [rbp+12E0h+var_10B0], r14
0x1800328a4  mov     [rbp+12E0h+var_10A8], r14d
0x1800328ab  mov     eax, [rdi]
0x1800328ad  mov     [rbp+12E0h+var_10BC], eax
0x1800328b3  xor     ecx, ecx; Time
0x1800328b5  call    cs:__imp_time
0x1800328bc  nop     dword ptr [rax+rax+00h]
0x1800328c1  mov     [rbp+12E0h+var_10C8], eax
0x1800328c7  lea     r8, [r12+54h]; unsigned __int16 *
0x1800328cc  mov     edx, 40h ; '@'; unsigned __int64
0x1800328d1  lea     rcx, [rbp+12E0h+var_1308]; unsigned __int16 *
0x1800328d5  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800328da  lea     r8, [r12+76h]; unsigned __int16 *
0x1800328df  mov     edx, 200h; unsigned __int64
0x1800328e4  lea     rcx, [rbp+12E0h+var_12C8]; unsigned __int16 *
0x1800328e8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800328ed  test    [rbp+12E0h+arg_30], sil
0x1800328f4  jz      loc_180032992
0x1800328fa  mov     r8d, 3; MaxCount
0x180032900  lea     rdx, aA02; "A02"
0x180032907  lea     rcx, [rbp+12E0h+String1]; String1
0x18003290e  call    cs:__imp__wcsnicmp
0x180032915  nop     dword ptr [rax+rax+00h]
0x18003291a  test    eax, eax
0x18003291c  jnz     short loc_180032992
0x18003291e  mov     dl, [rbp+12E0h+var_85C]
0x180032924  mov     al, dl
0x180032926  sub     al, sil
0x180032929  test    al, 0FAh
0x18003292b  jnz     short loc_180032998
0x18003292d  cmp     dl, 6
0x180032930  jz      short loc_180032998
0x180032932  call    cs:__imp_GetCurrentThreadId
0x180032939  nop     dword ptr [rax+rax+00h]
0x18003293e  mov     ecx, eax; unsigned int
0x180032940  call    ?GenerateRandomNumber@@YAKK@Z; GenerateRandomNumber(ulong)
0x180032945  xor     edx, edx
0x180032947  div     cs:?g_dwReissueLeaseRange@@3KA; ulong g_dwReissueLeaseRange
0x18003294d  mov     ebx, edx
0x18003294f  xor     ecx, ecx; Time
0x180032951  call    cs:__imp_time
0x180032958  nop     dword ptr [rax+rax+00h]
0x18003295d  add     eax, ebx
0x18003295f  add     eax, cs:?g_dwReissueLeaseMinimum@@3KA; ulong g_dwReissueLeaseMinimum
0x180032965  mov     r8d, [rbp+12E0h+var_1074]
0x18003296c  cmp     eax, r8d
0x18003296f  jnb     short loc_18003298A
0x180032971  xor     ecx, ecx; Time
0x180032973  call    cs:__imp_time
0x18003297a  nop     dword ptr [rax+rax+00h]
0x18003297f  lea     r8d, [rbx+rax]
0x180032983  add     r8d, cs:?g_dwReissueLeaseMinimum@@3KA; ulong g_dwReissueLeaseMinimum
0x18003298a  mov     dl, [rbp+12E0h+var_85C]
0x180032990  jmp     short loc_1800329C1
0x180032992  mov     dl, [rbp+12E0h+var_85C]
0x180032998  test    r13d, r13d
0x18003299b  jnz     short loc_1800329BB
0x18003299d  mov     al, dl
0x18003299f  sub     al, sil
0x1800329a2  test    al, 0FAh
0x1800329a4  jnz     short loc_1800329BB
0x1800329a6  cmp     dl, 6
0x1800329a9  jz      short loc_1800329BB
0x1800329ab  mov     r8d, [rbp+12E0h+var_10C8]
0x1800329b2  add     r8d, cs:?g_dwReissueLeasePU@@3KA; ulong g_dwReissueLeasePU
0x1800329b9  jmp     short loc_1800329C1
0x1800329bb  mov     r8d, 7FFFFFFFh
0x1800329c1  mov     [rbp+12E0h+var_10C4], r8d
0x1800329c8  mov     eax, 2
0x1800329cd  lea     ecx, [rax+3]
0x1800329d0  cmp     [rbp+12E0h+var_106C], al
0x1800329d6  cmovz   eax, ecx
0x1800329d9  mov     [rbp+12E0h+var_10C0], al
0x1800329df  mov     eax, [rbp+12E0h+var_10C8]
0x1800329e5  movsxd  rcx, eax
0x1800329e8  mov     r9, 2B6109100h
0x1800329f2  add     rcx, r9
0x1800329f5  imul    rax, rcx, 989680h
0x1800329fc  mov     rcx, rax
0x1800329ff  shr     rcx, 20h
0x180032a03  mov     dword ptr [rsp+13E0h+var_1380+4], ecx
0x180032a07  mov     dword ptr [rsp+13E0h+var_1380], eax
0x180032a0b  movsxd  rax, r8d
0x180032a0e  add     rax, r9
0x180032a11  imul    rax, 989680h
0x180032a18  mov     rcx, rax
0x180032a1b  shr     rcx, 20h
0x180032a1f  mov     dword ptr [rsp+13E0h+var_1390+4], ecx
0x180032a23  mov     dword ptr [rsp+13E0h+var_1390], eax
0x180032a27  mov     rcx, [r12]; this
0x180032a2b  mov     rsi, [rsp+13E0h+var_1388]
0x180032a30  mov     rbx, [rsp+13E0h+var_1380]
0x180032a35  mov     rdi, [rsp+13E0h+var_1390]
0x180032a3a  test    rcx, rcx
0x180032a3d  jz      short loc_180032AA3
0x180032a3f  movzx   eax, dl
0x180032a42  mov     dword ptr [rbp+12E0h+var_1358+8], eax
0x180032a45  mov     rax, [r12+2C0h]
0x180032a4d  mov     qword ptr [rbp+12E0h+var_1358], rax
0x180032a51  mov     eax, [rbp+12E0h+var_108C]
0x180032a57  mov     dword ptr [rbp+12E0h+var_1358+0Ch], eax
0x180032a5a  mov     eax, [rbp+12E0h+var_107C]
0x180032a60  mov     dword ptr [rbp+12E0h+var_1348], eax
0x180032a63  mov     qword ptr [rbp+12E0h+var_1348+8], rsi
0x180032a67  mov     qword ptr [rbp+12E0h+var_1338], rbx
0x180032a6b  mov     qword ptr [rbp+12E0h+var_1338+8], rdi
0x180032a6f  mov     [rsp+13E0h+var_13B8], 1; int
0x180032a77  lea     rax, [rsp+13E0h+var_1398]
0x180032a7c  mov     [rsp+13E0h+var_13C0], rax; void **
0x180032a81  lea     r9, [rbp+12E0h+var_1358]; void *
0x180032a85  mov     r8d, 6; unsigned int
0x180032a8b  mov     rdx, [r12+8]; void *
0x180032a90  call    ?PMLicenseRequest@CTLSPolicy@@QEAAKPEAXKQEAXPEAPEAXH@Z; CTLSPolicy::PMLicenseRequest(void *,ulong,void * const,void * *,int)
0x180032a95  mov     r14d, eax
0x180032a98  test    eax, eax
0x180032a9a  jnz     loc_180032DA4
0x180032aa0  xor     r14d, r14d
0x180032aa3  mov     rcx, [rsp+13E0h+var_1398]
0x180032aa8  test    rcx, rcx
0x180032aab  jz      loc_180032B5E
0x180032ab1  cmp     [rcx+8], r14
0x180032ab5  jz      short loc_180032ABE
0x180032ab7  cmp     [rcx], r14d
0x180032aba  jz      short loc_180032AC3
0x180032abc  jmp     short loc_180032AD4
0x180032abe  cmp     [rcx], r14d
0x180032ac1  jz      short loc_180032AD4
0x180032ac3  mov     [rcx], r14d
0x180032ac6  mov     rax, [rsp+13E0h+var_1398]
0x180032acb  mov     [rax+8], r14
0x180032acf  mov     rcx, [rsp+13E0h+var_1398]
0x180032ad4  lea     rdx, [rcx+18h]; lpFileTime2
0x180032ad8  add     rcx, 10h; lpFileTime1
0x180032adc  call    cs:__imp_CompareFileTime
0x180032ae3  nop     dword ptr [rax+rax+00h]
0x180032ae8  test    eax, eax
0x180032aea  jle     short loc_180032B1F
0x180032aec  mov     rax, [r12]
0x180032af0  lea     r9, [rax+258h]
0x180032af7  lea     r8, [rax+58h]
0x180032afb  mov     edx, 0C800000Fh; unsigned int
0x180032b00  mov     r14d, edx
0x180032b03  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x180032b0a  movdqu  xmmword ptr [rsp+13E0h+var_1370.Id], xmm0
0x180032b10  lea     rcx, [rsp+13E0h+var_1370]; struct _EVENT_DESCRIPTOR
0x180032b15  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180032b1a  jmp     loc_180032DA4
0x180032b1f  mov     rcx, [rsp+13E0h+var_1398]
0x180032b24  add     rcx, 10h
0x180032b28  lea     rdx, [rbp+12E0h+var_10C8]
0x180032b2f  call    FileTimeToLicenseDate
0x180032b34  test    eax, eax
0x180032b36  jz      short loc_180032AEC
0x180032b38  mov     rcx, [rsp+13E0h+var_1398]
0x180032b3d  add     rcx, 18h
0x180032b41  lea     rdx, [rbp+12E0h+var_10C4]
0x180032b48  call    FileTimeToLicenseDate
0x180032b4d  test    eax, eax
0x180032b4f  jz      short loc_180032AEC
0x180032b51  mov     rdi, [rsp+13E0h+var_1398]
0x180032b56  mov     rbx, [rdi+10h]
0x180032b5a  mov     rdi, [rdi+18h]
0x180032b5e  lea     rdx, [rbp+12E0h+var_1320]
0x180032b62  mov     rcx, [rbp+12E0h+var_1360]
0x180032b66  call    TLSDBLicenseAdd
0x180032b6b  mov     r14d, eax
  ... truncated ...
```
