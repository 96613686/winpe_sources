# CSchemaCache::_DeletePropertySchemaPath(ushort const *,int,SCHEMA_REGISTRATION_DATA * *)

- ea: `0x180091e8c`
- end: `0x1800920e5`
- name: `?_DeletePropertySchemaPath@CSchemaCache@@AEAAJPEBGHPEAPEAUSCHEMA_REGISTRATION_DATA@@@Z`
- size: `601`
- prototype: `int(CSchemaCache *__hidden this, const unsigned __int16 *, int, struct SCHEMA_REGISTRATION_DATA **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006d630`

## callees

- `0x180003434`
- `0x180004148`
- `0x18000457c`
- `0x18002f9e0`
- `0x18006114c`
- `0x180064148`
- `0x18006e0b8`
- `0x18006ed20`
- `0x180091e8c`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18009203e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18009203e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091f10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091fb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091f10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091fb9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180091f69`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180091f69`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180092088`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180092088`

## string_xrefs

- `0x180091fdc`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180092023`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSchemaCache::_DeletePropertySchemaPath(
        CSchemaCache *this,
        const unsigned __int16 *a2,
        int a3,
        struct SCHEMA_REGISTRATION_DATA **a4)
{
  signed int v7; // ebx
  LSTATUS v8; // eax
  bool v9; // sf
  DWORD i; // edi
  LSTATUS v11; // eax
  struct IMigrationContext *v12; // rdx
  int v13; // eax
  LSTATUS v14; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  LPCWSTR pszStr2; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v18; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a4 = 0;
  hKey = 0;
  v7 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertySchema",
         0,
         a3 != 0 ? 268 : 524,
         &hKey);
  v9 = v8 < 0;
  if ( v8 > 0 )
    v9 = 1;
  if ( !v9 )
  {
    cchName = 260;
    for ( i = 0; !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0); ++i )
    {
      v18 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v18,
        0);
      v11 = RegOpenKeyExW(hKey, Name, 0, a3 != 0 ? 257 : 513, &v18);
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      if ( v7 >= 0 )
      {
        pszStr2 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszStr2,
          0);
        v13 = GetAndExpandRegisteredPath(v18, v12, (unsigned __int16 **)&pszStr2);
        v7 = v13;
        if ( v13 >= 0 )
        {
          if ( !StrCmpICW(a2, pszStr2) )
          {
            v7 = SCHEMA_REGISTRATION_DATA::Load(v18, a4);
            if ( v7 >= 0 )
            {
              v14 = SHDeleteKeyW(hKey, Name);
              v7 = v14;
              if ( v14 > 0 )
                v7 = (unsigned __int16)v14 | 0x80070000;
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszStr2);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
            break;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4CD,
            (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
            (const char *)(unsigned int)v13,
            phkResult);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszStr2);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4C9,
          (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
          (const char *)(unsigned int)v7,
          phkResult);
      }
      cchName = 260;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180091e8c  mov     [rsp-8+arg_0], rbx
0x180091e91  push    rbp
0x180091e92  push    rsi
0x180091e93  push    rdi
0x180091e94  push    r14
0x180091e96  push    r15
0x180091e98  lea     rbp, [rsp-180h]
0x180091ea0  sub     rsp, 280h
0x180091ea7  mov     rax, cs:__security_cookie
0x180091eae  xor     rax, rsp
0x180091eb1  mov     [rbp+1A0h+var_30], rax
0x180091eb8  mov     rsi, r9
0x180091ebb  mov     r15d, r8d
0x180091ebe  mov     r14, rdx
0x180091ec1  mov     qword ptr [r9], 0
0x180091ec8  mov     [rsp+2A0h+hKey], 0
0x180091ed1  xor     ebx, ebx
0x180091ed3  xor     edx, edx
0x180091ed5  lea     rcx, [rsp+2A0h+hKey]
0x180091eda  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180091edf  mov     eax, r15d
0x180091ee2  neg     eax
0x180091ee4  sbb     r9d, r9d
0x180091ee7  and     r9d, 0FFFFFF00h
0x180091eee  add     r9d, 20Ch; samDesired
0x180091ef5  lea     rax, [rsp+2A0h+hKey]
0x180091efa  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180091eff  xor     r8d, r8d; ulOptions
0x180091f02  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180091f09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091f10  call    cs:__imp_RegOpenKeyExW
0x180091f16  test    eax, eax
0x180091f18  jle     short loc_180091F24
0x180091f1a  movzx   eax, ax
0x180091f1d  or      eax, 80070000h
0x180091f22  test    eax, eax
0x180091f24  js      loc_1800920B3
0x180091f2a  mov     [rsp+2A0h+cchName], 104h
0x180091f32  xor     edi, edi
0x180091f34  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180091f3d  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180091f46  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180091f4f  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x180091f58  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180091f5d  lea     r8, [rsp+2A0h+Name]; lpName
0x180091f62  mov     edx, edi; dwIndex
0x180091f64  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180091f69  call    cs:__imp_RegEnumKeyExW
0x180091f6f  test    eax, eax
0x180091f71  jnz     loc_1800920B3
0x180091f77  mov     [rsp+2A0h+var_258], 0
0x180091f80  xor     edx, edx
0x180091f82  lea     rcx, [rsp+2A0h+var_258]
0x180091f87  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180091f8c  mov     eax, r15d
0x180091f8f  neg     eax
0x180091f91  sbb     r9d, r9d
0x180091f94  and     r9d, 0FFFFFF00h
0x180091f9b  add     r9d, 201h; samDesired
0x180091fa2  lea     rax, [rsp+2A0h+var_258]
0x180091fa7  mov     [rsp+2A0h+phkResult], rax; int
0x180091fac  xor     r8d, r8d; ulOptions
0x180091faf  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x180091fb4  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180091fb9  call    cs:__imp_RegOpenKeyExW
0x180091fbf  mov     ebx, eax
0x180091fc1  test    eax, eax
0x180091fc3  jle     short loc_180091FCE
0x180091fc5  movzx   ebx, ax
0x180091fc8  or      ebx, 80070000h
0x180091fce  mov     rcx, [rbp+1A8h]; this
0x180091fd5  test    ebx, ebx
0x180091fd7  jns     short loc_180091FEF
0x180091fd9  mov     r9d, ebx; char *
0x180091fdc  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180091fe3  mov     edx, 4C9h; void *
0x180091fe8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091fed  jmp     short loc_180092052
0x180091fef  mov     [rsp+2A0h+pszStr2], 0
0x180091ff8  xor     edx, edx
0x180091ffa  lea     rcx, [rsp+2A0h+pszStr2]
0x180091fff  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180092004  lea     r8, [rsp+2A0h+pszStr2]; unsigned __int16 **
0x180092009  mov     rcx, [rsp+2A0h+var_258]; HKEY
0x18009200e  call    ?GetAndExpandRegisteredPath@@YAJPEAUHKEY__@@PEAUIMigrationContext@@PEAPEAG@Z; GetAndExpandRegisteredPath(HKEY__ *,IMigrationContext *,ushort * *)
0x180092013  mov     ebx, eax
0x180092015  mov     rcx, [rbp+1A8h]; this
0x18009201c  test    eax, eax
0x18009201e  jns     short loc_180092036
0x180092020  mov     r9d, eax; char *
0x180092023  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18009202a  mov     edx, 4CDh; void *
0x18009202f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092034  jmp     short loc_180092048
0x180092036  mov     rdx, [rsp+2A0h+pszStr2]; pszStr2
0x18009203b  mov     rcx, r14; pszStr1
0x18009203e  call    cs:__imp_StrCmpICW
0x180092044  test    eax, eax
0x180092046  jz      short loc_18009206B
0x180092048  lea     rcx, [rsp+2A0h+pszStr2]
0x18009204d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180092052  mov     [rsp+2A0h+cchName], 104h
0x18009205a  lea     rcx, [rsp+2A0h+var_258]
0x18009205f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180092064  inc     edi
0x180092066  jmp     loc_180091F34
0x18009206b  mov     rdx, rsi; struct SCHEMA_REGISTRATION_DATA **
0x18009206e  mov     rcx, [rsp+2A0h+var_258]; HKEY
0x180092073  call    ?Load@SCHEMA_REGISTRATION_DATA@@SAJPEAUHKEY__@@PEAPEAU1@@Z; SCHEMA_REGISTRATION_DATA::Load(HKEY__ *,SCHEMA_REGISTRATION_DATA * *)
0x180092078  mov     ebx, eax
0x18009207a  test    eax, eax
0x18009207c  js      short loc_18009209D
0x18009207e  lea     rdx, [rsp+2A0h+Name]; pszSubKey
0x180092083  mov     rcx, [rsp+2A0h+hKey]; hkey
0x180092088  call    cs:__imp_SHDeleteKeyW
0x18009208e  mov     ebx, eax
0x180092090  test    eax, eax
0x180092092  jle     short loc_18009209D
0x180092094  movzx   ebx, ax
0x180092097  or      ebx, 80070000h
0x18009209d  lea     rcx, [rsp+2A0h+pszStr2]
0x1800920a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800920a7  nop
0x1800920a8  lea     rcx, [rsp+2A0h+var_258]
0x1800920ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800920b2  nop
0x1800920b3  lea     rcx, [rsp+2A0h+hKey]
0x1800920b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800920bd  mov     eax, ebx
0x1800920bf  mov     rcx, [rbp+1A0h+var_30]
0x1800920c6  xor     rcx, rsp; StackCookie
0x1800920c9  call    __security_check_cookie
0x1800920ce  mov     rbx, [rsp+2A0h+arg_0]
0x1800920d6  add     rsp, 280h
0x1800920dd  pop     r15
0x1800920df  pop     r14
0x1800920e1  pop     rdi
0x1800920e2  pop     rsi
0x1800920e3  pop     rbp
0x1800920e4  retn
```
