# StorageWriter::DeleteAllFeatureOverrides(ushort const *)

- ea: `0x1801192d8`
- end: `0x1801195de`
- name: `?DeleteAllFeatureOverrides@StorageWriter@@SAJPEBG@Z`
- size: `774`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801158d0`

## callees

- `0x180004bd0`
- `0x18000da88`
- `0x180116dbc`
- `0x180118b64`
- `0x1801192d8`
- `0x1801195e4`
- `0x18011b8a0`
- `0x18011ba4c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801193e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801193e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119321`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119340`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119340`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119332`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801194d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801195b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119332`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801194d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801195b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801194b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011950d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801194b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011950d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119599`

## string_xrefs

- `0x180119386`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x1801194f3`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180119541`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18011955f`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18011957d`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageWriter::DeleteAllFeatureOverrides(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v2; // r8d
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int16 v5; // di
  int v6; // r12d
  int v7; // eax
  void *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  unsigned int v12; // eax
  HKEY hKey; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v16[528]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  RegPersistedKey::RegPersistedKey((RegPersistedKey *)v16, a2, a1);
  hKey = 0;
  v3 = RegPersistedKey::RegOpenKeyW((RegPersistedKey *)v16, L"Overrides", v2, &hKey);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = 0;
    v6 = 523;
    while ( 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SandboxCopyImmutableKeys>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SandboxCopyImmutableKeys>::GetImpl'::`2'::impl) )
      {
        if ( v5 > 9u
          || !_bittest(&v6, v5)
          || (InitOnceExecuteOnce(&InitOnce, lambda_22343f899db14d8b2f0e9cf2fff83038_::_lambda_invoker_cdecl_, 0, 0),
              dword_18021F678) )
        {
          pv = 0;
          v7 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                 &pv,
                 L"%u",
                 v5);
          v4 = v7;
          if ( v7 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3B3,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
              (const char *)(unsigned int)v7,
              (int)hKey);
            goto LABEL_33;
          }
          v8 = pv;
          v9 = RegWow64Helpers::DeleteTree(hKey, (const WCHAR *)pv);
          v10 = v9;
          if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -2147024894 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3B6,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
              (const char *)v9,
              (int)hKey);
LABEL_25:
            if ( v8 )
              CoTaskMemFree(v8);
            if ( hKey )
              RegCloseKey(hKey);
            return v10;
          }
LABEL_18:
          if ( v8 )
            CoTaskMemFree(v8);
        }
      }
      else if ( v5 > 9u || !_bittest(&v6, v5) )
      {
        pv = 0;
        v11 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &pv,
                L"%u",
                v5);
        v4 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3BE,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
            (const char *)(unsigned int)v11,
            (int)hKey);
LABEL_33:
          if ( pv )
            CoTaskMemFree(pv);
LABEL_35:
          if ( hKey )
            RegCloseKey(hKey);
          return v4;
        }
        v8 = pv;
        v12 = RegWow64Helpers::DeleteTree(hKey, (const WCHAR *)pv);
        v10 = v12;
        if ( ((v12 + 0x80000000) & 0x80000000) == 0 && v12 != -2147024894 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C1,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
            (const char *)v12,
            (int)hKey);
          goto LABEL_25;
        }
        goto LABEL_18;
      }
      if ( ++v5 >= 0xFu )
        goto LABEL_21;
    }
  }
  if ( v3 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v3,
      (int)hKey);
    goto LABEL_35;
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1801192d8  push    rbp
0x1801192da  push    rbx
0x1801192db  push    rsi
0x1801192dc  push    rdi
0x1801192dd  push    r12
0x1801192df  push    r13
0x1801192e1  lea     rbp, [rsp-158h]
0x1801192e9  sub     rsp, 258h
0x1801192f0  mov     rax, cs:__security_cookie
0x1801192f7  xor     rax, rsp
0x1801192fa  mov     [rbp+180h+var_40], rax
0x180119301  mov     [rsp+280h+hKey], 0
0x18011930a  mov     r8, rcx; unsigned __int16 *
0x18011930d  lea     rcx, [rsp+280h+var_250]; this
0x180119312  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x180119317  mov     rdi, [rsp+280h+hKey]
0x18011931c  test    rdi, rdi
0x18011931f  jz      short loc_18011934C
0x180119321  call    cs:__imp_GetLastError
0x180119328  nop     dword ptr [rax+rax+00h]
0x18011932d  mov     ebx, eax
0x18011932f  mov     rcx, rdi; hKey
0x180119332  call    cs:__imp_RegCloseKey
0x180119339  nop     dword ptr [rax+rax+00h]
0x18011933e  mov     ecx, ebx; dwErrCode
0x180119340  call    cs:__imp_SetLastError
0x180119347  nop     dword ptr [rax+rax+00h]
0x18011934c  mov     [rsp+280h+hKey], 0; int
0x180119355  lea     r9, [rsp+280h+hKey]; HKEY *
0x18011935a  lea     rdx, aOverrides; "Overrides"
0x180119361  lea     rcx, [rsp+280h+var_250]; this
0x180119366  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x18011936b  mov     ebx, eax
0x18011936d  test    eax, eax
0x18011936f  jns     short loc_18011939C
0x180119371  cmp     eax, 80070002h
0x180119376  jz      loc_1801194CC
0x18011937c  mov     rcx, [rbp+188h]; this
0x180119383  mov     r9d, eax; char *
0x180119386  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x18011938d  mov     edx, 3A8h; void *
0x180119392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119397  jmp     loc_1801195A6
0x18011939c  xor     edi, edi
0x18011939e  mov     r12d, 20Bh
0x1801193a4  mov     r13d, 80000000h
0x1801193aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SandboxCopyImmutableKeys@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SandboxCopyImmutableKeys@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SandboxCopyImmutableKeys> `wil::Feature<__WilFeatureTraits_Feature_SandboxCopyImmutableKeys>::GetImpl(void)'::`2'::impl
0x1801193b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SandboxCopyImmutableKeys@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SandboxCopyImmutableKeys>::__private_IsEnabled(void)
0x1801193b6  test    al, al
0x1801193b8  jz      loc_18011944C
0x1801193be  cmp     di, 9
0x1801193c2  ja      short loc_1801193FA
0x1801193c4  movzx   eax, di
0x1801193c7  bt      r12d, eax
0x1801193cb  jnb     short loc_1801193FA
0x1801193cd  xor     r9d, r9d; Context
0x1801193d0  xor     r8d, r8d; Parameter
0x1801193d3  lea     rdx, _lambda_22343f899db14d8b2f0e9cf2fff83038____lambda_invoker_cdecl_; InitFn
0x1801193da  lea     rcx, InitOnce; InitOnce
0x1801193e1  call    cs:__imp_InitOnceExecuteOnce
0x1801193e8  nop     dword ptr [rax+rax+00h]
0x1801193ed  cmp     cs:dword_18021F678, 0
0x1801193f4  jz      loc_1801194BF
0x1801193fa  mov     [rsp+280h+pv], 0
0x180119403  movzx   r8d, di
0x180119407  lea     rdx, aU; "%u"
0x18011940e  lea     rcx, [rsp+280h+pv]
0x180119413  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180119418  mov     ebx, eax
0x18011941a  test    eax, eax
0x18011941c  js      loc_180119537
0x180119422  mov     rbx, [rsp+280h+pv]
0x180119427  mov     rdx, rbx; unsigned __int16 *
0x18011942a  mov     rcx, [rsp+280h+hKey]; HKEY
0x18011942f  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x180119434  mov     esi, eax
0x180119436  lea     ecx, [rax+r13]
0x18011943a  test    r13d, ecx
0x18011943d  jnz     short loc_18011944A
0x18011943f  cmp     eax, 80070002h
0x180119444  jnz     loc_1801194E9
0x18011944a  jmp     short loc_1801194AB
0x18011944c  cmp     di, 9
0x180119450  ja      short loc_18011945B
0x180119452  movzx   eax, di
0x180119455  bt      r12d, eax
0x180119459  jb      short loc_1801194BF
0x18011945b  mov     [rsp+280h+pv], 0
0x180119464  movzx   r8d, di
0x180119468  lea     rdx, aU; "%u"
0x18011946f  lea     rcx, [rsp+280h+pv]
0x180119474  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180119479  mov     ebx, eax
0x18011947b  test    eax, eax
0x18011947d  js      loc_180119573
0x180119483  mov     rbx, [rsp+280h+pv]
0x180119488  mov     rdx, rbx; unsigned __int16 *
0x18011948b  mov     rcx, [rsp+280h+hKey]; HKEY
0x180119490  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x180119495  mov     esi, eax
0x180119497  lea     ecx, [rax+r13]
0x18011949b  test    r13d, ecx
0x18011949e  jnz     short loc_1801194AB
0x1801194a0  cmp     eax, 80070002h
0x1801194a5  jnz     loc_180119555
0x1801194ab  test    rbx, rbx
0x1801194ae  jz      short loc_1801194BF
0x1801194b0  mov     rcx, rbx; pv
0x1801194b3  call    cs:__imp_CoTaskMemFree
0x1801194ba  nop     dword ptr [rax+rax+00h]
0x1801194bf  inc     di
0x1801194c2  cmp     di, 0Fh
0x1801194c6  jb      loc_1801193AA
0x1801194cc  mov     rcx, [rsp+280h+hKey]; hKey
0x1801194d1  test    rcx, rcx
0x1801194d4  jz      short loc_1801194E2
0x1801194d6  call    cs:__imp_RegCloseKey
0x1801194dd  nop     dword ptr [rax+rax+00h]
0x1801194e2  xor     eax, eax
0x1801194e4  jmp     loc_1801195BE
0x1801194e9  mov     rcx, [rbp+188h]; this
0x1801194f0  mov     r9d, esi; char *
0x1801194f3  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x1801194fa  mov     edx, 3B6h; void *
0x1801194ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119504  nop
0x180119505  test    rbx, rbx
0x180119508  jz      short loc_18011951A
0x18011950a  mov     rcx, rbx; pv
0x18011950d  call    cs:__imp_CoTaskMemFree
0x180119514  nop     dword ptr [rax+rax+00h]
0x180119519  nop
0x18011951a  mov     rcx, [rsp+280h+hKey]; hKey
0x18011951f  test    rcx, rcx
0x180119522  jz      short loc_180119530
0x180119524  call    cs:__imp_RegCloseKey
0x18011952b  nop     dword ptr [rax+rax+00h]
0x180119530  mov     eax, esi
0x180119532  jmp     loc_1801195BE
0x180119537  mov     rcx, [rbp+188h]; this
0x18011953e  mov     r9d, ebx; char *
0x180119541  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180119548  mov     edx, 3B3h; void *
0x18011954d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119552  nop
0x180119553  jmp     short loc_18011958F
0x180119555  mov     rcx, [rbp+188h]; this
0x18011955c  mov     r9d, esi; char *
0x18011955f  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180119566  mov     edx, 3C1h; void *
0x18011956b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119570  nop
0x180119571  jmp     short loc_180119505
0x180119573  mov     rcx, [rbp+188h]; this
0x18011957a  mov     r9d, ebx; char *
0x18011957d  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180119584  mov     edx, 3BEh; void *
0x180119589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011958e  nop
0x18011958f  mov     rcx, [rsp+280h+pv]; pv
0x180119594  test    rcx, rcx
0x180119597  jz      short loc_1801195A6
0x180119599  call    cs:__imp_CoTaskMemFree
0x1801195a0  nop     dword ptr [rax+rax+00h]
0x1801195a5  nop
0x1801195a6  mov     rcx, [rsp+280h+hKey]; hKey
0x1801195ab  test    rcx, rcx
0x1801195ae  jz      short loc_1801195BC
0x1801195b0  call    cs:__imp_RegCloseKey
0x1801195b7  nop     dword ptr [rax+rax+00h]
0x1801195bc  mov     eax, ebx
0x1801195be  mov     rcx, [rbp+180h+var_40]
0x1801195c5  xor     rcx, rsp; StackCookie
0x1801195c8  call    __security_check_cookie
0x1801195cd  add     rsp, 258h
0x1801195d4  pop     r13
0x1801195d6  pop     r12
0x1801195d8  pop     rdi
0x1801195d9  pop     rsi
0x1801195da  pop     rbx
0x1801195db  pop     rbp
0x1801195dc  retn
```
