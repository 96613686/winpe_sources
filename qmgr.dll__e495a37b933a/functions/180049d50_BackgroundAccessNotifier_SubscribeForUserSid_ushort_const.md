# BackgroundAccessNotifier::SubscribeForUserSid(ushort const *)

- ea: `0x180049d50`
- end: `0x18004a54c`
- name: `?SubscribeForUserSid@BackgroundAccessNotifier@@QEAAJPEBG@Z`
- size: `2044`
- prototype: `__int64 __fastcall(BackgroundAccessNotifier *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004926c`
- `0x1800b3390`

## callees

- `0x180006640`
- `0x18000db20`
- `0x18002c6ac`
- `0x180035f70`
- `0x180049d50`
- `0x1800634e0`
- `0x18008fadc`
- `0x1800961b8`
- `0x180099740`
- `0x18009ab6c`
- `0x18009d024`
- `0x1800a1114`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800b2044`
- `0x1800b27e4`
- `0x1800b4d44`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004a4a7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004a4a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a4d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a4d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180049e67`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180049e67`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004a1be`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004a3d4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004a1be`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004a3d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall BackgroundAccessNotifier::SubscribeForUserSid(
        BackgroundAccessNotifier *this,
        const unsigned __int16 *a2)
{
  BackgroundAccessNotifier *v5; // rcx
  unsigned int LastError; // eax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  struct IBackgroundAccessManagerFactory *v10; // rdi
  __int64 (__fastcall *v11)(struct IBackgroundAccessManagerFactory *, const unsigned __int16 *, _QWORD, GUID *, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  __int64 *v16; // r14
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 inserted; // rdi
  __int64 v20; // rbx
  const wchar_t *v21; // rcx
  size_t v22; // r14
  const wchar_t *v23; // rdx
  size_t v24; // r15
  size_t v25; // r8
  int v26; // eax
  const wchar_t *v27; // rdx
  size_t v28; // rbx
  size_t v29; // r14
  const wchar_t *v30; // rcx
  size_t v31; // r8
  int v32; // eax
  _QWORD *v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rbx
  unsigned int v36; // r15d
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdi
  __int64 v40; // rbx
  const wchar_t *v41; // rcx
  size_t v42; // rsi
  const wchar_t *v43; // rdx
  size_t v44; // r14
  size_t v45; // r8
  int v46; // eax
  const wchar_t *v47; // rdx
  size_t v48; // rbx
  size_t v49; // rsi
  const wchar_t *v50; // rcx
  size_t v51; // r8
  int v52; // eax
  _QWORD *v53; // rax
  __int64 v54; // rbx
  __int64 v55; // rcx
  void *v56; // rcx
  struct IBackgroundAccessManagerFactory *v57; // rcx
  const ComError *v58; // rbx
  unsigned int v59; // [rsp+30h] [rbp-208h] BYREF
  struct IBackgroundAccessManagerFactory *v60; // [rsp+38h] [rbp-200h] BYREF
  __int64 v61; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 *v62; // [rsp+48h] [rbp-1F0h]
  void *v63; // [rsp+50h] [rbp-1E8h] BYREF
  __int128 v64; // [rsp+60h] [rbp-1D8h] BYREF
  __int128 v65; // [rsp+70h] [rbp-1C8h]
  const ComError *v66; // [rsp+88h] [rbp-1B0h] BYREF
  _QWORD v67[2]; // [rsp+90h] [rbp-1A8h] BYREF
  void **pExceptionObject; // [rsp+A0h] [rbp-198h] BYREF
  __int128 v69; // [rsp+A8h] [rbp-190h]
  unsigned int v70; // [rsp+B8h] [rbp-180h]
  int v71; // [rsp+BCh] [rbp-17Ch]
  int v72; // [rsp+C0h] [rbp-178h]
  void **v73; // [rsp+100h] [rbp-138h] BYREF
  __int128 v74; // [rsp+108h] [rbp-130h]
  int v75; // [rsp+118h] [rbp-120h]
  int v76; // [rsp+11Ch] [rbp-11Ch]
  int v77; // [rsp+120h] [rbp-118h]
  void **v78; // [rsp+160h] [rbp-D8h] BYREF
  __int128 v79; // [rsp+168h] [rbp-D0h]
  int v80; // [rsp+178h] [rbp-C0h]
  int v81; // [rsp+17Ch] [rbp-BCh]
  int v82; // [rsp+180h] [rbp-B8h]
  wchar_t *S2[2]; // [rsp+1C0h] [rbp-78h] BYREF
  size_t N; // [rsp+1D0h] [rbp-68h]
  unsigned __int64 v85; // [rsp+1D8h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+1E0h] [rbp-58h] BYREF
  size_t v87; // [rsp+1F0h] [rbp-48h]
  unsigned __int64 v88; // [rsp+1F8h] [rbp-40h]

  if ( !(*(unsigned __int8 (__fastcall **)(BackgroundAccessNotifier *))(*(_QWORD *)this + 16LL))(this) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
    return 0;
  }
  v60 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  BackgroundAccessNotifier::TryGetBackgroundAccessManagerFactory(v5, &v60);
  if ( !v60 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids, a2);
  try
  {
    CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v63);
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v69 = 0;
      pExceptionObject = &ComError::`vftable';
      v70 = LastError;
      v71 = 2024;
      v72 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( !*((_QWORD *)this + 3) )
    {
      v7 = operator new(0x18u);
      v8 = v7;
      if ( v7 )
      {
        v7[2] = 1;
        *v7 = &BackgroundAccessStateChangeImpl::`vftable'{for `IBackgroundAccessStateChangeHandler'};
        v7[1] = &BackgroundAccessStateChangeImpl::`vftable'{for `RefCountedObject'};
      }
      else
      {
        v8 = 0;
      }
      v9 = *((_QWORD *)this + 3);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 3) = v8;
      CEvent::Clear((BackgroundAccessNotifier *)((char *)this + 16));
    }
    v59 = 0;
    v61 = 0;
    v10 = v60;
    v11 = *(__int64 (__fastcall **)(struct IBackgroundAccessManagerFactory *, const unsigned __int16 *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v60 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v12 = v11(v10, a2, 0, &GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b, &v61);
    if ( v12 < 0 )
    {
      v74 = 0;
      v73 = &ComError::`vftable';
      v75 = v12;
      v76 = 2039;
      v77 = 1;
      throw (ComError *)&v73;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v61 + 152LL))(
            v61,
            *((_QWORD *)this + 3),
            &v59);
    if ( v13 < 0 )
    {
      v79 = 0;
      v78 = &ComError::`vftable';
      v80 = v13;
      v81 = 2045;
      v82 = 1;
      throw (ComError *)&v78;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (_DWORD)a2, v59);
    v16 = (__int64 *)((char *)this + 32);
    v62 = v16;
    *(_OWORD *)S2 = 0;
    N = 0;
    v85 = 0;
    v17 = -1;
    do
      ++v17;
    while ( a2[v17] );
    std::wstring::_Construct<1,unsigned short const *>(S2, a2);
    inserted = *v16;
    v20 = *(_QWORD *)(*v16 + 8);
    v65 = (unsigned __int64)v20;
    if ( !*(_BYTE *)(v20 + 25) )
    {
      while ( 1 )
      {
        *(_QWORD *)&v65 = v20;
        v21 = (const wchar_t *)(v20 + 32);
        v22 = N;
        v23 = (const wchar_t *)S2;
        if ( v85 > 7 )
          v23 = S2[0];
        v24 = *(_QWORD *)(v20 + 48);
        if ( *(_QWORD *)(v20 + 56) > 7u )
          v21 = *(const wchar_t **)v21;
        v25 = N;
        if ( N >= v24 )
          v25 = *(_QWORD *)(v20 + 48);
        v26 = wmemcmp(v21, v23, v25);
        if ( v26 )
        {
          if ( v26 < 0 )
            goto LABEL_63;
        }
        else if ( v24 < v22 )
        {
LABEL_63:
          DWORD2(v65) = 0;
          v20 += 16;
          goto LABEL_48;
        }
        DWORD2(v65) = 1;
        inserted = v20;
LABEL_48:
        v20 = *(_QWORD *)v20;
        if ( *(_BYTE *)(v20 + 25) )
        {
          v16 = v62;
          break;
        }
      }
    }
    if ( *(_BYTE *)(inserted + 25) )
      goto LABEL_60;
    v27 = (const wchar_t *)(inserted + 32);
    v28 = *(_QWORD *)(inserted + 48);
    if ( *(_QWORD *)(inserted + 56) > 7u )
      v27 = *(const wchar_t **)v27;
    v29 = N;
    v30 = (const wchar_t *)S2;
    if ( v85 > 7 )
      v30 = S2[0];
    v31 = *(_QWORD *)(inserted + 48);
    if ( v28 >= N )
      v31 = N;
    v32 = wmemcmp(v30, v27, v31);
    if ( v32 )
    {
      if ( v32 < 0 )
      {
LABEL_59:
        v16 = v62;
LABEL_60:
        if ( v16[1] == 0x333333333333333LL )
          std::_Xlength_error("map/set too long");
        *(_QWORD *)&v64 = S2;
        v33 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>(
                v67,
                (__int64)v16,
                *v16,
                v18,
                &v64);
        v34 = v33[1];
        v33[1] = 0;
        std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>((__int64)v67);
        v64 = v65;
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
                     v16,
                     &v64,
                     v34);
LABEL_67:
        v35 = v61;
        if ( *(_QWORD *)(inserted + 72) != v61 )
        {
          if ( v61 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 8LL))(v61);
          *(_QWORD *)&v64 = *(_QWORD *)(inserted + 72);
          *(_QWORD *)(inserted + 72) = v35;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
        }
        if ( v85 > 7 )
          std::_Deallocate<16>(S2[0], 2 * v85 + 2);
        v36 = v59;
        *(_OWORD *)S1 = 0;
        v87 = 0;
        v88 = 0;
        v37 = -1;
        do
          ++v37;
        while ( a2[v37] );
        std::wstring::_Construct<1,unsigned short const *>(S1, a2);
        v39 = *v16;
        v40 = *(_QWORD *)(*v16 + 8);
        v65 = (unsigned __int64)v40;
        if ( !*(_BYTE *)(v40 + 25) )
        {
          while ( 1 )
          {
            *(_QWORD *)&v65 = v40;
            v41 = (const wchar_t *)(v40 + 32);
            v42 = v87;
            v43 = (const wchar_t *)S1;
            if ( v88 > 7 )
              v43 = S1[0];
            v44 = *(_QWORD *)(v40 + 48);
            if ( *(_QWORD *)(v40 + 56) > 7u )
              v41 = *(const wchar_t **)v41;
            v45 = v87;
            if ( v87 >= v44 )
              v45 = *(_QWORD *)(v40 + 48);
            v46 = wmemcmp(v41, v43, v45);
            if ( v46 )
            {
              if ( v46 < 0 )
                goto LABEL_99;
            }
            else if ( v44 < v42 )
            {
LABEL_99:
              DWORD2(v65) = 0;
              v40 += 16;
              goto LABEL_85;
            }
            DWORD2(v65) = 1;
            v39 = v40;
LABEL_85:
            v40 = *(_QWORD *)v40;
            if ( *(_BYTE *)(v40 + 25) )
            {
              v16 = v62;
              break;
            }
          }
        }
        if ( *(_BYTE *)(v39 + 25) )
          goto LABEL_96;
        v47 = (const wchar_t *)(v39 + 32);
        v48 = *(_QWORD *)(v39 + 48);
        if ( *(_QWORD *)(v39 + 56) > 7u )
          v47 = *(const wchar_t **)v47;
        v49 = v87;
        v50 = (const wchar_t *)S1;
        if ( v88 > 7 )
          v50 = S1[0];
        v51 = *(_QWORD *)(v39 + 48);
        if ( v48 >= v87 )
          v51 = v87;
        v52 = wmemcmp(v50, v47, v51);
        if ( v52 )
        {
          if ( v52 < 0 )
          {
LABEL_96:
            if ( v16[1] == 0x333333333333333LL )
              std::_Xlength_error("map/set too long");
            *(_QWORD *)&v64 = S1;
            v53 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>(
                    v67,
                    (__int64)v16,
                    *v16,
                    v38,
                    &v64);
            v54 = v53[1];
            v53[1] = 0;
            std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>((__int64)v67);
            v64 = v65;
            v39 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
                    v16,
                    &v64,
                    v54);
          }
        }
        else if ( v49 < v48 )
        {
          goto LABEL_96;
        }
        *(_DWORD *)(v39 + 64) = v36;
        if ( v88 > 7 )
          std::_Deallocate<16>(S1[0], 2 * v88 + 2);
        v55 = v61;
        if ( v61 )
        {
          v61 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
        }
        SetThreadToken(0, *(HANDLE *)v63);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v63 + 2, 0xFFFFFFFF) == 1 )
        {
          v56 = v63;
          if ( (unsigned __int64)(*(_QWORD *)v63 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v63);
            *(_QWORD *)v63 = 0;
            v56 = v63;
          }
          operator delete(v56, 0x10u);
        }
        goto LABEL_122;
      }
    }
    else if ( v29 < v28 )
    {
      goto LABEL_59;
    }
    v16 = v62;
    goto LABEL_67;
  }
  catch ( const ComError *v66 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v58 = v66;
    }
    else
    {
      v58 = v66;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids,
        *((unsigned int *)v66 + 6),
        *((_DWORD *)v66 + 7));
    }
    v59 = *((_DWORD *)v58 + 6);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
    return v59;
  }
LABEL_122:
  v57 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(struct IBackgroundAccessManagerFactory *))(*(_QWORD *)v57 + 16LL))(v57);
  }
  return 0;
}

```

## disassembly

```asm
0x180049d50  mov     [rsp+arg_10], rbx
0x180049d55  mov     [rsp+arg_18], rsi
0x180049d5a  push    rdi
0x180049d5b  push    r12
0x180049d5d  push    r13
0x180049d5f  push    r14
0x180049d61  push    r15
0x180049d63  sub     rsp, 210h
0x180049d6a  mov     rax, cs:__security_cookie
0x180049d71  xor     rax, rsp
0x180049d74  mov     [rsp+238h+var_38], rax
0x180049d7c  mov     rsi, rdx
0x180049d7f  mov     r14, rcx
0x180049d82  mov     rax, [rcx]
0x180049d85  mov     rax, [rax+10h]
0x180049d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d8e  test    al, al
0x180049d90  jnz     short loc_180049DC7
0x180049d92  lea     r15, WPP_GLOBAL_Control
0x180049d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180049da0  cmp     rcx, r15
0x180049da3  jz      short loc_180049DC0
0x180049da5  test    byte ptr [rcx+1Ch], 1
0x180049da9  jz      short loc_180049DC0
0x180049dab  mov     edx, 6Ch ; 'l'
0x180049db0  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x180049db7  mov     rcx, [rcx+10h]
0x180049dbb  call    WPP_SF_
0x180049dc0  xor     eax, eax
0x180049dc2  jmp     loc_18004A51F
0x180049dc7  xor     r13d, r13d
0x180049dca  mov     [rsp+238h+var_200], r13
0x180049dcf  lea     rcx, [rsp+238h+var_200]
0x180049dd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049dd9  lea     rdx, [rsp+238h+var_200]; struct IBackgroundAccessManagerFactory **
0x180049dde  call    ?TryGetBackgroundAccessManagerFactory@BackgroundAccessNotifier@@AEAAXPEAPEAUIBackgroundAccessManagerFactory@@@Z; BackgroundAccessNotifier::TryGetBackgroundAccessManagerFactory(IBackgroundAccessManagerFactory * *)
0x180049de3  cmp     [rsp+238h+var_200], r13
0x180049de8  jnz     short loc_180049E2A
0x180049dea  lea     r15, WPP_GLOBAL_Control
0x180049df1  mov     rcx, cs:WPP_GLOBAL_Control
0x180049df8  cmp     rcx, r15
0x180049dfb  jz      short loc_180049E19
0x180049dfd  test    byte ptr [rcx+1Ch], 1
0x180049e01  jz      short loc_180049E19
0x180049e03  mov     edx, 6Dh ; 'm'
0x180049e08  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x180049e0f  mov     rcx, [rcx+10h]
0x180049e13  call    WPP_SF_
0x180049e18  nop
0x180049e19  lea     rcx, [rsp+238h+var_200]
0x180049e1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049e23  xor     eax, eax
0x180049e25  jmp     loc_18004A51F
0x180049e2a  lea     r15, WPP_GLOBAL_Control
0x180049e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e38  cmp     rcx, r15
0x180049e3b  jz      short loc_180049E5C
0x180049e3d  test    byte ptr [rcx+1Ch], 1
0x180049e41  jz      short loc_180049E5C
0x180049e43  mov     edx, 6Eh ; 'n'
0x180049e48  mov     r9, rsi
0x180049e4b  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x180049e52  mov     rcx, [rcx+10h]
0x180049e56  call    WPP_SF_S
0x180049e5b  nop
0x180049e5c  lea     rcx, [rsp+238h+var_1E8]; this
0x180049e61  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x180049e66  nop
0x180049e67  call    cs:__imp_RevertToSelf
0x180049e6d  test    eax, eax
0x180049e6f  jnz     short loc_180049EDC
0x180049e71  call    cs:__imp_GetLastError
0x180049e77  test    eax, eax
0x180049e79  jg      short loc_180049E83
0x180049e7b  call    cs:__imp_GetLastError
0x180049e81  jmp     short loc_180049E91
0x180049e83  call    cs:__imp_GetLastError
0x180049e89  movzx   eax, ax
0x180049e8c  or      eax, 80070000h
0x180049e91  xorps   xmm0, xmm0
0x180049e94  movups  [rsp+238h+var_190], xmm0
0x180049e9c  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180049ea3  mov     [rsp+238h+pExceptionObject], rcx
0x180049eab  mov     [rsp+238h+var_180], eax
0x180049eb2  mov     [rsp+238h+var_17C], 7E8h
0x180049ebd  mov     [rsp+238h+var_178], 1
0x180049ec8  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180049ecf  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x180049ed7  call    _CxxThrowException_0
0x180049edc  cmp     qword ptr [r14+18h], 0
0x180049ee1  jnz     short loc_180049F39
0x180049ee3  mov     ecx, 18h; dwBytes
0x180049ee8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049eed  mov     rbx, rax
0x180049ef0  test    rax, rax
0x180049ef3  jz      short loc_180049F14
0x180049ef5  mov     qword ptr [rax+10h], 1
0x180049efd  lea     rax, ??_7BackgroundAccessStateChangeImpl@@6BIBackgroundAccessStateChangeHandler@@@; const BackgroundAccessStateChangeImpl::`vftable'{for `IBackgroundAccessStateChangeHandler'}
0x180049f04  mov     [rbx], rax
0x180049f07  lea     rax, ??_7BackgroundAccessStateChangeImpl@@6BRefCountedObject@@@; const BackgroundAccessStateChangeImpl::`vftable'{for `RefCountedObject'}
0x180049f0e  mov     [rbx+8], rax
0x180049f12  jmp     short loc_180049F17
0x180049f14  mov     rbx, r13
0x180049f17  mov     rcx, [r14+18h]
0x180049f1b  test    rcx, rcx
0x180049f1e  jz      short loc_180049F2C
0x180049f20  mov     rax, [rcx]
0x180049f23  mov     rax, [rax+10h]
0x180049f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f2c  mov     [r14+18h], rbx
0x180049f30  lea     rcx, [r14+10h]; this
0x180049f34  call    ?Clear@CEvent@@QEAAXXZ; CEvent::Clear(void)
0x180049f39  mov     [rsp+238h+var_208], r13d
0x180049f3e  mov     [rsp+238h+var_1F8], r13
0x180049f43  mov     rdi, [rsp+238h+var_200]
0x180049f48  mov     rax, [rdi]
0x180049f4b  mov     rbx, [rax+20h]
0x180049f4f  lea     rcx, [rsp+238h+var_1F8]
0x180049f54  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049f59  lea     rax, [rsp+238h+var_1F8]
0x180049f5e  mov     [rsp+238h+var_218], rax
0x180049f63  lea     r9, _GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b
0x180049f6a  xor     r8d, r8d
0x180049f6d  mov     rdx, rsi
0x180049f70  mov     rcx, rdi
0x180049f73  mov     rax, rbx
0x180049f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f7b  test    eax, eax
0x180049f7d  jns     short loc_180049FCA
0x180049f7f  xorps   xmm0, xmm0
0x180049f82  movups  [rsp+238h+var_130], xmm0
0x180049f8a  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180049f91  mov     [rsp+238h+var_138], rcx
0x180049f99  mov     [rsp+238h+var_120], eax
0x180049fa0  mov     [rsp+238h+var_11C], 7F7h
0x180049fab  mov     [rsp+238h+var_118], 1
0x180049fb6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180049fbd  lea     rcx, [rsp+238h+var_138]; pExceptionObject
0x180049fc5  call    _CxxThrowException_0
0x180049fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fd1  cmp     rcx, r15
0x180049fd4  jz      short loc_180049FF1
0x180049fd6  test    byte ptr [rcx+1Ch], 1
0x180049fda  jz      short loc_180049FF1
0x180049fdc  mov     edx, 6Fh ; 'o'
0x180049fe1  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x180049fe8  mov     rcx, [rcx+10h]
0x180049fec  call    WPP_SF_
0x180049ff1  mov     rcx, [rsp+238h+var_1F8]
0x180049ff6  mov     rax, [rcx]
0x180049ff9  lea     r8, [rsp+238h+var_208]
0x180049ffe  mov     rdx, [r14+18h]
0x18004a002  mov     rax, [rax+98h]
0x18004a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a00e  test    eax, eax
0x18004a010  jns     short loc_18004A05D
0x18004a012  xorps   xmm0, xmm0
0x18004a015  movups  [rsp+238h+var_D0], xmm0
0x18004a01d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004a024  mov     [rsp+238h+var_D8], rcx
0x18004a02c  mov     [rsp+238h+var_C0], eax
0x18004a033  mov     [rsp+238h+var_BC], 7FDh
0x18004a03e  mov     [rsp+238h+var_B8], 1
0x18004a049  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004a050  lea     rcx, [rsp+238h+var_D8]; pExceptionObject
0x18004a058  call    _CxxThrowException_0
0x18004a05d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a064  cmp     rcx, r15
0x18004a067  jz      short loc_18004A083
0x18004a069  test    byte ptr [rcx+1Ch], 1
0x18004a06d  jz      short loc_18004A083
0x18004a06f  mov     eax, [rsp+238h+var_208]
0x18004a073  mov     dword ptr [rsp+238h+var_218], eax
0x18004a077  mov     r9, rsi
0x18004a07a  mov     rcx, [rcx+10h]
0x18004a07e  call    WPP_SF_SL
0x18004a083  add     r14, 20h ; ' '
0x18004a087  mov     [rsp+238h+var_1F0], r14
0x18004a08c  xorps   xmm0, xmm0
0x18004a08f  movups  xmmword ptr [rsp+238h+S2], xmm0
0x18004a097  mov     [rsp+238h+N], r13
0x18004a09f  mov     [rsp+238h+var_60], r13
0x18004a0a7  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18004a0ae  mov     r8, r12
0x18004a0b1  inc     r8
0x18004a0b4  cmp     word ptr [rsi+r8*2], 0
0x18004a0ba  jnz     short loc_18004A0B1
0x18004a0bc  mov     rdx, rsi
0x18004a0bf  lea     rcx, [rsp+238h+S2]
0x18004a0c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004a0cc  nop
0x18004a0cd  mov     rdi, [r14]
0x18004a0d0  mov     rbx, [rdi+8]
0x18004a0d4  mov     qword ptr [rsp+238h+var_1C8], rbx
0x18004a0d9  mov     qword ptr [rsp+238h+var_1C8+8], r13
0x18004a0de  cmp     byte ptr [rbx+19h], 0
0x18004a0e2  jnz     short loc_18004A153
0x18004a0e4  mov     qword ptr [rsp+238h+var_1C8], rbx
0x18004a0e9  lea     rcx, [rbx+20h]
0x18004a0ed  mov     r14, [rsp+238h+N]
0x18004a0f5  lea     rdx, [rsp+238h+S2]
0x18004a0fd  cmp     [rsp+238h+var_60], 7
0x18004a106  cmova   rdx, [rsp+238h+S2]; S2
0x18004a10f  mov     r15, [rbx+30h]
0x18004a113  cmp     qword ptr [rcx+18h], 7
0x18004a118  jbe     short loc_18004A11D
0x18004a11a  mov     rcx, [rcx]; S1
0x18004a11d  mov     r8, r14
0x18004a120  cmp     r14, r15
0x18004a123  cmovnb  r8, r15; N
0x18004a127  call    wmemcmp
0x18004a12c  test    eax, eax
0x18004a12e  jz      loc_18004A1C4
0x18004a134  js      loc_18004A1CD
0x18004a13a  mov     dword ptr [rsp+238h+var_1C8+8], 1
0x18004a142  mov     rdi, rbx
0x18004a145  mov     rbx, [rbx]
0x18004a148  cmp     byte ptr [rbx+19h], 0
0x18004a14c  jz      short loc_18004A0E4
0x18004a14e  mov     r14, [rsp+238h+var_1F0]
0x18004a153  cmp     byte ptr [rdi+19h], 0
0x18004a157  jnz     short loc_18004A1A7
0x18004a159  lea     rdx, [rdi+20h]
0x18004a15d  mov     rbx, [rdx+10h]
0x18004a161  cmp     qword ptr [rdx+18h], 7
0x18004a166  jbe     short loc_18004A16B
0x18004a168  mov     rdx, [rdx]; S2
0x18004a16b  mov     r14, [rsp+238h+N]
0x18004a173  lea     rcx, [rsp+238h+S2]
0x18004a17b  cmp     [rsp+238h+var_60], 7
0x18004a184  cmova   rcx, [rsp+238h+S2]; S1
0x18004a18d  mov     r8, rbx
0x18004a190  cmp     rbx, r14
0x18004a193  cmovnb  r8, r14; N
0x18004a197  call    wmemcmp
0x18004a19c  test    eax, eax
0x18004a19e  jz      short loc_18004A1DB
0x18004a1a0  jns     short loc_18004A1E0
0x18004a1a2  mov     r14, [rsp+238h+var_1F0]
0x18004a1a7  mov     r13, 333333333333333h
0x18004a1b1  cmp     [r14+8], r13
0x18004a1b5  jnz     short loc_18004A1F1
0x18004a1b7  lea     rcx, aMapSetTooLong; "map/set too long"
0x18004a1be  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18004a1c4  cmp     r15, r14
0x18004a1c7  jnb     loc_18004A13A
0x18004a1cd  mov     dword ptr [rsp+238h+var_1C8+8], r13d
0x18004a1d2  add     rbx, 10h
0x18004a1d6  jmp     loc_18004A145
0x18004a1db  cmp     r14, rbx
0x18004a1de  jb      short loc_18004A1A2
0x18004a1e0  mov     r13, 333333333333333h
0x18004a1ea  mov     r14, [rsp+238h+var_1F0]
0x18004a1ef  jmp     short loc_18004A251
0x18004a1f1  lea     rax, [rsp+238h+S2]
0x18004a1f9  mov     qword ptr [rsp+238h+var_1D8], rax
0x18004a1fe  lea     rax, [rsp+238h+var_1D8]
0x18004a203  mov     [rsp+238h+var_218], rax
0x18004a208  mov     r8, [r14]
0x18004a20b  mov     rdx, r14
0x18004a20e  lea     rcx, [rsp+238h+var_1A8]
0x18004a216  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UBackgroundAccessRegistration@BackgroundAccessNotifier@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UBackgroundAccessRegistration@BackgroundAccessNotifier@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UBackgroundAccessRegistration@BackgroundAccessNotifier@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>> &,std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *> *,std::piecewise_construct_t const &,std::tuple<std::wstring &&> &&,std::tuple<> &&)
0x18004a21b  mov     rbx, [rax+8]
0x18004a21f  mov     qword ptr [rax+8], 0
0x18004a227  lea     rcx, [rsp+238h+var_1A8]
0x18004a22f  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UBackgroundAccessRegistration@BackgroundAccessNotifier@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,BackgroundAccessNotifier::BackgroundAccessRegistration>,void *>>>(void)
0x18004a234  movups  xmm0, [rsp+238h+var_1C8]
0x18004a239  movaps  [rsp+238h+var_1D8], xmm0
0x18004a23e  mov     r8, rbx
0x18004a241  lea     rdx, [rsp+238h+var_1D8]
0x18004a246  mov     rcx, r14
0x18004a249  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> *>,std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> * const)
0x18004a24e  mov     rdi, rax
0x18004a251  mov     rbx, [rsp+238h+var_1F8]
0x18004a256  cmp     [rdi+48h], rbx
0x18004a25a  jz      short loc_18004A289
0x18004a25c  test    rbx, rbx
0x18004a25f  jz      short loc_18004A271
0x18004a261  mov     rax, [rbx]
0x18004a264  mov     rcx, rbx
0x18004a267  mov     rax, [rax+8]
0x18004a26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a270  nop
0x18004a271  mov     rax, [rdi+48h]
0x18004a275  mov     qword ptr [rsp+238h+var_1D8], rax
0x18004a27a  mov     [rdi+48h], rbx
0x18004a27e  lea     rcx, [rsp+238h+var_1D8]
0x18004a283  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a288  nop
0x18004a289  mov     rdx, [rsp+238h+var_60]
0x18004a291  cmp     rdx, 7
0x18004a295  jbe     short loc_18004A2AC
0x18004a297  lea     rdx, ds:2[rdx*2]
0x18004a29f  mov     rcx, [rsp+238h+S2]
0x18004a2a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004a2ac  mov     r15d, [rsp+238h+var_208]
0x18004a2b1  xorps   xmm0, xmm0
0x18004a2b4  movups  xmmword ptr [rsp+238h+S1], xmm0
0x18004a2bc  xor     eax, eax
0x18004a2be  mov     [rsp+238h+var_48], rax
  ... truncated ...
```
