# LPA::EsimManager::UpdateServiceTriggerEvent(bool)

- ea: `0x180096544`
- end: `0x1800968ac`
- name: `?UpdateServiceTriggerEvent@EsimManager@LPA@@AEAAX_N@Z`
- size: `872`
- prototype: `void __fastcall(LPA::EsimManager *__hidden this, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180087c60`
- `0x180088714`
- `0x18008d320`

## callees

- `0x1800017c8`
- `0x1800018b4`
- `0x18000df90`
- `0x18005e224`
- `0x18008596c`
- `0x180096544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800965ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800967a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800965ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800967a8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180096587`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180096587`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009661b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009661b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18009679c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18009679c`

## string_xrefs

- `0x1800965ca`: `LpaServiceEsimManager`
- `0x1800967d7`: `LpaServiceEsimManager`
- `0x180096834`: `LpaServiceEsimManager`
- `0x1800965be`: `LPA::EsimManager::UpdateServiceTriggerEvent`
- `0x1800967cb`: `LPA::EsimManager::UpdateServiceTriggerEvent`
- `0x18009681d`: `LPA::EsimManager::UpdateServiceTriggerEvent`

## pseudocode

```c
void __fastcall LPA::EsimManager::UpdateServiceTriggerEvent(LPA::EsimManager *this, unsigned __int8 a2)
{
  DWORD v2; // esi
  SC_HANDLE v3; // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // r14d
  DWORD LastError; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 *v12; // rdx
  __int64 v13; // rax
  BOOL v14; // ecx
  int v15; // r8d
  int v16; // r9d
  DWORD v17; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v18; // [rsp+44h] [rbp-BCh] BYREF
  const char *v19; // [rsp+48h] [rbp-B8h] BYREF
  const char *v20; // [rsp+50h] [rbp-B0h] BYREF
  SC_HANDLE v21; // [rsp+58h] [rbp-A8h] BYREF
  SC_HANDLE v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v25[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v26; // [rsp+80h] [rbp-80h]
  _DWORD v27[2]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD *v28; // [rsp+90h] [rbp-70h]
  _DWORD v29[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 *p_Destination; // [rsp+A0h] [rbp-60h]
  _DWORD Info[2]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h] BYREF
  __int64 Destination; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v36[2]; // [rsp+D0h] [rbp-30h] BYREF
  const GUID *v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+E0h] [rbp-20h]
  _DWORD *v39; // [rsp+E8h] [rbp-18h]
  int v40; // [rsp+F0h] [rbp-10h]
  int v41; // [rsp+F4h] [rbp-Ch]
  const GUID *v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+100h] [rbp+0h]
  _DWORD *v44; // [rsp+108h] [rbp+8h]
  int v45; // [rsp+110h] [rbp+10h]
  int v46; // [rsp+114h] [rbp+14h]
  const GUID *v47; // [rsp+118h] [rbp+18h]
  int v48; // [rsp+120h] [rbp+20h]
  _DWORD *v49; // [rsp+128h] [rbp+28h]
  _OWORD v50[3]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v51[2]; // [rsp+160h] [rbp+60h]

  v2 = a2;
  v24 = 0;
  v23 = 0;
  v3 = OpenSCManagerW(0, 0, 5u);
  v22 = v3;
  if ( v3 )
  {
    v7 = 3;
    v21 = OpenServiceW(v3, L"wlpasvc", 3u);
    if ( v21 )
    {
      Destination = 0;
      memcpy_s(&Destination, 8u, &WNF_NLM_INTERNET_PRESENT, 8u);
      v34 = 0;
      memcpy_s(&v34, 8u, &WNF_WWAN_EUICC_ARRIVAL, 8u);
      v50[0] = *(_OWORD *)L"4f4fa786-2f8f-49e8-8aae-6669febd5d1d";
      v26 = &v34;
      v50[2] = *(_OWORD *)L"e8-8aae-6669febd5d1d";
      p_Destination = &Destination;
      v13 = -1;
      v50[1] = *(_OWORD *)L"-2f8f-49e8-8aae-6669febd5d1d";
      v51[0] = *(_OWORD *)L"6669febd5d1d";
      *(_OWORD *)((char *)v51 + 10) = *(_OWORD *)L"ebd5d1d";
      v25[0] = 1;
      v25[1] = 8;
      v29[0] = 1;
      v29[1] = 8;
      v27[0] = 2;
      do
        ++v13;
      while ( *((_WORD *)v50 + v13) );
      v36[1] = 1;
      v27[1] = 2 * v13 + 2;
      v37 = &CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID;
      v36[0] = 7;
      v28 = v50;
      v39 = v25;
      v42 = &RPC_INTERFACE_EVENT_GUID;
      v44 = v27;
      v49 = v29;
      Info[1] = 0;
      v38 = 1;
      if ( !(_BYTE)v2 )
        v7 = 2;
      v41 = 1;
      v43 = 1;
      v45 = 7;
      v46 = 1;
      v47 = &CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID;
      v48 = 1;
      Info[0] = v7;
      v40 = 6;
      v32 = v36;
      v33 = 0;
      v14 = ChangeServiceConfig2W(v21, 8u, Info);
      if ( v14 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v17 = v14;
          v20 = "LPA::EsimManager::UpdateServiceTriggerEvent";
          v19 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v14,
            (unsigned int)&byte_18012D197,
            v15,
            v16,
            (__int64)&v19,
            (__int64)&v20,
            (__int64)&v17);
        }
        goto LABEL_17;
      }
      LastError = GetLastError();
      v9 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v17 = v2;
        v12 = (__int64 *)byte_18012D1E3;
        goto LABEL_14;
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v17 = v2;
      LastError = GetLastError();
      v12 = qword_18012D248;
LABEL_14:
      v18 = LastError;
      v20 = "LPA::EsimManager::UpdateServiceTriggerEvent";
      v19 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (_DWORD)v12,
        v10,
        v11,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v18,
        (__int64)&v17);
    }
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v21);
    goto LABEL_18;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v18 = v2;
    v17 = GetLastError();
    v19 = "LPA::EsimManager::UpdateServiceTriggerEvent";
    v20 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)byte_18012D29D,
      v5,
      v6,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v17,
      (__int64)&v18);
  }
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v22);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v23);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v24);
}

```

## disassembly

```asm
0x180096544  push    rbp
0x180096546  push    rbx
0x180096547  push    rsi
0x180096548  push    rdi
0x180096549  push    r12
0x18009654b  push    r14
0x18009654d  push    r15
0x18009654f  lea     rbp, [rsp-90h]
0x180096557  sub     rsp, 190h
0x18009655e  mov     rax, cs:__security_cookie
0x180096565  xor     rax, rsp
0x180096568  mov     [rbp+0C0h+var_40], rax
0x18009656f  xor     r15d, r15d
0x180096572  movzx   esi, dl
0x180096575  xor     edx, edx; lpDatabaseName
0x180096577  mov     [rsp+1C0h+var_150], r15
0x18009657c  xor     ecx, ecx; lpMachineName
0x18009657e  mov     [rsp+1C0h+var_158], r15
0x180096583  lea     r8d, [r15+5]; dwDesiredAccess
0x180096587  call    cs:__imp_OpenSCManagerW
0x18009658d  mov     [rsp+1C0h+var_160], rax
0x180096592  test    rax, rax
0x180096595  jnz     short loc_180096608
0x180096597  mov     eax, cs:CallbackContext
0x18009659d  lea     edi, [r15+2]
0x1800965a1  cmp     eax, edi
0x1800965a3  jbe     loc_18009686D
0x1800965a9  mov     [rsp+1C0h+var_17C], esi
0x1800965ad  call    cs:__imp_GetLastError
0x1800965b3  mov     [rsp+1C0h+var_180], eax
0x1800965b7  lea     rdx, byte_18012D29D
0x1800965be  lea     rax, aLpaEsimmanager_16; "LPA::EsimManager::UpdateServiceTriggerE"...
0x1800965c5  mov     [rsp+1C0h+var_178], rax
0x1800965ca  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x1800965d1  mov     [rsp+1C0h+var_170], rax
0x1800965d6  lea     rax, [rsp+1C0h+var_17C]
0x1800965db  mov     [rsp+1C0h+var_188], rax
0x1800965e0  lea     rax, [rsp+1C0h+var_180]
0x1800965e5  mov     [rsp+1C0h+var_190], rax
0x1800965ea  lea     rax, [rsp+1C0h+var_178]
0x1800965ef  mov     [rsp+1C0h+var_198], rax
0x1800965f4  lea     rax, [rsp+1C0h+var_170]
0x1800965f9  mov     [rsp+1C0h+var_1A0], rax
0x1800965fe  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180096603  jmp     loc_18009686D
0x180096608  mov     r14d, 3
0x18009660e  lea     rdx, ServiceName; "wlpasvc"
0x180096615  mov     r8d, r14d; dwDesiredAccess
0x180096618  mov     rcx, rax; hSCManager
0x18009661b  call    cs:__imp_OpenServiceW
0x180096621  mov     [rsp+1C0h+var_168], rax
0x180096626  mov     rbx, rax
0x180096629  test    rax, rax
0x18009662c  jnz     short loc_180096655
0x18009662e  mov     eax, cs:CallbackContext
0x180096634  lea     edi, [rbx+2]
0x180096637  cmp     eax, edi
0x180096639  jbe     loc_180096863
0x18009663f  mov     [rsp+1C0h+var_180], esi
0x180096643  call    cs:__imp_GetLastError
0x180096649  lea     rdx, qword_18012D248
0x180096650  jmp     loc_1800967C7
0x180096655  mov     r12d, 8
0x18009665b  mov     [rbp+0C0h+Destination], r15
0x18009665f  mov     r9d, r12d; SourceSize
0x180096662  lea     r8, WNF_NLM_INTERNET_PRESENT; Source
0x180096669  mov     edx, r12d; DestinationSize
0x18009666c  lea     rcx, [rbp+0C0h+Destination]; Destination
0x180096670  call    memcpy_s
0x180096675  mov     r9d, r12d; SourceSize
0x180096678  mov     [rbp+0C0h+var_100], r15
0x18009667c  lea     r8, WNF_WWAN_EUICC_ARRIVAL; Source
0x180096683  mov     edx, r12d; DestinationSize
0x180096686  lea     rcx, [rbp+0C0h+var_100]; Destination
0x18009668a  call    memcpy_s
0x18009668f  movaps  xmm0, xmmword ptr cs:a4f4fa7862f8f49; "4f4fa786-2f8f-49e8-8aae-6669febd5d1d"
0x180096696  lea     rax, [rbp+0C0h+var_100]
0x18009669a  movaps  xmm1, xmmword ptr cs:a4f4fa7862f8f49+10h; "-2f8f-49e8-8aae-6669febd5d1d"
0x1800966a1  lea     r8d, [r12-7]
0x1800966a6  movaps  [rbp+0C0h+var_90], xmm0
0x1800966aa  lea     edi, [r12-6]
0x1800966af  movaps  xmm0, xmmword ptr cs:a4f4fa7862f8f49+20h; "e8-8aae-6669febd5d1d"
0x1800966b6  lea     rcx, [rbp+0C0h+var_90]
0x1800966ba  mov     [rbp+0C0h+var_140], rax
0x1800966be  lea     rax, [rbp+0C0h+Destination]
0x1800966c2  movaps  [rbp+0C0h+var_70], xmm0
0x1800966c6  movups  xmm0, xmmword ptr cs:a4f4fa7862f8f49+3Ah; "ebd5d1d"
0x1800966cd  mov     [rbp+0C0h+var_120], rax
0x1800966d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800966d5  movaps  [rbp+0C0h+var_80], xmm1
0x1800966d9  movaps  xmm1, xmmword ptr cs:a4f4fa7862f8f49+30h; "6669febd5d1d"
0x1800966e0  movaps  xmmword ptr [rbp+0C0h+var_60], xmm1
0x1800966e4  movups  xmmword ptr [rbp+0C0h+var_60+0Ah], xmm0
0x1800966e8  mov     [rsp+1C0h+var_148], r8d
0x1800966ed  mov     [rsp+1C0h+var_144], r12d
0x1800966f2  mov     [rbp+0C0h+var_128], r8d
0x1800966f6  mov     [rbp+0C0h+var_124], r12d
0x1800966fa  mov     [rbp+0C0h+var_138], edi
0x1800966fd  inc     rax
0x180096700  cmp     [rcx+rax*2], r15w
0x180096705  jnz     short loc_1800966FD
0x180096707  lea     eax, ds:2[rax*2]
0x18009670e  mov     [rbp+0C0h+var_EC], r8d
0x180096712  mov     [rbp+0C0h+var_134], eax
0x180096715  lea     rcx, CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID
0x18009671c  mov     edx, 7
0x180096721  mov     [rbp+0C0h+var_E8], rcx
0x180096725  lea     rax, [rbp+0C0h+var_90]
0x180096729  mov     [rbp+0C0h+var_F0], edx
0x18009672c  mov     [rbp+0C0h+var_130], rax
0x180096730  lea     rax, [rsp+1C0h+var_148]
0x180096735  mov     [rbp+0C0h+var_D8], rax
0x180096739  lea     rax, RPC_INTERFACE_EVENT_GUID
0x180096740  mov     [rbp+0C0h+var_C8], rax
0x180096744  lea     rax, [rbp+0C0h+var_138]
0x180096748  mov     [rbp+0C0h+var_B8], rax
0x18009674c  lea     rax, [rbp+0C0h+var_128]
0x180096750  mov     [rbp+0C0h+var_98], rax
0x180096754  xor     eax, eax
0x180096756  mov     [rbp+0C0h+var_114], eax
0x180096759  test    sil, sil
0x18009675c  mov     [rbp+0C0h+var_E0], r8d
0x180096760  lea     rax, [rbp+0C0h+var_F0]
0x180096764  cmovz   r14d, edi
0x180096768  mov     [rbp+0C0h+var_CC], r8d
0x18009676c  mov     [rbp+0C0h+var_C0], r8d
0x180096770  mov     [rbp+0C0h+var_B0], edx
0x180096773  mov     edx, r12d; dwInfoLevel
0x180096776  mov     [rbp+0C0h+var_AC], r8d
0x18009677a  mov     [rbp+0C0h+var_A8], rcx
0x18009677e  mov     rcx, rbx; hService
0x180096781  mov     [rbp+0C0h+var_A0], r8d
0x180096785  lea     r8, [rbp+0C0h+Info]; lpInfo
0x180096789  mov     [rbp+0C0h+Info], r14d
0x18009678d  mov     [rbp+0C0h+var_D0], 6
0x180096794  mov     [rbp+0C0h+var_110], rax
0x180096798  mov     [rbp+0C0h+var_108], r15
0x18009679c  call    cs:__imp_ChangeServiceConfig2W
0x1800967a2  mov     ecx, eax
0x1800967a4  test    eax, eax
0x1800967a6  jnz     short loc_180096812
0x1800967a8  call    cs:__imp_GetLastError
0x1800967ae  mov     ecx, cs:CallbackContext
0x1800967b4  cmp     ecx, edi
0x1800967b6  jbe     loc_180096863
0x1800967bc  mov     [rsp+1C0h+var_180], esi
0x1800967c0  lea     rdx, byte_18012D1E3
0x1800967c7  mov     [rsp+1C0h+var_17C], eax
0x1800967cb  lea     rax, aLpaEsimmanager_16; "LPA::EsimManager::UpdateServiceTriggerE"...
0x1800967d2  mov     [rsp+1C0h+var_170], rax
0x1800967d7  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x1800967de  mov     [rsp+1C0h+var_178], rax
0x1800967e3  lea     rax, [rsp+1C0h+var_180]
0x1800967e8  mov     [rsp+1C0h+var_188], rax
0x1800967ed  lea     rax, [rsp+1C0h+var_17C]
0x1800967f2  mov     [rsp+1C0h+var_190], rax
0x1800967f7  lea     rax, [rsp+1C0h+var_170]
0x1800967fc  mov     [rsp+1C0h+var_198], rax
0x180096801  lea     rax, [rsp+1C0h+var_178]
0x180096806  mov     [rsp+1C0h+var_1A0], rax
0x18009680b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180096810  jmp     short loc_180096863
0x180096812  mov     eax, cs:CallbackContext
0x180096818  cmp     eax, 4
0x18009681b  jbe     short loc_180096863
0x18009681d  lea     rax, aLpaEsimmanager_16; "LPA::EsimManager::UpdateServiceTriggerE"...
0x180096824  mov     [rsp+1C0h+var_180], ecx
0x180096828  mov     [rsp+1C0h+var_170], rax
0x18009682d  lea     rdx, byte_18012D197
0x180096834  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18009683b  mov     [rsp+1C0h+var_178], rax
0x180096840  lea     rax, [rsp+1C0h+var_180]
0x180096845  mov     [rsp+1C0h+var_190], rax
0x18009684a  lea     rax, [rsp+1C0h+var_170]
0x18009684f  mov     [rsp+1C0h+var_198], rax
0x180096854  lea     rax, [rsp+1C0h+var_178]
0x180096859  mov     [rsp+1C0h+var_1A0], rax
0x18009685e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180096863  lea     rcx, [rsp+1C0h+var_168]
0x180096868  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18009686d  lea     rcx, [rsp+1C0h+var_160]
0x180096872  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180096877  lea     rcx, [rsp+1C0h+var_158]
0x18009687c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180096881  lea     rcx, [rsp+1C0h+var_150]
0x180096886  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18009688b  mov     rcx, [rbp+0C0h+var_40]
0x180096892  xor     rcx, rsp; StackCookie
0x180096895  call    __security_check_cookie
0x18009689a  add     rsp, 190h
0x1800968a1  pop     r15
0x1800968a3  pop     r14
0x1800968a5  pop     r12
0x1800968a7  pop     rdi
0x1800968a8  pop     rsi
0x1800968a9  pop     rbx
0x1800968aa  pop     rbp
0x1800968ab  retn
```
