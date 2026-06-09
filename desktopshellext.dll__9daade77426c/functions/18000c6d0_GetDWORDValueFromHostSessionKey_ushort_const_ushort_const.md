# GetDWORDValueFromHostSessionKey(ushort const *,ushort const *)

- ea: `0x18000c6d0`
- end: `0x18000c9be`
- name: `?GetDWORDValueFromHostSessionKey@@YA?AV?$optional@K@std@@PEBG0@Z`
- size: `750`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a2c0`
- `0x18001a360`

## callees

- `0x18000ad30`
- `0x18000c6d0`
- `0x18000c9c4`
- `0x18000ca20`
- `0x1800108cc`
- `0x180017988`
- `0x18002a3d0`
- `0x18002d848`
- `0x18003c6f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c79b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c79b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c844`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c99d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c844`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c99d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c8ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c8ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c97e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c97e`

## string_xrefs

- `0x18000c880`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c901`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c9ac`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall GetDWORDValueFromHostSessionKey(__int64 a1, __int64 a2, const WCHAR *a3, const char *a4)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  _QWORD *v9; // rax
  _WORD *v10; // rax
  HKEY v11; // rbx
  wchar_t *v12; // rcx
  char *v13; // r14
  const unsigned __int16 **i; // rdi
  int v15; // eax
  HKEY *v17; // rax
  void *v18; // rdi
  bool *v19; // r8
  HKEY v20; // rbx
  int pdwType; // [rsp+20h] [rbp-59h]
  int pdwTypea; // [rsp+20h] [rbp-59h]
  unsigned __int64 *pvData; // [rsp+28h] [rbp-51h]
  HKEY hkey; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+48h] [rbp-31h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v27[8]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v28[6]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  pv[0] = 0;
  v6 = -1;
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a2 + 2 * v7) );
  }
  else
  {
    v7 = 0;
  }
  if ( L"ShellUIHosts" )
  {
    do
      ++v6;
    while ( aShelluihosts[v6] );
  }
  else
  {
    v6 = 0;
  }
  v27[3] = v6;
  v8 = 0;
  v27[7] = v7;
  v27[4] = L"\\";
  v9 = v27;
  v27[0] = 0;
  v27[1] = 0;
  v27[2] = L"ShellUIHosts";
  v27[5] = 1;
  v27[6] = a2;
  do
  {
    v8 += v9[1];
    v9 += 2;
  }
  while ( v9 != v28 );
  hkey = 0;
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v10 = CoTaskMemAlloc(2 * v8 + 2);
  if ( v10 )
  {
    *v10 = 0;
    v10[v8] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &hkey,
    v10);
  v11 = hkey;
  if ( hkey )
  {
    v12 = (wchar_t *)hkey;
    v13 = (char *)hkey + 2 * v8 + 2;
    for ( i = (const unsigned __int16 **)v27; i != v28; i += 2 )
    {
      if ( *i )
      {
        v15 = StringCchCopyNExW(
                v12,
                (v13 - (char *)v12) >> 1,
                *i,
                (unsigned __int64)i[1],
                (unsigned __int16 **)&hkey,
                pvData,
                0x100u);
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x791,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v15,
            pdwTypea);
          if ( v11 )
            CoTaskMemFree(v11);
          goto LABEL_22;
        }
        v12 = (wchar_t *)hkey;
      }
    }
    hkey = v11;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      pv,
      &hkey);
    if ( hkey )
      CoTaskMemFree(hkey);
    hkey = 0;
    v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
    v18 = pv[0];
    if ( (int)CreateShellSessionSubKey((LPCWSTR)pv[0], 0x20019u, v19, v17) >= 0 )
    {
      v20 = hkey;
      hkey = 0;
      if ( v18 )
        CoTaskMemFree(v18);
      if ( v20 )
      {
        LODWORD(pv[0]) = 4;
        v25 = 0;
        if ( !RegGetValueW(v20, 0, a3, 0x18u, 0, &v25, (LPDWORD)pv) )
        {
          *(_DWORD *)a1 = v25;
          *(_BYTE *)(a1 + 4) = 1;
          RegCloseKey(v20);
          return a1;
        }
        RegCloseKey(v20);
      }
    }
    else
    {
      if ( hkey )
        RegCloseKey(hkey);
      if ( v18 )
        CoTaskMemFree(v18);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      pdwType);
  }
LABEL_22:
  *(_BYTE *)(a1 + 4) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000c6d0  push    rbp
0x18000c6d2  push    rsi
0x18000c6d3  push    rdi
0x18000c6d4  push    r12
0x18000c6d6  push    r15
0x18000c6d8  lea     rbp, [rsp-37h]
0x18000c6dd  sub     rsp, 0B0h
0x18000c6e4  mov     rax, cs:__security_cookie
0x18000c6eb  xor     rax, rsp
0x18000c6ee  mov     [rbp+57h+var_30], rax
0x18000c6f2  xor     r12d, r12d
0x18000c6f5  mov     r15, r8
0x18000c6f8  mov     [rbp+57h+pv], r12
0x18000c6fc  mov     rsi, rcx
0x18000c6ff  mov     r8, rdx
0x18000c702  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c709  test    rdx, rdx
0x18000c70c  jz      loc_18000C82C
0x18000c712  mov     rax, rcx
0x18000c715  inc     rax
0x18000c718  cmp     [rdx+rax*2], r12w
0x18000c71d  jnz     short loc_18000C715
0x18000c71f  mov     rdx, cs:off_18008A080; "ShellUIHosts"
0x18000c726  test    rdx, rdx
0x18000c729  jz      loc_18000C834
0x18000c72f  nop
0x18000c730  inc     rcx
0x18000c733  cmp     [rdx+rcx*2], r12w
0x18000c738  jnz     short loc_18000C730
0x18000c73a  mov     [rbp+57h+var_58], rcx
0x18000c73e  mov     rdi, r12
0x18000c741  lea     rcx, asc_18008FC3C; "\\"
0x18000c748  mov     [rbp+57h+var_38], rax
0x18000c74c  mov     [rbp+57h+var_50], rcx
0x18000c750  lea     rax, [rbp+57h+var_70]
0x18000c754  mov     [rbp+57h+var_70], r12
0x18000c758  mov     [rbp+57h+var_68], r12
0x18000c75c  mov     [rbp+57h+var_60], rdx
0x18000c760  mov     [rbp+57h+var_48], 1
0x18000c768  mov     [rbp+57h+var_40], r8
0x18000c76c  add     rdi, [rax+8]
0x18000c770  lea     rcx, [rbp+57h+var_30]
0x18000c774  add     rax, 10h
0x18000c778  cmp     rax, rcx
0x18000c77b  jnz     short loc_18000C76C
0x18000c77d  mov     [rbp+57h+hkey], r12
0x18000c781  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c785  jz      loc_18000C9A8
0x18000c78b  lea     rcx, ds:2[rdi*2]; cb
0x18000c793  mov     [rsp+0D0h+arg_8], rbx
0x18000c79b  call    cs:__imp_CoTaskMemAlloc
0x18000c7a1  mov     rdx, rax
0x18000c7a4  test    rax, rax
0x18000c7a7  jz      short loc_18000C7B2
0x18000c7a9  mov     [rax], r12w
0x18000c7ad  mov     [rax+rdi*2], r12w
0x18000c7b2  lea     rcx, [rbp+57h+hkey]
0x18000c7b6  mov     [rsp+0D0h+arg_18], r14
0x18000c7be  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000c7c3  mov     rbx, [rbp+57h+hkey]
0x18000c7c7  test    rbx, rbx
0x18000c7ca  jz      loc_18000C87C
0x18000c7d0  inc     rdi
0x18000c7d3  mov     [rbp+57h+hkey], rbx
0x18000c7d7  mov     rcx, rbx; pszDest
0x18000c7da  lea     r14, [rbx+rdi*2]
0x18000c7de  lea     rdi, [rbp+57h+var_70]
0x18000c7e2  lea     rax, [rbp+57h+var_30]
0x18000c7e6  cmp     rdi, rax
0x18000c7e9  jz      loc_18000C92C
0x18000c7ef  mov     r8, [rdi]; unsigned __int16 *
0x18000c7f2  test    r8, r8
0x18000c7f5  jz      short loc_18000C826
0x18000c7f7  mov     r9, [rdi+8]; unsigned __int64
0x18000c7fb  lea     rax, [rbp+57h+hkey]
0x18000c7ff  mov     rdx, r14
0x18000c802  mov     dword ptr [rsp+0D0h+pcbData], 100h; unsigned int
0x18000c80a  sub     rdx, rcx
0x18000c80d  mov     [rsp+0D0h+pdwType], rax; int
0x18000c812  sar     rdx, 1; unsigned __int64
0x18000c815  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000c81a  test    eax, eax
0x18000c81c  js      loc_18000C8FD
0x18000c822  mov     rcx, [rbp+57h+hkey]
0x18000c826  add     rdi, 10h
0x18000c82a  jmp     short loc_18000C7E2
0x18000c82c  mov     rax, r12
0x18000c82f  jmp     loc_18000C71F
0x18000c834  mov     rcx, r12
0x18000c837  jmp     loc_18000C73A
0x18000c83c  test    rdi, rdi
0x18000c83f  jz      short loc_18000C84A
0x18000c841  mov     rcx, rdi; pv
0x18000c844  call    cs:__imp_CoTaskMemFree
0x18000c84a  mov     [rsi+4], r12b
0x18000c84e  mov     r14, [rsp+0D0h+arg_18]
0x18000c856  mov     rax, rsi
0x18000c859  mov     rbx, [rsp+0D0h+arg_8]
0x18000c861  mov     rcx, [rbp+57h+var_30]
0x18000c865  xor     rcx, rsp; StackCookie
0x18000c868  call    __security_check_cookie
0x18000c86d  add     rsp, 0B0h
0x18000c874  pop     r15
0x18000c876  pop     r12
0x18000c878  pop     rdi
0x18000c879  pop     rsi
0x18000c87a  pop     rbp
0x18000c87b  retn
0x18000c87c  mov     rcx, [rbp+5Fh]; this
0x18000c880  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c887  mov     r9d, 8007000Eh; char *
0x18000c88d  mov     edx, 788h; void *
0x18000c892  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c897  jmp     short loc_18000C84A
0x18000c899  test    rbx, rbx
0x18000c89c  jz      short loc_18000C84A
0x18000c89e  lea     rax, [rbp+57h+pv]
0x18000c8a2  mov     dword ptr [rbp+57h+pv], 4
0x18000c8a9  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18000c8ae  mov     r9d, 18h; dwFlags
0x18000c8b4  lea     rax, [rbp+57h+var_88]
0x18000c8b8  mov     [rbp+57h+var_88], r12d
0x18000c8bc  mov     [rsp+0D0h+pvData], rax; pvData
0x18000c8c1  mov     r8, r15; lpValue
0x18000c8c4  xor     edx, edx; lpSubKey
0x18000c8c6  mov     [rsp+0D0h+pdwType], r12; pdwType
0x18000c8cb  mov     rcx, rbx; hkey
0x18000c8ce  call    cs:__imp_RegGetValueW
0x18000c8d4  test    eax, eax
0x18000c8d6  jnz     short loc_18000C8EF
0x18000c8d8  mov     ecx, [rbp+57h+var_88]
0x18000c8db  mov     [rsi], ecx
0x18000c8dd  mov     rcx, rbx; hKey
0x18000c8e0  mov     byte ptr [rsi+4], 1
0x18000c8e4  call    cs:__imp_RegCloseKey
0x18000c8ea  jmp     loc_18000C84E
0x18000c8ef  mov     rcx, rbx; hKey
0x18000c8f2  call    cs:__imp_RegCloseKey
0x18000c8f8  jmp     loc_18000C84A
0x18000c8fd  mov     rcx, [rbp+5Fh]; this
0x18000c901  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c908  mov     r9d, eax; char *
0x18000c90b  mov     edx, 791h; void *
0x18000c910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c915  test    rbx, rbx
0x18000c918  jz      loc_18000C84A
0x18000c91e  mov     rcx, rbx; pv
0x18000c921  call    cs:__imp_CoTaskMemFree
0x18000c927  jmp     loc_18000C84A
0x18000c92c  lea     rdx, [rbp+57h+hkey]
0x18000c930  mov     [rbp+57h+hkey], rbx
0x18000c934  lea     rcx, [rbp+57h+pv]
0x18000c938  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000c93d  mov     rcx, [rbp+57h+hkey]; pv
0x18000c941  test    rcx, rcx
0x18000c944  jz      short loc_18000C94C
0x18000c946  call    cs:__imp_CoTaskMemFree
0x18000c94c  lea     rcx, [rbp+57h+hkey]
0x18000c950  mov     [rbp+57h+hkey], r12
0x18000c954  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18000c959  mov     rdi, [rbp+57h+pv]
0x18000c95d  mov     r9, rax; HKEY *
0x18000c960  mov     rcx, rdi; lpSubKey
0x18000c963  mov     edx, 20019h; samDesired
0x18000c968  call    ?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18000c96d  test    eax, eax
0x18000c96f  jns     short loc_18000C989
0x18000c971  mov     rcx, [rbp+57h+hkey]; hKey
0x18000c975  test    rcx, rcx
0x18000c978  jz      loc_18000C83C
0x18000c97e  call    cs:__imp_RegCloseKey
0x18000c984  jmp     loc_18000C83C
0x18000c989  mov     rbx, [rbp+57h+hkey]
0x18000c98d  mov     [rbp+57h+hkey], r12
0x18000c991  test    rdi, rdi
0x18000c994  jz      loc_18000C899
0x18000c99a  mov     rcx, rdi; pv
0x18000c99d  call    cs:__imp_CoTaskMemFree
0x18000c9a3  jmp     loc_18000C899
0x18000c9a8  mov     rcx, [rbp+5Fh]; this
0x18000c9ac  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c9b3  mov     edx, 0F89h; void *
0x18000c9b8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
