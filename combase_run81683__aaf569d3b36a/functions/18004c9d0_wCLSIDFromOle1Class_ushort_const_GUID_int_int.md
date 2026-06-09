# wCLSIDFromOle1Class(ushort const *,_GUID *,int,int)

- ea: `0x18004c9d0`
- end: `0x18004cc1c`
- name: `?wCLSIDFromOle1Class@@YAJPEBGPEAU_GUID@@HH@Z`
- size: `588`
- prototype: `HRESULT __fastcall(const wchar_t *lpsz, _GUID *lpclsid, int fForceAssign, int recursionCount)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004c480`
- `0x18004c4d8`
- `0x18004c9d0`

## callees

- `0x18004c9d0`
- `0x18004cc24`
- `0x18004cce8`
- `0x18004d180`
- `0x18004d348`
- `0x180058e20`
- `0x1801999b0`
- `0x18019a080`
- `0x18019a654`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004cad7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004cad7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cafa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cbc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cafa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cbc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ca6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ca6d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004cbae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004cbae`

## string_xrefs

- `0x18004cc04`: `onecore\com\combase\classregcommon\comoleapi.cxx`

## pseudocode

```c
unsigned int __fastcall wCLSIDFromOle1Class(const wchar_t *lpsz, _GUID *lpclsid, int fForceAssign, int recursionCount)
{
  int v8; // esi
  LSTATUS ValueW; // ebx
  LSTATUS v11; // ecx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  unsigned int cbValue; // [rsp+40h] [rbp+0h] BYREF
  HKEY__ *hkProgID; // [rsp+48h] [rbp+8h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+18h] BYREF
  wchar_t sz[256]; // [rsp+60h] [rbp+20h] BYREF
  void *retaddr; // [rsp+2B8h] [rbp+278h]

  memset_0(sz, 0, sizeof(sz));
  cbValue = 512;
  hkProgID = 0;
  if ( !lpsz )
    return -2147024809;
  if ( !*lpsz )
    return -2147221005;
  v8 = wRegOpenProgIDKey(lpsz, &hkProgID);
  if ( v8 < 0 )
    return Ole10_CLSIDFromString(lpsz, lpclsid, fForceAssign);
  hkey = hkProgID;
  pdwType = 0;
  if ( !RegOpenKeyExW(hkProgID, Com::Catalog::Constants::CLSID, 0, 0x20019u, &hkey) )
  {
    ValueW = RegGetValueW(hkey, 0, 0, 0x30000003u, &pdwType, sz, &cbValue);
    RegCloseKey(hkey);
    v11 = 0;
    if ( ValueW != 2 )
      v11 = ValueW;
    if ( !v11 )
    {
LABEL_11:
      RegCloseKey(hkProgID);
      if ( v8 >= 0 )
        return wGUIDFromString(sz, lpclsid) == 0 ? 0x800401F3 : 0;
      return Ole10_CLSIDFromString(lpsz, lpclsid, fForceAssign);
    }
  }
  if ( wRegQueryValue(hkProgID, Com::Catalog::Constants::CurVer, 0, &cbValue) )
    goto LABEL_6;
  v12 = cbValue + 15LL;
  if ( v12 <= cbValue )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
  v14 = alloca(v13);
  v15 = alloca(v13);
  if ( wRegQueryValue(hkProgID, Com::Catalog::Constants::CurVer, (wchar_t *)&cbValue, &cbValue)
    || CompareStringW(0x400u, 1u, (PCNZWCH)&cbValue, -1, lpsz, -1) == 2 )
  {
LABEL_6:
    v8 = -2147467259;
    goto LABEL_11;
  }
  RegCloseKey(hkProgID);
  if ( recursionCount + 1 < 10 )
    return wCLSIDFromOle1Class((const wchar_t *)&cbValue, lpclsid, fForceAssign, recursionCount + 1);
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x1B0u,
    "onecore\\com\\combase\\classregcommon\\comoleapi.cxx",
    -2147221165,
    "Recursion limit reached! ProgID %ls",
    lpsz);
  return -2147221165;
}

```

## disassembly

```asm
0x18004c9d0  push    rbp
0x18004c9d2  push    rbx
0x18004c9d3  push    rsi
0x18004c9d4  push    rdi
0x18004c9d5  push    r12
0x18004c9d7  push    r13
0x18004c9d9  push    r14
0x18004c9db  push    r15
0x18004c9dd  sub     rsp, 278h
0x18004c9e4  lea     rbp, [rsp+40h]
0x18004c9e9  mov     rax, cs:__security_cookie
0x18004c9f0  xor     rax, rbp
0x18004c9f3  mov     [rbp+270h+var_50], rax
0x18004c9fa  mov     r15d, fForceAssign
0x18004c9fd  mov     r14, lpclsid
0x18004ca00  mov     rdi, lpsz
0x18004ca03  mov     ebx, 200h
0x18004ca08  mov     fForceAssign, ebx; Size
0x18004ca0b  lea     lpsz, [rbp+270h+sz]; void *
0x18004ca0f  xor     edx, edx; Val
0x18004ca11  mov     r13d, recursionCount
0x18004ca14  call    memset_0
0x18004ca19  xor     r12d, r12d
0x18004ca1c  mov     [rbp+270h+cbValue], ebx
0x18004ca1f  mov     [rbp+270h+hkProgID], r12
0x18004ca23  test    rdi, rdi
0x18004ca26  jz      loc_18004CB3E
0x18004ca2c  cmp     [rdi], r12w
0x18004ca30  jz      loc_18004CB45
0x18004ca36  lea     lpclsid, [rbp+270h+hkProgID]; lphkeyClsid
0x18004ca3a  mov     lpsz, rdi; pszProgID
0x18004ca3d  call    ?wRegOpenProgIDKey@@YAJPEBGPEAPEAUHKEY__@@@Z; wRegOpenProgIDKey(ushort const *,HKEY__ * *)
0x18004ca42  mov     esi, eax
0x18004ca44  test    eax, eax
0x18004ca46  js      short loc_18004CA9D
0x18004ca48  mov     lpsz, [rbp+270h+hkProgID]; hKey
0x18004ca4c  lea     rax, [rbp+270h+hkey]
0x18004ca50  mov     recursionCount, 20019h; samDesired
0x18004ca56  mov     [rbp+270h+hkey], lpsz
0x18004ca5a  xor     fForceAssign, fForceAssign; ulOptions
0x18004ca5d  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18004ca62  lea     lpclsid, ?CLSID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18004ca69  mov     [rbp+270h+pdwType], r12d
0x18004ca6d  call    cs:__imp_RegOpenKeyExW
0x18004ca73  test    eax, eax
0x18004ca75  jz      short loc_18004CAAD
0x18004ca77  mov     lpsz, [rbp+270h+hkProgID]; hKey
0x18004ca7b  lea     r9, [rbp+270h+cbValue]; lpdwSize
0x18004ca7f  xor     fForceAssign, fForceAssign; lpValue
0x18004ca82  lea     lpclsid, ?CurVer@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18004ca89  call    wRegQueryValue
0x18004ca8e  test    eax, eax
0x18004ca90  jz      loc_18004CB4C
0x18004ca96  mov     esi, 80004005h
0x18004ca9b  jmp     short loc_18004CAF6
0x18004ca9d  mov     fForceAssign, r15d; fForceAssign
0x18004caa0  mov     lpclsid, r14; pclsid
0x18004caa3  mov     lpsz, rdi; szOle1
0x18004caa6  call    ?Ole10_CLSIDFromString@@YAJPEBGPEAU_GUID@@H@Z; Ole10_CLSIDFromString(ushort const *,_GUID *,int)
0x18004caab  jmp     short loc_18004CB1B
0x18004caad  mov     lpsz, [rbp+270h+hkey]; hkey
0x18004cab1  lea     rax, [rbp+270h+cbValue]
0x18004cab5  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18004caba  mov     recursionCount, 30000003h; dwFlags
0x18004cac0  lea     rax, [rbp+270h+sz]
0x18004cac4  xor     fForceAssign, fForceAssign; lpValue
0x18004cac7  mov     [rsp+2B0h+pvData], rax; pvData
0x18004cacc  xor     edx, edx; lpSubKey
0x18004cace  lea     rax, [rbp+270h+pdwType]
0x18004cad2  mov     [rsp+2B0h+phkResult], rax; pdwType
0x18004cad7  call    cs:__imp_RegGetValueW
0x18004cadd  mov     lpsz, [rbp+270h+hkey]; hKey
0x18004cae1  mov     ebx, eax
0x18004cae3  call    cs:__imp_RegCloseKey
0x18004cae9  cmp     ebx, 2
0x18004caec  mov     ecx, r12d
0x18004caef  cmovnz  ecx, ebx
0x18004caf2  test    ecx, ecx
0x18004caf4  jnz     short loc_18004CA77
0x18004caf6  mov     lpsz, [rbp+270h+hkProgID]; hKey
0x18004cafa  call    cs:__imp_RegCloseKey
0x18004cb00  test    esi, esi
0x18004cb02  js      short loc_18004CA9D
0x18004cb04  mov     lpclsid, r14; pguid
0x18004cb07  lea     lpsz, [rbp+270h+sz]; lpsz
0x18004cb0b  call    ?wGUIDFromString@@YAHPEBGPEAU_GUID@@@Z; wGUIDFromString(ushort const *,_GUID *)
0x18004cb10  neg     eax
0x18004cb12  sbb     eax, eax
0x18004cb14  not     eax
0x18004cb16  and     eax, 800401F3h
0x18004cb1b  mov     lpsz, [rbp+270h+var_50]
0x18004cb22  xor     lpsz, rbp; StackCookie
0x18004cb25  call    __security_check_cookie
0x18004cb2a  lea     rsp, [rbp+238h]
0x18004cb31  pop     r15
0x18004cb33  pop     r14
0x18004cb35  pop     r13
0x18004cb37  pop     r12
0x18004cb39  pop     rdi
0x18004cb3a  pop     rsi
0x18004cb3b  pop     rbx
0x18004cb3c  pop     rbp
0x18004cb3d  retn
0x18004cb3e  mov     eax, 80070057h
0x18004cb43  jmp     short loc_18004CB1B
0x18004cb45  mov     eax, 800401F3h
0x18004cb4a  jmp     short loc_18004CB1B
0x18004cb4c  mov     eax, [rbp+270h+cbValue]
0x18004cb4f  lea     lpsz, [rax+0Fh]
0x18004cb53  cmp     lpsz, rax
0x18004cb56  ja      short loc_18004CB62
0x18004cb58  mov     lpsz, 0FFFFFFFFFFFFFF0h
0x18004cb62  and     lpsz, 0FFFFFFFFFFFFFFF0h
0x18004cb66  mov     rax, lpsz
0x18004cb69  call    _alloca_probe
0x18004cb6e  sub     rsp, lpsz
0x18004cb71  lea     r9, [rbp+270h+cbValue]; lpdwSize
0x18004cb75  mov     lpsz, [rbp+270h+hkProgID]; hKey
0x18004cb79  lea     lpclsid, ?CurVer@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18004cb80  lea     rbx, [rsp+2B0h+cbValue]
0x18004cb85  mov     r8, rbx; lpValue
0x18004cb88  call    wRegQueryValue
0x18004cb8d  test    eax, eax
0x18004cb8f  jnz     loc_18004CA96
0x18004cb95  or      recursionCount, 0FFFFFFFFh; cchCount1
0x18004cb99  lea     edx, [rax+1]; dwCmpFlags
0x18004cb9c  mov     dword ptr [rsp+2B0h+pvData], recursionCount; cchCount2
0x18004cba1  mov     r8, rbx; lpString1
0x18004cba4  mov     ecx, 400h; Locale
0x18004cba9  mov     [rsp+2B0h+phkResult], rdi; lpString2
0x18004cbae  call    cs:__imp_CompareStringW
0x18004cbb4  cmp     eax, 2
0x18004cbb7  jz      loc_18004CA96
0x18004cbbd  mov     lpsz, [rbp+270h+hkProgID]; hKey
0x18004cbc1  call    cs:__imp_RegCloseKey
0x18004cbc7  lea     recursionCount, [r13+1]; recursionCount
0x18004cbcb  cmp     recursionCount, 0Ah
0x18004cbcf  jge     short loc_18004CBE4
0x18004cbd1  mov     fForceAssign, r15d; fForceAssign
0x18004cbd4  mov     lpclsid, r14; lpclsid
0x18004cbd7  mov     lpsz, rbx; lpsz
0x18004cbda  call    ?wCLSIDFromOle1Class@@YAJPEBGPEAU_GUID@@HH@Z; wCLSIDFromOle1Class(ushort const *,_GUID *,int,int)
0x18004cbdf  jmp     loc_18004CB1B
0x18004cbe4  mov     lpsz, [rbp+278h]; callerReturnAddress
0x18004cbeb  lea     rax, aRecursionLimit; "Recursion limit reached! ProgID %ls"
0x18004cbf2  mov     ebx, 80040153h
0x18004cbf7  mov     [rsp+2B0h+pvData], rdi
0x18004cbfc  mov     recursionCount, ebx; hr
0x18004cbff  mov     [rsp+2B0h+phkResult], rax; formatString
0x18004cc04  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\classregcommon\\"...
0x18004cc0b  mov     edx, 1B0h; lineNumber
0x18004cc10  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cc15  mov     eax, ebx
0x18004cc17  jmp     loc_18004CB1B
```
