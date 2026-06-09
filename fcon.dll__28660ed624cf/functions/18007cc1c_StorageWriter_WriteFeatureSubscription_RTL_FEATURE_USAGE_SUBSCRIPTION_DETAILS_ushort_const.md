# StorageWriter::WriteFeatureSubscription(_RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS *,ushort const *)

- ea: `0x18007cc1c`
- end: `0x18007ce45`
- name: `?WriteFeatureSubscription@StorageWriter@@CAJPEAU_RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS@@PEBG@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct _RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ce4c`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180016698`
- `0x18001e820`
- `0x180024098`
- `0x18003888c`
- `0x1800711a0`
- `0x1800789e4`
- `0x180079d20`
- `0x18007cc1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007cce6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007cce6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007cca6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007cca6`

## string_xrefs

- `0x18007cc62`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007ccbe`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007cd4d`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
__int64 __fastcall StorageWriter::WriteFeatureSubscription(
        struct _RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS *a1,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // r8d
  int v10; // eax
  __int64 v11; // rdx
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+20h] [rbp-79h]
  int v14; // [rsp+20h] [rbp-79h]
  HKEY v15; // [rsp+40h] [rbp-59h] BYREF
  __int64 v16; // [rsp+48h] [rbp-51h] BYREF
  int v17; // [rsp+50h] [rbp-49h] BYREF
  HKEY v18; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v19; // [rsp+60h] [rbp-39h] BYREF
  GUID pguid; // [rsp+68h] [rbp-31h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v18 = 0;
  v3 = StorageWriter::CreateFeatureSubscriptionsKey(*(unsigned int *)a1, &v18, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v16 = 0;
    if ( (int)StorageWriter::FindFeatureSubscription(a1, &v18, &v16) < 0 )
    {
      pguid = 0;
      v5 = CoCreateGuid(&pguid);
      v4 = v5;
      if ( v5 < 0 )
      {
        v6 = (unsigned int)v5;
        v7 = 614;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
          (const char *)v6,
          (int)v13);
LABEL_7:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
        goto LABEL_21;
      }
      if ( !StringFromGUID2(&pguid, sz, 39) )
      {
        v4 = -2147024774;
        v7 = 616;
        v6 = 2147942522LL;
        goto LABEL_6;
      }
      v19 = 0;
      v15 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v15,
        0,
        v8);
      v10 = RegWow64Helpers::CreateKey(v18, sz, v9, 0xF003Fu, v13, &v15, &v19);
      v4 = v10;
      if ( v10 < 0 )
      {
        v11 = 620;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
          (const char *)(unsigned int)v10,
          v14);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
        goto LABEL_7;
      }
      v17 = *((unsigned __int16 *)a1 + 2);
      v10 = RegValet::SetValue::_Set(v15, L"ReportingKind", 4u, &v17, 4u);
      v4 = v10;
      if ( v10 < 0 )
      {
        v11 = 623;
        goto LABEL_12;
      }
      v17 = *((unsigned __int16 *)a1 + 3);
      v10 = RegValet::SetValue::_Set(v15, L"ReportingOptions", 4u, &v17, 4u);
      v4 = v10;
      if ( v10 < 0 )
      {
        v11 = 624;
        goto LABEL_12;
      }
      v10 = RegValet::SetValue::_Set(v15, L"ReportingTarget", 3u, (char *)a1 + 8, 8u);
      v4 = v10;
      if ( v10 < 0 )
      {
        v11 = 625;
        goto LABEL_12;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
    v4 = 0;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25B,
    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
    (const char *)(unsigned int)v3,
    (int)v13);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  return v4;
}

```

## disassembly

```asm
0x18007cc1c  mov     [rsp-8+arg_10], rbx
0x18007cc21  push    rbp
0x18007cc22  push    rdi
0x18007cc23  push    r14
0x18007cc25  lea     rbp, [rsp-47h]
0x18007cc2a  sub     rsp, 0E0h
0x18007cc31  mov     rax, cs:__security_cookie
0x18007cc38  xor     rax, rsp
0x18007cc3b  mov     [rbp+57h+var_20], rax
0x18007cc3f  mov     rdi, rcx
0x18007cc42  mov     [rbp+57h+var_98], 0
0x18007cc4a  mov     ecx, [rcx]
0x18007cc4c  mov     r8, rdx
0x18007cc4f  lea     rdx, [rbp+57h+var_98]
0x18007cc53  call    ?CreateFeatureSubscriptionsKey@StorageWriter@@CAJIAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; StorageWriter::CreateFeatureSubscriptionsKey(uint,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)
0x18007cc58  mov     ebx, eax
0x18007cc5a  test    eax, eax
0x18007cc5c  jns     short loc_18007CC7B
0x18007cc5e  mov     rcx, [rbp+5Fh]; this
0x18007cc62  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007cc69  mov     r9d, eax; char *
0x18007cc6c  mov     edx, 25Bh; void *
0x18007cc71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cc76  jmp     loc_18007CE1A
0x18007cc7b  lea     r8, [rbp+57h+var_A8]
0x18007cc7f  mov     [rbp+57h+var_A8], 0
0x18007cc87  lea     rdx, [rbp+57h+var_98]
0x18007cc8b  mov     rcx, rdi
0x18007cc8e  call    ?FindFeatureSubscription@StorageWriter@@CAJPEAU_RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@@Z; StorageWriter::FindFeatureSubscription(_RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18007cc93  test    eax, eax
0x18007cc95  jns     loc_18007CE0F
0x18007cc9b  xorps   xmm0, xmm0
0x18007cc9e  lea     rcx, [rbp+57h+pguid]; pguid
0x18007cca2  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18007cca6  call    cs:__imp_CoCreateGuid
0x18007ccac  mov     ebx, eax
0x18007ccae  test    eax, eax
0x18007ccb0  jns     short loc_18007CCD8
0x18007ccb2  mov     r9d, eax; char *
0x18007ccb5  mov     edx, 266h; void *
0x18007ccba  mov     rcx, [rbp+5Fh]; this
0x18007ccbe  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007ccc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ccca  lea     rcx, [rbp+57h+var_A8]
0x18007ccce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ccd3  jmp     loc_18007CE1A
0x18007ccd8  mov     r8d, 27h ; '''; cchMax
0x18007ccde  lea     rdx, [rbp+57h+sz]; lpsz
0x18007cce2  lea     rcx, [rbp+57h+pguid]; rguid
0x18007cce6  call    cs:__imp_StringFromGUID2
0x18007ccec  test    eax, eax
0x18007ccee  jnz     short loc_18007CCFF
0x18007ccf0  mov     ebx, 8007007Ah
0x18007ccf5  mov     edx, 268h
0x18007ccfa  mov     r9d, ebx
0x18007ccfd  jmp     short loc_18007CCBA
0x18007ccff  xor     edx, edx
0x18007cd01  mov     [rbp+57h+var_90], 0
0x18007cd08  lea     rcx, [rbp+57h+var_B0]
0x18007cd0c  mov     [rbp+57h+var_B0], 0
0x18007cd14  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007cd19  mov     rcx, [rbp+57h+var_98]; HKEY
0x18007cd1d  lea     rax, [rbp+57h+var_90]
0x18007cd21  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x18007cd26  lea     rdx, [rbp+57h+sz]; unsigned __int16 *
0x18007cd2a  lea     rax, [rbp+57h+var_B0]
0x18007cd2e  mov     r9d, 0F003Fh; unsigned int
0x18007cd34  mov     [rsp+0F0h+var_C8], rax; HKEY *
0x18007cd39  call    ?CreateKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; RegWow64Helpers::CreateKey(HKEY__ * const,ushort const * const,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x18007cd3e  mov     ebx, eax
0x18007cd40  test    eax, eax
0x18007cd42  jns     short loc_18007CD6A
0x18007cd44  mov     edx, 26Ch; void *
0x18007cd49  mov     rcx, [rbp+5Fh]; this
0x18007cd4d  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007cd54  mov     r9d, eax; char *
0x18007cd57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd5c  lea     rcx, [rbp+57h+var_B0]
0x18007cd60  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007cd65  jmp     loc_18007CCCA
0x18007cd6a  movzx   eax, word ptr [rdi+4]
0x18007cd6e  lea     r9, [rbp+57h+var_A0]; void *
0x18007cd72  mov     rcx, [rbp+57h+var_B0]; HKEY
0x18007cd76  lea     rdx, aReportingkind; "ReportingKind"
0x18007cd7d  mov     r14d, 4
0x18007cd83  mov     [rbp+57h+var_A0], eax
0x18007cd86  mov     r8d, r14d; unsigned int
0x18007cd89  mov     [rsp+0F0h+var_D0], r14; unsigned __int64
0x18007cd8e  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18007cd93  mov     ebx, eax
0x18007cd95  test    eax, eax
0x18007cd97  jns     short loc_18007CDA0
0x18007cd99  mov     edx, 26Fh
0x18007cd9e  jmp     short loc_18007CD49
0x18007cda0  movzx   eax, word ptr [rdi+6]
0x18007cda4  lea     r9, [rbp+57h+var_A0]; void *
0x18007cda8  mov     rcx, [rbp+57h+var_B0]; HKEY
0x18007cdac  lea     rdx, aReportingoptio; "ReportingOptions"
0x18007cdb3  mov     r8d, r14d; unsigned int
0x18007cdb6  mov     [rbp+57h+var_A0], eax
0x18007cdb9  mov     [rsp+0F0h+var_D0], r14; unsigned __int64
0x18007cdbe  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18007cdc3  mov     ebx, eax
0x18007cdc5  test    eax, eax
0x18007cdc7  jns     short loc_18007CDD3
0x18007cdc9  mov     edx, 270h
0x18007cdce  jmp     loc_18007CD49
0x18007cdd3  mov     rcx, [rbp+57h+var_B0]; HKEY
0x18007cdd7  lea     r9, [rdi+8]; void *
0x18007cddb  mov     r8d, 3; unsigned int
0x18007cde1  mov     [rsp+0F0h+var_D0], 8; unsigned __int64
0x18007cdea  lea     rdx, aReportingtarge; "ReportingTarget"
0x18007cdf1  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18007cdf6  mov     ebx, eax
0x18007cdf8  test    eax, eax
0x18007cdfa  jns     short loc_18007CE06
0x18007cdfc  mov     edx, 271h
0x18007ce01  jmp     loc_18007CD49
0x18007ce06  lea     rcx, [rbp+57h+var_B0]
0x18007ce0a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007ce0f  lea     rcx, [rbp+57h+var_A8]
0x18007ce13  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ce18  xor     ebx, ebx
0x18007ce1a  lea     rcx, [rbp+57h+var_98]
0x18007ce1e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007ce23  mov     eax, ebx
0x18007ce25  mov     rcx, [rbp+57h+var_20]
0x18007ce29  xor     rcx, rsp; StackCookie
0x18007ce2c  call    __security_check_cookie
0x18007ce31  mov     rbx, [rsp+0F0h+arg_10]
0x18007ce39  add     rsp, 0E0h
0x18007ce40  pop     r14
0x18007ce42  pop     rdi
0x18007ce43  pop     rbp
0x18007ce44  retn
```
