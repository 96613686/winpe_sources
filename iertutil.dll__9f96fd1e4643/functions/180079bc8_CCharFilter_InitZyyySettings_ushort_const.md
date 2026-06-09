# CCharFilter::InitZyyySettings(ushort const * *)

- ea: `0x180079bc8`
- end: `0x18007a003`
- name: `?InitZyyySettings@CCharFilter@@AEAAJPEAPEBG@Z`
- size: `1083`
- prototype: `__int64 __fastcall(CCharFilter *__hidden this, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800797f4`

## callees

- `0x1800798a4`
- `0x180079bc8`
- `0x180083bc2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079c23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079d23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079d79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079ddd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079e19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079c23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079d23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079d79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079ddd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079e19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079d15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079d6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079dcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079f48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079f7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079f99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079d15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079d6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079dcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079f48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079f7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079f99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079fd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079f8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079f8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180079c6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180079c6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079f35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079f35`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180079cc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180079cc2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180079e9b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180079e9b`

## string_xrefs

- `0x180079c60`: `Software\Microsoft\Internet Explorer\International\MixScripts\Common`

## pseudocode

```c
__int64 __fastcall CCharFilter::InitZyyySettings(CCharFilter *this, const unsigned __int16 **a2)
{
  unsigned __int64 v2; // r8
  unsigned __int16 **v3; // rsi
  bool v4; // r15
  const unsigned __int16 **v5; // r12
  unsigned __int16 **v6; // r14
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  int v11; // edi
  CCharFilter *v12; // rcx
  SIZE_T v13; // rbx
  HANDLE v14; // rax
  unsigned __int16 **v15; // rax
  SIZE_T v16; // rbx
  HANDLE v17; // rax
  unsigned __int16 **v18; // rax
  __int64 j; // rdi
  DWORD v20; // eax
  SIZE_T v21; // rbx
  HANDLE v22; // rax
  unsigned __int16 *v23; // rax
  unsigned __int64 v24; // rcx
  SIZE_T v25; // rbx
  HANDLE v26; // rax
  unsigned __int16 *v27; // rax
  DWORD v28; // ebx
  DWORD k; // edi
  LSTATUS v30; // eax
  __int64 i; // r15
  unsigned __int16 *ListOfChars; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  __int64 m; // rdi
  unsigned __int16 *v36; // rbx
  HANDLE v37; // rax
  HANDLE v38; // rax
  __int64 n; // rdi
  unsigned __int16 *v40; // rbx
  HANDLE v41; // rax
  HANDLE v42; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-9h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-5h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  char v48; // [rsp+D0h] [rbp+67h]
  DWORD cValues; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = *((unsigned int *)this + 4);
  v3 = 0;
  v4 = 0;
  hKey = 0;
  v5 = a2;
  v48 = 0;
  v6 = 0;
  cValues = 0;
  v8 = 8 * v2;
  if ( !is_mul_ok(v2, 8u) )
    v8 = -1;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, v8);
  *((_QWORD *)this + 1) = v10;
  if ( !v10 )
  {
    v11 = -2147024882;
    goto LABEL_42;
  }
  memset_0(v10, 0, 8LL * *((unsigned int *)this + 4));
  if ( RegOpenKeyExA(
         HKEY_CURRENT_USER,
         "Software\\Microsoft\\Internet Explorer\\International\\MixScripts\\Common",
         0,
         0x20019u,
         &hKey) )
  {
    cValues = 2;
    v6 = (unsigned __int16 **)&CCharFilter::s_ppwzScriptArr;
    v3 = (unsigned __int16 **)&CCharFilter::s_ppwzZyyChars;
    v11 = 0;
LABEL_39:
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
    {
      ListOfChars = CCharFilter::GetListOfChars(v12, v5[i], v6, v3, cValues);
      v12 = (CCharFilter *)*((_QWORD *)this + 1);
      *((_QWORD *)v12 + i) = ListOfChars;
    }
    goto LABEL_41;
  }
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
  {
    v12 = (CCharFilter *)cValues;
    if ( cValues )
    {
      if ( cbMaxValueNameLen && cbMaxValueLen )
      {
        cchValueName = 0;
        cbData = 0;
        ++cbMaxValueNameLen;
        v13 = 8LL * cValues;
        if ( !is_mul_ok(cValues, 8u) )
          v13 = -1;
        v14 = GetProcessHeap();
        v15 = (unsigned __int16 **)HeapAlloc(v14, 8u, v13);
        v6 = v15;
        if ( !v15 )
        {
          v11 = -2147024882;
          v4 = 0;
          goto LABEL_42;
        }
        v48 = 1;
        memset_0(v15, 0, 8LL * cValues);
        v16 = 8LL * cValues;
        if ( !is_mul_ok(cValues, 8u) )
          v16 = -1;
        v17 = GetProcessHeap();
        v18 = (unsigned __int16 **)HeapAlloc(v17, 8u, v16);
        v3 = v18;
        if ( !v18 )
        {
          v11 = -2147024882;
          v4 = 1;
          goto LABEL_42;
        }
        memset_0(v18, 0, 8LL * cValues);
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v20 = cValues;
          if ( (unsigned int)j >= cValues )
            break;
          v21 = 2LL * cbMaxValueNameLen;
          if ( !is_mul_ok(cbMaxValueNameLen, 2u) )
            v21 = -1;
          v22 = GetProcessHeap();
          v23 = (unsigned __int16 *)HeapAlloc(v22, 8u, v21);
          v6[j] = v23;
          if ( !v23 )
          {
            v11 = -2147024882;
            goto LABEL_41;
          }
          v24 = (unsigned __int64)cbMaxValueLen >> 1;
          v25 = 2 * v24;
          if ( !is_mul_ok(v24, 2u) )
            v25 = -1;
          v26 = GetProcessHeap();
          v27 = (unsigned __int16 *)HeapAlloc(v26, 8u, v25);
          v3[j] = v27;
          if ( !v27 )
          {
            v4 = 1;
            v11 = -2147024882;
            goto LABEL_42;
          }
        }
        v28 = 0;
        for ( k = 0; k < cValues; ++k )
        {
          if ( v28 >= v20 )
            break;
          cchValueName = cbMaxValueNameLen;
          cbData = cbMaxValueLen;
          v30 = RegEnumValueW(hKey, k, v6[v28], &cchValueName, 0, 0, (LPBYTE)v3[v28], &cbData);
          v12 = (CCharFilter *)(v28 + 1);
          if ( v30 )
            v12 = (CCharFilter *)v28;
          v28 = (unsigned int)v12;
          if ( v30 == 259 )
            break;
          v20 = cValues;
        }
        cValues = v28;
        v4 = v28 != 0;
        v5 = a2;
      }
    }
  }
  v11 = 0;
  if ( v4 )
    goto LABEL_39;
LABEL_41:
  v4 = v48;
LABEL_42:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( v11 < 0 )
  {
    v33 = (void *)*((_QWORD *)this + 1);
    if ( v33 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v33);
      *((_QWORD *)this + 1) = 0;
    }
  }
  if ( v4 )
  {
    if ( v6 )
    {
      for ( m = 0; (unsigned int)m < cValues; m = (unsigned int)(m + 1) )
      {
        v36 = v6[m];
        v37 = GetProcessHeap();
        HeapFree(v37, 0, v36);
      }
      v38 = GetProcessHeap();
      HeapFree(v38, 0, v6);
    }
    if ( v3 )
    {
      for ( n = 0; (unsigned int)n < cValues; n = (unsigned int)(n + 1) )
      {
        v40 = v3[n];
        v41 = GetProcessHeap();
        HeapFree(v41, 0, v40);
      }
      v42 = GetProcessHeap();
      HeapFree(v42, 0, v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180079bc8  mov     [rsp-8+arg_8], rdx
0x180079bcd  push    rbp
0x180079bce  push    rbx
0x180079bcf  push    rsi
0x180079bd0  push    rdi
0x180079bd1  push    r12
0x180079bd3  push    r13
0x180079bd5  push    r14
0x180079bd7  push    r15
0x180079bd9  lea     rbp, [rsp-1Fh]
0x180079bde  sub     rsp, 88h
0x180079be5  mov     r8d, [rcx+10h]
0x180079be9  xor     esi, esi
0x180079beb  xor     r15b, r15b
0x180079bee  mov     [rbp+57h+hKey], rsi
0x180079bf2  mov     r12, rdx
0x180079bf5  mov     [rbp+57h+arg_0], r15b
0x180079bf9  xor     r14d, r14d
0x180079bfc  mov     [rbp+57h+cValues], esi
0x180079bff  lea     edi, [rsi+8]
0x180079c02  mov     r13, rcx
0x180079c05  mov     eax, edi
0x180079c07  mul     r8
0x180079c0a  mov     rbx, rax
0x180079c0d  lea     rax, [rsi-1]
0x180079c11  cmovb   rbx, rax
0x180079c15  call    cs:__imp_GetProcessHeap
0x180079c1b  mov     r8, rbx; dwBytes
0x180079c1e  mov     edx, edi; dwFlags
0x180079c20  mov     rcx, rax; hHeap
0x180079c23  call    cs:__imp_HeapAlloc
0x180079c29  mov     [r13+8], rax
0x180079c2d  test    rax, rax
0x180079c30  jnz     short loc_180079C3C
0x180079c32  mov     edi, 8007000Eh
0x180079c37  jmp     loc_180079F21
0x180079c3c  mov     r8d, [r13+10h]
0x180079c40  xor     edx, edx; Val
0x180079c42  shl     r8, 3; Size
0x180079c46  mov     rcx, rax; void *
0x180079c49  call    memset_0
0x180079c4e  lea     rax, [rbp+57h+hKey]
0x180079c52  mov     r9d, 20019h; samDesired
0x180079c58  xor     r8d, r8d; ulOptions
0x180079c5b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180079c60  lea     rdx, aSoftwareMicros_27; "Software\\Microsoft\\Internet Explorer"...
0x180079c67  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180079c6e  call    cs:__imp_RegOpenKeyExA
0x180079c74  test    eax, eax
0x180079c76  jnz     loc_180079ED6
0x180079c7c  mov     rcx, [rbp+57h+hKey]; hKey
0x180079c80  lea     rax, [rbp+57h+cbMaxValueLen]
0x180079c84  mov     [rsp+0C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180079c89  xor     r9d, r9d; lpReserved
0x180079c8c  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180079c91  xor     r8d, r8d; lpcchClass
0x180079c94  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180079c99  xor     edx, edx; lpClass
0x180079c9b  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180079c9f  mov     [rbp+57h+cbMaxValueNameLen], esi
0x180079ca2  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180079ca7  lea     rax, [rbp+57h+cValues]
0x180079cab  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x180079cb0  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180079cb5  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180079cba  mov     [rsp+0C0h+phkResult], rsi; lpcSubKeys
0x180079cbf  mov     [rbp+57h+cbMaxValueLen], esi
0x180079cc2  call    cs:__imp_RegQueryInfoKeyW
0x180079cc8  test    eax, eax
0x180079cca  jnz     loc_180079ECD
0x180079cd0  mov     ecx, [rbp+57h+cValues]
0x180079cd3  test    ecx, ecx
0x180079cd5  jz      loc_180079ECD
0x180079cdb  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180079cde  test    eax, eax
0x180079ce0  jz      loc_180079ECD
0x180079ce6  cmp     [rbp+57h+cbMaxValueLen], esi
0x180079ce9  jbe     loc_180079ECD
0x180079cef  mov     r12d, 1
0x180079cf5  mov     [rbp+57h+cchValueName], esi
0x180079cf8  add     eax, r12d
0x180079cfb  mov     [rbp+57h+cbData], esi
0x180079cfe  mov     [rbp+57h+cbMaxValueNameLen], eax
0x180079d01  mov     rax, rdi
0x180079d04  mul     rcx
0x180079d07  mov     rbx, rax
0x180079d0a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180079d11  cmovb   rbx, rax
0x180079d15  call    cs:__imp_GetProcessHeap
0x180079d1b  mov     r8, rbx; dwBytes
0x180079d1e  mov     edx, edi; dwFlags
0x180079d20  mov     rcx, rax; hHeap
0x180079d23  call    cs:__imp_HeapAlloc
0x180079d29  mov     r14, rax
0x180079d2c  test    rax, rax
0x180079d2f  jnz     short loc_180079D3E
0x180079d31  mov     edi, 8007000Eh
0x180079d36  mov     r15b, sil
0x180079d39  jmp     loc_180079F27
0x180079d3e  mov     r8d, [rbp+57h+cValues]
0x180079d42  xor     edx, edx; Val
0x180079d44  shl     r8, 3; Size
0x180079d48  mov     rcx, r14; void *
0x180079d4b  mov     [rbp+57h+arg_0], r12b
0x180079d4f  call    memset_0
0x180079d54  mov     ecx, [rbp+57h+cValues]
0x180079d57  mov     rax, rdi
0x180079d5a  mul     rcx
0x180079d5d  mov     rbx, rax
0x180079d60  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180079d67  cmovb   rbx, rax
0x180079d6b  call    cs:__imp_GetProcessHeap
0x180079d71  mov     r8, rbx; dwBytes
0x180079d74  mov     edx, edi; dwFlags
0x180079d76  mov     rcx, rax; hHeap
0x180079d79  call    cs:__imp_HeapAlloc
0x180079d7f  mov     rsi, rax
0x180079d82  test    rax, rax
0x180079d85  jnz     short loc_180079D94
0x180079d87  mov     edi, 8007000Eh
0x180079d8c  mov     r15b, r12b
0x180079d8f  jmp     loc_180079F27
0x180079d94  mov     r8d, [rbp+57h+cValues]
0x180079d98  xor     edx, edx; Val
0x180079d9a  shl     r8, 3; Size
0x180079d9e  mov     rcx, rsi; void *
0x180079da1  call    memset_0
0x180079da6  xor     edi, edi
0x180079da8  mov     eax, [rbp+57h+cValues]
0x180079dab  cmp     edi, eax
0x180079dad  jnb     loc_180079E4E
0x180079db3  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180079db6  mov     eax, 2
0x180079dbb  mul     rcx
0x180079dbe  mov     rbx, rax
0x180079dc1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180079dc8  cmovb   rbx, rax
0x180079dcc  call    cs:__imp_GetProcessHeap
0x180079dd2  mov     r8, rbx; dwBytes
0x180079dd5  mov     edx, 8; dwFlags
0x180079dda  mov     rcx, rax; hHeap
0x180079ddd  call    cs:__imp_HeapAlloc
0x180079de3  mov     [r14+rdi*8], rax
0x180079de7  test    rax, rax
0x180079dea  jz      short loc_180079E44
0x180079dec  mov     ecx, [rbp+57h+cbMaxValueLen]
0x180079def  mov     eax, 2
0x180079df4  shr     rcx, 1
0x180079df7  mul     rcx
0x180079dfa  mov     rbx, rax
0x180079dfd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180079e04  cmovb   rbx, rax
0x180079e08  call    cs:__imp_GetProcessHeap
0x180079e0e  mov     r8, rbx; dwBytes
0x180079e11  mov     edx, 8; dwFlags
0x180079e16  mov     rcx, rax; hHeap
0x180079e19  call    cs:__imp_HeapAlloc
0x180079e1f  mov     [rsi+rdi*8], rax
0x180079e23  mov     r12d, 1
0x180079e29  test    rax, rax
0x180079e2c  jz      short loc_180079E36
0x180079e2e  add     edi, r12d
0x180079e31  jmp     loc_180079DA8
0x180079e36  mov     r15b, [rbp+57h+arg_0]
0x180079e3a  mov     edi, 8007000Eh
0x180079e3f  jmp     loc_180079F27
0x180079e44  mov     edi, 8007000Eh
0x180079e49  jmp     loc_180079F1D
0x180079e4e  xor     ebx, ebx
0x180079e50  xor     edi, edi
0x180079e52  test    eax, eax
0x180079e54  jz      short loc_180079EBC
0x180079e56  cmp     ebx, eax
0x180079e58  jnb     short loc_180079EBC
0x180079e5a  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180079e5d  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180079e61  mov     rcx, [rbp+57h+hKey]; hKey
0x180079e65  mov     edx, edi; dwIndex
0x180079e67  mov     [rbp+57h+cchValueName], eax
0x180079e6a  mov     eax, [rbp+57h+cbMaxValueLen]
0x180079e6d  mov     [rbp+57h+cbData], eax
0x180079e70  lea     rax, [rbp+57h+cbData]
0x180079e74  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x180079e79  mov     r8d, ebx
0x180079e7c  mov     rax, [rsi+r8*8]
0x180079e80  mov     r8, [r14+r8*8]; lpValueName
0x180079e84  mov     [rsp+0C0h+lpcbMaxClassLen], rax; lpData
0x180079e89  mov     [rsp+0C0h+lpcbMaxSubKeyLen], 0; lpType
0x180079e92  mov     [rsp+0C0h+phkResult], 0; lpReserved
0x180079e9b  call    cs:__imp_RegEnumValueW
0x180079ea1  test    eax, eax
0x180079ea3  lea     ecx, [rbx+1]
0x180079ea6  cmovnz  ecx, ebx
0x180079ea9  mov     ebx, ecx
0x180079eab  cmp     eax, 103h
0x180079eb0  jz      short loc_180079EBC
0x180079eb2  mov     eax, [rbp+57h+cValues]
0x180079eb5  add     edi, r12d
0x180079eb8  cmp     edi, eax
0x180079eba  jb      short loc_180079E56
0x180079ebc  test    ebx, ebx
0x180079ebe  movzx   r15d, r15b
0x180079ec2  mov     [rbp+57h+cValues], ebx
0x180079ec5  cmovnz  r15d, r12d
0x180079ec9  mov     r12, [rbp+57h+arg_8]
0x180079ecd  xor     edi, edi
0x180079ecf  test    r15b, r15b
0x180079ed2  jz      short loc_180079F1D
0x180079ed4  jmp     short loc_180079EED
0x180079ed6  mov     [rbp+57h+cValues], 2
0x180079edd  lea     r14, ?s_ppwzScriptArr@CCharFilter@@0PAPEAGA; ushort * near * CCharFilter::s_ppwzScriptArr
0x180079ee4  lea     rsi, ?s_ppwzZyyChars@CCharFilter@@0PAPEAGA; ushort * near * CCharFilter::s_ppwzZyyChars
0x180079eeb  xor     edi, edi
0x180079eed  xor     r15d, r15d
0x180079ef0  cmp     [r13+10h], r15d
0x180079ef4  jbe     short loc_180079F1D
0x180079ef6  mov     eax, [rbp+57h+cValues]
0x180079ef9  mov     r9, rsi; unsigned __int16 **
0x180079efc  mov     rdx, [r12+r15*8]; unsigned __int16 *
0x180079f00  mov     r8, r14; unsigned __int16 **
0x180079f03  mov     dword ptr [rsp+0C0h+phkResult], eax; unsigned int
0x180079f07  call    ?GetListOfChars@CCharFilter@@AEAAPEAGPEBGPEAPEAG1K@Z; CCharFilter::GetListOfChars(ushort const *,ushort * *,ushort * *,ulong)
0x180079f0c  mov     rcx, [r13+8]
0x180079f10  mov     [rcx+r15*8], rax
0x180079f14  inc     r15d
0x180079f17  cmp     r15d, [r13+10h]
0x180079f1b  jb      short loc_180079EF6
0x180079f1d  mov     r15b, [rbp+57h+arg_0]
0x180079f21  mov     r12d, 1
0x180079f27  mov     rcx, [rbp+57h+hKey]; hKey
0x180079f2b  lea     rax, [rcx-1]
0x180079f2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180079f33  ja      short loc_180079F3B
0x180079f35  call    cs:__imp_RegCloseKey
0x180079f3b  test    edi, edi
0x180079f3d  jns     short loc_180079F64
0x180079f3f  mov     rbx, [r13+8]
0x180079f43  test    rbx, rbx
0x180079f46  jz      short loc_180079F64
0x180079f48  call    cs:__imp_GetProcessHeap
0x180079f4e  mov     r8, rbx; lpMem
0x180079f51  xor     edx, edx; dwFlags
0x180079f53  mov     rcx, rax; hHeap
0x180079f56  call    cs:__imp_HeapFree
0x180079f5c  mov     qword ptr [r13+8], 0
0x180079f64  test    r15b, r15b
0x180079f67  jz      loc_180079FED
0x180079f6d  test    r14, r14
0x180079f70  jz      short loc_180079FAD
0x180079f72  xor     edi, edi
0x180079f74  cmp     [rbp+57h+cValues], edi
0x180079f77  jbe     short loc_180079F99
0x180079f79  mov     rbx, [r14+rdi*8]
0x180079f7d  call    cs:__imp_GetProcessHeap
0x180079f83  mov     r8, rbx; lpMem
0x180079f86  xor     edx, edx; dwFlags
0x180079f88  mov     rcx, rax; hHeap
0x180079f8b  call    cs:__imp_HeapFree
0x180079f91  add     edi, r12d
0x180079f94  cmp     edi, [rbp+57h+cValues]
0x180079f97  jb      short loc_180079F79
0x180079f99  call    cs:__imp_GetProcessHeap
0x180079f9f  mov     r8, r14; lpMem
0x180079fa2  xor     edx, edx; dwFlags
0x180079fa4  mov     rcx, rax; hHeap
0x180079fa7  call    cs:__imp_HeapFree
0x180079fad  test    rsi, rsi
0x180079fb0  jz      short loc_180079FED
0x180079fb2  xor     edi, edi
0x180079fb4  cmp     [rbp+57h+cValues], edi
0x180079fb7  jbe     short loc_180079FD9
0x180079fb9  mov     rbx, [rsi+rdi*8]
0x180079fbd  call    cs:__imp_GetProcessHeap
0x180079fc3  mov     r8, rbx; lpMem
0x180079fc6  xor     edx, edx; dwFlags
0x180079fc8  mov     rcx, rax; hHeap
0x180079fcb  call    cs:__imp_HeapFree
0x180079fd1  add     edi, r12d
0x180079fd4  cmp     edi, [rbp+57h+cValues]
0x180079fd7  jb      short loc_180079FB9
0x180079fd9  call    cs:__imp_GetProcessHeap
0x180079fdf  mov     r8, rsi; lpMem
0x180079fe2  xor     edx, edx; dwFlags
0x180079fe4  mov     rcx, rax; hHeap
0x180079fe7  call    cs:__imp_HeapFree
0x180079fed  xor     eax, eax
0x180079fef  add     rsp, 88h
0x180079ff6  pop     r15
0x180079ff8  pop     r14
0x180079ffa  pop     r13
0x180079ffc  pop     r12
0x180079ffe  pop     rdi
0x180079fff  pop     rsi
0x18007a000  pop     rbx
0x18007a001  pop     rbp
0x18007a002  retn
```
