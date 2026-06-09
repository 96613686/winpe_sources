# RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>> &)

- ea: `0x18000d0f8`
- end: `0x18000d331`
- name: `?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z`
- size: `569`
- prototype: `void __fastcall(HKEY *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18000f77c`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000aafc`
- `0x18000ab70`
- `0x18000c7b8`
- `0x18000c880`
- `0x18000cc1c`
- `0x18000d0f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d203`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d203`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d174`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d174`

## pseudocode

```c
void __fastcall RegistryKey::SubKeys(HKEY *a1, __int64 *a2)
{
  LSTATUS v4; // eax
  unsigned __int64 v5; // rbx
  _BYTE *v6; // rdx
  DWORD v7; // esi
  LSTATUS v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  __int128 v17; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  LPCVOID lpMem[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v20; // [rsp+98h] [rbp-68h]
  _BYTE *v21; // [rsp+B0h] [rbp-50h]
  __int64 v22; // [rsp+B8h] [rbp-48h]
  _BYTE v23[512]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v24; // [rsp+2C0h] [rbp+1C0h]

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    SystemError::Throw<long>((__int64)L"RegQueryInfoKey", v4);
  v17 = 0;
  v18 = 0;
  v5 = 2LL * (cbMaxSubKeyLen + 1);
  if ( v5 <= 0x200 )
  {
    v6 = v23;
    v21 = v23;
    v5 = 512;
    v22 = 512;
  }
  else
  {
    v6 = operator new(2LL * (cbMaxSubKeyLen + 1));
    v21 = v6;
    v22 = v5;
  }
  v24 = 0;
  v7 = 0;
  if ( cSubKeys )
  {
    while ( 1 )
    {
      cchName = v5 >> 1;
      v8 = RegEnumKeyExW(*a1, v7, (LPWSTR)v6, &cchName, 0, 0, 0, 0);
      if ( v8 )
        SystemError::Throw<long>((__int64)L"RegEnumKeyEx", v8);
      *(_OWORD *)lpMem = 0;
      v20 = 0;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
        lpMem,
        v21,
        cchName);
      v9 = *((_QWORD *)&v17 + 1);
      if ( *((_QWORD *)&v17 + 1) == v18 )
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
          &v17,
          *((_QWORD *)&v17 + 1),
          lpMem);
        v10 = *((_QWORD *)&v20 + 1);
      }
      else
      {
        **((_OWORD **)&v17 + 1) = *(_OWORD *)lpMem;
        *(_OWORD *)(v9 + 16) = v20;
        v10 = 7;
        LOWORD(lpMem[0]) = 0;
        *((_QWORD *)&v17 + 1) += 32LL;
      }
      if ( v10 > 7 )
        operator delete((void *)lpMem[0]);
      ++v7;
      v6 = v21;
      if ( v7 >= cSubKeys )
        break;
      v5 = v22;
    }
  }
  if ( a2 != (__int64 *)&v17 )
  {
    v11 = *a2;
    *a2 = v17;
    *(_QWORD *)&v17 = v11;
    v12 = a2[1];
    a2[1] = *((_QWORD *)&v17 + 1);
    *((_QWORD *)&v17 + 1) = v12;
    v13 = a2[2];
    a2[2] = v18;
    v18 = v13;
  }
  if ( v6 != v23 )
    operator delete(v6);
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>((void **)&v17);
}

```

## disassembly

```asm
0x18000d0f8  mov     [rsp-8+arg_10], rbx
0x18000d0fd  push    rbp
0x18000d0fe  push    rsi
0x18000d0ff  push    rdi
0x18000d100  push    r14
0x18000d102  push    r15
0x18000d104  lea     rbp, [rsp-1E0h]
0x18000d10c  sub     rsp, 2E0h
0x18000d113  mov     rax, cs:__security_cookie
0x18000d11a  xor     rax, rsp
0x18000d11d  mov     [rbp+200h+var_30], rax
0x18000d124  mov     rdi, rdx
0x18000d127  mov     r14, rcx
0x18000d12a  xor     r15d, r15d
0x18000d12d  mov     [rsp+300h+cSubKeys], r15d
0x18000d132  mov     [rsp+300h+cbMaxSubKeyLen], r15d
0x18000d137  mov     [rsp+300h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000d13c  mov     [rsp+300h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000d141  mov     [rsp+300h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000d146  mov     [rsp+300h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000d14b  mov     [rsp+300h+lpcValues], r15; lpcValues
0x18000d150  mov     [rsp+300h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000d155  lea     rax, [rsp+300h+cbMaxSubKeyLen]
0x18000d15a  mov     [rsp+300h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000d15f  lea     rax, [rsp+300h+cSubKeys]
0x18000d164  mov     [rsp+300h+lpcSubKeys], rax; lpcSubKeys
0x18000d169  xor     r9d, r9d; lpReserved
0x18000d16c  xor     r8d, r8d; lpcchClass
0x18000d16f  xor     edx, edx; lpClass
0x18000d171  mov     rcx, [rcx]; hKey
0x18000d174  call    cs:__imp_RegQueryInfoKeyW
0x18000d17a  test    eax, eax
0x18000d17c  jnz     loc_18000D322
0x18000d182  xorps   xmm0, xmm0
0x18000d185  movdqu  [rsp+300h+var_290], xmm0
0x18000d18b  mov     [rbp+200h+var_280], r15
0x18000d18f  mov     ebx, [rsp+300h+cbMaxSubKeyLen]
0x18000d193  inc     ebx
0x18000d195  add     rbx, rbx
0x18000d198  mov     eax, 200h
0x18000d19d  cmp     rbx, rax
0x18000d1a0  jbe     short loc_18000D1B7
0x18000d1a2  mov     rcx, rbx; dwBytes
0x18000d1a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d1aa  mov     rdx, rax
0x18000d1ad  mov     [rbp+200h+var_250], rax
0x18000d1b1  mov     [rbp+200h+var_248], rbx
0x18000d1b5  jmp     short loc_18000D1C6
0x18000d1b7  lea     rdx, [rbp+200h+var_240]
0x18000d1bb  mov     [rbp+200h+var_250], rdx
0x18000d1bf  mov     rbx, rax
0x18000d1c2  mov     [rbp+200h+var_248], rax
0x18000d1c6  mov     [rbp+200h+var_40], r15
0x18000d1cd  mov     esi, r15d
0x18000d1d0  cmp     [rsp+300h+cSubKeys], r15d
0x18000d1d5  jbe     loc_18000D295
0x18000d1db  shr     rbx, 1
0x18000d1de  mov     [rsp+300h+cchName], ebx
0x18000d1e2  mov     [rsp+300h+lpcValues], r15; lpftLastWriteTime
0x18000d1e7  mov     [rsp+300h+lpcbMaxClassLen], r15; lpcchClass
0x18000d1ec  mov     [rsp+300h+lpcbMaxSubKeyLen], r15; lpClass
0x18000d1f1  mov     [rsp+300h+lpcSubKeys], r15; lpReserved
0x18000d1f6  lea     r9, [rsp+300h+cchName]; lpcchName
0x18000d1fb  mov     r8, rdx; lpName
0x18000d1fe  mov     edx, esi; dwIndex
0x18000d200  mov     rcx, [r14]; hKey
0x18000d203  call    cs:__imp_RegEnumKeyExW
0x18000d209  test    eax, eax
0x18000d20b  jnz     loc_18000D313
0x18000d211  xorps   xmm0, xmm0
0x18000d214  movups  xmmword ptr [rbp+200h+lpMem], xmm0
0x18000d218  xorps   xmm1, xmm1
0x18000d21b  movdqu  [rbp+200h+var_268], xmm1
0x18000d220  mov     r8d, [rsp+300h+cchName]
0x18000d225  mov     rdx, [rbp+200h+var_250]
0x18000d229  lea     rcx, [rbp+200h+lpMem]
0x18000d22d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d232  nop
0x18000d233  mov     rdx, qword ptr [rsp+300h+var_290+8]
0x18000d238  cmp     rdx, [rbp+200h+var_280]
0x18000d23c  jz      short loc_18000D25F
0x18000d23e  movups  xmm0, xmmword ptr [rbp+200h+lpMem]
0x18000d242  movups  xmmword ptr [rdx], xmm0
0x18000d245  movups  xmm1, [rbp+200h+var_268]
0x18000d249  movups  xmmword ptr [rdx+10h], xmm1
0x18000d24d  mov     ecx, 7
0x18000d252  mov     word ptr [rbp+200h+lpMem], r15w
0x18000d257  add     qword ptr [rsp+300h+var_290+8], 20h ; ' '
0x18000d25d  jmp     short loc_18000D271
0x18000d25f  lea     r8, [rbp+200h+lpMem]
0x18000d263  lea     rcx, [rsp+300h+var_290]
0x18000d268  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::_Emplace_reallocate<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&)
0x18000d26d  mov     rcx, qword ptr [rbp+200h+var_268+8]
0x18000d271  cmp     rcx, 7
0x18000d275  jbe     short loc_18000D280
0x18000d277  mov     rcx, [rbp+200h+lpMem]; lpMem
0x18000d27b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d280  inc     esi
0x18000d282  mov     rdx, [rbp+200h+var_250]
0x18000d286  cmp     esi, [rsp+300h+cSubKeys]
0x18000d28a  jnb     short loc_18000D295
0x18000d28c  mov     rbx, [rbp+200h+var_248]
0x18000d290  jmp     loc_18000D1DB
0x18000d295  lea     rax, [rsp+300h+var_290]
0x18000d29a  cmp     rdi, rax
0x18000d29d  jz      short loc_18000D2D1
0x18000d29f  mov     rcx, [rdi]
0x18000d2a2  mov     rax, qword ptr [rsp+300h+var_290]
0x18000d2a7  mov     [rdi], rax
0x18000d2aa  mov     qword ptr [rsp+300h+var_290], rcx
0x18000d2af  mov     rcx, [rdi+8]
0x18000d2b3  mov     rax, qword ptr [rsp+300h+var_290+8]
0x18000d2b8  mov     [rdi+8], rax
0x18000d2bc  mov     qword ptr [rsp+300h+var_290+8], rcx
0x18000d2c1  mov     rcx, [rdi+10h]
0x18000d2c5  mov     rax, [rbp+200h+var_280]
0x18000d2c9  mov     [rdi+10h], rax
0x18000d2cd  mov     [rbp+200h+var_280], rcx
0x18000d2d1  lea     rax, [rbp+200h+var_240]
0x18000d2d5  cmp     rdx, rax
0x18000d2d8  jz      short loc_18000D2E3
0x18000d2da  mov     rcx, rdx; lpMem
0x18000d2dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d2e2  nop
0x18000d2e3  lea     rcx, [rsp+300h+var_290]
0x18000d2e8  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18000d2ed  mov     rcx, [rbp+200h+var_30]
0x18000d2f4  xor     rcx, rsp; StackCookie
0x18000d2f7  call    __security_check_cookie
0x18000d2fc  mov     rbx, [rsp+300h+arg_10]
0x18000d304  add     rsp, 2E0h
0x18000d30b  pop     r15
0x18000d30d  pop     r14
0x18000d30f  pop     rdi
0x18000d310  pop     rsi
0x18000d311  pop     rbp
0x18000d312  retn
0x18000d313  mov     edx, eax
0x18000d315  lea     rcx, aRegenumkeyex; "RegEnumKeyEx"
0x18000d31c  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x18000d322  mov     edx, eax
0x18000d324  lea     rcx, aRegqueryinfoke; "RegQueryInfoKey"
0x18000d32b  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
