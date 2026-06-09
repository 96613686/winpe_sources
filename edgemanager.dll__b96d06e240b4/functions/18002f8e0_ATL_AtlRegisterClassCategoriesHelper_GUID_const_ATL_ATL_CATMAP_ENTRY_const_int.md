# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18002f8e0`
- end: `0x18002fc1b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800321f0`
- `0x18003342c`
- `0x180033ec0`
- `0x180033fe0`
- `0x180034040`

## callees

- `0x180001a70`
- `0x18002b530`
- `0x18002e130`
- `0x18002e25c`
- `0x18002f5e0`
- `0x18002f8e0`
- `0x1800301b4`
- `0x1800305a0`
- `0x180031880`
- `0x180085010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fa25`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fa3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fb21`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fb3c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fa25`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fa3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fb21`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002fb3c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fa0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fb06`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fa0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fb06`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryInfoKeyW` at `0x18002faca`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryInfoKeyW` at `0x18002fb9b`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryInfoKeyW` at `0x18002faca`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryInfoKeyW` at `0x18002fb9b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f9ef`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f9ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f968`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f968`

## string_xrefs

- `0x18002fa00`: `CLSID\`
- `0x18002faf8`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
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
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18002f8e0  mov     [rsp-8+arg_10], rbx
0x18002f8e5  mov     [rsp-8+arg_18], rsi
0x18002f8ea  push    rbp
0x18002f8eb  push    rdi
0x18002f8ec  push    r12
0x18002f8ee  push    r14
0x18002f8f0  push    r15
0x18002f8f2  lea     rbp, [rsp-150h]
0x18002f8fa  sub     rsp, 250h
0x18002f901  mov     rax, cs:__security_cookie
0x18002f908  xor     rax, rsp
0x18002f90b  mov     [rbp+170h+var_30], rax
0x18002f912  xor     r15d, r15d
0x18002f915  xorps   xmm0, xmm0
0x18002f918  mov     [rsp+270h+var_208], r15
0x18002f91d  mov     r14d, r8d
0x18002f920  mov     rbx, rdx
0x18002f923  mov     rsi, rcx
0x18002f926  movups  [rbp+170h+var_1C8], xmm0
0x18002f92a  test    rdx, rdx
0x18002f92d  jz      loc_18002FBE1
0x18002f933  lea     rdx, GUID_NULL
0x18002f93a  call    InlineIsEqualGUID
0x18002f93f  test    eax, eax
0x18002f941  jnz     loc_18002FBE1
0x18002f947  lea     rax, [rsp+270h+var_208]
0x18002f94c  xor     edx, edx; pUnkOuter
0x18002f94e  lea     r12d, [r15+1]
0x18002f952  mov     [rsp+270h+ppv], rax; ppv
0x18002f957  mov     r8d, r12d; dwClsContext
0x18002f95a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18002f961  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18002f968  call    cs:__imp_CoCreateInstance
0x18002f96e  test    eax, eax
0x18002f970  js      loc_18002FBE1
0x18002f976  cmp     [rbx], r15d
0x18002f979  jz      short loc_18002F9D8
0x18002f97b  mov     rax, [rbx+8]
0x18002f97f  lea     r9, [rbp+170h+var_1C8]
0x18002f983  mov     rcx, [rsp+270h+var_208]
0x18002f988  mov     r8d, r12d
0x18002f98b  mov     rdx, rsi
0x18002f98e  movups  xmm0, xmmword ptr [rax]
0x18002f991  movdqu  [rbp+170h+var_1C8], xmm0
0x18002f996  mov     rax, [rcx]
0x18002f999  test    r14d, r14d
0x18002f99c  jz      short loc_18002F9BE
0x18002f99e  cmp     [rbx], r12d
0x18002f9a1  jnz     short loc_18002F9A9
0x18002f9a3  mov     rax, [rax+28h]
0x18002f9a7  jmp     short loc_18002F9AD
0x18002f9a9  mov     rax, [rax+38h]
0x18002f9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9b2  mov     edi, eax
0x18002f9b4  test    eax, eax
0x18002f9b6  js      loc_18002FBE4
0x18002f9bc  jmp     short loc_18002F9D2
0x18002f9be  cmp     [rbx], r12d
0x18002f9c1  jnz     short loc_18002F9C9
0x18002f9c3  mov     rax, [rax+30h]
0x18002f9c7  jmp     short loc_18002F9CD
0x18002f9c9  mov     rax, [rax+40h]
0x18002f9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9d2  add     rbx, 10h
0x18002f9d6  jmp     short loc_18002F976
0x18002f9d8  test    r14d, r14d
0x18002f9db  jnz     loc_18002FBE1
0x18002f9e1  lea     r8d, [r14+40h]; cchMax
0x18002f9e5  mov     rcx, rsi; rguid
0x18002f9e8  lea     rdx, [rbp+170h+sz]; lpsz
0x18002f9ef  call    cs:__imp_StringFromGUID2
0x18002f9f5  mov     esi, 80h
0x18002f9fa  mov     [rbp+170h+var_1D0], r15
0x18002f9fe  mov     edx, esi
0x18002fa00  lea     r8, aClsid; "CLSID\\"
0x18002fa07  lea     rcx, [rbp+170h+SubKey]
0x18002fa0b  call    cs:__imp__o_wcscpy_s
0x18002fa11  mov     ecx, eax; int
0x18002fa13  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fa18  lea     r8, [rbp+170h+sz]
0x18002fa1f  mov     edx, esi
0x18002fa21  lea     rcx, [rbp+170h+SubKey]
0x18002fa25  call    cs:__imp__o_wcscat_s
0x18002fa2b  mov     ecx, eax; int
0x18002fa2d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fa32  lea     r8, aRequiredCatego; "\\Required Categories"
0x18002fa39  mov     edx, esi
0x18002fa3b  lea     rcx, [rbp+170h+SubKey]
0x18002fa3f  call    cs:__imp__o_wcscat_s
0x18002fa45  mov     ecx, eax; int
0x18002fa47  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fa4c  mov     rdi, 0FFFFFFFF80000000h
0x18002fa53  mov     [rbp+170h+var_1E0], r15
0x18002fa57  mov     r14d, 20019h
0x18002fa5d  mov     [rbp+170h+var_1E8], rdi
0x18002fa61  mov     r9d, r14d; unsigned int
0x18002fa64  mov     [rbp+170h+var_1D8], r15
0x18002fa68  mov     rdx, rdi; hKey
0x18002fa6b  mov     [rsp+270h+hKey], r15
0x18002fa70  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18002fa74  mov     [rsp+270h+var_1F8], r15
0x18002fa79  lea     rcx, [rsp+270h+hKey]; this
0x18002fa7e  mov     [rbp+170h+var_1F0], r15
0x18002fa82  mov     [rsp+270h+cSubKeys], r15d
0x18002fa87  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002fa8c  test    eax, eax
0x18002fa8e  jnz     short loc_18002FAF8
0x18002fa90  mov     rcx, [rsp+270h+hKey]; hKey
0x18002fa95  lea     rax, [rsp+270h+cSubKeys]
0x18002fa9a  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002fa9f  xor     r9d, r9d; lpReserved
0x18002faa2  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002faa7  xor     r8d, r8d; lpcchClass
0x18002faaa  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002faaf  xor     edx, edx; lpClass
0x18002fab1  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002fab6  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18002fabb  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002fac0  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002fac5  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18002faca  call    cs:__imp_RegQueryInfoKeyW
0x18002fad0  lea     rcx, [rsp+270h+hKey]; this
0x18002fad5  mov     ebx, eax
0x18002fad7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002fadc  test    ebx, ebx
0x18002fade  jnz     short loc_18002FAF8
0x18002fae0  cmp     [rsp+270h+cSubKeys], r15d
0x18002fae5  jnz     short loc_18002FAF8
0x18002fae7  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18002faeb  lea     rcx, [rbp+170h+var_1E8]; this
0x18002faef  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002faf4  mov     rdi, [rbp+170h+var_1E8]
0x18002faf8  lea     r8, aClsid; "CLSID\\"
0x18002faff  mov     rdx, rsi
0x18002fb02  lea     rcx, [rbp+170h+SubKey]
0x18002fb06  call    cs:__imp__o_wcscpy_s
0x18002fb0c  mov     ecx, eax; int
0x18002fb0e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fb13  lea     r8, [rbp+170h+sz]
0x18002fb1a  mov     rdx, rsi
0x18002fb1d  lea     rcx, [rbp+170h+SubKey]
0x18002fb21  call    cs:__imp__o_wcscat_s
0x18002fb27  mov     ecx, eax; int
0x18002fb29  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fb2e  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18002fb35  mov     rdx, rsi
0x18002fb38  lea     rcx, [rbp+170h+SubKey]
0x18002fb3c  call    cs:__imp__o_wcscat_s
0x18002fb42  mov     ecx, eax; int
0x18002fb44  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fb49  mov     r9d, r14d; unsigned int
0x18002fb4c  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18002fb50  mov     rdx, rdi; hKey
0x18002fb53  lea     rcx, [rsp+270h+hKey]; this
0x18002fb58  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002fb5d  test    eax, eax
0x18002fb5f  jnz     short loc_18002FBC5
0x18002fb61  mov     rcx, [rsp+270h+hKey]; hKey
0x18002fb66  lea     rax, [rsp+270h+cSubKeys]
0x18002fb6b  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002fb70  xor     r9d, r9d; lpReserved
0x18002fb73  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002fb78  xor     r8d, r8d; lpcchClass
0x18002fb7b  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002fb80  xor     edx, edx; lpClass
0x18002fb82  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002fb87  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18002fb8c  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002fb91  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002fb96  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18002fb9b  call    cs:__imp_RegQueryInfoKeyW
0x18002fba1  lea     rcx, [rsp+270h+hKey]; this
0x18002fba6  mov     ebx, eax
0x18002fba8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002fbad  test    ebx, ebx
0x18002fbaf  jnz     short loc_18002FBC5
0x18002fbb1  cmp     [rsp+270h+cSubKeys], r15d
0x18002fbb6  jnz     short loc_18002FBC5
0x18002fbb8  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18002fbbc  lea     rcx, [rbp+170h+var_1E8]; this
0x18002fbc0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002fbc5  lea     rcx, [rsp+270h+hKey]; this
0x18002fbca  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002fbcf  lea     rcx, [rbp+170h+var_1E8]; this
0x18002fbd3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002fbd8  lea     rcx, [rbp+170h+var_1D0]
0x18002fbdc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002fbe1  mov     edi, r15d
0x18002fbe4  lea     rcx, [rsp+270h+var_208]
0x18002fbe9  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18002fbee  mov     eax, edi
0x18002fbf0  mov     rcx, [rbp+170h+var_30]
0x18002fbf7  xor     rcx, rsp; StackCookie
0x18002fbfa  call    __security_check_cookie
0x18002fbff  lea     r11, [rsp+270h+var_20]
0x18002fc07  mov     rbx, [r11+40h]
0x18002fc0b  mov     rsi, [r11+48h]
0x18002fc0f  mov     rsp, r11
0x18002fc12  pop     r15
0x18002fc14  pop     r14
0x18002fc16  pop     r12
0x18002fc18  pop     rdi
0x18002fc19  pop     rbp
0x18002fc1a  retn
```
