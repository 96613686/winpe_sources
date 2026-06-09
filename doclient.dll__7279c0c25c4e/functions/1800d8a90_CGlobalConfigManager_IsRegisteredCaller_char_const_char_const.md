# CGlobalConfigManager::IsRegisteredCaller(char const *,char const *)

- ea: `0x1800d8a90`
- end: `0x1800d928b`
- name: `?IsRegisteredCaller@CGlobalConfigManager@@QEBA_NPEBD0@Z`
- size: `2043`
- prototype: `bool(CGlobalConfigManager *__hidden this, const char *, const char *)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d4ec`
- `0x1800b11a4`
- `0x1800b3ad0`

## callees

- `0x18000d228`
- `0x1800a1ea4`
- `0x1800ab738`
- `0x1800d8a90`
- `0x1800d9294`
- `0x1800db530`
- `0x1800f8110`
- `0x1800f82f0`
- `0x1800f874c`
- `0x180107cbc`
- `0x180107d24`
- `0x180108bf8`
- `0x180108ed0`

## string_xrefs

- `0x1800d8bdf`: `ctldl.windowsupdate.com`
- `0x1800d8c07`: `*.dcat.dsp.mp.microsoft.com`
- `0x1800d8b92`: `*.adu.microsoft.com`
- `0x1800d8c72`: `*.download.windowsupdate.com`
- `0x1800d8c2a`: `*.delivery.mp.microsoft.com`
- `0x1800d8c4e`: `download.windowsupdate.com`
- `0x1800d8d06`: `*.manage-selfhost.microsoft.com`
- `0x1800d8d33`: `*.manage.microsoft.com`
- `0x1800d8cb8`: `*.manage-beta.microsoft.com`
- `0x1800d8cdc`: `*.manage-dogfood.microsoft.com`
- `0x1800d8d5f`: `officecdn.microsoft.com`
- `0x1800d8d8c`: `officecdn.microsoft.com.edgesuite.net`
- `0x1800d8e13`: `*.xboxlive.com`
- `0x1800d8f97`: `EdgeUpdate DO Job`
- `0x1800d9079`: `MSIX HttpsDataSource Download`
- `0x1800d9002`: `Microsoft Component Updater DO Job`
- `0x1800d90a5`: `Msk8sDownloadAgent`
- `0x1800d9257`: `CGlobalConfigManager::IsRegisteredCaller`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
char __fastcall CGlobalConfigManager::IsRegisteredCaller(CGlobalConfigManager *this, const char *a2, const char *a3)
{
  unsigned int v6; // r8d
  char IsMatchForWildcardConfig; // bl
  __int128 *v9; // [rsp+30h] [rbp-D0h] BYREF
  CHAR *v10; // [rsp+38h] [rbp-C8h]
  __int128 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+50h] [rbp-B0h]
  __int128 v13; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+70h] [rbp-90h]
  __int128 v15; // [rsp+80h] [rbp-80h] BYREF
  __int128 v16; // [rsp+90h] [rbp-70h]
  __int128 v17; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v18; // [rsp+B0h] [rbp-50h]
  __int128 v19; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v20; // [rsp+D0h] [rbp-30h]
  __int128 v21; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h]
  __int128 v23; // [rsp+100h] [rbp+0h] BYREF
  __int128 v24; // [rsp+110h] [rbp+10h]
  __int128 v25; // [rsp+120h] [rbp+20h] BYREF
  __int128 v26; // [rsp+130h] [rbp+30h]
  __int128 v27; // [rsp+140h] [rbp+40h] BYREF
  __int128 v28; // [rsp+150h] [rbp+50h]
  __int128 v29; // [rsp+160h] [rbp+60h] BYREF
  __int128 v30; // [rsp+170h] [rbp+70h]
  __int128 v31; // [rsp+180h] [rbp+80h] BYREF
  __int128 v32; // [rsp+190h] [rbp+90h]
  __int128 v33; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v34; // [rsp+1B0h] [rbp+B0h]
  __int128 v35; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v36; // [rsp+1D0h] [rbp+D0h]
  __int128 v37; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v38; // [rsp+1F0h] [rbp+F0h]
  __int128 v39; // [rsp+200h] [rbp+100h] BYREF
  __int128 v40; // [rsp+210h] [rbp+110h]
  __int128 v41; // [rsp+220h] [rbp+120h] BYREF
  __int128 v42; // [rsp+230h] [rbp+130h]
  __int128 v43; // [rsp+240h] [rbp+140h] BYREF
  __int128 v44; // [rsp+250h] [rbp+150h]
  _OWORD v45[2]; // [rsp+260h] [rbp+160h] BYREF
  CHAR pszOut[272]; // [rsp+280h] [rbp+180h] BYREF

  memset(pszOut, 0, 0x104u);
  if ( (unsigned int)o__stricmp_0(a2, "WU Client Download") )
  {
    IsMatchForWildcardConfig = 0;
    if ( !a3 || !*a3 || (int)UrlGetHostName(a3, pszOut, v6, 0) < 0 )
      goto LABEL_13;
    if ( dword_180195DD0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180195DD0);
      if ( dword_180195DD0 == -1 )
      {
        xmmword_180195DD8 = 0;
        qword_180195DE8 = 0;
        v11 = 0;
        v12 = 0;
        std::string::_Construct<1,char const *>(&v11, "*.adu.microsoft.com", 0x13u);
        v13 = 0;
        v14 = 0;
        std::string::_Construct<1,char const *>(&v13, "*.cdn.office.net", 0x10u);
        v15 = 0;
        v16 = 0;
        std::string::_Construct<1,char const *>(&v15, "ctldl.windowsupdate.com", 0x17u);
        v17 = 0;
        v18 = 0;
        std::string::_Construct<1,char const *>(&v17, "*.dcat.dsp.mp.microsoft.com", 0x1Bu);
        v19 = 0;
        v20 = 0;
        std::string::_Construct<1,char const *>(&v19, "*.delivery.mp.microsoft.com", 0x1Bu);
        v21 = 0;
        v22 = 0;
        std::string::_Construct<1,char const *>(&v21, "download.windowsupdate.com", 0x1Au);
        v23 = 0;
        v24 = 0;
        std::string::_Construct<1,char const *>(&v23, "*.download.windowsupdate.com", 0x1Cu);
        v25 = 0;
        v26 = 0;
        std::string::_Construct<1,char const *>(&v25, "*.m365.static.microsoft", 0x17u);
        v27 = 0;
        v28 = 0;
        std::string::_Construct<1,char const *>(&v27, "*.manage-beta.microsoft.com", 0x1Bu);
        v29 = 0;
        v30 = 0;
        std::string::_Construct<1,char const *>(&v29, "*.manage-dogfood.microsoft.com", 0x1Eu);
        v31 = 0;
        v32 = 0;
        std::string::_Construct<1,char const *>(&v31, "*.manage-selfhost.microsoft.com", 0x1Fu);
        v33 = 0;
        v34 = 0;
        std::string::_Construct<1,char const *>(&v33, "*.manage.microsoft.com", 0x16u);
        v35 = 0;
        v36 = 0;
        std::string::_Construct<1,char const *>(&v35, "officecdn.microsoft.com", 0x17u);
        v37 = 0;
        v38 = 0;
        std::string::_Construct<1,char const *>(&v37, "officecdn.microsoft.com.edgesuite.net", 0x25u);
        v39 = 0;
        v40 = 0;
        std::string::_Construct<1,char const *>(&v39, "*.teams.cdn.live.net", 0x14u);
        v41 = 0;
        v42 = 0;
        std::string::_Construct<1,char const *>(&v41, "*.teams.static.microsoft", 0x18u);
        v43 = 0;
        v44 = 0;
        std::string::_Construct<1,char const *>(&v43, "*.xboxlive.com", 0xEu);
        v9 = &v11;
        v10 = (CHAR *)v45;
        std::vector<std::string>::vector<std::string>(&xmmword_180195DD8, &v9);
        `eh vector destructor iterator'(&v11, 0x20u, 0x11u, (void (*)(void *))std::string::~string);
        atexit(CGlobalConfigManager::IsRegisteredCaller_::_10_::_dynamic_atexit_destructor_for__s_defaultAllowedHostNames__);
        Init_thread_footer(&dword_180195DD0);
      }
    }
    IsMatchForWildcardConfig = CGlobalConfigManager::_IsMatchForWildcardConfig(this, 134, pszOut, &xmmword_180195DD8);
    if ( !IsMatchForWildcardConfig )
      goto LABEL_13;
  }
  if ( dword_180195DF0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180195DF0);
    if ( dword_180195DF0 == -1 )
    {
      xmmword_180195DF8 = 0;
      qword_180195E08 = 0;
      v11 = 0;
      v12 = 0;
      std::string::_Construct<1,char const *>(&v11, "BeginLoadRange*", 0xFu);
      v13 = 0;
      v14 = 0;
      std::string::_Construct<1,char const *>(&v13, "*CheckReachable", 0xFu);
      v15 = 0;
      v16 = 0;
      std::string::_Construct<1,char const *>(&v15, "DoLoadFile", 0xAu);
      v17 = 0;
      v18 = 0;
      std::string::_Construct<1,char const *>(&v17, "DOContentPolicy", 0xFu);
      v19 = 0;
      v20 = 0;
      std::string::_Construct<1,char const *>(&v19, "EdgeUpdate DO Job", 0x11u);
      v21 = 0;
      v22 = 0;
      std::string::_Construct<1,char const *>(&v21, "IntuneAppDownload", 0x11u);
      v23 = 0;
      v24 = 0;
      std::string::_Construct<1,char const *>(&v23, "MDMSW Job", 9u);
      v25 = 0;
      v26 = 0;
      std::string::_Construct<1,char const *>(&v25, "Microsoft Component Updater DO Job", 0x22u);
      v27 = 0;
      v28 = 0;
      std::string::_Construct<1,char const *>(&v27, "Microsoft Office Click-to-Run", 0x1Du);
      v29 = 0;
      v30 = 0;
      std::string::_Construct<1,char const *>(&v29, "MLModelDownloadJob", 0x12u);
      v31 = 0;
      v32 = 0;
      std::string::_Construct<1,char const *>(&v31, "MSIX HttpsDataSource Download", 0x1Du);
      v33 = 0;
      v34 = 0;
      std::string::_Construct<1,char const *>(&v33, "Msk8sDownloadAgent", 0x12u);
      v35 = 0;
      v36 = 0;
      std::string::_Construct<1,char const *>(&v35, "Windows Dlp Manager", 0x13u);
      v37 = 0;
      v38 = 0;
      std::string::_Construct<1,char const *>(&v37, "Windows Package Manager", 0x17u);
      v39 = 0;
      v40 = 0;
      std::string::_Construct<1,char const *>(&v39, "Windows Recovery Media Creator", 0x1Eu);
      v41 = 0;
      v42 = 0;
      std::string::_Construct<1,char const *>(&v41, "WSXExperiencePackDownloadJob", 0x1Cu);
      v43 = 0;
      v44 = 0;
      std::string::_Construct<1,char const *>(&v43, "WU Client Download", 0x12u);
      memset(v45, 0, sizeof(v45));
      std::string::_Construct<1,char const *>(v45, "Xbox XVC Streaming", 0x12u);
      v9 = &v11;
      v10 = pszOut;
      std::vector<std::string>::vector<std::string>(&xmmword_180195DF8, &v9);
      `eh vector destructor iterator'(&v11, 0x20u, 0x12u, (void (*)(void *))std::string::~string);
      atexit(CGlobalConfigManager::IsRegisteredCaller_::_13_::_dynamic_atexit_destructor_for__s_defaultRegisteredCallers__);
      Init_thread_footer(&dword_180195DF0);
    }
  }
  IsMatchForWildcardConfig = CGlobalConfigManager::_IsMatchForWildcardConfig(this, 133, a2, &xmmword_180195DF8);
  if ( !IsMatchForWildcardConfig )
LABEL_13:
    LogMessage(5u, "CGlobalConfigManager::IsRegisteredCaller", 0x7C2u, "Unregistered caller: %s, host: %s", a2, pszOut);
  return IsMatchForWildcardConfig;
}

```

## disassembly

```asm
0x1800d8a90  push    rbp
0x1800d8a92  push    rbx
0x1800d8a93  push    rsi
0x1800d8a94  push    rdi
0x1800d8a95  push    r12
0x1800d8a97  push    r13
0x1800d8a99  push    r15
0x1800d8a9b  lea     rbp, [rsp-2A0h]
0x1800d8aa3  sub     rsp, 3A0h
0x1800d8aaa  mov     rax, cs:__security_cookie
0x1800d8ab1  xor     rax, rsp
0x1800d8ab4  mov     [rbp+2D0h+var_40], rax
0x1800d8abb  mov     rdi, r8
0x1800d8abe  mov     rsi, rdx
0x1800d8ac1  mov     r15, rcx
0x1800d8ac4  xor     edx, edx; Val
0x1800d8ac6  mov     r8d, 104h; Size
0x1800d8acc  lea     rcx, [rbp+2D0h+pszOut]; void *
0x1800d8ad3  call    memset
0x1800d8ad8  lea     rdx, aWuClientDownlo; "WU Client Download"
0x1800d8adf  mov     rcx, rsi
0x1800d8ae2  call    _o__stricmp_0
0x1800d8ae7  mov     r12d, 17h
0x1800d8aed  lea     r13d, [r12-6]
0x1800d8af2  test    eax, eax
0x1800d8af4  jnz     short loc_1800D8B00
0x1800d8af6  mov     edi, 4
0x1800d8afb  jmp     loc_1800D8EA4
0x1800d8b00  xor     bl, bl
0x1800d8b02  test    rdi, rdi
0x1800d8b05  jz      loc_1800D9239
0x1800d8b0b  cmp     [rdi], bl
0x1800d8b0d  jz      loc_1800D9239
0x1800d8b13  xor     r9d, r9d; unsigned __int16 *
0x1800d8b16  lea     rdx, [rbp+2D0h+pszOut]; pszOut
0x1800d8b1d  mov     rcx, rdi; pszIn
0x1800d8b20  call    ?UrlGetHostName@@YAJPEBDPEADIPEAG@Z; UrlGetHostName(char const *,char *,uint,ushort *)
0x1800d8b25  test    eax, eax
0x1800d8b27  js      loc_1800D9239
0x1800d8b2d  mov     edi, 4
0x1800d8b32  mov     ecx, cs:_tls_index
0x1800d8b38  mov     rax, gs:58h
0x1800d8b41  mov     rax, [rax+rcx*8]
0x1800d8b45  mov     eax, [rdi+rax]
0x1800d8b48  cmp     cs:dword_180195DD0, eax
0x1800d8b4e  jle     loc_1800D8E7F
0x1800d8b54  lea     rcx, dword_180195DD0
0x1800d8b5b  call    _Init_thread_header
0x1800d8b60  cmp     cs:dword_180195DD0, 0FFFFFFFFh
0x1800d8b67  jnz     loc_1800D8E7F
0x1800d8b6d  xorps   xmm0, xmm0
0x1800d8b70  xor     eax, eax
0x1800d8b72  movups  cs:xmmword_180195DD8, xmm0
0x1800d8b79  mov     cs:qword_180195DE8, rax
0x1800d8b80  movups  [rsp+3D0h+var_390], xmm0
0x1800d8b85  xorps   xmm1, xmm1
0x1800d8b88  movdqa  [rsp+3D0h+var_380], xmm1
0x1800d8b8e  lea     r8d, [rax+13h]
0x1800d8b92  lea     rdx, aAduMicrosoftCo; "*.adu.microsoft.com"
0x1800d8b99  lea     rcx, [rsp+3D0h+var_390]
0x1800d8b9e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8ba3  nop
0x1800d8ba4  xorps   xmm0, xmm0
0x1800d8ba7  movups  [rsp+3D0h+var_370], xmm0
0x1800d8bac  xorps   xmm1, xmm1
0x1800d8baf  movdqa  [rsp+3D0h+var_360], xmm1
0x1800d8bb5  mov     r8d, 10h
0x1800d8bbb  lea     rdx, aCdnOfficeNet; "*.cdn.office.net"
0x1800d8bc2  lea     rcx, [rsp+3D0h+var_370]
0x1800d8bc7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8bcc  nop
0x1800d8bcd  xorps   xmm0, xmm0
0x1800d8bd0  movups  [rbp+2D0h+var_350], xmm0
0x1800d8bd4  xorps   xmm1, xmm1
0x1800d8bd7  movdqa  [rbp+2D0h+var_340], xmm1
0x1800d8bdc  mov     r8, r12
0x1800d8bdf  lea     rdx, aCtldlWindowsup; "ctldl.windowsupdate.com"
0x1800d8be6  lea     rcx, [rbp+2D0h+var_350]
0x1800d8bea  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8bef  nop
0x1800d8bf0  xorps   xmm0, xmm0
0x1800d8bf3  movups  [rbp+2D0h+var_330], xmm0
0x1800d8bf7  xorps   xmm1, xmm1
0x1800d8bfa  movdqa  [rbp+2D0h+var_320], xmm1
0x1800d8bff  mov     ebx, 1Bh
0x1800d8c04  mov     r8d, ebx
0x1800d8c07  lea     rdx, aDcatDspMpMicro; "*.dcat.dsp.mp.microsoft.com"
0x1800d8c0e  lea     rcx, [rbp+2D0h+var_330]
0x1800d8c12  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8c17  nop
0x1800d8c18  xorps   xmm0, xmm0
0x1800d8c1b  movups  [rbp+2D0h+var_310], xmm0
0x1800d8c1f  xorps   xmm1, xmm1
0x1800d8c22  movdqa  [rbp+2D0h+var_300], xmm1
0x1800d8c27  mov     r8d, ebx
0x1800d8c2a  lea     rdx, aDeliveryMpMicr; "*.delivery.mp.microsoft.com"
0x1800d8c31  lea     rcx, [rbp+2D0h+var_310]
0x1800d8c35  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8c3a  nop
0x1800d8c3b  xorps   xmm0, xmm0
0x1800d8c3e  movups  [rbp+2D0h+var_2F0], xmm0
0x1800d8c42  xorps   xmm1, xmm1
0x1800d8c45  movdqa  [rbp+2D0h+var_2E0], xmm1
0x1800d8c4a  lea     r8d, [rbx-1]
0x1800d8c4e  lea     rdx, aDownloadWindow_0; "download.windowsupdate.com"
0x1800d8c55  lea     rcx, [rbp+2D0h+var_2F0]
0x1800d8c59  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8c5e  nop
0x1800d8c5f  xorps   xmm0, xmm0
0x1800d8c62  movups  [rbp+2D0h+var_2D0], xmm0
0x1800d8c66  xorps   xmm1, xmm1
0x1800d8c69  movdqa  [rbp+2D0h+var_2C0], xmm1
0x1800d8c6e  lea     r8d, [rbx+1]
0x1800d8c72  lea     rdx, aDownloadWindow; "*.download.windowsupdate.com"
0x1800d8c79  lea     rcx, [rbp+2D0h+var_2D0]
0x1800d8c7d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8c82  nop
0x1800d8c83  xorps   xmm0, xmm0
0x1800d8c86  movups  [rbp+2D0h+var_2B0], xmm0
0x1800d8c8a  xorps   xmm1, xmm1
0x1800d8c8d  movdqa  [rbp+2D0h+var_2A0], xmm1
0x1800d8c92  mov     r8, r12
0x1800d8c95  lea     rdx, aM365StaticMicr; "*.m365.static.microsoft"
0x1800d8c9c  lea     rcx, [rbp+2D0h+var_2B0]
0x1800d8ca0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8ca5  nop
0x1800d8ca6  xorps   xmm0, xmm0
0x1800d8ca9  movups  [rbp+2D0h+var_290], xmm0
0x1800d8cad  xorps   xmm1, xmm1
0x1800d8cb0  movdqa  [rbp+2D0h+var_280], xmm1
0x1800d8cb5  mov     r8d, ebx
0x1800d8cb8  lea     rdx, aManageBetaMicr; "*.manage-beta.microsoft.com"
0x1800d8cbf  lea     rcx, [rbp+2D0h+var_290]
0x1800d8cc3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8cc8  nop
0x1800d8cc9  xorps   xmm0, xmm0
0x1800d8ccc  movups  [rbp+2D0h+var_270], xmm0
0x1800d8cd0  xorps   xmm1, xmm1
0x1800d8cd3  movdqa  [rbp+2D0h+var_260], xmm1
0x1800d8cd8  lea     r8d, [rbx+3]
0x1800d8cdc  lea     rdx, aManageDogfoodM; "*.manage-dogfood.microsoft.com"
0x1800d8ce3  lea     rcx, [rbp+2D0h+var_270]
0x1800d8ce7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8cec  nop
0x1800d8ced  xorps   xmm0, xmm0
0x1800d8cf0  movups  [rbp+2D0h+var_250], xmm0
0x1800d8cf7  xorps   xmm1, xmm1
0x1800d8cfa  movdqa  [rbp+2D0h+var_240], xmm1
0x1800d8d02  lea     r8d, [rbx+4]
0x1800d8d06  lea     rdx, aManageSelfhost; "*.manage-selfhost.microsoft.com"
0x1800d8d0d  lea     rcx, [rbp+2D0h+var_250]
0x1800d8d14  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8d19  nop
0x1800d8d1a  xorps   xmm0, xmm0
0x1800d8d1d  movups  [rbp+2D0h+var_230], xmm0
0x1800d8d24  xorps   xmm1, xmm1
0x1800d8d27  movdqa  [rbp+2D0h+var_220], xmm1
0x1800d8d2f  lea     r8d, [rbx-5]
0x1800d8d33  lea     rdx, aManageMicrosof; "*.manage.microsoft.com"
0x1800d8d3a  lea     rcx, [rbp+2D0h+var_230]
0x1800d8d41  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8d46  nop
0x1800d8d47  xorps   xmm0, xmm0
0x1800d8d4a  movups  [rbp+2D0h+var_210], xmm0
0x1800d8d51  xorps   xmm1, xmm1
0x1800d8d54  movdqa  [rbp+2D0h+var_200], xmm1
0x1800d8d5c  mov     r8, r12
0x1800d8d5f  lea     rdx, aOfficecdnMicro_0; "officecdn.microsoft.com"
0x1800d8d66  lea     rcx, [rbp+2D0h+var_210]
0x1800d8d6d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8d72  nop
0x1800d8d73  xorps   xmm0, xmm0
0x1800d8d76  movups  [rbp+2D0h+var_1F0], xmm0
0x1800d8d7d  xorps   xmm1, xmm1
0x1800d8d80  movdqa  [rbp+2D0h+var_1E0], xmm1
0x1800d8d88  lea     r8d, [rbx+0Ah]
0x1800d8d8c  lea     rdx, aOfficecdnMicro; "officecdn.microsoft.com.edgesuite.net"
0x1800d8d93  lea     rcx, [rbp+2D0h+var_1F0]
0x1800d8d9a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8d9f  nop
0x1800d8da0  xorps   xmm0, xmm0
0x1800d8da3  movups  [rbp+2D0h+var_1D0], xmm0
0x1800d8daa  xorps   xmm1, xmm1
0x1800d8dad  movdqa  [rbp+2D0h+var_1C0], xmm1
0x1800d8db5  lea     r8d, [rbx-7]
0x1800d8db9  lea     rdx, aTeamsCdnLiveNe; "*.teams.cdn.live.net"
0x1800d8dc0  lea     rcx, [rbp+2D0h+var_1D0]
0x1800d8dc7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8dcc  nop
0x1800d8dcd  xorps   xmm0, xmm0
0x1800d8dd0  movups  [rbp+2D0h+var_1B0], xmm0
0x1800d8dd7  xorps   xmm1, xmm1
0x1800d8dda  movdqa  [rbp+2D0h+var_1A0], xmm1
0x1800d8de2  lea     r8d, [rbx-3]
0x1800d8de6  lea     rdx, aTeamsStaticMic; "*.teams.static.microsoft"
0x1800d8ded  lea     rcx, [rbp+2D0h+var_1B0]
0x1800d8df4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8df9  nop
0x1800d8dfa  xorps   xmm0, xmm0
0x1800d8dfd  movups  [rbp+2D0h+var_190], xmm0
0x1800d8e04  xorps   xmm1, xmm1
0x1800d8e07  movdqa  [rbp+2D0h+var_180], xmm1
0x1800d8e0f  lea     r8d, [rbx-0Dh]
0x1800d8e13  lea     rdx, aXboxliveCom; "*.xboxlive.com"
0x1800d8e1a  lea     rcx, [rbp+2D0h+var_190]
0x1800d8e21  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8e26  nop
0x1800d8e27  lea     rax, [rsp+3D0h+var_390]
0x1800d8e2c  mov     [rsp+3D0h+var_3A0], rax
0x1800d8e31  lea     rax, [rbp+2D0h+var_170]
0x1800d8e38  mov     [rsp+3D0h+var_398], rax
0x1800d8e3d  lea     rdx, [rsp+3D0h+var_3A0]
0x1800d8e42  lea     rcx, xmmword_180195DD8
0x1800d8e49  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@AEBV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::vector<std::string>::vector<std::string>(std::initializer_list<std::string>,std::allocator<std::string> const &)
0x1800d8e4e  nop
0x1800d8e4f  lea     r9, ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; void (*)(void *)
0x1800d8e56  mov     r8, r13; unsigned __int64
0x1800d8e59  lea     edx, [rbx+5]; unsigned __int64
0x1800d8e5c  lea     rcx, [rsp+3D0h+var_390]; void *
0x1800d8e61  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800d8e66  lea     rcx, _CGlobalConfigManager__IsRegisteredCaller____10____dynamic_atexit_destructor_for__s_defaultAllowedHostNames__; void (__cdecl *)()
0x1800d8e6d  call    atexit
0x1800d8e72  nop
0x1800d8e73  lea     rcx, dword_180195DD0
0x1800d8e7a  call    _Init_thread_footer
0x1800d8e7f  lea     r9, xmmword_180195DD8
0x1800d8e86  lea     r8, [rbp+2D0h+pszOut]
0x1800d8e8d  mov     edx, 86h
0x1800d8e92  mov     rcx, r15
0x1800d8e95  call    ?_IsMatchForWildcardConfig@CGlobalConfigManager@@AEBA_NW4Index@DOConfig@@PEBDAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; CGlobalConfigManager::_IsMatchForWildcardConfig(DOConfig::Index,char const *,std::vector<std::string> const &)
0x1800d8e9a  mov     bl, al
0x1800d8e9c  test    al, al
0x1800d8e9e  jz      loc_1800D9239
0x1800d8ea4  mov     ecx, cs:_tls_index
0x1800d8eaa  mov     rax, gs:58h
0x1800d8eb3  mov     rax, [rax+rcx*8]
0x1800d8eb7  mov     eax, [rdi+rax]
0x1800d8eba  cmp     cs:dword_180195DF0, eax
0x1800d8ec0  jle     loc_1800D921C
0x1800d8ec6  lea     rcx, dword_180195DF0
0x1800d8ecd  call    _Init_thread_header
0x1800d8ed2  cmp     cs:dword_180195DF0, 0FFFFFFFFh
0x1800d8ed9  jnz     loc_1800D921C
0x1800d8edf  xorps   xmm0, xmm0
0x1800d8ee2  xor     eax, eax
0x1800d8ee4  movups  cs:xmmword_180195DF8, xmm0
0x1800d8eeb  mov     cs:qword_180195E08, rax
0x1800d8ef2  movups  [rsp+3D0h+var_390], xmm0
0x1800d8ef7  xorps   xmm1, xmm1
0x1800d8efa  movdqa  [rsp+3D0h+var_380], xmm1
0x1800d8f00  lea     ebx, [rax+0Fh]
0x1800d8f03  mov     r8d, ebx
0x1800d8f06  lea     rdx, aBeginloadrange; "BeginLoadRange*"
0x1800d8f0d  lea     rcx, [rsp+3D0h+var_390]
0x1800d8f12  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8f17  nop
0x1800d8f18  xorps   xmm0, xmm0
0x1800d8f1b  movups  [rsp+3D0h+var_370], xmm0
0x1800d8f20  xorps   xmm1, xmm1
0x1800d8f23  movdqa  [rsp+3D0h+var_360], xmm1
0x1800d8f29  mov     r8d, ebx
0x1800d8f2c  lea     rdx, aCheckreachable; "*CheckReachable"
0x1800d8f33  lea     rcx, [rsp+3D0h+var_370]
0x1800d8f38  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8f3d  nop
0x1800d8f3e  xorps   xmm0, xmm0
0x1800d8f41  movups  [rbp+2D0h+var_350], xmm0
0x1800d8f45  xorps   xmm1, xmm1
0x1800d8f48  movdqa  [rbp+2D0h+var_340], xmm1
0x1800d8f4d  lea     r8d, [rbx-5]
0x1800d8f51  lea     rdx, aDoloadfile; "DoLoadFile"
0x1800d8f58  lea     rcx, [rbp+2D0h+var_350]
0x1800d8f5c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8f61  nop
0x1800d8f62  xorps   xmm0, xmm0
0x1800d8f65  movups  [rbp+2D0h+var_330], xmm0
0x1800d8f69  xorps   xmm1, xmm1
0x1800d8f6c  movdqa  [rbp+2D0h+var_320], xmm1
0x1800d8f71  mov     r8d, ebx
0x1800d8f74  lea     rdx, aDocontentpolic; "DOContentPolicy"
0x1800d8f7b  lea     rcx, [rbp+2D0h+var_330]
0x1800d8f7f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8f84  nop
0x1800d8f85  xorps   xmm0, xmm0
0x1800d8f88  movups  [rbp+2D0h+var_310], xmm0
0x1800d8f8c  xorps   xmm1, xmm1
0x1800d8f8f  movdqa  [rbp+2D0h+var_300], xmm1
0x1800d8f94  mov     r8, r13
0x1800d8f97  lea     rdx, aEdgeupdateDoJo; "EdgeUpdate DO Job"
0x1800d8f9e  lea     rcx, [rbp+2D0h+var_310]
0x1800d8fa2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8fa7  nop
0x1800d8fa8  xorps   xmm0, xmm0
0x1800d8fab  movups  [rbp+2D0h+var_2F0], xmm0
0x1800d8faf  xorps   xmm1, xmm1
0x1800d8fb2  movdqa  [rbp+2D0h+var_2E0], xmm1
0x1800d8fb7  mov     r8, r13
0x1800d8fba  lea     rdx, aIntuneappdownl; "IntuneAppDownload"
0x1800d8fc1  lea     rcx, [rbp+2D0h+var_2F0]
0x1800d8fc5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
  ... truncated ...
```
