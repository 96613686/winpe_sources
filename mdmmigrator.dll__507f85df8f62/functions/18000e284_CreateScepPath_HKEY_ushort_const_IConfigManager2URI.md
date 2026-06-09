# CreateScepPath(HKEY__ *,ushort const *,IConfigManager2URI * *)

- ea: `0x18000e284`
- end: `0x18000ead7`
- name: `?CreateScepPath@@YAJPEAUHKEY__@@PEBGPEAPEAUIConfigManager2URI@@@Z`
- size: `2131`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, struct IConfigManager2URI **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010610`

## callees

- `0x1800022e0`
- `0x180007720`
- `0x180007b38`
- `0x18000820c`
- `0x18000977c`
- `0x18000cc28`
- `0x18000dca4`
- `0x18000e284`
- `0x180011610`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e4de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e4de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eaa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eaa9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e378`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e3eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e461`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e378`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e3eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e461`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e300`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e300`

## pseudocode

```c
__int64 __fastcall CreateScepPath(HKEY a1, const unsigned __int16 *a2, struct IConfigManager2URI **a3)
{
  LSTATUS v5; // eax
  int v6; // ebx
  LSTATUS ValueW; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LPVOID v10; // rcx
  LPVOID v11; // rcx
  LPVOID v12; // rcx
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rbx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  unsigned __int64 v22; // r8
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  __int128 *p_Src; // rdx
  LPVOID v30; // rcx
  LPVOID v31; // rcx
  LPVOID v32; // rcx
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+54h] [rbp-ACh] BYREF
  __int128 Src; // [rsp+58h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h]
  __int128 v40; // [rsp+78h] [rbp-88h] BYREF
  __int128 v41; // [rsp+88h] [rbp-78h]
  __int128 v42; // [rsp+98h] [rbp-68h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-58h]
  __int128 v44; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v45; // [rsp+C8h] [rbp-38h]
  __int128 v46; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v47; // [rsp+E8h] [rbp-18h]
  char *v48[5]; // [rsp+F8h] [rbp-8h] BYREF
  _WORD v49[264]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v50[264]; // [rsp+330h] [rbp+230h] BYREF

  pcbData = 260;
  pvData = 0;
  ppv = 0;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  hkey = 0;
  v5 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hkey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_16:
    std::wstring::~wstring((char **)&Src);
    goto LABEL_47;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"StoreLocation", 0x10u, 0, &pvData, &pcbData);
  v6 = ValueW;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v6 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_16;
  }
  pcbData = 260;
  v8 = RegGetValueW(hkey, 0, L"EnhancedKeyUsages", 2u, 0, v49, &pcbData);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_16;
  }
  pcbData = 260;
  v9 = RegGetValueW(hkey, 0, L"Issuers", 2u, 0, v50, &pcbData);
  v6 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_16;
  }
  v6 = CoCreateInstance(
         &GUID_c196b2be_ba06_4049_8518_322e1e04282b,
         0,
         1u,
         &GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30,
         &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 40LL))(ppv, L"./cimv2");
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 176LL))(
             ppv,
             L"MDM_CertificateEnrollment",
             0);
      if ( v6 >= 0 )
      {
        v40 = 0;
        v41 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v40, L"MDM_CertificateEnrollment", 0x19u);
        std::wstring::operator=((char **)&Src, (__int64)&v40);
        std::wstring::~wstring((char **)&v40);
        std::wstring::append(&Src, L".");
        v42 = 0;
        v43 = 0;
        v13 = -1;
        v14 = -1;
        do
          ++v14;
        while ( a2[v14] );
        std::wstring::_Construct<1,unsigned short const *>(&v42, a2, v14);
        v40 = 0;
        v41 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v40, L"RequestID", 9u);
        v15 = std::wstring::append(&v40, L"=\"");
        v46 = *(_OWORD *)v15;
        v47 = *((_OWORD *)v15 + 1);
        v15[2] = 0;
        v15[3] = 7;
        *(_WORD *)v15 = 0;
        v16 = (_QWORD *)std::operator+<unsigned short>(v48, &v46, &v42);
        v17 = std::wstring::append(v16, L"\",");
        v44 = *(_OWORD *)v17;
        v45 = *((_OWORD *)v17 + 1);
        v17[2] = 0;
        v17[3] = 7;
        *(_WORD *)v17 = 0;
        std::wstring::operator+=(&Src);
        std::wstring::~wstring((char **)&v44);
        std::wstring::~wstring(v48);
        std::wstring::~wstring((char **)&v46);
        std::wstring::~wstring((char **)&v40);
        std::wstring::~wstring((char **)&v42);
        v18 = std::to_wstring(&v40);
        v42 = 0;
        v43 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v42, L"StoreLocation", 0xDu);
        v19 = std::wstring::append(&v42, L"=\"");
        v44 = *(_OWORD *)v19;
        v45 = *((_OWORD *)v19 + 1);
        v19[2] = 0;
        v19[3] = 7;
        *(_WORD *)v19 = 0;
        v20 = (_QWORD *)std::operator+<unsigned short>(v48, &v44, v18);
        v21 = std::wstring::append(v20, L"\",");
        v46 = *(_OWORD *)v21;
        v47 = *((_OWORD *)v21 + 1);
        v21[2] = 0;
        v21[3] = 7;
        *(_WORD *)v21 = 0;
        std::wstring::operator+=(&Src);
        std::wstring::~wstring((char **)&v46);
        std::wstring::~wstring(v48);
        std::wstring::~wstring((char **)&v44);
        std::wstring::~wstring((char **)&v42);
        std::wstring::~wstring((char **)&v40);
        v40 = 0;
        v41 = 0;
        v22 = -1;
        do
          ++v22;
        while ( v49[v22] );
        std::wstring::_Construct<1,unsigned short const *>(&v40, v49, v22);
        v42 = 0;
        v43 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v42, L"EnhancedKeyUsages", 0x11u);
        v23 = std::wstring::append(&v42, L"=\"");
        v44 = *(_OWORD *)v23;
        v45 = *((_OWORD *)v23 + 1);
        v23[2] = 0;
        v23[3] = 7;
        *(_WORD *)v23 = 0;
        v24 = (_QWORD *)std::operator+<unsigned short>(v48, &v44, &v40);
        v25 = std::wstring::append(v24, L"\",");
        v46 = *(_OWORD *)v25;
        v47 = *((_OWORD *)v25 + 1);
        v25[2] = 0;
        v25[3] = 7;
        *(_WORD *)v25 = 0;
        std::wstring::operator+=(&Src);
        std::wstring::~wstring((char **)&v46);
        std::wstring::~wstring(v48);
        std::wstring::~wstring((char **)&v44);
        std::wstring::~wstring((char **)&v42);
        std::wstring::~wstring((char **)&v40);
        v40 = 0;
        v41 = 0;
        do
          ++v13;
        while ( v50[v13] );
        std::wstring::_Construct<1,unsigned short const *>(&v40, v50, v13);
        v42 = 0;
        v43 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v42, L"Issuers", 7u);
        v26 = std::wstring::append(&v42, L"=\"");
        v44 = *(_OWORD *)v26;
        v45 = *((_OWORD *)v26 + 1);
        v26[2] = 0;
        v26[3] = 7;
        *(_WORD *)v26 = 0;
        v27 = (_QWORD *)std::operator+<unsigned short>(v48, &v44, &v40);
        v28 = std::wstring::append(v27, L"\"");
        v46 = *(_OWORD *)v28;
        v47 = *((_OWORD *)v28 + 1);
        v28[2] = 0;
        v28[3] = 7;
        *(_WORD *)v28 = 0;
        std::wstring::operator+=(&Src);
        std::wstring::~wstring((char **)&v46);
        std::wstring::~wstring(v48);
        std::wstring::~wstring((char **)&v44);
        std::wstring::~wstring((char **)&v42);
        std::wstring::~wstring((char **)&v40);
        p_Src = &Src;
        if ( si128.m128i_i64[1] > 7uLL )
          p_Src = (__int128 *)Src;
        v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, _QWORD))(*(_QWORD *)ppv + 176LL))(ppv, p_Src, 0);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, struct IConfigManager2URI **))(*(_QWORD *)ppv + 224LL))(ppv, a3);
          if ( v6 >= 0 )
          {
            std::wstring::~wstring((char **)&Src);
            v32 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
            }
          }
          else
          {
            std::wstring::~wstring((char **)&Src);
            v31 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
            }
          }
        }
        else
        {
          std::wstring::~wstring((char **)&Src);
          v30 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
          }
        }
      }
      else
      {
        std::wstring::~wstring((char **)&Src);
        v12 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
    }
    else
    {
      std::wstring::~wstring((char **)&Src);
      v11 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
  else
  {
    std::wstring::~wstring((char **)&Src);
    v10 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
LABEL_47:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e284  mov     [rsp-8+arg_18], rbx
0x18000e289  push    rbp
0x18000e28a  push    rsi
0x18000e28b  push    rdi
0x18000e28c  push    r14
0x18000e28e  push    r15
0x18000e290  lea     rbp, [rsp-450h]
0x18000e298  sub     rsp, 550h
0x18000e29f  mov     rax, cs:__security_cookie
0x18000e2a6  xor     rax, rsp
0x18000e2a9  mov     [rbp+470h+var_30], rax
0x18000e2b0  mov     r14, r8
0x18000e2b3  mov     rsi, rdx
0x18000e2b6  xor     r15d, r15d
0x18000e2b9  mov     edi, 104h
0x18000e2be  mov     [rsp+570h+var_520], edi
0x18000e2c2  mov     [rsp+570h+var_51C], r15d
0x18000e2c7  mov     [rsp+570h+ppv], r15
0x18000e2cc  xorps   xmm0, xmm0
0x18000e2cf  movups  [rsp+570h+Src], xmm0
0x18000e2d4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000e2dc  movdqu  [rsp+570h+var_508], xmm1
0x18000e2e2  mov     word ptr [rsp+570h+Src], r15w
0x18000e2e8  mov     [rsp+570h+hkey], r15
0x18000e2ed  lea     rax, [rsp+570h+hkey]
0x18000e2f2  mov     [rsp+570h+phkResult], rax; phkResult
0x18000e2f7  mov     r9d, 20019h; samDesired
0x18000e2fd  xor     r8d, r8d; ulOptions
0x18000e300  call    cs:__imp_RegOpenKeyExW
0x18000e306  mov     ebx, eax
0x18000e308  test    eax, eax
0x18000e30a  jz      short loc_18000E343
0x18000e30c  jle     short loc_18000E317
0x18000e30e  movzx   ebx, ax
0x18000e311  or      ebx, 80070000h
0x18000e317  lea     rcx, [rsp+570h+Src]; void *
0x18000e31c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e321  nop
0x18000e322  mov     rcx, [rsp+570h+ppv]
0x18000e327  test    rcx, rcx
0x18000e32a  jz      short loc_18000E33E
0x18000e32c  mov     [rsp+570h+ppv], r15
0x18000e331  mov     rax, [rcx]
0x18000e334  mov     rax, [rax+10h]
0x18000e338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33d  nop
0x18000e33e  jmp     loc_18000EA9F
0x18000e343  mov     [rsp+570h+var_520], 4
0x18000e34b  lea     rax, [rsp+570h+var_520]
0x18000e350  mov     [rsp+570h+pcbData], rax; pcbData
0x18000e355  lea     rax, [rsp+570h+var_51C]
0x18000e35a  mov     [rsp+570h+pvData], rax; pvData
0x18000e35f  mov     [rsp+570h+phkResult], r15; pdwType
0x18000e364  mov     r9d, 10h; dwFlags
0x18000e36a  lea     r8, aStorelocation; "StoreLocation"
0x18000e371  xor     edx, edx; lpSubKey
0x18000e373  mov     rcx, [rsp+570h+hkey]; hkey
0x18000e378  call    cs:__imp_RegGetValueW
0x18000e37e  mov     ebx, eax
0x18000e380  test    eax, eax
0x18000e382  jz      short loc_18000E3BB
0x18000e384  jle     short loc_18000E38F
0x18000e386  movzx   ebx, ax
0x18000e389  or      ebx, 80070000h
0x18000e38f  lea     rcx, [rsp+570h+Src]; void *
0x18000e394  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e399  nop
0x18000e39a  mov     rcx, [rsp+570h+ppv]
0x18000e39f  test    rcx, rcx
0x18000e3a2  jz      short loc_18000E3B6
0x18000e3a4  mov     [rsp+570h+ppv], r15
0x18000e3a9  mov     rax, [rcx]
0x18000e3ac  mov     rax, [rax+10h]
0x18000e3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3b5  nop
0x18000e3b6  jmp     loc_18000EA9F
0x18000e3bb  mov     [rsp+570h+var_520], edi
0x18000e3bf  lea     rax, [rsp+570h+var_520]
0x18000e3c4  mov     [rsp+570h+pcbData], rax; pcbData
0x18000e3c9  lea     rax, [rbp+470h+var_450]
0x18000e3cd  mov     [rsp+570h+pvData], rax; pvData
0x18000e3d2  mov     [rsp+570h+phkResult], r15; pdwType
0x18000e3d7  mov     r9d, 2; dwFlags
0x18000e3dd  lea     r8, aEnhancedkeyusa; "EnhancedKeyUsages"
0x18000e3e4  xor     edx, edx; lpSubKey
0x18000e3e6  mov     rcx, [rsp+570h+hkey]; hkey
0x18000e3eb  call    cs:__imp_RegGetValueW
0x18000e3f1  mov     ebx, eax
0x18000e3f3  test    eax, eax
0x18000e3f5  jz      short loc_18000E42E
0x18000e3f7  jle     short loc_18000E402
0x18000e3f9  movzx   ebx, ax
0x18000e3fc  or      ebx, 80070000h
0x18000e402  lea     rcx, [rsp+570h+Src]; void *
0x18000e407  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e40c  nop
0x18000e40d  mov     rcx, [rsp+570h+ppv]
0x18000e412  test    rcx, rcx
0x18000e415  jz      short loc_18000E429
0x18000e417  mov     [rsp+570h+ppv], r15
0x18000e41c  mov     rax, [rcx]
0x18000e41f  mov     rax, [rax+10h]
0x18000e423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e428  nop
0x18000e429  jmp     loc_18000EA9F
0x18000e42e  mov     [rsp+570h+var_520], edi
0x18000e432  lea     rax, [rsp+570h+var_520]
0x18000e437  mov     [rsp+570h+pcbData], rax; pcbData
0x18000e43c  lea     rax, [rbp+470h+var_240]
0x18000e443  mov     [rsp+570h+pvData], rax; pvData
0x18000e448  mov     [rsp+570h+phkResult], r15; pdwType
0x18000e44d  mov     r9d, 2; dwFlags
0x18000e453  lea     r8, aIssuers; "Issuers"
0x18000e45a  xor     edx, edx; lpSubKey
0x18000e45c  mov     rcx, [rsp+570h+hkey]; hkey
0x18000e461  call    cs:__imp_RegGetValueW
0x18000e467  mov     ebx, eax
0x18000e469  test    eax, eax
0x18000e46b  jz      short loc_18000E4A4
0x18000e46d  jle     short loc_18000E478
0x18000e46f  movzx   ebx, ax
0x18000e472  or      ebx, 80070000h
0x18000e478  lea     rcx, [rsp+570h+Src]; void *
0x18000e47d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e482  nop
0x18000e483  mov     rcx, [rsp+570h+ppv]
0x18000e488  test    rcx, rcx
0x18000e48b  jz      short loc_18000E49F
0x18000e48d  mov     [rsp+570h+ppv], r15
0x18000e492  mov     rax, [rcx]
0x18000e495  mov     rax, [rax+10h]
0x18000e499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e49e  nop
0x18000e49f  jmp     loc_18000EA9F
0x18000e4a4  mov     rcx, [rsp+570h+ppv]
0x18000e4a9  test    rcx, rcx
0x18000e4ac  jz      short loc_18000E4C0
0x18000e4ae  mov     [rsp+570h+ppv], r15
0x18000e4b3  mov     rax, [rcx]
0x18000e4b6  mov     rax, [rax+10h]
0x18000e4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4bf  nop
0x18000e4c0  lea     rax, [rsp+570h+ppv]
0x18000e4c5  mov     [rsp+570h+phkResult], rax; ppv
0x18000e4ca  lea     r9, _GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30; riid
0x18000e4d1  xor     edx, edx; pUnkOuter
0x18000e4d3  lea     r8d, [rdx+1]; dwClsContext
0x18000e4d7  lea     rcx, _GUID_c196b2be_ba06_4049_8518_322e1e04282b; rclsid
0x18000e4de  call    cs:__imp_CoCreateInstance
0x18000e4e4  mov     ebx, eax
0x18000e4e6  test    eax, eax
0x18000e4e8  jns     short loc_18000E516
0x18000e4ea  lea     rcx, [rsp+570h+Src]; void *
0x18000e4ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e4f4  nop
0x18000e4f5  mov     rcx, [rsp+570h+ppv]
0x18000e4fa  test    rcx, rcx
0x18000e4fd  jz      short loc_18000E511
0x18000e4ff  mov     [rsp+570h+ppv], r15
0x18000e504  mov     rax, [rcx]
0x18000e507  mov     rax, [rax+10h]
0x18000e50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e510  nop
0x18000e511  jmp     loc_18000EA9F
0x18000e516  mov     rcx, [rsp+570h+ppv]
0x18000e51b  mov     rax, [rcx]
0x18000e51e  lea     rdx, aCimv2; "./cimv2"
0x18000e525  mov     rax, [rax+28h]
0x18000e529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e52e  mov     ebx, eax
0x18000e530  test    eax, eax
0x18000e532  jns     short loc_18000E560
0x18000e534  lea     rcx, [rsp+570h+Src]; void *
0x18000e539  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e53e  nop
0x18000e53f  mov     rcx, [rsp+570h+ppv]
0x18000e544  test    rcx, rcx
0x18000e547  jz      short loc_18000E55B
0x18000e549  mov     [rsp+570h+ppv], r15
0x18000e54e  mov     rax, [rcx]
0x18000e551  mov     rax, [rax+10h]
0x18000e555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e55a  nop
0x18000e55b  jmp     loc_18000EA9F
0x18000e560  mov     rcx, [rsp+570h+ppv]
0x18000e565  mov     rax, [rcx]
0x18000e568  xor     r8d, r8d
0x18000e56b  lea     rdx, aMdmCertificate; "MDM_CertificateEnrollment"
0x18000e572  mov     rax, [rax+0B0h]
0x18000e579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e57e  mov     ebx, eax
0x18000e580  test    eax, eax
0x18000e582  jns     short loc_18000E5B0
0x18000e584  lea     rcx, [rsp+570h+Src]; void *
0x18000e589  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e58e  nop
0x18000e58f  mov     rcx, [rsp+570h+ppv]
0x18000e594  test    rcx, rcx
0x18000e597  jz      short loc_18000E5AB
0x18000e599  mov     [rsp+570h+ppv], r15
0x18000e59e  mov     rax, [rcx]
0x18000e5a1  mov     rax, [rax+10h]
0x18000e5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5aa  nop
0x18000e5ab  jmp     loc_18000EA9F
0x18000e5b0  xorps   xmm0, xmm0
0x18000e5b3  movups  [rsp+570h+var_4F8], xmm0
0x18000e5b8  xorps   xmm1, xmm1
0x18000e5bb  movdqu  [rbp+470h+var_4E8], xmm1
0x18000e5c0  mov     r8d, 19h
0x18000e5c6  lea     rdx, aMdmCertificate; "MDM_CertificateEnrollment"
0x18000e5cd  lea     rcx, [rsp+570h+var_4F8]
0x18000e5d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e5d7  lea     rdx, [rsp+570h+var_4F8]
0x18000e5dc  lea     rcx, [rsp+570h+Src]
0x18000e5e1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e5e6  lea     rcx, [rsp+570h+var_4F8]; void *
0x18000e5eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e5f0  lea     rdx, asc_180023428; "."
0x18000e5f7  lea     rcx, [rsp+570h+Src]; Src
0x18000e5fc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000e601  xorps   xmm0, xmm0
0x18000e604  movups  [rbp+470h+var_4D8], xmm0
0x18000e608  xorps   xmm1, xmm1
0x18000e60b  movdqu  [rbp+470h+var_4C8], xmm1
0x18000e610  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e614  mov     r8, rdi
0x18000e617  inc     r8
0x18000e61a  cmp     [rsi+r8*2], r15w
0x18000e61f  jnz     short loc_18000E617
0x18000e621  mov     rdx, rsi
0x18000e624  lea     rcx, [rbp+470h+var_4D8]
0x18000e628  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e62d  nop
0x18000e62e  xorps   xmm0, xmm0
0x18000e631  movups  [rsp+570h+var_4F8], xmm0
0x18000e636  xorps   xmm1, xmm1
0x18000e639  movdqu  [rbp+470h+var_4E8], xmm1
0x18000e63e  mov     r8d, 9
0x18000e644  lea     rdx, aRequestid; "RequestID"
0x18000e64b  lea     rcx, [rsp+570h+var_4F8]
0x18000e650  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e655  nop
0x18000e656  lea     rdx, asc_180023454; "=\""
0x18000e65d  lea     rcx, [rsp+570h+var_4F8]; Src
0x18000e662  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000e667  movups  xmm0, xmmword ptr [rax]
0x18000e66a  movups  [rbp+470h+var_498], xmm0
0x18000e66e  movups  xmm1, xmmword ptr [rax+10h]
0x18000e672  movups  [rbp+470h+var_488], xmm1
0x18000e676  mov     [rax+10h], r15
0x18000e67a  mov     esi, 7
0x18000e67f  mov     [rax+18h], rsi
0x18000e683  mov     [rax], r15w
0x18000e687  lea     r8, [rbp+470h+var_4D8]
0x18000e68b  lea     rdx, [rbp+470h+var_498]
0x18000e68f  lea     rcx, [rbp+470h+var_478]
0x18000e693  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18000e698  nop
0x18000e699  lea     rdx, asc_18002344C; "\","
0x18000e6a0  mov     rcx, rax; Src
0x18000e6a3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000e6a8  movups  xmm0, xmmword ptr [rax]
0x18000e6ab  movups  [rbp+470h+var_4B8], xmm0
0x18000e6af  movups  xmm1, xmmword ptr [rax+10h]
0x18000e6b3  movups  [rbp+470h+var_4A8], xmm1
0x18000e6b7  mov     [rax+10h], r15
0x18000e6bb  mov     [rax+18h], rsi
0x18000e6bf  mov     [rax], r15w
0x18000e6c3  lea     rdx, [rbp+470h+var_4B8]
0x18000e6c7  lea     rcx, [rsp+570h+Src]; Src
0x18000e6cc  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18000e6d1  nop
0x18000e6d2  lea     rcx, [rbp+470h+var_4B8]; void *
0x18000e6d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e6db  nop
0x18000e6dc  lea     rcx, [rbp+470h+var_478]; void *
0x18000e6e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e6e5  nop
0x18000e6e6  lea     rcx, [rbp+470h+var_498]; void *
0x18000e6ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e6ef  nop
0x18000e6f0  lea     rcx, [rsp+570h+var_4F8]; void *
0x18000e6f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e6fa  nop
0x18000e6fb  lea     rcx, [rbp+470h+var_4D8]; void *
0x18000e6ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e704  mov     edx, [rsp+570h+var_51C]
0x18000e708  lea     rcx, [rsp+570h+var_4F8]; void *
0x18000e70d  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18000e712  mov     rbx, rax
0x18000e715  xorps   xmm0, xmm0
0x18000e718  movups  [rbp+470h+var_4D8], xmm0
0x18000e71c  xorps   xmm1, xmm1
0x18000e71f  movdqu  [rbp+470h+var_4C8], xmm1
0x18000e724  lea     r8d, [rsi+6]
0x18000e728  lea     rdx, aStorelocation; "StoreLocation"
0x18000e72f  lea     rcx, [rbp+470h+var_4D8]
0x18000e733  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e738  nop
  ... truncated ...
```
