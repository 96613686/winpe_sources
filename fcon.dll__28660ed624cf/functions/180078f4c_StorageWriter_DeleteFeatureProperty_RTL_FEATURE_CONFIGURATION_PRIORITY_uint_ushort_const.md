# StorageWriter::DeleteFeatureProperty(_RTL_FEATURE_CONFIGURATION_PRIORITY,uint,ushort const *)

- ea: `0x180078f4c`
- end: `0x180079130`
- name: `?DeleteFeatureProperty@StorageWriter@@SAJW4_RTL_FEATURE_CONFIGURATION_PRIORITY@@IPEBG@Z`
- size: `484`
- prototype: `static int __high(enum _RTL_FEATURE_CONFIGURATION_PRIORITY, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18007c6c4`

## callees

- `0x18000949c`
- `0x180016698`
- `0x18001e820`
- `0x180024098`
- `0x18002b818`
- `0x18004dee0`
- `0x180077870`
- `0x180077f5c`
- `0x180078108`
- `0x180078f4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800790c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800790c7`

## string_xrefs

- `0x180078f98`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180078fed`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180079037`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x1800790a1`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007910c`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
__int64 __fastcall StorageWriter::DeleteFeatureProperty(__int64 a1, int a2, const WCHAR *a3)
{
  unsigned int v5; // ecx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // eax
  RegPersistedKey *v12; // rbx
  __int64 v13; // r8
  LSTATUS v14; // eax
  int v16; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v19[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  __int64 v21; // [rsp+98h] [rbp+40h] BYREF

  if ( (unsigned int)a1 > 0xF || (unsigned __int8)RtlpIsImmutableFeatureConfigurationPriority(a1) )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C9,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)0x80070057LL,
      v16);
    return v7;
  }
  v19[0] = 0;
  v6 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         v19,
         L"%u",
         v5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v21 = 0;
    v8 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &v21,
           L"%lu",
           __ROR4__(_byteswap_ulong(a2 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v18 = 0;
      v11 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [10],unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (unsigned int)&v18,
              v9,
              v10,
              (unsigned int)v19);
      v7 = v11;
      if ( v11 >= 0 )
      {
        hKey = 0;
        v12 = RegPersistedKeySingleton::KeyFeatureManagement();
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0,
          v13);
        v7 = RegPersistedKey::RegOpenKeyW(v12, v18, 0xF003Fu, &hKey);
        if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024894 )
        {
          v14 = RegDeleteValueW(hKey, a3);
          v7 = v14;
          if ( !v14 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
            v7 = 0;
            goto LABEL_19;
          }
          if ( v14 > 0 )
            v7 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D6,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
            (const char *)v7,
            v16);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D2,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
          (const char *)(unsigned int)v11,
          v16);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CF,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
        (const char *)(unsigned int)v8,
        v16);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CC,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v6,
      v16);
  }
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v19);
  return v7;
}

```

## disassembly

```asm
0x180078f4c  push    rbp
0x180078f4e  push    rbx
0x180078f4f  push    rsi
0x180078f50  push    rdi
0x180078f51  mov     rbp, rsp
0x180078f54  sub     rsp, 58h
0x180078f58  mov     rsi, r8
0x180078f5b  mov     edi, edx
0x180078f5d  cmp     ecx, 0Fh
0x180078f60  ja      loc_180079108
0x180078f66  call    RtlpIsImmutableFeatureConfigurationPriority
0x180078f6b  test    al, al
0x180078f6d  jnz     loc_180079108
0x180078f73  mov     r8d, ecx
0x180078f76  mov     [rbp+var_18], 0
0x180078f7e  lea     rcx, [rbp+var_18]
0x180078f82  lea     rdx, aU; "%u"
0x180078f89  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180078f8e  mov     ebx, eax
0x180078f90  test    eax, eax
0x180078f92  jns     short loc_180078FB1
0x180078f94  mov     rcx, [rbp+20h]; this
0x180078f98  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x180078f9f  mov     r9d, eax; char *
0x180078fa2  mov     edx, 4CCh; void *
0x180078fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078fac  jmp     loc_1800790FD
0x180078fb1  xor     edi, 74161A4Eh
0x180078fb7  mov     [rbp+arg_18], 0
0x180078fbf  bswap   edi
0x180078fc1  xor     edi, 8FB23D4Fh
0x180078fc7  lea     rdx, aLu; "%lu"
0x180078fce  ror     edi, 0FFh
0x180078fd1  lea     rcx, [rbp+arg_18]
0x180078fd5  xor     edi, 833EA8FFh
0x180078fdb  mov     r8d, edi
0x180078fde  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180078fe3  mov     ebx, eax
0x180078fe5  test    eax, eax
0x180078fe7  jns     short loc_18007900F
0x180078fe9  mov     rcx, [rbp+20h]; this
0x180078fed  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x180078ff4  mov     r9d, eax; char *
0x180078ff7  mov     edx, 4CFh; void *
0x180078ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079001  lea     rcx, [rbp+arg_18]
0x180079005  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007900a  jmp     loc_1800790FD
0x18007900f  lea     rax, [rbp+arg_18]
0x180079013  mov     [rbp+var_20], 0
0x18007901b  lea     r9, [rbp+var_18]
0x18007901f  mov     [rsp+58h+var_30], rax
0x180079024  lea     rcx, [rbp+var_20]
0x180079028  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY09G$$BY01GV12@$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY09$$CBGAEAY01$$CBGAEBV10@23@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [10],ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[10],ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x18007902d  mov     ebx, eax
0x18007902f  test    eax, eax
0x180079031  jns     short loc_180079056
0x180079033  mov     rcx, [rbp+20h]; this
0x180079037  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007903e  mov     r9d, eax; char *
0x180079041  mov     edx, 4D2h; void *
0x180079046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007904b  lea     rcx, [rbp+var_20]
0x18007904f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180079054  jmp     short loc_180079001
0x180079056  mov     [rbp+hKey], 0
0x18007905e  call    ?KeyFeatureManagement@RegPersistedKeySingleton@@SAAEAVRegPersistedKey@@XZ; RegPersistedKeySingleton::KeyFeatureManagement(void)
0x180079063  xor     edx, edx
0x180079065  lea     rcx, [rbp+hKey]
0x180079069  mov     rbx, rax
0x18007906c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180079071  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180079075  lea     r9, [rbp+hKey]; HKEY *
0x180079079  mov     r8d, 0F003Fh; unsigned int
0x18007907f  mov     rcx, rbx; this
0x180079082  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x180079087  mov     ebx, eax
0x180079089  mov     eax, 80000000h
0x18007908e  lea     ecx, [rbx+rax]
0x180079091  test    eax, ecx
0x180079093  jnz     short loc_1800790C0
0x180079095  cmp     ebx, 80070002h
0x18007909b  jz      short loc_1800790C0
0x18007909d  mov     rcx, [rbp+20h]; this
0x1800790a1  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x1800790a8  mov     r9d, ebx; char *
0x1800790ab  mov     edx, 4D6h; void *
0x1800790b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800790b5  lea     rcx, [rbp+hKey]
0x1800790b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800790be  jmp     short loc_18007904B
0x1800790c0  mov     rcx, [rbp+hKey]; hKey
0x1800790c4  mov     rdx, rsi; lpValueName
0x1800790c7  call    cs:__imp_RegDeleteValueW
0x1800790cd  mov     ebx, eax
0x1800790cf  test    eax, eax
0x1800790d1  jz      short loc_1800790E0
0x1800790d3  jle     short loc_1800790B5
0x1800790d5  movzx   ebx, ax
0x1800790d8  or      ebx, 80070000h
0x1800790de  jmp     short loc_1800790B5
0x1800790e0  lea     rcx, [rbp+hKey]
0x1800790e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800790e9  lea     rcx, [rbp+var_20]
0x1800790ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800790f2  lea     rcx, [rbp+arg_18]
0x1800790f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800790fb  xor     ebx, ebx
0x1800790fd  lea     rcx, [rbp+var_18]
0x180079101  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180079106  jmp     short loc_180079125
0x180079108  mov     rcx, [rbp+20h]; this
0x18007910c  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x180079113  mov     ebx, 80070057h
0x180079118  mov     edx, 4C9h; void *
0x18007911d  mov     r9d, ebx; char *
0x180079120  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079125  mov     eax, ebx
0x180079127  add     rsp, 58h
0x18007912b  pop     rdi
0x18007912c  pop     rsi
0x18007912d  pop     rbx
0x18007912e  pop     rbp
0x18007912f  retn
```
