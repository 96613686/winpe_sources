# StorageWriter::DeletePolicyFeatureState(uint)

- ea: `0x18007974c`
- end: `0x1800798aa`
- name: `?DeletePolicyFeatureState@StorageWriter@@SAJI@Z`
- size: `350`
- prototype: `static int(unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18007cacc`

## callees

- `0x18000949c`
- `0x180016698`
- `0x18001e820`
- `0x180024098`
- `0x180077870`
- `0x180078108`
- `0x18007974c`
- `0x18007acd0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180079758`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180079758`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180079854`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180079854`

## string_xrefs

- `0x180079767`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x1800797d2`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180079832`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
__int64 __fastcall StorageWriter::DeletePolicyFeatureState(int a1)
{
  unsigned int v2; // ebx
  RegPersistedKey *v3; // rbx
  __int64 v4; // r8
  int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  LSTATUS v9; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPCWSTR lpValueName; // [rsp+38h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned __int8)RtlIsStateSeparationEnabled() != 1 )
  {
    hKey = 0;
    v3 = RegPersistedKeySingleton::KeyPoliciesFeatureManagement();
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0,
      v4);
    v5 = RegPersistedKey::RegOpenKeyW(v3, L"Overrides", 0xF003Fu, &hKey);
    v2 = v5;
    if ( v5 < 0 )
    {
      if ( v5 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x208,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
          (const char *)(unsigned int)v5,
          v11);
LABEL_16:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v2;
      }
LABEL_15:
      v2 = 0;
      goto LABEL_16;
    }
    lpValueName = 0;
    v6 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &lpValueName,
           L"%lu",
           __ROR4__(_byteswap_ulong(a1 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF);
    v2 = v6;
    if ( v6 >= 0 )
    {
      v9 = RegDeleteValueW(hKey, lpValueName);
      v2 = v9;
      if ( v9 > 0 )
        v2 = (unsigned __int16)v9 | 0x80070000;
      if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147024894 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpValueName);
        goto LABEL_15;
      }
      v7 = v2;
      v8 = 527;
    }
    else
    {
      v7 = (unsigned int)v6;
      v8 = 524;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)v7,
      v11);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpValueName);
    goto LABEL_16;
  }
  v2 = -2147483634;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x204,
    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
    (const char *)0x8000000ELL,
    v11);
  return v2;
}

```

## disassembly

```asm
0x18007974c  mov     [rsp+arg_0], rbx
0x180079751  push    rdi; int
0x180079752  sub     rsp, 20h
0x180079756  mov     edi, ecx
0x180079758  call    cs:__imp_RtlIsStateSeparationEnabled
0x18007975e  cmp     al, 1
0x180079760  jnz     short loc_180079785
0x180079762  mov     rcx, [rsp+28h]; this
0x180079767  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007976e  mov     ebx, 8000000Eh
0x180079773  mov     edx, 204h; void *
0x180079778  mov     r9d, ebx; char *
0x18007977b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079780  jmp     loc_18007989D
0x180079785  mov     [rsp+28h+hKey], 0
0x18007978e  call    ?KeyPoliciesFeatureManagement@RegPersistedKeySingleton@@SAAEAVRegPersistedKey@@XZ; RegPersistedKeySingleton::KeyPoliciesFeatureManagement(void)
0x180079793  xor     edx, edx
0x180079795  lea     rcx, [rsp+28h+hKey]
0x18007979a  mov     rbx, rax
0x18007979d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800797a2  lea     r9, [rsp+28h+hKey]; HKEY *
0x1800797a7  mov     r8d, 0F003Fh; unsigned int
0x1800797ad  lea     rdx, aOverrides; "Overrides"
0x1800797b4  mov     rcx, rbx; this
0x1800797b7  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x1800797bc  mov     ebx, eax
0x1800797be  test    eax, eax
0x1800797c0  jns     short loc_1800797EB
0x1800797c2  cmp     eax, 80070002h
0x1800797c7  jz      loc_180079891
0x1800797cd  mov     rcx, [rsp+28h]; this
0x1800797d2  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x1800797d9  mov     r9d, eax; char *
0x1800797dc  mov     edx, 208h; void *
0x1800797e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800797e6  jmp     loc_180079893
0x1800797eb  xor     edi, 74161A4Eh
0x1800797f1  mov     [rsp+28h+lpValueName], 0
0x1800797fa  bswap   edi
0x1800797fc  xor     edi, 8FB23D4Fh
0x180079802  lea     rdx, aLu; "%lu"
0x180079809  ror     edi, 0FFh
0x18007980c  lea     rcx, [rsp+28h+lpValueName]
0x180079811  xor     edi, 833EA8FFh
0x180079817  mov     r8d, edi
0x18007981a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18007981f  mov     ebx, eax
0x180079821  test    eax, eax
0x180079823  jns     short loc_18007984A
0x180079825  mov     r9d, eax; char *
0x180079828  mov     edx, 20Ch; void *
0x18007982d  mov     rcx, [rsp+28h]; this
0x180079832  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x180079839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007983e  lea     rcx, [rsp+28h+lpValueName]
0x180079843  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180079848  jmp     short loc_180079893
0x18007984a  mov     rdx, [rsp+28h+lpValueName]; lpValueName
0x18007984f  mov     rcx, [rsp+28h+hKey]; hKey
0x180079854  call    cs:__imp_RegDeleteValueW
0x18007985a  mov     ebx, eax
0x18007985c  test    eax, eax
0x18007985e  jle     short loc_180079869
0x180079860  movzx   ebx, ax
0x180079863  or      ebx, 80070000h
0x180079869  mov     ecx, 80000000h
0x18007986e  lea     eax, [rbx+rcx]
0x180079871  test    ecx, eax
0x180079873  jnz     short loc_180079887
0x180079875  cmp     ebx, 80070002h
0x18007987b  jz      short loc_180079887
0x18007987d  mov     r9d, ebx
0x180079880  mov     edx, 20Fh
0x180079885  jmp     short loc_18007982D
0x180079887  lea     rcx, [rsp+28h+lpValueName]
0x18007988c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180079891  xor     ebx, ebx
0x180079893  lea     rcx, [rsp+28h+hKey]
0x180079898  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007989d  mov     eax, ebx
0x18007989f  mov     rbx, [rsp+28h+arg_0]
0x1800798a4  add     rsp, 20h
0x1800798a8  pop     rdi
0x1800798a9  retn
```
