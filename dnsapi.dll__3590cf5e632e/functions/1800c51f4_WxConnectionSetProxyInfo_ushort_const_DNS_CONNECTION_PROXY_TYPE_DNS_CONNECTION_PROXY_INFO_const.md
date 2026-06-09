# WxConnectionSetProxyInfo(ushort const *,_DNS_CONNECTION_PROXY_TYPE,_DNS_CONNECTION_PROXY_INFO const *)

- ea: `0x1800c51f4`
- end: `0x1800c59dd`
- name: `?WxConnectionSetProxyInfo@@YAKPEBGW4_DNS_CONNECTION_PROXY_TYPE@@PEBU_DNS_CONNECTION_PROXY_INFO@@@Z`
- size: `2025`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, enum _DNS_CONNECTION_PROXY_TYPE, const struct _DNS_CONNECTION_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config`

## callers

- `0x1800acab0`

## callees

- `0x18003de30`
- `0x1800412f4`
- `0x18004148c`
- `0x1800577b4`
- `0x18005cb48`
- `0x18005cd90`
- `0x18008b5f0`
- `0x1800c40f8`
- `0x1800c51f4`
- `0x1800c59e4`
- `0x1800dc9e0`
- `0x1800dd940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5904`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c597d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c59af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5904`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c597d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c59af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c55a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c5922`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c55a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c5922`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c562d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c5677`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c58d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c562d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c5677`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c58d5`

## pseudocode

```c
__int64 __fastcall WxConnectionSetProxyInfo(
        unsigned __int16 *a1,
        unsigned int a2,
        const struct _DNS_CONNECTION_PROXY_INFO *a3)
{
  signed int v6; // ebx
  WCHAR *pwszFriendlyName; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  DNS_CONNECTION_PROXY_INFO_SWITCH *p_Switch; // r14
  DNS_CONNECTION_PROXY_INFO_SWITCH Switch; // edx
  __int32 v12; // edx
  WCHAR *pwszUsername; // rax
  WCHAR *pwszServer; // rdx
  unsigned __int64 v15; // rax
  WCHAR *v16; // rax
  WCHAR *v17; // rdx
  unsigned __int64 v18; // rax
  WCHAR *v19; // r8
  unsigned __int64 v20; // rdx
  WCHAR *pwszPassword; // r8
  unsigned __int64 v22; // rdx
  WCHAR *pwszException; // rdx
  unsigned __int64 v24; // rax
  WCHAR *pwszExtraInfo; // rax
  WCHAR *v26; // r9
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  int v30; // r9d
  WCHAR *v31; // r8
  int v32; // eax
  int v33; // r9d
  int v34; // r9d
  int v35; // eax
  BYTE *v36; // r8
  int v37; // r9d
  BYTE *v38; // r8
  WCHAR *v39; // r8
  WCHAR *v40; // r8
  WCHAR *v41; // r8
  WCHAR *v42; // r8
  LSTATUS v43; // eax
  unsigned int v44; // ebx
  HKEY v46; // [rsp+38h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-29h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-21h] BYREF
  HKEY v49; // [rsp+50h] [rbp-19h]
  LPCWSTR lpSubKey[2]; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR v51[2]; // [rsp+68h] [rbp-1h] BYREF
  BYTE *v52[2]; // [rsp+78h] [rbp+Fh] BYREF

  v49 = 0;
  hKey = 0;
  v46 = 0;
  v51[0] = &word_1800F66E0;
  v51[1] = 0;
  lpSubKey[0] = &word_1800F66E0;
  lpSubKey[1] = 0;
  *(_DWORD *)Data = 0;
  v52[0] = (BYTE *)&word_1800F66E0;
  v52[1] = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_Sdq(1054, 23, (unsigned int)WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids, (_DWORD)a1, a2, (__int64)a3);
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_115;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_115;
  }
  pwszFriendlyName = a3->pwszFriendlyName;
  v8 = -1;
  if ( pwszFriendlyName )
  {
    v9 = -1;
    do
      ++v9;
    while ( pwszFriendlyName[v9] );
    if ( v9 > 0x40 )
    {
      v6 = -2147024809;
      goto LABEL_115;
    }
  }
  p_Switch = &a3->Switch;
  Switch = a3->Switch;
  if ( Switch )
  {
    v12 = Switch - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
      pwszUsername = a3->Config.pwszUsername;
      if ( pwszUsername )
      {
        do
          ++v8;
        while ( pwszUsername[v8] );
        if ( v8 > 0x80 )
        {
          v6 = -2147024809;
          goto LABEL_115;
        }
      }
    }
    else
    {
      pwszServer = a3->Config.pwszServer;
      if ( !pwszServer )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
      if ( !*pwszServer )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
      v15 = -1;
      do
        ++v15;
      while ( pwszServer[v15] );
      if ( v15 > 0x824 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
      v16 = a3->Config.pwszUsername;
      if ( v16 )
      {
        do
          ++v8;
        while ( v16[v8] );
        if ( v8 > 0x80 )
        {
          v6 = -2147024809;
          goto LABEL_115;
        }
      }
    }
  }
  else
  {
    v17 = a3->Config.pwszServer;
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      if ( v18 > 0x100 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
    }
    v19 = a3->Config.pwszUsername;
    if ( v19 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( v20 > 0x80 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
    }
    pwszPassword = a3->Config.pwszPassword;
    if ( pwszPassword )
    {
      v22 = -1;
      do
        ++v22;
      while ( pwszPassword[v22] );
      if ( v22 > 0x80 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
    }
    pwszException = a3->Config.pwszException;
    if ( pwszException )
    {
      v24 = -1;
      do
        ++v24;
      while ( pwszException[v24] );
      if ( v24 > 0x400 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
    }
    pwszExtraInfo = a3->Config.pwszExtraInfo;
    if ( pwszExtraInfo )
    {
      do
        ++v8;
      while ( pwszExtraInfo[v8] );
      if ( v8 > 0x400 )
      {
        v6 = -2147024809;
        goto LABEL_115;
      }
    }
  }
  if ( a3->Version != 1 )
  {
    v6 = -2147024809;
    goto LABEL_115;
  }
  v6 = OpenProxyRegistryKey(0x2001Fu, 1);
  if ( v6 >= 0 )
  {
    v6 = NormalizeConnectionName(a1, (CWxString *)v51);
    if ( v6 >= 0 )
    {
      v26 = a3->pwszFriendlyName;
      if ( !v26 || !*v26 || (v6 = CheckForDuplicateFriendlyName(v49, (wchar_t *)v51[0]), v6 >= 0) )
      {
        v6 = WxOpenRegistryKey(v49, v51[0], 0x2001Fu, 1, &hKey);
        if ( v6 >= 0 )
        {
          v6 = CWxString::Format((CWxString *)lpSubKey, L"%d", a2);
          if ( v6 >= 0 )
          {
            v27 = RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0);
            v6 = v27;
            if ( v27 == 2 )
              goto LABEL_69;
            if ( v27 > 0 )
              v6 = (unsigned __int16)v27 | 0x80070000;
            if ( v6 >= 0 )
            {
LABEL_69:
              v6 = WxOpenRegistryKey(hKey, lpSubKey[0], 0x2001Fu, 1, &v46);
              if ( v6 >= 0 )
              {
                v28 = RegSetValueExW(v46, L"Flags", 0, 4u, (const BYTE *)&a3->Flags, 4u);
                v6 = v28;
                if ( v28 > 0 )
                  v6 = (unsigned __int16)v28 | 0x80070000;
                if ( v6 < 0 )
                  goto LABEL_112;
                v29 = RegSetValueExW(v46, L"Switch", 0, 4u, (const BYTE *)&a3->Switch, 4u);
                v6 = v29;
                if ( v29 > 0 )
                  v6 = (unsigned __int16)v29 | 0x80070000;
                if ( v6 < 0 )
                  goto LABEL_112;
                v31 = a3->pwszFriendlyName;
                if ( v31 && *v31 )
                {
                  v32 = WxSetRegistryString(v46, L"FriendlyName", (BYTE *)v31, v30);
                  v6 = v32;
                  if ( v32 > 0 )
                    v6 = (unsigned __int16)v32 | 0x80070000;
                  if ( v6 < 0 )
                    goto LABEL_112;
                }
                else
                {
                  v6 = CWxString::Format((CWxString *)v52, L"PXY(%s:%d)", a1, a2);
                  if ( v6 < 0 )
                    goto LABEL_112;
                  v35 = WxSetRegistryString(v46, L"FriendlyName", v52[0], v34);
                  v6 = v35;
                  if ( v35 > 0 )
                    v6 = (unsigned __int16)v35 | 0x80070000;
                  if ( v6 < 0 )
                    goto LABEL_112;
                }
                if ( *p_Switch )
                {
                  if ( *p_Switch == DNS_CONNECTION_PROXY_INFO_SWITCH_SCRIPT )
                  {
                    v6 = WxSetRegistryString(v46, L"Script", (BYTE *)a3->Config.pwszServer, v33);
                    if ( v6 >= 0 )
                    {
                      v38 = (BYTE *)a3->Config.pwszUsername;
                      if ( !v38 )
                        goto LABEL_115;
                      if ( !*(_WORD *)v38 )
                        goto LABEL_115;
                      v6 = WxSetRegistryString(v46, L"Username", v38, v37);
                      if ( v6 >= 0 )
                        goto LABEL_115;
                    }
                  }
                  else
                  {
                    if ( *p_Switch != DNS_CONNECTION_PROXY_INFO_SWITCH_WPAD )
                      goto LABEL_115;
                    v36 = (BYTE *)a3->Config.pwszUsername;
                    if ( !v36 )
                      goto LABEL_115;
                    if ( !*(_WORD *)v36 )
                      goto LABEL_115;
                    v6 = WxSetRegistryString(v46, L"Username", v36, v33);
                    if ( v6 >= 0 )
                      goto LABEL_115;
                  }
                  goto LABEL_112;
                }
                v39 = a3->Config.pwszServer;
                if ( v39 )
                {
                  v6 = WxSetRegistryString(v46, L"Server", (BYTE *)v39, v33);
                  if ( v6 < 0 )
                    goto LABEL_112;
                }
                v40 = a3->Config.pwszUsername;
                if ( v40 )
                {
                  if ( *v40 )
                  {
                    v6 = WxSetRegistryString(v46, L"Username", (BYTE *)v40, v33);
                    if ( v6 < 0 )
                      goto LABEL_112;
                  }
                }
                v41 = a3->Config.pwszException;
                if ( v41 )
                {
                  if ( *v41 )
                  {
                    v6 = WxSetRegistryString(v46, L"Exception", (BYTE *)v41, v33);
                    if ( v6 < 0 )
                      goto LABEL_112;
                  }
                }
                v42 = a3->Config.pwszExtraInfo;
                if ( v42 )
                {
                  if ( *v42 )
                  {
                    v6 = WxSetRegistryString(v46, L"ExtraInfo", (BYTE *)v42, v33);
                    if ( v6 < 0 )
                      goto LABEL_112;
                  }
                }
                *(_DWORD *)Data = a3->Config.Port;
                v43 = RegSetValueExW(v46, L"Port", 0, 4u, Data, 4u);
                v6 = v43;
                if ( v43 > 0 )
                  v6 = (unsigned __int16)v43 | 0x80070000;
                if ( v6 < 0 )
                {
LABEL_112:
                  if ( v46 )
                  {
                    RegCloseKey(v46);
                    v46 = 0;
                  }
                  RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_115:
  if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_d(1054, 24, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids, (unsigned int)v6);
  v44 = WX_WIN32_FROM_HR((unsigned int)v6);
  CWxString::_Release((CWxString *)v52);
  CWxString::_Release((CWxString *)lpSubKey);
  CWxString::_Release((CWxString *)v51);
  if ( v46 )
  {
    RegCloseKey(v46);
    v46 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v49 )
    RegCloseKey(v49);
  return v44;
}

```

## disassembly

```asm
0x1800c51f4  push    rbp
0x1800c51f6  push    rbx
0x1800c51f7  push    rdi
0x1800c51f8  push    r12
0x1800c51fa  push    r13
0x1800c51fc  push    r14
0x1800c51fe  push    r15
0x1800c5200  lea     rbp, [rsp-27h]
0x1800c5205  sub     rsp, 90h
0x1800c520c  mov     rax, cs:__security_cookie
0x1800c5213  xor     rax, rsp
0x1800c5216  mov     [rbp+57h+var_38], rax
0x1800c521a  xor     r13d, r13d
0x1800c521d  lea     rax, word_1800F66E0
0x1800c5224  mov     [rbp+57h+var_8C], r13d
0x1800c5228  mov     rdi, r8
0x1800c522b  mov     [rbp+57h+var_70], r13
0x1800c522f  mov     r12d, edx
0x1800c5232  mov     [rbp+57h+hKey], r13
0x1800c5236  mov     r15, rcx
0x1800c5239  mov     [rbp+57h+var_88], r13
0x1800c523d  mov     [rbp+57h+var_58], rax
0x1800c5241  mov     [rbp+57h+var_50], r13
0x1800c5245  mov     [rbp+57h+lpSubKey], rax
0x1800c5249  mov     [rbp+57h+var_60], r13
0x1800c524d  mov     dword ptr [rbp+57h+Data], r13d
0x1800c5251  mov     [rbp+57h+var_48], rax
0x1800c5255  mov     [rbp+57h+var_40], r13
0x1800c5259  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800c5260  jz      short loc_1800C5284
0x1800c5262  mov     qword ptr [rsp+0C0h+cbData], r8
0x1800c5267  lea     edx, [r13+17h]
0x1800c526b  lea     r8, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids
0x1800c5272  mov     dword ptr [rsp+0C0h+lpData], r12d
0x1800c5277  mov     ecx, 41Eh
0x1800c527c  mov     r9, r15
0x1800c527f  call    WPP_SF_Sdq
0x1800c5284  test    r15, r15
0x1800c5287  jnz     short loc_1800C529A
0x1800c5289  mov     ebx, 80070057h
0x1800c528e  mov     [rbp+57h+var_8C], 1AAh
0x1800c5295  jmp     loc_1800C592E
0x1800c529a  test    rdi, rdi
0x1800c529d  jnz     short loc_1800C52B0
0x1800c529f  mov     ebx, 80070057h
0x1800c52a4  mov     [rbp+57h+var_8C], 1ABh
0x1800c52ab  jmp     loc_1800C592E
0x1800c52b0  mov     rdx, [rdi+8]
0x1800c52b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c52b8  test    rdx, rdx
0x1800c52bb  jz      short loc_1800C52E1
0x1800c52bd  mov     rax, rcx
0x1800c52c0  inc     rax
0x1800c52c3  cmp     [rdx+rax*2], r13w
0x1800c52c8  jnz     short loc_1800C52C0
0x1800c52ca  cmp     rax, 40h ; '@'
0x1800c52ce  jbe     short loc_1800C52E1
0x1800c52d0  mov     ebx, 80070057h
0x1800c52d5  mov     [rbp+57h+var_8C], 1B3h
0x1800c52dc  jmp     loc_1800C592E
0x1800c52e1  lea     r14, [rdi+14h]
0x1800c52e5  mov     edx, [r14]
0x1800c52e8  test    edx, edx
0x1800c52ea  jz      loc_1800C53CE
0x1800c52f0  sub     edx, 1
0x1800c52f3  jz      short loc_1800C5341
0x1800c52f5  cmp     edx, 1
0x1800c52f8  jz      short loc_1800C530B
0x1800c52fa  mov     ebx, 80070057h
0x1800c52ff  mov     [rbp+57h+var_8C], 1EBh
0x1800c5306  jmp     loc_1800C592E
0x1800c530b  mov     rax, [rdi+20h]
0x1800c530f  test    rax, rax
0x1800c5312  jz      loc_1800C54B5
0x1800c5318  inc     rcx
0x1800c531b  cmp     [rax+rcx*2], r13w
0x1800c5320  jnz     short loc_1800C5318
0x1800c5322  mov     eax, 80h
0x1800c5327  cmp     rcx, rax
0x1800c532a  jbe     loc_1800C54B5
0x1800c5330  mov     ebx, 80070057h
0x1800c5335  mov     [rbp+57h+var_8C], 1E5h
0x1800c533c  jmp     loc_1800C592E
0x1800c5341  mov     rdx, [rdi+18h]
0x1800c5345  test    rdx, rdx
0x1800c5348  jnz     short loc_1800C535B
0x1800c534a  mov     ebx, 80070057h
0x1800c534f  mov     [rbp+57h+var_8C], 1D5h
0x1800c5356  jmp     loc_1800C592E
0x1800c535b  cmp     [rdx], r13w
0x1800c535f  jnz     short loc_1800C5372
0x1800c5361  mov     ebx, 80070057h
0x1800c5366  mov     [rbp+57h+var_8C], 1D6h
0x1800c536d  jmp     loc_1800C592E
0x1800c5372  mov     rax, rcx
0x1800c5375  inc     rax
0x1800c5378  cmp     [rdx+rax*2], r13w
0x1800c537d  jnz     short loc_1800C5375
0x1800c537f  cmp     rax, 824h
0x1800c5385  jbe     short loc_1800C5398
0x1800c5387  mov     ebx, 80070057h
0x1800c538c  mov     [rbp+57h+var_8C], 1D8h
0x1800c5393  jmp     loc_1800C592E
0x1800c5398  mov     rax, [rdi+20h]
0x1800c539c  test    rax, rax
0x1800c539f  jz      loc_1800C54B5
0x1800c53a5  inc     rcx
0x1800c53a8  cmp     [rax+rcx*2], r13w
0x1800c53ad  jnz     short loc_1800C53A5
0x1800c53af  mov     eax, 80h
0x1800c53b4  cmp     rcx, rax
0x1800c53b7  jbe     loc_1800C54B5
0x1800c53bd  mov     ebx, 80070057h
0x1800c53c2  mov     [rbp+57h+var_8C], 1DCh
0x1800c53c9  jmp     loc_1800C592E
0x1800c53ce  mov     rdx, [rdi+18h]
0x1800c53d2  test    rdx, rdx
0x1800c53d5  jz      short loc_1800C53FD
0x1800c53d7  mov     rax, rcx
0x1800c53da  inc     rax
0x1800c53dd  cmp     [rdx+rax*2], r13w
0x1800c53e2  jnz     short loc_1800C53DA
0x1800c53e4  cmp     rax, 100h
0x1800c53ea  jbe     short loc_1800C53FD
0x1800c53ec  mov     ebx, 80070057h
0x1800c53f1  mov     [rbp+57h+var_8C], 1BBh
0x1800c53f8  jmp     loc_1800C592E
0x1800c53fd  mov     r8, [rdi+20h]
0x1800c5401  mov     eax, 80h
0x1800c5406  test    r8, r8
0x1800c5409  jz      short loc_1800C542E
0x1800c540b  mov     rdx, rcx
0x1800c540e  inc     rdx
0x1800c5411  cmp     [r8+rdx*2], r13w
0x1800c5416  jnz     short loc_1800C540E
0x1800c5418  cmp     rdx, rax
0x1800c541b  jbe     short loc_1800C542E
0x1800c541d  mov     ebx, 80070057h
0x1800c5422  mov     [rbp+57h+var_8C], 1C0h
0x1800c5429  jmp     loc_1800C592E
0x1800c542e  mov     r8, [rdi+28h]
0x1800c5432  test    r8, r8
0x1800c5435  jz      short loc_1800C545A
0x1800c5437  mov     rdx, rcx
0x1800c543a  inc     rdx
0x1800c543d  cmp     [r8+rdx*2], r13w
0x1800c5442  jnz     short loc_1800C543A
0x1800c5444  cmp     rdx, rax
0x1800c5447  jbe     short loc_1800C545A
0x1800c5449  mov     ebx, 80070057h
0x1800c544e  mov     [rbp+57h+var_8C], 1C5h
0x1800c5455  jmp     loc_1800C592E
0x1800c545a  mov     rdx, [rdi+30h]
0x1800c545e  mov     r8d, 400h
0x1800c5464  test    rdx, rdx
0x1800c5467  jz      short loc_1800C548C
0x1800c5469  mov     rax, rcx
0x1800c546c  inc     rax
0x1800c546f  cmp     [rdx+rax*2], r13w
0x1800c5474  jnz     short loc_1800C546C
0x1800c5476  cmp     rax, r8
0x1800c5479  jbe     short loc_1800C548C
0x1800c547b  mov     ebx, 80070057h
0x1800c5480  mov     [rbp+57h+var_8C], 1CAh
0x1800c5487  jmp     loc_1800C592E
0x1800c548c  mov     rax, [rdi+38h]
0x1800c5490  test    rax, rax
0x1800c5493  jz      short loc_1800C54B5
0x1800c5495  inc     rcx
0x1800c5498  cmp     [rax+rcx*2], r13w
0x1800c549d  jnz     short loc_1800C5495
0x1800c549f  cmp     rcx, r8
0x1800c54a2  jbe     short loc_1800C54B5
0x1800c54a4  mov     ebx, 80070057h
0x1800c54a9  mov     [rbp+57h+var_8C], 1CFh
0x1800c54b0  jmp     loc_1800C592E
0x1800c54b5  cmp     dword ptr [rdi], 1
0x1800c54b8  jz      short loc_1800C54CB
0x1800c54ba  mov     ebx, 80070057h
0x1800c54bf  mov     [rbp+57h+var_8C], 1F6h
0x1800c54c6  jmp     loc_1800C592E
0x1800c54cb  lea     r8, [rbp+57h+var_70]
0x1800c54cf  mov     edx, 1; int
0x1800c54d4  mov     ecx, 2001Fh; samDesired
0x1800c54d9  call    _OpenProxyRegistryKey
0x1800c54de  mov     ebx, eax
0x1800c54e0  test    eax, eax
0x1800c54e2  jns     short loc_1800C54F0
0x1800c54e4  mov     [rbp+57h+var_8C], 1F8h
0x1800c54eb  jmp     loc_1800C592E
0x1800c54f0  lea     rdx, [rbp+57h+var_58]; this
0x1800c54f4  mov     rcx, r15; unsigned __int16 *
0x1800c54f7  call    _NormalizeConnectionName
0x1800c54fc  mov     ebx, eax
0x1800c54fe  test    eax, eax
0x1800c5500  jns     short loc_1800C550E
0x1800c5502  mov     [rbp+57h+var_8C], 1FAh
0x1800c5509  jmp     loc_1800C592E
0x1800c550e  mov     r9, [rdi+8]
0x1800c5512  test    r9, r9
0x1800c5515  jz      short loc_1800C553F
0x1800c5517  cmp     [r9], r13w
0x1800c551b  jz      short loc_1800C553F
0x1800c551d  mov     rdx, [rbp+57h+var_58]; String1
0x1800c5521  mov     r8d, r12d
0x1800c5524  mov     rcx, [rbp+57h+var_70]; hKey
0x1800c5528  call    _CheckForDuplicateFriendlyName
0x1800c552d  mov     ebx, eax
0x1800c552f  test    eax, eax
0x1800c5531  jns     short loc_1800C553F
0x1800c5533  mov     [rbp+57h+var_8C], 202h
0x1800c553a  jmp     loc_1800C592E
0x1800c553f  mov     rdx, [rbp+57h+var_58]; lpSubKey
0x1800c5543  lea     rax, [rbp+57h+hKey]
0x1800c5547  mov     rcx, [rbp+57h+var_70]; hKey
0x1800c554b  mov     r9d, 1; int
0x1800c5551  mov     r8d, 2001Fh; samDesired
0x1800c5557  mov     [rsp+0C0h+lpData], rax; HKEY *
0x1800c555c  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800c5561  mov     ebx, eax
0x1800c5563  test    eax, eax
0x1800c5565  jns     short loc_1800C5573
0x1800c5567  mov     [rbp+57h+var_8C], 205h
0x1800c556e  jmp     loc_1800C592E
0x1800c5573  mov     r8d, r12d
0x1800c5576  lea     rdx, aD; "%d"
0x1800c557d  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800c5581  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1800c5586  mov     ebx, eax
0x1800c5588  test    eax, eax
0x1800c558a  jns     short loc_1800C5598
0x1800c558c  mov     [rbp+57h+var_8C], 20Bh
0x1800c5593  jmp     loc_1800C592E
0x1800c5598  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800c559c  xor     r9d, r9d; Reserved
0x1800c559f  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c55a3  xor     r8d, r8d; samDesired
0x1800c55a6  call    cs:__imp_RegDeleteKeyExW
0x1800c55ad  nop     dword ptr [rax+rax+00h]
0x1800c55b2  mov     ebx, eax
0x1800c55b4  cmp     eax, 2
0x1800c55b7  jz      short loc_1800C55D6
0x1800c55b9  test    eax, eax
0x1800c55bb  jle     short loc_1800C55C6
0x1800c55bd  movzx   ebx, ax
0x1800c55c0  or      ebx, 80070000h
0x1800c55c6  test    ebx, ebx
0x1800c55c8  jns     short loc_1800C55D6
0x1800c55ca  mov     [rbp+57h+var_8C], 210h
0x1800c55d1  jmp     loc_1800C592E
0x1800c55d6  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800c55da  lea     rax, [rbp+57h+var_88]
0x1800c55de  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c55e2  mov     r9d, 1; int
0x1800c55e8  mov     r8d, 2001Fh; samDesired
0x1800c55ee  mov     [rsp+0C0h+lpData], rax; HKEY *
0x1800c55f3  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800c55f8  mov     ebx, eax
0x1800c55fa  test    eax, eax
0x1800c55fc  jns     short loc_1800C560A
0x1800c55fe  mov     [rbp+57h+var_8C], 213h
0x1800c5605  jmp     loc_1800C592E
0x1800c560a  mov     ecx, 4
0x1800c560f  lea     rax, [rdi+10h]
0x1800c5613  mov     [rsp+0C0h+cbData], ecx; cbData
0x1800c5617  lea     rdx, aFlags; "Flags"
0x1800c561e  mov     r9d, ecx; dwType
0x1800c5621  mov     [rsp+0C0h+lpData], rax; lpData
0x1800c5626  mov     rcx, [rbp+57h+var_88]; hKey
0x1800c562a  xor     r8d, r8d; Reserved
0x1800c562d  call    cs:__imp_RegSetValueExW
0x1800c5634  nop     dword ptr [rax+rax+00h]
0x1800c5639  mov     ebx, eax
0x1800c563b  test    eax, eax
0x1800c563d  jle     short loc_1800C5648
0x1800c563f  movzx   ebx, ax
0x1800c5642  or      ebx, 80070000h
0x1800c5648  test    ebx, ebx
0x1800c564a  jns     short loc_1800C5658
0x1800c564c  mov     [rbp+57h+var_8C], 21Ah
0x1800c5653  jmp     loc_1800C58FB
0x1800c5658  mov     rcx, [rbp+57h+var_88]; hKey
0x1800c565c  lea     rdx, aSwitch; "Switch"
0x1800c5663  mov     eax, 4
0x1800c5668  xor     r8d, r8d; Reserved
0x1800c566b  mov     [rsp+0C0h+cbData], eax; cbData
0x1800c566f  mov     r9d, eax; dwType
0x1800c5672  mov     [rsp+0C0h+lpData], r14; lpData
0x1800c5677  call    cs:__imp_RegSetValueExW
0x1800c567e  nop     dword ptr [rax+rax+00h]
0x1800c5683  mov     ebx, eax
0x1800c5685  test    eax, eax
0x1800c5687  jle     short loc_1800C5692
0x1800c5689  movzx   ebx, ax
0x1800c568c  or      ebx, 80070000h
0x1800c5692  test    ebx, ebx
0x1800c5694  jns     short loc_1800C56A2
0x1800c5696  mov     [rbp+57h+var_8C], 21Bh
0x1800c569d  jmp     loc_1800C58FB
0x1800c56a2  mov     r8, [rdi+8]; lpData
  ... truncated ...
```
