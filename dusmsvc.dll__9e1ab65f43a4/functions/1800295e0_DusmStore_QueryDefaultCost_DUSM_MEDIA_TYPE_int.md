# DusmStore::QueryDefaultCost(_DUSM_MEDIA_TYPE,int)

- ea: `0x1800295e0`
- end: `0x18002973c`
- name: `?QueryDefaultCost@DusmStore@@SA?AU_DUSM_CONNECTION_COST_DATA@@W4_DUSM_MEDIA_TYPE@@H@Z`
- size: `348`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001bfec`
- `0x18001c23c`
- `0x180034d24`
- `0x1800381b8`
- `0x18003aa18`

## callees

- `0x180007c90`
- `0x18001d87c`
- `0x180026fa0`
- `0x1800295e0`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029643`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029643`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800296b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800296b8`

## pseudocode

```c
__int64 __fastcall DusmStore::QueryDefaultCost(int a1, int a2)
{
  const WCHAR *v4; // r8
  int v5; // ebx
  int v6; // ebx
  const char *pvData; // [rsp+28h] [rbp-48h]
  __int64 v9; // [rsp+40h] [rbp-30h]
  unsigned int v10; // [rsp+48h] [rbp-28h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  if ( (unsigned int)(a1 - 1) > 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::QueryDefaultCost::mediaType",
      pvData);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hkey) )
    goto LABEL_12;
  v4 = 0;
  v5 = a1 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        v4 = L"4G";
        if ( !a2 )
          v4 = L"3G";
      }
    }
    else
    {
      v4 = L"WiFi";
    }
  }
  else
  {
    v4 = L"Ethernet";
  }
  v10 = 0;
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, v4, 0x10u, 0, &v10, &pcbData) )
  {
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  else
  {
    v9 = v10;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v9;
  }
}

```

## disassembly

```asm
0x1800295e0  mov     [rsp-8+arg_0], rbx
0x1800295e5  mov     [rsp-8+arg_8], rdi
0x1800295ea  push    rbp
0x1800295eb  mov     rbp, rsp
0x1800295ee  sub     rsp, 70h
0x1800295f2  mov     rax, cs:__security_cookie
0x1800295f9  xor     rax, rsp
0x1800295fc  mov     [rbp+var_10], rax
0x180029600  lea     eax, [rcx-1]
0x180029603  mov     edi, edx
0x180029605  mov     ebx, ecx
0x180029607  cmp     eax, 2
0x18002960a  ja      loc_180029714
0x180029610  xor     edx, edx
0x180029612  mov     [rbp+hkey], 0
0x18002961a  lea     rcx, [rbp+hkey]
0x18002961e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029623  mov     rdx, cs:lpSubKey; lpSubKey
0x18002962a  lea     rax, [rbp+hkey]
0x18002962e  mov     r9d, 20019h; samDesired
0x180029634  mov     [rsp+70h+phkResult], rax; phkResult
0x180029639  xor     r8d, r8d; ulOptions
0x18002963c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029643  call    cs:__imp_RegOpenKeyExW
0x180029649  test    eax, eax
0x18002964b  jnz     short loc_1800296C2
0x18002964d  xor     r8d, r8d
0x180029650  sub     ebx, 1
0x180029653  jz      short loc_18002967E
0x180029655  sub     ebx, 1
0x180029658  jz      short loc_180029675
0x18002965a  cmp     ebx, 1
0x18002965d  jnz     short loc_180029685
0x18002965f  test    edi, edi
0x180029661  lea     rax, a3g; "3G"
0x180029668  lea     r8, a4g; "4G"
0x18002966f  cmovz   r8, rax
0x180029673  jmp     short loc_180029685
0x180029675  lea     r8, aWifi_1; "WiFi"
0x18002967c  jmp     short loc_180029685
0x18002967e  lea     r8, aEthernet_1; "Ethernet"
0x180029685  mov     rcx, [rbp+hkey]; hkey
0x180029689  lea     rax, [rbp+var_18]
0x18002968d  mov     [rsp+70h+pcbData], rax; pcbData
0x180029692  xor     edx, edx; lpSubKey
0x180029694  lea     rax, [rbp+var_28]
0x180029698  mov     [rbp+var_28], 0
0x18002969f  mov     [rsp+70h+pvData], rax; pvData
0x1800296a4  mov     [rsp+70h+phkResult], 0; pdwType
0x1800296ad  lea     r9d, [rdx+10h]; dwFlags
0x1800296b1  mov     [rbp+var_18], 4
0x1800296b8  call    cs:__imp_RegGetValueW
0x1800296be  test    eax, eax
0x1800296c0  jz      short loc_1800296DC
0x1800296c2  mov     [rbp+var_30], 1
0x1800296ca  lea     rcx, [rbp+hkey]
0x1800296ce  mov     rbx, [rbp+var_30]
0x1800296d2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800296d7  mov     rax, rbx
0x1800296da  jmp     short loc_1800296F6
0x1800296dc  mov     eax, [rbp+var_28]
0x1800296df  lea     rcx, [rbp+hkey]
0x1800296e3  mov     dword ptr [rbp+var_30], eax
0x1800296e6  mov     dword ptr [rbp+var_30+4], 0
0x1800296ed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800296f2  mov     rax, [rbp+var_30]
0x1800296f6  mov     rcx, [rbp+var_10]
0x1800296fa  xor     rcx, rsp; StackCookie
0x1800296fd  call    __security_check_cookie
0x180029702  lea     r11, [rsp+70h+var_s0]
0x180029707  mov     rbx, [r11+10h]
0x18002970b  mov     rdi, [r11+18h]
0x18002970f  mov     rsp, r11
0x180029712  pop     rbp
0x180029713  retn
0x180029714  mov     rcx, [rbp+8]; this
0x180029718  lea     rax, aDusmstoreQuery_7; "DusmStore::QueryDefaultCost::mediaType"
0x18002971f  mov     r9d, 57h ; 'W'; char *
0x180029725  mov     [rsp+70h+phkResult], rax; unsigned int
0x18002972a  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180029731  mov     edx, 10Eh; void *
0x180029736  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
