# GetProfileSids2(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800bd088`
- end: `0x1800bd35a`
- name: `?GetProfileSids2@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bbdd0`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180014f2c`
- `0x180016748`
- `0x1800a5e64`
- `0x1800b98fc`
- `0x1800bd088`
- `0x180184b58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bd250`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bd250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd308`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bd1f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bd1f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bd157`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bd157`

## string_xrefs

- `0x1800bd166`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetProfileSids2(__int64 *a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  DWORD v8; // esi
  __m128i si128; // xmm6
  LSTATUS v10; // eax
  __int64 v11; // r8
  _OWORD *v12; // rdx
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
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
  __int128 v24; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v25; // [rsp+B0h] [rbp-58h]
  WCHAR Name[256]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR Class; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v28[526]; // [rsp+2CAh] [rbp+1C2h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+510h] [rbp+408h]

  cSubKeys[0] = 0;
  Class = 0;
  memset_0(v28, 0, 0x206u);
  cchClass = 260;
  cSubKeys[1] = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  v2 = a1[1];
  v3 = *a1;
  if ( *a1 != v2 )
  {
    do
    {
      std::wstring::~wstring(v3);
      v3 += 32;
    }
    while ( v3 != v2 );
    a1[1] = *a1;
  }
  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &hKey);
  if ( v4 )
  {
    v5 = 512;
LABEL_6:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
           (const char *)v4,
           phkResult);
LABEL_7:
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v4 = RegQueryInfoKeyW(
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
  if ( v4 )
  {
    v5 = 526;
    goto LABEL_6;
  }
  if ( cSubKeys[1] )
  {
    v8 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      cSubKeys[0] = 255;
      v10 = RegEnumKeyExW(hKey, v8, Name, cSubKeys, 0, 0, 0, &ftLastWriteTime);
      v6 = v10;
      if ( v10 )
        break;
      if ( cSubKeys[0] > 9 && wcsncmp_0(Name, L"S-1-5-99", 8u) )
      {
        v24 = 0;
        v25 = 0;
        v11 = -1;
        do
          ++v11;
        while ( Name[v11] );
        std::wstring::_Construct<1,unsigned short const *>(&v24, Name, v11);
        v12 = (_OWORD *)a1[1];
        if ( v12 == (_OWORD *)a1[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, v12, &v24);
        }
        else
        {
          *v12 = v24;
          v12[1] = v25;
          v25 = si128;
          LOWORD(v24) = 0;
          a1[1] += 32;
        }
        std::wstring::~wstring(&v24);
      }
      if ( ++v8 >= cSubKeys[1] )
        goto LABEL_24;
    }
    if ( v10 != 259 )
    {
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_7;
    }
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800bd088  mov     rax, rsp
0x1800bd08b  mov     [rax+10h], rbx
0x1800bd08f  mov     [rax+18h], rsi
0x1800bd093  push    rbp
0x1800bd094  push    rdi
0x1800bd095  push    r14
0x1800bd097  lea     rbp, [rax-408h]
0x1800bd09e  sub     rsp, 4F0h
0x1800bd0a5  movaps  xmmword ptr [rax-28h], xmm6
0x1800bd0a9  mov     rax, cs:__security_cookie
0x1800bd0b0  xor     rax, rsp
0x1800bd0b3  mov     [rbp+400h+var_30], rax
0x1800bd0ba  mov     rdi, rcx
0x1800bd0bd  xor     r14d, r14d
0x1800bd0c0  mov     [rsp+500h+cSubKeys], r14d
0x1800bd0c5  mov     [rbp+400h+Class], r14w
0x1800bd0cd  xor     edx, edx; Val
0x1800bd0cf  mov     r8d, 206h; Size
0x1800bd0d5  lea     rcx, [rbp+400h+var_23E]; void *
0x1800bd0dc  call    memset_0
0x1800bd0e1  mov     [rbp+400h+cchClass], 104h
0x1800bd0e8  mov     [rsp+500h+cSubKeys+4], r14d
0x1800bd0ed  mov     [rbp+400h+cbMaxSubKeyLen], r14d
0x1800bd0f1  mov     [rbp+400h+cbMaxClassLen], r14d
0x1800bd0f5  mov     [rsp+500h+cValues], r14d
0x1800bd0fa  mov     [rsp+500h+cbMaxValueNameLen], r14d
0x1800bd0ff  mov     [rsp+500h+cbMaxValueLen], r14d
0x1800bd104  mov     [rsp+500h+cbSecurityDescriptor], r14d
0x1800bd109  mov     qword ptr [rbp+400h+ftLastWriteTime.dwLowDateTime], r14
0x1800bd10d  mov     rsi, [rdi+8]
0x1800bd111  mov     rbx, [rdi]
0x1800bd114  cmp     rbx, rsi
0x1800bd117  jz      short loc_1800BD131
0x1800bd119  mov     rcx, rbx
0x1800bd11c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bd121  add     rbx, 20h ; ' '
0x1800bd125  cmp     rbx, rsi
0x1800bd128  jnz     short loc_1800BD119
0x1800bd12a  mov     rax, [rdi]
0x1800bd12d  mov     [rdi+8], rax
0x1800bd131  mov     [rsp+500h+hKey], r14
0x1800bd136  lea     rax, [rsp+500h+hKey]
0x1800bd13b  mov     [rsp+500h+phkResult], rax; unsigned int
0x1800bd140  mov     r9d, 20019h; samDesired
0x1800bd146  xor     r8d, r8d; ulOptions
0x1800bd149  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bd150  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bd157  call    cs:__imp_RegOpenKeyExW
0x1800bd15d  test    eax, eax
0x1800bd15f  jz      short loc_1800BD195
0x1800bd161  mov     edx, 200h; void *
0x1800bd166  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appcompat\\programs\\dev"...
0x1800bd16d  mov     r9d, eax; char *
0x1800bd170  mov     rcx, [rbp+408h]; this
0x1800bd177  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bd17c  mov     ebx, eax
0x1800bd17e  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd183  test    rcx, rcx
0x1800bd186  jz      short loc_1800BD18E
0x1800bd188  call    cs:__imp_RegCloseKey
0x1800bd18e  mov     eax, ebx
0x1800bd190  jmp     loc_1800BD310
0x1800bd195  lea     rax, [rbp+400h+ftLastWriteTime]
0x1800bd199  mov     [rsp+500h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800bd19e  lea     rax, [rsp+500h+cbSecurityDescriptor]
0x1800bd1a3  mov     [rsp+500h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800bd1a8  lea     rax, [rsp+500h+cbMaxValueLen]
0x1800bd1ad  mov     [rsp+500h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800bd1b2  lea     rax, [rsp+500h+cbMaxValueNameLen]
0x1800bd1b7  mov     [rsp+500h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800bd1bc  lea     rax, [rsp+500h+cValues]
0x1800bd1c1  mov     [rsp+500h+lpcValues], rax; lpcValues
0x1800bd1c6  lea     rax, [rbp+400h+cbMaxClassLen]
0x1800bd1ca  mov     [rsp+500h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800bd1cf  lea     rax, [rbp+400h+cbMaxSubKeyLen]
0x1800bd1d3  mov     [rsp+500h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800bd1d8  lea     rax, [rsp+500h+cSubKeys+4]
0x1800bd1dd  mov     [rsp+500h+phkResult], rax; lpcSubKeys
0x1800bd1e2  xor     r9d, r9d; lpReserved
0x1800bd1e5  lea     r8, [rbp+400h+cchClass]; lpcchClass
0x1800bd1e9  lea     rdx, [rbp+400h+Class]; lpClass
0x1800bd1f0  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd1f5  call    cs:__imp_RegQueryInfoKeyW
0x1800bd1fb  test    eax, eax
0x1800bd1fd  jz      short loc_1800BD209
0x1800bd1ff  mov     edx, 20Eh
0x1800bd204  jmp     loc_1800BD166
0x1800bd209  mov     eax, [rsp+500h+cSubKeys+4]
0x1800bd20d  test    eax, eax
0x1800bd20f  jz      loc_1800BD2FE
0x1800bd215  mov     esi, r14d
0x1800bd218  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800bd220  mov     [rsp+500h+cSubKeys], 0FFh
0x1800bd228  lea     rax, [rbp+400h+ftLastWriteTime]
0x1800bd22c  mov     [rsp+500h+lpcValues], rax; lpftLastWriteTime
0x1800bd231  mov     [rsp+500h+lpcbMaxClassLen], r14; lpcchClass
0x1800bd236  mov     [rsp+500h+lpcbMaxSubKeyLen], r14; lpClass
0x1800bd23b  mov     [rsp+500h+phkResult], r14; lpReserved
0x1800bd240  lea     r9, [rsp+500h+cSubKeys]; lpcchName
0x1800bd245  lea     r8, [rbp+400h+Name]; lpName
0x1800bd249  mov     edx, esi; dwIndex
0x1800bd24b  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd250  call    cs:__imp_RegEnumKeyExW
0x1800bd256  mov     ebx, eax
0x1800bd258  test    eax, eax
0x1800bd25a  jnz     loc_1800BD33C
0x1800bd260  cmp     [rsp+500h+cSubKeys], 9
0x1800bd265  jbe     loc_1800BD2F2
0x1800bd26b  lea     r8d, [rax+8]; MaxCount
0x1800bd26f  lea     rdx, aS1599; "S-1-5-99"
0x1800bd276  lea     rcx, [rbp+400h+Name]; String1
0x1800bd27a  call    wcsncmp_0
0x1800bd27f  test    eax, eax
0x1800bd281  jz      short loc_1800BD2F2
0x1800bd283  xorps   xmm0, xmm0
0x1800bd286  movups  [rbp+400h+var_468], xmm0
0x1800bd28a  xorps   xmm1, xmm1
0x1800bd28d  movdqu  [rbp+400h+var_458], xmm1
0x1800bd292  lea     rax, [rbp+400h+Name]
0x1800bd296  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bd29a  inc     r8
0x1800bd29d  cmp     [rax+r8*2], r14w
0x1800bd2a2  jnz     short loc_1800BD29A
0x1800bd2a4  lea     rdx, [rbp+400h+Name]
0x1800bd2a8  lea     rcx, [rbp+400h+var_468]
0x1800bd2ac  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bd2b1  nop
0x1800bd2b2  mov     rdx, [rdi+8]
0x1800bd2b6  cmp     rdx, [rdi+10h]
0x1800bd2ba  jz      short loc_1800BD2DC
0x1800bd2bc  movups  xmm0, [rbp+400h+var_468]
0x1800bd2c0  movups  xmmword ptr [rdx], xmm0
0x1800bd2c3  movups  xmm1, [rbp+400h+var_458]
0x1800bd2c7  movups  xmmword ptr [rdx+10h], xmm1
0x1800bd2cb  movdqu  [rbp+400h+var_458], xmm6
0x1800bd2d0  mov     word ptr [rbp+400h+var_468], r14w
0x1800bd2d5  add     qword ptr [rdi+8], 20h ; ' '
0x1800bd2da  jmp     short loc_1800BD2E9
0x1800bd2dc  lea     r8, [rbp+400h+var_468]
0x1800bd2e0  mov     rcx, rdi
0x1800bd2e3  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800bd2e8  nop
0x1800bd2e9  lea     rcx, [rbp+400h+var_468]
0x1800bd2ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bd2f2  inc     esi
0x1800bd2f4  cmp     esi, [rsp+500h+cSubKeys+4]
0x1800bd2f8  jb      loc_1800BD220
0x1800bd2fe  mov     rcx, [rsp+500h+hKey]; hKey
0x1800bd303  test    rcx, rcx
0x1800bd306  jz      short loc_1800BD30E
0x1800bd308  call    cs:__imp_RegCloseKey
0x1800bd30e  xor     eax, eax
0x1800bd310  mov     rcx, [rbp+400h+var_30]
0x1800bd317  xor     rcx, rsp; StackCookie
0x1800bd31a  call    __security_check_cookie
0x1800bd31f  lea     r11, [rsp+500h+var_10]
0x1800bd327  mov     rbx, [r11+28h]
0x1800bd32b  mov     rsi, [r11+30h]
0x1800bd32f  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bd334  mov     rsp, r11
0x1800bd337  pop     r14
0x1800bd339  pop     rdi
0x1800bd33a  pop     rbp
0x1800bd33b  retn
0x1800bd33c  cmp     eax, 103h
0x1800bd341  jz      short loc_1800BD2FE
0x1800bd343  test    eax, eax
0x1800bd345  jle     loc_1800BD17E
0x1800bd34b  movzx   ebx, ax
0x1800bd34e  or      ebx, 80070000h
0x1800bd354  jmp     loc_1800BD17E
```
