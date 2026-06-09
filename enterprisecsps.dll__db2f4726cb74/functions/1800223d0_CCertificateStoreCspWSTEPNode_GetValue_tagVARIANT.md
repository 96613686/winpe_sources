# CCertificateStoreCspWSTEPNode::GetValue(tagVARIANT *)

- ea: `0x1800223d0`
- end: `0x1800228d3`
- name: `?GetValue@CCertificateStoreCspWSTEPNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1283`
- prototype: `int(CCertificateStoreCspWSTEPNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x18001a114`
- `0x18001a4d4`
- `0x18002201c`
- `0x1800223d0`
- `0x180022e10`
- `0x180036b00`
- `0x1800ce1fc`
- `0x1800ce344`
- `0x1800ce5f8`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022534`
- `OLEAUT32!__imp_SysAllocString` at `0x180022655`
- `OLEAUT32!__imp_SysAllocString` at `0x180022534`
- `OLEAUT32!__imp_SysAllocString` at `0x180022655`
- `OLEAUT32!__imp_SysFreeString` at `0x180022861`
- `OLEAUT32!__imp_SysFreeString` at `0x18002288f`
- `OLEAUT32!__imp_SysFreeString` at `0x180022861`
- `OLEAUT32!__imp_SysFreeString` at `0x18002288f`
- `OLEAUT32!__imp_VariantInit` at `0x18002244f`
- `OLEAUT32!__imp_VariantInit` at `0x1800224c7`
- `OLEAUT32!__imp_VariantInit` at `0x18002244f`
- `OLEAUT32!__imp_VariantInit` at `0x1800224c7`
- `OLEAUT32!__imp_VariantClear` at `0x180022852`
- `OLEAUT32!__imp_VariantClear` at `0x180022852`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18002278a`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18002278a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022880`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022880`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002275e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002275e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022496`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022496`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800227bc`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800227f6`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800227bc`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800227f6`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180022635`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18002269d`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180022635`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18002269d`

## string_xrefs

- `0x180022623`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall CCertificateStoreCspWSTEPNode::GetValue(CCertificateStoreCspWSTEPNode *this, struct tagVARIANT *a2)
{
  struct CConfigServiceProvider2Impl *v3; // rcx
  OLECHAR *v4; // r15
  const unsigned __int16 *EnrollmentId2; // rax
  unsigned __int16 *v7; // rbx
  signed int String; // edi
  const WCHAR *v9; // rax
  LSTATUS v10; // eax
  HKEY v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  bool v15; // zf
  unsigned int v16; // eax
  BSTR v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  int RenewPeriodInSeconds; // eax
  signed int v25; // eax
  OLECHAR *v26; // rcx
  BSTR v27; // rax
  LSTATUS ValueW; // eax
  signed int v29; // eax
  LONG v30; // eax
  signed int DWORD; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  LONG v34; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v40[48]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR psz[264]; // [rsp+F0h] [rbp-10h] BYREF

  v3 = (struct CConfigServiceProvider2Impl *)*((_QWORD *)this + 16);
  v4 = 0;
  v36 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v37 = 0;
  v34 = 0;
  pcbData = 0;
  EnrollmentId2 = GetEnrollmentId2(v3);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)lpSubKey, EnrollmentId2);
  hkey = 0;
  VariantInit(&pvarg);
  v7 = (unsigned __int16 *)lpSubKey[0];
  if ( a2 )
  {
    v9 = (const WCHAR *)DMGetKnownRegPath(1);
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x2001Fu, &hkey);
    String = v10;
    if ( v10 > 0 )
      String = (unsigned __int16)v10 | 0x80070000;
    if ( String < 0 )
    {
      v11 = hkey;
      hkey = 0;
      goto LABEL_65;
    }
    VariantInit(a2);
    v40[0] = 0;
    psz[0] = 0;
    v12 = *((_DWORD *)this + 11);
    if ( v12 > 0x13 )
    {
      v18 = v12 - 20;
      if ( v18 )
      {
        v16 = v18 - 3;
        v15 = v16 == 0;
        goto LABEL_12;
      }
    }
    else if ( v12 != 19 )
    {
      v13 = v12 - 13;
      if ( v13 )
      {
        v14 = v13 - 2;
        if ( v14 )
        {
          v16 = v14 - 1;
          v15 = v16 == 0;
LABEL_12:
          if ( !v15 && v16 - 1 > 1 )
            goto LABEL_24;
        }
      }
    }
    String = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 48LL))(
               *((_QWORD *)this + 2),
               &v36);
    if ( String < 0 )
      goto LABEL_64;
    v17 = SysAllocString(L"OMADM::ServerID");
    v4 = v17;
    if ( !v17 )
    {
LABEL_16:
      String = -2147024882;
      goto LABEL_64;
    }
    String = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v36 + 32LL))(v36, v17, &pvarg);
    if ( String < 0 )
      goto LABEL_64;
    if ( pvarg.vt != 8 )
      goto LABEL_63;
    String = StringCchLengthW(pvarg.bstrVal, 0x7FFFFFFFu, &v37);
    if ( String < 0 )
      goto LABEL_64;
    if ( !v37 )
    {
      String = -2046820335;
      goto LABEL_64;
    }
LABEL_24:
    v19 = *((_DWORD *)this + 11);
    if ( v19 <= 0x11 )
    {
      if ( v19 != 17 )
      {
        v20 = v19 - 12;
        if ( !v20 )
          goto LABEL_64;
        v21 = v20 - 1;
        if ( !v21 )
        {
          String = OmaDmRegistryGetString(hkey, v7, L"DMPCertThumbPrint", v40, 0x2Au);
          if ( String < 0 )
            goto LABEL_64;
          v26 = v40;
LABEL_35:
          v27 = SysAllocString(v26);
          a2->llVal = (LONGLONG)v27;
          if ( v27 )
          {
            a2->vt = 8;
            goto LABEL_64;
          }
          goto LABEL_16;
        }
        v22 = v21 - 1;
        if ( !v22 )
          goto LABEL_64;
        v23 = v22 - 1;
        if ( v23 )
        {
          if ( v23 == 1 )
          {
            pcbData = 0;
            RenewPeriodInSeconds = GetRenewPeriodInSeconds(v7, &pcbData);
LABEL_46:
            String = RenewPeriodInSeconds;
            if ( RenewPeriodInSeconds < 0 )
              goto LABEL_64;
            a2->lVal = pcbData / 0x15180;
LABEL_60:
            a2->vt = 3;
            goto LABEL_64;
          }
LABEL_63:
          String = -2147418113;
          goto LABEL_64;
        }
        v25 = OmaDmRegistryGetString(hkey, v7, L"DiscoveryServiceFullURL", psz, 0x101u);
        String = v25;
        if ( v25 != -2147024894 && v25 != -2147023267 )
        {
          v26 = psz;
          goto LABEL_35;
        }
LABEL_37:
        String = -2046820350;
        goto LABEL_64;
      }
LABEL_45:
      pcbData = 0;
      RenewPeriodInSeconds = GetRenewRetryIntervalInSeconds(v7, v19 == 17, &pcbData);
      goto LABEL_46;
    }
    switch ( v19 )
    {
      case 0x12u:
        String = IsROBOMode(v7, (int *)&pcbData);
        if ( String >= 0 )
        {
          a2->lVal = pcbData;
          a2->vt = 11;
        }
        goto LABEL_64;
      case 0x13u:
        DWORD = OmaDmRegistryGetDWORD(hkey, v7, L"RenewStatus", (unsigned int *)&v34);
        String = DWORD;
        if ( DWORD == -2147024894 || DWORD == -2147023267 )
          goto LABEL_37;
        break;
      case 0x14u:
        v29 = OmaDmRegistryGetDWORD(hkey, v7, L"RenewErrorCode", (unsigned int *)&v34);
        String = v29;
        if ( v29 == -2147024894 || v29 == -2147023267 )
        {
          v30 = 0;
          v34 = 0;
          String = 0;
LABEL_59:
          a2->lVal = v30;
          goto LABEL_60;
        }
        break;
      case 0x18u:
        pcbData = 16;
        *(_OWORD *)lpSubKey = 0;
        ValueW = RegGetValueW(hkey, v7, L"RenewTimestamp", 8u, 0, lpSubKey, &pcbData);
        String = ValueW;
        if ( ValueW > 0 )
          String = (unsigned __int16)ValueW | 0x80070000;
        if ( String < 0 )
          goto LABEL_64;
        if ( SystemTimeToVariantTime((LPSYSTEMTIME)lpSubKey, &a2->dblVal) )
        {
          a2->vt = 7;
          goto LABEL_64;
        }
        goto LABEL_2;
      case 0x19u:
        goto LABEL_45;
      default:
        goto LABEL_63;
    }
    v30 = v34;
    goto LABEL_59;
  }
LABEL_2:
  String = -2147024809;
LABEL_64:
  VariantClear(&pvarg);
  SysFreeString(v4);
  v11 = hkey;
  hkey = 0;
LABEL_65:
  if ( v11 )
    RegCloseKey(v11);
  SysFreeString(v7);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v36);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800223d0  mov     [rsp-8+arg_10], rbx
0x1800223d5  mov     [rsp-8+arg_18], rsi
0x1800223da  push    rbp
0x1800223db  push    rdi
0x1800223dc  push    r13
0x1800223de  push    r14
0x1800223e0  push    r15
0x1800223e2  lea     rbp, [rsp-210h]
0x1800223ea  sub     rsp, 310h
0x1800223f1  mov     rax, cs:__security_cookie
0x1800223f8  xor     rax, rsp
0x1800223fb  mov     [rbp+230h+var_30], rax
0x180022402  xor     eax, eax
0x180022404  mov     r14, rcx
0x180022407  mov     rcx, [rcx+80h]; struct CConfigServiceProvider2Impl *
0x18002240e  xorps   xmm0, xmm0
0x180022411  xor     r15d, r15d
0x180022414  mov     qword ptr [rsp+330h+pvarg+10h], rax
0x180022419  mov     [rsp+330h+var_2E0], r15
0x18002241e  mov     rsi, rdx
0x180022421  movups  xmmword ptr [rsp+330h+pvarg], xmm0
0x180022426  mov     [rsp+330h+var_2D8], rax
0x18002242b  mov     [rsp+330h+var_2EC], eax
0x18002242f  mov     [rsp+330h+var_2F0], eax
0x180022433  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180022438  mov     rdx, rax; unsigned __int16 *
0x18002243b  lea     rcx, [rsp+330h+lpSubKey]; this
0x180022440  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180022445  lea     rcx, [rsp+330h+pvarg]; pvarg
0x18002244a  mov     [rsp+330h+hkey], r15
0x18002244f  call    cs:__imp_VariantInit
0x180022456  nop     dword ptr [rax+rax+00h]
0x18002245b  mov     rbx, [rsp+330h+lpSubKey]
0x180022460  test    rsi, rsi
0x180022463  jnz     short loc_18002246F
0x180022465  mov     edi, 80070057h
0x18002246a  jmp     loc_18002284D
0x18002246f  mov     ecx, 1
0x180022474  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180022479  lea     rcx, [rsp+330h+hkey]
0x18002247e  mov     r9d, 2001Fh; samDesired
0x180022484  mov     [rsp+330h+phkResult], rcx; phkResult
0x180022489  xor     r8d, r8d; ulOptions
0x18002248c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022493  mov     rdx, rax; lpSubKey
0x180022496  call    cs:__imp_RegOpenKeyExW
0x18002249d  nop     dword ptr [rax+rax+00h]
0x1800224a2  mov     edi, eax
0x1800224a4  test    eax, eax
0x1800224a6  jle     short loc_1800224B1
0x1800224a8  movzx   edi, ax
0x1800224ab  or      edi, 80070000h
0x1800224b1  test    edi, edi
0x1800224b3  jns     short loc_1800224C4
0x1800224b5  mov     rcx, [rsp+330h+hkey]
0x1800224ba  mov     [rsp+330h+hkey], r15
0x1800224bf  jmp     loc_18002287B
0x1800224c4  mov     rcx, rsi; pvarg
0x1800224c7  call    cs:__imp_VariantInit
0x1800224ce  nop     dword ptr [rax+rax+00h]
0x1800224d3  xor     eax, eax
0x1800224d5  mov     edx, 8
0x1800224da  mov     [rbp+230h+var_2A0], ax
0x1800224de  mov     [rbp+230h+psz], ax
0x1800224e2  mov     eax, [r14+2Ch]
0x1800224e6  lea     r13d, [rdx-5]
0x1800224ea  cmp     eax, 13h
0x1800224ed  ja      short loc_180022552
0x1800224ef  jz      short loc_18002250E
0x1800224f1  sub     eax, 0Dh
0x1800224f4  jz      short loc_18002250E
0x1800224f6  sub     eax, 2
0x1800224f9  jz      short loc_18002250E
0x1800224fb  sub     eax, 1
0x1800224fe  jz      short loc_18002250E
0x180022500  sub     eax, 1
0x180022503  jz      short loc_18002250E
0x180022505  cmp     eax, 1
0x180022508  jnz     loc_1800225C4
0x18002250e  mov     rcx, [r14+10h]
0x180022512  lea     rdx, [rsp+330h+var_2E0]
0x180022517  mov     rax, [rcx]
0x18002251a  mov     rax, [rax+30h]
0x18002251e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022523  mov     edi, eax
0x180022525  test    eax, eax
0x180022527  js      loc_18002284D
0x18002252d  lea     rcx, aOmadmServerid; "OMADM::ServerID"
0x180022534  call    cs:__imp_SysAllocString
0x18002253b  nop     dword ptr [rax+rax+00h]
0x180022540  mov     r15, rax
0x180022543  test    rax, rax
0x180022546  jnz     short loc_18002255C
0x180022548  mov     edi, 8007000Eh
0x18002254d  jmp     loc_18002284D
0x180022552  sub     eax, 14h
0x180022555  jz      short loc_18002250E
0x180022557  sub     eax, r13d
0x18002255a  jmp     short loc_1800224FE
0x18002255c  mov     rcx, [rsp+330h+var_2E0]
0x180022561  lea     r8, [rsp+330h+pvarg]
0x180022566  mov     rdx, r15
0x180022569  mov     rax, [rcx]
0x18002256c  mov     rax, [rax+20h]
0x180022570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022575  mov     edi, eax
0x180022577  test    eax, eax
0x180022579  js      loc_18002284D
0x18002257f  mov     eax, 8
0x180022584  cmp     ax, word ptr [rsp+330h+pvarg]
0x180022589  jnz     loc_180022848
0x18002258f  mov     rcx, qword ptr [rsp+330h+pvarg+8]; unsigned __int16 *
0x180022594  lea     r8, [rsp+330h+var_2D8]; unsigned __int64 *
0x180022599  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002259e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800225a3  mov     edi, eax
0x1800225a5  test    eax, eax
0x1800225a7  js      loc_18002284D
0x1800225ad  cmp     [rsp+330h+var_2D8], 0
0x1800225b3  jnz     short loc_1800225BF
0x1800225b5  mov     edi, 86000011h
0x1800225ba  jmp     loc_18002284D
0x1800225bf  mov     edx, 8
0x1800225c4  mov     eax, [r14+2Ch]
0x1800225c8  cmp     eax, 11h
0x1800225cb  ja      loc_1800226B9
0x1800225d1  jz      loc_1800226E4
0x1800225d7  sub     eax, 0Ch
0x1800225da  jz      loc_18002284D
0x1800225e0  sub     eax, 1
0x1800225e3  jz      loc_180022682
0x1800225e9  sub     eax, 1
0x1800225ec  jz      loc_18002284D
0x1800225f2  sub     eax, 1
0x1800225f5  jz      short loc_18002261A
0x1800225f7  cmp     eax, 1
0x1800225fa  jnz     loc_180022848
0x180022600  lea     rdx, [rsp+330h+var_2F0]; unsigned int *
0x180022605  mov     [rsp+330h+var_2F0], 0
0x18002260d  mov     rcx, rbx; unsigned __int16 *
0x180022610  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x180022615  jmp     loc_180022701
0x18002261a  mov     rcx, [rsp+330h+hkey]
0x18002261f  lea     r9, [rbp+230h+psz]
0x180022623  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18002262a  mov     dword ptr [rsp+330h+phkResult], 101h
0x180022632  mov     rdx, rbx
0x180022635  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18002263c  nop     dword ptr [rax+rax+00h]
0x180022641  mov     edi, eax
0x180022643  cmp     eax, 80070002h
0x180022648  jz      short loc_180022678
0x18002264a  cmp     eax, 8007065Dh
0x18002264f  jz      short loc_180022678
0x180022651  lea     rcx, [rbp+230h+psz]; psz
0x180022655  call    cs:__imp_SysAllocString
0x18002265c  nop     dword ptr [rax+rax+00h]
0x180022661  mov     [rsi+8], rax
0x180022665  test    rax, rax
0x180022668  jz      loc_180022548
0x18002266e  mov     word ptr [rsi], 8
0x180022673  jmp     loc_18002284D
0x180022678  mov     edi, 86000002h
0x18002267d  jmp     loc_18002284D
0x180022682  mov     rcx, [rsp+330h+hkey]
0x180022687  lea     r9, [rbp+230h+var_2A0]
0x18002268b  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180022692  mov     dword ptr [rsp+330h+phkResult], 2Ah ; '*'
0x18002269a  mov     rdx, rbx
0x18002269d  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x1800226a4  nop     dword ptr [rax+rax+00h]
0x1800226a9  mov     edi, eax
0x1800226ab  test    eax, eax
0x1800226ad  js      loc_18002284D
0x1800226b3  lea     rcx, [rbp+230h+var_2A0]
0x1800226b7  jmp     short loc_180022655
0x1800226b9  mov     ecx, eax
0x1800226bb  sub     ecx, 12h
0x1800226be  jz      loc_180022827
0x1800226c4  sub     ecx, 1
0x1800226c7  jz      loc_1800227E2
0x1800226cd  sub     ecx, 1
0x1800226d0  jz      loc_1800227A8
0x1800226d6  sub     ecx, 4
0x1800226d9  jz      short loc_18002271F
0x1800226db  cmp     ecx, 1
0x1800226de  jnz     loc_180022848
0x1800226e4  xor     edx, edx
0x1800226e6  mov     [rsp+330h+var_2F0], 0
0x1800226ee  cmp     eax, 11h
0x1800226f1  lea     r8, [rsp+330h+var_2F0]; unsigned int *
0x1800226f6  mov     rcx, rbx; unsigned __int16 *
0x1800226f9  setz    dl; int
0x1800226fc  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x180022701  mov     edi, eax
0x180022703  test    eax, eax
0x180022705  js      loc_18002284D
0x18002270b  mov     eax, 0C22E4507h
0x180022710  mul     [rsp+330h+var_2F0]
0x180022714  shr     edx, 10h
0x180022717  mov     [rsi+8], edx
0x18002271a  jmp     loc_180022821
0x18002271f  mov     rcx, [rsp+330h+hkey]; hkey
0x180022724  lea     rax, [rsp+330h+var_2F0]
0x180022729  mov     [rsp+330h+pcbData], rax; pcbData
0x18002272e  lea     r8, Value; "RenewTimestamp"
0x180022735  lea     rax, [rsp+330h+lpSubKey]
0x18002273a  mov     [rsp+330h+var_2F0], 10h
0x180022742  xorps   xmm0, xmm0
0x180022745  mov     [rsp+330h+pvData], rax; pvData
0x18002274a  mov     r9d, edx; dwFlags
0x18002274d  mov     [rsp+330h+phkResult], 0; pdwType
0x180022756  mov     rdx, rbx; lpSubKey
0x180022759  movups  xmmword ptr [rsp+330h+lpSubKey], xmm0
0x18002275e  call    cs:__imp_RegGetValueW
0x180022765  nop     dword ptr [rax+rax+00h]
0x18002276a  mov     edi, eax
0x18002276c  test    eax, eax
0x18002276e  jle     short loc_180022779
0x180022770  movzx   edi, ax
0x180022773  or      edi, 80070000h
0x180022779  test    edi, edi
0x18002277b  js      loc_18002284D
0x180022781  lea     rdx, [rsi+8]; pvtime
0x180022785  lea     rcx, [rsp+330h+lpSubKey]; lpSystemTime
0x18002278a  call    cs:__imp_SystemTimeToVariantTime
0x180022791  nop     dword ptr [rax+rax+00h]
0x180022796  test    eax, eax
0x180022798  jz      loc_180022465
0x18002279e  mov     word ptr [rsi], 7
0x1800227a3  jmp     loc_18002284D
0x1800227a8  mov     rcx, [rsp+330h+hkey]
0x1800227ad  lea     r9, [rsp+330h+var_2EC]
0x1800227b2  lea     r8, aRenewerrorcode; "RenewErrorCode"
0x1800227b9  mov     rdx, rbx
0x1800227bc  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800227c3  nop     dword ptr [rax+rax+00h]
0x1800227c8  mov     edi, eax
0x1800227ca  cmp     eax, 80070002h
0x1800227cf  jz      short loc_1800227D8
0x1800227d1  cmp     eax, 8007065Dh
0x1800227d6  jnz     short loc_18002281A
0x1800227d8  xor     eax, eax
0x1800227da  mov     [rsp+330h+var_2EC], eax
0x1800227de  xor     edi, edi
0x1800227e0  jmp     short loc_18002281E
0x1800227e2  mov     rcx, [rsp+330h+hkey]
0x1800227e7  lea     r9, [rsp+330h+var_2EC]
0x1800227ec  lea     r8, aRenewstatus; "RenewStatus"
0x1800227f3  mov     rdx, rbx
0x1800227f6  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800227fd  nop     dword ptr [rax+rax+00h]
0x180022802  mov     edi, eax
0x180022804  cmp     eax, 80070002h
0x180022809  jz      loc_180022678
0x18002280f  cmp     eax, 8007065Dh
0x180022814  jz      loc_180022678
0x18002281a  mov     eax, [rsp+330h+var_2EC]
0x18002281e  mov     [rsi+8], eax
0x180022821  mov     [rsi], r13w
0x180022825  jmp     short loc_18002284D
0x180022827  lea     rdx, [rsp+330h+var_2F0]; int *
0x18002282c  mov     rcx, rbx; unsigned __int16 *
0x18002282f  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x180022834  mov     edi, eax
0x180022836  test    eax, eax
0x180022838  js      short loc_18002284D
0x18002283a  mov     eax, [rsp+330h+var_2F0]
0x18002283e  mov     [rsi+8], eax
0x180022841  mov     word ptr [rsi], 0Bh
0x180022846  jmp     short loc_18002284D
0x180022848  mov     edi, 8000FFFFh
0x18002284d  lea     rcx, [rsp+330h+pvarg]; pvarg
0x180022852  call    cs:__imp_VariantClear
0x180022859  nop     dword ptr [rax+rax+00h]
0x18002285e  mov     rcx, r15; bstrString
0x180022861  call    cs:__imp_SysFreeString
0x180022868  nop     dword ptr [rax+rax+00h]
0x18002286d  mov     rcx, [rsp+330h+hkey]; hKey
0x180022872  mov     [rsp+330h+hkey], 0
0x18002287b  test    rcx, rcx
0x18002287e  jz      short loc_18002288C
0x180022880  call    cs:__imp_RegCloseKey
0x180022887  nop     dword ptr [rax+rax+00h]
0x18002288c  mov     rcx, rbx; bstrString
0x18002288f  call    cs:__imp_SysFreeString
0x180022896  nop     dword ptr [rax+rax+00h]
0x18002289b  lea     rcx, [rsp+330h+var_2E0]
0x1800228a0  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1800228a5  mov     eax, edi
0x1800228a7  mov     rcx, [rbp+230h+var_30]
0x1800228ae  xor     rcx, rsp; StackCookie
0x1800228b1  call    __security_check_cookie
0x1800228b6  lea     r11, [rsp+330h+var_20]
0x1800228be  mov     rbx, [r11+40h]
0x1800228c2  mov     rsi, [r11+48h]
0x1800228c6  mov     rsp, r11
0x1800228c9  pop     r15
0x1800228cb  pop     r14
0x1800228cd  pop     r13
  ... truncated ...
```
