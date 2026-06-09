# I_RpcGetPortAllocationData

- ea: `0x1800b20c0`
- end: `0x1800b2663`
- name: `I_RpcGetPortAllocationData`
- size: `1443`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18005ceb0`
- `0x1800a6a40`
- `0x1800b20c0`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!wcschr` at `0x1800b24ec`
- `ntdll!wcschr` at `0x1800b24ec`
- `ntdll!wcstol` at `0x1800b23a2`
- `ntdll!wcstol` at `0x1800b23d8`
- `ntdll!wcstol` at `0x1800b23a2`
- `ntdll!wcstol` at `0x1800b23d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2128`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2640`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2640`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2170`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b21e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2310`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2170`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b21e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2310`

## pseudocode

```c
void __fastcall I_RpcGetPortAllocationData(__int64 a1)
{
  _WORD *v1; // r12
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int16 v8; // cx
  const wchar_t *v9; // r13
  unsigned __int64 v10; // rsi
  DWORD *p_pcbData; // rdi
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  DWORD *v17; // rax
  HKEY v18; // rcx
  LSTATUS ValueW; // r14d
  _WORD *v20; // rsi
  _WORD *v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // eax
  int v24; // eax
  __int16 v25; // r12
  _WORD *v26; // rax
  _QWORD *v27; // rcx
  _WORD *v28; // r12
  int v29; // r11d
  unsigned __int16 *v30; // r8
  unsigned int v31; // r9d
  unsigned __int16 v32; // r10
  unsigned __int16 v33; // ax
  _QWORD *v34; // r13
  unsigned int v35; // edi
  _WORD *v36; // rax
  __int16 v37; // cx
  int v38; // edi
  _WORD *v39; // rax
  _QWORD *v40; // rcx
  _QWORD *v41; // rcx
  __int64 v42; // [rsp+0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp+0h] BYREF
  int pvData; // [rsp+44h] [rbp+4h] BYREF
  _QWORD *v45; // [rsp+48h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp+10h] BYREF
  wchar_t *EndPtr; // [rsp+58h] [rbp+18h] BYREF

  v1 = 0;
  *(_DWORD *)(a1 + 8) = 3;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  hkey = 0;
  pcbData = 0;
  pvData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc\\Internet", 0, 0x20019u, &hkey) )
  {
    *(_DWORD *)a1 = 1;
    return;
  }
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"UseInternetPorts", 2u, 0, &pvData, &pcbData) )
    goto LABEL_109;
  v3 = 0x80100000001LL;
  if ( (_WORD)pvData == 89 )
    goto LABEL_8;
  if ( (unsigned __int16)(pvData - 78) > 0x2Bu || !_bittest64(&v3, (unsigned __int16)(pvData - 78)) )
    goto LABEL_109;
  v4 = 2;
  if ( (_WORD)pvData == 121 )
LABEL_8:
    v4 = 1;
  *(_DWORD *)(a1 + 8) = v4;
  pcbData = 4;
  if ( !RegGetValueW(hkey, 0, L"PortsInternetAvailable", 2u, 0, &pvData, &pcbData) )
  {
    v8 = pvData;
    if ( (_WORD)pvData == 89 )
    {
LABEL_14:
      pvData = 1;
LABEL_15:
      pcbData = 1;
      v9 = 0;
      while ( 1 )
      {
        if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        v10 = pcbData;
        p_pcbData = 0;
        if ( !pcbData )
          goto LABEL_113;
        if ( pcbData > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_113;
        v12 = pcbData + g_ulAdditionalProbeSize + 8;
        if ( v12 < pcbData || !(unsigned int)VerifyStackAvailable(v12, v5, v6, v7) )
          goto LABEL_113;
        v13 = v10 + 23;
        if ( v10 + 23 <= v10 + 8 )
          v13 = 0xFFFFFFFFFFFFFF0LL;
        v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
        v15 = alloca(v14);
        v16 = alloca(v14);
        p_pcbData = &pcbData;
        if ( &v42 == (__int64 *)-64LL || (pcbData = 1801679955, (p_pcbData = (DWORD *)&v45) == 0) )
        {
LABEL_113:
          if ( v10 + 8 >= v10 )
          {
            v17 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
            p_pcbData = v17;
            if ( v17 )
            {
              *v17 = 1885431112;
              p_pcbData = v17 + 2;
            }
          }
        }
        v18 = hkey;
        if ( !p_pcbData )
          goto LABEL_110;
        v9 = (const wchar_t *)p_pcbData;
        ValueW = RegGetValueW(hkey, 0, L"Ports", 0x20u, 0, p_pcbData, &pcbData);
        if ( ValueW != 234 )
        {
          RegCloseKey(hkey);
          if ( ValueW )
          {
            if ( *(p_pcbData - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
          }
          else
          {
            v20 = 0;
            v21 = (_WORD *)(pcbData >> 1);
            v22 = 87;
            if ( (unsigned int)v21 < 2
              || *((_WORD *)p_pcbData + (unsigned int)((_DWORD)v21 - 1))
              || *((_WORD *)p_pcbData + (unsigned int)((_DWORD)v21 - 2)) )
            {
              ValueW = 87;
            }
            else
            {
              while ( *v9 )
              {
                EndPtr = 0;
                v23 = wcstol(v9, &EndPtr, 10);
                LODWORD(v45) = v23;
                if ( v23 > 0xFFFF )
                  goto LABEL_78;
                if ( *EndPtr )
                {
                  if ( *EndPtr != 45 )
                  {
LABEL_78:
                    ValueW = 87;
                    break;
                  }
                  v24 = wcstol(EndPtr + 1, &EndPtr, 10);
                  v25 = v24;
                  if ( (unsigned int)v24 > 0xFFFF || v24 < (int)v45 )
                  {
                    v1 = 0;
                    ValueW = 87;
                    break;
                  }
                }
                else
                {
                  v25 = v23;
                }
                v26 = AllocWrapper(0x10u);
                v21 = v26;
                if ( !v26 )
                {
                  ValueW = 14;
                  v1 = 0;
                  break;
                }
                *(_QWORD *)v26 = 0;
                v26[5] = (_WORD)v45;
                v26[4] = v25;
LABEL_49:
                v27 = 0;
                v28 = v20;
                v45 = 0;
                while ( 1 )
                {
                  if ( !v20 )
                  {
                    v20 = v21;
                    goto LABEL_70;
                  }
                  v29 = (unsigned __int16)v28[4];
                  v30 = v28 + 5;
                  v31 = (unsigned __int16)v21[5];
                  if ( v31 <= v29 + 1 )
                  {
                    v32 = *v30;
                    if ( (unsigned __int16)v21[4] >= *v30 - 1 )
                    {
                      if ( (unsigned __int16)v31 < v32 )
                        v32 = v21[5];
                      *v30 = v32;
                      v33 = v21[4];
                      if ( (unsigned __int16)v29 > v33 )
                        v33 = v29;
                      v28[4] = v33;
                      FreeWrapper(v21);
                      v21 = v28;
                      if ( v45 )
                        *v45 = *(_QWORD *)v28;
                      if ( v20 == v28 )
                        v20 = *(_WORD **)v20;
                      goto LABEL_49;
                    }
                    v27 = v45;
                  }
                  if ( (unsigned __int16)v31 < *v30 )
                    break;
                  v27 = v28;
                  v28 = *(_WORD **)v28;
                  v45 = v27;
                  if ( !v28 )
                  {
                    *v27 = v21;
                    goto LABEL_70;
                  }
                }
                if ( v27 )
                  *v27 = v21;
                else
                  v20 = v21;
                *(_QWORD *)v21 = v28;
LABEL_70:
                v1 = 0;
                v9 = wcschr(v9, 0) + 1;
              }
            }
            if ( *(p_pcbData - 2) == 1885431112 )
              ((void (__fastcall *)(DWORD *, _WORD *, __int64))g_pfnFree)(p_pcbData - 2, v21, v22);
            if ( !v20 )
              ValueW = 87;
            if ( pvData == 1 )
              *(_QWORD *)(a1 + 16) = v20;
            else
              *(_QWORD *)(a1 + 24) = v20;
            if ( ValueW )
              goto LABEL_114;
            v34 = 0;
            v35 = 1025;
            while ( v20 )
            {
              LODWORD(v45) = (unsigned __int16)v20[5];
              if ( v35 < (unsigned int)v45 )
              {
                v36 = AllocWrapper(0x10u);
                if ( !v36 )
                  goto LABEL_97;
                v37 = (_WORD)v45 - 1;
                *(_QWORD *)v36 = 0;
                v36[5] = v35;
                v36[4] = v37;
                if ( v1 )
                  *v34 = v36;
                else
                  v1 = v36;
                v34 = v36;
              }
              v38 = (unsigned __int16)v20[4];
              v20 = *(_WORD **)v20;
              v35 = v38 + 1;
              if ( v35 < 0x401 )
                v35 = 1025;
            }
            if ( v35 >= 0xFFFF )
              goto LABEL_98;
            v39 = AllocWrapper(0x10u);
            if ( !v39 )
            {
LABEL_97:
              ValueW = 14;
              goto LABEL_98;
            }
            v39[5] = v35;
            v39[4] = -1;
            *(_QWORD *)v39 = 0;
            if ( v34 )
              *v34 = v39;
            else
              v1 = v39;
LABEL_98:
            if ( pvData == 1 )
              *(_QWORD *)(a1 + 24) = v1;
            else
              *(_QWORD *)(a1 + 16) = v1;
            if ( ValueW )
            {
LABEL_114:
              while ( 1 )
              {
                v40 = *(_QWORD **)(a1 + 16);
                if ( !v40 )
                  break;
                *(_QWORD *)(a1 + 16) = *v40;
                FreeWrapper(v40);
              }
              while ( 1 )
              {
                v41 = *(_QWORD **)(a1 + 24);
                if ( !v41 )
                  break;
                *(_QWORD *)(a1 + 24) = *v41;
                FreeWrapper(v41);
              }
            }
            else
            {
              *(_DWORD *)a1 = 1;
              *(_DWORD *)(a1 + 4) = 1;
            }
          }
          return;
        }
      }
    }
    if ( (unsigned __int16)(pvData - 78) <= 0x2Bu && _bittest64(&v3, (unsigned __int16)(pvData - 78)) )
    {
      pvData = 2;
      if ( v8 != 121 )
        goto LABEL_15;
      goto LABEL_14;
    }
  }
LABEL_109:
  v18 = hkey;
LABEL_110:
  RegCloseKey(v18);
}

```

## disassembly

```asm
0x1800b20c0  push    rbp
0x1800b20c2  push    rbx
0x1800b20c3  push    rsi
0x1800b20c4  push    rdi
0x1800b20c5  push    r12
0x1800b20c7  push    r13
0x1800b20c9  push    r14
0x1800b20cb  push    r15
0x1800b20cd  sub     rsp, 78h
0x1800b20d1  lea     rbp, [rsp+40h]
0x1800b20d6  mov     rax, cs:__security_cookie
0x1800b20dd  xor     rax, rbp
0x1800b20e0  mov     [rbp+70h+var_50], rax
0x1800b20e4  xor     r12d, r12d
0x1800b20e7  mov     dword ptr [rcx+8], 3
0x1800b20ee  mov     [rcx], r12
0x1800b20f1  lea     rax, [rbp+70h+hkey]
0x1800b20f5  mov     [rcx+10h], r12
0x1800b20f9  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Rpc\\Internet"
0x1800b2100  mov     [rcx+18h], r12
0x1800b2104  mov     rbx, rcx
0x1800b2107  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b210e  mov     [rbp+70h+hkey], r12
0x1800b2112  mov     r9d, 20019h; samDesired
0x1800b2118  mov     [rbp+70h+var_70], r12d
0x1800b211c  xor     r8d, r8d; ulOptions
0x1800b211f  mov     [rbp+70h+var_6C], r12d
0x1800b2123  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800b2128  call    cs:__imp_RegOpenKeyExW
0x1800b212e  test    eax, eax
0x1800b2130  jz      short loc_1800B213D
0x1800b2132  mov     dword ptr [rbx], 1
0x1800b2138  jmp     loc_1800B2646
0x1800b213d  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b2141  lea     rax, [rbp+70h+var_70]
0x1800b2145  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b214a  lea     r8, aUseinternetpor; "UseInternetPorts"
0x1800b2151  mov     esi, 4
0x1800b2156  lea     rax, [rbp+70h+var_6C]
0x1800b215a  mov     [rsp+0B0h+pvData], rax; pvData
0x1800b215f  xor     edx, edx; lpSubKey
0x1800b2161  mov     [rbp+70h+var_70], esi
0x1800b2164  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b2169  lea     r14d, [rsi-2]
0x1800b216d  mov     r9d, r14d; dwFlags
0x1800b2170  call    cs:__imp_RegGetValueW
0x1800b2176  test    eax, eax
0x1800b2178  jnz     loc_1800B263C
0x1800b217e  mov     ecx, [rbp+70h+var_6C]
0x1800b2181  lea     r15d, [rsi-3]
0x1800b2185  mov     rdi, 80100000001h
0x1800b218f  cmp     cx, 59h ; 'Y'
0x1800b2193  jz      short loc_1800B21B8
0x1800b2195  lea     eax, [rcx-4Eh]
0x1800b2198  cmp     ax, 2Bh ; '+'
0x1800b219c  ja      loc_1800B263C
0x1800b21a2  movzx   eax, ax
0x1800b21a5  bt      rdi, rax
0x1800b21a9  jnb     loc_1800B263C
0x1800b21af  mov     eax, r14d
0x1800b21b2  cmp     cx, 79h ; 'y'
0x1800b21b6  jnz     short loc_1800B21BB
0x1800b21b8  mov     eax, r15d
0x1800b21bb  mov     [rbx+8], eax
0x1800b21be  lea     r8, aPortsinterneta; "PortsInternetAvailable"
0x1800b21c5  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b21c9  lea     rax, [rbp+70h+var_70]
0x1800b21cd  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b21d2  mov     r9d, r14d; dwFlags
0x1800b21d5  lea     rax, [rbp+70h+var_6C]
0x1800b21d9  mov     [rbp+70h+var_70], esi
0x1800b21dc  mov     [rsp+0B0h+pvData], rax; pvData
0x1800b21e1  xor     edx, edx; lpSubKey
0x1800b21e3  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b21e8  call    cs:__imp_RegGetValueW
0x1800b21ee  test    eax, eax
0x1800b21f0  jnz     loc_1800B263C
0x1800b21f6  mov     ecx, [rbp+70h+var_6C]
0x1800b21f9  cmp     cx, 59h ; 'Y'
0x1800b21fd  jz      short loc_1800B2223
0x1800b21ff  lea     eax, [rcx-4Eh]
0x1800b2202  cmp     ax, 2Bh ; '+'
0x1800b2206  ja      loc_1800B263C
0x1800b220c  movzx   eax, ax
0x1800b220f  bt      rdi, rax
0x1800b2213  jnb     loc_1800B263C
0x1800b2219  mov     [rbp+70h+var_6C], r14d
0x1800b221d  cmp     cx, 79h ; 'y'
0x1800b2221  jnz     short loc_1800B2227
0x1800b2223  mov     [rbp+70h+var_6C], r15d
0x1800b2227  mov     [rbp+70h+var_70], r15d
0x1800b222b  mov     r13, r12
0x1800b222e  test    r13, r13
0x1800b2231  jz      short loc_1800B224B
0x1800b2233  lea     rcx, [r13-8]
0x1800b2237  cmp     dword ptr [rcx], 70616548h
0x1800b223d  jnz     short loc_1800B224B
0x1800b223f  mov     rax, cs:g_pfnFree
0x1800b2246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b224b  mov     esi, [rbp+70h+var_70]
0x1800b224e  mov     rdi, r12
0x1800b2251  test    rsi, rsi
0x1800b2254  jz      short loc_1800B22B7
0x1800b2256  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800b225d  ja      short loc_1800B22B7
0x1800b225f  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b2266  add     rcx, 8
0x1800b226a  add     rcx, rsi
0x1800b226d  cmp     rcx, rsi
0x1800b2270  jb      short loc_1800B22B7
0x1800b2272  call    VerifyStackAvailable
0x1800b2277  test    eax, eax
0x1800b2279  jz      short loc_1800B22B7
0x1800b227b  lea     rax, [rsi+8]
0x1800b227f  lea     rcx, [rax+0Fh]
0x1800b2283  cmp     rcx, rax
0x1800b2286  ja      short loc_1800B2292
0x1800b2288  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b2292  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b2296  mov     rax, rcx
0x1800b2299  call    __chkstk_0
0x1800b229e  sub     rsp, rcx
0x1800b22a1  lea     rdi, [rsp+0B0h+var_70]
0x1800b22a6  test    rdi, rdi
0x1800b22a9  jz      short loc_1800B22B7
0x1800b22ab  mov     dword ptr [rdi], 6B637453h
0x1800b22b1  add     rdi, 8
0x1800b22b5  jnz     short loc_1800B22DE
0x1800b22b7  lea     rcx, [rsi+8]
0x1800b22bb  cmp     rcx, rsi
0x1800b22be  jb      short loc_1800B22DE
0x1800b22c0  mov     rax, cs:g_pfnAllocate
0x1800b22c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b22cc  mov     rdi, rax
0x1800b22cf  test    rax, rax
0x1800b22d2  jz      short loc_1800B22DE
0x1800b22d4  mov     dword ptr [rax], 70616548h
0x1800b22da  add     rdi, 8
0x1800b22de  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b22e2  test    rdi, rdi
0x1800b22e5  jz      loc_1800B2640
0x1800b22eb  lea     rax, [rbp+70h+var_70]
0x1800b22ef  mov     r9d, 20h ; ' '; dwFlags
0x1800b22f5  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b22fa  lea     r8, aPorts; "Ports"
0x1800b2301  mov     [rsp+0B0h+pvData], rdi; pvData
0x1800b2306  xor     edx, edx; lpSubKey
0x1800b2308  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b230d  mov     r13, rdi
0x1800b2310  call    cs:__imp_RegGetValueW
0x1800b2316  mov     r14d, eax
0x1800b2319  cmp     eax, 0EAh
0x1800b231e  jz      loc_1800B222E
0x1800b2324  mov     rcx, [rbp+70h+hkey]; hKey
0x1800b2328  call    cs:__imp_RegCloseKey
0x1800b232e  test    r14d, r14d
0x1800b2331  jz      short loc_1800B2354
0x1800b2333  lea     rcx, [rdi-8]
0x1800b2337  cmp     dword ptr [rcx], 70616548h
0x1800b233d  jnz     loc_1800B2646
0x1800b2343  mov     rax, cs:g_pfnFree
0x1800b234a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b234f  jmp     loc_1800B2646
0x1800b2354  mov     edx, [rbp+70h+var_70]
0x1800b2357  mov     rsi, r12
0x1800b235a  shr     edx, 1
0x1800b235c  mov     r8d, 57h ; 'W'
0x1800b2362  cmp     edx, 2
0x1800b2365  jnb     short loc_1800B2372
0x1800b2367  mov     r14d, r8d
0x1800b236a  mov     r13d, r8d
0x1800b236d  jmp     loc_1800B250D
0x1800b2372  lea     eax, [rdx-1]
0x1800b2375  cmp     [rdi+rax*2], r12w
0x1800b237a  jnz     short loc_1800B2367
0x1800b237c  lea     eax, [rdx-2]
0x1800b237f  cmp     [rdi+rax*2], r12w
0x1800b2384  jnz     short loc_1800B2367
0x1800b2386  cmp     [r13+0], r12w
0x1800b238b  jz      loc_1800B2507
0x1800b2391  mov     r8d, 0Ah; Radix
0x1800b2397  mov     [rbp+70h+EndPtr], r12
0x1800b239b  lea     rdx, [rbp+70h+EndPtr]; EndPtr
0x1800b239f  mov     rcx, r13; String
0x1800b23a2  call    cs:__imp_wcstol
0x1800b23a8  mov     dword ptr [rbp+70h+var_68], eax
0x1800b23ab  cmp     eax, 0FFFFh
0x1800b23b0  ja      loc_1800B2538
0x1800b23b6  mov     rcx, [rbp+70h+EndPtr]
0x1800b23ba  cmp     [rcx], r12w
0x1800b23be  jz      short loc_1800B23FE
0x1800b23c0  cmp     word ptr [rcx], 2Dh ; '-'
0x1800b23c4  jnz     loc_1800B2538
0x1800b23ca  add     rcx, 2; String
0x1800b23ce  lea     rdx, [rbp+70h+EndPtr]; EndPtr
0x1800b23d2  mov     r8d, 0Ah; Radix
0x1800b23d8  call    cs:__imp_wcstol
0x1800b23de  mov     r12d, eax
0x1800b23e1  cmp     eax, 0FFFFh
0x1800b23e6  ja      short loc_1800B23ED
0x1800b23e8  cmp     eax, dword ptr [rbp+70h+var_68]
0x1800b23eb  jge     short loc_1800B2401
0x1800b23ed  mov     r13d, 57h ; 'W'
0x1800b23f3  xor     r12d, r12d
0x1800b23f6  mov     r14d, r13d
0x1800b23f9  jmp     loc_1800B250D
0x1800b23fe  mov     r12d, eax
0x1800b2401  mov     ecx, 10h; dwBytes
0x1800b2406  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b240b  mov     rdx, rax
0x1800b240e  test    rax, rax
0x1800b2411  jz      loc_1800B24FE
0x1800b2417  mov     qword ptr [rax], 0
0x1800b241e  mov     eax, dword ptr [rbp+70h+var_68]
0x1800b2421  mov     [rdx+0Ah], ax
0x1800b2425  mov     [rdx+8], r12w
0x1800b242a  xor     ecx, ecx
0x1800b242c  mov     r12, rsi
0x1800b242f  mov     [rbp+70h+var_68], rcx
0x1800b2433  test    rsi, rsi
0x1800b2436  jz      loc_1800B24E4
0x1800b243c  movzx   r11d, word ptr [r12+8]
0x1800b2442  lea     r8, [r12+0Ah]
0x1800b2447  movzx   r9d, word ptr [rdx+0Ah]
0x1800b244c  lea     eax, [r15+r11]
0x1800b2450  cmp     r9d, eax
0x1800b2453  ja      short loc_1800B24B3
0x1800b2455  movzx   r10d, word ptr [r8]
0x1800b2459  movzx   eax, word ptr [rdx+8]
0x1800b245d  mov     ecx, r10d
0x1800b2460  sub     ecx, r15d
0x1800b2463  cmp     eax, ecx
0x1800b2465  jl      short loc_1800B24AF
0x1800b2467  cmp     r9w, r10w
0x1800b246b  mov     rcx, rdx; lpMem
0x1800b246e  cmovb   r10w, r9w
0x1800b2473  mov     [r8], r10w
0x1800b2477  movzx   eax, word ptr [rdx+8]
0x1800b247b  cmp     r11w, ax
0x1800b247f  cmova   ax, r11w
0x1800b2484  mov     [r12+8], ax
0x1800b248a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b248f  mov     rcx, [rbp+70h+var_68]
0x1800b2493  mov     rdx, r12
0x1800b2496  test    rcx, rcx
0x1800b2499  jz      short loc_1800B24A2
0x1800b249b  mov     rax, [r12]
0x1800b249f  mov     [rcx], rax
0x1800b24a2  cmp     rsi, r12
0x1800b24a5  jnz     short loc_1800B242A
0x1800b24a7  mov     rsi, [rsi]
0x1800b24aa  jmp     loc_1800B242A
0x1800b24af  mov     rcx, [rbp+70h+var_68]
0x1800b24b3  cmp     r9w, [r8]
0x1800b24b7  jb      short loc_1800B24D2
0x1800b24b9  mov     rcx, r12
0x1800b24bc  mov     r12, [r12]
0x1800b24c0  mov     [rbp+70h+var_68], rcx
0x1800b24c4  test    r12, r12
0x1800b24c7  jnz     loc_1800B2433
0x1800b24cd  mov     [rcx], rdx
0x1800b24d0  jmp     short loc_1800B24E7
0x1800b24d2  test    rcx, rcx
0x1800b24d5  jz      short loc_1800B24DC
0x1800b24d7  mov     [rcx], rdx
0x1800b24da  jmp     short loc_1800B24DF
0x1800b24dc  mov     rsi, rdx
0x1800b24df  mov     [rdx], r12
0x1800b24e2  jmp     short loc_1800B24E7
0x1800b24e4  mov     rsi, rdx
0x1800b24e7  xor     edx, edx; Ch
0x1800b24e9  mov     rcx, r13; Str
0x1800b24ec  call    cs:__imp_wcschr
0x1800b24f2  xor     r12d, r12d
0x1800b24f5  lea     r13, [rax+2]
0x1800b24f9  jmp     loc_1800B2386
0x1800b24fe  mov     r14d, 0Eh
0x1800b2504  xor     r12d, r12d
0x1800b2507  mov     r13d, 57h ; 'W'
0x1800b250d  lea     rcx, [rdi-8]
0x1800b2511  cmp     dword ptr [rcx], 70616548h
0x1800b2517  jnz     short loc_1800B2525
0x1800b2519  mov     rax, cs:g_pfnFree
0x1800b2520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2525  test    rsi, rsi
0x1800b2528  cmovz   r14d, r13d
0x1800b252c  cmp     [rbp+70h+var_6C], r15d
0x1800b2530  jnz     short loc_1800B2543
0x1800b2532  mov     [rbx+10h], rsi
0x1800b2536  jmp     short loc_1800B2547
0x1800b2538  mov     r13d, 57h ; 'W'
0x1800b253e  mov     r14d, r13d
0x1800b2541  jmp     short loc_1800B250D
0x1800b2543  mov     [rbx+18h], rsi
0x1800b2547  test    r14d, r14d
0x1800b254a  jnz     loc_1800B261A
0x1800b2550  xor     r13d, r13d
0x1800b2553  mov     edi, 401h
0x1800b2558  test    rsi, rsi
0x1800b255b  jz      short loc_1800B25B3
  ... truncated ...
```
