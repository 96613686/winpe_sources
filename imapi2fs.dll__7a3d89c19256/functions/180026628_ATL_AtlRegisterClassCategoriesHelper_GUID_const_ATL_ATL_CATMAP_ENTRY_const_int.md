# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180026628`
- end: `0x180026963`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027758`
- `0x180027f74`

## callees

- `0x180005cec`
- `0x18001f27c`
- `0x180025934`
- `0x180026628`
- `0x180026c90`
- `0x180026cbc`
- `0x180027074`
- `0x180028538`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18002676d`
- `msvcrt!wcscat_s` at `0x180026787`
- `msvcrt!wcscat_s` at `0x180026869`
- `msvcrt!wcscat_s` at `0x180026884`
- `msvcrt!wcscat_s` at `0x18002676d`
- `msvcrt!wcscat_s` at `0x180026787`
- `msvcrt!wcscat_s` at `0x180026869`
- `msvcrt!wcscat_s` at `0x180026884`
- `msvcrt!wcscpy_s` at `0x180026753`
- `msvcrt!wcscpy_s` at `0x18002684e`
- `msvcrt!wcscpy_s` at `0x180026753`
- `msvcrt!wcscpy_s` at `0x18002684e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180026812`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800268e3`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180026812`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800268e3`
- `ole32!CoCreateInstance` at `0x1800266b0`
- `ole32!CoCreateInstance` at `0x1800266b0`
- `ole32!StringFromGUID2` at `0x180026737`
- `ole32!StringFromGUID2` at `0x180026737`

## string_xrefs

- `0x180026748`: `CLSID\`
- `0x180026840`: `CLSID\`

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
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180026628  mov     [rsp-8+arg_10], rbx
0x18002662d  mov     [rsp-8+arg_18], rsi
0x180026632  push    rbp
0x180026633  push    rdi
0x180026634  push    r12
0x180026636  push    r14
0x180026638  push    r15
0x18002663a  lea     rbp, [rsp-150h]
0x180026642  sub     rsp, 250h
0x180026649  mov     rax, cs:__security_cookie
0x180026650  xor     rax, rsp
0x180026653  mov     [rbp+170h+var_30], rax
0x18002665a  xor     r15d, r15d
0x18002665d  xorps   xmm0, xmm0
0x180026660  mov     [rsp+270h+var_208], r15
0x180026665  mov     r14d, r8d
0x180026668  mov     rbx, rdx
0x18002666b  mov     rsi, rcx
0x18002666e  movups  [rbp+170h+var_1C8], xmm0
0x180026672  test    rdx, rdx
0x180026675  jz      loc_180026929
0x18002667b  lea     rdx, GUID_NULL
0x180026682  call    InlineIsEqualGUID
0x180026687  test    eax, eax
0x180026689  jnz     loc_180026929
0x18002668f  lea     rax, [rsp+270h+var_208]
0x180026694  xor     edx, edx; pUnkOuter
0x180026696  lea     r12d, [r15+1]
0x18002669a  mov     [rsp+270h+ppv], rax; ppv
0x18002669f  mov     r8d, r12d; dwClsContext
0x1800266a2  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800266a9  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800266b0  call    cs:__imp_CoCreateInstance
0x1800266b6  test    eax, eax
0x1800266b8  js      loc_180026929
0x1800266be  cmp     [rbx], r15d
0x1800266c1  jz      short loc_180026720
0x1800266c3  mov     rax, [rbx+8]
0x1800266c7  lea     r9, [rbp+170h+var_1C8]
0x1800266cb  mov     rcx, [rsp+270h+var_208]
0x1800266d0  mov     r8d, r12d
0x1800266d3  mov     rdx, rsi
0x1800266d6  movups  xmm0, xmmword ptr [rax]
0x1800266d9  movdqu  [rbp+170h+var_1C8], xmm0
0x1800266de  mov     rax, [rcx]
0x1800266e1  test    r14d, r14d
0x1800266e4  jz      short loc_180026706
0x1800266e6  cmp     [rbx], r12d
0x1800266e9  jnz     short loc_1800266F1
0x1800266eb  mov     rax, [rax+28h]
0x1800266ef  jmp     short loc_1800266F5
0x1800266f1  mov     rax, [rax+38h]
0x1800266f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266fa  mov     edi, eax
0x1800266fc  test    eax, eax
0x1800266fe  js      loc_18002692C
0x180026704  jmp     short loc_18002671A
0x180026706  cmp     [rbx], r12d
0x180026709  jnz     short loc_180026711
0x18002670b  mov     rax, [rax+30h]
0x18002670f  jmp     short loc_180026715
0x180026711  mov     rax, [rax+40h]
0x180026715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002671a  add     rbx, 10h
0x18002671e  jmp     short loc_1800266BE
0x180026720  test    r14d, r14d
0x180026723  jnz     loc_180026929
0x180026729  lea     r8d, [r14+40h]; cchMax
0x18002672d  mov     rcx, rsi; rguid
0x180026730  lea     rdx, [rbp+170h+sz]; lpsz
0x180026737  call    cs:__imp_StringFromGUID2
0x18002673d  mov     esi, 80h
0x180026742  mov     [rbp+170h+var_1D0], r15
0x180026746  mov     edx, esi; SizeInWords
0x180026748  lea     r8, aClsid; "CLSID\\"
0x18002674f  lea     rcx, [rbp+170h+Destination]; Destination
0x180026753  call    cs:__imp_wcscpy_s
0x180026759  mov     ecx, eax; int
0x18002675b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180026760  lea     r8, [rbp+170h+sz]; Source
0x180026767  mov     edx, esi; SizeInWords
0x180026769  lea     rcx, [rbp+170h+Destination]; Destination
0x18002676d  call    cs:__imp_wcscat_s
0x180026773  mov     ecx, eax; int
0x180026775  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002677a  lea     r8, aRequiredCatego; "\\Required Categories"
0x180026781  mov     edx, esi; SizeInWords
0x180026783  lea     rcx, [rbp+170h+Destination]; Destination
0x180026787  call    cs:__imp_wcscat_s
0x18002678d  mov     ecx, eax; int
0x18002678f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180026794  mov     rdi, 0FFFFFFFF80000000h
0x18002679b  mov     [rbp+170h+var_1E0], r15
0x18002679f  mov     r14d, 20019h
0x1800267a5  mov     [rbp+170h+var_1E8], rdi
0x1800267a9  mov     r9d, r14d; unsigned int
0x1800267ac  mov     [rbp+170h+var_1D8], r15
0x1800267b0  mov     rdx, rdi; hKey
0x1800267b3  mov     [rsp+270h+hKey], r15
0x1800267b8  lea     r8, [rbp+170h+Destination]; lpSubKey
0x1800267bc  mov     [rsp+270h+var_1F8], r15
0x1800267c1  lea     rcx, [rsp+270h+hKey]; this
0x1800267c6  mov     [rbp+170h+var_1F0], r15
0x1800267ca  mov     [rsp+270h+cSubKeys], r15d
0x1800267cf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800267d4  test    eax, eax
0x1800267d6  jnz     short loc_180026840
0x1800267d8  mov     rcx, [rsp+270h+hKey]; hKey
0x1800267dd  lea     rax, [rsp+270h+cSubKeys]
0x1800267e2  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800267e7  xor     r9d, r9d; lpReserved
0x1800267ea  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800267ef  xor     r8d, r8d; lpcchClass
0x1800267f2  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800267f7  xor     edx, edx; lpClass
0x1800267f9  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800267fe  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180026803  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180026808  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002680d  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180026812  call    cs:__imp_RegQueryInfoKeyW
0x180026818  lea     rcx, [rsp+270h+hKey]; this
0x18002681d  mov     ebx, eax
0x18002681f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180026824  test    ebx, ebx
0x180026826  jnz     short loc_180026840
0x180026828  cmp     [rsp+270h+cSubKeys], r15d
0x18002682d  jnz     short loc_180026840
0x18002682f  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180026833  lea     rcx, [rbp+170h+var_1E8]; this
0x180026837  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002683c  mov     rdi, [rbp+170h+var_1E8]
0x180026840  lea     r8, aClsid; "CLSID\\"
0x180026847  mov     rdx, rsi; SizeInWords
0x18002684a  lea     rcx, [rbp+170h+Destination]; Destination
0x18002684e  call    cs:__imp_wcscpy_s
0x180026854  mov     ecx, eax; int
0x180026856  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002685b  lea     r8, [rbp+170h+sz]; Source
0x180026862  mov     rdx, rsi; SizeInWords
0x180026865  lea     rcx, [rbp+170h+Destination]; Destination
0x180026869  call    cs:__imp_wcscat_s
0x18002686f  mov     ecx, eax; int
0x180026871  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180026876  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18002687d  mov     rdx, rsi; SizeInWords
0x180026880  lea     rcx, [rbp+170h+Destination]; Destination
0x180026884  call    cs:__imp_wcscat_s
0x18002688a  mov     ecx, eax; int
0x18002688c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180026891  mov     r9d, r14d; unsigned int
0x180026894  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180026898  mov     rdx, rdi; hKey
0x18002689b  lea     rcx, [rsp+270h+hKey]; this
0x1800268a0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800268a5  test    eax, eax
0x1800268a7  jnz     short loc_18002690D
0x1800268a9  mov     rcx, [rsp+270h+hKey]; hKey
0x1800268ae  lea     rax, [rsp+270h+cSubKeys]
0x1800268b3  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800268b8  xor     r9d, r9d; lpReserved
0x1800268bb  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800268c0  xor     r8d, r8d; lpcchClass
0x1800268c3  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800268c8  xor     edx, edx; lpClass
0x1800268ca  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800268cf  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800268d4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800268d9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800268de  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800268e3  call    cs:__imp_RegQueryInfoKeyW
0x1800268e9  lea     rcx, [rsp+270h+hKey]; this
0x1800268ee  mov     ebx, eax
0x1800268f0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800268f5  test    ebx, ebx
0x1800268f7  jnz     short loc_18002690D
0x1800268f9  cmp     [rsp+270h+cSubKeys], r15d
0x1800268fe  jnz     short loc_18002690D
0x180026900  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180026904  lea     rcx, [rbp+170h+var_1E8]; this
0x180026908  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002690d  lea     rcx, [rsp+270h+hKey]; this
0x180026912  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180026917  lea     rcx, [rbp+170h+var_1E8]; this
0x18002691b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180026920  lea     rcx, [rbp+170h+var_1D0]
0x180026924  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180026929  mov     edi, r15d
0x18002692c  lea     rcx, [rsp+270h+var_208]
0x180026931  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180026936  mov     eax, edi
0x180026938  mov     rcx, [rbp+170h+var_30]
0x18002693f  xor     rcx, rsp; StackCookie
0x180026942  call    __security_check_cookie
0x180026947  lea     r11, [rsp+270h+var_20]
0x18002694f  mov     rbx, [r11+40h]
0x180026953  mov     rsi, [r11+48h]
0x180026957  mov     rsp, r11
0x18002695a  pop     r15
0x18002695c  pop     r14
0x18002695e  pop     r12
0x180026960  pop     rdi
0x180026961  pop     rbp
0x180026962  retn
```
