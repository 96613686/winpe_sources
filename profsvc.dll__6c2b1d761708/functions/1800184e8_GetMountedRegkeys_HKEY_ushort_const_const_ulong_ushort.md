# GetMountedRegkeys(HKEY__ *,ushort const * const *,ulong,ushort * *)

- ea: `0x1800184e8`
- end: `0x1800186f1`
- name: `?GetMountedRegkeys@@YAJPEAUHKEY__@@PEBQEBGKPEAPEAG@Z`
- size: `521`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *const *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017e3c`

## callees

- `0x180005330`
- `0x18000dc10`
- `0x18000e1a0`
- `0x180010420`
- `0x1800184e8`
- `0x18001a0f0`
- `0x180030ad0`
- `0x180031060`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018607`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018607`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180018551`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180018551`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800185d6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800185d6`

## string_xrefs

- `0x180018565`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18001866f`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x1800186ae`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

## pseudocode

```c
int __fastcall GetMountedRegkeys(HKEY hKey, const unsigned __int16 *const *a2, unsigned int a3, unsigned __int16 **a4)
{
  unsigned int v4; // edi
  unsigned int v9; // eax
  DWORD i; // esi
  int v12; // eax
  int v13; // edi
  __int64 v14; // rdx
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-39h]
  DWORD cSubKeys; // [rsp+68h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp+Bh] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp+Fh] BYREF
  _QWORD v19[4]; // [rsp+78h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  DWORD cbMaxSubKeyLen; // [rsp+E0h] [rbp+7Fh] BYREF

  v4 = 0;
  *a4 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x8B,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
             (const char *)v9,
             lpcSubKeys);
  cchName = cbMaxSubKeyLen + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    cbMaxSubKeyLen + 1);
  if ( lpName )
  {
    memset(v19, 0, 24);
    for ( i = 0; i < cSubKeys; ++i )
    {
      if ( !RegEnumKeyExW(hKey, i, lpName, &cchName, 0, 0, 0, 0) )
      {
        while ( v4 < a3 )
        {
          if ( CompareStringOrdinal(lpName, -1, a2[v4], -1, 1) == 2 )
            goto LABEL_11;
          ++v4;
        }
        v12 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                v19,
                L"%ws, ",
                lpName);
        v13 = v12;
        if ( v12 >= 0 )
        {
LABEL_11:
          v4 = 0;
          continue;
        }
        v14 = 158;
        goto LABEL_18;
      }
    }
    if ( v19[0] )
    {
      if ( *(_WORD *)v19[0] )
      {
        v12 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(v19, a4);
        v13 = v12;
        if ( v12 < 0 )
        {
          v14 = 165;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
            (const char *)(unsigned int)v12,
            lpcSubKeys);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v19);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
          return v13;
        }
      }
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v19);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
      (const char *)0x8007000ELL,
      lpcSubKeys);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x1800184e8  mov     rax, rsp
0x1800184eb  mov     [rax+8], rsi
0x1800184ef  mov     [rax+10h], rdi
0x1800184f3  push    rbp
0x1800184f4  push    r12
0x1800184f6  push    r13
0x1800184f8  push    r14
0x1800184fa  push    r15
0x1800184fc  lea     rbp, [rax-5Fh]
0x180018500  sub     rsp, 90h
0x180018507  xor     edi, edi
0x180018509  mov     r14, r9
0x18001850c  mov     [rax-60h], rdi
0x180018510  mov     r15d, r8d
0x180018513  mov     [rax-68h], rdi
0x180018517  mov     r13, rdx
0x18001851a  mov     [rax-70h], rdi
0x18001851e  xor     r8d, r8d; lpcchClass
0x180018521  mov     [rax-78h], rdi
0x180018525  xor     edx, edx; lpClass
0x180018527  mov     [rax-80h], rdi
0x18001852b  mov     r12, rcx
0x18001852e  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180018532  mov     [rsp+0B0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180018537  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001853c  lea     rax, [rbp+57h+cSubKeys]
0x180018540  mov     [r9], rdi
0x180018543  xor     r9d, r9d; lpReserved
0x180018546  mov     [rsp+0B0h+lpcSubKeys], rax; int
0x18001854b  mov     [rbp+57h+cSubKeys], edi
0x18001854e  mov     [rbp+57h+cbMaxSubKeyLen], edi
0x180018551  call    cs:__imp_RegQueryInfoKeyW
0x180018558  nop     dword ptr [rax+rax+00h]
0x18001855d  test    eax, eax
0x18001855f  jz      short loc_18001857E
0x180018561  mov     rcx, [rbp+5Fh]; this
0x180018565  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001856c  mov     r9d, eax; char *
0x18001856f  mov     edx, 8Bh; void *
0x180018574  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018579  jmp     loc_1800186D3
0x18001857e  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180018581  lea     rcx, [rbp+57h+lpName]
0x180018585  inc     eax
0x180018587  xor     edx, edx
0x180018589  mov     r8d, eax
0x18001858c  mov     [rbp+57h+cchName], eax
0x18001858f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180018594  cmp     [rbp+57h+lpName], rdi
0x180018598  jz      loc_1800186AA
0x18001859e  mov     [rbp+57h+var_40], rdi
0x1800185a2  mov     esi, edi
0x1800185a4  mov     [rbp+57h+var_38], rdi
0x1800185a8  mov     [rbp+57h+var_30], rdi
0x1800185ac  cmp     esi, [rbp+57h+cSubKeys]
0x1800185af  jnb     loc_180018646
0x1800185b5  mov     r8, [rbp+57h+lpName]; lpName
0x1800185b9  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800185bd  mov     [rsp+0B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800185c2  mov     edx, esi; dwIndex
0x1800185c4  mov     [rsp+0B0h+lpcbMaxClassLen], rdi; lpcchClass
0x1800185c9  mov     rcx, r12; hKey
0x1800185cc  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800185d1  mov     [rsp+0B0h+lpcSubKeys], rdi; lpReserved
0x1800185d6  call    cs:__imp_RegEnumKeyExW
0x1800185dd  nop     dword ptr [rax+rax+00h]
0x1800185e2  test    eax, eax
0x1800185e4  jnz     short loc_180018638
0x1800185e6  cmp     edi, r15d
0x1800185e9  jnb     short loc_18001861C
0x1800185eb  mov     rcx, [rbp+57h+lpName]; lpString1
0x1800185ef  or      eax, 0FFFFFFFFh
0x1800185f2  mov     r8d, edi
0x1800185f5  mov     r9d, eax; cchCount2
0x1800185f8  mov     edx, eax; cchCount1
0x1800185fa  mov     dword ptr [rsp+0B0h+lpcSubKeys], 1; bIgnoreCase
0x180018602  mov     r8, [r13+r8*8+0]; lpString2
0x180018607  call    cs:__imp_CompareStringOrdinal
0x18001860e  nop     dword ptr [rax+rax+00h]
0x180018613  cmp     eax, 2
0x180018616  jz      short loc_180018636
0x180018618  inc     edi
0x18001861a  jmp     short loc_1800185E6
0x18001861c  mov     r8, [rbp+57h+lpName]
0x180018620  lea     rdx, aWs_0; "%ws, "
0x180018627  lea     rcx, [rbp+57h+var_40]
0x18001862b  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180018630  mov     edi, eax
0x180018632  test    eax, eax
0x180018634  js      short loc_18001863F
0x180018636  xor     edi, edi
0x180018638  inc     esi
0x18001863a  jmp     loc_1800185AC
0x18001863f  mov     edx, 9Eh
0x180018644  jmp     short loc_18001866B
0x180018646  mov     rax, [rbp+57h+var_40]
0x18001864a  test    rax, rax
0x18001864d  jz      short loc_180018694
0x18001864f  cmp     [rax], di
0x180018652  jz      short loc_180018694
0x180018654  mov     rdx, r14
0x180018657  lea     rcx, [rbp+57h+var_40]
0x18001865b  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180018660  mov     edi, eax
0x180018662  test    eax, eax
0x180018664  jns     short loc_180018694
0x180018666  mov     edx, 0A5h; void *
0x18001866b  mov     rcx, [rbp+5Fh]; this
0x18001866f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018676  mov     r9d, eax; char *
0x180018679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001867e  lea     rcx, [rbp+57h+var_40]
0x180018682  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180018687  lea     rcx, [rbp+57h+lpName]
0x18001868b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018690  mov     eax, edi
0x180018692  jmp     short loc_1800186D3
0x180018694  lea     rcx, [rbp+57h+var_40]
0x180018698  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001869d  lea     rcx, [rbp+57h+lpName]
0x1800186a1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800186a6  xor     eax, eax
0x1800186a8  jmp     short loc_1800186D3
0x1800186aa  mov     rcx, [rbp+5Fh]; this
0x1800186ae  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800186b5  mov     r9d, 8007000Eh; char *
0x1800186bb  mov     edx, 8Fh; void *
0x1800186c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800186c5  lea     rcx, [rbp+57h+lpName]
0x1800186c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800186ce  mov     eax, 8007000Eh
0x1800186d3  lea     r11, [rsp+0B0h+var_20]
0x1800186db  mov     rsi, [r11+30h]
0x1800186df  mov     rdi, [r11+38h]
0x1800186e3  mov     rsp, r11
0x1800186e6  pop     r15
0x1800186e8  pop     r14
0x1800186ea  pop     r13
0x1800186ec  pop     r12
0x1800186ee  pop     rbp
0x1800186ef  retn
```
