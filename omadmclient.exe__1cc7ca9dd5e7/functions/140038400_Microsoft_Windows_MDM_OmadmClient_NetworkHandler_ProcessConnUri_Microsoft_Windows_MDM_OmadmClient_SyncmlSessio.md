# Microsoft::Windows::MDM::OmadmClient::NetworkHandler::ProcessConnUri(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *)

- ea: `0x140038400`
- end: `0x140038ae5`
- name: `?ProcessConnUri@NetworkHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEBG@Z`
- size: `1765`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::NetworkHandler *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x140015868`
- `0x140038400`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140038602`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140038602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038939`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140038958`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140038958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400388b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003894a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400389d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140038a3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140038a82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400388b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003894a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400389d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140038a3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140038a82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140038859`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140038859`
- `DMCmnUtils!BigStrcat` at `0x1400386e9`
- `DMCmnUtils!BigStrcat` at `0x140038707`
- `DMCmnUtils!BigStrcat` at `0x1400386e9`
- `DMCmnUtils!BigStrcat` at `0x140038707`

## string_xrefs

- `0x14003844b`: `ProcessConnUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkHandler::ProcessConnUri(
        Microsoft::Windows::MDM::OmadmClient::NetworkHandler *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // r8
  unsigned int v7; // edi
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // esi
  unsigned __int16 *v11; // rbx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // ecx
  unsigned __int64 v18; // rax
  HLOCAL v19; // r15
  int v20; // eax
  void *v21; // r12
  DWORD LastError; // esi
  bool v23; // zf
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+34h] [rbp-CCh] BYREF
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v30[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  int *v32; // [rsp+60h] [rbp-A0h]
  unsigned int v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h]
  __int128 v37; // [rsp+A0h] [rbp-60h]
  __int128 v38; // [rsp+B0h] [rbp-50h]
  __int128 v39; // [rsp+C0h] [rbp-40h]
  __int128 v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+E0h] [rbp-20h]
  int v42; // [rsp+F0h] [rbp-10h]
  char v43; // [rsp+F4h] [rbp-Ch]
  HLOCAL v44; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+100h] [rbp+0h] BYREF
  int *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  int v48[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v49; // [rsp+128h] [rbp+28h] BYREF
  int v50; // [rsp+130h] [rbp+30h]
  __int128 v51; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 v52[264]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v27 = 0;
  v30[0] = 0;
  v30[1] = "ProcessConnUri";
  v30[2] = COmaDmLogger::GetLogger();
  v31 = 2;
  v32 = &v27;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v48[0] = 29;
    v46 = v48;
    v47 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v6,
      2u,
      &v45);
  }
  v7 = v27;
  v42 = v27;
  v43 = 1;
  memset_0(&v35, 0, 0x68u);
  LODWORD(v35) = 104;
  LODWORD(v36) = 1;
  LODWORD(v37) = 1;
  LODWORD(v38) = 1;
  LODWORD(v39) = 1;
  LODWORD(v40) = 1;
  LODWORD(v41) = 1;
  v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 3)
                                                                                               + 8LL))(
         *((_QWORD *)this + 3),
         a3,
         0,
         0,
         &v35);
  v10 = v8;
  v27 = v8;
  if ( v8 < 0 )
  {
    LODWORD(v30[0]) = 18037;
    HIDWORD(v30[0]) = v8;
LABEL_67:
    v23 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
LABEL_68:
    if ( !v23 )
      McTemplateU0qq_EventWriteTransfer(v9, OmaDmClientFunctionReturnValueEvent, 29, v7);
    goto LABEL_70;
  }
  if ( (unsigned int)(DWORD1(v36) - 1) > 1 )
  {
    LODWORD(v30[0]) = 18010;
    v10 = -2147024809;
LABEL_7:
    HIDWORD(v30[0]) = v10;
    goto LABEL_67;
  }
  v28 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 6) + 240LL))(
          *((_QWORD *)this + 6),
          4130,
          &v28);
  v27 = v10;
  v9 = 0x80000000LL;
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024894 )
  {
    LODWORD(v30[0]) = 18023;
    goto LABEL_7;
  }
  v49 = *(_QWORD *)L"https";
  v50 = *(_DWORD *)L"s";
  if ( v28 != 1 )
  {
    if ( WORD2(v37) == 80 && DWORD1(v36) == 1 )
      WORD2(v37) = 443;
    *(_QWORD *)&v36 = 0x200000005LL;
    *((_QWORD *)&v35 + 1) = &v49;
  }
  v11 = 0;
  v34 = 0;
  if ( (*((_BYTE *)a2 + 140) & 0x20) != 0 )
  {
    v12 = *((_QWORD *)a2 + 65);
    if ( !v12 || !(unsigned int)_o__wcsicmp(L"1.0", v12) )
    {
      *(_QWORD *)v48 = 0x41006F0057LL;
      if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
             *((_QWORD *)this + 4),
             *((_QWORD *)a2 + 75)) )
      {
        v45 = *(struct _EVENT_DATA_DESCRIPTOR *)L"Maintenance";
        v46 = *(int **)L"nce";
        v13 = StringCchPrintfW(v52, 0x104u, L"mode=%s&Platform=%s", &v45, v48);
        v10 = v13;
        v27 = v13;
        if ( v13 < 0 )
        {
          LODWORD(v30[0]) = 18025;
LABEL_22:
          HIDWORD(v30[0]) = v13;
          goto LABEL_67;
        }
      }
      else
      {
        v51 = *(_OWORD *)L"Machine";
        v13 = StringCchPrintfW(v52, 0x104u, L"mode=%s&Platform=%s", &v51, v48);
        v10 = v13;
        v27 = v13;
        if ( v13 < 0 )
        {
          LODWORD(v30[0]) = 18024;
          goto LABEL_22;
        }
      }
      if ( !*((_QWORD *)&v40 + 1) )
        goto LABEL_30;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(*((_QWORD *)&v40 + 1) + 2 * v14) );
      if ( v14 )
        v15 = BigStrcat(3u, *((_QWORD *)&v40 + 1), L"&", v52);
      else
LABEL_30:
        v15 = BigStrcat(2u, L"?", v52);
      v34 = v15;
      v11 = v15;
      if ( !v15 )
      {
        v10 = -2147024882;
        v27 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x93,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
          (const char *)0x8007000ELL,
          v26);
        goto LABEL_67;
      }
      v27 = 0;
      v16 = 0x7FFFFFFF;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v16;
      }
      while ( v16 );
      v10 = v16 == 0 ? 0x80070057 : 0;
      v27 = v10;
      if ( !v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x96,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
          (const char *)v10,
          v26);
        goto LABEL_66;
      }
      *((_QWORD *)&v40 + 1) = v11;
      LODWORD(v41) = v16 != 0 ? 0x7FFFFFFF - v16 : 0;
    }
  }
  v29 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 16LL))(
          *((_QWORD *)this + 3),
          &v35,
          0,
          0);
  v27 = v10;
  if ( v10 != -2147024774 )
  {
    LODWORD(v30[0]) = 18039;
    HIDWORD(v30[0]) = v10;
LABEL_65:
    if ( !v11 )
      goto LABEL_67;
LABEL_66:
    LocalFree(v11);
    goto LABEL_67;
  }
  v17 = v29 + 1;
  if ( v29 + 1 < (unsigned int)v29 )
  {
    v10 = -2147024362;
    v17 = -1;
  }
  else
  {
    v10 = 0;
  }
  v33 = v17;
  v27 = v10;
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
      (const char *)v10,
      (int)&v29);
    goto LABEL_65;
  }
  v18 = 2LL * v17;
  if ( v18 <= 0xFFFFFFFF )
  {
    v27 = 0;
    v19 = LocalAlloc(0, (unsigned int)v18);
    v44 = v19;
    if ( v19 )
    {
      v27 = 0;
      v20 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, HLOCAL, unsigned int *))(**((_QWORD **)this + 3)
                                                                                          + 16LL))(
              *((_QWORD *)this + 3),
              &v35,
              0,
              v19,
              &v33);
      v10 = v20;
      v27 = v20;
      if ( v20 >= 0 )
      {
        memset_0(&v35, 0, 0x68u);
        LODWORD(v35) = 104;
        LODWORD(v36) = 1;
        LODWORD(v37) = 1;
        LODWORD(v38) = 1;
        LODWORD(v39) = 1;
        LODWORD(v40) = 1;
        LODWORD(v41) = 1;
        v20 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, _QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 3) + 8LL))(
                *((_QWORD *)this + 3),
                v19,
                0,
                0,
                &v35);
        v10 = v20;
        v27 = v20;
        if ( v20 >= 0 )
        {
          v44 = 0;
          v21 = (void *)*((_QWORD *)a2 + 222);
          if ( v21 )
          {
            LastError = GetLastError();
            LocalFree(v21);
            SetLastError(LastError);
          }
          *((_QWORD *)a2 + 222) = v19;
          *(_OWORD *)((char *)a2 + 1784) = v35;
          *(_OWORD *)((char *)a2 + 1800) = v36;
          *(_OWORD *)((char *)a2 + 1816) = v37;
          *(_OWORD *)((char *)a2 + 1832) = v38;
          *(_OWORD *)((char *)a2 + 1848) = v39;
          *(_OWORD *)((char *)a2 + 1864) = v40;
          *((_QWORD *)a2 + 235) = v41;
          Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState::ReleaseAllConnHandles(a2);
          v10 = v27;
          goto LABEL_55;
        }
        LODWORD(v30[0]) = 18038;
      }
      else
      {
        LODWORD(v30[0]) = 18040;
      }
      HIDWORD(v30[0]) = v20;
      LocalFree(v19);
    }
    else
    {
      v10 = -2147024882;
      v27 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
        (const char *)0x8007000ELL,
        (int)&v29);
    }
LABEL_55:
    if ( v11 )
      LocalFree(v11);
    v23 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
    goto LABEL_68;
  }
  v27 = -2147024362;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAB,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
    (const char *)0x80070216LL,
    (int)&v29);
  if ( v11 )
    LocalFree(v11);
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(v24, OmaDmClientFunctionReturnValueEvent, 29, v7);
  v10 = -2147024362;
LABEL_70:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v30);
  return v10;
}

```

## disassembly

```asm
0x140038400  mov     [rsp-8+arg_18], rbx
0x140038405  push    rbp
0x140038406  push    rsi
0x140038407  push    rdi
0x140038408  push    r12
0x14003840a  push    r13
0x14003840c  push    r14
0x14003840e  push    r15
0x140038410  lea     rbp, [rsp-270h]
0x140038418  sub     rsp, 370h
0x14003841f  mov     rax, cs:__security_cookie
0x140038426  xor     rax, rsp
0x140038429  mov     [rbp+2A0h+var_40], rax
0x140038430  mov     rbx, r8
0x140038433  mov     r14, rdx
0x140038436  mov     r13, rcx
0x140038439  xor     r12d, r12d
0x14003843c  mov     [rsp+3A0h+var_370], r12d
0x140038441  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140038446  mov     [rsp+3A0h+var_360], r12
0x14003844b  lea     rcx, aProcessconnuri; "ProcessConnUri"
0x140038452  mov     [rsp+3A0h+var_358], rcx
0x140038457  mov     [rsp+3A0h+var_350], rax
0x14003845c  mov     [rsp+3A0h+var_348], 2
0x140038464  lea     rax, [rsp+3A0h+var_370]
0x140038469  mov     [rsp+3A0h+var_340], rax
0x14003846e  mov     r15b, 8
0x140038471  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r15b
0x140038478  jz      short loc_1400384B2
0x14003847a  mov     [rbp+2A0h+var_280], 1Dh
0x140038481  lea     rax, [rbp+2A0h+var_280]
0x140038485  mov     [rbp+2A0h+var_290], rax
0x140038489  mov     [rbp+2A0h+var_288], 4
0x140038491  lea     rax, [rbp+2A0h+var_2A0]
0x140038495  mov     qword ptr [rsp+3A0h+var_380], rax
0x14003849a  lea     r9d, [r12+2]
0x14003849f  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x1400384a6  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x1400384ad  call    McGenEventWrite_EventWriteTransfer
0x1400384b2  mov     edi, [rsp+3A0h+var_370]
0x1400384b6  mov     [rbp+2A0h+var_2B0], edi
0x1400384b9  mov     esi, 1
0x1400384be  mov     [rbp+2A0h+var_2AC], sil
0x1400384c2  xor     edx, edx; Val
0x1400384c4  lea     r8d, [rsi+67h]; Size
0x1400384c8  lea     rcx, [rbp+2A0h+var_320]; void *
0x1400384cc  call    memset_0
0x1400384d1  mov     dword ptr [rbp+2A0h+var_320], 68h ; 'h'
0x1400384d8  mov     dword ptr [rbp+2A0h+var_310], esi
0x1400384db  mov     dword ptr [rbp+2A0h+var_300], esi
0x1400384de  mov     dword ptr [rbp+2A0h+var_2F0], esi
0x1400384e1  mov     dword ptr [rbp+2A0h+var_2E0], esi
0x1400384e4  mov     dword ptr [rbp+2A0h+var_2D0], esi
0x1400384e7  mov     dword ptr [rbp+2A0h+var_2C0], esi
0x1400384ea  mov     rcx, [r13+18h]
0x1400384ee  mov     rax, [rcx]
0x1400384f1  lea     rdx, [rbp+2A0h+var_320]
0x1400384f5  mov     qword ptr [rsp+3A0h+var_380], rdx
0x1400384fa  xor     r9d, r9d
0x1400384fd  xor     r8d, r8d
0x140038500  mov     rdx, rbx
0x140038503  mov     rax, [rax+8]
0x140038507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003850c  mov     esi, eax
0x14003850e  mov     [rsp+3A0h+var_370], eax
0x140038512  test    eax, eax
0x140038514  jns     short loc_140038527
0x140038516  mov     dword ptr [rsp+3A0h+var_360], 4675h
0x14003851e  mov     dword ptr [rsp+3A0h+var_360+4], eax
0x140038522  jmp     loc_140038A8F
0x140038527  mov     eax, dword ptr [rbp+2A0h+var_310+4]
0x14003852a  dec     eax
0x14003852c  cmp     eax, 1
0x14003852f  jbe     short loc_140038547
0x140038531  mov     dword ptr [rsp+3A0h+var_360], 465Ah
0x140038539  mov     esi, 80070057h
0x14003853e  mov     dword ptr [rsp+3A0h+var_360+4], esi
0x140038542  jmp     loc_140038A8F
0x140038547  mov     [rsp+3A0h+var_36C], r12d
0x14003854c  mov     rcx, [r13+30h]
0x140038550  mov     rax, [rcx]
0x140038553  lea     r8, [rsp+3A0h+var_36C]
0x140038558  mov     edx, 1022h
0x14003855d  mov     rax, [rax+0F0h]
0x140038564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038569  mov     esi, eax
0x14003856b  mov     [rsp+3A0h+var_370], eax
0x14003856f  mov     ecx, 80000000h
0x140038574  add     eax, ecx
0x140038576  test    ecx, eax
0x140038578  jnz     short loc_14003858C
0x14003857a  cmp     esi, 80070002h
0x140038580  jz      short loc_14003858C
0x140038582  mov     dword ptr [rsp+3A0h+var_360], 4667h
0x14003858a  jmp     short loc_14003853E
0x14003858c  movsd   xmm0, qword ptr cs:aHttps; "https"
0x140038594  movsd   [rbp+2A0h+var_278], xmm0
0x140038599  mov     eax, dword ptr cs:aHttps+8; "s"
0x14003859f  mov     [rbp+2A0h+var_270], eax
0x1400385a2  cmp     [rsp+3A0h+var_36C], 1
0x1400385a7  jz      short loc_1400385D9
0x1400385a9  mov     eax, 50h ; 'P'
0x1400385ae  cmp     ax, word ptr [rbp+2A0h+var_300+4]
0x1400385b2  jnz     short loc_1400385C3
0x1400385b4  cmp     dword ptr [rbp+2A0h+var_310+4], 1
0x1400385b8  jnz     short loc_1400385C3
0x1400385ba  mov     eax, 1BBh
0x1400385bf  mov     word ptr [rbp+2A0h+var_300+4], ax
0x1400385c3  mov     dword ptr [rbp+2A0h+var_310+4], 2
0x1400385ca  mov     dword ptr [rbp+2A0h+var_310], 5
0x1400385d1  lea     rax, [rbp+2A0h+var_278]
0x1400385d5  mov     qword ptr [rbp+2A0h+var_320+8], rax
0x1400385d9  mov     rbx, r12
0x1400385dc  mov     [rsp+3A0h+var_330], rbx
0x1400385e1  test    byte ptr [r14+8Ch], 20h
0x1400385e9  jz      loc_140038793
0x1400385ef  mov     rdx, [r14+208h]
0x1400385f6  test    rdx, rdx
0x1400385f9  jz      short loc_140038616
0x1400385fb  lea     rcx, a10; "1.0"
0x140038602  call    cs:__imp__o__wcsicmp
0x140038609  nop     dword ptr [rax+rax+00h]
0x14003860e  test    eax, eax
0x140038610  jnz     loc_140038793
0x140038616  mov     rax, 41006F0057h
0x140038620  mov     qword ptr [rbp+2A0h+var_280], rax
0x140038624  mov     rcx, [r13+20h]
0x140038628  mov     rax, [rcx]
0x14003862b  mov     rdx, [r14+258h]
0x140038632  mov     rax, [rax+18h]
0x140038636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003863b  lea     r8, ?gc_szBackcompExtraInfoFormat@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "mode=%s&Platform=%s"
0x140038642  mov     edx, 104h; unsigned __int64
0x140038647  lea     rcx, [rbp+2A0h+var_250]; unsigned __int16 *
0x14003864b  test    eax, eax
0x14003864d  lea     rax, [rbp+2A0h+var_280]
0x140038651  mov     qword ptr [rsp+3A0h+var_380], rax; int
0x140038656  jz      short loc_140038694
0x140038658  movups  xmm0, xmmword ptr cs:aMaintenance; "Maintenance"
0x14003865f  movups  [rbp+2A0h+var_2A0], xmm0
0x140038663  movsd   xmm1, qword ptr cs:aMaintenance+10h; "nce"
0x14003866b  movsd   [rbp+2A0h+var_290], xmm1
0x140038670  lea     r9, [rbp+2A0h+var_2A0]
0x140038674  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140038679  mov     esi, eax
0x14003867b  mov     [rsp+3A0h+var_370], eax
0x14003867f  test    eax, eax
0x140038681  jns     short loc_1400386BD
0x140038683  mov     dword ptr [rsp+3A0h+var_360], 4669h
0x14003868b  mov     dword ptr [rsp+3A0h+var_360+4], eax
0x14003868f  jmp     loc_140038A8F
0x140038694  movups  xmm0, xmmword ptr cs:aMachine; "Machine"
0x14003869b  movdqu  [rbp+2A0h+var_268], xmm0
0x1400386a0  lea     r9, [rbp+2A0h+var_268]
0x1400386a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400386a9  mov     esi, eax
0x1400386ab  mov     [rsp+3A0h+var_370], eax
0x1400386af  test    eax, eax
0x1400386b1  jns     short loc_1400386BD
0x1400386b3  mov     dword ptr [rsp+3A0h+var_360], 4668h
0x1400386bb  jmp     short loc_14003868B
0x1400386bd  mov     rdx, qword ptr [rbp+2A0h+var_2D0+8]
0x1400386c1  test    rdx, rdx
0x1400386c4  jz      short loc_1400386F7
0x1400386c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400386ca  inc     rax
0x1400386cd  cmp     [rdx+rax*2], r12w
0x1400386d2  jnz     short loc_1400386CA
0x1400386d4  test    rax, rax
0x1400386d7  jz      short loc_1400386F7
0x1400386d9  lea     r9, [rbp+2A0h+var_250]
0x1400386dd  lea     r8, asc_1400724A8; "&"
0x1400386e4  mov     ecx, 3
0x1400386e9  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400386f0  nop     dword ptr [rax+rax+00h]
0x1400386f5  jmp     short loc_140038713
0x1400386f7  lea     r8, [rbp+2A0h+var_250]
0x1400386fb  lea     rdx, asc_1400724AC; "?"
0x140038702  mov     ecx, 2
0x140038707  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x14003870e  nop     dword ptr [rax+rax+00h]
0x140038713  mov     [rsp+3A0h+var_330], rax
0x140038718  mov     rbx, rax
0x14003871b  test    rax, rax
0x14003871e  jz      loc_1400387E8
0x140038724  mov     [rsp+3A0h+var_370], r12d
0x140038729  mov     r8d, 7FFFFFFFh
0x14003872f  mov     edx, r8d
0x140038732  cmp     [rax], r12w
0x140038736  jz      short loc_140038742
0x140038738  add     rax, 2
0x14003873c  sub     rdx, 1
0x140038740  jnz     short loc_140038732
0x140038742  mov     rax, rdx
0x140038745  neg     rax
0x140038748  sbb     ecx, ecx
0x14003874a  not     ecx
0x14003874c  mov     esi, 80070057h
0x140038751  and     esi, ecx
0x140038753  mov     rax, rdx
0x140038756  sub     r8, rdx
0x140038759  neg     rax
0x14003875c  sbb     rcx, rcx
0x14003875f  and     rcx, r8
0x140038762  mov     [rsp+3A0h+var_370], esi
0x140038766  test    rdx, rdx
0x140038769  jnz     short loc_14003878C
0x14003876b  mov     rcx, [rbp+2A8h]; this
0x140038772  mov     r9d, esi; char *
0x140038775  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003877c  mov     edx, 96h; void *
0x140038781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038786  nop
0x140038787  jmp     loc_140038A7F
0x14003878c  mov     qword ptr [rbp+2A0h+var_2D0+8], rbx
0x140038790  mov     dword ptr [rbp+2A0h+var_2C0], ecx
0x140038793  mov     [rsp+3A0h+var_368], r12d
0x140038798  mov     rcx, [r13+18h]
0x14003879c  mov     rax, [rcx]
0x14003879f  lea     rdx, [rsp+3A0h+var_368]
0x1400387a4  mov     qword ptr [rsp+3A0h+var_380], rdx; int
0x1400387a9  xor     r9d, r9d
0x1400387ac  xor     r8d, r8d
0x1400387af  lea     rdx, [rbp+2A0h+var_320]
0x1400387b3  mov     rax, [rax+10h]
0x1400387b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400387bc  mov     esi, eax
0x1400387be  mov     [rsp+3A0h+var_370], eax
0x1400387c2  cmp     eax, 8007007Ah
0x1400387c7  jnz     loc_140038A6E
0x1400387cd  mov     eax, [rsp+3A0h+var_368]
0x1400387d1  lea     ecx, [rax+1]
0x1400387d4  mov     edx, 80070216h
0x1400387d9  mov     r8d, 0FFFFFFFFh
0x1400387df  cmp     ecx, eax
0x1400387e1  jb      short loc_140038811
0x1400387e3  mov     esi, r12d
0x1400387e6  jmp     short loc_140038816
0x1400387e8  mov     esi, 8007000Eh
0x1400387ed  mov     [rsp+3A0h+var_370], esi
0x1400387f1  mov     rcx, [rbp+2A8h]; this
0x1400387f8  mov     r9d, esi; char *
0x1400387fb  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140038802  mov     edx, 93h; void *
0x140038807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003880c  jmp     loc_14003868F
0x140038811  mov     esi, edx
0x140038813  mov     ecx, r8d
0x140038816  mov     [rsp+3A0h+var_338], ecx
0x14003881a  mov     [rsp+3A0h+var_370], esi
0x14003881e  test    esi, esi
0x140038820  jns     short loc_140038842
0x140038822  mov     rcx, [rbp+2A8h]; this
0x140038829  mov     r9d, esi; char *
0x14003882c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140038833  mov     edx, 0A8h; void *
0x140038838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003883d  jmp     loc_140038A7A
0x140038842  mov     eax, ecx
0x140038844  add     rax, rax
0x140038847  cmp     rax, r8
0x14003884a  ja      loc_140038A14
0x140038850  mov     [rsp+3A0h+var_370], r12d
0x140038855  mov     edx, eax; uBytes
0x140038857  xor     ecx, ecx; uFlags
0x140038859  call    cs:__imp_LocalAlloc
0x140038860  nop     dword ptr [rax+rax+00h]
0x140038865  mov     r15, rax
0x140038868  mov     [rbp+2A0h+var_2A8], rax
0x14003886c  test    rax, rax
0x14003886f  jz      loc_1400389EE
0x140038875  mov     [rsp+3A0h+var_370], r12d
0x14003887a  mov     rcx, [r13+18h]
0x14003887e  mov     rdx, [rcx]
0x140038881  mov     rax, [rdx+10h]
0x140038885  lea     rdx, [rsp+3A0h+var_338]
0x14003888a  mov     qword ptr [rsp+3A0h+var_380], rdx
0x14003888f  mov     r9, r15
0x140038892  xor     r8d, r8d
0x140038895  lea     rdx, [rbp+2A0h+var_320]
0x140038899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003889e  mov     esi, eax
0x1400388a0  mov     [rsp+3A0h+var_370], eax
0x1400388a4  test    eax, eax
0x1400388a6  jns     short loc_1400388C8
0x1400388a8  mov     dword ptr [rsp+3A0h+var_360], 4678h
0x1400388b0  mov     dword ptr [rsp+3A0h+var_360+4], eax
0x1400388b4  mov     rcx, r15; hMem
0x1400388b7  call    cs:__imp_LocalFree
0x1400388be  nop     dword ptr [rax+rax+00h]
0x1400388c3  jmp     loc_1400389CD
0x1400388c8  mov     esi, 68h ; 'h'
0x1400388cd  mov     r8d, esi; Size
0x1400388d0  xor     edx, edx; Val
0x1400388d2  lea     rcx, [rbp+2A0h+var_320]; void *
0x1400388d6  call    memset_0
0x1400388db  mov     dword ptr [rbp+2A0h+var_320], esi
0x1400388de  lea     eax, [rsi-67h]
0x1400388e1  mov     dword ptr [rbp+2A0h+var_310], eax
0x1400388e4  mov     dword ptr [rbp+2A0h+var_300], eax
  ... truncated ...
```
