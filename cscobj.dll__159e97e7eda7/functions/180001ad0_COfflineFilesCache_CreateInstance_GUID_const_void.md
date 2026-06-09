# COfflineFilesCache::CreateInstance(_GUID const &,void * *)

- ea: `0x180001ad0`
- end: `0x18000202f`
- name: `?CreateInstance@COfflineFilesCache@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `1375`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011140`

## callees

- `0x180001ad0`
- `0x180002040`
- `0x180002078`
- `0x18000b390`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180001ca4`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180001d71`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180001ca4`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180001d71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001e9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001e9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180001bc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180001bc2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001cf4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001dba`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001f9e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001ff3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001cf4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001dba`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001f9e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180001ff3`
- `CSCAPI!OfflineFilesQueryStatusEx` at `0x180001c0a`
- `CSCAPI!OfflineFilesQueryStatusEx` at `0x180001c0a`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::CreateInstance(const struct _GUID *a1, void **a2)
{
  int v4; // ebx
  const struct _GUID *v5; // rdx
  char *v6; // rdi
  DWORD v7; // r8d
  const IID *v8; // rcx
  HRESULT v9; // r14d
  int v10; // esi
  IUnknown *pItf; // r15
  HRESULT v13; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT v15; // eax
  __int64 v16; // r14
  HRESULT v17; // r15d
  _QWORD *v18; // rcx
  __int64 v19; // rax
  CUserSessionCallback *v20; // rax
  CUserSessionCallback *v21; // rax
  CUserSessionCallback *v22; // rsi
  DWORD pwAuthnSvc; // [rsp+40h] [rbp-69h] BYREF
  DWORD pImpLevel; // [rsp+44h] [rbp-65h] BYREF
  DWORD pAuthnLevel; // [rsp+48h] [rbp-61h] BYREF
  __int64 v26; // [rsp+50h] [rbp-59h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp-51h] BYREF
  IUnknown *v28; // [rsp+60h] [rbp-49h]
  MULTI_QI pResults; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v30[2]; // [rsp+80h] [rbp-29h] BYREF
  int v31; // [rsp+90h] [rbp-19h]
  int v32; // [rsp+94h] [rbp-15h]
  __int64 v33; // [rsp+98h] [rbp-11h]
  __int64 v34; // [rsp+A0h] [rbp-9h]
  COSERVERINFO pServerInfo; // [rsp+A8h] [rbp-1h] BYREF
  LPVOID dwCapabilities; // [rsp+120h] [rbp+77h] BYREF
  DWORD pAuthzSvc; // [rsp+128h] [rbp+7Fh] BYREF

  v4 = -2147024882;
  v6 = (char *)operator new(0x48u);
  if ( !v6 )
    return (unsigned int)v4;
  *(_QWORD *)v6 = &COfflineFilesCache::`vftable'{for `IOfflineFilesCache2'};
  *((_QWORD *)v6 + 1) = &COfflineFilesCache::`vftable'{for `IOfflineFilesItemContainer'};
  *((_QWORD *)v6 + 2) = &COfflineFilesCache::`vftable'{for `IConnectionPointContainer'};
  *((_DWORD *)v6 + 6) = 1;
  CObjectInGIT_SvcObj::CObjectInGIT_SvcObj((CObjectInGIT_SvcObj *)(v6 + 32), v5);
  _InterlockedIncrement(&g_cRefDll);
  v7 = *((_DWORD *)v6 + 16);
  v8 = (const IID *)*((_QWORD *)v6 + 7);
  pServerInfo.pAuthInfo = (COAUTHINFO *)v30;
  v26 = 0;
  pResults.pIID = &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce;
  v30[0] = -1;
  v30[1] = 0;
  v31 = 6;
  v32 = 3;
  v33 = 0;
  v34 = 0;
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pServerInfo.pwszName = 0;
  *(_QWORD *)&pServerInfo.dwReserved2 = 0;
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v9 = CoCreateInstanceEx(v8, 0, v7, &pServerInfo, 1u, &pResults);
  if ( v9 < 0 )
    goto LABEL_3;
  pItf = pResults.pItf;
  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  pAuthnLevel = 0;
  pImpLevel = 0;
  LODWORD(dwCapabilities) = 0;
  v13 = CoQueryProxyBlanket(
          pResults.pItf,
          &pwAuthnSvc,
          &pAuthzSvc,
          0,
          &pAuthnLevel,
          &pImpLevel,
          0,
          (DWORD *)&dwCapabilities);
  v10 = -2147467262;
  v9 = v13;
  if ( v13 != -2147467262 )
  {
    if ( v13 < 0 )
      goto LABEL_41;
    if ( CoSetProxyBlanket(pItf, pwAuthnSvc, pAuthzSvc, 0, 6u, 3u, 0, (unsigned int)dwCapabilities & 0xFFFFFF9F | 0x40) < 0 )
    {
      v9 = CoSetProxyBlanket(pItf, pwAuthnSvc, pAuthzSvc, 0, pAuthnLevel, pImpLevel, 0, (DWORD)dwCapabilities);
      if ( v9 < 0 )
        goto LABEL_41;
    }
  }
  lpVtbl = pItf->lpVtbl;
  pProxy = 0;
  v9 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))lpVtbl->QueryInterface)(pItf, &IID_IUnknown, &pProxy);
  if ( v9 < 0 )
    goto LABEL_41;
  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  pImpLevel = 0;
  pAuthnLevel = 0;
  LODWORD(dwCapabilities) = 0;
  v28 = pProxy;
  v15 = CoQueryProxyBlanket(pProxy, &pwAuthnSvc, &pAuthzSvc, 0, &pImpLevel, &pAuthnLevel, 0, (DWORD *)&dwCapabilities);
  v9 = v15;
  if ( v15 == -2147467262 )
  {
    v9 = 0;
  }
  else if ( v15 >= 0 )
  {
    v9 = CoSetProxyBlanket(v28, pwAuthnSvc, pAuthzSvc, 0, 6u, 3u, 0, (unsigned int)dwCapabilities & 0xFFFFFF9F | 0x40);
    if ( v9 < 0 )
      v9 = CoSetProxyBlanket(v28, pwAuthnSvc, pAuthzSvc, 0, pImpLevel, pAuthnLevel, 0, (DWORD)dwCapabilities);
  }
  ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))pItf->lpVtbl->QueryInterface)(
           pItf,
           &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
           &v26);
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    if ( v9 >= 0 )
    {
      v16 = v26;
      v17 = -2147024809;
      if ( v26 )
      {
        v18 = (_QWORD *)*((_QWORD *)v6 + 5);
        v19 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v18;
        if ( *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 == *v18 )
          v19 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v18[1];
        if ( v19 )
          goto LABEL_28;
        if ( *((_DWORD *)v6 + 12) )
        {
          v10 = -2147467259;
LABEL_28:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v26 = 0;
          goto LABEL_4;
        }
        *((_DWORD *)v6 + 12) = 0;
        dwCapabilities = 0;
        v17 = CoCreateInstance(
                &CLSID_StdGlobalInterfaceTable,
                0,
                1u,
                &GUID_00000146_0000_0000_c000_000000000046,
                &dwCapabilities);
        if ( v17 >= 0 )
        {
          v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, char *))(*(_QWORD *)dwCapabilities + 24LL))(
                  dwCapabilities,
                  v16,
                  &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
                  v6 + 48);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)dwCapabilities + 16LL))(dwCapabilities);
        }
        if ( v17 >= 0 )
        {
          dwCapabilities = 0;
          v20 = (CUserSessionCallback *)operator new(0x10u);
          if ( v20 )
          {
            v21 = CUserSessionCallback::CUserSessionCallback(v20);
            v22 = v21;
            if ( v21 )
            {
              v4 = (**(__int64 (__fastcall ***)(CUserSessionCallback *, GUID *, LPVOID *))v21)(
                     v21,
                     &GUID_f1ffcfc0_73e1_441b_a0c5_ba94d43e1acc,
                     &dwCapabilities);
              (*(void (__fastcall **)(CUserSessionCallback *))(*(_QWORD *)v22 + 16LL))(v22);
            }
            if ( v4 >= 0 )
            {
              (*(void (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v26 + 24LL))(v26, dwCapabilities);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)dwCapabilities + 16LL))(dwCapabilities);
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          goto LABEL_5;
        }
        *((_DWORD *)v6 + 12) = 0;
      }
      v10 = v17;
      goto LABEL_28;
    }
  }
  else
  {
LABEL_41:
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
  }
LABEL_3:
  v10 = v9;
LABEL_4:
  v4 = v10;
LABEL_5:
  if ( v4 == -2147024891 )
  {
    pAuthzSvc = 0;
    LODWORD(dwCapabilities) = 0;
    if ( !(unsigned int)OfflineFilesQueryStatusEx(&pAuthzSvc, 0, &dwCapabilities) )
    {
      if ( (_DWORD)dwCapabilities )
      {
        v4 = -2147023834;
      }
      else if ( !pAuthzSvc )
      {
        v4 = -2147023838;
      }
    }
  }
  else if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v6)(v6, a1, a2);
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001ad0  push    rbp
0x180001ad2  push    rbx
0x180001ad3  push    rdi
0x180001ad4  push    r12
0x180001ad6  push    r13
0x180001ad8  lea     rbp, [rsp-37h]
0x180001add  sub     rsp, 0E0h
0x180001ae4  mov     r13, rcx
0x180001ae7  mov     r12, rdx
0x180001aea  mov     ecx, 48h ; 'H'; Size
0x180001aef  mov     ebx, 8007000Eh
0x180001af4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001af9  mov     rdi, rax
0x180001afc  test    rax, rax
0x180001aff  jz      loc_180001C52
0x180001b05  lea     rax, ??_7COfflineFilesCache@@6BIOfflineFilesCache2@@@; const COfflineFilesCache::`vftable'{for `IOfflineFilesCache2'}
0x180001b0c  mov     [rsp+100h+arg_0], rsi
0x180001b14  mov     [rdi], rax
0x180001b17  lea     rcx, [rdi+20h]; this
0x180001b1b  lea     rax, ??_7COfflineFilesCache@@6BIOfflineFilesItemContainer@@@; const COfflineFilesCache::`vftable'{for `IOfflineFilesItemContainer'}
0x180001b22  mov     [rsp+100h+var_28], r14
0x180001b2a  mov     [rdi+8], rax
0x180001b2e  lea     rax, ??_7COfflineFilesCache@@6BIConnectionPointContainer@@@; const COfflineFilesCache::`vftable'{for `IConnectionPointContainer'}
0x180001b35  mov     [rdi+10h], rax
0x180001b39  mov     [rsp+100h+var_30], r15
0x180001b41  mov     dword ptr [rdi+18h], 1
0x180001b48  call    ??0CObjectInGIT_SvcObj@@QEAA@AEBU_GUID@@@Z; CObjectInGIT_SvcObj::CObjectInGIT_SvcObj(_GUID const &)
0x180001b4d  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180001b54  mov     r8d, [rdi+40h]; dwClsCtx
0x180001b58  lea     rax, [rbp+57h+var_80]
0x180001b5c  mov     rcx, [rdi+38h]; Clsid
0x180001b60  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180001b64  xor     esi, esi
0x180001b66  mov     [rbp+57h+pServerInfo.pAuthInfo], rax
0x180001b6a  lea     rax, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180001b71  mov     [rbp+57h+var_B0], rsi
0x180001b75  mov     [rbp+57h+var_98.pIID], rax
0x180001b79  xor     edx, edx; punkOuter
0x180001b7b  lea     rax, [rbp+57h+var_98]
0x180001b7f  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x180001b87  mov     [rsp+100h+pResults], rax; pResults
0x180001b8c  mov     [rsp+100h+dwCount], 1; dwCount
0x180001b94  mov     [rbp+57h+var_78], rsi
0x180001b98  mov     [rbp+57h+var_70], 6
0x180001b9f  mov     [rbp+57h+var_6C], 3
0x180001ba6  mov     [rbp+57h+var_68], rsi
0x180001baa  mov     [rbp+57h+var_60], rsi
0x180001bae  mov     qword ptr [rbp+57h+pServerInfo.dwReserved1], rsi
0x180001bb2  mov     [rbp+57h+pServerInfo.pwszName], rsi
0x180001bb6  mov     qword ptr [rbp+57h+pServerInfo.dwReserved2], rsi
0x180001bba  mov     [rbp+57h+var_98.pItf], rsi
0x180001bbe  mov     qword ptr [rbp+57h+var_98.hr], rsi
0x180001bc2  call    cs:__imp_CoCreateInstanceEx
0x180001bc8  mov     r14d, eax
0x180001bcb  test    eax, eax
0x180001bcd  jns     loc_180001C63
0x180001bd3  mov     esi, r14d
0x180001bd6  mov     ebx, esi
0x180001bd8  mov     r15, [rsp+100h+var_30]
0x180001be0  mov     r14, [rsp+100h+var_28]
0x180001be8  mov     rsi, [rsp+100h+arg_0]
0x180001bf0  cmp     ebx, 80070005h
0x180001bf6  jnz     short loc_180001C29
0x180001bf8  xor     eax, eax
0x180001bfa  lea     r8, [rbp+57h+dwCapabilities]
0x180001bfe  xor     edx, edx
0x180001c00  mov     [rbp+57h+pAuthzSvc], eax
0x180001c03  lea     rcx, [rbp+57h+pAuthzSvc]
0x180001c07  mov     dword ptr [rbp+57h+dwCapabilities], eax
0x180001c0a  call    cs:__imp_OfflineFilesQueryStatusEx
0x180001c10  test    eax, eax
0x180001c12  jnz     short loc_180001C43
0x180001c14  cmp     dword ptr [rbp+57h+dwCapabilities], eax
0x180001c17  jnz     loc_180002025
0x180001c1d  cmp     [rbp+57h+pAuthzSvc], eax
0x180001c20  jnz     short loc_180001C43
0x180001c22  mov     ebx, 80070422h
0x180001c27  jmp     short loc_180001C43
0x180001c29  test    ebx, ebx
0x180001c2b  js      short loc_180001C43
0x180001c2d  mov     rax, [rdi]
0x180001c30  mov     r8, r12
0x180001c33  mov     rdx, r13
0x180001c36  mov     rcx, rdi
0x180001c39  mov     rax, [rax]
0x180001c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c41  mov     ebx, eax
0x180001c43  mov     rax, [rdi]
0x180001c46  mov     rcx, rdi
0x180001c49  mov     rax, [rax+10h]
0x180001c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c52  mov     eax, ebx
0x180001c54  add     rsp, 0E0h
0x180001c5b  pop     r13
0x180001c5d  pop     r12
0x180001c5f  pop     rdi
0x180001c60  pop     rbx
0x180001c61  pop     rbp
0x180001c62  retn
0x180001c63  mov     r15, [rbp+57h+var_98.pItf]
0x180001c67  lea     rax, [rbp+57h+dwCapabilities]
0x180001c6b  mov     [rsp+100h+pCapabilites], rax; pCapabilites
0x180001c70  lea     r8, [rbp+57h+pAuthzSvc]; pAuthzSvc
0x180001c74  lea     rax, [rbp+57h+pImpLevel]
0x180001c78  mov     [rsp+100h+pAuthInfo], rsi; pAuthInfo
0x180001c7d  mov     [rsp+100h+pResults], rax; pImpLevel
0x180001c82  lea     rdx, [rbp+57h+pwAuthnSvc]; pwAuthnSvc
0x180001c86  lea     rax, [rbp+57h+pAuthnLevel]
0x180001c8a  mov     [rbp+57h+pwAuthnSvc], esi
0x180001c8d  xor     r9d, r9d; pServerPrincName
0x180001c90  mov     qword ptr [rsp+100h+dwCount], rax; pAuthnLevel
0x180001c95  mov     rcx, r15; pProxy
0x180001c98  mov     [rbp+57h+pAuthzSvc], esi
0x180001c9b  mov     [rbp+57h+pAuthnLevel], esi
0x180001c9e  mov     [rbp+57h+pImpLevel], esi
0x180001ca1  mov     dword ptr [rbp+57h+dwCapabilities], esi
0x180001ca4  call    cs:__imp_CoQueryProxyBlanket
0x180001caa  mov     esi, 80004002h
0x180001caf  mov     r14d, eax
0x180001cb2  cmp     eax, esi
0x180001cb4  jz      loc_180001FBF
0x180001cba  test    eax, eax
0x180001cbc  js      loc_180001FAB
0x180001cc2  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x180001cc5  xor     r14d, r14d
0x180001cc8  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x180001ccc  and     eax, 0FFFFFFDFh
0x180001ccf  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x180001cd2  or      eax, 40h
0x180001cd5  mov     dword ptr [rsp+100h+pCapabilites], eax; dwCapabilities
0x180001cd9  xor     r9d, r9d; pServerPrincName
0x180001cdc  mov     [rsp+100h+pAuthInfo], r14; pAuthInfo
0x180001ce1  mov     rcx, r15; pProxy
0x180001ce4  mov     dword ptr [rsp+100h+pResults], 3; dwImpLevel
0x180001cec  mov     [rsp+100h+dwCount], 6; dwAuthnLevel
0x180001cf4  call    cs:__imp_CoSetProxyBlanket
0x180001cfa  test    eax, eax
0x180001cfc  js      loc_180001F77
0x180001d02  mov     rax, [r15]
0x180001d05  lea     r8, [rbp+57h+pProxy]
0x180001d09  lea     rdx, IID_IUnknown
0x180001d10  mov     [rbp+57h+pProxy], r14
0x180001d14  mov     rcx, r15
0x180001d17  mov     rax, [rax]
0x180001d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d1f  mov     r14d, eax
0x180001d22  test    eax, eax
0x180001d24  js      loc_180001FAB
0x180001d2a  mov     rax, [rbp+57h+pProxy]
0x180001d2e  lea     rcx, [rbp+57h+dwCapabilities]
0x180001d32  xor     edx, edx
0x180001d34  mov     [rsp+100h+pCapabilites], rcx; pCapabilites
0x180001d39  mov     [rsp+100h+pAuthInfo], rdx; pAuthInfo
0x180001d3e  lea     rcx, [rbp+57h+pAuthnLevel]
0x180001d42  mov     [rsp+100h+pResults], rcx; pImpLevel
0x180001d47  lea     r8, [rbp+57h+pAuthzSvc]; pAuthzSvc
0x180001d4b  lea     rcx, [rbp+57h+pImpLevel]
0x180001d4f  mov     [rbp+57h+pwAuthnSvc], edx
0x180001d52  mov     qword ptr [rsp+100h+dwCount], rcx; pAuthnLevel
0x180001d57  xor     r9d, r9d; pServerPrincName
0x180001d5a  mov     [rbp+57h+pAuthzSvc], edx
0x180001d5d  mov     rcx, rax; pProxy
0x180001d60  mov     [rbp+57h+pImpLevel], edx
0x180001d63  mov     [rbp+57h+pAuthnLevel], edx
0x180001d66  mov     dword ptr [rbp+57h+dwCapabilities], edx
0x180001d69  lea     rdx, [rbp+57h+pwAuthnSvc]; pwAuthnSvc
0x180001d6d  mov     [rbp+57h+var_A0], rax
0x180001d71  call    cs:__imp_CoQueryProxyBlanket
0x180001d77  mov     r14d, eax
0x180001d7a  cmp     eax, esi
0x180001d7c  jz      loc_180001F6F
0x180001d82  test    eax, eax
0x180001d84  js      short loc_180001DCB
0x180001d86  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x180001d89  xor     r9d, r9d; pServerPrincName
0x180001d8c  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x180001d90  and     eax, 0FFFFFFDFh
0x180001d93  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x180001d96  or      eax, 40h
0x180001d99  mov     rcx, [rbp+57h+var_A0]; pProxy
0x180001d9d  mov     dword ptr [rsp+100h+pCapabilites], eax; dwCapabilities
0x180001da1  mov     [rsp+100h+pAuthInfo], 0; pAuthInfo
0x180001daa  mov     dword ptr [rsp+100h+pResults], 3; dwImpLevel
0x180001db2  mov     [rsp+100h+dwCount], 6; dwAuthnLevel
0x180001dba  call    cs:__imp_CoSetProxyBlanket
0x180001dc0  mov     r14d, eax
0x180001dc3  test    eax, eax
0x180001dc5  js      loc_180001FC7
0x180001dcb  mov     rcx, [rbp+57h+pProxy]
0x180001dcf  mov     rax, [rcx]
0x180001dd2  mov     rax, [rax+10h]
0x180001dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ddb  test    r14d, r14d
0x180001dde  js      loc_180001FAB
0x180001de4  mov     rax, [r15]
0x180001de7  lea     r8, [rbp+57h+var_B0]
0x180001deb  lea     rdx, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180001df2  mov     rcx, r15
0x180001df5  mov     rax, [rax]
0x180001df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dfd  mov     r14d, eax
0x180001e00  mov     rcx, r15
0x180001e03  mov     rax, [r15]
0x180001e06  mov     rax, [rax+10h]
0x180001e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e0f  test    r14d, r14d
0x180001e12  js      loc_180001BD3
0x180001e18  mov     r14, [rbp+57h+var_B0]
0x180001e1c  mov     r15d, 80070057h
0x180001e22  test    r14, r14
0x180001e25  jz      loc_180002014
0x180001e2b  mov     rcx, [rdi+28h]
0x180001e2f  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x180001e36  sub     rax, [rcx]
0x180001e39  jnz     short loc_180001E46
0x180001e3b  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x180001e42  sub     rax, [rcx+8]
0x180001e46  test    rax, rax
0x180001e49  jz      short loc_180001E6A
0x180001e4b  mov     rax, [r14]
0x180001e4e  mov     rcx, r14
0x180001e51  mov     rax, [rax+10h]
0x180001e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e5a  xor     eax, eax
0x180001e5c  mov     [rbp+57h+var_B0], rax
0x180001e60  test    esi, esi
0x180001e62  js      loc_180001BD6
0x180001e68  jmp     short loc_180001EE5
0x180001e6a  cmp     dword ptr [rdi+30h], 0
0x180001e6e  jnz     loc_180002001
0x180001e74  xor     eax, eax
0x180001e76  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180001e7d  mov     [rdi+30h], eax
0x180001e80  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180001e87  mov     [rbp+57h+dwCapabilities], rax
0x180001e8b  xor     edx, edx; pUnkOuter
0x180001e8d  lea     rax, [rbp+57h+dwCapabilities]
0x180001e91  mov     r8d, 1; dwClsContext
0x180001e97  mov     qword ptr [rsp+100h+dwCount], rax; ppv
0x180001e9c  call    cs:__imp_CoCreateInstance
0x180001ea2  mov     r15d, eax
0x180001ea5  test    eax, eax
0x180001ea7  js      short loc_180001EDA
0x180001ea9  mov     rcx, [rbp+57h+dwCapabilities]
0x180001ead  lea     r9, [rdi+30h]
0x180001eb1  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180001eb8  mov     rdx, r14
0x180001ebb  mov     rax, [rcx]
0x180001ebe  mov     rax, [rax+18h]
0x180001ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec7  mov     rcx, [rbp+57h+dwCapabilities]
0x180001ecb  mov     r15d, eax
0x180001ece  mov     rax, [rcx]
0x180001ed1  mov     rax, [rax+10h]
0x180001ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eda  test    r15d, r15d
0x180001edd  js      loc_18000200B
0x180001ee3  xor     eax, eax
0x180001ee5  mov     ecx, 10h; Size
0x180001eea  mov     [rbp+57h+dwCapabilities], rax
0x180001eee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ef3  test    rax, rax
0x180001ef6  jz      short loc_180001F5A
0x180001ef8  mov     rcx, rax; this
0x180001efb  call    ??0CUserSessionCallback@@AEAA@XZ; CUserSessionCallback::CUserSessionCallback(void)
0x180001f00  mov     rsi, rax
0x180001f03  test    rax, rax
0x180001f06  jz      short loc_180001F32
0x180001f08  mov     rcx, [rax]
0x180001f0b  lea     r8, [rbp+57h+dwCapabilities]
0x180001f0f  lea     rdx, _GUID_f1ffcfc0_73e1_441b_a0c5_ba94d43e1acc
0x180001f16  mov     rax, [rcx]
0x180001f19  mov     rcx, rsi
0x180001f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f21  mov     rcx, [rsi]
0x180001f24  mov     ebx, eax
0x180001f26  mov     rax, [rcx+10h]
0x180001f2a  mov     rcx, rsi
0x180001f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f32  test    ebx, ebx
0x180001f34  js      short loc_180001F5A
0x180001f36  mov     rcx, [rbp+57h+var_B0]
0x180001f3a  mov     rdx, [rbp+57h+dwCapabilities]
0x180001f3e  mov     rax, [rcx]
0x180001f41  mov     rax, [rax+18h]
0x180001f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f4a  mov     rcx, [rbp+57h+dwCapabilities]
0x180001f4e  mov     rax, [rcx]
0x180001f51  mov     rax, [rax+10h]
0x180001f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f5a  mov     rcx, [rbp+57h+var_B0]
0x180001f5e  mov     rax, [rcx]
0x180001f61  mov     rax, [rax+10h]
0x180001f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6a  jmp     loc_180001BD8
0x180001f6f  xor     r14d, r14d
0x180001f72  jmp     loc_180001DCB
0x180001f77  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x180001f7a  xor     r9d, r9d; pServerPrincName
0x180001f7d  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
  ... truncated ...
```
