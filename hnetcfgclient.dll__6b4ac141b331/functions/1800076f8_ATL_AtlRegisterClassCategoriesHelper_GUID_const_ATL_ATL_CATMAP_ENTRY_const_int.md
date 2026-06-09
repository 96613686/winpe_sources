# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800076f8`
- end: `0x180007a33`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008dd0`
- `0x1800098c4`
- `0x18000a2e0`

## callees

- `0x180006688`
- `0x1800067e8`
- `0x180007594`
- `0x1800076f8`
- `0x180007b74`
- `0x180007f70`
- `0x180008348`
- `0x180008570`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000783d`
- `msvcrt!wcscat_s` at `0x180007857`
- `msvcrt!wcscat_s` at `0x180007939`
- `msvcrt!wcscat_s` at `0x180007954`
- `msvcrt!wcscat_s` at `0x18000783d`
- `msvcrt!wcscat_s` at `0x180007857`
- `msvcrt!wcscat_s` at `0x180007939`
- `msvcrt!wcscat_s` at `0x180007954`
- `msvcrt!wcscpy_s` at `0x180007823`
- `msvcrt!wcscpy_s` at `0x18000791e`
- `msvcrt!wcscpy_s` at `0x180007823`
- `msvcrt!wcscpy_s` at `0x18000791e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800078e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800079b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800078e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800079b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007780`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007780`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007807`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007807`

## string_xrefs

- `0x180007818`: `CLSID\`
- `0x180007910`: `CLSID\`

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
  ATL::CComPtrBase<IHNetBridgedConnection>::~CComPtrBase<IHNetBridgedConnection>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800076f8  mov     [rsp-8+arg_10], rbx
0x1800076fd  mov     [rsp-8+arg_18], rsi
0x180007702  push    rbp
0x180007703  push    rdi
0x180007704  push    r12
0x180007706  push    r14
0x180007708  push    r15
0x18000770a  lea     rbp, [rsp-150h]
0x180007712  sub     rsp, 250h
0x180007719  mov     rax, cs:__security_cookie
0x180007720  xor     rax, rsp
0x180007723  mov     [rbp+170h+var_30], rax
0x18000772a  xor     r15d, r15d
0x18000772d  xorps   xmm0, xmm0
0x180007730  mov     [rsp+270h+var_208], r15
0x180007735  mov     r14d, r8d
0x180007738  mov     rbx, rdx
0x18000773b  mov     rsi, rcx
0x18000773e  movups  [rbp+170h+var_1C8], xmm0
0x180007742  test    rdx, rdx
0x180007745  jz      loc_1800079F9
0x18000774b  lea     rdx, GUID_NULL; struct _GUID *
0x180007752  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007757  test    eax, eax
0x180007759  jnz     loc_1800079F9
0x18000775f  lea     rax, [rsp+270h+var_208]
0x180007764  xor     edx, edx; pUnkOuter
0x180007766  lea     r12d, [r15+1]
0x18000776a  mov     [rsp+270h+ppv], rax; ppv
0x18000776f  mov     r8d, r12d; dwClsContext
0x180007772  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180007779  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180007780  call    cs:__imp_CoCreateInstance
0x180007786  test    eax, eax
0x180007788  js      loc_1800079F9
0x18000778e  cmp     [rbx], r15d
0x180007791  jz      short loc_1800077F0
0x180007793  mov     rax, [rbx+8]
0x180007797  lea     r9, [rbp+170h+var_1C8]
0x18000779b  mov     rcx, [rsp+270h+var_208]
0x1800077a0  mov     r8d, r12d
0x1800077a3  mov     rdx, rsi
0x1800077a6  movups  xmm0, xmmword ptr [rax]
0x1800077a9  movdqu  [rbp+170h+var_1C8], xmm0
0x1800077ae  mov     rax, [rcx]
0x1800077b1  test    r14d, r14d
0x1800077b4  jz      short loc_1800077D6
0x1800077b6  cmp     [rbx], r12d
0x1800077b9  jnz     short loc_1800077C1
0x1800077bb  mov     rax, [rax+28h]
0x1800077bf  jmp     short loc_1800077C5
0x1800077c1  mov     rax, [rax+38h]
0x1800077c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ca  mov     edi, eax
0x1800077cc  test    eax, eax
0x1800077ce  js      loc_1800079FC
0x1800077d4  jmp     short loc_1800077EA
0x1800077d6  cmp     [rbx], r12d
0x1800077d9  jnz     short loc_1800077E1
0x1800077db  mov     rax, [rax+30h]
0x1800077df  jmp     short loc_1800077E5
0x1800077e1  mov     rax, [rax+40h]
0x1800077e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ea  add     rbx, 10h
0x1800077ee  jmp     short loc_18000778E
0x1800077f0  test    r14d, r14d
0x1800077f3  jnz     loc_1800079F9
0x1800077f9  lea     r8d, [r14+40h]; cchMax
0x1800077fd  mov     rcx, rsi; rguid
0x180007800  lea     rdx, [rbp+170h+sz]; lpsz
0x180007807  call    cs:__imp_StringFromGUID2
0x18000780d  mov     esi, 80h
0x180007812  mov     [rbp+170h+var_1D0], r15
0x180007816  mov     edx, esi; SizeInWords
0x180007818  lea     r8, aClsid; "CLSID\\"
0x18000781f  lea     rcx, [rbp+170h+Destination]; Destination
0x180007823  call    cs:__imp_wcscpy_s
0x180007829  mov     ecx, eax; int
0x18000782b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007830  lea     r8, [rbp+170h+sz]; Source
0x180007837  mov     edx, esi; SizeInWords
0x180007839  lea     rcx, [rbp+170h+Destination]; Destination
0x18000783d  call    cs:__imp_wcscat_s
0x180007843  mov     ecx, eax; int
0x180007845  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000784a  lea     r8, aRequiredCatego; "\\Required Categories"
0x180007851  mov     edx, esi; SizeInWords
0x180007853  lea     rcx, [rbp+170h+Destination]; Destination
0x180007857  call    cs:__imp_wcscat_s
0x18000785d  mov     ecx, eax; int
0x18000785f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007864  mov     rdi, 0FFFFFFFF80000000h
0x18000786b  mov     [rbp+170h+var_1E0], r15
0x18000786f  mov     r14d, 20019h
0x180007875  mov     [rbp+170h+var_1E8], rdi
0x180007879  mov     r9d, r14d; unsigned int
0x18000787c  mov     [rbp+170h+var_1D8], r15
0x180007880  mov     rdx, rdi; hKey
0x180007883  mov     [rsp+270h+hKey], r15
0x180007888  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18000788c  mov     [rsp+270h+var_1F8], r15
0x180007891  lea     rcx, [rsp+270h+hKey]; this
0x180007896  mov     [rbp+170h+var_1F0], r15
0x18000789a  mov     [rsp+270h+cSubKeys], r15d
0x18000789f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800078a4  test    eax, eax
0x1800078a6  jnz     short loc_180007910
0x1800078a8  mov     rcx, [rsp+270h+hKey]; hKey
0x1800078ad  lea     rax, [rsp+270h+cSubKeys]
0x1800078b2  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800078b7  xor     r9d, r9d; lpReserved
0x1800078ba  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800078bf  xor     r8d, r8d; lpcchClass
0x1800078c2  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800078c7  xor     edx, edx; lpClass
0x1800078c9  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800078ce  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800078d3  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800078d8  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800078dd  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800078e2  call    cs:__imp_RegQueryInfoKeyW
0x1800078e8  lea     rcx, [rsp+270h+hKey]; this
0x1800078ed  mov     ebx, eax
0x1800078ef  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800078f4  test    ebx, ebx
0x1800078f6  jnz     short loc_180007910
0x1800078f8  cmp     [rsp+270h+cSubKeys], r15d
0x1800078fd  jnz     short loc_180007910
0x1800078ff  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180007903  lea     rcx, [rbp+170h+var_1E8]; this
0x180007907  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000790c  mov     rdi, [rbp+170h+var_1E8]
0x180007910  lea     r8, aClsid; "CLSID\\"
0x180007917  mov     rdx, rsi; SizeInWords
0x18000791a  lea     rcx, [rbp+170h+Destination]; Destination
0x18000791e  call    cs:__imp_wcscpy_s
0x180007924  mov     ecx, eax; int
0x180007926  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000792b  lea     r8, [rbp+170h+sz]; Source
0x180007932  mov     rdx, rsi; SizeInWords
0x180007935  lea     rcx, [rbp+170h+Destination]; Destination
0x180007939  call    cs:__imp_wcscat_s
0x18000793f  mov     ecx, eax; int
0x180007941  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007946  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000794d  mov     rdx, rsi; SizeInWords
0x180007950  lea     rcx, [rbp+170h+Destination]; Destination
0x180007954  call    cs:__imp_wcscat_s
0x18000795a  mov     ecx, eax; int
0x18000795c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007961  mov     r9d, r14d; unsigned int
0x180007964  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180007968  mov     rdx, rdi; hKey
0x18000796b  lea     rcx, [rsp+270h+hKey]; this
0x180007970  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007975  test    eax, eax
0x180007977  jnz     short loc_1800079DD
0x180007979  mov     rcx, [rsp+270h+hKey]; hKey
0x18000797e  lea     rax, [rsp+270h+cSubKeys]
0x180007983  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180007988  xor     r9d, r9d; lpReserved
0x18000798b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180007990  xor     r8d, r8d; lpcchClass
0x180007993  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180007998  xor     edx, edx; lpClass
0x18000799a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000799f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800079a4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800079a9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800079ae  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800079b3  call    cs:__imp_RegQueryInfoKeyW
0x1800079b9  lea     rcx, [rsp+270h+hKey]; this
0x1800079be  mov     ebx, eax
0x1800079c0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800079c5  test    ebx, ebx
0x1800079c7  jnz     short loc_1800079DD
0x1800079c9  cmp     [rsp+270h+cSubKeys], r15d
0x1800079ce  jnz     short loc_1800079DD
0x1800079d0  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800079d4  lea     rcx, [rbp+170h+var_1E8]; this
0x1800079d8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800079dd  lea     rcx, [rsp+270h+hKey]; this
0x1800079e2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800079e7  lea     rcx, [rbp+170h+var_1E8]; this
0x1800079eb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800079f0  lea     rcx, [rbp+170h+var_1D0]
0x1800079f4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800079f9  mov     edi, r15d
0x1800079fc  lea     rcx, [rsp+270h+var_208]
0x180007a01  call    ??1?$CComPtrBase@UIHNetBridgedConnection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IHNetBridgedConnection>::~CComPtrBase<IHNetBridgedConnection>(void)
0x180007a06  mov     eax, edi
0x180007a08  mov     rcx, [rbp+170h+var_30]
0x180007a0f  xor     rcx, rsp; StackCookie
0x180007a12  call    __security_check_cookie
0x180007a17  lea     r11, [rsp+270h+var_20]
0x180007a1f  mov     rbx, [r11+40h]
0x180007a23  mov     rsi, [r11+48h]
0x180007a27  mov     rsp, r11
0x180007a2a  pop     r15
0x180007a2c  pop     r14
0x180007a2e  pop     r12
0x180007a30  pop     rdi
0x180007a31  pop     rbp
0x180007a32  retn
```
