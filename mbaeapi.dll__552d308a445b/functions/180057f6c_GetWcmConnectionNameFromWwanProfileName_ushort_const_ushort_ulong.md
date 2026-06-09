# GetWcmConnectionNameFromWwanProfileName(ushort const *,ushort *,ulong &)

- ea: `0x180057f6c`
- end: `0x180058114`
- name: `?GetWcmConnectionNameFromWwanProfileName@@YAKPEBGPEAGAEAK@Z`
- size: `424`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, LPWSTR lpName, LPDWORD lpcchName)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800359bc`

## callees

- `0x1800024e0`
- `0x1800171b8`
- `0x180029f2c`
- `0x18002afe8`
- `0x180057f6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005803b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005803b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058028`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058071`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800580d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800580e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800580d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800580e9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800580c3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800580c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetWcmConnectionNameFromWwanProfileName(unsigned __int16 *a1, LPWSTR lpName, LPDWORD lpcchName)
{
  unsigned int PersistentRegPathWstring; // eax
  unsigned int v7; // esi
  __int64 result; // rax
  const WCHAR *v9; // rdx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  HKEY hKey; // [rsp+40h] [rbp-58h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-50h] BYREF
  __m128i si128; // [rsp+58h] [rbp-40h]

  hKey = 0;
  if ( !a1 || !lpName )
    return 87;
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  PersistentRegPathWstring = GetPersistentRegPathWstring(0xDu, (__int64)L"Connections\\WWAN", (__int64)lpSubKey);
  v7 = PersistentRegPathWstring;
  if ( PersistentRegPathWstring )
  {
    std::wstring::~wstring((char **)lpSubKey);
    return v7;
  }
  else
  {
    try
    {
      std::wstring::append(lpSubKey, (void *)L"\\");
      std::wstring::append(lpSubKey, a1);
      hKey = 0;
      v9 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v9 = lpSubKey[0];
      v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
      if ( v10 )
      {
        std::wstring::~wstring((char **)lpSubKey);
        if ( hKey )
          RegCloseKey(hKey);
        result = v10;
      }
      else
      {
        std::wstring::~wstring((char **)lpSubKey);
        v11 = RegEnumKeyExW(hKey, 0, lpName, lpcchName, 0, 0, 0, 0);
        if ( hKey )
          RegCloseKey(hKey);
        result = v11;
      }
    }
    catch ( std::exception )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180057f6c  push    rbx
0x180057f6e  push    rsi
0x180057f6f  push    rdi
0x180057f70  push    r14
0x180057f72  push    r15
0x180057f74  sub     rsp, 70h
0x180057f78  mov     rax, cs:__security_cookie
0x180057f7f  xor     rax, rsp
0x180057f82  mov     [rsp+98h+var_30], rax
0x180057f87  mov     r15, r8
0x180057f8a  mov     r14, rdx
0x180057f8d  mov     rbx, rcx
0x180057f90  xor     edi, edi
0x180057f92  mov     [rsp+98h+hKey], rdi
0x180057f97  test    rcx, rcx
0x180057f9a  jz      loc_1800580F6
0x180057fa0  test    rdx, rdx
0x180057fa3  jz      loc_1800580F6
0x180057fa9  xorps   xmm0, xmm0
0x180057fac  movups  xmmword ptr [rsp+98h+lpSubKey], xmm0
0x180057fb1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180057fb9  movdqu  [rsp+98h+var_40], xmm1
0x180057fbf  mov     word ptr [rsp+98h+lpSubKey], di
0x180057fc4  lea     r8, [rsp+98h+lpSubKey]
0x180057fc9  lea     rdx, aConnectionsWwa; "Connections\\WWAN"
0x180057fd0  lea     ecx, [rdi+0Dh]
0x180057fd3  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x180057fd8  mov     esi, eax
0x180057fda  test    eax, eax
0x180057fdc  jz      short loc_180058000
0x180057fde  lea     rcx, [rsp+98h+lpSubKey]
0x180057fe3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057fe8  nop
0x180057fe9  mov     rcx, [rsp+98h+hKey]; hKey
0x180057fee  test    rcx, rcx
0x180057ff1  jz      short loc_180057FF9
0x180057ff3  call    cs:__imp_RegCloseKey
0x180057ff9  mov     eax, esi
0x180057ffb  jmp     loc_1800580FB
0x180058000  lea     rdx, asc_1800657D8; "\\"
0x180058007  lea     rcx, [rsp+98h+lpSubKey]; Src
0x18005800c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180058011  mov     rdx, rbx; void *
0x180058014  lea     rcx, [rsp+98h+lpSubKey]; Src
0x180058019  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005801e  mov     rsi, [rsp+98h+hKey]
0x180058023  test    rsi, rsi
0x180058026  jz      short loc_180058041
0x180058028  call    cs:__imp_GetLastError
0x18005802e  mov     ebx, eax
0x180058030  mov     rcx, rsi; hKey
0x180058033  call    cs:__imp_RegCloseKey
0x180058039  mov     ecx, ebx; dwErrCode
0x18005803b  call    cs:__imp_SetLastError
0x180058041  mov     [rsp+98h+hKey], rdi
0x180058046  lea     rdx, [rsp+98h+lpSubKey]
0x18005804b  cmp     qword ptr [rsp+98h+var_40+8], 7
0x180058051  cmova   rdx, [rsp+98h+lpSubKey]; lpSubKey
0x180058057  lea     rax, [rsp+98h+hKey]
0x18005805c  mov     [rsp+98h+phkResult], rax; phkResult
0x180058061  mov     r9d, 20019h; samDesired
0x180058067  xor     r8d, r8d; ulOptions
0x18005806a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058071  call    cs:__imp_RegOpenKeyExW
0x180058077  mov     ebx, eax
0x180058079  lea     rcx, [rsp+98h+lpSubKey]
0x18005807e  test    eax, eax
0x180058080  jz      short loc_18005809C
0x180058082  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058087  nop
0x180058088  mov     rcx, [rsp+98h+hKey]; hKey
0x18005808d  test    rcx, rcx
0x180058090  jz      short loc_180058098
0x180058092  call    cs:__imp_RegCloseKey
0x180058098  mov     eax, ebx
0x18005809a  jmp     short loc_1800580FB
0x18005809c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800580a1  nop
0x1800580a2  mov     [rsp+98h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800580a7  mov     [rsp+98h+lpcchClass], rdi; lpcchClass
0x1800580ac  mov     [rsp+98h+lpClass], rdi; lpClass
0x1800580b1  mov     [rsp+98h+phkResult], rdi; lpReserved
0x1800580b6  mov     r9, r15; lpcchName
0x1800580b9  mov     r8, r14; lpName
0x1800580bc  xor     edx, edx; dwIndex
0x1800580be  mov     rcx, [rsp+98h+hKey]; hKey
0x1800580c3  call    cs:__imp_RegEnumKeyExW
0x1800580c9  mov     ebx, eax
0x1800580cb  mov     rcx, [rsp+98h+hKey]; hKey
0x1800580d0  test    rcx, rcx
0x1800580d3  jz      short loc_1800580DB
0x1800580d5  call    cs:__imp_RegCloseKey
0x1800580db  mov     eax, ebx
0x1800580dd  jmp     short loc_1800580FB
0x1800580df  mov     rcx, [rsp+98h+hKey]; hKey
0x1800580e4  test    rcx, rcx
0x1800580e7  jz      short loc_1800580EF
0x1800580e9  call    cs:__imp_RegCloseKey
0x1800580ef  mov     eax, 0Eh
0x1800580f4  jmp     short loc_1800580FB
0x1800580f6  mov     eax, 57h ; 'W'
0x1800580fb  mov     rcx, [rsp+98h+var_30]
0x180058100  xor     rcx, rsp; StackCookie
0x180058103  call    __security_check_cookie
0x180058108  add     rsp, 70h
0x18005810c  pop     r15
0x18005810e  pop     r14
0x180058110  pop     rdi
0x180058111  pop     rsi
0x180058112  pop     rbx
0x180058113  retn
```
