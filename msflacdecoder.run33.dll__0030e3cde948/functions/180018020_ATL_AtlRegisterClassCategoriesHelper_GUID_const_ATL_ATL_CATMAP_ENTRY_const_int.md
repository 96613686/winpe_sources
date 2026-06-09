# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180018020`
- end: `0x18001835b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a818`
- `0x18001b8e0`
- `0x18001c1d0`

## callees

- `0x180001e80`
- `0x180016bd0`
- `0x180016e48`
- `0x180017ebc`
- `0x180018020`
- `0x180018494`
- `0x180018d38`
- `0x180019ad0`
- `0x18001c33c`
- `0x180056010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018165`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001817f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018261`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001827c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018165`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001817f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018261`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001827c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001814b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018246`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001814b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018246`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800180a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800180a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001812f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001812f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001820a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800182db`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001820a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800182db`

## string_xrefs

- `0x180018140`: `CLSID\`
- `0x180018238`: `CLSID\`

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
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180018020  mov     [rsp-8+arg_10], rbx
0x180018025  mov     [rsp-8+arg_18], rsi
0x18001802a  push    rbp
0x18001802b  push    rdi
0x18001802c  push    r12
0x18001802e  push    r14
0x180018030  push    r15
0x180018032  lea     rbp, [rsp-150h]
0x18001803a  sub     rsp, 250h
0x180018041  mov     rax, cs:__security_cookie
0x180018048  xor     rax, rsp
0x18001804b  mov     [rbp+170h+var_30], rax
0x180018052  xor     r15d, r15d
0x180018055  xorps   xmm0, xmm0
0x180018058  mov     [rsp+270h+var_208], r15
0x18001805d  mov     r14d, r8d
0x180018060  mov     rbx, rdx
0x180018063  mov     rsi, rcx
0x180018066  movups  [rbp+170h+var_1C8], xmm0
0x18001806a  test    rdx, rdx
0x18001806d  jz      loc_180018321
0x180018073  lea     rdx, GUID_NULL
0x18001807a  call    InlineIsEqualGUID
0x18001807f  test    eax, eax
0x180018081  jnz     loc_180018321
0x180018087  lea     rax, [rsp+270h+var_208]
0x18001808c  xor     edx, edx; pUnkOuter
0x18001808e  lea     r12d, [r15+1]
0x180018092  mov     [rsp+270h+ppv], rax; ppv
0x180018097  mov     r8d, r12d; dwClsContext
0x18001809a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800180a1  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800180a8  call    cs:__imp_CoCreateInstance
0x1800180ae  test    eax, eax
0x1800180b0  js      loc_180018321
0x1800180b6  cmp     [rbx], r15d
0x1800180b9  jz      short loc_180018118
0x1800180bb  mov     rax, [rbx+8]
0x1800180bf  lea     r9, [rbp+170h+var_1C8]
0x1800180c3  mov     rcx, [rsp+270h+var_208]
0x1800180c8  mov     r8d, r12d
0x1800180cb  mov     rdx, rsi
0x1800180ce  movups  xmm0, xmmword ptr [rax]
0x1800180d1  movdqu  [rbp+170h+var_1C8], xmm0
0x1800180d6  mov     rax, [rcx]
0x1800180d9  test    r14d, r14d
0x1800180dc  jz      short loc_1800180FE
0x1800180de  cmp     [rbx], r12d
0x1800180e1  jnz     short loc_1800180E9
0x1800180e3  mov     rax, [rax+28h]
0x1800180e7  jmp     short loc_1800180ED
0x1800180e9  mov     rax, [rax+38h]
0x1800180ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180f2  mov     edi, eax
0x1800180f4  test    eax, eax
0x1800180f6  js      loc_180018324
0x1800180fc  jmp     short loc_180018112
0x1800180fe  cmp     [rbx], r12d
0x180018101  jnz     short loc_180018109
0x180018103  mov     rax, [rax+30h]
0x180018107  jmp     short loc_18001810D
0x180018109  mov     rax, [rax+40h]
0x18001810d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018112  add     rbx, 10h
0x180018116  jmp     short loc_1800180B6
0x180018118  test    r14d, r14d
0x18001811b  jnz     loc_180018321
0x180018121  lea     r8d, [r14+40h]; cchMax
0x180018125  mov     rcx, rsi; rguid
0x180018128  lea     rdx, [rbp+170h+sz]; lpsz
0x18001812f  call    cs:__imp_StringFromGUID2
0x180018135  mov     esi, 80h
0x18001813a  mov     [rbp+170h+var_1D0], r15
0x18001813e  mov     edx, esi
0x180018140  lea     r8, aClsid; "CLSID\\"
0x180018147  lea     rcx, [rbp+170h+SubKey]
0x18001814b  call    cs:__imp__o_wcscpy_s
0x180018151  mov     ecx, eax; int
0x180018153  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018158  lea     r8, [rbp+170h+sz]
0x18001815f  mov     edx, esi
0x180018161  lea     rcx, [rbp+170h+SubKey]
0x180018165  call    cs:__imp__o_wcscat_s
0x18001816b  mov     ecx, eax; int
0x18001816d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018172  lea     r8, aRequiredCatego; "\\Required Categories"
0x180018179  mov     edx, esi
0x18001817b  lea     rcx, [rbp+170h+SubKey]
0x18001817f  call    cs:__imp__o_wcscat_s
0x180018185  mov     ecx, eax; int
0x180018187  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001818c  mov     rdi, 0FFFFFFFF80000000h
0x180018193  mov     [rbp+170h+var_1E0], r15
0x180018197  mov     r14d, 20019h
0x18001819d  mov     [rbp+170h+var_1E8], rdi
0x1800181a1  mov     r9d, r14d; unsigned int
0x1800181a4  mov     [rbp+170h+var_1D8], r15
0x1800181a8  mov     rdx, rdi; hKey
0x1800181ab  mov     [rsp+270h+hKey], r15
0x1800181b0  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800181b4  mov     [rsp+270h+var_1F8], r15
0x1800181b9  lea     rcx, [rsp+270h+hKey]; this
0x1800181be  mov     [rbp+170h+var_1F0], r15
0x1800181c2  mov     [rsp+270h+cSubKeys], r15d
0x1800181c7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800181cc  test    eax, eax
0x1800181ce  jnz     short loc_180018238
0x1800181d0  mov     rcx, [rsp+270h+hKey]; hKey
0x1800181d5  lea     rax, [rsp+270h+cSubKeys]
0x1800181da  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800181df  xor     r9d, r9d; lpReserved
0x1800181e2  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800181e7  xor     r8d, r8d; lpcchClass
0x1800181ea  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800181ef  xor     edx, edx; lpClass
0x1800181f1  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800181f6  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800181fb  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180018200  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180018205  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001820a  call    cs:__imp_RegQueryInfoKeyW
0x180018210  lea     rcx, [rsp+270h+hKey]; this
0x180018215  mov     ebx, eax
0x180018217  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001821c  test    ebx, ebx
0x18001821e  jnz     short loc_180018238
0x180018220  cmp     [rsp+270h+cSubKeys], r15d
0x180018225  jnz     short loc_180018238
0x180018227  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18001822b  lea     rcx, [rbp+170h+var_1E8]; this
0x18001822f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180018234  mov     rdi, [rbp+170h+var_1E8]
0x180018238  lea     r8, aClsid; "CLSID\\"
0x18001823f  mov     rdx, rsi
0x180018242  lea     rcx, [rbp+170h+SubKey]
0x180018246  call    cs:__imp__o_wcscpy_s
0x18001824c  mov     ecx, eax; int
0x18001824e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018253  lea     r8, [rbp+170h+sz]
0x18001825a  mov     rdx, rsi
0x18001825d  lea     rcx, [rbp+170h+SubKey]
0x180018261  call    cs:__imp__o_wcscat_s
0x180018267  mov     ecx, eax; int
0x180018269  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001826e  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180018275  mov     rdx, rsi
0x180018278  lea     rcx, [rbp+170h+SubKey]
0x18001827c  call    cs:__imp__o_wcscat_s
0x180018282  mov     ecx, eax; int
0x180018284  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018289  mov     r9d, r14d; unsigned int
0x18001828c  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180018290  mov     rdx, rdi; hKey
0x180018293  lea     rcx, [rsp+270h+hKey]; this
0x180018298  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001829d  test    eax, eax
0x18001829f  jnz     short loc_180018305
0x1800182a1  mov     rcx, [rsp+270h+hKey]; hKey
0x1800182a6  lea     rax, [rsp+270h+cSubKeys]
0x1800182ab  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800182b0  xor     r9d, r9d; lpReserved
0x1800182b3  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800182b8  xor     r8d, r8d; lpcchClass
0x1800182bb  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800182c0  xor     edx, edx; lpClass
0x1800182c2  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800182c7  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800182cc  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800182d1  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800182d6  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800182db  call    cs:__imp_RegQueryInfoKeyW
0x1800182e1  lea     rcx, [rsp+270h+hKey]; this
0x1800182e6  mov     ebx, eax
0x1800182e8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800182ed  test    ebx, ebx
0x1800182ef  jnz     short loc_180018305
0x1800182f1  cmp     [rsp+270h+cSubKeys], r15d
0x1800182f6  jnz     short loc_180018305
0x1800182f8  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x1800182fc  lea     rcx, [rbp+170h+var_1E8]; this
0x180018300  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180018305  lea     rcx, [rsp+270h+hKey]; this
0x18001830a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001830f  lea     rcx, [rbp+170h+var_1E8]; this
0x180018313  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018318  lea     rcx, [rbp+170h+var_1D0]
0x18001831c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018321  mov     edi, r15d
0x180018324  lea     rcx, [rsp+270h+var_208]
0x180018329  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001832e  mov     eax, edi
0x180018330  mov     rcx, [rbp+170h+var_30]
0x180018337  xor     rcx, rsp; StackCookie
0x18001833a  call    __security_check_cookie
0x18001833f  lea     r11, [rsp+270h+var_20]
0x180018347  mov     rbx, [r11+40h]
0x18001834b  mov     rsi, [r11+48h]
0x18001834f  mov     rsp, r11
0x180018352  pop     r15
0x180018354  pop     r14
0x180018356  pop     r12
0x180018358  pop     rdi
0x180018359  pop     rbp
0x18001835a  retn
```
