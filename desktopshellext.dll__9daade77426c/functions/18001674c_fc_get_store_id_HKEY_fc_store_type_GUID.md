# fc::get_store_id(HKEY__ *,fc::store_type,_GUID &)

- ea: `0x18001674c`
- end: `0x1800168b7`
- name: `?get_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEAU_GUID@@@Z`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800168e4`

## callees

- `0x1800108cc`
- `0x18001674c`
- `0x1800168c0`
- `0x180017988`
- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001686a`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001686a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001681d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001681d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800167de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001688e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800167de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001688e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800167a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800167a8`

## pseudocode

```c
__int64 __fastcall fc::get_store_id(HKEY a1, __int64 a2, GUID *a3)
{
  HKEY *v5; // rax
  LSTATUS v6; // eax
  __int64 v7; // rdx
  HRESULT v8; // ebx
  __int64 v10; // rdx
  int phkResult; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+30h] [rbp-29h] BYREF
  DWORD Type; // [rsp+38h] [rbp-21h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Dh] BYREF
  GUID iid; // [rsp+40h] [rbp-19h] BYREF
  OLECHAR Data[40]; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  hKey = 0;
  *a3 = 0;
  v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v6 = RegOpenKeyExW(a1, L"SYSTEM\\Software\\Microsoft\\FT", 0, 0x20019u, v5);
  if ( v6 != 2 )
  {
    if ( v6 < 0 )
    {
      v7 = 565;
LABEL_4:
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v7,
             (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_utilities.h",
             (const char *)(unsigned int)v6,
             phkResult);
LABEL_5:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v8;
    }
    cbData = 78;
    Type = 0;
    v6 = RegQueryValueExW(hKey, L"ExpId", 0, &Type, (LPBYTE)Data, &cbData);
    if ( v6 != 2 )
    {
      if ( v6 < 0 )
      {
        v7 = 577;
        goto LABEL_4;
      }
      if ( Type != 1 )
      {
        v8 = -2147024885;
        v10 = 578;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_utilities.h",
          (const char *)(unsigned int)v8,
          phkResult);
        goto LABEL_5;
      }
      iid = 0;
      v8 = IIDFromString(Data, &iid);
      if ( v8 < 0 )
      {
        v10 = 581;
        goto LABEL_13;
      }
      *a3 = iid;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001674c  mov     [rsp-8+arg_8], rbx
0x180016751  mov     [rsp-8+arg_18], rdi
0x180016756  push    rbp
0x180016757  lea     rbp, [rsp-57h]
0x18001675c  sub     rsp, 0B0h
0x180016763  mov     rax, cs:__security_cookie
0x18001676a  xor     rax, rsp
0x18001676d  mov     [rbp+57h+var_10], rax
0x180016771  mov     rbx, rcx
0x180016774  mov     [rbp+57h+hKey], 0
0x18001677c  xorps   xmm0, xmm0
0x18001677f  lea     rcx, [rbp+57h+hKey]
0x180016783  movdqu  xmmword ptr [r8], xmm0
0x180016788  mov     rdi, r8
0x18001678b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180016790  mov     r9d, 20019h; samDesired
0x180016796  mov     [rsp+0B0h+phkResult], rax; int
0x18001679b  xor     r8d, r8d; ulOptions
0x18001679e  lea     rdx, aSystemSoftware_0; "SYSTEM\\Software\\Microsoft\\FT"
0x1800167a5  mov     rcx, rbx; hKey
0x1800167a8  call    cs:__imp_RegOpenKeyExW
0x1800167ae  cmp     eax, 2
0x1800167b1  jz      loc_180016885
0x1800167b7  test    eax, eax
0x1800167b9  jns     short loc_1800167EB
0x1800167bb  mov     edx, 235h; void *
0x1800167c0  mov     rcx, [rbp+5Fh]; this
0x1800167c4  lea     r8, aOnecoreInterna_5; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800167cb  mov     r9d, eax; char *
0x1800167ce  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800167d3  mov     ebx, eax
0x1800167d5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800167d9  test    rcx, rcx
0x1800167dc  jz      short loc_1800167E4
0x1800167de  call    cs:__imp_RegCloseKey
0x1800167e4  mov     eax, ebx
0x1800167e6  jmp     loc_180016896
0x1800167eb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800167ef  lea     rax, [rbp+57h+cbData]
0x1800167f3  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800167f8  lea     r9, [rbp+57h+Type]; lpType
0x1800167fc  lea     rax, [rbp+57h+Data]
0x180016800  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x180016807  xor     r8d, r8d; lpReserved
0x18001680a  mov     [rsp+0B0h+phkResult], rax; int
0x18001680f  lea     rdx, ValueName; "ExpId"
0x180016816  mov     [rbp+57h+Type], 0
0x18001681d  call    cs:__imp_RegQueryValueExW
0x180016823  cmp     eax, 2
0x180016826  jz      short loc_180016885
0x180016828  test    eax, eax
0x18001682a  jns     short loc_180016833
0x18001682c  mov     edx, 241h
0x180016831  jmp     short loc_1800167C0
0x180016833  cmp     [rbp+57h+Type], 1
0x180016837  jz      short loc_18001685B
0x180016839  mov     ebx, 8007000Bh
0x18001683e  mov     edx, 242h; void *
0x180016843  mov     rcx, [rbp+5Fh]; this
0x180016847  lea     r8, aOnecoreInterna_5; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001684e  mov     r9d, ebx; char *
0x180016851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016856  jmp     loc_1800167D5
0x18001685b  xorps   xmm0, xmm0
0x18001685e  lea     rdx, [rbp+57h+iid]; lpiid
0x180016862  lea     rcx, [rbp+57h+Data]; lpsz
0x180016866  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18001686a  call    cs:__imp_IIDFromString
0x180016870  mov     ebx, eax
0x180016872  test    eax, eax
0x180016874  jns     short loc_18001687D
0x180016876  mov     edx, 245h
0x18001687b  jmp     short loc_180016843
0x18001687d  movups  xmm0, xmmword ptr [rbp+57h+iid.Data1]
0x180016881  movdqu  xmmword ptr [rdi], xmm0
0x180016885  mov     rcx, [rbp+57h+hKey]; hKey
0x180016889  test    rcx, rcx
0x18001688c  jz      short loc_180016894
0x18001688e  call    cs:__imp_RegCloseKey
0x180016894  xor     eax, eax
0x180016896  mov     rcx, [rbp+57h+var_10]
0x18001689a  xor     rcx, rsp; StackCookie
0x18001689d  call    __security_check_cookie
0x1800168a2  lea     r11, [rsp+0B0h+var_s0]
0x1800168aa  mov     rbx, [r11+18h]
0x1800168ae  mov     rdi, [r11+28h]
0x1800168b2  mov     rsp, r11
0x1800168b5  pop     rbp
0x1800168b6  retn
```
