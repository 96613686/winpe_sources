# MprConfigInterfaceCreateEx

- ea: `0x1800236e0`
- end: `0x180023e39`
- name: `MprConfigInterfaceCreateEx`
- size: `1881`
- prototype: `__int64 __fastcall(HANDLE hMprConfig)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callees

- `0x180009868`
- `0x18000a070`
- `0x180017700`
- `0x1800178ac`
- `0x180017960`
- `0x180017a10`
- `0x1800184d0`
- `0x180022324`
- `0x1800236e0`
- `0x180023e40`
- `0x180027d5c`
- `0x1800291b4`
- `0x18002998c`
- `0x1800418e0`
- `0x18004214c`
- `0x180043390`
- `0x180043498`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `msvcrt!free` at `0x180023dd3`
- `msvcrt!free` at `0x180023dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800237b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800237b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023821`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023832`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023bb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023bb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180023b5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180023b5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023cc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023cf4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023d22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023d76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023dc3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023cc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023cf4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023d22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023d76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023dc3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023c19`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023c19`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800237ed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800237ed`

## pseudocode

```c
__int64 __fastcall MprConfigInterfaceCreateEx(char *hMprConfig, __int64 a2, char **a3)
{
  const WCHAR *v6; // r14
  _DWORD *v7; // rsi
  bool v8; // zf
  __int64 result; // rax
  unsigned int Interfaces; // ebx
  char *v11; // r12
  int v12; // eax
  char *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rax
  char *v16; // rdi
  unsigned int v17; // eax
  __int128 *v18; // rsi
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  int v21; // eax
  __int128 v22; // xmm0
  struct _GUID *v23; // rsi
  unsigned int v24; // eax
  _WORD *v25; // r13
  char *v26; // rax
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  _WORD *v30; // r10
  __int64 v31; // r8
  char *v32; // rcx
  _WORD *v33; // rax
  _WORD *v34; // rcx
  PWSTR v35; // rax
  HKEY *v36; // r13
  HKEY v37; // rcx
  HKEY *v38; // rsi
  LSTATUS i; // eax
  DWORD v40; // r9d
  char **v41; // rcx
  PWSTR v42; // rax
  __int64 v43; // rax
  int *v44; // r14
  __int64 v45; // r14
  unsigned int v46; // eax
  BYTE *v47; // r14
  DWORD cSubKeys; // [rsp+68h] [rbp-A0h] BYREF
  int v49; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-98h] BYREF
  int v51; // [rsp+74h] [rbp-94h] BYREF
  int v52; // [rsp+78h] [rbp-90h] BYREF
  DWORD v53; // [rsp+7Ch] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+80h] [rbp-88h] BYREF
  int v55; // [rsp+88h] [rbp-80h]
  BYTE *v56; // [rsp+90h] [rbp-78h] BYREF
  char **v57; // [rsp+98h] [rbp-70h]
  BYTE *lpData; // [rsp+A0h] [rbp-68h]
  BYTE *v59; // [rsp+A8h] [rbp-60h]
  __int64 v60; // [rsp+B0h] [rbp-58h]
  _OWORD v61[3]; // [rsp+B8h] [rbp-50h] BYREF
  char v62; // [rsp+F0h] [rbp-18h] BYREF
  int v63; // [rsp+2F4h] [rbp+1ECh]
  __int128 v64; // [rsp+2F8h] [rbp+1F0h]
  int v65; // [rsp+308h] [rbp+200h]
  wchar_t pszDest[12]; // [rsp+388h] [rbp+280h] BYREF

  v60 = a2;
  v57 = a3;
  memset_0(v61, 0, 0x2C8u);
  v49 = 0;
  hKey = 0;
  v56 = 0;
  v53 = 0;
  v52 = 0;
  if ( !a2 || !a3 )
    return 87;
  if ( *(_BYTE *)a2 != 1 || *(_BYTE *)(a2 + 1) != 100 )
    return 50;
  v6 = (const WCHAR *)(a2 + 8);
  v7 = (_DWORD *)(a2 + 540);
  v8 = *(_DWORD *)(a2 + 540) == 6;
  lpData = (BYTE *)(a2 + 540);
  if ( v8 )
    return 0;
  *a3 = 0;
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !(_DWORD)result )
  {
    EnterCriticalSection(&CfgLock);
    Interfaces = LoadInterfaces(0, hMprConfig);
    if ( Interfaces )
    {
LABEL_74:
      LeaveCriticalSection(&CfgLock);
      return Interfaces;
    }
    v11 = (char *)*((_QWORD *)hMprConfig + 13);
    v12 = 1;
    if ( v11 != hMprConfig + 104 )
    {
      do
      {
        v13 = v11 - 64;
        if ( !*((_DWORD *)v11 - 2) )
        {
          v12 = lstrcmpiW(*(LPCWSTR *)v13, (LPCWSTR)(a2 + 8));
          if ( v12 >= 0 )
            break;
        }
        v11 = *(char **)v11;
      }
      while ( v11 != hMprConfig + 104 );
      if ( v13 && !*((_DWORD *)v13 + 14) && !v12 )
      {
        *v57 = v13;
        Interfaces = 904;
        goto LABEL_74;
      }
    }
    ProcessHeap = GetProcessHeap();
    v15 = (char *)HeapAlloc(ProcessHeap, 0, 0x310u);
    v16 = v15;
    if ( !v15 )
    {
      Interfaces = 8;
      goto LABEL_74;
    }
    dwDisposition = 0;
    cSubKeys = 0;
    memset_0(v15, 0, 0x310u);
    *((_QWORD *)v16 + 11) = v16 + 80;
    *((_QWORD *)v16 + 10) = v16 + 80;
    *((_DWORD *)v16 + 6) = *v7;
    *((_DWORD *)v16 + 7) = *(_DWORD *)(a2 + 536);
    v17 = *v7 - 3;
    v59 = (BYTE *)(a2 + 536);
    if ( v17 <= 1 && !*(_DWORD *)(a2 + 536) )
      goto LABEL_25;
    Interfaces = CheckMultiTenancy(hMprConfig, &v49);
    if ( Interfaces )
      goto LABEL_26;
    Interfaces = CheckModernStackEnabled(hMprConfig, &v52);
    if ( Interfaces )
      goto LABEL_26;
    v18 = (__int128 *)(a2 + 572);
    if ( *(_DWORD *)(a2 + 540) == 2 )
    {
      Interfaces = ValidateQoSPolicies(a2 + 572);
      if ( Interfaces )
        goto LABEL_26;
      v19 = *v18;
      v20 = *(_OWORD *)(a2 + 584);
      v63 = *(_DWORD *)(a2 + 600);
      v21 = *(_DWORD *)(a2 + 1136);
      v61[0] = v19;
      v22 = *(_OWORD *)(a2 + 1120);
      v65 = v21;
      *(_OWORD *)((char *)v61 + 12) = v20;
      v64 = v22;
      *(_OWORD *)(v16 + 764) = v22;
      *((_DWORD *)v16 + 195) = *(_DWORD *)(a2 + 1136);
    }
    else if ( *(_DWORD *)v18 )
    {
LABEL_25:
      Interfaces = 87;
      goto LABEL_26;
    }
    if ( v49 )
    {
      v23 = (struct _GUID *)(a2 + 556);
      v24 = *(_DWORD *)(a2 + 540) - 2;
      v55 = 4;
      v51 = 0;
      if ( v24 <= 1 )
      {
        if ( *(_QWORD *)&v23->Data1 == *(_QWORD *)&GUID_NULL.Data1
          && *(_QWORD *)(a2 + 564) == _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0] )
        {
          goto LABEL_25;
        }
      }
      else if ( *(_QWORD *)&v23->Data1 != *(_QWORD *)&GUID_NULL.Data1
             || *(_QWORD *)(a2 + 564) != _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0] )
      {
        goto LABEL_25;
      }
      Interfaces = GetRoutingDomainConfiguration((struct _GUID *)(a2 + 556), (__int64)&v51);
      if ( Interfaces )
        goto LABEL_26;
      if ( *(_DWORD *)(a2 + 540) == 2 && (v51 & 0x24) == 0 )
      {
        Interfaces = 4317;
        goto LABEL_26;
      }
      v25 = (_WORD *)(a2 + 604);
      v26 = &v62;
      v27 = 2147483646;
      v28 = 257;
      *(struct _GUID *)(v16 + 200) = *v23;
      v29 = 2147483646;
      v30 = v25;
      v31 = 257;
      *(struct _GUID *)((char *)&v61[1] + 12) = *v23;
      do
      {
        if ( !v29 )
          break;
        if ( !*v30 )
          break;
        *(_WORD *)v26 = *v30++;
        v26 += 2;
        --v29;
        --v31;
      }
      while ( v31 );
      v32 = v26 - 2;
      if ( v31 )
        v32 = v26;
      v33 = v16 + 244;
      *(_WORD *)v32 = 0;
      do
      {
        if ( !v27 )
          break;
        if ( !*v25 )
          break;
        *v33++ = *v25++;
        --v27;
        --v28;
      }
      while ( v28 );
      v34 = v33 - 1;
      if ( v28 )
        v34 = v33;
      *v34 = 0;
    }
    else
    {
      v23 = (struct _GUID *)(a2 + 556);
      if ( *(_QWORD *)(a2 + 556) != *(_QWORD *)&GUID_NULL.Data1
        || *(_QWORD *)(a2 + 564) != _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0] )
      {
        goto LABEL_25;
      }
    }
    v35 = StrDupW(v6);
    *(_QWORD *)v16 = v35;
    if ( v35 )
    {
      v36 = (HKEY *)(hMprConfig + 56);
      if ( !*((_QWORD *)hMprConfig + 7) )
      {
        Interfaces = AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"Interfaces");
        if ( Interfaces )
          goto LABEL_26;
      }
      if ( v49 )
      {
        Interfaces = OpenInterfacesKey(v23, &hKey);
        if ( Interfaces )
          goto LABEL_26;
        v37 = hKey;
      }
      else
      {
        v37 = *v36;
        hKey = *v36;
      }
      Interfaces = RegQueryInfoKeyW(v37, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      if ( !Interfaces )
      {
        StringCbPrintfW(pszDest, 0x18u, L"%d", cSubKeys);
        v38 = (HKEY *)(v16 + 40);
        for ( i = RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x3001Fu, 0, (PHKEY)v16 + 5, &dwDisposition);
              ;
              i = RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x3001Fu, 0, (PHKEY)v16 + 5, &dwDisposition) )
        {
          Interfaces = i;
          if ( i )
            goto LABEL_26;
          if ( dwDisposition == 1 )
            break;
          RegCloseKey(*v38);
          v40 = cSubKeys + 1;
          *v38 = 0;
          cSubKeys = v40;
          StringCbPrintfW(pszDest, 0x18u, L"%d");
        }
        v41 = (char **)*((_QWORD *)v11 + 1);
        if ( *v41 != v11 )
          __fastfail(3u);
        *((_QWORD *)v16 + 8) = v11;
        *((_QWORD *)v16 + 9) = v41;
        *v41 = v16 + 64;
        *((_QWORD *)v11 + 1) = v16 + 64;
        UpdateTimeStamp(*v36, (PFILETIME)hMprConfig + 8);
        v42 = StrDupW(pszDest);
        *((_QWORD *)v16 + 2) = v42;
        if ( v42 )
        {
          v43 = -1;
          do
            ++v43;
          while ( v6[v43] );
          Interfaces = RegSetValueExW(*v38, L"InterfaceName", 0, 1u, (const BYTE *)v6, 2 * v43 + 2);
          if ( !Interfaces )
          {
            v44 = (int *)lpData;
            Interfaces = RegSetValueExW(*v38, L"Type", 0, 4u, lpData, 4u);
            if ( !Interfaces )
            {
              RegSetValueExW(*v38, L"Enabled", 0, 4u, v59, 4u);
              Interfaces = WriteInterfaceExtraInfo(*v38, *v44, v49, (const struct in_addr *)v61);
              if ( !Interfaces )
              {
                if ( !v52 )
                  goto LABEL_87;
                v45 = v60;
                Interfaces = RegSetValueExW(*v38, L"AutoConnectEnabled", 0, 4u, (const BYTE *)(v60 + 1276), 4u);
                if ( !Interfaces )
                {
                  v46 = ConvertPbkToRegistryEntry(v45 + 1144, &v56, &v53);
                  v47 = v56;
                  Interfaces = v46;
                  if ( !v46 )
                    Interfaces = RegSetValueExW(*v38, L"InterfaceInfoPbk", 0, 3u, v56, v53);
                  if ( v47 )
                    free(v47);
                  if ( !Interfaces )
                  {
LABEL_87:
                    GuidMapCleanup(*((LPVOID *)hMprConfig + 16));
                    Interfaces = 0;
                    *v57 = v16;
                    goto LABEL_74;
                  }
                }
              }
            }
          }
        }
        else
        {
          Interfaces = 8;
        }
        MprConfigInterfaceDelete(hMprConfig, v16);
        goto LABEL_74;
      }
      goto LABEL_26;
    }
    Interfaces = 8;
LABEL_26:
    FreeInterface(v16);
    goto LABEL_74;
  }
  return result;
}

```

## disassembly

```asm
0x1800236e0  mov     rax, rsp
0x1800236e3  mov     [rax+20h], rbx
0x1800236e7  push    rbp
0x1800236e8  push    rsi
0x1800236e9  push    rdi
0x1800236ea  push    r12
0x1800236ec  push    r13
0x1800236ee  push    r14
0x1800236f0  push    r15
0x1800236f2  lea     rbp, [rax-2E8h]
0x1800236f9  sub     rsp, 3B0h
0x180023700  movaps  xmmword ptr [rax-48h], xmm6
0x180023704  mov     rax, cs:__security_cookie
0x18002370b  xor     rax, rsp
0x18002370e  mov     [rbp+2E0h+var_48], rax
0x180023715  mov     rbx, r8
0x180023718  mov     [rbp+2E0h+var_338], rdx
0x18002371c  mov     r13, rdx
0x18002371f  mov     [rbp+2E0h+var_350], rbx
0x180023723  mov     r15, rcx
0x180023726  xor     edx, edx; Val
0x180023728  mov     r8d, 2C8h; Size
0x18002372e  lea     rcx, [rbp+2E0h+var_330]; void *
0x180023732  call    memset_0
0x180023737  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18002373e  xor     edi, edi
0x180023740  mov     [rsp+3E0h+var_37C], edi
0x180023744  mov     [rsp+3E0h+hKey], rdi
0x180023749  mov     [rbp+2E0h+var_358], rdi
0x18002374d  mov     [rsp+3E0h+var_36C], edi
0x180023751  mov     dword ptr [rsp+3E0h+var_374+4], edi
0x180023755  test    r13, r13
0x180023758  jz      loc_180023E05
0x18002375e  test    rbx, rbx
0x180023761  jz      loc_180023E05
0x180023767  cmp     byte ptr [r13+0], 1
0x18002376c  jnz     loc_180023DFE
0x180023772  cmp     byte ptr [r13+1], 64h ; 'd'
0x180023777  jnz     loc_180023DFE
0x18002377d  lea     r14, [r13+8]
0x180023781  lea     rsi, [r14+214h]
0x180023788  cmp     dword ptr [rsi], 6
0x18002378b  mov     [rbp+2E0h+lpData], rsi
0x18002378f  jnz     short loc_180023798
0x180023791  xor     eax, eax
0x180023793  jmp     loc_180023E0A
0x180023798  mov     rcx, r15
0x18002379b  mov     [rbx], rdi
0x18002379e  call    MprConfigServerValidateCb
0x1800237a3  test    eax, eax
0x1800237a5  jnz     loc_180023E0A
0x1800237ab  lea     rcx, CfgLock; lpCriticalSection
0x1800237b2  call    cs:__imp_EnterCriticalSection
0x1800237b8  mov     rdx, r15
0x1800237bb  xor     ecx, ecx
0x1800237bd  call    LoadInterfaces
0x1800237c2  mov     ebx, eax
0x1800237c4  test    eax, eax
0x1800237c6  jnz     loc_180023C81
0x1800237cc  lea     rdi, [r15+68h]
0x1800237d0  mov     r12, [rdi]
0x1800237d3  lea     eax, [rbx+1]
0x1800237d6  cmp     r12, rdi
0x1800237d9  jz      short loc_180023821
0x1800237db  xor     ecx, ecx
0x1800237dd  lea     rbx, [r12-40h]
0x1800237e2  cmp     [rbx+38h], ecx
0x1800237e5  jnz     short loc_1800237F9
0x1800237e7  mov     rcx, [rbx]; lpString1
0x1800237ea  mov     rdx, r14; lpString2
0x1800237ed  call    cs:__imp_lstrcmpiW
0x1800237f3  xor     ecx, ecx
0x1800237f5  test    eax, eax
0x1800237f7  jns     short loc_180023802
0x1800237f9  mov     r12, [r12]
0x1800237fd  cmp     r12, rdi
0x180023800  jnz     short loc_1800237DD
0x180023802  test    rbx, rbx
0x180023805  jz      short loc_180023821
0x180023807  cmp     [rbx+38h], ecx
0x18002380a  jnz     short loc_180023821
0x18002380c  test    eax, eax
0x18002380e  jnz     short loc_180023821
0x180023810  mov     rax, [rbp+2E0h+var_350]
0x180023814  mov     [rax], rbx
0x180023817  mov     ebx, 388h
0x18002381c  jmp     loc_180023C81
0x180023821  call    cs:__imp_GetProcessHeap
0x180023827  xor     edx, edx; dwFlags
0x180023829  mov     r8d, 310h; dwBytes
0x18002382f  mov     rcx, rax; hHeap
0x180023832  call    cs:__imp_HeapAlloc
0x180023838  xor     ebx, ebx
0x18002383a  mov     rdi, rax
0x18002383d  test    rax, rax
0x180023840  jnz     short loc_18002384A
0x180023842  lea     ebx, [rax+8]
0x180023845  jmp     loc_180023C81
0x18002384a  xor     edx, edx; Val
0x18002384c  mov     [rsp+3E0h+dwDisposition], ebx
0x180023850  mov     r8d, 310h; Size
0x180023856  mov     [rsp+3E0h+cSubKeys], ebx
0x18002385a  mov     rcx, rdi; void *
0x18002385d  call    memset_0
0x180023862  lea     rax, [rdi+50h]
0x180023866  mov     [rax+8], rax
0x18002386a  lea     rcx, [r14+210h]
0x180023871  mov     [rax], rax
0x180023874  mov     eax, [rsi]
0x180023876  mov     [rdi+18h], eax
0x180023879  mov     eax, [rcx]
0x18002387b  mov     [rdi+1Ch], eax
0x18002387e  mov     eax, [rsi]
0x180023880  sub     eax, 3
0x180023883  mov     [rbp+2E0h+var_340], rcx
0x180023887  cmp     eax, 1
0x18002388a  ja      short loc_180023890
0x18002388c  cmp     [rcx], ebx
0x18002388e  jz      short loc_1800238CD
0x180023890  lea     rdx, [rsp+3E0h+var_37C]
0x180023895  mov     rcx, r15
0x180023898  call    CheckMultiTenancy
0x18002389d  mov     ebx, eax
0x18002389f  test    eax, eax
0x1800238a1  jnz     short loc_1800238D2
0x1800238a3  lea     rdx, [rsp+3E0h+var_374+4]
0x1800238a8  mov     rcx, r15
0x1800238ab  call    CheckModernStackEnabled
0x1800238b0  mov     ebx, eax
0x1800238b2  test    eax, eax
0x1800238b4  jnz     short loc_1800238D2
0x1800238b6  cmp     dword ptr [r14+214h], 2
0x1800238be  lea     rsi, [r14+234h]
0x1800238c5  jz      short loc_1800238DF
0x1800238c7  xor     ebx, ebx
0x1800238c9  cmp     [rsi], ebx
0x1800238cb  jz      short loc_18002393B
0x1800238cd  mov     ebx, 57h ; 'W'
0x1800238d2  mov     rcx, rdi
0x1800238d5  call    FreeInterface
0x1800238da  jmp     loc_180023C81
0x1800238df  mov     rcx, rsi
0x1800238e2  call    ValidateQoSPolicies
0x1800238e7  mov     ebx, eax
0x1800238e9  test    eax, eax
0x1800238eb  jnz     short loc_1800238D2
0x1800238ed  movups  xmm0, xmmword ptr [rsi]
0x1800238f0  mov     eax, [r14+250h]
0x1800238f7  xor     ebx, ebx
0x1800238f9  movups  xmm1, xmmword ptr [rsi+0Ch]
0x1800238fd  mov     [rbp+2E0h+var_F4], eax
0x180023903  mov     eax, [r14+468h]
0x18002390a  movaps  xmmword ptr [rbp+2E0h+var_330], xmm0
0x18002390e  movups  xmm0, xmmword ptr [r14+458h]
0x180023916  mov     [rbp+2E0h+var_E0], eax
0x18002391c  movups  xmmword ptr [rbp+2E0h+var_330+0Ch], xmm1
0x180023920  movaps  [rbp+2E0h+var_F0], xmm0
0x180023927  movups  xmmword ptr [rdi+2FCh], xmm0
0x18002392e  mov     eax, [r14+468h]
0x180023935  mov     [rdi+30Ch], eax
0x18002393b  cmp     [rsp+3E0h+var_37C], ebx
0x18002393f  jz      loc_180023A88
0x180023945  mov     eax, [r14+214h]
0x18002394c  lea     rsi, [r14+224h]
0x180023953  sub     eax, 2
0x180023956  mov     [rbp+2E0h+var_360], 4
0x18002395d  cmp     eax, 1
0x180023960  mov     dword ptr [rsp+3E0h+var_374], ebx
0x180023964  movq    rax, xmm6
0x180023969  jbe     short loc_180023989
0x18002396b  cmp     [rsi], rax
0x18002396e  jnz     loc_1800238CD
0x180023974  psrldq  xmm6, 8
0x180023979  movq    rax, xmm6
0x18002397e  cmp     [rsi+8], rax
0x180023982  jz      short loc_1800239A2
0x180023984  jmp     loc_1800238CD
0x180023989  cmp     [rsi], rax
0x18002398c  jnz     short loc_1800239A2
0x18002398e  psrldq  xmm6, 8
0x180023993  movq    rax, xmm6
0x180023998  cmp     [rsi+8], rax
0x18002399c  jz      loc_1800238CD
0x1800239a2  lea     rax, [rsp+3E0h+var_374]
0x1800239a7  mov     edx, 8000h
0x1800239ac  lea     r9, [rbp+2E0h+var_360]
0x1800239b0  mov     [rsp+3E0h+lpcSubKeys], rax; __int64
0x1800239b5  mov     r8d, 1
0x1800239bb  mov     rcx, rsi; struct _GUID *
0x1800239be  call    GetRoutingDomainConfiguration
0x1800239c3  mov     ebx, eax
0x1800239c5  test    eax, eax
0x1800239c7  jnz     loc_1800238D2
0x1800239cd  cmp     dword ptr [r14+214h], 2
0x1800239d5  jnz     short loc_1800239E8
0x1800239d7  test    byte ptr [rsp+3E0h+var_374], 24h
0x1800239dc  jnz     short loc_1800239E8
0x1800239de  mov     ebx, 10DDh
0x1800239e3  jmp     loc_1800238D2
0x1800239e8  movups  xmm0, xmmword ptr [rsi]
0x1800239eb  add     r13, 25Ch
0x1800239f2  lea     rax, [rbp+2E0h+var_2F8]
0x1800239f6  mov     r9d, 7FFFFFFEh
0x1800239fc  mov     edx, 101h
0x180023a01  movdqu  xmmword ptr [rdi+0C8h], xmm0
0x180023a09  mov     ecx, r9d
0x180023a0c  mov     r10, r13
0x180023a0f  movups  xmm1, xmmword ptr [rsi]
0x180023a12  mov     r8d, edx
0x180023a15  xor     ebx, ebx
0x180023a17  movdqu  [rbp+2E0h+var_314], xmm1
0x180023a1c  test    rcx, rcx
0x180023a1f  jz      short loc_180023A40
0x180023a21  movzx   r11d, word ptr [r10]
0x180023a25  test    r11w, r11w
0x180023a29  jz      short loc_180023A40
0x180023a2b  mov     [rax], r11w
0x180023a2f  add     r10, 2
0x180023a33  add     rax, 2
0x180023a37  dec     rcx
0x180023a3a  sub     r8, 1
0x180023a3e  jnz     short loc_180023A1C
0x180023a40  lea     rcx, [rax-2]
0x180023a44  test    r8, r8
0x180023a47  cmovnz  rcx, rax
0x180023a4b  lea     rax, [rdi+0F4h]
0x180023a52  mov     [rcx], bx
0x180023a55  test    r9, r9
0x180023a58  jz      short loc_180023A78
0x180023a5a  movzx   ecx, word ptr [r13+0]
0x180023a5f  test    cx, cx
0x180023a62  jz      short loc_180023A78
0x180023a64  mov     [rax], cx
0x180023a67  add     r13, 2
0x180023a6b  add     rax, 2
0x180023a6f  dec     r9
0x180023a72  sub     rdx, 1
0x180023a76  jnz     short loc_180023A55
0x180023a78  test    rdx, rdx
0x180023a7b  lea     rcx, [rax-2]
0x180023a7f  cmovnz  rcx, rax
0x180023a83  mov     [rcx], bx
0x180023a86  jmp     short loc_180023AB1
0x180023a88  lea     rsi, [r13+22Ch]
0x180023a8f  movq    rax, xmm6
0x180023a94  cmp     [rsi], rax
0x180023a97  jnz     loc_1800238CD
0x180023a9d  psrldq  xmm6, 8
0x180023aa2  movq    rax, xmm6
0x180023aa7  cmp     [rsi+8], rax
0x180023aab  jnz     loc_1800238CD
0x180023ab1  mov     rcx, r14; pszSrch
0x180023ab4  call    StrDupW
0x180023ab9  mov     [rdi], rax
0x180023abc  test    rax, rax
0x180023abf  jnz     short loc_180023AC9
0x180023ac1  lea     ebx, [rax+8]
0x180023ac4  jmp     loc_1800238D2
0x180023ac9  lea     r13, [r15+38h]
0x180023acd  cmp     [r13+0], rbx
0x180023ad1  jnz     short loc_180023AF8
0x180023ad3  mov     rcx, [r15+10h]; hKey
0x180023ad7  lea     rdx, c_szInterfaces; "Interfaces"
0x180023ade  mov     r9, r13
0x180023ae1  mov     r8d, 1
0x180023ae7  call    AccessRouterSubkey
0x180023aec  mov     ebx, eax
0x180023aee  test    eax, eax
0x180023af0  jnz     loc_1800238D2
0x180023af6  xor     ebx, ebx
0x180023af8  cmp     [rsp+3E0h+var_37C], ebx
0x180023afc  jz      short loc_180023B1E
0x180023afe  lea     rdx, [rsp+3E0h+hKey]; HKEY *
0x180023b03  mov     rcx, rsi; struct _GUID *
0x180023b06  call    OpenInterfacesKey
0x180023b0b  mov     ebx, eax
0x180023b0d  test    eax, eax
0x180023b0f  jnz     loc_1800238D2
0x180023b15  mov     rcx, [rsp+3E0h+hKey]
0x180023b1a  xor     ebx, ebx
0x180023b1c  jmp     short loc_180023B27
0x180023b1e  mov     rcx, [r13+0]; hKey
0x180023b22  mov     [rsp+3E0h+hKey], rcx
0x180023b27  mov     [rsp+3E0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180023b2c  lea     rax, [rsp+3E0h+cSubKeys]
0x180023b31  mov     [rsp+3E0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x180023b36  xor     r9d, r9d; lpReserved
0x180023b39  mov     [rsp+3E0h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180023b3e  xor     r8d, r8d; lpcchClass
0x180023b41  mov     [rsp+3E0h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x180023b46  xor     edx, edx; lpClass
0x180023b48  mov     [rsp+3E0h+lpcValues], rbx; lpcValues
0x180023b4d  mov     [rsp+3E0h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180023b52  mov     [rsp+3E0h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x180023b57  mov     [rsp+3E0h+lpcSubKeys], rax; lpcSubKeys
0x180023b5c  call    cs:__imp_RegQueryInfoKeyW
0x180023b62  mov     ebx, eax
0x180023b64  test    eax, eax
0x180023b66  jnz     loc_1800238D2
0x180023b6c  mov     r9d, [rsp+3E0h+cSubKeys]
  ... truncated ...
```
