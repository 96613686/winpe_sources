# CSchemaCache::_AddPropertySchemaPath(ushort const *)

- ea: `0x180091974`
- end: `0x180091cca`
- name: `?_AddPropertySchemaPath@CSchemaCache@@AEAAJPEBG@Z`
- size: `854`
- prototype: `__int64 __fastcall(CSchemaCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x180091170`

## callees

- `0x180003c70`
- `0x180004148`
- `0x18000457c`
- `0x180025dd4`
- `0x18006114c`
- `0x180064148`
- `0x18006d3e0`
- `0x18006ed20`
- `0x18008fa74`
- `0x18008fc28`
- `0x180091974`
- `0x1800920ec`
- `0x1800926e8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091b22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091b22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091af0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091af0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180091b6d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180091bf9`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180091b6d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180091bf9`

## string_xrefs

- `0x180091a3d`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180091b33`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180091bbc`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSchemaCache::_AddPropertySchemaPath(CSchemaCache *this, const unsigned __int16 *a2)
{
  int v3; // edi
  struct IMigrationContext *v4; // rdx
  int v5; // ebx
  unsigned int v6; // edx
  SCHEMA_REGISTRATION_DATA *v7; // rcx
  __int64 v9; // rax
  int v10; // edx
  _BYTE *v11; // r14
  _QWORD *v12; // rsi
  __int64 v13; // r13
  HKEY *v14; // r15
  LPCWSTR *v15; // r12
  int v16; // edi
  int v17; // eax
  unsigned int v18; // edx
  SCHEMA_REGISTRATION_DATA *v19; // rcx
  unsigned int v20; // edx
  SCHEMA_REGISTRATION_DATA *v21; // rcx
  int v22; // [rsp+20h] [rbp-99h]
  int v23; // [rsp+20h] [rbp-99h]
  bool v24; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-71h] BYREF
  int v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+54h] [rbp-65h] BYREF
  CSchemaCache *v28; // [rsp+58h] [rbp-61h]
  SCHEMA_REGISTRATION_DATA **v29; // [rsp+60h] [rbp-59h] BYREF
  struct SCHEMA_REGISTRATION_DATA *v30; // [rsp+68h] [rbp-51h] BYREF
  char v31; // [rsp+70h] [rbp-49h]
  _BYTE *v32; // [rsp+88h] [rbp-31h]
  _QWORD *v33; // [rsp+90h] [rbp-29h]
  __int64 v34; // [rsp+98h] [rbp-21h]
  HKEY *v35; // [rsp+A0h] [rbp-19h]
  LPCWSTR *v36; // [rsp+A8h] [rbp-11h]
  char v37; // [rsp+B0h] [rbp-9h]
  bool v38; // [rsp+B8h] [rbp-1h] BYREF
  SCHEMA_REGISTRATION_DATA *v39; // [rsp+C0h] [rbp+7h] BYREF
  unsigned __int16 *v40; // [rsp+C8h] [rbp+Fh] BYREF
  HKEY v41; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = (int)this;
  v28 = this;
  v39 = 0;
  v38 = 0;
  v24 = 0;
  v41 = 0;
  v40 = 0;
  v25 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v25,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v40,
    0);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v41,
    0);
  v29 = &v39;
  v30 = 0;
  v31 = 1;
  v5 = AddPropertySchemaPathToRegistry(a2, v4, &v38, &v24, &v30, &v41, &v40, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(&v29);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x488,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v5,
      v22);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
    v7 = v39;
    v39 = 0;
LABEL_3:
    if ( v7 )
      SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(v7, v6);
    return (unsigned int)v5;
  }
  v9 = lambda_4e01028c1d19006666dacb404ab50b19_::_lambda_4e01028c1d19006666dacb404ab50b19_(
         (unsigned int)&v29,
         (unsigned int)&v38,
         (unsigned int)&v39,
         v3,
         (__int64)&v41,
         (__int64)&v40);
  v11 = *(_BYTE **)v9;
  v32 = *(_BYTE **)v9;
  v12 = *(_QWORD **)(v9 + 8);
  v33 = v12;
  v13 = *(_QWORD *)(v9 + 16);
  v34 = v13;
  v14 = *(HKEY **)(v9 + 24);
  v35 = v14;
  v15 = *(LPCWSTR **)(v9 + 32);
  v36 = v15;
  v37 = 1;
  v16 = 0;
  v26 = 0;
  v27 = 0;
  if ( v24 )
  {
    EnterCriticalSection(&CSchemaCache::s_critsec);
    v5 = CSchemaCache::_BuildCacheFromXML((IUnknown **)v28, v39, v25, 1u, &v26, 0);
    LeaveCriticalSection(&CSchemaCache::s_critsec);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A0,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)v5,
        v23);
      if ( !*v11 && *v12 )
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(v13 + 16) + 40LL))(
          *(_QWORD *)(v13 + 16),
          *v12,
          2);
LABEL_11:
      SHDeleteKeyW(*v14, *v15);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
      v7 = v39;
      v39 = 0;
      goto LABEL_3;
    }
    v16 = v26;
  }
  v17 = CSchemaCache::_ForceRebuildGlobalMapping(v28, v10, &v27);
  v5 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v17,
      v23);
    if ( !*v11 && *v12 )
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(v13 + 16) + 40LL))(*(_QWORD *)(v13 + 16), *v12, 2);
    goto LABEL_11;
  }
  if ( v16 || v27 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
    v21 = v39;
    v39 = 0;
    if ( v21 )
      SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(v21, v20);
    return 262560;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
    v19 = v39;
    v39 = 0;
    if ( v19 )
      SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(v19, v18);
    return 0;
  }
}

```

## disassembly

```asm
0x180091974  mov     [rsp-8+arg_10], rbx
0x180091979  push    rbp
0x18009197a  push    rsi
0x18009197b  push    rdi
0x18009197c  push    r12
0x18009197e  push    r13
0x180091980  push    r14
0x180091982  push    r15
0x180091984  lea     rbp, [rsp-27h]
0x180091989  sub     rsp, 0E0h
0x180091990  mov     rax, cs:__security_cookie
0x180091997  xor     rax, rsp
0x18009199a  mov     [rbp+57h+var_38], rax
0x18009199e  mov     rbx, rdx
0x1800919a1  mov     rdi, rcx
0x1800919a4  mov     [rbp+57h+var_B8], rcx
0x1800919a8  xor     esi, esi
0x1800919aa  mov     [rbp+57h+var_50], rsi
0x1800919ae  mov     [rbp+57h+var_58], sil
0x1800919b2  mov     [rbp+57h+var_D0], sil
0x1800919b6  mov     [rbp+57h+var_40], rsi
0x1800919ba  mov     [rbp+57h+var_48], rsi
0x1800919be  mov     [rbp+57h+var_C8], rsi
0x1800919c2  xor     edx, edx
0x1800919c4  lea     rcx, [rbp+57h+var_C8]
0x1800919c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800919cd  xor     edx, edx
0x1800919cf  lea     rcx, [rbp+57h+var_48]
0x1800919d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800919d8  xor     edx, edx
0x1800919da  lea     rcx, [rbp+57h+var_40]
0x1800919de  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800919e3  lea     rax, [rbp+57h+var_50]
0x1800919e7  mov     [rbp+57h+var_B0], rax
0x1800919eb  mov     [rbp+57h+var_A8], rsi
0x1800919ef  mov     [rbp+57h+var_A0], 1
0x1800919f3  lea     rax, [rbp+57h+var_C8]
0x1800919f7  mov     [rsp+110h+var_D8], rax; unsigned __int16 **
0x1800919fc  lea     rax, [rbp+57h+var_48]
0x180091a00  mov     [rsp+110h+var_E0], rax; unsigned __int16 **
0x180091a05  lea     rax, [rbp+57h+var_40]
0x180091a09  mov     [rsp+110h+var_E8], rax; HKEY *
0x180091a0e  lea     rax, [rbp+57h+var_A8]
0x180091a12  mov     [rsp+110h+var_F0], rax; int
0x180091a17  lea     r9, [rbp+57h+var_D0]; bool *
0x180091a1b  lea     r8, [rbp+57h+var_58]; bool *
0x180091a1f  mov     rcx, rbx; pszPath
0x180091a22  call    ?AddPropertySchemaPathToRegistry@@YAJPEBGPEAUIMigrationContext@@PEA_N2PEAPEAUSCHEMA_REGISTRATION_DATA@@PEAPEAUHKEY__@@PEAPEAG5@Z; AddPropertySchemaPathToRegistry(ushort const *,IMigrationContext *,bool *,bool *,SCHEMA_REGISTRATION_DATA * *,HKEY__ * *,ushort * *,ushort * *)
0x180091a27  mov     ebx, eax
0x180091a29  lea     rcx, [rbp+57h+var_B0]
0x180091a2d  call    ??1?$out_param_t@V?$unique_ptr@USCHEMA_REGISTRATION_DATA@@U?$default_delete@USCHEMA_REGISTRATION_DATA@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(void)
0x180091a32  test    ebx, ebx
0x180091a34  jns     short loc_180091A86
0x180091a36  mov     rcx, [rbp+5Fh]; this
0x180091a3a  mov     r9d, ebx; char *
0x180091a3d  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180091a44  mov     edx, 488h; void *
0x180091a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091a4e  nop
0x180091a4f  lea     rcx, [rbp+57h+var_C8]
0x180091a53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091a58  nop
0x180091a59  lea     rcx, [rbp+57h+var_48]
0x180091a5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091a62  nop
0x180091a63  lea     rcx, [rbp+57h+var_40]
0x180091a67  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091a6c  nop
0x180091a6d  mov     rcx, [rbp+57h+var_50]; this
0x180091a71  mov     [rbp+57h+var_50], rsi
0x180091a75  test    rcx, rcx
0x180091a78  jz      short loc_180091A7F
0x180091a7a  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x180091a7f  mov     eax, ebx
0x180091a81  jmp     loc_180091CA3
0x180091a86  lea     rax, [rbp+57h+var_48]
0x180091a8a  mov     [rsp+110h+var_E8], rax
0x180091a8f  lea     rax, [rbp+57h+var_40]
0x180091a93  mov     [rsp+110h+var_F0], rax
0x180091a98  mov     r9, rdi
0x180091a9b  lea     r8, [rbp+57h+var_50]
0x180091a9f  lea     rdx, [rbp+57h+var_58]
0x180091aa3  lea     rcx, [rbp+57h+var_B0]
0x180091aa7  call    _lambda_4e01028c1d19006666dacb404ab50b19____lambda_4e01028c1d19006666dacb404ab50b19_
0x180091aac  mov     r14, [rax]
0x180091aaf  mov     [rbp+57h+var_88], r14
0x180091ab3  mov     rsi, [rax+8]
0x180091ab7  mov     [rbp+57h+var_80], rsi
0x180091abb  mov     r13, [rax+10h]
0x180091abf  mov     [rbp+57h+var_78], r13
0x180091ac3  mov     r15, [rax+18h]
0x180091ac7  mov     [rbp+57h+var_70], r15
0x180091acb  mov     r12, [rax+20h]
0x180091acf  mov     [rbp+57h+var_68], r12
0x180091ad3  mov     [rbp+57h+var_60], 1
0x180091ad7  xor     edi, edi
0x180091ad9  mov     [rbp+57h+var_C0], edi
0x180091adc  mov     [rbp+57h+var_BC], edi
0x180091adf  cmp     [rbp+57h+var_D0], dil
0x180091ae3  jz      loc_180091BA2
0x180091ae9  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x180091af0  call    cs:__imp_EnterCriticalSection
0x180091af6  mov     [rsp+110h+var_E8], rdi; struct IMemoryMappedCache **
0x180091afb  lea     rax, [rbp+57h+var_C0]
0x180091aff  mov     [rsp+110h+var_F0], rax; int
0x180091b04  lea     r9d, [rdi+1]; int
0x180091b08  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x180091b0c  mov     rdx, [rbp+57h+var_50]; struct SCHEMA_REGISTRATION_DATA *
0x180091b10  mov     rcx, [rbp+57h+var_B8]; this
0x180091b14  call    ?_BuildCacheFromXML@CSchemaCache@@AEAAJPEBUSCHEMA_REGISTRATION_DATA@@PEBGHPEAHPEAPEAUIMemoryMappedCache@@@Z; CSchemaCache::_BuildCacheFromXML(SCHEMA_REGISTRATION_DATA const *,ushort const *,int,int *,IMemoryMappedCache * *)
0x180091b19  mov     ebx, eax
0x180091b1b  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x180091b22  call    cs:__imp_LeaveCriticalSection
0x180091b28  test    ebx, ebx
0x180091b2a  jns     short loc_180091B9F
0x180091b2c  mov     rcx, [rbp+5Fh]; this
0x180091b30  mov     r9d, ebx; char *
0x180091b33  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180091b3a  mov     edx, 4A0h; void *
0x180091b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091b44  nop
0x180091b45  cmp     [r14], dil
0x180091b48  jnz     short loc_180091B66
0x180091b4a  mov     rdx, [rsi]
0x180091b4d  test    rdx, rdx
0x180091b50  jz      short loc_180091B66
0x180091b52  mov     rcx, [r13+10h]
0x180091b56  mov     rax, [rcx]
0x180091b59  lea     r8d, [rdi+2]
0x180091b5d  mov     rax, [rax+28h]
0x180091b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b66  mov     rdx, [r12]; pszSubKey
0x180091b6a  mov     rcx, [r15]; hkey
0x180091b6d  call    cs:__imp_SHDeleteKeyW
0x180091b73  nop
0x180091b74  lea     rcx, [rbp+57h+var_C8]
0x180091b78  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091b7d  nop
0x180091b7e  lea     rcx, [rbp+57h+var_48]
0x180091b82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091b87  nop
0x180091b88  lea     rcx, [rbp+57h+var_40]
0x180091b8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091b91  nop
0x180091b92  mov     rcx, [rbp+57h+var_50]
0x180091b96  mov     [rbp+57h+var_50], rdi
0x180091b9a  jmp     loc_180091A75
0x180091b9f  mov     edi, [rbp+57h+var_C0]
0x180091ba2  lea     r8, [rbp+57h+var_BC]; int *
0x180091ba6  mov     rcx, [rbp+57h+var_B8]; this
0x180091baa  call    ?_ForceRebuildGlobalMapping@CSchemaCache@@AEAAJHPEAH@Z; CSchemaCache::_ForceRebuildGlobalMapping(int,int *)
0x180091baf  mov     ebx, eax
0x180091bb1  test    eax, eax
0x180091bb3  jns     short loc_180091C2F
0x180091bb5  mov     rcx, [rbp+5Fh]; this
0x180091bb9  mov     r9d, eax; char *
0x180091bbc  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180091bc3  mov     edx, 4A3h; void *
0x180091bc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091bcd  nop
0x180091bce  cmp     byte ptr [r14], 0
0x180091bd2  jnz     short loc_180091BF2
0x180091bd4  mov     rdx, [rsi]
0x180091bd7  test    rdx, rdx
0x180091bda  jz      short loc_180091BF2
0x180091bdc  mov     rcx, [r13+10h]
0x180091be0  mov     rax, [rcx]
0x180091be3  mov     r8d, 2
0x180091be9  mov     rax, [rax+28h]
0x180091bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091bf2  mov     rdx, [r12]; pszSubKey
0x180091bf6  mov     rcx, [r15]; hkey
0x180091bf9  call    cs:__imp_SHDeleteKeyW
0x180091bff  nop
0x180091c00  lea     rcx, [rbp+57h+var_C8]
0x180091c04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091c09  nop
0x180091c0a  lea     rcx, [rbp+57h+var_48]
0x180091c0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091c13  nop
0x180091c14  lea     rcx, [rbp+57h+var_40]
0x180091c18  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091c1d  nop
0x180091c1e  mov     rcx, [rbp+57h+var_50]
0x180091c22  mov     [rbp+57h+var_50], 0
0x180091c2a  jmp     loc_180091A75
0x180091c2f  xor     ebx, ebx
0x180091c31  test    edi, edi
0x180091c33  jnz     short loc_180091C6E
0x180091c35  cmp     [rbp+57h+var_BC], ebx
0x180091c38  jnz     short loc_180091C6E
0x180091c3a  lea     rcx, [rbp+57h+var_C8]
0x180091c3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091c43  nop
0x180091c44  lea     rcx, [rbp+57h+var_48]
0x180091c48  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091c4d  nop
0x180091c4e  lea     rcx, [rbp+57h+var_40]
0x180091c52  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091c57  nop
0x180091c58  mov     rcx, [rbp+57h+var_50]; this
0x180091c5c  mov     [rbp+57h+var_50], rbx
0x180091c60  test    rcx, rcx
0x180091c63  jz      short loc_180091C6A
0x180091c65  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x180091c6a  xor     eax, eax
0x180091c6c  jmp     short loc_180091CA3
0x180091c6e  lea     rcx, [rbp+57h+var_C8]
0x180091c72  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091c77  nop
0x180091c78  lea     rcx, [rbp+57h+var_48]
0x180091c7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180091c81  nop
0x180091c82  lea     rcx, [rbp+57h+var_40]
0x180091c86  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091c8b  nop
0x180091c8c  mov     rcx, [rbp+57h+var_50]; this
0x180091c90  mov     [rbp+57h+var_50], rbx
0x180091c94  test    rcx, rcx
0x180091c97  jz      short loc_180091C9E
0x180091c99  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x180091c9e  mov     eax, 401A0h
0x180091ca3  mov     rcx, [rbp+57h+var_38]
0x180091ca7  xor     rcx, rsp; StackCookie
0x180091caa  call    __security_check_cookie
0x180091caf  mov     rbx, [rsp+110h+arg_10]
0x180091cb7  add     rsp, 0E0h
0x180091cbe  pop     r15
0x180091cc0  pop     r14
0x180091cc2  pop     r13
0x180091cc4  pop     r12
0x180091cc6  pop     rdi
0x180091cc7  pop     rsi
0x180091cc8  pop     rbp
0x180091cc9  retn
```
