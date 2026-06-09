# UserAccountNode::Commit(void)

- ea: `0x180024ba0`
- end: `0x18002521c`
- name: `?Commit@UserAccountNode@@UEAAJXZ`
- size: `1660`
- prototype: `__int64 __fastcall(UserAccountNode *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006974`
- `0x180009eb0`
- `0x1800112a4`
- `0x180024ba0`
- `0x180025224`
- `0x180025dd8`
- `0x18003586a`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024c2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024c2a`
- `OLEAUT32!__imp_SysAllocString` at `0x180024c8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180024c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180024cce`
- `OLEAUT32!__imp_SysFreeString` at `0x180024cce`
- `OLEAUT32!__imp_VariantInit` at `0x180024d40`
- `OLEAUT32!__imp_VariantInit` at `0x180024d40`
- `OLEAUT32!__imp_VariantClear` at `0x180024d8e`
- `OLEAUT32!__imp_VariantClear` at `0x180024e0a`
- `OLEAUT32!__imp_VariantClear` at `0x180024e92`
- `OLEAUT32!__imp_VariantClear` at `0x180024f0e`
- `OLEAUT32!__imp_VariantClear` at `0x180024f5f`
- `OLEAUT32!__imp_VariantClear` at `0x180024d8e`
- `OLEAUT32!__imp_VariantClear` at `0x180024e0a`
- `OLEAUT32!__imp_VariantClear` at `0x180024e92`
- `OLEAUT32!__imp_VariantClear` at `0x180024f0e`
- `OLEAUT32!__imp_VariantClear` at `0x180024f5f`
- `samcli!NetLocalGroupAddMembers` at `0x1800251e4`
- `samcli!NetLocalGroupAddMembers` at `0x1800251e4`
- `samcli!NetUserAdd` at `0x180025186`
- `samcli!NetUserAdd` at `0x180025186`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180024bec`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180024bec`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800250cd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800250cd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180025048`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180025048`

## string_xrefs

- `0x18002520a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall UserAccountNode::Commit(UserAccountNode *this)
{
  HRESULT Instance; // eax
  signed int v3; // ebx
  __int64 *v4; // rcx
  __int64 *v6; // r14
  __int64 v7; // r15
  BSTR v8; // rax
  const char *v9; // r9
  OLECHAR *v10; // rbx
  int v11; // edi
  __int64 v12; // rcx
  __int64 *v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 v17; // rcx
  __int64 *v18; // rcx
  __int64 v19; // rcx
  __int64 *v20; // rcx
  int LocalAccountWithUserManager; // eax
  __int64 v22; // rcx
  __int64 *v23; // rcx
  __int64 v24; // rcx
  __int64 *v25; // rcx
  __int64 v26; // rax
  WELL_KNOWN_SID_TYPE v27; // ecx
  signed int v28; // eax
  __int64 v29; // rdx
  signed int LastError; // eax
  char *v31; // rbx
  char *v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  DWORD v37; // eax
  __int64 v38; // rdx
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  const char *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  DWORD parm_err[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+54h] [rbp-ACh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v47; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE v48[8]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE buf[16]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v50; // [rsp+78h] [rbp-88h]
  __int128 v51; // [rsp+88h] [rbp-78h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  _BYTE pSid[544]; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR Name[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  cbSid = 0;
  v45 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v45, 0);
  if ( v45 != 10 )
  {
    *(_OWORD *)buf = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    parm_err[0] = 0;
    memset_0(pSid, 0, sizeof(pSid));
    cbSid = 68;
    cchName[0] = 256;
    Name[256] = 0;
    v47 = 15;
    peUse = 0;
    v26 = *((_QWORD *)this + 8);
    if ( !v26 || (v27 = WinBuiltinAdministratorsSid, *(_DWORD *)(v26 + 24) != 2) )
      v27 = WinBuiltinUsersSid;
    if ( CreateWellKnownSid(v27, 0, pSid, &cbSid) )
    {
      if ( LookupAccountSidW(0, pSid, Name, cchName, &pvarg.vt, &v47, &peUse) )
      {
        v31 = (char *)this + 16;
        if ( *((_QWORD *)this + 5) < 8u )
          v32 = (char *)this + 16;
        else
          v32 = *(char **)v31;
        *(_QWORD *)buf = v32;
        v33 = *((_QWORD *)this + 7);
        if ( v33 )
        {
          v34 = (_QWORD *)(v33 + 24);
          if ( v34[3] >= 8u )
            v34 = (_QWORD *)*v34;
          *(_QWORD *)&buf[8] = v34;
          DWORD1(v50) = 1;
          DWORD2(v51) = 512;
          v35 = *((_QWORD *)this + 9);
          if ( v35 )
          {
            v36 = (_QWORD *)(v35 + 24);
            if ( v36[3] >= 8u )
              v36 = (_QWORD *)*v36;
            *((_QWORD *)&v50 + 1) = v36;
          }
          v37 = NetUserAdd(0, 1u, buf, parm_err);
          if ( v37 == 2224 || !v37 )
          {
            if ( *((_QWORD *)this + 5) >= 8u )
              v31 = *(char **)v31;
            *(_QWORD *)v48 = v31;
            v37 = NetLocalGroupAddMembers(0, Name, 3u, v48, 1u);
            if ( v37 == 1378 || !v37 )
              return 0;
            v38 = 186;
          }
          else
          {
            v38 = 176;
          }
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v38,
                   (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
                   (const char *)v37,
                   ppv);
        }
        v3 = -2147024809;
        v29 = 163;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          return v3;
        v29 = 157;
      }
    }
    else
    {
      v28 = GetLastError();
      v3 = v28;
      if ( v28 > 0 )
        v3 = (unsigned __int16)v28 | 0x80070000;
      if ( v3 >= 0 )
        return v3;
      v29 = 153;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
      (const char *)(unsigned int)v3,
      ppv);
    return v3;
  }
  *(_QWORD *)parm_err = 0;
  Instance = CoCreateInstance(
               &GUID_66d0db14_5638_475f_a386_629522d8c461,
               0,
               1u,
               &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
               (LPVOID *)parm_err);
  v3 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    v4 = *(__int64 **)parm_err;
    if ( *(_QWORD *)parm_err )
    {
      *(_QWORD *)parm_err = 0;
      (*(void (__fastcall **)(__int64 *))(*v4 + 16))(v4);
    }
    return v3;
  }
  *(_QWORD *)cchName = 0;
  v6 = *(__int64 **)parm_err;
  v7 = **(_QWORD **)parm_err;
  v8 = SysAllocString(L"./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE");
  v10 = v8;
  *(_QWORD *)v48 = v8;
  cbSid = 1;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  v11 = (*(__int64 (__fastcall **)(__int64 *, BSTR, DWORD *))(v7 + 80))(v6, v8, cchName);
  SysFreeString(v10);
  if ( v11 >= 0 )
  {
    VariantInit(&pvarg);
    v14 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *))(**(_QWORD **)cchName + 104LL))(*(_QWORD *)cchName, &pvarg);
    v3 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
        (const char *)(unsigned int)v14,
        ppva);
      VariantClear(&pvarg);
      v15 = *(_QWORD *)cchName;
      if ( *(_QWORD *)cchName )
      {
        *(_QWORD *)cchName = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = *(__int64 **)parm_err;
      if ( *(_QWORD *)parm_err )
      {
        *(_QWORD *)parm_err = 0;
        (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
      }
      return v3;
    }
    if ( pvarg.vt != 11 )
    {
      v3 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
        (const char *)0x8000FFFFLL,
        ppva);
      VariantClear(&pvarg);
      v17 = *(_QWORD *)cchName;
      if ( *(_QWORD *)cchName )
      {
        *(_QWORD *)cchName = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = *(__int64 **)parm_err;
      if ( *(_QWORD *)parm_err )
      {
        *(_QWORD *)parm_err = 0;
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      }
      return v3;
    }
    if ( pvarg.iVal == -1 )
    {
      v3 = -2147024891;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
        (const char *)0x80070005LL,
        (int)"Skipping local user creation, tenant lockdown is set.",
        cchReferencedDomainName);
      VariantClear(&pvarg);
      v19 = *(_QWORD *)cchName;
      if ( *(_QWORD *)cchName )
      {
        *(_QWORD *)cchName = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v20 = *(__int64 **)parm_err;
      if ( *(_QWORD *)parm_err )
      {
        *(_QWORD *)parm_err = 0;
        (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
      }
      return v3;
    }
    LocalAccountWithUserManager = UserAccountNode::CreateLocalAccountWithUserManager((UserAccountNode *)((char *)this - 8));
    v3 = LocalAccountWithUserManager;
    if ( LocalAccountWithUserManager < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
        (const char *)(unsigned int)LocalAccountWithUserManager,
        ppva);
      VariantClear(&pvarg);
      v22 = *(_QWORD *)cchName;
      if ( *(_QWORD *)cchName )
      {
        *(_QWORD *)cchName = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = *(__int64 **)parm_err;
      if ( *(_QWORD *)parm_err )
      {
        *(_QWORD *)parm_err = 0;
        (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
      }
      return v3;
    }
    VariantClear(&pvarg);
    v24 = *(_QWORD *)cchName;
    if ( *(_QWORD *)cchName )
    {
      *(_QWORD *)cchName = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = *(__int64 **)parm_err;
    if ( *(_QWORD *)parm_err )
    {
      *(_QWORD *)parm_err = 0;
      (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6F,
    (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
    (const char *)(unsigned int)v11,
    ppva);
  v12 = *(_QWORD *)cchName;
  if ( *(_QWORD *)cchName )
  {
    *(_QWORD *)cchName = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = *(__int64 **)parm_err;
  if ( *(_QWORD *)parm_err )
  {
    *(_QWORD *)parm_err = 0;
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  }
  return v11;
}

```

## disassembly

```asm
0x180024ba0  mov     [rsp-8+arg_8], rbx
0x180024ba5  mov     [rsp-8+arg_10], rsi
0x180024baa  push    rbp
0x180024bab  push    rdi
0x180024bac  push    r12
0x180024bae  push    r14
0x180024bb0  push    r15
0x180024bb2  lea     rbp, [rsp-400h]
0x180024bba  sub     rsp, 500h
0x180024bc1  mov     rax, cs:__security_cookie
0x180024bc8  xor     rax, rsp
0x180024bcb  mov     [rbp+420h+var_30], rax
0x180024bd2  mov     rsi, rcx
0x180024bd5  xor     r12d, r12d
0x180024bd8  mov     [rsp+520h+cbSid], r12d
0x180024bdd  mov     [rsp+520h+var_4CC], r12d
0x180024be2  xor     r8d, r8d
0x180024be5  lea     rdx, [rsp+520h+var_4CC]
0x180024bea  xor     ecx, ecx
0x180024bec  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180024bf3  nop     dword ptr [rax+rax+00h]
0x180024bf8  cmp     [rsp+520h+var_4CC], 0Ah
0x180024bfd  jnz     loc_180024FD2
0x180024c03  mov     qword ptr [rsp+520h+parm_err], r12
0x180024c08  lea     rax, [rsp+520h+parm_err]
0x180024c0d  mov     [rsp+520h+ppv], rax; int
0x180024c12  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180024c19  lea     edi, [r12+1]
0x180024c1e  mov     r8d, edi; dwClsContext
0x180024c21  xor     edx, edx; pUnkOuter
0x180024c23  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180024c2a  call    cs:__imp_CoCreateInstance
0x180024c31  nop     dword ptr [rax+rax+00h]
0x180024c36  mov     ebx, eax
0x180024c38  test    eax, eax
0x180024c3a  jns     short loc_180024C79
0x180024c3c  mov     rcx, [rbp+428h]; this
0x180024c43  mov     r9d, eax; char *
0x180024c46  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180024c4d  lea     edx, [rdi+6Ah]; void *
0x180024c50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c55  nop
0x180024c56  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024c5b  test    rcx, rcx
0x180024c5e  jz      short loc_180024C72
0x180024c60  mov     qword ptr [rsp+520h+parm_err], r12
0x180024c65  mov     rax, [rcx]
0x180024c68  mov     rax, [rax+10h]
0x180024c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c71  nop
0x180024c72  mov     eax, ebx
0x180024c74  jmp     loc_180024FA6
0x180024c79  mov     qword ptr [rsp+520h+cchName], r12
0x180024c7e  mov     r14, qword ptr [rsp+520h+parm_err]
0x180024c83  mov     r15, [r14]
0x180024c86  lea     rcx, psz; "./Vendor/MSFT/TenantLockdown/RequireNet"...
0x180024c8d  call    cs:__imp_SysAllocString
0x180024c94  nop     dword ptr [rax+rax+00h]
0x180024c99  mov     rbx, rax
0x180024c9c  mov     qword ptr [rsp+520h+var_4C0], rax
0x180024ca1  mov     [rsp+520h+cbSid], edi
0x180024ca5  mov     rcx, [rbp+428h]; this
0x180024cac  test    rax, rax
0x180024caf  jz      loc_18002520A
0x180024cb5  lea     r8, [rsp+520h+cchName]
0x180024cba  mov     rdx, rax
0x180024cbd  mov     rcx, r14
0x180024cc0  mov     rax, [r15+50h]
0x180024cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc9  mov     edi, eax
0x180024ccb  mov     rcx, rbx; bstrString
0x180024cce  call    cs:__imp_SysFreeString
0x180024cd5  nop     dword ptr [rax+rax+00h]
0x180024cda  test    edi, edi
0x180024cdc  jns     short loc_180024D39
0x180024cde  mov     rcx, [rbp+428h]; this
0x180024ce5  mov     r9d, edi; char *
0x180024ce8  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180024cef  mov     edx, 6Fh ; 'o'; void *
0x180024cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024cf9  nop
0x180024cfa  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024cff  test    rcx, rcx
0x180024d02  jz      short loc_180024D16
0x180024d04  mov     qword ptr [rsp+520h+cchName], r12
0x180024d09  mov     rax, [rcx]
0x180024d0c  mov     rax, [rax+10h]
0x180024d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d15  nop
0x180024d16  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024d1b  test    rcx, rcx
0x180024d1e  jz      short loc_180024D32
0x180024d20  mov     qword ptr [rsp+520h+parm_err], r12
0x180024d25  mov     rax, [rcx]
0x180024d28  mov     rax, [rax+10h]
0x180024d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d31  nop
0x180024d32  mov     eax, edi
0x180024d34  jmp     loc_180024FA6
0x180024d39  lea     rcx, [rbp+420h+pvarg]; pvarg
0x180024d40  call    cs:__imp_VariantInit
0x180024d47  nop     dword ptr [rax+rax+00h]
0x180024d4c  nop
0x180024d4d  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024d52  mov     rax, [rcx]
0x180024d55  lea     rdx, [rbp+420h+pvarg]
0x180024d5c  mov     rax, [rax+68h]
0x180024d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d65  mov     ebx, eax
0x180024d67  test    eax, eax
0x180024d69  jns     short loc_180024DD8
0x180024d6b  mov     rcx, [rbp+428h]; this
0x180024d72  mov     r9d, eax; char *
0x180024d75  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180024d7c  mov     edx, 72h ; 'r'; void *
0x180024d81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d86  nop
0x180024d87  lea     rcx, [rbp+420h+pvarg]; pvarg
0x180024d8e  call    cs:__imp_VariantClear
0x180024d95  nop     dword ptr [rax+rax+00h]
0x180024d9a  nop
0x180024d9b  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024da0  test    rcx, rcx
0x180024da3  jz      short loc_180024DB7
0x180024da5  mov     qword ptr [rsp+520h+cchName], r12
0x180024daa  mov     rax, [rcx]
0x180024dad  mov     rax, [rax+10h]
0x180024db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024db6  nop
0x180024db7  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024dbc  test    rcx, rcx
0x180024dbf  jz      short loc_180024DD3
0x180024dc1  mov     qword ptr [rsp+520h+parm_err], r12
0x180024dc6  mov     rax, [rcx]
0x180024dc9  mov     rax, [rax+10h]
0x180024dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dd2  nop
0x180024dd3  jmp     loc_180024C72
0x180024dd8  cmp     word ptr [rbp+420h+pvarg], 0Bh
0x180024de0  jz      short loc_180024E54
0x180024de2  mov     rcx, [rbp+428h]; this
0x180024de9  mov     ebx, 8000FFFFh
0x180024dee  mov     r9d, ebx; char *
0x180024df1  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180024df8  mov     edx, 73h ; 's'; void *
0x180024dfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e02  nop
0x180024e03  lea     rcx, [rbp+420h+pvarg]; pvarg
0x180024e0a  call    cs:__imp_VariantClear
0x180024e11  nop     dword ptr [rax+rax+00h]
0x180024e16  nop
0x180024e17  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024e1c  test    rcx, rcx
0x180024e1f  jz      short loc_180024E33
0x180024e21  mov     qword ptr [rsp+520h+cchName], r12
0x180024e26  mov     rax, [rcx]
0x180024e29  mov     rax, [rax+10h]
0x180024e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e32  nop
0x180024e33  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024e38  test    rcx, rcx
0x180024e3b  jz      short loc_180024E4F
0x180024e3d  mov     qword ptr [rsp+520h+parm_err], r12
0x180024e42  mov     rdx, [rcx]
0x180024e45  mov     rax, [rdx+10h]
0x180024e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e4e  nop
0x180024e4f  jmp     loc_180024C72
0x180024e54  cmp     word ptr [rbp+420h+pvarg+8], 0FFFFh
0x180024e5c  jnz     short loc_180024EDC
0x180024e5e  mov     rcx, [rbp+428h]; this
0x180024e65  lea     rax, aSkippingLocalU; "Skipping local user creation, tenant lo"...
0x180024e6c  mov     [rsp+520h+ppv], rax; int
0x180024e71  mov     ebx, 80070005h
0x180024e76  mov     r9d, ebx; char *
0x180024e79  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180024e80  mov     edx, 78h ; 'x'; void *
0x180024e85  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024e8a  nop
0x180024e8b  lea     rcx, [rbp+420h+pvarg]; pvarg
0x180024e92  call    cs:__imp_VariantClear
0x180024e99  nop     dword ptr [rax+rax+00h]
0x180024e9e  nop
0x180024e9f  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024ea4  test    rcx, rcx
0x180024ea7  jz      short loc_180024EBB
0x180024ea9  mov     qword ptr [rsp+520h+cchName], r12
0x180024eae  mov     rax, [rcx]
0x180024eb1  mov     rax, [rax+10h]
0x180024eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eba  nop
0x180024ebb  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024ec0  test    rcx, rcx
0x180024ec3  jz      short loc_180024ED7
0x180024ec5  mov     qword ptr [rsp+520h+parm_err], r12
0x180024eca  mov     rdx, [rcx]
0x180024ecd  mov     rax, [rdx+10h]
0x180024ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ed6  nop
0x180024ed7  jmp     loc_180024C72
0x180024edc  lea     rcx, [rsi-8]; this
0x180024ee0  call    ?CreateLocalAccountWithUserManager@UserAccountNode@@AEAAJXZ; UserAccountNode::CreateLocalAccountWithUserManager(void)
0x180024ee5  mov     ebx, eax
0x180024ee7  test    eax, eax
0x180024ee9  jns     short loc_180024F58
0x180024eeb  mov     rcx, [rbp+428h]; this
0x180024ef2  mov     r9d, eax; char *
0x180024ef5  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x180024efc  mov     edx, 81h; void *
0x180024f01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024f06  nop
0x180024f07  lea     rcx, [rbp+420h+pvarg]; pvarg
0x180024f0e  call    cs:__imp_VariantClear
0x180024f15  nop     dword ptr [rax+rax+00h]
0x180024f1a  nop
0x180024f1b  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024f20  test    rcx, rcx
0x180024f23  jz      short loc_180024F37
0x180024f25  mov     qword ptr [rsp+520h+cchName], r12
0x180024f2a  mov     rax, [rcx]
0x180024f2d  mov     rax, [rax+10h]
0x180024f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f36  nop
0x180024f37  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024f3c  test    rcx, rcx
0x180024f3f  jz      short loc_180024F53
0x180024f41  mov     qword ptr [rsp+520h+parm_err], r12
0x180024f46  mov     rax, [rcx]
0x180024f49  mov     rax, [rax+10h]
0x180024f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f52  nop
0x180024f53  jmp     loc_180024C72
0x180024f58  lea     rcx, [rbp+420h+pvarg]; pvarg
0x180024f5f  call    cs:__imp_VariantClear
0x180024f66  nop     dword ptr [rax+rax+00h]
0x180024f6b  nop
0x180024f6c  mov     rcx, qword ptr [rsp+520h+cchName]
0x180024f71  test    rcx, rcx
0x180024f74  jz      short loc_180024F88
0x180024f76  mov     qword ptr [rsp+520h+cchName], r12
0x180024f7b  mov     rax, [rcx]
0x180024f7e  mov     rax, [rax+10h]
0x180024f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f87  nop
0x180024f88  mov     rcx, qword ptr [rsp+520h+parm_err]
0x180024f8d  test    rcx, rcx
0x180024f90  jz      short loc_180024FA4
0x180024f92  mov     qword ptr [rsp+520h+parm_err], r12
0x180024f97  mov     rax, [rcx]
0x180024f9a  mov     rax, [rax+10h]
0x180024f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fa3  nop
0x180024fa4  xor     eax, eax
0x180024fa6  mov     rcx, [rbp+420h+var_30]
0x180024fad  xor     rcx, rsp; StackCookie
0x180024fb0  call    __security_check_cookie
0x180024fb5  lea     r11, [rsp+520h+var_20]
0x180024fbd  mov     rbx, [r11+38h]
0x180024fc1  mov     rsi, [r11+40h]
0x180024fc5  mov     rsp, r11
0x180024fc8  pop     r15
0x180024fca  pop     r14
0x180024fcc  pop     r12
0x180024fce  pop     rdi
0x180024fcf  pop     rbp
0x180024fd0  retn
0x180024fd2  xorps   xmm0, xmm0
0x180024fd5  xor     eax, eax
0x180024fd7  movups  xmmword ptr [rsp+520h+buf], xmm0
0x180024fdc  movups  [rsp+520h+var_4A8], xmm0
0x180024fe1  movups  [rbp+420h+var_498], xmm0
0x180024fe5  mov     [rbp+420h+var_488], rax
0x180024fe9  mov     [rsp+520h+parm_err], r12d
0x180024fee  xor     edx, edx; Val
0x180024ff0  mov     r8d, 220h; Size
0x180024ff6  lea     rcx, [rbp+420h+pSid]; void *
0x180024ffa  call    memset_0
0x180024fff  mov     [rsp+520h+cbSid], 44h ; 'D'
0x180025007  mov     [rsp+520h+cchName], 100h
0x18002500f  mov     [rbp+420h+var_40], r12w
0x180025017  mov     [rsp+520h+var_4C4], 0Fh
0x18002501f  mov     [rsp+520h+var_4C8], r12d
0x180025024  mov     rax, [rsi+40h]
0x180025028  test    rax, rax
0x18002502b  jz      short loc_180025038
0x18002502d  cmp     dword ptr [rax+18h], 2
0x180025031  mov     ecx, 1Ah
0x180025036  jz      short loc_18002503D
0x180025038  mov     ecx, 1Bh; WellKnownSidType
0x18002503d  lea     r9, [rsp+520h+cbSid]; cbSid
0x180025042  lea     r8, [rbp+420h+pSid]; pSid
0x180025046  xor     edx, edx; DomainSid
0x180025048  call    cs:__imp_CreateWellKnownSid
0x18002504f  nop     dword ptr [rax+rax+00h]
0x180025054  test    eax, eax
0x180025056  jnz     short loc_18002509B
0x180025058  call    cs:__imp_GetLastError
0x18002505f  nop     dword ptr [rax+rax+00h]
0x180025064  mov     ebx, eax
0x180025066  test    eax, eax
  ... truncated ...
```
