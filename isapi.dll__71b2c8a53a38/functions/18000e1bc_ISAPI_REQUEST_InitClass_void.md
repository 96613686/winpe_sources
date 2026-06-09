# ISAPI_REQUEST::InitClass(void)

- ea: `0x18000e1bc`
- end: `0x18000e35e`
- name: `?InitClass@ISAPI_REQUEST@@SAHXZ`
- size: `418`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001f2c`

## callees

- `0x180001020`
- `0x1800033a0`
- `0x18000e1bc`
- `0x180011af4`
- `0x180011b80`
- `0x1800124c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e31f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e31f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e2ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e2ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e2c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e2c4`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000e21d`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000e21d`

## string_xrefs

- `0x18000e2b6`: `System\CurrentControlSet\Services\w3svc\Parameters`
- `0x18000e2d9`: `DontFlushCachedIsapiResponses`

## pseudocode

```c
__int64 ISAPI_REQUEST::InitClass(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  int v1; // eax
  DWORD v2; // ecx
  wchar_t *v4; // rcx
  LSTATUS v5; // eax
  DWORD Type; // [rsp+30h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-2Ch] BYREF
  DWORD cbData; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v10[4]; // [rsp+48h] [rbp-18h] BYREF

  v10[0] = 1;
  v10[1] = 400;
  v10[2] = 72;
  if ( ISAPI_REQUEST::sm_pachIsapiRequest )
    return 1;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( !v0 )
  {
    ISAPI_REQUEST::sm_pachIsapiRequest = 0;
    goto LABEL_17;
  }
  ISAPI_REQUEST::sm_pachIsapiRequest = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                         v0,
                                         "IsapiRequest",
                                         (const struct ALLOC_CACHE_CONFIGURATION *)v10,
                                         1);
  if ( !ISAPI_REQUEST::sm_pachIsapiRequest )
  {
LABEL_17:
    v2 = 8;
    goto LABEL_6;
  }
  ISAPI_REQUEST::sm_pTraceLog = 0;
  v1 = TOKEN_KEY::Initialize();
  if ( v1 < 0 )
  {
LABEL_5:
    v2 = WIN32_FROM_HRESULT(v1);
LABEL_6:
    SetLastError(v2);
    return 0;
  }
  v4 = (wchar_t *)operator new(0xA0Cu);
  if ( !v4 )
  {
    ISAPI_REQUEST::sm_pLogonProvider = 0;
    goto LABEL_17;
  }
  ISAPI_REQUEST::sm_pLogonProvider = v4;
  *v4 = 0;
  v4[256] = 0;
  *((_QWORD *)v4 + 320) = 0;
  *((_DWORD *)v4 + 642) = 0;
  v1 = IIS_LOGON_PROVIDER::InitializeInstance((IIS_LOGON_PROVIDER *)v4);
  if ( v1 < 0 )
    goto LABEL_5;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\w3svc\\Parameters", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"DontFlushCachedIsapiResponses", 0, &Type, Data, &cbData);
    if ( !v5 && Type == 4 )
    {
      LOBYTE(v5) = *(_DWORD *)Data != 0;
      ISAPI_REQUEST::sm_fDontFlushCachedResponses = v5;
    }
    RegCloseKey(hKey);
  }
  return 1;
}

```

## disassembly

```asm
0x18000e1bc  push    rbp
0x18000e1be  mov     rbp, rsp
0x18000e1c1  sub     rsp, 60h
0x18000e1c5  mov     rax, cs:__security_cookie
0x18000e1cc  xor     rax, rsp
0x18000e1cf  mov     [rbp+var_8], rax
0x18000e1d3  cmp     cs:?sm_pachIsapiRequest@ISAPI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ISAPI_REQUEST::sm_pachIsapiRequest
0x18000e1db  mov     [rbp+var_18], 1
0x18000e1e2  mov     [rbp+var_14], 190h
0x18000e1e9  mov     [rbp+var_10], 48h ; 'H'
0x18000e1f0  jnz     loc_18000E325
0x18000e1f6  mov     ecx, 100h; Size
0x18000e1fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e200  test    rax, rax
0x18000e203  jz      loc_18000E349
0x18000e209  mov     r9d, 1
0x18000e20f  lea     r8, [rbp+var_18]
0x18000e213  lea     rdx, aIsapirequest; "IsapiRequest"
0x18000e21a  mov     rcx, rax
0x18000e21d  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000e223  mov     cs:?sm_pachIsapiRequest@ISAPI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * ISAPI_REQUEST::sm_pachIsapiRequest
0x18000e22a  test    rax, rax
0x18000e22d  jz      loc_18000E354
0x18000e233  mov     cs:?sm_pTraceLog@ISAPI_REQUEST@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * ISAPI_REQUEST::sm_pTraceLog
0x18000e23e  call    ?Initialize@TOKEN_KEY@@SAJXZ; TOKEN_KEY::Initialize(void)
0x18000e243  test    eax, eax
0x18000e245  jns     short loc_18000E25D
0x18000e247  mov     ecx, eax; int
0x18000e249  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000e24e  mov     ecx, eax; dwErrCode
0x18000e250  call    cs:__imp_SetLastError
0x18000e256  xor     eax, eax
0x18000e258  jmp     loc_18000E32A
0x18000e25d  mov     ecx, 0A0Ch; Size
0x18000e262  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e267  mov     rcx, rax; this
0x18000e26a  test    rax, rax
0x18000e26d  jz      loc_18000E33C
0x18000e273  xor     eax, eax
0x18000e275  mov     cs:?sm_pLogonProvider@ISAPI_REQUEST@@0PEAVIIS_LOGON_PROVIDER@@EA, rcx; IIS_LOGON_PROVIDER * ISAPI_REQUEST::sm_pLogonProvider
0x18000e27c  mov     [rcx], ax
0x18000e27f  mov     [rcx+200h], ax
0x18000e286  mov     [rcx+0A00h], rax
0x18000e28d  mov     [rcx+0A08h], eax
0x18000e293  call    ?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ; IIS_LOGON_PROVIDER::InitializeInstance(void)
0x18000e298  test    eax, eax
0x18000e29a  js      short loc_18000E247
0x18000e29c  lea     rax, [rbp+hKey]
0x18000e2a0  mov     [rbp+hKey], 0
0x18000e2a8  mov     r9d, 20019h; samDesired
0x18000e2ae  mov     [rsp+60h+phkResult], rax; phkResult
0x18000e2b3  xor     r8d, r8d; ulOptions
0x18000e2b6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x18000e2bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e2c4  call    cs:__imp_RegOpenKeyExW
0x18000e2ca  test    eax, eax
0x18000e2cc  jnz     short loc_18000E325
0x18000e2ce  mov     rcx, [rbp+hKey]; hKey
0x18000e2d2  lea     r9, [rbp+Type]; lpType
0x18000e2d6  mov     [rbp+Type], eax
0x18000e2d9  lea     rdx, ValueName; "DontFlushCachedIsapiResponses"
0x18000e2e0  mov     dword ptr [rbp+Data], eax
0x18000e2e3  xor     r8d, r8d; lpReserved
0x18000e2e6  lea     rax, [rbp+cbData]
0x18000e2ea  mov     [rbp+cbData], 4
0x18000e2f1  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000e2f6  lea     rax, [rbp+Data]
0x18000e2fa  mov     [rsp+60h+phkResult], rax; lpData
0x18000e2ff  call    cs:__imp_RegQueryValueExW
0x18000e305  test    eax, eax
0x18000e307  jnz     short loc_18000E31B
0x18000e309  cmp     [rbp+Type], 4
0x18000e30d  jnz     short loc_18000E31B
0x18000e30f  cmp     dword ptr [rbp+Data], eax
0x18000e312  setnz   al
0x18000e315  mov     cs:?sm_fDontFlushCachedResponses@ISAPI_REQUEST@@0HA, eax; int ISAPI_REQUEST::sm_fDontFlushCachedResponses
0x18000e31b  mov     rcx, [rbp+hKey]; hKey
0x18000e31f  call    cs:__imp_RegCloseKey
0x18000e325  mov     eax, 1
0x18000e32a  mov     rcx, [rbp+var_8]
0x18000e32e  xor     rcx, rsp; StackCookie
0x18000e331  call    __security_check_cookie
0x18000e336  add     rsp, 60h
0x18000e33a  pop     rbp
0x18000e33b  retn
0x18000e33c  mov     cs:?sm_pLogonProvider@ISAPI_REQUEST@@0PEAVIIS_LOGON_PROVIDER@@EA, 0; IIS_LOGON_PROVIDER * ISAPI_REQUEST::sm_pLogonProvider
0x18000e347  jmp     short loc_18000E354
0x18000e349  mov     cs:?sm_pachIsapiRequest@ISAPI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ISAPI_REQUEST::sm_pachIsapiRequest
0x18000e354  mov     ecx, 8
0x18000e359  jmp     loc_18000E250
```
