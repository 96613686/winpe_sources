# MigrateWmiAppInstallJob(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010170`
- end: `0x18001060a`
- name: `?MigrateWmiAppInstallJob@@YAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f5c4`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x1800034f0`
- `0x180007720`
- `0x180007b38`
- `0x180007f40`
- `0x18000820c`
- `0x18000977c`
- `0x18000cde0`
- `0x18000da88`
- `0x18000dca4`
- `0x18000f004`
- `0x180010170`
- `0x180010dc0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800102ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800102ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001020d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001023d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001057b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001020d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001023d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001057b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010284`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010284`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001054b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001054b`
- `DMCmnUtils!DmRevertToSelf` at `0x180010494`
- `DMCmnUtils!DmRevertToSelf` at `0x180010494`

## string_xrefs

- `0x18001033c`: `MDM_AppInstallJob`
- `0x18001036e`: `MDM_AppInstallJob`

## pseudocode

```c
__int64 __fastcall MigrateWmiAppInstallJob(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  int v4; // ebx
  bool v6; // cc
  int v7; // esi
  DWORD v8; // r15d
  WCHAR *v9; // rdi
  WCHAR *v10; // r8
  DWORD i; // edx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  __int128 *p_Src; // rdx
  const unsigned __int16 *v16; // rcx
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // rdx
  struct IConfigManager2URI *v19; // rcx
  LPVOID v20; // rcx
  const struct std::nothrow_t *v21; // rdx
  LPVOID v22; // rcx
  LPVOID v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  int v29; // [rsp+78h] [rbp-88h] BYREF
  struct IConfigManager2URI *v30; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v31; // [rsp+88h] [rbp-78h]
  __int128 Src; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v34; // [rsp+A8h] [rbp-58h]
  __int128 v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  _OWORD v38[2]; // [rsp+D0h] [rbp-30h] BYREF
  char *v39[4]; // [rsp+F0h] [rbp-10h] BYREF

  cbMaxSubKeyLen = 0;
  cchName = 0;
  v31 = 0;
  Src = 0;
  v33 = 0;
  v34 = 7;
  LOWORD(Src) = 0;
  v29 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(a1, L"JobDB", 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 == 2 )
  {
    std::wstring::~wstring((char **)&Src);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v6 = v3 <= 0;
    if ( v3 || (v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0), v4 = v3, v6 = v3 <= 0, v3) )
    {
      if ( !v6 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&Src);
LABEL_9:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v4;
    }
    else
    {
      v7 = 0;
      v8 = 0;
      v9 = (WCHAR *)operator new[](saturated_mul(cbMaxSubKeyLen + 1, 2u));
      v31 = v9;
      *v9 = 0;
      cchName = cbMaxSubKeyLen + 1;
      v10 = v9;
      for ( i = 0; ; i = v8 )
      {
        v4 = RegEnumKeyExW(hKey, i, v10, &cchName, 0, 0, 0, 0);
        if ( v4 == 259 )
          break;
        if ( v4 )
        {
          if ( v4 > 0 )
            v4 = (unsigned __int16)v4 | 0x80070000;
          goto LABEL_48;
        }
        ppv = 0;
        v4 = CoCreateInstance(
               &GUID_c196b2be_ba06_4049_8518_322e1e04282b,
               0,
               1u,
               &GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30,
               &ppv);
        if ( v4 < 0 )
        {
          v23 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
          }
          goto LABEL_48;
        }
        v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 40LL))(ppv, L"./cimv2");
        if ( v4 < 0 )
        {
          v22 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
          }
LABEL_48:
          std::wstring::~wstring((char **)&Src);
          operator delete(v9, v24);
          goto LABEL_9;
        }
        v7 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 176LL))(
               ppv,
               L"MDM_AppInstallJob",
               0);
        if ( v7 >= 0 )
        {
          v35 = 0;
          v36 = 0;
          v37 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v35, L"MDM_AppInstallJob", 0x11u);
          std::wstring::operator=((char **)&Src, (__int64)&v35);
          std::wstring::~wstring((char **)&v35);
          v35 = 0;
          v36 = 0;
          v37 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v35, L"JobID", 5u);
          v13 = (_QWORD *)std::operator+<unsigned short>(v39, v12, &v35);
          v14 = std::wstring::append(v13, L"=");
          v38[0] = *(_OWORD *)v14;
          v38[1] = *((_OWORD *)v14 + 1);
          v14[2] = 0;
          v14[3] = 7;
          *(_WORD *)v14 = 0;
          std::wstring::operator+=(&Src);
          std::wstring::~wstring((char **)v38);
          std::wstring::~wstring(v39);
          std::wstring::~wstring((char **)&v35);
          std::wstring::append(&Src, v9);
          p_Src = &Src;
          if ( v34 > 7 )
            p_Src = (__int128 *)Src;
          v7 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, _QWORD))(*(_QWORD *)ppv + 176LL))(ppv, p_Src, 0);
          if ( v7 >= 0 )
          {
            v30 = 0;
            v7 = (*(__int64 (__fastcall **)(LPVOID, struct IConfigManager2URI **))(*(_QWORD *)ppv + 224LL))(ppv, &v30);
            if ( v7 >= 0 )
            {
              std::wstring::wstring((__int64)v39, (__int64)a2);
              if ( byte_18002B7D8 )
                DmRevertToSelf();
              byte_18002B7D8 = 0;
              v7 = IsWmiResourceProvisioned(v30, &v29);
              if ( v7 >= 0 && !v29 )
              {
                if ( *((_QWORD *)a2 + 3) <= 7u )
                  v18 = a2;
                else
                  v18 = *(const unsigned __int16 **)a2;
                v7 = WriteToERMTracked(v16, v18, v17, v30);
              }
              ErmRevertImpersonate::~ErmRevertImpersonate((ErmRevertImpersonate *)v39);
            }
            v19 = v30;
            if ( v30 )
            {
              v30 = 0;
              (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v19 + 16LL))(v19);
            }
          }
        }
        *v9 = 0;
        cchName = cbMaxSubKeyLen + 1;
        ++v8;
        v20 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v10 = v9;
      }
      std::wstring::~wstring((char **)&Src);
      operator delete(v9, v21);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v7;
    }
  }
}

```

## disassembly

```asm
0x180010170  mov     [rsp-8+arg_10], rbx
0x180010175  mov     [rsp-8+arg_18], rsi
0x18001017a  push    rbp
0x18001017b  push    rdi
0x18001017c  push    r12
0x18001017e  push    r14
0x180010180  push    r15
0x180010182  lea     rbp, [rsp-20h]
0x180010187  sub     rsp, 120h
0x18001018e  mov     rax, cs:__security_cookie
0x180010195  xor     rax, rsp
0x180010198  mov     [rbp+40h+var_30], rax
0x18001019c  mov     r14, rdx
0x18001019f  xor     r12d, r12d
0x1800101a2  mov     [rsp+140h+cbMaxSubKeyLen], r12d
0x1800101a7  mov     [rsp+140h+cchName], r12d
0x1800101ac  mov     [rbp+40h+var_B8], r12
0x1800101b0  xorps   xmm0, xmm0
0x1800101b3  movups  [rbp+40h+Src], xmm0
0x1800101b7  mov     [rbp+40h+var_A0], r12
0x1800101bb  mov     [rbp+40h+var_98], 7
0x1800101c3  mov     word ptr [rbp+40h+Src], r12w
0x1800101c8  mov     [rsp+140h+var_C8], r12d
0x1800101cd  mov     [rsp+140h+hKey], r12
0x1800101d2  lea     rax, [rsp+140h+hKey]
0x1800101d7  mov     [rsp+140h+phkResult], rax; phkResult
0x1800101dc  mov     r9d, 20019h; samDesired
0x1800101e2  xor     r8d, r8d; ulOptions
0x1800101e5  lea     rdx, aJobdb; "JobDB"
0x1800101ec  call    cs:__imp_RegOpenKeyExW
0x1800101f2  mov     ebx, eax
0x1800101f4  cmp     eax, 2
0x1800101f7  jnz     short loc_18001021A
0x1800101f9  lea     rcx, [rbp+40h+Src]; void *
0x1800101fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010202  nop
0x180010203  mov     rcx, [rsp+140h+hKey]; hKey
0x180010208  test    rcx, rcx
0x18001020b  jz      short loc_180010213
0x18001020d  call    cs:__imp_RegCloseKey
0x180010213  xor     eax, eax
0x180010215  jmp     loc_180010583
0x18001021a  test    eax, eax
0x18001021c  jz      short loc_18001024A
0x18001021e  jle     short loc_180010229
0x180010220  movzx   ebx, ax
0x180010223  or      ebx, 80070000h
0x180010229  lea     rcx, [rbp+40h+Src]; void *
0x18001022d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010232  nop
0x180010233  mov     rcx, [rsp+140h+hKey]; hKey
0x180010238  test    rcx, rcx
0x18001023b  jz      short loc_180010243
0x18001023d  call    cs:__imp_RegCloseKey
0x180010243  mov     eax, ebx
0x180010245  jmp     loc_180010583
0x18001024a  mov     [rsp+140h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001024f  mov     [rsp+140h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180010254  mov     [rsp+140h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180010259  mov     [rsp+140h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18001025e  mov     [rsp+140h+lpcValues], r12; lpcValues
0x180010263  mov     [rsp+140h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180010268  lea     rax, [rsp+140h+cbMaxSubKeyLen]
0x18001026d  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180010272  mov     [rsp+140h+phkResult], r12; lpcSubKeys
0x180010277  xor     r9d, r9d; lpReserved
0x18001027a  xor     r8d, r8d; lpcchClass
0x18001027d  xor     edx, edx; lpClass
0x18001027f  mov     rcx, [rsp+140h+hKey]; hKey
0x180010284  call    cs:__imp_RegQueryInfoKeyW
0x18001028a  mov     ebx, eax
0x18001028c  test    eax, eax
0x18001028e  jnz     short loc_18001021E
0x180010290  mov     esi, r12d
0x180010293  mov     r15d, r12d
0x180010296  mov     edx, [rsp+140h+cbMaxSubKeyLen]
0x18001029a  inc     edx
0x18001029c  lea     eax, [rbx+2]
0x18001029f  mul     rdx
0x1800102a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800102a9  cmovb   rax, rcx
0x1800102ad  mov     rcx, rax; unsigned __int64
0x1800102b0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800102b5  mov     rdi, rax
0x1800102b8  mov     [rbp+40h+var_B8], rax
0x1800102bc  mov     [rax], r12w
0x1800102c0  mov     ecx, [rsp+140h+cbMaxSubKeyLen]
0x1800102c4  inc     ecx
0x1800102c6  mov     [rsp+140h+cchName], ecx
0x1800102ca  mov     r8, rax
0x1800102cd  xor     edx, edx
0x1800102cf  jmp     loc_18001052D
0x1800102d4  test    ebx, ebx
0x1800102d6  jnz     loc_1800105E7
0x1800102dc  mov     [rsp+140h+ppv], r12
0x1800102e1  lea     rax, [rsp+140h+ppv]
0x1800102e6  mov     [rsp+140h+phkResult], rax; ppv
0x1800102eb  lea     r9, _GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30; riid
0x1800102f2  xor     edx, edx; pUnkOuter
0x1800102f4  lea     r8d, [rbx+1]; dwClsContext
0x1800102f8  lea     rcx, _GUID_c196b2be_ba06_4049_8518_322e1e04282b; rclsid
0x1800102ff  call    cs:__imp_CoCreateInstance
0x180010305  mov     ebx, eax
0x180010307  test    eax, eax
0x180010309  js      loc_1800105C9
0x18001030f  mov     rcx, [rsp+140h+ppv]
0x180010314  mov     rax, [rcx]
0x180010317  lea     rdx, aCimv2; "./cimv2"
0x18001031e  mov     rax, [rax+28h]
0x180010322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010327  mov     ebx, eax
0x180010329  test    eax, eax
0x18001032b  js      loc_1800105AB
0x180010331  mov     rcx, [rsp+140h+ppv]
0x180010336  mov     rax, [rcx]
0x180010339  xor     r8d, r8d
0x18001033c  lea     rdx, aMdmAppinstallj; "MDM_AppInstallJob"
0x180010343  mov     rax, [rax+0B0h]
0x18001034a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001034f  mov     esi, eax
0x180010351  test    eax, eax
0x180010353  js      loc_1800104FA
0x180010359  xorps   xmm0, xmm0
0x18001035c  movups  [rbp+40h+var_90], xmm0
0x180010360  mov     [rbp+40h+var_80], r12
0x180010364  mov     [rbp+40h+var_78], r12
0x180010368  mov     r8d, 11h
0x18001036e  lea     rdx, aMdmAppinstallj; "MDM_AppInstallJob"
0x180010375  lea     rcx, [rbp+40h+var_90]
0x180010379  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001037e  lea     rdx, [rbp+40h+var_90]
0x180010382  lea     rcx, [rbp+40h+Src]
0x180010386  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001038b  lea     rcx, [rbp+40h+var_90]; void *
0x18001038f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010394  xorps   xmm0, xmm0
0x180010397  movups  [rbp+40h+var_90], xmm0
0x18001039b  mov     [rbp+40h+var_80], r12
0x18001039f  mov     [rbp+40h+var_78], r12
0x1800103a3  mov     r8d, 5
0x1800103a9  lea     rdx, aJobid; "JobID"
0x1800103b0  lea     rcx, [rbp+40h+var_90]
0x1800103b4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800103b9  nop
0x1800103ba  lea     r8, [rbp+40h+var_90]
0x1800103be  lea     rcx, [rbp+40h+var_50]
0x1800103c2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800103c7  nop
0x1800103c8  lea     rdx, asc_180023424; "="
0x1800103cf  mov     rcx, rax; Src
0x1800103d2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800103d7  movups  xmm0, xmmword ptr [rax]
0x1800103da  movups  [rbp+40h+var_70], xmm0
0x1800103de  movups  xmm1, xmmword ptr [rax+10h]
0x1800103e2  movups  [rbp+40h+var_60], xmm1
0x1800103e6  mov     [rax+10h], r12
0x1800103ea  mov     qword ptr [rax+18h], 7
0x1800103f2  mov     [rax], r12w
0x1800103f6  lea     rdx, [rbp+40h+var_70]
0x1800103fa  lea     rcx, [rbp+40h+Src]; Src
0x1800103fe  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x180010403  nop
0x180010404  lea     rcx, [rbp+40h+var_70]; void *
0x180010408  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001040d  nop
0x18001040e  lea     rcx, [rbp+40h+var_50]; void *
0x180010412  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010417  nop
0x180010418  lea     rcx, [rbp+40h+var_90]; void *
0x18001041c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010421  mov     rdx, rdi; void *
0x180010424  lea     rcx, [rbp+40h+Src]; Src
0x180010428  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001042d  mov     rcx, [rsp+140h+ppv]
0x180010432  mov     rax, [rcx]
0x180010435  lea     rdx, [rbp+40h+Src]
0x180010439  cmp     [rbp+40h+var_98], 7
0x18001043e  cmova   rdx, qword ptr [rbp+40h+Src]
0x180010443  xor     r8d, r8d
0x180010446  mov     rax, [rax+0B0h]
0x18001044d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010452  mov     esi, eax
0x180010454  test    eax, eax
0x180010456  js      loc_1800104FA
0x18001045c  mov     [rbp+40h+var_C0], r12
0x180010460  mov     rcx, [rsp+140h+ppv]
0x180010465  mov     rax, [rcx]
0x180010468  lea     rdx, [rbp+40h+var_C0]
0x18001046c  mov     rax, [rax+0E0h]
0x180010473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010478  mov     esi, eax
0x18001047a  test    eax, eax
0x18001047c  js      short loc_1800104E0
0x18001047e  mov     rdx, r14
0x180010481  lea     rcx, [rbp+40h+var_50]
0x180010485  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001048a  nop
0x18001048b  cmp     cs:byte_18002B7D8, r12b
0x180010492  jz      short loc_18001049A
0x180010494  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001049a  mov     cs:byte_18002B7D8, r12b
0x1800104a1  lea     rdx, [rsp+140h+var_C8]; int *
0x1800104a6  mov     rcx, [rbp+40h+var_C0]; struct IConfigManager2URI *
0x1800104aa  call    ?IsWmiResourceProvisioned@@YAJPEAUIConfigManager2URI@@PEAH@Z; IsWmiResourceProvisioned(IConfigManager2URI *,int *)
0x1800104af  mov     esi, eax
0x1800104b1  test    eax, eax
0x1800104b3  js      short loc_1800104D6
0x1800104b5  cmp     [rsp+140h+var_C8], r12d
0x1800104ba  jnz     short loc_1800104D6
0x1800104bc  cmp     qword ptr [r14+18h], 7
0x1800104c1  jbe     short loc_1800104C8
0x1800104c3  mov     rdx, [r14]
0x1800104c6  jmp     short loc_1800104CB
0x1800104c8  mov     rdx, r14; unsigned __int16 *
0x1800104cb  mov     r9, [rbp+40h+var_C0]; struct IConfigManager2URI *
0x1800104cf  call    ?WriteToERMTracked@@YAJPEBG00PEAUIConfigManager2URI@@@Z; WriteToERMTracked(ushort const *,ushort const *,ushort const *,IConfigManager2URI *)
0x1800104d4  mov     esi, eax
0x1800104d6  lea     rcx, [rbp+40h+var_50]; this
0x1800104da  call    ??1ErmRevertImpersonate@@QEAA@XZ; ErmRevertImpersonate::~ErmRevertImpersonate(void)
0x1800104df  nop
0x1800104e0  mov     rcx, [rbp+40h+var_C0]
0x1800104e4  test    rcx, rcx
0x1800104e7  jz      short loc_1800104FA
0x1800104e9  mov     [rbp+40h+var_C0], r12
0x1800104ed  mov     rax, [rcx]
0x1800104f0  mov     rax, [rax+10h]
0x1800104f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f9  nop
0x1800104fa  mov     [rdi], r12w
0x1800104fe  mov     eax, [rsp+140h+cbMaxSubKeyLen]
0x180010502  inc     eax
0x180010504  mov     [rsp+140h+cchName], eax
0x180010508  inc     r15d
0x18001050b  mov     rcx, [rsp+140h+ppv]
0x180010510  test    rcx, rcx
0x180010513  jz      short loc_180010527
0x180010515  mov     [rsp+140h+ppv], r12
0x18001051a  mov     rax, [rcx]
0x18001051d  mov     rax, [rax+10h]
0x180010521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010526  nop
0x180010527  mov     r8, rdi; lpName
0x18001052a  mov     edx, r15d; dwIndex
0x18001052d  mov     [rsp+140h+lpcValues], r12; lpftLastWriteTime
0x180010532  mov     [rsp+140h+lpcbMaxClassLen], r12; lpcchClass
0x180010537  mov     [rsp+140h+lpcbMaxSubKeyLen], r12; lpClass
0x18001053c  mov     [rsp+140h+phkResult], r12; lpReserved
0x180010541  lea     r9, [rsp+140h+cchName]; lpcchName
0x180010546  mov     rcx, [rsp+140h+hKey]; hKey
0x18001054b  call    cs:__imp_RegEnumKeyExW
0x180010551  cmp     eax, 103h
0x180010556  mov     ebx, eax
0x180010558  jnz     loc_1800102D4
0x18001055e  lea     rcx, [rbp+40h+Src]; void *
0x180010562  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010567  nop
0x180010568  mov     rcx, rdi; void *
0x18001056b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010570  nop
0x180010571  mov     rcx, [rsp+140h+hKey]; hKey
0x180010576  test    rcx, rcx
0x180010579  jz      short loc_180010581
0x18001057b  call    cs:__imp_RegCloseKey
0x180010581  mov     eax, esi
0x180010583  mov     rcx, [rbp+40h+var_30]
0x180010587  xor     rcx, rsp; StackCookie
0x18001058a  call    __security_check_cookie
0x18001058f  lea     r11, [rsp+140h+var_20]
0x180010597  mov     rbx, [r11+40h]
0x18001059b  mov     rsi, [r11+48h]
0x18001059f  mov     rsp, r11
0x1800105a2  pop     r15
0x1800105a4  pop     r14
0x1800105a6  pop     r12
0x1800105a8  pop     rdi
0x1800105a9  pop     rbp
0x1800105aa  retn
0x1800105ab  mov     rcx, [rsp+140h+ppv]
0x1800105b0  test    rcx, rcx
0x1800105b3  jz      short loc_1800105C7
0x1800105b5  mov     [rsp+140h+ppv], r12
0x1800105ba  mov     rax, [rcx]
0x1800105bd  mov     rax, [rax+10h]
0x1800105c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c6  nop
0x1800105c7  jmp     short loc_1800105F2
0x1800105c9  mov     rcx, [rsp+140h+ppv]
0x1800105ce  test    rcx, rcx
0x1800105d1  jz      short loc_1800105E5
0x1800105d3  mov     [rsp+140h+ppv], r12
0x1800105d8  mov     rax, [rcx]
0x1800105db  mov     rax, [rax+10h]
0x1800105df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e4  nop
0x1800105e5  jmp     short loc_1800105F2
0x1800105e7  jle     short loc_1800105F2
0x1800105e9  movzx   ebx, bx
0x1800105ec  or      ebx, 80070000h
0x1800105f2  lea     rcx, [rbp+40h+Src]; void *
0x1800105f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
