# GetProfileSids(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800bd360`
- end: `0x1800bd5d9`
- name: `?GetProfileSids@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bbdd0`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180014f2c`
- `0x180016748`
- `0x1800b98fc`
- `0x1800bd360`
- `0x180184b58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bd4f2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bd4f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd5a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd5a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bd49d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bd49d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bd42f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bd42f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall GetProfileSids(__int64 a1)
{
  char **v2; // rsi
  char **v3; // rdi
  LSTATUS result; // eax
  DWORD v5; // edi
  __m128i si128; // xmm6
  unsigned __int64 v7; // r8
  _OWORD *v8; // rdx
  DWORD cSubKeys[2]; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+78h] [rbp-90h] BYREF
  DWORD cbMaxValueLen; // [rsp+7Ch] [rbp-8Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+80h] [rbp-88h] BYREF
  DWORD cValues; // [rsp+84h] [rbp-84h] BYREF
  DWORD cbMaxClassLen; // [rsp+88h] [rbp-80h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+8Ch] [rbp-7Ch] BYREF
  DWORD cchClass; // [rsp+90h] [rbp-78h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp-70h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v20; // [rsp+B0h] [rbp-58h]
  WCHAR Name[256]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR Class; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v23[526]; // [rsp+2CAh] [rbp+1C2h] BYREF

  hKey = 0;
  cSubKeys[0] = 0;
  Class = 0;
  memset_0(v23, 0, 0x206u);
  cchClass = 260;
  cSubKeys[1] = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  v2 = *(char ***)(a1 + 8);
  v3 = *(char ***)a1;
  if ( *(char ***)a1 != v2 )
  {
    do
    {
      std::wstring::~wstring(v3);
      v3 += 4;
    }
    while ( v3 != v2 );
    *(_QWORD *)(a1 + 8) = *(_QWORD *)a1;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &hKey) >= 0 )
  {
    result = RegQueryInfoKeyW(
               hKey,
               &Class,
               &cchClass,
               0,
               &cSubKeys[1],
               &cbMaxSubKeyLen,
               &cbMaxClassLen,
               &cValues,
               &cbMaxValueNameLen,
               &cbMaxValueLen,
               &cbSecurityDescriptor,
               &ftLastWriteTime);
    if ( result < 0 )
      return result;
    if ( cSubKeys[1] )
    {
      v5 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        cSubKeys[0] = 255;
        if ( RegEnumKeyExW(hKey, v5, Name, cSubKeys, 0, 0, 0, &ftLastWriteTime) >= 0
          && cSubKeys[0] > 9
          && wcsncmp_0(Name, L"S-1-5-99", 8u) )
        {
          v19 = 0;
          v20 = 0;
          v7 = -1;
          do
            ++v7;
          while ( Name[v7] );
          std::wstring::_Construct<1,unsigned short const *>((char **)&v19, Name, v7);
          v8 = *(_OWORD **)(a1 + 8);
          if ( v8 == *(_OWORD **)(a1 + 16) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, v8, &v19);
          }
          else
          {
            *v8 = v19;
            v8[1] = v20;
            v20 = si128;
            LOWORD(v19) = 0;
            *(_QWORD *)(a1 + 8) += 32LL;
          }
          std::wstring::~wstring((char **)&v19);
        }
        ++v5;
      }
      while ( v5 < cSubKeys[1] );
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bd360  mov     rax, rsp
0x1800bd363  mov     [rax+10h], rbx
0x1800bd367  mov     [rax+18h], rsi
0x1800bd36b  push    rbp
0x1800bd36c  push    rdi
0x1800bd36d  push    r14
0x1800bd36f  lea     rbp, [rax-408h]
0x1800bd376  sub     rsp, 4F0h
0x1800bd37d  movaps  xmmword ptr [rax-28h], xmm6
0x1800bd381  mov     rax, cs:__security_cookie
0x1800bd388  xor     rax, rsp
0x1800bd38b  mov     [rbp+400h+var_30], rax
0x1800bd392  mov     rbx, rcx
0x1800bd395  xor     r14d, r14d
0x1800bd398  mov     [rsp+500h+hKey], r14
0x1800bd39d  mov     [rsp+500h+cSubKeys], r14d
0x1800bd3a2  mov     [rbp+400h+Class], r14w
0x1800bd3aa  xor     edx, edx; Val
0x1800bd3ac  mov     r8d, 206h; Size
0x1800bd3b2  lea     rcx, [rbp+400h+var_23E]; void *
0x1800bd3b9  call    memset_0
0x1800bd3be  mov     [rbp+400h+cchClass], 104h
0x1800bd3c5  mov     [rsp+500h+cSubKeys+4], r14d
0x1800bd3ca  mov     [rbp+400h+cbMaxSubKeyLen], r14d
0x1800bd3ce  mov     [rbp+400h+cbMaxClassLen], r14d
0x1800bd3d2  mov     [rsp+500h+cValues], r14d
0x1800bd3d7  mov     [rsp+500h+cbMaxValueNameLen], r14d
0x1800bd3dc  mov     [rsp+500h+cbMaxValueLen], r14d
0x1800bd3e1  mov     [rsp+500h+cbSecurityDescriptor], r14d
0x1800bd3e6  mov     qword ptr [rbp+400h+ftLastWriteTime.dwLowDateTime], r14
0x1800bd3ea  mov     rsi, [rbx+8]
0x1800bd3ee  mov     rdi, [rbx]
0x1800bd3f1  cmp     rdi, rsi
0x1800bd3f4  jz      short loc_1800BD40E
0x1800bd3f6  mov     rcx, rdi
0x1800bd3f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bd3fe  add     rdi, 20h ; ' '
0x1800bd402  cmp     rdi, rsi
0x1800bd405  jnz     short loc_1800BD3F6
0x1800bd407  mov     rax, [rbx]
0x1800bd40a  mov     [rbx+8], rax
0x1800bd40e  lea     rax, [rsp+500h+hKey]
0x1800bd413  mov     [rsp+500h+phkResult], rax; phkResult
0x1800bd418  mov     r9d, 20019h; samDesired
0x1800bd41e  xor     r8d, r8d; ulOptions
0x1800bd421  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bd428  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bd42f  call    cs:__imp_RegOpenKeyExW
0x1800bd435  test    eax, eax
0x1800bd437  js      loc_1800BD5AB
0x1800bd43d  lea     rax, [rbp+400h+ftLastWriteTime]
0x1800bd441  mov     [rsp+500h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800bd446  lea     rax, [rsp+500h+cbSecurityDescriptor]
0x1800bd44b  mov     [rsp+500h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800bd450  lea     rax, [rsp+500h+cbMaxValueLen]
0x1800bd455  mov     [rsp+500h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800bd45a  lea     rax, [rsp+500h+cbMaxValueNameLen]
0x1800bd45f  mov     [rsp+500h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800bd464  lea     rax, [rsp+500h+cValues]
0x1800bd469  mov     [rsp+500h+lpcValues], rax; lpcValues
0x1800bd46e  lea     rax, [rbp+400h+cbMaxClassLen]
0x1800bd472  mov     [rsp+500h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800bd477  lea     rax, [rbp+400h+cbMaxSubKeyLen]
0x1800bd47b  mov     [rsp+500h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800bd480  lea     rax, [rsp+500h+cSubKeys+4]
0x1800bd485  mov     [rsp+500h+phkResult], rax; lpcSubKeys
0x1800bd48a  xor     r9d, r9d; lpReserved
0x1800bd48d  lea     r8, [rbp+400h+cchClass]; lpcchClass
0x1800bd491  lea     rdx, [rbp+400h+Class]; lpClass
0x1800bd498  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd49d  call    cs:__imp_RegQueryInfoKeyW
0x1800bd4a3  test    eax, eax
0x1800bd4a5  js      loc_1800BD5AD
0x1800bd4ab  mov     eax, [rsp+500h+cSubKeys+4]
0x1800bd4af  test    eax, eax
0x1800bd4b1  jz      loc_1800BD5A0
0x1800bd4b7  mov     edi, r14d
0x1800bd4ba  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800bd4c2  mov     [rsp+500h+cSubKeys], 0FFh
0x1800bd4ca  lea     rax, [rbp+400h+ftLastWriteTime]
0x1800bd4ce  mov     [rsp+500h+lpcValues], rax; lpftLastWriteTime
0x1800bd4d3  mov     [rsp+500h+lpcbMaxClassLen], r14; lpcchClass
0x1800bd4d8  mov     [rsp+500h+lpcbMaxSubKeyLen], r14; lpClass
0x1800bd4dd  mov     [rsp+500h+phkResult], r14; lpReserved
0x1800bd4e2  lea     r9, [rsp+500h+cSubKeys]; lpcchName
0x1800bd4e7  lea     r8, [rbp+400h+Name]; lpName
0x1800bd4eb  mov     edx, edi; dwIndex
0x1800bd4ed  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd4f2  call    cs:__imp_RegEnumKeyExW
0x1800bd4f8  test    eax, eax
0x1800bd4fa  js      loc_1800BD594
0x1800bd500  cmp     [rsp+500h+cSubKeys], 9
0x1800bd505  jbe     loc_1800BD594
0x1800bd50b  mov     r8d, 8; MaxCount
0x1800bd511  lea     rdx, aS1599; "S-1-5-99"
0x1800bd518  lea     rcx, [rbp+400h+Name]; String1
0x1800bd51c  call    wcsncmp_0
0x1800bd521  test    eax, eax
0x1800bd523  jz      short loc_1800BD594
0x1800bd525  xorps   xmm0, xmm0
0x1800bd528  movups  [rbp+400h+var_468], xmm0
0x1800bd52c  xorps   xmm1, xmm1
0x1800bd52f  movdqu  [rbp+400h+var_458], xmm1
0x1800bd534  lea     rax, [rbp+400h+Name]
0x1800bd538  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bd53c  inc     r8
0x1800bd53f  cmp     [rax+r8*2], r14w
0x1800bd544  jnz     short loc_1800BD53C
0x1800bd546  lea     rdx, [rbp+400h+Name]
0x1800bd54a  lea     rcx, [rbp+400h+var_468]
0x1800bd54e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bd553  nop
0x1800bd554  mov     rdx, [rbx+8]
0x1800bd558  cmp     rdx, [rbx+10h]
0x1800bd55c  jz      short loc_1800BD57E
0x1800bd55e  movups  xmm0, [rbp+400h+var_468]
0x1800bd562  movups  xmmword ptr [rdx], xmm0
0x1800bd565  movups  xmm1, [rbp+400h+var_458]
0x1800bd569  movups  xmmword ptr [rdx+10h], xmm1
0x1800bd56d  movdqu  [rbp+400h+var_458], xmm6
0x1800bd572  mov     word ptr [rbp+400h+var_468], r14w
0x1800bd577  add     qword ptr [rbx+8], 20h ; ' '
0x1800bd57c  jmp     short loc_1800BD58B
0x1800bd57e  lea     r8, [rbp+400h+var_468]
0x1800bd582  mov     rcx, rbx
0x1800bd585  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800bd58a  nop
0x1800bd58b  lea     rcx, [rbp+400h+var_468]
0x1800bd58f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bd594  inc     edi
0x1800bd596  cmp     edi, [rsp+500h+cSubKeys+4]
0x1800bd59a  jb      loc_1800BD4C2
0x1800bd5a0  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd5a5  call    cs:__imp_RegCloseKey
0x1800bd5ab  xor     eax, eax
0x1800bd5ad  mov     rcx, [rbp+400h+var_30]
0x1800bd5b4  xor     rcx, rsp; StackCookie
0x1800bd5b7  call    __security_check_cookie
0x1800bd5bc  lea     r11, [rsp+500h+var_10]
0x1800bd5c4  mov     rbx, [r11+28h]
0x1800bd5c8  mov     rsi, [r11+30h]
0x1800bd5cc  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bd5d1  mov     rsp, r11
0x1800bd5d4  pop     r14
0x1800bd5d6  pop     rdi
0x1800bd5d7  pop     rbp
0x1800bd5d8  retn
```
