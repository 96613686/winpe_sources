# GetAllowEmbeddedMode(int *)

- ea: `0x1800180a4`
- end: `0x180018216`
- name: `?GetAllowEmbeddedMode@@YAJPEAH@Z`
- size: `370`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180008018`

## callees

- `0x180003940`
- `0x18001053c`
- `0x180010558`
- `0x1800180a4`
- `0x180018590`
- `0x180018754`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800181ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800181ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001812b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001818a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001812b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001818a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800180fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800180fe`

## string_xrefs

- `0x1800180ef`: `System\CurrentControlSet\Services\EmbeddedMode\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetAllowEmbeddedMode(int *a1)
{
  unsigned int v3; // eax
  int found; // eax
  unsigned int v5; // ebx
  LPBYTE v6; // rbx
  bool v7; // sf
  DWORD v8; // eax
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  LPBYTE v11; // [rsp+60h] [rbp+30h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v11 = 0;
  cbData = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\EmbeddedMode\\Parameters",
         0,
         0x20019u,
         &hKey);
  if ( v3 || (v3 = RegQueryValueExW(hKey, L"Flags", 0, 0, 0, &cbData)) != 0 )
  {
    found = VerifyFileNotFoundError(a1, v3);
  }
  else
  {
    v11 = (LPBYTE)operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v11;
    if ( !v11 )
    {
      v5 = -2147024882;
      goto LABEL_19;
    }
    found = RegQueryValueExW(hKey, L"Flags", 0, 0, v11, &cbData);
    v7 = found < 0;
    if ( found > 0 )
    {
      found = (unsigned __int16)found | 0x80070000;
      v7 = found < 0;
    }
    if ( !v7 )
    {
      v8 = cbData;
      if ( cbData != 4 || *(_DWORD *)v6 )
      {
        if ( !g_isSMBiosUniqueIdHashInitialized )
        {
          InitOnceExecuteOnce(&g_initSMBiosUniqueIdHash, InitializeSMBiosUniqueIdHashHandler, 0, 0);
          v8 = cbData;
        }
        if ( (_DWORD)g_smbiosUniqueIdHashLength == v8 )
          *a1 = memcmp_0(g_smbiosUniqueIdHash, v6, (unsigned int)g_smbiosUniqueIdHashLength) == 0;
      }
      v5 = 0;
      goto LABEL_19;
    }
  }
  v5 = found;
LABEL_19:
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x1800180a4  push    rbp
0x1800180a6  push    rbx
0x1800180a7  push    rdi
0x1800180a8  mov     rbp, rsp
0x1800180ab  sub     rsp, 30h
0x1800180af  mov     rdi, rcx
0x1800180b2  test    rcx, rcx
0x1800180b5  jnz     short loc_1800180C1
0x1800180b7  mov     eax, 80004003h
0x1800180bc  jmp     loc_18001820E
0x1800180c1  mov     dword ptr [rcx], 0
0x1800180c7  lea     rax, [rbp+hKey]
0x1800180cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800180d2  mov     [rsp+30h+phkResult], rax; phkResult
0x1800180d7  mov     r9d, 20019h; samDesired
0x1800180dd  mov     [rbp+arg_10], 0
0x1800180e5  xor     r8d, r8d; ulOptions
0x1800180e8  mov     [rbp+cbData], 0
0x1800180ef  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Em"...
0x1800180f6  mov     [rbp+hKey], 0
0x1800180fe  call    cs:__imp_RegOpenKeyExW
0x180018104  test    eax, eax
0x180018106  jnz     short loc_180018135
0x180018108  mov     rcx, [rbp+hKey]; hKey
0x18001810c  lea     rax, [rbp+cbData]
0x180018110  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180018115  lea     rdx, ValueName; "Flags"
0x18001811c  xor     r9d, r9d; lpType
0x18001811f  mov     [rsp+30h+phkResult], 0; lpData
0x180018128  xor     r8d, r8d; lpReserved
0x18001812b  call    cs:__imp_RegQueryValueExW
0x180018131  test    eax, eax
0x180018133  jz      short loc_180018146
0x180018135  mov     edx, eax
0x180018137  mov     rcx, rdi
0x18001813a  call    VerifyFileNotFoundError
0x18001813f  mov     ebx, eax
0x180018141  jmp     loc_1800181FA
0x180018146  mov     ecx, [rbp+cbData]; unsigned __int64
0x180018149  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018150  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018155  mov     [rbp+arg_10], rax
0x180018159  mov     rbx, rax
0x18001815c  test    rax, rax
0x18001815f  jnz     short loc_18001816B
0x180018161  mov     ebx, 8007000Eh
0x180018166  jmp     loc_1800181FA
0x18001816b  mov     rcx, [rbp+hKey]; hKey
0x18001816f  lea     rax, [rbp+cbData]
0x180018173  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180018178  lea     rdx, ValueName; "Flags"
0x18001817f  xor     r9d, r9d; lpType
0x180018182  mov     [rsp+30h+phkResult], rbx; lpData
0x180018187  xor     r8d, r8d; lpReserved
0x18001818a  call    cs:__imp_RegQueryValueExW
0x180018190  test    eax, eax
0x180018192  jle     short loc_18001819E
0x180018194  movzx   eax, ax
0x180018197  or      eax, 80070000h
0x18001819c  test    eax, eax
0x18001819e  js      short loc_18001813F
0x1800181a0  mov     eax, [rbp+cbData]
0x1800181a3  cmp     eax, 4
0x1800181a6  jnz     short loc_1800181AD
0x1800181a8  cmp     dword ptr [rbx], 0
0x1800181ab  jz      short loc_1800181F8
0x1800181ad  cmp     cs:?g_isSMBiosUniqueIdHashInitialized@@3HA, 0; int g_isSMBiosUniqueIdHashInitialized
0x1800181b4  jnz     short loc_1800181D3
0x1800181b6  xor     r9d, r9d; Context
0x1800181b9  lea     rdx, ?InitializeSMBiosUniqueIdHashHandler@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800181c0  xor     r8d, r8d; Parameter
0x1800181c3  lea     rcx, ?g_initSMBiosUniqueIdHash@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800181ca  call    cs:__imp_InitOnceExecuteOnce
0x1800181d0  mov     eax, [rbp+cbData]
0x1800181d3  mov     ecx, cs:?g_smbiosUniqueIdHashLength@@3KA; ulong g_smbiosUniqueIdHashLength
0x1800181d9  cmp     ecx, eax
0x1800181db  jnz     short loc_1800181F8
0x1800181dd  mov     r8d, ecx; Size
0x1800181e0  mov     rdx, rbx; Buf2
0x1800181e3  mov     rcx, cs:?g_smbiosUniqueIdHash@@3V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@A; Buf1
0x1800181ea  call    memcmp_0
0x1800181ef  xor     ecx, ecx
0x1800181f1  test    eax, eax
0x1800181f3  setz    cl
0x1800181f6  mov     [rdi], ecx
0x1800181f8  xor     ebx, ebx
0x1800181fa  lea     rcx, [rbp+arg_10]
0x1800181fe  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180018203  lea     rcx, [rbp+hKey]
0x180018207  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001820c  mov     eax, ebx
0x18001820e  add     rsp, 30h
0x180018212  pop     rdi
0x180018213  pop     rbx
0x180018214  pop     rbp
0x180018215  retn
```
