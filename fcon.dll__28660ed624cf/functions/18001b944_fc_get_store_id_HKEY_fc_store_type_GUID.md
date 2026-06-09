# fc::get_store_id(HKEY__ *,fc::store_type,_GUID &)

- ea: `0x18001b944`
- end: `0x18001bab7`
- name: `?get_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEAU_GUID@@@Z`
- size: `371`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c088`
- `0x18001c624`
- `0x180020a74`
- `0x180021098`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180016698`
- `0x180018a90`
- `0x18001b944`
- `0x18001bac0`
- `0x18001e820`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ba1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ba1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b9a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b9a5`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001ba6a`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001ba6a`

## pseudocode

```c
__int64 __fastcall fc::get_store_id(HKEY a1, unsigned int a2, GUID *a3)
{
  LSTATUS v6; // eax
  __int64 v7; // rdx
  const WCHAR *store_id_reg_value_name; // rax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  HRESULT v12; // eax
  int phkResult; // [rsp+20h] [rbp-59h]
  DWORD Type; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-39h] BYREF
  GUID iid; // [rsp+48h] [rbp-31h] BYREF
  OLECHAR Data[40]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  hKey = 0;
  *a3 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    a3);
  v6 = RegOpenKeyExW(a1, L"SYSTEM\\Software\\Microsoft\\FT", 0, 0x20019u, &hKey);
  if ( v6 == 2 )
    goto LABEL_17;
  if ( v6 < 0 )
  {
    v7 = 565;
LABEL_11:
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v7,
           (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_utilities.h",
           (const char *)(unsigned int)v6,
           phkResult);
    goto LABEL_18;
  }
  store_id_reg_value_name = (const WCHAR *)fc::get_store_id_reg_value_name(a2);
  if ( store_id_reg_value_name )
  {
    cbData = 78;
    Type = 0;
    v6 = RegQueryValueExW(hKey, store_id_reg_value_name, 0, &Type, (LPBYTE)Data, &cbData);
    if ( v6 != 2 )
    {
      if ( v6 < 0 )
      {
        v7 = 577;
        goto LABEL_11;
      }
      if ( Type != 1 )
      {
        v9 = -2147024885;
        v10 = 578;
        goto LABEL_6;
      }
      iid = 0;
      v12 = IIDFromString(Data, &iid);
      v9 = v12;
      if ( v12 < 0 )
      {
        v11 = (unsigned int)v12;
        v10 = 581;
        goto LABEL_7;
      }
      *a3 = iid;
    }
LABEL_17:
    v9 = 0;
    goto LABEL_18;
  }
  v9 = -2147024809;
  v10 = 569;
LABEL_6:
  v11 = v9;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_utilities.h",
    (const char *)v11,
    phkResult);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x18001b944  mov     [rsp-8+arg_18], rbx
0x18001b949  push    rbp
0x18001b94a  push    rsi
0x18001b94b  push    rdi
0x18001b94c  lea     rbp, [rsp-47h]
0x18001b951  sub     rsp, 0C0h
0x18001b958  mov     rax, cs:__security_cookie
0x18001b95f  xor     rax, rsp
0x18001b962  mov     [rbp+57h+var_20], rax
0x18001b966  mov     esi, edx
0x18001b968  mov     [rbp+57h+hKey], 0
0x18001b970  mov     rbx, rcx
0x18001b973  xorps   xmm0, xmm0
0x18001b976  xor     edx, edx
0x18001b978  lea     rcx, [rbp+57h+hKey]
0x18001b97c  movdqu  xmmword ptr [r8], xmm0
0x18001b981  mov     rdi, r8
0x18001b984  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001b989  lea     rax, [rbp+57h+hKey]
0x18001b98d  mov     r9d, 20019h; samDesired
0x18001b993  xor     r8d, r8d; ulOptions
0x18001b996  mov     [rsp+0D0h+phkResult], rax; int
0x18001b99b  lea     rdx, SubKey; "SYSTEM\\Software\\Microsoft\\FT"
0x18001b9a2  mov     rcx, rbx; hKey
0x18001b9a5  call    cs:__imp_RegOpenKeyExW
0x18001b9ab  cmp     eax, 2
0x18001b9ae  jz      loc_18001BA8B
0x18001b9b4  test    eax, eax
0x18001b9b6  jns     short loc_18001B9BF
0x18001b9b8  mov     edx, 235h
0x18001b9bd  jmp     short loc_18001BA2F
0x18001b9bf  mov     ecx, esi
0x18001b9c1  call    ?get_store_id_reg_value_name@fc@@YAPEBGW4store_type@1@@Z; fc::get_store_id_reg_value_name(fc::store_type)
0x18001b9c6  test    rax, rax
0x18001b9c9  jnz     short loc_18001B9ED
0x18001b9cb  mov     ebx, 80070057h
0x18001b9d0  mov     edx, 239h; void *
0x18001b9d5  mov     r9d, ebx; char *
0x18001b9d8  mov     rcx, [rbp+5Fh]; this
0x18001b9dc  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001b9e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9e8  jmp     loc_18001BA8D
0x18001b9ed  lea     rcx, [rbp+57h+cbData]
0x18001b9f1  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x18001b9f8  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x18001b9fd  lea     r9, [rbp+57h+Type]; lpType
0x18001ba01  lea     rcx, [rbp+57h+Data]
0x18001ba05  mov     [rbp+57h+Type], 0
0x18001ba0c  mov     [rsp+0D0h+phkResult], rcx; int
0x18001ba11  xor     r8d, r8d; lpReserved
0x18001ba14  mov     rcx, [rbp+57h+hKey]; hKey
0x18001ba18  mov     rdx, rax; lpValueName
0x18001ba1b  call    cs:__imp_RegQueryValueExW
0x18001ba21  cmp     eax, 2
0x18001ba24  jz      short loc_18001BA8B
0x18001ba26  test    eax, eax
0x18001ba28  jns     short loc_18001BA46
0x18001ba2a  mov     edx, 241h; void *
0x18001ba2f  mov     rcx, [rbp+5Fh]; this
0x18001ba33  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001ba3a  mov     r9d, eax; char *
0x18001ba3d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001ba42  mov     ebx, eax
0x18001ba44  jmp     short loc_18001BA8D
0x18001ba46  cmp     [rbp+57h+Type], 1
0x18001ba4a  jz      short loc_18001BA5B
0x18001ba4c  mov     ebx, 8007000Bh
0x18001ba51  mov     edx, 242h
0x18001ba56  jmp     loc_18001B9D5
0x18001ba5b  xorps   xmm0, xmm0
0x18001ba5e  lea     rdx, [rbp+57h+iid]; lpiid
0x18001ba62  lea     rcx, [rbp+57h+Data]; lpsz
0x18001ba66  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18001ba6a  call    cs:__imp_IIDFromString
0x18001ba70  mov     ebx, eax
0x18001ba72  test    eax, eax
0x18001ba74  jns     short loc_18001BA83
0x18001ba76  mov     r9d, eax
0x18001ba79  mov     edx, 245h
0x18001ba7e  jmp     loc_18001B9D8
0x18001ba83  movups  xmm0, xmmword ptr [rbp+57h+iid.Data1]
0x18001ba87  movdqu  xmmword ptr [rdi], xmm0
0x18001ba8b  xor     ebx, ebx
0x18001ba8d  lea     rcx, [rbp+57h+hKey]
0x18001ba91  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001ba96  mov     eax, ebx
0x18001ba98  mov     rcx, [rbp+57h+var_20]
0x18001ba9c  xor     rcx, rsp; StackCookie
0x18001ba9f  call    __security_check_cookie
0x18001baa4  mov     rbx, [rsp+0D0h+arg_18]
0x18001baac  add     rsp, 0C0h
0x18001bab3  pop     rdi
0x18001bab4  pop     rsi
0x18001bab5  pop     rbp
0x18001bab6  retn
```
