# getLibraryPathForEapTypeId(ushort const *,ushort * *)

- ea: `0x180012130`
- end: `0x1800124ba`
- name: `?getLibraryPathForEapTypeId@@YAKPEBGPEAPEAG@Z`
- size: `906`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18005fb70`
- `0x18005ff50`

## callees

- `0x1800075b0`
- `0x18000f350`
- `0x180012130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001246b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001246b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012170`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800123c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001243a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012170`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800123c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001243a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001247e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800124a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001247e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800124a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012492`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012492`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012315`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012315`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800123a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800123ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800123a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800123ff`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012423`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001245a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012423`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001245a`

## string_xrefs

- `0x180012374`: `ConfigUIPath`
- `0x1800123f0`: `ConfigUIPath`
- `0x1800121d8`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`

## pseudocode

```c
__int64 __fastcall getLibraryPathForEapTypeId(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  SIZE_T v6; // rdi
  WCHAR *v7; // rax
  WCHAR *v8; // r14
  DWORD LastError; // ebx
  unsigned __int64 v10; // rdi
  __int64 v11; // r10
  __int64 v12; // rcx
  const WCHAR *v13; // r8
  unsigned __int64 v14; // rdx
  WCHAR *v15; // rcx
  WCHAR *v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  const unsigned __int16 *v19; // r8
  __int64 v20; // rcx
  WCHAR *v21; // rax
  unsigned __int64 v22; // r9
  WCHAR *v23; // rcx
  unsigned __int64 v24; // rcx
  WCHAR *v25; // rax
  WCHAR *v26; // rax
  unsigned __int64 v27; // rdi
  WCHAR *v28; // rcx
  HKEY v29; // rbp
  HKEY v30; // rcx
  BYTE *v31; // rsi
  unsigned __int16 *v32; // rdi
  WCHAR *v33; // rax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+18h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  v3 = a1;
  v4 = -1;
  while ( a1[++v4] != 0 )
    ;
  v6 = 2 * (int)v4 + 102;
  v7 = (WCHAR *)LocalAlloc(0x40u, v6);
  v8 = v7;
  if ( v7 )
  {
    v10 = v6 >> 1;
    v11 = 2147483646;
    if ( !v10 )
      goto LABEL_26;
    if ( v10 > 0x7FFFFFFF )
    {
      *v7 = 0;
      goto LABEL_38;
    }
    v12 = 2147483646;
    v13 = L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP";
    v14 = v10;
    do
    {
      if ( !v12 )
        break;
      if ( !*v13 )
        break;
      *v7++ = *v13++;
      --v12;
      --v14;
    }
    while ( v14 );
    v15 = v7 - 1;
    if ( v14 )
      v15 = v7;
    v16 = v8;
    *v15 = 0;
    v17 = v10;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v17;
    }
    while ( v17 );
    v18 = v10 - v17;
    if ( v17 )
    {
      v19 = L"\\";
      v20 = 2147483646;
      v21 = &v8[v18];
      v22 = v10 - v18;
      if ( v10 != v18 )
      {
        do
        {
          if ( !v20 )
            break;
          if ( !*v19 )
            break;
          *v21++ = *v19++;
          --v20;
          --v22;
        }
        while ( v22 );
      }
      v23 = v21 - 1;
      if ( v22 )
        v23 = v21;
      *v23 = 0;
      v24 = v10;
    }
    else
    {
LABEL_26:
      v24 = v10;
      if ( !v10 )
        goto LABEL_38;
    }
    v25 = v8;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    if ( v24 )
    {
      v26 = &v8[v10 - v24];
      v27 = v24;
      do
      {
        if ( !v11 )
          break;
        if ( !*v3 )
          break;
        *v26++ = *v3++;
        --v11;
        --v27;
      }
      while ( v27 );
      v28 = v26 - 1;
      if ( v27 )
        v28 = v26;
      *v28 = 0;
    }
LABEL_38:
    LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v8);
      goto LABEL_50;
    }
    v29 = hKey;
    v30 = hKey;
    Type = 0;
    cbData = 0;
    v31 = 0;
    v32 = 0;
    *a2 = 0;
    LastError = RegQueryValueExW(v30, L"ConfigUIPath", 0, &Type, 0, &cbData);
    if ( !LastError )
    {
      v31 = (BYTE *)LocalAlloc(0x40u, cbData);
      if ( v31 )
      {
        LastError = RegQueryValueExW(v29, L"ConfigUIPath", 0, &Type, v31, &cbData);
        if ( LastError )
          goto LABEL_49;
        *(_WORD *)&v31[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
        cbData = ExpandEnvironmentStringsW((LPCWSTR)v31, 0, 0);
        v33 = (WCHAR *)LocalAlloc(0x40u, 2LL * cbData);
        v32 = v33;
        if ( v33 )
        {
          *v33 = 0;
          cbData = ExpandEnvironmentStringsW((LPCWSTR)v31, v33, cbData);
          if ( cbData )
          {
            *a2 = v32;
            v32 = 0;
          }
          else
          {
            LastError = GetLastError();
          }
          goto LABEL_49;
        }
      }
      LastError = 14;
    }
LABEL_49:
    LocalFree(v31);
    LocalFree(v32);
    RegCloseKey(hKey);
LABEL_50:
    LocalFree(v8);
    return LastError;
  }
  LastError = 14;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x180012130  push    rbx
0x180012132  push    rdi
0x180012133  push    r12
0x180012135  push    r14
0x180012137  push    r15
0x180012139  sub     rsp, 40h
0x18001213d  xor     r12d, r12d
0x180012140  mov     r15, rdx
0x180012143  mov     [rsp+68h+hKey], r12
0x180012148  mov     rbx, rcx
0x18001214b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012152  cmp     [rcx+rax*2+2], r12w
0x180012158  lea     rax, [rax+1]
0x18001215c  jnz     short loc_180012152
0x18001215e  lea     eax, ds:66h[rax*2]
0x180012165  mov     ecx, 40h ; '@'; uFlags
0x18001216a  movsxd  rdi, eax
0x18001216d  mov     rdx, rdi; uBytes
0x180012170  call    cs:__imp_LocalAlloc
0x180012176  mov     r14, rax
0x180012179  test    rax, rax
0x18001217c  jnz     short loc_1800121B4
0x18001217e  mov     ebx, 0Eh
0x180012183  mov     rcx, cs:WPP_GLOBAL_Control
0x18001218a  lea     rax, WPP_GLOBAL_Control
0x180012191  cmp     rcx, rax
0x180012194  jz      loc_1800124AB
0x18001219a  mov     rcx, [rcx+10h]
0x18001219e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800121a5  mov     edx, 0F8h
0x1800121aa  call    WPP_SF_
0x1800121af  jmp     loc_1800124AB
0x1800121b4  shr     rdi, 1
0x1800121b7  mov     r10d, 7FFFFFFEh
0x1800121bd  jz      loc_180012288
0x1800121c3  cmp     rdi, 7FFFFFFFh
0x1800121ca  jbe     short loc_1800121D5
0x1800121cc  mov     [rax], r12w
0x1800121d0  jmp     loc_1800122F8
0x1800121d5  mov     rcx, r10
0x1800121d8  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x1800121df  mov     rdx, rdi
0x1800121e2  test    rcx, rcx
0x1800121e5  jz      short loc_180012206
0x1800121e7  movzx   r9d, word ptr [r8]
0x1800121eb  test    r9w, r9w
0x1800121ef  jz      short loc_180012206
0x1800121f1  mov     [rax], r9w
0x1800121f5  add     r8, 2
0x1800121f9  add     rax, 2
0x1800121fd  dec     rcx
0x180012200  sub     rdx, 1
0x180012204  jnz     short loc_1800121E2
0x180012206  lea     rcx, [rax-2]
0x18001220a  test    rdx, rdx
0x18001220d  mov     r9, rdi
0x180012210  cmovnz  rcx, rax
0x180012214  mov     rax, r14
0x180012217  mov     [rcx], r12w
0x18001221b  mov     rcx, rdi
0x18001221e  xchg    ax, ax
0x180012220  cmp     [rax], r12w
0x180012224  jz      short loc_180012230
0x180012226  add     rax, 2
0x18001222a  sub     rcx, 1
0x18001222e  jnz     short loc_180012220
0x180012230  mov     rdx, r9
0x180012233  sub     rdx, rcx
0x180012236  test    rcx, rcx
0x180012239  cmovz   rdx, r12
0x18001223d  jz      short loc_180012288
0x18001223f  lea     r8, asc_180081834; "\\"
0x180012246  mov     rcx, r10
0x180012249  lea     rax, [r14+rdx*2]
0x18001224d  sub     r9, rdx
0x180012250  jz      short loc_180012274
0x180012252  test    rcx, rcx
0x180012255  jz      short loc_180012274
0x180012257  movzx   edx, word ptr [r8]
0x18001225b  test    dx, dx
0x18001225e  jz      short loc_180012274
0x180012260  mov     [rax], dx
0x180012263  add     r8, 2
0x180012267  add     rax, 2
0x18001226b  dec     rcx
0x18001226e  sub     r9, 1
0x180012272  jnz     short loc_180012252
0x180012274  test    r9, r9
0x180012277  lea     rcx, [rax-2]
0x18001227b  cmovnz  rcx, rax
0x18001227f  mov     [rcx], r12w
0x180012283  mov     rcx, rdi
0x180012286  jmp     short loc_180012299
0x180012288  mov     rcx, rdi
0x18001228b  test    rdi, rdi
0x18001228e  jz      short loc_1800122F8
0x180012290  cmp     rcx, 7FFFFFFFh
0x180012297  ja      short loc_1800122F8
0x180012299  mov     rax, r14
0x18001229c  nop     dword ptr [rax+00h]
0x1800122a0  cmp     [rax], r12w
0x1800122a4  jz      short loc_1800122B0
0x1800122a6  add     rax, 2
0x1800122aa  sub     rcx, 1
0x1800122ae  jnz     short loc_1800122A0
0x1800122b0  mov     rdx, rdi
0x1800122b3  sub     rdx, rcx
0x1800122b6  test    rcx, rcx
0x1800122b9  cmovz   rdx, r12
0x1800122bd  jz      short loc_1800122F8
0x1800122bf  lea     rax, [r14+rdx*2]
0x1800122c3  sub     rdi, rdx
0x1800122c6  jz      short loc_1800122E9
0x1800122c8  test    r10, r10
0x1800122cb  jz      short loc_1800122E9
0x1800122cd  movzx   ecx, word ptr [rbx]
0x1800122d0  test    cx, cx
0x1800122d3  jz      short loc_1800122E9
0x1800122d5  mov     [rax], cx
0x1800122d8  add     rbx, 2
0x1800122dc  add     rax, 2
0x1800122e0  dec     r10
0x1800122e3  sub     rdi, 1
0x1800122e7  jnz     short loc_1800122C8
0x1800122e9  test    rdi, rdi
0x1800122ec  lea     rcx, [rax-2]
0x1800122f0  cmovnz  rcx, rax
0x1800122f4  mov     [rcx], r12w
0x1800122f8  lea     rax, [rsp+68h+hKey]
0x1800122fd  mov     r9d, 20019h; samDesired
0x180012303  xor     r8d, r8d; ulOptions
0x180012306  mov     [rsp+68h+phkResult], rax; phkResult
0x18001230b  mov     rdx, r14; lpSubKey
0x18001230e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012315  call    cs:__imp_RegOpenKeyExW
0x18001231b  mov     ebx, eax
0x18001231d  test    eax, eax
0x18001231f  jz      short loc_180012355
0x180012321  mov     rcx, cs:WPP_GLOBAL_Control
0x180012328  lea     rax, WPP_GLOBAL_Control
0x18001232f  cmp     rcx, rax
0x180012332  jz      loc_1800124A2
0x180012338  mov     rcx, [rcx+10h]
0x18001233c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180012343  mov     edx, 0F9h
0x180012348  mov     r9, r14
0x18001234b  call    WPP_SF_S
0x180012350  jmp     loc_1800124A2
0x180012355  mov     [rsp+68h+arg_0], rbp
0x18001235a  lea     rax, [rsp+68h+cbData]
0x180012362  mov     rbp, [rsp+68h+hKey]
0x180012367  lea     r9, [rsp+68h+Type]; lpType
0x18001236f  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180012374  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18001237b  mov     rcx, rbp; hKey
0x18001237e  mov     [rsp+68h+arg_8], rsi
0x180012383  xor     r8d, r8d; lpReserved
0x180012386  mov     [rsp+68h+Type], r12d
0x18001238e  mov     [rsp+68h+cbData], r12d
0x180012396  mov     rsi, r12
0x180012399  mov     rdi, r12
0x18001239c  mov     [r15], r12
0x18001239f  mov     [rsp+68h+phkResult], r12; lpData
0x1800123a4  call    cs:__imp_RegQueryValueExW
0x1800123aa  mov     ebx, eax
0x1800123ac  test    eax, eax
0x1800123ae  jnz     loc_18001247B
0x1800123b4  mov     edx, [rsp+68h+cbData]; uBytes
0x1800123bb  mov     ecx, 40h ; '@'; uFlags
0x1800123c0  call    cs:__imp_LocalAlloc
0x1800123c6  mov     rsi, rax
0x1800123c9  test    rax, rax
0x1800123cc  jnz     short loc_1800123D8
0x1800123ce  mov     ebx, 0Eh
0x1800123d3  jmp     loc_18001247B
0x1800123d8  lea     rax, [rsp+68h+cbData]
0x1800123e0  xor     r8d, r8d; lpReserved
0x1800123e3  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800123e8  lea     r9, [rsp+68h+Type]; lpType
0x1800123f0  lea     rdx, aConfiguipath; "ConfigUIPath"
0x1800123f7  mov     [rsp+68h+phkResult], rsi; lpData
0x1800123fc  mov     rcx, rbp; hKey
0x1800123ff  call    cs:__imp_RegQueryValueExW
0x180012405  mov     ebx, eax
0x180012407  test    eax, eax
0x180012409  jnz     short loc_18001247B
0x18001240b  mov     edx, [rsp+68h+cbData]
0x180012412  xor     r8d, r8d; nSize
0x180012415  shr     rdx, 1
0x180012418  mov     rcx, rsi; lpSrc
0x18001241b  mov     [rsi+rdx*2-2], r12w
0x180012421  xor     edx, edx; lpDst
0x180012423  call    cs:__imp_ExpandEnvironmentStringsW
0x180012429  mov     edx, eax
0x18001242b  mov     ecx, 40h ; '@'; uFlags
0x180012430  mov     [rsp+68h+cbData], edx
0x180012437  add     rdx, rdx; uBytes
0x18001243a  call    cs:__imp_LocalAlloc
0x180012440  mov     rdi, rax
0x180012443  test    rax, rax
0x180012446  jz      short loc_1800123CE
0x180012448  mov     [rax], r12w
0x18001244c  mov     rdx, rax; lpDst
0x18001244f  mov     r8d, [rsp+68h+cbData]; nSize
0x180012457  mov     rcx, rsi; lpSrc
0x18001245a  call    cs:__imp_ExpandEnvironmentStringsW
0x180012460  mov     [rsp+68h+cbData], eax
0x180012467  test    eax, eax
0x180012469  jnz     short loc_180012475
0x18001246b  call    cs:__imp_GetLastError
0x180012471  mov     ebx, eax
0x180012473  jmp     short loc_18001247B
0x180012475  mov     [r15], rdi
0x180012478  mov     rdi, r12
0x18001247b  mov     rcx, rsi; hMem
0x18001247e  call    cs:__imp_LocalFree
0x180012484  mov     rcx, rdi; hMem
0x180012487  call    cs:__imp_LocalFree
0x18001248d  mov     rcx, [rsp+68h+hKey]; hKey
0x180012492  call    cs:__imp_RegCloseKey
0x180012498  mov     rsi, [rsp+68h+arg_8]
0x18001249d  mov     rbp, [rsp+68h+arg_0]
0x1800124a2  mov     rcx, r14; hMem
0x1800124a5  call    cs:__imp_LocalFree
0x1800124ab  mov     eax, ebx
0x1800124ad  add     rsp, 40h
0x1800124b1  pop     r15
0x1800124b3  pop     r14
0x1800124b5  pop     r12
0x1800124b7  pop     rdi
0x1800124b8  pop     rbx
0x1800124b9  retn
```
