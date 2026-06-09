# RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>> &)

- ea: `0x180030784`
- end: `0x18003098a`
- name: `?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180019fbc`
- `0x18001b698`
- `0x18001b7cc`

## callees

- `0x180002a90`
- `0x1800072cc`
- `0x180011908`
- `0x18001755c`
- `0x1800197d8`
- `0x180019cf0`
- `0x18002edf4`
- `0x18002f1a8`
- `0x18002fe0c`
- `0x18002fe40`
- `0x18003002c`
- `0x180030784`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003087a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003087a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180030802`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180030802`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RegistryKey::SubKeys(HKEY *a1, __int64 a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD i; // edi
  int v8; // eax
  __int64 v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h]
  __int64 v18; // [rsp+80h] [rbp-80h]
  _BYTE v19[40]; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR lpName[2]; // [rsp+B0h] [rbp-50h] BYREF
  char v21; // [rsp+C0h] [rbp-40h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    SystemError::ThrowHelper(L"RegQueryInfoKey", v4);
  }
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v16);
  PodVector<wchar_t,-1>::PodVector<wchar_t,-1>(lpName, cbMaxSubKeyLen + 1);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = (unsigned __int64)lpName[1] >> 1;
    v8 = RegEnumKeyExW(*a1, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      SystemError::ThrowHelper(L"RegEnumKeyEx", v8);
    }
    v9 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
           v19,
           lpName[0],
           cchName);
    if ( v17 == v18 )
    {
      std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        &v16,
        v17,
        v9);
    }
    else
    {
      std::_Construct_in_place<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        v17,
        v9);
      v17 += 32;
    }
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v19);
  }
  if ( (_QWORD **)a2 != &v16 )
  {
    v10 = *(_QWORD **)a2;
    *(_QWORD *)a2 = v16;
    v16 = v10;
    v11 = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a2 + 8) = v17;
    v17 = v11;
    v12 = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = v18;
    v18 = v12;
  }
  if ( (char *)lpName[0] != &v21 )
    HeapAllocator::Free(lpName[0]);
  if ( v16 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v16,
      v17,
      v5,
      v6);
    std::_Deallocate<16>(v16, (v18 - (_QWORD)v16) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x180030784  mov     [rsp-8+arg_10], rbx
0x180030789  mov     [rsp-8+arg_18], rsi
0x18003078e  push    rbp
0x18003078f  push    rdi
0x180030790  push    r14
0x180030792  lea     rbp, [rsp-1E0h]
0x18003079a  sub     rsp, 2E0h
0x1800307a1  mov     rax, cs:__security_cookie
0x1800307a8  xor     rax, rsp
0x1800307ab  mov     [rbp+1F0h+var_20], rax
0x1800307b2  mov     rbx, rdx
0x1800307b5  mov     rsi, rcx
0x1800307b8  xor     r14d, r14d
0x1800307bb  mov     [rsp+2F0h+cSubKeys], r14d
0x1800307c0  mov     [rsp+2F0h+cbMaxSubKeyLen], r14d
0x1800307c5  mov     [rsp+2F0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800307ca  mov     [rsp+2F0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800307cf  mov     [rsp+2F0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800307d4  mov     [rsp+2F0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800307d9  mov     [rsp+2F0h+lpcValues], r14; lpcValues
0x1800307de  mov     [rsp+2F0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800307e3  lea     rax, [rsp+2F0h+cbMaxSubKeyLen]
0x1800307e8  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800307ed  lea     rax, [rsp+2F0h+cSubKeys]
0x1800307f2  mov     [rsp+2F0h+lpcSubKeys], rax; lpcSubKeys
0x1800307f7  xor     r9d, r9d; lpReserved
0x1800307fa  xor     r8d, r8d; lpcchClass
0x1800307fd  xor     edx, edx; lpClass
0x1800307ff  mov     rcx, [rcx]; hKey
0x180030802  call    cs:__imp_RegQueryInfoKeyW
0x180030808  test    eax, eax
0x18003080a  jz      short loc_180030825
0x18003080c  jle     short loc_180030816
0x18003080e  movzx   eax, ax
0x180030811  or      eax, 80070000h
0x180030816  mov     edx, eax; int
0x180030818  lea     rcx, aRegqueryinfoke; "RegQueryInfoKey"
0x18003081f  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x180030825  lea     rcx, [rsp+2F0h+var_280]
0x18003082a  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18003082f  nop
0x180030830  mov     edx, [rsp+2F0h+cbMaxSubKeyLen]
0x180030834  inc     edx
0x180030836  lea     rcx, [rbp+1F0h+lpName]
0x18003083a  call    ??0?$PodVector@_W$0?0@@QEAA@_K@Z; PodVector<wchar_t,-1>::PodVector<wchar_t,-1>(unsigned __int64)
0x18003083f  nop
0x180030840  mov     edi, r14d
0x180030843  cmp     edi, [rsp+2F0h+cSubKeys]
0x180030847  jnb     loc_1800308EB
0x18003084d  mov     rax, [rbp+1F0h+var_238]
0x180030851  shr     rax, 1
0x180030854  mov     [rsp+2F0h+cchName], eax
0x180030858  mov     [rsp+2F0h+lpcValues], r14; lpftLastWriteTime
0x18003085d  mov     [rsp+2F0h+lpcbMaxClassLen], r14; lpcchClass
0x180030862  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r14; lpClass
0x180030867  mov     [rsp+2F0h+lpcSubKeys], r14; lpReserved
0x18003086c  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x180030871  mov     r8, [rbp+1F0h+lpName]; lpName
0x180030875  mov     edx, edi; dwIndex
0x180030877  mov     rcx, [rsi]; hKey
0x18003087a  call    cs:__imp_RegEnumKeyExW
0x180030880  test    eax, eax
0x180030882  jnz     short loc_1800308D2
0x180030884  mov     r8d, [rsp+2F0h+cchName]
0x180030889  mov     rdx, [rbp+1F0h+lpName]
0x18003088d  lea     rcx, [rbp+1F0h+var_268]
0x180030891  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const,unsigned __int64)
0x180030896  mov     rdx, rax
0x180030899  mov     rcx, [rsp+2F0h+var_278]
0x18003089e  cmp     rcx, [rbp+1F0h+var_270]
0x1800308a2  jz      short loc_1800308B1
0x1800308a4  call    ??$_Construct_in_place@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V12@@std@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@@Z; std::_Construct_in_place<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x1800308a9  add     [rsp+2F0h+var_278], 20h ; ' '
0x1800308af  jmp     short loc_1800308C2
0x1800308b1  mov     r8, rdx
0x1800308b4  mov     rdx, rcx
0x1800308b7  lea     rcx, [rsp+2F0h+var_280]
0x1800308bc  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x1800308c1  nop
0x1800308c2  lea     rcx, [rbp+1F0h+var_268]
0x1800308c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800308cb  inc     edi
0x1800308cd  jmp     loc_180030843
0x1800308d2  jle     short loc_1800308DC
0x1800308d4  movzx   eax, ax
0x1800308d7  or      eax, 80070000h
0x1800308dc  mov     edx, eax; int
0x1800308de  lea     rcx, aRegenumkeyex; "RegEnumKeyEx"
0x1800308e5  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x1800308eb  lea     rax, [rsp+2F0h+var_280]
0x1800308f0  cmp     rbx, rax
0x1800308f3  jz      short loc_180030927
0x1800308f5  mov     rcx, [rbx]
0x1800308f8  mov     rax, [rsp+2F0h+var_280]
0x1800308fd  mov     [rbx], rax
0x180030900  mov     [rsp+2F0h+var_280], rcx
0x180030905  mov     rcx, [rbx+8]
0x180030909  mov     rax, [rsp+2F0h+var_278]
0x18003090e  mov     [rbx+8], rax
0x180030912  mov     [rsp+2F0h+var_278], rcx
0x180030917  mov     rcx, [rbx+10h]
0x18003091b  mov     rax, [rbp+1F0h+var_270]
0x18003091f  mov     [rbx+10h], rax
0x180030923  mov     [rbp+1F0h+var_270], rcx
0x180030927  lea     rax, [rbp+1F0h+var_230]
0x18003092b  mov     rcx, [rbp+1F0h+lpName]; void *
0x18003092f  cmp     rcx, rax
0x180030932  jz      short loc_18003093A
0x180030934  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030939  nop
0x18003093a  mov     rcx, [rsp+2F0h+var_280]
0x18003093f  test    rcx, rcx
0x180030942  jz      short loc_180030963
0x180030944  mov     rdx, [rsp+2F0h+var_278]
0x180030949  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18003094e  mov     rcx, [rsp+2F0h+var_280]
0x180030953  mov     rdx, [rbp+1F0h+var_270]
0x180030957  sub     rdx, rcx
0x18003095a  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18003095e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180030963  mov     rcx, [rbp+1F0h+var_20]
0x18003096a  xor     rcx, rsp; StackCookie
0x18003096d  call    __security_check_cookie
0x180030972  lea     r11, [rsp+2F0h+var_10]
0x18003097a  mov     rbx, [r11+30h]
0x18003097e  mov     rsi, [r11+38h]
0x180030982  mov     rsp, r11
0x180030985  pop     r14
0x180030987  pop     rdi
0x180030988  pop     rbp
0x180030989  retn
```
