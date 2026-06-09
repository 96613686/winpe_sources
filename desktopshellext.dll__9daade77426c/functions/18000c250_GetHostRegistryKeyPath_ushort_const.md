# GetHostRegistryKeyPath(ushort const *)

- ea: `0x18000c250`
- end: `0x18000c43d`
- name: `?GetHostRegistryKeyPath@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c15c`

## callees

- `0x18000c250`
- `0x18000c444`
- `0x18000c9c4`
- `0x18000ca20`
- `0x180017988`
- `0x18002a3d0`
- `0x18002d848`
- `0x18003c6f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c317`

## string_xrefs

- `0x18000c2fd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c39f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c3f4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall GetHostRegistryKeyPath(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rsi
  _QWORD *v7; // rax
  _WORD *v8; // rax
  unsigned __int16 *v9; // rbx
  wchar_t *v10; // rcx
  wchar_t *v11; // r12
  const unsigned __int16 **i; // rsi
  int v13; // eax
  int v14; // r14d
  _QWORD *v15; // rcx
  int v17; // [rsp+20h] [rbp-59h]
  int v18; // [rsp+20h] [rbp-59h]
  unsigned __int64 *v19; // [rsp+28h] [rbp-51h]
  STRSAFE_LPWSTR pszDest; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-31h] BYREF
  __int64 v22; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v23[6]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v24[9]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v22 = 0;
  v3 = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a2 + 2 * v4) );
  }
  else
  {
    v4 = 0;
  }
  if ( L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Shell\\ShellUIHosts\\" )
  {
    v5 = -1;
    do
      ++v5;
    while ( aSoftwareMicros_6[v5] );
  }
  else
  {
    v5 = 0;
  }
  v23[5] = v4;
  v6 = 0;
  v7 = v23;
  v23[0] = 0;
  v23[1] = 0;
  v23[2] = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Shell\\ShellUIHosts\\";
  v23[3] = v5;
  v23[4] = a2;
  do
  {
    v6 += v7[1];
    v7 += 2;
  }
  while ( v7 != v24 );
  pszDest = 0;
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0xFFFFFFFFFFFFFFFFLL);
  v8 = CoTaskMemAlloc(2 * v6 + 2);
  if ( v8 )
  {
    *v8 = 0;
    v8[v6] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszDest,
    v8);
  v9 = pszDest;
  if ( !pszDest )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v17);
    v15 = a1;
LABEL_29:
    *v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
    return a1;
  }
  v21 = pszDest;
  v10 = pszDest;
  v11 = &pszDest[v6 + 1];
  for ( i = (const unsigned __int16 **)v23; i != v24; i += 2 )
  {
    if ( *i )
    {
      v13 = StringCchCopyNExW(v10, v11 - v10, *i, (unsigned __int64)i[1], &v21, v19, 0x100u);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x791,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          (const char *)(unsigned int)v13,
          v18);
        goto LABEL_26;
      }
      v10 = v21;
    }
  }
  v21 = v9;
  pszDest = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v22,
    &v21);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
  v3 = v22;
  v14 = 0;
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszDest);
  v15 = a1;
  if ( v14 < 0 )
    goto LABEL_29;
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x18000c250  push    rbp
0x18000c252  push    rbx
0x18000c253  push    rsi
0x18000c254  push    rdi
0x18000c255  push    r12
0x18000c257  push    r13
0x18000c259  push    r14
0x18000c25b  push    r15
0x18000c25d  lea     rbp, [rsp-1Fh]
0x18000c262  sub     rsp, 98h
0x18000c269  mov     rax, cs:__security_cookie
0x18000c270  xor     rax, rsp
0x18000c273  mov     [rbp+57h+var_48], rax
0x18000c277  xor     r13d, r13d
0x18000c27a  or      r9, 0FFFFFFFFFFFFFFFFh; char *
0x18000c27e  mov     [rbp+57h+var_80], r13
0x18000c282  mov     r8, rdx
0x18000c285  mov     r15, rcx
0x18000c288  mov     edi, r13d
0x18000c28b  test    rdx, rdx
0x18000c28e  jz      short loc_18000C29F
0x18000c290  mov     rax, r9
0x18000c293  inc     rax
0x18000c296  cmp     [rdx+rax*2], r13w
0x18000c29b  jnz     short loc_18000C293
0x18000c29d  jmp     short loc_18000C2A2
0x18000c29f  mov     rax, r13
0x18000c2a2  mov     rdx, cs:off_18008A078; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c2a9  test    rdx, rdx
0x18000c2ac  jz      short loc_18000C2BD
0x18000c2ae  mov     rcx, r9
0x18000c2b1  inc     rcx
0x18000c2b4  cmp     [rdx+rcx*2], r13w
0x18000c2b9  jnz     short loc_18000C2B1
0x18000c2bb  jmp     short loc_18000C2C0
0x18000c2bd  mov     rcx, r13
0x18000c2c0  mov     [rbp+57h+var_50], rax
0x18000c2c4  mov     rsi, r13
0x18000c2c7  lea     rax, [rbp+57h+var_78]
0x18000c2cb  mov     [rbp+57h+var_78], r13
0x18000c2cf  mov     [rbp+57h+var_70], r13
0x18000c2d3  mov     [rbp+57h+var_68], rdx
0x18000c2d7  mov     [rbp+57h+var_60], rcx
0x18000c2db  mov     [rbp+57h+var_58], r8
0x18000c2df  add     rsi, [rax+8]
0x18000c2e3  lea     rcx, [rbp+57h+var_48]
0x18000c2e7  add     rax, 10h
0x18000c2eb  cmp     rax, rcx
0x18000c2ee  jnz     short loc_18000C2DF
0x18000c2f0  mov     [rbp+57h+pszDest], r13
0x18000c2f4  cmp     rsi, r9
0x18000c2f7  jnz     short loc_18000C30F
0x18000c2f9  mov     rcx, [rbp+5Fh]; this
0x18000c2fd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c304  mov     edx, 0F89h; void *
0x18000c309  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000c30f  lea     rcx, ds:2[rsi*2]; cb
0x18000c317  call    cs:__imp_CoTaskMemAlloc
0x18000c31d  mov     rdx, rax
0x18000c320  test    rax, rax
0x18000c323  jz      short loc_18000C32E
0x18000c325  mov     [rax], r13w
0x18000c329  mov     [rax+rsi*2], r13w
0x18000c32e  lea     rcx, [rbp+57h+pszDest]
0x18000c332  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000c337  mov     rbx, [rbp+57h+pszDest]
0x18000c33b  test    rbx, rbx
0x18000c33e  jz      loc_18000C3F0
0x18000c344  inc     rsi
0x18000c347  mov     [rbp+57h+var_88], rbx
0x18000c34b  mov     rcx, rbx; pszDest
0x18000c34e  lea     r12, [rbx+rsi*2]
0x18000c352  lea     rsi, [rbp+57h+var_78]
0x18000c356  lea     rax, [rbp+57h+var_48]
0x18000c35a  cmp     rsi, rax
0x18000c35d  jz      short loc_18000C3B5
0x18000c35f  mov     r8, [rsi]; unsigned __int16 *
0x18000c362  test    r8, r8
0x18000c365  jz      short loc_18000C395
0x18000c367  mov     r9, [rsi+8]; unsigned __int64
0x18000c36b  lea     rax, [rbp+57h+var_88]
0x18000c36f  mov     rdx, r12
0x18000c372  mov     [rsp+0D0h+var_A0], 100h; unsigned int
0x18000c37a  sub     rdx, rcx
0x18000c37d  mov     [rsp+0D0h+var_B0], rax; int
0x18000c382  sar     rdx, 1; unsigned __int64
0x18000c385  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000c38a  mov     r14d, eax
0x18000c38d  test    eax, eax
0x18000c38f  js      short loc_18000C39B
0x18000c391  mov     rcx, [rbp+57h+var_88]
0x18000c395  add     rsi, 10h
0x18000c399  jmp     short loc_18000C356
0x18000c39b  mov     rcx, [rbp+5Fh]; this
0x18000c39f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c3a6  mov     r9d, eax; char *
0x18000c3a9  mov     edx, 791h; void *
0x18000c3ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3b3  jmp     short loc_18000C3DA
0x18000c3b5  lea     rdx, [rbp+57h+var_88]
0x18000c3b9  mov     [rbp+57h+var_88], rbx
0x18000c3bd  lea     rcx, [rbp+57h+var_80]
0x18000c3c1  mov     [rbp+57h+pszDest], r13
0x18000c3c5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000c3ca  lea     rcx, [rbp+57h+var_88]
0x18000c3ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000c3d3  mov     rdi, [rbp+57h+var_80]
0x18000c3d7  mov     r14d, r13d
0x18000c3da  lea     rcx, [rbp+57h+pszDest]
0x18000c3de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000c3e3  mov     rcx, r15
0x18000c3e6  test    r14d, r14d
0x18000c3e9  js      short loc_18000C40E
0x18000c3eb  mov     [r15], rdi
0x18000c3ee  jmp     short loc_18000C41A
0x18000c3f0  mov     rcx, [rbp+5Fh]; this
0x18000c3f4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c3fb  mov     r9d, 8007000Eh; char *
0x18000c401  mov     edx, 788h; void *
0x18000c406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c40b  mov     rcx, r15
0x18000c40e  mov     [rcx], r13
0x18000c411  lea     rcx, [rbp+57h+var_80]
0x18000c415  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000c41a  mov     rax, r15
0x18000c41d  mov     rcx, [rbp+57h+var_48]
0x18000c421  xor     rcx, rsp; StackCookie
0x18000c424  call    __security_check_cookie
0x18000c429  add     rsp, 98h
0x18000c430  pop     r15
0x18000c432  pop     r14
0x18000c434  pop     r13
0x18000c436  pop     r12
0x18000c438  pop     rdi
0x18000c439  pop     rsi
0x18000c43a  pop     rbx
0x18000c43b  pop     rbp
0x18000c43c  retn
```
