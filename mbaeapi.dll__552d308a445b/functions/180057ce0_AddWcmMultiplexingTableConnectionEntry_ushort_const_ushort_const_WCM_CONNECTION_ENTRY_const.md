# AddWcmMultiplexingTableConnectionEntry(ushort const *,ushort const *,WCM_CONNECTION_ENTRY const *)

- ea: `0x180057ce0`
- end: `0x180057f63`
- name: `?AddWcmMultiplexingTableConnectionEntry@@YAKPEBG0PEBUWCM_CONNECTION_ENTRY@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(WCHAR *lpSubKey, unsigned __int16 *, BYTE *lpData)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180049050`

## callees

- `0x1800024e0`
- `0x1800171b8`
- `0x180029f2c`
- `0x18002afe8`
- `0x180057ce0`
- `0x18005811c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057dda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057f1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057dda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057f1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057f32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057e84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ec7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ef6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057e84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ec7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ef6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180057e2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180057e2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddWcmMultiplexingTableConnectionEntry(WCHAR *lpSubKey, unsigned __int16 *a2, BYTE *lpData)
{
  unsigned int PersistentRegPathWstring; // eax
  unsigned int v7; // r14d
  __int64 result; // rax
  const WCHAR *v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rax
  HKEY hKey; // [rsp+50h] [rbp-68h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-60h] BYREF
  LPCWSTR lpSubKeya[2]; // [rsp+60h] [rbp-58h] BYREF
  __m128i si128; // [rsp+70h] [rbp-48h]

  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !lpSubKey || !a2 || !lpData )
    return 87;
  *(_OWORD *)lpSubKeya = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKeya[0]) = 0;
  PersistentRegPathWstring = GetPersistentRegPathWstring(13, L"Connections\\WWAN", lpSubKeya);
  v7 = PersistentRegPathWstring;
  if ( PersistentRegPathWstring )
  {
    std::wstring::~wstring((char **)lpSubKeya);
    return v7;
  }
  else
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      std::wstring::append(lpSubKeya, (void *)L"\\");
      std::wstring::append(lpSubKeya, lpSubKey);
      std::wstring::append(lpSubKeya, (void *)L"\\");
      std::wstring::append(lpSubKeya, a2);
      hKey = 0;
      v9 = (const WCHAR *)lpSubKeya;
      if ( si128.m128i_i64[1] > 7uLL )
        v9 = lpSubKeya[0];
      v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      if ( v10 )
      {
        std::wstring::~wstring((char **)lpSubKeya);
      }
      else
      {
        std::wstring::~wstring((char **)lpSubKeya);
        if ( !*(_WORD *)lpData )
          goto LABEL_35;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&lpData[2 * v11] );
        v10 = RegSetValueExW(hKey, L"Desc", 0, 1u, lpData, 2 * v11 + 2);
        if ( !v10 )
        {
LABEL_35:
          *(_DWORD *)Data = lpData[260] != 0;
          v10 = RegSetValueExW(hKey, L"UseRequiresMappingsPolicy", 0, 4u, Data, 4u);
          if ( !v10 )
            v10 = RegSetValueExW(hKey, L"IdleDisconnectTimeout", 0, 4u, lpData + 256, 4u);
        }
      }
      if ( v10 == 5 )
      {
        v10 = 0;
      }
      else if ( v10 )
      {
        RemoveWcmMultiplexingTableConnectionEntry(lpSubKey);
      }
      if ( hKey )
        RegCloseKey(hKey);
      result = v10;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_180057F28);
        if ( hKey )
          RegCloseKey(hKey);
        return 14;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180057ce0  push    rbx
0x180057ce2  push    rsi
0x180057ce3  push    rdi
0x180057ce4  push    r14
0x180057ce6  push    r15
0x180057ce8  sub     rsp, 90h
0x180057cef  mov     rax, cs:__security_cookie
0x180057cf6  xor     rax, rsp
0x180057cf9  mov     [rsp+0B8h+var_38], rax
0x180057d01  mov     rsi, r8
0x180057d04  mov     rbx, rdx
0x180057d07  mov     r15, rcx
0x180057d0a  xor     edi, edi
0x180057d0c  mov     [rsp+0B8h+hKey], rdi
0x180057d11  mov     dword ptr [rsp+0B8h+Data], edi
0x180057d15  test    rcx, rcx
0x180057d18  jz      loc_180057F3F
0x180057d1e  test    rdx, rdx
0x180057d21  jz      loc_180057F3F
0x180057d27  test    r8, r8
0x180057d2a  jz      loc_180057F3F
0x180057d30  xorps   xmm0, xmm0
0x180057d33  movups  xmmword ptr [rsp+0B8h+lpSubKey], xmm0
0x180057d38  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180057d40  movdqu  [rsp+0B8h+var_48], xmm1
0x180057d46  mov     word ptr [rsp+0B8h+lpSubKey], di
0x180057d4b  lea     r8, [rsp+0B8h+lpSubKey]
0x180057d50  lea     rdx, aConnectionsWwa; "Connections\\WWAN"
0x180057d57  lea     ecx, [rdi+0Dh]
0x180057d5a  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x180057d5f  mov     r14d, eax
0x180057d62  test    eax, eax
0x180057d64  jz      short loc_180057D89
0x180057d66  lea     rcx, [rsp+0B8h+lpSubKey]
0x180057d6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057d70  nop
0x180057d71  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057d76  test    rcx, rcx
0x180057d79  jz      short loc_180057D81
0x180057d7b  call    cs:__imp_RegCloseKey
0x180057d81  mov     eax, r14d
0x180057d84  jmp     loc_180057F44
0x180057d89  lea     rdx, asc_1800657D8; "\\"
0x180057d90  lea     rcx, [rsp+0B8h+lpSubKey]; Src
0x180057d95  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180057d9a  mov     rdx, r15; void *
0x180057d9d  lea     rcx, [rsp+0B8h+lpSubKey]; Src
0x180057da2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180057da7  lea     rdx, asc_1800657D8; "\\"
0x180057dae  lea     rcx, [rsp+0B8h+lpSubKey]; Src
0x180057db3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180057db8  mov     rdx, rbx; void *
0x180057dbb  lea     rcx, [rsp+0B8h+lpSubKey]; Src
0x180057dc0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180057dc5  mov     r14, [rsp+0B8h+hKey]
0x180057dca  test    r14, r14
0x180057dcd  jz      short loc_180057DE8
0x180057dcf  call    cs:__imp_GetLastError
0x180057dd5  mov     ebx, eax
0x180057dd7  mov     rcx, r14; hKey
0x180057dda  call    cs:__imp_RegCloseKey
0x180057de0  mov     ecx, ebx; dwErrCode
0x180057de2  call    cs:__imp_SetLastError
0x180057de8  mov     [rsp+0B8h+hKey], rdi
0x180057ded  lea     rdx, [rsp+0B8h+lpSubKey]
0x180057df2  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x180057df8  cmova   rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x180057dfe  mov     [rsp+0B8h+lpdwDisposition], rdi; lpdwDisposition
0x180057e03  lea     rax, [rsp+0B8h+hKey]
0x180057e08  mov     [rsp+0B8h+phkResult], rax; phkResult
0x180057e0d  mov     [rsp+0B8h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180057e12  mov     [rsp+0B8h+samDesired], 20006h; samDesired
0x180057e1a  mov     [rsp+0B8h+dwOptions], edi; dwOptions
0x180057e1e  xor     r9d, r9d; lpClass
0x180057e21  xor     r8d, r8d; Reserved
0x180057e24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057e2b  call    cs:__imp_RegCreateKeyExW
0x180057e31  mov     ebx, eax
0x180057e33  lea     rcx, [rsp+0B8h+lpSubKey]
0x180057e38  test    eax, eax
0x180057e3a  jz      short loc_180057E47
0x180057e3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057e41  nop
0x180057e42  jmp     loc_180057EFE
0x180057e47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057e4c  nop
0x180057e4d  cmp     [rsi], di
0x180057e50  jz      short loc_180057E90
0x180057e52  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057e56  inc     rax
0x180057e59  cmp     [rsi+rax*2], di
0x180057e5d  jnz     short loc_180057E56
0x180057e5f  lea     eax, ds:2[rax*2]
0x180057e66  mov     [rsp+0B8h+samDesired], eax; cbData
0x180057e6a  mov     qword ptr [rsp+0B8h+dwOptions], rsi; lpData
0x180057e6f  mov     r9d, 1; dwType
0x180057e75  xor     r8d, r8d; Reserved
0x180057e78  lea     rdx, aDesc; "Desc"
0x180057e7f  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057e84  call    cs:__imp_RegSetValueExW
0x180057e8a  mov     ebx, eax
0x180057e8c  test    eax, eax
0x180057e8e  jnz     short loc_180057EFE
0x180057e90  mov     eax, edi
0x180057e92  cmp     [rsi+104h], dil
0x180057e99  setnz   al
0x180057e9c  mov     dword ptr [rsp+0B8h+Data], eax
0x180057ea0  mov     r14d, 4
0x180057ea6  mov     [rsp+0B8h+samDesired], r14d; cbData
0x180057eab  lea     rax, [rsp+0B8h+Data]
0x180057eb0  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x180057eb5  mov     r9d, r14d; dwType
0x180057eb8  xor     r8d, r8d; Reserved
0x180057ebb  lea     rdx, aUserequiresmap; "UseRequiresMappingsPolicy"
0x180057ec2  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057ec7  call    cs:__imp_RegSetValueExW
0x180057ecd  mov     ebx, eax
0x180057ecf  test    eax, eax
0x180057ed1  jnz     short loc_180057EFE
0x180057ed3  lea     rax, [rsi+100h]
0x180057eda  mov     [rsp+0B8h+samDesired], r14d; cbData
0x180057edf  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x180057ee4  mov     r9d, r14d; dwType
0x180057ee7  xor     r8d, r8d; Reserved
0x180057eea  lea     rdx, aIdledisconnect; "IdleDisconnectTimeout"
0x180057ef1  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057ef6  call    cs:__imp_RegSetValueExW
0x180057efc  mov     ebx, eax
0x180057efe  cmp     ebx, 5
0x180057f01  jnz     short loc_180057F07
0x180057f03  mov     ebx, edi
0x180057f05  jmp     short loc_180057F14
0x180057f07  test    ebx, ebx
0x180057f09  jz      short loc_180057F14
0x180057f0b  mov     rcx, r15; lpSubKey
0x180057f0e  call    ?RemoveWcmMultiplexingTableConnectionEntry@@YAKPEBG@Z; RemoveWcmMultiplexingTableConnectionEntry(ushort const *)
0x180057f13  nop
0x180057f14  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057f19  test    rcx, rcx
0x180057f1c  jz      short loc_180057F24
0x180057f1e  call    cs:__imp_RegCloseKey
0x180057f24  mov     eax, ebx
0x180057f26  jmp     short loc_180057F44
0x180057f28  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057f2d  test    rcx, rcx
0x180057f30  jz      short loc_180057F38
0x180057f32  call    cs:__imp_RegCloseKey
0x180057f38  mov     eax, 0Eh
0x180057f3d  jmp     short loc_180057F44
0x180057f3f  mov     eax, 57h ; 'W'
0x180057f44  mov     rcx, [rsp+0B8h+var_38]
0x180057f4c  xor     rcx, rsp; StackCookie
0x180057f4f  call    __security_check_cookie
0x180057f54  add     rsp, 90h
0x180057f5b  pop     r15
0x180057f5d  pop     r14
0x180057f5f  pop     rdi
0x180057f60  pop     rsi
0x180057f61  pop     rbx
0x180057f62  retn
```
