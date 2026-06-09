# OobeUpdateSettingsElevatedManagerCore::CommitUpdateSettings(uint,uchar *)

- ea: `0x1800125b0`
- end: `0x18001274e`
- name: `?CommitUpdateSettings@OobeUpdateSettingsElevatedManagerCore@@UEAAJIPEAE@Z`
- size: `414`
- prototype: `__int64 __fastcall(OobeUpdateSettingsElevatedManagerCore *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180009814`
- `0x18000ac18`
- `0x18000ae3c`
- `0x18000b098`
- `0x18000b200`
- `0x1800125b0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001269f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001269f`

## string_xrefs

- `0x18001262c`: `shellcommon\shell\oobe\core\components\com\oobeupdatesettingscore.cpp`
- `0x1800126e8`: `shellcommon\shell\oobe\core\components\com\oobeupdatesettingscore.cpp`
- `0x18001270d`: `shellcommon\shell\oobe\core\components\com\oobeupdatesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall OobeUpdateSettingsElevatedManagerCore::CommitUpdateSettings(
        OobeUpdateSettingsElevatedManagerCore *this,
        int a2,
        unsigned __int8 *a3)
{
  __int64 *i; // rbx
  unsigned int v6; // esi
  const unsigned __int16 *v7; // r14
  const unsigned __int16 *v8; // r15
  const unsigned __int16 *v9; // r12
  const WCHAR *v10; // rdi
  int v11; // eax
  int RedirectionKeyPath; // eax
  __int64 v13; // rdx
  HRESULT v14; // eax
  unsigned int v15; // edi
  PWSTR v16; // rdx
  PWSTR ppszPathOut[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  bool v19; // [rsp+78h] [rbp+48h] BYREF
  PCWSTR pszPathIn; // [rsp+88h] [rbp+58h] BYREF

  if ( a2 != 2 )
    return 2147942487LL;
  for ( i = &`OobeUpdateSettingsElevatedManagerCore::CommitUpdateSettings'::`2'::UpdateSettings;
        i != (__int64 *)&aProxyFileList;
        i += 6 )
  {
    v6 = *((_DWORD *)i + 10);
    v7 = (const unsigned __int16 *)i[3];
    v8 = (const unsigned __int16 *)i[4];
    v9 = (const unsigned __int16 *)i[1];
    if ( !a3[*(int *)i] )
      v6 = *((_DWORD *)i + 11);
    v10 = (const WCHAR *)i[2];
    v11 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)i[3], (const unsigned __int16 *)i[4], v6);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobeupdatesettingscore.cpp",
        (const char *)(unsigned int)v11,
        (int)ppszPathOut[0]);
    pszPathIn = 0;
    v19 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPathIn,
      0);
    RedirectionKeyPath = Details::TryGetRedirectionKeyPath(v9, v7, &pszPathIn, &v19);
    if ( RedirectionKeyPath < 0 )
    {
      v13 = 47;
LABEL_17:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobeupdatesettingscore.cpp",
        (const char *)(unsigned int)RedirectionKeyPath,
        (int)ppszPathOut[0]);
      goto LABEL_18;
    }
    if ( v19 )
    {
      if ( v10 )
      {
        ppszPathOut[0] = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          ppszPathOut,
          0);
        v14 = PathAllocCombine(pszPathIn, v10, 0, ppszPathOut);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x36,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobeupdatesettingscore.cpp",
            (const char *)(unsigned int)v14,
            (int)ppszPathOut[0]);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
          return v15;
        }
        v16 = ppszPathOut[0];
        ppszPathOut[0] = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszPathIn,
          v16);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppszPathOut);
      }
      RedirectionKeyPath = SHRegSetDWORD(HKEY_LOCAL_MACHINE, pszPathIn, v8, v6);
      if ( RedirectionKeyPath < 0 )
      {
        v13 = 58;
        goto LABEL_17;
      }
    }
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  }
  return 0;
}

```

## disassembly

```asm
0x1800125b0  mov     [rsp-38h+arg_0], rbx
0x1800125b5  push    rbp
0x1800125b6  push    rsi
0x1800125b7  push    rdi
0x1800125b8  push    r12
0x1800125ba  push    r13
0x1800125bc  push    r14
0x1800125be  push    r15
0x1800125c0  mov     rbp, rsp
0x1800125c3  sub     rsp, 30h
0x1800125c7  mov     r13, r8
0x1800125ca  cmp     edx, 2
0x1800125cd  jz      short loc_1800125D9
0x1800125cf  mov     eax, 80070057h
0x1800125d4  jmp     loc_180012739
0x1800125d9  lea     rbx, ?UpdateSettings@?1??CommitUpdateSettings@OobeUpdateSettingsElevatedManagerCore@@UEAAJIPEAE@Z@4QBU_unnamed_type_UpdateSettings_@?1??12@UEAAJI0@Z@B; `OobeUpdateSettingsElevatedManagerCore::CommitUpdateSettings(uint,uchar *)'::`2'::_unnamed_type_UpdateSettings_ const near * const `OobeUpdateSettingsElevatedManagerCore::CommitUpdateSettings(uint,uchar *)'::`2'::UpdateSettings
0x1800125e0  lea     rax, aProxyFileList
0x1800125e7  cmp     rbx, rax
0x1800125ea  jz      loc_180012737
0x1800125f0  movsxd  rax, dword ptr [rbx]
0x1800125f3  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800125fa  mov     esi, [rbx+28h]
0x1800125fd  mov     r14, [rbx+18h]
0x180012601  mov     r15, [rbx+20h]
0x180012605  mov     rdx, r14; unsigned __int16 *
0x180012608  cmp     byte ptr [rax+r13], 0
0x18001260d  mov     r8, r15; unsigned __int16 *
0x180012610  mov     r12, [rbx+8]
0x180012614  cmovz   esi, [rbx+2Ch]
0x180012618  mov     rdi, [rbx+10h]
0x18001261c  mov     r9d, esi; unsigned int
0x18001261f  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180012624  test    eax, eax
0x180012626  jns     short loc_180012640
0x180012628  mov     rcx, [rbp+38h]; this
0x18001262c  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\oobe\\core\\compone"...
0x180012633  mov     r9d, eax; char *
0x180012636  mov     edx, 29h ; ')'; void *
0x18001263b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012640  xor     edx, edx
0x180012642  mov     [rbp+pszPathIn], 0
0x18001264a  lea     rcx, [rbp+pszPathIn]
0x18001264e  mov     [rbp+arg_8], 0
0x180012652  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180012657  lea     r9, [rbp+arg_8]; bool *
0x18001265b  mov     rdx, r14; unsigned __int16 *
0x18001265e  lea     r8, [rbp+pszPathIn]; unsigned __int16 **
0x180012662  mov     rcx, r12; unsigned __int16 *
0x180012665  call    ?TryGetRedirectionKeyPath@Details@@YAJPEBG0PEAPEAGPEA_N@Z; Details::TryGetRedirectionKeyPath(ushort const *,ushort const *,ushort * *,bool *)
0x18001266a  xor     r14d, r14d
0x18001266d  test    eax, eax
0x18001266f  jns     short loc_180012677
0x180012671  lea     edx, [r14+2Fh]
0x180012675  jmp     short loc_1800126E4
0x180012677  cmp     [rbp+arg_8], r14b
0x18001267b  jz      short loc_1800126F7
0x18001267d  test    rdi, rdi
0x180012680  jz      short loc_1800126C5
0x180012682  xor     edx, edx
0x180012684  mov     [rbp+ppszPathOut], r14
0x180012688  lea     rcx, [rbp+ppszPathOut]
0x18001268c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180012691  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x180012695  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180012699  xor     r8d, r8d; dwFlags
0x18001269c  mov     rdx, rdi; pszMore
0x18001269f  call    cs:__imp_PathAllocCombine
0x1800126a5  mov     edi, eax
0x1800126a7  test    eax, eax
0x1800126a9  js      short loc_180012709
0x1800126ab  mov     rdx, [rbp+ppszPathOut]
0x1800126af  lea     rcx, [rbp+pszPathIn]
0x1800126b3  mov     [rbp+ppszPathOut], r14
0x1800126b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800126bc  lea     rcx, [rbp+ppszPathOut]
0x1800126c0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800126c5  mov     rdx, [rbp+pszPathIn]; unsigned __int16 *
0x1800126c9  mov     r9d, esi; unsigned int
0x1800126cc  mov     r8, r15; unsigned __int16 *
0x1800126cf  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800126d6  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800126db  test    eax, eax
0x1800126dd  jns     short loc_1800126F7
0x1800126df  mov     edx, 3Ah ; ':'; void *
0x1800126e4  mov     rcx, [rbp+38h]; this
0x1800126e8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800126ef  mov     r9d, eax; char *
0x1800126f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800126f7  lea     rcx, [rbp+pszPathIn]
0x1800126fb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012700  add     rbx, 30h ; '0'
0x180012704  jmp     loc_1800125E0
0x180012709  mov     rcx, [rbp+38h]; this
0x18001270d  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\oobe\\core\\compone"...
0x180012714  mov     r9d, edi; char *
0x180012717  mov     edx, 36h ; '6'; void *
0x18001271c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012721  lea     rcx, [rbp+ppszPathOut]
0x180012725  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001272a  lea     rcx, [rbp+pszPathIn]
0x18001272e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012733  mov     eax, edi
0x180012735  jmp     short loc_180012739
0x180012737  xor     eax, eax
0x180012739  mov     rbx, [rsp+30h+arg_0]
0x18001273e  add     rsp, 30h
0x180012742  pop     r15
0x180012744  pop     r14
0x180012746  pop     r13
0x180012748  pop     r12
0x18001274a  pop     rdi
0x18001274b  pop     rsi
0x18001274c  pop     rbp
0x18001274d  retn
```
