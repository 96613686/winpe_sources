# ResourceManager::CleanLeakedTH2Biometrics(ushort const *)

- ea: `0x180013ec0`
- end: `0x1800140ad`
- name: `?CleanLeakedTH2Biometrics@ResourceManager@@SAXPEBG@Z`
- size: `493`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800200f0`
- `0x18006b980`

## callees

- `0x180013ec0`
- `0x1800140b4`
- `0x18001e770`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180078034`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180013ff7`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180013ff7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f54`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013fa3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014042`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013fa3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014080`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001406a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001406a`
- `DMCmnUtils!BigStrcat` at `0x180013efe`
- `DMCmnUtils!BigStrcat` at `0x180013efe`

## pseudocode

```c
void __fastcall ResourceManager::CleanLeakedTH2Biometrics(const unsigned __int16 *a1)
{
  const WCHAR *v1; // rbx
  unsigned int v2; // ebx
  HKEY v3; // rcx
  HKEY hkey; // [rsp+40h] [rbp-59h] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-51h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-4Dh] BYREF
  DWORD v7; // [rsp+50h] [rbp-49h] BYREF
  const WCHAR *v8; // [rsp+58h] [rbp-41h] BYREF
  WCHAR Value[4]; // [rsp+60h] [rbp-39h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-31h] BYREF
  char v11; // [rsp+70h] [rbp-29h]
  wchar_t String1[48]; // [rsp+80h] [rbp-19h] BYREF

  v1 = BigStrcat(3u, L"SOFTWARE\\Microsoft\\EnterpriseResourceManager\\Tracked\\", a1, L"\\device\\default");
  LocalFree(0);
  v8 = v1;
  if ( v1 )
  {
    hkey = 0;
    *(_QWORD *)Value = &hkey;
    phkResult = 0;
    v11 = 1;
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20019u, &phkResult);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(Value);
    v3 = hkey;
    if ( !v2 )
    {
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"count", 0x10u, 0, &pvData, &pcbData) )
      {
        while ( v2 < pvData )
        {
          if ( v2 > 0x63 )
            break;
          *(_QWORD *)Value = 0x68007400610050LL;
          LOBYTE(phkResult) = 88;
          *(_DWORD *)((char *)&phkResult + 1) = *(_DWORD *)((char *)L"XX" + 1);
          BYTE5(phkResult) = HIBYTE(aPathxx[6]);
          if ( (unsigned int)_o__itow_s(v2, &phkResult, 2) )
            break;
          memset_0(String1, 0, 0x54u);
          v7 = 84;
          if ( RegGetValueW(hkey, 0, Value, 2u, 0, String1, &v7) )
            break;
          if ( !wcscmp_0(String1, L"./Vendor/MSFT/PassportForWork/Biometrics") )
            RegDeleteKeyValueW(hkey, 0, Value);
          ++v2;
        }
      }
      v3 = hkey;
    }
    if ( v3 )
      RegCloseKey(v3);
  }
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v8);
}

```

## disassembly

```asm
0x180013ec0  mov     [rsp-8+arg_8], rbx
0x180013ec5  push    rbp
0x180013ec6  lea     rbp, [rsp-57h]
0x180013ecb  sub     rsp, 0F0h
0x180013ed2  mov     rax, cs:__security_cookie
0x180013ed9  xor     rax, rsp
0x180013edc  mov     [rbp+57h+var_10], rax
0x180013ee0  mov     [rbp+57h+var_98], 0
0x180013ee8  lea     r9, aDeviceDefault; "\\device\\default"
0x180013eef  mov     r8, rcx
0x180013ef2  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\EnterpriseResource"...
0x180013ef9  mov     ecx, 3
0x180013efe  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x180013f04  mov     rbx, rax
0x180013f07  xor     ecx, ecx; hMem
0x180013f09  call    cs:__imp_LocalFree
0x180013f0f  mov     [rbp+57h+var_98], rbx
0x180013f13  test    rbx, rbx
0x180013f16  jz      loc_180014087
0x180013f1c  mov     [rbp+57h+hkey], 0
0x180013f24  lea     rax, [rbp+57h+hkey]
0x180013f28  mov     qword ptr [rbp+57h+Value], rax
0x180013f2c  mov     [rbp+57h+var_88], 0
0x180013f34  mov     [rbp+57h+var_80], 1
0x180013f38  lea     rax, [rbp+57h+var_88]
0x180013f3c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180013f41  mov     r9d, 20019h; samDesired
0x180013f47  xor     r8d, r8d; ulOptions
0x180013f4a  mov     rdx, rbx; lpSubKey
0x180013f4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013f54  call    cs:__imp_RegOpenKeyExW
0x180013f5a  mov     ebx, eax
0x180013f5c  lea     rcx, [rbp+57h+Value]
0x180013f60  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180013f65  mov     rcx, [rbp+57h+hkey]; hkey
0x180013f69  test    ebx, ebx
0x180013f6b  jnz     loc_18001407B
0x180013f71  mov     [rbp+57h+var_A8], ebx
0x180013f74  mov     [rbp+57h+var_A4], 4
0x180013f7b  lea     rax, [rbp+57h+var_A4]
0x180013f7f  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180013f84  lea     rax, [rbp+57h+var_A8]
0x180013f88  mov     [rsp+0F0h+pvData], rax; pvData
0x180013f8d  mov     [rsp+0F0h+phkResult], 0; pdwType
0x180013f96  lea     r9d, [rbx+10h]; dwFlags
0x180013f9a  lea     r8, aCount; "count"
0x180013fa1  xor     edx, edx; lpSubKey
0x180013fa3  call    cs:__imp_RegGetValueW
0x180013fa9  test    eax, eax
0x180013fab  jnz     loc_180014077
0x180013fb1  cmp     ebx, [rbp+57h+var_A8]
0x180013fb4  jnb     loc_180014077
0x180013fba  cmp     ebx, 63h ; 'c'
0x180013fbd  ja      loc_180014077
0x180013fc3  mov     rax, 68007400610050h
0x180013fcd  mov     qword ptr [rbp+57h+Value], rax
0x180013fd1  mov     byte ptr [rbp+57h+var_88], 58h ; 'X'
0x180013fd5  mov     eax, dword ptr cs:aPathxx+9; "堀"
0x180013fdb  mov     dword ptr [rbp+57h+var_88+1], eax
0x180013fde  mov     al, byte ptr cs:aPathxx+0Dh; ""
0x180013fe4  mov     byte ptr [rbp+57h+var_88+5], al
0x180013fe7  mov     r9d, 0Ah
0x180013fed  lea     r8d, [r9-8]
0x180013ff1  lea     rdx, [rbp+57h+var_88]
0x180013ff5  mov     ecx, ebx
0x180013ff7  call    cs:__imp__o__itow_s
0x180013ffd  test    eax, eax
0x180013fff  jnz     short loc_180014077
0x180014001  xor     edx, edx; Val
0x180014003  lea     r8d, [rax+54h]; Size
0x180014007  lea     rcx, [rbp+57h+String1]; void *
0x18001400b  call    memset_0
0x180014010  mov     [rbp+57h+var_A0], 54h ; 'T'
0x180014017  lea     rax, [rbp+57h+var_A0]
0x18001401b  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180014020  lea     rax, [rbp+57h+String1]
0x180014024  mov     [rsp+0F0h+pvData], rax; pvData
0x180014029  mov     [rsp+0F0h+phkResult], 0; pdwType
0x180014032  mov     r9d, 2; dwFlags
0x180014038  lea     r8, [rbp+57h+Value]; lpValue
0x18001403c  xor     edx, edx; lpSubKey
0x18001403e  mov     rcx, [rbp+57h+hkey]; hkey
0x180014042  call    cs:__imp_RegGetValueW
0x180014048  test    eax, eax
0x18001404a  jnz     short loc_180014077
0x18001404c  lea     rdx, aVendorMsftPass; "./Vendor/MSFT/PassportForWork/Biometric"...
0x180014053  lea     rcx, [rbp+57h+String1]; String1
0x180014057  call    wcscmp_0
0x18001405c  test    eax, eax
0x18001405e  jnz     short loc_180014070
0x180014060  lea     r8, [rbp+57h+Value]; lpValueName
0x180014064  xor     edx, edx; lpSubKey
0x180014066  mov     rcx, [rbp+57h+hkey]; hKey
0x18001406a  call    cs:__imp_RegDeleteKeyValueW
0x180014070  inc     ebx
0x180014072  jmp     loc_180013FB1
0x180014077  mov     rcx, [rbp+57h+hkey]; hKey
0x18001407b  test    rcx, rcx
0x18001407e  jz      short loc_180014087
0x180014080  call    cs:__imp_RegCloseKey
0x180014086  nop
0x180014087  lea     rcx, [rbp+57h+var_98]
0x18001408b  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x180014090  mov     rcx, [rbp+57h+var_10]
0x180014094  xor     rcx, rsp; StackCookie
0x180014097  call    __security_check_cookie
0x18001409c  mov     rbx, [rsp+0F0h+arg_8]
0x1800140a4  add     rsp, 0F0h
0x1800140ab  pop     rbp
0x1800140ac  retn
```
