# UnMarshallRegistryFilterObject

- ea: `0x18003a12c`
- end: `0x18003a660`
- name: `UnMarshallRegistryFilterObject`
- size: `1332`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800394e4`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000c828`
- `0x18000e510`
- `0x180039f64`
- `0x18003a12c`
- `0x180042afc`
- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a37e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a5a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a37e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a5a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a1fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a1fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a640`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a640`

## pseudocode

```c
__int64 __fastcall UnMarshallRegistryFilterObject(HKEY hKey, __int64 a2, unsigned __int16 *a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  __int64 v9; // r9
  unsigned int Value; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _DWORD *v13; // rdi
  unsigned __int16 *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int16 *v18; // r14
  unsigned int v19; // esi
  _WORD *i; // rax
  __int64 v21; // rcx
  _QWORD *v22; // r12
  unsigned __int16 *v23; // rbx
  unsigned int j; // r15d
  unsigned __int16 *v25; // rax
  __int64 v26; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  BYTE v29[4]; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-10h]
  SIZE_T v32; // [rsp+48h] [rbp-8h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+58h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v29 = 0;
  lpMem = 0;
  v32 = 0;
  if ( !a3 || !*a3 )
  {
    v9 = 13;
    Value = 13;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_75;
    v12 = 57;
LABEL_74:
    WPP_SF_d(v11[2], v12, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v9);
    goto LABEL_75;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 <= (unsigned int)(v7 + 1) )
  {
    v9 = 13;
    Value = 13;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_75;
    v12 = 58;
    goto LABEL_74;
  }
  Value = RegOpenKeyExW(hKey, &a3[(unsigned int)v7 + 1], 0, 0x20019u, &hKeya);
  if ( Value )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_75;
    v12 = 59;
    v9 = Value;
    goto LABEL_74;
  }
  v13 = IpsecAllocMem(0x48u);
  if ( !v13 )
  {
    Value = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_75;
    v12 = 60;
    v9 = 14;
    goto LABEL_74;
  }
  v14 = IpsecAllocStr(a3);
  *(_QWORD *)v13 = v14;
  if ( !v14 )
  {
    Value = 14;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 61;
    goto LABEL_23;
  }
  RegstoreQueryValue(hKeya, L"description", (__int64)&cbData);
  RegstoreQueryValue(hKeya, L"ipsecName", (__int64)&cbData);
  Value = RegstoreQueryValue(hKeya, L"ipsecID", (__int64)&cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 62;
    goto LABEL_67;
  }
  Type = 4;
  cbData = 4;
  Value = RegQueryValueExW(hKeya, L"ipsecDataType", 0, &Type, Data, &cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 63;
    goto LABEL_67;
  }
  v13[6] = *(_DWORD *)Data;
  Value = RegstoreQueryValue(hKeya, L"ipsecData", (__int64)(v13 + 10));
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 64;
    goto LABEL_67;
  }
  if ( (unsigned int)RegstoreQueryValue(hKeya, L"ipsecOwnersReference", (__int64)&cbData) )
  {
LABEL_63:
    Type = 4;
    cbData = 4;
    Value = RegQueryValueExW(hKeya, L"whenChanged", 0, &Type, v29, &cbData);
    if ( !Value )
    {
      v13[15] = *(_DWORD *)v29;
      goto LABEL_76;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 68;
LABEL_67:
    v17 = Value;
    goto LABEL_68;
  }
  v18 = (unsigned __int16 *)lpMem;
  v19 = 0;
  for ( i = lpMem; *i; i += v21 + 1 )
  {
    v21 = -1;
    do
      ++v21;
    while ( i[v21] );
    ++v19;
  }
  Value = NsuSizeTMultiply(v19, 8, &v32);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 65;
    goto LABEL_67;
  }
  v22 = IpsecAllocMem(v32);
  if ( v22 )
  {
    v23 = v18;
    for ( j = 0; ; ++j )
    {
      if ( j >= v19 )
      {
        if ( v18 )
          IpsecFreeMem(v18);
        v13[14] = v19;
        *((_QWORD *)v13 + 6) = v22;
        goto LABEL_63;
      }
      v25 = IpsecAllocStr(v23);
      if ( !v25 )
        break;
      v22[j] = v25;
      v26 = -1;
      do
        ++v26;
      while ( v23[v26] );
      v23 += v26 + 1;
    }
    *((_QWORD *)v13 + 6) = v22;
    v13[14] = j;
    Value = 14;
    if ( v18 )
      IpsecFreeMem(v18);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v16 = 67;
      goto LABEL_23;
    }
    goto LABEL_69;
  }
  Value = 14;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v16 = 66;
LABEL_23:
    v17 = 14;
LABEL_68:
    WPP_SF_d(v15[2], v16, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v17);
  }
LABEL_69:
  FreeIpsecFilterObject(v13);
LABEL_75:
  v13 = 0;
LABEL_76:
  *a5 = v13;
  if ( hKeya )
    RegCloseKey(hKeya);
  return Value;
}

```

## disassembly

```asm
0x18003a12c  mov     [rsp-38h+arg_0], rbx
0x18003a131  mov     [rsp-38h+cbData], r9d
0x18003a136  push    rbp
0x18003a137  push    rsi
0x18003a138  push    rdi
0x18003a139  push    r12
0x18003a13b  push    r13
0x18003a13d  push    r14
0x18003a13f  push    r15
0x18003a141  mov     rbp, rsp
0x18003a144  sub     rsp, 50h
0x18003a148  xor     r13d, r13d
0x18003a14b  mov     rsi, r8
0x18003a14e  mov     [rbp+hKey], r13
0x18003a152  mov     rax, rdx
0x18003a155  mov     [rbp+Type], r13d
0x18003a159  mov     r10, rcx
0x18003a15c  mov     [rbp+cbData], r13d
0x18003a160  mov     dword ptr [rbp+Data], r13d
0x18003a164  mov     dword ptr [rbp+var_1C], r13d
0x18003a168  mov     [rbp+lpMem], r13
0x18003a16c  mov     [rbp+var_8], r13
0x18003a170  test    r8, r8
0x18003a173  jz      loc_18003A5F7
0x18003a179  cmp     [r8], r13w
0x18003a17d  jz      loc_18003A5F7
0x18003a183  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003a187  mov     rdx, r15
0x18003a18a  inc     rdx
0x18003a18d  cmp     [rax+rdx*2], r13w
0x18003a192  jnz     short loc_18003A18A
0x18003a194  mov     r8, r15
0x18003a197  inc     r8
0x18003a19a  cmp     [rsi+r8*2], r13w
0x18003a19f  jnz     short loc_18003A197
0x18003a1a1  lea     ecx, [rdx+1]
0x18003a1a4  cmp     r8, rcx
0x18003a1a7  ja      short loc_18003A1DC
0x18003a1a9  mov     r9d, 0Dh
0x18003a1af  mov     ebx, r9d
0x18003a1b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1b9  lea     rax, WPP_GLOBAL_Control
0x18003a1c0  cmp     rcx, rax
0x18003a1c3  jz      loc_18003A62D
0x18003a1c9  test    byte ptr [rcx+1Ch], 10h
0x18003a1cd  jz      loc_18003A62D
0x18003a1d3  lea     edx, [r9+2Dh]
0x18003a1d7  jmp     loc_18003A61D
0x18003a1dc  mov     eax, edx
0x18003a1de  mov     r9d, 20019h; samDesired
0x18003a1e4  inc     rax
0x18003a1e7  xor     r8d, r8d; ulOptions
0x18003a1ea  mov     rcx, r10; hKey
0x18003a1ed  lea     rdx, [rsi+rax*2]; lpSubKey
0x18003a1f1  lea     rax, [rbp+hKey]
0x18003a1f5  mov     [rsp+50h+phkResult], rax; phkResult
0x18003a1fa  call    cs:__imp_RegOpenKeyExW
0x18003a200  mov     ebx, eax
0x18003a202  test    eax, eax
0x18003a204  jz      short loc_18003A234
0x18003a206  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a20d  lea     rax, WPP_GLOBAL_Control
0x18003a214  cmp     rcx, rax
0x18003a217  jz      loc_18003A62D
0x18003a21d  test    byte ptr [rcx+1Ch], 10h
0x18003a221  jz      loc_18003A62D
0x18003a227  mov     edx, 3Bh ; ';'
0x18003a22c  mov     r9d, ebx
0x18003a22f  jmp     loc_18003A61D
0x18003a234  mov     ecx, 48h ; 'H'
0x18003a239  call    IpsecAllocMem
0x18003a23e  mov     rdi, rax
0x18003a241  test    rax, rax
0x18003a244  jnz     short loc_18003A277
0x18003a246  lea     esi, [rax+0Eh]
0x18003a249  mov     ebx, esi
0x18003a24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a252  lea     rax, WPP_GLOBAL_Control
0x18003a259  cmp     rcx, rax
0x18003a25c  jz      loc_18003A62D
0x18003a262  test    byte ptr [rcx+1Ch], 10h
0x18003a266  jz      loc_18003A62D
0x18003a26c  lea     edx, [rdi+3Ch]
0x18003a26f  mov     r9d, esi
0x18003a272  jmp     loc_18003A61D
0x18003a277  mov     rcx, rsi; unsigned __int16 *
0x18003a27a  call    IpsecAllocStr
0x18003a27f  mov     [rdi], rax
0x18003a282  test    rax, rax
0x18003a285  jnz     short loc_18003A2B8
0x18003a287  lea     esi, [rax+0Eh]
0x18003a28a  mov     ebx, esi
0x18003a28c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a293  lea     rax, WPP_GLOBAL_Control
0x18003a29a  cmp     rcx, rax
0x18003a29d  jz      loc_18003A5E5
0x18003a2a3  test    byte ptr [rcx+1Ch], 10h
0x18003a2a7  jz      loc_18003A5E5
0x18003a2ad  lea     edx, [rsi+2Fh]
0x18003a2b0  mov     r9d, esi
0x18003a2b3  jmp     loc_18003A5D5
0x18003a2b8  mov     rcx, [rbp+hKey]; hKey
0x18003a2bc  lea     rax, [rbp+cbData]
0x18003a2c0  mov     r12d, 1
0x18003a2c6  mov     [rsp+50h+phkResult], rax; __int64
0x18003a2cb  mov     r8d, r12d
0x18003a2ce  lea     r9, [rdi+40h]
0x18003a2d2  lea     rdx, aDescription; "description"
0x18003a2d9  call    RegstoreQueryValue
0x18003a2de  mov     rcx, [rbp+hKey]; hKey
0x18003a2e2  lea     rax, [rbp+cbData]
0x18003a2e6  lea     r9, [rdi+8]
0x18003a2ea  mov     [rsp+50h+phkResult], rax; __int64
0x18003a2ef  mov     r8d, r12d
0x18003a2f2  lea     rdx, aIpsecname; "ipsecName"
0x18003a2f9  call    RegstoreQueryValue
0x18003a2fe  mov     rcx, [rbp+hKey]; hKey
0x18003a302  lea     rax, [rbp+cbData]
0x18003a306  lea     r9, [rdi+10h]
0x18003a30a  mov     [rsp+50h+phkResult], rax; __int64
0x18003a30f  mov     r8d, r12d
0x18003a312  lea     rdx, aIpsecid; "ipsecID"
0x18003a319  call    RegstoreQueryValue
0x18003a31e  mov     ebx, eax
0x18003a320  test    eax, eax
0x18003a322  jz      short loc_18003A34F
0x18003a324  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a32b  lea     rax, WPP_GLOBAL_Control
0x18003a332  cmp     rcx, rax
0x18003a335  jz      loc_18003A5E5
0x18003a33b  test    byte ptr [rcx+1Ch], 10h
0x18003a33f  jz      loc_18003A5E5
0x18003a345  lea     edx, [r12+3Dh]
0x18003a34a  jmp     loc_18003A5D2
0x18003a34f  mov     rcx, [rbp+hKey]; hKey
0x18003a353  lea     rax, [rbp+cbData]
0x18003a357  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003a35c  lea     r9, [rbp+Type]; lpType
0x18003a360  lea     rax, [rbp+Data]
0x18003a364  mov     esi, 4
0x18003a369  xor     r8d, r8d; lpReserved
0x18003a36c  mov     [rsp+50h+phkResult], rax; lpData
0x18003a371  lea     rdx, aIpsecdatatype; "ipsecDataType"
0x18003a378  mov     [rbp+Type], esi
0x18003a37b  mov     [rbp+cbData], esi
0x18003a37e  call    cs:__imp_RegQueryValueExW
0x18003a384  mov     ebx, eax
0x18003a386  test    eax, eax
0x18003a388  jz      short loc_18003A3B3
0x18003a38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a391  lea     rax, WPP_GLOBAL_Control
0x18003a398  cmp     rcx, rax
0x18003a39b  jz      loc_18003A5E5
0x18003a3a1  test    byte ptr [rcx+1Ch], 10h
0x18003a3a5  jz      loc_18003A5E5
0x18003a3ab  lea     edx, [rsi+3Bh]
0x18003a3ae  jmp     loc_18003A5D2
0x18003a3b3  mov     eax, dword ptr [rbp+Data]
0x18003a3b6  lea     r9, [rdi+20h]
0x18003a3ba  mov     [rdi+18h], eax
0x18003a3bd  lea     rdx, attr; "ipsecData"
0x18003a3c4  mov     r8d, [rbp+Type]
0x18003a3c8  lea     rax, [rdi+28h]
0x18003a3cc  mov     rcx, [rbp+hKey]; hKey
0x18003a3d0  mov     [rsp+50h+phkResult], rax; __int64
0x18003a3d5  call    RegstoreQueryValue
0x18003a3da  mov     ebx, eax
0x18003a3dc  test    eax, eax
0x18003a3de  jz      short loc_18003A40B
0x18003a3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3e7  lea     rax, WPP_GLOBAL_Control
0x18003a3ee  cmp     rcx, rax
0x18003a3f1  jz      loc_18003A5E5
0x18003a3f7  test    byte ptr [rcx+1Ch], 10h
0x18003a3fb  jz      loc_18003A5E5
0x18003a401  mov     edx, 40h ; '@'
0x18003a406  jmp     loc_18003A5D2
0x18003a40b  mov     rcx, [rbp+hKey]; hKey
0x18003a40f  lea     rax, [rbp+cbData]
0x18003a413  lea     r9, [rbp+lpMem]
0x18003a417  mov     [rsp+50h+phkResult], rax; __int64
0x18003a41c  mov     r8d, 7
0x18003a422  lea     rdx, aIpsecownersref; "ipsecOwnersReference"
0x18003a429  call    RegstoreQueryValue
0x18003a42e  test    eax, eax
0x18003a430  jnz     loc_18003A57E
0x18003a436  mov     r14, [rbp+lpMem]
0x18003a43a  mov     esi, r13d
0x18003a43d  mov     rax, r14
0x18003a440  cmp     [r14], r13w
0x18003a444  jz      short loc_18003A464
0x18003a446  mov     rcx, r15
0x18003a449  inc     rcx
0x18003a44c  cmp     [rax+rcx*2], r13w
0x18003a451  jnz     short loc_18003A449
0x18003a453  lea     rax, [rax+rcx*2]
0x18003a457  add     esi, r12d
0x18003a45a  add     rax, 2
0x18003a45e  cmp     [rax], r13w
0x18003a462  jnz     short loc_18003A446
0x18003a464  mov     ecx, esi
0x18003a466  lea     r8, [rbp+var_8]
0x18003a46a  mov     edx, 8
0x18003a46f  call    NsuSizeTMultiply
0x18003a474  mov     ebx, eax
0x18003a476  test    eax, eax
0x18003a478  jz      short loc_18003A4A5
0x18003a47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a481  lea     rax, WPP_GLOBAL_Control
0x18003a488  cmp     rcx, rax
0x18003a48b  jz      loc_18003A5E5
0x18003a491  test    byte ptr [rcx+1Ch], 10h
0x18003a495  jz      loc_18003A5E5
0x18003a49b  mov     edx, 41h ; 'A'
0x18003a4a0  jmp     loc_18003A5D2
0x18003a4a5  mov     rcx, [rbp+var_8]
0x18003a4a9  call    IpsecAllocMem
0x18003a4ae  mov     r12, rax
0x18003a4b1  test    rax, rax
0x18003a4b4  jnz     short loc_18003A4E4
0x18003a4b6  lea     esi, [rax+0Eh]
0x18003a4b9  mov     ebx, esi
0x18003a4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4c2  lea     rax, WPP_GLOBAL_Control
0x18003a4c9  cmp     rcx, rax
0x18003a4cc  jz      loc_18003A5E5
0x18003a4d2  test    byte ptr [rcx+1Ch], 10h
0x18003a4d6  jz      loc_18003A5E5
0x18003a4dc  lea     edx, [rsi+34h]
0x18003a4df  jmp     loc_18003A2B0
0x18003a4e4  mov     rbx, r14
0x18003a4e7  mov     r15d, r13d
0x18003a4ea  cmp     r15d, esi
0x18003a4ed  jnb     short loc_18003A565
0x18003a4ef  mov     rcx, rbx; unsigned __int16 *
0x18003a4f2  call    IpsecAllocStr
0x18003a4f7  test    rax, rax
0x18003a4fa  jz      short loc_18003A51E
0x18003a4fc  mov     ecx, r15d
0x18003a4ff  mov     [r12+rcx*8], rax
0x18003a503  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a507  inc     rax
0x18003a50a  cmp     [rbx+rax*2], r13w
0x18003a50f  jnz     short loc_18003A507
0x18003a511  lea     rbx, [rbx+rax*2]
0x18003a515  add     rbx, 2
0x18003a519  inc     r15d
0x18003a51c  jmp     short loc_18003A4EA
0x18003a51e  mov     [rdi+30h], r12
0x18003a522  mov     esi, 0Eh
0x18003a527  mov     [rdi+38h], r15d
0x18003a52b  mov     ebx, esi
0x18003a52d  test    r14, r14
0x18003a530  jz      short loc_18003A53A
0x18003a532  mov     rcx, r14; lpMem
0x18003a535  call    IpsecFreeMem
0x18003a53a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a541  lea     rax, WPP_GLOBAL_Control
0x18003a548  cmp     rcx, rax
0x18003a54b  jz      loc_18003A5E5
0x18003a551  test    byte ptr [rcx+1Ch], 10h
0x18003a555  jz      loc_18003A5E5
0x18003a55b  mov     edx, 43h ; 'C'
0x18003a560  jmp     loc_18003A2B0
0x18003a565  test    r14, r14
0x18003a568  jz      short loc_18003A572
0x18003a56a  mov     rcx, r14; lpMem
0x18003a56d  call    IpsecFreeMem
0x18003a572  mov     [rdi+38h], esi
0x18003a575  mov     esi, 4
0x18003a57a  mov     [rdi+30h], r12
0x18003a57e  mov     rcx, [rbp+hKey]; hKey
0x18003a582  lea     rax, [rbp+cbData]
0x18003a586  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003a58b  lea     r9, [rbp+Type]; lpType
0x18003a58f  lea     rax, [rbp+var_1C]
0x18003a593  mov     [rbp+Type], esi
0x18003a596  xor     r8d, r8d; lpReserved
0x18003a599  mov     [rsp+50h+phkResult], rax; lpData
0x18003a59e  lea     rdx, aWhenchanged; "whenChanged"
0x18003a5a5  mov     [rbp+cbData], esi
0x18003a5a8  call    cs:__imp_RegQueryValueExW
0x18003a5ae  mov     ebx, eax
0x18003a5b0  test    eax, eax
0x18003a5b2  jz      short loc_18003A5EF
0x18003a5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a5bb  lea     rax, WPP_GLOBAL_Control
0x18003a5c2  cmp     rcx, rax
0x18003a5c5  jz      short loc_18003A5E5
0x18003a5c7  test    byte ptr [rcx+1Ch], 10h
0x18003a5cb  jz      short loc_18003A5E5
0x18003a5cd  mov     edx, 44h ; 'D'
0x18003a5d2  mov     r9d, ebx
0x18003a5d5  mov     rcx, [rcx+10h]
0x18003a5d9  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003a5e0  call    WPP_SF_d
0x18003a5e5  mov     rcx, rdi; lpMem
0x18003a5e8  call    FreeIpsecFilterObject
0x18003a5ed  jmp     short loc_18003A62D
0x18003a5ef  mov     eax, dword ptr [rbp+var_1C]
  ... truncated ...
```
