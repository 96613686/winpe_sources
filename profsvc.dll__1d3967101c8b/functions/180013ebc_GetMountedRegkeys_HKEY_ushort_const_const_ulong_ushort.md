# GetMountedRegkeys(HKEY__ *,ushort const * const *,ulong,ushort * *)

- ea: `0x180013ebc`
- end: `0x1800140b2`
- name: `?GetMountedRegkeys@@YAJPEAUHKEY__@@PEBQEBGKPEAPEAG@Z`
- size: `502`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *const *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d1c`

## callees

- `0x180007978`
- `0x18000fa10`
- `0x1800111a0`
- `0x180013ebc`
- `0x180015010`
- `0x180016250`
- `0x18002d2d8`
- `0x18002e648`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013fcf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013fcf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013f25`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013f25`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013fa4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013fa4`

## string_xrefs

- `0x180013f33`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180014031`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180014070`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

## pseudocode

```c
int __fastcall GetMountedRegkeys(HKEY hKey, const unsigned __int16 *const *a2, unsigned int a3, unsigned __int16 **a4)
{
  unsigned int v4; // edi
  unsigned int v9; // eax
  const char *v10; // r9
  DWORD i; // esi
  int v13; // eax
  int v14; // edi
  __int64 v15; // rdx
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-39h]
  DWORD cSubKeys; // [rsp+68h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp+Bh] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp+Fh] BYREF
  _QWORD v20[4]; // [rsp+78h] [rbp+17h] BYREF
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
    cbMaxSubKeyLen + 1,
    v10);
  if ( lpName )
  {
    memset(v20, 0, 24);
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
        v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                v20,
                L"%ws, ",
                lpName);
        v14 = v13;
        if ( v13 >= 0 )
        {
LABEL_11:
          v4 = 0;
          continue;
        }
        v15 = 158;
        goto LABEL_18;
      }
    }
    if ( v20[0] )
    {
      if ( *(_WORD *)v20[0] )
      {
        v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
                (__int64)v20,
                a4);
        v14 = v13;
        if ( v13 < 0 )
        {
          v15 = 165;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
            (const char *)(unsigned int)v13,
            lpcSubKeys);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v20);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
          return v14;
        }
      }
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v20);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180013ebc  mov     rax, rsp
0x180013ebf  mov     [rax+8], rsi
0x180013ec3  mov     [rax+10h], rdi
0x180013ec7  push    rbp
0x180013ec8  push    r12
0x180013eca  push    r13
0x180013ecc  push    r14
0x180013ece  push    r15
0x180013ed0  lea     rbp, [rax-5Fh]
0x180013ed4  sub     rsp, 90h
0x180013edb  xor     edi, edi
0x180013edd  mov     r14, r9
0x180013ee0  mov     [rax-60h], rdi
0x180013ee4  mov     r15d, r8d
0x180013ee7  mov     [rax-68h], rdi
0x180013eeb  mov     r13, rdx
0x180013eee  mov     [rax-70h], rdi
0x180013ef2  xor     r8d, r8d; lpcchClass
0x180013ef5  mov     [rax-78h], rdi
0x180013ef9  xor     edx, edx; lpClass
0x180013efb  mov     [rax-80h], rdi
0x180013eff  mov     r12, rcx
0x180013f02  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180013f06  mov     [rsp+0B0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180013f0b  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180013f10  lea     rax, [rbp+57h+cSubKeys]
0x180013f14  mov     [r9], rdi
0x180013f17  xor     r9d, r9d; lpReserved
0x180013f1a  mov     [rsp+0B0h+lpcSubKeys], rax; int
0x180013f1f  mov     [rbp+57h+cSubKeys], edi
0x180013f22  mov     [rbp+57h+cbMaxSubKeyLen], edi
0x180013f25  call    cs:__imp_RegQueryInfoKeyW
0x180013f2b  test    eax, eax
0x180013f2d  jz      short loc_180013F4C
0x180013f2f  mov     rcx, [rbp+5Fh]; this
0x180013f33  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013f3a  mov     r9d, eax; char *
0x180013f3d  mov     edx, 8Bh; void *
0x180013f42  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013f47  jmp     loc_180014095
0x180013f4c  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180013f4f  lea     rcx, [rbp+57h+lpName]
0x180013f53  inc     eax
0x180013f55  xor     edx, edx
0x180013f57  mov     r8d, eax
0x180013f5a  mov     [rbp+57h+cchName], eax
0x180013f5d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180013f62  cmp     [rbp+57h+lpName], rdi
0x180013f66  jz      loc_18001406C
0x180013f6c  mov     [rbp+57h+var_40], rdi
0x180013f70  mov     esi, edi
0x180013f72  mov     [rbp+57h+var_38], rdi
0x180013f76  mov     [rbp+57h+var_30], rdi
0x180013f7a  cmp     esi, [rbp+57h+cSubKeys]
0x180013f7d  jnb     loc_180014008
0x180013f83  mov     r8, [rbp+57h+lpName]; lpName
0x180013f87  lea     r9, [rbp+57h+cchName]; lpcchName
0x180013f8b  mov     [rsp+0B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180013f90  mov     edx, esi; dwIndex
0x180013f92  mov     [rsp+0B0h+lpcbMaxClassLen], rdi; lpcchClass
0x180013f97  mov     rcx, r12; hKey
0x180013f9a  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rdi; lpClass
0x180013f9f  mov     [rsp+0B0h+lpcSubKeys], rdi; lpReserved
0x180013fa4  call    cs:__imp_RegEnumKeyExW
0x180013faa  test    eax, eax
0x180013fac  jnz     short loc_180013FFA
0x180013fae  cmp     edi, r15d
0x180013fb1  jnb     short loc_180013FDE
0x180013fb3  mov     rcx, [rbp+57h+lpName]; lpString1
0x180013fb7  or      eax, 0FFFFFFFFh
0x180013fba  mov     r8d, edi
0x180013fbd  mov     r9d, eax; cchCount2
0x180013fc0  mov     edx, eax; cchCount1
0x180013fc2  mov     dword ptr [rsp+0B0h+lpcSubKeys], 1; bIgnoreCase
0x180013fca  mov     r8, [r13+r8*8+0]; lpString2
0x180013fcf  call    cs:__imp_CompareStringOrdinal
0x180013fd5  cmp     eax, 2
0x180013fd8  jz      short loc_180013FF8
0x180013fda  inc     edi
0x180013fdc  jmp     short loc_180013FAE
0x180013fde  mov     r8, [rbp+57h+lpName]
0x180013fe2  lea     rdx, aWs_0; "%ws, "
0x180013fe9  lea     rcx, [rbp+57h+var_40]
0x180013fed  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180013ff2  mov     edi, eax
0x180013ff4  test    eax, eax
0x180013ff6  js      short loc_180014001
0x180013ff8  xor     edi, edi
0x180013ffa  inc     esi
0x180013ffc  jmp     loc_180013F7A
0x180014001  mov     edx, 9Eh
0x180014006  jmp     short loc_18001402D
0x180014008  mov     rax, [rbp+57h+var_40]
0x18001400c  test    rax, rax
0x18001400f  jz      short loc_180014056
0x180014011  cmp     [rax], di
0x180014014  jz      short loc_180014056
0x180014016  mov     rdx, r14
0x180014019  lea     rcx, [rbp+57h+var_40]
0x18001401d  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180014022  mov     edi, eax
0x180014024  test    eax, eax
0x180014026  jns     short loc_180014056
0x180014028  mov     edx, 0A5h; void *
0x18001402d  mov     rcx, [rbp+5Fh]; this
0x180014031  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014038  mov     r9d, eax; char *
0x18001403b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014040  lea     rcx, [rbp+57h+var_40]
0x180014044  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180014049  lea     rcx, [rbp+57h+lpName]
0x18001404d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014052  mov     eax, edi
0x180014054  jmp     short loc_180014095
0x180014056  lea     rcx, [rbp+57h+var_40]
0x18001405a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001405f  lea     rcx, [rbp+57h+lpName]
0x180014063  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014068  xor     eax, eax
0x18001406a  jmp     short loc_180014095
0x18001406c  mov     rcx, [rbp+5Fh]; this
0x180014070  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014077  mov     r9d, 8007000Eh; char *
0x18001407d  mov     edx, 8Fh; void *
0x180014082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014087  lea     rcx, [rbp+57h+lpName]
0x18001408b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014090  mov     eax, 8007000Eh
0x180014095  lea     r11, [rsp+0B0h+var_20]
0x18001409d  mov     rsi, [r11+30h]
0x1800140a1  mov     rdi, [r11+38h]
0x1800140a5  mov     rsp, r11
0x1800140a8  pop     r15
0x1800140aa  pop     r14
0x1800140ac  pop     r13
0x1800140ae  pop     r12
0x1800140b0  pop     rbp
0x1800140b1  retn
```
