# Csl::CopyRegistryKeyToOfflineHive(Csl::RegistryKey &,Csl::OfflineHive &,Csl::Path const &)

- ea: `0x180198e0c`
- end: `0x18019923f`
- name: `?CopyRegistryKeyToOfflineHive@Csl@@YAJAEAVRegistryKey@1@AEAVOfflineHive@1@AEBVPath@1@@Z`
- size: `1075`
- prototype: `int(Csl *__hidden this, struct Csl::RegistryKey *, struct Csl::OfflineHive *, const struct Path *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180199248`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x18000da88`
- `0x18000dad8`
- `0x180032714`
- `0x180033104`
- `0x1800343f0`
- `0x180198e0c`
- `0x18019a068`
- `0x18019a1b4`
- `0x18019a294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180198e74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019902b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801990da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801991e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019921c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180198e74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019902b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801990da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801991e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019921c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180198ea0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180198f34`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180198ea0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180198f34`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180199129`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180199129`

## string_xrefs

- `0x180198ec6`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x180198f4f`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18019913d`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x180198e57`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x180198f77`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x180198fdb`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18019908f`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x180199160`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x180199205`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::CopyRegistryKeyToOfflineHive(
        Csl *this,
        struct Csl::RegistryKey *a2,
        const unsigned __int16 **a3,
        const struct Path *a4)
{
  __int64 v4; // rcx
  Csl::OfflineHive *v6; // r12
  int v7; // eax
  unsigned int v8; // ebx
  HKEY v10; // rbx
  unsigned int KeySecurity; // eax
  int v12; // edi
  __int64 v13; // rdx
  DWORD v14; // edi
  void *v15; // rax
  void *v16; // r15
  unsigned int v17; // eax
  unsigned int v18; // r8d
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  int v21; // eax
  int v22; // esi
  const struct std::nothrow_t *v23; // rdx
  __int64 v24; // rcx
  void *v25; // rdi
  void *v26; // rcx
  _BYTE *v27; // r14
  char *v28; // rdi
  char *i; // rsi
  int v30; // eax
  unsigned int v31; // r12d
  const struct std::nothrow_t *v32; // rdx
  __int64 v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  __int64 v38; // rcx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-49h]
  int lpcSubKeysa; // [rsp+20h] [rbp-49h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-49h]
  void *v42[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v43; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbSecurityDescriptor; // [rsp+D0h] [rbp+67h] BYREF
  struct Csl::RegistryKey *v46; // [rsp+D8h] [rbp+6Fh]
  HKEY hKey; // [rsp+E0h] [rbp+77h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+E8h] [rbp+7Fh] BYREF

  v46 = a2;
  v4 = *(_QWORD *)this;
  hKey = 0;
  v6 = a2;
  v7 = Csl::OpenRegistryKey(v4, *a3, 131097, &hKey);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)v7,
      lpcSubKeys);
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  v10 = hKey;
  cbSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
  v12 = KeySecurity;
  if ( KeySecurity == 122 )
  {
    v12 = -2147024774;
  }
  else if ( KeySecurity )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4CE,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
            (const char *)KeySecurity,
            lpcSubKeys);
  }
  if ( v12 != -2147024774 )
  {
    if ( v12 < 0 )
    {
      v13 = 1272;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v12,
        lpcSubKeys);
    }
LABEL_52:
    if ( v10 )
      RegCloseKey(v10);
    return (unsigned int)v12;
  }
  v14 = cbSecurityDescriptor;
  v15 = operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    v13 = 1276;
    goto LABEL_51;
  }
  memset_0(v15, 0, v14);
  v17 = RegGetKeySecurity(v10, 4u, v16, &cbSecurityDescriptor);
  v12 = v17;
  if ( v17 == 122 )
  {
    v12 = -2147024774;
  }
  else if ( v17 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4CE,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
            (const char *)v17,
            lpcSubKeys);
  }
  if ( v12 < 0 )
  {
    v19 = 1283;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)v12,
      lpcSubKeys);
    operator delete(v16, v20);
    goto LABEL_52;
  }
  v12 = Csl::OfflineHive::SetKeySecurity(v6, *a3, v18, v16);
  if ( v12 < 0 )
  {
    v19 = 1288;
    goto LABEL_19;
  }
  v43 = -1;
  *(__m128i *)v42 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v21 = Csl::RegistryKey::EnumerateValues(&hKey, v42);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)v21,
      lpcSubKeys);
    v25 = v42[0];
    if ( v42[0] == (void *)-1LL )
    {
LABEL_26:
      operator delete(v16, v23);
      if ( v10 )
        RegCloseKey(v10);
      return (unsigned int)v22;
    }
    utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v24, v42[0], ((char *)v42[1] - (char *)v42[0]) >> 6);
    v26 = v25;
LABEL_25:
    operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_26;
  }
  v27 = v42[0];
  v28 = (char *)v42[1];
  for ( i = (char *)v42[0]; i != v28; i += 64 )
  {
    v30 = Csl::OfflineHive::SetValue(
            v6,
            *a3,
            *(const unsigned __int16 **)i,
            *((const unsigned __int8 **)i + 5),
            *((_DWORD *)i + 12) - (unsigned int)*((_QWORD *)i + 5),
            *((_DWORD *)i + 8));
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x515,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v30,
        lpcSubKeysa);
      if ( v27 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v33, v27, (v28 - v27) >> 6);
        operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
      }
      operator delete(v16, v32);
      if ( v10 )
        RegCloseKey(v10);
      return v31;
    }
    v6 = v46;
  }
  ftLastWriteTime = 0;
  v34 = RegQueryInfoKeyW(v10, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
  if ( v34 )
  {
    v22 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4F6,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
            (const char *)v34,
            lpcSubKeysb);
    if ( v22 < 0 )
    {
      v35 = 1306;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v22,
        lpcSubKeysb);
      if ( v27 == (_BYTE *)-1LL )
        goto LABEL_26;
      utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v36, v27, (v28 - v27) >> 6);
      v26 = v27;
      goto LABEL_25;
    }
  }
  v22 = Csl::OfflineHive::SetKeyLastWriteTime(v6, *a3, &ftLastWriteTime);
  if ( v22 < 0 )
  {
    v35 = 1308;
    goto LABEL_41;
  }
  if ( v27 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(v38, v27, (v28 - v27) >> 6);
    operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
  }
  operator delete(v16, v37);
  if ( v10 )
    RegCloseKey(v10);
  return 0;
}

```

## disassembly

```asm
0x180198e0c  mov     [rsp-8+arg_8], rdx
0x180198e11  push    rbp
0x180198e12  push    rbx
0x180198e13  push    rsi
0x180198e14  push    rdi
0x180198e15  push    r12
0x180198e17  push    r13
0x180198e19  push    r14
0x180198e1b  push    r15
0x180198e1d  lea     rbp, [rsp-1Fh]
0x180198e22  sub     rsp, 88h
0x180198e29  mov     rcx, [rcx]
0x180198e2c  lea     r9, [rbp+57h+hKey]
0x180198e30  mov     r13, r8
0x180198e33  mov     [rbp+57h+hKey], 0
0x180198e3b  mov     r12, rdx
0x180198e3e  mov     r8d, 20019h
0x180198e44  mov     rdx, [r13+0]
0x180198e48  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180198e4d  mov     ebx, eax
0x180198e4f  test    eax, eax
0x180198e51  jns     short loc_180198E87
0x180198e53  mov     rcx, [rbp+5Fh]; this
0x180198e57  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198e5e  mov     r9d, eax; char *
0x180198e61  mov     edx, 4EBh; void *
0x180198e66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198e6b  mov     rcx, [rbp+57h+hKey]; hKey
0x180198e6f  test    rcx, rcx
0x180198e72  jz      short loc_180198E80
0x180198e74  call    cs:__imp_RegCloseKey
0x180198e7b  nop     dword ptr [rax+rax+00h]
0x180198e80  mov     eax, ebx
0x180198e82  jmp     loc_18019922A
0x180198e87  mov     rbx, [rbp+57h+hKey]
0x180198e8b  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180198e8f  xor     r8d, r8d; pSecurityDescriptor
0x180198e92  mov     [rbp+57h+cbSecurityDescriptor], 0
0x180198e99  mov     rcx, rbx; hKey
0x180198e9c  lea     edx, [r8+4]; SecurityInformation
0x180198ea0  call    cs:__imp_RegGetKeySecurity
0x180198ea7  nop     dword ptr [rax+rax+00h]
0x180198eac  mov     esi, 80070000h
0x180198eb1  mov     r14d, 4CEh
0x180198eb7  mov     edi, eax
0x180198eb9  cmp     eax, 7Ah ; 'z'
0x180198ebc  jz      short loc_180198EDC
0x180198ebe  test    eax, eax
0x180198ec0  jz      short loc_180198EE1
0x180198ec2  mov     rcx, [rbp+5Fh]; this
0x180198ec6  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198ecd  mov     r9d, eax; char *
0x180198ed0  mov     edx, r14d; void *
0x180198ed3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180198ed8  mov     edi, eax
0x180198eda  jmp     short loc_180198EE1
0x180198edc  movzx   edi, ax
0x180198edf  or      edi, esi
0x180198ee1  cmp     edi, 8007007Ah
0x180198ee7  jz      short loc_180198EFB
0x180198ee9  test    edi, edi
0x180198eeb  jns     loc_180199214
0x180198ef1  mov     edx, 4F8h
0x180198ef6  jmp     loc_180199201
0x180198efb  mov     edi, [rbp+57h+cbSecurityDescriptor]
0x180198efe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180198f05  mov     ecx, edi; unsigned __int64
0x180198f07  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180198f0c  mov     r15, rax
0x180198f0f  test    rax, rax
0x180198f12  jz      loc_1801991F7
0x180198f18  mov     r8d, edi; Size
0x180198f1b  xor     edx, edx; Val
0x180198f1d  mov     rcx, rax; void *
0x180198f20  call    memset_0
0x180198f25  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180198f29  mov     r8, r15; pSecurityDescriptor
0x180198f2c  mov     edx, 4; SecurityInformation
0x180198f31  mov     rcx, rbx; hKey
0x180198f34  call    cs:__imp_RegGetKeySecurity
0x180198f3b  nop     dword ptr [rax+rax+00h]
0x180198f40  mov     edi, eax
0x180198f42  cmp     eax, 7Ah ; 'z'
0x180198f45  jz      short loc_180198F65
0x180198f47  test    eax, eax
0x180198f49  jz      short loc_180198F6A
0x180198f4b  mov     rcx, [rbp+5Fh]; this
0x180198f4f  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198f56  mov     r9d, eax; char *
0x180198f59  mov     edx, r14d; void *
0x180198f5c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180198f61  mov     edi, eax
0x180198f63  jmp     short loc_180198F6A
0x180198f65  movzx   edi, ax
0x180198f68  or      edi, esi
0x180198f6a  test    edi, edi
0x180198f6c  jns     short loc_180198F93
0x180198f6e  mov     edx, 503h; void *
0x180198f73  mov     rcx, [rbp+5Fh]; this
0x180198f77  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198f7e  mov     r9d, edi; char *
0x180198f81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198f86  mov     rcx, r15; void *
0x180198f89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198f8e  jmp     loc_180199214
0x180198f93  mov     rdx, [r13+0]; unsigned __int16 *
0x180198f97  mov     r9, r15; void *
0x180198f9a  mov     rcx, r12; this
0x180198f9d  call    ?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z; Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)
0x180198fa2  mov     edi, eax
0x180198fa4  test    eax, eax
0x180198fa6  jns     short loc_180198FAF
0x180198fa8  mov     edx, 508h
0x180198fad  jmp     short loc_180198F73
0x180198faf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180198fb7  lea     rdx, [rbp+57h+var_60]
0x180198fbb  lea     rcx, [rbp+57h+hKey]
0x180198fbf  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFFh
0x180198fc7  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180198fcc  call    ?EnumerateValues@RegistryKey@Csl@@QEBAJAEAV?$vector@URegistryValue@Csl@@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@@Z; Csl::RegistryKey::EnumerateValues(utl::vector<Csl::RegistryValue,utl::allocator<Csl::RegistryValue>> &)
0x180198fd1  mov     esi, eax
0x180198fd3  test    eax, eax
0x180198fd5  jns     short loc_18019903E
0x180198fd7  mov     rcx, [rbp+5Fh]; this
0x180198fdb  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198fe2  mov     r9d, eax; char *
0x180198fe5  mov     edx, 50Ch; void *
0x180198fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198fef  mov     rdi, [rbp+57h+var_60]
0x180198ff3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180198ff7  jz      short loc_18019901B
0x180198ff9  mov     r8, [rbp+57h+var_60+8]
0x180198ffd  mov     rdx, rdi
0x180199000  sub     r8, rdi
0x180199003  sar     r8, 6
0x180199007  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x18019900c  mov     rcx, rdi; void *
0x18019900f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180199016  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019901b  mov     rcx, r15; void *
0x18019901e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180199023  test    rbx, rbx
0x180199026  jz      short loc_180199037
0x180199028  mov     rcx, rbx; hKey
0x18019902b  call    cs:__imp_RegCloseKey
0x180199032  nop     dword ptr [rax+rax+00h]
0x180199037  mov     eax, esi
0x180199039  jmp     loc_18019922A
0x18019903e  mov     r14, [rbp+57h+var_60]
0x180199042  xor     ecx, ecx
0x180199044  mov     rdi, [rbp+57h+var_60+8]
0x180199048  mov     rsi, r14
0x18019904b  cmp     rsi, rdi
0x18019904e  jz      loc_1801990EE
0x180199054  mov     ecx, [rsi+30h]
0x180199057  mov     r9, [rsi+28h]; unsigned __int8 *
0x18019905b  mov     eax, [rsi+20h]
0x18019905e  sub     ecx, r9d
0x180199061  mov     r8, [rsi]; unsigned __int16 *
0x180199064  mov     rdx, [r13+0]; unsigned __int16 *
0x180199068  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; unsigned int
0x18019906c  mov     dword ptr [rsp+0C0h+lpcSubKeys], ecx; int
0x180199070  mov     rcx, r12; this
0x180199073  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x180199078  xor     ecx, ecx
0x18019907a  mov     r12d, eax
0x18019907d  test    eax, eax
0x18019907f  js      short loc_18019908B
0x180199081  mov     r12, [rbp+57h+arg_8]
0x180199085  add     rsi, 40h ; '@'
0x180199089  jmp     short loc_18019904B
0x18019908b  mov     rcx, [rbp+5Fh]; this
0x18019908f  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180199096  mov     r9d, r12d; char *
0x180199099  mov     edx, 515h; void *
0x18019909e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801990a3  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1801990a7  jz      short loc_1801990CA
0x1801990a9  sub     rdi, r14
0x1801990ac  mov     rdx, r14
0x1801990af  sar     rdi, 6
0x1801990b3  mov     r8, rdi
0x1801990b6  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x1801990bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801990c2  mov     rcx, r14; void *
0x1801990c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801990ca  mov     rcx, r15; void *
0x1801990cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801990d2  test    rbx, rbx
0x1801990d5  jz      short loc_1801990E6
0x1801990d7  mov     rcx, rbx; hKey
0x1801990da  call    cs:__imp_RegCloseKey
0x1801990e1  nop     dword ptr [rax+rax+00h]
0x1801990e6  mov     eax, r12d
0x1801990e9  jmp     loc_18019922A
0x1801990ee  lea     rax, [rbp+57h+ftLastWriteTime]
0x1801990f2  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rcx
0x1801990f6  mov     [rsp+0C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1801990fb  xor     r9d, r9d; lpReserved
0x1801990fe  mov     [rsp+0C0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x180199103  xor     r8d, r8d; lpcchClass
0x180199106  mov     [rsp+0C0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x18019910b  xor     edx, edx; lpClass
0x18019910d  mov     [rsp+0C0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180199112  mov     [rsp+0C0h+lpcValues], rcx; lpcValues
0x180199117  mov     [rsp+0C0h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x18019911c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x180199121  mov     [rsp+0C0h+lpcSubKeys], rcx; int
0x180199126  mov     rcx, rbx; hKey
0x180199129  call    cs:__imp_RegQueryInfoKeyW
0x180199130  nop     dword ptr [rax+rax+00h]
0x180199135  test    eax, eax
0x180199137  jz      short loc_180199193
0x180199139  mov     rcx, [rbp+5Fh]; this
0x18019913d  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180199144  mov     r9d, eax; char *
0x180199147  mov     edx, 4F6h; void *
0x18019914c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180199151  mov     esi, eax
0x180199153  test    eax, eax
0x180199155  jns     short loc_180199193
0x180199157  mov     edx, 51Ah; void *
0x18019915c  mov     rcx, [rbp+5Fh]; this
0x180199160  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180199167  mov     r9d, esi; char *
0x18019916a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019916f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180199173  jz      loc_18019901B
0x180199179  sub     rdi, r14
0x18019917c  mov     rdx, r14
0x18019917f  sar     rdi, 6
0x180199183  mov     r8, rdi
0x180199186  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x18019918b  mov     rcx, r14
0x18019918e  jmp     loc_18019900F
0x180199193  mov     rdx, [r13+0]; unsigned __int16 *
0x180199197  lea     r8, [rbp+57h+ftLastWriteTime]; struct _FILETIME *
0x18019919b  mov     rcx, r12; this
0x18019919e  call    ?SetKeyLastWriteTime@OfflineHive@Csl@@QEAAJPEBGAEBU_FILETIME@@@Z; Csl::OfflineHive::SetKeyLastWriteTime(ushort const *,_FILETIME const &)
0x1801991a3  mov     esi, eax
0x1801991a5  test    eax, eax
0x1801991a7  jns     short loc_1801991B0
0x1801991a9  mov     edx, 51Ch
0x1801991ae  jmp     short loc_18019915C
0x1801991b0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1801991b4  jz      short loc_1801991D7
0x1801991b6  sub     rdi, r14
0x1801991b9  mov     rdx, r14
0x1801991bc  sar     rdi, 6
0x1801991c0  mov     r8, rdi
0x1801991c3  call    ??$_RangeDestroyApc@V?$allocator@URegistryValue@Csl@@@utl@@@utl@@YAXAEAV?$allocator@URegistryValue@Csl@@@0@PEAURegistryValue@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::RegistryValue>>(utl::allocator<Csl::RegistryValue> &,Csl::RegistryValue *,unsigned __int64)
0x1801991c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801991cf  mov     rcx, r14; void *
0x1801991d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801991d7  mov     rcx, r15; void *
0x1801991da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801991df  test    rbx, rbx
0x1801991e2  jz      short loc_1801991F3
0x1801991e4  mov     rcx, rbx; hKey
0x1801991e7  call    cs:__imp_RegCloseKey
0x1801991ee  nop     dword ptr [rax+rax+00h]
0x1801991f3  xor     eax, eax
0x1801991f5  jmp     short loc_18019922A
0x1801991f7  mov     edi, 8007000Eh
0x1801991fc  mov     edx, 4FCh; void *
0x180199201  mov     rcx, [rbp+5Fh]; this
0x180199205  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019920c  mov     r9d, edi; char *
0x18019920f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199214  test    rbx, rbx
0x180199217  jz      short loc_180199228
0x180199219  mov     rcx, rbx; hKey
0x18019921c  call    cs:__imp_RegCloseKey
0x180199223  nop     dword ptr [rax+rax+00h]
0x180199228  mov     eax, edi
0x18019922a  add     rsp, 88h
0x180199231  pop     r15
0x180199233  pop     r14
0x180199235  pop     r13
0x180199237  pop     r12
0x180199239  pop     rdi
0x18019923a  pop     rsi
0x18019923b  pop     rbx
0x18019923c  pop     rbp
0x18019923d  retn
```
