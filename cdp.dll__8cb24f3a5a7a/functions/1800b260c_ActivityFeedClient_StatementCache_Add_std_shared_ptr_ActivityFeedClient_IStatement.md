# ActivityFeedClient::StatementCache::Add(std::shared_ptr<ActivityFeedClient::IStatement>)

- ea: `0x1800b260c`
- end: `0x1800b2abe`
- name: `?Add@StatementCache@ActivityFeedClient@@QEAAXV?$shared_ptr@VIStatement@ActivityFeedClient@@@std@@@Z`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b25a0`

## callees

- `0x18000d350`
- `0x1800117f8`
- `0x180013da0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800b260c`
- `0x1800b2c70`
- `0x1800b2cb0`
- `0x1800b2d18`
- `0x1800b2df0`
- `0x1800c0cd4`
- `0x180143248`
- `0x180199618`
- `0x1801f6fb0`
- `0x1801fc5e8`
- `0x1801fcb36`
- `0x1801fcb4e`
- `0x1801fcb72`
- `0x1803088bc`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2a3b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b29b6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b29b6`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800b2736`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800b2736`

## string_xrefs

- `0x1800b2a6f`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800b2a20`: `.\statementcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
void __fastcall ActivityFeedClient::StatementCache::Add(_QWORD *a1, const char **a2)
{
  const void *v4; // rax
  const void *v5; // r13
  size_t v6; // rbx
  __int64 v7; // rsi
  const char *v8; // rax
  const char *v9; // rax
  volatile signed __int32 *v10; // rsi
  unsigned __int64 v11; // rcx
  size_t v12; // r12
  void **v13; // rdx
  unsigned __int64 appended; // rax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // r13
  __int64 v18; // r13
  _QWORD *v19; // rdx
  void **v20; // rcx
  void *v21; // r12
  std::_Ref_count_base *v22; // rcx
  const struct std::nothrow_t *v23; // rdx
  void *v24; // rcx
  unsigned int v25; // ebx
  std::_Ref_count_base *v26; // rcx
  __int64 v27; // rdx
  __int64 *v28; // rdx
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  unsigned __int64 v37; // [rsp+50h] [rbp-118h] BYREF
  void *v38; // [rsp+58h] [rbp-110h] BYREF
  int v39; // [rsp+60h] [rbp-108h]
  const char *v40; // [rsp+68h] [rbp-100h]
  _QWORD *v41; // [rsp+70h] [rbp-F8h]
  const char *v42; // [rsp+78h] [rbp-F0h] BYREF
  volatile signed __int32 *v43; // [rsp+80h] [rbp-E8h] BYREF
  clock_t v44; // [rsp+88h] [rbp-E0h]
  _QWORD v45[5]; // [rsp+90h] [rbp-D8h] BYREF
  __int128 v46; // [rsp+B8h] [rbp-B0h]
  __m128i si128; // [rsp+C8h] [rbp-A0h]
  _BYTE pExceptionObject[56]; // [rsp+D8h] [rbp-90h] BYREF
  void *Buf1[2]; // [rsp+110h] [rbp-58h] BYREF
  size_t Size[2]; // [rsp+120h] [rbp-48h]

  v41 = a1;
  v45[3] = a2;
  v39 = 0;
  v46 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v46) = 0;
  v4 = (const void *)(*(__int64 (__fastcall **)(const char *))(*(_QWORD *)*a2 + 64LL))(*a2);
  v5 = v4;
  *(_OWORD *)Buf1 = 0;
  *(_OWORD *)Size = 0;
  v6 = -1;
  do
    ++v6;
  while ( *((_BYTE *)v4 + v6) );
  v7 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v6 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("string too long");
  if ( v6 > 0xF )
  {
    if ( (v6 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v7 = v6 | 0xF;
      if ( (v6 | 0xF) < 0x16 )
        v7 = 22;
    }
    v21 = (void *)std::allocator<char>::allocate(Buf1, v7 + 1);
    Buf1[0] = v21;
    Size[0] = v6;
    Size[1] = v7;
    memcpy_0(v21, v5, v6);
    *((_BYTE *)v21 + v6) = 0;
  }
  else
  {
    Size[0] = v6;
    Size[1] = 15;
    memcpy_0(Buf1, v4, v6);
    *((_BYTE *)Buf1 + v6) = 0;
  }
  (*(void (__fastcall **)(const char *))(*(_QWORD *)*a2 + 32LL))(*a2);
  v8 = a2[1];
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  v9 = *a2;
  v40 = *a2;
  v10 = (volatile signed __int32 *)a2[1];
  if ( v10 )
    _InterlockedIncrement(v10 + 2);
  v42 = v9;
  v43 = v10;
  v44 = clock();
  if ( v10 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v10);
  v12 = Size[0];
  v13 = Buf1;
  if ( Size[1] > 0xF )
    v13 = (void **)Buf1[0];
  appended = std::_Fnv1a_append_bytes(v11, (const unsigned __int8 *const)v13, Size[0]);
  v37 = appended;
  v15 = a1[3];
  v16 = *(_QWORD *)(v15 + 16 * (appended & a1[6]) + 8);
  v17 = a1[1];
  if ( v16 == v17 )
  {
LABEL_46:
    std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Check_max_size(a1);
    v45[0] = a1 + 1;
    v16 = std::_Allocate<16,std::_Default_allocate_traits>(72);
    v45[1] = v16;
    v38 = Buf1;
    ____0AEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std____Z__V___pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__VStatementCacheEntry_ActivityFeedClient___std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___1_V__tuple___V_1__Z(
      v16 + 16,
      v27,
      &v38);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Rehash_for_1(a1);
      v17 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Find_last<std::string>(
                         a1,
                         v45,
                         v16 + 16,
                         v37);
    }
    v28 = *(__int64 **)(v17 + 8);
    ++a1[2];
    *(_QWORD *)v16 = v17;
    *(_QWORD *)(v16 + 8) = v28;
    *v28 = v16;
    *(_QWORD *)(v17 + 8) = v16;
    v29 = 2 * (v37 & a1[6]);
    v30 = a1[3];
    v31 = *(_QWORD *)(v30 + 16 * (v37 & a1[6]));
    if ( v31 == a1[1] )
    {
      *(_QWORD *)(v30 + 16 * (v37 & a1[6])) = v16;
    }
    else
    {
      if ( v31 == v17 )
      {
        *(_QWORD *)(v30 + 16 * (v37 & a1[6])) = v16;
        goto LABEL_31;
      }
      if ( *(__int64 **)(v30 + 16 * (v37 & a1[6]) + 8) != v28 )
        goto LABEL_31;
    }
    *(_QWORD *)(v30 + 8 * v29 + 8) = v16;
    goto LABEL_31;
  }
  v18 = *(_QWORD *)(v15 + 16 * (appended & a1[6]));
  while ( 1 )
  {
    v19 = (_QWORD *)(v16 + 16);
    if ( *(_QWORD *)(v16 + 40) > 0xFu )
      v19 = (_QWORD *)*v19;
    v20 = Buf1;
    if ( Size[1] > 0xF )
      v20 = (void **)Buf1[0];
    if ( v12 == *(_QWORD *)(v16 + 32) && (!v12 || !memcmp_0(v20, v19, v12)) )
      break;
    if ( v16 == v18 )
    {
      v17 = v16;
      goto LABEL_46;
    }
    v16 = *(_QWORD *)(v16 + 8);
  }
LABEL_31:
  if ( v10 )
    _InterlockedIncrement(v10 + 2);
  *(_QWORD *)(v16 + 48) = v40;
  v22 = *(std::_Ref_count_base **)(v16 + 56);
  *(_QWORD *)(v16 + 56) = v10;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  *(_DWORD *)(v16 + 64) = v44;
  if ( v10 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v10);
  if ( Size[1] > 0xF )
  {
    v23 = (const struct std::nothrow_t *)(Size[1] + 1);
    v37 = Size[1] + 1;
    v24 = Buf1[0];
    v38 = Buf1[0];
    if ( Size[1] + 1 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v38, &v37);
      v23 = (const struct std::nothrow_t *)v37;
      v24 = v38;
    }
    operator delete(v24, v23);
  }
  v25 = v39;
  if ( v39 < 0 )
  {
    v42 = ".\\statementcache.cpp";
    LODWORD(v43) = 46;
    LODWORD(v37) = v39;
    v45[0] = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v32,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v37,
      (unsigned int)&v42,
      (__int64)&v43,
      (__int64)v45);
    v33 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v42);
    v36 = cdp::ErrorCodeToString(v25, v34, v35, v33);
    ConnectedDevices::Exception::Exception(pExceptionObject, v25, v36);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v26 = (std::_Ref_count_base *)a2[1];
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
}

```

## disassembly

```asm
0x1800b260c  mov     [rsp+arg_10], rbx
0x1800b2611  mov     [rsp+arg_18], rsi
0x1800b2616  push    rdi
0x1800b2617  push    r12
0x1800b2619  push    r13
0x1800b261b  push    r14
0x1800b261d  push    r15
0x1800b261f  sub     rsp, 140h
0x1800b2626  mov     rax, cs:__security_cookie
0x1800b262d  xor     rax, rsp
0x1800b2630  mov     [rsp+168h+var_38], rax
0x1800b2638  mov     r14, rdx
0x1800b263b  mov     r15, rcx
0x1800b263e  mov     [rsp+168h+var_F8], rcx
0x1800b2643  mov     [rsp+168h+var_C0], rdx
0x1800b264b  xor     edi, edi
0x1800b264d  mov     [rsp+168h+var_108], edi
0x1800b2651  xorps   xmm0, xmm0
0x1800b2654  movups  [rsp+168h+var_B0], xmm0
0x1800b265c  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800b2664  movdqu  [rsp+168h+var_A0], xmm1
0x1800b266d  mov     byte ptr [rsp+168h+var_B0], dil
0x1800b2675  mov     rcx, [rdx]
0x1800b2678  mov     rax, [rcx]
0x1800b267b  mov     rax, [rax+40h]
0x1800b267f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2684  mov     r13, rax
0x1800b2687  xorps   xmm0, xmm0
0x1800b268a  movups  xmmword ptr [rsp+168h+Buf1], xmm0
0x1800b2692  xorps   xmm1, xmm1
0x1800b2695  movdqu  xmmword ptr [rsp+168h+Size], xmm1
0x1800b269e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b26a2  inc     rbx
0x1800b26a5  cmp     [rbx+rax], dil
0x1800b26a9  jnz     short loc_1800B26A2
0x1800b26ab  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1800b26b5  cmp     rbx, rsi
0x1800b26b8  ja      loc_1800B29AF
0x1800b26be  cmp     rbx, 0Fh
0x1800b26c2  ja      loc_1800B27F3
0x1800b26c8  mov     [rsp+168h+Size], rbx
0x1800b26d0  mov     [rsp+168h+Size+8], 0Fh
0x1800b26dc  mov     r8, rbx; Size
0x1800b26df  mov     rdx, r13; Src
0x1800b26e2  lea     rcx, [rsp+168h+Buf1]; void *
0x1800b26ea  call    memcpy_0
0x1800b26ef  mov     byte ptr [rsp+rbx+168h+Buf1], dil
0x1800b26f7  mov     rcx, [r14]
0x1800b26fa  mov     rax, [rcx]
0x1800b26fd  mov     rax, [rax+20h]
0x1800b2701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2706  nop
0x1800b2707  mov     rax, [r14+8]
0x1800b270b  test    rax, rax
0x1800b270e  jz      short loc_1800B2714
0x1800b2710  lock inc dword ptr [rax+8]
0x1800b2714  mov     rax, [r14]
0x1800b2717  mov     [rsp+168h+var_100], rax
0x1800b271c  mov     rsi, [r14+8]
0x1800b2720  test    rsi, rsi
0x1800b2723  jz      short loc_1800B2729
0x1800b2725  lock inc dword ptr [rsi+8]
0x1800b2729  mov     [rsp+168h+var_F0], rax
0x1800b272e  mov     [rsp+168h+var_E8], rsi
0x1800b2736  call    cs:__imp_clock
0x1800b273c  mov     [rsp+168h+var_E0], eax
0x1800b2743  test    rsi, rsi
0x1800b2746  jz      short loc_1800B2750
0x1800b2748  mov     rcx, rsi; this
0x1800b274b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b2750  mov     r12, [rsp+168h+Size]
0x1800b2758  lea     rdx, [rsp+168h+Buf1]
0x1800b2760  cmp     [rsp+168h+Size+8], 0Fh
0x1800b2769  cmova   rdx, [rsp+168h+Buf1]; unsigned __int8 *
0x1800b2772  mov     r8, r12; unsigned __int64
0x1800b2775  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x1800b277a  mov     [rsp+168h+var_118], rax
0x1800b277f  mov     rcx, [r15+30h]
0x1800b2783  and     rcx, rax
0x1800b2786  add     rcx, rcx
0x1800b2789  mov     rdx, [r15+18h]
0x1800b278d  mov     rbx, [rdx+rcx*8+8]
0x1800b2792  mov     r13, [r15+8]
0x1800b2796  cmp     rbx, r13
0x1800b2799  jz      loc_1800B2918
0x1800b279f  mov     r13, [rdx+rcx*8]
0x1800b27a3  lea     rdx, [rbx+10h]
0x1800b27a7  cmp     qword ptr [rbx+28h], 0Fh
0x1800b27ac  jbe     short loc_1800B27B1
0x1800b27ae  mov     rdx, [rdx]; Buf2
0x1800b27b1  lea     rcx, [rsp+168h+Buf1]
0x1800b27b9  cmp     [rsp+168h+Size+8], 0Fh
0x1800b27c2  cmova   rcx, [rsp+168h+Buf1]; Buf1
0x1800b27cb  cmp     r12, [rbx+20h]
0x1800b27cf  jz      short loc_1800B27E0
0x1800b27d1  cmp     rbx, r13
0x1800b27d4  jz      loc_1800B2915
0x1800b27da  mov     rbx, [rbx+8]
0x1800b27de  jmp     short loc_1800B27A3
0x1800b27e0  test    r12, r12
0x1800b27e3  jz      short loc_1800B285C
0x1800b27e5  mov     r8, r12; Size
0x1800b27e8  call    memcmp_0
0x1800b27ed  test    eax, eax
0x1800b27ef  jz      short loc_1800B285C
0x1800b27f1  jmp     short loc_1800B27D1
0x1800b27f3  mov     rax, rbx
0x1800b27f6  or      rax, 0Fh
0x1800b27fa  cmp     rax, rsi
0x1800b27fd  ja      short loc_1800B280E
0x1800b27ff  mov     rsi, rax
0x1800b2802  mov     ecx, 16h
0x1800b2807  cmp     rax, rcx
0x1800b280a  cmovb   rsi, rcx
0x1800b280e  lea     rdx, [rsi+1]
0x1800b2812  lea     rcx, [rsp+168h+Buf1]
0x1800b281a  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x1800b281f  mov     r12, rax
0x1800b2822  mov     [rsp+168h+Buf1], rax
0x1800b282a  mov     [rsp+168h+Size], rbx
0x1800b2832  mov     [rsp+168h+Size+8], rsi
0x1800b283a  mov     r8, rbx; Size
0x1800b283d  mov     rdx, r13; Src
0x1800b2840  mov     rcx, rax; void *
0x1800b2843  call    memcpy_0
0x1800b2848  mov     [rbx+r12], dil
0x1800b284c  jmp     loc_1800B26F7
0x1800b2851  cmp     [rcx+rax*8+8], rdx
0x1800b2856  jz      loc_1800B29A5
0x1800b285c  test    rsi, rsi
0x1800b285f  jz      short loc_1800B2865
0x1800b2861  lock inc dword ptr [rsi+8]
0x1800b2865  mov     rax, [rsp+168h+var_100]
0x1800b286a  mov     [rbx+30h], rax
0x1800b286e  mov     rcx, [rbx+38h]; this
0x1800b2872  mov     [rbx+38h], rsi
0x1800b2876  test    rcx, rcx
0x1800b2879  jz      short loc_1800B2880
0x1800b287b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b2880  mov     eax, [rsp+168h+var_E0]
0x1800b2887  mov     [rbx+40h], eax
0x1800b288a  test    rsi, rsi
0x1800b288d  jz      short loc_1800B2898
0x1800b288f  mov     rcx, rsi; this
0x1800b2892  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b2897  nop
0x1800b2898  mov     rdx, [rsp+168h+Size+8]
0x1800b28a0  cmp     rdx, 0Fh
0x1800b28a4  jbe     short loc_1800B28CE
0x1800b28a6  inc     rdx; struct std::nothrow_t *
0x1800b28a9  mov     [rsp+168h+var_118], rdx
0x1800b28ae  mov     rcx, [rsp+168h+Buf1]; void *
0x1800b28b6  mov     [rsp+168h+var_110], rcx
0x1800b28bb  cmp     rdx, 1000h
0x1800b28c2  jnb     loc_1800B29F5
0x1800b28c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b28cd  nop
0x1800b28ce  mov     ebx, [rsp+168h+var_108]
0x1800b28d2  test    ebx, ebx
0x1800b28d4  js      loc_1800B2A20
0x1800b28da  mov     rcx, [r14+8]; this
0x1800b28de  test    rcx, rcx
0x1800b28e1  jz      short loc_1800B28E8
0x1800b28e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b28e8  mov     rcx, [rsp+168h+var_38]
0x1800b28f0  xor     rcx, rsp; StackCookie
0x1800b28f3  call    __security_check_cookie
0x1800b28f8  lea     r11, [rsp+168h+var_28]
0x1800b2900  mov     rbx, [r11+40h]
0x1800b2904  mov     rsi, [r11+48h]
0x1800b2908  mov     rsp, r11
0x1800b290b  pop     r15
0x1800b290d  pop     r14
0x1800b290f  pop     r13
0x1800b2911  pop     r12
0x1800b2913  pop     rdi
0x1800b2914  retn
0x1800b2915  mov     r13, rbx
0x1800b2918  mov     rcx, r15
0x1800b291b  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@@std@@@2@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Check_max_size(void)
0x1800b2920  lea     r12, [r15+8]
0x1800b2924  mov     [rsp+168h+var_D8], r12
0x1800b292c  mov     [rsp+168h+var_D0], rdi
0x1800b2934  mov     ecx, 48h ; 'H'
0x1800b2939  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800b293e  mov     rbx, rax
0x1800b2941  mov     [rsp+168h+var_D0], rax
0x1800b2949  lea     rax, [rsp+168h+Buf1]
0x1800b2951  mov     [rsp+168h+var_110], rax
0x1800b2956  lea     rcx, [rbx+10h]
0x1800b295a  lea     r8, [rsp+168h+var_110]
0x1800b295f  call    ??$?0AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$Z$$V@?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@@std@@QEAA@Upiecewise_construct_t@1@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@V?$tuple@$$V@1@@Z
0x1800b2964  nop
0x1800b2965  mov     rcx, r15
0x1800b2968  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@@std@@@2@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Check_rehash_required_1(void)
0x1800b296d  test    al, al
0x1800b296f  jnz     short loc_1800B29BD
0x1800b2971  mov     rdx, [r13+8]
0x1800b2975  inc     qword ptr [r15+10h]
0x1800b2979  mov     [rbx], r13
0x1800b297c  mov     [rbx+8], rdx
0x1800b2980  mov     [rdx], rbx
0x1800b2983  mov     [r13+8], rbx
0x1800b2987  mov     rax, [r15+30h]
0x1800b298b  and     rax, [rsp+168h+var_118]
0x1800b2990  add     rax, rax
0x1800b2993  mov     rcx, [r15+18h]
0x1800b2997  mov     r8, [rcx+rax*8]
0x1800b299b  cmp     r8, [r12]
0x1800b299f  jnz     short loc_1800B29E3
0x1800b29a1  mov     [rcx+rax*8], rbx
0x1800b29a5  mov     [rcx+rax*8+8], rbx
0x1800b29aa  jmp     loc_1800B285C
0x1800b29af  lea     rcx, aStringTooLong; "string too long"
0x1800b29b6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b29bd  mov     rcx, r15
0x1800b29c0  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Rehash_for_1(void)
0x1800b29c5  lea     r8, [rbx+10h]
0x1800b29c9  mov     r9, [rsp+168h+var_118]
0x1800b29ce  lea     rdx, [rsp+168h+var_D8]
0x1800b29d6  mov     rcx, r15
0x1800b29d9  call    ??$_Find_last@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VStatementCacheEntry@ActivityFeedClient@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::string,ActivityFeedClient::StatementCacheEntry,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ActivityFeedClient::StatementCacheEntry>>,0>>::_Find_last<std::string>(std::string const &,unsigned __int64)
0x1800b29de  mov     r13, [rax]
0x1800b29e1  jmp     short loc_1800B2971
0x1800b29e3  cmp     r8, r13
0x1800b29e6  jnz     loc_1800B2851
0x1800b29ec  mov     [rcx+rax*8], rbx
0x1800b29f0  jmp     loc_1800B285C
0x1800b29f5  lea     rdx, [rsp+168h+var_118]; unsigned __int64 *
0x1800b29fa  lea     rcx, [rsp+168h+var_110]; void **
0x1800b29ff  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800b2a04  mov     rdx, [rsp+168h+var_118]
0x1800b2a09  mov     rcx, [rsp+168h+var_110]
0x1800b2a0e  jmp     loc_1800B28C8
0x1800b2a13  mov     r14, [rsp+168h+var_C0]
0x1800b2a1b  jmp     loc_1800B28CE
0x1800b2a20  lea     rax, aStatementcache; ".\\statementcache.cpp"
0x1800b2a27  mov     [rsp+168h+var_F0], rax
0x1800b2a2c  mov     dword ptr [rsp+168h+var_E8], 2Eh ; '.'
0x1800b2a37  mov     dword ptr [rsp+168h+var_118], ebx
0x1800b2a3b  call    cs:__imp_GetCurrentThreadId
0x1800b2a41  mov     eax, eax
0x1800b2a43  mov     [rsp+168h+var_D8], rax
0x1800b2a4b  lea     rax, [rsp+168h+var_D8]
0x1800b2a53  mov     [rsp+168h+var_140], rax
0x1800b2a58  lea     rax, [rsp+168h+var_E8]
0x1800b2a60  mov     [rsp+168h+var_148], rax
0x1800b2a65  lea     r9, [rsp+168h+var_F0]
0x1800b2a6a  lea     r8, [rsp+168h+var_118]
0x1800b2a6f  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800b2a76  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800b2a7b  lea     rdx, [rsp+168h+var_F0]
0x1800b2a80  lea     rcx, [rsp+168h+var_D8]
0x1800b2a88  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800b2a8d  mov     r9, rax
0x1800b2a90  mov     ecx, ebx
0x1800b2a92  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800b2a97  mov     r8, rax
0x1800b2a9a  mov     edx, ebx
0x1800b2a9c  lea     rcx, [rsp+168h+pExceptionObject]
0x1800b2aa4  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800b2aa9  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800b2ab0  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x1800b2ab8  call    _CxxThrowException_0
```
