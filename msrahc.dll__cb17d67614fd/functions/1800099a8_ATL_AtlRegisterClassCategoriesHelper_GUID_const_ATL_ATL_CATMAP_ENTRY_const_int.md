# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800099a8`
- end: `0x180009ce3`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3a4`
- `0x18000bee4`
- `0x18000c720`
- `0x18000c780`

## callees

- `0x18000882c`
- `0x180008924`
- `0x1800096a8`
- `0x1800099a8`
- `0x18000a064`
- `0x18000a394`
- `0x18000a994`
- `0x18000ac00`
- `0x18001a5e0`
- `0x18001c010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180009aed`
- `msvcrt!wcscat_s` at `0x180009b07`
- `msvcrt!wcscat_s` at `0x180009be9`
- `msvcrt!wcscat_s` at `0x180009c04`
- `msvcrt!wcscat_s` at `0x180009aed`
- `msvcrt!wcscat_s` at `0x180009b07`
- `msvcrt!wcscat_s` at `0x180009be9`
- `msvcrt!wcscat_s` at `0x180009c04`
- `msvcrt!wcscpy_s` at `0x180009ad3`
- `msvcrt!wcscpy_s` at `0x180009bce`
- `msvcrt!wcscpy_s` at `0x180009ad3`
- `msvcrt!wcscpy_s` at `0x180009bce`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009b92`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009c63`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009b92`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009c63`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009a30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009a30`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009ab7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009ab7`

## string_xrefs

- `0x180009ac8`: `CLSID\`
- `0x180009bc0`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  errno_t v9; // eax
  errno_t v10; // eax
  errno_t v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  errno_t v14; // eax
  errno_t v15; // eax
  errno_t v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v24);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v24);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v24);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v24);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v23 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800099a8  mov     [rsp-8+arg_10], rbx
0x1800099ad  mov     [rsp-8+arg_18], rsi
0x1800099b2  push    rbp
0x1800099b3  push    rdi
0x1800099b4  push    r12
0x1800099b6  push    r14
0x1800099b8  push    r15
0x1800099ba  lea     rbp, [rsp-150h]
0x1800099c2  sub     rsp, 250h
0x1800099c9  mov     rax, cs:__security_cookie
0x1800099d0  xor     rax, rsp
0x1800099d3  mov     [rbp+170h+var_30], rax
0x1800099da  xor     r15d, r15d
0x1800099dd  xorps   xmm0, xmm0
0x1800099e0  mov     [rsp+270h+var_208], r15
0x1800099e5  mov     r14d, r8d
0x1800099e8  mov     rbx, rdx
0x1800099eb  mov     rsi, rcx
0x1800099ee  movups  [rbp+170h+var_1C8], xmm0
0x1800099f2  test    rdx, rdx
0x1800099f5  jz      loc_180009CA9
0x1800099fb  lea     rdx, GUID_NULL; struct _GUID *
0x180009a02  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009a07  test    eax, eax
0x180009a09  jnz     loc_180009CA9
0x180009a0f  lea     rax, [rsp+270h+var_208]
0x180009a14  xor     edx, edx; pUnkOuter
0x180009a16  lea     r12d, [r15+1]
0x180009a1a  mov     [rsp+270h+ppv], rax; ppv
0x180009a1f  mov     r8d, r12d; dwClsContext
0x180009a22  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180009a29  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180009a30  call    cs:__imp_CoCreateInstance
0x180009a36  test    eax, eax
0x180009a38  js      loc_180009CA9
0x180009a3e  cmp     [rbx], r15d
0x180009a41  jz      short loc_180009AA0
0x180009a43  mov     rax, [rbx+8]
0x180009a47  lea     r9, [rbp+170h+var_1C8]
0x180009a4b  mov     rcx, [rsp+270h+var_208]
0x180009a50  mov     r8d, r12d
0x180009a53  mov     rdx, rsi
0x180009a56  movups  xmm0, xmmword ptr [rax]
0x180009a59  movdqu  [rbp+170h+var_1C8], xmm0
0x180009a5e  mov     rax, [rcx]
0x180009a61  test    r14d, r14d
0x180009a64  jz      short loc_180009A86
0x180009a66  cmp     [rbx], r12d
0x180009a69  jnz     short loc_180009A71
0x180009a6b  mov     rax, [rax+28h]
0x180009a6f  jmp     short loc_180009A75
0x180009a71  mov     rax, [rax+38h]
0x180009a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7a  mov     edi, eax
0x180009a7c  test    eax, eax
0x180009a7e  js      loc_180009CAC
0x180009a84  jmp     short loc_180009A9A
0x180009a86  cmp     [rbx], r12d
0x180009a89  jnz     short loc_180009A91
0x180009a8b  mov     rax, [rax+30h]
0x180009a8f  jmp     short loc_180009A95
0x180009a91  mov     rax, [rax+40h]
0x180009a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a9a  add     rbx, 10h
0x180009a9e  jmp     short loc_180009A3E
0x180009aa0  test    r14d, r14d
0x180009aa3  jnz     loc_180009CA9
0x180009aa9  lea     r8d, [r14+40h]; cchMax
0x180009aad  mov     rcx, rsi; rguid
0x180009ab0  lea     rdx, [rbp+170h+sz]; lpsz
0x180009ab7  call    cs:__imp_StringFromGUID2
0x180009abd  mov     esi, 80h
0x180009ac2  mov     [rbp+170h+var_1D0], r15
0x180009ac6  mov     edx, esi; SizeInWords
0x180009ac8  lea     r8, aClsid; "CLSID\\"
0x180009acf  lea     rcx, [rbp+170h+Destination]; Destination
0x180009ad3  call    cs:__imp_wcscpy_s
0x180009ad9  mov     ecx, eax; int
0x180009adb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009ae0  lea     r8, [rbp+170h+sz]; Source
0x180009ae7  mov     edx, esi; SizeInWords
0x180009ae9  lea     rcx, [rbp+170h+Destination]; Destination
0x180009aed  call    cs:__imp_wcscat_s
0x180009af3  mov     ecx, eax; int
0x180009af5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009afa  lea     r8, aRequiredCatego; "\\Required Categories"
0x180009b01  mov     edx, esi; SizeInWords
0x180009b03  lea     rcx, [rbp+170h+Destination]; Destination
0x180009b07  call    cs:__imp_wcscat_s
0x180009b0d  mov     ecx, eax; int
0x180009b0f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009b14  mov     rdi, 0FFFFFFFF80000000h
0x180009b1b  mov     [rbp+170h+var_1E0], r15
0x180009b1f  mov     r14d, 20019h
0x180009b25  mov     [rbp+170h+var_1E8], rdi
0x180009b29  mov     r9d, r14d; unsigned int
0x180009b2c  mov     [rbp+170h+var_1D8], r15
0x180009b30  mov     rdx, rdi; hKey
0x180009b33  mov     [rsp+270h+hKey], r15
0x180009b38  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180009b3c  mov     [rsp+270h+var_1F8], r15
0x180009b41  lea     rcx, [rsp+270h+hKey]; this
0x180009b46  mov     [rbp+170h+var_1F0], r15
0x180009b4a  mov     [rsp+270h+cSubKeys], r15d
0x180009b4f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180009b54  test    eax, eax
0x180009b56  jnz     short loc_180009BC0
0x180009b58  mov     rcx, [rsp+270h+hKey]; hKey
0x180009b5d  lea     rax, [rsp+270h+cSubKeys]
0x180009b62  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009b67  xor     r9d, r9d; lpReserved
0x180009b6a  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009b6f  xor     r8d, r8d; lpcchClass
0x180009b72  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009b77  xor     edx, edx; lpClass
0x180009b79  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009b7e  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180009b83  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009b88  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009b8d  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180009b92  call    cs:__imp_RegQueryInfoKeyW
0x180009b98  lea     rcx, [rsp+270h+hKey]; this
0x180009b9d  mov     ebx, eax
0x180009b9f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180009ba4  test    ebx, ebx
0x180009ba6  jnz     short loc_180009BC0
0x180009ba8  cmp     [rsp+270h+cSubKeys], r15d
0x180009bad  jnz     short loc_180009BC0
0x180009baf  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180009bb3  lea     rcx, [rbp+170h+var_1E8]; this
0x180009bb7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009bbc  mov     rdi, [rbp+170h+var_1E8]
0x180009bc0  lea     r8, aClsid; "CLSID\\"
0x180009bc7  mov     rdx, rsi; SizeInWords
0x180009bca  lea     rcx, [rbp+170h+Destination]; Destination
0x180009bce  call    cs:__imp_wcscpy_s
0x180009bd4  mov     ecx, eax; int
0x180009bd6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009bdb  lea     r8, [rbp+170h+sz]; Source
0x180009be2  mov     rdx, rsi; SizeInWords
0x180009be5  lea     rcx, [rbp+170h+Destination]; Destination
0x180009be9  call    cs:__imp_wcscat_s
0x180009bef  mov     ecx, eax; int
0x180009bf1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009bf6  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180009bfd  mov     rdx, rsi; SizeInWords
0x180009c00  lea     rcx, [rbp+170h+Destination]; Destination
0x180009c04  call    cs:__imp_wcscat_s
0x180009c0a  mov     ecx, eax; int
0x180009c0c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009c11  mov     r9d, r14d; unsigned int
0x180009c14  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180009c18  mov     rdx, rdi; hKey
0x180009c1b  lea     rcx, [rsp+270h+hKey]; this
0x180009c20  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180009c25  test    eax, eax
0x180009c27  jnz     short loc_180009C8D
0x180009c29  mov     rcx, [rsp+270h+hKey]; hKey
0x180009c2e  lea     rax, [rsp+270h+cSubKeys]
0x180009c33  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009c38  xor     r9d, r9d; lpReserved
0x180009c3b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009c40  xor     r8d, r8d; lpcchClass
0x180009c43  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009c48  xor     edx, edx; lpClass
0x180009c4a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009c4f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180009c54  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009c59  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009c5e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180009c63  call    cs:__imp_RegQueryInfoKeyW
0x180009c69  lea     rcx, [rsp+270h+hKey]; this
0x180009c6e  mov     ebx, eax
0x180009c70  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180009c75  test    ebx, ebx
0x180009c77  jnz     short loc_180009C8D
0x180009c79  cmp     [rsp+270h+cSubKeys], r15d
0x180009c7e  jnz     short loc_180009C8D
0x180009c80  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180009c84  lea     rcx, [rbp+170h+var_1E8]; this
0x180009c88  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009c8d  lea     rcx, [rsp+270h+hKey]; this
0x180009c92  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180009c97  lea     rcx, [rbp+170h+var_1E8]; this
0x180009c9b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180009ca0  lea     rcx, [rbp+170h+var_1D0]
0x180009ca4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009ca9  mov     edi, r15d
0x180009cac  lea     rcx, [rsp+270h+var_208]
0x180009cb1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009cb6  mov     eax, edi
0x180009cb8  mov     rcx, [rbp+170h+var_30]
0x180009cbf  xor     rcx, rsp; StackCookie
0x180009cc2  call    __security_check_cookie
0x180009cc7  lea     r11, [rsp+270h+var_20]
0x180009ccf  mov     rbx, [r11+40h]
0x180009cd3  mov     rsi, [r11+48h]
0x180009cd7  mov     rsp, r11
0x180009cda  pop     r15
0x180009cdc  pop     r14
0x180009cde  pop     r12
0x180009ce0  pop     rdi
0x180009ce1  pop     rbp
0x180009ce2  retn
```
