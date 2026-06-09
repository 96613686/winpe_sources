# ResetNetworkAdapter(_GUID const &)

- ea: `0x1800a2bec`
- end: `0x1800a314a`
- name: `?ResetNetworkAdapter@@YAJAEBU_GUID@@@Z`
- size: `1374`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a2bb0`

## callees

- `0x180002a90`
- `0x180037ddc`
- `0x1800a2bec`
- `0x1800a88a0`
- `0x1800c9af8`
- `0x1800cc460`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800a2dfc`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800a2dfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2c31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2c31`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2eb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2fce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2eb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2fce`

## string_xrefs

- `0x1800a2c50`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x1800a2cb4`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x1800a2e1f`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x1800a2ed5`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x1800a2fee`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x1800a2c41`: `ResetNetworkAdapter - CoCreateInstance failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ResetNetworkAdapter(const struct _GUID *a1)
{
  unsigned int v2; // ebx
  LPVOID v3; // rcx
  __int64 v4; // rcx
  LPVOID v5; // rcx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  IUnknown *v9; // rcx
  IUnknown *v10; // rcx
  IUnknown *v11; // rcx
  __int64 v12; // rcx
  LPVOID v13; // rcx
  int v14; // edi
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  IUnknown *v19; // rcx
  __int64 v20; // rcx
  IUnknown *v21; // rcx
  __int64 v22; // rcx
  LPVOID v23; // rcx
  int v24; // edi
  int v25; // eax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  IUnknown *v29; // rcx
  __int64 v30; // rcx
  IUnknown *v31; // rcx
  __int64 v32; // rcx
  LPVOID v33; // rcx
  IUnknown *v34; // rcx
  IUnknown *v35; // rcx
  __int64 v36; // rcx
  LPVOID v37; // rcx
  const char *dwImpLevel; // [rsp+28h] [rbp-21h]
  const char *dwImpLevela; // [rsp+28h] [rbp-21h]
  const struct _GUID *v41; // [rsp+40h] [rbp-9h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-1h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+7h] BYREF
  __int64 v44; // [rsp+58h] [rbp+Fh] BYREF
  _QWORD *v45; // [rsp+60h] [rbp+17h] BYREF
  int v46; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  ppv = 0;
  v2 = CoCreateInstance(&CLSID_ConnectionManager, 0, 0x17u, &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e, &ppv);
  if ( (v2 & 0x80000000) == 0 )
  {
    v44 = 0;
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v44);
    if ( (v2 & 0x80000000) == 0 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v46 = 0;
          pProxy = 0;
          v2 = (*(__int64 (__fastcall **)(__int64, __int64, IUnknown **, int *))(*(_QWORD *)v44 + 24LL))(
                 v44,
                 1,
                 &pProxy,
                 &v46);
          if ( v2 )
          {
            v35 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v35->lpVtbl->Release)(v35);
            }
            goto LABEL_72;
          }
          v45 = 0;
          if ( ((int (__fastcall *)(IUnknown *, _QWORD **))pProxy->lpVtbl[2].AddRef)(pProxy, &v45) >= 0 )
            break;
          if ( (unsigned int)dword_1801BD288 > 5 )
          {
            v41 = a1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
              v6,
              (unsigned int)byte_18018CE11,
              v7,
              v8,
              (__int64)&v41);
          }
          wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
          v9 = pProxy;
          if ( pProxy )
          {
            pProxy = 0;
            ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
          }
        }
        if ( *v45 == *(_QWORD *)&a1->Data1 && v45[1] == *(_QWORD *)a1->Data4 )
          break;
        wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
        v10 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
        }
      }
      v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
      if ( (v2 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x10D6,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
          (const char *)v2,
          (int)"ResetNetworkAdapter - CoSetProxyBlanket failed",
          dwImpLevela);
        wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
        v11 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
        }
        v12 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        v13 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
        }
        return v2;
      }
      v14 = 0;
      while ( 1 )
      {
        v15 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].AddRef)(pProxy);
        v2 = v15;
        if ( v15 >= 0 )
          break;
        if ( v15 != -2147023659 )
        {
          if ( (unsigned int)dword_1801BD288 > 5 )
          {
            LODWORD(v41) = v15;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v16,
              (unsigned int)&unk_18018CDC0,
              v17,
              v18,
              (__int64)&v41);
          }
          wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
          v21 = pProxy;
          if ( pProxy )
          {
            pProxy = 0;
            ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
          }
          v22 = v44;
          if ( v44 )
          {
            v44 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          goto LABEL_46;
        }
        Sleep(0x64u);
        if ( (unsigned int)++v14 >= 5 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x10EA,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
            (const char *)v2,
            (int)"ResetNetworkAdapter - Disabling network adapter failed after max retries",
            dwImpLevela);
          wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
          v19 = pProxy;
          if ( pProxy )
          {
            pProxy = 0;
            ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
          }
          v20 = v44;
          if ( v44 )
          {
            v44 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
LABEL_46:
          v23 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
          }
          return v2;
        }
      }
      v24 = 0;
      while ( 1 )
      {
        v25 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].QueryInterface)(pProxy);
        v2 = v25;
        if ( v25 >= 0 )
          break;
        if ( v25 != -2147023659 )
        {
          if ( (unsigned int)dword_1801BD288 > 5 )
          {
            LODWORD(v41) = v25;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&unk_18018CD70,
              v27,
              v28,
              (__int64)&v41);
          }
          wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
          v31 = pProxy;
          if ( pProxy )
          {
            pProxy = 0;
            ((void (__fastcall *)(IUnknown *))v31->lpVtbl->Release)(v31);
          }
          v32 = v44;
          if ( v44 )
          {
            v44 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          goto LABEL_64;
        }
        Sleep(0x64u);
        if ( (unsigned int)++v24 >= 5 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x10FB,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
            (const char *)v2,
            (int)"ResetNetworkAdapter - Enabling network adapter failed",
            dwImpLevela);
          wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
          v29 = pProxy;
          if ( pProxy )
          {
            pProxy = 0;
            ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
          }
          v30 = v44;
          if ( v44 )
          {
            v44 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
LABEL_64:
          v33 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
          }
          return v2;
        }
      }
      wil::details::unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd::integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std::nullptr_t___(&v45);
      v34 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v34->lpVtbl->Release)(v34);
      }
LABEL_72:
      v36 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x10B3,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
        (const char *)v2,
        (int)"ResetNetworkAdapter - EnumConnections failed",
        dwImpLevel);
      v4 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      v5 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x10AE,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
      (const char *)v2,
      (int)"ResetNetworkAdapter - CoCreateInstance failed",
      dwImpLevel);
    v3 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800a2bec  push    rbp
0x1800a2bee  push    rbx
0x1800a2bef  push    rsi
0x1800a2bf0  push    rdi
0x1800a2bf1  lea     rbp, [rsp-3Fh]
0x1800a2bf6  sub     rsp, 88h
0x1800a2bfd  mov     rax, cs:__security_cookie
0x1800a2c04  xor     rax, rsp
0x1800a2c07  mov     [rbp+57h+var_30], rax
0x1800a2c0b  mov     rdi, rcx
0x1800a2c0e  xor     esi, esi
0x1800a2c10  mov     [rbp+57h+var_50], rsi
0x1800a2c14  lea     rax, [rbp+57h+var_50]
0x1800a2c18  mov     [rsp+0A0h+ppv], rax; ppv
0x1800a2c1d  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x1800a2c24  xor     edx, edx; pUnkOuter
0x1800a2c26  lea     r8d, [rsi+17h]; dwClsContext
0x1800a2c2a  lea     rcx, CLSID_ConnectionManager; rclsid
0x1800a2c31  call    cs:__imp_CoCreateInstance
0x1800a2c37  mov     ebx, eax
0x1800a2c39  test    eax, eax
0x1800a2c3b  jns     short loc_1800A2C81
0x1800a2c3d  mov     rcx, [rbp+5Fh]; this
0x1800a2c41  lea     rax, aResetnetworkad_1; "ResetNetworkAdapter - CoCreateInstance "...
0x1800a2c48  mov     [rsp+0A0h+ppv], rax; int
0x1800a2c4d  mov     r9d, ebx; char *
0x1800a2c50  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800a2c57  mov     edx, 10AEh; void *
0x1800a2c5c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a2c61  nop
0x1800a2c62  mov     rcx, [rbp+57h+var_50]
0x1800a2c66  test    rcx, rcx
0x1800a2c69  jz      short loc_1800A2C7C
0x1800a2c6b  mov     [rbp+57h+var_50], rsi
0x1800a2c6f  mov     rax, [rcx]
0x1800a2c72  mov     rax, [rax+10h]
0x1800a2c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c7b  nop
0x1800a2c7c  jmp     loc_1800A3130
0x1800a2c81  mov     [rbp+57h+var_48], rsi
0x1800a2c85  mov     rcx, [rbp+57h+var_50]
0x1800a2c89  mov     rax, [rcx]
0x1800a2c8c  lea     r8, [rbp+57h+var_48]
0x1800a2c90  xor     edx, edx
0x1800a2c92  mov     rax, [rax+18h]
0x1800a2c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c9b  mov     ebx, eax
0x1800a2c9d  test    eax, eax
0x1800a2c9f  jns     short loc_1800A2CFF
0x1800a2ca1  mov     rcx, [rbp+5Fh]; this
0x1800a2ca5  lea     rax, aResetnetworkad_2; "ResetNetworkAdapter - EnumConnections f"...
0x1800a2cac  mov     [rsp+0A0h+ppv], rax; int
0x1800a2cb1  mov     r9d, ebx; char *
0x1800a2cb4  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800a2cbb  mov     edx, 10B3h; void *
0x1800a2cc0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a2cc5  nop
0x1800a2cc6  mov     rcx, [rbp+57h+var_48]
0x1800a2cca  test    rcx, rcx
0x1800a2ccd  jz      short loc_1800A2CE0
0x1800a2ccf  mov     [rbp+57h+var_48], rsi
0x1800a2cd3  mov     rax, [rcx]
0x1800a2cd6  mov     rax, [rax+10h]
0x1800a2cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2cdf  nop
0x1800a2ce0  mov     rcx, [rbp+57h+var_50]
0x1800a2ce4  test    rcx, rcx
0x1800a2ce7  jz      short loc_1800A2CFA
0x1800a2ce9  mov     [rbp+57h+var_50], rsi
0x1800a2ced  mov     rax, [rcx]
0x1800a2cf0  mov     rax, [rax+10h]
0x1800a2cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2cf9  nop
0x1800a2cfa  jmp     loc_1800A3130
0x1800a2cff  mov     [rbp+57h+var_38], esi
0x1800a2d02  mov     [rbp+57h+pProxy], rsi
0x1800a2d06  mov     rcx, [rbp+57h+var_48]
0x1800a2d0a  mov     rax, [rcx]
0x1800a2d0d  lea     r9, [rbp+57h+var_38]
0x1800a2d11  lea     r8, [rbp+57h+pProxy]
0x1800a2d15  mov     edx, 1
0x1800a2d1a  mov     rax, [rax+18h]
0x1800a2d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d23  mov     ebx, eax
0x1800a2d25  test    eax, eax
0x1800a2d27  jnz     loc_1800A30E2
0x1800a2d2d  mov     [rbp+57h+var_40], rsi
0x1800a2d31  mov     rcx, [rbp+57h+pProxy]
0x1800a2d35  mov     rax, [rcx]
0x1800a2d38  lea     rdx, [rbp+57h+var_40]
0x1800a2d3c  mov     rax, [rax+38h]
0x1800a2d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d45  test    eax, eax
0x1800a2d47  jns     short loc_1800A2D96
0x1800a2d49  mov     eax, cs:dword_1801BD288
0x1800a2d4f  cmp     eax, 5
0x1800a2d52  jbe     short loc_1800A2D6D
0x1800a2d54  mov     [rbp+57h+var_60], rdi
0x1800a2d58  lea     rax, [rbp+57h+var_60]
0x1800a2d5c  mov     [rsp+0A0h+ppv], rax
0x1800a2d61  lea     rdx, byte_18018CE11
0x1800a2d68  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x1800a2d6d  lea     rcx, [rbp+57h+var_40]
0x1800a2d71  call    wil__details__unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t______unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t___
0x1800a2d76  nop
0x1800a2d77  mov     rcx, [rbp+57h+pProxy]
0x1800a2d7b  test    rcx, rcx
0x1800a2d7e  jz      short loc_1800A2D91
0x1800a2d80  mov     [rbp+57h+pProxy], rsi
0x1800a2d84  mov     rax, [rcx]
0x1800a2d87  mov     rax, [rax+10h]
0x1800a2d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d90  nop
0x1800a2d91  jmp     loc_1800A2CFF
0x1800a2d96  mov     rcx, [rbp+57h+var_40]
0x1800a2d9a  mov     rax, [rcx]
0x1800a2d9d  cmp     rax, [rdi]
0x1800a2da0  jnz     short loc_1800A2DAC
0x1800a2da2  mov     rax, [rcx+8]
0x1800a2da6  cmp     rax, [rdi+8]
0x1800a2daa  jz      short loc_1800A2DD5
0x1800a2dac  lea     rcx, [rbp+57h+var_40]
0x1800a2db0  call    wil__details__unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t______unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t___
0x1800a2db5  nop
0x1800a2db6  mov     rcx, [rbp+57h+pProxy]
0x1800a2dba  test    rcx, rcx
0x1800a2dbd  jz      short loc_1800A2DD0
0x1800a2dbf  mov     [rbp+57h+pProxy], rsi
0x1800a2dc3  mov     rax, [rcx]
0x1800a2dc6  mov     rax, [rax+10h]
0x1800a2dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2dcf  nop
0x1800a2dd0  jmp     loc_1800A2CFF
0x1800a2dd5  mov     [rsp+0A0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800a2ddd  mov     [rsp+0A0h+pAuthInfo], rsi; pAuthInfo
0x1800a2de2  mov     dword ptr [rsp+0A0h+dwImpLevel], 3; char *
0x1800a2dea  mov     dword ptr [rsp+0A0h+ppv], esi; dwAuthnLevel
0x1800a2dee  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800a2df2  xor     r8d, r8d; dwAuthzSvc
0x1800a2df5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800a2df8  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800a2dfc  call    cs:__imp_CoSetProxyBlanket
0x1800a2e02  mov     ebx, eax
0x1800a2e04  test    eax, eax
0x1800a2e06  jns     loc_1800A2E8D
0x1800a2e0c  mov     rcx, [rbp+5Fh]; this
0x1800a2e10  lea     rax, aResetnetworkad_3; "ResetNetworkAdapter - CoSetProxyBlanket"...
0x1800a2e17  mov     [rsp+0A0h+ppv], rax; int
0x1800a2e1c  mov     r9d, ebx; char *
0x1800a2e1f  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800a2e26  mov     edx, 10D6h; void *
0x1800a2e2b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a2e30  lea     rcx, [rbp+57h+var_40]
0x1800a2e34  call    wil__details__unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t______unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t___
0x1800a2e39  nop
0x1800a2e3a  mov     rcx, [rbp+57h+pProxy]
0x1800a2e3e  test    rcx, rcx
0x1800a2e41  jz      short loc_1800A2E54
0x1800a2e43  mov     [rbp+57h+pProxy], rsi
0x1800a2e47  mov     rax, [rcx]
0x1800a2e4a  mov     rax, [rax+10h]
0x1800a2e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e53  nop
0x1800a2e54  mov     rcx, [rbp+57h+var_48]
0x1800a2e58  test    rcx, rcx
0x1800a2e5b  jz      short loc_1800A2E6E
0x1800a2e5d  mov     [rbp+57h+var_48], rsi
0x1800a2e61  mov     rax, [rcx]
0x1800a2e64  mov     rax, [rax+10h]
0x1800a2e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e6d  nop
0x1800a2e6e  mov     rcx, [rbp+57h+var_50]
0x1800a2e72  test    rcx, rcx
0x1800a2e75  jz      short loc_1800A2E88
0x1800a2e77  mov     [rbp+57h+var_50], rsi
0x1800a2e7b  mov     rax, [rcx]
0x1800a2e7e  mov     rax, [rax+10h]
0x1800a2e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e87  nop
0x1800a2e88  jmp     loc_1800A3130
0x1800a2e8d  mov     edi, esi
0x1800a2e8f  mov     rcx, [rbp+57h+pProxy]
0x1800a2e93  mov     rax, [rcx]
0x1800a2e96  mov     rax, [rax+20h]
0x1800a2e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e9f  mov     ebx, eax
0x1800a2ea1  test    eax, eax
0x1800a2ea3  jns     loc_1800A2FA6
0x1800a2ea9  cmp     eax, 800704D5h
0x1800a2eae  jnz     short loc_1800A2F26
0x1800a2eb0  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800a2eb5  call    cs:__imp_Sleep
0x1800a2ebb  inc     edi
0x1800a2ebd  cmp     edi, 5
0x1800a2ec0  jb      short loc_1800A2E8F
0x1800a2ec2  mov     rcx, [rbp+5Fh]; this
0x1800a2ec6  lea     rax, aResetnetworkad_0; "ResetNetworkAdapter - Disabling network"...
0x1800a2ecd  mov     [rsp+0A0h+ppv], rax; int
0x1800a2ed2  mov     r9d, ebx; char *
0x1800a2ed5  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800a2edc  mov     edx, 10EAh; void *
0x1800a2ee1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a2ee6  lea     rcx, [rbp+57h+var_40]
0x1800a2eea  call    wil__details__unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t______unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t___
0x1800a2eef  nop
0x1800a2ef0  mov     rcx, [rbp+57h+pProxy]
0x1800a2ef4  test    rcx, rcx
0x1800a2ef7  jz      short loc_1800A2F0A
0x1800a2ef9  mov     [rbp+57h+pProxy], rsi
0x1800a2efd  mov     rax, [rcx]
0x1800a2f00  mov     rax, [rax+10h]
0x1800a2f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f09  nop
0x1800a2f0a  mov     rcx, [rbp+57h+var_48]
0x1800a2f0e  test    rcx, rcx
0x1800a2f11  jz      short loc_1800A2F24
0x1800a2f13  mov     [rbp+57h+var_48], rsi
0x1800a2f17  mov     rax, [rcx]
0x1800a2f1a  mov     rax, [rax+10h]
0x1800a2f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f23  nop
0x1800a2f24  jmp     short loc_1800A2F87
0x1800a2f26  mov     eax, cs:dword_1801BD288
0x1800a2f2c  cmp     eax, 5
0x1800a2f2f  jbe     short loc_1800A2F49
0x1800a2f31  mov     dword ptr [rbp+57h+var_60], ebx
0x1800a2f34  lea     rax, [rbp+57h+var_60]
0x1800a2f38  mov     [rsp+0A0h+ppv], rax
0x1800a2f3d  lea     rdx, unk_18018CDC0
0x1800a2f44  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800a2f49  lea     rcx, [rbp+57h+var_40]
0x1800a2f4d  call    wil__details__unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t______unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t___
0x1800a2f52  nop
0x1800a2f53  mov     rcx, [rbp+57h+pProxy]
0x1800a2f57  test    rcx, rcx
0x1800a2f5a  jz      short loc_1800A2F6D
0x1800a2f5c  mov     [rbp+57h+pProxy], rsi
0x1800a2f60  mov     rax, [rcx]
0x1800a2f63  mov     rax, [rax+10h]
0x1800a2f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f6c  nop
0x1800a2f6d  mov     rcx, [rbp+57h+var_48]
0x1800a2f71  test    rcx, rcx
0x1800a2f74  jz      short loc_1800A2F87
0x1800a2f76  mov     [rbp+57h+var_48], rsi
0x1800a2f7a  mov     rax, [rcx]
0x1800a2f7d  mov     rax, [rax+10h]
0x1800a2f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f86  nop
0x1800a2f87  mov     rcx, [rbp+57h+var_50]
0x1800a2f8b  test    rcx, rcx
0x1800a2f8e  jz      short loc_1800A2FA1
0x1800a2f90  mov     [rbp+57h+var_50], rsi
0x1800a2f94  mov     rax, [rcx]
0x1800a2f97  mov     rax, [rax+10h]
0x1800a2f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2fa0  nop
0x1800a2fa1  jmp     loc_1800A3130
0x1800a2fa6  mov     edi, esi
0x1800a2fa8  mov     rcx, [rbp+57h+pProxy]
0x1800a2fac  mov     rax, [rcx]
0x1800a2faf  mov     rax, [rax+18h]
0x1800a2fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2fb8  mov     ebx, eax
0x1800a2fba  test    eax, eax
0x1800a2fbc  jns     loc_1800A30BC
0x1800a2fc2  cmp     eax, 800704D5h
0x1800a2fc7  jnz     short loc_1800A303F
0x1800a2fc9  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800a2fce  call    cs:__imp_Sleep
0x1800a2fd4  inc     edi
0x1800a2fd6  cmp     edi, 5
0x1800a2fd9  jb      short loc_1800A2FA8
0x1800a2fdb  mov     rcx, [rbp+5Fh]; this
0x1800a2fdf  lea     rax, aResetnetworkad; "ResetNetworkAdapter - Enabling network "...
0x1800a2fe6  mov     [rsp+0A0h+ppv], rax; int
0x1800a2feb  mov     r9d, ebx; char *
0x1800a2fee  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x1800a2ff5  mov     edx, 10FBh; void *
0x1800a2ffa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a2fff  lea     rcx, [rbp+57h+var_40]
0x1800a3003  call    wil__details__unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t______unique_storage_wil__details__resource_policy_tagNETCON_PROPERTIES___void____cdecl___tagNETCON_PROPERTIES_____FreeNetConProperties_wistd__integral_constant_unsigned___int64_0__tagNETCON_PROPERTIES___tagNETCON_PROPERTIES___0_std__nullptr_t___
0x1800a3008  nop
0x1800a3009  mov     rcx, [rbp+57h+pProxy]
0x1800a300d  test    rcx, rcx
0x1800a3010  jz      short loc_1800A3023
0x1800a3012  mov     [rbp+57h+pProxy], rsi
0x1800a3016  mov     rax, [rcx]
0x1800a3019  mov     rax, [rax+10h]
0x1800a301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3022  nop
0x1800a3023  mov     rcx, [rbp+57h+var_48]
0x1800a3027  test    rcx, rcx
0x1800a302a  jz      short loc_1800A303D
0x1800a302c  mov     [rbp+57h+var_48], rsi
0x1800a3030  mov     rax, [rcx]
0x1800a3033  mov     rax, [rax+10h]
0x1800a3037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a303c  nop
0x1800a303d  jmp     short loc_1800A30A0
  ... truncated ...
```
