# RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>> &)

- ea: `0x180031930`
- end: `0x180031b3a`
- name: `?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z`
- size: `522`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001a99c`
- `0x18001c0a8`
- `0x18001c1e4`

## callees

- `0x180002af0`
- `0x18001206c`
- `0x180017e48`
- `0x18001a1c0`
- `0x18001a6d4`
- `0x18002fef4`
- `0x1800302e0`
- `0x180030c84`
- `0x18003101c`
- `0x180031054`
- `0x180031240`
- `0x180031930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031a2c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031a2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800319ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800319ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryKey::SubKeys(HKEY *a1, __int64 *a2)
{
  int v4; // eax
  DWORD i; // edi
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 result; // rax
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v15; // [rsp+70h] [rbp-90h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  __int64 v17; // [rsp+80h] [rbp-80h]
  _BYTE v18[40]; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR lpName[68]; // [rsp+B0h] [rbp-50h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    SystemError::ThrowHelper(L"RegQueryInfoKey", v4);
  }
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v15);
  PodVector<wchar_t,-1>::PodVector<wchar_t,-1>(lpName, cbMaxSubKeyLen + 1);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = (unsigned __int64)lpName[1] >> 1;
    v6 = RegEnumKeyExW(*a1, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v6 )
    {
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      SystemError::ThrowHelper(L"RegEnumKeyEx", v6);
    }
    v7 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
           v18,
           lpName[0],
           cchName);
    if ( v16 == v17 )
    {
      std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        &v15,
        v16,
        v7);
    }
    else
    {
      std::_Construct_in_place<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        v16,
        v7);
      v16 += 32;
    }
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v18);
  }
  if ( a2 != &v15 )
  {
    v8 = *a2;
    *a2 = v15;
    v15 = v8;
    v9 = a2[1];
    a2[1] = v16;
    v16 = v9;
    v10 = a2[2];
    a2[2] = v17;
    v17 = v10;
  }
  result = TempBuffer<520>::Destroy(lpName);
  if ( v15 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v15,
      v16);
    return std::_Deallocate<16>(v15, (v17 - v15) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x180031930  mov     [rsp-8+arg_10], rbx
0x180031935  mov     [rsp-8+arg_18], rsi
0x18003193a  push    rbp
0x18003193b  push    rdi
0x18003193c  push    r14
0x18003193e  lea     rbp, [rsp-1E0h]
0x180031946  sub     rsp, 2E0h
0x18003194d  mov     rax, cs:__security_cookie
0x180031954  xor     rax, rsp
0x180031957  mov     [rbp+1F0h+var_20], rax
0x18003195e  mov     rbx, rdx
0x180031961  mov     rsi, rcx
0x180031964  xor     r14d, r14d
0x180031967  mov     [rsp+2F0h+cSubKeys], r14d
0x18003196c  mov     [rsp+2F0h+cbMaxSubKeyLen], r14d
0x180031971  mov     [rsp+2F0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180031976  mov     [rsp+2F0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18003197b  mov     [rsp+2F0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180031980  mov     [rsp+2F0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180031985  mov     [rsp+2F0h+lpcValues], r14; lpcValues
0x18003198a  mov     [rsp+2F0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18003198f  lea     rax, [rsp+2F0h+cbMaxSubKeyLen]
0x180031994  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180031999  lea     rax, [rsp+2F0h+cSubKeys]
0x18003199e  mov     [rsp+2F0h+lpcSubKeys], rax; lpcSubKeys
0x1800319a3  xor     r9d, r9d; lpReserved
0x1800319a6  xor     r8d, r8d; lpcchClass
0x1800319a9  xor     edx, edx; lpClass
0x1800319ab  mov     rcx, [rcx]; hKey
0x1800319ae  call    cs:__imp_RegQueryInfoKeyW
0x1800319b5  nop     dword ptr [rax+rax+00h]
0x1800319ba  test    eax, eax
0x1800319bc  jz      short loc_1800319D7
0x1800319be  jle     short loc_1800319C8
0x1800319c0  movzx   eax, ax
0x1800319c3  or      eax, 80070000h
0x1800319c8  mov     edx, eax; int
0x1800319ca  lea     rcx, aRegqueryinfoke; "RegQueryInfoKey"
0x1800319d1  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x1800319d7  lea     rcx, [rsp+2F0h+var_280]
0x1800319dc  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x1800319e1  nop
0x1800319e2  mov     edx, [rsp+2F0h+cbMaxSubKeyLen]
0x1800319e6  inc     edx
0x1800319e8  lea     rcx, [rbp+1F0h+lpName]
0x1800319ec  call    ??0?$PodVector@_W$0?0@@QEAA@_K@Z; PodVector<wchar_t,-1>::PodVector<wchar_t,-1>(unsigned __int64)
0x1800319f1  nop
0x1800319f2  mov     edi, r14d
0x1800319f5  cmp     edi, [rsp+2F0h+cSubKeys]
0x1800319f9  jnb     loc_180031AA3
0x1800319ff  mov     rax, [rbp+1F0h+var_238]
0x180031a03  shr     rax, 1
0x180031a06  mov     [rsp+2F0h+cchName], eax
0x180031a0a  mov     [rsp+2F0h+lpcValues], r14; lpftLastWriteTime
0x180031a0f  mov     [rsp+2F0h+lpcbMaxClassLen], r14; lpcchClass
0x180031a14  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r14; lpClass
0x180031a19  mov     [rsp+2F0h+lpcSubKeys], r14; lpReserved
0x180031a1e  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x180031a23  mov     r8, [rbp+1F0h+lpName]; lpName
0x180031a27  mov     edx, edi; dwIndex
0x180031a29  mov     rcx, [rsi]; hKey
0x180031a2c  call    cs:__imp_RegEnumKeyExW
0x180031a33  nop     dword ptr [rax+rax+00h]
0x180031a38  test    eax, eax
0x180031a3a  jnz     short loc_180031A8A
0x180031a3c  mov     r8d, [rsp+2F0h+cchName]
0x180031a41  mov     rdx, [rbp+1F0h+lpName]
0x180031a45  lea     rcx, [rbp+1F0h+var_268]
0x180031a49  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const,unsigned __int64)
0x180031a4e  mov     rdx, rax
0x180031a51  mov     rcx, [rsp+2F0h+var_278]
0x180031a56  cmp     rcx, [rbp+1F0h+var_270]
0x180031a5a  jz      short loc_180031A69
0x180031a5c  call    ??$_Construct_in_place@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V12@@std@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@@Z; std::_Construct_in_place<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x180031a61  add     [rsp+2F0h+var_278], 20h ; ' '
0x180031a67  jmp     short loc_180031A7A
0x180031a69  mov     r8, rdx
0x180031a6c  mov     rdx, rcx
0x180031a6f  lea     rcx, [rsp+2F0h+var_280]
0x180031a74  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x180031a79  nop
0x180031a7a  lea     rcx, [rbp+1F0h+var_268]
0x180031a7e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180031a83  inc     edi
0x180031a85  jmp     loc_1800319F5
0x180031a8a  jle     short loc_180031A94
0x180031a8c  movzx   eax, ax
0x180031a8f  or      eax, 80070000h
0x180031a94  mov     edx, eax; int
0x180031a96  lea     rcx, aRegenumkeyex; "RegEnumKeyEx"
0x180031a9d  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x180031aa3  lea     rax, [rsp+2F0h+var_280]
0x180031aa8  cmp     rbx, rax
0x180031aab  jz      short loc_180031ADF
0x180031aad  mov     rcx, [rbx]
0x180031ab0  mov     rax, [rsp+2F0h+var_280]
0x180031ab5  mov     [rbx], rax
0x180031ab8  mov     [rsp+2F0h+var_280], rcx
0x180031abd  mov     rcx, [rbx+8]
0x180031ac1  mov     rax, [rsp+2F0h+var_278]
0x180031ac6  mov     [rbx+8], rax
0x180031aca  mov     [rsp+2F0h+var_278], rcx
0x180031acf  mov     rcx, [rbx+10h]
0x180031ad3  mov     rax, [rbp+1F0h+var_270]
0x180031ad7  mov     [rbx+10h], rax
0x180031adb  mov     [rbp+1F0h+var_270], rcx
0x180031adf  lea     rcx, [rbp+1F0h+lpName]
0x180031ae3  call    ?Destroy@?$TempBuffer@$0CAI@@@AEAAXXZ; TempBuffer<520>::Destroy(void)
0x180031ae8  nop
0x180031ae9  mov     rcx, [rsp+2F0h+var_280]
0x180031aee  test    rcx, rcx
0x180031af1  jz      short loc_180031B12
0x180031af3  mov     rdx, [rsp+2F0h+var_278]
0x180031af8  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x180031afd  mov     rcx, [rsp+2F0h+var_280]
0x180031b02  mov     rdx, [rbp+1F0h+var_270]
0x180031b06  sub     rdx, rcx
0x180031b09  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180031b0d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180031b12  mov     rcx, [rbp+1F0h+var_20]
0x180031b19  xor     rcx, rsp; StackCookie
0x180031b1c  call    __security_check_cookie
0x180031b21  lea     r11, [rsp+2F0h+var_10]
0x180031b29  mov     rbx, [r11+30h]
0x180031b2d  mov     rsi, [r11+38h]
0x180031b31  mov     rsp, r11
0x180031b34  pop     r14
0x180031b36  pop     rdi
0x180031b37  pop     rbp
0x180031b38  retn
```
