# CompareEnumerateKey

- ea: `0x140007be0`
- end: `0x140008319`
- name: `CompareEnumerateKey`
- size: `1849`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, HKEY, const WCHAR *, unsigned int, int, _DWORD *, int, int, _DWORD *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007be0`
- `0x140008788`

## callees

- `0x140002b70`
- `0x140007be0`
- `0x140008320`
- `0x1400094a0`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000e2f8`
- `0x14000e450`
- `0x14000e604`
- `0x14000e634`
- `0x14000e7a4`
- `0x14000e928`
- `0x14000eae0`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000808a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400080b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000808a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400080b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007e63`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007eed`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007e63`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007eed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400080c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000818c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400082ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400082c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400080c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000818c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400082ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400082c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007ce0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007d50`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007ce0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007d50`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007f33`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007f4a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007f33`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007f4a`

## pseudocode

```c
__int64 __fastcall CompareEnumerateKey(
        HKEY a1,
        const WCHAR *a2,
        HKEY a3,
        const WCHAR *a4,
        unsigned int a5,
        int a6,
        _DWORD *a7,
        int a8,
        int a9,
        _DWORD *a10)
{
  DWORD v10; // r14d
  _DWORD *v13; // r15
  unsigned int v14; // r13d
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v18; // edi
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // ecx
  __int64 v22; // r12
  WCHAR *v23; // rsi
  WCHAR *v24; // rax
  __int64 i; // rcx
  DWORD v26; // r14d
  __int64 v27; // r15
  WCHAR *v28; // rax
  __int64 j; // rcx
  int v30; // eax
  int v31; // eax
  DWORD v32; // esi
  __int64 v33; // r14
  __int64 Item; // rax
  __int64 v35; // rdx
  const WCHAR *v36; // rdi
  LPVOID v37; // rbx
  LPVOID v38; // rbx
  int v39; // ecx
  DWORD v40; // edi
  __int64 v41; // rax
  __int64 v42; // rdx
  DWORD v43; // edi
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rdx
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-61h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-5Dh] BYREF
  LSTATUS v49; // [rsp+70h] [rbp-59h]
  DWORD lpcbMaxSubKeyLen; // [rsp+74h] [rbp-55h] BYREF
  DWORD lpcSubKeys; // [rsp+78h] [rbp-51h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-4Dh] BYREF
  HKEY hKey; // [rsp+80h] [rbp-49h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v55; // [rsp+90h] [rbp-39h]
  __int64 v56; // [rsp+98h] [rbp-31h] BYREF
  LPVOID Memory; // [rsp+A0h] [rbp-29h] BYREF
  LPVOID v58; // [rsp+A8h] [rbp-21h] BYREF
  REGSAM samDesired; // [rsp+B0h] [rbp-19h]
  __int64 DynamicArray; // [rsp+B8h] [rbp-11h] BYREF
  _QWORD v61[9]; // [rsp+C0h] [rbp-9h] BYREF

  v10 = 0;
  cchName = 0;
  cSubKeys = 0;
  lpcSubKeys = 0;
  hKey = 0;
  phkResult = 0;
  cbMaxSubKeyLen = 0;
  lpcbMaxSubKeyLen = 0;
  Memory = 0;
  v58 = 0;
  if ( a1 && a2 && a3 && a4 && (v13 = a7) != 0 )
  {
    v14 = a5;
    v15 = CompareEnumerateValueName(a1, (__int64)a2, a3, (__int64)a4, a5, a7);
    v16 = v15;
    if ( a6 && !v15 )
    {
      if ( a5 <= 1 && *a7 == 1 )
        return 0;
      v16 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( !v16 )
      {
        if ( !cSubKeys || cbMaxSubKeyLen )
        {
          if ( cbMaxSubKeyLen < 0x100 )
            cbMaxSubKeyLen *= 2;
        }
        else
        {
          cbMaxSubKeyLen = 256;
        }
        v18 = RegQueryInfoKeyW(a3, 0, 0, 0, &lpcSubKeys, &lpcbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( v18 )
          goto LABEL_18;
        v19 = lpcbMaxSubKeyLen;
        if ( !lpcSubKeys || lpcbMaxSubKeyLen )
        {
          if ( lpcbMaxSubKeyLen < 0x100 )
            v19 = 2 * lpcbMaxSubKeyLen;
        }
        else
        {
          v19 = 256;
        }
        if ( a5 <= 1 && (cSubKeys != lpcSubKeys || cbMaxSubKeyLen != v19) )
        {
          *a7 = 1;
          return 0;
        }
        v20 = v19 + 1;
        v21 = cbMaxSubKeyLen + 1;
        lpcbMaxSubKeyLen = v20;
        cbMaxSubKeyLen = v21;
        if ( v20 <= v21 )
          lpcbMaxSubKeyLen = v21;
        else
          cbMaxSubKeyLen = v20;
        DynamicArray = CreateDynamicArray();
        v22 = DynamicArray;
        if ( !DynamicArray )
        {
LABEL_32:
          v18 = 14;
LABEL_18:
          SaveErrorMessage(v18);
          return v18;
        }
        v56 = CreateDynamicArray();
        if ( !v56 )
        {
LABEL_34:
          DestroyDynamicArray(&DynamicArray);
          goto LABEL_32;
        }
        v61[0] = AllocateMemory(2 * cbMaxSubKeyLen);
        v23 = (WCHAR *)v61[0];
        if ( !v61[0] )
        {
          DestroyDynamicArray(&v56);
          goto LABEL_34;
        }
        v16 = 0;
        v49 = 0;
        if ( cSubKeys )
        {
          do
          {
            if ( v16 && v16 != 5 )
              break;
            cchName = cbMaxSubKeyLen;
            v24 = v23;
            for ( i = 2LL * cbMaxSubKeyLen; i; --i )
            {
              *(_BYTE *)v24 = 0;
              v24 = (WCHAR *)((char *)v24 + 1);
            }
            v16 = RegEnumKeyExW(a1, v10, v23, &cchName, 0, 0, 0, 0);
            if ( !v16 && (unsigned int)DynArrayAppendString(v22, v23) == -1 )
              v16 = 14;
            ++v10;
          }
          while ( v10 < cSubKeys );
          v13 = a7;
          v49 = v16;
        }
        v26 = 0;
        if ( lpcSubKeys )
        {
          v27 = v56;
          do
          {
            if ( v16 && v16 != 5 )
              break;
            cchName = lpcbMaxSubKeyLen;
            v28 = v23;
            for ( j = 2LL * lpcbMaxSubKeyLen; j; --j )
            {
              *(_BYTE *)v28 = 0;
              v28 = (WCHAR *)((char *)v28 + 1);
            }
            v16 = RegEnumKeyExW(a3, v26, v23, &cchName, 0, 0, 0, 0);
            if ( !v16 && (unsigned int)DynArrayAppendString(v27, v23) == -1 )
              v16 = 14;
            ++v26;
          }
          while ( v26 < lpcSubKeys );
          v13 = a7;
          v14 = a5;
          v49 = v16;
        }
        FreeMemory(v61);
        if ( !v16 )
        {
          v30 = lstrlenW(a2);
          cbMaxSubKeyLen += 5 + v30;
          v31 = lstrlenW(a4);
          lpcbMaxSubKeyLen += 5 + v31;
          Memory = AllocateMemory(2 * cbMaxSubKeyLen);
          if ( Memory )
          {
            v58 = AllocateMemory(2 * lpcbMaxSubKeyLen);
            if ( !v58 )
              v16 = 14;
          }
          else
          {
            v16 = 14;
          }
          v49 = v16;
        }
        v32 = 0;
        if ( cSubKeys )
        {
          v33 = v56;
          while ( !v16 )
          {
            Item = _DynArrayGetItem(v22, v32, 0);
            if ( Item && *(_DWORD *)(Item + 4) == 0x20000 )
              v36 = *(const WCHAR **)(Item + 16);
            else
              v36 = 0;
            v55 = _DynArrayFind(v33, v35, v36);
            if ( v55 == -1 )
            {
              ++v32;
            }
            else
            {
              if ( ((v14 - 2) & 0xFFFFFFFD) == 0 )
                PrintKey(a2, v36, 3);
              v37 = Memory;
              StringCopyW(Memory, a2, cbMaxSubKeyLen);
              StringConcatW(v37, L"\\", cbMaxSubKeyLen);
              StringConcatW(v37, v36, cbMaxSubKeyLen);
              v38 = v58;
              StringCopyW(v58, a4, lpcbMaxSubKeyLen);
              StringConcatW(v38, L"\\", lpcbMaxSubKeyLen);
              StringConcatW(v38, v36, lpcbMaxSubKeyLen);
              samDesired = a9 | 0x20019;
              v49 = RegOpenKeyExW(a1, v36, 0, a9 | 0x20019, &hKey);
              v16 = v49;
              if ( v49 || (v49 = RegOpenKeyExW(a3, v36, 0, samDesired, &phkResult), (v16 = v49) == 0) )
              {
                v39 = (int)hKey;
              }
              else
              {
                v39 = (int)hKey;
                if ( hKey )
                {
                  RegCloseKey(hKey);
                  v39 = 0;
                  hKey = 0;
                }
              }
              if ( v16 == 5 )
              {
                v16 = 0;
                v49 = 0;
                SaveErrorMessage(0);
                *a10 = 1;
                DynArrayRemove(v22, v32);
                DynArrayRemove(v33, v55);
                --cSubKeys;
                --lpcSubKeys;
              }
              else
              {
                if ( v16 )
                  break;
                v16 = CompareEnumerateKey(
                        v39,
                        (_DWORD)Memory,
                        (_DWORD)phkResult,
                        (_DWORD)v58,
                        v14,
                        a6,
                        (__int64)v13,
                        a8 + 1,
                        a9,
                        (__int64)a10);
                v49 = v16;
                if ( hKey )
                {
                  RegCloseKey(hKey);
                  hKey = 0;
                }
                if ( phkResult )
                {
                  RegCloseKey(phkResult);
                  phkResult = 0;
                }
                if ( !v16 )
                {
                  DynArrayRemove(v22, v32);
                  DynArrayRemove(v33, v55);
                  --cSubKeys;
                  --lpcSubKeys;
                }
                if ( *v13 == 1 && v14 < 2 )
                {
                  cSubKeys = 0;
                  lpcSubKeys = 0;
                  break;
                }
              }
            }
            if ( v32 >= cSubKeys )
              break;
          }
        }
        if ( cSubKeys )
        {
          v40 = 0;
          if ( !v16 )
          {
            do
            {
              v41 = _DynArrayGetItem(v22, v40, 0);
              if ( v41 && *(_DWORD *)(v41 + 4) == 0x20000 )
                v42 = *(_QWORD *)(v41 + 16);
              else
                v42 = 0;
              if ( v14 - 3 <= 1 )
                PrintKey(a2, v42, 1);
              ++v40;
              *v13 = 1;
            }
            while ( v40 < cSubKeys );
            v16 = v49;
          }
        }
        if ( lpcSubKeys )
        {
          v43 = 0;
          if ( !v16 )
          {
            v44 = v56;
            do
            {
              v45 = _DynArrayGetItem(v44, v43, 0);
              if ( v45 && *(_DWORD *)(v45 + 4) == 0x20000 )
                v46 = *(_QWORD *)(v45 + 16);
              else
                v46 = 0;
              if ( v14 - 3 <= 1 )
                PrintKey(a4, v46, 2);
              ++v43;
              *v13 = 1;
            }
            while ( v43 < lpcSubKeys );
            v16 = v49;
          }
        }
        FreeMemory(v61);
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        FreeMemory(&Memory);
        FreeMemory(&v58);
        DestroyDynamicArray(&DynamicArray);
        DestroyDynamicArray(&v56);
      }
    }
  }
  else
  {
    v16 = 87;
  }
  SaveErrorMessage(v16);
  return v16;
}

```

## disassembly

```asm
0x140007be0  mov     rax, rsp
0x140007be3  mov     [rax+20h], r9
0x140007be7  mov     [rax+18h], r8
0x140007beb  mov     [rax+10h], rdx
0x140007bef  mov     [rax+8], rcx
0x140007bf3  push    rbp
0x140007bf4  push    rbx
0x140007bf5  push    rsi
0x140007bf6  push    rdi
0x140007bf7  push    r12
0x140007bf9  push    r13
0x140007bfb  push    r14
0x140007bfd  push    r15
0x140007bff  lea     rbp, [rax-47h]
0x140007c03  sub     rsp, 0C8h
0x140007c0a  xor     r14d, r14d
0x140007c0d  mov     rdi, r8
0x140007c10  mov     [rbp+3Fh+cchName], r14d
0x140007c14  mov     rax, rdx
0x140007c17  mov     [rbp+3Fh+cSubKeys], r14d
0x140007c1b  mov     rsi, rcx
0x140007c1e  mov     [rbp+3Fh+var_90], r14d
0x140007c22  mov     [rbp+3Fh+hKey], r14
0x140007c26  mov     [rbp+3Fh+phkResult], r14
0x140007c2a  mov     [rbp+3Fh+cbMaxSubKeyLen], r14d
0x140007c2e  mov     [rbp+3Fh+var_94], r14d
0x140007c32  mov     [rbp+3Fh+var_68], r14
0x140007c36  mov     [rbp+3Fh+var_60], r14
0x140007c3a  test    rcx, rcx
0x140007c3d  jz      loc_1400082F7
0x140007c43  test    rax, rax
0x140007c46  jz      loc_1400082F7
0x140007c4c  test    r8, r8
0x140007c4f  jz      loc_1400082F7
0x140007c55  test    r9, r9
0x140007c58  jz      loc_1400082F7
0x140007c5e  mov     r15, [rbp+3Fh+arg_30]
0x140007c62  test    r15, r15
0x140007c65  jz      loc_1400082F7
0x140007c6b  mov     r13d, [rbp+3Fh+arg_20]
0x140007c6f  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; __int64
0x140007c74  mov     dword ptr [rsp+100h+lpcSubKeys], r13d; int
0x140007c79  call    CompareEnumerateValueName
0x140007c7e  mov     ebx, eax
0x140007c80  cmp     [rbp+3Fh+arg_28], r14d
0x140007c84  jz      loc_1400082FC
0x140007c8a  test    eax, eax
0x140007c8c  jnz     loc_1400082FC
0x140007c92  cmp     r13d, 1
0x140007c96  ja      short loc_140007CA5
0x140007c98  cmp     dword ptr [r15], 1
0x140007c9c  jnz     short loc_140007CA5
0x140007c9e  xor     eax, eax
0x140007ca0  jmp     loc_140008305
0x140007ca5  mov     [rsp+58h], r14; lpftLastWriteTime
0x140007caa  lea     rax, [rbp+3Fh+cbMaxSubKeyLen]
0x140007cae  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140007cb3  xor     r9d, r9d; lpReserved
0x140007cb6  mov     [rsp+100h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140007cbb  xor     r8d, r8d; lpcchClass
0x140007cbe  mov     [rsp+100h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140007cc3  xor     edx, edx; lpClass
0x140007cc5  mov     [rsp+100h+lpcValues], r14; lpcValues
0x140007cca  mov     rcx, rsi; hKey
0x140007ccd  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140007cd2  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140007cd7  lea     rax, [rbp+3Fh+cSubKeys]
0x140007cdb  mov     [rsp+100h+lpcSubKeys], rax; lpcSubKeys
0x140007ce0  call    cs:__imp_RegQueryInfoKeyW
0x140007ce6  mov     ebx, eax
0x140007ce8  test    eax, eax
0x140007cea  jnz     loc_1400082FC
0x140007cf0  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x140007cf3  cmp     [rbp+3Fh+cSubKeys], r14d
0x140007cf7  jz      short loc_140007D07
0x140007cf9  test    eax, eax
0x140007cfb  jnz     short loc_140007D07
0x140007cfd  mov     ebx, 100h
0x140007d02  mov     [rbp+3Fh+cbMaxSubKeyLen], ebx
0x140007d05  jmp     short loc_140007D15
0x140007d07  mov     ebx, 100h
0x140007d0c  cmp     eax, ebx
0x140007d0e  jnb     short loc_140007D15
0x140007d10  add     eax, eax
0x140007d12  mov     [rbp+3Fh+cbMaxSubKeyLen], eax
0x140007d15  mov     [rsp+58h], r14; lpftLastWriteTime
0x140007d1a  lea     rax, [rbp+3Fh+var_94]
0x140007d1e  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140007d23  xor     r9d, r9d; lpReserved
0x140007d26  mov     [rsp+100h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140007d2b  xor     r8d, r8d; lpcchClass
0x140007d2e  mov     [rsp+100h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140007d33  xor     edx, edx; lpClass
0x140007d35  mov     [rsp+100h+lpcValues], r14; lpcValues
0x140007d3a  mov     rcx, rdi; hKey
0x140007d3d  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140007d42  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140007d47  lea     rax, [rbp+3Fh+var_90]
0x140007d4b  mov     [rsp+100h+lpcSubKeys], rax; lpcSubKeys
0x140007d50  call    cs:__imp_RegQueryInfoKeyW
0x140007d56  mov     edi, eax
0x140007d58  test    eax, eax
0x140007d5a  jz      short loc_140007D6A
0x140007d5c  mov     ecx, edi
0x140007d5e  call    SaveErrorMessage
0x140007d63  mov     eax, edi
0x140007d65  jmp     loc_140008305
0x140007d6a  mov     edx, [rbp+3Fh+var_90]
0x140007d6d  mov     eax, [rbp+3Fh+var_94]
0x140007d70  test    edx, edx
0x140007d72  jz      short loc_140007D7C
0x140007d74  test    eax, eax
0x140007d76  jnz     short loc_140007D7C
0x140007d78  mov     eax, ebx
0x140007d7a  jmp     short loc_140007D82
0x140007d7c  cmp     eax, ebx
0x140007d7e  jnb     short loc_140007D82
0x140007d80  add     eax, eax
0x140007d82  mov     ecx, [rbp+3Fh+cbMaxSubKeyLen]
0x140007d85  cmp     r13d, 1
0x140007d89  ja      short loc_140007DA0
0x140007d8b  cmp     [rbp+3Fh+cSubKeys], edx
0x140007d8e  jnz     short loc_140007D94
0x140007d90  cmp     ecx, eax
0x140007d92  jz      short loc_140007DA0
0x140007d94  mov     dword ptr [r15], 1
0x140007d9b  jmp     loc_140007C9E
0x140007da0  inc     eax
0x140007da2  inc     ecx
0x140007da4  mov     [rbp+3Fh+var_94], eax
0x140007da7  mov     [rbp+3Fh+cbMaxSubKeyLen], ecx
0x140007daa  cmp     eax, ecx
0x140007dac  jbe     short loc_140007DB3
0x140007dae  mov     [rbp+3Fh+cbMaxSubKeyLen], eax
0x140007db1  jmp     short loc_140007DB6
0x140007db3  mov     [rbp+3Fh+var_94], ecx
0x140007db6  call    CreateDynamicArray
0x140007dbb  mov     [rbp+3Fh+var_50], rax
0x140007dbf  mov     r12, rax
0x140007dc2  test    rax, rax
0x140007dc5  jnz     short loc_140007DCE
0x140007dc7  mov     edi, 0Eh
0x140007dcc  jmp     short loc_140007D5C
0x140007dce  call    CreateDynamicArray
0x140007dd3  mov     [rbp+3Fh+var_70], rax
0x140007dd7  test    rax, rax
0x140007dda  jnz     short loc_140007DE7
0x140007ddc  lea     rcx, [rbp+3Fh+var_50]
0x140007de0  call    DestroyDynamicArray
0x140007de5  jmp     short loc_140007DC7
0x140007de7  mov     ecx, [rbp+3Fh+cbMaxSubKeyLen]
0x140007dea  add     ecx, ecx; dwBytes
0x140007dec  call    AllocateMemory
0x140007df1  mov     [rbp+3Fh+var_48], rax
0x140007df5  mov     rsi, rax
0x140007df8  test    rax, rax
0x140007dfb  jnz     short loc_140007E08
0x140007dfd  lea     rcx, [rbp+3Fh+var_70]
0x140007e01  call    DestroyDynamicArray
0x140007e06  jmp     short loc_140007DDC
0x140007e08  xor     edx, edx
0x140007e0a  mov     ebx, r14d
0x140007e0d  mov     edi, 0Eh
0x140007e12  mov     [rbp+3Fh+var_98], ebx
0x140007e15  cmp     [rbp+3Fh+cSubKeys], edx
0x140007e18  jbe     short loc_140007E94
0x140007e1a  mov     r15, [rbp+3Fh+arg_0]
0x140007e1e  test    ebx, ebx
0x140007e20  jz      short loc_140007E27
0x140007e22  cmp     ebx, 5
0x140007e25  jnz     short loc_140007E8D
0x140007e27  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x140007e2a  mov     ecx, eax
0x140007e2c  mov     [rbp+3Fh+cchName], eax
0x140007e2f  mov     rax, rsi
0x140007e32  add     rcx, rcx
0x140007e35  jz      short loc_140007E42
0x140007e37  mov     [rax], dl
0x140007e39  inc     rax
0x140007e3c  sub     rcx, 1
0x140007e40  jnz     short loc_140007E37
0x140007e42  mov     [rsp+100h+lpcValues], rdx; lpftLastWriteTime
0x140007e47  lea     r9, [rbp+3Fh+cchName]; lpcchName
0x140007e4b  mov     [rsp+100h+lpcbMaxClassLen], rdx; lpcchClass
0x140007e50  mov     r8, rsi; lpName
0x140007e53  mov     [rsp+100h+lpcbMaxSubKeyLen], rdx; lpClass
0x140007e58  mov     rcx, r15; hKey
0x140007e5b  mov     [rsp+100h+lpcSubKeys], rdx; lpReserved
0x140007e60  mov     edx, r14d; dwIndex
0x140007e63  call    cs:__imp_RegEnumKeyExW
0x140007e69  xor     edx, edx
0x140007e6b  mov     ebx, eax
0x140007e6d  test    eax, eax
0x140007e6f  jnz     short loc_140007E84
0x140007e71  mov     rdx, rsi
0x140007e74  mov     rcx, r12
0x140007e77  call    DynArrayAppendString
0x140007e7c  cmp     eax, 0FFFFFFFFh
0x140007e7f  cmovz   ebx, edi
0x140007e82  xor     edx, edx
0x140007e84  inc     r14d
0x140007e87  cmp     r14d, [rbp+3Fh+cSubKeys]
0x140007e8b  jb      short loc_140007E1E
0x140007e8d  mov     r15, [rbp+3Fh+arg_30]
0x140007e91  mov     [rbp+3Fh+var_98], ebx
0x140007e94  mov     r14d, edx
0x140007e97  cmp     [rbp+3Fh+var_90], edx
0x140007e9a  jbe     loc_140007F22
0x140007ea0  mov     r15, [rbp+3Fh+var_70]
0x140007ea4  mov     r13, [rbp+3Fh+arg_10]
0x140007ea8  test    ebx, ebx
0x140007eaa  jz      short loc_140007EB1
0x140007eac  cmp     ebx, 5
0x140007eaf  jnz     short loc_140007F17
0x140007eb1  mov     eax, [rbp+3Fh+var_94]
0x140007eb4  mov     ecx, eax
0x140007eb6  mov     [rbp+3Fh+cchName], eax
0x140007eb9  mov     rax, rsi
0x140007ebc  add     rcx, rcx
0x140007ebf  jz      short loc_140007ECC
0x140007ec1  mov     [rax], dl
0x140007ec3  inc     rax
0x140007ec6  sub     rcx, 1
0x140007eca  jnz     short loc_140007EC1
0x140007ecc  mov     [rsp+100h+lpcValues], rdx; lpftLastWriteTime
0x140007ed1  lea     r9, [rbp+3Fh+cchName]; lpcchName
0x140007ed5  mov     [rsp+100h+lpcbMaxClassLen], rdx; lpcchClass
0x140007eda  mov     r8, rsi; lpName
0x140007edd  mov     [rsp+100h+lpcbMaxSubKeyLen], rdx; lpClass
0x140007ee2  mov     rcx, r13; hKey
0x140007ee5  mov     [rsp+100h+lpcSubKeys], rdx; lpReserved
0x140007eea  mov     edx, r14d; dwIndex
0x140007eed  call    cs:__imp_RegEnumKeyExW
0x140007ef3  xor     edx, edx
0x140007ef5  mov     ebx, eax
0x140007ef7  test    eax, eax
0x140007ef9  jnz     short loc_140007F0E
0x140007efb  mov     rdx, rsi
0x140007efe  mov     rcx, r15
0x140007f01  call    DynArrayAppendString
0x140007f06  cmp     eax, 0FFFFFFFFh
0x140007f09  cmovz   ebx, edi
0x140007f0c  xor     edx, edx
0x140007f0e  inc     r14d
0x140007f11  cmp     r14d, [rbp+3Fh+var_90]
0x140007f15  jb      short loc_140007EA8
0x140007f17  mov     r15, [rbp+3Fh+arg_30]
0x140007f1b  mov     r13d, [rbp+3Fh+arg_20]
0x140007f1f  mov     [rbp+3Fh+var_98], ebx
0x140007f22  lea     rcx, [rbp+3Fh+var_48]
0x140007f26  call    FreeMemory
0x140007f2b  test    ebx, ebx
0x140007f2d  jnz     short loc_140007F8B
0x140007f2f  mov     rcx, [rbp+3Fh+lpString]; lpString
0x140007f33  call    cs:__imp_lstrlenW
0x140007f39  mov     ecx, eax
0x140007f3b  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x140007f3e  add     eax, 5
0x140007f41  add     ecx, eax
0x140007f43  mov     [rbp+3Fh+cbMaxSubKeyLen], ecx
0x140007f46  mov     rcx, [rbp+3Fh+arg_18]; lpString
0x140007f4a  call    cs:__imp_lstrlenW
0x140007f50  mov     ecx, eax
0x140007f52  mov     eax, [rbp+3Fh+var_94]
0x140007f55  add     eax, 5
0x140007f58  add     ecx, eax
0x140007f5a  mov     [rbp+3Fh+var_94], ecx
0x140007f5d  mov     ecx, [rbp+3Fh+cbMaxSubKeyLen]
0x140007f60  add     ecx, ecx; dwBytes
0x140007f62  call    AllocateMemory
0x140007f67  mov     [rbp+3Fh+var_68], rax
0x140007f6b  test    rax, rax
0x140007f6e  jnz     short loc_140007F74
0x140007f70  mov     ebx, edi
0x140007f72  jmp     short loc_140007F88
0x140007f74  mov     ecx, [rbp+3Fh+var_94]
0x140007f77  add     ecx, ecx; dwBytes
0x140007f79  call    AllocateMemory
0x140007f7e  test    rax, rax
0x140007f81  mov     [rbp+3Fh+var_60], rax
0x140007f85  cmovz   ebx, edi
0x140007f88  mov     [rbp+3Fh+var_98], ebx
0x140007f8b  xor     esi, esi
0x140007f8d  cmp     [rbp+3Fh+cSubKeys], esi
0x140007f90  jbe     loc_1400081D6
0x140007f96  mov     r14, [rbp+3Fh+var_70]
0x140007f9a  test    ebx, ebx
0x140007f9c  jnz     loc_1400081D6
0x140007fa2  xor     r8d, r8d
0x140007fa5  mov     edx, esi
0x140007fa7  mov     rcx, r12
0x140007faa  call    __DynArrayGetItem
0x140007faf  test    rax, rax
0x140007fb2  jnz     short loc_140007FB8
0x140007fb4  xor     edi, edi
0x140007fb6  jmp     short loc_140007FC5
0x140007fb8  cmp     dword ptr [rax+4], 20000h
0x140007fbf  jnz     short loc_140007FB4
0x140007fc1  mov     rdi, [rax+10h]
0x140007fc5  mov     r8, rdi
  ... truncated ...
```
