# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800180bc`
- end: `0x1800183f7`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800184b0`
- `0x1800186e0`

## callees

- `0x18000ba34`
- `0x18000f970`
- `0x180010f88`
- `0x180011f78`
- `0x180012144`
- `0x180012560`
- `0x1800146d4`
- `0x180017f80`
- `0x1800180bc`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018201`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001821b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800182fd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018318`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018201`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001821b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800182fd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018318`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800181e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800182e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800181e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800182e2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800182a6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180018377`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800182a6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180018377`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018144`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018144`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800181cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800181cb`

## string_xrefs

- `0x1800181dc`: `CLSID\`
- `0x1800182d4`: `CLSID\`

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
  ATL::CComPtrBase<ICatRegister>::~CComPtrBase<ICatRegister>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800180bc  mov     [rsp-8+arg_10], rbx
0x1800180c1  mov     [rsp-8+arg_18], rsi
0x1800180c6  push    rbp
0x1800180c7  push    rdi
0x1800180c8  push    r12
0x1800180ca  push    r14
0x1800180cc  push    r15
0x1800180ce  lea     rbp, [rsp-150h]
0x1800180d6  sub     rsp, 250h
0x1800180dd  mov     rax, cs:__security_cookie
0x1800180e4  xor     rax, rsp
0x1800180e7  mov     [rbp+170h+var_30], rax
0x1800180ee  xor     r15d, r15d
0x1800180f1  xorps   xmm0, xmm0
0x1800180f4  mov     [rsp+270h+var_208], r15
0x1800180f9  mov     r14d, r8d
0x1800180fc  mov     rbx, rdx
0x1800180ff  mov     rsi, rcx
0x180018102  movups  [rbp+170h+var_1C8], xmm0
0x180018106  test    rdx, rdx
0x180018109  jz      loc_1800183BD
0x18001810f  lea     rdx, GUID_NULL
0x180018116  call    InlineIsEqualGUID
0x18001811b  test    eax, eax
0x18001811d  jnz     loc_1800183BD
0x180018123  lea     rax, [rsp+270h+var_208]
0x180018128  xor     edx, edx; pUnkOuter
0x18001812a  lea     r12d, [r15+1]
0x18001812e  mov     [rsp+270h+ppv], rax; ppv
0x180018133  mov     r8d, r12d; dwClsContext
0x180018136  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18001813d  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180018144  call    cs:__imp_CoCreateInstance
0x18001814a  test    eax, eax
0x18001814c  js      loc_1800183BD
0x180018152  cmp     [rbx], r15d
0x180018155  jz      short loc_1800181B4
0x180018157  mov     rax, [rbx+8]
0x18001815b  lea     r9, [rbp+170h+var_1C8]
0x18001815f  mov     rcx, [rsp+270h+var_208]
0x180018164  mov     r8d, r12d
0x180018167  mov     rdx, rsi
0x18001816a  movups  xmm0, xmmword ptr [rax]
0x18001816d  movdqu  [rbp+170h+var_1C8], xmm0
0x180018172  mov     rax, [rcx]
0x180018175  test    r14d, r14d
0x180018178  jz      short loc_18001819A
0x18001817a  cmp     [rbx], r12d
0x18001817d  jnz     short loc_180018185
0x18001817f  mov     rax, [rax+28h]
0x180018183  jmp     short loc_180018189
0x180018185  mov     rax, [rax+38h]
0x180018189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001818e  mov     edi, eax
0x180018190  test    eax, eax
0x180018192  js      loc_1800183C0
0x180018198  jmp     short loc_1800181AE
0x18001819a  cmp     [rbx], r12d
0x18001819d  jnz     short loc_1800181A5
0x18001819f  mov     rax, [rax+30h]
0x1800181a3  jmp     short loc_1800181A9
0x1800181a5  mov     rax, [rax+40h]
0x1800181a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181ae  add     rbx, 10h
0x1800181b2  jmp     short loc_180018152
0x1800181b4  test    r14d, r14d
0x1800181b7  jnz     loc_1800183BD
0x1800181bd  lea     r8d, [r14+40h]; cchMax
0x1800181c1  mov     rcx, rsi; rguid
0x1800181c4  lea     rdx, [rbp+170h+sz]; lpsz
0x1800181cb  call    cs:__imp_StringFromGUID2
0x1800181d1  mov     esi, 80h
0x1800181d6  mov     [rbp+170h+var_1D0], r15
0x1800181da  mov     edx, esi
0x1800181dc  lea     r8, aClsid; "CLSID\\"
0x1800181e3  lea     rcx, [rbp+170h+SubKey]
0x1800181e7  call    cs:__imp__o_wcscpy_s
0x1800181ed  mov     ecx, eax; int
0x1800181ef  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800181f4  lea     r8, [rbp+170h+sz]
0x1800181fb  mov     edx, esi
0x1800181fd  lea     rcx, [rbp+170h+SubKey]
0x180018201  call    cs:__imp__o_wcscat_s
0x180018207  mov     ecx, eax; int
0x180018209  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001820e  lea     r8, aRequiredCatego; "\\Required Categories"
0x180018215  mov     edx, esi
0x180018217  lea     rcx, [rbp+170h+SubKey]
0x18001821b  call    cs:__imp__o_wcscat_s
0x180018221  mov     ecx, eax; int
0x180018223  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018228  mov     rdi, 0FFFFFFFF80000000h
0x18001822f  mov     [rbp+170h+var_1E0], r15
0x180018233  mov     r14d, 20019h
0x180018239  mov     [rbp+170h+var_1E8], rdi
0x18001823d  mov     r9d, r14d; unsigned int
0x180018240  mov     [rbp+170h+var_1D8], r15
0x180018244  mov     rdx, rdi; hKey
0x180018247  mov     [rsp+270h+hKey], r15
0x18001824c  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180018250  mov     [rsp+270h+var_1F8], r15
0x180018255  lea     rcx, [rsp+270h+hKey]; this
0x18001825a  mov     [rbp+170h+var_1F0], r15
0x18001825e  mov     [rsp+270h+cSubKeys], r15d
0x180018263  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180018268  test    eax, eax
0x18001826a  jnz     short loc_1800182D4
0x18001826c  mov     rcx, [rsp+270h+hKey]; hKey
0x180018271  lea     rax, [rsp+270h+cSubKeys]
0x180018276  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001827b  xor     r9d, r9d; lpReserved
0x18001827e  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180018283  xor     r8d, r8d; lpcchClass
0x180018286  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001828b  xor     edx, edx; lpClass
0x18001828d  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180018292  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180018297  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001829c  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800182a1  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800182a6  call    cs:__imp_RegQueryInfoKeyW
0x1800182ac  lea     rcx, [rsp+270h+hKey]; this
0x1800182b1  mov     ebx, eax
0x1800182b3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800182b8  test    ebx, ebx
0x1800182ba  jnz     short loc_1800182D4
0x1800182bc  cmp     [rsp+270h+cSubKeys], r15d
0x1800182c1  jnz     short loc_1800182D4
0x1800182c3  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x1800182c7  lea     rcx, [rbp+170h+var_1E8]; this
0x1800182cb  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800182d0  mov     rdi, [rbp+170h+var_1E8]
0x1800182d4  lea     r8, aClsid; "CLSID\\"
0x1800182db  mov     rdx, rsi
0x1800182de  lea     rcx, [rbp+170h+SubKey]
0x1800182e2  call    cs:__imp__o_wcscpy_s
0x1800182e8  mov     ecx, eax; int
0x1800182ea  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800182ef  lea     r8, [rbp+170h+sz]
0x1800182f6  mov     rdx, rsi
0x1800182f9  lea     rcx, [rbp+170h+SubKey]
0x1800182fd  call    cs:__imp__o_wcscat_s
0x180018303  mov     ecx, eax; int
0x180018305  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001830a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180018311  mov     rdx, rsi
0x180018314  lea     rcx, [rbp+170h+SubKey]
0x180018318  call    cs:__imp__o_wcscat_s
0x18001831e  mov     ecx, eax; int
0x180018320  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018325  mov     r9d, r14d; unsigned int
0x180018328  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18001832c  mov     rdx, rdi; hKey
0x18001832f  lea     rcx, [rsp+270h+hKey]; this
0x180018334  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180018339  test    eax, eax
0x18001833b  jnz     short loc_1800183A1
0x18001833d  mov     rcx, [rsp+270h+hKey]; hKey
0x180018342  lea     rax, [rsp+270h+cSubKeys]
0x180018347  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001834c  xor     r9d, r9d; lpReserved
0x18001834f  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180018354  xor     r8d, r8d; lpcchClass
0x180018357  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001835c  xor     edx, edx; lpClass
0x18001835e  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180018363  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180018368  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001836d  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180018372  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180018377  call    cs:__imp_RegQueryInfoKeyW
0x18001837d  lea     rcx, [rsp+270h+hKey]; this
0x180018382  mov     ebx, eax
0x180018384  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018389  test    ebx, ebx
0x18001838b  jnz     short loc_1800183A1
0x18001838d  cmp     [rsp+270h+cSubKeys], r15d
0x180018392  jnz     short loc_1800183A1
0x180018394  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180018398  lea     rcx, [rbp+170h+var_1E8]; this
0x18001839c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800183a1  lea     rcx, [rsp+270h+hKey]; this
0x1800183a6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800183ab  lea     rcx, [rbp+170h+var_1E8]; this
0x1800183af  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800183b4  lea     rcx, [rbp+170h+var_1D0]
0x1800183b8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800183bd  mov     edi, r15d
0x1800183c0  lea     rcx, [rsp+270h+var_208]
0x1800183c5  call    ??1?$CComPtrBase@UICatRegister@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICatRegister>::~CComPtrBase<ICatRegister>(void)
0x1800183ca  mov     eax, edi
0x1800183cc  mov     rcx, [rbp+170h+var_30]
0x1800183d3  xor     rcx, rsp; StackCookie
0x1800183d6  call    __security_check_cookie
0x1800183db  lea     r11, [rsp+270h+var_20]
0x1800183e3  mov     rbx, [r11+40h]
0x1800183e7  mov     rsi, [r11+48h]
0x1800183eb  mov     rsp, r11
0x1800183ee  pop     r15
0x1800183f0  pop     r14
0x1800183f2  pop     r12
0x1800183f4  pop     rdi
0x1800183f5  pop     rbp
0x1800183f6  retn
```
