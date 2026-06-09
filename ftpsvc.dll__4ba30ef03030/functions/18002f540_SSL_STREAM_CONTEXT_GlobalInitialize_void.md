# SSL_STREAM_CONTEXT::GlobalInitialize(void)

- ea: `0x18002f540`
- end: `0x18002f67e`
- name: `?GlobalInitialize@SSL_STREAM_CONTEXT@@SAJXZ`
- size: `318`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800029fc`

## callees

- `0x180001210`
- `0x18002f540`
- `0x18002f684`
- `0x180030960`
- `0x180031558`
- `0x180047050`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002f634`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f634`
- `ADVAPI32!RegQueryValueExW` at `0x18002f669`
- `ADVAPI32!RegQueryValueExW` at `0x18002f669`
- `ADVAPI32!RegCloseKey` at `0x18002f673`
- `ADVAPI32!RegCloseKey` at `0x18002f673`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002f5d4`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002f5d4`

## string_xrefs

- `0x18002f626`: `System\CurrentControlSet\Services\FTPSVC\Parameters`
- `0x18002f65e`: `CertChainCacheOnlyUrlRetrieval`

## pseudocode

```c
__int64 SSL_STREAM_CONTEXT::GlobalInitialize(void)
{
  int v0; // ebx
  ALLOC_CACHE_HANDLER *v1; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-30h] BYREF
  DWORD Type; // [rsp+34h] [rbp-2Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v7; // [rsp+48h] [rbp-18h] BYREF
  int v8; // [rsp+50h] [rbp-10h]

  v7 = 0;
  v8 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v0 = SSL_CERT_STORE::GlobalInitialize();
  if ( v0 < 0 )
    goto LABEL_7;
  SSL_STREAM_CONTEXT::s_InitState = 1;
  v0 = SSL_SERVER_CERT::GlobalInitialize();
  if ( v0 < 0 )
    goto LABEL_7;
  SSL_STREAM_CONTEXT::s_InitState = 2;
  v7 = 0x6400000001LL;
  v8 = 176;
  v1 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  *(_QWORD *)cbData = v1;
  if ( v1 )
    v1 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
           v1,
           "SSL_STREAM_CONTEXT",
           (const struct ALLOC_CACHE_CONFIGURATION *)&v7,
           1);
  SSL_STREAM_CONTEXT::sm_pachSslStreamContexts = v1;
  if ( !v1 )
  {
    v0 = -2147024888;
LABEL_7:
    SSL_STREAM_CONTEXT::GlobalTerminate();
    return (unsigned int)v0;
  }
  SSL_STREAM_CONTEXT::s_InitState = 3;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\FTPSVC\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData[0] = 4;
    RegQueryValueExW(hKey, L"CertChainCacheOnlyUrlRetrieval", 0, &Type, Data, cbData);
    RegCloseKey(hKey);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002f540  mov     [rsp-8+arg_0], rbx
0x18002f545  push    rbp
0x18002f546  mov     rbp, rsp
0x18002f549  sub     rsp, 60h
0x18002f54d  mov     rax, cs:__security_cookie
0x18002f554  xor     rax, rsp
0x18002f557  mov     [rbp+var_8], rax
0x18002f55b  xor     eax, eax
0x18002f55d  mov     [rbp+var_18], rax
0x18002f561  mov     [rbp+var_10], eax
0x18002f564  mov     [rbp+hKey], rax
0x18002f568  mov     [rbp+Type], eax
0x18002f56b  mov     dword ptr [rbp+Data], eax
0x18002f56e  call    ?GlobalInitialize@SSL_CERT_STORE@@SAJXZ; SSL_CERT_STORE::GlobalInitialize(void)
0x18002f573  mov     ebx, eax
0x18002f575  test    eax, eax
0x18002f577  js      short loc_18002F5EC
0x18002f579  mov     cs:?s_InitState@SSL_STREAM_CONTEXT@@0W4INIT_STATE@1@A, 1; SSL_STREAM_CONTEXT::INIT_STATE SSL_STREAM_CONTEXT::s_InitState
0x18002f583  call    ?GlobalInitialize@SSL_SERVER_CERT@@SAJXZ; SSL_SERVER_CERT::GlobalInitialize(void)
0x18002f588  mov     ebx, eax
0x18002f58a  test    eax, eax
0x18002f58c  js      short loc_18002F5EC
0x18002f58e  mov     cs:?s_InitState@SSL_STREAM_CONTEXT@@0W4INIT_STATE@1@A, 2; SSL_STREAM_CONTEXT::INIT_STATE SSL_STREAM_CONTEXT::s_InitState
0x18002f598  mov     dword ptr [rbp+var_18], 1
0x18002f59f  mov     dword ptr [rbp+var_18+4], 64h ; 'd'
0x18002f5a6  mov     [rbp+var_10], 0B0h
0x18002f5ad  mov     ecx, 100h; Size
0x18002f5b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f5b7  mov     qword ptr [rbp+cbData], rax
0x18002f5bb  test    rax, rax
0x18002f5be  jz      short loc_18002F5DB
0x18002f5c0  mov     r9d, 1
0x18002f5c6  lea     r8, [rbp+var_18]
0x18002f5ca  lea     rdx, aSslStreamConte_3; "SSL_STREAM_CONTEXT"
0x18002f5d1  mov     rcx, rax
0x18002f5d4  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18002f5da  nop
0x18002f5db  mov     cs:?sm_pachSslStreamContexts@SSL_STREAM_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * SSL_STREAM_CONTEXT::sm_pachSslStreamContexts
0x18002f5e2  test    rax, rax
0x18002f5e5  jnz     short loc_18002F60A
0x18002f5e7  mov     ebx, 80070008h
0x18002f5ec  call    ?GlobalTerminate@SSL_STREAM_CONTEXT@@SAXXZ; SSL_STREAM_CONTEXT::GlobalTerminate(void)
0x18002f5f1  mov     eax, ebx
0x18002f5f3  mov     rcx, [rbp+var_8]
0x18002f5f7  xor     rcx, rsp; StackCookie
0x18002f5fa  call    __security_check_cookie
0x18002f5ff  mov     rbx, [rsp+60h+arg_0]
0x18002f604  add     rsp, 60h
0x18002f608  pop     rbp
0x18002f609  retn
0x18002f60a  mov     cs:?s_InitState@SSL_STREAM_CONTEXT@@0W4INIT_STATE@1@A, 3; SSL_STREAM_CONTEXT::INIT_STATE SSL_STREAM_CONTEXT::s_InitState
0x18002f614  lea     rax, [rbp+hKey]
0x18002f618  mov     [rsp+60h+phkResult], rax; phkResult
0x18002f61d  mov     r9d, 20019h; samDesired
0x18002f623  xor     r8d, r8d; ulOptions
0x18002f626  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\FT"...
0x18002f62d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f634  call    cs:__imp_RegOpenKeyExW
0x18002f63a  test    eax, eax
0x18002f63c  jnz     short loc_18002F5F1
0x18002f63e  mov     [rbp+cbData], 4
0x18002f645  lea     rax, [rbp+cbData]
0x18002f649  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002f64e  lea     rax, [rbp+Data]
0x18002f652  mov     [rsp+60h+phkResult], rax; lpData
0x18002f657  lea     r9, [rbp+Type]; lpType
0x18002f65b  xor     r8d, r8d; lpReserved
0x18002f65e  lea     rdx, aCertchaincache; "CertChainCacheOnlyUrlRetrieval"
0x18002f665  mov     rcx, [rbp+hKey]; hKey
0x18002f669  call    cs:__imp_RegQueryValueExW
0x18002f66f  mov     rcx, [rbp+hKey]; hKey
0x18002f673  call    cs:__imp_RegCloseKey
0x18002f679  jmp     loc_18002F5F1
```
