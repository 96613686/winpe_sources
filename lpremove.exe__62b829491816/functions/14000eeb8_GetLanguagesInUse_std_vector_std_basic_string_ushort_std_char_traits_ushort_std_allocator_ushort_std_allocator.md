# GetLanguagesInUse(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x14000eeb8`
- end: `0x14000f234`
- name: `?GetLanguagesInUse@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `892`
- prototype: `LSTATUS __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006a50`
- `0x14000c36c`

## callees

- `0x140002190`
- `0x1400021b4`
- `0x14000316c`
- `0x1400042a4`
- `0x140005020`
- `0x14000513c`
- `0x140005a04`
- `0x14000d124`
- `0x14000dc4c`
- `0x14000df20`
- `0x14000e3b8`
- `0x14000eeb8`
- `0x14000f358`
- `0x14000f490`
- `0x14000f530`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000f20e`
- `ADVAPI32!RegCloseKey` at `0x14000f20e`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ef0d`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ef0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000efc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000efc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ef8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ef8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f012`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ef4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ef4d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14000ef79`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14000ef79`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x14000f054`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x14000f08d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x14000f054`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x14000f08d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f022`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f022`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x14000efa8`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x14000efa8`

## string_xrefs

- `0x14000eeff`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
LSTATUS __fastcall GetLanguagesInUse(_QWORD *a1)
{
  LSTATUS result; // eax
  DWORD v3; // ebx
  LSTATUS v4; // esi
  PCWSTR StringRawBuffer; // rax
  WCHAR *v6; // rbx
  _QWORD *v7; // rbx
  _QWORD *i; // rsi
  __int64 v9; // rax
  _QWORD *v10; // rbx
  _QWORD *j; // rsi
  _QWORD *k; // r14
  _QWORD *v13; // r14
  _QWORD *v14; // rbx
  _QWORD *v15; // rbx
  _QWORD *m; // rsi
  const wchar_t *v17; // rcx
  ULONG pcchLanguagesBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  ULONG pulNumLanguages; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  UINT32 length; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    v3 = 0;
    cchName = 260;
    do
    {
      v4 = RegEnumKeyExW(hKey, v3, Name, &cchName, 0, 0, 0, 0);
      if ( ((Name[0] - 83) & 0xFFDF) == 0 )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(Name, &Sid) )
        {
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          if ( (int)GetUserLanguagesForUser(Sid, 59, &string) >= 0 )
          {
            length = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
            VectorFromDelimitedString(&v25, StringRawBuffer, 59);
            std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(
              a1,
              a1[1],
              v25,
              (__int64)(*((_QWORD *)&v25 + 1) - v25) >> 5);
            std::vector<std::wstring>::~vector<std::wstring>(&v25);
          }
          _GetPreferredUILanguageForUser(Name, a1);
          WindowsDeleteString(string);
        }
        if ( Sid )
          LocalFree(Sid);
      }
      ++v3;
      cchName = 260;
    }
    while ( !v4 );
    pcchLanguagesBuffer = 0;
    pulNumLanguages = 0;
    if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    {
      v6 = (WCHAR *)operator new[](saturated_mul(pcchLanguagesBuffer, 2u));
      if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, v6, &pcchLanguagesBuffer) )
      {
        VectorFromDelimitedString(&v25, v6, 0);
        std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(
          a1,
          a1[1],
          v25,
          (__int64)(*((_QWORD *)&v25 + 1) - v25) >> 5);
        std::vector<std::wstring>::~vector<std::wstring>(&v25);
      }
      operator delete(v6);
    }
    v7 = (_QWORD *)a1[1];
    for ( i = (_QWORD *)*a1; i != v7; i += 4 )
    {
      v9 = LanguageTagAsMuiForm(&v25, i);
      std::wstring::operator=(i, v9);
      std::wstring::~wstring(&v25);
    }
    v10 = (_QWORD *)a1[1];
    for ( j = (_QWORD *)*a1; j != v10 && j[2]; j += 4 )
      ;
    if ( j != v10 )
    {
      for ( k = j + 4; k != v10; k += 4 )
      {
        if ( k[2] )
        {
          std::wstring::operator=(j, k);
          j += 4;
        }
      }
    }
    v13 = (_QWORD *)a1[1];
    if ( j != v13 )
    {
      v14 = j;
      do
      {
        std::wstring::~wstring(v14);
        v14 += 4;
      }
      while ( v14 != v13 );
      a1[1] = j;
    }
    RemoveDuplicates<std::vector<std::wstring>>(a1);
    v15 = (_QWORD *)a1[1];
    for ( m = (_QWORD *)*a1; m != v15; m += 4 )
    {
      v17 = m[3] <= 7u ? (const wchar_t *)m : (const wchar_t *)*m;
      if ( m[2] == 5 && !wmemcmp(v17, L"en-GB", 5u) )
        break;
    }
    if ( m != (_QWORD *)a1[1] )
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v25, L"en-US", 5);
      std::vector<std::wstring>::insert(a1, &Sid, a1[1], &v25);
      std::wstring::~wstring(&v25);
    }
    result = RemoveDuplicates<std::vector<std::wstring>>(a1);
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x14000eeb8  push    rbp
0x14000eeba  push    rbx
0x14000eebb  push    rsi
0x14000eebc  push    rdi
0x14000eebd  push    r14
0x14000eebf  push    r15
0x14000eec1  lea     rbp, [rsp-1B8h]
0x14000eec9  sub     rsp, 2B8h
0x14000eed0  mov     rax, cs:__security_cookie
0x14000eed7  xor     rax, rsp
0x14000eeda  mov     [rbp+1E0h+var_40], rax
0x14000eee1  mov     rdi, rcx
0x14000eee4  xor     r15d, r15d
0x14000eee7  mov     [rsp+2E0h+hKey], r15
0x14000eeec  lea     rax, [rsp+2E0h+hKey]
0x14000eef1  mov     [rsp+2E0h+phkResult], rax; phkResult
0x14000eef6  mov     r9d, 20019h; samDesired
0x14000eefc  xor     r8d, r8d; ulOptions
0x14000eeff  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000ef06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ef0d  call    cs:__imp_RegOpenKeyExW
0x14000ef13  test    eax, eax
0x14000ef15  jnz     loc_14000F204
0x14000ef1b  mov     ebx, r15d
0x14000ef1e  mov     r14d, 104h
0x14000ef24  mov     [rsp+2E0h+cchName], r14d
0x14000ef29  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14000ef2e  mov     [rsp+2E0h+lpcchClass], r15; lpcchClass
0x14000ef33  mov     [rsp+2E0h+lpClass], r15; lpClass
0x14000ef38  mov     [rsp+2E0h+phkResult], r15; lpReserved
0x14000ef3d  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x14000ef42  lea     r8, [rbp+1E0h+Name]; lpName
0x14000ef46  mov     edx, ebx; dwIndex
0x14000ef48  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14000ef4d  call    cs:__imp_RegEnumKeyExW
0x14000ef53  mov     esi, eax
0x14000ef55  movzx   ecx, [rbp+1E0h+Name]
0x14000ef59  sub     cx, 53h ; 'S'
0x14000ef5d  mov     eax, 0FFDFh
0x14000ef62  test    ax, cx
0x14000ef65  jnz     loc_14000F028
0x14000ef6b  mov     [rsp+2E0h+Sid], r15
0x14000ef70  lea     rdx, [rsp+2E0h+Sid]; Sid
0x14000ef75  lea     rcx, [rbp+1E0h+Name]; StringSid
0x14000ef79  call    cs:__imp_ConvertStringSidToSidW
0x14000ef7f  test    eax, eax
0x14000ef81  jz      loc_14000F018
0x14000ef87  mov     [rsp+2E0h+string], r15
0x14000ef8c  xor     ecx, ecx; string
0x14000ef8e  call    cs:__imp_WindowsDeleteString
0x14000ef94  mov     [rsp+2E0h+string], r15
0x14000ef99  mov     edx, 3Bh ; ';'
0x14000ef9e  lea     r8, [rsp+2E0h+string]
0x14000efa3  mov     rcx, [rsp+2E0h+Sid]
0x14000efa8  call    cs:__imp_GetUserLanguagesForUser
0x14000efae  test    eax, eax
0x14000efb0  js      short loc_14000F001
0x14000efb2  mov     [rsp+2E0h+length], r15d
0x14000efb7  lea     rdx, [rsp+2E0h+length]; length
0x14000efbc  mov     rcx, [rsp+2E0h+string]; string
0x14000efc1  call    cs:__imp_WindowsGetStringRawBuffer
0x14000efc7  mov     r8d, 3Bh ; ';'
0x14000efcd  mov     rdx, rax
0x14000efd0  lea     rcx, [rsp+2E0h+var_270]
0x14000efd5  call    ?VectorFromDelimitedString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; VectorFromDelimitedString(ushort const *,ushort)
0x14000efda  mov     r9, qword ptr [rsp+2E0h+var_270+8]
0x14000efdf  mov     r8, qword ptr [rsp+2E0h+var_270]
0x14000efe4  sub     r9, r8
0x14000efe7  sar     r9, 5
0x14000efeb  mov     rdx, [rdi+8]
0x14000efef  mov     rcx, rdi
0x14000eff2  call    ??$_Insert_counted_range@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring *,unsigned __int64)
0x14000eff7  lea     rcx, [rsp+2E0h+var_270]
0x14000effc  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000f001  mov     rdx, rdi
0x14000f004  lea     rcx, [rbp+1E0h+Name]
0x14000f008  call    ?_GetPreferredUILanguageForUser@@YAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; _GetPreferredUILanguageForUser(ushort const *,std::vector<std::wstring> &)
0x14000f00d  mov     rcx, [rsp+2E0h+string]; string
0x14000f012  call    cs:__imp_WindowsDeleteString
0x14000f018  mov     rcx, [rsp+2E0h+Sid]; hMem
0x14000f01d  test    rcx, rcx
0x14000f020  jz      short loc_14000F028
0x14000f022  call    cs:__imp_LocalFree
0x14000f028  inc     ebx
0x14000f02a  mov     [rsp+2E0h+cchName], r14d
0x14000f02f  test    esi, esi
0x14000f031  jz      loc_14000EF29
0x14000f037  mov     [rsp+2E0h+pcchLanguagesBuffer], r15d
0x14000f03c  mov     [rsp+2E0h+pulNumLanguages], r15d
0x14000f041  lea     r9, [rsp+2E0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x14000f046  xor     r8d, r8d; pwszLanguagesBuffer
0x14000f049  lea     rdx, [rsp+2E0h+pulNumLanguages]; pulNumLanguages
0x14000f04e  lea     esi, [r8+8]
0x14000f052  mov     ecx, esi; dwFlags
0x14000f054  call    cs:__imp_GetSystemPreferredUILanguages
0x14000f05a  test    eax, eax
0x14000f05c  jz      short loc_14000F0D6
0x14000f05e  mov     ecx, [rsp+2E0h+pcchLanguagesBuffer]
0x14000f062  lea     eax, [rsi-6]
0x14000f065  mul     rcx
0x14000f068  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000f06f  cmovb   rax, rdx
0x14000f073  mov     rcx, rax; unsigned __int64
0x14000f076  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000f07b  mov     rbx, rax
0x14000f07e  lea     r9, [rsp+2E0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x14000f083  mov     r8, rax; pwszLanguagesBuffer
0x14000f086  lea     rdx, [rsp+2E0h+pulNumLanguages]; pulNumLanguages
0x14000f08b  mov     ecx, esi; dwFlags
0x14000f08d  call    cs:__imp_GetSystemPreferredUILanguages
0x14000f093  test    eax, eax
0x14000f095  jz      short loc_14000F0CE
0x14000f097  xor     r8d, r8d
0x14000f09a  mov     rdx, rbx
0x14000f09d  lea     rcx, [rsp+2E0h+var_270]
0x14000f0a2  call    ?VectorFromDelimitedString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; VectorFromDelimitedString(ushort const *,ushort)
0x14000f0a7  mov     r9, qword ptr [rsp+2E0h+var_270+8]
0x14000f0ac  mov     r8, qword ptr [rsp+2E0h+var_270]
0x14000f0b1  sub     r9, r8
0x14000f0b4  sar     r9, 5
0x14000f0b8  mov     rdx, [rdi+8]
0x14000f0bc  mov     rcx, rdi
0x14000f0bf  call    ??$_Insert_counted_range@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::vector<std::wstring>::_Insert_counted_range<std::wstring *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring *,unsigned __int64)
0x14000f0c4  lea     rcx, [rsp+2E0h+var_270]
0x14000f0c9  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000f0ce  mov     rcx, rbx; Block
0x14000f0d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f0d6  mov     rbx, [rdi+8]
0x14000f0da  mov     rsi, [rdi]
0x14000f0dd  jmp     short loc_14000F105
0x14000f0df  mov     rdx, rsi
0x14000f0e2  lea     rcx, [rsp+2E0h+var_270]
0x14000f0e7  call    ?LanguageTagAsMuiForm@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; LanguageTagAsMuiForm(std::wstring const &)
0x14000f0ec  mov     rdx, rax
0x14000f0ef  mov     rcx, rsi
0x14000f0f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000f0f7  lea     rcx, [rsp+2E0h+var_270]
0x14000f0fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f101  add     rsi, 20h ; ' '
0x14000f105  cmp     rsi, rbx
0x14000f108  jnz     short loc_14000F0DF
0x14000f10a  mov     rbx, [rdi+8]
0x14000f10e  mov     rsi, [rdi]
0x14000f111  jmp     short loc_14000F11D
0x14000f113  cmp     [rsi+10h], r15
0x14000f117  jz      short loc_14000F122
0x14000f119  add     rsi, 20h ; ' '
0x14000f11d  cmp     rsi, rbx
0x14000f120  jnz     short loc_14000F113
0x14000f122  cmp     rsi, rbx
0x14000f125  jz      short loc_14000F14B
0x14000f127  lea     r14, [rsi+20h]
0x14000f12b  jmp     short loc_14000F146
0x14000f12d  cmp     [r14+10h], r15
0x14000f131  jz      short loc_14000F142
0x14000f133  mov     rdx, r14
0x14000f136  mov     rcx, rsi
0x14000f139  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000f13e  add     rsi, 20h ; ' '
0x14000f142  add     r14, 20h ; ' '
0x14000f146  cmp     r14, rbx
0x14000f149  jnz     short loc_14000F12D
0x14000f14b  mov     r14, [rdi+8]
0x14000f14f  cmp     rsi, r14
0x14000f152  jz      short loc_14000F16C
0x14000f154  mov     rbx, rsi
0x14000f157  mov     rcx, rbx
0x14000f15a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f15f  add     rbx, 20h ; ' '
0x14000f163  cmp     rbx, r14
0x14000f166  jnz     short loc_14000F157
0x14000f168  mov     [rdi+8], rsi
0x14000f16c  mov     rcx, rdi
0x14000f16f  call    ??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RemoveDuplicates<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x14000f174  mov     rbx, [rdi+8]
0x14000f178  mov     rsi, [rdi]
0x14000f17b  jmp     short loc_14000F1AA
0x14000f17d  mov     r8, [rsi+10h]; N
0x14000f181  cmp     qword ptr [rsi+18h], 7
0x14000f186  jbe     short loc_14000F18D
0x14000f188  mov     rcx, [rsi]
0x14000f18b  jmp     short loc_14000F190
0x14000f18d  mov     rcx, rsi; S1
0x14000f190  cmp     r8, 5
0x14000f194  jnz     short loc_14000F1A6
0x14000f196  lea     rdx, aEnGb; "en-GB"
0x14000f19d  call    wmemcmp
0x14000f1a2  test    eax, eax
0x14000f1a4  jz      short loc_14000F1AF
0x14000f1a6  add     rsi, 20h ; ' '
0x14000f1aa  cmp     rsi, rbx
0x14000f1ad  jnz     short loc_14000F17D
0x14000f1af  cmp     rsi, [rdi+8]
0x14000f1b3  jz      short loc_14000F1FC
0x14000f1b5  xorps   xmm0, xmm0
0x14000f1b8  movups  [rsp+2E0h+var_270], xmm0
0x14000f1bd  mov     [rbp+1E0h+var_260], r15
0x14000f1c1  mov     [rbp+1E0h+var_258], r15
0x14000f1c5  mov     r8d, 5
0x14000f1cb  lea     rdx, aEnUs; "en-US"
0x14000f1d2  lea     rcx, [rsp+2E0h+var_270]
0x14000f1d7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000f1dc  lea     r9, [rsp+2E0h+var_270]
0x14000f1e1  mov     r8, [rdi+8]
0x14000f1e5  lea     rdx, [rsp+2E0h+Sid]
0x14000f1ea  mov     rcx, rdi
0x14000f1ed  call    ?insert@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring &&)
0x14000f1f2  lea     rcx, [rsp+2E0h+var_270]
0x14000f1f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f1fc  mov     rcx, rdi
0x14000f1ff  call    ??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RemoveDuplicates<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x14000f204  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14000f209  test    rcx, rcx
0x14000f20c  jz      short loc_14000F215
0x14000f20e  call    cs:__imp_RegCloseKey
0x14000f214  nop
0x14000f215  mov     rcx, [rbp+1E0h+var_40]
0x14000f21c  xor     rcx, rsp; StackCookie
0x14000f21f  call    __security_check_cookie
0x14000f224  add     rsp, 2B8h
0x14000f22b  pop     r15
0x14000f22d  pop     r14
0x14000f22f  pop     rdi
0x14000f230  pop     rsi
0x14000f231  pop     rbx
0x14000f232  pop     rbp
0x14000f233  retn
```
