# ProviderContext::MakeAndInitialize(ushort const *,_DAF_PROVIDER_PATH,HKEY__ *,bool,ProviderContext * *)

- ea: `0x180062a50`
- end: `0x1800632b9`
- name: `?MakeAndInitialize@ProviderContext@@SAJPEBGW4_DAF_PROVIDER_PATH@@PEAUHKEY__@@_NPEAPEAV1@@Z`
- size: `2153`
- prototype: `__int64 __fastcall(const WCHAR *, int, HKEY, unsigned __int8, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f930`

## callees

- `0x180009220`
- `0x18001eae0`
- `0x18001fc74`
- `0x18002a948`
- `0x18003aa4c`
- `0x18003bc80`
- `0x18003c79c`
- `0x18003ca3c`
- `0x18005ee9c`
- `0x18005fefc`
- `0x180061c68`
- `0x180062a50`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180062c12`
- `RPCRT4!UuidFromStringW` at `0x180062c94`
- `RPCRT4!UuidFromStringW` at `0x180062c12`
- `RPCRT4!UuidFromStringW` at `0x180062c94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062bcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062c62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062ce3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062d56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062daf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062e05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062e5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062ed3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062f4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062fc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006303b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800630b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063124`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062bcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062c62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062ce3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062d56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062daf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062e05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062e5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062ed3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062f4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180062fc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006303b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800630b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063124`

## string_xrefs

- `0x180062c55`: `CLSID`
- `0x180062bc0`: `ProtocolId`
- `0x180062da2`: `SecurityContext`
- `0x18006302e`: `ImpersonateCaller`
- `0x180063051`: `ImpersonateCaller`
- `0x18006321a`: `ImpersonateCaller`
- `0x180062cd6`: `DllPath`
- `0x180062d49`: `DllPath`
- `0x180062bdc`: `could not read the ProtocolId value for %ws`
- `0x180062c21`: `could not convert ProtocolId string to GUID for %ws`
- `0x180062c71`: `could not read the CLSID value for %ws`
- `0x180062ca3`: `could not read convert CLSID string to GUID for %ws`
- `0x180063185`: `could not read the %ws value for %ws`
- `0x18006314d`: `could not read the FederatedAepStoreLocations value for %ws`
- `0x180062cf2`: `could not get size for the DllPath value for %ws`
- `0x180062d65`: `could not read the DllPath value for %ws`
- `0x180062dbe`: `could not read the SecurityContext value for %ws`
- `0x180062e14`: `could not read the PropertyRank value for %ws`

## pseudocode

```c
__int64 __fastcall ProviderContext::MakeAndInitialize(const WCHAR *a1, int a2, HKEY a3, unsigned __int8 a4, _QWORD *a5)
{
  int v5; // r15d
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned int ValueW; // eax
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rax
  void *v19; // rax
  const char *v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  int pdwType; // [rsp+20h] [rbp-81h]
  const char *pdwTypea; // [rsp+20h] [rbp-81h]
  const char *pvData; // [rsp+28h] [rbp-79h]
  DWORD pcbData; // [rsp+40h] [rbp-61h] BYREF
  DWORD v32; // [rsp+44h] [rbp-5Dh] BYREF
  _QWORD *v33; // [rsp+48h] [rbp-59h] BYREF
  _BYTE v34[2]; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int16 StringUuid[36]; // [rsp+52h] [rbp-4Fh] BYREF
  __int16 v36; // [rsp+9Ah] [rbp-7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v5 = a4;
  if ( a5 )
  {
    v10 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *v10 = 0;
      v10[5] = 0;
      v10[6] = 0;
      v10[7] = 0;
      v10[8] = 0;
      v10[9] = 0;
      *((_DWORD *)v10 + 20) = 0;
      *(_QWORD *)((char *)v10 + 84) = 1;
      v10[12] = 0;
      *((_DWORD *)v10 + 26) = 0;
      v10[14] = 0;
      *((_DWORD *)v10 + 30) = 0;
      v10[16] = 0;
      v10[17] = 0;
      v10[18] = 0;
      v10[19] = 0;
      v33 = v10;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_91edd21030e531619c269f99d7a31287_Traceguids, a1);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v11,
        0);
      v12 = DafStringCopy_2(a1, v11);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = (unsigned int)v12;
        v14 = 118;
LABEL_61:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
          (const char *)v13,
          pdwType);
        goto LABEL_62;
      }
      *((_DWORD *)v11 + 26) = a2;
      *((_DWORD *)v11 + 21) = v5;
      memset_0(v34, 0, 0x52u);
      v32 = 0;
      pcbData = 82;
      ValueW = RegGetValueW(a3, a1, L"ProtocolId", 2u, &v32, v34, &pcbData);
      if ( ValueW )
      {
        pvData = (const char *)a1;
        pdwTypea = "could not read the ProtocolId value for %ws";
        v16 = 130;
        goto LABEL_11;
      }
      v36 = 0;
      ValueW = UuidFromStringW(StringUuid, (UUID *)(v11 + 1));
      if ( ValueW )
      {
        pvData = (const char *)a1;
        pdwTypea = "could not convert ProtocolId string to GUID for %ws";
        v16 = 132;
        goto LABEL_11;
      }
      pcbData = 82;
      ValueW = RegGetValueW(a3, a1, L"CLSID", 2u, &v32, v34, &pcbData);
      if ( ValueW )
      {
        pvData = (const char *)a1;
        pdwTypea = "could not read the CLSID value for %ws";
        v16 = 136;
        goto LABEL_11;
      }
      v36 = 0;
      ValueW = UuidFromStringW(StringUuid, (UUID *)(v11 + 3));
      if ( ValueW )
      {
        pvData = (const char *)a1;
        pdwTypea = "could not read convert CLSID string to GUID for %ws";
        v16 = 138;
        goto LABEL_11;
      }
      pcbData = 0;
      ValueW = RegGetValueW(a3, a1, L"DllPath", 0xFFFFu, 0, 0, &pcbData);
      if ( ValueW )
      {
        pvData = (const char *)a1;
        pdwTypea = "could not get size for the DllPath value for %ws";
        v16 = 142;
        goto LABEL_11;
      }
      v18 = DAF_user_alloc(pcbData);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v11 + 5,
        v18);
      v19 = (void *)v11[5];
      if ( v19 )
      {
        ValueW = RegGetValueW(a3, a1, L"DllPath", 2u, &v32, v19, &pcbData);
        if ( ValueW )
        {
          pvData = (const char *)a1;
          pdwTypea = "could not read the DllPath value for %ws";
          v16 = 145;
        }
        else
        {
          pcbData = 4;
          ValueW = RegGetValueW(a3, a1, L"SecurityContext", 0x18u, &v32, v11 + 6, &pcbData);
          if ( ValueW )
          {
            pvData = (const char *)a1;
            pdwTypea = "could not read the SecurityContext value for %ws";
            v16 = 149;
          }
          else
          {
            pcbData = 4;
            ValueW = RegGetValueW(a3, a1, L"PropertyRank", 0x18u, &v32, (char *)v11 + 52, &pcbData);
            if ( !ValueW )
            {
              pcbData = 4;
              v20 = (const char *)(unsigned int)RegGetValueW(a3, a1, L"Capabilities", 0x18u, &v32, v11 + 7, &pcbData);
              if ( (_DWORD)v20 == 2 )
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
              else if ( (_DWORD)v20 )
              {
                v17 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0x9C,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                        v20,
                        (unsigned int)"could not read the %ws value for %ws",
                        (const char *)L"Capabilities",
                        a1);
                goto LABEL_12;
              }
              pcbData = 4;
              v21 = RegGetValueW(a3, a1, L"AllowReassociation", 0x18u, &v32, (char *)v11 + 60, &pcbData);
              if ( v21 == 2 )
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
              else if ( v21 )
              {
                v17 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0x9F,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                        (const char *)v21,
                        (unsigned int)"could not read the %ws value for %ws",
                        (const char *)L"AllowReassociation",
                        a1);
                goto LABEL_12;
              }
              pcbData = 4;
              v22 = RegGetValueW(a3, a1, L"SyncSetAssociations", 0x18u, &v32, v11 + 8, &pcbData);
              if ( v22 == 2 )
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
              else if ( v22 )
              {
                v17 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0xA2,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                        (const char *)v22,
                        (unsigned int)"could not read the %ws value for %ws",
                        (const char *)L"SyncSetAssociations",
                        a1);
                goto LABEL_12;
              }
              pcbData = 4;
              v23 = RegGetValueW(a3, a1, L"SuspendAppQueries", 0x18u, &v32, (char *)v11 + 68, &pcbData);
              if ( v23 == 2 )
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
              else if ( v23 )
              {
                v17 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0xA5,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                        (const char *)v23,
                        (unsigned int)"could not read the %ws value for %ws",
                        (const char *)L"SuspendAppQueries",
                        a1);
                goto LABEL_12;
              }
              pcbData = 4;
              v24 = RegGetValueW(a3, a1, L"ImpersonateCaller", 0x18u, &v32, v11 + 9, &pcbData);
              if ( v24 == 2 )
              {
                wil::details::in1diag3::Log_IfWin32ErrorMsg(
                  retaddr,
                  (void *)0xA8,
                  (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                  (const char *)2,
                  (unsigned int)"provider %ws did not have a %ws value",
                  (const char *)a1,
                  L"ImpersonateCaller");
              }
              else if ( v24 )
              {
                v17 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0xA8,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                        (const char *)v24,
                        (unsigned int)"could not read the %ws value for %ws",
                        (const char *)L"ImpersonateCaller",
                        a1);
                goto LABEL_12;
              }
              pcbData = 4;
              v25 = RegGetValueW(a3, a1, L"DynamicUnload", 0x18u, &v32, v11 + 10, &pcbData);
              if ( v25 == 2 )
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
              else if ( v25 )
              {
                v17 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0xAB,
                        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                        (const char *)v25,
                        (unsigned int)"could not read the %ws value for %ws",
                        (const char *)L"DynamicUnload",
                        a1);
                goto LABEL_12;
              }
              pcbData = 0;
              v26 = RegGetValueW(a3, a1, L"FederatedAepStoreLocations", 0x22u, &v32, 0, &pcbData);
              if ( v26 == 2 || v26 == 234 || !v26 )
              {
                *((_DWORD *)v11 + 19) = v26 != 2;
                v33 = 0;
                *a5 = v11;
                v9 = 0;
                goto LABEL_62;
              }
              v17 = wil::details::in1diag3::Return_Win32Msg(
                      retaddr,
                      (void *)0xB7,
                      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                      (const char *)v26,
                      (unsigned int)"could not read the FederatedAepStoreLocations value for %ws",
                      (const char *)a1);
LABEL_12:
              v9 = v17;
LABEL_62:
              std::_Temporary_owner<ProviderContext>::~_Temporary_owner<ProviderContext>(&v33);
              return v9;
            }
            pvData = (const char *)a1;
            pdwTypea = "could not read the PropertyRank value for %ws";
            v16 = 153;
          }
        }
LABEL_11:
        v17 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)v16,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
                (const char *)ValueW,
                (unsigned int)pdwTypea,
                pvData);
        goto LABEL_12;
      }
      v14 = 144;
    }
    else
    {
      v33 = 0;
      v14 = 113;
    }
    v9 = -2147024882;
    v13 = 2147942414LL;
    goto LABEL_61;
  }
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6F,
    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providercontext.cpp",
    (const char *)0x80004003LL,
    pdwType);
  return v9;
}

```

## disassembly

```asm
0x180062a50  mov     [rsp-8+arg_8], rbx
0x180062a55  push    rbp
0x180062a56  push    rsi
0x180062a57  push    rdi
0x180062a58  push    r12
0x180062a5a  push    r13
0x180062a5c  push    r14
0x180062a5e  push    r15
0x180062a60  lea     rbp, [rsp-1Fh]
0x180062a65  sub     rsp, 0C0h
0x180062a6c  mov     rax, cs:__security_cookie
0x180062a73  xor     rax, rsp
0x180062a76  mov     [rbp+4Fh+var_40], rax
0x180062a7a  movzx   r15d, r9b
0x180062a7e  mov     r14, r8
0x180062a81  mov     r12d, edx
0x180062a84  mov     rsi, rcx
0x180062a87  mov     r13, [rbp+4Fh+arg_20]
0x180062a8b  xor     ebx, ebx
0x180062a8d  test    r13, r13
0x180062a90  jnz     short loc_180062AB3
0x180062a92  mov     rcx, [rbp+57h]; this
0x180062a96  mov     ebx, 80004003h
0x180062a9b  mov     r9d, ebx; char *
0x180062a9e  lea     r8, aOnecoreBaseDev_13; "onecore\\base\\devices\\association\\li"...
0x180062aa5  lea     edx, [r13+6Fh]; void *
0x180062aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062aae  jmp     loc_180063290
0x180062ab3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180062aba  mov     ecx, 0A0h; unsigned __int64
0x180062abf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180062ac4  mov     rdi, rax
0x180062ac7  test    rax, rax
0x180062aca  jz      loc_180063266
0x180062ad0  mov     [rax], rbx
0x180062ad3  mov     [rax+28h], rbx
0x180062ad7  mov     [rax+30h], rbx
0x180062adb  mov     [rax+38h], rbx
0x180062adf  mov     [rax+40h], rbx
0x180062ae3  mov     [rax+48h], rbx
0x180062ae7  mov     [rax+50h], ebx
0x180062aea  mov     qword ptr [rax+54h], 1
0x180062af2  mov     [rax+60h], rbx
0x180062af6  mov     [rax+68h], ebx
0x180062af9  mov     [rax+70h], rbx
0x180062afd  mov     [rax+78h], ebx
0x180062b00  mov     [rax+80h], rbx
0x180062b07  mov     [rax+88h], rbx
0x180062b0e  mov     [rax+90h], rbx
0x180062b15  mov     [rax+98h], rbx
0x180062b1c  mov     [rbp+4Fh+var_A8], rax
0x180062b20  lea     rax, WPP_GLOBAL_Control
0x180062b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180062b2e  cmp     rcx, rax
0x180062b31  jz      short loc_180062B51
0x180062b33  cmp     byte ptr [rcx+19h], 4
0x180062b37  jb      short loc_180062B51
0x180062b39  mov     edx, 10h
0x180062b3e  mov     r9, rsi
0x180062b41  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x180062b48  mov     rcx, [rcx+10h]
0x180062b4c  call    WPP_SF_S
0x180062b51  xor     edx, edx
0x180062b53  mov     rcx, rdi
0x180062b56  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180062b5b  mov     rdx, rdi
0x180062b5e  mov     rcx, rsi
0x180062b61  call    DafStringCopy_2
0x180062b66  mov     ebx, eax
0x180062b68  test    eax, eax
0x180062b6a  jns     short loc_180062B79
0x180062b6c  mov     r9d, eax
0x180062b6f  mov     edx, 76h ; 'v'
0x180062b74  jmp     loc_180063277
0x180062b79  mov     [rdi+68h], r12d
0x180062b7d  mov     [rdi+54h], r15d
0x180062b81  mov     ebx, 52h ; 'R'
0x180062b86  mov     r8d, ebx; Size
0x180062b89  xor     edx, edx; Val
0x180062b8b  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180062b8f  call    memset_0
0x180062b94  xor     r15d, r15d
0x180062b97  mov     [rbp+4Fh+var_AC], r15d
0x180062b9b  mov     [rbp+4Fh+var_B0], ebx
0x180062b9e  lea     rax, [rbp+4Fh+var_B0]
0x180062ba2  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180062ba7  lea     rax, [rbp+4Fh+var_A0]
0x180062bab  mov     [rsp+0F0h+pvData], rax; pvData
0x180062bb0  lea     rax, [rbp+4Fh+var_AC]
0x180062bb4  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062bb9  lea     r12d, [rbx-50h]
0x180062bbd  mov     r9d, r12d; dwFlags
0x180062bc0  lea     r8, aProtocolid; "ProtocolId"
0x180062bc7  mov     rdx, rsi; lpSubKey
0x180062bca  mov     rcx, r14; hkey
0x180062bcd  call    cs:__imp_RegGetValueW
0x180062bd3  test    eax, eax
0x180062bd5  jz      short loc_180062C05
0x180062bd7  mov     [rsp+0F0h+pvData], rsi; char *
0x180062bdc  lea     rdx, aCouldNotReadTh; "could not read the ProtocolId value for"...
0x180062be3  mov     [rsp+0F0h+pdwType], rdx; unsigned int
0x180062be8  lea     edx, [rbx+30h]; void *
0x180062beb  mov     r9d, eax; char *
0x180062bee  mov     rcx, [rbp+57h]; this
0x180062bf2  lea     r8, aOnecoreBaseDev_13; "onecore\\base\\devices\\association\\li"...
0x180062bf9  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180062bfe  mov     ebx, eax
0x180062c00  jmp     loc_180063287
0x180062c05  mov     [rbp+4Fh+var_56], r15w
0x180062c0a  lea     rdx, [rdi+8]; Uuid
0x180062c0e  lea     rcx, [rbp+4Fh+StringUuid]; StringUuid
0x180062c12  call    cs:__imp_UuidFromStringW
0x180062c18  test    eax, eax
0x180062c1a  jz      short loc_180062C34
0x180062c1c  mov     [rsp+0F0h+pvData], rsi
0x180062c21  lea     rdx, aCouldNotConver; "could not convert ProtocolId string to "...
0x180062c28  mov     [rsp+0F0h+pdwType], rdx
0x180062c2d  mov     edx, 84h
0x180062c32  jmp     short loc_180062BEB
0x180062c34  mov     [rbp+4Fh+var_B0], ebx
0x180062c37  lea     rax, [rbp+4Fh+var_B0]
0x180062c3b  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180062c40  lea     rax, [rbp+4Fh+var_A0]
0x180062c44  mov     [rsp+0F0h+pvData], rax; pvData
0x180062c49  lea     rax, [rbp+4Fh+var_AC]
0x180062c4d  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062c52  mov     r9d, r12d; dwFlags
0x180062c55  lea     r8, ValueName; "CLSID"
0x180062c5c  mov     rdx, rsi; lpSubKey
0x180062c5f  mov     rcx, r14; hkey
0x180062c62  call    cs:__imp_RegGetValueW
0x180062c68  test    eax, eax
0x180062c6a  jz      short loc_180062C87
0x180062c6c  mov     [rsp+0F0h+pvData], rsi
0x180062c71  lea     rdx, aCouldNotReadTh_2; "could not read the CLSID value for %ws"
0x180062c78  mov     [rsp+0F0h+pdwType], rdx
0x180062c7d  mov     edx, 88h
0x180062c82  jmp     loc_180062BEB
0x180062c87  mov     [rbp+4Fh+var_56], r15w
0x180062c8c  lea     rdx, [rdi+18h]; Uuid
0x180062c90  lea     rcx, [rbp+4Fh+StringUuid]; StringUuid
0x180062c94  call    cs:__imp_UuidFromStringW
0x180062c9a  test    eax, eax
0x180062c9c  jz      short loc_180062CB9
0x180062c9e  mov     [rsp+0F0h+pvData], rsi
0x180062ca3  lea     rdx, aCouldNotReadCo; "could not read convert CLSID string to "...
0x180062caa  mov     [rsp+0F0h+pdwType], rdx
0x180062caf  mov     edx, 8Ah
0x180062cb4  jmp     loc_180062BEB
0x180062cb9  mov     [rbp+4Fh+var_B0], r15d
0x180062cbd  lea     rax, [rbp+4Fh+var_B0]
0x180062cc1  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180062cc6  mov     [rsp+0F0h+pvData], r15; pvData
0x180062ccb  mov     [rsp+0F0h+pdwType], r15; pdwType
0x180062cd0  mov     r9d, 0FFFFh; dwFlags
0x180062cd6  lea     r8, aDllpath; "DllPath"
0x180062cdd  mov     rdx, rsi; lpSubKey
0x180062ce0  mov     rcx, r14; hkey
0x180062ce3  call    cs:__imp_RegGetValueW
0x180062ce9  test    eax, eax
0x180062ceb  jz      short loc_180062D08
0x180062ced  mov     [rsp+0F0h+pvData], rsi
0x180062cf2  lea     rdx, aCouldNotGetSiz; "could not get size for the DllPath valu"...
0x180062cf9  mov     [rsp+0F0h+pdwType], rdx
0x180062cfe  mov     edx, 8Eh
0x180062d03  jmp     loc_180062BEB
0x180062d08  mov     ecx, [rbp+4Fh+var_B0]
0x180062d0b  call    DAF_user_alloc
0x180062d10  mov     rdx, rax
0x180062d13  lea     rcx, [rdi+28h]
0x180062d17  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180062d1c  mov     rax, [rdi+28h]
0x180062d20  test    rax, rax
0x180062d23  jnz     short loc_180062D2F
0x180062d25  mov     edx, 90h
0x180062d2a  jmp     loc_18006326F
0x180062d2f  lea     rcx, [rbp+4Fh+var_B0]
0x180062d33  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x180062d38  mov     [rsp+0F0h+pvData], rax; pvData
0x180062d3d  lea     rax, [rbp+4Fh+var_AC]
0x180062d41  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062d46  mov     r9d, r12d; dwFlags
0x180062d49  lea     r8, aDllpath; "DllPath"
0x180062d50  mov     rdx, rsi; lpSubKey
0x180062d53  mov     rcx, r14; hkey
0x180062d56  call    cs:__imp_RegGetValueW
0x180062d5c  test    eax, eax
0x180062d5e  jz      short loc_180062D7B
0x180062d60  mov     [rsp+0F0h+pvData], rsi
0x180062d65  lea     rdx, aCouldNotReadTh_0; "could not read the DllPath value for %w"...
0x180062d6c  mov     [rsp+0F0h+pdwType], rdx
0x180062d71  mov     edx, 91h
0x180062d76  jmp     loc_180062BEB
0x180062d7b  mov     ebx, 4
0x180062d80  mov     [rbp+4Fh+var_B0], ebx
0x180062d83  lea     rax, [rdi+30h]
0x180062d87  lea     rcx, [rbp+4Fh+var_B0]
0x180062d8b  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x180062d90  mov     [rsp+0F0h+pvData], rax; pvData
0x180062d95  lea     rax, [rbp+4Fh+var_AC]
0x180062d99  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062d9e  lea     r9d, [rbx+14h]; dwFlags
0x180062da2  lea     r8, aSecuritycontex; "SecurityContext"
0x180062da9  mov     rdx, rsi; lpSubKey
0x180062dac  mov     rcx, r14; hkey
0x180062daf  call    cs:__imp_RegGetValueW
0x180062db5  test    eax, eax
0x180062db7  jz      short loc_180062DD4
0x180062db9  mov     [rsp+0F0h+pvData], rsi
0x180062dbe  lea     rdx, aCouldNotReadTh_3; "could not read the SecurityContext valu"...
0x180062dc5  mov     [rsp+0F0h+pdwType], rdx
0x180062dca  mov     edx, 95h
0x180062dcf  jmp     loc_180062BEB
0x180062dd4  mov     [rbp+4Fh+var_B0], ebx
0x180062dd7  lea     rax, [rdi+34h]
0x180062ddb  lea     rcx, [rbp+4Fh+var_B0]
0x180062ddf  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x180062de4  mov     [rsp+0F0h+pvData], rax; pvData
0x180062de9  lea     rax, [rbp+4Fh+var_AC]
0x180062ded  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062df2  mov     r9d, 18h; dwFlags
0x180062df8  lea     r8, aPropertyrank; "PropertyRank"
0x180062dff  mov     rdx, rsi; lpSubKey
0x180062e02  mov     rcx, r14; hkey
0x180062e05  call    cs:__imp_RegGetValueW
0x180062e0b  test    eax, eax
0x180062e0d  jz      short loc_180062E2A
0x180062e0f  mov     [rsp+0F0h+pvData], rsi
0x180062e14  lea     rdx, aCouldNotReadTh_4; "could not read the PropertyRank value f"...
0x180062e1b  mov     [rsp+0F0h+pdwType], rdx
0x180062e20  mov     edx, 99h
0x180062e25  jmp     loc_180062BEB
0x180062e2a  mov     [rbp+4Fh+var_B0], ebx
0x180062e2d  lea     rax, [rdi+38h]
0x180062e31  lea     rcx, [rbp+4Fh+var_B0]
0x180062e35  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x180062e3a  mov     [rsp+0F0h+pvData], rax; pvData
0x180062e3f  lea     rax, [rbp+4Fh+var_AC]
0x180062e43  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062e48  mov     r9d, 18h; dwFlags
0x180062e4e  lea     r8, aCapabilities; "Capabilities"
0x180062e55  mov     rdx, rsi; lpSubKey
0x180062e58  mov     rcx, r14; hkey
0x180062e5b  call    cs:__imp_RegGetValueW
0x180062e61  mov     r9d, eax; char *
0x180062e64  lea     rax, aProviderWsDidN; "provider %ws did not have a %ws value"
0x180062e6b  cmp     r9d, r12d
0x180062e6e  jnz     loc_180063166
0x180062e74  mov     rcx, [rbp+57h]; this
0x180062e78  lea     rdx, aCapabilities; "Capabilities"
0x180062e7f  mov     [rsp+0F0h+pcbData], rdx
0x180062e84  mov     [rsp+0F0h+pvData], rsi; char *
0x180062e89  mov     [rsp+0F0h+pdwType], rax; unsigned int
0x180062e8e  mov     r9d, r12d; char *
0x180062e91  lea     r8, aOnecoreBaseDev_13; "onecore\\base\\devices\\association\\li"...
0x180062e98  mov     edx, 9Ch; void *
0x180062e9d  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180062ea2  mov     [rbp+4Fh+var_B0], ebx
0x180062ea5  lea     rax, [rdi+3Ch]
0x180062ea9  lea     rcx, [rbp+4Fh+var_B0]
0x180062ead  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x180062eb2  mov     [rsp+0F0h+pvData], rax; pvData
0x180062eb7  lea     rax, [rbp+4Fh+var_AC]
0x180062ebb  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062ec0  mov     r9d, 18h; dwFlags
0x180062ec6  lea     r8, aAllowreassocia; "AllowReassociation"
0x180062ecd  mov     rdx, rsi; lpSubKey
0x180062ed0  mov     rcx, r14; hkey
0x180062ed3  call    cs:__imp_RegGetValueW
0x180062ed9  mov     r9d, eax
0x180062edc  cmp     eax, r12d
0x180062edf  jnz     loc_1800631A6
0x180062ee5  mov     rcx, [rbp+57h]; this
0x180062ee9  lea     rax, aAllowreassocia; "AllowReassociation"
0x180062ef0  mov     [rsp+0F0h+pcbData], rax
0x180062ef5  mov     [rsp+0F0h+pvData], rsi; char *
0x180062efa  lea     rax, aProviderWsDidN; "provider %ws did not have a %ws value"
0x180062f01  mov     [rsp+0F0h+pdwType], rax; unsigned int
0x180062f06  mov     r9d, r12d; char *
0x180062f09  lea     r8, aOnecoreBaseDev_13; "onecore\\base\\devices\\association\\li"...
0x180062f10  mov     edx, 9Fh; void *
0x180062f15  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180062f1a  mov     [rbp+4Fh+var_B0], ebx
0x180062f1d  lea     rax, [rdi+40h]
0x180062f21  lea     rcx, [rbp+4Fh+var_B0]
0x180062f25  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x180062f2a  mov     [rsp+0F0h+pvData], rax; pvData
0x180062f2f  lea     rax, [rbp+4Fh+var_AC]
0x180062f33  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180062f38  mov     r9d, 18h; dwFlags
0x180062f3e  lea     r8, aSyncsetassocia; "SyncSetAssociations"
0x180062f45  mov     rdx, rsi; lpSubKey
0x180062f48  mov     rcx, r14; hkey
0x180062f4b  call    cs:__imp_RegGetValueW
0x180062f51  mov     r9d, eax
0x180062f54  cmp     eax, r12d
0x180062f57  jnz     loc_1800631C7
0x180062f5d  mov     rcx, [rbp+57h]; this
0x180062f61  lea     rax, aSyncsetassocia; "SyncSetAssociations"
0x180062f68  mov     [rsp+0F0h+pcbData], rax
  ... truncated ...
```
