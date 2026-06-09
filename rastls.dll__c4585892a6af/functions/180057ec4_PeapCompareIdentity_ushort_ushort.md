# PeapCompareIdentity(ushort *,ushort *)

- ea: `0x180057ec4`
- end: `0x180058450`
- name: `?PeapCompareIdentity@@YAHPEAG0@Z`
- size: `1420`
- prototype: `int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180030090`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180038e28`
- `0x180038e64`
- `0x180057ec4`
- `0x18005dbe4`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057f37`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800581ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058395`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800583b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057f37`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800581ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058395`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800583b5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180058293`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180058293`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180057f6c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180057f89`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800580fd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058208`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058222`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800582bc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800582dc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800582fe`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180057f6c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180057f89`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800580fd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058208`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058222`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800582bc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800582dc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800582fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180057fd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180057fd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058030`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800580a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058030`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800580a5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005807f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005807f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580c6`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180058367`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180058367`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800583d2`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800583d2`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800583e8`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800583e8`
- `NTDSAPI!DsBindW` at `0x180058321`
- `NTDSAPI!DsBindW` at `0x180058321`

## string_xrefs

- `0x180057fc8`: `netapi32.dll`

## pseudocode

```c
__int64 __fastcall PeapCompareIdentity(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // edi
  HMODULE Library; // rax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // eax
  __int64 v10; // rdx
  wchar_t *v11; // r14
  __int64 v12; // rbx
  __int64 v13; // r9
  _WORD *v14; // r8
  __int64 v15; // rax
  wchar_t *v16; // rax
  wchar_t *v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rbx
  DS_NAME_FORMAT v20; // esi
  PDS_NAME_RESULT_ITEMW rItems; // rdx
  wchar_t *Str; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE phDS; // [rsp+50h] [rbp-B0h] BYREF
  PDS_NAME_RESULTW pResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR DnsDomainName[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[528]; // [rsp+270h] [rbp+170h] BYREF
  _WORD Destination[520]; // [rsp+480h] [rbp+380h] BYREF

  Str = a1;
  phDS = 0;
  pResult = 0;
  memset_0(DnsDomainName, 0, 0x202u);
  memset_0(v28, 0, 0x202u);
  if ( !(unsigned int)_o__wcsicmp(a1, a2) )
  {
    v4 = 1;
    goto LABEL_51;
  }
  v4 = 0;
  if ( wcschr(Str, 0x5Cu) && wcschr(Str, 0x2Eu) )
  {
    memset_0(Destination, 0, 0x402u);
    v24 = 0;
    if ( !g_netapi32Handle )
    {
      Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
      g_netapi32Handle = Library;
      if ( !Library )
      {
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_51;
        LastError = GetLastError();
        v7 = WPP_GLOBAL_Control;
        v8 = 532;
        goto LABEL_9;
      }
      qword_1800ABE38 = (__int64)GetProcAddress(Library, "DsGetDcNameW");
      if ( !qword_1800ABE38 )
      {
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
LABEL_14:
          FreeLibrary(g_netapi32Handle);
          g_netapi32Handle = 0;
          goto LABEL_51;
        }
        v9 = GetLastError();
        v10 = 533;
LABEL_13:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v9);
        goto LABEL_14;
      }
      qword_1800ABE30 = (__int64)GetProcAddress(g_netapi32Handle, "NetApiBufferFree");
      if ( !qword_1800ABE30 )
      {
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_14;
        v9 = GetLastError();
        v10 = 534;
        goto LABEL_13;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 535, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    }
    v11 = wcschr(Str, 0x5Cu);
    *v11 = 0;
    LastError = ((__int64 (__fastcall *)(_QWORD, wchar_t *, _QWORD, _QWORD, int, __int64 *))qword_1800ABE38)(
                  0,
                  Str,
                  0,
                  0,
                  -2147352576,
                  &v24);
    *v11 = 92;
    if ( LastError )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v8 = 536;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
      }
    }
    else
    {
      v12 = -1;
      v13 = -1;
      v14 = *(_WORD **)(v24 + 40);
      do
        ++v13;
      while ( v14[v13] );
      memcpy_s_2(Destination, 0x402u, v14, 2 * v13);
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(*(_QWORD *)(v24 + 40) + 2 * v15) );
      do
        ++v12;
      while ( v11[v12] );
      memcpy_s_2(&Destination[v15], 1026 - 2 * v15, v11, 2 * v12);
      ((void (__fastcall *)(__int64))qword_1800ABE30)(v24);
      LOBYTE(v4) = (unsigned int)_o__wcsicmp(Destination, a2) == 0;
    }
  }
  else if ( !wcschr(Str, 0x5Cu) )
  {
    v16 = wcschr(a2, 0x5Cu);
    v17 = v16;
    if ( v16 )
    {
      v18 = v16 - a2;
      memcpy_s_2(DnsDomainName, 0x202u, a2, 2 * v18);
      v19 = -1;
      do
        ++v19;
      while ( a2[v19] );
      memcpy_s_2(v28, 0x202u, v17 + 1, 2 * (v19 - v18) - 2);
      if ( wcsstr(Str, L"host/") )
      {
        v20 = DS_SERVICE_PRINCIPAL_NAME;
      }
      else if ( wcschr(Str, 0x40u) )
      {
        v20 = DS_USER_PRINCIPAL_NAME;
      }
      else if ( wcschr(Str, 0x2Fu) )
      {
        v20 = DS_CANONICAL_NAME;
      }
      else
      {
        if ( !wcschr(Str, 0x3Du) )
        {
          if ( !(unsigned int)_o__wcsicmp(Str, v28) )
            v4 = 1;
          goto LABEL_51;
        }
        v20 = DS_FQDN_1779_NAME;
      }
      if ( !DsBindW(0, DnsDomainName, &phDS) )
      {
        if ( !phDS )
          goto LABEL_53;
        if ( !DsCrackNamesW(
                phDS,
                DS_NAME_FLAG_TRUST_REFERRAL,
                v20,
                DS_NT4_ACCOUNT_NAME,
                1u,
                (const LPCWSTR *)&Str,
                &pResult) )
        {
          if ( pResult )
          {
            if ( pResult->cItems == 1 )
            {
              rItems = pResult->rItems;
              if ( !rItems->status && !(unsigned int)_o__wcsicmp(a2, rItems->pName) )
                v4 = 1;
            }
          }
        }
      }
    }
  }
LABEL_51:
  if ( phDS )
    DsUnBindW(&phDS);
LABEL_53:
  if ( pResult )
    DsFreeNameResultW(pResult);
  if ( !v4 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      537,
      (unsigned int)&WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
      (_DWORD)Str,
      (__int64)a2);
  return v4;
}

```

## disassembly

```asm
0x180057ec4  mov     [rsp-8+arg_10], rbx
0x180057ec9  push    rbp
0x180057eca  push    rsi
0x180057ecb  push    rdi
0x180057ecc  push    r12
0x180057ece  push    r13
0x180057ed0  push    r14
0x180057ed2  push    r15
0x180057ed4  lea     rbp, [rsp-7A0h]
0x180057edc  sub     rsp, 8A0h
0x180057ee3  mov     rax, cs:__security_cookie
0x180057eea  xor     rax, rsp
0x180057eed  mov     [rbp+7D0h+var_40], rax
0x180057ef4  mov     r15, rdx
0x180057ef7  mov     [rsp+8D0h+Str], rcx
0x180057efc  mov     rbx, rcx
0x180057eff  xor     r12d, r12d
0x180057f02  mov     edi, 202h
0x180057f07  mov     [rsp+8D0h+phDS], r12
0x180057f0c  mov     r8d, edi; Size
0x180057f0f  mov     [rsp+8D0h+pResult], r12
0x180057f14  xor     edx, edx; Val
0x180057f16  lea     rcx, [rsp+8D0h+DnsDomainName]; void *
0x180057f1b  call    memset_0
0x180057f20  mov     r8d, edi; Size
0x180057f23  lea     rcx, [rbp+7D0h+var_660]; void *
0x180057f2a  xor     edx, edx; Val
0x180057f2c  call    memset_0
0x180057f31  mov     rdx, r15
0x180057f34  mov     rcx, rbx
0x180057f37  call    cs:__imp__o__wcsicmp
0x180057f3e  nop     dword ptr [rax+rax+00h]
0x180057f43  lea     r13, WPP_GLOBAL_Control
0x180057f4a  lea     r14, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180057f51  test    eax, eax
0x180057f53  jnz     short loc_180057F5D
0x180057f55  lea     edi, [rax+1]
0x180057f58  jmp     loc_1800583C6
0x180057f5d  mov     rcx, [rsp+8D0h+Str]; Str
0x180057f62  mov     ebx, 5Ch ; '\'
0x180057f67  mov     edx, ebx; Ch
0x180057f69  mov     edi, r12d
0x180057f6c  call    cs:__imp_wcschr
0x180057f73  nop     dword ptr [rax+rax+00h]
0x180057f78  test    rax, rax
0x180057f7b  jz      loc_180058201
0x180057f81  mov     rcx, [rsp+8D0h+Str]; Str
0x180057f86  lea     edx, [rbx-2Eh]; Ch
0x180057f89  call    cs:__imp_wcschr
0x180057f90  nop     dword ptr [rax+rax+00h]
0x180057f95  test    rax, rax
0x180057f98  jz      loc_180058201
0x180057f9e  mov     esi, 402h
0x180057fa3  lea     rcx, [rbp+7D0h+Destination]; void *
0x180057faa  mov     r8d, esi; Size
0x180057fad  xor     edx, edx; Val
0x180057faf  call    memset_0
0x180057fb4  cmp     cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_netapi32Handle
0x180057fbb  mov     [rsp+8D0h+var_888], r12
0x180057fc0  jnz     loc_1800580F6
0x180057fc6  xor     edx, edx; hFile
0x180057fc8  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x180057fcf  mov     r8d, 800h; dwFlags
0x180057fd5  call    cs:__imp_LoadLibraryExW
0x180057fdc  nop     dword ptr [rax+rax+00h]
0x180057fe1  mov     cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_netapi32Handle
0x180057fe8  test    rax, rax
0x180057feb  jnz     short loc_180058026
0x180057fed  cmp     cs:WPP_GLOBAL_Control, r13
0x180057ff4  jz      loc_1800583C6
0x180057ffa  call    cs:__imp_GetLastError
0x180058001  nop     dword ptr [rax+rax+00h]
0x180058006  mov     rcx, cs:WPP_GLOBAL_Control
0x18005800d  mov     edx, 214h
0x180058012  mov     r8, r14
0x180058015  mov     rcx, [rcx+10h]
0x180058019  mov     r9d, eax
0x18005801c  call    WPP_SF_d
0x180058021  jmp     loc_1800583C6
0x180058026  lea     rdx, aDsgetdcnamew; "DsGetDcNameW"
0x18005802d  mov     rcx, rax; hModule
0x180058030  call    cs:__imp_GetProcAddress
0x180058037  nop     dword ptr [rax+rax+00h]
0x18005803c  mov     cs:qword_1800ABE38, rax
0x180058043  test    rax, rax
0x180058046  jnz     short loc_180058097
0x180058048  cmp     cs:WPP_GLOBAL_Control, r13
0x18005804f  jz      short loc_180058078
0x180058051  call    cs:__imp_GetLastError
0x180058058  nop     dword ptr [rax+rax+00h]
0x18005805d  mov     edx, 215h
0x180058062  mov     rcx, cs:WPP_GLOBAL_Control
0x180058069  mov     r9d, eax
0x18005806c  mov     r8, r14
0x18005806f  mov     rcx, [rcx+10h]
0x180058073  call    WPP_SF_d
0x180058078  mov     rcx, cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA; hLibModule
0x18005807f  call    cs:__imp_FreeLibrary
0x180058086  nop     dword ptr [rax+rax+00h]
0x18005808b  mov     cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_netapi32Handle
0x180058092  jmp     loc_1800583C6
0x180058097  mov     rcx, cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA; hModule
0x18005809e  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x1800580a5  call    cs:__imp_GetProcAddress
0x1800580ac  nop     dword ptr [rax+rax+00h]
0x1800580b1  mov     cs:qword_1800ABE30, rax
0x1800580b8  test    rax, rax
0x1800580bb  jnz     short loc_1800580D9
0x1800580bd  cmp     cs:WPP_GLOBAL_Control, r13
0x1800580c4  jz      short loc_180058078
0x1800580c6  call    cs:__imp_GetLastError
0x1800580cd  nop     dword ptr [rax+rax+00h]
0x1800580d2  mov     edx, 216h
0x1800580d7  jmp     short loc_180058062
0x1800580d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580e0  cmp     rcx, r13
0x1800580e3  jz      short loc_1800580F6
0x1800580e5  mov     rcx, [rcx+10h]
0x1800580e9  mov     edx, 217h
0x1800580ee  mov     r8, r14
0x1800580f1  call    WPP_SF_
0x1800580f6  mov     rcx, [rsp+8D0h+Str]; Str
0x1800580fb  mov     edx, ebx; Ch
0x1800580fd  call    cs:__imp_wcschr
0x180058104  nop     dword ptr [rax+rax+00h]
0x180058109  xor     r9d, r9d
0x18005810c  xor     r8d, r8d
0x18005810f  mov     r14, rax
0x180058112  xor     ecx, ecx
0x180058114  mov     [rax], r12w
0x180058118  lea     rax, [rsp+8D0h+var_888]
0x18005811d  mov     rdx, [rsp+8D0h+Str]
0x180058122  mov     [rsp+8D0h+rpNames], rax
0x180058127  mov     rax, cs:qword_1800ABE38
0x18005812e  mov     [rsp+8D0h+cNames], 80020000h
0x180058136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005813b  mov     [r14], bx
0x18005813f  test    eax, eax
0x180058141  jz      short loc_180058164
0x180058143  mov     rcx, cs:WPP_GLOBAL_Control
0x18005814a  cmp     rcx, r13
0x18005814d  jz      loc_1800583C6
0x180058153  mov     edx, 218h
0x180058158  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005815f  jmp     loc_180058015
0x180058164  mov     rax, [rsp+8D0h+var_888]
0x180058169  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005816d  mov     r9, rbx
0x180058170  mov     r8, [rax+28h]; Source
0x180058174  inc     r9
0x180058177  cmp     [r8+r9*2], r12w
0x18005817c  jnz     short loc_180058174
0x18005817e  add     r9, r9; SourceSize
0x180058181  lea     rcx, [rbp+7D0h+Destination]; Destination
0x180058188  mov     rdx, rsi; DestinationSize
0x18005818b  call    memcpy_s_2
0x180058190  mov     rax, [rsp+8D0h+var_888]
0x180058195  mov     rcx, [rax+28h]
0x180058199  mov     rax, rbx
0x18005819c  inc     rax
0x18005819f  cmp     [rcx+rax*2], r12w
0x1800581a4  jnz     short loc_18005819C
0x1800581a6  inc     rbx
0x1800581a9  cmp     [r14+rbx*2], r12w
0x1800581ae  jnz     short loc_1800581A6
0x1800581b0  add     rax, rax
0x1800581b3  lea     rcx, [rbp+7D0h+Destination]
0x1800581ba  sub     rsi, rax
0x1800581bd  lea     r9, [rbx+rbx]; SourceSize
0x1800581c1  mov     rdx, rsi; DestinationSize
0x1800581c4  add     rcx, rax; Destination
0x1800581c7  mov     r8, r14; Source
0x1800581ca  call    memcpy_s_2
0x1800581cf  mov     rcx, [rsp+8D0h+var_888]
0x1800581d4  mov     rax, cs:qword_1800ABE30
0x1800581db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581e0  mov     rdx, r15
0x1800581e3  lea     rcx, [rbp+7D0h+Destination]
0x1800581ea  call    cs:__imp__o__wcsicmp
0x1800581f1  nop     dword ptr [rax+rax+00h]
0x1800581f6  test    eax, eax
0x1800581f8  setz    dil
0x1800581fc  jmp     loc_1800583C6
0x180058201  mov     rcx, [rsp+8D0h+Str]; Str
0x180058206  mov     edx, ebx; Ch
0x180058208  call    cs:__imp_wcschr
0x18005820f  nop     dword ptr [rax+rax+00h]
0x180058214  test    rax, rax
0x180058217  jnz     loc_1800583C6
0x18005821d  mov     edx, ebx; Ch
0x18005821f  mov     rcx, r15; Str
0x180058222  call    cs:__imp_wcschr
0x180058229  nop     dword ptr [rax+rax+00h]
0x18005822e  mov     r14, rax
0x180058231  test    rax, rax
0x180058234  jz      loc_1800583C6
0x18005823a  mov     rsi, rax
0x18005823d  lea     rcx, [rsp+8D0h+DnsDomainName]; Destination
0x180058242  sub     rsi, r15
0x180058245  mov     r8, r15; Source
0x180058248  sar     rsi, 1
0x18005824b  mov     edx, 202h; DestinationSize
0x180058250  lea     r9, [rsi+rsi]; SourceSize
0x180058254  call    memcpy_s_2
0x180058259  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005825d  inc     rbx
0x180058260  cmp     [r15+rbx*2], r12w
0x180058265  jnz     short loc_18005825D
0x180058267  sub     rbx, rsi
0x18005826a  lea     r8, [r14+2]; Source
0x18005826e  mov     edx, 202h; DestinationSize
0x180058273  lea     rcx, [rbp+7D0h+var_660]; Destination
0x18005827a  lea     r9, ds:0FFFFFFFFFFFFFFFEh[rbx*2]; SourceSize
0x180058282  call    memcpy_s_2
0x180058287  mov     rcx, [rsp+8D0h+Str]; Str
0x18005828c  lea     rdx, aHost; "host/"
0x180058293  call    cs:__imp_wcsstr
0x18005829a  nop     dword ptr [rax+rax+00h]
0x18005829f  mov     ebx, 1
0x1800582a4  lea     r14d, [rbx+7]
0x1800582a8  test    rax, rax
0x1800582ab  jz      short loc_1800582B2
0x1800582ad  lea     esi, [rbx+9]
0x1800582b0  jmp     short loc_180058315
0x1800582b2  mov     rcx, [rsp+8D0h+Str]; Str
0x1800582b7  mov     edx, 40h ; '@'; Ch
0x1800582bc  call    cs:__imp_wcschr
0x1800582c3  nop     dword ptr [rax+rax+00h]
0x1800582c8  test    rax, rax
0x1800582cb  jz      short loc_1800582D2
0x1800582cd  mov     esi, r14d
0x1800582d0  jmp     short loc_180058315
0x1800582d2  mov     rcx, [rsp+8D0h+Str]; Str
0x1800582d7  mov     edx, 2Fh ; '/'; Ch
0x1800582dc  call    cs:__imp_wcschr
0x1800582e3  nop     dword ptr [rax+rax+00h]
0x1800582e8  test    rax, rax
0x1800582eb  jz      short loc_1800582F4
0x1800582ed  mov     esi, 7
0x1800582f2  jmp     short loc_180058315
0x1800582f4  mov     rcx, [rsp+8D0h+Str]; Str
0x1800582f9  mov     edx, 3Dh ; '='; Ch
0x1800582fe  call    cs:__imp_wcschr
0x180058305  nop     dword ptr [rax+rax+00h]
0x18005830a  test    rax, rax
0x18005830d  jz      loc_1800583A9
0x180058313  mov     esi, ebx
0x180058315  lea     r8, [rsp+8D0h+phDS]; phDS
0x18005831a  xor     ecx, ecx; DomainControllerName
0x18005831c  lea     rdx, [rsp+8D0h+DnsDomainName]; DnsDomainName
0x180058321  call    cs:__imp_DsBindW
0x180058328  nop     dword ptr [rax+rax+00h]
0x18005832d  test    eax, eax
0x18005832f  jnz     loc_1800583C6
0x180058335  mov     rcx, [rsp+8D0h+phDS]; hDS
0x18005833a  test    rcx, rcx
0x18005833d  jz      loc_1800583DE
0x180058343  lea     rax, [rsp+8D0h+pResult]
0x180058348  mov     r9d, 2; formatDesired
0x18005834e  mov     [rsp+8D0h+ppResult], rax; ppResult
0x180058353  mov     r8d, esi; formatOffered
0x180058356  lea     rax, [rsp+8D0h+Str]
0x18005835b  mov     edx, r14d; flags
0x18005835e  mov     [rsp+8D0h+rpNames], rax; rpNames
0x180058363  mov     [rsp+8D0h+cNames], ebx; cNames
0x180058367  call    cs:__imp_DsCrackNamesW
0x18005836e  nop     dword ptr [rax+rax+00h]
0x180058373  test    eax, eax
0x180058375  jnz     short loc_1800583C6
0x180058377  mov     rcx, [rsp+8D0h+pResult]
0x18005837c  test    rcx, rcx
0x18005837f  jz      short loc_1800583C6
0x180058381  cmp     [rcx], ebx
0x180058383  jnz     short loc_1800583C6
0x180058385  mov     rdx, [rcx+8]
0x180058389  cmp     [rdx], r12d
0x18005838c  jnz     short loc_1800583C6
0x18005838e  mov     rdx, [rdx+10h]
0x180058392  mov     rcx, r15
0x180058395  call    cs:__imp__o__wcsicmp
0x18005839c  nop     dword ptr [rax+rax+00h]
0x1800583a1  test    eax, eax
0x1800583a3  jnz     short loc_1800583C6
0x1800583a5  mov     edi, ebx
0x1800583a7  jmp     short loc_1800583C6
0x1800583a9  mov     rcx, [rsp+8D0h+Str]
0x1800583ae  lea     rdx, [rbp+7D0h+var_660]
0x1800583b5  call    cs:__imp__o__wcsicmp
0x1800583bc  nop     dword ptr [rax+rax+00h]
0x1800583c1  test    eax, eax
0x1800583c3  cmovz   edi, ebx
0x1800583c6  cmp     [rsp+8D0h+phDS], r12
0x1800583cb  jz      short loc_1800583DE
0x1800583cd  lea     rcx, [rsp+8D0h+phDS]; phDS
0x1800583d2  call    cs:__imp_DsUnBindW
0x1800583d9  nop     dword ptr [rax+rax+00h]
0x1800583de  mov     rcx, [rsp+8D0h+pResult]; pResult
0x1800583e3  test    rcx, rcx
0x1800583e6  jz      short loc_1800583F4
0x1800583e8  call    cs:__imp_DsFreeNameResultW
  ... truncated ...
```
