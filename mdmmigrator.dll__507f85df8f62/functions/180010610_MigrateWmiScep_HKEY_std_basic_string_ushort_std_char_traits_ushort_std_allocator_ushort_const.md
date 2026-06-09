# MigrateWmiScep(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010610`
- end: `0x18001085b`
- name: `?MigrateWmiScep@@YAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f5c4`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x1800034f0`
- `0x180007f40`
- `0x18000da88`
- `0x18000e284`
- `0x18000f004`
- `0x180010610`
- `0x180010dc0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001068f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001068f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010812`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001066f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001066f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800106d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800106d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800107ed`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800107ed`
- `DMCmnUtils!DmRevertToSelf` at `0x180010759`
- `DMCmnUtils!DmRevertToSelf` at `0x180010759`

## pseudocode

```c
__int64 __fastcall MigrateWmiScep(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  int v4; // ebx
  bool v5; // cc
  int v7; // edi
  DWORD v8; // r15d
  WCHAR *v9; // rsi
  WCHAR *v10; // r8
  DWORD i; // edx
  const unsigned __int16 *v12; // rcx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // rdx
  struct IConfigManager2URI *v15; // rcx
  const struct std::nothrow_t *v16; // rdx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  int v20; // [rsp+70h] [rbp-9h] BYREF
  struct IConfigManager2URI *v21; // [rsp+78h] [rbp-1h] BYREF
  WCHAR *v22; // [rsp+80h] [rbp+7h]
  _BYTE v23[32]; // [rsp+88h] [rbp+Fh] BYREF

  cbMaxSubKeyLen = 0;
  cchName = 0;
  v22 = 0;
  v20 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(a1, L"MDM_CertificateEnrollmentDB", 0, 0x20019u, &hKey);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3 || (v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0), v4 = v3, v5 = v3 <= 0, v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v7 = 0;
    v8 = 0;
    v9 = (WCHAR *)operator new[](saturated_mul(cbMaxSubKeyLen + 1, 2u));
    v22 = v9;
    *v9 = 0;
    cchName = cbMaxSubKeyLen + 1;
    v10 = v9;
    for ( i = 0; ; i = v8 )
    {
      v4 = RegEnumKeyExW(hKey, i, v10, &cchName, 0, 0, 0, 0);
      if ( v4 == 259 )
      {
        operator delete(v9, v16);
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v7;
      }
      if ( v4 )
        break;
      v21 = 0;
      v7 = CreateScepPath(hKey, v9, &v21);
      if ( v7 >= 0 )
      {
        std::wstring::wstring((__int64)v23, (__int64)a2);
        if ( byte_18002B7D8 )
          DmRevertToSelf();
        byte_18002B7D8 = 0;
        v7 = IsWmiResourceProvisioned(v21, &v20);
        if ( v7 >= 0 && !v20 )
        {
          if ( *((_QWORD *)a2 + 3) <= 7u )
            v14 = a2;
          else
            v14 = *(const unsigned __int16 **)a2;
          v7 = WriteToERMTracked(v12, v14, v13, v21);
        }
        ErmRevertImpersonate::~ErmRevertImpersonate((ErmRevertImpersonate *)v23);
      }
      *v9 = 0;
      cchName = cbMaxSubKeyLen + 1;
      ++v8;
      v15 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v10 = v9;
    }
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    operator delete(v9, v16);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010610  mov     [rsp-8+arg_10], rbx
0x180010615  mov     [rsp-8+arg_18], rsi
0x18001061a  push    rbp
0x18001061b  push    rdi
0x18001061c  push    r12
0x18001061e  push    r14
0x180010620  push    r15
0x180010622  lea     rbp, [rsp-37h]
0x180010627  sub     rsp, 0B0h
0x18001062e  mov     rax, cs:__security_cookie
0x180010635  xor     rax, rsp
0x180010638  mov     [rbp+57h+var_28], rax
0x18001063c  mov     r14, rdx
0x18001063f  xor     r12d, r12d
0x180010642  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180010646  mov     [rbp+57h+cchName], r12d
0x18001064a  mov     [rbp+57h+var_50], r12
0x18001064e  mov     [rbp+57h+var_60], r12d
0x180010652  mov     [rbp+57h+hKey], r12
0x180010656  lea     rax, [rbp+57h+hKey]
0x18001065a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001065f  mov     r9d, 20019h; samDesired
0x180010665  xor     r8d, r8d; ulOptions
0x180010668  lea     rdx, aMdmCertificate_1; "MDM_CertificateEnrollmentDB"
0x18001066f  call    cs:__imp_RegOpenKeyExW
0x180010675  mov     ebx, eax
0x180010677  test    eax, eax
0x180010679  jz      short loc_18001069C
0x18001067b  jle     short loc_180010686
0x18001067d  movzx   ebx, ax
0x180010680  or      ebx, 80070000h
0x180010686  mov     rcx, [rbp+57h+hKey]; hKey
0x18001068a  test    rcx, rcx
0x18001068d  jz      short loc_180010695
0x18001068f  call    cs:__imp_RegCloseKey
0x180010695  mov     eax, ebx
0x180010697  jmp     loc_18001081A
0x18001069c  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800106a1  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800106a6  mov     [rsp+0D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800106ab  mov     [rsp+0D0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800106b0  mov     [rsp+0D0h+lpcValues], r12; lpcValues
0x1800106b5  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800106ba  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800106be  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800106c3  mov     [rsp+0D0h+phkResult], r12; lpcSubKeys
0x1800106c8  xor     r9d, r9d; lpReserved
0x1800106cb  xor     r8d, r8d; lpcchClass
0x1800106ce  xor     edx, edx; lpClass
0x1800106d0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800106d4  call    cs:__imp_RegQueryInfoKeyW
0x1800106da  mov     ebx, eax
0x1800106dc  test    eax, eax
0x1800106de  jnz     short loc_18001067B
0x1800106e0  mov     edi, r12d
0x1800106e3  mov     r15d, r12d
0x1800106e6  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1800106e9  inc     ecx
0x1800106eb  lea     eax, [rbx+2]
0x1800106ee  mul     rcx
0x1800106f1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800106f8  cmovb   rax, rcx
0x1800106fc  mov     rcx, rax; unsigned __int64
0x1800106ff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010704  mov     rsi, rax
0x180010707  mov     [rbp+57h+var_50], rax
0x18001070b  mov     [rax], r12w
0x18001070f  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x180010712  inc     ecx
0x180010714  mov     [rbp+57h+cchName], ecx
0x180010717  mov     r8, rax
0x18001071a  xor     edx, edx
0x18001071c  jmp     loc_1800107D1
0x180010721  test    ebx, ebx
0x180010723  jnz     loc_180010842
0x180010729  mov     [rbp+57h+var_58], r12
0x18001072d  lea     r8, [rbp+57h+var_58]; struct IConfigManager2URI **
0x180010731  mov     rdx, rsi; unsigned __int16 *
0x180010734  mov     rcx, [rbp+57h+hKey]; HKEY
0x180010738  call    ?CreateScepPath@@YAJPEAUHKEY__@@PEBGPEAPEAUIConfigManager2URI@@@Z; CreateScepPath(HKEY__ *,ushort const *,IConfigManager2URI * *)
0x18001073d  mov     edi, eax
0x18001073f  test    eax, eax
0x180010741  js      short loc_1800107A2
0x180010743  mov     rdx, r14
0x180010746  lea     rcx, [rbp+57h+var_48]
0x18001074a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001074f  nop
0x180010750  cmp     cs:byte_18002B7D8, r12b
0x180010757  jz      short loc_18001075F
0x180010759  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001075f  mov     cs:byte_18002B7D8, r12b
0x180010766  lea     rdx, [rbp+57h+var_60]; int *
0x18001076a  mov     rcx, [rbp+57h+var_58]; struct IConfigManager2URI *
0x18001076e  call    ?IsWmiResourceProvisioned@@YAJPEAUIConfigManager2URI@@PEAH@Z; IsWmiResourceProvisioned(IConfigManager2URI *,int *)
0x180010773  mov     edi, eax
0x180010775  test    eax, eax
0x180010777  js      short loc_180010799
0x180010779  cmp     [rbp+57h+var_60], r12d
0x18001077d  jnz     short loc_180010799
0x18001077f  cmp     qword ptr [r14+18h], 7
0x180010784  jbe     short loc_18001078B
0x180010786  mov     rdx, [r14]
0x180010789  jmp     short loc_18001078E
0x18001078b  mov     rdx, r14; unsigned __int16 *
0x18001078e  mov     r9, [rbp+57h+var_58]; struct IConfigManager2URI *
0x180010792  call    ?WriteToERMTracked@@YAJPEBG00PEAUIConfigManager2URI@@@Z; WriteToERMTracked(ushort const *,ushort const *,ushort const *,IConfigManager2URI *)
0x180010797  mov     edi, eax
0x180010799  lea     rcx, [rbp+57h+var_48]; this
0x18001079d  call    ??1ErmRevertImpersonate@@QEAA@XZ; ErmRevertImpersonate::~ErmRevertImpersonate(void)
0x1800107a2  mov     [rsi], r12w
0x1800107a6  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800107a9  inc     eax
0x1800107ab  mov     [rbp+57h+cchName], eax
0x1800107ae  inc     r15d
0x1800107b1  mov     rcx, [rbp+57h+var_58]
0x1800107b5  test    rcx, rcx
0x1800107b8  jz      short loc_1800107CB
0x1800107ba  mov     [rbp+57h+var_58], r12
0x1800107be  mov     rax, [rcx]
0x1800107c1  mov     rax, [rax+10h]
0x1800107c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ca  nop
0x1800107cb  mov     r8, rsi; lpName
0x1800107ce  mov     edx, r15d; dwIndex
0x1800107d1  mov     [rsp+0D0h+lpcValues], r12; lpftLastWriteTime
0x1800107d6  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcchClass
0x1800107db  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800107e0  mov     [rsp+0D0h+phkResult], r12; lpReserved
0x1800107e5  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800107e9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800107ed  call    cs:__imp_RegEnumKeyExW
0x1800107f3  cmp     eax, 103h
0x1800107f8  mov     ebx, eax
0x1800107fa  jnz     loc_180010721
0x180010800  mov     rcx, rsi; void *
0x180010803  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010808  nop
0x180010809  mov     rcx, [rbp+57h+hKey]; hKey
0x18001080d  test    rcx, rcx
0x180010810  jz      short loc_180010818
0x180010812  call    cs:__imp_RegCloseKey
0x180010818  mov     eax, edi
0x18001081a  mov     rcx, [rbp+57h+var_28]
0x18001081e  xor     rcx, rsp; StackCookie
0x180010821  call    __security_check_cookie
0x180010826  lea     r11, [rsp+0D0h+var_20]
0x18001082e  mov     rbx, [r11+40h]
0x180010832  mov     rsi, [r11+48h]
0x180010836  mov     rsp, r11
0x180010839  pop     r15
0x18001083b  pop     r14
0x18001083d  pop     r12
0x18001083f  pop     rdi
0x180010840  pop     rbp
0x180010841  retn
0x180010842  jle     short loc_18001084D
0x180010844  movzx   ebx, bx
0x180010847  or      ebx, 80070000h
0x18001084d  mov     rcx, rsi; void *
0x180010850  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010855  jmp     loc_180010686
```
