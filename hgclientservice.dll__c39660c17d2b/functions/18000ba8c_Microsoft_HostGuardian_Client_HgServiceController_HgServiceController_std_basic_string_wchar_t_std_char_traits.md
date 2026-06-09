# Microsoft::HostGuardian::Client::HgServiceController::HgServiceController(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000ba8c`
- end: `0x18000bcf2`
- name: `??0HgServiceController@Client@HostGuardian@Microsoft@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009300`

## callees

- `0x180001794`
- `0x180001bb4`
- `0x180008780`
- `0x18000a7bc`
- `0x18000ba8c`
- `0x18000ee6c`
- `0x180011274`
- `0x180012234`
- `0x180013d28`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bb64`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bbf0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bb64`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bbf0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000bc75`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000bc75`

## string_xrefs

- `0x18000bcce`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000bce0`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x18000bb5d`: `%programdata%\Microsoft\HgClient`
- `0x18000bbe9`: `%programdata%\Microsoft\HgClient`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::HgServiceController(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  DWORD v5; // eax
  const char *v6; // r9
  unsigned __int64 v7; // rcx
  _WORD *v8; // rdi
  unsigned __int64 i; // rcx
  WCHAR *v10; // rdx
  __time64_t *v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  const char *v14; // r9
  Microsoft::HostGuardian::Client::CertificateCache *v15; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __time64_t Time; // [rsp+80h] [rbp+18h] BYREF
  __time64_t *v19; // [rsp+88h] [rbp+20h]

  Microsoft::HostGuardian::Client::HgServicePlugin::HgServicePlugin(a1, a2);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  Time = a1 + 160;
  *(_QWORD *)(a1 + 160) = &Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable';
  v3 = (_QWORD *)(a1 + 168);
  *(_OWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 7;
  *(_WORD *)(a1 + 168) = 0;
  v19 = (__time64_t *)(a1 + 200);
  *(_DWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  v4 = operator new(0xA8u);
  *v4 = v4;
  v4[1] = v4;
  *(_QWORD *)(a1 + 208) = v4;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 7;
  *(_QWORD *)(a1 + 256) = 8;
  *(_DWORD *)(a1 + 200) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>::_Assign_grow(
    a1 + 224,
    16,
    *(_QWORD *)(a1 + 208));
  *(_QWORD *)(a1 + 264) = 0;
  v5 = ExpandEnvironmentStringsW(L"%programdata%\\Microsoft\\HgClient", 0, 0);
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
      v6);
  v7 = *(_QWORD *)(a1 + 184);
  if ( v5 <= v7 )
  {
    *(_QWORD *)(a1 + 184) = v5;
    if ( *(_QWORD *)(a1 + 192) > 7u )
      v3 = (_QWORD *)*v3;
LABEL_12:
    *((_WORD *)v3 + v5) = 0;
    goto LABEL_14;
  }
  if ( v5 - v7 <= *(_QWORD *)(a1 + 192) - v7 )
  {
    *(_QWORD *)(a1 + 184) = v5;
    if ( *(_QWORD *)(a1 + 192) > 7u )
      v3 = (_QWORD *)*v3;
    v8 = (_WORD *)v3 + v7;
    if ( v5 != v7 )
    {
      for ( i = v5 - v7; i; --i )
        *v8++ = 0;
    }
    goto LABEL_12;
  }
  std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>((void *)(a1 + 168));
LABEL_14:
  v10 = (WCHAR *)(a1 + 168);
  if ( *(_QWORD *)(a1 + 192) > 7u )
    v10 = *(WCHAR **)v10;
  ExpandEnvironmentStringsW(L"%programdata%\\Microsoft\\HgClient", v10, *(_DWORD *)(a1 + 184));
  *(_QWORD *)(a1 + 160) = &Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable';
  v11 = (__time64_t *)operator new(0x30u);
  v19 = v11;
  v11[1] = 0;
  v11[2] = 0;
  v12 = operator new(0x38u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  v11[1] = (__time64_t)v12;
  v11[3] = 0;
  v11[4] = 0;
  v13 = operator new(0x48u);
  *v13 = v13;
  v13[1] = v13;
  v13[2] = v13;
  *((_WORD *)v13 + 12) = 257;
  v11[3] = (__time64_t)v13;
  v11[5] = 0;
  Time = 0;
  _time64(&Time);
  *v11 = Time;
  v15 = *(Microsoft::HostGuardian::Client::CertificateCache **)(a1 + 136);
  *(_QWORD *)(a1 + 136) = v11;
  if ( v15 )
  {
    Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(v15);
    operator delete(v15);
  }
  if ( !*(_QWORD *)(a1 + 136) )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x17,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v14);
  return a1;
}

```

## disassembly

```asm
0x18000ba8c  mov     [rsp+arg_8], rbx
0x18000ba91  mov     [rsp+arg_0], rcx
0x18000ba96  push    rbp
0x18000ba97  push    rsi
0x18000ba98  push    rdi
0x18000ba99  push    r12
0x18000ba9b  push    r14
0x18000ba9d  sub     rsp, 40h
0x18000baa1  mov     rsi, rcx
0x18000baa4  xor     ebp, ebp
0x18000baa6  call    ??0HgServicePlugin@Client@HostGuardian@Microsoft@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::HgServicePlugin(std::wstring const &)
0x18000baab  nop
0x18000baac  mov     [rsi+88h], rbp
0x18000bab3  mov     [rsi+90h], rbp
0x18000baba  xor     eax, eax
0x18000babc  mov     [rsi+98h], rax
0x18000bac3  lea     r14, [rsi+0A0h]
0x18000baca  mov     [rsp+68h+Time], r14
0x18000bad2  lea     r12, ??_7HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable'
0x18000bad9  mov     [r14], r12
0x18000badc  lea     rbx, [r14+8]
0x18000bae0  xorps   xmm0, xmm0
0x18000bae3  movups  xmmword ptr [rbx], xmm0
0x18000bae6  mov     [rbx+10h], rbp
0x18000baea  mov     qword ptr [rbx+18h], 7
0x18000baf2  mov     [rbx], bp
0x18000baf5  lea     rdi, [r14+28h]
0x18000baf9  mov     [rsp+68h+arg_18], rdi
0x18000bb01  mov     [rdi], ebp
0x18000bb03  mov     [rdi+8], rbp
0x18000bb07  mov     [rdi+10h], rbp
0x18000bb0b  mov     ecx, 0A8h; Size
0x18000bb10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb15  mov     [rax], rax
0x18000bb18  mov     [rax+8], rax
0x18000bb1c  mov     [rdi+8], rax
0x18000bb20  lea     rcx, [rdi+18h]
0x18000bb24  mov     [rcx], rbp
0x18000bb27  mov     [rcx+8], rbp
0x18000bb2b  mov     [rcx+10h], rbp
0x18000bb2f  mov     qword ptr [rdi+30h], 7
0x18000bb37  mov     qword ptr [rdi+38h], 8
0x18000bb3f  mov     dword ptr [rdi], 3F800000h
0x18000bb45  mov     r8, [rdi+8]
0x18000bb49  lea     edx, [rbp+10h]
0x18000bb4c  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>)
0x18000bb51  nop
0x18000bb52  xor     eax, eax
0x18000bb54  mov     [r14+68h], rax
0x18000bb58  xor     r8d, r8d; nSize
0x18000bb5b  xor     edx, edx; lpDst
0x18000bb5d  lea     rcx, ?c_defaultCacheRoot@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@0QB_WB; "%programdata%\\Microsoft\\HgClient"
0x18000bb64  call    cs:__imp_ExpandEnvironmentStringsW
0x18000bb6a  mov     rcx, [rsp+68h]; this
0x18000bb6f  test    eax, eax
0x18000bb71  jz      loc_18000BCE0
0x18000bb77  mov     r8d, eax
0x18000bb7a  mov     rcx, [rbx+10h]
0x18000bb7e  cmp     r8, rcx
0x18000bb81  ja      short loc_18000BB93
0x18000bb83  mov     [rbx+10h], r8
0x18000bb87  cmp     qword ptr [rbx+18h], 7
0x18000bb8c  jbe     short loc_18000BBC5
0x18000bb8e  mov     rbx, [rbx]
0x18000bb91  jmp     short loc_18000BBC5
0x18000bb93  mov     rdx, r8
0x18000bb96  sub     rdx, rcx
0x18000bb99  mov     rax, [rbx+18h]
0x18000bb9d  sub     rax, rcx
0x18000bba0  cmp     rdx, rax
0x18000bba3  ja      short loc_18000BBCC
0x18000bba5  mov     [rbx+10h], r8
0x18000bba9  cmp     qword ptr [rbx+18h], 7
0x18000bbae  jbe     short loc_18000BBB3
0x18000bbb0  mov     rbx, [rbx]
0x18000bbb3  lea     rdi, [rbx+rcx*2]
0x18000bbb7  test    rdx, rdx
0x18000bbba  jz      short loc_18000BBC5
0x18000bbbc  movzx   eax, bp
0x18000bbbf  mov     rcx, rdx
0x18000bbc2  rep stosw
0x18000bbc5  mov     [rbx+r8*2], bp
0x18000bbca  jmp     short loc_18000BBD7
0x18000bbcc  mov     r9, rdx
0x18000bbcf  mov     rcx, rbx; Src
0x18000bbd2  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x18000bbd7  lea     rdx, [r14+8]
0x18000bbdb  cmp     qword ptr [rdx+18h], 7
0x18000bbe0  jbe     short loc_18000BBE5
0x18000bbe2  mov     rdx, [rdx]; lpDst
0x18000bbe5  mov     r8d, [r14+18h]; nSize
0x18000bbe9  lea     rcx, ?c_defaultCacheRoot@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@0QB_WB; "%programdata%\\Microsoft\\HgClient"
0x18000bbf0  call    cs:__imp_ExpandEnvironmentStringsW
0x18000bbf6  nop
0x18000bbf7  mov     [r14], r12
0x18000bbfa  mov     r14d, 30h ; '0'
0x18000bc00  mov     ecx, r14d; Size
0x18000bc03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc08  mov     rbx, rax
0x18000bc0b  mov     [rsp+68h+arg_18], rax
0x18000bc13  mov     [rax+8], rbp
0x18000bc17  mov     [rax+10h], rbp
0x18000bc1b  lea     ecx, [r14+8]; Size
0x18000bc1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc24  mov     [rax], rax
0x18000bc27  mov     [rax+8], rax
0x18000bc2b  mov     [rax+10h], rax
0x18000bc2f  mov     word ptr [rax+18h], 101h
0x18000bc35  mov     [rbx+8], rax
0x18000bc39  mov     [rbx+18h], rbp
0x18000bc3d  mov     [rbx+20h], rbp
0x18000bc41  lea     ecx, [r14+18h]; Size
0x18000bc45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc4a  mov     [rax], rax
0x18000bc4d  mov     [rax+8], rax
0x18000bc51  mov     [rax+10h], rax
0x18000bc55  mov     word ptr [rax+18h], 101h
0x18000bc5b  mov     [rbx+18h], rax
0x18000bc5f  xor     eax, eax
0x18000bc61  mov     [rbx+28h], rax
0x18000bc65  mov     [rsp+68h+Time], rbp
0x18000bc6d  lea     rcx, [rsp+68h+Time]; Time
0x18000bc75  call    cs:__imp__time64
0x18000bc7b  mov     rax, [rsp+68h+Time]
0x18000bc83  mov     [rbx], rax
0x18000bc86  mov     rdi, [rsi+88h]
0x18000bc8d  mov     [rsi+88h], rbx
0x18000bc94  test    rdi, rdi
0x18000bc97  jz      short loc_18000BCAC
0x18000bc99  mov     rcx, rdi; this
0x18000bc9c  call    ??1CertificateCache@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(void)
0x18000bca1  mov     edx, r14d
0x18000bca4  mov     rcx, rdi; Block
0x18000bca7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bcac  mov     rcx, [rsp+68h]; this
0x18000bcb1  cmp     [rsi+88h], rbp
0x18000bcb8  jz      short loc_18000BCCE
0x18000bcba  mov     rax, rsi
0x18000bcbd  mov     rbx, [rsp+68h+arg_8]
0x18000bcc2  add     rsp, 40h
0x18000bcc6  pop     r14
0x18000bcc8  pop     r12
0x18000bcca  pop     rdi
0x18000bccb  pop     rsi
0x18000bccc  pop     rbp
0x18000bccd  retn
0x18000bcce  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000bcd5  mov     edx, 17h; void *
0x18000bcda  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000bce0  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x18000bce7  mov     edx, 1Fh; void *
0x18000bcec  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
