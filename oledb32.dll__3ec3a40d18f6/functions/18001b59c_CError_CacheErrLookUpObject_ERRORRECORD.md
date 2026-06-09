# CError::CacheErrLookUpObject(__ERRORRECORD *)

- ea: `0x18001b59c`
- end: `0x18001b85f`
- name: `?CacheErrLookUpObject@CError@@AEAAJPEAU__ERRORRECORD@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(CError *__hidden this, struct __ERRORRECORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024380`

## callees

- `0x180013870`
- `0x18001b59c`
- `0x180029414`
- `0x180029560`
- `0x18002ec26`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18001b6dc`
- `MSDART!UMSEnterCSWraper` at `0x18001b6dc`
- `KERNEL32!LeaveCriticalSection` at `0x18001b7a3`
- `KERNEL32!LeaveCriticalSection` at `0x18001b7a3`
- `ADVAPI32!RegEnumKeyExW` at `0x18001b689`
- `ADVAPI32!RegEnumKeyExW` at `0x18001b689`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b655`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b655`
- `ADVAPI32!RegCloseKey` at `0x18001b7ae`
- `ADVAPI32!RegCloseKey` at `0x18001b7ae`
- `ole32!CLSIDFromString` at `0x18001b6a4`
- `ole32!CLSIDFromString` at `0x18001b6a4`
- `ole32!CoCreateInstance` at `0x18001b787`
- `ole32!CoCreateInstance` at `0x18001b787`
- `ole32!StringFromGUID2` at `0x18001b5ed`
- `ole32!StringFromGUID2` at `0x18001b5ed`

## string_xrefs

- `0x18001b604`: `CLSID\%s\ExtendedErrors`
- `0x18001b626`: `<CError::CacheErrLookUpObject|OLEDB|ERR> `
- `0x18001b7c9`: `<CError::CacheErrLookUpObject|OLEDB|ERR> `
- `0x18001b7eb`: `<CError::CacheErrLookUpObject|OLEDB|ERR> `
- `0x18001b81d`: `<CError::CacheErrLookUpObject|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CError::CacheErrLookUpObject(CError *this, struct __ERRORRECORD *a2)
{
  unsigned int v4; // r14d
  int v5; // eax
  LSTATUS v6; // edi
  _QWORD *v7; // r15
  __int64 v8; // rsi
  unsigned int v9; // r12d
  size_t *v10; // rax
  unsigned __int64 v11; // rdx
  size_t v12; // rcx
  size_t v13; // r13
  __int64 v14; // rax
  HRESULT Instance; // eax
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  size_t v20; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v21; // [rsp+60h] [rbp-A0h]
  _BYTE v22[16]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+80h] [rbp-80h]
  __int64 v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  OLECHAR sz[128]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[256]; // [rsp+1F0h] [rbp+F0h] BYREF

  v4 = 0;
  cchName = 128;
  hKey = 0;
  if ( StringFromGUID2((const GUID *const)a2 + 2, sz, 128) <= 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(0, L"<CError::CacheErrLookUpObject|OLEDB|ERR> ", 0x27Fu);
    v6 = -2147467259;
LABEL_27:
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v6, L"<CError::CacheErrLookUpObject|OLEDB|ERR> ", 0x285u);
    *((_QWORD *)a2 + 14) = 0;
    *((_QWORD *)a2 + 12) = 0;
    *((_QWORD *)a2 + 13) = 0;
    goto LABEL_30;
  }
  v5 = StringCchPrintfW(SubKey, 0x100u, L"CLSID\\%s\\ExtendedErrors", sz);
  if ( (bidGblFlags & 2) != 0 )
    OLEDBTraceErr(v5, L"<CError::CacheErrLookUpObject|OLEDB|ERR> ", 0x24Du);
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
  if ( !v6 )
  {
    v6 = RegEnumKeyExW(hKey, 0, sz, &cchName, 0, 0, 0, 0);
    if ( !v6 )
    {
      v7 = (_QWORD *)((char *)a2 + 96);
      v6 = CLSIDFromString(sz, (LPCLSID)a2 + 6);
      if ( v6 >= 0 )
      {
        if ( *((_DWORD *)a2 + 4) )
        {
          v17 = 0;
          v8 = 0;
          if ( this != (CError *)-56LL )
          {
            v17 = *((_QWORD *)this + 7);
            UMSEnterCSWraper(&v17);
            v8 = v17;
          }
          memset_0(v22, 0, 0x78u);
          v9 = *((_DWORD *)this + 10);
          if ( v9 )
          {
            v10 = (size_t *)*((_QWORD *)this + 6);
            v11 = v10[1];
            v12 = v10[4];
            v13 = *v10;
            v21 = v11;
            v20 = v12;
            while ( 1 )
            {
              memcpy_0(v22, (const void *)(v12 + v13 * (v4 & (unsigned __int64)-(__int64)(v4 < v11))), v13);
              v14 = v24 - *v7;
              if ( v24 == *v7 )
                v14 = v25 - *((_QWORD *)a2 + 13);
              if ( !v14 && v23 == *((_DWORD *)a2 + 4) )
                break;
              v12 = v20;
              ++v4;
              v11 = v21;
              if ( v4 >= v9 )
                goto LABEL_17;
            }
          }
          else
          {
LABEL_17:
            if ( v4 >= v9 )
            {
              Instance = CoCreateInstance((const IID *const)a2 + 6, 0, 1u, &IID_IErrorLookup, (LPVOID *)a2 + 14);
              v8 = v17;
              v6 = Instance;
            }
          }
          if ( v8 )
          {
            --*(_DWORD *)(v8 + 48);
            LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  if ( v6 < 0 )
    goto LABEL_27;
LABEL_30:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C8540[0],
                           665609,
                           L"<CError::CacheErrLookUpObject|Trace|HR> ",
                           (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b59c  mov     [rsp-8+arg_10], rbx
0x18001b5a1  push    rbp
0x18001b5a2  push    rsi
0x18001b5a3  push    rdi
0x18001b5a4  push    r12
0x18001b5a6  push    r13
0x18001b5a8  push    r14
0x18001b5aa  push    r15
0x18001b5ac  lea     rbp, [rsp-300h]
0x18001b5b4  sub     rsp, 400h
0x18001b5bb  mov     rax, cs:__security_cookie
0x18001b5c2  xor     rax, rsp
0x18001b5c5  mov     [rbp+330h+var_40], rax
0x18001b5cc  mov     r13, rcx
0x18001b5cf  mov     rbx, rdx
0x18001b5d2  lea     rcx, [rdx+20h]; rguid
0x18001b5d6  mov     r8d, 80h; cchMax
0x18001b5dc  xor     r14d, r14d
0x18001b5df  mov     [rsp+430h+cchName], r8d
0x18001b5e4  lea     rdx, [rbp+330h+sz]; lpsz
0x18001b5e8  mov     [rsp+430h+hKey], r14
0x18001b5ed  call    cs:__imp_StringFromGUID2
0x18001b5f3  test    eax, eax
0x18001b5f5  jle     loc_18001B7BA
0x18001b5fb  lea     r9, [rbp+330h+sz]
0x18001b5ff  mov     edx, 100h; unsigned __int64
0x18001b604  lea     r8, aClsidSExtended; "CLSID\\%s\\ExtendedErrors"
0x18001b60b  lea     rcx, [rbp+330h+SubKey]; unsigned __int16 *
0x18001b612  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b617  test    byte ptr cs:_bidGblFlags, 2
0x18001b61e  jz      short loc_18001B634
0x18001b620  mov     r8d, 24Dh; unsigned int
0x18001b626  lea     rdx, aCerrorCacheerr_0; "<CError::CacheErrLookUpObject|OLEDB|ERR"...
0x18001b62d  mov     ecx, eax; int
0x18001b62f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001b634  lea     rax, [rsp+430h+hKey]
0x18001b639  mov     r9d, 20019h; samDesired
0x18001b63f  xor     r8d, r8d; ulOptions
0x18001b642  mov     [rsp+430h+phkResult], rax; phkResult
0x18001b647  lea     rdx, [rbp+330h+SubKey]; lpSubKey
0x18001b64e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001b655  call    cs:__imp_RegOpenKeyExW
0x18001b65b  mov     edi, eax
0x18001b65d  test    eax, eax
0x18001b65f  jnz     loc_18001B7B4
0x18001b665  mov     rcx, [rsp+430h+hKey]; hKey
0x18001b66a  lea     r9, [rsp+430h+cchName]; lpcchName
0x18001b66f  mov     [rsp+430h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001b674  lea     r8, [rbp+330h+sz]; lpName
0x18001b678  mov     [rsp+430h+lpcchClass], r14; lpcchClass
0x18001b67d  xor     edx, edx; dwIndex
0x18001b67f  mov     [rsp+430h+lpClass], r14; lpClass
0x18001b684  mov     [rsp+430h+phkResult], r14; lpReserved
0x18001b689  call    cs:__imp_RegEnumKeyExW
0x18001b68f  mov     edi, eax
0x18001b691  test    eax, eax
0x18001b693  jnz     loc_18001B7A9
0x18001b699  lea     r15, [rbx+60h]
0x18001b69d  mov     rdx, r15; pclsid
0x18001b6a0  lea     rcx, [rbp+330h+sz]; lpsz
0x18001b6a4  call    cs:__imp_CLSIDFromString
0x18001b6aa  mov     edi, eax
0x18001b6ac  test    eax, eax
0x18001b6ae  js      loc_18001B7A9
0x18001b6b4  cmp     [rbx+10h], r14d
0x18001b6b8  jz      loc_18001B7A9
0x18001b6be  lea     rax, [r13+38h]
0x18001b6c2  mov     [rsp+430h+var_3F0], r14
0x18001b6c7  mov     rsi, r14
0x18001b6ca  test    rax, rax
0x18001b6cd  jz      short loc_18001B6E7
0x18001b6cf  mov     rax, [rax]
0x18001b6d2  lea     rcx, [rsp+430h+var_3F0]
0x18001b6d7  mov     [rsp+430h+var_3F0], rax
0x18001b6dc  call    cs:__imp_UMSEnterCSWraper
0x18001b6e2  mov     rsi, [rsp+430h+var_3F0]
0x18001b6e7  xor     edx, edx; Val
0x18001b6e9  lea     rcx, [rsp+430h+var_3C0]; void *
0x18001b6ee  lea     r8d, [rdx+78h]; Size
0x18001b6f2  call    memset_0
0x18001b6f7  mov     r12d, [r13+28h]
0x18001b6fb  test    r12d, r12d
0x18001b6fe  jz      short loc_18001B769
0x18001b700  mov     rax, [r13+30h]
0x18001b704  mov     rdx, [rax+8]
0x18001b708  mov     rcx, [rax+20h]
0x18001b70c  mov     r13, [rax]
0x18001b70f  mov     [rsp+430h+var_3D0], rdx
0x18001b714  mov     [rsp+430h+var_3D8], rcx
0x18001b719  mov     eax, r14d
0x18001b71c  mov     r8, r13; Size
0x18001b71f  cmp     rax, rdx
0x18001b722  sbb     rdx, rdx
0x18001b725  and     rdx, rax
0x18001b728  imul    rdx, r13
0x18001b72c  add     rdx, rcx; Src
0x18001b72f  lea     rcx, [rsp+430h+var_3C0]; void *
0x18001b734  call    memcpy_0
0x18001b739  mov     rax, [rbp+330h+var_360]
0x18001b73d  sub     rax, [r15]
0x18001b740  jnz     short loc_18001B74A
0x18001b742  mov     rax, [rbp+330h+var_358]
0x18001b746  sub     rax, [r15+8]
0x18001b74a  test    rax, rax
0x18001b74d  jnz     short loc_18001B757
0x18001b74f  mov     eax, [rbx+10h]
0x18001b752  cmp     [rbp+330h+var_3B0], eax
0x18001b755  jz      short loc_18001B794
0x18001b757  mov     rcx, [rsp+430h+var_3D8]
0x18001b75c  inc     r14d
0x18001b75f  mov     rdx, [rsp+430h+var_3D0]
0x18001b764  cmp     r14d, r12d
0x18001b767  jb      short loc_18001B719
0x18001b769  cmp     r14d, r12d
0x18001b76c  jb      short loc_18001B794
0x18001b76e  xor     edx, edx; pUnkOuter
0x18001b770  lea     rax, [rbx+70h]
0x18001b774  lea     r9, IID_IErrorLookup; riid
0x18001b77b  mov     [rsp+430h+phkResult], rax; ppv
0x18001b780  mov     rcx, r15; rclsid
0x18001b783  lea     r8d, [rdx+1]; dwClsContext
0x18001b787  call    cs:__imp_CoCreateInstance
0x18001b78d  mov     rsi, [rsp+430h+var_3F0]
0x18001b792  mov     edi, eax
0x18001b794  xor     r14d, r14d
0x18001b797  test    rsi, rsi
0x18001b79a  jz      short loc_18001B7A9
0x18001b79c  dec     dword ptr [rsi+30h]
0x18001b79f  lea     rcx, [rsi+8]; lpCriticalSection
0x18001b7a3  call    cs:__imp_LeaveCriticalSection
0x18001b7a9  mov     rcx, [rsp+430h+hKey]; hKey
0x18001b7ae  call    cs:__imp_RegCloseKey
0x18001b7b4  test    edi, edi
0x18001b7b6  js      short loc_18001B7DC
0x18001b7b8  jmp     short loc_18001B80D
0x18001b7ba  test    byte ptr cs:_bidGblFlags, 2
0x18001b7c1  jz      short loc_18001B7D7
0x18001b7c3  mov     r8d, 27Fh; unsigned int
0x18001b7c9  lea     rdx, aCerrorCacheerr_0; "<CError::CacheErrLookUpObject|OLEDB|ERR"...
0x18001b7d0  xor     ecx, ecx; int
0x18001b7d2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001b7d7  mov     edi, 80004005h
0x18001b7dc  test    byte ptr cs:_bidGblFlags, 2
0x18001b7e3  jz      short loc_18001B7F9
0x18001b7e5  mov     r8d, 285h; unsigned int
0x18001b7eb  lea     rdx, aCerrorCacheerr_0; "<CError::CacheErrLookUpObject|OLEDB|ERR"...
0x18001b7f2  mov     ecx, edi; int
0x18001b7f4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001b7f9  mov     [rbx+70h], r14
0x18001b7fd  mov     qword ptr [rbx+60h], 0
0x18001b805  mov     qword ptr [rbx+68h], 0
0x18001b80d  test    byte ptr cs:_bidGblFlags, 2
0x18001b814  jz      short loc_18001B833
0x18001b816  mov     rcx, cs:off_1800C8540; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001b81d  lea     r8, aCerrorCacheerr; "<CError::CacheErrLookUpObject|Trace|HR>"...
0x18001b824  mov     r9d, edi
0x18001b827  mov     edx, 0A2809h
0x18001b82c  call    _bidTraceHR
0x18001b831  mov     edi, eax
0x18001b833  mov     eax, edi
0x18001b835  mov     rcx, [rbp+330h+var_40]
0x18001b83c  xor     rcx, rsp; StackCookie
0x18001b83f  call    __security_check_cookie
0x18001b844  mov     rbx, [rsp+430h+arg_10]
0x18001b84c  add     rsp, 400h
0x18001b853  pop     r15
0x18001b855  pop     r14
0x18001b857  pop     r13
0x18001b859  pop     r12
0x18001b85b  pop     rdi
0x18001b85c  pop     rsi
0x18001b85d  pop     rbp
0x18001b85e  retn
```
