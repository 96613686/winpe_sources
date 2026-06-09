# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18007792c`
- end: `0x180077c62`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `822`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180079aa8`
- `0x18007a964`
- `0x18007b2a0`

## callees

- `0x1800227e0`
- `0x180029314`
- `0x180048210`
- `0x180074160`
- `0x180076b00`
- `0x18007792c`
- `0x180077e10`
- `0x1800783c0`
- `0x180079284`
- `0x18007b274`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180077a63`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180077b56`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180077a63`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180077b56`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800779b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800779b4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180077a41`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180077a41`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180077b14`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180077bdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180077b14`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180077bdb`

## string_xrefs

- `0x180077a58`: `CLSID\`
- `0x180077b48`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r9
  HKEY v14; // rdi
  LSTATUS v15; // ebx
  int v16; // eax
  unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r9
  LSTATUS v21; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v28 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v28);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v28);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v27 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v10, (unsigned __int64)sz, v11);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v12, (unsigned __int64)L"\\Required Categories", v13);
      v14 = HKEY_CLASSES_ROOT;
      v26[1] = 0;
      v26[0] = 0xFFFFFFFF80000000uLL;
      v26[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, SubKey);
          v14 = (HKEY)v26[0];
        }
      }
      v16 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v16);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v17, (unsigned __int64)sz, v18);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v19, (unsigned __int64)L"\\Implemented Categories", v20);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v14, SubKey, 0x20019u) )
      {
        v21 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v21 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v26);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18007792c  mov     [rsp-8+arg_10], rbx
0x180077931  mov     [rsp-8+arg_18], rsi
0x180077936  push    rbp
0x180077937  push    rdi
0x180077938  push    r12
0x18007793a  push    r14
0x18007793c  push    r15
0x18007793e  lea     rbp, [rsp-150h]
0x180077946  sub     rsp, 250h
0x18007794d  mov     rax, cs:__security_cookie
0x180077954  xor     rax, rsp
0x180077957  mov     [rbp+170h+var_30], rax
0x18007795e  xor     r15d, r15d
0x180077961  xorps   xmm0, xmm0
0x180077964  mov     [rsp+270h+var_208], r15
0x180077969  mov     r14d, r8d
0x18007796c  mov     rbx, rdx
0x18007796f  mov     rsi, rcx
0x180077972  movups  [rbp+170h+var_1C8], xmm0
0x180077976  test    rdx, rdx
0x180077979  jz      loc_180077C27
0x18007797f  lea     rdx, GUID_NULL
0x180077986  call    InlineIsEqualGUID
0x18007798b  test    eax, eax
0x18007798d  jnz     loc_180077C27
0x180077993  lea     rax, [rsp+270h+var_208]
0x180077998  xor     edx, edx; pUnkOuter
0x18007799a  lea     r12d, [r15+1]
0x18007799e  mov     [rsp+270h+ppv], rax; ppv
0x1800779a3  mov     r8d, r12d; dwClsContext
0x1800779a6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800779ad  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800779b4  call    cs:__imp_CoCreateInstance
0x1800779bb  nop     dword ptr [rax+rax+00h]
0x1800779c0  test    eax, eax
0x1800779c2  js      loc_180077C27
0x1800779c8  cmp     [rbx], r15d
0x1800779cb  jz      short loc_180077A2A
0x1800779cd  mov     rax, [rbx+8]
0x1800779d1  lea     r9, [rbp+170h+var_1C8]
0x1800779d5  mov     rcx, [rsp+270h+var_208]
0x1800779da  mov     r8d, r12d
0x1800779dd  mov     rdx, rsi
0x1800779e0  movups  xmm0, xmmword ptr [rax]
0x1800779e3  movdqu  [rbp+170h+var_1C8], xmm0
0x1800779e8  mov     rax, [rcx]
0x1800779eb  test    r14d, r14d
0x1800779ee  jz      short loc_180077A10
0x1800779f0  cmp     [rbx], r12d
0x1800779f3  jnz     short loc_1800779FB
0x1800779f5  mov     rax, [rax+28h]
0x1800779f9  jmp     short loc_1800779FF
0x1800779fb  mov     rax, [rax+38h]
0x1800779ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a04  mov     edi, eax
0x180077a06  test    eax, eax
0x180077a08  js      loc_180077C2A
0x180077a0e  jmp     short loc_180077A24
0x180077a10  cmp     [rbx], r12d
0x180077a13  jnz     short loc_180077A1B
0x180077a15  mov     rax, [rax+30h]
0x180077a19  jmp     short loc_180077A1F
0x180077a1b  mov     rax, [rax+40h]
0x180077a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a24  add     rbx, 10h
0x180077a28  jmp     short loc_1800779C8
0x180077a2a  test    r14d, r14d
0x180077a2d  jnz     loc_180077C27
0x180077a33  lea     r8d, [r14+40h]; cchMax
0x180077a37  mov     rcx, rsi; rguid
0x180077a3a  lea     rdx, [rbp+170h+sz]; lpsz
0x180077a41  call    cs:__imp_StringFromGUID2
0x180077a48  nop     dword ptr [rax+rax+00h]
0x180077a4d  mov     esi, 80h
0x180077a52  mov     [rbp+170h+var_1D0], r15
0x180077a56  mov     edx, esi
0x180077a58  lea     r8, aClsid; "CLSID\\"
0x180077a5f  lea     rcx, [rbp+170h+SubKey]
0x180077a63  call    cs:__imp__o_wcscpy_s
0x180077a6a  nop     dword ptr [rax+rax+00h]
0x180077a6f  mov     ecx, eax; int
0x180077a71  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180077a76  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180077a7d  lea     rcx, [rbp+170h+SubKey]; this
0x180077a81  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180077a86  lea     r8, aRequiredCatego; "\\Required Categories"
0x180077a8d  lea     rcx, [rbp+170h+SubKey]; this
0x180077a91  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180077a96  mov     rdi, 0FFFFFFFF80000000h
0x180077a9d  mov     [rbp+170h+var_1E0], r15
0x180077aa1  mov     r14d, 20019h
0x180077aa7  mov     [rbp+170h+var_1E8], rdi
0x180077aab  mov     r9d, r14d; unsigned int
0x180077aae  mov     [rbp+170h+var_1D8], r15
0x180077ab2  mov     rdx, rdi; hKey
0x180077ab5  mov     [rsp+270h+hKey], r15
0x180077aba  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180077abe  mov     [rsp+270h+var_1F8], r15
0x180077ac3  lea     rcx, [rsp+270h+hKey]; this
0x180077ac8  mov     [rbp+170h+var_1F0], r15
0x180077acc  mov     [rsp+270h+cSubKeys], r15d
0x180077ad1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180077ad6  test    eax, eax
0x180077ad8  jnz     short loc_180077B48
0x180077ada  mov     rcx, [rsp+270h+hKey]; hKey
0x180077adf  lea     rax, [rsp+270h+cSubKeys]
0x180077ae4  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180077ae9  xor     r9d, r9d; lpReserved
0x180077aec  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180077af1  xor     r8d, r8d; lpcchClass
0x180077af4  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180077af9  xor     edx, edx; lpClass
0x180077afb  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180077b00  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180077b05  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180077b0a  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180077b0f  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180077b14  call    cs:__imp_RegQueryInfoKeyW
0x180077b1b  nop     dword ptr [rax+rax+00h]
0x180077b20  lea     rcx, [rsp+270h+hKey]; this
0x180077b25  mov     ebx, eax
0x180077b27  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180077b2c  test    ebx, ebx
0x180077b2e  jnz     short loc_180077B48
0x180077b30  cmp     [rsp+270h+cSubKeys], r15d
0x180077b35  jnz     short loc_180077B48
0x180077b37  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180077b3b  lea     rcx, [rbp+170h+var_1E8]; this
0x180077b3f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180077b44  mov     rdi, [rbp+170h+var_1E8]
0x180077b48  lea     r8, aClsid; "CLSID\\"
0x180077b4f  mov     rdx, rsi
0x180077b52  lea     rcx, [rbp+170h+SubKey]
0x180077b56  call    cs:__imp__o_wcscpy_s
0x180077b5d  nop     dword ptr [rax+rax+00h]
0x180077b62  mov     ecx, eax; int
0x180077b64  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180077b69  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180077b70  lea     rcx, [rbp+170h+SubKey]; this
0x180077b74  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180077b79  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180077b80  lea     rcx, [rbp+170h+SubKey]; this
0x180077b84  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180077b89  mov     r9d, r14d; unsigned int
0x180077b8c  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180077b90  mov     rdx, rdi; hKey
0x180077b93  lea     rcx, [rsp+270h+hKey]; this
0x180077b98  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180077b9d  test    eax, eax
0x180077b9f  jnz     short loc_180077C0B
0x180077ba1  mov     rcx, [rsp+270h+hKey]; hKey
0x180077ba6  lea     rax, [rsp+270h+cSubKeys]
0x180077bab  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180077bb0  xor     r9d, r9d; lpReserved
0x180077bb3  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180077bb8  xor     r8d, r8d; lpcchClass
0x180077bbb  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180077bc0  xor     edx, edx; lpClass
0x180077bc2  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180077bc7  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180077bcc  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180077bd1  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180077bd6  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180077bdb  call    cs:__imp_RegQueryInfoKeyW
0x180077be2  nop     dword ptr [rax+rax+00h]
0x180077be7  lea     rcx, [rsp+270h+hKey]; this
0x180077bec  mov     ebx, eax
0x180077bee  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180077bf3  test    ebx, ebx
0x180077bf5  jnz     short loc_180077C0B
0x180077bf7  cmp     [rsp+270h+cSubKeys], r15d
0x180077bfc  jnz     short loc_180077C0B
0x180077bfe  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180077c02  lea     rcx, [rbp+170h+var_1E8]; this
0x180077c06  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180077c0b  lea     rcx, [rsp+270h+hKey]; this
0x180077c10  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180077c15  lea     rcx, [rbp+170h+var_1E8]; this
0x180077c19  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180077c1e  lea     rcx, [rbp+170h+var_1D0]
0x180077c22  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180077c27  mov     edi, r15d
0x180077c2a  lea     rcx, [rsp+270h+var_208]; void *
0x180077c2f  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180077c34  mov     eax, edi
0x180077c36  mov     rcx, [rbp+170h+var_30]
0x180077c3d  xor     rcx, rsp; StackCookie
0x180077c40  call    __security_check_cookie
0x180077c45  lea     r11, [rsp+270h+var_20]
0x180077c4d  mov     rbx, [r11+40h]
0x180077c51  mov     rsi, [r11+48h]
0x180077c55  mov     rsp, r11
0x180077c58  pop     r15
0x180077c5a  pop     r14
0x180077c5c  pop     r12
0x180077c5e  pop     rdi
0x180077c5f  pop     rbp
0x180077c60  retn
```
