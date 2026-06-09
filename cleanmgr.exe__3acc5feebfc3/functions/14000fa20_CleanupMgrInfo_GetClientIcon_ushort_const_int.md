# CleanupMgrInfo::GetClientIcon(ushort const *,int)

- ea: `0x14000fa20`
- end: `0x14000fc65`
- name: `?GetClientIcon@CleanupMgrInfo@@IEAAPEAUHICON__@@PEBGH@Z`
- size: `581`
- prototype: `HICON __fastcall(CleanupMgrInfo *this, const unsigned __int16 *, BOOL)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013530`

## callees

- `0x1400029a0`
- `0x140002c80`
- `0x140003390`
- `0x140005fa0`
- `0x140005fe4`
- `0x14000fa20`
- `0x140011ef0`

## import_xrefs

- `USER32!DestroyIcon` at `0x14000fc44`
- `USER32!DestroyIcon` at `0x14000fc44`
- `USER32!LoadIconW` at `0x14000fabf`
- `USER32!LoadIconW` at `0x14000fabf`
- `SHELL32!ExtractIconExW` at `0x14000fc22`
- `SHELL32!ExtractIconExW` at `0x14000fc22`
- `SHLWAPI!StrToIntW` at `0x14000fc01`
- `SHLWAPI!StrToIntW` at `0x14000fc01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fb7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fb7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fb2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fb2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000fb6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000fb6b`

## string_xrefs

- `0x14000faf2`: `CLSID\%s\DefaultIcon`

## pseudocode

```c
HICON __fastcall CleanupMgrInfo::GetClientIcon(CleanupMgrInfo *this, const unsigned __int16 *a2, BOOL a3)
{
  unsigned __int64 v5; // rdx
  HICON v6; // rbx
  int v8; // eax
  int i; // ecx
  __int64 v10; // rdx
  WCHAR v11; // r8
  int v12; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HICON phiconLarge; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  HICON phiconSmall; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[526]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR szFile[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR SubKey[264]; // [rsp+480h] [rbp+380h] BYREF

  hKey = 0;
  phiconLarge = 0;
  phiconSmall = 0;
  memset_0(v20, 0, 0x206u);
  Type = 0;
  cbData = 0;
  *(_WORD *)Data = 0;
  if ( a3 )
  {
    if ( StringCchCopyW((unsigned __int16 *)Data, 0x104u, a2) < 0 )
      return LoadIconW(CleanupMgrInfo::m_hInstance, (LPCWSTR)0x6F);
  }
  else
  {
    if ( StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\DefaultIcon", a2) < 0
      || RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
    {
      return LoadIconW(CleanupMgrInfo::m_hInstance, (LPCWSTR)0x6F);
    }
    Type = 1;
    cbData = 520;
    a3 = RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData) == 0;
    RegCloseKey(hKey);
  }
  if ( !a3 )
    return LoadIconW(CleanupMgrInfo::m_hInstance, (LPCWSTR)0x6F);
  v17 = 0;
  if ( (int)StringCchLengthW((const unsigned __int16 *)Data, v5, &v17) >= 0 )
  {
    v8 = v17;
    for ( i = 0; i < v8; szFile[v10] = v11 )
    {
      v10 = i;
      v11 = *(_WORD *)&Data[2 * i];
      if ( v11 == 44 )
        break;
      ++i;
    }
    if ( (unsigned __int64)(2LL * i) >= 0x208 )
      _report_rangecheckfailure();
    szFile[i] = 0;
    v12 = StrToIntW((PCWSTR)&Data[2 * i + 2]);
    if ( ExtractIconExW(szFile, v12, &phiconLarge, &phiconSmall, 1u) )
    {
      v6 = phiconSmall;
      if ( phiconSmall )
      {
        if ( phiconLarge )
          DestroyIcon(phiconLarge);
      }
      else
      {
        v6 = phiconLarge;
      }
      if ( v6 )
        return v6;
    }
    return LoadIconW(CleanupMgrInfo::m_hInstance, (LPCWSTR)0x6F);
  }
  return 0;
}

```

## disassembly

```asm
0x14000fa20  mov     [rsp-8+arg_0], rbx
0x14000fa25  mov     [rsp-8+arg_10], rdi
0x14000fa2a  push    rbp
0x14000fa2b  lea     rbp, [rsp-5A0h]
0x14000fa33  sub     rsp, 6A0h
0x14000fa3a  mov     rax, cs:__security_cookie
0x14000fa41  xor     rax, rsp
0x14000fa44  mov     [rbp+5A0h+var_10], rax
0x14000fa4b  mov     ebx, r8d
0x14000fa4e  mov     [rsp+6A0h+hKey], 0
0x14000fa57  mov     rdi, rdx
0x14000fa5a  mov     [rsp+6A0h+phiconLarge], 0
0x14000fa63  xor     edx, edx; Val
0x14000fa65  mov     [rsp+6A0h+phiconSmall], 0
0x14000fa6e  mov     r8d, 206h; Size
0x14000fa74  lea     rcx, [rsp+6A0h+var_63E]; void *
0x14000fa79  call    memset_0
0x14000fa7e  xor     eax, eax
0x14000fa80  mov     [rsp+6A0h+Type], 0
0x14000fa88  mov     [rsp+6A0h+cbData], 0
0x14000fa90  mov     edx, 104h; unsigned __int64
0x14000fa95  mov     word ptr [rsp+6A0h+Data], ax
0x14000fa9a  test    ebx, ebx
0x14000fa9c  jz      short loc_14000FAEF
0x14000fa9e  mov     r8, rdi; unsigned __int16 *
0x14000faa1  lea     rcx, [rsp+6A0h+Data]; unsigned __int16 *
0x14000faa6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000faab  test    eax, eax
0x14000faad  jns     loc_14000FB83
0x14000fab3  mov     rcx, cs:?m_hInstance@CleanupMgrInfo@@1PEAUHINSTANCE__@@EA; hInstance
0x14000faba  mov     edx, 6Fh ; 'o'; lpIconName
0x14000fabf  call    cs:__imp_LoadIconW
0x14000fac5  mov     rbx, rax
0x14000fac8  mov     rax, rbx
0x14000facb  mov     rcx, [rbp+5A0h+var_10]
0x14000fad2  xor     rcx, rsp; StackCookie
0x14000fad5  call    __security_check_cookie
0x14000fada  lea     r11, [rsp+6A0h+var_s0]
0x14000fae2  mov     rbx, [r11+10h]
0x14000fae6  mov     rdi, [r11+20h]
0x14000faea  mov     rsp, r11
0x14000faed  pop     rbp
0x14000faee  retn
0x14000faef  mov     r9, rdi
0x14000faf2  lea     r8, aClsidSDefaulti; "CLSID\\%s\\DefaultIcon"
0x14000faf9  lea     rcx, [rbp+5A0h+SubKey]; unsigned __int16 *
0x14000fb00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fb05  test    eax, eax
0x14000fb07  js      short loc_14000FAB3
0x14000fb09  lea     rax, [rsp+6A0h+hKey]
0x14000fb0e  mov     r9d, 20019h; samDesired
0x14000fb14  xor     r8d, r8d; ulOptions
0x14000fb17  mov     [rsp+6A0h+phkResult], rax; phkResult
0x14000fb1c  lea     rdx, [rbp+5A0h+SubKey]; lpSubKey
0x14000fb23  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000fb2a  call    cs:__imp_RegOpenKeyExW
0x14000fb30  test    eax, eax
0x14000fb32  jnz     loc_14000FAB3
0x14000fb38  mov     rcx, [rsp+6A0h+hKey]; hKey
0x14000fb3d  lea     rax, [rsp+6A0h+cbData]
0x14000fb42  mov     [rsp+6A0h+lpcbData], rax; lpcbData
0x14000fb47  lea     r9, [rsp+6A0h+Type]; lpType
0x14000fb4c  lea     rax, [rsp+6A0h+Data]
0x14000fb51  mov     [rsp+6A0h+Type], 1
0x14000fb59  xor     r8d, r8d; lpReserved
0x14000fb5c  mov     [rsp+6A0h+phkResult], rax; lpData
0x14000fb61  xor     edx, edx; lpValueName
0x14000fb63  mov     [rsp+6A0h+cbData], 208h
0x14000fb6b  call    cs:__imp_RegQueryValueExW
0x14000fb71  mov     rcx, [rsp+6A0h+hKey]; hKey
0x14000fb76  xor     ebx, ebx
0x14000fb78  test    eax, eax
0x14000fb7a  setz    bl
0x14000fb7d  call    cs:__imp_RegCloseKey
0x14000fb83  test    ebx, ebx
0x14000fb85  jz      loc_14000FAB3
0x14000fb8b  lea     r8, [rsp+6A0h+var_658]; unsigned __int64 *
0x14000fb90  mov     [rsp+6A0h+var_658], 0
0x14000fb99  lea     rcx, [rsp+6A0h+Data]; unsigned __int16 *
0x14000fb9e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000fba3  test    eax, eax
0x14000fba5  jns     short loc_14000FBAE
0x14000fba7  xor     eax, eax
0x14000fba9  jmp     loc_14000FACB
0x14000fbae  mov     rax, [rsp+6A0h+var_658]
0x14000fbb3  xor     ecx, ecx
0x14000fbb5  test    eax, eax
0x14000fbb7  jle     short loc_14000FBD8
0x14000fbb9  movsxd  rdx, ecx
0x14000fbbc  movzx   r8d, word ptr [rsp+rdx*2+6A0h+Data]
0x14000fbc2  cmp     r8w, 2Ch ; ','
0x14000fbc7  jz      short loc_14000FBD8
0x14000fbc9  inc     ecx
0x14000fbcb  mov     [rbp+rdx*2+5A0h+szFile], r8w
0x14000fbd4  cmp     ecx, eax
0x14000fbd6  jl      short loc_14000FBB9
0x14000fbd8  movsxd  rax, ecx
0x14000fbdb  lea     rdx, [rax+rax]
0x14000fbdf  cmp     rdx, 208h
0x14000fbe6  jnb     short loc_14000FC5F
0x14000fbe8  xor     eax, eax
0x14000fbea  mov     [rbp+rdx+5A0h+szFile], ax
0x14000fbf2  lea     eax, [rcx+1]
0x14000fbf5  movsxd  rcx, eax
0x14000fbf8  lea     rax, [rsp+6A0h+Data]
0x14000fbfd  lea     rcx, [rax+rcx*2]; pszSrc
0x14000fc01  call    cs:__imp_StrToIntW
0x14000fc07  lea     r9, [rsp+6A0h+phiconSmall]; phiconSmall
0x14000fc0c  mov     dword ptr [rsp+6A0h+phkResult], 1; nIcons
0x14000fc14  mov     edx, eax; nIconIndex
0x14000fc16  lea     r8, [rsp+6A0h+phiconLarge]; phiconLarge
0x14000fc1b  lea     rcx, [rbp+5A0h+szFile]; lpszFile
0x14000fc22  call    cs:__imp_ExtractIconExW
0x14000fc28  test    eax, eax
0x14000fc2a  jz      loc_14000FAB3
0x14000fc30  mov     rbx, [rsp+6A0h+phiconSmall]
0x14000fc35  test    rbx, rbx
0x14000fc38  jz      short loc_14000FC4C
0x14000fc3a  mov     rcx, [rsp+6A0h+phiconLarge]; hIcon
0x14000fc3f  test    rcx, rcx
0x14000fc42  jz      short loc_14000FC51
0x14000fc44  call    cs:__imp_DestroyIcon
0x14000fc4a  jmp     short loc_14000FC51
0x14000fc4c  mov     rbx, [rsp+6A0h+phiconLarge]
0x14000fc51  test    rbx, rbx
0x14000fc54  jnz     loc_14000FAC8
0x14000fc5a  jmp     loc_14000FAB3
0x14000fc5f  call    __report_rangecheckfailure
```
