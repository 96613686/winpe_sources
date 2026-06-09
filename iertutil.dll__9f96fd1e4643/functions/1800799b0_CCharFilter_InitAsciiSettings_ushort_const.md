# CCharFilter::InitAsciiSettings(ushort const * *)

- ea: `0x1800799b0`
- end: `0x180079bc2`
- name: `?InitAsciiSettings@CCharFilter@@AEAAJPEAPEBG@Z`
- size: `530`
- prototype: `__int64 __fastcall(CCharFilter *__hidden this, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800797f4`

## callees

- `0x1800799b0`
- `0x180083bc2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079a01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079ab9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079a01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079ab9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800799ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079aab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079b23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079b5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800799ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079aab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079b23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079b5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079b31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079b31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079b6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180079a46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180079a46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079a7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079aec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079a7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079aec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079b3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079b3c`
- `api-ms-win-core-normalization-l1-1-0!VerifyScripts` at `0x180079b10`
- `api-ms-win-core-normalization-l1-1-0!VerifyScripts` at `0x180079bad`
- `api-ms-win-core-normalization-l1-1-0!VerifyScripts` at `0x180079b10`
- `api-ms-win-core-normalization-l1-1-0!VerifyScripts` at `0x180079bad`

## pseudocode

```c
__int64 __fastcall CCharFilter::InitAsciiSettings(CCharFilter *this, const unsigned __int16 **a2)
{
  unsigned __int64 v2; // r8
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  LSTATUS v8; // edi
  unsigned __int64 v9; // rcx
  SIZE_T v10; // rbx
  HANDLE v11; // rax
  BYTE *v12; // r14
  __int64 j; // rbp
  HANDLE v14; // rax
  bool v15; // sf
  void *v16; // rbx
  HANDLE v17; // rax
  __int64 i; // rdi
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v2 = *((unsigned int *)this + 4);
  hKey = 0;
  v5 = 4 * v2;
  if ( !is_mul_ok(v2, 4u) )
    v5 = -1;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, v5);
  *(_QWORD *)this = v7;
  if ( !v7 )
    goto LABEL_18;
  memset_0(v7, 0, 4LL * *((unsigned int *)this + 4));
  if ( RegOpenKeyExA(
         HKEY_CURRENT_USER,
         "Software\\Microsoft\\Internet Explorer\\International\\MixScripts\\Ascii",
         0,
         0x20019u,
         &hKey) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
      *(_DWORD *)(*(_QWORD *)this + 4 * i) = VerifyScripts(
                                               0,
                                               L"Arab;Bali;Beng;Bugi;Deva;Ethi;Gujr;Guru;Hang;Hani;Hans;Hant;Hebr;Hira;Jpa"
                                                "n;Kana;Khmr;Knda;Kore;Laoo;Mlym;Mong;Mymr;Orya;Sinh;Syrc;Taml;Telu;Thaa;Thai;Tibt;",
                                               -1,
                                               a2[i],
                                               -1);
  }
  else
  {
    cbData = 0;
    v8 = RegQueryValueExW(hKey, L"AllowedScripts", 0, 0, 0, &cbData);
    if ( !v8 && cbData )
    {
      v9 = (unsigned __int64)cbData >> 1;
      v10 = 2 * v9;
      if ( !is_mul_ok(v9, 2u) )
        v10 = -1;
      v11 = GetProcessHeap();
      v12 = (BYTE *)HeapAlloc(v11, 8u, v10);
      if ( !v12 )
        goto LABEL_18;
      v8 = RegQueryValueExW(hKey, L"AllowedScripts", 0, 0, v12, &cbData);
      if ( !v8 )
      {
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 4); j = (unsigned int)(j + 1) )
          *(_DWORD *)(*(_QWORD *)this + 4 * j) = VerifyScripts(0, (LPCWSTR)v12, -1, a2[j], -1);
      }
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v12);
    }
    RegCloseKey(hKey);
    v15 = v8 < 0;
    if ( v8 )
    {
      if ( v8 > 0 )
        v15 = 1;
      if ( v15 )
      {
LABEL_18:
        v16 = *(void **)this;
        if ( *(_QWORD *)this )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v16);
          *(_QWORD *)this = 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800799b0  mov     [rsp+arg_8], rbx
0x1800799b5  mov     [rsp+arg_18], rbp
0x1800799ba  push    rsi
0x1800799bb  push    rdi
0x1800799bc  push    r13
0x1800799be  push    r14
0x1800799c0  push    r15
0x1800799c2  sub     rsp, 30h
0x1800799c6  mov     r8d, [rcx+10h]
0x1800799ca  mov     r15, rdx
0x1800799cd  mov     eax, 4
0x1800799d2  mov     [rsp+58h+hKey], 0
0x1800799db  mul     r8
0x1800799de  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800799e5  mov     rsi, rcx
0x1800799e8  mov     rbx, rax
0x1800799eb  cmovb   rbx, r13
0x1800799ef  call    cs:__imp_GetProcessHeap
0x1800799f5  lea     ebp, [r13+9]
0x1800799f9  mov     r8, rbx; dwBytes
0x1800799fc  mov     rcx, rax; hHeap
0x1800799ff  mov     edx, ebp; dwFlags
0x180079a01  call    cs:__imp_HeapAlloc
0x180079a07  mov     [rsi], rax
0x180079a0a  test    rax, rax
0x180079a0d  jz      loc_180079B55
0x180079a13  mov     r8d, [rsi+10h]
0x180079a17  xor     edx, edx; Val
0x180079a19  shl     r8, 2; Size
0x180079a1d  mov     rcx, rax; void *
0x180079a20  call    memset_0
0x180079a25  lea     rax, [rsp+58h+hKey]
0x180079a2a  mov     r9d, 20019h; samDesired
0x180079a30  xor     r8d, r8d; ulOptions
0x180079a33  mov     [rsp+58h+phkResult], rax; phkResult
0x180079a38  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Internet Explorer"...
0x180079a3f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180079a46  call    cs:__imp_RegOpenKeyExA
0x180079a4c  test    eax, eax
0x180079a4e  jnz     loc_180079B91
0x180079a54  mov     rcx, [rsp+58h+hKey]; hKey
0x180079a59  lea     rdx, aAllowedscripts; "AllowedScripts"
0x180079a60  mov     [rsp+58h+cbData], eax
0x180079a64  xor     r9d, r9d; lpType
0x180079a67  lea     rax, [rsp+58h+cbData]
0x180079a6c  xor     r8d, r8d; lpReserved
0x180079a6f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180079a74  mov     [rsp+58h+phkResult], 0; lpData
0x180079a7d  call    cs:__imp_RegQueryValueExW
0x180079a83  mov     edi, eax
0x180079a85  test    eax, eax
0x180079a87  jnz     loc_180079B37
0x180079a8d  mov     eax, [rsp+58h+cbData]
0x180079a91  test    eax, eax
0x180079a93  jz      loc_180079B37
0x180079a99  mov     ecx, eax
0x180079a9b  lea     eax, [rbp-6]
0x180079a9e  shr     rcx, 1
0x180079aa1  mul     rcx
0x180079aa4  mov     rbx, rax
0x180079aa7  cmovb   rbx, r13
0x180079aab  call    cs:__imp_GetProcessHeap
0x180079ab1  mov     r8, rbx; dwBytes
0x180079ab4  mov     edx, ebp; dwFlags
0x180079ab6  mov     rcx, rax; hHeap
0x180079ab9  call    cs:__imp_HeapAlloc
0x180079abf  mov     r14, rax
0x180079ac2  test    rax, rax
0x180079ac5  jz      loc_180079B55
0x180079acb  mov     rcx, [rsp+58h+hKey]; hKey
0x180079ad0  lea     rax, [rsp+58h+cbData]
0x180079ad5  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180079ada  lea     rdx, aAllowedscripts; "AllowedScripts"
0x180079ae1  xor     r9d, r9d; lpType
0x180079ae4  mov     [rsp+58h+phkResult], r14; lpData
0x180079ae9  xor     r8d, r8d; lpReserved
0x180079aec  call    cs:__imp_RegQueryValueExW
0x180079af2  mov     edi, eax
0x180079af4  test    eax, eax
0x180079af6  jnz     short loc_180079B23
0x180079af8  xor     ebp, ebp
0x180079afa  cmp     [rsi+10h], ebp
0x180079afd  jbe     short loc_180079B23
0x180079aff  mov     r9, [r15+rbp*8]; lpTestScripts
0x180079b03  mov     r8d, r13d; cchLocaleScripts
0x180079b06  mov     rdx, r14; lpLocaleScripts
0x180079b09  mov     dword ptr [rsp+58h+phkResult], r13d; cchTestScripts
0x180079b0e  xor     ecx, ecx; dwFlags
0x180079b10  call    cs:__imp_VerifyScripts
0x180079b16  mov     rcx, [rsi]
0x180079b19  mov     [rcx+rbp*4], eax
0x180079b1c  inc     ebp
0x180079b1e  cmp     ebp, [rsi+10h]
0x180079b21  jb      short loc_180079AFF
0x180079b23  call    cs:__imp_GetProcessHeap
0x180079b29  mov     r8, r14; lpMem
0x180079b2c  xor     edx, edx; dwFlags
0x180079b2e  mov     rcx, rax; hHeap
0x180079b31  call    cs:__imp_HeapFree
0x180079b37  mov     rcx, [rsp+58h+hKey]; hKey
0x180079b3c  call    cs:__imp_RegCloseKey
0x180079b42  test    edi, edi
0x180079b44  jz      short loc_180079B78
0x180079b46  jle     short loc_180079B53
0x180079b48  movzx   edi, di
0x180079b4b  or      edi, 80070000h
0x180079b51  test    edi, edi
0x180079b53  jns     short loc_180079B78
0x180079b55  mov     rbx, [rsi]
0x180079b58  test    rbx, rbx
0x180079b5b  jz      short loc_180079B78
0x180079b5d  call    cs:__imp_GetProcessHeap
0x180079b63  mov     r8, rbx; lpMem
0x180079b66  xor     edx, edx; dwFlags
0x180079b68  mov     rcx, rax; hHeap
0x180079b6b  call    cs:__imp_HeapFree
0x180079b71  mov     qword ptr [rsi], 0
0x180079b78  mov     rbx, [rsp+58h+arg_8]
0x180079b7d  xor     eax, eax
0x180079b7f  mov     rbp, [rsp+58h+arg_18]
0x180079b84  add     rsp, 30h
0x180079b88  pop     r15
0x180079b8a  pop     r14
0x180079b8c  pop     r13
0x180079b8e  pop     rdi
0x180079b8f  pop     rsi
0x180079b90  retn
0x180079b91  xor     edi, edi
0x180079b93  cmp     [rsi+10h], edi
0x180079b96  jbe     short loc_180079B78
0x180079b98  mov     r9, [r15+rdi*8]; lpTestScripts
0x180079b9c  lea     rdx, LocaleScripts; "Arab;Bali;Beng;Bugi;Deva;Ethi;Gujr;Guru"...
0x180079ba3  mov     r8d, r13d; cchLocaleScripts
0x180079ba6  mov     dword ptr [rsp+58h+phkResult], r13d; cchTestScripts
0x180079bab  xor     ecx, ecx; dwFlags
0x180079bad  call    cs:__imp_VerifyScripts
0x180079bb3  mov     rcx, [rsi]
0x180079bb6  mov     [rcx+rdi*4], eax
0x180079bb9  inc     edi
0x180079bbb  cmp     edi, [rsi+10h]
0x180079bbe  jb      short loc_180079B98
0x180079bc0  jmp     short loc_180079B78
```
