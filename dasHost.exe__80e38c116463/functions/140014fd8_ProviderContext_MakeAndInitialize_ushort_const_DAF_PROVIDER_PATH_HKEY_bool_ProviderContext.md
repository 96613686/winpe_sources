# ProviderContext::MakeAndInitialize(ushort const *,_DAF_PROVIDER_PATH,HKEY__ *,bool,ProviderContext * *)

- ea: `0x140014fd8`
- end: `0x1400158ad`
- name: `?MakeAndInitialize@ProviderContext@@SAJPEBGW4_DAF_PROVIDER_PATH@@PEAUHKEY__@@_NPEAPEAV1@@Z`
- size: `2261`
- prototype: `__int64 __fastcall(const WCHAR *, int, HKEY, unsigned __int8, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140012c08`

## callees

- `0x140001570`
- `0x1400018d4`
- `0x1400020d0`
- `0x1400021f0`
- `0x140006ce4`
- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x1400137b8`
- `0x1400149d8`
- `0x140014b60`
- `0x140014f8c`
- `0x140014fd8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015313`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400150cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400152fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400150cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400152fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400150eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001531b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400150eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001531b`
- `RPCRT4!UuidFromStringW` at `0x1400151e5`
- `RPCRT4!UuidFromStringW` at `0x140015270`
- `RPCRT4!UuidFromStringW` at `0x1400151e5`
- `RPCRT4!UuidFromStringW` at `0x140015270`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400151a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001523c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400152c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015375`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400153d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001542d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015484`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400154fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001556f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400155e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015653`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400156c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001572e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400151a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001523c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400152c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015375`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400153d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001542d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015484`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400154fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001556f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400155e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015653`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400156c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001572e`

## string_xrefs

- `0x14001563a`: `ImpersonateCaller`
- `0x140015669`: `ImpersonateCaller`
- `0x140015823`: `ImpersonateCaller`
- `0x1400153b5`: `SecurityContext`
- `0x1400152a4`: `DllPath`
- `0x14001535a`: `DllPath`
- `0x14001518a`: `ProtocolId`
- `0x14001521a`: `CLSID`
- `0x1400151ad`: `could not read the ProtocolId value for %ws`
- `0x1400151ef`: `could not convert ProtocolId string to GUID for %ws`
- `0x140015246`: `could not read the CLSID value for %ws`
- `0x14001527a`: `could not read convert CLSID string to GUID for %ws`
- `0x1400152cb`: `could not get size for the DllPath value for %ws`
- `0x14001537f`: `could not read the DllPath value for %ws`
- `0x1400153e1`: `could not read the SecurityContext value for %ws`
- `0x140015437`: `could not read the PropertyRank value for %ws`
- `0x1400157bb`: `could not read the %ws value for %ws`
- `0x140015753`: `could not read the FederatedAepStoreLocations value for %ws`

## pseudocode

```c
__int64 __fastcall ProviderContext::MakeAndInitialize(
        const WCHAR *a1,
        int a2,
        HKEY a3,
        unsigned __int8 a4,
        unsigned __int16 ***a5)
{
  int v5; // r12d
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _QWORD *v11; // rax
  unsigned __int16 **v12; // rdi
  unsigned __int16 *v13; // r15
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  unsigned int ValueW; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned __int16 *v27; // r12
  unsigned __int16 *v28; // r15
  DWORD v29; // ebx
  HANDLE v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  const char *v35; // r9
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  const WCHAR *v42; // rax
  __int64 v43; // rdx
  int pdwType; // [rsp+20h] [rbp-81h]
  DWORD pcbData; // [rsp+40h] [rbp-61h] BYREF
  DWORD v47; // [rsp+44h] [rbp-5Dh] BYREF
  unsigned __int16 ***v48; // [rsp+48h] [rbp-59h]
  _BYTE pvData[2]; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int16 StringUuid[36]; // [rsp+52h] [rbp-4Fh] BYREF
  __int16 v51; // [rsp+9Ah] [rbp-7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v5 = a4;
  v48 = a5;
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 111;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
      (const char *)v9,
      pdwType);
    return v9;
  }
  v11 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = (unsigned __int16 **)v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    v10 = 113;
    goto LABEL_72;
  }
  *v11 = 0;
  v11[5] = 0;
  v11[6] = 0;
  v11[7] = 0;
  v11[8] = 0;
  v11[9] = 0;
  *((_DWORD *)v11 + 20) = 0;
  *(_QWORD *)((char *)v11 + 84) = 1;
  v11[12] = 0;
  *((_DWORD *)v11 + 26) = 0;
  v11[14] = 0;
  *((_DWORD *)v11 + 30) = 0;
  v11[16] = 0;
  v11[17] = 0;
  v11[18] = 0;
  v11[19] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_91edd21030e531619c269f99d7a31287_Traceguids, a1);
  v13 = *v12;
  if ( *v12 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
    SetLastError(LastError);
  }
  *v12 = 0;
  if ( !a1 )
  {
LABEL_16:
    *((_DWORD *)v12 + 26) = a2;
    *((_DWORD *)v12 + 21) = v5;
    memset_0(pvData, 0, 0x52u);
    v47 = 0;
    pcbData = 82;
    ValueW = RegGetValueW(a3, a1, L"ProtocolId", 2u, &v47, pvData, &pcbData);
    if ( ValueW )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x82,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)ValueW,
              (unsigned int)"could not read the ProtocolId value for %ws",
              (const char *)a1);
LABEL_55:
      v9 = v20;
      goto LABEL_56;
    }
    v51 = 0;
    v22 = UuidFromStringW(StringUuid, (UUID *)(v12 + 1));
    if ( v22 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x84,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v22,
              (unsigned int)"could not convert ProtocolId string to GUID for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    pcbData = 82;
    v23 = RegGetValueW(a3, a1, L"CLSID", 2u, &v47, pvData, &pcbData);
    if ( v23 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x88,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v23,
              (unsigned int)"could not read the CLSID value for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    v51 = 0;
    v24 = UuidFromStringW(StringUuid, (UUID *)(v12 + 3));
    if ( v24 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x8A,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v24,
              (unsigned int)"could not read convert CLSID string to GUID for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    pcbData = 0;
    v25 = RegGetValueW(a3, a1, L"DllPath", 0xFFFFu, 0, 0, &pcbData);
    if ( v25 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x8E,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v25,
              (unsigned int)"could not get size for the DllPath value for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    v26 = DAF_user_alloc(pcbData);
    v27 = v12[5];
    v28 = (unsigned __int16 *)v26;
    if ( v27 )
    {
      v29 = GetLastError();
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v27);
      SetLastError(v29);
    }
    v12[5] = v28;
    if ( !v28 )
    {
      v9 = -2147024882;
      v21 = 144;
      goto LABEL_32;
    }
    v31 = RegGetValueW(a3, a1, L"DllPath", 2u, &v47, v28, &pcbData);
    if ( v31 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x91,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v31,
              (unsigned int)"could not read the DllPath value for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    pcbData = 4;
    v32 = RegGetValueW(a3, a1, L"SecurityContext", 0x18u, &v47, v12 + 6, &pcbData);
    if ( v32 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x95,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v32,
              (unsigned int)"could not read the SecurityContext value for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    pcbData = 4;
    v33 = RegGetValueW(a3, a1, L"PropertyRank", 0x18u, &v47, (char *)v12 + 52, &pcbData);
    if ( v33 )
    {
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v33,
              (unsigned int)"could not read the PropertyRank value for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    pcbData = 4;
    v34 = RegGetValueW(a3, a1, L"Capabilities", 0x18u, &v47, v12 + 7, &pcbData);
    v35 = (const char *)v34;
    if ( v34 == 2 )
    {
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
        (const char *)2,
        (unsigned int)"provider %ws did not have a %ws value",
        (const char *)a1,
        L"Capabilities");
    }
    else if ( v34 )
    {
      v42 = L"Capabilities";
      v43 = 156;
      goto LABEL_59;
    }
    pcbData = 4;
    v36 = RegGetValueW(a3, a1, L"AllowReassociation", 0x18u, &v47, (char *)v12 + 60, &pcbData);
    v35 = (const char *)v36;
    if ( v36 == 2 )
    {
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
        (const char *)2,
        (unsigned int)"provider %ws did not have a %ws value",
        (const char *)a1,
        L"AllowReassociation");
    }
    else if ( v36 )
    {
      v42 = L"AllowReassociation";
      v43 = 159;
      goto LABEL_59;
    }
    pcbData = 4;
    v37 = RegGetValueW(a3, a1, L"SyncSetAssociations", 0x18u, &v47, v12 + 8, &pcbData);
    v35 = (const char *)v37;
    if ( v37 == 2 )
    {
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
        (const char *)2,
        (unsigned int)"provider %ws did not have a %ws value",
        (const char *)a1,
        L"SyncSetAssociations");
    }
    else if ( v37 )
    {
      v42 = L"SyncSetAssociations";
      v43 = 162;
      goto LABEL_59;
    }
    pcbData = 4;
    v38 = RegGetValueW(a3, a1, L"SuspendAppQueries", 0x18u, &v47, (char *)v12 + 68, &pcbData);
    v35 = (const char *)v38;
    if ( v38 == 2 )
    {
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
        (const char *)2,
        (unsigned int)"provider %ws did not have a %ws value",
        (const char *)a1,
        L"SuspendAppQueries");
    }
    else if ( v38 )
    {
      v42 = L"SuspendAppQueries";
      v43 = 165;
      goto LABEL_59;
    }
    pcbData = 4;
    v39 = RegGetValueW(a3, a1, L"ImpersonateCaller", 0x18u, &v47, v12 + 9, &pcbData);
    v35 = (const char *)v39;
    if ( v39 == 2 )
    {
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
        (const char *)2,
        (unsigned int)"provider %ws did not have a %ws value",
        (const char *)a1,
        L"ImpersonateCaller");
      goto LABEL_49;
    }
    if ( !v39 )
    {
LABEL_49:
      pcbData = 4;
      v40 = RegGetValueW(a3, a1, L"DynamicUnload", 0x18u, &v47, v12 + 10, &pcbData);
      if ( v40 == 2 )
      {
        wil::details::in1diag3::Log_IfWin32ErrorMsg(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
          (const char *)2,
          (unsigned int)"provider %ws did not have a %ws value",
          (const char *)a1,
          L"DynamicUnload");
      }
      else if ( v40 )
      {
        v20 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0xAB,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                (const char *)v40,
                (unsigned int)"could not read the %ws value for %ws",
                (const char *)L"DynamicUnload",
                a1);
        goto LABEL_55;
      }
      pcbData = 0;
      v41 = RegGetValueW(a3, a1, L"FederatedAepStoreLocations", 0x22u, &v47, 0, &pcbData);
      if ( v41 == 2 || v41 == 234 || !v41 )
      {
        *((_DWORD *)v12 + 19) = v41 != 2;
        *v48 = v12;
        return 0;
      }
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0xB7,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
              (const char *)v41,
              (unsigned int)"could not read the FederatedAepStoreLocations value for %ws",
              (const char *)a1);
      goto LABEL_55;
    }
    v42 = L"ImpersonateCaller";
    v43 = 168;
LABEL_59:
    v20 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)v43,
            (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
            v35,
            (unsigned int)"could not read the %ws value for %ws",
            (const char *)v42,
            a1);
    goto LABEL_55;
  }
  v16 = -1;
  do
    ++v16;
  while ( a1[v16] );
  v17 = 2 * v16 + 2;
  v18 = (unsigned __int16 *)DAF_user_alloc(v17);
  *v12 = v18;
  if ( v18 )
  {
    v9 = StringCbCopyW(v18, v17, a1);
    if ( v9 )
    {
      MIDL_user_free(*v12);
      *v12 = 0;
    }
    if ( (v9 & 0x80000000) == 0 )
      goto LABEL_16;
  }
  else
  {
    v9 = -2147024882;
  }
  v21 = 118;
LABEL_32:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
    (const char *)v9,
    pdwType);
LABEL_56:
  ProviderContext::~ProviderContext((ProviderContext *)v12);
  operator delete(v12, 0xA0u);
  return v9;
}

```

## disassembly

```asm
0x140014fd8  mov     [rsp-8+arg_8], rbx
0x140014fdd  push    rbp
0x140014fde  push    rsi
0x140014fdf  push    rdi
0x140014fe0  push    r12
0x140014fe2  push    r13
0x140014fe4  push    r14
0x140014fe6  push    r15
0x140014fe8  lea     rbp, [rsp-1Fh]
0x140014fed  sub     rsp, 0C0h
0x140014ff4  mov     rax, cs:__security_cookie
0x140014ffb  xor     rax, rsp
0x140014ffe  mov     [rbp+4Fh+var_40], rax
0x140015002  mov     rax, [rbp+4Fh+arg_20]
0x140015006  xor     ebx, ebx
0x140015008  movzx   r12d, r9b
0x14001500c  mov     r14, r8
0x14001500f  mov     [rbp+4Fh+var_A8], rax
0x140015013  mov     r13d, edx
0x140015016  mov     rsi, rcx
0x140015019  test    rax, rax
0x14001501c  jnz     short loc_14001502B
0x14001501e  mov     ebx, 80004003h
0x140015023  lea     edx, [rax+6Fh]
0x140015026  jmp     loc_140015871
0x14001502b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015032  mov     ecx, 0A0h; unsigned __int64
0x140015037  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001503c  mov     rdi, rax
0x14001503f  test    rax, rax
0x140015042  jz      loc_140015867
0x140015048  mov     [rax], rbx
0x14001504b  mov     [rax+28h], rbx
0x14001504f  mov     [rax+30h], rbx
0x140015053  mov     [rax+38h], rbx
0x140015057  mov     [rax+40h], rbx
0x14001505b  mov     [rax+48h], rbx
0x14001505f  mov     [rax+50h], ebx
0x140015062  mov     qword ptr [rax+54h], 1
0x14001506a  mov     [rax+60h], rbx
0x14001506e  mov     [rax+68h], ebx
0x140015071  mov     [rax+70h], rbx
0x140015075  mov     [rax+78h], ebx
0x140015078  mov     [rax+80h], rbx
0x14001507f  mov     [rax+88h], rbx
0x140015086  mov     [rax+90h], rbx
0x14001508d  mov     [rax+98h], rbx
0x140015094  mov     rcx, cs:WPP_GLOBAL_Control
0x14001509b  lea     rax, WPP_GLOBAL_Control
0x1400150a2  cmp     rcx, rax
0x1400150a5  jz      short loc_1400150C5
0x1400150a7  cmp     byte ptr [rcx+19h], 4
0x1400150ab  jb      short loc_1400150C5
0x1400150ad  mov     rcx, [rcx+10h]
0x1400150b1  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x1400150b8  mov     edx, 10h
0x1400150bd  mov     r9, rsi
0x1400150c0  call    WPP_SF_S
0x1400150c5  mov     r15, [rdi]
0x1400150c8  test    r15, r15
0x1400150cb  jz      short loc_1400150F3
0x1400150cd  call    cs:__imp_GetLastError
0x1400150d3  mov     ebx, eax
0x1400150d5  call    cs:__imp_GetProcessHeap
0x1400150db  mov     r8, r15; lpMem
0x1400150de  xor     edx, edx; dwFlags
0x1400150e0  mov     rcx, rax; hHeap
0x1400150e3  call    cs:__imp_HeapFree
0x1400150e9  mov     ecx, ebx; dwErrCode
0x1400150eb  call    cs:__imp_SetLastError
0x1400150f1  xor     ebx, ebx
0x1400150f3  mov     [rdi], rbx
0x1400150f6  test    rsi, rsi
0x1400150f9  jz      short loc_140015151
0x1400150fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400150ff  inc     rax
0x140015102  cmp     [rsi+rax*2], bx
0x140015106  jnz     short loc_1400150FF
0x140015108  lea     rbx, ds:2[rax*2]
0x140015110  mov     rcx, rbx
0x140015113  call    DAF_user_alloc
0x140015118  mov     [rdi], rax
0x14001511b  test    rax, rax
0x14001511e  jz      loc_1400151CA
0x140015124  mov     r8, rsi; unsigned __int16 *
0x140015127  mov     rdx, rbx; unsigned __int64
0x14001512a  mov     rcx, rax; unsigned __int16 *
0x14001512d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140015132  mov     ebx, eax
0x140015134  test    eax, eax
0x140015136  jz      short loc_140015147
0x140015138  mov     rcx, [rdi]; void *
0x14001513b  call    MIDL_user_free
0x140015140  mov     qword ptr [rdi], 0
0x140015147  test    ebx, ebx
0x140015149  js      loc_1400151CF
0x14001514f  xor     ebx, ebx
0x140015151  mov     [rdi+68h], r13d
0x140015155  lea     rcx, [rbp+4Fh+var_A0]; void *
0x140015159  mov     r15d, 52h ; 'R'
0x14001515f  mov     [rdi+54h], r12d
0x140015163  mov     r8d, r15d; Size
0x140015166  xor     edx, edx; Val
0x140015168  call    memset_0
0x14001516d  lea     rax, [rbp+4Fh+var_B0]
0x140015171  mov     [rbp+4Fh+var_AC], ebx
0x140015174  mov     [rsp+0F0h+pcbData], rax; pcbData
0x140015179  lea     r13d, [r15-50h]
0x14001517d  lea     rax, [rbp+4Fh+var_A0]
0x140015181  mov     [rbp+4Fh+var_B0], r15d
0x140015185  mov     [rsp+0F0h+pvData], rax; pvData
0x14001518a  lea     r8, Value; "ProtocolId"
0x140015191  lea     rax, [rbp+4Fh+var_AC]
0x140015195  mov     r9d, r13d; dwFlags
0x140015198  mov     rdx, rsi; lpSubKey
0x14001519b  mov     [rsp+0F0h+pdwType], rax; pdwType
0x1400151a0  mov     rcx, r14; hkey
0x1400151a3  call    cs:__imp_RegGetValueW
0x1400151a9  test    eax, eax
0x1400151ab  jz      short loc_1400151D9
0x1400151ad  lea     rdx, aCouldNotReadTh; "could not read the ProtocolId value for"...
0x1400151b4  mov     [rsp+0F0h+pvData], rsi
0x1400151b9  mov     [rsp+0F0h+pdwType], rdx
0x1400151be  mov     r9d, eax
0x1400151c1  lea     edx, [r15+30h]
0x1400151c5  jmp     loc_14001576C
0x1400151ca  mov     ebx, 8007000Eh
0x1400151cf  mov     edx, 76h ; 'v'
0x1400151d4  jmp     loc_140015336
0x1400151d9  lea     rdx, [rdi+8]; Uuid
0x1400151dd  mov     [rbp+4Fh+var_56], bx
0x1400151e1  lea     rcx, [rbp+4Fh+StringUuid]; StringUuid
0x1400151e5  call    cs:__imp_UuidFromStringW
0x1400151eb  test    eax, eax
0x1400151ed  jz      short loc_14001520D
0x1400151ef  lea     rdx, aCouldNotConver; "could not convert ProtocolId string to "...
0x1400151f6  mov     [rsp+0F0h+pvData], rsi
0x1400151fb  mov     [rsp+0F0h+pdwType], rdx
0x140015200  mov     r9d, eax
0x140015203  mov     edx, 84h
0x140015208  jmp     loc_14001576C
0x14001520d  lea     rax, [rbp+4Fh+var_B0]
0x140015211  mov     [rbp+4Fh+var_B0], r15d
0x140015215  mov     [rsp+0F0h+pcbData], rax; pcbData
0x14001521a  lea     r8, aClsid; "CLSID"
0x140015221  lea     rax, [rbp+4Fh+var_A0]
0x140015225  mov     r9d, r13d; dwFlags
0x140015228  mov     [rsp+0F0h+pvData], rax; pvData
0x14001522d  mov     rdx, rsi; lpSubKey
0x140015230  lea     rax, [rbp+4Fh+var_AC]
0x140015234  mov     rcx, r14; hkey
0x140015237  mov     [rsp+0F0h+pdwType], rax; pdwType
0x14001523c  call    cs:__imp_RegGetValueW
0x140015242  test    eax, eax
0x140015244  jz      short loc_140015264
0x140015246  lea     rdx, aCouldNotReadTh_2; "could not read the CLSID value for %ws"
0x14001524d  mov     [rsp+0F0h+pvData], rsi
0x140015252  mov     [rsp+0F0h+pdwType], rdx
0x140015257  mov     r9d, eax
0x14001525a  mov     edx, 88h
0x14001525f  jmp     loc_14001576C
0x140015264  lea     rdx, [rdi+18h]; Uuid
0x140015268  mov     [rbp+4Fh+var_56], bx
0x14001526c  lea     rcx, [rbp+4Fh+StringUuid]; StringUuid
0x140015270  call    cs:__imp_UuidFromStringW
0x140015276  test    eax, eax
0x140015278  jz      short loc_140015298
0x14001527a  lea     rdx, aCouldNotReadCo; "could not read convert CLSID string to "...
0x140015281  mov     [rsp+0F0h+pvData], rsi
0x140015286  mov     [rsp+0F0h+pdwType], rdx
0x14001528b  mov     r9d, eax
0x14001528e  mov     edx, 8Ah
0x140015293  jmp     loc_14001576C
0x140015298  lea     rax, [rbp+4Fh+var_B0]
0x14001529c  mov     [rbp+4Fh+var_B0], ebx
0x14001529f  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1400152a4  lea     r8, aDllpath; "DllPath"
0x1400152ab  mov     [rsp+0F0h+pvData], rbx; pvData
0x1400152b0  mov     r9d, 0FFFFh; dwFlags
0x1400152b6  mov     rdx, rsi; lpSubKey
0x1400152b9  mov     [rsp+0F0h+pdwType], rbx; int
0x1400152be  mov     rcx, r14; hkey
0x1400152c1  call    cs:__imp_RegGetValueW
0x1400152c7  test    eax, eax
0x1400152c9  jz      short loc_1400152E9
0x1400152cb  lea     rdx, aCouldNotGetSiz; "could not get size for the DllPath valu"...
0x1400152d2  mov     [rsp+0F0h+pvData], rsi
0x1400152d7  mov     [rsp+0F0h+pdwType], rdx
0x1400152dc  mov     r9d, eax
0x1400152df  mov     edx, 8Eh
0x1400152e4  jmp     loc_14001576C
0x1400152e9  mov     ecx, [rbp+4Fh+var_B0]
0x1400152ec  call    DAF_user_alloc
0x1400152f1  mov     r12, [rdi+28h]
0x1400152f5  mov     r15, rax
0x1400152f8  test    r12, r12
0x1400152fb  jz      short loc_140015323
0x1400152fd  call    cs:__imp_GetLastError
0x140015303  mov     ebx, eax
0x140015305  call    cs:__imp_GetProcessHeap
0x14001530b  mov     r8, r12; lpMem
0x14001530e  xor     edx, edx; dwFlags
0x140015310  mov     rcx, rax; hHeap
0x140015313  call    cs:__imp_HeapFree
0x140015319  mov     ecx, ebx; dwErrCode
0x14001531b  call    cs:__imp_SetLastError
0x140015321  xor     ebx, ebx
0x140015323  mov     [rdi+28h], r15
0x140015327  test    r15, r15
0x14001532a  jnz     short loc_14001534E
0x14001532c  mov     ebx, 8007000Eh
0x140015331  mov     edx, 90h; void *
0x140015336  mov     rcx, [rbp+57h]; this
0x14001533a  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\association\\li"...
0x140015341  mov     r9d, ebx; char *
0x140015344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015349  jmp     loc_14001577E
0x14001534e  lea     rax, [rbp+4Fh+var_B0]
0x140015352  mov     r9d, r13d; dwFlags
0x140015355  mov     [rsp+0F0h+pcbData], rax; pcbData
0x14001535a  lea     r8, aDllpath; "DllPath"
0x140015361  lea     rax, [rbp+4Fh+var_AC]
0x140015365  mov     [rsp+0F0h+pvData], r15; pvData
0x14001536a  mov     rdx, rsi; lpSubKey
0x14001536d  mov     [rsp+0F0h+pdwType], rax; pdwType
0x140015372  mov     rcx, r14; hkey
0x140015375  call    cs:__imp_RegGetValueW
0x14001537b  test    eax, eax
0x14001537d  jz      short loc_14001539D
0x14001537f  lea     rdx, aCouldNotReadTh_0; "could not read the DllPath value for %w"...
0x140015386  mov     [rsp+0F0h+pvData], rsi
0x14001538b  mov     [rsp+0F0h+pdwType], rdx
0x140015390  mov     r9d, eax
0x140015393  mov     edx, 91h
0x140015398  jmp     loc_14001576C
0x14001539d  mov     r12d, 4
0x1400153a3  lea     rcx, [rbp+4Fh+var_B0]
0x1400153a7  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x1400153ac  lea     rax, [rdi+30h]
0x1400153b0  mov     [rsp+0F0h+pvData], rax; pvData
0x1400153b5  lea     r8, aSecuritycontex; "SecurityContext"
0x1400153bc  lea     rax, [rbp+4Fh+var_AC]
0x1400153c0  mov     [rbp+4Fh+var_B0], r12d
0x1400153c4  lea     r15d, [r12+14h]
0x1400153c9  mov     [rsp+0F0h+pdwType], rax; pdwType
0x1400153ce  mov     r9d, r15d; dwFlags
0x1400153d1  mov     rdx, rsi; lpSubKey
0x1400153d4  mov     rcx, r14; hkey
0x1400153d7  call    cs:__imp_RegGetValueW
0x1400153dd  test    eax, eax
0x1400153df  jz      short loc_1400153FE
0x1400153e1  lea     rdx, aCouldNotReadTh_3; "could not read the SecurityContext valu"...
0x1400153e8  mov     [rsp+0F0h+pvData], rsi
0x1400153ed  mov     [rsp+0F0h+pdwType], rdx
0x1400153f2  mov     r9d, eax
0x1400153f5  lea     edx, [r15+7Dh]
0x1400153f9  jmp     loc_14001576C
0x1400153fe  lea     rcx, [rbp+4Fh+var_B0]
0x140015402  mov     [rbp+4Fh+var_B0], r12d
0x140015406  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x14001540b  lea     rax, [rdi+34h]
0x14001540f  mov     [rsp+0F0h+pvData], rax; pvData
0x140015414  lea     r8, aPropertyrank; "PropertyRank"
0x14001541b  lea     rax, [rbp+4Fh+var_AC]
0x14001541f  mov     r9d, r15d; dwFlags
0x140015422  mov     rdx, rsi; lpSubKey
0x140015425  mov     [rsp+0F0h+pdwType], rax; pdwType
0x14001542a  mov     rcx, r14; hkey
0x14001542d  call    cs:__imp_RegGetValueW
0x140015433  test    eax, eax
0x140015435  jz      short loc_140015455
0x140015437  lea     rdx, aCouldNotReadTh_4; "could not read the PropertyRank value f"...
0x14001543e  mov     [rsp+0F0h+pvData], rsi
0x140015443  mov     [rsp+0F0h+pdwType], rdx
0x140015448  mov     r9d, eax
0x14001544b  mov     edx, 99h
0x140015450  jmp     loc_14001576C
0x140015455  lea     rcx, [rbp+4Fh+var_B0]
0x140015459  mov     [rbp+4Fh+var_B0], r12d
0x14001545d  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x140015462  lea     rax, [rdi+38h]
0x140015466  mov     [rsp+0F0h+pvData], rax; pvData
0x14001546b  lea     r8, aCapabilities; "Capabilities"
0x140015472  lea     rax, [rbp+4Fh+var_AC]
0x140015476  mov     r9d, r15d; dwFlags
0x140015479  mov     rdx, rsi; lpSubKey
0x14001547c  mov     [rsp+0F0h+pdwType], rax; pdwType
0x140015481  mov     rcx, r14; hkey
0x140015484  call    cs:__imp_RegGetValueW
0x14001548a  lea     r12, aProviderWsDidN; "provider %ws did not have a %ws value"
0x140015491  mov     r9d, eax; char *
0x140015494  cmp     eax, r13d
0x140015497  jnz     loc_140015798
0x14001549d  mov     rcx, [rbp+57h]; this
0x1400154a1  lea     rax, aCapabilities; "Capabilities"
0x1400154a8  mov     [rsp+0F0h+pcbData], rax
0x1400154ad  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\association\\li"...
0x1400154b4  mov     [rsp+0F0h+pvData], rsi; char *
0x1400154b9  mov     r9d, r13d; char *
0x1400154bc  mov     edx, 9Ch; void *
  ... truncated ...
```
