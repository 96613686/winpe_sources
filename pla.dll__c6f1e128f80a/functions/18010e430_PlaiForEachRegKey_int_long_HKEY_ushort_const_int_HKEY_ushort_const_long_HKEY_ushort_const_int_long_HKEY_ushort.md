# PlaiForEachRegKey<int,long (*)(HKEY__ *,ushort const *,int)>(HKEY__ *,ushort const *,long (*)(HKEY__ *,ushort const *,int),long (*)(HKEY__ *,ushort const *,int),int)

- ea: `0x18010e430`
- end: `0x18010ea28`
- name: `??$PlaiForEachRegKey@HP6AJPEAUHKEY__@@PEBGH@Z@@YAJPEAUHKEY__@@PEBGP6AJ01H@Z2H@Z`
- size: `1528`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800de848`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x1800c2328`
- `0x18010e430`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010e708`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010e708`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e491`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e9fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e9fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010e566`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010e566`

## pseudocode

```c
__int64 __fastcall PlaiForEachRegKey<int,long (*)(HKEY__ *,unsigned short const *,int)>(HKEY a1)
{
  LSTATUS v1; // eax
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  int *v5; // r9
  int *v6; // rcx
  LSTATUS v7; // eax
  int v8; // eax
  __int64 v9; // rax
  DWORD v10; // eax
  unsigned __int64 v11; // rax
  unsigned int v12; // r12d
  WCHAR *v13; // r14
  __int64 v14; // rax
  DWORD v15; // esi
  LSTATUS v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cSubKeys; // [rsp+8Ch] [rbp-74h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  DWORD cValues; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v33[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v34[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v35[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v36[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v37[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v38[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v39[64]; // [rsp+3A0h] [rbp+2A0h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchName = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(a1, L"Log Queries", 0, 0x20019u, &hKey);
  v2 = PlaiHResultFromWin32(v1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    v8 = PlaiHResultFromWin32(v7);
    v3 = v8;
    if ( v8 >= 0 )
    {
      v10 = cbMaxValueNameLen;
      if ( cbMaxSubKeyLen > cbMaxValueNameLen )
        v10 = cbMaxSubKeyLen;
      if ( v10 + 1 < v10 )
      {
        v3 = -2147024362;
        cchName = -1;
        v25 = -2147024362;
        v26 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v39, 0x4000000000000800uLL);
          v22 = -1;
          do
            ++v22;
          while ( v39[v22] );
          v5 = &v25;
          v6 = &v26;
          goto LABEL_57;
        }
        goto LABEL_58;
      }
      cchName = v10 + 1;
      v11 = 2LL * (v10 + 1);
      if ( v11 > 0xFFFFFFFF )
      {
        v3 = -2147024362;
        v25 = -2147024362;
        v26 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_58;
        }
        PlaiWhoAmI(v38, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v38[v21] );
      }
      else
      {
        v12 = v11;
        v13 = (WCHAR *)PlaiAlloc((unsigned int)v11, 1, 0, qword_180147320, phkResult);
        if ( v13 )
        {
          v15 = 0;
          v3 = 0;
          while ( 1 )
          {
            if ( v15 >= cSubKeys )
              goto LABEL_44;
            cchName = v12 >> 1;
            v16 = RegEnumKeyExW(hKey, v15, v13, &cchName, 0, 0, 0, 0);
            v17 = PlaiHResultFromWin32(v16);
            v3 = v17;
            if ( v17 < 0 )
              break;
            v18 = PlaiSetLegacyState(hKey, v13, 0);
            v3 = v18;
            if ( v18 < 0 )
            {
              v26 = 0;
              v25 = v18;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v36, 0x4000000000000800uLL);
                v19 = -1;
                do
                  ++v19;
                while ( v36[v19] );
LABEL_43:
                EventingWriteEvent(
                  &g_Eventing,
                  PLA_EVENT_ERROR,
                  5,
                  &v25,
                  4,
                  qword_180147320,
                  1,
                  &v26,
                  4,
                  "PlaiForEachRegKey",
                  18);
                goto LABEL_44;
              }
              goto LABEL_44;
            }
            if ( v18 == 1 )
              goto LABEL_44;
            ++v15;
          }
          v26 = 0;
          v25 = v17;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v37, 0x4000000000000800uLL);
            v20 = -1;
            do
              ++v20;
            while ( v37[v20] );
            goto LABEL_43;
          }
LABEL_44:
          PlaiFree(v13, 1);
          goto LABEL_58;
        }
        v3 = -2147024882;
        v25 = -2147024882;
        v26 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_58;
        }
        PlaiWhoAmI(v35, 0x4000000000000800uLL);
        v14 = -1;
        do
          ++v14;
        while ( v35[v14] );
      }
    }
    else
    {
      v26 = 0;
      v25 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_58;
      }
      PlaiWhoAmI(v34, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v34[v9] );
    }
    v5 = &v25;
    v6 = &v26;
LABEL_57:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v5, 4, qword_180147320, 1, v6, 4, "PlaiForEachRegKey", 18);
    goto LABEL_58;
  }
  v25 = 0;
  v26 = v2;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v33, 0x4000000000000800uLL);
    v4 = -1;
    do
      ++v4;
    while ( v33[v4] );
    v5 = &v26;
    v6 = &v25;
    goto LABEL_57;
  }
LABEL_58:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18010e430  push    rbp
0x18010e432  push    rbx
0x18010e433  push    rsi
0x18010e434  push    rdi
0x18010e435  push    r12
0x18010e437  push    r13
0x18010e439  push    r14
0x18010e43b  push    r15
0x18010e43d  lea     rbp, [rsp-338h]
0x18010e445  sub     rsp, 438h
0x18010e44c  mov     rax, cs:__security_cookie
0x18010e453  xor     rax, rsp
0x18010e456  mov     [rbp+370h+var_50], rax
0x18010e45d  xor     r13d, r13d
0x18010e460  lea     rax, [rbp+370h+hKey]
0x18010e464  mov     r9d, 20019h; samDesired
0x18010e46a  mov     [rbp+370h+cSubKeys], r13d
0x18010e46e  xor     r8d, r8d; ulOptions
0x18010e471  mov     [rbp+370h+cbMaxSubKeyLen], r13d
0x18010e475  lea     rdx, aLogQueries; "Log Queries"
0x18010e47c  mov     [rbp+370h+cValues], r13d
0x18010e480  mov     [rbp+370h+cbMaxValueNameLen], r13d
0x18010e484  mov     [rbp+370h+cchName], r13d
0x18010e488  mov     [rbp+370h+hKey], r13
0x18010e48c  mov     [rsp+470h+phkResult], rax; phkResult
0x18010e491  call    cs:__imp_RegOpenKeyExW
0x18010e497  mov     ecx, eax; unsigned int
0x18010e499  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18010e49e  mov     ebx, eax
0x18010e4a0  test    eax, eax
0x18010e4a2  jns     short loc_18010E522
0x18010e4a4  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e4ab  mov     [rsp+470h+var_400], r13d
0x18010e4b0  mov     [rsp+470h+var_3F8], eax
0x18010e4b4  jz      loc_18010E9F4
0x18010e4ba  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e4c4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e4cb  jz      loc_18010E9F4
0x18010e4d1  mov     rax, cs:qword_180169748
0x18010e4d8  and     rax, rdx
0x18010e4db  cmp     cs:qword_180169748, rax
0x18010e4e2  jnz     loc_18010E9F4
0x18010e4e8  lea     rcx, [rbp+370h+var_3D0]; unsigned __int16 *
0x18010e4ec  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e4f1  lea     rcx, [rbp+370h+var_3D0]
0x18010e4f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e4f9  inc     rax
0x18010e4fc  cmp     [rcx+rax*2], r13w
0x18010e501  jnz     short loc_18010E4F9
0x18010e503  lea     ecx, [rax+rax]
0x18010e506  add     rcx, 2
0x18010e50a  lea     rax, [rbp+370h+var_3D0]
0x18010e50e  mov     [rsp+470h+var_410], rcx
0x18010e513  lea     r9, [rsp+470h+var_3F8]
0x18010e518  lea     rcx, [rsp+470h+var_400]
0x18010e51d  jmp     loc_18010E999
0x18010e522  mov     rcx, [rbp+370h+hKey]; hKey
0x18010e526  lea     rax, [rbp+370h+cbMaxValueNameLen]
0x18010e52a  mov     [rsp+470h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18010e52f  xor     r9d, r9d; lpReserved
0x18010e532  mov     [rsp+470h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18010e537  xor     r8d, r8d; lpcchClass
0x18010e53a  mov     [rsp+470h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18010e53f  xor     edx, edx; lpClass
0x18010e541  mov     [rsp+470h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18010e546  lea     rax, [rbp+370h+cValues]
0x18010e54a  mov     [rsp+470h+lpcValues], rax; lpcValues
0x18010e54f  lea     rax, [rbp+370h+cbMaxSubKeyLen]
0x18010e553  mov     [rsp+470h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18010e558  mov     [rsp+470h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18010e55d  lea     rax, [rbp+370h+cSubKeys]
0x18010e561  mov     [rsp+470h+phkResult], rax; int
0x18010e566  call    cs:__imp_RegQueryInfoKeyW
0x18010e56c  mov     ecx, eax; unsigned int
0x18010e56e  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18010e573  mov     ebx, eax
0x18010e575  test    eax, eax
0x18010e577  jns     loc_18010E607
0x18010e57d  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e584  mov     [rsp+470h+var_3F8], r13d
0x18010e589  mov     [rsp+470h+var_400], eax
0x18010e58d  jz      loc_18010E9F4
0x18010e593  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e59d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e5a4  jz      loc_18010E9F4
0x18010e5aa  mov     rax, cs:qword_180169748
0x18010e5b1  and     rax, rdx
0x18010e5b4  cmp     cs:qword_180169748, rax
0x18010e5bb  jnz     loc_18010E9F4
0x18010e5c1  lea     rcx, [rbp+370h+var_350]; unsigned __int16 *
0x18010e5c5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e5ca  lea     rcx, [rbp+370h+var_350]
0x18010e5ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e5d2  inc     rax
0x18010e5d5  cmp     [rcx+rax*2], r13w
0x18010e5da  jnz     short loc_18010E5D2
0x18010e5dc  lea     ecx, [rax+rax]
0x18010e5df  lea     rax, [rbp+370h+var_350]
0x18010e5e3  mov     edi, 1
0x18010e5e8  lea     r15, qword_180147320
0x18010e5ef  add     rcx, 2
0x18010e5f3  lea     r9, [rsp+470h+var_400]
0x18010e5f8  mov     [rsp+470h+var_410], rcx
0x18010e5fd  lea     rcx, [rsp+470h+var_3F8]
0x18010e602  jmp     loc_18010E9A5
0x18010e607  mov     eax, [rbp+370h+cbMaxValueNameLen]
0x18010e60a  cmp     [rbp+370h+cbMaxSubKeyLen], eax
0x18010e60d  cmova   eax, [rbp+370h+cbMaxSubKeyLen]
0x18010e611  lea     ecx, [rax+1]
0x18010e614  cmp     ecx, eax
0x18010e616  jb      loc_18010E90A
0x18010e61c  mov     eax, ecx
0x18010e61e  mov     [rbp+370h+cchName], ecx
0x18010e621  add     rax, rax
0x18010e624  mov     ecx, 0FFFFFFFFh
0x18010e629  cmp     rax, rcx
0x18010e62c  ja      loc_18010E891
0x18010e632  xor     r8d, r8d; int
0x18010e635  mov     ecx, eax; dwBytes
0x18010e637  lea     r15, qword_180147320
0x18010e63e  mov     r12d, eax
0x18010e641  mov     r9, r15; char *
0x18010e644  lea     edi, [r8+1]
0x18010e648  mov     edx, edi; int
0x18010e64a  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18010e64f  mov     r14, rax
0x18010e652  test    rax, rax
0x18010e655  jnz     short loc_18010E6D0
0x18010e657  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e65e  mov     ebx, 8007000Eh
0x18010e663  mov     [rsp+470h+var_400], ebx
0x18010e667  mov     [rsp+470h+var_3F8], r13d
0x18010e66c  jz      loc_18010E9F4
0x18010e672  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e67c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e683  jz      loc_18010E9F4
0x18010e689  mov     rax, cs:qword_180169748
0x18010e690  and     rax, rdx
0x18010e693  cmp     cs:qword_180169748, rax
0x18010e69a  jnz     loc_18010E9F4
0x18010e6a0  lea     rcx, [rbp+370h+var_2D0]; unsigned __int16 *
0x18010e6a7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e6ac  lea     rcx, [rbp+370h+var_2D0]
0x18010e6b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e6b7  inc     rax
0x18010e6ba  cmp     [rcx+rax*2], r13w
0x18010e6bf  jnz     short loc_18010E6B7
0x18010e6c1  lea     ecx, [rax+rax]
0x18010e6c4  lea     rax, [rbp+370h+var_2D0]
0x18010e6cb  jmp     loc_18010E5EF
0x18010e6d0  mov     esi, r13d
0x18010e6d3  mov     ebx, r13d
0x18010e6d6  cmp     esi, [rbp+370h+cSubKeys]
0x18010e6d9  jnb     loc_18010E882
0x18010e6df  mov     rcx, [rbp+370h+hKey]; hKey
0x18010e6e3  lea     r9, [rbp+370h+cchName]; lpcchName
0x18010e6e7  mov     [rsp+470h+lpcValues], r13; lpftLastWriteTime
0x18010e6ec  mov     eax, r12d
0x18010e6ef  shr     eax, 1
0x18010e6f1  mov     r8, r14; lpName
0x18010e6f4  mov     [rsp+470h+lpcbMaxClassLen], r13; lpcchClass
0x18010e6f9  mov     edx, esi; dwIndex
0x18010e6fb  mov     [rsp+470h+lpcbMaxSubKeyLen], r13; lpClass
0x18010e700  mov     [rbp+370h+cchName], eax
0x18010e703  mov     [rsp+470h+phkResult], r13; lpReserved
0x18010e708  call    cs:__imp_RegEnumKeyExW
0x18010e70e  mov     ecx, eax; unsigned int
0x18010e710  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18010e715  mov     ebx, eax
0x18010e717  test    eax, eax
0x18010e719  js      loc_18010E7B1
0x18010e71f  mov     rcx, [rbp+370h+hKey]; HKEY
0x18010e723  xor     r8d, r8d; int
0x18010e726  mov     rdx, r14; unsigned __int16 *
0x18010e729  call    ?PlaiSetLegacyState@@YAJPEAUHKEY__@@PEBGH@Z; PlaiSetLegacyState(HKEY__ *,ushort const *,int)
0x18010e72e  mov     ebx, eax
0x18010e730  test    eax, eax
0x18010e732  js      short loc_18010E740
0x18010e734  cmp     eax, edi
0x18010e736  jz      loc_18010E882
0x18010e73c  add     esi, edi
0x18010e73e  jmp     short loc_18010E6D6
0x18010e740  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e747  mov     [rsp+470h+var_3F8], r13d
0x18010e74c  mov     [rsp+470h+var_400], eax
0x18010e750  jz      loc_18010E882
0x18010e756  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e760  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e767  jz      loc_18010E882
0x18010e76d  mov     rax, cs:qword_180169748
0x18010e774  and     rax, rdx
0x18010e777  cmp     cs:qword_180169748, rax
0x18010e77e  jnz     loc_18010E882
0x18010e784  lea     rcx, [rbp+370h+var_250]; unsigned __int16 *
0x18010e78b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e790  lea     rcx, [rbp+370h+var_250]
0x18010e797  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e79b  inc     rax
0x18010e79e  cmp     [rcx+rax*2], r13w
0x18010e7a3  jnz     short loc_18010E79B
0x18010e7a5  lea     ecx, [rax+rax]
0x18010e7a8  lea     rax, [rbp+370h+var_250]
0x18010e7af  jmp     short loc_18010E820
0x18010e7b1  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e7b8  mov     [rsp+470h+var_3F8], r13d
0x18010e7bd  mov     [rsp+470h+var_400], eax
0x18010e7c1  jz      loc_18010E882
0x18010e7c7  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e7d1  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e7d8  jz      loc_18010E882
0x18010e7de  mov     rax, cs:qword_180169748
0x18010e7e5  and     rax, rdx
0x18010e7e8  cmp     cs:qword_180169748, rax
0x18010e7ef  jnz     loc_18010E882
0x18010e7f5  lea     rcx, [rbp+370h+var_1D0]; unsigned __int16 *
0x18010e7fc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e801  lea     rcx, [rbp+370h+var_1D0]
0x18010e808  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e80c  inc     rax
0x18010e80f  cmp     [rcx+rax*2], r13w
0x18010e814  jnz     short loc_18010E80C
0x18010e816  lea     ecx, [rax+rax]
0x18010e819  lea     rax, [rbp+370h+var_1D0]
0x18010e820  add     rcx, 2
0x18010e824  lea     r9, [rsp+470h+var_400]
0x18010e829  mov     [rsp+470h+var_410], rcx
0x18010e82e  lea     rdx, PLA_EVENT_ERROR
0x18010e835  mov     [rsp+470h+lpftLastWriteTime], rax
0x18010e83a  lea     rcx, [rsp+470h+var_3F8]
0x18010e83f  mov     [rsp+470h+lpcbSecurityDescriptor], 12h
0x18010e848  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18010e84f  mov     [rsp+470h+lpcbMaxValueLen], rax
0x18010e854  mov     eax, 4
0x18010e859  mov     [rsp+470h+lpcbMaxValueNameLen], rax
0x18010e85e  mov     [rsp+470h+lpcValues], rcx
0x18010e863  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18010e86a  mov     [rsp+470h+lpcbMaxClassLen], rdi
0x18010e86f  mov     [rsp+470h+lpcbMaxSubKeyLen], r15
0x18010e874  lea     r8d, [rax+1]
0x18010e878  mov     [rsp+470h+phkResult], rax
0x18010e87d  call    EventingWriteEvent
0x18010e882  mov     edx, edi; int
0x18010e884  mov     rcx, r14; lpMem
0x18010e887  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18010e88c  jmp     loc_18010E9F4
0x18010e891  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e898  mov     ebx, 80070216h
0x18010e89d  mov     [rsp+470h+var_400], ebx
0x18010e8a1  mov     [rsp+470h+var_3F8], r13d
0x18010e8a6  jz      loc_18010E9F4
0x18010e8ac  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e8b6  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e8bd  jz      loc_18010E9F4
0x18010e8c3  mov     rax, cs:qword_180169748
0x18010e8ca  and     rax, rdx
0x18010e8cd  cmp     cs:qword_180169748, rax
0x18010e8d4  jnz     loc_18010E9F4
0x18010e8da  lea     rcx, [rbp+370h+var_150]; unsigned __int16 *
0x18010e8e1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e8e6  lea     rcx, [rbp+370h+var_150]
0x18010e8ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e8f1  inc     rax
0x18010e8f4  cmp     [rcx+rax*2], r13w
0x18010e8f9  jnz     short loc_18010E8F1
0x18010e8fb  lea     ecx, [rax+rax]
0x18010e8fe  lea     rax, [rbp+370h+var_150]
0x18010e905  jmp     loc_18010E5E3
0x18010e90a  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e911  mov     ecx, 0FFFFFFFFh
0x18010e916  mov     ebx, 80070216h
0x18010e91b  mov     [rbp+370h+cchName], ecx
0x18010e91e  mov     [rsp+470h+var_400], ebx
0x18010e922  mov     [rsp+470h+var_3F8], r13d
0x18010e927  jz      loc_18010E9F4
0x18010e92d  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e937  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e93e  jz      loc_18010E9F4
0x18010e944  mov     rax, cs:qword_180169748
0x18010e94b  and     rax, rdx
0x18010e94e  cmp     cs:qword_180169748, rax
0x18010e955  jnz     loc_18010E9F4
0x18010e95b  lea     rcx, [rbp+370h+var_D0]; unsigned __int16 *
0x18010e962  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e967  lea     rcx, [rbp+370h+var_D0]
0x18010e96e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010e972  inc     rax
0x18010e975  cmp     [rcx+rax*2], r13w
0x18010e97a  jnz     short loc_18010E972
0x18010e97c  lea     ecx, [rax+rax]
0x18010e97f  add     rcx, 2
0x18010e983  lea     rax, [rbp+370h+var_D0]
0x18010e98a  mov     [rsp+470h+var_410], rcx
0x18010e98f  lea     r9, [rsp+470h+var_400]
0x18010e994  lea     rcx, [rsp+470h+var_3F8]
0x18010e999  mov     edi, 1
0x18010e99e  lea     r15, qword_180147320
0x18010e9a5  mov     [rsp+470h+lpftLastWriteTime], rax
0x18010e9aa  lea     rdx, PLA_EVENT_ERROR
0x18010e9b1  mov     [rsp+470h+lpcbSecurityDescriptor], 12h
0x18010e9ba  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
  ... truncated ...
```
