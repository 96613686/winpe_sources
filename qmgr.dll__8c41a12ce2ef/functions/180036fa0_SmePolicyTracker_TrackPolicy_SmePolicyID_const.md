# SmePolicyTracker::TrackPolicy(SmePolicyID const &)

- ea: `0x180036fa0`
- end: `0x1800377b1`
- name: `?TrackPolicy@SmePolicyTracker@@QEAAJAEBUSmePolicyID@@@Z`
- size: `2065`
- prototype: `int(SmePolicyTracker *__hidden this, const struct SmePolicyID *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f29a0`

## callees

- `0x180006640`
- `0x180011760`
- `0x180033420`
- `0x180033480`
- `0x180035928`
- `0x180036fa0`
- `0x1800377b8`
- `0x180037804`
- `0x180038ec0`
- `0x1800634e0`
- `0x180080430`
- `0x180081600`
- `0x1800836b0`
- `0x180086674`
- `0x180090524`
- `0x180095600`
- `0x1800959c0`
- `0x18009b668`
- `0x18009d024`
- `0x1800a3444`
- `0x1800e8d24`
- `0x1800e8db8`
- `0x1800e90ac`
- `0x1800e912c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037118`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180037131`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180037131`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180037176`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180037176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003713b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003713b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800376e6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800376e6`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x1800370f7`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x180037397`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x180037788`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x1800370f7`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x180037397`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x180037788`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityWindowClosedReasonSubscribe` at `0x1800374f1`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityWindowClosedReasonSubscribe` at `0x1800374f1`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x1800372b4`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x1800372b4`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityRequest` at `0x180037469`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityRequest` at `0x180037469`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityAllocate` at `0x1800373e2`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityAllocate` at `0x1800373e2`

## string_xrefs

- `0x18003714d`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SmePolicyTracker::TrackPolicy(SmePolicyTracker *this, const struct SmePolicyID *a2)
{
  __int64 *v4; // r8
  __int64 *v5; // rcx
  __int64 *v6; // rbx
  int v7; // edx
  __int64 result; // rax
  __int64 v9; // rdi
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int LastError; // ebx
  __int64 *v15; // rcx
  __int64 *v16; // rax
  __int64 *i; // rbx
  void *v18; // r12
  NTSTATUS v19; // eax
  unsigned __int64 v20; // rdx
  unsigned __int8 v21; // cl
  int v22; // ebx
  __int64 v23; // rcx
  CTelemetry *v24; // rcx
  unsigned int v25; // r13d
  void *v26; // rbx
  NTSTATUS v27; // eax
  unsigned __int64 v28; // rdx
  unsigned __int8 v29; // cl
  int v30; // ebx
  __int64 v31; // rcx
  CTelemetry *v32; // rcx
  NTSTATUS v33; // eax
  int v34; // ebx
  NTSTATUS v35; // eax
  unsigned __int64 v36; // rdx
  unsigned __int8 v37; // cl
  int v38; // ebx
  __int64 v39; // rcx
  CTelemetry *v40; // rcx
  void *v41; // rbx
  _QWORD *v42; // rax
  char *v43; // rsi
  int updated; // ecx
  __int64 v45; // rax
  char *v46; // r13
  _QWORD *v47; // r10
  _QWORD *v48; // rcx
  int v49; // r15d
  _QWORD *v50; // rdx
  void *v51; // r12
  __int64 v52; // rax
  __int64 v53; // rbx
  const ComError *v54; // rbx
  __int64 v55; // [rsp+40h] [rbp-2D8h] BYREF
  char *v56; // [rsp+48h] [rbp-2D0h]
  char *v57; // [rsp+50h] [rbp-2C8h]
  void *v58; // [rsp+60h] [rbp-2B8h] BYREF
  int v59; // [rsp+68h] [rbp-2B0h]
  int v60; // [rsp+6Ch] [rbp-2ACh]
  const ComError *v61; // [rsp+70h] [rbp-2A8h] BYREF
  char v62[8]; // [rsp+78h] [rbp-2A0h] BYREF
  char *v63; // [rsp+80h] [rbp-298h]
  _BYTE v64[12]; // [rsp+88h] [rbp-290h] BYREF
  int v65; // [rsp+94h] [rbp-284h]
  void **pExceptionObject; // [rsp+A0h] [rbp-278h] BYREF
  __int128 v67; // [rsp+A8h] [rbp-270h]
  int v68; // [rsp+B8h] [rbp-260h]
  int v69; // [rsp+BCh] [rbp-25Ch]
  int v70; // [rsp+C0h] [rbp-258h]
  void **v71; // [rsp+100h] [rbp-218h] BYREF
  __int128 v72; // [rsp+108h] [rbp-210h]
  int v73; // [rsp+118h] [rbp-200h]
  int v74; // [rsp+11Ch] [rbp-1FCh]
  int v75; // [rsp+120h] [rbp-1F8h]
  void **v76; // [rsp+160h] [rbp-1B8h] BYREF
  __int128 v77; // [rsp+168h] [rbp-1B0h]
  int v78; // [rsp+178h] [rbp-1A0h]
  int v79; // [rsp+17Ch] [rbp-19Ch]
  int v80; // [rsp+180h] [rbp-198h]
  void **v81; // [rsp+1C0h] [rbp-158h] BYREF
  __int128 v82; // [rsp+1C8h] [rbp-150h]
  int v83; // [rsp+1D8h] [rbp-140h]
  int v84; // [rsp+1DCh] [rbp-13Ch]
  int v85; // [rsp+1E0h] [rbp-138h]
  void **v86; // [rsp+220h] [rbp-F8h] BYREF
  __int128 v87; // [rsp+228h] [rbp-F0h]
  int v88; // [rsp+238h] [rbp-E0h]
  int v89; // [rsp+23Ch] [rbp-DCh]
  int v90; // [rsp+240h] [rbp-D8h]
  void **v91; // [rsp+280h] [rbp-98h] BYREF
  __int128 v92; // [rsp+288h] [rbp-90h]
  int v93; // [rsp+298h] [rbp-80h]
  int v94; // [rsp+29Ch] [rbp-7Ch]
  int v95; // [rsp+2A0h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]
  void *TokenHandle; // [rsp+320h] [rbp+8h] BYREF
  void *v98; // [rsp+330h] [rbp+18h] BYREF
  __int64 v99; // [rsp+338h] [rbp+20h]

  if ( !*((_BYTE *)this + 8) || !(*(unsigned __int8 (__fastcall **)(SmePolicyTracker *))(*(_QWORD *)this + 16LL))(this) )
    return 0;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_0130018c1051356b936cc0c81fcbc476_Traceguids);
  SmePolicyID::Dump(a2);
  v98 = 0;
  v58 = 0;
  v63 = (char *)this + 224;
  CCritSec2::enter((SmePolicyTracker *)((char *)this + 224));
  v62[0] = 1;
  v57 = (char *)this + 288;
  v4 = (__int64 *)*((_QWORD *)this + 36);
  v5 = (__int64 *)v4[1];
  v65 = 0;
  v6 = v4;
  if ( !*((_BYTE *)v5 + 25) )
  {
    v7 = *(_DWORD *)a2;
    do
    {
      if ( *((_DWORD *)v5 + 8) <= v7 && (*((_DWORD *)v5 + 8) < v7 || *((_DWORD *)v5 + 9) < *((_DWORD *)a2 + 1)) )
        v5 += 2;
      else
        v6 = v5;
      v5 = (__int64 *)*v5;
    }
    while ( !*((_BYTE *)v5 + 25) );
  }
  if ( !*((_BYTE *)v6 + 25)
    && (*(_DWORD *)a2 > *((_DWORD *)v6 + 8)
     || *(_DWORD *)a2 >= *((_DWORD *)v6 + 8) && *((_DWORD *)a2 + 1) >= *((_DWORD *)v6 + 9))
    && v6 != v4 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_0130018c1051356b936cc0c81fcbc476_Traceguids);
    ++*(_DWORD *)(v6[5] + 28);
    SmePolicyTracker::TrackedSmePolicyState::Dump((SmePolicyTracker::TrackedSmePolicyState *)v6[5]);
    HoldCritSec::~HoldCritSec((HoldCritSec *)v62);
    if ( v98 )
      CrmActivityFree(v98);
    return 0;
  }
  v9 = -1;
  v99 = -1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, 0) )
    {
      v9 = (__int64)TokenHandle;
      v99 = (__int64)TokenHandle;
      LastError = 0;
      goto LABEL_104;
    }
    v12 = 454;
  }
  else
  {
    v12 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v12,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                v11);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_104:
  try
  {
    if ( LastError < 0 )
    {
      v67 = 0;
      pExceptionObject = &ComError::`vftable';
      v68 = LastError;
      v69 = 267;
      v70 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v15 = (__int64 *)*((_QWORD *)this + 34);
    v16 = (__int64 *)v15[1];
    v65 = 0;
    for ( i = v15; !*((_BYTE *)v16 + 25); v16 = (__int64 *)*v16 )
    {
      if ( *((_DWORD *)v16 + 8) >= *(_DWORD *)a2 )
        i = v16;
      else
        v16 += 2;
    }
    if ( *((_BYTE *)i + 25) || i == v15 || *(_DWORD *)a2 < *((_DWORD *)i + 8) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_0130018c1051356b936cc0c81fcbc476_Traceguids);
      TokenHandle = 0;
      v19 = CrmRegister(&TokenHandle, *(unsigned int *)a2, L"BITS");
      v22 = NtStatusToHResult(v19);
      if ( v22 < 0 )
      {
        if ( CTelemetry::IsEnabled(v21, v20) )
        {
          wil::details::static_lazy<CTelemetry>::get(
            v23,
            _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
          CTelemetry::CrmAPIFailure_(v24, L"CrmRegister", v22);
        }
        v72 = 0;
        v71 = &ComError::`vftable';
        v73 = v22;
        v74 = 285;
        v75 = 1;
        throw (ComError *)&v71;
      }
      LODWORD(v55) = *(_DWORD *)a2;
      v56 = (char *)TokenHandle;
      std::_Tree<std::_Tmap_traits<enum _CRM_CLIENT_ID,void *,std::less<enum _CRM_CLIENT_ID>,std::allocator<std::pair<enum _CRM_CLIENT_ID const,void *>>,0>>::_Emplace<std::pair<enum _CRM_CLIENT_ID,void *>>(
        (char *)this + 272,
        v64,
        &v55);
      v18 = TokenHandle;
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CrmUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CrmUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&TokenHandle);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_0130018c1051356b936cc0c81fcbc476_Traceguids);
      v18 = (void *)i[5];
    }
    v25 = *((_DWORD *)a2 + 1);
    v26 = v98;
    if ( v98 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v55);
      CrmActivityFree(v26);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v55);
    }
    v98 = 0;
    v27 = CrmActivityAllocate(&v98, v18, v25, L"BITS Transfers", 0, CCancelTransfer::SetProgress, this);
    v30 = NtStatusToHResult(v27);
    if ( v30 < 0 )
    {
      if ( CTelemetry::IsEnabled(v29, v28) )
      {
        wil::details::static_lazy<CTelemetry>::get(
          v31,
          _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
        CTelemetry::CrmAPIFailure_(v32, L"CrmActivityAllocate", v30);
      }
      v77 = 0;
      v76 = &ComError::`vftable';
      v78 = v30;
      v79 = 307;
      v80 = 1;
      throw (ComError *)&v76;
    }
    v33 = CrmActivityRequest(v98);
    v34 = NtStatusToHResult(v33);
    LODWORD(TokenHandle) = v34;
    if ( v34 < 0 )
    {
      CTelemetry::CrmAPIFailure<unsigned short const (&)[19],long &>(L"CrmActivityRequest");
      v82 = 0;
      v81 = &ComError::`vftable';
      v83 = v34;
      v84 = 310;
      v85 = 1;
      throw (ComError *)&v81;
    }
    v35 = CrmActivityWindowClosedReasonSubscribe(v98, SmePolicyTracker::SmePolicyBlockingReasonsChangedCallback, this);
    v38 = NtStatusToHResult(v35);
    if ( v38 < 0 )
    {
      if ( CTelemetry::IsEnabled(v37, v36) )
      {
        wil::details::static_lazy<CTelemetry>::get(
          v39,
          _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
        CTelemetry::CrmAPIFailure_(v40, L"CrmActivityWindowClosedReasonSubscribe", v38);
      }
      v87 = 0;
      v86 = &ComError::`vftable';
      v88 = v38;
      v89 = 320;
      v90 = 1;
      throw (ComError *)&v86;
    }
    v41 = v98;
    v58 = v98;
    v42 = operator new(0x28u);
    v43 = (char *)v42;
    if ( v42 )
    {
      *v42 = *(_QWORD *)a2;
      v42[1] = v18;
      v42[2] = v41;
      *((_DWORD *)v42 + 6) = 0;
      *(_QWORD *)((char *)v42 + 28) = 1;
      *((_DWORD *)v42 + 9) = 16;
    }
    else
    {
      v43 = 0;
    }
    TokenHandle = v43;
    updated = SmePolicyTracker::UpdateSmePolicyEvaluation(v98, (struct SmePolicyEvaluation *)(v43 + 32));
    if ( updated < 0 )
    {
      v92 = 0;
      v91 = &ComError::`vftable';
      v93 = updated;
      v94 = 328;
      v95 = 1;
      throw (ComError *)&v91;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_0130018c1051356b936cc0c81fcbc476_Traceguids);
    SmePolicyTracker::TrackedSmePolicyState::Dump((SmePolicyTracker::TrackedSmePolicyState *)v43);
    v45 = *(_QWORD *)a2;
    v55 = *(_QWORD *)a2;
    TokenHandle = 0;
    v56 = v43;
    v46 = v57;
    v47 = *(_QWORD **)v57;
    v48 = *(_QWORD **)(*(_QWORD *)v57 + 8LL);
    v49 = 0;
    v57 = 0;
    v50 = v47;
    if ( *((_BYTE *)v48 + 25) )
    {
      v51 = v48;
    }
    else
    {
      do
      {
        v51 = v48;
        if ( *((_DWORD *)v48 + 8) <= (int)v45
          && (*((_DWORD *)v48 + 8) < (int)v45 || *((_DWORD *)v48 + 9) < SHIDWORD(v55)) )
        {
          v49 = 0;
          v48 += 2;
        }
        else
        {
          v49 = 1;
          v50 = v48;
        }
        v48 = (_QWORD *)*v48;
      }
      while ( !*((_BYTE *)v48 + 25) );
    }
    if ( *((_BYTE *)v50 + 25)
      || (int)v45 <= *((_DWORD *)v50 + 8) && ((int)v45 < *((_DWORD *)v50 + 8) || SHIDWORD(v55) < *((_DWORD *)v50 + 9)) )
    {
      if ( *((_QWORD *)v46 + 1) == 0x555555555555555LL )
        std::_Xlength_error("map/set too long");
      v52 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SmePolicyID const,std::unique_ptr<SmePolicyTracker::TrackedSmePolicyState>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SmePolicyID const,std::unique_ptr<SmePolicyTracker::TrackedSmePolicyState>>,void *>>>(
              v64,
              v46,
              v47,
              &v55);
      v53 = *(_QWORD *)(v52 + 8);
      *(_QWORD *)(v52 + 8) = 0;
      std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SmePolicyID const,std::unique_ptr<SmePolicyTracker::TrackedSmePolicyState>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SmePolicyID const,std::unique_ptr<SmePolicyTracker::TrackedSmePolicyState>>,void *>>>(v64);
      v58 = v51;
      v59 = v49;
      v60 = (int)v57;
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
        v46,
        &v58,
        v53);
      v43 = v56;
    }
    if ( v43 )
      operator delete(v43, 0x28u);
    v98 = 0;
    if ( v9 != -1 )
      wil::details::RevertImpersonateToken((HANDLE)v9, v50);
    HoldCritSec::~HoldCritSec((HoldCritSec *)v62);
    if ( v98 )
      CrmActivityFree(v98);
    result = 0;
  }
  catch ( const ComError *v61 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v54 = v61;
    }
    else
    {
      v54 = v61;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_0130018c1051356b936cc0c81fcbc476_Traceguids,
        *((unsigned int *)v61 + 6),
        *((_DWORD *)v61 + 7));
    }
    LODWORD(TokenHandle) = *((_DWORD *)v54 + 6);
    return (unsigned int)TokenHandle;
  }
  return result;
}

```

## disassembly

```asm
0x180036fa0  push    rbx
0x180036fa2  push    rsi
0x180036fa3  push    rdi
0x180036fa4  push    r12
0x180036fa6  push    r13
0x180036fa8  push    r14
0x180036faa  push    r15
0x180036fac  sub     rsp, 2E0h
0x180036fb3  mov     r15, rdx
0x180036fb6  mov     rsi, rcx
0x180036fb9  xor     r13d, r13d
0x180036fbc  cmp     [rcx+8], r13b
0x180036fc0  jz      loc_18003779B
0x180036fc6  mov     rax, [rcx]
0x180036fc9  mov     rax, [rax+10h]
0x180036fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fd2  test    al, al
0x180036fd4  jz      loc_18003779B
0x180036fda  lea     rdi, WPP_GLOBAL_Control
0x180036fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fe8  lea     r14d, [r13+1]
0x180036fec  cmp     rcx, rdi
0x180036fef  jz      short loc_18003700B
0x180036ff1  test    [rcx+1Ch], r14b
0x180036ff5  jz      short loc_18003700B
0x180036ff7  lea     edx, [r13+18h]
0x180036ffb  lea     r8, WPP_0130018c1051356b936cc0c81fcbc476_Traceguids
0x180037002  mov     rcx, [rcx+10h]
0x180037006  call    WPP_SF_
0x18003700b  mov     rcx, r15; this
0x18003700e  call    ?Dump@SmePolicyID@@QEBAXXZ; SmePolicyID::Dump(void)
0x180037013  nop
0x180037014  mov     [rsp+318h+arg_10], r13
0x18003701c  mov     [rsp+318h+var_2B8], r13
0x180037021  lea     rcx, [rsi+0E0h]; this
0x180037028  mov     [rsp+318h+var_298], rcx
0x180037030  call    ?enter@CCritSec2@@QEAAXXZ; CCritSec2::enter(void)
0x180037035  mov     [rsp+318h+var_2A0], r14b
0x18003703a  lea     rax, [rsi+120h]
0x180037041  mov     [rsp+318h+var_2C8], rax
0x180037046  mov     r8, [rsi+120h]
0x18003704d  mov     rcx, [r8+8]
0x180037051  xor     eax, eax
0x180037053  mov     [rsp+318h+var_284], eax
0x18003705a  mov     rbx, r8
0x18003705d  cmp     [rcx+19h], r13b
0x180037061  jnz     short loc_180037088
0x180037063  mov     edx, [r15]
0x180037066  cmp     [rcx+20h], edx
0x180037069  jg      short loc_180037076
0x18003706b  jl      short loc_18003707B
0x18003706d  mov     eax, [r15+4]
0x180037071  cmp     [rcx+24h], eax
0x180037074  jl      short loc_18003707B
0x180037076  mov     rbx, rcx
0x180037079  jmp     short loc_18003707F
0x18003707b  add     rcx, 10h
0x18003707f  mov     rcx, [rcx]
0x180037082  cmp     [rcx+19h], r13b
0x180037086  jz      short loc_180037066
0x180037088  cmp     [rbx+19h], r13b
0x18003708c  jnz     short loc_180037104
0x18003708e  mov     eax, [r15]
0x180037091  cmp     eax, [rbx+20h]
0x180037094  jg      short loc_1800370A1
0x180037096  jl      short loc_180037104
0x180037098  mov     eax, [rbx+24h]
0x18003709b  cmp     [r15+4], eax
0x18003709f  jl      short loc_180037104
0x1800370a1  cmp     rbx, r8
0x1800370a4  jz      short loc_180037104
0x1800370a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370ad  cmp     rcx, rdi
0x1800370b0  jz      short loc_1800370CD
0x1800370b2  test    [rcx+1Ch], r14b
0x1800370b6  jz      short loc_1800370CD
0x1800370b8  mov     edx, 19h
0x1800370bd  lea     r8, WPP_0130018c1051356b936cc0c81fcbc476_Traceguids
0x1800370c4  mov     rcx, [rcx+10h]
0x1800370c8  call    WPP_SF_
0x1800370cd  mov     rax, [rbx+28h]
0x1800370d1  add     [rax+1Ch], r14d
0x1800370d5  mov     rcx, [rbx+28h]; this
0x1800370d9  call    ?Dump@TrackedSmePolicyState@SmePolicyTracker@@QEBAXXZ; SmePolicyTracker::TrackedSmePolicyState::Dump(void)
0x1800370de  nop
0x1800370df  lea     rcx, [rsp+318h+var_2A0]; this
0x1800370e4  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x1800370e9  nop
0x1800370ea  mov     rcx, [rsp+318h+arg_10]
0x1800370f2  test    rcx, rcx
0x1800370f5  jz      short loc_1800370FD
0x1800370f7  call    cs:__imp_CrmActivityFree
0x1800370fd  xor     eax, eax
0x1800370ff  jmp     loc_18003779D
0x180037104  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180037108  mov     [rsp+318h+arg_18], rdi
0x180037110  mov     [rsp+318h+TokenHandle], r13
0x180037118  call    cs:__imp_GetCurrentThread
0x18003711e  lea     r9, [rsp+318h+TokenHandle]; TokenHandle
0x180037126  mov     r8d, r14d; OpenAsSelf
0x180037129  mov     edx, 0F01FFh; DesiredAccess
0x18003712e  mov     rcx, rax; ThreadHandle
0x180037131  call    cs:__imp_OpenThreadToken
0x180037137  test    eax, eax
0x180037139  jnz     short loc_180037172
0x18003713b  call    cs:__imp_GetLastError
0x180037141  cmp     eax, 3F0h
0x180037146  jz      short loc_180037172
0x180037148  mov     edx, 1C2h; void *
0x18003714d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037154  mov     rcx, [rsp+318h]; this
0x18003715c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037161  mov     ebx, eax
0x180037163  lea     rcx, [rsp+318h+TokenHandle]
0x18003716b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037170  jmp     short loc_18003719A
0x180037172  xor     edx, edx; Token
0x180037174  xor     ecx, ecx; Thread
0x180037176  call    cs:__imp_SetThreadToken
0x18003717c  test    eax, eax
0x18003717e  jnz     short loc_180037187
0x180037180  mov     edx, 1C6h
0x180037185  jmp     short loc_18003714D
0x180037187  mov     rdi, [rsp+318h+TokenHandle]
0x18003718f  mov     [rsp+318h+arg_18], rdi
0x180037197  mov     ebx, r13d
0x18003719a  test    ebx, ebx
0x18003719c  jns     short loc_1800371E6
0x18003719e  xorps   xmm0, xmm0
0x1800371a1  movups  [rsp+318h+var_270], xmm0
0x1800371a9  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800371b0  mov     [rsp+318h+pExceptionObject], rax
0x1800371b8  mov     [rsp+318h+var_260], ebx
0x1800371bf  mov     [rsp+318h+var_25C], 10Bh
0x1800371ca  mov     [rsp+318h+var_258], r14d
0x1800371d2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800371d9  lea     rcx, [rsp+318h+pExceptionObject]; pExceptionObject
0x1800371e1  call    _CxxThrowException_0
0x1800371e6  lea     r12, [rsi+110h]
0x1800371ed  mov     rcx, [r12]
0x1800371f1  mov     rax, [rcx+8]
0x1800371f5  xor     edx, edx
0x1800371f7  mov     [rsp+318h+var_284], edx
0x1800371fe  mov     rbx, rcx
0x180037201  cmp     [rax+19h], r13b
0x180037205  jnz     short loc_180037221
0x180037207  mov     edx, [r15]
0x18003720a  cmp     [rax+20h], edx
0x18003720d  jge     short loc_180037215
0x18003720f  add     rax, 10h
0x180037213  jmp     short loc_180037218
0x180037215  mov     rbx, rax
0x180037218  mov     rax, [rax]
0x18003721b  cmp     [rax+19h], r13b
0x18003721f  jz      short loc_18003720A
0x180037221  cmp     [rbx+19h], r13b
0x180037225  jnz     short loc_18003726B
0x180037227  mov     eax, [rbx+20h]
0x18003722a  cmp     rbx, rcx
0x18003722d  jz      short loc_18003726B
0x18003722f  cmp     [r15], eax
0x180037232  jl      short loc_18003726B
0x180037234  mov     rcx, cs:WPP_GLOBAL_Control
0x18003723b  lea     rax, WPP_GLOBAL_Control
0x180037242  cmp     rcx, rax
0x180037245  jz      short loc_180037262
0x180037247  test    [rcx+1Ch], r14b
0x18003724b  jz      short loc_180037262
0x18003724d  mov     edx, 1Ah
0x180037252  lea     r8, WPP_0130018c1051356b936cc0c81fcbc476_Traceguids
0x180037259  mov     rcx, [rcx+10h]
0x18003725d  call    WPP_SF_
0x180037262  mov     r12, [rbx+28h]
0x180037266  jmp     loc_180037379
0x18003726b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037272  lea     rax, WPP_GLOBAL_Control
0x180037279  cmp     rcx, rax
0x18003727c  jz      short loc_18003729A
0x18003727e  test    [rcx+1Ch], r14b
0x180037282  jz      short loc_18003729A
0x180037284  mov     edx, 1Bh
0x180037289  lea     r8, WPP_0130018c1051356b936cc0c81fcbc476_Traceguids
0x180037290  mov     rcx, [rcx+10h]
0x180037294  call    WPP_SF_
0x180037299  nop
0x18003729a  mov     [rsp+318h+TokenHandle], r13
0x1800372a2  lea     r8, ?BitsCrmClientDescription@SmePolicyTracker@@0QBGB; "BITS"
0x1800372a9  mov     edx, [r15]
0x1800372ac  lea     rcx, [rsp+318h+TokenHandle]
0x1800372b4  call    cs:__imp_CrmRegister
0x1800372ba  mov     ecx, eax; Status
0x1800372bc  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x1800372c1  mov     ebx, eax
0x1800372c3  test    eax, eax
0x1800372c5  jns     short loc_180037333
0x1800372c7  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800372cc  test    al, al
0x1800372ce  jz      short loc_1800372EB
0x1800372d0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x1800372d7  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x1800372dc  mov     r8d, ebx; int
0x1800372df  lea     rdx, aCrmregister_0; "CrmRegister"
0x1800372e6  call    ?CrmAPIFailure_@CTelemetry@@QEAAXPEBGJ@Z; CTelemetry::CrmAPIFailure_(ushort const *,long)
0x1800372eb  xorps   xmm0, xmm0
0x1800372ee  movups  [rsp+318h+var_210], xmm0
0x1800372f6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800372fd  mov     [rsp+318h+var_218], rax
0x180037305  mov     [rsp+318h+var_200], ebx
0x18003730c  mov     [rsp+318h+var_1FC], 11Dh
0x180037317  mov     [rsp+318h+var_1F8], r14d
0x18003731f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180037326  lea     rcx, [rsp+318h+var_218]; pExceptionObject
0x18003732e  call    _CxxThrowException_0
0x180037333  mov     eax, [r15]
0x180037336  mov     dword ptr [rsp+318h+var_2D8], eax
0x18003733a  mov     rax, [rsp+318h+TokenHandle]
0x180037342  mov     [rsp+318h+var_2D0], rax
0x180037347  lea     r8, [rsp+318h+var_2D8]
0x18003734c  lea     rdx, [rsp+318h+var_290]
0x180037354  mov     rcx, r12
0x180037357  call    ??$_Emplace@U?$pair@W4_CRM_CLIENT_ID@@PEAX@std@@@?$_Tree@V?$_Tmap_traits@W4_CRM_CLIENT_ID@@PEAXU?$less@W4_CRM_CLIENT_ID@@@std@@V?$allocator@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@PEAX@std@@_N@1@$$QEAU?$pair@W4_CRM_CLIENT_ID@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_CRM_CLIENT_ID,void *,std::less<_CRM_CLIENT_ID>,std::allocator<std::pair<_CRM_CLIENT_ID const,void *>>,0>>::_Emplace<std::pair<_CRM_CLIENT_ID,void *>>(std::pair<_CRM_CLIENT_ID,void *> &&)
0x18003735c  mov     r12, [rsp+318h+TokenHandle]
0x180037364  mov     [rsp+318h+TokenHandle], r13
0x18003736c  lea     rcx, [rsp+318h+TokenHandle]
0x180037374  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CrmUnregister@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CrmUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CrmUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037379  mov     r13d, [r15+4]
0x18003737d  mov     rbx, [rsp+318h+arg_10]
0x180037385  test    rbx, rbx
0x180037388  jz      short loc_1800373A7
0x18003738a  lea     rcx, [rsp+318h+var_2D8]; this
0x18003738f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180037394  mov     rcx, rbx
0x180037397  call    cs:__imp_CrmActivityFree
0x18003739d  lea     rcx, [rsp+318h+var_2D8]; this
0x1800373a2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800373a7  mov     [rsp+318h+arg_10], 0
0x1800373b3  mov     [rsp+318h+var_2E8], rsi
0x1800373b8  lea     rax, ?SetProgress@CCancelTransfer@@UEAAXPEAUFILE_PROGRESS@IAbstractTransfer@@@Z; CCancelTransfer::SetProgress(IAbstractTransfer::FILE_PROGRESS *)
0x1800373bf  mov     [rsp+318h+var_2F0], rax
0x1800373c4  mov     [rsp+318h+var_2F8], 0
0x1800373cd  lea     r9, ?BitsCrmActivityDescription@SmePolicyTracker@@0QBGB; "BITS Transfers"
0x1800373d4  mov     r8d, r13d
0x1800373d7  mov     rdx, r12
0x1800373da  lea     rcx, [rsp+318h+arg_10]
0x1800373e2  call    cs:__imp_CrmActivityAllocate
0x1800373e8  mov     ecx, eax; Status
0x1800373ea  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x1800373ef  mov     ebx, eax
0x1800373f1  test    eax, eax
0x1800373f3  jns     short loc_180037461
0x1800373f5  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800373fa  test    al, al
0x1800373fc  jz      short loc_180037419
0x1800373fe  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x180037405  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x18003740a  mov     r8d, ebx; int
0x18003740d  lea     rdx, aCrmactivityall_0; "CrmActivityAllocate"
0x180037414  call    ?CrmAPIFailure_@CTelemetry@@QEAAXPEBGJ@Z; CTelemetry::CrmAPIFailure_(ushort const *,long)
0x180037419  xorps   xmm0, xmm0
0x18003741c  movups  [rsp+318h+var_1B0], xmm0
0x180037424  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003742b  mov     [rsp+318h+var_1B8], rax
0x180037433  mov     [rsp+318h+var_1A0], ebx
0x18003743a  mov     [rsp+318h+var_19C], 133h
0x180037445  mov     [rsp+318h+var_198], r14d
0x18003744d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180037454  lea     rcx, [rsp+318h+var_1B8]; pExceptionObject
0x18003745c  call    _CxxThrowException_0
0x180037461  mov     rcx, [rsp+318h+arg_10]
0x180037469  call    cs:__imp_CrmActivityRequest
0x18003746f  mov     ecx, eax; Status
0x180037471  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x180037476  mov     ebx, eax
0x180037478  mov     dword ptr [rsp+318h+TokenHandle], eax
0x18003747f  test    eax, eax
0x180037481  jns     short loc_1800374DF
0x180037483  lea     rdx, [rsp+318h+TokenHandle]
0x18003748b  lea     rcx, aCrmactivityreq_0; "CrmActivityRequest"
0x180037492  call    ??$CrmAPIFailure@AEAY0BD@$$CBGAEAJ@CTelemetry@@SAXAEAY0BD@$$CBGAEAJ@Z; CTelemetry::CrmAPIFailure<ushort const (&)[19],long &>(ushort const (&)[19],long &)
0x180037497  xorps   xmm0, xmm0
0x18003749a  movups  [rsp+318h+var_150], xmm0
0x1800374a2  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800374a9  mov     [rsp+318h+var_158], rax
0x1800374b1  mov     [rsp+318h+var_140], ebx
0x1800374b8  mov     [rsp+318h+var_13C], 136h
0x1800374c3  mov     [rsp+318h+var_138], r14d
0x1800374cb  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800374d2  lea     rcx, [rsp+318h+var_158]; pExceptionObject
0x1800374da  call    _CxxThrowException_0
0x1800374df  mov     r8, rsi
0x1800374e2  lea     rdx, ?SmePolicyBlockingReasonsChangedCallback@SmePolicyTracker@@CAXPEAX00@Z; SmePolicyTracker::SmePolicyBlockingReasonsChangedCallback(void *,void *,void *)
0x1800374e9  mov     rcx, [rsp+318h+arg_10]
0x1800374f1  call    cs:__imp_CrmActivityWindowClosedReasonSubscribe
0x1800374f7  mov     ecx, eax; Status
0x1800374f9  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x1800374fe  mov     ebx, eax
0x180037500  test    eax, eax
0x180037502  jns     short loc_180037570
0x180037504  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x180037509  test    al, al
  ... truncated ...
```
