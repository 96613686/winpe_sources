# GetHostSessionSubKey(ushort const *,ulong)

- ea: `0x18000c470`
- end: `0x18000c6c9`
- name: `?GetHostSessionSubKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017ca4`
- `0x1800632a0`

## callees

- `0x18000ad30`
- `0x18000c470`
- `0x18000c9c4`
- `0x18000ca20`
- `0x1800108cc`
- `0x180017988`
- `0x18002a3d0`
- `0x18002d848`
- `0x18003c6f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c660`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c671`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c671`

## string_xrefs

- `0x18000c530`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c5df`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c680`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
LPVOID *__fastcall GetHostSessionSubKey(LPVOID *a1, __int64 a2, REGSAM a3, const char *a4)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  _QWORD *v9; // rax
  _WORD *v10; // rax
  void *v11; // rbx
  wchar_t *v12; // rcx
  char *v13; // rsi
  const unsigned __int16 **i; // rdi
  int v15; // eax
  HKEY *v16; // rax
  WCHAR *v17; // rbx
  bool *v18; // r8
  int v20; // [rsp+20h] [rbp-49h]
  int v21; // [rsp+20h] [rbp-49h]
  unsigned __int64 *v22; // [rsp+28h] [rbp-41h]
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v25[8]; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v26[6]; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  lpSubKey = 0;
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
  v25[3] = v6;
  v8 = 0;
  v25[7] = v7;
  v25[4] = L"\\";
  v9 = v25;
  v25[0] = 0;
  v25[1] = 0;
  v25[2] = L"ShellUIHosts";
  v25[5] = 1;
  v25[6] = a2;
  do
  {
    v8 += v9[1];
    v9 += 2;
  }
  while ( v9 != v26 );
  pv = 0;
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
    &pv,
    v10);
  v11 = pv;
  if ( pv )
  {
    v12 = (wchar_t *)pv;
    v13 = (char *)pv + 2 * v8 + 2;
    for ( i = (const unsigned __int16 **)v25; i != v26; i += 2 )
    {
      if ( *i )
      {
        v15 = StringCchCopyNExW(
                v12,
                (v13 - (char *)v12) >> 1,
                *i,
                (unsigned __int64)i[1],
                (unsigned __int16 **)&pv,
                v22,
                0x100u);
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x791,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v15,
            v21);
          if ( v11 )
            CoTaskMemFree(v11);
          goto LABEL_35;
        }
        v12 = (wchar_t *)pv;
      }
    }
    pv = v11;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpSubKey,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    pv = 0;
    v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&pv);
    v17 = (WCHAR *)lpSubKey;
    if ( (int)CreateShellSessionSubKey(lpSubKey, a3, v18, v16) < 0 )
    {
      if ( pv )
        RegCloseKey((HKEY)pv);
      *a1 = 0;
    }
    else
    {
      *a1 = pv;
      pv = 0;
    }
    if ( v17 )
      CoTaskMemFree(v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v20);
LABEL_35:
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000c470  push    rbp
0x18000c472  push    rdi
0x18000c473  push    r12
0x18000c475  push    r14
0x18000c477  push    r15
0x18000c479  lea     rbp, [rsp-37h]
0x18000c47e  sub     rsp, 0A0h
0x18000c485  mov     rax, cs:__security_cookie
0x18000c48c  xor     rax, rsp
0x18000c48f  mov     [rbp+57h+var_30], rax
0x18000c493  xor     r12d, r12d
0x18000c496  mov     r15d, r8d
0x18000c499  mov     [rbp+57h+lpSubKey], r12
0x18000c49d  mov     r14, rcx
0x18000c4a0  mov     r8, rdx
0x18000c4a3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c4aa  test    rdx, rdx
0x18000c4ad  jz      short loc_18000C4BE
0x18000c4af  mov     rax, rcx
0x18000c4b2  inc     rax
0x18000c4b5  cmp     [rdx+rax*2], r12w
0x18000c4ba  jnz     short loc_18000C4B2
0x18000c4bc  jmp     short loc_18000C4C1
0x18000c4be  mov     rax, r12
0x18000c4c1  mov     rdx, cs:off_18008A080; "ShellUIHosts"
0x18000c4c8  test    rdx, rdx
0x18000c4cb  jz      short loc_18000C4DC
0x18000c4cd  nop     dword ptr [rax]
0x18000c4d0  inc     rcx
0x18000c4d3  cmp     [rdx+rcx*2], r12w
0x18000c4d8  jnz     short loc_18000C4D0
0x18000c4da  jmp     short loc_18000C4DF
0x18000c4dc  mov     rcx, r12
0x18000c4df  mov     [rbp+57h+var_58], rcx
0x18000c4e3  mov     rdi, r12
0x18000c4e6  lea     rcx, asc_18008FC3C; "\\"
0x18000c4ed  mov     [rbp+57h+var_38], rax
0x18000c4f1  mov     [rbp+57h+var_50], rcx
0x18000c4f5  lea     rax, [rbp+57h+var_70]
0x18000c4f9  mov     [rbp+57h+var_70], r12
0x18000c4fd  mov     [rbp+57h+var_68], r12
0x18000c501  mov     [rbp+57h+var_60], rdx
0x18000c505  mov     [rbp+57h+var_48], 1
0x18000c50d  mov     [rbp+57h+var_40], r8
0x18000c511  add     rdi, [rax+8]
0x18000c515  lea     rcx, [rbp+57h+var_30]
0x18000c519  add     rax, 10h
0x18000c51d  cmp     rax, rcx
0x18000c520  jnz     short loc_18000C511
0x18000c522  mov     [rbp+57h+pv], r12
0x18000c526  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c52a  jnz     short loc_18000C542
0x18000c52c  mov     rcx, [rbp+5Fh]; this
0x18000c530  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c537  mov     edx, 0F89h; void *
0x18000c53c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000c542  lea     rcx, ds:2[rdi*2]; cb
0x18000c54a  mov     [rsp+0C0h+arg_8], rbx
0x18000c552  call    cs:__imp_CoTaskMemAlloc
0x18000c558  mov     rdx, rax
0x18000c55b  test    rax, rax
0x18000c55e  jz      short loc_18000C569
0x18000c560  mov     [rax], r12w
0x18000c564  mov     [rax+rdi*2], r12w
0x18000c569  lea     rcx, [rbp+57h+pv]
0x18000c56d  mov     [rsp+0C0h+arg_18], rsi
0x18000c575  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000c57a  mov     rbx, [rbp+57h+pv]
0x18000c57e  test    rbx, rbx
0x18000c581  jz      loc_18000C67C
0x18000c587  inc     rdi
0x18000c58a  mov     [rbp+57h+pv], rbx
0x18000c58e  mov     rcx, rbx; pszDest
0x18000c591  lea     rsi, [rbx+rdi*2]
0x18000c595  lea     rdi, [rbp+57h+var_70]
0x18000c599  lea     rax, [rbp+57h+var_30]
0x18000c59d  cmp     rdi, rax
0x18000c5a0  jz      short loc_18000C60A
0x18000c5a2  mov     r8, [rdi]; unsigned __int16 *
0x18000c5a5  test    r8, r8
0x18000c5a8  jz      short loc_18000C5D5
0x18000c5aa  mov     r9, [rdi+8]; unsigned __int64
0x18000c5ae  lea     rax, [rbp+57h+pv]
0x18000c5b2  mov     rdx, rsi
0x18000c5b5  mov     [rsp+0C0h+var_90], 100h; unsigned int
0x18000c5bd  sub     rdx, rcx
0x18000c5c0  mov     [rsp+0C0h+var_A0], rax; int
0x18000c5c5  sar     rdx, 1; unsigned __int64
0x18000c5c8  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000c5cd  test    eax, eax
0x18000c5cf  js      short loc_18000C5DB
0x18000c5d1  mov     rcx, [rbp+57h+pv]
0x18000c5d5  add     rdi, 10h
0x18000c5d9  jmp     short loc_18000C599
0x18000c5db  mov     rcx, [rbp+5Fh]; this
0x18000c5df  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c5e6  mov     r9d, eax; char *
0x18000c5e9  mov     edx, 791h; void *
0x18000c5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5f3  test    rbx, rbx
0x18000c5f6  jz      loc_18000C697
0x18000c5fc  mov     rcx, rbx; pv
0x18000c5ff  call    cs:__imp_CoTaskMemFree
0x18000c605  jmp     loc_18000C697
0x18000c60a  lea     rdx, [rbp+57h+pv]
0x18000c60e  mov     [rbp+57h+pv], rbx
0x18000c612  lea     rcx, [rbp+57h+lpSubKey]
0x18000c616  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000c61b  mov     rcx, [rbp+57h+pv]; pv
0x18000c61f  test    rcx, rcx
0x18000c622  jz      short loc_18000C62A
0x18000c624  call    cs:__imp_CoTaskMemFree
0x18000c62a  lea     rcx, [rbp+57h+pv]
0x18000c62e  mov     [rbp+57h+pv], r12
0x18000c632  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18000c637  mov     rbx, [rbp+57h+lpSubKey]
0x18000c63b  mov     r9, rax; HKEY *
0x18000c63e  mov     rcx, rbx; lpSubKey
0x18000c641  mov     edx, r15d; samDesired
0x18000c644  call    ?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18000c649  test    eax, eax
0x18000c64b  js      short loc_18000C668
0x18000c64d  mov     rax, [rbp+57h+pv]
0x18000c651  mov     [r14], rax
0x18000c654  mov     [rbp+57h+pv], r12
0x18000c658  test    rbx, rbx
0x18000c65b  jz      short loc_18000C69A
0x18000c65d  mov     rcx, rbx; pv
0x18000c660  call    cs:__imp_CoTaskMemFree
0x18000c666  jmp     short loc_18000C69A
0x18000c668  mov     rcx, [rbp+57h+pv]; hKey
0x18000c66c  test    rcx, rcx
0x18000c66f  jz      short loc_18000C677
0x18000c671  call    cs:__imp_RegCloseKey
0x18000c677  mov     [r14], r12
0x18000c67a  jmp     short loc_18000C658
0x18000c67c  mov     rcx, [rbp+5Fh]; this
0x18000c680  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c687  mov     r9d, 8007000Eh; char *
0x18000c68d  mov     edx, 788h; void *
0x18000c692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c697  mov     [r14], r12
0x18000c69a  mov     rsi, [rsp+0C0h+arg_18]
0x18000c6a2  mov     rax, r14
0x18000c6a5  mov     rbx, [rsp+0C0h+arg_8]
0x18000c6ad  mov     rcx, [rbp+57h+var_30]
0x18000c6b1  xor     rcx, rsp; StackCookie
0x18000c6b4  call    __security_check_cookie
0x18000c6b9  add     rsp, 0A0h
0x18000c6c0  pop     r15
0x18000c6c2  pop     r14
0x18000c6c4  pop     r12
0x18000c6c6  pop     rdi
0x18000c6c7  pop     rbp
0x18000c6c8  retn
```
