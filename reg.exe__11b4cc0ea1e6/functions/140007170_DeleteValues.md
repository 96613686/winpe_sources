# DeleteValues

- ea: `0x140007170`
- end: `0x140007524`
- name: `DeleteValues`
- size: `948`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006f9c`

## callees

- `0x140001bb2`
- `0x140002a28`
- `0x140002b70`
- `0x140007170`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000cd48`
- `0x14000da24`
- `0x14000dc24`
- `0x14000e604`
- `0x14000e7a4`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400073bc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400073bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000726c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000726c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400072cd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140007449`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400072cd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140007449`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000749c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000749c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007320`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007320`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400071eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400071eb`

## pseudocode

```c
__int64 __fastcall DeleteValues(__int64 a1)
{
  int v1; // r12d
  __int64 v3; // rcx
  unsigned int v4; // r14d
  __int64 v5; // r8
  __int64 v6; // rdx
  const WCHAR *v7; // rcx
  const WCHAR *ResString2FromModule; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rcx
  FILE *v14; // rax
  const WCHAR *v15; // rdx
  WCHAR *v16; // r13
  int v17; // r15d
  DWORD i; // edi
  WCHAR *v19; // rax
  __int64 j; // rcx
  LSTATUS v21; // eax
  unsigned int v22; // edi
  unsigned int k; // r15d
  __int64 Item; // rax
  const WCHAR *v25; // rdx
  LSTATUS v26; // eax
  DWORD v27; // eax
  HKEY v28; // rcx
  __int64 v29; // rax
  _DWORD *DynamicArray; // [rsp+60h] [rbp-18h]
  LPVOID v32[2]; // [rsp+68h] [rbp-10h] BYREF
  DWORD cchValueName; // [rsp+C0h] [rbp+48h] BYREF
  DWORD cValues; // [rsp+C8h] [rbp+50h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+D0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+60h] BYREF

  v1 = 0;
  cchValueName = 0;
  hKey = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  if ( !a1 )
    goto LABEL_64;
  GetResString2FromModule(a1, 206, 1);
  v4 = 2;
  if ( *(_DWORD *)(a1 + 28) == 1 )
  {
    v5 = 0;
    v6 = 204;
    goto LABEL_8;
  }
  v7 = *(const WCHAR **)(a1 + 96);
  if ( !v7 )
  {
LABEL_64:
    v10 = 87;
    SaveErrorMessage(87);
    v11 = 2;
    goto LABEL_65;
  }
  if ( !lstrlenW(v7) )
    GetResString2FromModule(v3, 501, 0);
  v5 = 2;
  v6 = 205;
LABEL_8:
  ResString2FromModule = (const WCHAR *)GetResString2FromModule(v3, v6, v5);
  do
    v9 = Prompt(ResString2FromModule);
  while ( v9 > 2 );
  if ( v9 == 2 )
  {
    v10 = 1223;
    SaveErrorMessage(1223);
    v11 = 1;
LABEL_65:
    v14 = o___acrt_iob_func_0(v11);
    goto LABEL_66;
  }
  v12 = RegOpenKeyExW(*(HKEY *)(a1 + 8), *(LPCWSTR *)(a1 + 80), 0, *(_DWORD *)(a1 + 140) | 0xF003F, &hKey);
  v10 = v12;
  if ( v12 )
  {
    v13 = v12;
LABEL_18:
    SaveErrorMessage(v13);
    v14 = o___acrt_iob_func_0(2u);
    goto LABEL_66;
  }
  DynamicArray = CreateDynamicArray();
  if ( !DynamicArray )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v10 = 14;
    v13 = 14;
    goto LABEL_18;
  }
  v15 = *(const WCHAR **)(a1 + 96);
  if ( v15 )
  {
    v10 = RegDeleteValueW(hKey, v15);
  }
  else if ( *(_DWORD *)(a1 + 28) == 1 )
  {
    v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v10 )
    {
      if ( cValues )
      {
        ++cbMaxValueNameLen;
        v32[0] = AllocateMemory(2 * cbMaxValueNameLen + 4);
        v16 = (WCHAR *)v32[0];
        v10 = 14;
        if ( v32[0] )
        {
          v17 = 0;
          for ( i = 0; i < cValues; ++i )
          {
            cchValueName = cbMaxValueNameLen;
            v19 = v16;
            for ( j = 2LL * cbMaxValueNameLen; j; --j )
            {
              *(_BYTE *)v19 = 0;
              v19 = (WCHAR *)((char *)v19 + 1);
            }
            v21 = RegEnumValueW(hKey, i, v16, &cchValueName, 0, 0, 0, 0);
            v1 = v21;
            if ( v21 )
            {
              if ( !v17 )
                v17 = v21;
            }
            else if ( (unsigned int)DynArrayAppendString(DynamicArray, v16) == -1 )
            {
              v17 = 14;
              v1 = 14;
              break;
            }
          }
          FreeMemory(v32);
          if ( *DynamicArray == 9 )
            v22 = DynamicArray[1];
          else
            v22 = 0;
          if ( v1 == 14 || !v22 )
          {
            v10 = v17;
          }
          else
          {
            cchValueName = 0;
            v10 = 0;
            for ( k = 0; k < v22; ++k )
            {
              Item = _DynArrayGetItem(DynamicArray, k, 0);
              v25 = 0;
              if ( Item && *(_DWORD *)(Item + 4) == 0x20000 )
                v25 = *(const WCHAR **)(Item + 16);
              v26 = RegDeleteValueW(hKey, v25);
              if ( v26 )
              {
                if ( !v10 )
                  v10 = v26;
                v27 = cchValueName;
              }
              else
              {
                v27 = ++cchValueName;
              }
            }
            v4 = 2;
            if ( v27 )
            {
              if ( v22 == cValues && v27 == v22 )
                v10 = 0;
              else
                v10 = -2147286527;
            }
          }
        }
      }
    }
  }
  v28 = hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v10 )
  {
    if ( v10 == -2147286527 )
    {
      v29 = GetResString2FromModule(v28, 141, 0);
      SetReason(v29);
    }
    else
    {
      SaveErrorMessage(v10);
    }
  }
  else
  {
    SaveErrorMessage(0);
    v4 = 1;
  }
  v14 = o___acrt_iob_func_0(v4);
LABEL_66:
  ShowLastErrorEx(v14);
  return v10;
}

```

## disassembly

```asm
0x140007170  push    rbp
0x140007172  push    rbx
0x140007173  push    rsi
0x140007174  push    rdi
0x140007175  push    r12
0x140007177  push    r13
0x140007179  push    r14
0x14000717b  push    r15
0x14000717d  mov     rbp, rsp
0x140007180  sub     rsp, 78h
0x140007184  xor     r12d, r12d
0x140007187  mov     rdi, rcx
0x14000718a  mov     [rbp+cchValueName], r12d
0x14000718e  mov     [rbp+hKey], r12
0x140007192  mov     [rbp+cValues], r12d
0x140007196  mov     [rbp+cbMaxValueNameLen], r12d
0x14000719a  test    rcx, rcx
0x14000719d  jnz     short loc_1400071B1
0x14000719f  lea     ebx, [rcx+57h]
0x1400071a2  mov     ecx, ebx
0x1400071a4  call    SaveErrorMessage
0x1400071a9  lea     ecx, [rdi+2]
0x1400071ac  jmp     loc_1400074FF
0x1400071b1  mov     edx, 0CEh
0x1400071b6  mov     r8d, 1
0x1400071bc  call    GetResString2FromModule
0x1400071c1  cmp     dword ptr [rdi+1Ch], 1
0x1400071c5  mov     r15, rax
0x1400071c8  mov     r14d, 2
0x1400071ce  jnz     short loc_1400071DE
0x1400071d0  mov     rbx, [rdi+58h]
0x1400071d4  xor     r8d, r8d
0x1400071d7  mov     edx, 0CCh
0x1400071dc  jmp     short loc_140007213
0x1400071de  mov     rcx, [rdi+60h]; lpString
0x1400071e2  test    rcx, rcx
0x1400071e5  jz      loc_1400074F0
0x1400071eb  call    cs:__imp_lstrlenW
0x1400071f1  test    eax, eax
0x1400071f3  jnz     short loc_140007207
0x1400071f5  xor     r8d, r8d
0x1400071f8  mov     edx, 1F5h
0x1400071fd  call    GetResString2FromModule
0x140007202  mov     rbx, rax
0x140007205  jmp     short loc_14000720B
0x140007207  mov     rbx, [rdi+60h]
0x14000720b  mov     r8d, r14d
0x14000720e  mov     edx, 0CDh
0x140007213  call    GetResString2FromModule
0x140007218  mov     rsi, rax
0x14000721b  mov     r9d, [rdi+18h]
0x14000721f  mov     r8, r15
0x140007222  mov     rdx, rbx
0x140007225  mov     rcx, rsi
0x140007228  call    Prompt
0x14000722d  cmp     eax, r14d
0x140007230  jg      short loc_14000721B
0x140007232  jnz     short loc_14000724A
0x140007234  mov     ebx, 4C7h
0x140007239  mov     ecx, ebx
0x14000723b  call    SaveErrorMessage
0x140007240  mov     ecx, 1
0x140007245  jmp     loc_1400074FF
0x14000724a  mov     r9d, [rdi+8Ch]
0x140007251  lea     rax, [rbp+hKey]
0x140007255  mov     rdx, [rdi+50h]; lpSubKey
0x140007259  or      r9d, 0F003Fh; samDesired
0x140007260  mov     rcx, [rdi+8]; hKey
0x140007264  xor     r8d, r8d; ulOptions
0x140007267  mov     [rsp+78h+phkResult], rax; phkResult
0x14000726c  call    cs:__imp_RegOpenKeyExW
0x140007272  mov     ebx, eax
0x140007274  test    eax, eax
0x140007276  jz      short loc_14000727C
0x140007278  mov     ecx, eax
0x14000727a  jmp     short loc_1400072A4
0x14000727c  call    CreateDynamicArray
0x140007281  mov     [rbp+var_18], rax
0x140007285  test    rax, rax
0x140007288  jnz     short loc_1400072BB
0x14000728a  mov     rcx, [rbp+hKey]; hKey
0x14000728e  test    rcx, rcx
0x140007291  jz      short loc_14000729D
0x140007293  call    cs:__imp_RegCloseKey
0x140007299  mov     [rbp+hKey], r12
0x14000729d  mov     ebx, 0Eh
0x1400072a2  mov     ecx, ebx
0x1400072a4  call    SaveErrorMessage
0x1400072a9  mov     ecx, r14d; Ix
0x1400072ac  call    _o___acrt_iob_func_0
0x1400072b1  mov     edx, 20001h
0x1400072b6  jmp     loc_140007509
0x1400072bb  mov     rdx, [rdi+60h]; lpValueName
0x1400072bf  mov     esi, 20000h
0x1400072c4  test    rdx, rdx
0x1400072c7  jz      short loc_1400072DA
0x1400072c9  mov     rcx, [rbp+hKey]; hKey
0x1400072cd  call    cs:__imp_RegDeleteValueW
0x1400072d3  mov     ebx, eax
0x1400072d5  jmp     loc_140007493
0x1400072da  cmp     dword ptr [rdi+1Ch], 1
0x1400072de  jnz     loc_140007493
0x1400072e4  mov     rcx, [rbp+hKey]; hKey
0x1400072e8  lea     rax, [rbp+cbMaxValueNameLen]
0x1400072ec  mov     [rsp+78h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400072f1  xor     r9d, r9d; lpReserved
0x1400072f4  mov     [rsp+78h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1400072f9  xor     r8d, r8d; lpcchClass
0x1400072fc  mov     [rsp+78h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x140007301  xor     edx, edx; lpClass
0x140007303  mov     [rsp+78h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140007308  lea     rax, [rbp+cValues]
0x14000730c  mov     [rsp+78h+lpcValues], rax; lpcValues
0x140007311  mov     [rsp+78h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x140007316  mov     [rsp+78h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x14000731b  mov     [rsp+78h+phkResult], r12; lpcSubKeys
0x140007320  call    cs:__imp_RegQueryInfoKeyW
0x140007326  mov     ebx, eax
0x140007328  test    eax, eax
0x14000732a  jnz     loc_140007493
0x140007330  cmp     [rbp+cValues], r12d
0x140007334  jz      loc_140007493
0x14000733a  mov     ecx, [rbp+cbMaxValueNameLen]
0x14000733d  inc     ecx
0x14000733f  mov     [rbp+cbMaxValueNameLen], ecx
0x140007342  lea     ecx, ds:4[rcx*2]; dwBytes
0x140007349  call    AllocateMemory
0x14000734e  mov     [rbp+var_10], rax
0x140007352  mov     r13, rax
0x140007355  mov     ebx, 0Eh
0x14000735a  test    rax, rax
0x14000735d  jz      loc_140007493
0x140007363  xor     r15d, r15d
0x140007366  mov     edi, r12d
0x140007369  cmp     [rbp+cValues], r12d
0x14000736d  jbe     short loc_1400073E0
0x14000736f  mov     eax, [rbp+cbMaxValueNameLen]
0x140007372  mov     ecx, eax
0x140007374  mov     [rbp+cchValueName], eax
0x140007377  mov     rax, r13
0x14000737a  add     rcx, rcx
0x14000737d  jz      short loc_14000738B
0x14000737f  mov     byte ptr [rax], 0
0x140007382  inc     rax
0x140007385  sub     rcx, 1
0x140007389  jnz     short loc_14000737F
0x14000738b  mov     rcx, [rbp+hKey]; hKey
0x14000738f  lea     r9, [rbp+cchValueName]; lpcchValueName
0x140007393  mov     [rsp+78h+lpcValues], 0; lpcbData
0x14000739c  mov     r8, r13; lpValueName
0x14000739f  mov     [rsp+78h+lpcbMaxClassLen], 0; lpData
0x1400073a8  mov     edx, edi; dwIndex
0x1400073aa  mov     [rsp+78h+lpcbMaxSubKeyLen], 0; lpType
0x1400073b3  mov     [rsp+78h+phkResult], 0; lpReserved
0x1400073bc  call    cs:__imp_RegEnumValueW
0x1400073c2  mov     r12d, eax
0x1400073c5  test    eax, eax
0x1400073c7  jnz     short loc_1400073F7
0x1400073c9  mov     rcx, [rbp+var_18]
0x1400073cd  mov     rdx, r13
0x1400073d0  call    DynArrayAppendString
0x1400073d5  cmp     eax, 0FFFFFFFFh
0x1400073d8  jnz     short loc_1400073FE
0x1400073da  mov     r15d, ebx
0x1400073dd  mov     r12d, ebx
0x1400073e0  lea     rcx, [rbp+var_10]
0x1400073e4  call    FreeMemory
0x1400073e9  mov     rax, [rbp+var_18]
0x1400073ed  cmp     dword ptr [rax], 9
0x1400073f0  jnz     short loc_14000740B
0x1400073f2  mov     edi, [rax+4]
0x1400073f5  jmp     short loc_14000740D
0x1400073f7  test    r15d, r15d
0x1400073fa  cmovz   r15d, eax
0x1400073fe  inc     edi
0x140007400  cmp     edi, [rbp+cValues]
0x140007403  jb      loc_14000736F
0x140007409  jmp     short loc_1400073E0
0x14000740b  xor     edi, edi
0x14000740d  cmp     r12d, ebx
0x140007410  jz      short loc_14000748D
0x140007412  xor     r12d, r12d
0x140007415  test    edi, edi
0x140007417  jz      short loc_140007490
0x140007419  mov     [rbp+cchValueName], r12d
0x14000741d  mov     ebx, r12d
0x140007420  mov     r15d, r12d
0x140007423  mov     r14, rax
0x140007426  xor     r8d, r8d
0x140007429  mov     edx, r15d
0x14000742c  mov     rcx, r14
0x14000742f  call    __DynArrayGetItem
0x140007434  mov     rdx, r12
0x140007437  test    rax, rax
0x14000743a  jz      short loc_140007445
0x14000743c  cmp     [rax+4], esi
0x14000743f  jnz     short loc_140007445
0x140007441  mov     rdx, [rax+10h]; lpValueName
0x140007445  mov     rcx, [rbp+hKey]; hKey
0x140007449  call    cs:__imp_RegDeleteValueW
0x14000744f  test    eax, eax
0x140007451  jz      short loc_14000745E
0x140007453  test    ebx, ebx
0x140007455  jnz     short loc_140007459
0x140007457  mov     ebx, eax
0x140007459  mov     eax, [rbp+cchValueName]
0x14000745c  jmp     short loc_140007466
0x14000745e  mov     eax, [rbp+cchValueName]
0x140007461  inc     eax
0x140007463  mov     [rbp+cchValueName], eax
0x140007466  inc     r15d
0x140007469  cmp     r15d, edi
0x14000746c  jb      short loc_140007426
0x14000746e  mov     r14d, 2
0x140007474  test    eax, eax
0x140007476  jz      short loc_140007493
0x140007478  cmp     edi, [rbp+cValues]
0x14000747b  jnz     short loc_140007486
0x14000747d  cmp     eax, edi
0x14000747f  jnz     short loc_140007486
0x140007481  mov     ebx, r12d
0x140007484  jmp     short loc_140007493
0x140007486  mov     ebx, 80030201h
0x14000748b  jmp     short loc_140007493
0x14000748d  xor     r12d, r12d
0x140007490  mov     ebx, r15d
0x140007493  mov     rcx, [rbp+hKey]; hKey
0x140007497  test    rcx, rcx
0x14000749a  jz      short loc_1400074A6
0x14000749c  call    cs:__imp_RegCloseKey
0x1400074a2  mov     [rbp+hKey], r12
0x1400074a6  test    ebx, ebx
0x1400074a8  jz      short loc_1400074D7
0x1400074aa  cmp     ebx, 80030201h
0x1400074b0  jnz     short loc_1400074C9
0x1400074b2  xor     r8d, r8d
0x1400074b5  mov     edx, 8Dh
0x1400074ba  call    GetResString2FromModule
0x1400074bf  mov     rcx, rax
0x1400074c2  call    SetReason
0x1400074c7  jmp     short loc_1400074D0
0x1400074c9  mov     ecx, ebx
0x1400074cb  call    SaveErrorMessage
0x1400074d0  mov     esi, 20001h
0x1400074d5  jmp     short loc_1400074E4
0x1400074d7  xor     ecx, ecx
0x1400074d9  call    SaveErrorMessage
0x1400074de  mov     r14d, 1
0x1400074e4  mov     ecx, r14d; Ix
0x1400074e7  call    _o___acrt_iob_func_0
0x1400074ec  mov     edx, esi
0x1400074ee  jmp     short loc_140007509
0x1400074f0  mov     ebx, 57h ; 'W'
0x1400074f5  mov     ecx, ebx
0x1400074f7  call    SaveErrorMessage
0x1400074fc  mov     ecx, r14d; Ix
0x1400074ff  call    _o___acrt_iob_func_0
0x140007504  mov     edx, 20000h
0x140007509  mov     rcx, rax
0x14000750c  call    ShowLastErrorEx
0x140007511  mov     eax, ebx
0x140007513  add     rsp, 78h
0x140007517  pop     r15
0x140007519  pop     r14
0x14000751b  pop     r13
0x14000751d  pop     r12
0x14000751f  pop     rdi
0x140007520  pop     rsi
0x140007521  pop     rbx
0x140007522  pop     rbp
0x140007523  retn
```
