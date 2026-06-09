# GetProcessRolloutDelayReasons(ushort const * const)

- ea: `0x1800632a0`
- end: `0x1800634e5`
- name: `?GetProcessRolloutDelayReasons@@YA?AW4ExperienceRolloutDelayReasons@@QEBG@Z`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180062430`

## callees

- `0x18000ad30`
- `0x18000c470`
- `0x1800108cc`
- `0x18002a3d0`
- `0x18002af50`
- `0x18005edb8`
- `0x180060df4`
- `0x1800632a0`
- `0x1800651fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180063400`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180063400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006345f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006345f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006342b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006342b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063493`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063493`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetProcessRolloutDelayReasons(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // r15
  unsigned int v6; // r12d
  HKEY v7; // rbx
  __int64 ActivePidsForExperience; // rdi
  unsigned __int128 v9; // kr00_16
  __int64 v10; // rdi
  HKEY *v11; // rax
  bool *v12; // r8
  DWORD v13; // edi
  DWORD i; // edx
  __int64 j; // rbx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v18; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[256]; // [rsp+90h] [rbp-70h] BYREF

  v5 = 0;
  v6 = 0;
  v20 = 0;
  v21 = 0;
  GetHostSessionSubKey((LPVOID *)&hKey, a1, 0x2001Fu, a4);
  v7 = hKey;
  if ( hKey )
  {
    ActivePidsForExperience = detail::FindActivePidsForExperience(v22, hKey);
    if ( &v20 == (unsigned __int128 *)ActivePidsForExperience )
    {
      v10 = 0;
      v9 = v20;
    }
    else
    {
      std::vector<unsigned long>::_Tidy(&v20);
      v20 = *(_OWORD *)ActivePidsForExperience;
      v9 = v20;
      v21 = *(_QWORD *)(ActivePidsForExperience + 16);
      *(_QWORD *)ActivePidsForExperience = 0;
      *(_QWORD *)(ActivePidsForExperience + 8) = 0;
      *(_QWORD *)(ActivePidsForExperience + 16) = 0;
      v5 = v9 >> 64;
      v10 = v9;
    }
    std::vector<unsigned long>::_Tidy(v22);
    while ( v10 != v5 )
    {
      v6 |= detail::ReadDelayReasonsForPid(v7);
      v10 += 4;
    }
  }
  else
  {
    v9 = v20;
  }
  if ( v7 )
    RegCloseKey(v7);
  if ( (_QWORD)v9 != *((_QWORD *)&v9 + 1) )
  {
    v18 = 0;
    v11 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v18);
    if ( CreateShellSessionSubKey(L"ShellUIHosts", 0x20019u, v12, v11) >= 0 )
    {
      v13 = 0;
      memset_0(SubKey, 0, sizeof(SubKey));
      for ( i = 0; ; i = v13 )
      {
        cchName = 256;
        if ( RegEnumKeyExW(v18, i, SubKey, &cchName, 0, 0, 0, 0) )
          break;
        if ( (unsigned int)_o__wcsicmp(SubKey, a1) )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(v18, SubKey, 0, 0x20019u, &hKey) )
          {
            for ( j = v9; j != *((_QWORD *)&v9 + 1); j += 4 )
              v6 |= detail::ReadDelayReasonsForPid(hKey);
          }
          if ( hKey )
            RegCloseKey(hKey);
        }
        ++v13;
      }
    }
    if ( v18 )
      RegCloseKey(v18);
  }
  std::vector<unsigned long>::_Tidy(&v20);
  return v6;
}

```

## disassembly

```asm
0x1800632a0  push    rbp
0x1800632a2  push    rbx
0x1800632a3  push    rsi
0x1800632a4  push    rdi
0x1800632a5  push    r12
0x1800632a7  push    r13
0x1800632a9  push    r14
0x1800632ab  push    r15
0x1800632ad  lea     rbp, [rsp-1A8h]
0x1800632b5  sub     rsp, 2A8h
0x1800632bc  mov     rax, cs:__security_cookie
0x1800632c3  xor     rax, rsp
0x1800632c6  mov     [rbp+1E0h+var_50], rax
0x1800632cd  mov     r13, rcx
0x1800632d0  xor     r15d, r15d
0x1800632d3  mov     r12d, r15d
0x1800632d6  xorps   xmm0, xmm0
0x1800632d9  movdqu  [rsp+2E0h+var_288], xmm0
0x1800632df  mov     [rsp+2E0h+var_278], r15
0x1800632e4  mov     r8d, 2001Fh
0x1800632ea  mov     rdx, rcx
0x1800632ed  lea     rcx, [rsp+2E0h+hKey]
0x1800632f2  call    ?GetHostSessionSubKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z; GetHostSessionSubKey(ushort const *,ulong)
0x1800632f7  nop
0x1800632f8  mov     rbx, [rsp+2E0h+hKey]
0x1800632fd  test    rbx, rbx
0x180063300  jz      loc_1800633E5
0x180063306  mov     rdx, rbx
0x180063309  lea     rcx, [rsp+2E0h+var_270]
0x18006330e  call    ?FindActivePidsForExperience@detail@@YA?AV?$vector@KV?$allocator@K@std@@@std@@PEAUHKEY__@@@Z; detail::FindActivePidsForExperience(HKEY__ *)
0x180063313  mov     rdi, rax
0x180063316  lea     rax, [rsp+2E0h+var_288]
0x18006331b  cmp     rax, rdi
0x18006331e  jz      short loc_180063357
0x180063320  lea     rcx, [rsp+2E0h+var_288]
0x180063325  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18006332a  mov     r14, [rdi]
0x18006332d  mov     qword ptr [rsp+2E0h+var_288], r14
0x180063332  mov     rsi, [rdi+8]
0x180063336  mov     qword ptr [rsp+2E0h+var_288+8], rsi
0x18006333b  mov     rax, [rdi+10h]
0x18006333f  mov     [rsp+2E0h+var_278], rax
0x180063344  mov     [rdi], r15
0x180063347  mov     [rdi+8], r15
0x18006334b  mov     [rdi+10h], r15
0x18006334f  mov     rdi, r14
0x180063352  mov     r15, rsi
0x180063355  jmp     short loc_180063363
0x180063357  xor     edi, edi
0x180063359  mov     rsi, qword ptr [rsp+2E0h+var_288+8]
0x18006335e  mov     r14, qword ptr [rsp+2E0h+var_288]
0x180063363  lea     rcx, [rsp+2E0h+var_270]
0x180063368  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18006336d  jmp     short loc_180063380
0x18006336f  mov     edx, [rdi]
0x180063371  mov     rcx, rbx
0x180063374  call    ?ReadDelayReasonsForPid@detail@@YA?AW4ExperienceRolloutDelayReasons@@PEAUHKEY__@@K@Z; detail::ReadDelayReasonsForPid(HKEY__ *,ulong)
0x180063379  or      r12d, eax
0x18006337c  add     rdi, 4
0x180063380  cmp     rdi, r15
0x180063383  jnz     short loc_18006336F
0x180063385  xor     r15d, r15d
0x180063388  test    rbx, rbx
0x18006338b  jz      short loc_180063396
0x18006338d  mov     rcx, rbx; hKey
0x180063390  call    cs:__imp_RegCloseKey
0x180063396  cmp     r14, rsi
0x180063399  jz      loc_1800634B5
0x18006339f  mov     [rsp+2E0h+var_298], r15
0x1800633a4  lea     rcx, [rsp+2E0h+var_298]
0x1800633a9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800633ae  mov     r9, rax; HKEY *
0x1800633b1  mov     edx, 20019h; samDesired
0x1800633b6  lea     rcx, aShelluihosts; "ShellUIHosts"
0x1800633bd  call    ?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)
0x1800633c2  test    eax, eax
0x1800633c4  js      loc_1800634A4
0x1800633ca  mov     edi, r15d
0x1800633cd  xor     edx, edx; Val
0x1800633cf  mov     r8d, 200h; Size
0x1800633d5  lea     rcx, [rbp+1E0h+SubKey]; void *
0x1800633d9  call    memset_0
0x1800633de  xor     edx, edx
0x1800633e0  jmp     loc_180063469
0x1800633e5  mov     rsi, qword ptr [rsp+2E0h+var_288+8]
0x1800633ea  mov     r14, qword ptr [rsp+2E0h+var_288]
0x1800633ef  jmp     short loc_180063388
0x1800633f1  test    eax, eax
0x1800633f3  jnz     loc_1800634A4
0x1800633f9  mov     rdx, r13
0x1800633fc  lea     rcx, [rbp+1E0h+SubKey]
0x180063400  call    cs:__imp__o__wcsicmp
0x180063406  test    eax, eax
0x180063408  jz      short loc_180063465
0x18006340a  mov     [rsp+2E0h+hKey], r15
0x18006340f  lea     rax, [rsp+2E0h+hKey]
0x180063414  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180063419  mov     r9d, 20019h; samDesired
0x18006341f  xor     r8d, r8d; ulOptions
0x180063422  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180063426  mov     rcx, [rsp+2E0h+var_298]; hKey
0x18006342b  call    cs:__imp_RegOpenKeyExW
0x180063431  test    eax, eax
0x180063433  jnz     short loc_180063455
0x180063435  mov     rbx, r14
0x180063438  cmp     r14, rsi
0x18006343b  jz      short loc_180063455
0x18006343d  mov     edx, [rbx]
0x18006343f  mov     rcx, [rsp+2E0h+hKey]
0x180063444  call    ?ReadDelayReasonsForPid@detail@@YA?AW4ExperienceRolloutDelayReasons@@PEAUHKEY__@@K@Z; detail::ReadDelayReasonsForPid(HKEY__ *,ulong)
0x180063449  or      r12d, eax
0x18006344c  add     rbx, 4
0x180063450  cmp     rbx, rsi
0x180063453  jnz     short loc_18006343D
0x180063455  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18006345a  test    rcx, rcx
0x18006345d  jz      short loc_180063465
0x18006345f  call    cs:__imp_RegCloseKey
0x180063465  inc     edi
0x180063467  mov     edx, edi; dwIndex
0x180063469  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18006346e  mov     [rsp+2E0h+lpcchClass], r15; lpcchClass
0x180063473  mov     [rsp+2E0h+lpClass], r15; lpClass
0x180063478  mov     [rsp+2E0h+phkResult], r15; lpReserved
0x18006347d  mov     [rsp+2E0h+cchName], 100h
0x180063485  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x18006348a  lea     r8, [rbp+1E0h+SubKey]; lpName
0x18006348e  mov     rcx, [rsp+2E0h+var_298]; hKey
0x180063493  call    cs:__imp_RegEnumKeyExW
0x180063499  cmp     eax, 103h
0x18006349e  jnz     loc_1800633F1
0x1800634a4  mov     rcx, [rsp+2E0h+var_298]; hKey
0x1800634a9  test    rcx, rcx
0x1800634ac  jz      short loc_1800634B5
0x1800634ae  call    cs:__imp_RegCloseKey
0x1800634b4  nop
0x1800634b5  lea     rcx, [rsp+2E0h+var_288]
0x1800634ba  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x1800634bf  mov     eax, r12d
0x1800634c2  mov     rcx, [rbp+1E0h+var_50]
0x1800634c9  xor     rcx, rsp; StackCookie
0x1800634cc  call    __security_check_cookie
0x1800634d1  add     rsp, 2A8h
0x1800634d8  pop     r15
0x1800634da  pop     r14
0x1800634dc  pop     r13
0x1800634de  pop     r12
0x1800634e0  pop     rdi
0x1800634e1  pop     rsi
0x1800634e2  pop     rbx
0x1800634e3  pop     rbp
0x1800634e4  retn
```
