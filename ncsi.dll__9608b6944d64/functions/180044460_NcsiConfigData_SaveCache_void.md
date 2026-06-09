# NcsiConfigData::SaveCache(void)

- ea: `0x180044460`
- end: `0x180044577`
- name: `?SaveCache@NcsiConfigData@@QEAAXXZ`
- size: `279`
- prototype: `void __fastcall(NcsiConfigData *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002c150`
- `0x180044350`

## callees

- `0x180011a58`
- `0x18002d6a0`
- `0x180044460`
- `0x180047240`
- `0x180061af4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444af`

## pseudocode

```c
void __fastcall NcsiConfigData::SaveCache(NcsiConfigData *this)
{
  const WCHAR *v1; // rdx
  unsigned int v2; // eax
  HKEY v3; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v1 = (const WCHAR *)&qword_18009AA80;
  if ( (unsigned __int64)qword_18009AA98 > 7 )
    v1 = qword_18009AA80;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 2u, &phkResult);
  if ( v2 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v2);
    }
  }
  else
  {
    v3 = phkResult;
    PhysicalAddressCache::SaveToRegistry((PhysicalAddressCache *)&qword_18009AB80, phkResult);
    PhysicalAddressCache::SaveToRegistry((PhysicalAddressCache *)&qword_18009ABE0, v3);
    PhysicalAddressCache::SaveToRegistry((PhysicalAddressCache *)&qword_18009AC40, v3);
    PhysicalAddressCache::SaveToRegistry((PhysicalAddressCache *)&qword_18009ACA0, v3);
    PhysicalAddressCache::SaveToRegistry((PhysicalAddressCache *)&qword_18009AD00, v3);
    PhysicalAddressCache::SaveToRegistry((PhysicalAddressCache *)&qword_18009AD60, v3);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
}

```

## disassembly

```asm
0x180044460  push    rbx
0x180044462  sub     rsp, 40h
0x180044466  mov     rax, cs:__security_cookie
0x18004446d  xor     rax, rsp
0x180044470  mov     [rsp+48h+var_10], rax
0x180044475  mov     [rsp+48h+var_18], 0
0x18004447e  lea     rdx, qword_18009AA80
0x180044485  cmp     cs:qword_18009AA98, 7
0x18004448d  cmova   rdx, cs:qword_18009AA80; lpSubKey
0x180044495  lea     rax, [rsp+48h+var_18]
0x18004449a  mov     [rsp+48h+phkResult], rax; phkResult
0x18004449f  mov     r9d, 2; samDesired
0x1800444a5  xor     r8d, r8d; ulOptions
0x1800444a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800444af  call    cs:__imp_RegOpenKeyExW
0x1800444b5  test    eax, eax
0x1800444b7  jz      short loc_1800444FA
0x1800444b9  lea     rdx, WPP_GLOBAL_Control
0x1800444c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800444c7  cmp     rcx, rdx
0x1800444ca  jz      loc_18004455A
0x1800444d0  test    byte ptr [rcx+1Ch], 10h
0x1800444d4  jz      loc_18004455A
0x1800444da  cmp     byte ptr [rcx+19h], 2
0x1800444de  jb      short loc_18004455A
0x1800444e0  mov     edx, 24h ; '$'
0x1800444e5  mov     r9d, eax
0x1800444e8  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x1800444ef  mov     rcx, [rcx+10h]
0x1800444f3  call    WPP_SF_d
0x1800444f8  jmp     short loc_18004455A
0x1800444fa  mov     rbx, [rsp+48h+var_18]
0x1800444ff  mov     rdx, rbx; HKEY
0x180044502  lea     rcx, qword_18009AB80; this
0x180044509  call    ?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z; PhysicalAddressCache::SaveToRegistry(HKEY__ *)
0x18004450e  mov     rdx, rbx; HKEY
0x180044511  lea     rcx, qword_18009ABE0; this
0x180044518  call    ?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z; PhysicalAddressCache::SaveToRegistry(HKEY__ *)
0x18004451d  mov     rdx, rbx; HKEY
0x180044520  lea     rcx, qword_18009AC40; this
0x180044527  call    ?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z; PhysicalAddressCache::SaveToRegistry(HKEY__ *)
0x18004452c  mov     rdx, rbx; HKEY
0x18004452f  lea     rcx, qword_18009ACA0; this
0x180044536  call    ?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z; PhysicalAddressCache::SaveToRegistry(HKEY__ *)
0x18004453b  mov     rdx, rbx; HKEY
0x18004453e  lea     rcx, qword_18009AD00; this
0x180044545  call    ?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z; PhysicalAddressCache::SaveToRegistry(HKEY__ *)
0x18004454a  mov     rdx, rbx; HKEY
0x18004454d  lea     rcx, qword_18009AD60; this
0x180044554  call    ?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z; PhysicalAddressCache::SaveToRegistry(HKEY__ *)
0x180044559  nop
0x18004455a  lea     rcx, [rsp+48h+var_18]
0x18004455f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044564  mov     rcx, [rsp+48h+var_10]
0x180044569  xor     rcx, rsp; StackCookie
0x18004456c  call    __security_check_cookie
0x180044571  add     rsp, 40h
0x180044575  pop     rbx
0x180044576  retn
```
