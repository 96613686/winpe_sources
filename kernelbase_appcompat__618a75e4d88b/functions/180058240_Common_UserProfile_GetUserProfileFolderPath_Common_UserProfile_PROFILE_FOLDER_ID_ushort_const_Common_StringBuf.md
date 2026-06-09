# Common::UserProfile::GetUserProfileFolderPath(Common::UserProfile::PROFILE_FOLDER_ID,ushort const *,Common::StringBuffer &)

- ea: `0x180058240`
- end: `0x180058be4`
- name: `?GetUserProfileFolderPath@UserProfile@Common@@YAJW4PROFILE_FOLDER_ID@12@PEBGAEAVStringBuffer@2@@Z`
- size: `2468`
- prototype: `int __high(enum Common::UserProfile::PROFILE_FOLDER_ID, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `4`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800579c0`
- `0x180068fe4`
- `0x18006a4a8`
- `0x18006aad4`

## callees

- `0x18000c660`
- `0x18000cda0`
- `0x180037c60`
- `0x180056dc0`
- `0x1800579c0`
- `0x180058240`
- `0x180058da8`
- `0x1800599c0`
- `0x18005b2c4`
- `0x18005b2f0`
- `0x18005b400`
- `0x18005ca00`
- `0x18005e040`
- `0x18005e320`
- `0x1800a4f80`
- `0x1800ec430`
- `0x1800f4550`
- `0x180128e1c`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x1800584db`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18005853a`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180058931`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18005899d`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800584db`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18005853a`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180058931`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18005899d`
- `ntdll!RtlFreeHeap` at `0x1800585f8`
- `ntdll!RtlFreeHeap` at `0x1800585f8`

## string_xrefs

- `0x1800585d2`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18005865d`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058679`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18005870d`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058762`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1800587de`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1800588a0`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1800588de`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058a10`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058ab7`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058ae5`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058b28`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058b67`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058ba1`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x180058bd2`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x1800585ba`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800586e5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800587c6`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058857`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800586f5`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180058365`: `ProfileImagePath`
- `0x1800588fd`: `%PROGRAMDATA%`

## pseudocode

```c
__int64 __fastcall Common::UserProfile::GetUserProfileFolderPath(
        int a1,
        const WCHAR *a2,
        struct Common::StringBuffer *a3,
        const char *a4)
{
  __int64 v5; // r15
  _WORD *v6; // rdx
  int v8; // ecx
  __int64 v9; // rax
  __int64 v11; // rdi
  WCHAR *v12; // rsi
  int v13; // eax
  HRESULT v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  BYTE *v17; // rdi
  unsigned int v18; // r13d
  unsigned int v19; // eax
  unsigned int v20; // r12d
  LSTATUS v21; // eax
  DWORD v22; // edx
  int v23; // eax
  bool v24; // cf
  __int64 v25; // r15
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // r14d
  PWSTR v31; // rcx
  int v33; // eax
  unsigned int v34; // esi
  int UserProfileFolderPathFromSid; // eax
  unsigned int v36; // ebx
  HKEY v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rdx
  PWSTR v40; // rcx
  int v41; // eax
  unsigned int v42; // r12d
  int v43; // eax
  int v44; // eax
  __int64 v45; // rsi
  PWSTR v46; // rbx
  int v47; // eax
  int v48; // eax
  unsigned int v49; // edi
  int v50; // eax
  unsigned __int16 *v51; // rdi
  int v52; // eax
  int v53; // eax
  __int64 v54; // rcx
  unsigned int v55; // edi
  PWSTR v56; // rbx
  int dwFlags; // [rsp+20h] [rbp-29h]
  int dwFlagsa; // [rsp+20h] [rbp-29h]
  int dwFlagsb; // [rsp+20h] [rbp-29h]
  int dwFlagsc; // [rsp+20h] [rbp-29h]
  int dwFlagsd; // [rsp+20h] [rbp-29h]
  int dwFlagsf; // [rsp+20h] [rbp-29h]
  int dwFlagsg; // [rsp+20h] [rbp-29h]
  int dwFlagsh; // [rsp+20h] [rbp-29h]
  int dwFlagse; // [rsp+20h] [rbp-29h]
  LPBYTE lpData[2]; // [rsp+40h] [rbp-9h] BYREF
  int v67; // [rsp+50h] [rbp+7h]
  PWSTR pszPathOut[2]; // [rsp+58h] [rbp+Fh] BYREF
  int v69; // [rsp+68h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  DWORD cbData; // [rsp+B0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+77h] BYREF
  void *v73; // [rsp+C8h] [rbp+7Fh] BYREF

  LODWORD(v5) = 0;
  v6 = (_WORD *)*((_QWORD *)a3 + 1);
  if ( v6 )
    *v6 = 0;
  *(_DWORD *)a3 = 0;
  if ( a1 != 5 )
  {
    if ( a1 == 6 )
    {
      UserProfileFolderPathFromSid = GetUserProfileFolderPathFromSid(a2, L"Local AppData", a3);
      v36 = UserProfileFolderPathFromSid;
      if ( UserProfileFolderPathFromSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)UserProfileFolderPathFromSid,
          dwFlags);
        return v36;
      }
      return 0;
    }
    if ( a1 != 4 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        a4);
    v69 = 0;
    *(_OWORD *)pszPathOut = 0;
    v44 = Common::StringBuffer::SetLength((Common::StringBuffer *)pszPathOut, 0xDu);
    v15 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v44,
        dwFlags);
      v40 = pszPathOut[1];
      if ( !pszPathOut[1] )
        return v15;
      goto LABEL_90;
    }
    Common::StringBuffer::SetValue((Common::StringBuffer *)pszPathOut, L"%PROGRAMDATA%", 0xDu);
    v45 = LODWORD(pszPathOut[0]);
    v46 = pszPathOut[1];
    hKey = 0;
    v47 = RtlExpandEnvironmentStrings(0, pszPathOut[1], LODWORD(pszPathOut[0]), 0);
    if ( v47 != -1073741789 && v47 < 0 )
    {
      v55 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xB7,
              (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
              (const char *)(unsigned int)v47,
              0);
      if ( v46 )
        Common::GlobalHeap::Free(v46);
      return v55;
    }
    v67 = 0;
    *(_OWORD *)lpData = 0;
    v48 = Common::StringBuffer::SetLength((Common::StringBuffer *)lpData, (_DWORD)hKey - 1);
    v49 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v48,
        0);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpData);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
      return v49;
    }
    v73 = 0;
    if ( v67 )
      v50 = v67 - 1;
    else
      v50 = 0;
    v51 = (unsigned __int16 *)lpData[1];
    dwFlagse = v50 + 1;
    v52 = RtlExpandEnvironmentStrings(0, v46, v45, lpData[1]);
    if ( v52 < 0 )
    {
      v34 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xC4,
              (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
              (const char *)(unsigned int)v52,
              dwFlagse);
    }
    else
    {
      v53 = Common::StringBuffer::SetValueFromString(a3, v51);
      v34 = v53;
      if ( v53 >= 0 )
      {
        if ( v51 )
          Common::GlobalHeap::Free(v51);
        if ( v46 )
        {
          v31 = v46;
LABEL_65:
          Common::GlobalHeap::Free(v31);
        }
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v53,
        dwFlagse);
    }
    if ( v51 )
      Common::GlobalHeap::Free(v51);
    if ( v46 )
      Common::GlobalHeap::Free(v46);
    return v34;
  }
  v8 = 0;
  *(_OWORD *)pszPathOut = 0;
  v69 = 0;
  v9 = -1;
  while ( a2[++v9] != 0 )
    ;
  v11 = (unsigned int)(v9 + 57);
  if ( (_DWORD)v9 == -57 )
  {
    v12 = pszPathOut[1];
    goto LABEL_8;
  }
  v33 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)pszPathOut, v11);
  v34 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v33,
      dwFlags);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)v34,
      dwFlagsf);
    if ( pszPathOut[1] )
      RtlFreeHeap(ReservedForLocalUse::g_heap, 0, pszPathOut[1]);
    return v34;
  }
  v12 = pszPathOut[1];
  v8 = v69;
  pszPathOut[1][v11] = 0;
LABEL_8:
  LODWORD(pszPathOut[0]) = v11;
  v13 = 0;
  if ( v8 )
    v13 = v8 - 1;
  v14 = PathCchCombineEx(
          v12,
          (unsigned int)(v13 + 1),
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
          a2,
          0);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)(unsigned int)v14,
      dwFlagsa);
LABEL_88:
    if ( !v12 )
      return v15;
    v40 = v12;
LABEL_90:
    Common::GlobalHeap::Free(v40);
    return v15;
  }
  hKey = 0;
  v16 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v12, (PHANDLE)&hKey, 0);
  v15 = v16;
  if ( v16 > 0 )
    v15 = (unsigned __int16)v16 | 0x80070000;
  if ( (v15 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)v15,
      dwFlagsb);
LABEL_86:
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    goto LABEL_88;
  }
  v67 = 0;
  *(_OWORD *)lpData = 0;
  v17 = 0;
  v18 = 0;
  while ( 1 )
  {
    if ( v17 )
    {
      v19 = 0;
      if ( v18 )
        v19 = v18 - 1;
      v20 = v19 + 1;
    }
    else
    {
      v20 = 0;
    }
    cbData = 2 * v20;
    v21 = RegQueryValueExW(hKey, L"ProfileImagePath", 0, 0, v17, &cbData);
    v15 = v21;
    if ( !v21 || v21 == 234 )
    {
      if ( (cbData & 1) != 0 )
      {
        v15 = -2147024883;
        goto LABEL_50;
      }
      v22 = cbData >> 1;
      if ( !(cbData >> 1) )
      {
        LODWORD(v5) = 0;
        goto LABEL_25;
      }
      if ( v21 || !v17 )
      {
        LODWORD(v5) = v22 - 1;
LABEL_25:
        if ( v21 <= 0 )
          goto LABEL_28;
LABEL_26:
        v15 = (unsigned __int16)v15;
LABEL_27:
        v15 |= 0x80070000;
        goto LABEL_28;
      }
      v5 = v22 - 1;
      if ( *(_WORD *)&v17[2 * v5] )
      {
        LODWORD(v5) = v22 + 1;
        if ( v22 + 1 > v20 )
        {
          LOWORD(v15) = 234;
          goto LABEL_26;
        }
        LODWORD(v5) = cbData >> 1;
        *(_WORD *)&v17[2 * v22] = 0;
      }
    }
    else if ( v21 > 0 )
    {
      v15 = (unsigned __int16)v21;
      goto LABEL_27;
    }
LABEL_28:
    if ( !v15 )
      break;
    if ( v15 != -2147024662 )
      goto LABEL_50;
LABEL_35:
    if ( (unsigned int)v5 > 0x3FFFFFFF )
    {
      v15 = -2147023613;
      v39 = 425;
      v38 = 2147943683LL;
LABEL_83:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v38,
        dwFlagsc);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
        (const char *)v15,
        dwFlagsg);
LABEL_84:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)v15,
        dwFlagsc);
      if ( v17 )
        Common::GlobalHeap::Free(v17);
      goto LABEL_86;
    }
    if ( (_DWORD)v5 )
    {
      if ( (_DWORD)v5 + 1 == v18 )
      {
        LODWORD(v5) = 0;
      }
      else
      {
        v73 = 0;
        v23 = CommonHeapReAllocDefault(v17, 2LL * v18, 2LL * (unsigned int)(v5 + 1), &v73);
        v15 = v23;
        if ( v23 < 0 )
        {
          v38 = (unsigned int)v23;
          v39 = 458;
          goto LABEL_83;
        }
        v17 = (BYTE *)v73;
        v18 = v5 + 1;
        lpData[1] = (LPBYTE)v73;
        v67 = v5 + 1;
        v24 = LODWORD(lpData[0]) < (unsigned int)v5;
        if ( LODWORD(lpData[0]) > (unsigned int)v5 )
        {
          v54 = (unsigned int)v5;
          LODWORD(lpData[0]) = v5;
          LODWORD(v5) = 0;
          *((_WORD *)v73 + v54) = 0;
        }
        else
        {
          LODWORD(v5) = 0;
          if ( v24 && !LODWORD(lpData[0]) )
            *(_WORD *)v73 = 0;
        }
      }
    }
    else
    {
      if ( v17 )
      {
        Common::GlobalHeap::Free(v17);
        LODWORD(v5) = 0;
        v17 = 0;
        lpData[1] = 0;
        LODWORD(lpData[0]) = 0;
      }
      else
      {
        LODWORD(v5) = 0;
      }
      v18 = 0;
      v67 = 0;
    }
  }
  if ( (unsigned int)v5 > v20 )
    goto LABEL_35;
  if ( v18 )
    --v18;
  if ( (unsigned int)v5 > v18 )
  {
    v43 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)lpData, v5);
    v15 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v43,
        dwFlagsc);
      v17 = lpData[1];
      goto LABEL_50;
    }
    v17 = lpData[1];
  }
  LODWORD(lpData[0]) = v5;
  if ( (_DWORD)v5 )
    *(_WORD *)&v17[2 * (unsigned int)v5] = 0;
  v15 = 0;
LABEL_50:
  if ( (v15 & 0x80000000) != 0 )
    goto LABEL_84;
  v25 = LODWORD(lpData[0]);
  v26 = RtlExpandEnvironmentStrings(0, v17, LODWORD(lpData[0]), 0);
  if ( v26 != -1073741789 && v26 < 0 )
  {
    v15 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x8E,
            (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
            (const char *)(unsigned int)v26,
            0);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpData);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
    return v15;
  }
  v69 = 0;
  *(_OWORD *)pszPathOut = 0;
  v41 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)pszPathOut, 0xFFFFFFFF);
  v42 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v41,
      0);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)v42,
      dwFlagsh);
    if ( pszPathOut[1] )
      Common::GlobalHeap::Free(pszPathOut[1]);
    if ( v17 )
      Common::GlobalHeap::Free(v17);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    if ( v12 )
      Common::GlobalHeap::Free(v12);
    return v42;
  }
  v56 = pszPathOut[1];
  pszPathOut[1][0xFFFFFFFFLL] = 0;
  v27 = 0;
  if ( v69 )
    v27 = v69 - 1;
  dwFlagsd = v27 + 1;
  v28 = RtlExpandEnvironmentStrings(0, v17, v25, v56);
  if ( v28 < 0 )
  {
    v30 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x9B,
            (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
            (const char *)(unsigned int)v28,
            dwFlagsd);
    if ( v56 )
      Common::GlobalHeap::Free(v56);
    if ( v17 )
      Common::GlobalHeap::Free(v17);
    v37 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_97;
  }
  else
  {
    v29 = Common::StringBuffer::SetValueFromString(a3, v56);
    v30 = v29;
    if ( v29 >= 0 )
    {
      if ( v56 )
        Common::GlobalHeap::Free(v56);
      if ( v17 )
        Common::GlobalHeap::Free(v17);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      if ( v12 )
      {
        v31 = v12;
        goto LABEL_65;
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)(unsigned int)v29,
      dwFlagsd);
    if ( v56 )
      Common::GlobalHeap::Free(v56);
    if ( v17 )
      Common::GlobalHeap::Free(v17);
    v37 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_97:
      RegCloseKey(v37);
  }
  if ( v12 )
    Common::GlobalHeap::Free(v12);
  return v30;
}

```

## disassembly

```asm
0x180058240  push    rbp
0x180058242  push    rbx
0x180058243  push    r14
0x180058245  push    r15
0x180058247  lea     rbp, [rsp-3Fh]
0x18005824c  sub     rsp, 88h
0x180058253  mov     rbx, rdx
0x180058256  xor     r15d, r15d
0x180058259  mov     rdx, [r8+8]
0x18005825d  mov     r14, r8
0x180058260  test    rdx, rdx
0x180058263  jnz     loc_180058834
0x180058269  mov     [rsp+0A0h+arg_8], rsi
0x180058271  mov     [rsp+0A0h+var_20], rdi
0x180058279  mov     [rsp+0A0h+var_28], r12
0x18005827e  mov     [rsp+0A0h+var_30], r13
0x180058283  mov     [r8], r15d
0x180058286  cmp     ecx, 5
0x180058289  jnz     loc_180058637
0x18005828f  xorps   xmm0, xmm0
0x180058292  mov     ecx, r15d
0x180058295  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x180058299  mov     [rbp+57h+var_38], ecx
0x18005829c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800582a3  cmp     [rbx+rax*2+2], cx
0x1800582a8  lea     rax, [rax+1]
0x1800582ac  jnz     short loc_1800582A3
0x1800582ae  lea     edi, [rax+39h]
0x1800582b1  test    edi, edi
0x1800582b3  jnz     loc_1800585A1
0x1800582b9  mov     rsi, [rbp+57h+pszPathOut+8]
0x1800582bd  mov     dword ptr [rbp+57h+pszPathOut], edi
0x1800582c0  mov     eax, r15d
0x1800582c3  test    ecx, ecx
0x1800582c5  jz      short loc_1800582CA
0x1800582c7  lea     eax, [rcx-1]
0x1800582ca  lea     edx, [rax+1]; cchPathOut
0x1800582cd  mov     [rsp+0A0h+dwFlags], r15d; int
0x1800582d2  mov     r9, rbx; pszMore
0x1800582d5  lea     r8, pszPathIn; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800582dc  mov     rcx, rsi; pszPathOut
0x1800582df  call    PathCchCombineEx
0x1800582e4  mov     ebx, eax
0x1800582e6  test    eax, eax
0x1800582e8  js      loc_180058AE1
0x1800582ee  lea     rax, [rbp+57h+hKey]
0x1800582f2  mov     [rsp+0A0h+lpcbData], r15; __int64
0x1800582f7  mov     r9d, 20019h
0x1800582fd  mov     qword ptr [rsp+0A0h+dwFlags], rax; int
0x180058302  xor     r8d, r8d
0x180058305  mov     [rbp+57h+hKey], r15
0x180058309  mov     rdx, rsi; SourceString
0x18005830c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058313  call    RegOpenKeyExInternalW
0x180058318  mov     ebx, eax
0x18005831a  test    eax, eax
0x18005831c  jle     short loc_180058327
0x18005831e  movzx   ebx, ax
0x180058321  or      ebx, 80070000h
0x180058327  test    ebx, ebx
0x180058329  js      loc_1800588DA
0x18005832f  xorps   xmm0, xmm0
0x180058332  mov     [rbp+57h+var_50], r15d
0x180058336  movups  xmmword ptr [rbp+57h+lpData], xmm0
0x18005833a  mov     rdi, [rbp+57h+lpData+8]
0x18005833e  mov     r13d, r15d
0x180058341  test    rdi, rdi
0x180058344  jz      loc_180058481
0x18005834a  mov     eax, r15d
0x18005834d  test    r13d, r13d
0x180058350  jz      short loc_180058356
0x180058352  lea     eax, [r13-1]
0x180058356  lea     r12d, [rax+1]
0x18005835a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005835e  lea     eax, [r12+r12]
0x180058362  mov     [rbp+57h+cbData], eax
0x180058365  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18005836c  lea     rax, [rbp+57h+cbData]
0x180058370  xor     r9d, r9d; lpType
0x180058373  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x180058378  xor     r8d, r8d; lpReserved
0x18005837b  mov     qword ptr [rsp+0A0h+dwFlags], rdi; int
0x180058380  call    RegQueryValueExW
0x180058385  mov     ebx, eax
0x180058387  test    eax, eax
0x180058389  jnz     loc_1800589EA
0x18005838f  mov     edx, [rbp+57h+cbData]
0x180058392  test    dl, 1
0x180058395  jnz     loc_180058A47
0x18005839b  shr     edx, 1
0x18005839d  jz      loc_180058B4B
0x1800583a3  test    eax, eax
0x1800583a5  jnz     short loc_1800583AC
0x1800583a7  test    rdi, rdi
0x1800583aa  jnz     short loc_1800583CF
0x1800583ac  lea     r15d, [rdx-1]
0x1800583b0  test    eax, eax
0x1800583b2  jle     short loc_1800583BD
0x1800583b4  movzx   ebx, bx
0x1800583b7  or      ebx, 80070000h
0x1800583bd  test    ebx, ebx
0x1800583bf  jz      short loc_1800583F3
0x1800583c1  cmp     ebx, 800700EAh
0x1800583c7  jnz     loc_1800584AF
0x1800583cd  jmp     short loc_1800583FC
0x1800583cf  lea     r15d, [rdx-1]
0x1800583d3  cmp     word ptr [rdi+r15*2], 0
0x1800583d9  jz      short loc_1800583BD
0x1800583db  lea     r15d, [rdx+1]
0x1800583df  cmp     r15d, r12d
0x1800583e2  ja      loc_180058A51
0x1800583e8  xor     eax, eax
0x1800583ea  mov     r15d, edx
0x1800583ed  mov     [rdi+rdx*2], ax
0x1800583f1  jmp     short loc_1800583BD
0x1800583f3  cmp     r15d, r12d
0x1800583f6  jbe     loc_180058489
0x1800583fc  cmp     r15d, 3FFFFFFFh
0x180058403  ja      loc_1800588C8
0x180058409  test    r15d, r15d
0x18005840c  jz      loc_180058A6C
0x180058412  lea     r12d, [r15+1]
0x180058416  cmp     r12d, r13d
0x180058419  jz      loc_180058B43
0x18005841f  mov     r8d, r12d
0x180058422  lea     r9, [rbp+57h+arg_18]; void **
0x180058426  mov     edx, r13d
0x180058429  add     r8, r8; unsigned __int64
0x18005842c  add     rdx, rdx; unsigned __int64
0x18005842f  mov     [rbp+57h+arg_18], 0
0x180058437  mov     rcx, rdi; Ptr
0x18005843a  call    ?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z; CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)
0x18005843f  mov     ebx, eax
0x180058441  test    eax, eax
0x180058443  js      loc_1800586D9
0x180058449  mov     rdi, [rbp+57h+arg_18]
0x18005844d  mov     r13d, r12d
0x180058450  mov     eax, dword ptr [rbp+57h+lpData]
0x180058453  mov     [rbp+57h+lpData+8], rdi
0x180058457  mov     [rbp+57h+var_50], r12d
0x18005845b  cmp     eax, r15d
0x18005845e  ja      loc_180058A97
0x180058464  mov     r15d, 0
0x18005846a  jnb     loc_180058341
0x180058470  test    eax, eax
0x180058472  jnz     loc_180058341
0x180058478  mov     [rdi], r15w
0x18005847c  jmp     loc_180058341
0x180058481  mov     r12d, r15d
0x180058484  jmp     loc_18005835A
0x180058489  test    r13d, r13d
0x18005848c  jnz     loc_1800586D1
0x180058492  cmp     r15d, r13d
0x180058495  ja      loc_18005883D
0x18005849b  mov     dword ptr [rbp+57h+lpData], r15d
0x18005849f  test    r15d, r15d
0x1800584a2  jz      short loc_1800584AD
0x1800584a4  mov     ecx, r15d
0x1800584a7  xor     eax, eax
0x1800584a9  mov     [rdi+rcx*2], ax
0x1800584ad  xor     ebx, ebx
0x1800584af  test    ebx, ebx
0x1800584b1  js      loc_180058709
0x1800584b7  mov     r15d, dword ptr [rbp+57h+lpData]
0x1800584bb  lea     rax, [rbp+57h+var_70]
0x1800584bf  xor     r13d, r13d
0x1800584c2  mov     [rsp+0A0h+lpcbData], rax
0x1800584c7  mov     r8d, r15d
0x1800584ca  mov     qword ptr [rsp+0A0h+dwFlags], r13; int
0x1800584cf  xor     r9d, r9d
0x1800584d2  mov     [rbp+57h+var_70], r13
0x1800584d6  mov     rdx, rdi
0x1800584d9  xor     ecx, ecx
0x1800584db  call    cs:__imp_RtlExpandEnvironmentStrings
0x1800584e2  nop     dword ptr [rax+rax+00h]
0x1800584e7  cmp     eax, 0C0000023h
0x1800584ec  jnz     loc_180058B5B
0x1800584f2  mov     ebx, dword ptr [rbp+57h+var_70]
0x1800584f5  xorps   xmm0, xmm0
0x1800584f8  mov     ecx, r13d
0x1800584fb  mov     [rbp+57h+var_38], ecx
0x1800584fe  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x180058502  sub     ebx, 1
0x180058505  jnz     loc_1800587AC
0x18005850b  mov     rbx, [rbp+57h+pszPathOut+8]
0x18005850f  mov     [rbp+57h+var_68], r13
0x180058513  mov     eax, r13d
0x180058516  test    ecx, ecx
0x180058518  jnz     loc_18005862F
0x18005851e  lea     ecx, [rax+1]
0x180058521  mov     r9, rbx
0x180058524  lea     rax, [rbp+57h+var_68]
0x180058528  mov     r8, r15
0x18005852b  mov     [rsp+0A0h+lpcbData], rax
0x180058530  mov     rdx, rdi
0x180058533  mov     qword ptr [rsp+0A0h+dwFlags], rcx; int
0x180058538  xor     ecx, ecx
0x18005853a  call    cs:__imp_RtlExpandEnvironmentStrings
0x180058541  nop     dword ptr [rax+rax+00h]
0x180058546  test    eax, eax
0x180058548  js      loc_180058675
0x18005854e  mov     rdx, rbx; unsigned __int16 *
0x180058551  mov     rcx, r14; this
0x180058554  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180058559  mov     r14d, eax
0x18005855c  test    eax, eax
0x18005855e  js      loc_18005875E
0x180058564  test    rbx, rbx
0x180058567  jz      short loc_180058571
0x180058569  mov     rcx, rbx; void *
0x18005856c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180058571  test    rdi, rdi
0x180058574  jz      short loc_18005857E
0x180058576  mov     rcx, rdi; void *
0x180058579  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18005857e  mov     rcx, [rbp+57h+hKey]; hKey
0x180058582  lea     rax, [rcx-1]
0x180058586  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005858a  jbe     loc_180058754
0x180058590  test    rsi, rsi
0x180058593  jz      short loc_18005859D
0x180058595  mov     rcx, rsi; void *
0x180058598  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18005859d  xor     eax, eax
0x18005859f  jmp     short loc_180058606
0x1800585a1  mov     edx, edi; unsigned int
0x1800585a3  lea     rcx, [rbp+57h+pszPathOut]; this
0x1800585a7  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x1800585ac  mov     esi, eax
0x1800585ae  test    eax, eax
0x1800585b0  jns     loc_180058A5B
0x1800585b6  mov     rcx, [rbp+5Fh]; this
0x1800585ba  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x1800585c1  mov     r9d, eax; char *
0x1800585c4  mov     edx, 20Ch; void *
0x1800585c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800585ce  mov     rcx, [rbp+5Fh]; this
0x1800585d2  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\userpr"...
0x1800585d9  mov     r9d, esi; char *
0x1800585dc  mov     edx, 78h ; 'x'; void *
0x1800585e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800585e6  mov     r8, [rbp+57h+pszPathOut+8]; P
0x1800585ea  test    r8, r8
0x1800585ed  jz      short loc_180058604
0x1800585ef  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x1800585f6  xor     edx, edx; Flags
0x1800585f8  call    cs:__imp_RtlFreeHeap
0x1800585ff  nop     dword ptr [rax+rax+00h]
0x180058604  mov     eax, esi
0x180058606  mov     r13, [rsp+0A0h+var_30]
0x18005860b  mov     r12, [rsp+0A0h+var_28]
0x180058610  mov     rdi, [rsp+0A0h+var_20]
0x180058618  mov     rsi, [rsp+0A0h+arg_8]
0x180058620  add     rsp, 88h
0x180058627  pop     r15
0x180058629  pop     r14
0x18005862b  pop     rbx
0x18005862c  pop     rbp
0x18005862d  retn
0x18005862f  lea     eax, [rcx-1]
0x180058632  jmp     loc_18005851E
0x180058637  cmp     ecx, 6
0x18005863a  jnz     loc_180058874
0x180058640  lea     rdx, aLocalAppdata; "Local AppData"
0x180058647  mov     rcx, rbx; pszPathIn
0x18005864a  call    ?GetUserProfileFolderPathFromSid@@YAJPEBG0AEAVStringBuffer@Common@@@Z; GetUserProfileFolderPathFromSid(ushort const *,ushort const *,Common::StringBuffer &)
0x18005864f  mov     ebx, eax
0x180058651  test    eax, eax
0x180058653  jns     loc_18005859D
0x180058659  mov     rcx, [rbp+5Fh]; this
0x18005865d  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\userpr"...
0x180058664  mov     r9d, eax; char *
0x180058667  mov     edx, 0A5h; void *
0x18005866c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058671  mov     eax, ebx
0x180058673  jmp     short loc_180058606
0x180058675  mov     rcx, [rbp+5Fh]; this
0x180058679  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\userpr"...
0x180058680  mov     r9d, eax; char *
0x180058683  mov     edx, 9Bh; void *
0x180058688  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005868d  mov     r14d, eax
0x180058690  test    rbx, rbx
0x180058693  jz      short loc_18005869D
0x180058695  mov     rcx, rbx; void *
0x180058698  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18005869d  test    rdi, rdi
0x1800586a0  jz      short loc_1800586AA
0x1800586a2  mov     rcx, rdi; void *
0x1800586a5  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800586aa  mov     rcx, [rbp+57h+hKey]
0x1800586ae  lea     rax, [rcx-1]
0x1800586b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800586b6  jbe     loc_1800587A2
0x1800586bc  test    rsi, rsi
0x1800586bf  jz      short loc_1800586C9
0x1800586c1  mov     rcx, rsi; void *
0x1800586c4  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800586c9  mov     eax, r14d
0x1800586cc  jmp     loc_180058606
  ... truncated ...
```
