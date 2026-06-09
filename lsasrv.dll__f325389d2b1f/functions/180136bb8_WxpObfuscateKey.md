# WxpObfuscateKey

- ea: `0x180136bb8`
- end: `0x18013702e`
- name: `WxpObfuscateKey`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180103c28`

## callees

- `0x1800b86d0`
- `0x1801362f8`
- `0x180136b10`
- `0x180136bb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136d12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136df6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136ed7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136ff0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180137002`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136d12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136df6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136ed7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136ff0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180137002`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136d02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136ec7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136fe0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136d02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136ec7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180136fe0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136cc9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136db4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136e92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136f89`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136cc9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136db4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136e92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180136f89`
- `CRYPTBASE!SystemFunction036` at `0x180136c43`
- `CRYPTBASE!SystemFunction036` at `0x180136d30`
- `CRYPTBASE!SystemFunction036` at `0x180136e09`
- `CRYPTBASE!SystemFunction036` at `0x180136eec`
- `CRYPTBASE!SystemFunction036` at `0x180136f07`
- `CRYPTBASE!SystemFunction036` at `0x180136fa0`
- `CRYPTBASE!SystemFunction036` at `0x180136c43`
- `CRYPTBASE!SystemFunction036` at `0x180136d30`
- `CRYPTBASE!SystemFunction036` at `0x180136e09`
- `CRYPTBASE!SystemFunction036` at `0x180136eec`
- `CRYPTBASE!SystemFunction036` at `0x180136f07`
- `CRYPTBASE!SystemFunction036` at `0x180136fa0`

## pseudocode

```c
char __fastcall WxpObfuscateKey(__int64 a1)
{
  __int64 v2; // rax
  HKEY v3; // rbx
  __int64 i; // rdx
  char v5; // r14
  CHAR *v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ecx
  int v9; // edi
  CHAR *v10; // rsi
  unsigned __int64 v11; // rax
  CHAR *v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ecx
  CHAR *v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ecx
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-21h] BYREF
  __int128 RandomBuffer; // [rsp+60h] [rbp-19h] BYREF
  __int128 v22; // [rsp+70h] [rbp-9h] BYREF
  CHAR Class[16]; // [rsp+80h] [rbp+7h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v22 = 0;
  RandomBuffer = 0;
  v2 = OpenLsaKey();
  v3 = (HKEY)v2;
  if ( v2 )
  {
    for ( i = 0; i != 16; ++i )
      Class[i - 16] = *(_BYTE *)(*((unsigned __int8 *)qword_180171BC0 + i) + a1);
    WxpDeleteLocalKey();
    v5 = 0;
    Class[8] = 0;
    if ( !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v6 = Class;
    v7 = 0;
    do
    {
      v8 = (unsigned __int8)Class[v7++ - 16];
      *v6 = a0123456789abcd_2[(unsigned __int64)v8 >> 4];
      v6 += 2;
      *(v6 - 1) = a0123456789abcd_2[v8 & 0xF];
    }
    while ( v7 != 4 );
    if ( RegCreateKeyExA(v3, "JD", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
      goto LABEL_28;
    RegSetValueExA(hKey, "Lookup", 0, 3u, (const BYTE *)&RandomBuffer, 6u);
    RegCloseKey(hKey);
    v9 = 0;
    v10 = Class;
    while ( v9 < 4 )
    {
      if ( !SystemFunction036(&RandomBuffer, 0x10u) )
        goto LABEL_28;
      v11 = (unsigned __int8)Class[v9 - 12];
      *v10 = a0123456789abcd_2[v11 >> 4];
      v10[1] = a0123456789abcd_2[v11 & 0xF];
      v10 += 2;
      ++v9;
    }
    if ( !RegCreateKeyExA(v3, "Skew1", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      RegSetValueExA(hKey, "SkewMatrix", 0, 3u, (const BYTE *)&RandomBuffer, 0x10u);
      RegCloseKey(hKey);
    }
    if ( !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v12 = Class;
    v13 = 0;
    do
    {
      v14 = (unsigned __int8)Class[v13++ - 8];
      *v12 = a0123456789abcd_2[(unsigned __int64)v14 >> 4];
      v12 += 2;
      *(v12 - 1) = a0123456789abcd_2[v14 & 0xF];
    }
    while ( v13 != 4 );
    if ( !RegCreateKeyExA(v3, "GBG", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      RegSetValueExA(hKey, "GrafBlumGroup", 0, 3u, (const BYTE *)&RandomBuffer, 9u);
      RegCloseKey(hKey);
    }
    if ( !SystemFunction036(&v22, 8u) || !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v15 = Class;
    v16 = 0;
    do
    {
      v17 = (unsigned __int8)Class[v16++ - 4];
      *v15 = a0123456789abcd_2[(unsigned __int64)v17 >> 4];
      v15 += 2;
      *(v15 - 1) = a0123456789abcd_2[v17 & 0xF];
    }
    while ( v16 != 4 );
    if ( !RegCreateKeyExA(v3, "Data", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      if ( !SystemFunction036(&v22, 0x10u) )
      {
        RegCloseKey(hKey);
LABEL_28:
        RegCloseKey(v3);
        LOBYTE(v2) = v5;
        return v2;
      }
      RegSetValueExA(hKey, "Pattern", 0, 3u, (const BYTE *)&RandomBuffer, 0x10u);
      RegCloseKey(hKey);
    }
    v5 = 1;
    goto LABEL_28;
  }
  return v2;
}

```

## disassembly

```asm
0x180136bb8  push    rbp
0x180136bba  push    rbx
0x180136bbb  push    rsi
0x180136bbc  push    rdi
0x180136bbd  push    r12
0x180136bbf  push    r14
0x180136bc1  lea     rbp, [rsp-2Fh]
0x180136bc6  sub     rsp, 0A8h
0x180136bcd  mov     rax, cs:__security_cookie
0x180136bd4  xor     rax, rsp
0x180136bd7  mov     [rbp+57h+var_40], rax
0x180136bdb  xorps   xmm0, xmm0
0x180136bde  mov     [rbp+57h+hKey], 0
0x180136be6  xorps   xmm1, xmm1
0x180136be9  mov     [rbp+57h+dwDisposition], 0
0x180136bf0  movups  [rbp+57h+var_60], xmm0
0x180136bf4  mov     rdi, rcx
0x180136bf7  movups  [rbp+57h+RandomBuffer], xmm1
0x180136bfb  call    OpenLsaKey
0x180136c00  mov     rbx, rax
0x180136c03  test    rax, rax
0x180136c06  jz      loc_180137011
0x180136c0c  xor     edx, edx
0x180136c0e  lea     rsi, __ImageBase
0x180136c15  lea     r12d, [rdx+10h]
0x180136c19  movzx   eax, byte ptr [rdx+rsi+171BC0h]
0x180136c21  mov     cl, [rax+rdi]
0x180136c24  mov     byte ptr [rbp+rdx+57h+var_60], cl
0x180136c28  inc     rdx
0x180136c2b  cmp     rdx, r12
0x180136c2e  jnz     short loc_180136C19
0x180136c30  call    WxpDeleteLocalKey
0x180136c35  xor     r14b, r14b
0x180136c38  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180136c3c  mov     edx, r12d; RandomBufferLength
0x180136c3f  mov     [rbp+57h+var_48], r14b
0x180136c43  call    cs:__imp_SystemFunction036
0x180136c4a  nop     dword ptr [rax+rax+00h]
0x180136c4f  test    al, al
0x180136c51  jz      loc_180136FFF
0x180136c57  lea     rdx, [rbp+57h+Class]
0x180136c5b  xor     r8d, r8d
0x180136c5e  movzx   ecx, byte ptr [rbp+r8+57h+var_60]
0x180136c64  inc     r8
0x180136c67  mov     eax, ecx
0x180136c69  and     ecx, 0Fh
0x180136c6c  shr     rax, 4
0x180136c70  mov     al, [rax+rsi+171BA8h]
0x180136c77  mov     [rdx], al
0x180136c79  lea     rdx, [rdx+2]
0x180136c7d  mov     al, [rcx+rsi+171BA8h]
0x180136c84  mov     [rdx-1], al
0x180136c87  cmp     r8, 4
0x180136c8b  jnz     short loc_180136C5E
0x180136c8d  lea     rax, [rbp+57h+dwDisposition]
0x180136c91  xor     r8d, r8d; Reserved
0x180136c94  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180136c99  lea     r9, [rbp+57h+Class]; lpClass
0x180136c9d  lea     rax, [rbp+57h+hKey]
0x180136ca1  mov     rcx, rbx; hKey
0x180136ca4  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180136ca9  lea     rdx, aJd; "JD"
0x180136cb0  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180136cb9  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x180136cc1  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180136cc9  call    cs:__imp_RegCreateKeyExA
0x180136cd0  nop     dword ptr [rax+rax+00h]
0x180136cd5  test    eax, eax
0x180136cd7  jnz     loc_180136FFF
0x180136cdd  mov     rcx, [rbp+57h+hKey]; hKey
0x180136ce1  lea     rax, [rbp+57h+RandomBuffer]
0x180136ce5  mov     [rsp+0D0h+samDesired], 6; cbData
0x180136ced  lea     rdx, aLookup; "Lookup"
0x180136cf4  mov     r9d, 3; dwType
0x180136cfa  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180136cff  xor     r8d, r8d; Reserved
0x180136d02  call    cs:__imp_RegSetValueExA
0x180136d09  nop     dword ptr [rax+rax+00h]
0x180136d0e  mov     rcx, [rbp+57h+hKey]; hKey
0x180136d12  call    cs:__imp_RegCloseKey
0x180136d19  nop     dword ptr [rax+rax+00h]
0x180136d1e  xor     edi, edi
0x180136d20  lea     rsi, [rbp+57h+Class]
0x180136d24  cmp     edi, 4
0x180136d27  jge     short loc_180136D77
0x180136d29  mov     edx, r12d; RandomBufferLength
0x180136d2c  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180136d30  call    cs:__imp_SystemFunction036
0x180136d37  nop     dword ptr [rax+rax+00h]
0x180136d3c  test    al, al
0x180136d3e  jz      loc_180136FFF
0x180136d44  movsxd  rax, edi
0x180136d47  lea     rdx, __ImageBase
0x180136d4e  movzx   ecx, byte ptr [rbp+rax+57h+var_60+4]
0x180136d53  mov     eax, ecx
0x180136d55  and     ecx, 0Fh
0x180136d58  shr     rax, 4
0x180136d5c  mov     al, [rax+rdx+171BA8h]
0x180136d63  mov     [rsi], al
0x180136d65  mov     al, [rcx+rdx+171BA8h]
0x180136d6c  mov     [rsi+1], al
0x180136d6f  add     rsi, 2
0x180136d73  inc     edi
0x180136d75  jmp     short loc_180136D24
0x180136d77  lea     rax, [rbp+57h+dwDisposition]
0x180136d7b  mov     esi, 20006h
0x180136d80  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180136d85  lea     r9, [rbp+57h+Class]; lpClass
0x180136d89  lea     rax, [rbp+57h+hKey]
0x180136d8d  xor     r8d, r8d; Reserved
0x180136d90  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180136d95  lea     rdx, aSkew1; "Skew1"
0x180136d9c  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180136da5  mov     rcx, rbx; hKey
0x180136da8  mov     [rsp+0D0h+samDesired], esi; samDesired
0x180136dac  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180136db4  call    cs:__imp_RegCreateKeyExA
0x180136dbb  nop     dword ptr [rax+rax+00h]
0x180136dc0  test    eax, eax
0x180136dc2  jnz     short loc_180136E02
0x180136dc4  mov     rcx, [rbp+57h+hKey]; hKey
0x180136dc8  lea     rax, [rbp+57h+RandomBuffer]
0x180136dcc  mov     [rsp+0D0h+samDesired], r12d; cbData
0x180136dd1  lea     rdx, aSkewmatrix; "SkewMatrix"
0x180136dd8  mov     r9d, 3; dwType
0x180136dde  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180136de3  xor     r8d, r8d; Reserved
0x180136de6  call    cs:__imp_RegSetValueExA
0x180136ded  nop     dword ptr [rax+rax+00h]
0x180136df2  mov     rcx, [rbp+57h+hKey]; hKey
0x180136df6  call    cs:__imp_RegCloseKey
0x180136dfd  nop     dword ptr [rax+rax+00h]
0x180136e02  mov     edx, r12d; RandomBufferLength
0x180136e05  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180136e09  call    cs:__imp_SystemFunction036
0x180136e10  nop     dword ptr [rax+rax+00h]
0x180136e15  test    al, al
0x180136e17  jz      loc_180136FFF
0x180136e1d  lea     rdx, [rbp+57h+Class]
0x180136e21  xor     r8d, r8d
0x180136e24  lea     rdi, __ImageBase
0x180136e2b  movzx   ecx, byte ptr [rbp+r8+57h+var_60+8]
0x180136e31  inc     r8
0x180136e34  mov     eax, ecx
0x180136e36  and     ecx, 0Fh
0x180136e39  shr     rax, 4
0x180136e3d  mov     al, [rax+rdi+171BA8h]
0x180136e44  mov     [rdx], al
0x180136e46  lea     rdx, [rdx+2]
0x180136e4a  mov     al, [rcx+rdi+171BA8h]
0x180136e51  mov     [rdx-1], al
0x180136e54  cmp     r8, 4
0x180136e58  jnz     short loc_180136E2B
0x180136e5a  lea     rax, [rbp+57h+dwDisposition]
0x180136e5e  xor     r8d, r8d; Reserved
0x180136e61  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180136e66  lea     r9, [rbp+57h+Class]; lpClass
0x180136e6a  lea     rax, [rbp+57h+hKey]
0x180136e6e  mov     rcx, rbx; hKey
0x180136e71  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180136e76  lea     rdx, aGbg; "GBG"
0x180136e7d  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180136e86  mov     [rsp+0D0h+samDesired], esi; samDesired
0x180136e8a  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180136e92  call    cs:__imp_RegCreateKeyExA
0x180136e99  nop     dword ptr [rax+rax+00h]
0x180136e9e  test    eax, eax
0x180136ea0  jnz     short loc_180136EE3
0x180136ea2  mov     rcx, [rbp+57h+hKey]; hKey
0x180136ea6  lea     rax, [rbp+57h+RandomBuffer]
0x180136eaa  mov     [rsp+0D0h+samDesired], 9; cbData
0x180136eb2  lea     rdx, aGrafblumgroup; "GrafBlumGroup"
0x180136eb9  mov     r9d, 3; dwType
0x180136ebf  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180136ec4  xor     r8d, r8d; Reserved
0x180136ec7  call    cs:__imp_RegSetValueExA
0x180136ece  nop     dword ptr [rax+rax+00h]
0x180136ed3  mov     rcx, [rbp+57h+hKey]; hKey
0x180136ed7  call    cs:__imp_RegCloseKey
0x180136ede  nop     dword ptr [rax+rax+00h]
0x180136ee3  mov     edx, 8; RandomBufferLength
0x180136ee8  lea     rcx, [rbp+57h+var_60]; RandomBuffer
0x180136eec  call    cs:__imp_SystemFunction036
0x180136ef3  nop     dword ptr [rax+rax+00h]
0x180136ef8  test    al, al
0x180136efa  jz      loc_180136FFF
0x180136f00  mov     edx, r12d; RandomBufferLength
0x180136f03  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180136f07  call    cs:__imp_SystemFunction036
0x180136f0e  nop     dword ptr [rax+rax+00h]
0x180136f13  test    al, al
0x180136f15  jz      loc_180136FFF
0x180136f1b  lea     rdx, [rbp+57h+Class]
0x180136f1f  xor     r8d, r8d
0x180136f22  movzx   ecx, byte ptr [rbp+r8+57h+var_60+0Ch]
0x180136f28  inc     r8
0x180136f2b  mov     eax, ecx
0x180136f2d  and     ecx, 0Fh
0x180136f30  shr     rax, 4
0x180136f34  mov     al, [rax+rdi+171BA8h]
0x180136f3b  mov     [rdx], al
0x180136f3d  lea     rdx, [rdx+2]
0x180136f41  mov     al, [rcx+rdi+171BA8h]
0x180136f48  mov     [rdx-1], al
0x180136f4b  cmp     r8, 4
0x180136f4f  jnz     short loc_180136F22
0x180136f51  lea     rax, [rbp+57h+dwDisposition]
0x180136f55  xor     r8d, r8d; Reserved
0x180136f58  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180136f5d  lea     r9, [rbp+57h+Class]; lpClass
0x180136f61  lea     rax, [rbp+57h+hKey]
0x180136f65  mov     rcx, rbx; hKey
0x180136f68  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180136f6d  lea     rdx, aData; "Data"
0x180136f74  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180136f7d  mov     [rsp+0D0h+samDesired], esi; samDesired
0x180136f81  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180136f89  call    cs:__imp_RegCreateKeyExA
0x180136f90  nop     dword ptr [rax+rax+00h]
0x180136f95  test    eax, eax
0x180136f97  jnz     short loc_180136FFC
0x180136f99  mov     edx, r12d; RandomBufferLength
0x180136f9c  lea     rcx, [rbp+57h+var_60]; RandomBuffer
0x180136fa0  call    cs:__imp_SystemFunction036
0x180136fa7  nop     dword ptr [rax+rax+00h]
0x180136fac  mov     rcx, [rbp+57h+hKey]; hKey
0x180136fb0  test    al, al
0x180136fb2  jnz     short loc_180136FC2
0x180136fb4  call    cs:__imp_RegCloseKey
0x180136fbb  nop     dword ptr [rax+rax+00h]
0x180136fc0  jmp     short loc_180136FFF
0x180136fc2  lea     rax, [rbp+57h+RandomBuffer]
0x180136fc6  mov     [rsp+0D0h+samDesired], r12d; cbData
0x180136fcb  mov     r9d, 3; dwType
0x180136fd1  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180136fd6  xor     r8d, r8d; Reserved
0x180136fd9  lea     rdx, aPattern; "Pattern"
0x180136fe0  call    cs:__imp_RegSetValueExA
0x180136fe7  nop     dword ptr [rax+rax+00h]
0x180136fec  mov     rcx, [rbp+57h+hKey]; hKey
0x180136ff0  call    cs:__imp_RegCloseKey
0x180136ff7  nop     dword ptr [rax+rax+00h]
0x180136ffc  mov     r14b, 1
0x180136fff  mov     rcx, rbx; hKey
0x180137002  call    cs:__imp_RegCloseKey
0x180137009  nop     dword ptr [rax+rax+00h]
0x18013700e  mov     al, r14b
0x180137011  mov     rcx, [rbp+57h+var_40]
0x180137015  xor     rcx, rsp; StackCookie
0x180137018  call    __security_check_cookie
0x18013701d  add     rsp, 0A8h
0x180137024  pop     r14
0x180137026  pop     r12
0x180137028  pop     rdi
0x180137029  pop     rsi
0x18013702a  pop     rbx
0x18013702b  pop     rbp
0x18013702c  retn
```
