# RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>> &)

- ea: `0x18002ae64`
- end: `0x18002b06a`
- name: `?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002b8dc`
- `0x18002cee8`
- `0x18002d040`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x18000eb94`
- `0x180011c30`
- `0x180011ff0`
- `0x180012a70`
- `0x180012dfc`
- `0x18002a4e0`
- `0x18002a514`
- `0x18002a54c`
- `0x18002a738`
- `0x18002ae64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002af5a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002af5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002aee2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002aee2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RegistryKey::SubKeys(HKEY *a1, __int64 a2)
{
  int v4; // eax
  DWORD i; // edi
  int v6; // eax
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v14; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+78h] [rbp-88h]
  __int64 v16; // [rsp+80h] [rbp-80h]
  _BYTE v17[40]; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR lpName[2]; // [rsp+B0h] [rbp-50h] BYREF
  char v19; // [rsp+C0h] [rbp-40h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    SystemError::ThrowHelper(L"RegQueryInfoKey", v4);
  }
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v14);
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
           v17,
           lpName[0],
           cchName);
    if ( v15 == v16 )
    {
      std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        &v14,
        v15,
        v7);
    }
    else
    {
      std::_Construct_in_place<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        v15,
        v7);
      v15 += 32;
    }
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v17);
  }
  if ( (_QWORD **)a2 != &v14 )
  {
    v8 = *(_QWORD **)a2;
    *(_QWORD *)a2 = v14;
    v14 = v8;
    v9 = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a2 + 8) = v15;
    v15 = v9;
    v10 = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = v16;
    v16 = v10;
  }
  if ( (char *)lpName[0] != &v19 )
    HeapAllocator::Free(lpName[0]);
  if ( v14 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v14,
      v15);
    std::_Deallocate<16>(v14, (v16 - (_QWORD)v14) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x18002ae64  mov     [rsp-8+arg_10], rbx
0x18002ae69  mov     [rsp-8+arg_18], rsi
0x18002ae6e  push    rbp
0x18002ae6f  push    rdi
0x18002ae70  push    r14
0x18002ae72  lea     rbp, [rsp-1E0h]
0x18002ae7a  sub     rsp, 2E0h
0x18002ae81  mov     rax, cs:__security_cookie
0x18002ae88  xor     rax, rsp
0x18002ae8b  mov     [rbp+1F0h+var_20], rax
0x18002ae92  mov     rbx, rdx
0x18002ae95  mov     rsi, rcx
0x18002ae98  xor     r14d, r14d
0x18002ae9b  mov     [rsp+2F0h+cSubKeys], r14d
0x18002aea0  mov     [rsp+2F0h+cbMaxSubKeyLen], r14d
0x18002aea5  mov     [rsp+2F0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18002aeaa  mov     [rsp+2F0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18002aeaf  mov     [rsp+2F0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18002aeb4  mov     [rsp+2F0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18002aeb9  mov     [rsp+2F0h+lpcValues], r14; lpcValues
0x18002aebe  mov     [rsp+2F0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18002aec3  lea     rax, [rsp+2F0h+cbMaxSubKeyLen]
0x18002aec8  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002aecd  lea     rax, [rsp+2F0h+cSubKeys]
0x18002aed2  mov     [rsp+2F0h+lpcSubKeys], rax; lpcSubKeys
0x18002aed7  xor     r9d, r9d; lpReserved
0x18002aeda  xor     r8d, r8d; lpcchClass
0x18002aedd  xor     edx, edx; lpClass
0x18002aedf  mov     rcx, [rcx]; hKey
0x18002aee2  call    cs:__imp_RegQueryInfoKeyW
0x18002aee8  test    eax, eax
0x18002aeea  jz      short loc_18002AF05
0x18002aeec  jle     short loc_18002AEF6
0x18002aeee  movzx   eax, ax
0x18002aef1  or      eax, 80070000h
0x18002aef6  mov     edx, eax; int
0x18002aef8  lea     rcx, aRegqueryinfoke; "RegQueryInfoKey"
0x18002aeff  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18002af05  lea     rcx, [rsp+2F0h+var_280]
0x18002af0a  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18002af0f  nop
0x18002af10  mov     edx, [rsp+2F0h+cbMaxSubKeyLen]
0x18002af14  inc     edx
0x18002af16  lea     rcx, [rbp+1F0h+lpName]
0x18002af1a  call    ??0?$PodVector@_W$0?0@@QEAA@_K@Z; PodVector<wchar_t,-1>::PodVector<wchar_t,-1>(unsigned __int64)
0x18002af1f  nop
0x18002af20  mov     edi, r14d
0x18002af23  cmp     edi, [rsp+2F0h+cSubKeys]
0x18002af27  jnb     loc_18002AFCB
0x18002af2d  mov     rax, [rbp+1F0h+var_238]
0x18002af31  shr     rax, 1
0x18002af34  mov     [rsp+2F0h+cchName], eax
0x18002af38  mov     [rsp+2F0h+lpcValues], r14; lpftLastWriteTime
0x18002af3d  mov     [rsp+2F0h+lpcbMaxClassLen], r14; lpcchClass
0x18002af42  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r14; lpClass
0x18002af47  mov     [rsp+2F0h+lpcSubKeys], r14; lpReserved
0x18002af4c  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x18002af51  mov     r8, [rbp+1F0h+lpName]; lpName
0x18002af55  mov     edx, edi; dwIndex
0x18002af57  mov     rcx, [rsi]; hKey
0x18002af5a  call    cs:__imp_RegEnumKeyExW
0x18002af60  test    eax, eax
0x18002af62  jnz     short loc_18002AFB2
0x18002af64  mov     r8d, [rsp+2F0h+cchName]
0x18002af69  mov     rdx, [rbp+1F0h+lpName]
0x18002af6d  lea     rcx, [rbp+1F0h+var_268]
0x18002af71  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const,unsigned __int64)
0x18002af76  mov     rdx, rax
0x18002af79  mov     rcx, [rsp+2F0h+var_278]
0x18002af7e  cmp     rcx, [rbp+1F0h+var_270]
0x18002af82  jz      short loc_18002AF91
0x18002af84  call    ??$_Construct_in_place@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V12@@std@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@@Z; std::_Construct_in_place<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x18002af89  add     [rsp+2F0h+var_278], 20h ; ' '
0x18002af8f  jmp     short loc_18002AFA2
0x18002af91  mov     r8, rdx
0x18002af94  mov     rdx, rcx
0x18002af97  lea     rcx, [rsp+2F0h+var_280]
0x18002af9c  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x18002afa1  nop
0x18002afa2  lea     rcx, [rbp+1F0h+var_268]
0x18002afa6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002afab  inc     edi
0x18002afad  jmp     loc_18002AF23
0x18002afb2  jle     short loc_18002AFBC
0x18002afb4  movzx   eax, ax
0x18002afb7  or      eax, 80070000h
0x18002afbc  mov     edx, eax; int
0x18002afbe  lea     rcx, aRegenumkeyex; "RegEnumKeyEx"
0x18002afc5  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18002afcb  lea     rax, [rsp+2F0h+var_280]
0x18002afd0  cmp     rbx, rax
0x18002afd3  jz      short loc_18002B007
0x18002afd5  mov     rcx, [rbx]
0x18002afd8  mov     rax, [rsp+2F0h+var_280]
0x18002afdd  mov     [rbx], rax
0x18002afe0  mov     [rsp+2F0h+var_280], rcx
0x18002afe5  mov     rcx, [rbx+8]
0x18002afe9  mov     rax, [rsp+2F0h+var_278]
0x18002afee  mov     [rbx+8], rax
0x18002aff2  mov     [rsp+2F0h+var_278], rcx
0x18002aff7  mov     rcx, [rbx+10h]
0x18002affb  mov     rax, [rbp+1F0h+var_270]
0x18002afff  mov     [rbx+10h], rax
0x18002b003  mov     [rbp+1F0h+var_270], rcx
0x18002b007  lea     rax, [rbp+1F0h+var_230]
0x18002b00b  mov     rcx, [rbp+1F0h+lpName]; void *
0x18002b00f  cmp     rcx, rax
0x18002b012  jz      short loc_18002B01A
0x18002b014  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002b019  nop
0x18002b01a  mov     rcx, [rsp+2F0h+var_280]
0x18002b01f  test    rcx, rcx
0x18002b022  jz      short loc_18002B043
0x18002b024  mov     rdx, [rsp+2F0h+var_278]
0x18002b029  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002b02e  mov     rcx, [rsp+2F0h+var_280]
0x18002b033  mov     rdx, [rbp+1F0h+var_270]
0x18002b037  sub     rdx, rcx
0x18002b03a  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b03e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b043  mov     rcx, [rbp+1F0h+var_20]
0x18002b04a  xor     rcx, rsp; StackCookie
0x18002b04d  call    __security_check_cookie
0x18002b052  lea     r11, [rsp+2F0h+var_10]
0x18002b05a  mov     rbx, [r11+30h]
0x18002b05e  mov     rsi, [r11+38h]
0x18002b062  mov     rsp, r11
0x18002b065  pop     r14
0x18002b067  pop     rdi
0x18002b068  pop     rbp
0x18002b069  retn
```
