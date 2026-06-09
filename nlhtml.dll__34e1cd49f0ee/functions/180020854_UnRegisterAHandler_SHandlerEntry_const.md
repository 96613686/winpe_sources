# UnRegisterAHandler(SHandlerEntry const &)

- ea: `0x180020854`
- end: `0x180020b80`
- name: `?UnRegisterAHandler@@YAJAEBUSHandlerEntry@@@Z`
- size: `812`
- prototype: `__int64 __fastcall(const struct SHandlerEntry *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002122c`

## callees

- `0x1800112e0`
- `0x180011324`
- `0x180014130`
- `0x1800145a0`
- `0x18001f904`
- `0x180020304`
- `0x180020854`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020a40`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020a40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020a17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020a17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b45`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002097c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020afd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002097c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020afd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020901`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800209d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020a98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020901`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800209d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020a98`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020ab5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020ac0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020ab5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020ac0`

## string_xrefs

- `0x180020914`: `CLSID\`
- `0x1800208d4`: `CLSID`

## pseudocode

```c
__int64 __fastcall UnRegisterAHandler(const struct SHandlerEntry *a1)
{
  unsigned int v1; // r14d
  LSTATUS v2; // esi
  unsigned int v3; // edi
  DWORD v4; // r15d
  __int64 v5; // rcx
  LSTATUS v6; // eax
  __int64 v7; // rax
  LSTATUS v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  LSTATUS v11; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v18[7]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t SubKey[6]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v20[258]; // [rsp+ACh] [rbp-54h] BYREF
  WCHAR Data[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v18[0] = (wchar_t *)L"{eec97550-47a9-11cf-b952-00aa0051fe20}";
  v18[1] = L"HTML File persistent handler";
  v18[2] = L"PersistentAddinsRegistered";
  v18[4] = L"{89BCB740-6119-101A-BCB7-00DD010655AF}";
  v18[5] = L"{e0ca5340-4534-11cf-b952-00aa0051fe20}";
  v18[3] = 0;
  v1 = DestroyKeyValues((const wchar_t *const *)v18, 6);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = 0;
  v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2001Fu, &hKey);
  v4 = 0;
  while ( !v3 )
  {
    v2 = StringCchCopyW(SubKey, 0x104u, L"CLSID\\");
    v5 = -1;
    do
      ++v5;
    while ( SubKey[v5] );
    ftLastWriteTime = 0;
    cchName = 260 - v5;
    v6 = RegEnumKeyExW(hKey, v4++, &SubKey[(unsigned int)v5], &cchName, 0, 0, 0, &ftLastWriteTime);
    v3 = v6;
    if ( !v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( SubKey[v7] );
      StringCchCatW(SubKey, 260 - v7, L"\\PersistentHandler");
      phkResult = 0;
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &phkResult) )
      {
LABEL_22:
        v2 = 0;
      }
      else
      {
        Type = 0;
        cchName = 520;
        v8 = RegQueryValueExW(phkResult, 0, 0, &Type, (LPBYTE)Data, &cchName);
        RegCloseKey(phkResult);
        if ( v8 || (unsigned int)_o__wcsicmp(Data) )
        {
          v1 = v8;
          goto LABEL_22;
        }
        v9 = -1;
        do
          ++v9;
        while ( SubKey[v9] );
        v10 = 2 * v9 - 36;
        if ( v10 >= 0x208 )
          _report_rangecheckfailure();
        *(wchar_t *)((char *)SubKey + v10) = 0;
        v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &phkResult);
        if ( !v2 )
        {
          if ( v1 )
            RegDeleteKeyW(phkResult, L"PersistentHandler");
          else
            v1 = RegDeleteKeyW(phkResult, L"PersistentHandler");
          v4 = 0;
        }
        cchName = 260;
        v11 = RegEnumKeyExW(phkResult, 0, Data, &cchName, 0, 0, 0, &ftLastWriteTime);
        RegCloseKey(phkResult);
        if ( v11 == 259 )
          RemoveAClass(v20);
      }
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( v3 == 259 )
    v3 = v2;
  if ( v3 )
    return v3;
  return v1;
}

```

## disassembly

```asm
0x180020854  push    rbp
0x180020856  push    rbx
0x180020857  push    rsi
0x180020858  push    rdi
0x180020859  push    r12
0x18002085b  push    r13
0x18002085d  push    r14
0x18002085f  push    r15
0x180020861  lea     rbp, [rsp-3D8h]
0x180020869  sub     rsp, 4D8h
0x180020870  mov     rax, cs:__security_cookie
0x180020877  xor     rax, rsp
0x18002087a  mov     [rbp+410h+var_50], rax
0x180020881  mov     rax, cs:off_18002B130; "{eec97550-47a9-11cf-b952-00aa0051fe20}"
0x180020888  lea     rcx, [rsp+510h+var_4A8]; wchar_t **
0x18002088d  mov     [rsp+510h+var_4A8], rax
0x180020892  xor     r12d, r12d
0x180020895  mov     rax, cs:off_18002B138; "HTML File persistent handler"
0x18002089c  mov     [rsp+510h+var_4A0], rax
0x1800208a1  lea     rax, aPersistentaddi; "PersistentAddinsRegistered"
0x1800208a8  mov     [rsp+510h+var_498], rax
0x1800208ad  lea     rax, a89bcb740611910; "{89BCB740-6119-101A-BCB7-00DD010655AF}"
0x1800208b4  mov     [rbp+410h+var_488], rax
0x1800208b8  lea     edx, [r12+6]; int
0x1800208bd  mov     rax, cs:off_18002B140; "{e0ca5340-4534-11cf-b952-00aa0051fe20}"
0x1800208c4  mov     [rbp+410h+var_480], rax
0x1800208c8  mov     [rbp+410h+var_490], r12
0x1800208cc  call    ?DestroyKeyValues@@YAJPEBQEB_WH@Z; DestroyKeyValues(wchar_t const * const *,int)
0x1800208d1  mov     r14d, eax
0x1800208d4  lea     rdx, aClsid_1; "CLSID"
0x1800208db  lea     rax, [rsp+510h+hKey]
0x1800208e0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800208e4  mov     r9d, 2001Fh; samDesired
0x1800208ea  mov     [rsp+510h+phkResult], rax; phkResult
0x1800208ef  xor     r8d, r8d; ulOptions
0x1800208f2  mov     [rsp+510h+hKey], r13
0x1800208f7  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800208fe  mov     esi, r12d
0x180020901  call    cs:__imp_RegOpenKeyExW
0x180020907  mov     edi, eax
0x180020909  mov     r15d, r12d
0x18002090c  test    edi, edi
0x18002090e  jnz     loc_180020B3B
0x180020914  lea     r8, aClsid; "CLSID\\"
0x18002091b  mov     edx, 104h; unsigned __int64
0x180020920  lea     rcx, [rbp+410h+SubKey]; wchar_t *
0x180020924  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180020929  mov     esi, eax
0x18002092b  mov     rcx, r13
0x18002092e  lea     rax, [rbp+410h+SubKey]
0x180020932  inc     rcx
0x180020935  cmp     [rax+rcx*2], r12w
0x18002093a  jnz     short loc_180020932
0x18002093c  mov     eax, 104h
0x180020941  mov     qword ptr [rsp+510h+ftLastWriteTime.dwLowDateTime], r12
0x180020946  sub     eax, ecx
0x180020948  lea     r8, [rbp+410h+SubKey]
0x18002094c  mov     [rsp+510h+cchName], eax
0x180020950  lea     r9, [rsp+510h+cchName]; lpcchName
0x180020955  mov     eax, ecx
0x180020957  mov     edx, r15d; dwIndex
0x18002095a  mov     rcx, [rsp+510h+hKey]; hKey
0x18002095f  lea     r8, [r8+rax*2]; lpName
0x180020963  lea     rax, [rsp+510h+ftLastWriteTime]
0x180020968  mov     [rsp+510h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002096d  mov     [rsp+510h+lpcchClass], r12; lpcchClass
0x180020972  mov     [rsp+510h+lpClass], r12; lpClass
0x180020977  mov     [rsp+510h+phkResult], r12; lpReserved
0x18002097c  call    cs:__imp_RegEnumKeyExW
0x180020982  inc     r15d
0x180020985  mov     edi, eax
0x180020987  test    eax, eax
0x180020989  jnz     short loc_18002090C
0x18002098b  lea     rcx, [rbp+410h+SubKey]
0x18002098f  mov     rax, r13
0x180020992  inc     rax
0x180020995  cmp     [rcx+rax*2], r12w
0x18002099a  jnz     short loc_180020992
0x18002099c  mov     edx, 104h
0x1800209a1  lea     r8, aPersistenthand; "\\PersistentHandler"
0x1800209a8  sub     rdx, rax; unsigned __int64
0x1800209ab  lea     rcx, [rbp+410h+SubKey]; wchar_t *
0x1800209af  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800209b4  lea     rax, [rsp+510h+var_4C8]
0x1800209b9  mov     [rsp+510h+var_4C8], r12
0x1800209be  mov     r9d, 2001Fh; samDesired
0x1800209c4  mov     [rsp+510h+phkResult], rax; phkResult
0x1800209c9  xor     r8d, r8d; ulOptions
0x1800209cc  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x1800209d0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800209d7  call    cs:__imp_RegOpenKeyExW
0x1800209dd  test    eax, eax
0x1800209df  jnz     loc_180020B2D
0x1800209e5  mov     rcx, [rsp+510h+var_4C8]; hKey
0x1800209ea  lea     rax, [rsp+510h+cchName]
0x1800209ef  mov     [rsp+510h+lpClass], rax; lpcbData
0x1800209f4  lea     r9, [rsp+510h+Type]; lpType
0x1800209f9  lea     rax, [rbp+410h+Data]
0x180020a00  mov     [rsp+510h+Type], r12d
0x180020a05  xor     r8d, r8d; lpReserved
0x180020a08  mov     [rsp+510h+phkResult], rax; lpData
0x180020a0d  xor     edx, edx; lpValueName
0x180020a0f  mov     [rsp+510h+cchName], 208h
0x180020a17  call    cs:__imp_RegQueryValueExW
0x180020a1d  mov     rcx, [rsp+510h+var_4C8]; hKey
0x180020a22  mov     ebx, eax
0x180020a24  call    cs:__imp_RegCloseKey
0x180020a2a  test    ebx, ebx
0x180020a2c  jnz     loc_180020B2A
0x180020a32  mov     rdx, cs:off_18002B130; "{eec97550-47a9-11cf-b952-00aa0051fe20}"
0x180020a39  lea     rcx, [rbp+410h+Data]
0x180020a40  call    cs:__imp__o__wcsicmp
0x180020a46  test    eax, eax
0x180020a48  jnz     loc_180020B2A
0x180020a4e  lea     rcx, [rbp+410h+SubKey]
0x180020a52  mov     rax, r13
0x180020a55  inc     rax
0x180020a58  cmp     [rcx+rax*2], r12w
0x180020a5d  jnz     short loc_180020A55
0x180020a5f  lea     rcx, ds:0FFFFFFFFFFFFFFDCh[rax*2]
0x180020a67  cmp     rcx, 208h
0x180020a6e  jnb     loc_180020B35
0x180020a74  mov     [rbp+rcx+410h+SubKey], r12w
0x180020a7a  lea     rax, [rsp+510h+var_4C8]
0x180020a7f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180020a86  mov     [rsp+510h+phkResult], rax; phkResult
0x180020a8b  mov     r9d, 2001Fh; samDesired
0x180020a91  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x180020a95  xor     r8d, r8d; ulOptions
0x180020a98  call    cs:__imp_RegOpenKeyExW
0x180020a9e  mov     esi, eax
0x180020aa0  test    eax, eax
0x180020aa2  jnz     short loc_180020AC9
0x180020aa4  mov     rcx, [rsp+510h+var_4C8]; hKey
0x180020aa9  lea     rdx, SubKey; "PersistentHandler"
0x180020ab0  test    r14d, r14d
0x180020ab3  jnz     short loc_180020AC0
0x180020ab5  call    cs:__imp_RegDeleteKeyW
0x180020abb  mov     r14d, eax
0x180020abe  jmp     short loc_180020AC6
0x180020ac0  call    cs:__imp_RegDeleteKeyW
0x180020ac6  mov     r15d, r12d
0x180020ac9  mov     rcx, [rsp+510h+var_4C8]; hKey
0x180020ace  lea     rax, [rsp+510h+ftLastWriteTime]
0x180020ad3  mov     [rsp+510h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180020ad8  lea     r9, [rsp+510h+cchName]; lpcchName
0x180020add  mov     [rsp+510h+lpcchClass], r12; lpcchClass
0x180020ae2  lea     r8, [rbp+410h+Data]; lpName
0x180020ae9  mov     [rsp+510h+lpClass], r12; lpClass
0x180020aee  xor     edx, edx; dwIndex
0x180020af0  mov     [rsp+510h+phkResult], r12; lpReserved
0x180020af5  mov     [rsp+510h+cchName], 104h
0x180020afd  call    cs:__imp_RegEnumKeyExW
0x180020b03  mov     rcx, [rsp+510h+var_4C8]; hKey
0x180020b08  mov     ebx, eax
0x180020b0a  call    cs:__imp_RegCloseKey
0x180020b10  cmp     ebx, 103h
0x180020b16  jnz     loc_18002090C
0x180020b1c  lea     rcx, [rbp+410h+var_464]; lpSubKey
0x180020b20  call    ?RemoveAClass@@YAJPEB_W@Z; RemoveAClass(wchar_t const *)
0x180020b25  jmp     loc_18002090C
0x180020b2a  mov     r14d, ebx
0x180020b2d  mov     esi, r12d
0x180020b30  jmp     loc_18002090C
0x180020b35  call    __report_rangecheckfailure
0x180020b3b  mov     rcx, [rsp+510h+hKey]; hKey
0x180020b40  cmp     rcx, r13
0x180020b43  jz      short loc_180020B4B
0x180020b45  call    cs:__imp_RegCloseKey
0x180020b4b  cmp     edi, 103h
0x180020b51  cmovz   edi, esi
0x180020b54  test    edi, edi
0x180020b56  cmovnz  r14d, edi
0x180020b5a  mov     eax, r14d
0x180020b5d  mov     rcx, [rbp+410h+var_50]
0x180020b64  xor     rcx, rsp; StackCookie
0x180020b67  call    __security_check_cookie
0x180020b6c  add     rsp, 4D8h
0x180020b73  pop     r15
0x180020b75  pop     r14
0x180020b77  pop     r13
0x180020b79  pop     r12
0x180020b7b  pop     rdi
0x180020b7c  pop     rsi
0x180020b7d  pop     rbx
0x180020b7e  pop     rbp
0x180020b7f  retn
```
