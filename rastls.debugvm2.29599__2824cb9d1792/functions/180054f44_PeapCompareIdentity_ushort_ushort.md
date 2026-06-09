# PeapCompareIdentity(ushort *,ushort *)

- ea: `0x180054f44`
- end: `0x18005543b`
- name: `?PeapCompareIdentity@@YAHPEAG0@Z`
- size: `1271`
- prototype: `int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d9e8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x180036218`
- `0x180036254`
- `0x180054f44`
- `0x18005a800`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180054fb7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055228`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055399`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800553b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180054fb7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055228`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055399`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800553b3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800552bf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800552bf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180054fe6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180054ffd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055141`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055240`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055254`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800552e2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800552fc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055318`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180054fe6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180054ffd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055141`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055240`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055254`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800552e2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800552fc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055318`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055043`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055043`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055092`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800550f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055092`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800550f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800550d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800550d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055110`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180055371`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180055371`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800553ca`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800553ca`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800553da`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800553da`
- `NTDSAPI!DsBindW` at `0x180055335`
- `NTDSAPI!DsBindW` at `0x180055335`

## string_xrefs

- `0x180055036`: `netapi32.dll`

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
      qword_1800A5D78 = (__int64)GetProcAddress(Library, "DsGetDcNameW");
      if ( !qword_1800A5D78 )
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v9);
        goto LABEL_14;
      }
      qword_1800A5D70 = (__int64)GetProcAddress(g_netapi32Handle, "NetApiBufferFree");
      if ( !qword_1800A5D70 )
      {
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_14;
        v9 = GetLastError();
        v10 = 534;
        goto LABEL_13;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 535, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    }
    v11 = wcschr(Str, 0x5Cu);
    *v11 = 0;
    LastError = ((__int64 (__fastcall *)(_QWORD, wchar_t *, _QWORD, _QWORD, int, __int64 *))qword_1800A5D78)(
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
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
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
      ((void (__fastcall *)(__int64))qword_1800A5D70)(v24);
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
      (unsigned int)&WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
      (_DWORD)Str,
      (__int64)a2);
  return v4;
}

```

## disassembly

```asm
0x180054f44  mov     [rsp-8+arg_10], rbx
0x180054f49  push    rbp
0x180054f4a  push    rsi
0x180054f4b  push    rdi
0x180054f4c  push    r12
0x180054f4e  push    r13
0x180054f50  push    r14
0x180054f52  push    r15
0x180054f54  lea     rbp, [rsp-7A0h]
0x180054f5c  sub     rsp, 8A0h
0x180054f63  mov     rax, cs:__security_cookie
0x180054f6a  xor     rax, rsp
0x180054f6d  mov     [rbp+7D0h+var_40], rax
0x180054f74  mov     r15, rdx
0x180054f77  mov     [rsp+8D0h+Str], rcx
0x180054f7c  mov     rbx, rcx
0x180054f7f  xor     r12d, r12d
0x180054f82  mov     edi, 202h
0x180054f87  mov     [rsp+8D0h+phDS], r12
0x180054f8c  mov     r8d, edi; Size
0x180054f8f  mov     [rsp+8D0h+pResult], r12
0x180054f94  xor     edx, edx; Val
0x180054f96  lea     rcx, [rsp+8D0h+DnsDomainName]; void *
0x180054f9b  call    memset_0
0x180054fa0  mov     r8d, edi; Size
0x180054fa3  lea     rcx, [rbp+7D0h+var_660]; void *
0x180054faa  xor     edx, edx; Val
0x180054fac  call    memset_0
0x180054fb1  mov     rdx, r15
0x180054fb4  mov     rcx, rbx
0x180054fb7  call    cs:__imp__o__wcsicmp
0x180054fbd  lea     r13, WPP_GLOBAL_Control
0x180054fc4  lea     r14, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180054fcb  test    eax, eax
0x180054fcd  jnz     short loc_180054FD7
0x180054fcf  lea     edi, [rax+1]
0x180054fd2  jmp     loc_1800553BE
0x180054fd7  mov     rcx, [rsp+8D0h+Str]; Str
0x180054fdc  mov     ebx, 5Ch ; '\'
0x180054fe1  mov     edx, ebx; Ch
0x180054fe3  mov     edi, r12d
0x180054fe6  call    cs:__imp_wcschr
0x180054fec  test    rax, rax
0x180054fef  jz      loc_180055239
0x180054ff5  mov     rcx, [rsp+8D0h+Str]; Str
0x180054ffa  lea     edx, [rbx-2Eh]; Ch
0x180054ffd  call    cs:__imp_wcschr
0x180055003  test    rax, rax
0x180055006  jz      loc_180055239
0x18005500c  mov     esi, 402h
0x180055011  lea     rcx, [rbp+7D0h+Destination]; void *
0x180055018  mov     r8d, esi; Size
0x18005501b  xor     edx, edx; Val
0x18005501d  call    memset_0
0x180055022  cmp     cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_netapi32Handle
0x180055029  mov     [rsp+8D0h+var_888], r12
0x18005502e  jnz     loc_18005513A
0x180055034  xor     edx, edx; hFile
0x180055036  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18005503d  mov     r8d, 800h; dwFlags
0x180055043  call    cs:__imp_LoadLibraryExW
0x180055049  mov     cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_netapi32Handle
0x180055050  test    rax, rax
0x180055053  jnz     short loc_180055088
0x180055055  cmp     cs:WPP_GLOBAL_Control, r13
0x18005505c  jz      loc_1800553BE
0x180055062  call    cs:__imp_GetLastError
0x180055068  mov     rcx, cs:WPP_GLOBAL_Control
0x18005506f  mov     edx, 214h
0x180055074  mov     r8, r14
0x180055077  mov     rcx, [rcx+10h]
0x18005507b  mov     r9d, eax
0x18005507e  call    WPP_SF_d
0x180055083  jmp     loc_1800553BE
0x180055088  lea     rdx, aDsgetdcnamew; "DsGetDcNameW"
0x18005508f  mov     rcx, rax; hModule
0x180055092  call    cs:__imp_GetProcAddress
0x180055098  mov     cs:qword_1800A5D78, rax
0x18005509f  test    rax, rax
0x1800550a2  jnz     short loc_1800550E7
0x1800550a4  cmp     cs:WPP_GLOBAL_Control, r13
0x1800550ab  jz      short loc_1800550CE
0x1800550ad  call    cs:__imp_GetLastError
0x1800550b3  mov     edx, 215h
0x1800550b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550bf  mov     r9d, eax
0x1800550c2  mov     r8, r14
0x1800550c5  mov     rcx, [rcx+10h]
0x1800550c9  call    WPP_SF_d
0x1800550ce  mov     rcx, cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800550d5  call    cs:__imp_FreeLibrary
0x1800550db  mov     cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_netapi32Handle
0x1800550e2  jmp     loc_1800553BE
0x1800550e7  mov     rcx, cs:?g_netapi32Handle@@3PEAUHINSTANCE__@@EA; hModule
0x1800550ee  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x1800550f5  call    cs:__imp_GetProcAddress
0x1800550fb  mov     cs:qword_1800A5D70, rax
0x180055102  test    rax, rax
0x180055105  jnz     short loc_18005511D
0x180055107  cmp     cs:WPP_GLOBAL_Control, r13
0x18005510e  jz      short loc_1800550CE
0x180055110  call    cs:__imp_GetLastError
0x180055116  mov     edx, 216h
0x18005511b  jmp     short loc_1800550B8
0x18005511d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055124  cmp     rcx, r13
0x180055127  jz      short loc_18005513A
0x180055129  mov     rcx, [rcx+10h]
0x18005512d  mov     edx, 217h
0x180055132  mov     r8, r14
0x180055135  call    WPP_SF_
0x18005513a  mov     rcx, [rsp+8D0h+Str]; Str
0x18005513f  mov     edx, ebx; Ch
0x180055141  call    cs:__imp_wcschr
0x180055147  xor     r9d, r9d
0x18005514a  xor     r8d, r8d
0x18005514d  mov     r14, rax
0x180055150  xor     ecx, ecx
0x180055152  mov     [rax], r12w
0x180055156  lea     rax, [rsp+8D0h+var_888]
0x18005515b  mov     rdx, [rsp+8D0h+Str]
0x180055160  mov     [rsp+8D0h+rpNames], rax
0x180055165  mov     rax, cs:qword_1800A5D78
0x18005516c  mov     [rsp+8D0h+cNames], 80020000h
0x180055174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055179  mov     [r14], bx
0x18005517d  test    eax, eax
0x18005517f  jz      short loc_1800551A2
0x180055181  mov     rcx, cs:WPP_GLOBAL_Control
0x180055188  cmp     rcx, r13
0x18005518b  jz      loc_1800553BE
0x180055191  mov     edx, 218h
0x180055196  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005519d  jmp     loc_180055077
0x1800551a2  mov     rax, [rsp+8D0h+var_888]
0x1800551a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800551ab  mov     r9, rbx
0x1800551ae  mov     r8, [rax+28h]; Source
0x1800551b2  inc     r9
0x1800551b5  cmp     [r8+r9*2], r12w
0x1800551ba  jnz     short loc_1800551B2
0x1800551bc  add     r9, r9; SourceSize
0x1800551bf  lea     rcx, [rbp+7D0h+Destination]; Destination
0x1800551c6  mov     rdx, rsi; DestinationSize
0x1800551c9  call    memcpy_s_2
0x1800551ce  mov     rax, [rsp+8D0h+var_888]
0x1800551d3  mov     rcx, [rax+28h]
0x1800551d7  mov     rax, rbx
0x1800551da  inc     rax
0x1800551dd  cmp     [rcx+rax*2], r12w
0x1800551e2  jnz     short loc_1800551DA
0x1800551e4  inc     rbx
0x1800551e7  cmp     [r14+rbx*2], r12w
0x1800551ec  jnz     short loc_1800551E4
0x1800551ee  add     rax, rax
0x1800551f1  lea     rcx, [rbp+7D0h+Destination]
0x1800551f8  sub     rsi, rax
0x1800551fb  lea     r9, [rbx+rbx]; SourceSize
0x1800551ff  mov     rdx, rsi; DestinationSize
0x180055202  add     rcx, rax; Destination
0x180055205  mov     r8, r14; Source
0x180055208  call    memcpy_s_2
0x18005520d  mov     rcx, [rsp+8D0h+var_888]
0x180055212  mov     rax, cs:qword_1800A5D70
0x180055219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005521e  mov     rdx, r15
0x180055221  lea     rcx, [rbp+7D0h+Destination]
0x180055228  call    cs:__imp__o__wcsicmp
0x18005522e  test    eax, eax
0x180055230  setz    dil
0x180055234  jmp     loc_1800553BE
0x180055239  mov     rcx, [rsp+8D0h+Str]; Str
0x18005523e  mov     edx, ebx; Ch
0x180055240  call    cs:__imp_wcschr
0x180055246  test    rax, rax
0x180055249  jnz     loc_1800553BE
0x18005524f  mov     edx, ebx; Ch
0x180055251  mov     rcx, r15; Str
0x180055254  call    cs:__imp_wcschr
0x18005525a  mov     r14, rax
0x18005525d  test    rax, rax
0x180055260  jz      loc_1800553BE
0x180055266  mov     rsi, rax
0x180055269  lea     rcx, [rsp+8D0h+DnsDomainName]; Destination
0x18005526e  sub     rsi, r15
0x180055271  mov     r8, r15; Source
0x180055274  sar     rsi, 1
0x180055277  mov     edx, 202h; DestinationSize
0x18005527c  lea     r9, [rsi+rsi]; SourceSize
0x180055280  call    memcpy_s_2
0x180055285  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180055289  inc     rbx
0x18005528c  cmp     [r15+rbx*2], r12w
0x180055291  jnz     short loc_180055289
0x180055293  sub     rbx, rsi
0x180055296  lea     r8, [r14+2]; Source
0x18005529a  mov     edx, 202h; DestinationSize
0x18005529f  lea     rcx, [rbp+7D0h+var_660]; Destination
0x1800552a6  lea     r9, ds:0FFFFFFFFFFFFFFFEh[rbx*2]; SourceSize
0x1800552ae  call    memcpy_s_2
0x1800552b3  mov     rcx, [rsp+8D0h+Str]; Str
0x1800552b8  lea     rdx, aHost; "host/"
0x1800552bf  call    cs:__imp_wcsstr
0x1800552c5  mov     ebx, 1
0x1800552ca  lea     r14d, [rbx+7]
0x1800552ce  test    rax, rax
0x1800552d1  jz      short loc_1800552D8
0x1800552d3  lea     esi, [rbx+9]
0x1800552d6  jmp     short loc_180055329
0x1800552d8  mov     rcx, [rsp+8D0h+Str]; Str
0x1800552dd  mov     edx, 40h ; '@'; Ch
0x1800552e2  call    cs:__imp_wcschr
0x1800552e8  test    rax, rax
0x1800552eb  jz      short loc_1800552F2
0x1800552ed  mov     esi, r14d
0x1800552f0  jmp     short loc_180055329
0x1800552f2  mov     rcx, [rsp+8D0h+Str]; Str
0x1800552f7  mov     edx, 2Fh ; '/'; Ch
0x1800552fc  call    cs:__imp_wcschr
0x180055302  test    rax, rax
0x180055305  jz      short loc_18005530E
0x180055307  mov     esi, 7
0x18005530c  jmp     short loc_180055329
0x18005530e  mov     rcx, [rsp+8D0h+Str]; Str
0x180055313  mov     edx, 3Dh ; '='; Ch
0x180055318  call    cs:__imp_wcschr
0x18005531e  test    rax, rax
0x180055321  jz      loc_1800553A7
0x180055327  mov     esi, ebx
0x180055329  lea     r8, [rsp+8D0h+phDS]; phDS
0x18005532e  xor     ecx, ecx; DomainControllerName
0x180055330  lea     rdx, [rsp+8D0h+DnsDomainName]; DnsDomainName
0x180055335  call    cs:__imp_DsBindW
0x18005533b  test    eax, eax
0x18005533d  jnz     short loc_1800553BE
0x18005533f  mov     rcx, [rsp+8D0h+phDS]; hDS
0x180055344  test    rcx, rcx
0x180055347  jz      loc_1800553D0
0x18005534d  lea     rax, [rsp+8D0h+pResult]
0x180055352  mov     r9d, 2; formatDesired
0x180055358  mov     [rsp+8D0h+ppResult], rax; ppResult
0x18005535d  mov     r8d, esi; formatOffered
0x180055360  lea     rax, [rsp+8D0h+Str]
0x180055365  mov     edx, r14d; flags
0x180055368  mov     [rsp+8D0h+rpNames], rax; rpNames
0x18005536d  mov     [rsp+8D0h+cNames], ebx; cNames
0x180055371  call    cs:__imp_DsCrackNamesW
0x180055377  test    eax, eax
0x180055379  jnz     short loc_1800553BE
0x18005537b  mov     rcx, [rsp+8D0h+pResult]
0x180055380  test    rcx, rcx
0x180055383  jz      short loc_1800553BE
0x180055385  cmp     [rcx], ebx
0x180055387  jnz     short loc_1800553BE
0x180055389  mov     rdx, [rcx+8]
0x18005538d  cmp     [rdx], r12d
0x180055390  jnz     short loc_1800553BE
0x180055392  mov     rdx, [rdx+10h]
0x180055396  mov     rcx, r15
0x180055399  call    cs:__imp__o__wcsicmp
0x18005539f  test    eax, eax
0x1800553a1  jnz     short loc_1800553BE
0x1800553a3  mov     edi, ebx
0x1800553a5  jmp     short loc_1800553BE
0x1800553a7  mov     rcx, [rsp+8D0h+Str]
0x1800553ac  lea     rdx, [rbp+7D0h+var_660]
0x1800553b3  call    cs:__imp__o__wcsicmp
0x1800553b9  test    eax, eax
0x1800553bb  cmovz   edi, ebx
0x1800553be  cmp     [rsp+8D0h+phDS], r12
0x1800553c3  jz      short loc_1800553D0
0x1800553c5  lea     rcx, [rsp+8D0h+phDS]; phDS
0x1800553ca  call    cs:__imp_DsUnBindW
0x1800553d0  mov     rcx, [rsp+8D0h+pResult]; pResult
0x1800553d5  test    rcx, rcx
0x1800553d8  jz      short loc_1800553E0
0x1800553da  call    cs:__imp_DsFreeNameResultW
0x1800553e0  test    edi, edi
0x1800553e2  jnz     short loc_18005540F
0x1800553e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553eb  cmp     rcx, r13
0x1800553ee  jz      short loc_18005540F
0x1800553f0  mov     r9, [rsp+8D0h+Str]
0x1800553f5  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800553fc  mov     rcx, [rcx+10h]
0x180055400  mov     edx, 219h
0x180055405  mov     qword ptr [rsp+8D0h+cNames], r15
0x18005540a  call    WPP_SF_SS
0x18005540f  mov     eax, edi
0x180055411  mov     rcx, [rbp+7D0h+var_40]
0x180055418  xor     rcx, rsp; StackCookie
0x18005541b  call    __security_check_cookie
0x180055420  mov     rbx, [rsp+8D0h+arg_10]
0x180055428  add     rsp, 8A0h
0x18005542f  pop     r15
0x180055431  pop     r14
0x180055433  pop     r13
0x180055435  pop     r12
0x180055437  pop     rdi
0x180055438  pop     rsi
  ... truncated ...
```
