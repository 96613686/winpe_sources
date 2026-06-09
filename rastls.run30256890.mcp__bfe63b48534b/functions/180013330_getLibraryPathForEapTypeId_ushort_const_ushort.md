# getLibraryPathForEapTypeId(ushort const *,ushort * *)

- ea: `0x180013330`
- end: `0x18001370b`
- name: `?getLibraryPathForEapTypeId@@YAKPEBGPEAPEAG@Z`
- size: `987`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800633e0`
- `0x1800637fc`

## callees

- `0x180007d00`
- `0x180010140`
- `0x180013330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001369d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001369d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013370`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800135cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001365c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013370`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800135cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001365c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013515`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013515`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800135aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013611`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800135aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013611`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001363f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180013686`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001363f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180013686`

## string_xrefs

- `0x18001357a`: `ConfigUIPath`
- `0x180013602`: `ConfigUIPath`
- `0x1800133de`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`

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
0x180013330  push    rbx
0x180013332  push    rdi
0x180013333  push    r12
0x180013335  push    r14
0x180013337  push    r15
0x180013339  sub     rsp, 40h
0x18001333d  xor     r12d, r12d
0x180013340  mov     r15, rdx
0x180013343  mov     [rsp+68h+hKey], r12
0x180013348  mov     rbx, rcx
0x18001334b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180013352  cmp     [rcx+rax*2+2], r12w
0x180013358  lea     rax, [rax+1]
0x18001335c  jnz     short loc_180013352
0x18001335e  lea     eax, ds:66h[rax*2]
0x180013365  mov     ecx, 40h ; '@'; uFlags
0x18001336a  movsxd  rdi, eax
0x18001336d  mov     rdx, rdi; uBytes
0x180013370  call    cs:__imp_LocalAlloc
0x180013377  nop     dword ptr [rax+rax+00h]
0x18001337c  mov     r14, rax
0x18001337f  test    rax, rax
0x180013382  jnz     short loc_1800133BA
0x180013384  mov     ebx, 0Eh
0x180013389  mov     rcx, cs:WPP_GLOBAL_Control
0x180013390  lea     rax, WPP_GLOBAL_Control
0x180013397  cmp     rcx, rax
0x18001339a  jz      loc_1800136FB
0x1800133a0  mov     rcx, [rcx+10h]
0x1800133a4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800133ab  mov     edx, 0F8h
0x1800133b0  call    WPP_SF_
0x1800133b5  jmp     loc_1800136FB
0x1800133ba  shr     rdi, 1
0x1800133bd  mov     r10d, 7FFFFFFEh
0x1800133c3  jz      loc_18001348C
0x1800133c9  cmp     rdi, 7FFFFFFFh
0x1800133d0  jbe     short loc_1800133DB
0x1800133d2  mov     [rax], r12w
0x1800133d6  jmp     loc_1800134F8
0x1800133db  mov     rcx, r10
0x1800133de  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x1800133e5  mov     rdx, rdi
0x1800133e8  test    rcx, rcx
0x1800133eb  jz      short loc_18001340C
0x1800133ed  movzx   r9d, word ptr [r8]
0x1800133f1  test    r9w, r9w
0x1800133f5  jz      short loc_18001340C
0x1800133f7  mov     [rax], r9w
0x1800133fb  add     r8, 2
0x1800133ff  add     rax, 2
0x180013403  dec     rcx
0x180013406  sub     rdx, 1
0x18001340a  jnz     short loc_1800133E8
0x18001340c  lea     rcx, [rax-2]
0x180013410  test    rdx, rdx
0x180013413  mov     r9, rdi
0x180013416  cmovnz  rcx, rax
0x18001341a  mov     rax, r14
0x18001341d  mov     [rcx], r12w
0x180013421  mov     rcx, rdi
0x180013424  cmp     [rax], r12w
0x180013428  jz      short loc_180013434
0x18001342a  add     rax, 2
0x18001342e  sub     rcx, 1
0x180013432  jnz     short loc_180013424
0x180013434  mov     rdx, r9
0x180013437  sub     rdx, rcx
0x18001343a  test    rcx, rcx
0x18001343d  cmovz   rdx, r12
0x180013441  jz      short loc_18001348C
0x180013443  lea     r8, asc_180087834; "\\"
0x18001344a  mov     rcx, r10
0x18001344d  lea     rax, [r14+rdx*2]
0x180013451  sub     r9, rdx
0x180013454  jz      short loc_180013478
0x180013456  test    rcx, rcx
0x180013459  jz      short loc_180013478
0x18001345b  movzx   edx, word ptr [r8]
0x18001345f  test    dx, dx
0x180013462  jz      short loc_180013478
0x180013464  mov     [rax], dx
0x180013467  add     r8, 2
0x18001346b  add     rax, 2
0x18001346f  dec     rcx
0x180013472  sub     r9, 1
0x180013476  jnz     short loc_180013456
0x180013478  test    r9, r9
0x18001347b  lea     rcx, [rax-2]
0x18001347f  cmovnz  rcx, rax
0x180013483  mov     [rcx], r12w
0x180013487  mov     rcx, rdi
0x18001348a  jmp     short loc_18001349D
0x18001348c  mov     rcx, rdi
0x18001348f  test    rdi, rdi
0x180013492  jz      short loc_1800134F8
0x180013494  cmp     rcx, 7FFFFFFFh
0x18001349b  ja      short loc_1800134F8
0x18001349d  mov     rax, r14
0x1800134a0  cmp     [rax], r12w
0x1800134a4  jz      short loc_1800134B0
0x1800134a6  add     rax, 2
0x1800134aa  sub     rcx, 1
0x1800134ae  jnz     short loc_1800134A0
0x1800134b0  mov     rdx, rdi
0x1800134b3  sub     rdx, rcx
0x1800134b6  test    rcx, rcx
0x1800134b9  cmovz   rdx, r12
0x1800134bd  jz      short loc_1800134F8
0x1800134bf  lea     rax, [r14+rdx*2]
0x1800134c3  sub     rdi, rdx
0x1800134c6  jz      short loc_1800134E9
0x1800134c8  test    r10, r10
0x1800134cb  jz      short loc_1800134E9
0x1800134cd  movzx   ecx, word ptr [rbx]
0x1800134d0  test    cx, cx
0x1800134d3  jz      short loc_1800134E9
0x1800134d5  mov     [rax], cx
0x1800134d8  add     rbx, 2
0x1800134dc  add     rax, 2
0x1800134e0  dec     r10
0x1800134e3  sub     rdi, 1
0x1800134e7  jnz     short loc_1800134C8
0x1800134e9  test    rdi, rdi
0x1800134ec  lea     rcx, [rax-2]
0x1800134f0  cmovnz  rcx, rax
0x1800134f4  mov     [rcx], r12w
0x1800134f8  lea     rax, [rsp+68h+hKey]
0x1800134fd  mov     r9d, 20019h; samDesired
0x180013503  xor     r8d, r8d; ulOptions
0x180013506  mov     [rsp+68h+phkResult], rax; phkResult
0x18001350b  mov     rdx, r14; lpSubKey
0x18001350e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013515  call    cs:__imp_RegOpenKeyExW
0x18001351c  nop     dword ptr [rax+rax+00h]
0x180013521  mov     ebx, eax
0x180013523  test    eax, eax
0x180013525  jz      short loc_18001355B
0x180013527  mov     rcx, cs:WPP_GLOBAL_Control
0x18001352e  lea     rax, WPP_GLOBAL_Control
0x180013535  cmp     rcx, rax
0x180013538  jz      loc_1800136EC
0x18001353e  mov     rcx, [rcx+10h]
0x180013542  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180013549  mov     edx, 0F9h
0x18001354e  mov     r9, r14
0x180013551  call    WPP_SF_S
0x180013556  jmp     loc_1800136EC
0x18001355b  mov     [rsp+68h+arg_0], rbp
0x180013560  lea     rax, [rsp+68h+cbData]
0x180013568  mov     rbp, [rsp+68h+hKey]
0x18001356d  lea     r9, [rsp+68h+Type]; lpType
0x180013575  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001357a  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180013581  mov     rcx, rbp; hKey
0x180013584  mov     [rsp+68h+arg_8], rsi
0x180013589  xor     r8d, r8d; lpReserved
0x18001358c  mov     [rsp+68h+Type], r12d
0x180013594  mov     [rsp+68h+cbData], r12d
0x18001359c  mov     rsi, r12
0x18001359f  mov     rdi, r12
0x1800135a2  mov     [r15], r12
0x1800135a5  mov     [rsp+68h+phkResult], r12; lpData
0x1800135aa  call    cs:__imp_RegQueryValueExW
0x1800135b1  nop     dword ptr [rax+rax+00h]
0x1800135b6  mov     ebx, eax
0x1800135b8  test    eax, eax
0x1800135ba  jnz     loc_1800136B3
0x1800135c0  mov     edx, [rsp+68h+cbData]; uBytes
0x1800135c7  mov     ecx, 40h ; '@'; uFlags
0x1800135cc  call    cs:__imp_LocalAlloc
0x1800135d3  nop     dword ptr [rax+rax+00h]
0x1800135d8  mov     rsi, rax
0x1800135db  test    rax, rax
0x1800135de  jnz     short loc_1800135EA
0x1800135e0  mov     ebx, 0Eh
0x1800135e5  jmp     loc_1800136B3
0x1800135ea  lea     rax, [rsp+68h+cbData]
0x1800135f2  xor     r8d, r8d; lpReserved
0x1800135f5  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800135fa  lea     r9, [rsp+68h+Type]; lpType
0x180013602  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180013609  mov     [rsp+68h+phkResult], rsi; lpData
0x18001360e  mov     rcx, rbp; hKey
0x180013611  call    cs:__imp_RegQueryValueExW
0x180013618  nop     dword ptr [rax+rax+00h]
0x18001361d  mov     ebx, eax
0x18001361f  test    eax, eax
0x180013621  jnz     loc_1800136B3
0x180013627  mov     edx, [rsp+68h+cbData]
0x18001362e  xor     r8d, r8d; nSize
0x180013631  shr     rdx, 1
0x180013634  mov     rcx, rsi; lpSrc
0x180013637  mov     [rsi+rdx*2-2], r12w
0x18001363d  xor     edx, edx; lpDst
0x18001363f  call    cs:__imp_ExpandEnvironmentStringsW
0x180013646  nop     dword ptr [rax+rax+00h]
0x18001364b  mov     edx, eax
0x18001364d  mov     ecx, 40h ; '@'; uFlags
0x180013652  mov     [rsp+68h+cbData], edx
0x180013659  add     rdx, rdx; uBytes
0x18001365c  call    cs:__imp_LocalAlloc
0x180013663  nop     dword ptr [rax+rax+00h]
0x180013668  mov     rdi, rax
0x18001366b  test    rax, rax
0x18001366e  jz      loc_1800135E0
0x180013674  mov     [rax], r12w
0x180013678  mov     rdx, rax; lpDst
0x18001367b  mov     r8d, [rsp+68h+cbData]; nSize
0x180013683  mov     rcx, rsi; lpSrc
0x180013686  call    cs:__imp_ExpandEnvironmentStringsW
0x18001368d  nop     dword ptr [rax+rax+00h]
0x180013692  mov     [rsp+68h+cbData], eax
0x180013699  test    eax, eax
0x18001369b  jnz     short loc_1800136AD
0x18001369d  call    cs:__imp_GetLastError
0x1800136a4  nop     dword ptr [rax+rax+00h]
0x1800136a9  mov     ebx, eax
0x1800136ab  jmp     short loc_1800136B3
0x1800136ad  mov     [r15], rdi
0x1800136b0  mov     rdi, r12
0x1800136b3  mov     rcx, rsi; hMem
0x1800136b6  call    cs:__imp_LocalFree
0x1800136bd  nop     dword ptr [rax+rax+00h]
0x1800136c2  mov     rcx, rdi; hMem
0x1800136c5  call    cs:__imp_LocalFree
0x1800136cc  nop     dword ptr [rax+rax+00h]
0x1800136d1  mov     rcx, [rsp+68h+hKey]; hKey
0x1800136d6  call    cs:__imp_RegCloseKey
0x1800136dd  nop     dword ptr [rax+rax+00h]
0x1800136e2  mov     rsi, [rsp+68h+arg_8]
0x1800136e7  mov     rbp, [rsp+68h+arg_0]
0x1800136ec  mov     rcx, r14; hMem
0x1800136ef  call    cs:__imp_LocalFree
0x1800136f6  nop     dword ptr [rax+rax+00h]
0x1800136fb  mov     eax, ebx
0x1800136fd  add     rsp, 40h
0x180013701  pop     r15
0x180013703  pop     r14
0x180013705  pop     r12
0x180013707  pop     rdi
0x180013708  pop     rbx
0x180013709  retn
```
