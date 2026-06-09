# RegistryStore::RegistryStore(bool)

- ea: `0x14000e624`
- end: `0x14000e778`
- name: `??0RegistryStore@@QEAA@_N@Z`
- size: `340`
- prototype: `RegistryStore *__fastcall(RegistryStore *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d2a4`

## callees

- `0x140002630`
- `0x1400034f8`
- `0x14000e624`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000e745`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000e745`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000e755`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000e755`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000e734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e764`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e764`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000e6f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000e727`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000e6f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000e727`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e6c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e6c6`

## pseudocode

```c
RegistryStore *__fastcall RegistryStore::RegistryStore(RegistryStore *this, char a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _DWORD *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v4 = operator new(0x30u);
  *v4 = v4;
  v4[1] = v4;
  *(_QWORD *)this = v4;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  *((_QWORD *)this + 2) = v5;
  *((_BYTE *)this + 32) = a2;
  *((_DWORD *)this + 9) = 0;
  v6 = (_DWORD *)((char *)this + 40);
  *((_DWORD *)this + 10) = 5;
  if ( a2 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Print\\EDU",
            0,
            0x20019u,
            &hKey) )
    {
      Type = 0;
      cbData = 4;
      RegQueryValueExW(hKey, L"MaxRetryCount", 0, &Type, (LPBYTE)this + 40, &cbData);
      *((_DWORD *)this + 9) = *v6;
      cbData = 4;
      RegQueryValueExW(hKey, L"RetryCount", 0, &Type, (LPBYTE)this + 36, &cbData);
    }
    v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"MaxRetryCount = ");
    v8 = std::basic_ostream<unsigned short>::operator<<(v7, (unsigned int)*v6);
    std::basic_ostream<unsigned short>::operator<<(v8, std::endl<unsigned short,std::char_traits<unsigned short>>);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return this;
}

```

## disassembly

```asm
0x14000e624  push    rbp
0x14000e626  push    rbx
0x14000e627  push    rsi
0x14000e628  push    rdi
0x14000e629  push    r14
0x14000e62b  mov     rbp, rsp
0x14000e62e  sub     rsp, 30h
0x14000e632  mov     bl, dl
0x14000e634  mov     rdi, rcx
0x14000e637  mov     qword ptr [rcx], 0
0x14000e63e  mov     qword ptr [rcx+8], 0
0x14000e646  mov     esi, 30h ; '0'
0x14000e64b  mov     ecx, esi; Size
0x14000e64d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e652  mov     [rax], rax
0x14000e655  mov     [rax+8], rax
0x14000e659  mov     [rdi], rax
0x14000e65c  mov     qword ptr [rdi+10h], 0
0x14000e664  mov     qword ptr [rdi+18h], 0
0x14000e66c  mov     ecx, esi; Size
0x14000e66e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e673  mov     [rax], rax
0x14000e676  mov     [rax+8], rax
0x14000e67a  mov     [rdi+10h], rax
0x14000e67e  mov     [rdi+20h], bl
0x14000e681  lea     r14, [rdi+24h]
0x14000e685  mov     dword ptr [r14], 0
0x14000e68c  lea     rsi, [rdi+28h]
0x14000e690  mov     dword ptr [rsi], 5
0x14000e696  test    bl, bl
0x14000e698  jz      loc_14000E76A
0x14000e69e  mov     [rbp+hKey], 0
0x14000e6a6  lea     rax, [rbp+hKey]
0x14000e6aa  mov     [rsp+30h+phkResult], rax; phkResult
0x14000e6af  mov     r9d, 20019h; samDesired
0x14000e6b5  xor     r8d, r8d; ulOptions
0x14000e6b8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000e6bf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000e6c6  call    cs:__imp_RegOpenKeyExW
0x14000e6cc  test    eax, eax
0x14000e6ce  jnz     short loc_14000E72D
0x14000e6d0  mov     [rbp+Type], eax
0x14000e6d3  lea     ebx, [rax+4]
0x14000e6d6  mov     [rbp+cbData], ebx
0x14000e6d9  lea     rax, [rbp+cbData]
0x14000e6dd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14000e6e2  mov     [rsp+30h+phkResult], rsi; lpData
0x14000e6e7  lea     r9, [rbp+Type]; lpType
0x14000e6eb  xor     r8d, r8d; lpReserved
0x14000e6ee  lea     rdx, aMaxretrycount_1; "MaxRetryCount"
0x14000e6f5  mov     rcx, [rbp+hKey]; hKey
0x14000e6f9  call    cs:__imp_RegQueryValueExW
0x14000e6ff  mov     eax, [rsi]
0x14000e701  mov     [r14], eax
0x14000e704  mov     [rbp+cbData], ebx
0x14000e707  lea     rax, [rbp+cbData]
0x14000e70b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14000e710  mov     [rsp+30h+phkResult], r14; lpData
0x14000e715  lea     r9, [rbp+Type]; lpType
0x14000e719  xor     r8d, r8d; lpReserved
0x14000e71c  lea     rdx, aRetrycount; "RetryCount"
0x14000e723  mov     rcx, [rbp+hKey]; hKey
0x14000e727  call    cs:__imp_RegQueryValueExW
0x14000e72d  lea     rdx, aMaxretrycount_0; "MaxRetryCount = "
0x14000e734  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000e73b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000e740  mov     edx, [rsi]
0x14000e742  mov     rcx, rax
0x14000e745  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14000e74b  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000e752  mov     rcx, rax
0x14000e755  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000e75b  mov     rcx, [rbp+hKey]; hKey
0x14000e75f  test    rcx, rcx
0x14000e762  jz      short loc_14000E76A
0x14000e764  call    cs:__imp_RegCloseKey
0x14000e76a  mov     rax, rdi
0x14000e76d  add     rsp, 30h
0x14000e771  pop     r14
0x14000e773  pop     rdi
0x14000e774  pop     rsi
0x14000e775  pop     rbx
0x14000e776  pop     rbp
0x14000e777  retn
```
