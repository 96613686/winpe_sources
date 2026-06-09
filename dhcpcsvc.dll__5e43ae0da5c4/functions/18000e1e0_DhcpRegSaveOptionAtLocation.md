# DhcpRegSaveOptionAtLocation

- ea: `0x18000e1e0`
- end: `0x18000e5ef`
- name: `DhcpRegSaveOptionAtLocation`
- size: `1039`
- prototype: `LSTATUS __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e5f8`

## callees

- `0x180001f90`
- `0x180002160`
- `0x1800048c0`
- `0x180005162`
- `0x18000df6c`
- `0x18000e1e0`
- `0x18000e784`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e251`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000e251`
- `ntdll!RtlxOemStringToUnicodeSize` at `0x18000e3d1`
- `ntdll!RtlxOemStringToUnicodeSize` at `0x18000e3d1`
- `ntdll!RtlInitString` at `0x18000e3c6`
- `ntdll!RtlInitString` at `0x18000e3c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e28e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e28e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e2d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e2d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e374`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e556`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e592`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e374`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e556`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e592`
- `WS2_32!__imp_inet_ntoa` at `0x18000e3ad`
- `WS2_32!__imp_inet_ntoa` at `0x18000e3ad`

## pseudocode

```c
LSTATUS __fastcall DhcpRegSaveOptionAtLocation(__int64 a1, const wchar_t *a2)
{
  int v4; // edi
  wchar_t *v5; // rax
  const WCHAR *v6; // r14
  LSTATUS result; // eax
  __int64 v8; // rdx
  LSTATUS v9; // ebx
  int v10; // ecx
  __int64 v11; // r13
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  unsigned int *v16; // rdi
  int v17; // ebx
  int v18; // ecx
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int *v21; // r12
  unsigned int v22; // r13d
  char *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned int v28; // edx
  unsigned int *v29; // rcx
  __int64 v30; // rax
  _WORD *v31; // rax
  int i; // eax
  int v33; // ecx
  LSTATUS v34; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v39; // [rsp+50h] [rbp-B0h]
  struct _STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[512]; // [rsp+70h] [rbp-90h] BYREF
  char v42; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v43[1008]; // [rsp+660h] [rbp+560h] BYREF

  hKey = 0;
  memset_0(v43, 0, 0x3EAu);
  memset_0(v41, 0, 0x1F4u);
  v4 = *(_DWORD *)(a1 + 20);
  v5 = wcsrchr(a2, 0x5Cu);
  v39 = v5;
  v6 = v5;
  if ( v5 )
  {
    v6 = v5 + 1;
    *v5 = 0;
    v39 = v5 + 1;
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xFu, &hKey);
  if ( !result )
  {
    v8 = *(unsigned int *)(a1 + 56);
    if ( !(_DWORD)v8 )
    {
      if ( g_fVelocityDhcpv4InformNegativeCacheFix )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
          WPP_SF_d(1028, 11, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, *(unsigned int *)(a1 + 16));
      }
      v9 = RegDeleteValueW(hKey, v6);
      goto LABEL_23;
    }
    if ( !v4 )
    {
      v10 = *(_DWORD *)(a1 + 16);
      v36 = 0;
      v11 = 0;
      v38 = 0;
      v12 = v10 - 1;
      if ( v12 && (v13 = v12 - 2) != 0 && (v14 = v13 - 3) != 0 && (v15 = v14 - 38) != 0 )
      {
        if ( v15 == 2 )
        {
          if ( (_DWORD)v8 == 1 )
            v18 = **(unsigned __int8 **)(a1 + 48);
          else
            v18 = 1;
          v36 = v18;
          v16 = &v36;
          v17 = 4;
        }
        else
        {
          v16 = 0;
          v17 = 0;
        }
      }
      else
      {
        v19 = (unsigned __int64)(34 * v8) >> 2;
        if ( (unsigned int)v19 <= 0x3E8 )
        {
          v16 = (unsigned int *)&v42;
        }
        else
        {
          v20 = DhcpAlloc((unsigned int)v19, v8, 32);
          v38 = v20;
          v11 = v20;
          if ( !v20 )
          {
            v9 = 8;
LABEL_23:
            RegCloseKey(hKey);
            return v9;
          }
          v16 = (unsigned int *)v20;
        }
        v21 = v16;
        if ( (*(_DWORD *)(a1 + 56) & 0xFFFFFFFC) != 0 )
        {
          v22 = 0;
          do
          {
            v23 = inet_ntoa(*(struct in_addr *)(*(_QWORD *)(a1 + 48) + 4LL * v22));
            DestinationString = 0;
            RtlInitString(&DestinationString, v23);
            RtlxOemStringToUnicodeSize(&DestinationString);
            v24 = DhcpOemToUnicodeN(v23);
            v25 = v24;
            if ( (BYTE1(xmmword_18001E1E0) & 0x20) != 0 )
              WPP_SF_S(1037, 12, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, v24);
            if ( !v25 )
              break;
            v26 = -1;
            do
              ++v26;
            while ( *(_WORD *)(v25 + 2 * v26) );
            ++v22;
            v21 = (unsigned int *)(v25 + 2 + 2 * v26);
          }
          while ( v22 < *(_DWORD *)(a1 + 56) >> 2 );
          v6 = v39;
          v11 = v38;
        }
        *(_WORD *)v21 = 0;
        v27 = -1;
        do
          ++v27;
        while ( *((_WORD *)v21 + v27) );
        v17 = 2 * (((__int64)v21 + 2 * v27 - (__int64)v16) >> 1) + 2;
      }
      if ( *(_DWORD *)(a1 + 16) == 44 )
      {
        if ( !v17 )
        {
          v16 = (unsigned int *)byte_180018278;
          v17 = 2;
        }
      }
      else if ( *(_DWORD *)(a1 + 16) == 6 )
      {
        v28 = 1;
        v17 -= 2;
        v36 = *(_DWORD *)(a1 + 56) >> 2;
        v29 = v16;
        if ( v36 > 1 )
        {
          do
          {
            v30 = -1;
            do
              ++v30;
            while ( *((_WORD *)v29 + v30) );
            v31 = (_WORD *)v29 + v30;
            ++v28;
            *v31 = 32;
            v29 = (unsigned int *)(v31 + 1);
          }
          while ( v28 < v36 );
        }
        if ( (BYTE1(xmmword_18001E1E0) & 0x20) != 0 )
          WPP_SF_S(1037, 13, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, v16);
      }
      for ( i = 0; ; ++i )
      {
        v33 = qword_18001E080[i];
        if ( !v33 )
          break;
        if ( *(_DWORD *)(a1 + 16) == v33 )
        {
          LODWORD(phkResult) = v17;
          v34 = DhcpRegSetOptionRegVal(hKey, v6, HIDWORD(qword_18001E080[i]), v16, (size_t)phkResult);
          v9 = v34;
          if ( v34 && (xmmword_18001E1E0 & 2) != 0 )
            WPP_SF_SD(1025, 14, (unsigned int)WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, (_DWORD)v6, v34);
          RegCloseKey(hKey);
          if ( v11 )
            DhcpFree(&v38);
          return v9;
        }
      }
    }
    LODWORD(phkResult) = *(_DWORD *)(a1 + 56);
    v9 = DhcpRegSetOptionRegVal(hKey, v6, 3u, *(void **)(a1 + 48), (size_t)phkResult);
    RegCloseKey(hKey);
    if ( v9 && (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_SD(1025, 18, (unsigned int)WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, (_DWORD)v6, v9);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18000e1e0  mov     [rsp-8+arg_10], rbx
0x18000e1e5  mov     [rsp-8+arg_18], rsi
0x18000e1ea  push    rbp
0x18000e1eb  push    rdi
0x18000e1ec  push    r12
0x18000e1ee  push    r13
0x18000e1f0  push    r14
0x18000e1f2  lea     rbp, [rsp-960h]
0x18000e1fa  sub     rsp, 0A60h
0x18000e201  mov     rax, cs:__security_cookie
0x18000e208  xor     rax, rsp
0x18000e20b  mov     [rbp+980h+var_30], rax
0x18000e212  mov     rbx, rdx
0x18000e215  mov     rsi, rcx
0x18000e218  xor     r12d, r12d
0x18000e21b  lea     rcx, [rbp+980h+var_420]; void *
0x18000e222  xor     edx, edx; Val
0x18000e224  mov     [rsp+0A80h+hKey], r12
0x18000e229  mov     r8d, 3EAh; Size
0x18000e22f  call    memset_0
0x18000e234  xor     edx, edx; Val
0x18000e236  lea     rcx, [rsp+0A80h+var_A10]; void *
0x18000e23b  mov     r8d, 1F4h; Size
0x18000e241  call    memset_0
0x18000e246  mov     edi, [rsi+14h]
0x18000e249  lea     edx, [r12+5Ch]; Ch
0x18000e24e  mov     rcx, rbx; Str
0x18000e251  call    cs:__imp_wcsrchr
0x18000e257  mov     [rsp+0A80h+var_A30], rax
0x18000e25c  mov     r14, rax
0x18000e25f  test    rax, rax
0x18000e262  jz      short loc_18000E271
0x18000e264  add     r14, 2
0x18000e268  mov     [rax], r12w
0x18000e26c  mov     [rsp+0A80h+var_A30], r14
0x18000e271  lea     rax, [rsp+0A80h+hKey]
0x18000e276  mov     r9d, 0Fh; samDesired
0x18000e27c  xor     r8d, r8d; ulOptions
0x18000e27f  mov     [rsp+0A80h+phkResult], rax; phkResult
0x18000e284  mov     rdx, rbx; lpSubKey
0x18000e287  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e28e  call    cs:__imp_RegOpenKeyExW
0x18000e294  test    eax, eax
0x18000e296  jnz     loc_18000E5C4
0x18000e29c  mov     edx, [rsi+38h]
0x18000e29f  test    edx, edx
0x18000e2a1  jnz     short loc_18000E2E2
0x18000e2a3  cmp     cs:g_fVelocityDhcpv4InformNegativeCacheFix, r12d
0x18000e2aa  jz      short loc_18000E2CD
0x18000e2ac  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000e2b3  jz      short loc_18000E2CD
0x18000e2b5  mov     r9d, [rsi+10h]
0x18000e2b9  lea     edx, [rax+0Bh]
0x18000e2bc  mov     ecx, 404h
0x18000e2c1  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e2c8  call    WPP_SF_d
0x18000e2cd  mov     rcx, [rsp+0A80h+hKey]; hKey
0x18000e2d2  mov     rdx, r14; lpValueName
0x18000e2d5  call    cs:__imp_RegDeleteValueW
0x18000e2db  mov     ebx, eax
0x18000e2dd  jmp     loc_18000E36F
0x18000e2e2  test    edi, edi
0x18000e2e4  jnz     loc_18000E56D
0x18000e2ea  mov     ecx, [rsi+10h]
0x18000e2ed  lea     r8d, [rdi+20h]
0x18000e2f1  mov     [rsp+0A80h+var_A50], r12d
0x18000e2f6  mov     r13, r12
0x18000e2f9  mov     [rsp+0A80h+var_A38], r12
0x18000e2fe  sub     ecx, 1
0x18000e301  jz      short loc_18000E348
0x18000e303  sub     ecx, 2
0x18000e306  jz      short loc_18000E348
0x18000e308  sub     ecx, 3
0x18000e30b  jz      short loc_18000E348
0x18000e30d  sub     ecx, 26h ; '&'
0x18000e310  jz      short loc_18000E348
0x18000e312  cmp     ecx, 2
0x18000e315  jz      short loc_18000E322
0x18000e317  mov     rdi, r12
0x18000e31a  mov     ebx, r12d
0x18000e31d  jmp     loc_18000E473
0x18000e322  cmp     edx, 1
0x18000e325  jnz     short loc_18000E330
0x18000e327  mov     rax, [rsi+30h]
0x18000e32b  movzx   ecx, byte ptr [rax]
0x18000e32e  jmp     short loc_18000E335
0x18000e330  mov     ecx, 1
0x18000e335  mov     [rsp+0A80h+var_A50], ecx
0x18000e339  lea     rdi, [rsp+0A80h+var_A50]
0x18000e33e  mov     ebx, 4
0x18000e343  jmp     loc_18000E473
0x18000e348  imul    rcx, rdx, 22h ; '"'
0x18000e34c  shr     rcx, 2
0x18000e350  cmp     ecx, 3E8h
0x18000e356  jbe     short loc_18000E384
0x18000e358  mov     ecx, ecx
0x18000e35a  call    DhcpAlloc
0x18000e35f  mov     [rsp+0A80h+var_A38], rax
0x18000e364  mov     r13, rax
0x18000e367  test    rax, rax
0x18000e36a  jnz     short loc_18000E37F
0x18000e36c  lea     ebx, [rax+8]
0x18000e36f  mov     rcx, [rsp+0A80h+hKey]; hKey
0x18000e374  call    cs:__imp_RegCloseKey
0x18000e37a  jmp     loc_18000E5C2
0x18000e37f  mov     rdi, rax
0x18000e382  jmp     short loc_18000E38B
0x18000e384  lea     rdi, [rbp+980h+var_810]
0x18000e38b  xor     ecx, ecx
0x18000e38d  mov     r12, rdi
0x18000e390  test    dword ptr [rsi+38h], 0FFFFFFFCh
0x18000e397  jbe     loc_18000E445
0x18000e39d  mov     r13d, ecx
0x18000e3a0  mov     r14, rdi
0x18000e3a3  mov     rax, [rsi+30h]
0x18000e3a7  mov     ecx, r13d
0x18000e3aa  mov     ecx, [rax+rcx*4]; in
0x18000e3ad  call    cs:__imp_inet_ntoa
0x18000e3b3  xorps   xmm0, xmm0
0x18000e3b6  lea     rcx, [rsp+0A80h+DestinationString]; DestinationString
0x18000e3bb  mov     rdx, rax; SourceString
0x18000e3be  mov     rbx, rax
0x18000e3c1  movups  xmmword ptr [rsp+0A80h+DestinationString.Length], xmm0
0x18000e3c6  call    cs:__imp_RtlInitString
0x18000e3cc  lea     rcx, [rsp+0A80h+DestinationString]; OemString
0x18000e3d1  call    cs:__imp_RtlxOemStringToUnicodeSize
0x18000e3d7  mov     rdx, r14
0x18000e3da  mov     rcx, rbx; SourceString
0x18000e3dd  mov     r8d, eax
0x18000e3e0  call    DhcpOemToUnicodeN
0x18000e3e5  mov     rbx, rax
0x18000e3e8  test    byte ptr cs:xmmword_18001E1E0+1, 20h
0x18000e3ef  jz      short loc_18000E40A
0x18000e3f1  mov     edx, 0Ch
0x18000e3f6  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e3fd  mov     ecx, 40Dh
0x18000e402  mov     r9, rax
0x18000e405  call    WPP_SF_S
0x18000e40a  xor     ecx, ecx
0x18000e40c  test    rbx, rbx
0x18000e40f  jz      short loc_18000E43B
0x18000e411  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e415  inc     rax
0x18000e418  cmp     [rbx+rax*2], cx
0x18000e41c  jnz     short loc_18000E415
0x18000e41e  lea     r14, [rbx+2]
0x18000e422  inc     r13d
0x18000e425  lea     r14, [r14+rax*2]
0x18000e429  mov     eax, [rsi+38h]
0x18000e42c  shr     eax, 2
0x18000e42f  mov     r12, r14
0x18000e432  cmp     r13d, eax
0x18000e435  jb      loc_18000E3A3
0x18000e43b  mov     r14, [rsp+0A80h+var_A30]
0x18000e440  mov     r13, [rsp+0A80h+var_A38]
0x18000e445  mov     [r12], cx
0x18000e44a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e44e  inc     rax
0x18000e451  cmp     [r12+rax*2], cx
0x18000e456  jnz     short loc_18000E44E
0x18000e458  add     rax, rax
0x18000e45b  sub     rax, rdi
0x18000e45e  add     rax, r12
0x18000e461  sar     rax, 1
0x18000e464  xor     r12d, r12d
0x18000e467  lea     ebx, ds:2[rax*2]
0x18000e46e  lea     r8d, [r12+20h]
0x18000e473  cmp     dword ptr [rsi+10h], 2Ch ; ','
0x18000e477  jnz     short loc_18000E48B
0x18000e479  test    ebx, ebx
0x18000e47b  jnz     short loc_18000E4EE
0x18000e47d  lea     rdi, byte_180018278
0x18000e484  mov     ebx, 2
0x18000e489  jmp     short loc_18000E4EE
0x18000e48b  cmp     dword ptr [rsi+10h], 6
0x18000e48f  jnz     short loc_18000E4EE
0x18000e491  mov     eax, [rsi+38h]
0x18000e494  mov     edx, 1
0x18000e499  shr     eax, 2
0x18000e49c  add     ebx, 0FFFFFFFEh
0x18000e49f  mov     [rsp+0A80h+var_A50], eax
0x18000e4a3  mov     rcx, rdi
0x18000e4a6  cmp     eax, edx
0x18000e4a8  jbe     short loc_18000E4CC
0x18000e4aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e4ae  inc     rax
0x18000e4b1  cmp     [rcx+rax*2], r12w
0x18000e4b6  jnz     short loc_18000E4AE
0x18000e4b8  lea     rax, [rcx+rax*2]
0x18000e4bc  inc     edx
0x18000e4be  mov     [rax], r8w
0x18000e4c2  lea     rcx, [rax+2]
0x18000e4c6  cmp     edx, [rsp+0A80h+var_A50]
0x18000e4ca  jb      short loc_18000E4AA
0x18000e4cc  test    byte ptr cs:xmmword_18001E1E0+1, r8b
0x18000e4d3  jz      short loc_18000E4EE
0x18000e4d5  mov     edx, 0Dh
0x18000e4da  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e4e1  mov     ecx, 40Dh
0x18000e4e6  mov     r9, rdi
0x18000e4e9  call    WPP_SF_S
0x18000e4ee  mov     eax, r12d
0x18000e4f1  lea     rdx, qword_18001E080
0x18000e4f8  mov     r8d, eax
0x18000e4fb  mov     ecx, [rdx+r8*8]
0x18000e4ff  test    ecx, ecx
0x18000e501  jz      short loc_18000E56D
0x18000e503  cmp     [rsi+10h], ecx
0x18000e506  jz      short loc_18000E50C
0x18000e508  inc     eax
0x18000e50a  jmp     short loc_18000E4F8
0x18000e50c  mov     r8d, [rdx+r8*8+4]; dwType
0x18000e511  mov     r9, rdi; Buf2
0x18000e514  mov     rcx, [rsp+0A80h+hKey]; hKey
0x18000e519  mov     rdx, r14; lpValueName
0x18000e51c  mov     dword ptr [rsp+0A80h+phkResult], ebx; Size
0x18000e520  call    DhcpRegSetOptionRegVal
0x18000e525  mov     ebx, eax
0x18000e527  test    eax, eax
0x18000e529  jz      short loc_18000E551
0x18000e52b  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000e532  jz      short loc_18000E551
0x18000e534  mov     edx, 0Eh
0x18000e539  mov     dword ptr [rsp+0A80h+phkResult], eax
0x18000e53d  mov     ecx, 401h
0x18000e542  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e549  mov     r9, r14
0x18000e54c  call    WPP_SF_SD
0x18000e551  mov     rcx, [rsp+0A80h+hKey]; hKey
0x18000e556  call    cs:__imp_RegCloseKey
0x18000e55c  test    r13, r13
0x18000e55f  jz      short loc_18000E5C2
0x18000e561  lea     rcx, [rsp+0A80h+var_A38]
0x18000e566  call    DhcpFree
0x18000e56b  jmp     short loc_18000E5C2
0x18000e56d  mov     eax, [rsi+38h]
0x18000e570  mov     r8d, 3; dwType
0x18000e576  mov     r9, [rsi+30h]; Buf2
0x18000e57a  mov     rdx, r14; lpValueName
0x18000e57d  mov     rcx, [rsp+0A80h+hKey]; hKey
0x18000e582  mov     dword ptr [rsp+0A80h+phkResult], eax; Size
0x18000e586  call    DhcpRegSetOptionRegVal
0x18000e58b  mov     ebx, eax
0x18000e58d  mov     rcx, [rsp+0A80h+hKey]; hKey
0x18000e592  call    cs:__imp_RegCloseKey
0x18000e598  test    ebx, ebx
0x18000e59a  jz      short loc_18000E5C2
0x18000e59c  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000e5a3  jz      short loc_18000E5C2
0x18000e5a5  mov     edx, 12h
0x18000e5aa  mov     dword ptr [rsp+0A80h+phkResult], ebx
0x18000e5ae  mov     ecx, 401h
0x18000e5b3  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e5ba  mov     r9, r14
0x18000e5bd  call    WPP_SF_SD
0x18000e5c2  mov     eax, ebx
0x18000e5c4  mov     rcx, [rbp+980h+var_30]
0x18000e5cb  xor     rcx, rsp; StackCookie
0x18000e5ce  call    __security_check_cookie
0x18000e5d3  lea     r11, [rsp+0A80h+var_20]
0x18000e5db  mov     rbx, [r11+40h]
0x18000e5df  mov     rsi, [r11+48h]
0x18000e5e3  mov     rsp, r11
0x18000e5e6  pop     r14
0x18000e5e8  pop     r13
0x18000e5ea  pop     r12
0x18000e5ec  pop     rdi
0x18000e5ed  pop     rbp
0x18000e5ee  retn
```
