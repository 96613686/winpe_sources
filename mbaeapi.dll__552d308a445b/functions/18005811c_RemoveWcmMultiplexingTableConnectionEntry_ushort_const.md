# RemoveWcmMultiplexingTableConnectionEntry(ushort const *)

- ea: `0x18005811c`
- end: `0x180058290`
- name: `?RemoveWcmMultiplexingTableConnectionEntry@@YAKPEBG@Z`
- size: `372`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180046960`
- `0x180057ce0`

## callees

- `0x1800024e0`
- `0x1800171b8`
- `0x180029f2c`
- `0x18005811c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800581c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800581c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800581ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800581ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800581f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800581f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058197`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058235`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005826d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058197`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058235`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005826d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180058247`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180058247`

## pseudocode

```c
__int64 __fastcall RemoveWcmMultiplexingTableConnectionEntry(LPCWSTR lpSubKey)
{
  __int64 result; // rax
  unsigned int PersistentRegPathWstring; // ebx
  const WCHAR *v4; // rdx
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+30h] [rbp-58h] BYREF
  LPCWSTR lpSubKeya[2]; // [rsp+38h] [rbp-50h] BYREF
  __m128i si128; // [rsp+48h] [rbp-40h]

  hKey = 0;
  if ( lpSubKey )
  {
    *(_OWORD *)lpSubKeya = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpSubKeya[0]) = 0;
    PersistentRegPathWstring = GetPersistentRegPathWstring(13, L"Connections\\WWAN", lpSubKeya);
    if ( PersistentRegPathWstring )
    {
      std::wstring::~wstring((char **)lpSubKeya);
      result = PersistentRegPathWstring;
    }
    else
    {
      hKey = 0;
      v4 = (const WCHAR *)lpSubKeya;
      if ( si128.m128i_i64[1] > 7uLL )
        v4 = lpSubKeya[0];
      v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0xF003Fu, &hKey);
      if ( v5 == 5 )
      {
        std::wstring::~wstring((char **)lpSubKeya);
        if ( hKey )
          RegCloseKey(hKey);
        result = 0;
      }
      else
      {
        std::wstring::~wstring((char **)lpSubKeya);
        if ( v5 )
        {
          if ( hKey )
            RegCloseKey(hKey);
          result = v5;
        }
        else
        {
          v6 = RegDeleteTreeW(hKey, lpSubKey);
          if ( hKey )
            RegCloseKey(hKey);
          result = v6;
        }
      }
    }
  }
  else
  {
    result = 87;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( std::exception )
    {
      if ( hKey )
        RegCloseKey(hKey);
      result = 14;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18005811c  push    rbx
0x18005811e  push    rsi
0x18005811f  push    rdi
0x180058120  push    r14
0x180058122  sub     rsp, 68h
0x180058126  mov     rax, cs:__security_cookie
0x18005812d  xor     rax, rsp
0x180058130  mov     [rsp+88h+var_30], rax
0x180058135  mov     r14, rcx
0x180058138  xor     edi, edi
0x18005813a  mov     [rsp+88h+hKey], rdi
0x18005813f  test    rcx, rcx
0x180058142  jnz     short loc_18005814C
0x180058144  lea     eax, [rcx+57h]
0x180058147  jmp     loc_180058278
0x18005814c  xorps   xmm0, xmm0
0x18005814f  movups  xmmword ptr [rsp+88h+lpSubKey], xmm0
0x180058154  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005815c  movdqu  [rsp+88h+var_40], xmm1
0x180058162  mov     word ptr [rsp+88h+lpSubKey], di
0x180058167  lea     r8, [rsp+88h+lpSubKey]
0x18005816c  lea     rdx, aConnectionsWwa; "Connections\\WWAN"
0x180058173  mov     ecx, 0Dh
0x180058178  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x18005817d  mov     ebx, eax
0x18005817f  test    eax, eax
0x180058181  jz      short loc_1800581A4
0x180058183  lea     rcx, [rsp+88h+lpSubKey]
0x180058188  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005818d  mov     rcx, [rsp+88h+hKey]; hKey
0x180058192  test    rcx, rcx
0x180058195  jz      short loc_18005819D
0x180058197  call    cs:__imp_RegCloseKey
0x18005819d  mov     eax, ebx
0x18005819f  jmp     loc_180058278
0x1800581a4  mov     rsi, [rsp+88h+hKey]
0x1800581a9  test    rsi, rsi
0x1800581ac  jz      short loc_1800581C7
0x1800581ae  call    cs:__imp_GetLastError
0x1800581b4  mov     ebx, eax
0x1800581b6  mov     rcx, rsi; hKey
0x1800581b9  call    cs:__imp_RegCloseKey
0x1800581bf  mov     ecx, ebx; dwErrCode
0x1800581c1  call    cs:__imp_SetLastError
0x1800581c7  mov     [rsp+88h+hKey], rdi
0x1800581cc  lea     rdx, [rsp+88h+lpSubKey]
0x1800581d1  cmp     qword ptr [rsp+88h+var_40+8], 7
0x1800581d7  cmova   rdx, [rsp+88h+lpSubKey]; lpSubKey
0x1800581dd  lea     rax, [rsp+88h+hKey]
0x1800581e2  mov     [rsp+88h+phkResult], rax; phkResult
0x1800581e7  mov     r9d, 0F003Fh; samDesired
0x1800581ed  xor     r8d, r8d; ulOptions
0x1800581f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800581f7  call    cs:__imp_RegOpenKeyExW
0x1800581fd  mov     ebx, eax
0x1800581ff  lea     rcx, [rsp+88h+lpSubKey]
0x180058204  cmp     eax, 5
0x180058207  jnz     short loc_180058222
0x180058209  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005820e  mov     rcx, [rsp+88h+hKey]; hKey
0x180058213  test    rcx, rcx
0x180058216  jz      short loc_18005821E
0x180058218  call    cs:__imp_RegCloseKey
0x18005821e  xor     eax, eax
0x180058220  jmp     short loc_180058278
0x180058222  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058227  test    ebx, ebx
0x180058229  jz      short loc_18005823F
0x18005822b  mov     rcx, [rsp+88h+hKey]; hKey
0x180058230  test    rcx, rcx
0x180058233  jz      short loc_18005823B
0x180058235  call    cs:__imp_RegCloseKey
0x18005823b  mov     eax, ebx
0x18005823d  jmp     short loc_180058278
0x18005823f  mov     rdx, r14; lpSubKey
0x180058242  mov     rcx, [rsp+88h+hKey]; hKey
0x180058247  call    cs:__imp_RegDeleteTreeW
0x18005824d  mov     ebx, eax
0x18005824f  mov     rcx, [rsp+88h+hKey]; hKey
0x180058254  test    rcx, rcx
0x180058257  jz      short loc_18005825F
0x180058259  call    cs:__imp_RegCloseKey
0x18005825f  mov     eax, ebx
0x180058261  jmp     short loc_180058278
0x180058263  mov     rcx, [rsp+88h+hKey]; hKey
0x180058268  test    rcx, rcx
0x18005826b  jz      short loc_180058273
0x18005826d  call    cs:__imp_RegCloseKey
0x180058273  mov     eax, 0Eh
0x180058278  mov     rcx, [rsp+88h+var_30]
0x18005827d  xor     rcx, rsp; StackCookie
0x180058280  call    __security_check_cookie
0x180058285  add     rsp, 68h
0x180058289  pop     r14
0x18005828b  pop     rdi
0x18005828c  pop     rsi
0x18005828d  pop     rbx
0x18005828e  retn
```
