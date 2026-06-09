# CompareEnumerateValueName

- ea: `0x140008320`
- end: `0x140008782`
- name: `CompareEnumerateValueName`
- size: `1122`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, HKEY, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007be0`

## callees

- `0x140002b70`
- `0x140008320`
- `0x140008b4c`
- `0x140008f10`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000e604`
- `0x14000e634`
- `0x14000e7a4`
- `0x14000e928`
- `0x14000eae0`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140008527`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400085a1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140008527`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400085a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400083e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008433`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400083e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008433`

## pseudocode

```c
__int64 __fastcall CompareEnumerateValueName(HKEY hKey, __int64 a2, HKEY a3, __int64 a4, unsigned int a5, _DWORD *a6)
{
  DWORD v6; // r14d
  _DWORD *v8; // r15
  unsigned int v10; // ebx
  DWORD v11; // edx
  DWORD v12; // ecx
  __int64 v13; // r12
  __int64 v14; // r13
  WCHAR *v15; // rsi
  unsigned int v16; // edi
  WCHAR *v17; // rax
  __int64 i; // rcx
  DWORD v19; // r14d
  WCHAR *v20; // rax
  __int64 j; // rcx
  DWORD v22; // ecx
  DWORD v23; // r14d
  __int64 Item; // rax
  __int64 v25; // rdx
  const WCHAR *v26; // rbx
  unsigned int v27; // esi
  DWORD v28; // eax
  DWORD v29; // ebx
  DWORD k; // ebx
  DWORD cValues; // [rsp+68h] [rbp-29h] BYREF
  DWORD lpcValues; // [rsp+6Ch] [rbp-25h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp-21h] BYREF
  DWORD lpcbMaxValueNameLen; // [rsp+74h] [rbp-1Dh] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-19h] BYREF
  __int64 DynamicArray; // [rsp+80h] [rbp-11h] BYREF
  __int64 v37; // [rsp+88h] [rbp-9h] BYREF
  __int64 v38[9]; // [rsp+90h] [rbp-1h] BYREF

  v6 = 0;
  cchValueName = 0;
  cValues = 0;
  lpcValues = 0;
  cbMaxValueNameLen = 0;
  lpcbMaxValueNameLen = 0;
  if ( !hKey || !a2 || !a3 || !a4 || (v8 = a6) == 0 )
  {
    v10 = 87;
    goto LABEL_68;
  }
  if ( a5 <= 1 && *a6 == 1 )
    return 0;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v10 )
    goto LABEL_68;
  v10 = RegQueryInfoKeyW(a3, 0, 0, 0, 0, 0, 0, &lpcValues, &lpcbMaxValueNameLen, 0, 0, 0);
  if ( v10 )
    goto LABEL_68;
  if ( a5 <= 1 && (cValues != lpcValues || cbMaxValueNameLen != lpcbMaxValueNameLen) )
  {
    *a6 = 1;
    return 0;
  }
  v11 = lpcbMaxValueNameLen + 1;
  v12 = cbMaxValueNameLen + 1;
  lpcbMaxValueNameLen = v11;
  cbMaxValueNameLen = v12;
  if ( v11 <= v12 )
    lpcbMaxValueNameLen = v12;
  else
    cbMaxValueNameLen = v11;
  DynamicArray = CreateDynamicArray();
  v13 = DynamicArray;
  if ( !DynamicArray )
  {
LABEL_19:
    v10 = 14;
LABEL_68:
    SaveErrorMessage(v10);
    return v10;
  }
  v37 = CreateDynamicArray();
  v14 = v37;
  if ( !v37 )
  {
LABEL_21:
    DestroyDynamicArray(&DynamicArray);
    goto LABEL_19;
  }
  v38[0] = AllocateMemory(2 * cbMaxValueNameLen);
  v15 = (WCHAR *)v38[0];
  if ( !v38[0] )
  {
    DestroyDynamicArray(&v37);
    goto LABEL_21;
  }
  v16 = 0;
  if ( cValues )
  {
    do
    {
      if ( v16 )
        break;
      cchValueName = cbMaxValueNameLen;
      v17 = v15;
      for ( i = 2LL * cbMaxValueNameLen; i; --i )
      {
        *(_BYTE *)v17 = 0;
        v17 = (WCHAR *)((char *)v17 + 1);
      }
      v16 = RegEnumValueW(hKey, v6, v15, &cchValueName, 0, 0, 0, 0);
      if ( !v16 && (unsigned int)DynArrayAppendString(v13, v15) == -1 )
        v16 = 14;
      ++v6;
    }
    while ( v6 < cValues );
    v8 = a6;
  }
  v19 = 0;
  if ( lpcValues )
  {
    do
    {
      if ( v16 )
        break;
      cchValueName = lpcbMaxValueNameLen;
      v20 = v15;
      for ( j = 2LL * lpcbMaxValueNameLen; j; --j )
      {
        *(_BYTE *)v20 = 0;
        v20 = (WCHAR *)((char *)v20 + 1);
      }
      v16 = RegEnumValueW(a3, v19, v15, &cchValueName, 0, 0, 0, 0);
      if ( !v16 && (unsigned int)DynArrayAppendString(v14, v15) == -1 )
        v16 = 14;
      ++v19;
    }
    while ( v19 < lpcValues );
    v8 = a6;
  }
  FreeMemory(v38);
  v22 = cValues;
  v23 = 0;
  if ( cValues )
  {
    do
    {
      if ( v16 )
        break;
      Item = _DynArrayGetItem(v13, v23, 0);
      if ( Item && *(_DWORD *)(Item + 4) == 0x20000 )
        v26 = *(const WCHAR **)(Item + 16);
      else
        v26 = 0;
      v27 = _DynArrayFind(v14, v25, v26);
      if ( v27 == -1 || (v16 = CompareValues(hKey, v26, a5, (__int64)v8)) != 0 )
      {
        v22 = cValues;
      }
      else
      {
        DynArrayRemove(v13, v23);
        DynArrayRemove(v14, v27);
        v22 = cValues - 1;
        --lpcValues;
        --cValues;
      }
      v28 = v23 + 1;
      if ( v27 != -1 )
        v28 = v23;
      v23 = v28;
    }
    while ( v28 < v22 );
  }
  v29 = 0;
  if ( v22 )
  {
    do
    {
      if ( v16 )
        break;
      _DynArrayGetItem(v13, v29, 0);
      if ( a5 - 3 <= 1 )
        v16 = OutputValue(hKey);
      ++v29;
      *v8 = 1;
    }
    while ( v29 < cValues );
    v14 = v37;
  }
  for ( k = 0; k < lpcValues; *v8 = 1 )
  {
    if ( v16 )
      break;
    _DynArrayGetItem(v14, k, 0);
    if ( a5 - 3 <= 1 )
      v16 = OutputValue(a3);
    ++k;
  }
  DestroyDynamicArray(&DynamicArray);
  DestroyDynamicArray(&v37);
  SaveErrorMessage(v16);
  return v16;
}

```

## disassembly

```asm
0x140008320  mov     rax, rsp
0x140008323  mov     [rax+20h], r9
0x140008327  mov     [rax+18h], r8
0x14000832b  mov     [rax+10h], rdx
0x14000832f  mov     [rax+8], rcx
0x140008333  push    rbp
0x140008334  push    rbx
0x140008335  push    rsi
0x140008336  push    rdi
0x140008337  push    r12
0x140008339  push    r13
0x14000833b  push    r14
0x14000833d  push    r15
0x14000833f  lea     rbp, [rax-4Fh]
0x140008343  sub     rsp, 98h
0x14000834a  xor     r14d, r14d
0x14000834d  mov     rsi, r8
0x140008350  mov     [rbp+47h+cchValueName], r14d
0x140008354  mov     rax, rcx
0x140008357  mov     [rbp+47h+cValues], r14d
0x14000835b  mov     [rbp+47h+var_6C], r14d
0x14000835f  mov     [rbp+47h+cbMaxValueNameLen], r14d
0x140008363  mov     [rbp+47h+var_64], r14d
0x140008367  test    rcx, rcx
0x14000836a  jz      loc_140008760
0x140008370  test    rdx, rdx
0x140008373  jz      loc_140008760
0x140008379  test    r8, r8
0x14000837c  jz      loc_140008760
0x140008382  test    r9, r9
0x140008385  jz      loc_140008760
0x14000838b  mov     r15, [rbp+47h+arg_28]
0x14000838f  test    r15, r15
0x140008392  jz      loc_140008760
0x140008398  mov     edi, [rbp+47h+arg_20]
0x14000839b  cmp     edi, 1
0x14000839e  ja      short loc_1400083AD
0x1400083a0  cmp     dword ptr [r15], 1
0x1400083a4  jnz     short loc_1400083AD
0x1400083a6  xor     eax, eax
0x1400083a8  jmp     loc_14000876E
0x1400083ad  mov     [rsp+58h], r14; lpftLastWriteTime
0x1400083b2  lea     rcx, [rbp+47h+cbMaxValueNameLen]
0x1400083b6  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1400083bb  xor     r9d, r9d; lpReserved
0x1400083be  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1400083c3  xor     r8d, r8d; lpcchClass
0x1400083c6  mov     [rsp+0D0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x1400083cb  xor     edx, edx; lpClass
0x1400083cd  lea     rcx, [rbp+47h+cValues]
0x1400083d1  mov     [rsp+0D0h+lpcValues], rcx; lpcValues
0x1400083d6  mov     rcx, rax; hKey
0x1400083d9  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1400083de  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1400083e3  mov     [rsp+0D0h+lpcSubKeys], r14; lpcSubKeys
0x1400083e8  call    cs:__imp_RegQueryInfoKeyW
0x1400083ee  mov     ebx, eax
0x1400083f0  test    eax, eax
0x1400083f2  jnz     loc_140008765
0x1400083f8  mov     [rsp+58h], r14; lpftLastWriteTime
0x1400083fd  lea     rax, [rbp+47h+var_64]
0x140008401  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140008406  xor     r9d, r9d; lpReserved
0x140008409  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14000840e  xor     r8d, r8d; lpcchClass
0x140008411  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140008416  xor     edx, edx; lpClass
0x140008418  lea     rax, [rbp+47h+var_6C]
0x14000841c  mov     rcx, rsi; hKey
0x14000841f  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x140008424  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140008429  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x14000842e  mov     [rsp+0D0h+lpcSubKeys], r14; lpcSubKeys
0x140008433  call    cs:__imp_RegQueryInfoKeyW
0x140008439  mov     ebx, eax
0x14000843b  test    eax, eax
0x14000843d  jnz     loc_140008765
0x140008443  mov     ecx, [rbp+47h+cbMaxValueNameLen]
0x140008446  mov     edx, [rbp+47h+var_64]
0x140008449  cmp     edi, 1
0x14000844c  ja      short loc_140008466
0x14000844e  mov     eax, [rbp+47h+var_6C]
0x140008451  cmp     [rbp+47h+cValues], eax
0x140008454  jnz     short loc_14000845A
0x140008456  cmp     ecx, edx
0x140008458  jz      short loc_140008466
0x14000845a  mov     dword ptr [r15], 1
0x140008461  jmp     loc_1400083A6
0x140008466  inc     edx
0x140008468  inc     ecx
0x14000846a  mov     [rbp+47h+var_64], edx
0x14000846d  mov     [rbp+47h+cbMaxValueNameLen], ecx
0x140008470  cmp     edx, ecx
0x140008472  jbe     short loc_140008479
0x140008474  mov     [rbp+47h+cbMaxValueNameLen], edx
0x140008477  jmp     short loc_14000847C
0x140008479  mov     [rbp+47h+var_64], ecx
0x14000847c  call    CreateDynamicArray
0x140008481  mov     [rbp+47h+var_58], rax
0x140008485  mov     r12, rax
0x140008488  test    rax, rax
0x14000848b  jnz     short loc_140008497
0x14000848d  mov     ebx, 0Eh
0x140008492  jmp     loc_140008765
0x140008497  call    CreateDynamicArray
0x14000849c  mov     [rbp+47h+var_50], rax
0x1400084a0  mov     r13, rax
0x1400084a3  test    rax, rax
0x1400084a6  jnz     short loc_1400084B3
0x1400084a8  lea     rcx, [rbp+47h+var_58]
0x1400084ac  call    DestroyDynamicArray
0x1400084b1  jmp     short loc_14000848D
0x1400084b3  mov     ecx, [rbp+47h+cbMaxValueNameLen]
0x1400084b6  add     ecx, ecx; dwBytes
0x1400084b8  call    AllocateMemory
0x1400084bd  mov     [rbp+47h+var_48], rax
0x1400084c1  mov     rsi, rax
0x1400084c4  test    rax, rax
0x1400084c7  jnz     short loc_1400084D4
0x1400084c9  lea     rcx, [rbp+47h+var_50]
0x1400084cd  call    DestroyDynamicArray
0x1400084d2  jmp     short loc_1400084A8
0x1400084d4  xor     edx, edx
0x1400084d6  mov     edi, r14d
0x1400084d9  mov     ebx, 0Eh
0x1400084de  cmp     [rbp+47h+cValues], edx
0x1400084e1  jbe     short loc_140008555
0x1400084e3  mov     r15, [rbp+47h+hKey]
0x1400084e7  test    edi, edi
0x1400084e9  jnz     short loc_140008551
0x1400084eb  mov     eax, [rbp+47h+cbMaxValueNameLen]
0x1400084ee  mov     ecx, eax
0x1400084f0  mov     [rbp+47h+cchValueName], eax
0x1400084f3  mov     rax, rsi
0x1400084f6  add     rcx, rcx
0x1400084f9  jz      short loc_140008506
0x1400084fb  mov     [rax], dl
0x1400084fd  inc     rax
0x140008500  sub     rcx, 1
0x140008504  jnz     short loc_1400084FB
0x140008506  mov     [rsp+0D0h+lpcValues], rdx; lpcbData
0x14000850b  lea     r9, [rbp+47h+cchValueName]; lpcchValueName
0x14000850f  mov     [rsp+0D0h+lpcbMaxClassLen], rdx; lpData
0x140008514  mov     r8, rsi; lpValueName
0x140008517  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; lpType
0x14000851c  mov     rcx, r15; hKey
0x14000851f  mov     [rsp+0D0h+lpcSubKeys], rdx; lpReserved
0x140008524  mov     edx, r14d; dwIndex
0x140008527  call    cs:__imp_RegEnumValueW
0x14000852d  xor     edx, edx
0x14000852f  mov     edi, eax
0x140008531  test    eax, eax
0x140008533  jnz     short loc_140008548
0x140008535  mov     rdx, rsi
0x140008538  mov     rcx, r12
0x14000853b  call    DynArrayAppendString
0x140008540  cmp     eax, 0FFFFFFFFh
0x140008543  cmovz   edi, ebx
0x140008546  xor     edx, edx
0x140008548  inc     r14d
0x14000854b  cmp     r14d, [rbp+47h+cValues]
0x14000854f  jb      short loc_1400084E7
0x140008551  mov     r15, [rbp+47h+arg_28]
0x140008555  mov     r14d, edx
0x140008558  cmp     [rbp+47h+var_6C], edx
0x14000855b  jbe     short loc_1400085CF
0x14000855d  mov     r15, [rbp+47h+arg_10]
0x140008561  test    edi, edi
0x140008563  jnz     short loc_1400085CB
0x140008565  mov     eax, [rbp+47h+var_64]
0x140008568  mov     ecx, eax
0x14000856a  mov     [rbp+47h+cchValueName], eax
0x14000856d  mov     rax, rsi
0x140008570  add     rcx, rcx
0x140008573  jz      short loc_140008580
0x140008575  mov     [rax], dl
0x140008577  inc     rax
0x14000857a  sub     rcx, 1
0x14000857e  jnz     short loc_140008575
0x140008580  mov     [rsp+0D0h+lpcValues], rdx; lpcbData
0x140008585  lea     r9, [rbp+47h+cchValueName]; lpcchValueName
0x140008589  mov     [rsp+0D0h+lpcbMaxClassLen], rdx; lpData
0x14000858e  mov     r8, rsi; lpValueName
0x140008591  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; lpType
0x140008596  mov     rcx, r15; hKey
0x140008599  mov     [rsp+0D0h+lpcSubKeys], rdx; lpReserved
0x14000859e  mov     edx, r14d; dwIndex
0x1400085a1  call    cs:__imp_RegEnumValueW
0x1400085a7  xor     edx, edx
0x1400085a9  mov     edi, eax
0x1400085ab  test    eax, eax
0x1400085ad  jnz     short loc_1400085C2
0x1400085af  mov     rdx, rsi
0x1400085b2  mov     rcx, r13
0x1400085b5  call    DynArrayAppendString
0x1400085ba  cmp     eax, 0FFFFFFFFh
0x1400085bd  cmovz   edi, ebx
0x1400085c0  xor     edx, edx
0x1400085c2  inc     r14d
0x1400085c5  cmp     r14d, [rbp+47h+var_6C]
0x1400085c9  jb      short loc_140008561
0x1400085cb  mov     r15, [rbp+47h+arg_28]
0x1400085cf  lea     rcx, [rbp+47h+var_48]
0x1400085d3  call    FreeMemory
0x1400085d8  mov     ecx, [rbp+47h+cValues]
0x1400085db  xor     r14d, r14d
0x1400085de  test    ecx, ecx
0x1400085e0  jz      loc_14000868E
0x1400085e6  test    edi, edi
0x1400085e8  jnz     loc_14000868E
0x1400085ee  xor     r8d, r8d
0x1400085f1  mov     edx, r14d
0x1400085f4  mov     rcx, r12
0x1400085f7  call    __DynArrayGetItem
0x1400085fc  test    rax, rax
0x1400085ff  jnz     short loc_140008605
0x140008601  xor     ebx, ebx
0x140008603  jmp     short loc_140008612
0x140008605  cmp     dword ptr [rax+4], 20000h
0x14000860c  jnz     short loc_140008601
0x14000860e  mov     rbx, [rax+10h]
0x140008612  mov     r8, rbx
0x140008615  mov     rcx, r13
0x140008618  call    __DynArrayFind
0x14000861d  mov     esi, eax
0x14000861f  cmp     eax, 0FFFFFFFFh
0x140008622  jz      short loc_140008675
0x140008624  mov     eax, [rbp+47h+arg_20]
0x140008627  mov     r9, [rbp+47h+arg_18]
0x14000862b  mov     r8, [rbp+47h+arg_10]
0x14000862f  mov     rdx, [rbp+47h+arg_8]
0x140008633  mov     rcx, [rbp+47h+hKey]; hKey
0x140008637  mov     [rsp+0D0h+lpcbMaxClassLen], r15; __int64
0x14000863c  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax; int
0x140008640  mov     [rsp+0D0h+lpcSubKeys], rbx; lpValueName
0x140008645  call    CompareValues
0x14000864a  mov     edi, eax
0x14000864c  test    eax, eax
0x14000864e  jnz     short loc_140008675
0x140008650  mov     edx, r14d
0x140008653  mov     rcx, r12
0x140008656  call    DynArrayRemove
0x14000865b  mov     edx, esi
0x14000865d  mov     rcx, r13
0x140008660  call    DynArrayRemove
0x140008665  mov     ecx, [rbp+47h+cValues]
0x140008668  or      edx, 0FFFFFFFFh
0x14000866b  add     ecx, edx
0x14000866d  add     [rbp+47h+var_6C], edx
0x140008670  mov     [rbp+47h+cValues], ecx
0x140008673  jmp     short loc_140008678
0x140008675  mov     ecx, [rbp+47h+cValues]
0x140008678  cmp     esi, 0FFFFFFFFh
0x14000867b  lea     eax, [r14+1]
0x14000867f  cmovnz  eax, r14d
0x140008683  mov     r14d, eax
0x140008686  cmp     eax, ecx
0x140008688  jb      loc_1400085E6
0x14000868e  xor     ebx, ebx
0x140008690  test    ecx, ecx
0x140008692  jz      short loc_1400086EB
0x140008694  mov     r13d, [rbp+47h+arg_20]
0x140008698  test    edi, edi
0x14000869a  jnz     short loc_1400086E7
0x14000869c  xor     r8d, r8d
0x14000869f  mov     edx, ebx
0x1400086a1  mov     rcx, r12
0x1400086a4  call    __DynArrayGetItem
0x1400086a9  test    rax, rax
0x1400086ac  jz      short loc_1400086BB
0x1400086ae  cmp     dword ptr [rax+4], 20000h
0x1400086b5  jnz     short loc_1400086BB
0x1400086b7  mov     r8, [rax+10h]
0x1400086bb  lea     eax, [r13-3]
0x1400086bf  cmp     eax, 1
0x1400086c2  ja      short loc_1400086D9
0x1400086c4  mov     rdx, [rbp+47h+arg_8]
0x1400086c8  mov     r9d, 1
0x1400086ce  mov     rcx, [rbp+47h+hKey]; hKey
0x1400086d2  call    OutputValue
0x1400086d7  mov     edi, eax
0x1400086d9  inc     ebx
0x1400086db  mov     dword ptr [r15], 1
0x1400086e2  cmp     ebx, [rbp+47h+cValues]
0x1400086e5  jb      short loc_140008698
0x1400086e7  mov     r13, [rbp+47h+var_50]
0x1400086eb  xor     ebx, ebx
0x1400086ed  cmp     [rbp+47h+var_6C], ebx
0x1400086f0  jbe     short loc_140008743
0x1400086f2  test    edi, edi
0x1400086f4  jnz     short loc_140008743
0x1400086f6  xor     r8d, r8d
0x1400086f9  mov     edx, ebx
0x1400086fb  mov     rcx, r13
0x1400086fe  call    __DynArrayGetItem
0x140008703  test    rax, rax
0x140008706  jz      short loc_140008715
0x140008708  cmp     dword ptr [rax+4], 20000h
0x14000870f  jnz     short loc_140008715
0x140008711  mov     r8, [rax+10h]
  ... truncated ...
```
