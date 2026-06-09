# CallFileApiAsApp<int>(ushort const *,std::function<int (void)>,std::function<int (ComError const &)>)

- ea: `0x1800f5088`
- end: `0x1800f553c`
- name: `??$CallFileApiAsApp@H@@YAHPEBGV?$function@$$A6AHXZ@std@@V?$function@$$A6AHAEBVComError@@@Z@1@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f55fc`

## callees

- `0x180006640`
- `0x180012b18`
- `0x180014310`
- `0x180016d60`
- `0x1800543a0`
- `0x1800586f0`
- `0x18005b280`
- `0x180073b34`
- `0x18007c29c`
- `0x180086674`
- `0x180099ce8`
- `0x1800a0738`
- `0x1800b15a8`
- `0x1800f5088`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800f5401`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800f5401`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800f51bd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800f51bd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800f5223`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800f5223`
- `ext-ms-win-winrt-storage-l1-2-3!QueryStorageAccess_FullTrustCaller_ForToken` at `0x1800f5399`
- `ext-ms-win-winrt-storage-l1-2-3!QueryStorageAccess_FullTrustCaller_ForToken` at `0x1800f5399`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CallFileApiAsApp<int>(__int64 a1, __int64 a2, __int64 a3)
{
  char v6; // r14
  signed int v7; // eax
  HANDLE *v8; // rax
  int v9; // eax
  _DWORD *v10; // rax
  int v11; // eax
  void **RawBuffer; // rax
  int UserToken; // eax
  __int64 v14; // rax
  char **Sid; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 result; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  void *v27; // [rsp+20h] [rbp-308h] BYREF
  __int64 v28; // [rsp+28h] [rbp-300h] BYREF
  HANDLE *v29; // [rsp+30h] [rbp-2F8h] BYREF
  __int64 v30; // [rsp+38h] [rbp-2F0h] BYREF
  _BYTE v31[16]; // [rsp+40h] [rbp-2E8h] BYREF
  const ComError *v32; // [rsp+50h] [rbp-2D8h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-2C8h] BYREF
  __int128 v34; // [rsp+68h] [rbp-2C0h]
  signed int v35; // [rsp+78h] [rbp-2B0h]
  int v36; // [rsp+7Ch] [rbp-2ACh]
  int v37; // [rsp+80h] [rbp-2A8h]
  void **v38; // [rsp+C0h] [rbp-268h] BYREF
  __int128 v39; // [rsp+C8h] [rbp-260h]
  int v40; // [rsp+D8h] [rbp-250h]
  int v41; // [rsp+DCh] [rbp-24Ch]
  int v42; // [rsp+E0h] [rbp-248h]
  void **v43; // [rsp+120h] [rbp-208h] BYREF
  __int128 v44; // [rsp+128h] [rbp-200h]
  int v45; // [rsp+138h] [rbp-1F0h]
  int v46; // [rsp+13Ch] [rbp-1ECh]
  int v47; // [rsp+140h] [rbp-1E8h]
  void **v48; // [rsp+180h] [rbp-1A8h] BYREF
  __int128 v49; // [rsp+188h] [rbp-1A0h]
  int v50; // [rsp+198h] [rbp-190h]
  int v51; // [rsp+19Ch] [rbp-18Ch]
  int v52; // [rsp+1A0h] [rbp-188h]
  void **v53; // [rsp+1E0h] [rbp-148h] BYREF
  __int128 v54; // [rsp+1E8h] [rbp-140h]
  int v55; // [rsp+1F8h] [rbp-130h]
  int v56; // [rsp+1FCh] [rbp-12Ch]
  int v57; // [rsp+200h] [rbp-128h]
  void **v58; // [rsp+240h] [rbp-E8h] BYREF
  __int128 v59; // [rsp+248h] [rbp-E0h]
  int v60; // [rsp+258h] [rbp-D0h]
  int v61; // [rsp+25Ch] [rbp-CCh]
  int v62; // [rsp+260h] [rbp-C8h]
  void **v63; // [rsp+2A0h] [rbp-88h] BYREF
  __int128 v64; // [rsp+2A8h] [rbp-80h]
  int v65; // [rsp+2B8h] [rbp-70h]
  int v66; // [rsp+2BCh] [rbp-6Ch]
  int v67; // [rsp+2C0h] [rbp-68h]
  _DWORD *v70; // [rsp+348h] [rbp+20h] BYREF

  v6 = 0;
  LODWORD(v70) = 0;
  v27 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v27,
    0);
  v7 = wil::open_current_access_token_nothrow(&v27);
  try
  {
    if ( v7 < 0 )
    {
      v34 = 0;
      pExceptionObject = &ComError::`vftable';
      v35 = v7;
      v36 = 1135;
      v37 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v8 = (HANDLE *)operator new(0x10u);
    v29 = v8;
    *((_DWORD *)v8 + 2) = 1;
    *v8 = 0;
    v28 = -1;
    v9 = wil::impersonate_token_nothrow(0, (void **)&v28);
    if ( v9 < 0 )
    {
      v39 = 0;
      v38 = &ComError::`vftable';
      v40 = v9;
      v41 = 1142;
      v42 = 1;
      throw (ComError *)&v38;
    }
    v10 = operator new(0x10u);
    v70 = v10;
    v10[2] = 1;
    *(_QWORD *)v10 = 0;
    v30 = 0;
    v11 = UMgrQueryUserContext(v27, &v30);
    if ( v11 < 0 )
    {
      v44 = 0;
      v43 = &ComError::`vftable';
      v45 = v11;
      v46 = 1146;
      v47 = 1;
      throw (ComError *)&v43;
    }
    RawBuffer = TokenHandle::GetRawBuffer((TokenHandle *)&v70);
    UserToken = UMgrQueryUserToken(v30, RawBuffer);
    if ( UserToken < 0 )
    {
      v49 = 0;
      v48 = &ComError::`vftable';
      v50 = UserToken;
      v51 = 1147;
      v52 = 1;
      throw (ComError *)&v48;
    }
    v14 = TokenHandle::copyEx(&v70, v31, 2, 2);
    TokenHandle::operator=(&v29, v14);
    TokenHandle::Decrement((TokenHandle *)v31);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      Sid = (char **)TokenHandle::GetSid(&v29, v31);
      v6 = 1;
      WPP_SF__sid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x24u,
        (__int64)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        *Sid);
    }
    if ( (v6 & 1) != 0 )
      SidHandle::~SidHandle((SidHandle *)v31);
    TokenHandle::Decrement((TokenHandle *)&v70);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v28);
    v28 = -1;
    v16 = wil::impersonate_token_nothrow(*v29, (void **)&v28);
    if ( v16 < 0 )
    {
      v54 = 0;
      v53 = &ComError::`vftable';
      v55 = v16;
      v56 = 1157;
      v57 = 1;
      throw (ComError *)&v53;
    }
    LODWORD(v70) = 0;
    v17 = QueryStorageAccess_FullTrustCaller_ForToken(v27, a1, &v70);
    if ( v17 < 0 )
    {
      v59 = 0;
      v58 = &ComError::`vftable';
      v60 = v17;
      v61 = 1160;
      v62 = 1;
      throw (ComError *)&v58;
    }
    if ( !(_DWORD)v70 )
    {
      v64 = 0;
      v63 = &ComError::`vftable';
      v65 = -2147024891;
      v66 = 1167;
      v67 = 1;
      throw (ComError *)&v63;
    }
    v18 = *(_QWORD *)(a2 + 56);
    if ( !v18 )
      std::_Xbad_function_call();
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v28);
    TokenHandle::Decrement((TokenHandle *)&v29);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
    v21 = *(_QWORD *)(a2 + 56);
    if ( v21 )
    {
      LOBYTE(v20) = v21 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 32LL))(v21, v20);
      *(_QWORD *)(a2 + 56) = 0;
    }
    v22 = *(_QWORD *)(a3 + 56);
    if ( v22 )
    {
      LOBYTE(v20) = v22 != a3;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 32LL))(v22, v20);
      *(_QWORD *)(a3 + 56) = 0;
    }
    result = v19;
  }
  catch ( const ComError *v32 )
  {
    if ( !*(_QWORD *)(a3 + 56) )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    LODWORD(v70) = (*(__int64 (__fastcall **)(_QWORD, const ComError *))(**(_QWORD **)(a3 + 56) + 16LL))(
                     *(_QWORD *)(a3 + 56),
                     v32);
    v24 = *(_QWORD *)(a2 + 56);
    if ( v24 )
    {
      LOBYTE(v25) = v24 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 32LL))(v24, v25);
      *(_QWORD *)(a2 + 56) = 0;
    }
    v26 = *(_QWORD *)(a3 + 56);
    if ( v26 )
    {
      LOBYTE(v25) = v26 != a3;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 32LL))(v26, v25);
      *(_QWORD *)(a3 + 56) = 0;
    }
    return (unsigned int)v70;
  }
  return result;
}

```

## disassembly

```asm
0x1800f5088  mov     [rsp+arg_10], r8
0x1800f508d  mov     [rsp+arg_8], rdx
0x1800f5092  push    rsi
0x1800f5093  push    rdi
0x1800f5094  push    r12
0x1800f5096  push    r14
0x1800f5098  push    r15
0x1800f509a  sub     rsp, 300h
0x1800f50a1  mov     r15, r8
0x1800f50a4  mov     rsi, rdx
0x1800f50a7  mov     r12, rcx
0x1800f50aa  xor     r14d, r14d
0x1800f50ad  mov     dword ptr [rsp+328h+arg_18], r14d
0x1800f50b5  mov     [rsp+328h+var_308], r14
0x1800f50ba  xor     edx, edx
0x1800f50bc  lea     rcx, [rsp+328h+var_308]
0x1800f50c1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800f50c6  lea     rcx, [rsp+328h+var_308]
0x1800f50cb  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x1800f50d0  test    eax, eax
0x1800f50d2  jns     short loc_1800F5110
0x1800f50d4  xorps   xmm0, xmm0
0x1800f50d7  movups  [rsp+328h+var_2C0], xmm0
0x1800f50dc  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f50e3  mov     [rsp+328h+pExceptionObject], rcx
0x1800f50e8  mov     [rsp+328h+var_2B0], eax
0x1800f50ec  mov     [rsp+328h+var_2AC], 46Fh
0x1800f50f4  lea     edi, [r14+1]
0x1800f50f8  mov     [rsp+328h+var_2A8], edi
0x1800f50ff  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f5106  lea     rcx, [rsp+328h+pExceptionObject]; pExceptionObject
0x1800f510b  call    _CxxThrowException_0
0x1800f5110  mov     ecx, 10h; dwBytes
0x1800f5115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f511a  mov     [rsp+328h+var_2F8], rax
0x1800f511f  mov     edi, 1
0x1800f5124  mov     [rax+8], edi
0x1800f5127  mov     qword ptr [rax], 0
0x1800f512e  mov     [rsp+328h+var_300], 0FFFFFFFFFFFFFFFFh
0x1800f5137  lea     rdx, [rsp+328h+var_300]
0x1800f513c  xor     ecx, ecx; Token
0x1800f513e  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800f5143  test    eax, eax
0x1800f5145  jns     short loc_1800F518E
0x1800f5147  xorps   xmm0, xmm0
0x1800f514a  movups  [rsp+328h+var_260], xmm0
0x1800f5152  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f5159  mov     [rsp+328h+var_268], rcx
0x1800f5161  mov     [rsp+328h+var_250], eax
0x1800f5168  mov     [rsp+328h+var_24C], 476h
0x1800f5173  mov     [rsp+328h+var_248], edi
0x1800f517a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f5181  lea     rcx, [rsp+328h+var_268]; pExceptionObject
0x1800f5189  call    _CxxThrowException_0
0x1800f518e  mov     ecx, 10h; dwBytes
0x1800f5193  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f5198  mov     [rsp+328h+arg_18], rax
0x1800f51a0  mov     [rax+8], edi
0x1800f51a3  mov     qword ptr [rax], 0
0x1800f51aa  mov     [rsp+328h+var_2F0], 0
0x1800f51b3  lea     rdx, [rsp+328h+var_2F0]
0x1800f51b8  mov     rcx, [rsp+328h+var_308]
0x1800f51bd  call    cs:__imp_UMgrQueryUserContext
0x1800f51c3  test    eax, eax
0x1800f51c5  jns     short loc_1800F520E
0x1800f51c7  xorps   xmm0, xmm0
0x1800f51ca  movups  [rsp+328h+var_200], xmm0
0x1800f51d2  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f51d9  mov     [rsp+328h+var_208], rcx
0x1800f51e1  mov     [rsp+328h+var_1F0], eax
0x1800f51e8  mov     [rsp+328h+var_1EC], 47Ah
0x1800f51f3  mov     [rsp+328h+var_1E8], edi
0x1800f51fa  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f5201  lea     rcx, [rsp+328h+var_208]; pExceptionObject
0x1800f5209  call    _CxxThrowException_0
0x1800f520e  lea     rcx, [rsp+328h+arg_18]; this
0x1800f5216  call    ?GetRawBuffer@TokenHandle@@QEAAPEAPEAXXZ; TokenHandle::GetRawBuffer(void)
0x1800f521b  mov     rdx, rax
0x1800f521e  mov     rcx, [rsp+328h+var_2F0]
0x1800f5223  call    cs:__imp_UMgrQueryUserToken
0x1800f5229  test    eax, eax
0x1800f522b  jns     short loc_1800F5274
0x1800f522d  xorps   xmm0, xmm0
0x1800f5230  movups  [rsp+328h+var_1A0], xmm0
0x1800f5238  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f523f  mov     [rsp+328h+var_1A8], rcx
0x1800f5247  mov     [rsp+328h+var_190], eax
0x1800f524e  mov     [rsp+328h+var_18C], 47Bh
0x1800f5259  mov     [rsp+328h+var_188], edi
0x1800f5260  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f5267  lea     rcx, [rsp+328h+var_1A8]; pExceptionObject
0x1800f526f  call    _CxxThrowException_0
0x1800f5274  mov     r8d, 2
0x1800f527a  mov     r9d, r8d
0x1800f527d  lea     rdx, [rsp+328h+var_2E8]
0x1800f5282  lea     rcx, [rsp+328h+arg_18]
0x1800f528a  call    ?copyEx@TokenHandle@@QEBA?AV1@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; TokenHandle::copyEx(_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x1800f528f  mov     rdx, rax
0x1800f5292  lea     rcx, [rsp+328h+var_2F8]
0x1800f5297  call    ??4TokenHandle@@QEAAAEAV0@AEBV0@@Z; TokenHandle::operator=(TokenHandle const &)
0x1800f529c  lea     rcx, [rsp+328h+var_2E8]; this
0x1800f52a1  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800f52a6  lea     rcx, WPP_GLOBAL_Control
0x1800f52ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800f52b4  cmp     rax, rcx
0x1800f52b7  jz      short loc_1800F52F0
0x1800f52b9  test    [rax+1Ch], dil
0x1800f52bd  jz      short loc_1800F52F0
0x1800f52bf  lea     rdx, [rsp+328h+var_2E8]
0x1800f52c4  lea     rcx, [rsp+328h+var_2F8]
0x1800f52c9  call    ?GetSid@TokenHandle@@QEBA?AVSidHandle@@XZ; TokenHandle::GetSid(void)
0x1800f52ce  mov     r14d, edi
0x1800f52d1  mov     edx, 24h ; '$'
0x1800f52d6  mov     r9, [rax]
0x1800f52d9  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x1800f52e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f52e7  mov     rcx, [rcx+10h]
0x1800f52eb  call    WPP_SF__sid_
0x1800f52f0  test    dil, r14b
0x1800f52f3  jz      short loc_1800F5300
0x1800f52f5  lea     rcx, [rsp+328h+var_2E8]; this
0x1800f52fa  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x1800f52ff  nop
0x1800f5300  lea     rcx, [rsp+328h+arg_18]; this
0x1800f5308  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800f530d  nop
0x1800f530e  lea     rcx, [rsp+328h+var_300]
0x1800f5313  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800f5318  mov     [rsp+328h+var_300], 0FFFFFFFFFFFFFFFFh
0x1800f5321  lea     rdx, [rsp+328h+var_300]
0x1800f5326  mov     rcx, [rsp+328h+var_2F8]
0x1800f532b  mov     rcx, [rcx]; Token
0x1800f532e  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800f5333  test    eax, eax
0x1800f5335  jns     short loc_1800F537E
0x1800f5337  xorps   xmm0, xmm0
0x1800f533a  movups  [rsp+328h+var_140], xmm0
0x1800f5342  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f5349  mov     [rsp+328h+var_148], rcx
0x1800f5351  mov     [rsp+328h+var_130], eax
0x1800f5358  mov     [rsp+328h+var_12C], 485h
0x1800f5363  mov     [rsp+328h+var_128], edi
0x1800f536a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f5371  lea     rcx, [rsp+328h+var_148]; pExceptionObject
0x1800f5379  call    _CxxThrowException_0
0x1800f537e  mov     dword ptr [rsp+328h+arg_18], 0
0x1800f5389  lea     r8, [rsp+328h+arg_18]
0x1800f5391  mov     rdx, r12
0x1800f5394  mov     rcx, [rsp+328h+var_308]
0x1800f5399  call    cs:__imp_QueryStorageAccess_FullTrustCaller_ForToken
0x1800f539f  test    eax, eax
0x1800f53a1  jns     short loc_1800F53EA
0x1800f53a3  xorps   xmm0, xmm0
0x1800f53a6  movups  [rsp+328h+var_E0], xmm0
0x1800f53ae  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f53b5  mov     [rsp+328h+var_E8], rcx
0x1800f53bd  mov     [rsp+328h+var_D0], eax
0x1800f53c4  mov     [rsp+328h+var_CC], 488h
0x1800f53cf  mov     [rsp+328h+var_C8], edi
0x1800f53d6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f53dd  lea     rcx, [rsp+328h+var_E8]; pExceptionObject
0x1800f53e5  call    _CxxThrowException_0
0x1800f53ea  cmp     dword ptr [rsp+328h+arg_18], 0
0x1800f53f2  jz      loc_1800F5483
0x1800f53f8  mov     rcx, [rsi+38h]
0x1800f53fc  test    rcx, rcx
0x1800f53ff  jnz     short loc_1800F5407
0x1800f5401  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800f5407  mov     rax, [rcx]
0x1800f540a  mov     rax, [rax+10h]
0x1800f540e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5413  mov     edi, eax
0x1800f5415  lea     rcx, [rsp+328h+var_300]
0x1800f541a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800f541f  nop
0x1800f5420  lea     rcx, [rsp+328h+var_2F8]; this
0x1800f5425  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800f542a  nop
0x1800f542b  lea     rcx, [rsp+328h+var_308]
0x1800f5430  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f5435  nop
0x1800f5436  mov     rcx, [rsi+38h]
0x1800f543a  test    rcx, rcx
0x1800f543d  jz      short loc_1800F5459
0x1800f543f  mov     rax, [rcx]
0x1800f5442  cmp     rcx, rsi
0x1800f5445  setnz   dl
0x1800f5448  mov     rax, [rax+20h]
0x1800f544c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5451  mov     qword ptr [rsi+38h], 0
0x1800f5459  mov     rcx, [r15+38h]
0x1800f545d  test    rcx, rcx
0x1800f5460  jz      short loc_1800F547C
0x1800f5462  mov     rax, [rcx]
0x1800f5465  cmp     rcx, r15
0x1800f5468  setnz   dl
0x1800f546b  mov     rax, [rax+20h]
0x1800f546f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5474  mov     qword ptr [r15+38h], 0
0x1800f547c  mov     eax, edi
0x1800f547e  jmp     loc_1800F552C
0x1800f5483  xorps   xmm0, xmm0
0x1800f5486  movups  [rsp+328h+var_80], xmm0
0x1800f548e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800f5495  mov     [rsp+328h+var_88], rcx
0x1800f549d  mov     [rsp+328h+var_70], 80070005h
0x1800f54a8  mov     [rsp+328h+var_6C], 48Fh
0x1800f54b3  mov     [rsp+328h+var_68], edi
0x1800f54ba  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800f54c1  lea     rcx, [rsp+328h+var_88]; pExceptionObject
0x1800f54c9  call    _CxxThrowException_0
0x1800f54cf  mov     rdi, [rsp+328h+arg_8]
0x1800f54d7  mov     rcx, [rdi+38h]
0x1800f54db  test    rcx, rcx
0x1800f54de  jz      short loc_1800F54FA
0x1800f54e0  mov     rax, [rcx]
0x1800f54e3  cmp     rcx, rdi
0x1800f54e6  setnz   dl
0x1800f54e9  mov     rax, [rax+20h]
0x1800f54ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f54f2  mov     qword ptr [rdi+38h], 0
0x1800f54fa  mov     rdi, [rsp+328h+arg_10]
0x1800f5502  mov     rcx, [rdi+38h]
0x1800f5506  test    rcx, rcx
0x1800f5509  jz      short loc_1800F5525
0x1800f550b  mov     rax, [rcx]
0x1800f550e  cmp     rcx, rdi
0x1800f5511  setnz   dl
0x1800f5514  mov     rax, [rax+20h]
0x1800f5518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f551d  mov     qword ptr [rdi+38h], 0
0x1800f5525  mov     eax, dword ptr [rsp+328h+arg_18]
0x1800f552c  add     rsp, 300h
0x1800f5533  pop     r15
0x1800f5535  pop     r14
0x1800f5537  pop     r12
0x1800f5539  pop     rdi
0x1800f553a  pop     rsi
0x1800f553b  retn
```
