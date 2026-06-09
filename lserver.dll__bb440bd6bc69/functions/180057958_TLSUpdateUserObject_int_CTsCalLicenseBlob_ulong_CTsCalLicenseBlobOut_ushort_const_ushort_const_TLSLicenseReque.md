# TLSUpdateUserObject(int,CTsCalLicenseBlob *,ulong,CTsCalLicenseBlobOut *,ushort const *,ushort const *,_TLSLicenseRequest *,ushort const *,_RDLSTelemetryData &)

- ea: `0x180057958`
- end: `0x18005827c`
- name: `?TLSUpdateUserObject@@YAJHPEAVCTsCalLicenseBlob@@KPEAUCTsCalLicenseBlobOut@@PEBG2PEAU_TLSLicenseRequest@@2AEAU_RDLSTelemetryData@@@Z`
- size: `2340`
- prototype: `__int64 __fastcall(int, struct CTsCalLicenseBlob *, __int64, struct CTsCalLicenseBlobOut *, const unsigned __int16 *, unsigned __int16 *, struct _TLSLicenseRequest *, unsigned __int16 *, struct _RDLSTelemetryData *)`
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180073490`

## callees

- `0x180005665`
- `0x18000575c`
- `0x18000bb98`
- `0x18000cff0`
- `0x18000d060`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001b128`
- `0x18001e2b4`
- `0x18003b248`
- `0x18004ed84`
- `0x1800576ac`
- `0x180057780`
- `0x180057838`
- `0x180057958`
- `0x18005cde4`
- `0x18005cfec`
- `0x180075e34`
- `0x1800766c8`
- `0x180076798`
- `0x180076938`
- `0x1800776e0`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180057cf0`
- `msvcrt!swscanf_s` at `0x180057cf0`
- `msvcrt!memcpy_s` at `0x180057c60`
- `msvcrt!memcpy_s` at `0x18005821b`
- `msvcrt!memcpy_s` at `0x180057c60`
- `msvcrt!memcpy_s` at `0x18005821b`
- `ole32!CoUninitialize` at `0x180058243`
- `ole32!CoUninitialize` at `0x180058243`
- `ole32!CoInitialize` at `0x180057a50`
- `ole32!CoInitialize` at `0x180057a50`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180057bae`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180057bae`
- `KERNEL32!LocalAlloc` at `0x180057ac3`
- `KERNEL32!LocalAlloc` at `0x180058132`
- `KERNEL32!LocalAlloc` at `0x1800581e6`
- `KERNEL32!LocalAlloc` at `0x180057ac3`
- `KERNEL32!LocalAlloc` at `0x180058132`
- `KERNEL32!LocalAlloc` at `0x1800581e6`
- `KERNEL32!LocalFree` at `0x180057b41`
- `KERNEL32!LocalFree` at `0x18005817b`
- `KERNEL32!LocalFree` at `0x180057b41`
- `KERNEL32!LocalFree` at `0x18005817b`
- `TlsBrand!CALDetailsCreator` at `0x180057d6c`
- `TlsBrand!CALDetailsCreator` at `0x180057d6c`

## string_xrefs

- `0x180057bf4`: `AdsOpenObject failed for IID_IDirectorySearch. HR = %x`
- `0x180057aa8`: `QueryUserADsPath failed HR = %x`
- `0x180057c2d`: `Failure in AdsOpenObject or FindUser. Continue PU CAL issue. HR = %x`
- `0x180057ea6`: `Failed GetCALAccessRights. HR = %x, ValidCALCount=%d`

## pseudocode

```c
__int64 __fastcall TLSUpdateUserObject(
        int a1,
        struct CTsCalLicenseBlob *a2,
        __int64 a3,
        struct CTsCalLicenseBlobOut *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct _TLSLicenseRequest *a7,
        unsigned __int16 *a8,
        struct _RDLSTelemetryData *a9)
{
  const unsigned __int16 *v12; // rsi
  int UserADsPath; // eax
  signed int updated; // ebx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  HRESULT v17; // eax
  unsigned int v18; // ebx
  int User; // eax
  const void *v20; // r8
  struct _TLSLicenseRequest *v21; // rbx
  const wchar_t *v22; // rcx
  int v23; // ebx
  unsigned int v24; // esi
  struct ICALDetails *v26; // rax
  struct ICALDetails *v27; // r14
  unsigned int v28; // eax
  unsigned int v29; // r11d
  const unsigned __int16 *v30; // rcx
  int v31; // eax
  __int64 *v32; // rdx
  int v33; // esi
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rdi
  int v36; // edx
  int v37; // eax
  IID *riid; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v41; // [rsp+58h] [rbp-A8h]
  int v42; // [rsp+5Ch] [rbp-A4h]
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch]
  int v45; // [rsp+68h] [rbp-98h]
  struct _TLSLicenseRequest *v46; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v47; // [rsp+78h] [rbp-88h]
  struct IDirectorySearch *ppObject; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v49; // [rsp+88h] [rbp-78h]
  _DWORD Destination[15]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v51; // [rsp+CCh] [rbp-34h]
  wchar_t Buffer[256]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD Source[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t v54[256]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v55[256]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR szPathName[256]; // [rsp+710h] [rbp+610h] BYREF
  unsigned __int16 v57[256]; // [rsp+910h] [rbp+810h] BYREF
  char v58; // [rsp+B10h] [rbp+A10h] BYREF
  unsigned __int16 v59[512]; // [rsp+D10h] [rbp+C10h] BYREF

  ppObject = 0;
  v46 = a7;
  v45 = a1;
  v49 = a8;
  v44 = 1;
  memset_0(szPathName, 0, sizeof(szPathName));
  memset_0(v59, 0, sizeof(v59));
  memset_0(Destination, 0, 0x240u);
  memset_0(Source, 0, 0x240u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids);
  CoInitialize(0);
  v42 = 1;
  if ( !a1 )
  {
    if ( a2 && *(_DWORD *)a2 && (v20 = (const void *)*((_QWORD *)a2 + 1)) != 0 )
    {
      if ( *(_DWORD *)a2 != 576 )
      {
        updated = -2147023728;
        StringCchPrintfW(
          (unsigned __int16 *)a9 + 1034,
          0xFFu,
          L"RDLS New Interface. Invalid Old License format. HR = %x",
          2147943568LL);
LABEL_94:
        if ( ppObject )
          ((void (__fastcall *)(struct IDirectorySearch *))ppObject->lpVtbl->Release)(ppObject);
        CoUninitialize();
        return (unsigned int)updated;
      }
      memcpy_s(Destination, 0x240u, v20, 0x240u);
    }
    else
    {
      StringCchPrintfW(
        (unsigned __int16 *)a9 + 1034,
        0xFFu,
        L"RDLS New Interface. Old License is NULL, issueing new license. HR = %x",
        0);
    }
LABEL_30:
    v21 = v46;
    v40 = 0;
    v39 = 0;
    v47 = 0;
    v22 = (const wchar_t *)*((_QWORD *)v46 + 6);
    v41 = 0;
    swscanf_s(v22, L"%3s-%ld-%ld", &v58, 255, &v40, &v39);
    if ( Destination[0] )
      v23 = -(Destination[0] < *((_DWORD *)v21 + 6)) - 1;
    else
      v23 = -2;
    if ( (v40 & v51) != v40 )
      v23 &= ~2u;
    if ( (v39 & v51) != v39 )
      v23 &= ~4u;
    v24 = v23 & 0xFFFFFFF7;
    if ( !(unsigned int)IsUserLicenseExpired(Destination) )
      v24 = v23;
    if ( v24 == -1 )
    {
      StringCchCopyW((unsigned __int16 *)a9 + 1290, 0xFFu, L"UNEXPECTED - PU_VALID_CAL, must occur only in 2K3 AD");
      return 0;
    }
    v26 = CALDetailsCreator();
    v27 = v26;
    if ( !v26 )
    {
      updated = 1;
      StringCchCopyW((unsigned __int16 *)a9 + 1290, 0xFFu, L"Failed to get CAL Details");
LABEL_79:
      v33 = v45;
      if ( v45 && updated < 0 )
      {
        LogFailedPUIssuanceInDB(v46, v54, v59, v49, a9);
        v34 = (unsigned __int16 *)LocalAlloc(0x40u, 0x1FEu);
        v35 = v34;
        if ( v34 )
        {
          StringCchPrintfW(v34, 0xFFu, L"0x%x", (unsigned int)updated);
          CrimsonHelper::RaiseEvent<unsigned short const *,unsigned short const *,unsigned short *>(
            (unsigned int)CrimsonHelper::s_instance,
            v36,
            (_DWORD)a5,
            (_DWORD)a6,
            (__int64)v35);
          LocalFree(v35);
        }
      }
      else
      {
        v37 = LogSuccessFullPUIssuanceInDB(v46, v54, v59, v49, (struct _FILETIME)riid, a9);
        if ( v37 )
        {
          if ( v37 > 0 )
            updated = (unsigned __int16)v37 | 0x80070000;
          else
            updated = v37;
        }
        else if ( !v33 && a4 && *(_QWORD *)a4 && *((_QWORD *)a4 + 1) )
        {
          **(_DWORD **)a4 = 0;
          **((_QWORD **)a4 + 1) = LocalAlloc(0x40u, 0x240u);
          if ( **((_QWORD **)a4 + 1) )
          {
            **(_DWORD **)a4 = 576;
            memcpy_s(**((void *const **)a4 + 1), 0x240u, Source, 0x240u);
          }
          else
          {
            updated = -2147024882;
          }
        }
      }
      goto LABEL_94;
    }
    LODWORD(riid) = *((_DWORD *)v46 + 6);
    v28 = (*(__int64 (__fastcall **)(struct ICALDetails *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 24LL))(
            v26,
            v51,
            v40,
            v39);
    updated = v28;
    if ( v28 )
    {
      StringCchPrintfW((unsigned __int16 *)a9 + 1290, 0xFFu, L"Failed to get matching valid CAL types. HR = %x", v28);
      goto LABEL_79;
    }
    if ( !v41 )
    {
      updated = 4136;
      StringCchCopyW((unsigned __int16 *)a9 + 776, 0xFFu, L"UnSupported");
      StringCchPrintfW((unsigned __int16 *)a9 + 1034, v29, L"GetValidCALTypes Wrong LS version. HR = %x", 4136);
      CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_E_INCOMPATIBLEVERSION, 0, 0);
      goto LABEL_94;
    }
    v43 = 0;
    updated = (*(__int64 (__fastcall **)(struct ICALDetails *, unsigned __int16 *, int *))(*(_QWORD *)v27 + 8LL))(
                v27,
                *v47,
                &v43);
    if ( updated )
    {
      LODWORD(riid) = v41;
      StringCchPrintfW(
        (unsigned __int16 *)a9 + 1290,
        0xFFu,
        L"Failed GetCALAccessRights. HR = %x, ValidCALCount=%d",
        (unsigned int)updated);
      goto LABEL_79;
    }
    if ( (v39 & v43) != v39 && v24 == -5 )
    {
      StringCchPrintfW((unsigned __int16 *)a9 + 1290, 0xFFu, L"PU_INVALID_NON_ENF_RIGHTS. ValidCALCount=%d", v41);
      return 0;
    }
    updated = FineTuneIssuingLicAttrs(v30, *((_DWORD *)v46 + 6), *v47, (struct USERLICENSEDATA_WIN8 *)Source);
    if ( updated < 0 )
      goto LABEL_94;
    if ( v45 )
    {
      updated = UpdateUserLicenseAttributes(v42, a6, (struct USERLICENSEDATA_WIN8 *)Source, szPathName);
      if ( updated < 0 )
      {
LABEL_78:
        StringCbPrintfW(v59, 0x200u, L"%s\\%s", a6, a5);
        goto LABEL_79;
      }
    }
    if ( !v44 )
    {
LABEL_75:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids);
      goto LABEL_78;
    }
    if ( Destination[0] )
    {
      if ( Destination[0] == Source[0] && v51 == Source[15] )
      {
        v31 = 0;
        if ( ((v24 >> 3) & 1) == 0 )
        {
          if ( (unsigned int)GetProductDescFromPid(Buffer, L"Microsoft Corporation") )
            StringCchCopyW(v55, 0x100u, Buffer);
          v32 = TLS_I_PU_CALRENEWED;
LABEL_74:
          CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,unsigned short *>(
            (unsigned int)CrimsonHelper::s_instance,
            (_DWORD)v32,
            (unsigned int)v55,
            (_DWORD)a5,
            (__int64)a6);
          goto LABEL_75;
        }
      }
      else
      {
        v31 = 1;
      }
      if ( v31 )
      {
        if ( (unsigned int)GetProductDescFromPid(Buffer, L"Microsoft Corporation") )
          StringCchCopyW(v55, 0x100u, Buffer);
        if ( (unsigned int)GetProductDescFromPid(v54, L"Microsoft Corporation") )
          StringCchCopyW(v57, 0x100u, v54);
        CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,unsigned short const *,unsigned short const *>(
          (CrimsonHelper *)CrimsonHelper::s_instance,
          (__int64)a5,
          (__int64)a6);
      }
      goto LABEL_75;
    }
    if ( (unsigned int)GetProductDescFromPid(v54, L"Microsoft Corporation") )
      StringCchCopyW(v55, 0x100u, v54);
    v32 = TLS_I_PU_NEWCAL;
    goto LABEL_74;
  }
  v12 = 0;
  v42 = IsLocalDomain(a6);
  if ( !v42 )
    v12 = a6;
  UserADsPath = queryUserADsPath(a5, v12, szPathName);
  updated = UserADsPath;
  if ( UserADsPath >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids, szPathName);
    v17 = ADsOpenObject(szPathName, 0, 0, 0xC5u, &IID_IDirectorySearch, (void **)&ppObject);
    v18 = v17;
    if ( v17 >= 0 )
    {
      User = FindUser(ppObject, a5, v12, (struct USERLICENSEDATA_WIN8 *)Destination);
      if ( User < 0 )
        StringCchPrintfW(
          (unsigned __int16 *)a9 + 1034,
          0xFFu,
          L"Failure in AdsOpenObject or FindUser. Continue PU CAL issue. HR = %x",
          (unsigned int)User);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids,
          (unsigned int)v17);
      StringCchPrintfW(
        (unsigned __int16 *)a9 + 1034,
        0xFFu,
        L"AdsOpenObject failed for IID_IDirectorySearch. HR = %x",
        v18);
      v44 = 0;
    }
    goto LABEL_30;
  }
  StringCchPrintfW((unsigned __int16 *)a9 + 1034, 0xFFu, L"QueryUserADsPath failed HR = %x", (unsigned int)UserADsPath);
  v15 = (unsigned __int16 *)LocalAlloc(0x40u, 0x1FEu);
  v16 = v15;
  if ( v15 )
  {
    StringCchPrintfW(v15, 0xFFu, L"0x%x", (unsigned int)updated);
    CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, TLS_W_PU_AD_QUERY, v16);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids,
        (_DWORD)a6,
        (__int64)a5);
    LocalFree(v16);
    goto LABEL_30;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180057958  mov     [rsp-8+arg_0], rbx
0x18005795d  push    rbp
0x18005795e  push    rsi
0x18005795f  push    rdi
0x180057960  push    r12
0x180057962  push    r13
0x180057964  push    r14
0x180057966  push    r15
0x180057968  lea     rbp, [rsp-1020h]
0x180057970  mov     eax, 1120h
0x180057975  call    _alloca_probe
0x18005797a  sub     rsp, rax
0x18005797d  mov     rax, cs:__security_cookie
0x180057984  xor     rax, rsp
0x180057987  mov     [rbp+1050h+var_40], rax
0x18005798e  mov     rax, [rbp+1050h+arg_30]
0x180057995  mov     rbx, rdx
0x180057998  mov     r12, [rbp+1050h+arg_28]
0x18005799f  mov     r14d, ecx
0x1800579a2  mov     r13, qword ptr [rbp+1050h+arg_20.dwLowDateTime]
0x1800579a9  mov     esi, 1
0x1800579ae  mov     rdi, [rbp+1050h+arg_40]
0x1800579b5  xor     edx, edx; Val
0x1800579b7  and     [rbp+1050h+var_10D0], 0
0x1800579bc  mov     r8d, 200h; Size
0x1800579c2  mov     [rsp+1150h+var_10E0], rax
0x1800579c7  mov     r15, r9
0x1800579ca  mov     rax, [rbp+1050h+arg_38]
0x1800579d1  mov     [rsp+1150h+var_10E8], ecx
0x1800579d5  lea     rcx, [rbp+1050h+szPathName]; void *
0x1800579dc  mov     [rbp+1050h+var_10C8], rax
0x1800579e0  mov     [rsp+1150h+var_10EC], esi
0x1800579e4  call    memset_0
0x1800579e9  xor     edx, edx; Val
0x1800579eb  lea     rcx, [rbp+1050h+var_440]; void *
0x1800579f2  mov     r8d, 400h; Size
0x1800579f8  call    memset_0
0x1800579fd  xor     edx, edx; Val
0x1800579ff  lea     rcx, [rbp+1050h+Destination]; void *
0x180057a03  mov     r8d, 240h; Size
0x180057a09  call    memset_0
0x180057a0e  xor     edx, edx; Val
0x180057a10  lea     rcx, [rbp+1050h+Source]; void *
0x180057a17  mov     r8d, 240h; Size
0x180057a1d  call    memset_0
0x180057a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a29  lea     rax, WPP_GLOBAL_Control
0x180057a30  cmp     rcx, rax
0x180057a33  jz      short loc_180057A4E
0x180057a35  test    byte ptr [rcx+1Ch], 10h
0x180057a39  jz      short loc_180057A4E
0x180057a3b  mov     rcx, [rcx+10h]
0x180057a3f  lea     edx, [rsi+9]
0x180057a42  lea     r8, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids
0x180057a49  call    WPP_SF_
0x180057a4e  xor     ecx, ecx; pvReserved
0x180057a50  call    cs:__imp_CoInitialize
0x180057a57  nop     dword ptr [rax+rax+00h]
0x180057a5c  mov     [rsp+1150h+var_10F4], esi
0x180057a60  mov     eax, 0FFh
0x180057a65  test    r14d, r14d
0x180057a68  jz      loc_180057C3B
0x180057a6e  mov     rcx, r12; unsigned __int16 *
0x180057a71  call    ?IsLocalDomain@@YAHPEBG@Z; IsLocalDomain(ushort const *)
0x180057a76  xor     esi, esi
0x180057a78  mov     [rsp+1150h+var_10F4], eax
0x180057a7c  test    eax, eax
0x180057a7e  lea     r8, [rbp+1050h+szPathName]
0x180057a85  mov     rcx, r13
0x180057a88  cmovz   rsi, r12
0x180057a8c  mov     rdx, rsi
0x180057a8f  call    queryUserADsPath
0x180057a94  mov     ebx, eax
0x180057a96  test    eax, eax
0x180057a98  jns     loc_180057B52
0x180057a9e  lea     rcx, [rdi+814h]; unsigned __int16 *
0x180057aa5  mov     r9d, eax
0x180057aa8  lea     r8, aQueryuseradspa; "QueryUserADsPath failed HR = %x"
0x180057aaf  mov     edx, 0FFh; unsigned __int64
0x180057ab4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057ab9  mov     edx, 1FEh; uBytes
0x180057abe  mov     ecx, 40h ; '@'; uFlags
0x180057ac3  call    cs:__imp_LocalAlloc
0x180057aca  nop     dword ptr [rax+rax+00h]
0x180057acf  mov     rsi, rax
0x180057ad2  test    rax, rax
0x180057ad5  jz      loc_18005824F
0x180057adb  mov     r9d, ebx
0x180057ade  lea     r8, a0xX_0; "0x%x"
0x180057ae5  mov     edx, 0FFh; unsigned __int64
0x180057aea  mov     rcx, rax; unsigned __int16 *
0x180057aed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057af2  mov     r8, rsi
0x180057af5  lea     rdx, TLS_W_PU_AD_QUERY
0x180057afc  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180057b03  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180057b08  mov     rcx, cs:WPP_GLOBAL_Control
0x180057b0f  lea     rax, WPP_GLOBAL_Control
0x180057b16  cmp     rcx, rax
0x180057b19  jz      short loc_180057B3E
0x180057b1b  test    byte ptr [rcx+1Ch], 10h
0x180057b1f  jz      short loc_180057B3E
0x180057b21  mov     rcx, [rcx+10h]
0x180057b25  lea     r8, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids
0x180057b2c  mov     edx, 0Bh
0x180057b31  mov     [rsp+1150h+riid], r13
0x180057b36  mov     r9, r12
0x180057b39  call    WPP_SF_SS
0x180057b3e  mov     rcx, rsi; hMem
0x180057b41  call    cs:__imp_LocalFree
0x180057b48  nop     dword ptr [rax+rax+00h]
0x180057b4d  jmp     loc_180057CAA
0x180057b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180057b59  lea     r14, WPP_GLOBAL_Control
0x180057b60  cmp     rcx, r14
0x180057b63  jz      short loc_180057B87
0x180057b65  test    byte ptr [rcx+1Ch], 10h
0x180057b69  jz      short loc_180057B87
0x180057b6b  mov     rcx, [rcx+10h]
0x180057b6f  lea     r9, [rbp+1050h+szPathName]
0x180057b76  mov     edx, 0Ch
0x180057b7b  lea     r8, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids
0x180057b82  call    WPP_SF_S
0x180057b87  lea     rax, [rbp+1050h+var_10D0]
0x180057b8b  mov     r9d, 0C5h; dwReserved
0x180057b91  mov     [rsp+1150h+ppObject], rax; ppObject
0x180057b96  lea     rcx, [rbp+1050h+szPathName]; lpszPathName
0x180057b9d  lea     rax, IID_IDirectorySearch
0x180057ba4  xor     r8d, r8d; lpszPassword
0x180057ba7  xor     edx, edx; lpszUserName
0x180057ba9  mov     [rsp+1150h+riid], rax; riid
0x180057bae  call    cs:__imp_ADsOpenObject
0x180057bb5  nop     dword ptr [rax+rax+00h]
0x180057bba  mov     ebx, eax
0x180057bbc  test    eax, eax
0x180057bbe  jns     short loc_180057C0F
0x180057bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180057bc7  cmp     rcx, r14
0x180057bca  jz      short loc_180057BEA
0x180057bcc  test    byte ptr [rcx+1Ch], 10h
0x180057bd0  jz      short loc_180057BEA
0x180057bd2  mov     rcx, [rcx+10h]
0x180057bd6  lea     r8, WPP_4a7a7b334f5e340c944a9da8b3a697a7_Traceguids
0x180057bdd  mov     edx, 0Dh
0x180057be2  mov     r9d, eax
0x180057be5  call    WPP_SF_D
0x180057bea  lea     rcx, [rdi+814h]; unsigned __int16 *
0x180057bf1  mov     r9d, ebx
0x180057bf4  lea     r8, aAdsopenobjectF_0; "AdsOpenObject failed for IID_IDirectory"...
0x180057bfb  mov     edx, 0FFh; unsigned __int64
0x180057c00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057c05  and     [rsp+1150h+var_10EC], 0
0x180057c0a  jmp     loc_180057CAA
0x180057c0f  mov     rcx, [rbp+1050h+var_10D0]; struct IDirectorySearch *
0x180057c13  lea     r9, [rbp+1050h+Destination]; struct USERLICENSEDATA_WIN8 *
0x180057c17  mov     r8, rsi; unsigned __int16 *
0x180057c1a  mov     rdx, r13; unsigned __int16 *
0x180057c1d  call    ?FindUser@@YAJPEAUIDirectorySearch@@PEBG1PEAUUSERLICENSEDATA_WIN8@@@Z; FindUser(IDirectorySearch *,ushort const *,ushort const *,USERLICENSEDATA_WIN8 *)
0x180057c22  test    eax, eax
0x180057c24  jns     loc_180057CAA
0x180057c2a  mov     r9d, eax
0x180057c2d  lea     r8, aFailureInAdsop; "Failure in AdsOpenObject or FindUser. C"...
0x180057c34  mov     edx, 0FFh
0x180057c39  jmp     short loc_180057C9E
0x180057c3b  test    rbx, rbx
0x180057c3e  jz      short loc_180057C91
0x180057c40  cmp     dword ptr [rbx], 0
0x180057c43  jz      short loc_180057C91
0x180057c45  mov     r8, [rbx+8]; Source
0x180057c49  test    r8, r8
0x180057c4c  jz      short loc_180057C91
0x180057c4e  mov     ecx, 240h
0x180057c53  cmp     [rbx], ecx
0x180057c55  jnz     short loc_180057C6E
0x180057c57  mov     r9d, ecx; SourceSize
0x180057c5a  mov     edx, ecx; DestinationSize
0x180057c5c  lea     rcx, [rbp+1050h+Destination]; Destination
0x180057c60  call    cs:__imp_memcpy_s
0x180057c67  nop     dword ptr [rax+rax+00h]
0x180057c6c  jmp     short loc_180057CAA
0x180057c6e  mov     ebx, 80070490h
0x180057c73  lea     rcx, [rdi+814h]; unsigned __int16 *
0x180057c7a  mov     r9d, ebx
0x180057c7d  lea     r8, aRdlsNewInterfa; "RDLS New Interface. Invalid Old License"...
0x180057c84  mov     rdx, rax; unsigned __int64
0x180057c87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057c8c  jmp     loc_18005822E
0x180057c91  xor     r9d, r9d
0x180057c94  lea     r8, aRdlsNewInterfa_0; "RDLS New Interface. Old License is NULL"...
0x180057c9b  mov     rdx, rax; unsigned __int64
0x180057c9e  lea     rcx, [rdi+814h]; unsigned __int16 *
0x180057ca5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057caa  mov     rbx, [rsp+1150h+var_10E0]
0x180057caf  lea     rax, [rsp+1150h+var_1100]
0x180057cb4  and     [rsp+1150h+var_10FC], 0
0x180057cb9  lea     r8, [rbp+1050h+var_640]
0x180057cc0  and     [rsp+1150h+var_1100], 0
0x180057cc5  lea     rdx, a3sLdLd; "%3s-%ld-%ld"
0x180057ccc  and     [rsp+1150h+var_10D8], 0
0x180057cd2  mov     r9d, 0FFh
0x180057cd8  mov     rcx, [rbx+30h]; Buffer
0x180057cdc  and     [rsp+1150h+var_10F8], 0
0x180057ce1  mov     [rsp+1150h+ppObject], rax
0x180057ce6  lea     rax, [rsp+1150h+var_10FC]
0x180057ceb  mov     [rsp+1150h+riid], rax
0x180057cf0  call    cs:__imp_swscanf_s
0x180057cf7  nop     dword ptr [rax+rax+00h]
0x180057cfc  mov     eax, [rbp+1050h+Destination]
0x180057cff  or      r14d, 0FFFFFFFFh
0x180057d03  test    eax, eax
0x180057d05  jnz     short loc_180057D0E
0x180057d07  mov     ebx, 0FFFFFFFEh
0x180057d0c  jmp     short loc_180057D16
0x180057d0e  cmp     eax, [rbx+18h]
0x180057d11  sbb     ebx, ebx
0x180057d13  add     ebx, r14d
0x180057d16  mov     ecx, [rbp+1050h+var_1084]
0x180057d19  mov     eax, ecx
0x180057d1b  and     eax, [rsp+1150h+var_10FC]
0x180057d1f  cmp     eax, [rsp+1150h+var_10FC]
0x180057d23  jz      short loc_180057D28
0x180057d25  and     ebx, 0FFFFFFFDh
0x180057d28  and     ecx, [rsp+1150h+var_1100]
0x180057d2c  cmp     ecx, [rsp+1150h+var_1100]
0x180057d30  jz      short loc_180057D35
0x180057d32  and     ebx, 0FFFFFFFBh
0x180057d35  lea     rcx, [rbp+1050h+Destination]
0x180057d39  call    IsUserLicenseExpired
0x180057d3e  mov     esi, ebx
0x180057d40  and     esi, 0FFFFFFF7h
0x180057d43  test    eax, eax
0x180057d45  cmovz   esi, ebx
0x180057d48  cmp     esi, r14d
0x180057d4b  jnz     short loc_180057D6C
0x180057d4d  lea     rcx, [rdi+0A14h]; unsigned __int16 *
0x180057d54  mov     edx, 0FFh; unsigned __int64
0x180057d59  lea     r8, aUnexpectedPuVa; "UNEXPECTED - PU_VALID_CAL, must occur o"...
0x180057d60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057d65  xor     eax, eax
0x180057d67  jmp     loc_180058251
0x180057d6c  call    cs:__imp_?CALDetailsCreator@@YAPEAVICALDetails@@XZ; CALDetailsCreator(void)
0x180057d73  nop     dword ptr [rax+rax+00h]
0x180057d78  mov     r14, rax
0x180057d7b  test    rax, rax
0x180057d7e  jnz     short loc_180057DA0
0x180057d80  lea     rcx, [rdi+0A14h]; unsigned __int16 *
0x180057d87  mov     edx, 0FFh; unsigned __int64
0x180057d8c  lea     r8, aFailedToGetCal; "Failed to get CAL Details"
0x180057d93  lea     ebx, [rax+1]
0x180057d96  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057d9b  jmp     loc_1800580F3
0x180057da0  mov     rax, [rax]
0x180057da3  lea     rcx, [rsp+1150h+var_10F8]
0x180057da8  mov     r9d, [rsp+1150h+var_1100]
0x180057dad  mov     r8d, [rsp+1150h+var_10FC]
0x180057db2  mov     edx, [rbp+1050h+var_1084]
0x180057db5  mov     rax, [rax+18h]
0x180057db9  mov     [rsp+1150h+var_1118], rcx
0x180057dbe  lea     rcx, [rsp+1150h+var_10D8]
0x180057dc3  mov     [rsp+1150h+var_1120], rcx
0x180057dc8  lea     rcx, [rbp+1050h+var_640]
0x180057dcf  mov     [rsp+1150h+ppObject], rcx
0x180057dd4  mov     rcx, [rsp+1150h+var_10E0]
0x180057dd9  mov     ecx, [rcx+18h]
0x180057ddc  mov     dword ptr [rsp+1150h+riid], ecx
0x180057de0  mov     rcx, r14
0x180057de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057de8  mov     ebx, eax
0x180057dea  test    eax, eax
0x180057dec  jz      short loc_180057E0E
0x180057dee  lea     rcx, [rdi+0A14h]; unsigned __int16 *
0x180057df5  mov     r9d, eax
0x180057df8  lea     r8, aFailedToGetMat; "Failed to get matching valid CAL types."...
0x180057dff  mov     edx, 0FFh; unsigned __int64
0x180057e04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057e09  jmp     loc_1800580F3
0x180057e0e  cmp     [rsp+1150h+var_10F8], 0
0x180057e13  jnz     short loc_180057E6D
0x180057e15  mov     r11d, 0FFh
0x180057e1b  lea     rcx, [rdi+610h]; unsigned __int16 *
0x180057e22  mov     edx, r11d; unsigned __int64
0x180057e25  lea     r8, aUnsupported; "UnSupported"
0x180057e2c  mov     ebx, 1028h
0x180057e31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057e36  lea     rcx, [rdi+814h]; unsigned __int16 *
0x180057e3d  mov     r9d, ebx
0x180057e40  lea     r8, aGetvalidcaltyp; "GetValidCALTypes Wrong LS version. HR ="...
0x180057e47  mov     edx, r11d; unsigned __int64
0x180057e4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057e4f  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180057e52  lea     rdx, TLS_E_INCOMPATIBLEVERSION; struct _EVENT_DESCRIPTOR *
0x180057e59  xor     r8d, r8d; unsigned int
0x180057e5c  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180057e63  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180057e68  jmp     loc_18005822E
0x180057e6d  and     [rsp+1150h+var_10F0], 0
0x180057e72  lea     r8, [rsp+1150h+var_10F0]
0x180057e77  mov     rax, [r14]
0x180057e7a  mov     rcx, r14
0x180057e7d  mov     rdx, [rsp+1150h+var_10D8]
  ... truncated ...
```
