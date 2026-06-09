# cdp::ActivityManager::GetActivitiesByAppActivityIdAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,CDPDownloadOptionFlags,uint,char const *)

- ea: `0x180029360`
- end: `0x1800298d4`
- name: `?GetActivitiesByAppActivityIdAsync@ActivityManager@cdp@@UEAAXW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBDW4CDPDownloadOptionFlags@@I2@Z`
- size: `1396`
- prototype: `void __high(enum CDPActivityType, struct ICDPCrossPlatformAppId *, const char *, enum CDPDownloadOptionFlags, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x1800117f8`
- `0x180013da0`
- `0x180029360`
- `0x1800298dc`
- `0x180029abc`
- `0x18002a444`
- `0x180030190`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fcb36`
- `0x1801fcb4e`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002971d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800297ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002971d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800297ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029839`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800298b1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800298bf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800298cd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800298b1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800298bf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800298cd`

## string_xrefs

- `0x180029748`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800297d6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180029864`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall cdp::ActivityManager::GetActivitiesByAppActivityIdAsync(
        const char *a1,
        int a2,
        __int64 a3,
        _BYTE *a4,
        __int16 a5,
        int a6,
        __int64 a7)
{
  void *v9; // r13
  size_t v10; // rbx
  __int64 v11; // rdi
  unsigned __int64 v12; // rsi
  void *v13; // r12
  const char *v14; // rcx
  void **v15; // r14
  unsigned __int64 v16; // rbx
  void **v17; // rsi
  const char *v18; // rdi
  void (__fastcall *v19)(const char *, _BYTE *); // rbx
  _BYTE *v20; // rdx
  unsigned __int64 v21; // rsi
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  char v37; // [rsp+30h] [rbp-D0h] BYREF
  int v38; // [rsp+38h] [rbp-C8h] BYREF
  const char *v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 CurrentThreadId; // [rsp+50h] [rbp-B0h] BYREF
  char *v42; // [rsp+58h] [rbp-A8h]
  char v43; // [rsp+60h] [rbp-A0h]
  void *Src[2]; // [rsp+68h] [rbp-98h] BYREF
  size_t v45; // [rsp+78h] [rbp-88h]
  __int64 v46; // [rsp+80h] [rbp-80h]
  const char *v47; // [rsp+A0h] [rbp-60h] BYREF
  int v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  std::_Ref_count_base *v50; // [rsp+B8h] [rbp-48h]
  __int128 v51; // [rsp+C0h] [rbp-40h] BYREF
  size_t v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+E0h] [rbp-20h]
  __int16 v55; // [rsp+E4h] [rbp-1Ch]
  __int128 v56; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v57; // [rsp+F8h] [rbp-8h]
  __int64 v58; // [rsp+100h] [rbp+0h]
  void *v59[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v60; // [rsp+120h] [rbp+20h]
  unsigned __int64 v61; // [rsp+128h] [rbp+28h]
  _BYTE v62[56]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE *v63; // [rsp+168h] [rbp+68h]

  v38 = a2;
  v39 = a1;
  cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(a1, v59, a7);
  if ( !(unsigned __int8)cdp::CorrelationVectorData::Increment(v59) )
  {
    v39 = "..\\activitymanager.cpp";
    v40 = 1714;
    v38 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v22,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v38,
      (unsigned int)&v39,
      (__int64)&v40,
      (__int64)&CurrentThreadId);
    v23 = cdp::ExceptionStackFromSourceLocationInfo(&CurrentThreadId, &v39);
    v26 = cdp::ErrorCodeToString(2147942487LL, v24, v25, v23);
    ConnectedDevices::Exception::Exception(Src, 2147942487LL, v26);
    throw (ConnectedDevices::Exception *)Src;
  }
  if ( !a3 )
  {
    v39 = "..\\activitymanager.cpp";
    v40 = 1719;
    v38 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v27,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v38,
      (unsigned int)&v39,
      (__int64)&v40,
      (__int64)&CurrentThreadId);
    v28 = cdp::ExceptionStackFromSourceLocationInfo(&CurrentThreadId, &v39);
    v31 = cdp::ErrorCodeToString(2147942487LL, v29, v30, v28);
    ConnectedDevices::Exception::Exception(Src, 2147942487LL, v31);
    throw (ConnectedDevices::Exception *)Src;
  }
  if ( !a4 )
  {
    v39 = "..\\activitymanager.cpp";
    v40 = 1720;
    v38 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v32,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v38,
      (unsigned int)&v39,
      (__int64)&v40,
      (__int64)&CurrentThreadId);
    v33 = cdp::ExceptionStackFromSourceLocationInfo(&CurrentThreadId, &v39);
    v36 = cdp::ErrorCodeToString(2147942487LL, v34, v35, v33);
    ConnectedDevices::Exception::Exception(Src, 2147942487LL, v36);
    throw (ConnectedDevices::Exception *)Src;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  CurrentThreadId = a3;
  v42 = &v37;
  v43 = 1;
  v9 = operator new(0x18u);
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
  *((_QWORD *)v9 + 2) = a3;
  CurrentThreadId = a3;
  v42 = (char *)v9;
  *(_OWORD *)Src = 0;
  v45 = 0;
  v46 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a4[v10] );
  v11 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v10 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("string too long");
  if ( v10 > 0xF )
  {
    v12 = v10 | 0xF;
    if ( (v10 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v12 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else if ( v12 < 0x16 )
    {
      v12 = 22;
    }
    v13 = (void *)std::allocator<char>::allocate(Src, v12 + 1);
    Src[0] = v13;
    v45 = v10;
    v46 = v12;
    memcpy_0(v13, a4, v10);
    *((_BYTE *)v13 + v10) = 0;
  }
  else
  {
    v45 = v10;
    v46 = 15;
    memcpy_0(Src, a4, v10);
    *((_BYTE *)Src + v10) = 0;
    v12 = v46;
    v10 = v45;
    v13 = Src[0];
  }
  v14 = v39;
  v39 = (const char *)*((_QWORD *)v39 + 123);
  v47 = v14;
  v48 = v38;
  _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
  v49 = a3;
  v50 = (std::_Ref_count_base *)v9;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v15 = Src;
  if ( v12 > 0xF )
    v15 = (void **)v13;
  if ( v10 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("string too long");
  if ( v10 > 0xF )
  {
    v21 = v10 | 0xF;
    if ( (v10 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v21 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else if ( v21 < 0x16 )
    {
      v21 = 22;
    }
    *(_QWORD *)&v51 = std::allocator<char>::allocate(&v51, v21 + 1);
    v52 = v10;
    v53 = v21;
    memcpy_0((void *)v51, v15, v10 + 1);
  }
  else
  {
    v52 = v10;
    v53 = 15;
    v51 = *(_OWORD *)v15;
  }
  v54 = a6;
  v55 = a5;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v16 = v60;
  v17 = v59;
  if ( v61 > 0xF )
    v17 = (void **)v59[0];
  if ( v60 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("string too long");
  if ( v60 > 0xF )
  {
    if ( (v60 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v11 = v60 | 0xF;
      if ( (v60 | 0xF) < 0x16 )
        v11 = 22;
    }
    *(_QWORD *)&v56 = std::allocator<char>::allocate(&v56, v11 + 1);
    v57 = v16;
    v58 = v11;
    memcpy_0((void *)v56, v17, v16 + 1);
  }
  else
  {
    v57 = v60;
    v58 = 15;
    v56 = *(_OWORD *)v17;
  }
  v18 = v39;
  v19 = *(void (__fastcall **)(const char *, _BYTE *))(*(_QWORD *)v39 + 24LL);
  v63 = 0;
  v63 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_7db761cae605cf8de79a6f19b6fe1761__void___lambda_7db761cae605cf8de79a6f19b6fe1761____(&v47);
  v19(v18, v62);
  if ( v63 )
  {
    v20 = v62;
    LOBYTE(v20) = v63 != v62;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v63 + 32LL))(v63, v20);
  }
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v56);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v51);
  if ( v50 )
    std::_Ref_count_base::_Decref(v50);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(Src);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v9);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v59);
}

```

## disassembly

```asm
0x180029360  mov     [rsp-8+arg_8], rbx
0x180029365  push    rbp
0x180029366  push    rsi
0x180029367  push    rdi
0x180029368  push    r12
0x18002936a  push    r13
0x18002936c  push    r14
0x18002936e  push    r15
0x180029370  lea     rbp, [rsp-80h]
0x180029375  sub     rsp, 180h
0x18002937c  mov     rax, cs:__security_cookie
0x180029383  xor     rax, rsp
0x180029386  mov     [rbp+0B0h+var_40], rax
0x18002938a  mov     r14, r9
0x18002938d  mov     r15, r8
0x180029390  mov     [rsp+1B0h+var_178], edx
0x180029394  mov     [rsp+1B0h+var_170], rcx
0x180029399  mov     r8, [rbp+0B0h+arg_30]
0x1800293a0  xor     esi, esi
0x1800293a2  lea     rdx, [rbp+0B0h+var_A0]
0x1800293a6  call    ?GetOrCreateCorrelationVectorForOperation@ActivityManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(char const *)
0x1800293ab  nop
0x1800293ac  lea     rcx, [rbp+0B0h+var_A0]; void *
0x1800293b0  call    ?Increment@CorrelationVectorData@cdp@@SA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::CorrelationVectorData::Increment(std::string &)
0x1800293b5  test    al, al
0x1800293b7  jz      loc_180029700
0x1800293bd  test    r15, r15
0x1800293c0  jz      loc_18002978E
0x1800293c6  test    r14, r14
0x1800293c9  jz      loc_18002981C
0x1800293cf  mov     rax, [r15]
0x1800293d2  mov     rcx, r15
0x1800293d5  mov     rax, [rax+8]
0x1800293d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293de  mov     al, [rsp+1B0h+var_180]
0x1800293e2  mov     [rsp+1B0h+var_180], al
0x1800293e6  mov     [rsp+1B0h+var_160], r15
0x1800293eb  lea     rax, [rsp+1B0h+var_180]
0x1800293f0  mov     [rsp+1B0h+var_158], rax
0x1800293f5  lea     ebx, [rsi+1]
0x1800293f8  mov     [rsp+1B0h+var_150], bl
0x1800293fc  lea     ecx, [rsi+18h]; Size
0x1800293ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029404  mov     r13, rax
0x180029407  mov     [rsp+1B0h+var_160], rax
0x18002940c  xorps   xmm0, xmm0
0x18002940f  movups  xmmword ptr [rax], xmm0
0x180029412  mov     [rax+8], ebx
0x180029415  mov     [rax+0Ch], ebx
0x180029418  lea     rax, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x18002941f  mov     [r13+0], rax
0x180029423  mov     [r13+10h], r15
0x180029427  mov     [rsp+1B0h+var_160], r15
0x18002942c  mov     [rsp+1B0h+var_158], r13
0x180029431  movups  xmmword ptr [rsp+1B0h+Src], xmm0
0x180029436  mov     [rsp+1B0h+var_138], rsi
0x18002943b  mov     [rbp+0B0h+var_130], rsi
0x18002943f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029443  inc     rbx
0x180029446  cmp     [r14+rbx], sil
0x18002944a  jnz     short loc_180029443
0x18002944c  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180029456  cmp     rbx, rdi
0x180029459  ja      loc_1800298AA
0x18002945f  mov     eax, 16h
0x180029464  cmp     rbx, 0Fh
0x180029468  ja      loc_180029618
0x18002946e  mov     [rsp+1B0h+var_138], rbx
0x180029473  mov     [rbp+0B0h+var_130], 0Fh
0x18002947b  mov     r8, rbx; Size
0x18002947e  mov     rdx, r14; Src
0x180029481  lea     rcx, [rsp+1B0h+Src]; void *
0x180029486  call    memcpy_0
0x18002948b  mov     byte ptr [rsp+rbx+1B0h+Src], sil
0x180029490  mov     rsi, [rbp+0B0h+var_130]
0x180029494  mov     rbx, [rsp+1B0h+var_138]
0x180029499  mov     r12, [rsp+1B0h+Src]
0x18002949e  mov     rcx, [rsp+1B0h+var_170]
0x1800294a3  mov     rax, [rcx+3D8h]
0x1800294aa  mov     [rsp+1B0h+var_170], rax
0x1800294af  mov     [rbp+0B0h+var_110], rcx
0x1800294b3  mov     eax, [rsp+1B0h+var_178]
0x1800294b7  mov     [rbp+0B0h+var_108], eax
0x1800294ba  lock inc dword ptr [r13+8]
0x1800294bf  mov     [rbp+0B0h+var_100], r15
0x1800294c3  mov     [rbp+0B0h+var_F8], r13
0x1800294c7  xorps   xmm0, xmm0
0x1800294ca  movups  [rbp+0B0h+var_F0], xmm0
0x1800294ce  xor     r15d, r15d
0x1800294d1  mov     [rbp+0B0h+var_E0], r15
0x1800294d5  mov     [rbp+0B0h+var_D8], r15
0x1800294d9  lea     r14, [rsp+1B0h+Src]
0x1800294de  lea     ecx, [r15+0Fh]
0x1800294e2  cmp     rsi, rcx
0x1800294e5  cmova   r14, r12
0x1800294e9  cmp     rbx, rdi
0x1800294ec  ja      loc_1800298B8
0x1800294f2  lea     r12d, [r15+16h]
0x1800294f6  cmp     rbx, rcx
0x1800294f9  ja      loc_180029666
0x1800294ff  mov     [rbp+0B0h+var_E0], rbx
0x180029503  mov     [rbp+0B0h+var_D8], rcx
0x180029507  movups  xmm0, xmmword ptr [r14]
0x18002950b  movdqu  [rbp+0B0h+var_F0], xmm0
0x180029510  mov     eax, [rbp+0B0h+arg_28]
0x180029516  mov     [rbp+0B0h+var_D0], eax
0x180029519  movzx   eax, [rbp+0B0h+arg_20]
0x180029520  mov     [rbp+0B0h+var_CC], ax
0x180029524  xorps   xmm0, xmm0
0x180029527  movups  [rbp+0B0h+var_C8], xmm0
0x18002952b  mov     [rbp+0B0h+var_B8], r15
0x18002952f  mov     [rbp+0B0h+var_B0], r15
0x180029533  mov     rbx, [rbp+0B0h+var_90]
0x180029537  lea     rsi, [rbp+0B0h+var_A0]
0x18002953b  cmp     [rbp+0B0h+var_88], rcx
0x18002953f  cmova   rsi, [rbp+0B0h+var_A0]
0x180029544  cmp     rbx, rdi
0x180029547  ja      loc_1800298C6
0x18002954d  cmp     rbx, rcx
0x180029550  ja      loc_1800296AE
0x180029556  mov     [rbp+0B0h+var_B8], rbx
0x18002955a  mov     [rbp+0B0h+var_B0], rcx
0x18002955e  movups  xmm0, xmmword ptr [rsi]
0x180029561  movdqu  [rbp+0B0h+var_C8], xmm0
0x180029566  mov     rdi, [rsp+1B0h+var_170]
0x18002956b  mov     rax, [rdi]
0x18002956e  mov     rbx, [rax+18h]
0x180029572  mov     [rbp+0B0h+var_48], r15
0x180029576  lea     rcx, [rbp+0B0h+var_110]
0x18002957a  call    std___Global_new_std___Func_impl_no_alloc__lambda_7db761cae605cf8de79a6f19b6fe1761__void___lambda_7db761cae605cf8de79a6f19b6fe1761____
0x18002957f  mov     [rbp+0B0h+var_48], rax
0x180029583  lea     rdx, [rbp+0B0h+var_80]
0x180029587  mov     rcx, rdi
0x18002958a  mov     rax, rbx
0x18002958d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029592  nop
0x180029593  mov     rcx, [rbp+0B0h+var_48]
0x180029597  test    rcx, rcx
0x18002959a  jz      short loc_1800295B3
0x18002959c  mov     rax, [rcx]
0x18002959f  lea     rdx, [rbp+0B0h+var_80]
0x1800295a3  cmp     rcx, rdx
0x1800295a6  setnz   dl
0x1800295a9  mov     rax, [rax+20h]
0x1800295ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295b2  nop
0x1800295b3  lea     rcx, [rbp+0B0h+var_C8]; void *
0x1800295b7  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800295bc  lea     rcx, [rbp+0B0h+var_F0]; void *
0x1800295c0  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800295c5  mov     rcx, [rbp+0B0h+var_F8]; this
0x1800295c9  test    rcx, rcx
0x1800295cc  jz      short loc_1800295D4
0x1800295ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800295d3  nop
0x1800295d4  lea     rcx, [rsp+1B0h+Src]; void *
0x1800295d9  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800295de  nop
0x1800295df  mov     rcx, r13; this
0x1800295e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800295e7  nop
0x1800295e8  lea     rcx, [rbp+0B0h+var_A0]; void *
0x1800295ec  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800295f1  mov     rcx, [rbp+0B0h+var_40]
0x1800295f5  xor     rcx, rsp; StackCookie
0x1800295f8  call    __security_check_cookie
0x1800295fd  mov     rbx, [rsp+1B0h+arg_8]
0x180029605  add     rsp, 180h
0x18002960c  pop     r15
0x18002960e  pop     r14
0x180029610  pop     r13
0x180029612  pop     r12
0x180029614  pop     rdi
0x180029615  pop     rsi
0x180029616  pop     rbp
0x180029617  retn
0x180029618  mov     rsi, rbx
0x18002961b  or      rsi, 0Fh
0x18002961f  cmp     rsi, rdi
0x180029622  ja      loc_1800296F0
0x180029628  cmp     rsi, rax
0x18002962b  cmovb   rsi, rax
0x18002962f  lea     rdx, [rsi+1]
0x180029633  lea     rcx, [rsp+1B0h+Src]
0x180029638  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x18002963d  mov     r12, rax
0x180029640  mov     [rsp+1B0h+Src], rax
0x180029645  mov     [rsp+1B0h+var_138], rbx
0x18002964a  mov     [rbp+0B0h+var_130], rsi
0x18002964e  mov     r8, rbx; Size
0x180029651  mov     rdx, r14; Src
0x180029654  mov     rcx, rax; void *
0x180029657  call    memcpy_0
0x18002965c  mov     byte ptr [rbx+r12], 0
0x180029661  jmp     loc_18002949E
0x180029666  mov     rsi, rbx
0x180029669  or      rsi, rcx
0x18002966c  cmp     rsi, rdi
0x18002966f  ja      loc_1800296F8
0x180029675  cmp     rsi, r12
0x180029678  cmovb   rsi, r12
0x18002967c  lea     rdx, [rsi+1]
0x180029680  lea     rcx, [rbp+0B0h+var_F0]
0x180029684  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x180029689  mov     qword ptr [rbp+0B0h+var_F0], rax
0x18002968d  mov     [rbp+0B0h+var_E0], rbx
0x180029691  mov     [rbp+0B0h+var_D8], rsi
0x180029695  lea     r8, [rbx+1]; Size
0x180029699  mov     rdx, r14; Src
0x18002969c  mov     rcx, rax; void *
0x18002969f  call    memcpy_0
0x1800296a4  mov     ecx, 0Fh
0x1800296a9  jmp     loc_180029510
0x1800296ae  mov     rax, rbx
0x1800296b1  or      rax, rcx
0x1800296b4  cmp     rax, rdi
0x1800296b7  ja      short loc_1800296C3
0x1800296b9  mov     rdi, rax
0x1800296bc  cmp     rax, r12
0x1800296bf  cmovb   rdi, r12
0x1800296c3  lea     rdx, [rdi+1]
0x1800296c7  lea     rcx, [rbp+0B0h+var_C8]
0x1800296cb  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x1800296d0  mov     qword ptr [rbp+0B0h+var_C8], rax
0x1800296d4  mov     [rbp+0B0h+var_B8], rbx
0x1800296d8  mov     [rbp+0B0h+var_B0], rdi
0x1800296dc  lea     r8, [rbx+1]; Size
0x1800296e0  mov     rdx, rsi; Src
0x1800296e3  mov     rcx, rax; void *
0x1800296e6  call    memcpy_0
0x1800296eb  jmp     loc_180029566
0x1800296f0  mov     rsi, rdi
0x1800296f3  jmp     loc_18002962F
0x1800296f8  mov     rsi, rdi
0x1800296fb  jmp     loc_18002967C
0x180029700  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x180029707  mov     [rsp+1B0h+var_170], rax
0x18002970c  mov     [rsp+1B0h+var_168], 6B2h
0x180029714  mov     ebx, 80070057h
0x180029719  mov     [rsp+1B0h+var_178], ebx
0x18002971d  call    cs:__imp_GetCurrentThreadId
0x180029723  mov     eax, eax
0x180029725  mov     [rsp+1B0h+var_160], rax
0x18002972a  lea     rax, [rsp+1B0h+var_160]
0x18002972f  mov     [rsp+1B0h+var_188], rax
0x180029734  lea     rax, [rsp+1B0h+var_168]
0x180029739  mov     [rsp+1B0h+var_190], rax
0x18002973e  lea     r9, [rsp+1B0h+var_170]
0x180029743  lea     r8, [rsp+1B0h+var_178]
0x180029748  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18002974f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180029754  lea     rdx, [rsp+1B0h+var_170]
0x180029759  lea     rcx, [rsp+1B0h+var_160]
0x18002975e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180029763  mov     r9, rax
0x180029766  mov     ecx, ebx
0x180029768  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18002976d  mov     r8, rax
0x180029770  mov     edx, ebx
0x180029772  lea     rcx, [rsp+1B0h+Src]
0x180029777  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18002977c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180029783  lea     rcx, [rsp+1B0h+Src]; pExceptionObject
0x180029788  call    _CxxThrowException_0
0x18002978e  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x180029795  mov     [rsp+1B0h+var_170], rax
0x18002979a  mov     [rsp+1B0h+var_168], 6B7h
0x1800297a2  mov     ebx, 80070057h
0x1800297a7  mov     [rsp+1B0h+var_178], ebx
0x1800297ab  call    cs:__imp_GetCurrentThreadId
0x1800297b1  mov     eax, eax
0x1800297b3  mov     [rsp+1B0h+var_160], rax
0x1800297b8  lea     rax, [rsp+1B0h+var_160]
0x1800297bd  mov     [rsp+1B0h+var_188], rax
0x1800297c2  lea     rax, [rsp+1B0h+var_168]
0x1800297c7  mov     [rsp+1B0h+var_190], rax
0x1800297cc  lea     r9, [rsp+1B0h+var_170]
0x1800297d1  lea     r8, [rsp+1B0h+var_178]
0x1800297d6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800297dd  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800297e2  lea     rdx, [rsp+1B0h+var_170]
0x1800297e7  lea     rcx, [rsp+1B0h+var_160]
0x1800297ec  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800297f1  mov     r9, rax
0x1800297f4  mov     ecx, ebx
0x1800297f6  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800297fb  mov     r8, rax
0x1800297fe  mov     edx, ebx
0x180029800  lea     rcx, [rsp+1B0h+Src]
0x180029805  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18002980a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180029811  lea     rcx, [rsp+1B0h+Src]; pExceptionObject
0x180029816  call    _CxxThrowException_0
0x18002981c  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x180029823  mov     [rsp+1B0h+var_170], rax
0x180029828  mov     [rsp+1B0h+var_168], 6B8h
0x180029830  mov     ebx, 80070057h
0x180029835  mov     [rsp+1B0h+var_178], ebx
0x180029839  call    cs:__imp_GetCurrentThreadId
0x18002983f  mov     eax, eax
  ... truncated ...
```
