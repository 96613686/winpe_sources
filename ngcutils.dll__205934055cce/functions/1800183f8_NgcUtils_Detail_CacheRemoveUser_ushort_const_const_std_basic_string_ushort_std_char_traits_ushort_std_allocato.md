# NgcUtils::Detail::CacheRemoveUser(ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800183f8`
- end: `0x1800185c9`
- name: `?CacheRemoveUser@Detail@NgcUtils@@YAJQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(void *, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017718`

## callees

- `0x180003080`
- `0x18000a5b4`
- `0x18000c95c`
- `0x18000ce74`
- `0x180013dc8`
- `0x180014e34`
- `0x180015ca4`
- `0x1800183f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001846a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018552`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800185a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001846a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018552`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800185a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001850c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001850c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001856d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001856d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018587`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018587`

## string_xrefs

- `0x18001844f`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001851e`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::Detail::CacheRemoveUser(void *a1, const WCHAR *lpSubKey)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  HLOCAL v7; // rbx
  __int64 v8; // r8
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // edi
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  int phkResult; // [rsp+20h] [rbp-50h]
  unsigned int phkResulta; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpSubKeya[2]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  hMem = 0;
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        &hMem);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x522,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResult);
    if ( hMem )
      LocalFree(hMem);
    return v5;
  }
  v7 = hMem;
  *(_OWORD *)lpSubKeya = 0;
  v22 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)hMem + v8) );
  std::wstring::_Construct<1,unsigned short const *>(lpSubKeya, hMem, v8);
  std::wstring::append(lpSubKeya, (void *)L"\\");
  std::wstring::append(lpSubKeya, a1);
  std::wstring::append(lpSubKeya, (void *)L"\\");
  std::wstring::append(lpSubKeya, L"UserNames");
  hKey = 0;
  v9 = (const WCHAR *)lpSubKeya;
  if ( *((_QWORD *)&v22 + 1) > 7u )
    v9 = lpSubKeya[0];
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x2001Fu, &hKey);
  if ( v10 )
  {
    v11 = 1329;
LABEL_11:
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
            (const char *)v10,
            phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring(lpSubKeya, v12, v14);
    if ( v7 )
      LocalFree(v7);
    return v13;
  }
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    lpSubKey = *(const WCHAR **)lpSubKey;
  v10 = RegDeleteTreeW(hKey, lpSubKey);
  if ( v10 )
  {
    v11 = 1334;
    goto LABEL_11;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKeya, v15, v16);
  if ( v7 )
    LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x1800183f8  mov     [rsp-18h+arg_10], rbx
0x1800183fd  mov     [rsp-18h+arg_18], rsi
0x180018402  push    rbp
0x180018403  push    rdi
0x180018404  push    r14
0x180018406  mov     rbp, rsp
0x180018409  sub     rsp, 70h
0x18001840d  mov     rax, cs:__security_cookie
0x180018414  xor     rax, rsp
0x180018417  mov     [rbp+var_10], rax
0x18001841b  mov     rdi, rdx
0x18001841e  mov     rsi, rcx
0x180018421  xor     r14d, r14d
0x180018424  mov     [rbp+hMem], r14
0x180018428  lea     r9, [rbp+hMem]; unsigned __int16 *
0x18001842c  xor     r8d, r8d; unsigned __int16 *
0x18001842f  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180018436  lea     rcx, aNgccredprov; "NgcCredprov"
0x18001843d  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180018442  mov     ebx, eax
0x180018444  test    eax, eax
0x180018446  jns     short loc_180018477
0x180018448  mov     rcx, [rbp+18h]; this
0x18001844c  mov     r9d, eax; char *
0x18001844f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018456  mov     edx, 522h; void *
0x18001845b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018460  nop
0x180018461  mov     rcx, [rbp+hMem]; hMem
0x180018465  test    rcx, rcx
0x180018468  jz      short loc_180018470
0x18001846a  call    cs:__imp_LocalFree
0x180018470  mov     eax, ebx
0x180018472  jmp     loc_1800185A8
0x180018477  mov     rbx, [rbp+hMem]
0x18001847b  xorps   xmm0, xmm0
0x18001847e  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180018482  xorps   xmm1, xmm1
0x180018485  movdqu  [rbp+var_20], xmm1
0x18001848a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001848e  inc     r8
0x180018491  cmp     [rbx+r8*2], r14w
0x180018496  jnz     short loc_18001848E
0x180018498  mov     rdx, rbx
0x18001849b  lea     rcx, [rbp+lpSubKey]
0x18001849f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800184a4  nop
0x1800184a5  lea     rdx, asc_180064548; "\\"
0x1800184ac  lea     rcx, [rbp+lpSubKey]; Src
0x1800184b0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800184b5  mov     rdx, rsi; void *
0x1800184b8  lea     rcx, [rbp+lpSubKey]; Src
0x1800184bc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800184c1  lea     rdx, asc_180064548; "\\"
0x1800184c8  lea     rcx, [rbp+lpSubKey]; Src
0x1800184cc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800184d1  lea     rdx, aUsernames; "UserNames"
0x1800184d8  lea     rcx, [rbp+lpSubKey]; Src
0x1800184dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800184e1  mov     [rbp+hKey], r14
0x1800184e5  lea     rdx, [rbp+lpSubKey]
0x1800184e9  cmp     qword ptr [rbp+var_20+8], 7
0x1800184ee  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x1800184f3  lea     rax, [rbp+hKey]
0x1800184f7  mov     qword ptr [rsp+70h+phkResult], rax; unsigned int
0x1800184fc  mov     r9d, 2001Fh; samDesired
0x180018502  xor     r8d, r8d; ulOptions
0x180018505  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001850c  call    cs:__imp_RegOpenKeyExW
0x180018512  test    eax, eax
0x180018514  jz      short loc_18001855C
0x180018516  mov     edx, 531h; void *
0x18001851b  mov     r9d, eax; char *
0x18001851e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018525  mov     rcx, [rbp+18h]; this
0x180018529  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001852e  mov     rcx, [rbp+hKey]; hKey
0x180018532  test    rcx, rcx
0x180018535  mov     edi, eax
0x180018537  jz      short loc_180018540
0x180018539  call    cs:__imp_RegCloseKey
0x18001853f  nop
0x180018540  lea     rcx, [rbp+lpSubKey]
0x180018544  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018549  nop
0x18001854a  test    rbx, rbx
0x18001854d  jz      short loc_180018558
0x18001854f  mov     rcx, rbx; hMem
0x180018552  call    cs:__imp_LocalFree
0x180018558  mov     eax, edi
0x18001855a  jmp     short loc_1800185A8
0x18001855c  cmp     qword ptr [rdi+18h], 7
0x180018561  jbe     short loc_180018566
0x180018563  mov     rdi, [rdi]
0x180018566  mov     rdx, rdi; lpSubKey
0x180018569  mov     rcx, [rbp+hKey]; hKey
0x18001856d  call    cs:__imp_RegDeleteTreeW
0x180018573  test    eax, eax
0x180018575  jz      short loc_18001857E
0x180018577  mov     edx, 536h
0x18001857c  jmp     short loc_18001851B
0x18001857e  mov     rcx, [rbp+hKey]; hKey
0x180018582  test    rcx, rcx
0x180018585  jz      short loc_18001858E
0x180018587  call    cs:__imp_RegCloseKey
0x18001858d  nop
0x18001858e  lea     rcx, [rbp+lpSubKey]
0x180018592  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018597  nop
0x180018598  test    rbx, rbx
0x18001859b  jz      short loc_1800185A6
0x18001859d  mov     rcx, rbx; hMem
0x1800185a0  call    cs:__imp_LocalFree
0x1800185a6  xor     eax, eax
0x1800185a8  mov     rcx, [rbp+var_10]
0x1800185ac  xor     rcx, rsp; StackCookie
0x1800185af  call    __security_check_cookie
0x1800185b4  lea     r11, [rsp+70h+var_s0]
0x1800185b9  mov     rbx, [r11+30h]
0x1800185bd  mov     rsi, [r11+38h]
0x1800185c1  mov     rsp, r11
0x1800185c4  pop     r14
0x1800185c6  pop     rdi
0x1800185c7  pop     rbp
0x1800185c8  retn
```
