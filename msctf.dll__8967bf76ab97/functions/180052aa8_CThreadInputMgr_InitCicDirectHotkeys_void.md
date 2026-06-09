# CThreadInputMgr::_InitCicDirectHotkeys(void)

- ea: `0x180052aa8`
- end: `0x180052fef`
- name: `?_InitCicDirectHotkeys@CThreadInputMgr@@AEAAXXZ`
- size: `1351`
- prototype: `void __fastcall(CThreadInputMgr *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006bfc0`

## callees

- `0x1800250fc`
- `0x18003a5b0`
- `0x18003abd0`
- `0x180052aa8`
- `0x1800538fc`
- `0x1800539d8`
- `0x180053a08`
- `0x18005d0f0`
- `0x180068f74`
- `0x180069160`
- `0x1800855f0`
- `0x18008ae98`
- `0x180106a60`

## import_xrefs

- `msvcrt!wcstoul` at `0x180052c91`
- `msvcrt!wcstoul` at `0x180052e8b`
- `msvcrt!wcstoul` at `0x180052ebe`
- `msvcrt!wcstoul` at `0x180052f16`
- `msvcrt!wcstoul` at `0x180052c91`
- `msvcrt!wcstoul` at `0x180052e8b`
- `msvcrt!wcstoul` at `0x180052ebe`
- `msvcrt!wcstoul` at `0x180052f16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052cf2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052d33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052d70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052cf2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052d33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052d70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052c56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052c56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052f7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052f92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052f7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052f92`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180052c2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180052c2b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180052bd9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180052bd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052b48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052b48`

## string_xrefs

- `0x180052ec7`: `CLSID`

## pseudocode

```c
void __fastcall CThreadInputMgr::_InitCicDirectHotkeys(CThreadInputMgr *this)
{
  unsigned int v2; // edx
  const char *v3; // r9
  CVoidStructArray *v4; // rax
  CVoidStructArray *v5; // rbx
  HKEY v6; // rdx
  HKEY v7; // rsi
  DWORD v8; // r13d
  DWORD v9; // edx
  LSTATUS v10; // eax
  HKEY v11; // rdi
  HKEY v12; // r14
  LSTATUS v13; // r14d
  unsigned int v14; // eax
  HKEY v15; // rdi
  unsigned int v16; // r14d
  unsigned int v17; // edx
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult[2]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v21[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE v22[4]; // [rsp+60h] [rbp-A0h] BYREF
  void **v23; // [rsp+68h] [rbp-98h] BYREF
  HKEY v24; // [rsp+70h] [rbp-90h]
  void **v25; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h]
  DWORD dwIndex; // [rsp+88h] [rbp-78h]
  _QWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v29; // [rsp+A0h] [rbp-60h]
  struct _GUID v30; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v31; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  wchar_t String[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Name[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x156,
      (unsigned int)"clientcore\\windows\\advcore\\ctf\\uim\\hotkey.cpp",
      v3);
  if ( !*((_QWORD *)this + 290) )
  {
    CCurrentUserKey::CCurrentUserKey((CCurrentUserKey *)&v23, v2);
    CEnumRegBase::CEnumRegBase((CEnumRegBase *)v28, v24, L"Software\\Microsoft\\CTF\\DirectSwitchHotkeys");
    v28[0] = &CPreloadRegKey::`vftable';
    v4 = (CVoidStructArray *)LocalAlloc(0x40u, 0x20u);
    v5 = v4;
    if ( v4 )
    {
      CVoidStructArray::CVoidStructArray(v4, 56, 0);
      v6 = v24;
      *(_QWORD *)v5 = &CStructArray<char>::`vftable';
      *((_QWORD *)this + 290) = v5;
      CEnumRegBase::CEnumRegBase((CEnumRegBase *)&v25, v6, L"Control Panel\\Input Method\\Hot Keys");
      v7 = hKey;
      v8 = dwIndex;
      while ( v7 )
      {
        v9 = v8++;
        cchName[0] = 260;
        v10 = RegEnumKeyExW(v7, v9, Name, cchName, 0, 0, 0, 0);
        *(WCHAR *)((char *)Name + (v10 == 0 ? 0x206 : 0)) = 0;
        if ( v10 )
          break;
        *(_QWORD *)cchName = 0;
        v11 = 0;
        phkResult[0] = 0;
        v12 = v7;
        if ( v7 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, phkResult) )
          v12 = phkResult[0];
        v13 = RegOpenKeyExW(v12, Name, 0, 0x20019u, (PHKEY)cchName);
        if ( !v13 )
          v11 = *(HKEY *)cchName;
        hKey = v11;
        if ( phkResult[0] )
          RegCloseKey(phkResult[0]);
        if ( !v13 )
        {
          v14 = wcstoul(Name, 0, 16);
          if ( v14 >= 0x100 )
          {
            if ( v14 > 0x11F )
            {
              v25 = &CPreloadRegKey::`vftable';
              CInputDllRegKey::Close((CInputDllRegKey *)&v25);
              break;
            }
            cchName[0] = 4;
            *(_DWORD *)Data = 0;
            *(_DWORD *)v21 = 0;
            *(_DWORD *)v22 = 0;
            LODWORD(phkResult[0]) = 0;
            if ( RegQueryValueExW(v11, L"Key Modifiers", 0, (LPDWORD)phkResult, Data, cchName) >= 0 )
            {
              cchName[0] = 0;
              LODWORD(phkResult[0]) = 4;
              if ( RegQueryValueExW(v11, L"Virtual Key", 0, cchName, v21, (LPDWORD)phkResult) >= 0 )
              {
                cchName[0] = 0;
                LODWORD(phkResult[0]) = 4;
                if ( RegQueryValueExW(v11, L"Target IME", 0, cchName, v22, (LPDWORD)phkResult) >= 0 )
                {
                  *(_QWORD *)v30.Data4 = 0;
                  *(_DWORD *)&v30.Data2 = *(_DWORD *)Data;
                  v30.Data1 = *(_DWORD *)v21;
                  v33 = *(int *)v22;
                  v31 = 0;
                  v32 = 0;
                  CThreadInputMgr::_AddDirectHotkey(this, (const struct tag_DIRECTHOTKEY *)&v30);
                }
              }
            }
          }
        }
        v25 = &CPreloadRegKey::`vftable';
        if ( v11 )
        {
          RegCloseKey(v11);
          hKey = 0;
        }
      }
      v15 = (HKEY)v28[1];
      v16 = v29;
      while ( v15 )
      {
        v17 = v16++;
        v29 = v16;
        if ( (unsigned int)CMyRegKey::EnumKey((CMyRegKey *)v28, v17, Name, 0x104u) )
          break;
        phkResult[0] = (HKEY)&CPreloadRegKey::`vftable';
        phkResult[1] = 0;
        if ( !CMyRegKey::Open((CMyRegKey *)phkResult, v15, Name, 0x20019u) )
        {
          v33 = 0;
          v30 = 0;
          v31 = 0;
          v32 = 0;
          if ( !CMyRegKey::QueryValueCch((CMyRegKey *)phkResult, String, L"Modifiers", 0x104u) )
          {
            *(_DWORD *)&v30.Data2 = wcstoul(String, 0, 16);
            if ( !CMyRegKey::QueryValueCch((CMyRegKey *)phkResult, String, L"VirtualKey", 0x104u) )
            {
              v30.Data1 = wcstoul(String, 0, 16);
              if ( !CMyRegKey::QueryValueCch((CMyRegKey *)phkResult, String, L"CLSID", 0x104u) )
              {
                StringToCLSID(String, (struct _GUID *)v30.Data4);
                if ( !CMyRegKey::QueryValueCch((CMyRegKey *)phkResult, String, L"LangId", 0x104u) )
                {
                  *(_WORD *)v31.Data4 = wcstoul(String, 0, 16);
                  if ( !CMyRegKey::QueryValueCch((CMyRegKey *)phkResult, String, L"Profile", 0x104u) )
                  {
                    StringToCLSID(String, (struct _GUID *)&v31.Data4[4]);
                    CThreadInputMgr::_AddDirectHotkey(this, (const struct tag_DIRECTHOTKEY *)&v30);
                  }
                }
              }
            }
          }
        }
        phkResult[0] = (HKEY)&CPreloadRegKey::`vftable';
        CInputDllRegKey::Close((CInputDllRegKey *)phkResult);
      }
      if ( v7 )
        RegCloseKey(v7);
      if ( v15 )
        RegCloseKey(v15);
      if ( v24 )
        RegCloseKey(v24);
    }
    else
    {
      *((_QWORD *)this + 290) = 0;
      v28[0] = &CPreloadRegKey::`vftable';
      CInputDllRegKey::Close((CInputDllRegKey *)v28);
      v23 = &CPreloadRegKey::`vftable';
      CInputDllRegKey::Close((CInputDllRegKey *)&v23);
    }
  }
}

```

## disassembly

```asm
0x180052aa8  mov     [rsp-8+arg_8], rbx
0x180052aad  mov     [rsp-8+arg_10], rsi
0x180052ab2  push    rbp
0x180052ab3  push    rdi
0x180052ab4  push    r13
0x180052ab6  push    r14
0x180052ab8  push    r15
0x180052aba  lea     rbp, [rsp-410h]
0x180052ac2  sub     rsp, 510h
0x180052ac9  mov     rax, cs:__security_cookie
0x180052ad0  xor     rax, rsp
0x180052ad3  mov     [rbp+430h+var_30], rax
0x180052ada  mov     r15, rcx
0x180052add  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys> `wil::Feature<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::GetImpl(void)'::`2'::impl
0x180052ae4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_InputProfileHotKeys>::__private_IsEnabled(void)
0x180052ae9  xor     r14d, r14d
0x180052aec  test    al, al
0x180052aee  jz      short loc_180052B09
0x180052af0  mov     rcx, [rbp+438h]; this
0x180052af7  lea     r8, aClientcoreWind_5; "clientcore\\windows\\advcore\\ctf\\uim"...
0x180052afe  mov     edx, 156h; void *
0x180052b03  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180052b09  cmp     [r15+910h], r14
0x180052b10  jnz     loc_180052FC4
0x180052b16  lea     rcx, [rsp+530h+var_4C8]; this
0x180052b1b  call    ??0CCurrentUserKey@@QEAA@K@Z; CCurrentUserKey::CCurrentUserKey(ulong)
0x180052b20  mov     rdx, [rsp+530h+var_4C0]; hKey
0x180052b25  lea     r8, aSoftwareMicros_20; "Software\\Microsoft\\CTF\\DirectSwitchH"...
0x180052b2c  lea     rcx, [rbp+430h+var_4A0]; this
0x180052b30  call    ??0CEnumRegBase@@QEAA@PEAUHKEY__@@PEBG@Z; CEnumRegBase::CEnumRegBase(HKEY__ *,ushort const *)
0x180052b35  mov     edx, 20h ; ' '; uBytes
0x180052b3a  lea     rax, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180052b41  mov     [rbp+430h+var_4A0], rax
0x180052b45  lea     ecx, [rdx+20h]; uFlags
0x180052b48  call    cs:__imp_LocalAlloc
0x180052b4e  mov     rbx, rax
0x180052b51  test    rax, rax
0x180052b54  jz      loc_180052F9A
0x180052b5a  xor     r8d, r8d; int
0x180052b5d  mov     rcx, rax; this
0x180052b60  lea     edx, [r8+38h]; int
0x180052b64  call    ??0CVoidStructArray@@QEAA@HH@Z; CVoidStructArray::CVoidStructArray(int,int)
0x180052b69  mov     rdx, [rsp+530h+var_4C0]; hKey
0x180052b6e  lea     rax, ??_7?$CStructArray@D@@6B@; const CStructArray<char>::`vftable'
0x180052b75  mov     [rbx], rax
0x180052b78  lea     r8, aControlPanelIn; "Control Panel\\Input Method\\Hot Keys"
0x180052b7f  lea     rcx, [rsp+530h+var_4B8]; this
0x180052b84  mov     [r15+910h], rbx
0x180052b8b  call    ??0CEnumRegBase@@QEAA@PEAUHKEY__@@PEBG@Z; CEnumRegBase::CEnumRegBase(HKEY__ *,ushort const *)
0x180052b90  mov     rsi, [rbp+430h+hKey]
0x180052b94  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180052b9b  mov     r13d, [rbp+430h+dwIndex]
0x180052b9f  test    rsi, rsi
0x180052ba2  jz      loc_180052DE0
0x180052ba8  mov     [rsp+530h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180052bad  lea     r9, [rsp+530h+cchName]; lpcchName
0x180052bb2  mov     [rsp+530h+lpcchClass], r14; lpcchClass
0x180052bb7  lea     r8, [rbp+430h+Name]; lpName
0x180052bbe  mov     edx, r13d; dwIndex
0x180052bc1  mov     [rsp+530h+lpClass], r14; lpClass
0x180052bc6  mov     rcx, rsi; hKey
0x180052bc9  mov     [rsp+530h+lpReserved], r14; lpReserved
0x180052bce  inc     r13d
0x180052bd1  mov     [rsp+530h+cchName], 104h
0x180052bd9  call    cs:__imp_RegEnumKeyExW
0x180052bdf  mov     ecx, eax
0x180052be1  neg     ecx
0x180052be3  sbb     rdx, rdx
0x180052be6  not     rdx
0x180052be9  and     edx, 206h
0x180052bef  mov     [rbp+rdx+430h+Name], r14w
0x180052bf8  test    eax, eax
0x180052bfa  jnz     loc_180052DE0
0x180052c00  mov     qword ptr [rsp+530h+cchName], 0
0x180052c09  mov     rdi, r14
0x180052c0c  mov     [rsp+530h+phkResult], 0
0x180052c15  mov     r14, rsi
0x180052c18  cmp     rsi, 0FFFFFFFF80000001h
0x180052c1f  jnz     short loc_180052C39
0x180052c21  lea     rdx, [rsp+530h+phkResult]; phkResult
0x180052c26  mov     ecx, 20019h; samDesired
0x180052c2b  call    cs:__imp_RegOpenCurrentUser
0x180052c31  test    eax, eax
0x180052c33  cmovz   r14, [rsp+530h+phkResult]
0x180052c39  lea     rax, [rsp+530h+cchName]
0x180052c3e  mov     r9d, 20019h; samDesired
0x180052c44  xor     r8d, r8d; ulOptions
0x180052c47  mov     [rsp+530h+lpReserved], rax; phkResult
0x180052c4c  lea     rdx, [rbp+430h+Name]; lpSubKey
0x180052c53  mov     rcx, r14; hKey
0x180052c56  call    cs:__imp_RegOpenKeyExW
0x180052c5c  mov     rcx, [rsp+530h+phkResult]; hKey
0x180052c61  test    eax, eax
0x180052c63  mov     r14d, eax
0x180052c66  cmovz   rdi, qword ptr [rsp+530h+cchName]
0x180052c6c  mov     [rbp+430h+hKey], rdi
0x180052c70  test    rcx, rcx
0x180052c73  jz      short loc_180052C7B
0x180052c75  call    cs:__imp_RegCloseKey
0x180052c7b  test    r14d, r14d
0x180052c7e  jnz     loc_180052DAE
0x180052c84  xor     edx, edx; EndPtr
0x180052c86  lea     r8d, [r14+10h]; Radix
0x180052c8a  lea     rcx, [rbp+430h+Name]; String
0x180052c91  call    cs:__imp_wcstoul
0x180052c97  cmp     eax, 100h
0x180052c9c  jb      loc_180052DAE
0x180052ca2  cmp     eax, 11Fh
0x180052ca7  ja      loc_180052DD1
0x180052cad  xor     r14d, r14d
0x180052cb0  mov     [rsp+530h+cchName], 4
0x180052cb8  lea     rax, [rsp+530h+cchName]
0x180052cbd  mov     dword ptr [rsp+530h+Data], r14d
0x180052cc2  mov     [rsp+530h+lpClass], rax; lpcbData
0x180052cc7  lea     r9, [rsp+530h+phkResult]; lpType
0x180052ccc  lea     rax, [rsp+530h+Data]
0x180052cd1  mov     dword ptr [rsp+530h+var_4D4], r14d
0x180052cd6  xor     r8d, r8d; lpReserved
0x180052cd9  mov     [rsp+530h+lpReserved], rax; lpData
0x180052cde  lea     rdx, aKeyModifiers; "Key Modifiers"
0x180052ce5  mov     dword ptr [rsp+530h+var_4D0], r14d
0x180052cea  mov     rcx, rdi; hKey
0x180052ced  mov     dword ptr [rsp+530h+phkResult], r14d
0x180052cf2  call    cs:__imp_RegQueryValueExW
0x180052cf8  test    eax, eax
0x180052cfa  js      loc_180052DB1
0x180052d00  lea     rax, [rsp+530h+phkResult]
0x180052d05  mov     [rsp+530h+cchName], r14d
0x180052d0a  mov     [rsp+530h+lpClass], rax; lpcbData
0x180052d0f  lea     r9, [rsp+530h+cchName]; lpType
0x180052d14  lea     rax, [rsp+530h+var_4D4]
0x180052d19  mov     dword ptr [rsp+530h+phkResult], 4
0x180052d21  xor     r8d, r8d; lpReserved
0x180052d24  mov     [rsp+530h+lpReserved], rax; lpData
0x180052d29  lea     rdx, aVirtualKey; "Virtual Key"
0x180052d30  mov     rcx, rdi; hKey
0x180052d33  call    cs:__imp_RegQueryValueExW
0x180052d39  test    eax, eax
0x180052d3b  js      short loc_180052DB1
0x180052d3d  lea     rax, [rsp+530h+phkResult]
0x180052d42  mov     [rsp+530h+cchName], r14d
0x180052d47  mov     [rsp+530h+lpClass], rax; lpcbData
0x180052d4c  lea     r9, [rsp+530h+cchName]; lpType
0x180052d51  lea     rax, [rsp+530h+var_4D0]
0x180052d56  mov     dword ptr [rsp+530h+phkResult], 4
0x180052d5e  xor     r8d, r8d; lpReserved
0x180052d61  mov     [rsp+530h+lpReserved], rax; lpData
0x180052d66  lea     rdx, aTargetIme; "Target IME"
0x180052d6d  mov     rcx, rdi; hKey
0x180052d70  call    cs:__imp_RegQueryValueExW
0x180052d76  test    eax, eax
0x180052d78  js      short loc_180052DB1
0x180052d7a  mov     eax, dword ptr [rsp+530h+Data]
0x180052d7e  lea     rdx, [rbp+430h+var_488]; struct tag_DIRECTHOTKEY *
0x180052d82  xorps   xmm0, xmm0
0x180052d85  mov     rcx, r15; this
0x180052d88  movups  xmmword ptr [rbp+430h+var_488.Data1], xmm0
0x180052d8c  mov     dword ptr [rbp+430h+var_488.Data2], eax
0x180052d8f  mov     eax, dword ptr [rsp+530h+var_4D4]
0x180052d93  mov     [rbp+430h+var_488.Data1], eax
0x180052d96  movsxd  rax, dword ptr [rsp+530h+var_4D0]
0x180052d9b  mov     [rbp+430h+var_458], rax
0x180052d9f  movups  xmmword ptr [rbp+430h+var_478.Data1], xmm0
0x180052da3  movups  [rbp+430h+var_468], xmm0
0x180052da7  call    ?_AddDirectHotkey@CThreadInputMgr@@AEAAXAEBUtag_DIRECTHOTKEY@@@Z; CThreadInputMgr::_AddDirectHotkey(tag_DIRECTHOTKEY const &)
0x180052dac  jmp     short loc_180052DB1
0x180052dae  xor     r14d, r14d
0x180052db1  mov     [rsp+530h+var_4B8], rbx
0x180052db6  test    rdi, rdi
0x180052db9  jz      loc_180052B9F
0x180052dbf  mov     rcx, rdi; hKey
0x180052dc2  call    cs:__imp_RegCloseKey
0x180052dc8  mov     [rbp+430h+hKey], r14
0x180052dcc  jmp     loc_180052B9F
0x180052dd1  lea     rcx, [rsp+530h+var_4B8]; this
0x180052dd6  mov     [rsp+530h+var_4B8], rbx
0x180052ddb  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180052de0  mov     rdi, [rbp+430h+var_498]
0x180052de4  mov     r13d, 104h
0x180052dea  mov     r14d, [rbp+430h+var_490]
0x180052dee  test    rdi, rdi
0x180052df1  jz      loc_180052F69
0x180052df7  mov     edx, r14d; unsigned int
0x180052dfa  lea     r8, [rbp+430h+Name]; unsigned __int16 *
0x180052e01  inc     r14d
0x180052e04  lea     rcx, [rbp+430h+var_4A0]; this
0x180052e08  mov     r9d, r13d; unsigned int
0x180052e0b  mov     [rbp+430h+var_490], r14d
0x180052e0f  call    ?EnumKey@CMyRegKey@@QEAAJKPEAGK@Z; CMyRegKey::EnumKey(ulong,ushort *,ulong)
0x180052e14  test    eax, eax
0x180052e16  jnz     loc_180052F69
0x180052e1c  mov     r9d, 20019h; unsigned int
0x180052e22  mov     [rsp+530h+phkResult], rbx
0x180052e27  lea     r8, [rbp+430h+Name]; unsigned __int16 *
0x180052e2e  mov     [rsp+530h+var_4E0], 0
0x180052e37  mov     rdx, rdi; HKEY
0x180052e3a  lea     rcx, [rsp+530h+phkResult]; this
0x180052e3f  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180052e44  test    eax, eax
0x180052e46  jnz     loc_180052F55
0x180052e4c  xorps   xmm0, xmm0
0x180052e4f  lea     r8, aModifiers; "Modifiers"
0x180052e56  xor     eax, eax
0x180052e58  lea     rdx, [rbp+430h+String]; unsigned __int16 *
0x180052e5c  mov     r9d, r13d; unsigned int
0x180052e5f  mov     [rbp+430h+var_458], rax
0x180052e63  lea     rcx, [rsp+530h+phkResult]; this
0x180052e68  movups  xmmword ptr [rbp+430h+var_488.Data1], xmm0
0x180052e6c  movups  xmmword ptr [rbp+430h+var_478.Data1], xmm0
0x180052e70  movups  [rbp+430h+var_468], xmm0
0x180052e74  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180052e79  test    eax, eax
0x180052e7b  jnz     loc_180052F55
0x180052e81  xor     edx, edx; EndPtr
0x180052e83  lea     r8d, [rax+10h]; Radix
0x180052e87  lea     rcx, [rbp+430h+String]; String
0x180052e8b  call    cs:__imp_wcstoul
0x180052e91  mov     r9d, r13d; unsigned int
0x180052e94  lea     r8, aVirtualkey; "VirtualKey"
0x180052e9b  lea     rdx, [rbp+430h+String]; unsigned __int16 *
0x180052e9f  mov     dword ptr [rbp+430h+var_488.Data2], eax
0x180052ea2  lea     rcx, [rsp+530h+phkResult]; this
0x180052ea7  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180052eac  test    eax, eax
0x180052eae  jnz     loc_180052F55
0x180052eb4  xor     edx, edx; EndPtr
0x180052eb6  lea     r8d, [rax+10h]; Radix
0x180052eba  lea     rcx, [rbp+430h+String]; String
0x180052ebe  call    cs:__imp_wcstoul
0x180052ec4  mov     r9d, r13d; unsigned int
0x180052ec7  lea     r8, ?c_szCLSID@@3QBGB; "CLSID"
0x180052ece  lea     rdx, [rbp+430h+String]; unsigned __int16 *
0x180052ed2  mov     [rbp+430h+var_488.Data1], eax
0x180052ed5  lea     rcx, [rsp+530h+phkResult]; this
0x180052eda  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180052edf  test    eax, eax
0x180052ee1  jnz     short loc_180052F55
0x180052ee3  lea     rdx, [rbp+430h+var_488.Data4]; struct _GUID *
0x180052ee7  lea     rcx, [rbp+430h+String]; unsigned __int16 *
0x180052eeb  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x180052ef0  mov     r9d, r13d; unsigned int
0x180052ef3  lea     r8, aLangid; "LangId"
0x180052efa  lea     rdx, [rbp+430h+String]; unsigned __int16 *
0x180052efe  lea     rcx, [rsp+530h+phkResult]; this
0x180052f03  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180052f08  test    eax, eax
0x180052f0a  jnz     short loc_180052F55
0x180052f0c  xor     edx, edx; EndPtr
0x180052f0e  lea     r8d, [rax+10h]; Radix
0x180052f12  lea     rcx, [rbp+430h+String]; String
0x180052f16  call    cs:__imp_wcstoul
0x180052f1c  mov     r9d, r13d; unsigned int
0x180052f1f  lea     r8, ?c_szProfile@@3QBGB; "Profile"
0x180052f26  lea     rdx, [rbp+430h+String]; unsigned __int16 *
0x180052f2a  mov     word ptr [rbp+430h+var_478.Data4], ax
0x180052f2e  lea     rcx, [rsp+530h+phkResult]; this
0x180052f33  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180052f38  test    eax, eax
0x180052f3a  jnz     short loc_180052F55
0x180052f3c  lea     rdx, [rbp+430h+var_478.Data4+4]; struct _GUID *
0x180052f40  lea     rcx, [rbp+430h+String]; unsigned __int16 *
0x180052f44  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x180052f49  lea     rdx, [rbp+430h+var_488]; struct tag_DIRECTHOTKEY *
0x180052f4d  mov     rcx, r15; this
0x180052f50  call    ?_AddDirectHotkey@CThreadInputMgr@@AEAAXAEBUtag_DIRECTHOTKEY@@@Z; CThreadInputMgr::_AddDirectHotkey(tag_DIRECTHOTKEY const &)
0x180052f55  lea     rcx, [rsp+530h+phkResult]; this
0x180052f5a  mov     [rsp+530h+phkResult], rbx
0x180052f5f  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180052f64  jmp     loc_180052DEE
0x180052f69  test    rsi, rsi
0x180052f6c  jz      short loc_180052F77
0x180052f6e  mov     rcx, rsi; hKey
0x180052f71  call    cs:__imp_RegCloseKey
0x180052f77  test    rdi, rdi
0x180052f7a  jz      short loc_180052F85
0x180052f7c  mov     rcx, rdi; hKey
0x180052f7f  call    cs:__imp_RegCloseKey
0x180052f85  cmp     [rsp+530h+var_4C0], 0
0x180052f8b  jz      short loc_180052FC4
0x180052f8d  mov     rcx, [rsp+530h+var_4C0]; hKey
0x180052f92  call    cs:__imp_RegCloseKey
0x180052f98  jmp     short loc_180052FC4
0x180052f9a  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180052fa1  mov     [r15+910h], r14
0x180052fa8  lea     rcx, [rbp+430h+var_4A0]; this
0x180052fac  mov     [rbp+430h+var_4A0], rbx
0x180052fb0  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180052fb5  lea     rcx, [rsp+530h+var_4C8]; this
0x180052fba  mov     [rsp+530h+var_4C8], rbx
0x180052fbf  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180052fc4  mov     rcx, [rbp+430h+var_30]
0x180052fcb  xor     rcx, rsp; StackCookie
0x180052fce  call    __security_check_cookie
0x180052fd3  lea     r11, [rsp+530h+var_20]
0x180052fdb  mov     rbx, [r11+38h]
0x180052fdf  mov     rsi, [r11+40h]
0x180052fe3  mov     rsp, r11
0x180052fe6  pop     r15
0x180052fe8  pop     r14
0x180052fea  pop     r13
  ... truncated ...
```
