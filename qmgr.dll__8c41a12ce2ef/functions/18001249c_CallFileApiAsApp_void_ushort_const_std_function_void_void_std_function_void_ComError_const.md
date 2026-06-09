# CallFileApiAsApp<void *>(ushort const *,std::function<void * (void)>,std::function<void * (ComError const &)>)

- ea: `0x18001249c`
- end: `0x180012b12`
- name: `??$CallFileApiAsApp@PEAX@@YAPEAXPEBGV?$function@$$A6APEAXXZ@std@@V?$function@$$A6APEAXAEBVComError@@@Z@1@@Z`
- size: `1654`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f5574`

## callees

- `0x180006640`
- `0x180011760`
- `0x18001249c`
- `0x180012b18`
- `0x180016d60`
- `0x180086674`
- `0x1800959c0`
- `0x180099ce8`
- `0x1800a0738`
- `0x1800a3444`
- `0x1800b15a8`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001254b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001254b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012858`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012561`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001286e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012561`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001286e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800125a3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800128b1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800125a3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800128b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001256b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001256b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012692`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012824`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012692`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012824`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a04`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800129a1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800129a1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180012633`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180012633`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800126a3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800126a3`
- `ext-ms-win-winrt-storage-l1-2-3!QueryStorageAccess_FullTrustCaller_ForToken` at `0x180012938`
- `ext-ms-win-winrt-storage-l1-2-3!QueryStorageAccess_FullTrustCaller_ForToken` at `0x180012938`

## string_xrefs

- `0x18001257d`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001288a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CallFileApiAsApp<void *>(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rsi
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // edi
  LPVOID v11; // rdi
  int v12; // eax
  int UserToken; // eax
  void ***v14; // r12
  void *v15; // rdx
  void *v16; // rcx
  _QWORD *Sid; // rax
  char v18; // r12
  __int64 v19; // rdi
  HANDLE v20; // rsi
  HANDLE v21; // rax
  const char *v22; // r9
  __int64 v23; // rdx
  int LastError; // esi
  int v25; // eax
  __int64 v26; // rcx
  void *v27; // rdx
  __int64 v28; // rsi
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 result; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  void *TokenHandle[2]; // [rsp+20h] [rbp-318h] BYREF
  HANDLE hObject; // [rsp+30h] [rbp-308h] BYREF
  void *v37; // [rsp+38h] [rbp-300h] BYREF
  __int64 v38; // [rsp+40h] [rbp-2F8h] BYREF
  __int64 v39; // [rsp+48h] [rbp-2F0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-2E8h]
  const ComError *v41; // [rsp+58h] [rbp-2E0h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-2D8h] BYREF
  __int128 v43; // [rsp+68h] [rbp-2D0h]
  int v44; // [rsp+78h] [rbp-2C0h]
  int v45; // [rsp+7Ch] [rbp-2BCh]
  int v46; // [rsp+80h] [rbp-2B8h]
  void **v47; // [rsp+C0h] [rbp-278h] BYREF
  __int128 v48; // [rsp+C8h] [rbp-270h]
  int v49; // [rsp+D8h] [rbp-260h]
  int v50; // [rsp+DCh] [rbp-25Ch]
  int v51; // [rsp+E0h] [rbp-258h]
  void **v52; // [rsp+120h] [rbp-218h] BYREF
  __int128 v53; // [rsp+128h] [rbp-210h]
  int v54; // [rsp+138h] [rbp-200h]
  int v55; // [rsp+13Ch] [rbp-1FCh]
  int v56; // [rsp+140h] [rbp-1F8h]
  void **v57; // [rsp+180h] [rbp-1B8h] BYREF
  __int128 v58; // [rsp+188h] [rbp-1B0h]
  int v59; // [rsp+198h] [rbp-1A0h]
  int v60; // [rsp+19Ch] [rbp-19Ch]
  int v61; // [rsp+1A0h] [rbp-198h]
  void **v62; // [rsp+1E0h] [rbp-158h] BYREF
  __int128 v63; // [rsp+1E8h] [rbp-150h]
  int v64; // [rsp+1F8h] [rbp-140h]
  int v65; // [rsp+1FCh] [rbp-13Ch]
  int v66; // [rsp+200h] [rbp-138h]
  void **v67; // [rsp+240h] [rbp-F8h] BYREF
  __int128 v68; // [rsp+248h] [rbp-F0h]
  int v69; // [rsp+258h] [rbp-E0h]
  int v70; // [rsp+25Ch] [rbp-DCh]
  int v71; // [rsp+260h] [rbp-D8h]
  void **v72; // [rsp+2A0h] [rbp-98h] BYREF
  __int128 v73; // [rsp+2A8h] [rbp-90h]
  int v74; // [rsp+2B8h] [rbp-80h]
  int v75; // [rsp+2BCh] [rbp-7Ch]
  int v76; // [rsp+2C0h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]
  __int64 v81; // [rsp+358h] [rbp+20h] BYREF

  LODWORD(v81) = 0;
  hObject = 0;
  v4 = wil::open_current_access_token_nothrow(&hObject);
  try
  {
    if ( v4 < 0 )
    {
      v43 = 0;
      pExceptionObject = &ComError::`vftable';
      v44 = v4;
      v45 = 1135;
      v46 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v5 = (volatile signed __int32 *)operator new(0x10u);
    v37 = (void *)v5;
    *((_DWORD *)v5 + 2) = 1;
    *(_QWORD *)v5 = 0;
    v6 = -1;
    v40 = -1;
    TokenHandle[0] = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) || GetLastError() == 1008 )
    {
      if ( SetThreadToken(0, 0) )
      {
        v6 = (__int64)TokenHandle[0];
        v40 = (__int64)TokenHandle[0];
        v10 = 0;
LABEL_11:
        if ( v10 < 0 )
        {
          v48 = 0;
          v47 = &ComError::`vftable';
          v49 = v10;
          v50 = 1142;
          v51 = 1;
          throw (ComError *)&v47;
        }
        v11 = operator new(0x10u);
        v38 = (__int64)v11;
        *((_DWORD *)v11 + 2) = 1;
        *(_QWORD *)v11 = 0;
        v39 = 0;
        v12 = UMgrQueryUserContext(hObject, &v39);
        if ( v12 < 0 )
        {
          v53 = 0;
          v52 = &ComError::`vftable';
          v54 = v12;
          v55 = 1146;
          v56 = 1;
          throw (ComError *)&v52;
        }
        if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(*(HANDLE *)v11);
        *(_QWORD *)v11 = 0;
        UserToken = UMgrQueryUserToken(v39, v11);
        if ( UserToken < 0 )
        {
          v58 = 0;
          v57 = &ComError::`vftable';
          v59 = UserToken;
          v60 = 1147;
          v61 = 1;
          throw (ComError *)&v57;
        }
        v14 = (void ***)TokenHandle::copyEx(&v38, TokenHandle, 2, 2);
        v15 = **v14;
        if ( *(void **)v5 != v15 )
        {
          if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
          {
            if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              CloseHandle(*(HANDLE *)v5);
              *(_QWORD *)v5 = 0;
            }
            operator delete((void *)v5, 0x10u);
          }
          v5 = (volatile signed __int32 *)*v14;
          v37 = (void *)v5;
          _InterlockedAdd(v5 + 2, 1u);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)TokenHandle[0] + 2, 0xFFFFFFFF) == 1 )
        {
          v16 = TokenHandle[0];
          if ( (unsigned __int64)(*(_QWORD *)TokenHandle[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)TokenHandle[0]);
            *(_QWORD *)TokenHandle[0] = 0;
            v16 = TokenHandle[0];
          }
          operator delete(v16, 0x10u);
        }
        if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v18 = v81;
        }
        else
        {
          Sid = (_QWORD *)TokenHandle::GetSid(&v37, TokenHandle);
          v18 = 1;
          WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, *Sid);
          v5 = (volatile signed __int32 *)v37;
        }
        if ( (v18 & 1) != 0 )
          SidHandle::~SidHandle((SidHandle *)TokenHandle);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) == 1 )
        {
          if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v11);
            *(_QWORD *)v11 = 0;
          }
          operator delete(v11, 0x10u);
        }
        if ( v6 != -1 )
          wil::details::RevertImpersonateToken((HANDLE)v6, v15);
        v19 = -1;
        v38 = -1;
        v20 = *(HANDLE *)v5;
        TokenHandle[0] = 0;
        v21 = GetCurrentThread();
        if ( OpenThreadToken(v21, 0xF01FFu, 1, TokenHandle) || GetLastError() == 1008 )
        {
          if ( SetThreadToken(0, v20) )
          {
            v19 = (__int64)TokenHandle[0];
            v38 = (__int64)TokenHandle[0];
            LastError = 0;
            goto LABEL_48;
          }
          v23 = 454;
        }
        else
        {
          v23 = 450;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v23,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                      v22);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
LABEL_48:
        if ( LastError < 0 )
        {
          v63 = 0;
          v62 = &ComError::`vftable';
          v64 = LastError;
          v65 = 1157;
          v66 = 1;
          throw (ComError *)&v62;
        }
        LODWORD(v81) = 0;
        v25 = QueryStorageAccess_FullTrustCaller_ForToken(hObject, a1, &v81);
        if ( v25 < 0 )
        {
          v68 = 0;
          v67 = &ComError::`vftable';
          v69 = v25;
          v70 = 1160;
          v71 = 1;
          throw (ComError *)&v67;
        }
        if ( !(_DWORD)v81 )
        {
          v73 = 0;
          v72 = &ComError::`vftable';
          v74 = -2147024891;
          v75 = 1167;
          v76 = 1;
          throw (ComError *)&v72;
        }
        v26 = *(_QWORD *)(a2 + 56);
        if ( !v26 )
          std::_Xbad_function_call();
        v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( v19 != -1 )
          wil::details::RevertImpersonateToken((HANDLE)v19, v27);
        if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
        {
          if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v5);
            *(_QWORD *)v5 = 0;
          }
          operator delete((void *)v5, 0x10u);
        }
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v29 = *(_QWORD *)(a2 + 56);
        if ( v29 )
        {
          LOBYTE(v27) = v29 != a2;
          (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v29 + 32LL))(v29, v27);
          *(_QWORD *)(a2 + 56) = 0;
        }
        v30 = *(_QWORD *)(a3 + 56);
        if ( v30 )
        {
          LOBYTE(v27) = v30 != a3;
          (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v30 + 32LL))(v30, v27);
          *(_QWORD *)(a3 + 56) = 0;
        }
        return v28;
      }
      v9 = 454;
    }
    else
    {
      v9 = 450;
    }
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v9,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
            v8);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
    goto LABEL_11;
  }
  catch ( const ComError *v41 )
  {
    if ( !*(_QWORD *)(a3 + 56) )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v81 = (*(__int64 (__fastcall **)(_QWORD, const ComError *))(**(_QWORD **)(a3 + 56) + 16LL))(
            *(_QWORD *)(a3 + 56),
            v41);
    v32 = *(_QWORD *)(a2 + 56);
    if ( v32 )
    {
      LOBYTE(v33) = v32 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 32LL))(v32, v33);
      *(_QWORD *)(a2 + 56) = 0;
    }
    v34 = *(_QWORD *)(a3 + 56);
    if ( v34 )
    {
      LOBYTE(v33) = v34 != a3;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 32LL))(v34, v33);
      *(_QWORD *)(a3 + 56) = 0;
    }
    return v81;
  }
  return result;
}

```

## disassembly

```asm
0x18001249c  mov     [rsp+arg_10], r8
0x1800124a1  mov     [rsp+arg_8], rdx
0x1800124a6  mov     [rsp+arg_0], rcx
0x1800124ab  push    rbx
0x1800124ac  push    rsi
0x1800124ad  push    rdi
0x1800124ae  push    r12
0x1800124b0  push    r13
0x1800124b2  push    r14
0x1800124b4  push    r15
0x1800124b6  sub     rsp, 300h
0x1800124bd  mov     r13, rdx
0x1800124c0  xor     r14d, r14d
0x1800124c3  mov     dword ptr [rsp+338h+arg_18], r14d
0x1800124cb  mov     [rsp+338h+hObject], r14
0x1800124d0  lea     rcx, [rsp+338h+hObject]
0x1800124d5  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x1800124da  test    eax, eax
0x1800124dc  jns     short loc_18001251B
0x1800124de  xorps   xmm0, xmm0
0x1800124e1  movups  [rsp+338h+var_2D0], xmm0
0x1800124e6  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800124ed  mov     [rsp+338h+pExceptionObject], rcx
0x1800124f2  mov     [rsp+338h+var_2C0], eax
0x1800124f6  mov     [rsp+338h+var_2BC], 46Fh
0x1800124fe  lea     r15d, [r14+1]
0x180012502  mov     [rsp+338h+var_2B8], r15d
0x18001250a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012511  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x180012516  call    _CxxThrowException_0
0x18001251b  mov     r12d, 10h
0x180012521  mov     ecx, r12d; dwBytes
0x180012524  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012529  mov     rbx, rax
0x18001252c  mov     [rsp+338h+var_300], rax
0x180012531  lea     r15d, [r12-0Fh]
0x180012536  mov     [rax+8], r15d
0x18001253a  mov     [rax], r14
0x18001253d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012541  mov     [rsp+338h+var_2E8], rsi
0x180012546  mov     [rsp+338h+TokenHandle], r14
0x18001254b  call    cs:__imp_GetCurrentThread
0x180012551  lea     r9, [rsp+338h+TokenHandle]; TokenHandle
0x180012556  mov     r8d, r15d; OpenAsSelf
0x180012559  mov     edx, 0F01FFh; DesiredAccess
0x18001255e  mov     rcx, rax; ThreadHandle
0x180012561  call    cs:__imp_OpenThreadToken
0x180012567  test    eax, eax
0x180012569  jnz     short loc_18001259F
0x18001256b  call    cs:__imp_GetLastError
0x180012571  cmp     eax, 3F0h
0x180012576  jz      short loc_18001259F
0x180012578  mov     edx, 1C2h; void *
0x18001257d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012584  mov     rcx, [rsp+338h]; this
0x18001258c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012591  mov     edi, eax
0x180012593  lea     rcx, [rsp+338h+TokenHandle]
0x180012598  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001259d  jmp     short loc_1800125C1
0x18001259f  xor     edx, edx; Token
0x1800125a1  xor     ecx, ecx; Thread
0x1800125a3  call    cs:__imp_SetThreadToken
0x1800125a9  test    eax, eax
0x1800125ab  jnz     short loc_1800125B4
0x1800125ad  mov     edx, 1C6h
0x1800125b2  jmp     short loc_18001257D
0x1800125b4  mov     rsi, [rsp+338h+TokenHandle]
0x1800125b9  mov     [rsp+338h+var_2E8], rsi
0x1800125be  mov     edi, r14d
0x1800125c1  test    edi, edi
0x1800125c3  jns     short loc_18001260D
0x1800125c5  xorps   xmm0, xmm0
0x1800125c8  movups  [rsp+338h+var_270], xmm0
0x1800125d0  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800125d7  mov     [rsp+338h+var_278], rcx
0x1800125df  mov     [rsp+338h+var_260], edi
0x1800125e6  mov     [rsp+338h+var_25C], 476h
0x1800125f1  mov     [rsp+338h+var_258], r15d
0x1800125f9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012600  lea     rcx, [rsp+338h+var_278]; pExceptionObject
0x180012608  call    _CxxThrowException_0
0x18001260d  mov     rcx, r12; dwBytes
0x180012610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012615  mov     rdi, rax
0x180012618  mov     [rsp+338h+var_2F8], rax
0x18001261d  mov     [rax+8], r15d
0x180012621  mov     [rax], r14
0x180012624  mov     [rsp+338h+var_2F0], r14
0x180012629  lea     rdx, [rsp+338h+var_2F0]
0x18001262e  mov     rcx, [rsp+338h+hObject]
0x180012633  call    cs:__imp_UMgrQueryUserContext
0x180012639  test    eax, eax
0x18001263b  jns     short loc_180012685
0x18001263d  xorps   xmm0, xmm0
0x180012640  movups  [rsp+338h+var_210], xmm0
0x180012648  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001264f  mov     [rsp+338h+var_218], rcx
0x180012657  mov     [rsp+338h+var_200], eax
0x18001265e  mov     [rsp+338h+var_1FC], 47Ah
0x180012669  mov     [rsp+338h+var_1F8], r15d
0x180012671  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012678  lea     rcx, [rsp+338h+var_218]; pExceptionObject
0x180012680  call    _CxxThrowException_0
0x180012685  mov     rcx, [rdi]; hObject
0x180012688  lea     rax, [rcx-1]
0x18001268c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012690  ja      short loc_180012698
0x180012692  call    cs:__imp_CloseHandle
0x180012698  mov     [rdi], r14
0x18001269b  mov     rdx, rdi
0x18001269e  mov     rcx, [rsp+338h+var_2F0]
0x1800126a3  call    cs:__imp_UMgrQueryUserToken
0x1800126a9  test    eax, eax
0x1800126ab  jns     short loc_1800126F5
0x1800126ad  xorps   xmm0, xmm0
0x1800126b0  movups  [rsp+338h+var_1B0], xmm0
0x1800126b8  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800126bf  mov     [rsp+338h+var_1B8], rcx
0x1800126c7  mov     [rsp+338h+var_1A0], eax
0x1800126ce  mov     [rsp+338h+var_19C], 47Bh
0x1800126d9  mov     [rsp+338h+var_198], r15d
0x1800126e1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800126e8  lea     rcx, [rsp+338h+var_1B8]; pExceptionObject
0x1800126f0  call    _CxxThrowException_0
0x1800126f5  mov     r8d, 2
0x1800126fb  mov     r9d, r8d
0x1800126fe  lea     rdx, [rsp+338h+TokenHandle]
0x180012703  lea     rcx, [rsp+338h+var_2F8]
0x180012708  call    ?copyEx@TokenHandle@@QEBA?AV1@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; TokenHandle::copyEx(_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x18001270d  mov     r12, rax
0x180012710  mov     rcx, [rax]
0x180012713  mov     rdx, [rcx]
0x180012716  cmp     [rbx], rdx
0x180012719  jz      short loc_180012759
0x18001271b  or      ecx, 0FFFFFFFFh
0x18001271e  lock xadd [rbx+8], ecx
0x180012723  cmp     ecx, 1
0x180012726  jnz     short loc_18001274B
0x180012728  mov     rcx, [rbx]; hObject
0x18001272b  lea     rax, [rcx-1]
0x18001272f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012733  ja      short loc_18001273E
0x180012735  call    cs:__imp_CloseHandle
0x18001273b  mov     [rbx], r14
0x18001273e  mov     edx, 10h; unsigned __int64
0x180012743  mov     rcx, rbx; void *
0x180012746  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001274b  mov     rbx, [r12]
0x18001274f  mov     [rsp+338h+var_300], rbx
0x180012754  lock add [rbx+8], r15d
0x180012759  mov     rcx, [rsp+338h+TokenHandle]
0x18001275e  or      eax, 0FFFFFFFFh
0x180012761  lock xadd [rcx+8], eax
0x180012766  cmp     eax, 1
0x180012769  jnz     short loc_18001279D
0x18001276b  mov     rcx, [rsp+338h+TokenHandle]
0x180012770  mov     rdx, [rcx]
0x180012773  lea     rax, [rdx-1]
0x180012777  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001277b  ja      short loc_180012793
0x18001277d  mov     rcx, rdx; hObject
0x180012780  call    cs:__imp_CloseHandle
0x180012786  mov     rax, [rsp+338h+TokenHandle]
0x18001278b  mov     [rax], r14
0x18001278e  mov     rcx, [rsp+338h+TokenHandle]; void *
0x180012793  mov     edx, 10h; unsigned __int64
0x180012798  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001279d  lea     rcx, WPP_GLOBAL_Control
0x1800127a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800127ab  cmp     rax, rcx
0x1800127ae  jz      short loc_1800127EE
0x1800127b0  test    [rax+1Ch], r15b
0x1800127b4  jz      short loc_1800127EE
0x1800127b6  lea     rdx, [rsp+338h+TokenHandle]
0x1800127bb  lea     rcx, [rsp+338h+var_300]
0x1800127c0  call    ?GetSid@TokenHandle@@QEBA?AVSidHandle@@XZ; TokenHandle::GetSid(void)
0x1800127c5  mov     r12d, r15d
0x1800127c8  mov     edx, 24h ; '$'
0x1800127cd  mov     r9, [rax]
0x1800127d0  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x1800127d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127de  mov     rcx, [rcx+10h]
0x1800127e2  call    WPP_SF__sid_
0x1800127e7  mov     rbx, [rsp+338h+var_300]
0x1800127ec  jmp     short loc_1800127F6
0x1800127ee  mov     r12d, dword ptr [rsp+338h+arg_18]
0x1800127f6  test    r15b, r12b
0x1800127f9  jz      short loc_180012806
0x1800127fb  lea     rcx, [rsp+338h+TokenHandle]; this
0x180012800  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x180012805  nop
0x180012806  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001280a  mov     eax, r12d
0x18001280d  lock xadd [rdi+8], eax
0x180012812  add     eax, r12d
0x180012815  jnz     short loc_18001283B
0x180012817  mov     rcx, [rdi]; hObject
0x18001281a  lea     rax, [rcx-1]
0x18001281e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012822  ja      short loc_18001282D
0x180012824  call    cs:__imp_CloseHandle
0x18001282a  mov     [rdi], r14
0x18001282d  mov     edx, 10h; unsigned __int64
0x180012832  mov     rcx, rdi; void *
0x180012835  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001283a  nop
0x18001283b  cmp     rsi, r12
0x18001283e  jz      short loc_180012848
0x180012840  mov     rcx, rsi; Token
0x180012843  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180012848  mov     rdi, r12
0x18001284b  mov     [rsp+338h+var_2F8], r12
0x180012850  mov     rsi, [rbx]
0x180012853  mov     [rsp+338h+TokenHandle], r14
0x180012858  call    cs:__imp_GetCurrentThread
0x18001285e  lea     r9, [rsp+338h+TokenHandle]; TokenHandle
0x180012863  mov     r8d, r15d; OpenAsSelf
0x180012866  mov     edx, 0F01FFh; DesiredAccess
0x18001286b  mov     rcx, rax; ThreadHandle
0x18001286e  call    cs:__imp_OpenThreadToken
0x180012874  test    eax, eax
0x180012876  jnz     short loc_1800128AC
0x180012878  call    cs:__imp_GetLastError
0x18001287e  cmp     eax, 3F0h
0x180012883  jz      short loc_1800128AC
0x180012885  mov     edx, 1C2h; void *
0x18001288a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012891  mov     rcx, [rsp+338h]; this
0x180012899  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001289e  mov     esi, eax
0x1800128a0  lea     rcx, [rsp+338h+TokenHandle]
0x1800128a5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800128aa  jmp     short loc_1800128CF
0x1800128ac  mov     rdx, rsi; Token
0x1800128af  xor     ecx, ecx; Thread
0x1800128b1  call    cs:__imp_SetThreadToken
0x1800128b7  test    eax, eax
0x1800128b9  jnz     short loc_1800128C2
0x1800128bb  mov     edx, 1C6h
0x1800128c0  jmp     short loc_18001288A
0x1800128c2  mov     rdi, [rsp+338h+TokenHandle]
0x1800128c7  mov     [rsp+338h+var_2F8], rdi
0x1800128cc  mov     esi, r14d
0x1800128cf  test    esi, esi
0x1800128d1  jns     short loc_18001291B
0x1800128d3  xorps   xmm0, xmm0
0x1800128d6  movups  [rsp+338h+var_150], xmm0
0x1800128de  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800128e5  mov     [rsp+338h+var_158], rcx
0x1800128ed  mov     [rsp+338h+var_140], esi
0x1800128f4  mov     [rsp+338h+var_13C], 485h
0x1800128ff  mov     [rsp+338h+var_138], r15d
0x180012907  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001290e  lea     rcx, [rsp+338h+var_158]; pExceptionObject
0x180012916  call    _CxxThrowException_0
0x18001291b  mov     dword ptr [rsp+338h+arg_18], r14d
0x180012923  lea     r8, [rsp+338h+arg_18]
0x18001292b  mov     rdx, [rsp+338h+arg_0]
0x180012933  mov     rcx, [rsp+338h+hObject]
0x180012938  call    cs:__imp_QueryStorageAccess_FullTrustCaller_ForToken
0x18001293e  test    eax, eax
0x180012940  jns     short loc_18001298A
0x180012942  xorps   xmm0, xmm0
0x180012945  movups  [rsp+338h+var_F0], xmm0
0x18001294d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180012954  mov     [rsp+338h+var_F8], rcx
0x18001295c  mov     [rsp+338h+var_E0], eax
0x180012963  mov     [rsp+338h+var_DC], 488h
0x18001296e  mov     [rsp+338h+var_D8], r15d
0x180012976  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001297d  lea     rcx, [rsp+338h+var_F8]; pExceptionObject
0x180012985  call    _CxxThrowException_0
0x18001298a  cmp     dword ptr [rsp+338h+arg_18], r14d
0x180012992  jz      loc_180012A59
0x180012998  mov     rcx, [r13+38h]
0x18001299c  test    rcx, rcx
0x18001299f  jnz     short loc_1800129A7
0x1800129a1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800129a7  mov     rax, [rcx]
0x1800129aa  mov     rax, [rax+10h]
0x1800129ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b3  mov     rsi, rax
0x1800129b6  cmp     rdi, r12
0x1800129b9  jz      short loc_1800129C4
0x1800129bb  mov     rcx, rdi; Token
0x1800129be  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800129c3  nop
0x1800129c4  mov     ecx, r12d
0x1800129c7  lock xadd [rbx+8], ecx
0x1800129cc  add     ecx, r12d
0x1800129cf  jnz     short loc_1800129F5
0x1800129d1  mov     rcx, [rbx]; hObject
0x1800129d4  lea     rax, [rcx-1]
0x1800129d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800129dc  ja      short loc_1800129E7
0x1800129de  call    cs:__imp_CloseHandle
0x1800129e4  mov     [rbx], r14
0x1800129e7  mov     edx, 10h; unsigned __int64
0x1800129ec  mov     rcx, rbx; void *
  ... truncated ...
```
