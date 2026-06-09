# CWinHttpSessionManager::WinHttpOpenInternal(wchar_t const *,ulong,wchar_t const *,wchar_t const *,ulong,bool,std::shared_ptr<std::tuple<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,ulong>> &)

- ea: `0x1800f2c54`
- end: `0x1800f3046`
- name: `?WinHttpOpenInternal@CWinHttpSessionManager@@AEAAPEAXPEB_WK00K_NAEAV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@std@@@Z`
- size: `1010`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: ``

## callers

- `0x1800f1de4`
- `0x1800f1f90`
- `0x1800f2084`

## callees

- `0x18000adf0`
- `0x18000b6e0`
- `0x18000c2dc`
- `0x18000ffb0`
- `0x180028df8`
- `0x1800303d0`
- `0x18003e690`
- `0x18009afa0`
- `0x1800d037c`
- `0x1800d1094`
- `0x1800d10b8`
- `0x1800d113c`
- `0x1800d1154`
- `0x1800f24ac`
- `0x1800f2690`
- `0x1800f2818`
- `0x1800f28c8`
- `0x1800f2a08`
- `0x1800f2a28`
- `0x1800f2c54`
- `0x1800f32f0`

## import_xrefs

- `WINHTTP!WinHttpCloseHandle` at `0x1800f2f8b`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f2f8b`
- `WINHTTP!WinHttpOpen` at `0x1800f2f30`
- `WINHTTP!WinHttpOpen` at `0x1800f2f30`

## pseudocode

```c
void *__fastcall CWinHttpSessionManager::WinHttpOpenInternal(
        __int64 a1,
        const WCHAR *a2,
        DWORD a3,
        const WCHAR *a4,
        const WCHAR *pszProxyBypassW,
        DWORD a6,
        unsigned __int8 a7,
        _QWORD *a8)
{
  void *v10; // rdi
  unsigned int Dw; // eax
  int v12; // edx
  __int64 v13; // rsi
  __int64 v14; // rcx
  CWinHttpSessionManager *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool v20; // dl
  CWinHttpSessionManager *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  CWinHttpSessionManager *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  _DWORD v30[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v31[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v32; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v33[2]; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwFlags; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  DWORD dwAccessType[4]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v39[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v40[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v41[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[32]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v43[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v44[2]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v45; // [rsp+128h] [rbp+28h] BYREF
  __m128i si128; // [rsp+138h] [rbp+38h]
  _BYTE v47[128]; // [rsp+150h] [rbp+50h] BYREF

  dwAccessType[0] = a3;
  v32 = a3;
  dwFlags = a6;
  v31[0] = a6;
  v10 = 0;
  v45 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v45) = 0;
  v44[0] = 0;
  v44[1] = si128;
  LOWORD(v44[0]) = 0;
  v43[0] = 0;
  v43[1] = si128;
  LOWORD(v43[0]) = 0;
  v30[0] = 0;
  Dw = MsoDwRegGetDw((const struct _msoreg *)&vmsoridDisableConnectionReuse);
  v12 = 0;
  if ( !Dw )
    v12 = a7;
  v34 = v12;
  if ( !(_BYTE)v12 )
    v30[0] = CWinHttpSessionManager::GetNextCounter((CWinHttpSessionManager *)a7);
  if ( a2 )
  {
    std::wstring::wstring(v42, a2);
    std::wstring::operator=(&v45);
    std::wstring::~wstring(v42);
  }
  if ( a4 )
  {
    std::wstring::wstring(v42, a4);
    std::wstring::operator=(v44);
    std::wstring::~wstring(v42);
  }
  if ( pszProxyBypassW )
  {
    std::wstring::wstring(v42, pszProxyBypassW);
    std::wstring::operator=(v43);
    std::wstring::~wstring(v42);
  }
  std::make_shared<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::wstring &,unsigned long &,std::wstring &,std::wstring &,unsigned long &,unsigned long &>(
    (unsigned int)&v36,
    (unsigned int)&v45,
    (unsigned int)&v32,
    (unsigned int)v44,
    (__int64)v43,
    (__int64)v31,
    (__int64)v30);
  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v39, &qword_18021AD10);
  v13 = v36;
  v16 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>>,std::allocator<std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(
                     v14,
                     v40,
                     v36);
  if ( !(_BYTE)v34 )
  {
    while ( v16 != qword_18021AD00 )
    {
      v30[0] = CWinHttpSessionManager::GetNextCounter(v15);
      v17 = std::make_shared<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::wstring &,unsigned long &,std::wstring &,std::wstring &,unsigned long &,unsigned long &>(
              (unsigned int)v33,
              (unsigned int)&v45,
              (unsigned int)&v32,
              (unsigned int)v44,
              (__int64)v43,
              (__int64)v31,
              (__int64)v30);
      std::shared_ptr<Mso::Http::ConnectionDataUsage>::operator=(&v36, v17);
      std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v33);
      v13 = v36;
      v16 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>>,std::allocator<std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(
                         v18,
                         v41,
                         v36);
    }
  }
  std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v39);
  if ( v16 == qword_18021AD00 )
  {
    std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(v42, &qword_18021AD10);
    v16 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>>,std::allocator<std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(
                       v19,
                       v39,
                       v13);
    if ( (_BYTE)v34 )
    {
      if ( v16 != qword_18021AD00 )
        goto LABEL_25;
    }
    else
    {
      while ( v16 != qword_18021AD00 )
      {
        v30[0] = CWinHttpSessionManager::GetNextCounter(v21);
        v22 = std::make_shared<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::wstring &,unsigned long &,std::wstring &,std::wstring &,unsigned long &,unsigned long &>(
                (unsigned int)v33,
                (unsigned int)&v45,
                (unsigned int)&v32,
                (unsigned int)v44,
                (__int64)v43,
                (__int64)v31,
                (__int64)v30);
        std::shared_ptr<Mso::Http::ConnectionDataUsage>::operator=(&v36, v22);
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v33);
        v13 = v36;
        v16 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>>,std::allocator<std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(
                           v23,
                           &v34,
                           v36);
      }
    }
    Mso::Http::Util::CheckIfAPIIsCalledOnMainThread(v21, v20);
    v10 = WinHttpOpen(a2, dwAccessType[0], a4, pszProxyBypassW, dwFlags);
    *(_QWORD *)dwAccessType = v10;
    std::make_shared<CWinHttpSessionInfo,void * &>(v33, dwAccessType);
    if ( v10 )
    {
      if ( v33[0] )
      {
        CWinHttpSessionManager::SetIPV6Fallback(v24, v10);
        v25 = std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>>::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>>(
                v47,
                v13,
                v33);
        std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>>,std::allocator<std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::_Emplace<std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long>,std::shared_ptr<CWinHttpSessionInfo>>>(
          v26,
          dwAccessType,
          v25);
        std::pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>::~pair<std::tuple<std::wstring,unsigned long,std::wstring,std::wstring,unsigned long,unsigned long> const,std::shared_ptr<CWinHttpSessionInfo>>(v47);
LABEL_24:
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v33);
LABEL_25:
        std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v42);
        if ( v16 == qword_18021AD00 )
          goto LABEL_27;
        goto LABEL_26;
      }
      WinHttpCloseHandle(v10);
    }
    v10 = 0;
    goto LABEL_24;
  }
LABEL_26:
  v27 = *(_QWORD *)(v16 + 144);
  v10 = *(void **)(v27 + 8);
  _InterlockedIncrement((volatile signed __int32 *)(v27 + 16));
LABEL_27:
  if ( v10 )
  {
    v28 = v37;
    if ( v37 )
      _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
    v33[0] = *a8;
    *a8 = v13;
    v33[1] = a8[1];
    a8[1] = v28;
    std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v33);
  }
  std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(&v36);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(&v45);
  return v10;
}

```

## disassembly

```asm
0x1800f2c54  mov     [rsp-8+arg_0], rbx
0x1800f2c59  push    rbp
0x1800f2c5a  push    rsi
0x1800f2c5b  push    rdi
0x1800f2c5c  push    r12
0x1800f2c5e  push    r13
0x1800f2c60  push    r14
0x1800f2c62  push    r15
0x1800f2c64  lea     rbp, [rsp-0E0h]
0x1800f2c6c  sub     rsp, 1E0h
0x1800f2c73  mov     rax, cs:__security_cookie
0x1800f2c7a  xor     rax, rsp
0x1800f2c7d  mov     [rbp+110h+var_40], rax
0x1800f2c84  mov     r12, r9
0x1800f2c87  mov     eax, r8d
0x1800f2c8a  mov     [rbp+110h+dwAccessType], eax
0x1800f2c8d  mov     r15, rdx
0x1800f2c90  mov     [rsp+210h+var_1B0], eax
0x1800f2c94  mov     r13, [rbp+110h+pszProxyBypassW]
0x1800f2c9b  mov     eax, [rbp+110h+arg_28]
0x1800f2ca1  mov     [rbp+110h+var_190], eax
0x1800f2ca4  mov     [rsp+210h+var_1C0], eax
0x1800f2ca8  mov     r14, [rbp+110h+arg_38]
0x1800f2caf  xor     ebx, ebx
0x1800f2cb1  mov     edi, ebx
0x1800f2cb3  xorps   xmm0, xmm0
0x1800f2cb6  movups  [rbp+110h+var_E8], xmm0
0x1800f2cba  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800f2cc2  movdqu  [rbp+110h+var_D8], xmm1
0x1800f2cc7  mov     word ptr [rbp+110h+var_E8], bx
0x1800f2ccb  movups  [rbp+110h+var_108], xmm0
0x1800f2ccf  movdqu  [rbp+110h+var_F8], xmm1
0x1800f2cd4  mov     word ptr [rbp+110h+var_108], bx
0x1800f2cd8  movups  [rbp+110h+var_128], xmm0
0x1800f2cdc  movdqu  [rbp+110h+var_118], xmm1
0x1800f2ce1  mov     word ptr [rbp+110h+var_128], bx
0x1800f2ce5  mov     [rsp+210h+var_1D0], ebx
0x1800f2ce9  lea     rcx, ?vmsoridDisableConnectionReuse@@3U_msoreg@@B; struct _msoreg *
0x1800f2cf0  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1800f2cf5  mov     edx, ebx
0x1800f2cf7  movzx   ecx, [rbp+110h+arg_30]; this
0x1800f2cfe  test    eax, eax
0x1800f2d00  cmovz   edx, ecx
0x1800f2d03  mov     [rsp+210h+var_198], edx
0x1800f2d07  test    dl, dl
0x1800f2d09  jnz     short loc_1800F2D14
0x1800f2d0b  call    ?GetNextCounter@CWinHttpSessionManager@@AEAAKXZ; CWinHttpSessionManager::GetNextCounter(void)
0x1800f2d10  mov     [rsp+210h+var_1D0], eax
0x1800f2d14  test    r15, r15
0x1800f2d17  jz      short loc_1800F2D3A
0x1800f2d19  mov     rdx, r15
0x1800f2d1c  lea     rcx, [rbp+110h+var_148]
0x1800f2d20  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800f2d25  mov     rdx, rax
0x1800f2d28  lea     rcx, [rbp+110h+var_E8]
0x1800f2d2c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f2d31  lea     rcx, [rbp+110h+var_148]; void *
0x1800f2d35  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f2d3a  test    r12, r12
0x1800f2d3d  jz      short loc_1800F2D60
0x1800f2d3f  mov     rdx, r12
0x1800f2d42  lea     rcx, [rbp+110h+var_148]
0x1800f2d46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800f2d4b  mov     rdx, rax
0x1800f2d4e  lea     rcx, [rbp+110h+var_108]
0x1800f2d52  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f2d57  lea     rcx, [rbp+110h+var_148]; void *
0x1800f2d5b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f2d60  test    r13, r13
0x1800f2d63  jz      short loc_1800F2D86
0x1800f2d65  mov     rdx, r13
0x1800f2d68  lea     rcx, [rbp+110h+var_148]
0x1800f2d6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800f2d71  mov     rdx, rax
0x1800f2d74  lea     rcx, [rbp+110h+var_128]
0x1800f2d78  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f2d7d  lea     rcx, [rbp+110h+var_148]; void *
0x1800f2d81  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f2d86  lea     rax, [rsp+210h+var_1D0]
0x1800f2d8b  mov     [rsp+210h+var_1E0], rax
0x1800f2d90  lea     rax, [rsp+210h+var_1C0]
0x1800f2d95  mov     [rsp+210h+var_1E8], rax
0x1800f2d9a  lea     rax, [rbp+110h+var_128]
0x1800f2d9e  mov     qword ptr [rsp+210h+dwFlags], rax
0x1800f2da3  lea     r9, [rbp+110h+var_108]
0x1800f2da7  lea     r8, [rsp+210h+var_1B0]
0x1800f2dac  lea     rdx, [rbp+110h+var_E8]
0x1800f2db0  lea     rcx, [rbp+110h+var_188]
0x1800f2db4  call    ??$make_shared@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAKAEAV32@AEAV32@AEAKAEAK@std@@YA?AV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAK0011@Z; std::make_shared<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::wstring &,ulong &,std::wstring &,std::wstring &,ulong &,ulong &>(std::wstring &,ulong &,std::wstring &,std::wstring &,ulong &,ulong &)
0x1800f2db9  lea     rdx, qword_18021AD10
0x1800f2dc0  lea     rcx, [rbp+110h+var_168]
0x1800f2dc4  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800f2dc9  mov     rsi, [rbp+110h+var_188]
0x1800f2dcd  mov     r8, rsi
0x1800f2dd0  lea     rdx, [rbp+110h+var_158]
0x1800f2dd4  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@U?$less@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>>,std::allocator<std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const &)
0x1800f2dd9  mov     rbx, [rax]
0x1800f2ddc  cmp     byte ptr [rsp+210h+var_198], dil
0x1800f2de1  jnz     short loc_1800F2E54
0x1800f2de3  cmp     rbx, cs:qword_18021AD00
0x1800f2dea  jz      short loc_1800F2E54
0x1800f2dec  call    ?GetNextCounter@CWinHttpSessionManager@@AEAAKXZ; CWinHttpSessionManager::GetNextCounter(void)
0x1800f2df1  mov     [rsp+210h+var_1D0], eax
0x1800f2df5  lea     rax, [rsp+210h+var_1D0]
0x1800f2dfa  mov     [rsp+210h+var_1E0], rax
0x1800f2dff  lea     rax, [rsp+210h+var_1C0]
0x1800f2e04  mov     [rsp+210h+var_1E8], rax
0x1800f2e09  lea     rax, [rbp+110h+var_128]
0x1800f2e0d  mov     qword ptr [rsp+210h+dwFlags], rax
0x1800f2e12  lea     r9, [rbp+110h+var_108]
0x1800f2e16  lea     r8, [rsp+210h+var_1B0]
0x1800f2e1b  lea     rdx, [rbp+110h+var_E8]
0x1800f2e1f  lea     rcx, [rsp+210h+var_1A8]
0x1800f2e24  call    ??$make_shared@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAKAEAV32@AEAV32@AEAKAEAK@std@@YA?AV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAK0011@Z; std::make_shared<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::wstring &,ulong &,std::wstring &,std::wstring &,ulong &,ulong &>(std::wstring &,ulong &,std::wstring &,std::wstring &,ulong &,ulong &)
0x1800f2e29  mov     rdx, rax
0x1800f2e2c  lea     rcx, [rbp+110h+var_188]
0x1800f2e30  call    ??4?$shared_ptr@VConnectionDataUsage@Http@Mso@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Mso::Http::ConnectionDataUsage>::operator=(std::shared_ptr<Mso::Http::ConnectionDataUsage> &&)
0x1800f2e35  lea     rcx, [rsp+210h+var_1A8]; void *
0x1800f2e3a  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800f2e3f  mov     rsi, [rbp+110h+var_188]
0x1800f2e43  mov     r8, rsi
0x1800f2e46  lea     rdx, [rbp+110h+var_150]
0x1800f2e4a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@U?$less@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>>,std::allocator<std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const &)
0x1800f2e4f  mov     rbx, [rax]
0x1800f2e52  jmp     short loc_1800F2DE3
0x1800f2e54  lea     rcx, [rbp+110h+var_168]
0x1800f2e58  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800f2e5d  mov     rax, cs:qword_18021AD00
0x1800f2e64  cmp     rbx, rax
0x1800f2e67  jnz     loc_1800F2FB2
0x1800f2e6d  lea     rdx, qword_18021AD10
0x1800f2e74  lea     rcx, [rbp+110h+var_148]
0x1800f2e78  call    ??0?$unique_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(std::shared_mutex &)
0x1800f2e7d  mov     r8, rsi
0x1800f2e80  lea     rdx, [rbp+110h+var_168]
0x1800f2e84  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@U?$less@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>>,std::allocator<std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const &)
0x1800f2e89  mov     rbx, [rax]
0x1800f2e8c  cmp     byte ptr [rsp+210h+var_198], dil
0x1800f2e91  jnz     short loc_1800F2F08
0x1800f2e93  mov     rax, cs:qword_18021AD00
0x1800f2e9a  cmp     rbx, rax
0x1800f2e9d  jz      short loc_1800F2F18
0x1800f2e9f  call    ?GetNextCounter@CWinHttpSessionManager@@AEAAKXZ; CWinHttpSessionManager::GetNextCounter(void)
0x1800f2ea4  mov     [rsp+210h+var_1D0], eax
0x1800f2ea8  lea     rax, [rsp+210h+var_1D0]
0x1800f2ead  mov     [rsp+210h+var_1E0], rax
0x1800f2eb2  lea     rax, [rsp+210h+var_1C0]
0x1800f2eb7  mov     [rsp+210h+var_1E8], rax
0x1800f2ebc  lea     rax, [rbp+110h+var_128]
0x1800f2ec0  mov     qword ptr [rsp+210h+dwFlags], rax
0x1800f2ec5  lea     r9, [rbp+110h+var_108]
0x1800f2ec9  lea     r8, [rsp+210h+var_1B0]
0x1800f2ece  lea     rdx, [rbp+110h+var_E8]
0x1800f2ed2  lea     rcx, [rsp+210h+var_1A8]
0x1800f2ed7  call    ??$make_shared@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAKAEAV32@AEAV32@AEAKAEAK@std@@YA?AV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAK0011@Z; std::make_shared<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::wstring &,ulong &,std::wstring &,std::wstring &,ulong &,ulong &>(std::wstring &,ulong &,std::wstring &,std::wstring &,ulong &,ulong &)
0x1800f2edc  mov     rdx, rax
0x1800f2edf  lea     rcx, [rbp+110h+var_188]
0x1800f2ee3  call    ??4?$shared_ptr@VConnectionDataUsage@Http@Mso@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Mso::Http::ConnectionDataUsage>::operator=(std::shared_ptr<Mso::Http::ConnectionDataUsage> &&)
0x1800f2ee8  lea     rcx, [rsp+210h+var_1A8]; void *
0x1800f2eed  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800f2ef2  mov     rsi, [rbp+110h+var_188]
0x1800f2ef6  mov     r8, rsi
0x1800f2ef9  lea     rdx, [rsp+210h+var_198]
0x1800f2efe  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@U?$less@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>>,std::allocator<std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::find(std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const &)
0x1800f2f03  mov     rbx, [rax]
0x1800f2f06  jmp     short loc_1800F2E93
0x1800f2f08  mov     rax, cs:qword_18021AD00
0x1800f2f0f  cmp     rbx, rax
0x1800f2f12  jnz     loc_1800F2F9D
0x1800f2f18  call    ?CheckIfAPIIsCalledOnMainThread@Util@Http@Mso@@YAX_N@Z; Mso::Http::Util::CheckIfAPIIsCalledOnMainThread(bool)
0x1800f2f1d  mov     ecx, [rbp+110h+var_190]
0x1800f2f20  mov     [rsp+210h+dwFlags], ecx; dwFlags
0x1800f2f24  mov     r9, r13; pszProxyBypassW
0x1800f2f27  mov     r8, r12; pszProxyW
0x1800f2f2a  mov     edx, [rbp+110h+dwAccessType]; dwAccessType
0x1800f2f2d  mov     rcx, r15; pszAgentW
0x1800f2f30  call    cs:__imp_WinHttpOpen
0x1800f2f36  mov     rdi, rax
0x1800f2f39  mov     qword ptr [rbp+110h+dwAccessType], rax
0x1800f2f3d  lea     rdx, [rbp+110h+dwAccessType]
0x1800f2f41  lea     rcx, [rsp+210h+var_1A8]
0x1800f2f46  call    ??$make_shared@VCWinHttpSessionInfo@@AEAPEAX@std@@YA?AV?$shared_ptr@VCWinHttpSessionInfo@@@0@AEAPEAX@Z; std::make_shared<CWinHttpSessionInfo,void * &>(void * &)
0x1800f2f4b  test    rdi, rdi
0x1800f2f4e  jz      short loc_1800F2F91
0x1800f2f50  cmp     [rsp+210h+var_1A8], 0
0x1800f2f56  jz      short loc_1800F2F88
0x1800f2f58  mov     rdx, rdi; void *
0x1800f2f5b  call    ?SetIPV6Fallback@CWinHttpSessionManager@@AEAAXPEAX@Z; CWinHttpSessionManager::SetIPV6Fallback(void *)
0x1800f2f60  lea     r8, [rsp+210h+var_1A8]
0x1800f2f65  mov     rdx, rsi
0x1800f2f68  lea     rcx, [rbp+110h+var_C0]
0x1800f2f6c  call    ??$?0AEAV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@AEAV?$shared_ptr@VCWinHttpSessionInfo@@@1@$0A@@?$pair@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@QEAA@AEAV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@1@AEAV?$shared_ptr@VCWinHttpSessionInfo@@@1@@Z; std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>>::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>>(std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> &,std::shared_ptr<CWinHttpSessionInfo> &)
0x1800f2f71  mov     r8, rax
0x1800f2f74  lea     rdx, [rbp+110h+dwAccessType]
0x1800f2f78  call    ??$_Emplace@U?$pair@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@U?$less@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>,std::less<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>>,std::allocator<std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>>,0>>::_Emplace<std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>>>(std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong>,std::shared_ptr<CWinHttpSessionInfo>> &&)
0x1800f2f7d  lea     rcx, [rbp+110h+var_C0]
0x1800f2f81  call    ??1?$pair@$$CBV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@V?$shared_ptr@VCWinHttpSessionInfo@@@2@@std@@QEAA@XZ; std::pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>::~pair<std::tuple<std::wstring,ulong,std::wstring,std::wstring,ulong,ulong> const,std::shared_ptr<CWinHttpSessionInfo>>(void)
0x1800f2f86  jmp     short loc_1800F2F93
0x1800f2f88  mov     rcx, rdi; hInternet
0x1800f2f8b  call    cs:__imp_WinHttpCloseHandle
0x1800f2f91  xor     edi, edi
0x1800f2f93  lea     rcx, [rsp+210h+var_1A8]; void *
0x1800f2f98  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800f2f9d  lea     rcx, [rbp+110h+var_148]
0x1800f2fa1  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x1800f2fa6  mov     rax, cs:qword_18021AD00
0x1800f2fad  cmp     rbx, rax
0x1800f2fb0  jz      short loc_1800F2FC1
0x1800f2fb2  mov     rax, [rbx+90h]
0x1800f2fb9  mov     rdi, [rax+8]
0x1800f2fbd  lock inc dword ptr [rax+10h]
0x1800f2fc1  test    rdi, rdi
0x1800f2fc4  jz      short loc_1800F2FF5
0x1800f2fc6  mov     rcx, [rbp+110h+var_180]
0x1800f2fca  test    rcx, rcx
0x1800f2fcd  jz      short loc_1800F2FD3
0x1800f2fcf  lock inc dword ptr [rcx+8]
0x1800f2fd3  mov     rax, [r14]
0x1800f2fd6  mov     [rsp+210h+var_1A8], rax
0x1800f2fdb  mov     [r14], rsi
0x1800f2fde  mov     rax, [r14+8]
0x1800f2fe2  mov     [rsp+210h+var_1A0], rax
0x1800f2fe7  mov     [r14+8], rcx
0x1800f2feb  lea     rcx, [rsp+210h+var_1A8]; void *
0x1800f2ff0  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800f2ff5  lea     rcx, [rbp+110h+var_188]; void *
0x1800f2ff9  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800f2ffe  lea     rcx, [rbp+110h+var_128]; void *
0x1800f3002  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f3007  lea     rcx, [rbp+110h+var_108]; void *
0x1800f300b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f3010  lea     rcx, [rbp+110h+var_E8]; void *
0x1800f3014  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f3019  mov     rax, rdi
0x1800f301c  mov     rcx, [rbp+110h+var_40]
0x1800f3023  xor     rcx, rsp; StackCookie
0x1800f3026  call    __security_check_cookie
0x1800f302b  mov     rbx, [rsp+210h+arg_0]
0x1800f3033  add     rsp, 1E0h
0x1800f303a  pop     r15
0x1800f303c  pop     r14
0x1800f303e  pop     r13
0x1800f3040  pop     r12
0x1800f3042  pop     rdi
0x1800f3043  pop     rsi
0x1800f3044  pop     rbp
0x1800f3045  retn
```
