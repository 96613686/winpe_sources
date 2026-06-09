# CWebDriverHost::_CreateNewSession(ushort const *,ulong)

- ea: `0x180066a88`
- end: `0x180066d1e`
- name: `?_CreateNewSession@CWebDriverHost@@AEAAXPEBGK@Z`
- size: `662`
- prototype: `void __fastcall(CWebDriverHost *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180065cd0`

## callees

- `0x180018b30`
- `0x180019ad0`
- `0x18001a1f8`
- `0x18001ad34`
- `0x18001afe4`
- `0x18001b820`
- `0x18002b530`
- `0x18002b5a0`
- `0x180035b88`
- `0x180065374`
- `0x180065448`
- `0x180065614`
- `0x1800656cc`
- `0x180066a88`
- `0x180067178`
- `0x1800671bc`
- `0x180077804`
- `0x180079924`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180066b13`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180066b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ca4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066b3e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066b3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWebDriverHost::_CreateNewSession(void ***this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 *v5; // r9
  struct JSONNode *v6; // rsi
  HRESULT v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r9d
  const char *v12; // r9
  int v13; // r14d
  __int64 DefaultCapabilities; // rax
  LPOLESTR v15; // rax
  unsigned int v16; // edx
  void **v17; // rax
  void **v18; // rdx
  void **v19; // rdi
  unsigned __int16 *v20; // rbx
  void *v21; // rcx
  int v22; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v23; // [rsp+30h] [rbp-40h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  int v26; // [rsp+48h] [rbp-28h]
  int v27; // [rsp+4Ch] [rbp-24h]
  GUID pguid; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( *((_BYTE *)this + 192) )
  {
    CWebDriverHost::_ReplyToWebDriverServer((CWebDriverHost *)this, a3, 0x21u, 0, 0);
    return;
  }
  *(_QWORD *)&pguid.Data1 = 0;
  v25 = 0;
  v27 = -1;
  v26 = -1;
  ParseJson((struct WebDriverReturnResponse *)&v25, a2, (struct JSONNode **)&pguid);
  v5 = 0;
  v23 = 0;
  lpsz = 0;
  v6 = *(struct JSONNode **)&pguid.Data1;
  if ( !(_DWORD)v25 && *(_QWORD *)&pguid.Data1 && **(_DWORD **)&pguid.Data1 == 5 )
  {
    pguid = 0;
    v7 = CoCreateGuid(&pguid);
    if ( v7 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x21C,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverhost.cxx",
        (const char *)(unsigned int)v7,
        v22);
    v8 = StringFromCLSID(&pguid, &lpsz);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverhost.cxx",
        (const char *)(unsigned int)v8,
        v22);
    v9 = ConvertCodeToName(6);
    if ( JSONNode::operator[](v6, v9) )
    {
      DefaultCapabilities = CWebDriverHost::_GetDefaultCapabilities(v10, &v25);
      v13 = CWebDriverCapabilityChecker::PerformW3cWebDriverCapabilityChecking(
              (unsigned int)&v23,
              (_DWORD)v6,
              (_DWORD)lpsz,
              (int)this + 80,
              DefaultCapabilities,
              (__int64)&v23);
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<JSONNode>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<JSONNode>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<JSONNode>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<JSONNode>>>,0>>(&v25);
    }
    else
    {
      v13 = CWebDriverHost::_PerformJWPWebDriverCapabilityChecking(
              (CWebDriverHost *)this,
              v6,
              lpsz,
              v11,
              (struct WebDriverReturnResponse *)&v25,
              &v23);
    }
    if ( !v13 )
    {
      if ( this[22] )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x22E,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverhost.cxx",
          v12);
      v15 = lpsz;
      lpsz = 0;
      this[22] = (void **)v15;
      if ( *((_DWORD *)this + 30) )
      {
        CWebDriverHost::_PostNewSessionResponse((CWebDriverHost *)this, a3, v23);
      }
      else
      {
        if ( this[23] )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x23A,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverhost.cxx",
            v12);
        v17 = (void **)operator new(0x10u);
        *(_OWORD *)v17 = 0;
        *v17 = 0;
        *(_QWORD *)&pguid.Data1 = 0;
        v18 = this[23];
        this[23] = v17;
        if ( v18 )
          std::default_delete<CWebDriverHost::SessionResponse>::operator()();
        std::unique_ptr<CWebDriverHost::SessionResponse>::~unique_ptr<CWebDriverHost::SessionResponse>(&pguid);
        *((_DWORD *)this[23] + 2) = a3;
        v19 = this[23];
        v20 = v23;
        v23 = 0;
        v21 = *v19;
        *v19 = 0;
        CoTaskMemFree(v21);
        *v19 = v20;
      }
      goto LABEL_24;
    }
    v5 = v23;
  }
  CWebDriverHost::_ReplyToWebDriverServer((CWebDriverHost *)this, a3, 0x21u, v5, 0);
LABEL_24:
  if ( v6 )
    JSONNode::`scalar deleting destructor'(v6, v16);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v23);
}

```

## disassembly

```asm
0x180066a88  mov     [rsp-28h+arg_18], rbx
0x180066a8d  push    rbp
0x180066a8e  push    rsi
0x180066a8f  push    rdi
0x180066a90  push    r14
0x180066a92  push    r15
0x180066a94  mov     rbp, rsp
0x180066a97  sub     rsp, 70h
0x180066a9b  mov     rax, cs:__security_cookie
0x180066aa2  xor     rax, rsp
0x180066aa5  mov     [rbp+var_10], rax
0x180066aa9  mov     edi, r8d
0x180066aac  mov     rbx, rcx
0x180066aaf  xor     r15d, r15d
0x180066ab2  cmp     [rcx+0C0h], r15b
0x180066ab9  jnz     loc_180066CEB
0x180066abf  mov     qword ptr [rbp+pguid.Data1], r15
0x180066ac3  mov     [rbp+var_30], r15
0x180066ac7  or      eax, 0FFFFFFFFh
0x180066aca  mov     [rbp+var_24], eax
0x180066acd  mov     [rbp+var_28], eax
0x180066ad0  lea     r8, [rbp+pguid]; struct JSONNode **
0x180066ad4  lea     rcx, [rbp+var_30]; struct WebDriverReturnResponse *
0x180066ad8  call    ?ParseJson@@YAXPEAUWebDriverReturnResponse@@PEBGPEAPEAUJSONNode@@@Z; ParseJson(WebDriverReturnResponse *,ushort const *,JSONNode * *)
0x180066add  mov     r9d, r15d
0x180066ae0  mov     [rbp+var_40], r15
0x180066ae4  mov     [rbp+lpsz], r15
0x180066ae8  mov     rsi, qword ptr [rbp+pguid.Data1]
0x180066aec  cmp     dword ptr [rbp+var_30], r15d
0x180066af0  jnz     loc_180066CB3
0x180066af6  test    rsi, rsi
0x180066af9  jz      loc_180066CB3
0x180066aff  cmp     dword ptr [rsi], 5
0x180066b02  jnz     loc_180066CB3
0x180066b08  xorps   xmm0, xmm0
0x180066b0b  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x180066b0f  lea     rcx, [rbp+pguid]; pguid
0x180066b13  call    cs:__imp_CoCreateGuid
0x180066b19  mov     rcx, [rbp+28h]; this
0x180066b1d  test    eax, eax
0x180066b1f  jns     short loc_180066B36
0x180066b21  mov     r9d, eax; char *
0x180066b24  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180066b2b  mov     edx, 21Ch; void *
0x180066b30  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180066b36  lea     rdx, [rbp+lpsz]; lplpsz
0x180066b3a  lea     rcx, [rbp+pguid]; rclsid
0x180066b3e  call    cs:__imp_StringFromCLSID
0x180066b44  mov     rcx, [rbp+28h]; this
0x180066b48  test    eax, eax
0x180066b4a  jns     short loc_180066B61
0x180066b4c  mov     r9d, eax; char *
0x180066b4f  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180066b56  mov     edx, 21Dh; void *
0x180066b5b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180066b61  mov     ecx, 6
0x180066b66  call    ?ConvertCodeToName@@YAPEBGW4WebDriverName@@@Z; ConvertCodeToName(WebDriverName)
0x180066b6b  mov     rdx, rax
0x180066b6e  mov     rcx, rsi
0x180066b71  call    ??AJSONNode@@QEBAPEBU0@PEBG@Z; JSONNode::operator[](ushort const *)
0x180066b76  test    rax, rax
0x180066b79  jnz     short loc_180066BA1
0x180066b7b  lea     rax, [rbp+var_40]
0x180066b7f  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x180066b84  lea     rax, [rbp+var_30]
0x180066b88  mov     [rsp+70h+var_50], rax; struct WebDriverReturnResponse *
0x180066b8d  mov     r8, [rbp+lpsz]; unsigned __int16 *
0x180066b91  mov     rdx, rsi; struct JSONNode *
0x180066b94  mov     rcx, rbx; this
0x180066b97  call    ?_PerformJWPWebDriverCapabilityChecking@CWebDriverHost@@AEAAJPEAUJSONNode@@QEBGKAEAUWebDriverReturnResponse@@PEAPEAG@Z; CWebDriverHost::_PerformJWPWebDriverCapabilityChecking(JSONNode *,ushort const * const,ulong,WebDriverReturnResponse &,ushort * *)
0x180066b9c  mov     r14d, eax
0x180066b9f  jmp     short loc_180066BD5
0x180066ba1  lea     rdx, [rbp+var_30]
0x180066ba5  call    ?_GetDefaultCapabilities@CWebDriverHost@@AEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@2@@std@@@2@@std@@XZ; CWebDriverHost::_GetDefaultCapabilities(void)
0x180066baa  nop
0x180066bab  lea     r9, [rbx+50h]
0x180066baf  lea     rcx, [rbp+var_40]
0x180066bb3  mov     [rsp+70h+var_48], rcx
0x180066bb8  mov     [rsp+70h+var_50], rax
0x180066bbd  mov     r8, [rbp+lpsz]
0x180066bc1  mov     rdx, rsi
0x180066bc4  call    ?PerformW3cWebDriverCapabilityChecking@CWebDriverCapabilityChecker@@QEAAJPEBUJSONNode@@QEBGPEAUIWebDriverCapabilityConfigurator@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@2@@std@@@2@@std@@PEAPEAG@Z; CWebDriverCapabilityChecker::PerformW3cWebDriverCapabilityChecking(JSONNode const *,ushort const * const,IWebDriverCapabilityConfigurator *,std::map<std::wstring,std::unique_ptr<JSONNode>> const &,ushort * *)
0x180066bc9  mov     r14d, eax
0x180066bcc  lea     rcx, [rbp+var_30]
0x180066bd0  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<JSONNode>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<JSONNode>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<JSONNode>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<JSONNode>>>,0>>(void)
0x180066bd5  test    r14d, r14d
0x180066bd8  jnz     loc_180066CAF
0x180066bde  mov     rcx, [rbp+28h]; this
0x180066be2  cmp     [rbx+0B0h], r15
0x180066be9  jz      short loc_180066BFD
0x180066beb  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180066bf2  mov     edx, 22Eh; void *
0x180066bf7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180066bfd  mov     rax, [rbp+lpsz]
0x180066c01  mov     [rbp+lpsz], r15
0x180066c05  mov     [rbx+0B0h], rax
0x180066c0c  cmp     [rbx+78h], r15d
0x180066c10  jz      short loc_180066C25
0x180066c12  mov     r8, [rbp+var_40]; unsigned __int16 *
0x180066c16  mov     edx, edi; unsigned int
0x180066c18  mov     rcx, rbx; this
0x180066c1b  call    ?_PostNewSessionResponse@CWebDriverHost@@AEAAXKPEAG@Z; CWebDriverHost::_PostNewSessionResponse(ulong,ushort *)
0x180066c20  jmp     loc_180066CC8
0x180066c25  cmp     [rbx+0B8h], r15
0x180066c2c  setnz   al
0x180066c2f  mov     rcx, [rbp+28h]; this
0x180066c33  test    al, al
0x180066c35  jz      short loc_180066C49
0x180066c37  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180066c3e  mov     edx, 23Ah; void *
0x180066c43  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180066c49  mov     ecx, 10h; Size
0x180066c4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066c53  mov     qword ptr [rbp+pguid.Data1], rax
0x180066c57  xorps   xmm0, xmm0
0x180066c5a  movups  xmmword ptr [rax], xmm0
0x180066c5d  mov     [rax], r15
0x180066c60  mov     qword ptr [rbp+pguid.Data1], r15
0x180066c64  mov     rdx, [rbx+0B8h]
0x180066c6b  mov     [rbx+0B8h], rax
0x180066c72  test    rdx, rdx
0x180066c75  jz      short loc_180066C7C
0x180066c77  call    ??R?$default_delete@USessionResponse@CWebDriverHost@@@std@@QEBAXPEAUSessionResponse@CWebDriverHost@@@Z; std::default_delete<CWebDriverHost::SessionResponse>::operator()(CWebDriverHost::SessionResponse *)
0x180066c7c  lea     rcx, [rbp+pguid]
0x180066c80  call    ??1?$unique_ptr@USessionResponse@CWebDriverHost@@U?$default_delete@USessionResponse@CWebDriverHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWebDriverHost::SessionResponse>::~unique_ptr<CWebDriverHost::SessionResponse>(void)
0x180066c85  mov     rax, [rbx+0B8h]
0x180066c8c  mov     [rax+8], edi
0x180066c8f  mov     rdi, [rbx+0B8h]
0x180066c96  mov     rbx, [rbp+var_40]
0x180066c9a  mov     [rbp+var_40], r15
0x180066c9e  mov     rcx, [rdi]; pv
0x180066ca1  mov     [rdi], r15
0x180066ca4  call    cs:__imp_CoTaskMemFree
0x180066caa  mov     [rdi], rbx
0x180066cad  jmp     short loc_180066CC8
0x180066caf  mov     r9, [rbp+var_40]; unsigned __int16 *
0x180066cb3  mov     dword ptr [rsp+70h+var_50], r15d; int
0x180066cb8  mov     r8d, 21h ; '!'; unsigned int
0x180066cbe  mov     edx, edi; unsigned int
0x180066cc0  mov     rcx, rbx; this
0x180066cc3  call    ?_ReplyToWebDriverServer@CWebDriverHost@@AEAAJKKPEBGH@Z; CWebDriverHost::_ReplyToWebDriverServer(ulong,ulong,ushort const *,int)
0x180066cc8  test    rsi, rsi
0x180066ccb  jz      short loc_180066CD6
0x180066ccd  mov     rcx, rsi; this
0x180066cd0  call    ??_GJSONNode@@QEAAPEAXI@Z; JSONNode::`scalar deleting destructor'(uint)
0x180066cd5  nop
0x180066cd6  lea     rcx, [rbp+lpsz]
0x180066cda  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180066cdf  nop
0x180066ce0  lea     rcx, [rbp+var_40]
0x180066ce4  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180066ce9  jmp     short loc_180066CFE
0x180066ceb  mov     dword ptr [rsp+70h+var_50], r15d; int
0x180066cf0  xor     r9d, r9d; unsigned __int16 *
0x180066cf3  lea     r8d, [r9+21h]; unsigned int
0x180066cf7  mov     edx, edi; unsigned int
0x180066cf9  call    ?_ReplyToWebDriverServer@CWebDriverHost@@AEAAJKKPEBGH@Z; CWebDriverHost::_ReplyToWebDriverServer(ulong,ulong,ushort const *,int)
0x180066cfe  mov     rcx, [rbp+var_10]
0x180066d02  xor     rcx, rsp; StackCookie
0x180066d05  call    __security_check_cookie
0x180066d0a  mov     rbx, [rsp+70h+arg_18]
0x180066d12  add     rsp, 70h
0x180066d16  pop     r15
0x180066d18  pop     r14
0x180066d1a  pop     rdi
0x180066d1b  pop     rsi
0x180066d1c  pop     rbp
0x180066d1d  retn
```
