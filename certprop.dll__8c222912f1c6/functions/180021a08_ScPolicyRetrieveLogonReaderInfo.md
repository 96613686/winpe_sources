# ScPolicyRetrieveLogonReaderInfo

- ea: `0x180021a08`
- end: `0x180021b78`
- name: `ScPolicyRetrieveLogonReaderInfo`
- size: `368`
- prototype: `__int64 __fastcall(__int64, __int64, int, _DWORD *, BYTE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001af6c`

## callees

- `0x180016090`
- `0x180021a08`
- `0x180021b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180021a77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180021a77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180021b2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180021b2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021ab9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021aff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021ab9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021aff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021ad5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021ad5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b3e`

## pseudocode

```c
__int64 __fastcall ScPolicyRetrieveLogonReaderInfo(__int64 a1, __int64 a2, int a3, _DWORD *a4, BYTE **a5)
{
  unsigned int v7; // edi
  BYTE *v8; // rbx
  __int64 v9; // rax
  HKEY v10; // rcx
  DWORD cbData; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  char pszDest[16]; // [rsp+60h] [rbp-20h] BYREF

  hKey = 0;
  cbData = 0;
  v7 = RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows NT\\CurrentVersion\\Removal Policy",
         0,
         0,
         1u,
         3u,
         0,
         &hKey,
         0);
  if ( !v7 )
  {
    StringCbPrintfA(pszDest, 9u, "%x", a3);
    v7 = RegQueryValueExA(hKey, pszDest, 0, 0, 0, &cbData);
    if ( !v7 )
    {
      v7 = 8;
      v8 = (BYTE *)HeapAlloc(g_hScPolicyHeap, 8u, cbData);
      if ( v8 )
      {
        v7 = RegQueryValueExA(hKey, pszDest, 0, 0, v8, &cbData);
        if ( v7 )
        {
          HeapFree(g_hScPolicyHeap, 0, v8);
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&v8[2 * v9] );
          v10 = hKey;
          *a4 = *(_DWORD *)&v8[2 * v9 + 2];
          *a5 = v8;
          RegDeleteValueA(v10, pszDest);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180021a08  mov     r11, rsp
0x180021a0b  mov     [r11+8], rbx
0x180021a0f  push    rbp
0x180021a10  push    rsi
0x180021a11  push    rdi
0x180021a12  push    r14
0x180021a14  push    r15
0x180021a16  mov     rbp, rsp
0x180021a19  sub     rsp, 80h
0x180021a20  mov     rax, cs:__security_cookie
0x180021a27  xor     rax, rsp
0x180021a2a  mov     [rbp+var_10], rax
0x180021a2e  mov     r14, [rbp+arg_20]
0x180021a32  lea     rax, [rbp+hKey]
0x180021a36  xor     r15d, r15d
0x180021a39  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180021a40  mov     [r11-68h], r15
0x180021a44  mov     rsi, r9
0x180021a47  mov     [r11-70h], rax
0x180021a4b  mov     ebx, r8d
0x180021a4e  mov     [r11-78h], r15
0x180021a52  xor     r9d, r9d; lpClass
0x180021a55  mov     [rsp+80h+samDesired], 3; samDesired
0x180021a5d  xor     r8d, r8d; Reserved
0x180021a60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021a67  mov     [rsp+80h+dwOptions], 1; dwOptions
0x180021a6f  mov     [rbp+hKey], r15
0x180021a73  mov     [rbp+cbData], r15d
0x180021a77  call    cs:__imp_RegCreateKeyExA
0x180021a7d  mov     edi, eax
0x180021a7f  test    eax, eax
0x180021a81  jnz     loc_180021B44
0x180021a87  mov     r9d, ebx
0x180021a8a  lea     r8, asc_180028D64; "%x"
0x180021a91  lea     edx, [rax+9]; cbDest
0x180021a94  lea     rcx, [rbp+pszDest]; pszDest
0x180021a98  call    StringCbPrintfA
0x180021a9d  mov     rcx, [rbp+hKey]; hKey
0x180021aa1  lea     rax, [rbp+cbData]
0x180021aa5  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x180021aaa  lea     rdx, [rbp+pszDest]; lpValueName
0x180021aae  xor     r9d, r9d; lpType
0x180021ab1  mov     qword ptr [rsp+80h+dwOptions], r15; lpData
0x180021ab6  xor     r8d, r8d; lpReserved
0x180021ab9  call    cs:__imp_RegQueryValueExA
0x180021abf  mov     edi, eax
0x180021ac1  test    eax, eax
0x180021ac3  jnz     short loc_180021B44
0x180021ac5  mov     r8d, [rbp+cbData]; dwBytes
0x180021ac9  lea     edi, [rax+8]
0x180021acc  mov     rcx, cs:g_hScPolicyHeap; hHeap
0x180021ad3  mov     edx, edi; dwFlags
0x180021ad5  call    cs:__imp_HeapAlloc
0x180021adb  mov     rbx, rax
0x180021ade  test    rax, rax
0x180021ae1  jz      short loc_180021B44
0x180021ae3  mov     rcx, [rbp+hKey]; hKey
0x180021ae7  lea     rax, [rbp+cbData]
0x180021aeb  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x180021af0  lea     rdx, [rbp+pszDest]; lpValueName
0x180021af4  xor     r9d, r9d; lpType
0x180021af7  mov     qword ptr [rsp+80h+dwOptions], rbx; lpData
0x180021afc  xor     r8d, r8d; lpReserved
0x180021aff  call    cs:__imp_RegQueryValueExA
0x180021b05  mov     edi, eax
0x180021b07  test    eax, eax
0x180021b09  jnz     short loc_180021B32
0x180021b0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021b0f  inc     rax
0x180021b12  cmp     [rbx+rax*2], r15w
0x180021b17  jnz     short loc_180021B0F
0x180021b19  mov     eax, [rbx+rax*2+2]
0x180021b1d  lea     rdx, [rbp+pszDest]; lpValueName
0x180021b21  mov     rcx, [rbp+hKey]; hKey
0x180021b25  mov     [rsi], eax
0x180021b27  mov     [r14], rbx
0x180021b2a  call    cs:__imp_RegDeleteValueA
0x180021b30  jmp     short loc_180021B44
0x180021b32  mov     rcx, cs:g_hScPolicyHeap; hHeap
0x180021b39  mov     r8, rbx; lpMem
0x180021b3c  xor     edx, edx; dwFlags
0x180021b3e  call    cs:__imp_HeapFree
0x180021b44  mov     rcx, [rbp+hKey]; hKey
0x180021b48  test    rcx, rcx
0x180021b4b  jz      short loc_180021B53
0x180021b4d  call    cs:__imp_RegCloseKey
0x180021b53  mov     eax, edi
0x180021b55  mov     rcx, [rbp+var_10]
0x180021b59  xor     rcx, rsp; StackCookie
0x180021b5c  call    __security_check_cookie
0x180021b61  mov     rbx, [rsp+80h+arg_0]
0x180021b69  add     rsp, 80h
0x180021b70  pop     r15
0x180021b72  pop     r14
0x180021b74  pop     rdi
0x180021b75  pop     rsi
0x180021b76  pop     rbp
0x180021b77  retn
```
