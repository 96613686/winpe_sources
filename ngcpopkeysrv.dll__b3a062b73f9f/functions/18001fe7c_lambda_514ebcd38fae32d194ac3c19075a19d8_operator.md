# _lambda_514ebcd38fae32d194ac3c19075a19d8_::operator()

- ea: `0x18001fe7c`
- end: `0x1800201fd`
- name: `_lambda_514ebcd38fae32d194ac3c19075a19d8_::operator()`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001f5c8`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18000da94`
- `0x180010784`
- `0x180013754`
- `0x180017e08`
- `0x18001862c`
- `0x18001f4a8`
- `0x18001f810`
- `0x18001fbc0`
- `0x18001fc50`
- `0x18001fcb4`
- `0x18001fe7c`
- `0x180020244`
- `0x1800202a0`
- `0x180020334`
- `0x1800208ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ff1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020162`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ff1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020162`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800201a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800201a7`
- `ncrypt!NCryptSetProperty` at `0x1800200ca`
- `ncrypt!NCryptSetProperty` at `0x1800200ca`
- `ncrypt!NCryptImportKey` at `0x18002013a`
- `ncrypt!NCryptImportKey` at `0x18002013a`
- `ncrypt!NCryptOpenKey` at `0x1800200f1`
- `ncrypt!NCryptOpenKey` at `0x1800200f1`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002009e`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002009e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall lambda_514ebcd38fae32d194ac3c19075a19d8_::operator()(__int64 a1)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 *v3; // rax
  __int64 v4; // r14
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rax
  _DWORD *v8; // r9
  NCRYPT_KEY_HANDLE v9; // rdx
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  RTL_SRWLOCK *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  char v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-B8h] BYREF
  NCRYPT_KEY_HANDLE v18; // [rsp+50h] [rbp-B0h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  NCRYPT_KEY_HANDLE v21[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[16]; // [rsp+98h] [rbp-68h] BYREF
  NCRYPT_PROV_HANDLE *p_phProvider; // [rsp+A8h] [rbp-58h] BYREF
  NCRYPT_KEY_HANDLE *p_phKey; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v26; // [rsp+B8h] [rbp-48h]
  _DWORD v27[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v29[80]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v30[64]; // [rsp+160h] [rbp+60h] BYREF

  std::vector<unsigned char>::vector<unsigned char>(v22, **(_QWORD **)a1, **(_QWORD **)a1 + **(unsigned int **)(a1 + 8));
  v16[0] = 1;
  std::make_tuple<std::vector<unsigned char> &,std::wstring &,bool>(v28, v22, *(_QWORD *)(a1 + 16), v16);
  std::_Tree<std::_Tmap_traits<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<unsigned char>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<unsigned char>,std::wstring,bool> const,unsigned __int64>>,0>>::find(
    *(_QWORD *)(a1 + 24) + 8LL,
    &v18,
    v28);
  v2 = *(RTL_SRWLOCK **)(a1 + 24);
  if ( (PVOID)v18 != v2[1].Ptr )
  {
    if ( **(_BYTE **)(a1 + 32) )
    {
      AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
      v18 = (NCRYPT_KEY_HANDLE)v2;
      v3 = (__int64 *)std::_Tree<std::_Tmap_traits<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<unsigned char>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<unsigned char>,std::wstring,bool> const,unsigned __int64>>,0>>::find(
                        *(_QWORD *)(a1 + 24) + 8LL,
                        v21,
                        v28);
      v4 = *v3;
      if ( *v3 != *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) )
      {
        v16[0] = 0;
        std::make_tuple<std::vector<unsigned char> &,std::wstring &,bool>(v30, v22, *(_QWORD *)(a1 + 16), v16);
        v5 = *(_QWORD *)(a1 + 24);
        v20 = *(_OWORD *)std::_Tree<std::_Tmap_traits<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<unsigned char>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<unsigned char>,std::wstring,bool> const,unsigned __int64>>,0>>::_Eqrange<std::tuple<std::vector<unsigned char>,std::wstring,bool>>(
                           v5 + 8,
                           v21,
                           v28);
        std::_Tree<std::_Tmap_traits<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<unsigned char>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<unsigned char>,std::wstring,bool> const,unsigned __int64>>,0>>::_Erase(
          v5 + 8,
          &v20);
        v6 = *(_QWORD *)(a1 + 24);
        v7 = std::make_pair<std::tuple<std::vector<unsigned char>,std::wstring,bool> &,unsigned __int64 &>(
               v29,
               v30,
               v4 + 96);
        std::map<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64>::insert<std::pair<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64>,0>(
          v6 + 8,
          &v20,
          v7);
        std::tuple<std::vector<unsigned char>,std::wstring,bool>::~tuple<std::vector<unsigned char>,std::wstring,bool>(v29);
        LODWORD(p_phProvider) = 0;
        BYTE4(p_phProvider) = 0;
        _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&p_phProvider);
        if ( (unsigned int)dword_180037000 > 5 )
        {
          if ( BYTE4(p_phProvider) && (v27[0] || v27[1] || v27[2] || v27[3]) )
            v8 = v27;
          else
            v8 = 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_180037000,
            &unk_18002F0B8,
            &p_phKey,
            v8);
        }
        *(_QWORD *)&v20 = &p_phProvider;
        WORD4(v20) = 256;
        wil::details::ScopeExitFnGuard__lambda_c043ee833b7a9482bfee435ffcd5aa2d___::operator()(&v20);
        _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&p_phProvider);
        std::tuple<std::vector<unsigned char>,std::wstring,bool>::~tuple<std::vector<unsigned char>,std::wstring,bool>(v30);
      }
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
    }
    else
    {
      v9 = *(_QWORD *)(v18 + 96);
      if ( v9 )
      {
LABEL_24:
        ***(_QWORD ***)(a1 + 40) = v9;
        v10 = 0;
        goto LABEL_25;
      }
    }
  }
  phProvider = 0;
  phKey = 0;
  p_phProvider = &phProvider;
  p_phKey = &phKey;
  v26 = 256;
  v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( !v10 )
  {
    NCryptSetProperty(phProvider, L"PCP_SESSIONID", (PBYTE)&byte_18002B758, 0x10u, 0);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(_QWORD *)(a1 + 16));
    v10 = NCryptOpenKey(phProvider, &phKey, v11, 0, 0x10000000u);
    if ( !v10 )
    {
      v21[0] = 0;
      v10 = NCryptImportKey(phProvider, phKey, L"OpaqueTransport", 0, v21, **(PBYTE **)a1, **(_DWORD **)(a1 + 8), 0);
      if ( !v10 )
      {
        v18 = v21[0];
        v12 = *(RTL_SRWLOCK **)(a1 + 24);
        AcquireSRWLockExclusive(v12);
        *(_QWORD *)&v20 = v12;
        v13 = *(_QWORD *)(a1 + 24);
        v14 = std::make_pair<std::tuple<std::vector<unsigned char>,std::wstring,bool> &,unsigned __int64 &>(
                v29,
                v28,
                &v18);
        std::map<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64>::insert<std::pair<std::tuple<std::vector<unsigned char>,std::wstring,bool>,unsigned __int64>,0>(
          v13 + 8,
          v23,
          v14);
        std::tuple<std::vector<unsigned char>,std::wstring,bool>::~tuple<std::vector<unsigned char>,std::wstring,bool>(v29);
        if ( v12 )
          ReleaseSRWLockExclusive(v12);
        wil::details::ScopeExitFnGuard__lambda_212d9ac23ba45ae0c898d24db370a86e___::operator()(&p_phProvider);
        v9 = v18;
        goto LABEL_24;
      }
    }
  }
  wil::details::ScopeExitFnGuard__lambda_212d9ac23ba45ae0c898d24db370a86e___::operator()(&p_phProvider);
LABEL_25:
  std::tuple<std::vector<unsigned char>,std::wstring,bool>::~tuple<std::vector<unsigned char>,std::wstring,bool>(v28);
  std::vector<unsigned char>::_Tidy(v22);
  return v10;
}

```

## disassembly

```asm
0x18001fe7c  push    rbp
0x18001fe7e  push    rbx
0x18001fe7f  push    rsi
0x18001fe80  push    rdi
0x18001fe81  push    r14
0x18001fe83  push    r15
0x18001fe85  lea     rbp, [rsp-0B8h]
0x18001fe8d  sub     rsp, 1B8h
0x18001fe94  mov     rax, cs:__security_cookie
0x18001fe9b  xor     rax, rsp
0x18001fe9e  mov     [rbp+0E0h+var_40], rax
0x18001fea5  mov     rsi, rcx
0x18001fea8  mov     rax, [rcx]
0x18001feab  mov     rdx, [rax]
0x18001feae  mov     rax, [rcx+8]
0x18001feb2  mov     r8d, [rax]
0x18001feb5  add     r8, rdx
0x18001feb8  lea     rcx, [rbp+0E0h+var_160]
0x18001febc  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18001fec1  nop
0x18001fec2  mov     [rsp+1E0h+var_1A0], 1
0x18001fec7  lea     r9, [rsp+1E0h+var_1A0]
0x18001fecc  mov     r8, [rsi+10h]
0x18001fed0  lea     rdx, [rbp+0E0h+var_160]
0x18001fed4  lea     rcx, [rbp+0E0h+var_110]
0x18001fed8  call    ??$make_tuple@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@YA?AV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@0@AEAV?$vector@EV?$allocator@E@std@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEA_N@Z; std::make_tuple<std::vector<uchar> &,std::wstring &,bool>(std::vector<uchar> &,std::wstring &,bool &&)
0x18001fedd  nop
0x18001fede  mov     rcx, [rsi+18h]
0x18001fee2  add     rcx, 8
0x18001fee6  lea     r8, [rbp+0E0h+var_110]
0x18001feea  lea     rdx, [rsp+1E0h+var_190]
0x18001feef  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_KU?$less@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@std@@@std@@@2@AEBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<uchar>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool> const,unsigned __int64>>,0>>::find(std::tuple<std::vector<uchar>,std::wstring,bool> const &)
0x18001fef4  mov     rbx, [rsi+18h]
0x18001fef8  xor     r15d, r15d
0x18001fefb  mov     rax, [rsp+1E0h+var_190]
0x18001ff00  cmp     rax, [rbx+8]
0x18001ff04  jz      loc_18002006D
0x18001ff0a  mov     rcx, [rsi+20h]
0x18001ff0e  cmp     [rcx], r15b
0x18001ff11  jz      loc_180020060
0x18001ff17  mov     rcx, rbx; SRWLock
0x18001ff1a  call    cs:__imp_AcquireSRWLockExclusive
0x18001ff20  mov     [rsp+1E0h+var_190], rbx
0x18001ff25  mov     rcx, [rsi+18h]
0x18001ff29  add     rcx, 8
0x18001ff2d  lea     r8, [rbp+0E0h+var_110]
0x18001ff31  lea     rdx, [rsp+1E0h+var_170]
0x18001ff36  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_KU?$less@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@std@@@std@@@2@AEBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<uchar>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool> const,unsigned __int64>>,0>>::find(std::tuple<std::vector<uchar>,std::wstring,bool> const &)
0x18001ff3b  mov     r14, [rax]
0x18001ff3e  mov     rax, [rsi+18h]
0x18001ff42  cmp     r14, [rax+8]
0x18001ff46  jz      loc_18002004F
0x18001ff4c  mov     [rsp+1E0h+var_1A0], r15b
0x18001ff51  lea     r9, [rsp+1E0h+var_1A0]
0x18001ff56  mov     r8, [rsi+10h]
0x18001ff5a  lea     rdx, [rbp+0E0h+var_160]
0x18001ff5e  lea     rcx, [rbp+0E0h+var_80]
0x18001ff62  call    ??$make_tuple@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@YA?AV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@0@AEAV?$vector@EV?$allocator@E@std@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEA_N@Z; std::make_tuple<std::vector<uchar> &,std::wstring &,bool>(std::vector<uchar> &,std::wstring &,bool &&)
0x18001ff67  nop
0x18001ff68  mov     rdi, [rsi+18h]
0x18001ff6c  lea     r8, [rbp+0E0h+var_110]
0x18001ff70  lea     rdx, [rsp+1E0h+var_170]
0x18001ff75  lea     rcx, [rdi+8]
0x18001ff79  call    ??$_Eqrange@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_KU?$less@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@PEAX@std@@PEAU12@@1@AEBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@1@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<uchar>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool> const,unsigned __int64>>,0>>::_Eqrange<std::tuple<std::vector<uchar>,std::wstring,bool>>(std::tuple<std::vector<uchar>,std::wstring,bool> const &)
0x18001ff7e  movups  xmm0, xmmword ptr [rax]
0x18001ff81  movdqu  [rsp+1E0h+var_180], xmm0
0x18001ff87  lea     rdx, [rsp+1E0h+var_180]
0x18001ff8c  lea     rcx, [rdi+8]
0x18001ff90  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_KU?$less@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64,std::less<std::tuple<std::vector<uchar>,std::wstring,bool>>,std::allocator<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool> const,unsigned __int64>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool> const,unsigned __int64>,void *> *,std::_Tree_node<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool> const,unsigned __int64>,void *> *>)
0x18001ff95  mov     rdi, [rsi+18h]
0x18001ff99  lea     r8, [r14+60h]
0x18001ff9d  lea     rdx, [rbp+0E0h+var_80]
0x18001ffa1  lea     rcx, [rbp+0E0h+var_D0]
0x18001ffa5  call    ??$make_pair@AEAV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@AEA_K@std@@YA?AU?$pair@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@0@AEAV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@0@AEA_K@Z; std::make_pair<std::tuple<std::vector<uchar>,std::wstring,bool> &,unsigned __int64 &>(std::tuple<std::vector<uchar>,std::wstring,bool> &,unsigned __int64 &)
0x18001ffaa  nop
0x18001ffab  mov     r8, rax
0x18001ffae  lea     rdx, [rsp+1E0h+var_180]
0x18001ffb3  lea     rcx, [rdi+8]
0x18001ffb7  call    ??$insert@U?$pair@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@$0A@@?$map@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_KU?$less@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@1@@Z; std::map<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64>::insert<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64>,0>(std::pair<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64> &&)
0x18001ffbc  nop
0x18001ffbd  lea     rcx, [rbp+0E0h+var_D0]
0x18001ffc1  call    ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::wstring,bool>::~tuple<std::vector<uchar>,std::wstring,bool>(void)
0x18001ffc6  mov     dword ptr [rbp+0E0h+var_138], r15d
0x18001ffca  mov     byte ptr [rbp+0E0h+var_138+4], r15b
0x18001ffce  lea     rcx, [rbp+0E0h+var_138]
0x18001ffd2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18001ffd7  mov     eax, cs:dword_180037000
0x18001ffdd  cmp     eax, 5
0x18001ffe0  jbe     short loc_180020020
0x18001ffe2  cmp     byte ptr [rbp+0E0h+var_138+4], r15b
0x18001ffe6  jz      short loc_180020006
0x18001ffe8  cmp     [rbp+0E0h+var_120], r15d
0x18001ffec  jnz     short loc_180020000
0x18001ffee  cmp     [rbp+0E0h+var_11C], r15d
0x18001fff2  jnz     short loc_180020000
0x18001fff4  cmp     [rbp+0E0h+var_118], r15d
0x18001fff8  jnz     short loc_180020000
0x18001fffa  cmp     [rbp+0E0h+var_114], r15d
0x18001fffe  jz      short loc_180020006
0x180020000  lea     r9, [rbp+0E0h+var_120]
0x180020004  jmp     short loc_180020009
0x180020006  mov     r9, r15
0x180020009  lea     r8, [rbp+0E0h+var_130]
0x18002000d  lea     rdx, unk_18002F0B8
0x180020014  lea     rcx, dword_180037000
0x18002001b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180020020  lea     rax, [rbp+0E0h+var_138]
0x180020024  mov     qword ptr [rsp+1E0h+var_180], rax
0x180020029  mov     word ptr [rsp+1E0h+var_180+8], 100h
0x180020030  lea     rcx, [rsp+1E0h+var_180]
0x180020035  call    wil__details__ScopeExitFnGuard__lambda_c043ee833b7a9482bfee435ffcd5aa2d_____operator__
0x18002003a  nop
0x18002003b  lea     rcx, [rbp+0E0h+var_138]
0x18002003f  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180020044  nop
0x180020045  lea     rcx, [rbp+0E0h+var_80]
0x180020049  call    ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::wstring,bool>::~tuple<std::vector<uchar>,std::wstring,bool>(void)
0x18002004e  nop
0x18002004f  test    rbx, rbx
0x180020052  jz      short loc_18002006D
0x180020054  mov     rcx, rbx; SRWLock
0x180020057  call    cs:__imp_ReleaseSRWLockExclusive
0x18002005d  nop
0x18002005e  jmp     short loc_18002006D
0x180020060  mov     rdx, [rax+60h]
0x180020064  test    rdx, rdx
0x180020067  jnz     loc_1800201BC
0x18002006d  mov     [rsp+1E0h+phProvider], r15
0x180020072  mov     [rsp+1E0h+phKey], r15
0x180020077  lea     rax, [rsp+1E0h+phProvider]
0x18002007c  mov     [rbp+0E0h+var_138], rax
0x180020080  lea     rax, [rsp+1E0h+phKey]
0x180020085  mov     [rbp+0E0h+var_130], rax
0x180020089  mov     [rbp+0E0h+var_128], 100h
0x18002008f  xor     r8d, r8d; dwFlags
0x180020092  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180020099  lea     rcx, [rsp+1E0h+phProvider]; phProvider
0x18002009e  call    cs:__imp_NCryptOpenStorageProvider
0x1800200a4  mov     ebx, eax
0x1800200a6  test    eax, eax
0x1800200a8  jnz     loc_180020146
0x1800200ae  mov     [rsp+1E0h+dwFlags], r15d; dwFlags
0x1800200b3  lea     r9d, [rax+10h]; cbInput
0x1800200b7  lea     r8, byte_18002B758; pbInput
0x1800200be  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x1800200c5  mov     rcx, [rsp+1E0h+phProvider]; hObject
0x1800200ca  call    cs:__imp_NCryptSetProperty
0x1800200d0  mov     rcx, [rsi+10h]
0x1800200d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800200d9  mov     [rsp+1E0h+dwFlags], 10000000h; dwFlags
0x1800200e1  xor     r9d, r9d; dwLegacyKeySpec
0x1800200e4  mov     r8, rax; pszKeyName
0x1800200e7  lea     rdx, [rsp+1E0h+phKey]; phKey
0x1800200ec  mov     rcx, [rsp+1E0h+phProvider]; hProvider
0x1800200f1  call    cs:__imp_NCryptOpenKey
0x1800200f7  mov     ebx, eax
0x1800200f9  test    eax, eax
0x1800200fb  jnz     short loc_180020146
0x1800200fd  mov     [rsp+1E0h+var_170], r15
0x180020102  mov     rax, [rsi+8]
0x180020106  mov     rcx, [rsi]
0x180020109  mov     [rsp+1E0h+var_1A8], r15d; dwFlags
0x18002010e  mov     eax, [rax]
0x180020110  mov     [rsp+1E0h+cbData], eax; cbData
0x180020114  mov     rax, [rcx]
0x180020117  mov     [rsp+1E0h+pbData], rax; pbData
0x18002011c  lea     rax, [rsp+1E0h+var_170]
0x180020121  mov     qword ptr [rsp+1E0h+dwFlags], rax; phKey
0x180020126  xor     r9d, r9d; pParameterList
0x180020129  lea     r8, pszBlobType; "OpaqueTransport"
0x180020130  mov     rdx, [rsp+1E0h+phKey]; hImportKey
0x180020135  mov     rcx, [rsp+1E0h+phProvider]; hProvider
0x18002013a  call    cs:__imp_NCryptImportKey
0x180020140  mov     ebx, eax
0x180020142  test    eax, eax
0x180020144  jz      short loc_180020151
0x180020146  lea     rcx, [rbp+0E0h+var_138]
0x18002014a  call    wil__details__ScopeExitFnGuard__lambda_212d9ac23ba45ae0c898d24db370a86e_____operator__
0x18002014f  jmp     short loc_1800201C9
0x180020151  mov     rax, [rsp+1E0h+var_170]
0x180020156  mov     [rsp+1E0h+var_190], rax
0x18002015b  mov     rdi, [rsi+18h]
0x18002015f  mov     rcx, rdi; SRWLock
0x180020162  call    cs:__imp_AcquireSRWLockExclusive
0x180020168  mov     qword ptr [rsp+1E0h+var_180], rdi
0x18002016d  mov     rbx, [rsi+18h]
0x180020171  lea     r8, [rsp+1E0h+var_190]
0x180020176  lea     rdx, [rbp+0E0h+var_110]
0x18002017a  lea     rcx, [rbp+0E0h+var_D0]
0x18002017e  call    ??$make_pair@AEAV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@AEA_K@std@@YA?AU?$pair@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@0@AEAV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@0@AEA_K@Z; std::make_pair<std::tuple<std::vector<uchar>,std::wstring,bool> &,unsigned __int64 &>(std::tuple<std::vector<uchar>,std::wstring,bool> &,unsigned __int64 &)
0x180020183  nop
0x180020184  mov     r8, rax
0x180020187  lea     rdx, [rbp+0E0h+var_148]
0x18002018b  lea     rcx, [rbx+8]
0x18002018f  call    ??$insert@U?$pair@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@$0A@@?$map@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_KU?$less@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@_K@1@@Z; std::map<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64>::insert<std::pair<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64>,0>(std::pair<std::tuple<std::vector<uchar>,std::wstring,bool>,unsigned __int64> &&)
0x180020194  nop
0x180020195  lea     rcx, [rbp+0E0h+var_D0]
0x180020199  call    ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::wstring,bool>::~tuple<std::vector<uchar>,std::wstring,bool>(void)
0x18002019e  nop
0x18002019f  test    rdi, rdi
0x1800201a2  jz      short loc_1800201AE
0x1800201a4  mov     rcx, rdi; SRWLock
0x1800201a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800201ad  nop
0x1800201ae  lea     rcx, [rbp+0E0h+var_138]
0x1800201b2  call    wil__details__ScopeExitFnGuard__lambda_212d9ac23ba45ae0c898d24db370a86e_____operator__
0x1800201b7  mov     rdx, [rsp+1E0h+var_190]
0x1800201bc  mov     rax, [rsi+28h]
0x1800201c0  mov     rcx, [rax]
0x1800201c3  mov     [rcx], rdx
0x1800201c6  mov     ebx, r15d
0x1800201c9  lea     rcx, [rbp+0E0h+var_110]
0x1800201cd  call    ??1?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@std@@QEAA@XZ; std::tuple<std::vector<uchar>,std::wstring,bool>::~tuple<std::vector<uchar>,std::wstring,bool>(void)
0x1800201d2  nop
0x1800201d3  lea     rcx, [rbp+0E0h+var_160]
0x1800201d7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800201dc  mov     eax, ebx
0x1800201de  mov     rcx, [rbp+0E0h+var_40]
0x1800201e5  xor     rcx, rsp; StackCookie
0x1800201e8  call    __security_check_cookie
0x1800201ed  add     rsp, 1B8h
0x1800201f4  pop     r15
0x1800201f6  pop     r14
0x1800201f8  pop     rdi
0x1800201f9  pop     rsi
0x1800201fa  pop     rbx
0x1800201fb  pop     rbp
0x1800201fc  retn
```
