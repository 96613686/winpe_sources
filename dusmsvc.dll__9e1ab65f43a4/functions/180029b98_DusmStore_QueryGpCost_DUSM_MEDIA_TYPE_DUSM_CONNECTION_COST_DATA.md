# DusmStore::QueryGpCost(_DUSM_MEDIA_TYPE,_DUSM_CONNECTION_COST_DATA *)

- ea: `0x180029b98`
- end: `0x180029ce3`
- name: `?QueryGpCost@DusmStore@@SAHW4_DUSM_MEDIA_TYPE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z`
- size: `331`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001c23c`
- `0x1800381b8`
- `0x18003aa18`
- `0x18003ccd8`
- `0x18003cd5c`

## callees

- `0x180007c90`
- `0x18001d87c`
- `0x180026fa0`
- `0x180029b98`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029c08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029c08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029c5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029c5c`

## pseudocode

```c
__int64 __fastcall DusmStore::QueryGpCost(int a1, int *a2)
{
  const WCHAR *v4; // rdx
  const WCHAR *v5; // r8
  int v6; // ecx
  const char *pvData; // [rsp+28h] [rbp-40h]
  int v9; // [rsp+40h] [rbp-28h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned int)(a1 - 2) > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::QueryGpCost::mediaType",
      pvData);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v4 = (const WCHAR *)qword_180068EA0;
  if ( a1 == 3 )
    v4 = qword_180068EA8;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hkey) )
    goto LABEL_12;
  v9 = 0;
  v5 = L"Cost4G";
  pcbData = 4;
  if ( a1 != 3 )
    v5 = L"Cost";
  if ( RegGetValueW(hkey, 0, v5, 0x10u, 0, &v9, &pcbData) || (v6 = v9) == 0 )
  {
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 0;
  }
  else
  {
    a2[1] = 1;
    if ( v6 == 3 )
      v6 = 4;
    *a2 = v6;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
}

```

## disassembly

```asm
0x180029b98  mov     r11, rsp
0x180029b9b  mov     [r11+8], rbx
0x180029b9f  mov     [r11+18h], rdi
0x180029ba3  push    r14
0x180029ba5  sub     rsp, 60h
0x180029ba9  mov     rax, cs:__security_cookie
0x180029bb0  xor     rax, rsp
0x180029bb3  mov     [rsp+68h+var_10], rax
0x180029bb8  lea     eax, [rcx-2]
0x180029bbb  mov     rdi, rdx
0x180029bbe  mov     ebx, ecx
0x180029bc0  cmp     eax, 1
0x180029bc3  ja      loc_180029CBA
0x180029bc9  xor     edx, edx
0x180029bcb  mov     qword ptr [r11-20h], 0
0x180029bd3  lea     rcx, [r11-20h]
0x180029bd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029bdc  mov     rdx, cs:qword_180068EA0
0x180029be3  lea     rax, [rsp+68h+hkey]
0x180029be8  cmp     ebx, 3
0x180029beb  mov     [rsp+68h+phkResult], rax; phkResult
0x180029bf0  mov     r9d, 20019h; samDesired
0x180029bf6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029bfd  cmovz   rdx, cs:qword_180068EA8; lpSubKey
0x180029c05  xor     r8d, r8d; ulOptions
0x180029c08  call    cs:__imp_RegOpenKeyExW
0x180029c0e  test    eax, eax
0x180029c10  jnz     short loc_180029C8E
0x180029c12  mov     rcx, [rsp+68h+hkey]; hkey
0x180029c17  lea     r14d, [rax+4]
0x180029c1b  mov     [rsp+68h+var_28], eax
0x180029c1f  lea     r8, aCost4g; "Cost4G"
0x180029c26  lea     rax, aCost; "Cost"
0x180029c2d  mov     [rsp+68h+var_18], r14d
0x180029c32  cmp     ebx, 3
0x180029c35  lea     r9d, [r14+0Ch]; dwFlags
0x180029c39  cmovnz  r8, rax; lpValue
0x180029c3d  lea     rax, [rsp+68h+var_18]
0x180029c42  mov     [rsp+68h+pcbData], rax; pcbData
0x180029c47  xor     edx, edx; lpSubKey
0x180029c49  lea     rax, [rsp+68h+var_28]
0x180029c4e  mov     [rsp+68h+pvData], rax; pvData
0x180029c53  mov     [rsp+68h+phkResult], 0; pdwType
0x180029c5c  call    cs:__imp_RegGetValueW
0x180029c62  test    eax, eax
0x180029c64  jnz     short loc_180029C8E
0x180029c66  mov     ecx, [rsp+68h+var_28]
0x180029c6a  test    ecx, ecx
0x180029c6c  jz      short loc_180029C8E
0x180029c6e  cmp     ecx, 3
0x180029c71  mov     dword ptr [rdi+4], 1
0x180029c78  cmovz   ecx, r14d
0x180029c7c  mov     [rdi], ecx
0x180029c7e  lea     rcx, [rsp+68h+hkey]
0x180029c83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029c88  lea     eax, [r14-3]
0x180029c8c  jmp     short loc_180029C9A
0x180029c8e  lea     rcx, [rsp+68h+hkey]
0x180029c93  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029c98  xor     eax, eax
0x180029c9a  mov     rcx, [rsp+68h+var_10]
0x180029c9f  xor     rcx, rsp; StackCookie
0x180029ca2  call    __security_check_cookie
0x180029ca7  lea     r11, [rsp+68h+var_8]
0x180029cac  mov     rbx, [r11+10h]
0x180029cb0  mov     rdi, [r11+20h]
0x180029cb4  mov     rsp, r11
0x180029cb7  pop     r14
0x180029cb9  retn
0x180029cba  mov     rcx, [rsp+68h]; this
0x180029cbf  lea     rax, aDusmstoreQuery_13; "DusmStore::QueryGpCost::mediaType"
0x180029cc6  mov     r9d, 57h ; 'W'; char *
0x180029ccc  mov     [rsp+68h+phkResult], rax; unsigned int
0x180029cd1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180029cd8  mov     edx, 13Dh; void *
0x180029cdd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
