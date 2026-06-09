# CompareEnumerateKey

- ea: `0x1400080a4`
- end: `0x140008830`
- name: `CompareEnumerateKey`
- size: `1932`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, HKEY, const WCHAR *, unsigned int, int, _DWORD *, int, int, _DWORD *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400080a4`
- `0x140008cbc`

## callees

- `0x140002ce4`
- `0x1400080a4`
- `0x140008838`
- `0x140009a50`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000ef5c`
- `0x14000f0c0`
- `0x14000f294`
- `0x14000f2c4`
- `0x14000f43c`
- `0x14000f5c8`
- `0x14000f78c`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400085a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400085a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140008337`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400083c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140008337`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400083c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400085c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008673`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008690`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400087b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400087d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400085c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008673`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008690`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400087b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400087d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400081a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000821a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400081a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000821a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008413`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008430`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008413`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008430`

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
  __int64 v37; // rbx
  __int64 v38; // rbx
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
  __int64 Memory; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-21h] BYREF
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
    v15 = CompareEnumerateValueName(a1, a5, (__int64)a7);
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
                        Memory,
                        (_DWORD)phkResult,
                        v58,
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
0x1400080a4  mov     rax, rsp
0x1400080a7  mov     [rax+20h], r9
0x1400080ab  mov     [rax+18h], r8
0x1400080af  mov     [rax+10h], rdx
0x1400080b3  mov     [rax+8], rcx
0x1400080b7  push    rbp
0x1400080b8  push    rbx
0x1400080b9  push    rsi
0x1400080ba  push    rdi
0x1400080bb  push    r12
0x1400080bd  push    r13
0x1400080bf  push    r14
0x1400080c1  push    r15
0x1400080c3  lea     rbp, [rax-47h]
0x1400080c7  sub     rsp, 0C8h
0x1400080ce  xor     r14d, r14d
0x1400080d1  mov     rdi, r8
0x1400080d4  mov     [rbp+3Fh+cchName], r14d
0x1400080d8  mov     rax, rdx
0x1400080db  mov     [rbp+3Fh+cSubKeys], r14d
0x1400080df  mov     rsi, rcx
0x1400080e2  mov     [rbp+3Fh+var_90], r14d
0x1400080e6  mov     [rbp+3Fh+hKey], r14
0x1400080ea  mov     [rbp+3Fh+phkResult], r14
0x1400080ee  mov     [rbp+3Fh+cbMaxSubKeyLen], r14d
0x1400080f2  mov     [rbp+3Fh+var_94], r14d
0x1400080f6  mov     [rbp+3Fh+var_68], r14
0x1400080fa  mov     [rbp+3Fh+var_60], r14
0x1400080fe  test    rcx, rcx
0x140008101  jz      loc_14000880D
0x140008107  test    rax, rax
0x14000810a  jz      loc_14000880D
0x140008110  test    r8, r8
0x140008113  jz      loc_14000880D
0x140008119  test    r9, r9
0x14000811c  jz      loc_14000880D
0x140008122  mov     r15, [rbp+3Fh+arg_30]
0x140008126  test    r15, r15
0x140008129  jz      loc_14000880D
0x14000812f  mov     r13d, [rbp+3Fh+arg_20]
0x140008133  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; __int64
0x140008138  mov     dword ptr [rsp+100h+lpcSubKeys], r13d; int
0x14000813d  call    CompareEnumerateValueName
0x140008142  mov     ebx, eax
0x140008144  cmp     [rbp+3Fh+arg_28], r14d
0x140008148  jz      loc_140008812
0x14000814e  test    eax, eax
0x140008150  jnz     loc_140008812
0x140008156  cmp     r13d, 1
0x14000815a  ja      short loc_140008169
0x14000815c  cmp     dword ptr [r15], 1
0x140008160  jnz     short loc_140008169
0x140008162  xor     eax, eax
0x140008164  jmp     loc_14000881B
0x140008169  mov     [rsp+58h], r14; lpftLastWriteTime
0x14000816e  lea     rax, [rbp+3Fh+cbMaxSubKeyLen]
0x140008172  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140008177  xor     r9d, r9d; lpReserved
0x14000817a  mov     [rsp+100h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14000817f  xor     r8d, r8d; lpcchClass
0x140008182  mov     [rsp+100h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140008187  xor     edx, edx; lpClass
0x140008189  mov     [rsp+100h+lpcValues], r14; lpcValues
0x14000818e  mov     rcx, rsi; hKey
0x140008191  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140008196  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14000819b  lea     rax, [rbp+3Fh+cSubKeys]
0x14000819f  mov     [rsp+100h+lpcSubKeys], rax; lpcSubKeys
0x1400081a4  call    cs:__imp_RegQueryInfoKeyW
0x1400081ab  nop     dword ptr [rax+rax+00h]
0x1400081b0  mov     ebx, eax
0x1400081b2  test    eax, eax
0x1400081b4  jnz     loc_140008812
0x1400081ba  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x1400081bd  cmp     [rbp+3Fh+cSubKeys], r14d
0x1400081c1  jz      short loc_1400081D1
0x1400081c3  test    eax, eax
0x1400081c5  jnz     short loc_1400081D1
0x1400081c7  mov     ebx, 100h
0x1400081cc  mov     [rbp+3Fh+cbMaxSubKeyLen], ebx
0x1400081cf  jmp     short loc_1400081DF
0x1400081d1  mov     ebx, 100h
0x1400081d6  cmp     eax, ebx
0x1400081d8  jnb     short loc_1400081DF
0x1400081da  add     eax, eax
0x1400081dc  mov     [rbp+3Fh+cbMaxSubKeyLen], eax
0x1400081df  mov     [rsp+58h], r14; lpftLastWriteTime
0x1400081e4  lea     rax, [rbp+3Fh+var_94]
0x1400081e8  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1400081ed  xor     r9d, r9d; lpReserved
0x1400081f0  mov     [rsp+100h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1400081f5  xor     r8d, r8d; lpcchClass
0x1400081f8  mov     [rsp+100h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1400081fd  xor     edx, edx; lpClass
0x1400081ff  mov     [rsp+100h+lpcValues], r14; lpcValues
0x140008204  mov     rcx, rdi; hKey
0x140008207  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x14000820c  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140008211  lea     rax, [rbp+3Fh+var_90]
0x140008215  mov     [rsp+100h+lpcSubKeys], rax; lpcSubKeys
0x14000821a  call    cs:__imp_RegQueryInfoKeyW
0x140008221  nop     dword ptr [rax+rax+00h]
0x140008226  mov     edi, eax
0x140008228  test    eax, eax
0x14000822a  jz      short loc_14000823A
0x14000822c  mov     ecx, edi
0x14000822e  call    SaveErrorMessage
0x140008233  mov     eax, edi
0x140008235  jmp     loc_14000881B
0x14000823a  mov     edx, [rbp+3Fh+var_90]
0x14000823d  mov     eax, [rbp+3Fh+var_94]
0x140008240  test    edx, edx
0x140008242  jz      short loc_14000824C
0x140008244  test    eax, eax
0x140008246  jnz     short loc_14000824C
0x140008248  mov     eax, ebx
0x14000824a  jmp     short loc_140008252
0x14000824c  cmp     eax, ebx
0x14000824e  jnb     short loc_140008252
0x140008250  add     eax, eax
0x140008252  mov     ecx, [rbp+3Fh+cbMaxSubKeyLen]
0x140008255  cmp     r13d, 1
0x140008259  ja      short loc_140008270
0x14000825b  cmp     [rbp+3Fh+cSubKeys], edx
0x14000825e  jnz     short loc_140008264
0x140008260  cmp     ecx, eax
0x140008262  jz      short loc_140008270
0x140008264  mov     dword ptr [r15], 1
0x14000826b  jmp     loc_140008162
0x140008270  inc     eax
0x140008272  inc     ecx
0x140008274  mov     [rbp+3Fh+var_94], eax
0x140008277  mov     [rbp+3Fh+cbMaxSubKeyLen], ecx
0x14000827a  cmp     eax, ecx
0x14000827c  jbe     short loc_140008283
0x14000827e  mov     [rbp+3Fh+cbMaxSubKeyLen], eax
0x140008281  jmp     short loc_140008286
0x140008283  mov     [rbp+3Fh+var_94], ecx
0x140008286  call    CreateDynamicArray
0x14000828b  mov     [rbp+3Fh+var_50], rax
0x14000828f  mov     r12, rax
0x140008292  test    rax, rax
0x140008295  jnz     short loc_14000829E
0x140008297  mov     edi, 0Eh
0x14000829c  jmp     short loc_14000822C
0x14000829e  call    CreateDynamicArray
0x1400082a3  mov     [rbp+3Fh+var_70], rax
0x1400082a7  test    rax, rax
0x1400082aa  jnz     short loc_1400082B7
0x1400082ac  lea     rcx, [rbp+3Fh+var_50]
0x1400082b0  call    DestroyDynamicArray
0x1400082b5  jmp     short loc_140008297
0x1400082b7  mov     ecx, [rbp+3Fh+cbMaxSubKeyLen]
0x1400082ba  add     ecx, ecx; dwBytes
0x1400082bc  call    AllocateMemory
0x1400082c1  mov     [rbp+3Fh+var_48], rax
0x1400082c5  mov     rsi, rax
0x1400082c8  test    rax, rax
0x1400082cb  jnz     short loc_1400082D8
0x1400082cd  lea     rcx, [rbp+3Fh+var_70]
0x1400082d1  call    DestroyDynamicArray
0x1400082d6  jmp     short loc_1400082AC
0x1400082d8  xor     edx, edx
0x1400082da  mov     ebx, r14d
0x1400082dd  mov     edi, 0Eh
0x1400082e2  mov     [rbp+3Fh+var_98], ebx
0x1400082e5  cmp     [rbp+3Fh+cSubKeys], edx
0x1400082e8  jbe     loc_14000836E
0x1400082ee  mov     r15, [rbp+3Fh+arg_0]
0x1400082f2  test    ebx, ebx
0x1400082f4  jz      short loc_1400082FB
0x1400082f6  cmp     ebx, 5
0x1400082f9  jnz     short loc_140008367
0x1400082fb  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x1400082fe  mov     ecx, eax
0x140008300  mov     [rbp+3Fh+cchName], eax
0x140008303  mov     rax, rsi
0x140008306  add     rcx, rcx
0x140008309  jz      short loc_140008316
0x14000830b  mov     [rax], dl
0x14000830d  inc     rax
0x140008310  sub     rcx, 1
0x140008314  jnz     short loc_14000830B
0x140008316  mov     [rsp+100h+lpcValues], rdx; lpftLastWriteTime
0x14000831b  lea     r9, [rbp+3Fh+cchName]; lpcchName
0x14000831f  mov     [rsp+100h+lpcbMaxClassLen], rdx; lpcchClass
0x140008324  mov     r8, rsi; lpName
0x140008327  mov     [rsp+100h+lpcbMaxSubKeyLen], rdx; lpClass
0x14000832c  mov     rcx, r15; hKey
0x14000832f  mov     [rsp+100h+lpcSubKeys], rdx; lpReserved
0x140008334  mov     edx, r14d; dwIndex
0x140008337  call    cs:__imp_RegEnumKeyExW
0x14000833e  nop     dword ptr [rax+rax+00h]
0x140008343  xor     edx, edx
0x140008345  mov     ebx, eax
0x140008347  test    eax, eax
0x140008349  jnz     short loc_14000835E
0x14000834b  mov     rdx, rsi
0x14000834e  mov     rcx, r12
0x140008351  call    DynArrayAppendString
0x140008356  cmp     eax, 0FFFFFFFFh
0x140008359  cmovz   ebx, edi
0x14000835c  xor     edx, edx
0x14000835e  inc     r14d
0x140008361  cmp     r14d, [rbp+3Fh+cSubKeys]
0x140008365  jb      short loc_1400082F2
0x140008367  mov     r15, [rbp+3Fh+arg_30]
0x14000836b  mov     [rbp+3Fh+var_98], ebx
0x14000836e  mov     r14d, edx
0x140008371  cmp     [rbp+3Fh+var_90], edx
0x140008374  jbe     loc_140008402
0x14000837a  mov     r15, [rbp+3Fh+var_70]
0x14000837e  mov     r13, [rbp+3Fh+arg_10]
0x140008382  test    ebx, ebx
0x140008384  jz      short loc_14000838B
0x140008386  cmp     ebx, 5
0x140008389  jnz     short loc_1400083F7
0x14000838b  mov     eax, [rbp+3Fh+var_94]
0x14000838e  mov     ecx, eax
0x140008390  mov     [rbp+3Fh+cchName], eax
0x140008393  mov     rax, rsi
0x140008396  add     rcx, rcx
0x140008399  jz      short loc_1400083A6
0x14000839b  mov     [rax], dl
0x14000839d  inc     rax
0x1400083a0  sub     rcx, 1
0x1400083a4  jnz     short loc_14000839B
0x1400083a6  mov     [rsp+100h+lpcValues], rdx; lpftLastWriteTime
0x1400083ab  lea     r9, [rbp+3Fh+cchName]; lpcchName
0x1400083af  mov     [rsp+100h+lpcbMaxClassLen], rdx; lpcchClass
0x1400083b4  mov     r8, rsi; lpName
0x1400083b7  mov     [rsp+100h+lpcbMaxSubKeyLen], rdx; lpClass
0x1400083bc  mov     rcx, r13; hKey
0x1400083bf  mov     [rsp+100h+lpcSubKeys], rdx; lpReserved
0x1400083c4  mov     edx, r14d; dwIndex
0x1400083c7  call    cs:__imp_RegEnumKeyExW
0x1400083ce  nop     dword ptr [rax+rax+00h]
0x1400083d3  xor     edx, edx
0x1400083d5  mov     ebx, eax
0x1400083d7  test    eax, eax
0x1400083d9  jnz     short loc_1400083EE
0x1400083db  mov     rdx, rsi
0x1400083de  mov     rcx, r15
0x1400083e1  call    DynArrayAppendString
0x1400083e6  cmp     eax, 0FFFFFFFFh
0x1400083e9  cmovz   ebx, edi
0x1400083ec  xor     edx, edx
0x1400083ee  inc     r14d
0x1400083f1  cmp     r14d, [rbp+3Fh+var_90]
0x1400083f5  jb      short loc_140008382
0x1400083f7  mov     r15, [rbp+3Fh+arg_30]
0x1400083fb  mov     r13d, [rbp+3Fh+arg_20]
0x1400083ff  mov     [rbp+3Fh+var_98], ebx
0x140008402  lea     rcx, [rbp+3Fh+var_48]
0x140008406  call    FreeMemory
0x14000840b  test    ebx, ebx
0x14000840d  jnz     short loc_140008477
0x14000840f  mov     rcx, [rbp+3Fh+lpString]; lpString
0x140008413  call    cs:__imp_lstrlenW
0x14000841a  nop     dword ptr [rax+rax+00h]
0x14000841f  mov     ecx, eax
0x140008421  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x140008424  add     eax, 5
0x140008427  add     ecx, eax
0x140008429  mov     [rbp+3Fh+cbMaxSubKeyLen], ecx
0x14000842c  mov     rcx, [rbp+3Fh+arg_18]; lpString
0x140008430  call    cs:__imp_lstrlenW
0x140008437  nop     dword ptr [rax+rax+00h]
0x14000843c  mov     ecx, eax
0x14000843e  mov     eax, [rbp+3Fh+var_94]
0x140008441  add     eax, 5
0x140008444  add     ecx, eax
0x140008446  mov     [rbp+3Fh+var_94], ecx
0x140008449  mov     ecx, [rbp+3Fh+cbMaxSubKeyLen]
0x14000844c  add     ecx, ecx; dwBytes
0x14000844e  call    AllocateMemory
0x140008453  mov     [rbp+3Fh+var_68], rax
0x140008457  test    rax, rax
0x14000845a  jnz     short loc_140008460
0x14000845c  mov     ebx, edi
0x14000845e  jmp     short loc_140008474
0x140008460  mov     ecx, [rbp+3Fh+var_94]
0x140008463  add     ecx, ecx; dwBytes
0x140008465  call    AllocateMemory
0x14000846a  test    rax, rax
0x14000846d  mov     [rbp+3Fh+var_60], rax
0x140008471  cmovz   ebx, edi
0x140008474  mov     [rbp+3Fh+var_98], ebx
0x140008477  xor     esi, esi
0x140008479  cmp     [rbp+3Fh+cSubKeys], esi
0x14000847c  jbe     loc_1400086E0
0x140008482  mov     r14, [rbp+3Fh+var_70]
0x140008486  test    ebx, ebx
0x140008488  jnz     loc_1400086E0
0x14000848e  xor     r8d, r8d
0x140008491  mov     edx, esi
0x140008493  mov     rcx, r12
0x140008496  call    __DynArrayGetItem
0x14000849b  test    rax, rax
0x14000849e  jnz     short loc_1400084A4
  ... truncated ...
```
