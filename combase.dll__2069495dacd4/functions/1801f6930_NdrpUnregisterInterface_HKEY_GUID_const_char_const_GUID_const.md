# NdrpUnregisterInterface(HKEY__ *,_GUID const &,char const *,_GUID const *)

- ea: `0x1801f6930`
- end: `0x1801f6ada`
- name: `?NdrpUnregisterInterface@@YAJPEAUHKEY__@@AEBU_GUID@@PEBDPEBU2@@Z`
- size: `426`
- prototype: `HRESULT __fastcall(HKEY__ *hKeyInterface, const _GUID *riid, const char *pszClassID, const _GUID *riidAsync)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801f61f0`

## callees

- `0x1801020cc`
- `0x1801999b0`
- `0x1801f60f0`
- `0x1801f6930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f69ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f69e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f69fc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6a60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6a77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6a94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6ab8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f69ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f69e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f69fc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6a60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6a77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6a94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1801f6ab8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6a81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6a81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6aa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6999`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6a45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6999`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801f6a45`

## string_xrefs

- `0x1801f69d8`: `ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall NdrpUnregisterInterface(
        HKEY hKeyInterface,
        const _GUID *riid,
        const char *pszClassID,
        const _GUID *riidAsync)
{
  int v7; // ebx
  HKEY__ *hKeyIID; // [rsp+30h] [rbp-39h] BYREF
  HKEY__ *hKeyAsyncIID; // [rsp+38h] [rbp-31h] BYREF
  char szAsyncIID[40]; // [rsp+40h] [rbp-29h] BYREF
  char szIID[40]; // [rsp+68h] [rbp-1h] BYREF

  hKeyIID = 0;
  v7 = 0;
  memset(szIID, 0, 39);
  NdrStringFromIID(riid, szIID);
  if ( !RegOpenKeyExA(hKeyInterface, szIID, 0, 0x20006u, &hKeyIID) )
  {
    v7 = CheckProxyStubClsid32(hKeyIID, pszClassID);
    if ( v7 < 0 )
    {
      v7 = 1;
    }
    else
    {
      RegDeleteKeyExA(hKeyIID, "NumMethods", 0, 0);
      RegDeleteKeyExA(hKeyIID, "ProxyStubClsid32", 0, 0);
      RegDeleteKeyExA(hKeyIID, "AsynchronousInterface", 0, 0);
      if ( riidAsync )
      {
        memset(szAsyncIID, 0, 39);
        hKeyAsyncIID = 0;
        NdrStringFromIID(riidAsync, szAsyncIID);
        if ( !RegOpenKeyExA(hKeyInterface, szAsyncIID, 0, 0x20006u, &hKeyAsyncIID) )
        {
          RegDeleteKeyExA(hKeyAsyncIID, "NumMethods", 0, 0);
          RegDeleteKeyExA(hKeyAsyncIID, "SynchronousInterface", 0, 0);
          RegCloseKey(hKeyAsyncIID);
          RegDeleteKeyExA(hKeyInterface, szAsyncIID, 0, 0);
        }
      }
    }
    RegCloseKey(hKeyIID);
    RegDeleteKeyExA(hKeyInterface, szIID, 0, 0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801f6930  push    rbp
0x1801f6932  push    rbx
0x1801f6933  push    rsi
0x1801f6934  push    rdi
0x1801f6935  push    r14
0x1801f6937  lea     rbp, [rsp-37h]
0x1801f693c  sub     rsp, 0A0h
0x1801f6943  mov     rax, cs:__security_cookie
0x1801f694a  xor     rax, rsp
0x1801f694d  mov     [rbp+57h+var_30], rax
0x1801f6951  mov     rdi, hKeyInterface
0x1801f6954  xorps   xmm0, xmm0
0x1801f6957  xor     ecx, ecx
0x1801f6959  mov     rax, riid
0x1801f695c  movups  xmmword ptr [rbp+57h+szIID+10h], xmm0
0x1801f6960  mov     qword ptr [rbp+57h+szIID+1Fh], hKeyInterface
0x1801f6964  lea     riid, [rbp+57h+szIID]; lpsz
0x1801f6968  mov     [rbp+57h+hKeyIID], hKeyInterface
0x1801f696c  mov     rsi, riidAsync
0x1801f696f  mov     hKeyInterface, rax; rclsid
0x1801f6972  mov     r14, pszClassID
0x1801f6975  xor     ebx, ebx
0x1801f6977  movups  xmmword ptr [rbp+57h+szIID], xmm0
0x1801f697b  call    NdrStringFromIID
0x1801f6980  lea     rax, [rbp+57h+hKeyIID]
0x1801f6984  mov     r9d, 20006h; samDesired
0x1801f698a  xor     r8d, r8d; ulOptions
0x1801f698d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1801f6992  lea     riid, [rbp+57h+szIID]; lpSubKey
0x1801f6996  mov     hKeyInterface, rdi; hKey
0x1801f6999  call    cs:__imp_RegOpenKeyExA
0x1801f699f  test    eax, eax
0x1801f69a1  jnz     loc_1801F6ABE
0x1801f69a7  mov     hKeyInterface, [rbp+57h+hKeyIID]; hKeyIID
0x1801f69ab  mov     riid, r14; pszClassID
0x1801f69ae  call    ?CheckProxyStubClsid32@@YAJPEAUHKEY__@@PEBD@Z; CheckProxyStubClsid32(HKEY__ *,char const *)
0x1801f69b3  mov     ebx, eax
0x1801f69b5  test    eax, eax
0x1801f69b7  js      loc_1801F6A9C
0x1801f69bd  mov     hKeyInterface, [rbp+57h+hKeyIID]; hKey
0x1801f69c1  lea     riid, aNummethods; "NumMethods"
0x1801f69c8  xor     r9d, r9d; Reserved
0x1801f69cb  xor     r8d, r8d; samDesired
0x1801f69ce  call    cs:__imp_RegDeleteKeyExA
0x1801f69d4  mov     hKeyInterface, [rbp+57h+hKeyIID]; hKey
0x1801f69d8  lea     riid, aProxystubclsid_1; "ProxyStubClsid32"
0x1801f69df  xor     r9d, r9d; Reserved
0x1801f69e2  xor     r8d, r8d; samDesired
0x1801f69e5  call    cs:__imp_RegDeleteKeyExA
0x1801f69eb  mov     hKeyInterface, [rbp+57h+hKeyIID]; hKey
0x1801f69ef  lea     riid, aAsynchronousin_0; "AsynchronousInterface"
0x1801f69f6  xor     r9d, r9d; Reserved
0x1801f69f9  xor     r8d, r8d; samDesired
0x1801f69fc  call    cs:__imp_RegDeleteKeyExA
0x1801f6a02  test    rsi, rsi
0x1801f6a05  jz      loc_1801F6AA1
0x1801f6a0b  xorps   xmm0, xmm0
0x1801f6a0e  lea     riid, [rbp+57h+szAsyncIID]; lpsz
0x1801f6a12  xor     eax, eax
0x1801f6a14  mov     hKeyInterface, rsi; rclsid
0x1801f6a17  movups  xmmword ptr [rbp+57h+szAsyncIID+10h], xmm0
0x1801f6a1b  mov     qword ptr [rbp+57h+szAsyncIID+1Fh], rax
0x1801f6a1f  movups  xmmword ptr [rbp+57h+szAsyncIID], xmm0
0x1801f6a23  mov     [rbp+57h+hKeyAsyncIID], rax
0x1801f6a27  call    NdrStringFromIID
0x1801f6a2c  lea     rax, [rbp+57h+hKeyAsyncIID]
0x1801f6a30  mov     r9d, 20006h; samDesired
0x1801f6a36  xor     r8d, r8d; ulOptions
0x1801f6a39  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1801f6a3e  lea     riid, [rbp+57h+szAsyncIID]; lpSubKey
0x1801f6a42  mov     hKeyInterface, rdi; hKey
0x1801f6a45  call    cs:__imp_RegOpenKeyExA
0x1801f6a4b  test    eax, eax
0x1801f6a4d  jnz     short loc_1801F6AA1
0x1801f6a4f  mov     hKeyInterface, [rbp+57h+hKeyAsyncIID]; hKey
0x1801f6a53  lea     riid, aNummethods; "NumMethods"
0x1801f6a5a  xor     r9d, r9d; Reserved
0x1801f6a5d  xor     r8d, r8d; samDesired
0x1801f6a60  call    cs:__imp_RegDeleteKeyExA
0x1801f6a66  mov     hKeyInterface, [rbp+57h+hKeyAsyncIID]; hKey
0x1801f6a6a  lea     riid, aSynchronousint_1; "SynchronousInterface"
0x1801f6a71  xor     r9d, r9d; Reserved
0x1801f6a74  xor     r8d, r8d; samDesired
0x1801f6a77  call    cs:__imp_RegDeleteKeyExA
0x1801f6a7d  mov     hKeyInterface, [rbp+57h+hKeyAsyncIID]; hKey
0x1801f6a81  call    cs:__imp_RegCloseKey
0x1801f6a87  xor     r9d, r9d; Reserved
0x1801f6a8a  lea     riid, [rbp+57h+szAsyncIID]; lpSubKey
0x1801f6a8e  xor     r8d, r8d; samDesired
0x1801f6a91  mov     hKeyInterface, rdi; hKey
0x1801f6a94  call    cs:__imp_RegDeleteKeyExA
0x1801f6a9a  jmp     short loc_1801F6AA1
0x1801f6a9c  mov     ebx, 1
0x1801f6aa1  mov     hKeyInterface, [rbp+57h+hKeyIID]; hKey
0x1801f6aa5  call    cs:__imp_RegCloseKey
0x1801f6aab  xor     r9d, r9d; Reserved
0x1801f6aae  lea     riid, [rbp+57h+szIID]; lpSubKey
0x1801f6ab2  xor     r8d, r8d; samDesired
0x1801f6ab5  mov     hKeyInterface, rdi; hKey
0x1801f6ab8  call    cs:__imp_RegDeleteKeyExA
0x1801f6abe  mov     eax, ebx
0x1801f6ac0  mov     hKeyInterface, [rbp+57h+var_30]
0x1801f6ac4  xor     hKeyInterface, rsp; StackCookie
0x1801f6ac7  call    __security_check_cookie
0x1801f6acc  add     rsp, 0A0h
0x1801f6ad3  pop     r14
0x1801f6ad5  pop     rdi
0x1801f6ad6  pop     rsi
0x1801f6ad7  pop     rbx
0x1801f6ad8  pop     rbp
0x1801f6ad9  retn
```
