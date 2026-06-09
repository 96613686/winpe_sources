# CWUInfo::GetIsHotPatchEnrolled(void)

- ea: `0x1800d6f20`
- end: `0x1800d7184`
- name: `?GetIsHotPatchEnrolled@CWUInfo@@QEBAHXZ`
- size: `612`
- prototype: `__int64 __fastcall(CWUInfo *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x180028858`
- `0x1800d6f20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800d70a8`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800d70b2`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800d70a8`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800d70b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6fda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6fc7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d7109`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d7109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d6fd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d712c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d6fd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d712c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7177`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7006`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7006`

## string_xrefs

- `0x1800d6f9d`: `DynamicInstalledProducts`
- `0x1800d6f96`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`

## pseudocode

```c
__int64 __fastcall CWUInfo::GetIsHotPatchEnrolled(CWUInfo *this)
{
  DWORD v1; // r15d
  DWORD i; // edx
  unsigned __int64 v3; // r8
  unsigned __int16 *v4; // r14
  __int128 *v5; // rax
  unsigned __int16 *v6; // r12
  unsigned __int16 *v7; // rsi
  int v8; // ebx
  int v9; // edi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+60h] [rbp-A0h]
  __int128 v15; // [rsp+70h] [rbp-90h] BYREF
  __int128 v16; // [rsp+80h] [rbp-80h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  cchName = 260;
  v13 = 0;
  v14 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v13, L"Hotpatch.", 9u);
  if ( word_180200350
    || (int)Windows::Compat::Shared::Registry::GetPersistedLocation(
              &word_180200350,
              0x104u,
              L"DynamicInstalledProducts",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled",
              1) >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &word_180200350, 0, 0x20019u, &hKey) )
    {
      v1 = 0;
      for ( i = 0; !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0); i = v1 )
      {
        if ( cchName > (unsigned __int64)v14 )
        {
          v15 = 0;
          v16 = 0;
          v3 = -1;
          do
            ++v3;
          while ( Name[v3] );
          std::wstring::_Construct<1,unsigned short const *>((char **)&v15, Name, v3);
          if ( (unsigned __int64)v16 > (unsigned __int64)v14 )
          {
            v4 = (unsigned __int16 *)&v15;
            if ( *((_QWORD *)&v16 + 1) > 7u )
              v4 = (unsigned __int16 *)v15;
            v5 = &v13;
            if ( *((_QWORD *)&v14 + 1) > 7u )
              v5 = (__int128 *)v13;
            v6 = (unsigned __int16 *)v5 + v14;
            v7 = (unsigned __int16 *)&v13;
            if ( *((_QWORD *)&v14 + 1) > 7u )
              v7 = (unsigned __int16 *)v13;
            if ( v7 == v6 )
            {
LABEL_25:
              std::wstring::~wstring((char **)&v15);
              std::wstring::~wstring((char **)&v13);
              if ( hKey )
                RegCloseKey(hKey);
              return 1;
            }
            while ( 1 )
            {
              v8 = *v7;
              v9 = toupper(*v4);
              if ( toupper(v8) != v9 )
                break;
              if ( ++v7 == v6 )
                goto LABEL_25;
              ++v4;
            }
          }
          std::wstring::~wstring((char **)&v15);
        }
        ++v1;
        cchName = 260;
      }
    }
  }
  std::wstring::~wstring((char **)&v13);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800d6f20  push    rbp
0x1800d6f22  push    rbx
0x1800d6f23  push    rsi
0x1800d6f24  push    rdi
0x1800d6f25  push    r12
0x1800d6f27  push    r13
0x1800d6f29  push    r14
0x1800d6f2b  push    r15
0x1800d6f2d  lea     rbp, [rsp-1B8h]
0x1800d6f35  sub     rsp, 2B8h
0x1800d6f3c  mov     rax, cs:__security_cookie
0x1800d6f43  xor     rax, rsp
0x1800d6f46  mov     [rbp+1F0h+var_50], rax
0x1800d6f4d  xor     r13d, r13d
0x1800d6f50  mov     [rsp+2F0h+hKey], r13
0x1800d6f55  mov     [rsp+2F0h+cchName], 104h
0x1800d6f5d  xorps   xmm0, xmm0
0x1800d6f60  movups  [rsp+2F0h+var_2A0], xmm0
0x1800d6f65  xorps   xmm1, xmm1
0x1800d6f68  movdqu  [rsp+2F0h+var_290], xmm1
0x1800d6f6e  lea     r8d, [r13+9]
0x1800d6f72  lea     rdx, aHotpatch; "Hotpatch."
0x1800d6f79  lea     rcx, [rsp+2F0h+var_2A0]
0x1800d6f7e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d6f83  nop
0x1800d6f84  cmp     cs:word_180200350, r13w
0x1800d6f8c  jnz     short loc_1800D6FBD
0x1800d6f8e  mov     dword ptr [rsp+2F0h+phkResult], 1; int
0x1800d6f96  lea     r9, aSoftwareMicros_57; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800d6f9d  lea     r8, aDynamicinstall; "DynamicInstalledProducts"
0x1800d6fa4  mov     edx, 104h; unsigned int
0x1800d6fa9  lea     rcx, word_180200350; unsigned __int16 *
0x1800d6fb0  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800d6fb5  test    eax, eax
0x1800d6fb7  js      loc_1800D7117
0x1800d6fbd  mov     rdi, [rsp+2F0h+hKey]
0x1800d6fc2  test    rdi, rdi
0x1800d6fc5  jz      short loc_1800D6FE0
0x1800d6fc7  call    cs:__imp_GetLastError
0x1800d6fcd  mov     ebx, eax
0x1800d6fcf  mov     rcx, rdi; hKey
0x1800d6fd2  call    cs:__imp_RegCloseKey
0x1800d6fd8  mov     ecx, ebx; dwErrCode
0x1800d6fda  call    cs:__imp_SetLastError
0x1800d6fe0  mov     [rsp+2F0h+hKey], r13
0x1800d6fe5  lea     rax, [rsp+2F0h+hKey]
0x1800d6fea  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800d6fef  mov     r9d, 20019h; samDesired
0x1800d6ff5  xor     r8d, r8d; ulOptions
0x1800d6ff8  lea     rdx, word_180200350; lpSubKey
0x1800d6fff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7006  call    cs:__imp_RegOpenKeyExW
0x1800d700c  test    eax, eax
0x1800d700e  jnz     loc_1800D7117
0x1800d7014  mov     r15d, r13d
0x1800d7017  xor     edx, edx
0x1800d7019  jmp     loc_1800D70E7
0x1800d701e  mov     eax, [rsp+2F0h+cchName]
0x1800d7022  cmp     rax, qword ptr [rsp+2F0h+var_290]
0x1800d7027  jbe     loc_1800D70D9
0x1800d702d  xorps   xmm0, xmm0
0x1800d7030  movups  [rsp+2F0h+var_280], xmm0
0x1800d7035  xorps   xmm1, xmm1
0x1800d7038  movdqu  [rbp+1F0h+var_270], xmm1
0x1800d703d  lea     rax, [rbp+1F0h+Name]
0x1800d7041  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d7045  inc     r8
0x1800d7048  cmp     [rax+r8*2], r13w
0x1800d704d  jnz     short loc_1800D7045
0x1800d704f  lea     rdx, [rbp+1F0h+Name]
0x1800d7053  lea     rcx, [rsp+2F0h+var_280]
0x1800d7058  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d705d  mov     rcx, qword ptr [rsp+2F0h+var_290]
0x1800d7062  cmp     qword ptr [rbp+1F0h+var_270], rcx
0x1800d7066  jbe     short loc_1800D70CF
0x1800d7068  lea     r14, [rsp+2F0h+var_280]
0x1800d706d  cmp     qword ptr [rbp+1F0h+var_270+8], 7
0x1800d7072  cmova   r14, qword ptr [rsp+2F0h+var_280]
0x1800d7078  lea     rax, [rsp+2F0h+var_2A0]
0x1800d707d  cmp     qword ptr [rsp+2F0h+var_290+8], 7
0x1800d7083  cmova   rax, qword ptr [rsp+2F0h+var_2A0]
0x1800d7089  lea     r12, [rax+rcx*2]
0x1800d708d  lea     rsi, [rsp+2F0h+var_2A0]
0x1800d7092  cmova   rsi, qword ptr [rsp+2F0h+var_2A0]
0x1800d7098  cmp     rsi, r12
0x1800d709b  jz      loc_1800D7157
0x1800d70a1  movzx   ecx, word ptr [r14]; C
0x1800d70a5  movzx   ebx, word ptr [rsi]
0x1800d70a8  call    cs:__imp_toupper
0x1800d70ae  mov     edi, eax
0x1800d70b0  mov     ecx, ebx; C
0x1800d70b2  call    cs:__imp_toupper
0x1800d70b8  cmp     eax, edi
0x1800d70ba  jnz     short loc_1800D70CF
0x1800d70bc  add     rsi, 2
0x1800d70c0  cmp     rsi, r12
0x1800d70c3  jz      loc_1800D7157
0x1800d70c9  add     r14, 2
0x1800d70cd  jmp     short loc_1800D70A1
0x1800d70cf  lea     rcx, [rsp+2F0h+var_280]
0x1800d70d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d70d9  inc     r15d
0x1800d70dc  mov     [rsp+2F0h+cchName], 104h
0x1800d70e4  mov     edx, r15d; dwIndex
0x1800d70e7  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800d70ec  mov     [rsp+2F0h+lpcchClass], r13; lpcchClass
0x1800d70f1  mov     [rsp+2F0h+lpClass], r13; lpClass
0x1800d70f6  mov     [rsp+2F0h+phkResult], r13; lpReserved
0x1800d70fb  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x1800d7100  lea     r8, [rbp+1F0h+Name]; lpName
0x1800d7104  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800d7109  call    cs:__imp_RegEnumKeyExW
0x1800d710f  test    eax, eax
0x1800d7111  jz      loc_1800D701E
0x1800d7117  lea     rcx, [rsp+2F0h+var_2A0]
0x1800d711c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7121  nop
0x1800d7122  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800d7127  test    rcx, rcx
0x1800d712a  jz      short loc_1800D7132
0x1800d712c  call    cs:__imp_RegCloseKey
0x1800d7132  xor     eax, eax
0x1800d7134  mov     rcx, [rbp+1F0h+var_50]
0x1800d713b  xor     rcx, rsp; StackCookie
0x1800d713e  call    __security_check_cookie
0x1800d7143  add     rsp, 2B8h
0x1800d714a  pop     r15
0x1800d714c  pop     r14
0x1800d714e  pop     r13
0x1800d7150  pop     r12
0x1800d7152  pop     rdi
0x1800d7153  pop     rsi
0x1800d7154  pop     rbx
0x1800d7155  pop     rbp
0x1800d7156  retn
0x1800d7157  lea     rcx, [rsp+2F0h+var_280]
0x1800d715c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d7161  nop
0x1800d7162  lea     rcx, [rsp+2F0h+var_2A0]
0x1800d7167  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d716c  nop
0x1800d716d  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800d7172  test    rcx, rcx
0x1800d7175  jz      short loc_1800D717D
0x1800d7177  call    cs:__imp_RegCloseKey
0x1800d717d  mov     eax, 1
0x1800d7182  jmp     short loc_1800D7134
```
