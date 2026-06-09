# CompareEnumerateValueName

- ea: `0x140008838`
- end: `0x140008cb3`
- name: `CompareEnumerateValueName`
- size: `1147`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, HKEY, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400080a4`

## callees

- `0x140002ce4`
- `0x140008838`
- `0x1400090a8`
- `0x140009498`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000f294`
- `0x14000f2c4`
- `0x14000f43c`
- `0x14000f5c8`
- `0x14000f78c`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140008a4b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140008acb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140008a4b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140008acb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008900`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008951`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008900`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008951`

## pseudocode

```c
__int64 __fastcall CompareEnumerateValueName(HKEY hKey, __int64 a2, HKEY a3, __int64 a4, unsigned int a5, _DWORD *a6)
{
  DWORD v6; // r14d
  _DWORD *v8; // r15
  unsigned int v10; // ebx
  DWORD v11; // edx
  DWORD v12; // ecx
  _DWORD *v13; // r12
  _DWORD *v14; // r13
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
  __int64 v30; // rax
  const WCHAR *v31; // r8
  DWORD k; // ebx
  __int64 v33; // rax
  const WCHAR *v34; // r8
  DWORD cValues; // [rsp+68h] [rbp-29h] BYREF
  DWORD lpcValues; // [rsp+6Ch] [rbp-25h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp-21h] BYREF
  DWORD lpcbMaxValueNameLen; // [rsp+74h] [rbp-1Dh] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-19h] BYREF
  __int64 DynamicArray; // [rsp+80h] [rbp-11h] BYREF
  __int64 v41; // [rsp+88h] [rbp-9h] BYREF
  __int64 v42[9]; // [rsp+90h] [rbp-1h] BYREF
  int v44; // [rsp+F0h] [rbp+5Fh]
  int v46; // [rsp+100h] [rbp+6Fh]

  v46 = a4;
  v44 = a2;
  v6 = 0;
  cchValueName = 0;
  cValues = 0;
  lpcValues = 0;
  cbMaxValueNameLen = 0;
  lpcbMaxValueNameLen = 0;
  if ( !hKey || !a2 || !a3 || !a4 || (v8 = a6) == 0 )
  {
    v10 = 87;
    goto LABEL_74;
  }
  if ( a5 <= 1 && *a6 == 1 )
    return 0;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v10 )
    goto LABEL_74;
  v10 = RegQueryInfoKeyW(a3, 0, 0, 0, 0, 0, 0, &lpcValues, &lpcbMaxValueNameLen, 0, 0, 0);
  if ( v10 )
    goto LABEL_74;
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
  v13 = (_DWORD *)DynamicArray;
  if ( !DynamicArray )
  {
LABEL_19:
    v10 = 14;
LABEL_74:
    SaveErrorMessage(v10);
    return v10;
  }
  v41 = CreateDynamicArray();
  v14 = (_DWORD *)v41;
  if ( !v41 )
  {
LABEL_21:
    DestroyDynamicArray(&DynamicArray);
    goto LABEL_19;
  }
  v42[0] = AllocateMemory(2 * cbMaxValueNameLen);
  v15 = (WCHAR *)v42[0];
  if ( !v42[0] )
  {
    DestroyDynamicArray(&v41);
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
  FreeMemory(v42);
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
      v30 = _DynArrayGetItem(v13, v29, 0);
      if ( v30 && *(_DWORD *)(v30 + 4) == 0x20000 )
        v31 = *(const WCHAR **)(v30 + 16);
      if ( a5 - 3 <= 1 )
        v16 = OutputValue(hKey, v44, v31, 1);
      ++v29;
      *v8 = 1;
    }
    while ( v29 < cValues );
    v14 = (_DWORD *)v41;
  }
  for ( k = 0; k < lpcValues; *v8 = 1 )
  {
    if ( v16 )
      break;
    v33 = _DynArrayGetItem(v14, k, 0);
    if ( v33 && *(_DWORD *)(v33 + 4) == 0x20000 )
      v34 = *(const WCHAR **)(v33 + 16);
    if ( a5 - 3 <= 1 )
      v16 = OutputValue(a3, v46, v34, 2);
    ++k;
  }
  DestroyDynamicArray(&DynamicArray);
  DestroyDynamicArray(&v41);
  SaveErrorMessage(v16);
  return v16;
}

```

## disassembly

```asm
0x140008838  mov     rax, rsp
0x14000883b  mov     [rax+20h], r9
0x14000883f  mov     [rax+18h], r8
0x140008843  mov     [rax+10h], rdx
0x140008847  mov     [rax+8], rcx
0x14000884b  push    rbp
0x14000884c  push    rbx
0x14000884d  push    rsi
0x14000884e  push    rdi
0x14000884f  push    r12
0x140008851  push    r13
0x140008853  push    r14
0x140008855  push    r15
0x140008857  lea     rbp, [rax-4Fh]
0x14000885b  sub     rsp, 98h
0x140008862  xor     r14d, r14d
0x140008865  mov     rsi, r8
0x140008868  mov     [rbp+47h+cchValueName], r14d
0x14000886c  mov     rax, rcx
0x14000886f  mov     [rbp+47h+cValues], r14d
0x140008873  mov     [rbp+47h+var_6C], r14d
0x140008877  mov     [rbp+47h+cbMaxValueNameLen], r14d
0x14000887b  mov     [rbp+47h+var_64], r14d
0x14000887f  test    rcx, rcx
0x140008882  jz      loc_140008C90
0x140008888  test    rdx, rdx
0x14000888b  jz      loc_140008C90
0x140008891  test    r8, r8
0x140008894  jz      loc_140008C90
0x14000889a  test    r9, r9
0x14000889d  jz      loc_140008C90
0x1400088a3  mov     r15, [rbp+47h+arg_28]
0x1400088a7  test    r15, r15
0x1400088aa  jz      loc_140008C90
0x1400088b0  mov     edi, [rbp+47h+arg_20]
0x1400088b3  cmp     edi, 1
0x1400088b6  ja      short loc_1400088C5
0x1400088b8  cmp     dword ptr [r15], 1
0x1400088bc  jnz     short loc_1400088C5
0x1400088be  xor     eax, eax
0x1400088c0  jmp     loc_140008C9E
0x1400088c5  mov     [rsp+58h], r14; lpftLastWriteTime
0x1400088ca  lea     rcx, [rbp+47h+cbMaxValueNameLen]
0x1400088ce  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1400088d3  xor     r9d, r9d; lpReserved
0x1400088d6  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1400088db  xor     r8d, r8d; lpcchClass
0x1400088de  mov     [rsp+0D0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x1400088e3  xor     edx, edx; lpClass
0x1400088e5  lea     rcx, [rbp+47h+cValues]
0x1400088e9  mov     [rsp+0D0h+lpcValues], rcx; lpcValues
0x1400088ee  mov     rcx, rax; hKey
0x1400088f1  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1400088f6  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1400088fb  mov     [rsp+0D0h+lpcSubKeys], r14; lpcSubKeys
0x140008900  call    cs:__imp_RegQueryInfoKeyW
0x140008907  nop     dword ptr [rax+rax+00h]
0x14000890c  mov     ebx, eax
0x14000890e  test    eax, eax
0x140008910  jnz     loc_140008C95
0x140008916  mov     [rsp+58h], r14; lpftLastWriteTime
0x14000891b  lea     rax, [rbp+47h+var_64]
0x14000891f  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140008924  xor     r9d, r9d; lpReserved
0x140008927  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14000892c  xor     r8d, r8d; lpcchClass
0x14000892f  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140008934  xor     edx, edx; lpClass
0x140008936  lea     rax, [rbp+47h+var_6C]
0x14000893a  mov     rcx, rsi; hKey
0x14000893d  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x140008942  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140008947  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x14000894c  mov     [rsp+0D0h+lpcSubKeys], r14; lpcSubKeys
0x140008951  call    cs:__imp_RegQueryInfoKeyW
0x140008958  nop     dword ptr [rax+rax+00h]
0x14000895d  mov     ebx, eax
0x14000895f  test    eax, eax
0x140008961  jnz     loc_140008C95
0x140008967  mov     ecx, [rbp+47h+cbMaxValueNameLen]
0x14000896a  mov     edx, [rbp+47h+var_64]
0x14000896d  cmp     edi, 1
0x140008970  ja      short loc_14000898A
0x140008972  mov     eax, [rbp+47h+var_6C]
0x140008975  cmp     [rbp+47h+cValues], eax
0x140008978  jnz     short loc_14000897E
0x14000897a  cmp     ecx, edx
0x14000897c  jz      short loc_14000898A
0x14000897e  mov     dword ptr [r15], 1
0x140008985  jmp     loc_1400088BE
0x14000898a  inc     edx
0x14000898c  inc     ecx
0x14000898e  mov     [rbp+47h+var_64], edx
0x140008991  mov     [rbp+47h+cbMaxValueNameLen], ecx
0x140008994  cmp     edx, ecx
0x140008996  jbe     short loc_14000899D
0x140008998  mov     [rbp+47h+cbMaxValueNameLen], edx
0x14000899b  jmp     short loc_1400089A0
0x14000899d  mov     [rbp+47h+var_64], ecx
0x1400089a0  call    CreateDynamicArray
0x1400089a5  mov     [rbp+47h+var_58], rax
0x1400089a9  mov     r12, rax
0x1400089ac  test    rax, rax
0x1400089af  jnz     short loc_1400089BB
0x1400089b1  mov     ebx, 0Eh
0x1400089b6  jmp     loc_140008C95
0x1400089bb  call    CreateDynamicArray
0x1400089c0  mov     [rbp+47h+var_50], rax
0x1400089c4  mov     r13, rax
0x1400089c7  test    rax, rax
0x1400089ca  jnz     short loc_1400089D7
0x1400089cc  lea     rcx, [rbp+47h+var_58]
0x1400089d0  call    DestroyDynamicArray
0x1400089d5  jmp     short loc_1400089B1
0x1400089d7  mov     ecx, [rbp+47h+cbMaxValueNameLen]
0x1400089da  add     ecx, ecx; dwBytes
0x1400089dc  call    AllocateMemory
0x1400089e1  mov     [rbp+47h+var_48], rax
0x1400089e5  mov     rsi, rax
0x1400089e8  test    rax, rax
0x1400089eb  jnz     short loc_1400089F8
0x1400089ed  lea     rcx, [rbp+47h+var_50]
0x1400089f1  call    DestroyDynamicArray
0x1400089f6  jmp     short loc_1400089CC
0x1400089f8  xor     edx, edx
0x1400089fa  mov     edi, r14d
0x1400089fd  mov     ebx, 0Eh
0x140008a02  cmp     [rbp+47h+cValues], edx
0x140008a05  jbe     short loc_140008A7F
0x140008a07  mov     r15, [rbp+47h+hKey]
0x140008a0b  test    edi, edi
0x140008a0d  jnz     short loc_140008A7B
0x140008a0f  mov     eax, [rbp+47h+cbMaxValueNameLen]
0x140008a12  mov     ecx, eax
0x140008a14  mov     [rbp+47h+cchValueName], eax
0x140008a17  mov     rax, rsi
0x140008a1a  add     rcx, rcx
0x140008a1d  jz      short loc_140008A2A
0x140008a1f  mov     [rax], dl
0x140008a21  inc     rax
0x140008a24  sub     rcx, 1
0x140008a28  jnz     short loc_140008A1F
0x140008a2a  mov     [rsp+0D0h+lpcValues], rdx; lpcbData
0x140008a2f  lea     r9, [rbp+47h+cchValueName]; lpcchValueName
0x140008a33  mov     [rsp+0D0h+lpcbMaxClassLen], rdx; lpData
0x140008a38  mov     r8, rsi; lpValueName
0x140008a3b  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; lpType
0x140008a40  mov     rcx, r15; hKey
0x140008a43  mov     [rsp+0D0h+lpcSubKeys], rdx; lpReserved
0x140008a48  mov     edx, r14d; dwIndex
0x140008a4b  call    cs:__imp_RegEnumValueW
0x140008a52  nop     dword ptr [rax+rax+00h]
0x140008a57  xor     edx, edx
0x140008a59  mov     edi, eax
0x140008a5b  test    eax, eax
0x140008a5d  jnz     short loc_140008A72
0x140008a5f  mov     rdx, rsi
0x140008a62  mov     rcx, r12
0x140008a65  call    DynArrayAppendString
0x140008a6a  cmp     eax, 0FFFFFFFFh
0x140008a6d  cmovz   edi, ebx
0x140008a70  xor     edx, edx
0x140008a72  inc     r14d
0x140008a75  cmp     r14d, [rbp+47h+cValues]
0x140008a79  jb      short loc_140008A0B
0x140008a7b  mov     r15, [rbp+47h+arg_28]
0x140008a7f  mov     r14d, edx
0x140008a82  cmp     [rbp+47h+var_6C], edx
0x140008a85  jbe     short loc_140008AFF
0x140008a87  mov     r15, [rbp+47h+arg_10]
0x140008a8b  test    edi, edi
0x140008a8d  jnz     short loc_140008AFB
0x140008a8f  mov     eax, [rbp+47h+var_64]
0x140008a92  mov     ecx, eax
0x140008a94  mov     [rbp+47h+cchValueName], eax
0x140008a97  mov     rax, rsi
0x140008a9a  add     rcx, rcx
0x140008a9d  jz      short loc_140008AAA
0x140008a9f  mov     [rax], dl
0x140008aa1  inc     rax
0x140008aa4  sub     rcx, 1
0x140008aa8  jnz     short loc_140008A9F
0x140008aaa  mov     [rsp+0D0h+lpcValues], rdx; lpcbData
0x140008aaf  lea     r9, [rbp+47h+cchValueName]; lpcchValueName
0x140008ab3  mov     [rsp+0D0h+lpcbMaxClassLen], rdx; lpData
0x140008ab8  mov     r8, rsi; lpValueName
0x140008abb  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; lpType
0x140008ac0  mov     rcx, r15; hKey
0x140008ac3  mov     [rsp+0D0h+lpcSubKeys], rdx; lpReserved
0x140008ac8  mov     edx, r14d; dwIndex
0x140008acb  call    cs:__imp_RegEnumValueW
0x140008ad2  nop     dword ptr [rax+rax+00h]
0x140008ad7  xor     edx, edx
0x140008ad9  mov     edi, eax
0x140008adb  test    eax, eax
0x140008add  jnz     short loc_140008AF2
0x140008adf  mov     rdx, rsi
0x140008ae2  mov     rcx, r13
0x140008ae5  call    DynArrayAppendString
0x140008aea  cmp     eax, 0FFFFFFFFh
0x140008aed  cmovz   edi, ebx
0x140008af0  xor     edx, edx
0x140008af2  inc     r14d
0x140008af5  cmp     r14d, [rbp+47h+var_6C]
0x140008af9  jb      short loc_140008A8B
0x140008afb  mov     r15, [rbp+47h+arg_28]
0x140008aff  lea     rcx, [rbp+47h+var_48]
0x140008b03  call    FreeMemory
0x140008b08  mov     ecx, [rbp+47h+cValues]
0x140008b0b  xor     r14d, r14d
0x140008b0e  test    ecx, ecx
0x140008b10  jz      loc_140008BBE
0x140008b16  test    edi, edi
0x140008b18  jnz     loc_140008BBE
0x140008b1e  xor     r8d, r8d
0x140008b21  mov     edx, r14d
0x140008b24  mov     rcx, r12
0x140008b27  call    __DynArrayGetItem
0x140008b2c  test    rax, rax
0x140008b2f  jnz     short loc_140008B35
0x140008b31  xor     ebx, ebx
0x140008b33  jmp     short loc_140008B42
0x140008b35  cmp     dword ptr [rax+4], 20000h
0x140008b3c  jnz     short loc_140008B31
0x140008b3e  mov     rbx, [rax+10h]
0x140008b42  mov     r8, rbx
0x140008b45  mov     rcx, r13
0x140008b48  call    __DynArrayFind
0x140008b4d  mov     esi, eax
0x140008b4f  cmp     eax, 0FFFFFFFFh
0x140008b52  jz      short loc_140008BA5
0x140008b54  mov     eax, [rbp+47h+arg_20]
0x140008b57  mov     r9, [rbp+47h+arg_18]
0x140008b5b  mov     r8, [rbp+47h+arg_10]
0x140008b5f  mov     rdx, [rbp+47h+arg_8]
0x140008b63  mov     rcx, [rbp+47h+hKey]; hKey
0x140008b67  mov     [rsp+0D0h+lpcbMaxClassLen], r15; __int64
0x140008b6c  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax; int
0x140008b70  mov     [rsp+0D0h+lpcSubKeys], rbx; lpValueName
0x140008b75  call    CompareValues
0x140008b7a  mov     edi, eax
0x140008b7c  test    eax, eax
0x140008b7e  jnz     short loc_140008BA5
0x140008b80  mov     edx, r14d
0x140008b83  mov     rcx, r12
0x140008b86  call    DynArrayRemove
0x140008b8b  mov     edx, esi
0x140008b8d  mov     rcx, r13
0x140008b90  call    DynArrayRemove
0x140008b95  mov     ecx, [rbp+47h+cValues]
0x140008b98  or      edx, 0FFFFFFFFh
0x140008b9b  add     ecx, edx
0x140008b9d  add     [rbp+47h+var_6C], edx
0x140008ba0  mov     [rbp+47h+cValues], ecx
0x140008ba3  jmp     short loc_140008BA8
0x140008ba5  mov     ecx, [rbp+47h+cValues]
0x140008ba8  cmp     esi, 0FFFFFFFFh
0x140008bab  lea     eax, [r14+1]
0x140008baf  cmovnz  eax, r14d
0x140008bb3  mov     r14d, eax
0x140008bb6  cmp     eax, ecx
0x140008bb8  jb      loc_140008B16
0x140008bbe  xor     ebx, ebx
0x140008bc0  test    ecx, ecx
0x140008bc2  jz      short loc_140008C1B
0x140008bc4  mov     r13d, [rbp+47h+arg_20]
0x140008bc8  test    edi, edi
0x140008bca  jnz     short loc_140008C17
0x140008bcc  xor     r8d, r8d
0x140008bcf  mov     edx, ebx
0x140008bd1  mov     rcx, r12
0x140008bd4  call    __DynArrayGetItem
0x140008bd9  test    rax, rax
0x140008bdc  jz      short loc_140008BEB
0x140008bde  cmp     dword ptr [rax+4], 20000h
0x140008be5  jnz     short loc_140008BEB
0x140008be7  mov     r8, [rax+10h]
0x140008beb  lea     eax, [r13-3]
0x140008bef  cmp     eax, 1
0x140008bf2  ja      short loc_140008C09
0x140008bf4  mov     rdx, [rbp+47h+arg_8]
0x140008bf8  mov     r9d, 1
0x140008bfe  mov     rcx, [rbp+47h+hKey]; hKey
0x140008c02  call    OutputValue
0x140008c07  mov     edi, eax
0x140008c09  inc     ebx
0x140008c0b  mov     dword ptr [r15], 1
0x140008c12  cmp     ebx, [rbp+47h+cValues]
0x140008c15  jb      short loc_140008BC8
0x140008c17  mov     r13, [rbp+47h+var_50]
0x140008c1b  xor     ebx, ebx
0x140008c1d  cmp     [rbp+47h+var_6C], ebx
0x140008c20  jbe     short loc_140008C73
0x140008c22  test    edi, edi
0x140008c24  jnz     short loc_140008C73
0x140008c26  xor     r8d, r8d
0x140008c29  mov     edx, ebx
0x140008c2b  mov     rcx, r13
0x140008c2e  call    __DynArrayGetItem
0x140008c33  test    rax, rax
  ... truncated ...
```
