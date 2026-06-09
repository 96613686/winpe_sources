# RealtimeProtection::DlpUserSidCache::RefreshSessionIdToUserSidMap(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x18007d1b8`
- end: `0x18007d491`
- name: `?RefreshSessionIdToUserSidMap@DlpUserSidCache@RealtimeProtection@@YAJAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `729`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007ba1c`
- `0x1801aa9e8`

## callees

- `0x180028d80`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x18004b514`
- `0x18007d1b8`
- `0x18007d570`
- `0x1800809d0`
- `0x180094e70`
- `0x1800c8f68`
- `0x1800ca2b8`
- `0x180106d38`
- `0x180108e2a`
- `0x18010cb40`
- `0x18010ce3c`
- `0x1801d96ec`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007d404`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007d404`
- `KERNEL32!CloseHandle` at `0x18007d3eb`
- `KERNEL32!CloseHandle` at `0x18007d3eb`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18007d237`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18007d237`
- `WTSAPI32!WTSQueryUserToken` at `0x18007d2c0`
- `WTSAPI32!WTSQueryUserToken` at `0x18007d2c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
__int64 __fastcall RealtimeProtection::DlpUserSidCache::RefreshSessionIdToUserSidMap(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int LastError; // ebx
  __int64 i; // rdi
  void *v5; // r8
  const struct std::nothrow_t *v6; // rdx
  __int64 v7; // r15
  _QWORD *v8; // rax
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-A8h] BYREF
  char v11; // [rsp+58h] [rbp-A0h]
  _BYTE v12[48]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v13[16]; // [rsp+90h] [rbp-68h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+A0h] [rbp-58h] BYREF
  DWORD pCount; // [rsp+A8h] [rbp-50h] BYREF
  void *v16; // [rsp+B0h] [rbp-48h] BYREF
  void *phToken; // [rsp+B8h] [rbp-40h] BYREF
  __int128 v18; // [rsp+C0h] [rbp-38h] BYREF

  v18 = 0;
  std::atomic_load__anonymous_namespace_::UserSidCache_(&v18);
  v1 = v18;
  if ( (_QWORD)v18 )
  {
    ppSessionInfo = 0;
    pCount = 0;
    if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
        &SRWLock,
        v1 + 64);
      std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::clear(v1);
      for ( i = 0; (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
      {
        phToken = 0;
        if ( WTSQueryUserToken(ppSessionInfo[i].SessionId, &phToken) )
        {
          v16 = 0;
          if ( (int)CommonUtil::UtilGetStringSidFromToken((CommonUtil *)&v16, (wchar_t **)phToken, v5) >= 0 )
          {
            v7 = std::wstring::wstring(v12, v16);
            v8 = (_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::_Try_emplace<unsigned long const &,>(
                             v1,
                             v13,
                             &ppSessionInfo[i]);
            std::wstring::operator=(*v8 + 24LL, v7);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v12);
            std::wstring::wstring(v12, v16);
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v12);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v12);
          }
          if ( v16 )
            operator delete(v16, v6);
        }
        if ( phToken )
          CloseHandle(phToken);
      }
      if ( v11 )
        ReleaseSRWLockExclusive(SRWLock);
      WTSFreeMemory_0(ppSessionInfo);
      if ( *((_QWORD *)&v18 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v18 + 1));
      return 0;
    }
    else
    {
      LastError = HrGetLastError();
      if ( *((_QWORD *)&v18 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v18 + 1));
      return LastError;
    }
  }
  else
  {
    if ( *((_QWORD *)&v18 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v18 + 1));
    return 2147483662LL;
  }
}

```

## disassembly

```asm
0x18007d1b8  mov     r11, rsp
0x18007d1bb  mov     [r11+10h], rbx
0x18007d1bf  mov     [r11+18h], rsi
0x18007d1c3  push    rdi
0x18007d1c4  push    r14
0x18007d1c6  push    r15
0x18007d1c8  sub     rsp, 0E0h
0x18007d1cf  mov     rax, cs:__security_cookie
0x18007d1d6  xor     rax, rsp
0x18007d1d9  mov     [rsp+0F8h+var_28], rax
0x18007d1e1  mov     [rsp+0F8h+var_C0], rcx
0x18007d1e6  xorps   xmm0, xmm0
0x18007d1e9  movups  xmmword ptr [r11-38h], xmm0
0x18007d1ee  lea     rcx, [r11-38h]
0x18007d1f2  call    std__atomic_load__anonymous_namespace___UserSidCache_
0x18007d1f7  nop
0x18007d1f8  mov     rsi, [rsp+0F8h+var_38]
0x18007d200  test    rsi, rsi
0x18007d203  jz      loc_18007D451
0x18007d209  xor     ebx, ebx
0x18007d20b  mov     [rsp+0F8h+ppSessionInfo], rbx
0x18007d213  mov     [rsp+0F8h+var_50], ebx
0x18007d21a  lea     rax, [rsp+0F8h+var_50]
0x18007d222  mov     [rsp+0F8h+pCount], rax; pCount
0x18007d227  lea     r9, [rsp+0F8h+ppSessionInfo]; ppSessionInfo
0x18007d22f  xor     edx, edx; Reserved
0x18007d231  xor     ecx, ecx; hServer
0x18007d233  lea     r8d, [rbx+1]; Version
0x18007d237  call    cs:__imp_WTSEnumerateSessionsW
0x18007d23d  test    eax, eax
0x18007d23f  jnz     short loc_18007D261
0x18007d241  call    HrGetLastError
0x18007d246  mov     ebx, eax
0x18007d248  mov     rcx, [rsp+0F8h+var_30]; this
0x18007d250  test    rcx, rcx
0x18007d253  jz      short loc_18007D25A
0x18007d255  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007d25a  mov     eax, ebx
0x18007d25c  jmp     loc_18007D468
0x18007d261  mov     [rsp+0F8h+var_B8], bl
0x18007d265  lea     rax, [rsp+0F8h+ppSessionInfo]
0x18007d26d  mov     [rsp+0F8h+var_B0], rax
0x18007d272  lea     rdx, [rsi+40h]
0x18007d276  lea     rcx, [rsp+0F8h+SRWLock]
0x18007d27b  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x18007d280  nop
0x18007d281  mov     rcx, rsi
0x18007d284  call    ?clear@?$_Hash@V?$_Umap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::clear(void)
0x18007d289  xor     edi, edi
0x18007d28b  mov     [rsp+0F8h+var_C4], edi
0x18007d28f  cmp     edi, [rsp+0F8h+var_50]
0x18007d296  jnb     loc_18007D3F8
0x18007d29c  mov     [rsp+0F8h+phToken], 0
0x18007d2a8  lea     r14, [rdi+rdi*2]
0x18007d2ac  lea     rdx, [rsp+0F8h+phToken]; phToken
0x18007d2b4  mov     rcx, [rsp+0F8h+ppSessionInfo]
0x18007d2bc  mov     ecx, [rcx+r14*8]; SessionId
0x18007d2c0  call    cs:__imp_WTSQueryUserToken
0x18007d2c6  test    eax, eax
0x18007d2c8  jz      loc_18007D3DE
0x18007d2ce  mov     [rsp+0F8h+var_48], 0
0x18007d2da  mov     rdx, [rsp+0F8h+phToken]; wchar_t **
0x18007d2e2  lea     rcx, [rsp+0F8h+var_48]; this
0x18007d2ea  call    ?UtilGetStringSidFromToken@CommonUtil@@YAJPEAPEA_WPEAX@Z; CommonUtil::UtilGetStringSidFromToken(wchar_t * *,void *)
0x18007d2ef  test    eax, eax
0x18007d2f1  js      loc_18007D3CB
0x18007d2f7  mov     rdx, [rsp+0F8h+var_48]
0x18007d2ff  lea     rcx, [rsp+0F8h+var_98]
0x18007d304  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007d309  mov     r15, rax
0x18007d30c  mov     rcx, [rsp+0F8h+ppSessionInfo]
0x18007d314  lea     r8, [rcx+r14*8]
0x18007d318  lea     rdx, [rsp+0F8h+var_68]
0x18007d320  mov     rcx, rsi
0x18007d323  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18007d328  mov     rcx, [rax]
0x18007d32b  add     rcx, 18h
0x18007d32f  mov     rdx, r15
0x18007d332  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007d337  nop
0x18007d338  lea     rcx, [rsp+0F8h+var_98]; void *
0x18007d33d  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18007d342  mov     rdx, [rsp+0F8h+var_48]
0x18007d34a  lea     rcx, [rsp+0F8h+var_98]
0x18007d34f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007d354  nop
0x18007d355  lea     rdx, [rsp+0F8h+var_98]
0x18007d35a  mov     rcx, [rsp+0F8h+var_C0]
0x18007d35f  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18007d364  nop
0x18007d365  lea     rcx, [rsp+0F8h+var_98]; void *
0x18007d36a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18007d36f  nop
0x18007d370  jmp     short loc_18007D382
0x18007d372  mov     rsi, [rsp+0F8h+var_38]
0x18007d37a  mov     ebx, [rsp+0F8h+var_C8]
0x18007d37e  mov     edi, [rsp+0F8h+var_C4]
0x18007d382  test    ebx, ebx
0x18007d384  js      short loc_18007D398
0x18007d386  jmp     short loc_18007D3CB
0x18007d388  mov     rsi, [rsp+0F8h+var_38]
0x18007d390  mov     ebx, [rsp+0F8h+var_C8]
0x18007d394  mov     edi, [rsp+0F8h+var_C4]
0x18007d398  lea     rax, WPP_GLOBAL_Control
0x18007d39f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3a6  cmp     rcx, rax
0x18007d3a9  jz      short loc_18007D3C9
0x18007d3ab  test    byte ptr [rcx+1Ch], 1
0x18007d3af  jz      short loc_18007D3C9
0x18007d3b1  mov     edx, 0Ah
0x18007d3b6  mov     r9d, ebx
0x18007d3b9  lea     r8, WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids
0x18007d3c0  mov     rcx, [rcx+10h]
0x18007d3c4  call    WPP_SF_d
0x18007d3c9  xor     ebx, ebx
0x18007d3cb  mov     rcx, [rsp+0F8h+var_48]; void *
0x18007d3d3  test    rcx, rcx
0x18007d3d6  jz      short loc_18007D3DE
0x18007d3d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007d3dd  nop
0x18007d3de  mov     rcx, [rsp+0F8h+phToken]; hObject
0x18007d3e6  test    rcx, rcx
0x18007d3e9  jz      short loc_18007D3F1
0x18007d3eb  call    cs:__imp_CloseHandle
0x18007d3f1  inc     edi
0x18007d3f3  jmp     loc_18007D28B
0x18007d3f8  cmp     [rsp+0F8h+var_A0], 0
0x18007d3fd  jz      short loc_18007D40B
0x18007d3ff  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x18007d404  call    cs:__imp_ReleaseSRWLockExclusive
0x18007d40a  nop
0x18007d40b  jmp     short loc_18007D417
0x18007d40d  mov     ebx, [rsp+0F8h+var_C8]
0x18007d411  jmp     short loc_18007D41B
0x18007d413  mov     ebx, [rsp+0F8h+var_C8]
0x18007d417  test    ebx, ebx
0x18007d419  jns     short loc_18007D42D
0x18007d41b  mov     rcx, [rsp+0F8h+var_B0]
0x18007d420  mov     rcx, [rcx]; pMemory
0x18007d423  call    WTSFreeMemory_0
0x18007d428  jmp     loc_18007D248
0x18007d42d  mov     rcx, [rsp+0F8h+var_B0]
0x18007d432  mov     rcx, [rcx]; pMemory
0x18007d435  call    WTSFreeMemory_0
0x18007d43a  nop
0x18007d43b  mov     rcx, [rsp+0F8h+var_30]; this
0x18007d443  test    rcx, rcx
0x18007d446  jz      short loc_18007D44D
0x18007d448  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007d44d  xor     eax, eax
0x18007d44f  jmp     short loc_18007D468
0x18007d451  mov     rcx, [rsp+0F8h+var_30]; this
0x18007d459  test    rcx, rcx
0x18007d45c  jz      short loc_18007D463
0x18007d45e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007d463  mov     eax, 8000000Eh
0x18007d468  mov     rcx, [rsp+0F8h+var_28]
0x18007d470  xor     rcx, rsp; StackCookie
0x18007d473  call    __security_check_cookie
0x18007d478  lea     r11, [rsp+0F8h+var_18]
0x18007d480  mov     rbx, [r11+28h]
0x18007d484  mov     rsi, [r11+30h]
0x18007d488  mov     rsp, r11
0x18007d48b  pop     r15
0x18007d48d  pop     r14
0x18007d48f  pop     rdi
0x18007d490  retn
```
