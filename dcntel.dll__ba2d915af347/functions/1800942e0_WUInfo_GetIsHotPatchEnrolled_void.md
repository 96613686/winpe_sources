# WUInfo::GetIsHotPatchEnrolled(void)

- ea: `0x1800942e0`
- end: `0x180094544`
- name: `?GetIsHotPatchEnrolled@WUInfo@@AEBAHXZ`
- size: `612`
- prototype: `__int64 __fastcall(WUInfo *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x180028858`
- `0x1800942e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180094468`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180094472`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180094468`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180094472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009439a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009439a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094387`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800944c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800944c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094392`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800944ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094392`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800944ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094537`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800943c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800943c6`

## string_xrefs

- `0x18009435d`: `DynamicInstalledProducts`
- `0x180094356`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WUInfo::GetIsHotPatchEnrolled(WUInfo *this)
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
  if ( word_1801FF8C0
    || (int)Windows::Compat::Shared::Registry::GetPersistedLocation(
              &word_1801FF8C0,
              0x104u,
              L"DynamicInstalledProducts",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled",
              1) >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &word_1801FF8C0, 0, 0x20019u, &hKey) )
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
0x1800942e0  push    rbp
0x1800942e2  push    rbx
0x1800942e3  push    rsi
0x1800942e4  push    rdi
0x1800942e5  push    r12
0x1800942e7  push    r13
0x1800942e9  push    r14
0x1800942eb  push    r15
0x1800942ed  lea     rbp, [rsp-1B8h]
0x1800942f5  sub     rsp, 2B8h
0x1800942fc  mov     rax, cs:__security_cookie
0x180094303  xor     rax, rsp
0x180094306  mov     [rbp+1F0h+var_50], rax
0x18009430d  xor     r13d, r13d
0x180094310  mov     [rsp+2F0h+hKey], r13
0x180094315  mov     [rsp+2F0h+cchName], 104h
0x18009431d  xorps   xmm0, xmm0
0x180094320  movups  [rsp+2F0h+var_2A0], xmm0
0x180094325  xorps   xmm1, xmm1
0x180094328  movdqu  [rsp+2F0h+var_290], xmm1
0x18009432e  lea     r8d, [r13+9]
0x180094332  lea     rdx, aHotpatch; "Hotpatch."
0x180094339  lea     rcx, [rsp+2F0h+var_2A0]
0x18009433e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180094343  nop
0x180094344  cmp     cs:word_1801FF8C0, r13w
0x18009434c  jnz     short loc_18009437D
0x18009434e  mov     dword ptr [rsp+2F0h+phkResult], 1; int
0x180094356  lea     r9, aSoftwareMicros_57; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18009435d  lea     r8, aDynamicinstall; "DynamicInstalledProducts"
0x180094364  mov     edx, 104h; unsigned int
0x180094369  lea     rcx, word_1801FF8C0; unsigned __int16 *
0x180094370  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180094375  test    eax, eax
0x180094377  js      loc_1800944D7
0x18009437d  mov     rdi, [rsp+2F0h+hKey]
0x180094382  test    rdi, rdi
0x180094385  jz      short loc_1800943A0
0x180094387  call    cs:__imp_GetLastError
0x18009438d  mov     ebx, eax
0x18009438f  mov     rcx, rdi; hKey
0x180094392  call    cs:__imp_RegCloseKey
0x180094398  mov     ecx, ebx; dwErrCode
0x18009439a  call    cs:__imp_SetLastError
0x1800943a0  mov     [rsp+2F0h+hKey], r13
0x1800943a5  lea     rax, [rsp+2F0h+hKey]
0x1800943aa  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800943af  mov     r9d, 20019h; samDesired
0x1800943b5  xor     r8d, r8d; ulOptions
0x1800943b8  lea     rdx, word_1801FF8C0; lpSubKey
0x1800943bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800943c6  call    cs:__imp_RegOpenKeyExW
0x1800943cc  test    eax, eax
0x1800943ce  jnz     loc_1800944D7
0x1800943d4  mov     r15d, r13d
0x1800943d7  xor     edx, edx
0x1800943d9  jmp     loc_1800944A7
0x1800943de  mov     eax, [rsp+2F0h+cchName]
0x1800943e2  cmp     rax, qword ptr [rsp+2F0h+var_290]
0x1800943e7  jbe     loc_180094499
0x1800943ed  xorps   xmm0, xmm0
0x1800943f0  movups  [rsp+2F0h+var_280], xmm0
0x1800943f5  xorps   xmm1, xmm1
0x1800943f8  movdqu  [rbp+1F0h+var_270], xmm1
0x1800943fd  lea     rax, [rbp+1F0h+Name]
0x180094401  or      r8, 0FFFFFFFFFFFFFFFFh
0x180094405  inc     r8
0x180094408  cmp     [rax+r8*2], r13w
0x18009440d  jnz     short loc_180094405
0x18009440f  lea     rdx, [rbp+1F0h+Name]
0x180094413  lea     rcx, [rsp+2F0h+var_280]
0x180094418  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009441d  mov     rcx, qword ptr [rsp+2F0h+var_290]
0x180094422  cmp     qword ptr [rbp+1F0h+var_270], rcx
0x180094426  jbe     short loc_18009448F
0x180094428  lea     r14, [rsp+2F0h+var_280]
0x18009442d  cmp     qword ptr [rbp+1F0h+var_270+8], 7
0x180094432  cmova   r14, qword ptr [rsp+2F0h+var_280]
0x180094438  lea     rax, [rsp+2F0h+var_2A0]
0x18009443d  cmp     qword ptr [rsp+2F0h+var_290+8], 7
0x180094443  cmova   rax, qword ptr [rsp+2F0h+var_2A0]
0x180094449  lea     r12, [rax+rcx*2]
0x18009444d  lea     rsi, [rsp+2F0h+var_2A0]
0x180094452  cmova   rsi, qword ptr [rsp+2F0h+var_2A0]
0x180094458  cmp     rsi, r12
0x18009445b  jz      loc_180094517
0x180094461  movzx   ecx, word ptr [r14]; C
0x180094465  movzx   ebx, word ptr [rsi]
0x180094468  call    cs:__imp_toupper
0x18009446e  mov     edi, eax
0x180094470  mov     ecx, ebx; C
0x180094472  call    cs:__imp_toupper
0x180094478  cmp     eax, edi
0x18009447a  jnz     short loc_18009448F
0x18009447c  add     rsi, 2
0x180094480  cmp     rsi, r12
0x180094483  jz      loc_180094517
0x180094489  add     r14, 2
0x18009448d  jmp     short loc_180094461
0x18009448f  lea     rcx, [rsp+2F0h+var_280]
0x180094494  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180094499  inc     r15d
0x18009449c  mov     [rsp+2F0h+cchName], 104h
0x1800944a4  mov     edx, r15d; dwIndex
0x1800944a7  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800944ac  mov     [rsp+2F0h+lpcchClass], r13; lpcchClass
0x1800944b1  mov     [rsp+2F0h+lpClass], r13; lpClass
0x1800944b6  mov     [rsp+2F0h+phkResult], r13; lpReserved
0x1800944bb  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x1800944c0  lea     r8, [rbp+1F0h+Name]; lpName
0x1800944c4  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800944c9  call    cs:__imp_RegEnumKeyExW
0x1800944cf  test    eax, eax
0x1800944d1  jz      loc_1800943DE
0x1800944d7  lea     rcx, [rsp+2F0h+var_2A0]
0x1800944dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800944e1  nop
0x1800944e2  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800944e7  test    rcx, rcx
0x1800944ea  jz      short loc_1800944F2
0x1800944ec  call    cs:__imp_RegCloseKey
0x1800944f2  xor     eax, eax
0x1800944f4  mov     rcx, [rbp+1F0h+var_50]
0x1800944fb  xor     rcx, rsp; StackCookie
0x1800944fe  call    __security_check_cookie
0x180094503  add     rsp, 2B8h
0x18009450a  pop     r15
0x18009450c  pop     r14
0x18009450e  pop     r13
0x180094510  pop     r12
0x180094512  pop     rdi
0x180094513  pop     rsi
0x180094514  pop     rbx
0x180094515  pop     rbp
0x180094516  retn
0x180094517  lea     rcx, [rsp+2F0h+var_280]
0x18009451c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180094521  nop
0x180094522  lea     rcx, [rsp+2F0h+var_2A0]
0x180094527  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009452c  nop
0x18009452d  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180094532  test    rcx, rcx
0x180094535  jz      short loc_18009453D
0x180094537  call    cs:__imp_RegCloseKey
0x18009453d  mov     eax, 1
0x180094542  jmp     short loc_1800944F4
```
