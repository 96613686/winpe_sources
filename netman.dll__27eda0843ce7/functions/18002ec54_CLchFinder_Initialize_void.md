# CLchFinder::Initialize(void)

- ea: `0x18002ec54`
- end: `0x18002efaf`
- name: `?Initialize@CLchFinder@@AEAAJXZ`
- size: `859`
- prototype: `__int64 __fastcall(CLchFinder *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e910`

## callees

- `0x180001710`
- `0x180002380`
- `0x1800043a8`
- `0x180004d04`
- `0x180019c68`
- `0x18001e1e4`
- `0x18001efb8`
- `0x18002e5b0`
- `0x18002e658`
- `0x18002e7e4`
- `0x18002e97c`
- `0x18002ec54`
- `0x18002efb8`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18002ed7d`
- `ADVAPI32!RegEnumKeyExW` at `0x18002ed7d`
- `ADVAPI32!RegCloseKey` at `0x18002eddb`
- `ADVAPI32!RegCloseKey` at `0x18002edf7`
- `ADVAPI32!RegCloseKey` at `0x18002eddb`
- `ADVAPI32!RegCloseKey` at `0x18002edf7`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ed3c`
- `ADVAPI32!RegOpenKeyExW` at `0x18002edab`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ed3c`
- `ADVAPI32!RegOpenKeyExW` at `0x18002edab`
- `KERNEL32!lstrcmpW` at `0x18002eef1`
- `KERNEL32!lstrcmpW` at `0x18002eef1`

## pseudocode

```c
__int64 __fastcall CLchFinder::Initialize(CLchFinder *this)
{
  unsigned int v3; // r14d
  DWORD v4; // edi
  LSTATUS v5; // esi
  __int64 v6; // rcx
  void *v7; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  unsigned int i; // edi
  __int64 v11; // r13
  __int64 v12; // rcx
  char v13; // al
  __int64 v14; // rsi
  const WCHAR *v15; // r15
  unsigned int j; // esi
  __int64 v17; // rcx
  _QWORD **v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rbx
  DWORD cchName; // [rsp+40h] [rbp-308h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-300h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-2F8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-2F0h] BYREF
  __int128 v25; // [rsp+68h] [rbp-2E0h] BYREF
  _BYTE v26[16]; // [rsp+78h] [rbp-2D0h] BYREF
  __int64 v27; // [rsp+88h] [rbp-2C0h]
  _BYTE v28[32]; // [rsp+90h] [rbp-2B8h] BYREF
  WCHAR Name[40]; // [rsp+B0h] [rbp-298h] BYREF
  wchar_t Buffer[264]; // [rsp+100h] [rbp-248h] BYREF

  if ( *((_DWORD *)this + 3) )
    return 0;
  *((_DWORD *)this + 3) = 1;
  if ( !*((_QWORD *)this + 2) )
    return 2147549183LL;
  try
  {
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
    v3 = 0;
    v24 = 0;
    std::list<CLch *>::_Alloc_sentinel_and_proxy(&v24);
    v25 = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(&v25);
    if ( swprintf_s(
           Buffer,
           0x104u,
           L"%s\\%s",
           L"SYSTEM\\CurrentControlSet\\Control\\Network\\LightweightCallHandlers",
           *((_QWORD *)this + 2)) != -1 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey) )
      {
        v4 = 0;
        do
        {
          while ( 1 )
          {
            cchName = 40;
            v5 = RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0);
            if ( v5 )
              break;
            phkResult = 0;
            if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
              break;
            CLchFinder::AddHandlersForCall(v6, phkResult, Name, &v24, &v25);
            RegCloseKey(phkResult);
            ++v4;
          }
          ++v4;
        }
        while ( !v5 );
        RegCloseKey(hKey);
      }
    }
    if ( *((_QWORD *)&v24 + 1) )
    {
      v7 = MemAlloc(saturated_mul(*((unsigned __int64 *)&v24 + 1), 8u));
      *(_QWORD *)this = v7;
      if ( v7 )
      {
        v8 = (_QWORD *)v24;
        v9 = *(_QWORD **)v24;
        while ( v9 != v8 )
        {
          *(_QWORD *)(*(_QWORD *)this + 8LL * (unsigned int)(*((_DWORD *)this + 2))++) = v9[2];
          v9 = (_QWORD *)*v9;
          v8 = (_QWORD *)v24;
        }
        for ( i = 0; i < *((_DWORD *)this + 2); ++i )
        {
          v11 = *(_QWORD *)(*(_QWORD *)this + 8LL * i);
          std::wstring::wstring(v28, v11 + 80);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
            &v25,
            v26,
            v28);
          v13 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Lower_bound_duplicate<std::wstring>(
                  v12,
                  v27,
                  v28);
          v14 = v25;
          if ( v13 )
            v14 = v27;
          std::wstring::_Tidy_deallocate(v28);
          if ( v14 != (_QWORD)v25 )
          {
            v15 = (const WCHAR *)(v14 + 64);
            if ( *(_QWORD *)(v14 + 88) > 7u )
              v15 = *(const WCHAR **)v15;
            for ( j = 0; j < *((_DWORD *)this + 2); ++j )
            {
              if ( !lstrcmpW((LPCWSTR)(*(_QWORD *)(*(_QWORD *)this + 8LL * j) + 80LL), v15) )
              {
                v17 = *(_QWORD *)(*(_QWORD *)this + 8LL * j);
                goto LABEL_31;
              }
            }
            v17 = 0;
LABEL_31:
            *(_QWORD *)(v11 + 200) = v17;
            *(_QWORD *)(v17 + 192) = v11;
          }
        }
      }
      else
      {
        v3 = -2147024882;
      }
    }
    else
    {
      v3 = 1;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v25);
    v18 = (_QWORD **)v24;
    **(_QWORD **)(v24 + 8) = 0;
    v19 = *v18;
    if ( v19 )
    {
      do
      {
        v20 = (_QWORD *)*v19;
        std::_Deallocate<16>(v19, 24);
        v19 = v20;
      }
      while ( v20 );
    }
    std::_Deallocate<16>(v24, 24);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18002ec54  mov     [rsp+arg_8], rbx
0x18002ec59  mov     [rsp+arg_10], rsi
0x18002ec5e  push    rdi
0x18002ec5f  push    r12
0x18002ec61  push    r13
0x18002ec63  push    r14
0x18002ec65  push    r15
0x18002ec67  sub     rsp, 320h
0x18002ec6e  mov     rax, cs:__security_cookie
0x18002ec75  xor     rax, rsp
0x18002ec78  mov     [rsp+348h+var_38], rax
0x18002ec80  mov     rbx, rcx
0x18002ec83  xor     r12d, r12d
0x18002ec86  cmp     [rcx+0Ch], r12d
0x18002ec8a  jz      short loc_18002EC93
0x18002ec8c  xor     eax, eax
0x18002ec8e  jmp     loc_18002EF82
0x18002ec93  mov     dword ptr [rcx+0Ch], 1
0x18002ec9a  cmp     [rcx+10h], r12
0x18002ec9e  jnz     short loc_18002ECAA
0x18002eca0  mov     eax, 8000FFFFh
0x18002eca5  jmp     loc_18002EF82
0x18002ecaa  mov     [rcx], r12
0x18002ecad  mov     [rcx+8], r12d
0x18002ecb1  mov     r14d, r12d
0x18002ecb4  xorps   xmm0, xmm0
0x18002ecb7  movdqu  [rsp+348h+var_2F0], xmm0
0x18002ecbd  lea     rcx, [rsp+348h+var_2F0]
0x18002ecc2  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCLch@@V?$allocator@PEAVCLch@@@std@@@std@@AEAAXXZ; std::list<CLch *>::_Alloc_sentinel_and_proxy(void)
0x18002ecc7  nop
0x18002ecc8  xorps   xmm0, xmm0
0x18002eccb  movdqu  [rsp+348h+var_2E0], xmm0
0x18002ecd1  lea     rcx, [rsp+348h+var_2E0]
0x18002ecd6  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002ecdb  nop
0x18002ecdc  mov     rax, [rbx+10h]
0x18002ece0  mov     [rsp+348h+phkResult], rax
0x18002ece5  lea     r9, ?c_szLchKey@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x18002ecec  lea     r8, aSS; "%s\\%s"
0x18002ecf3  mov     edx, 104h; BufferCount
0x18002ecf8  lea     rcx, [rsp+348h+Buffer]; Buffer
0x18002ed00  call    swprintf_s
0x18002ed05  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002ed09  cmp     eax, r13d
0x18002ed0c  jz      loc_18002EDFD
0x18002ed12  mov     [rsp+348h+hKey], r12
0x18002ed17  lea     rax, [rsp+348h+hKey]
0x18002ed1c  mov     [rsp+348h+phkResult], rax; phkResult
0x18002ed21  mov     r15d, 20019h
0x18002ed27  mov     r9d, r15d; samDesired
0x18002ed2a  xor     r8d, r8d; ulOptions
0x18002ed2d  lea     rdx, [rsp+348h+Buffer]; lpSubKey
0x18002ed35  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ed3c  call    cs:__imp_RegOpenKeyExW
0x18002ed42  test    eax, eax
0x18002ed44  jnz     loc_18002EDFD
0x18002ed4a  mov     edi, r12d
0x18002ed4d  mov     [rsp+348h+cchName], 28h ; '('
0x18002ed55  mov     [rsp+348h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18002ed5a  mov     [rsp+348h+lpcchClass], r12; lpcchClass
0x18002ed5f  mov     [rsp+348h+lpClass], r12; lpClass
0x18002ed64  mov     [rsp+348h+phkResult], r12; lpReserved
0x18002ed69  lea     r9, [rsp+348h+cchName]; lpcchName
0x18002ed6e  lea     r8, [rsp+348h+Name]; lpName
0x18002ed76  mov     edx, edi; dwIndex
0x18002ed78  mov     rcx, [rsp+348h+hKey]; hKey
0x18002ed7d  call    cs:__imp_RegEnumKeyExW
0x18002ed83  mov     esi, eax
0x18002ed85  test    eax, eax
0x18002ed87  jnz     short loc_18002EDE8
0x18002ed89  mov     [rsp+348h+var_2F8], r12
0x18002ed8e  lea     rax, [rsp+348h+var_2F8]
0x18002ed93  mov     [rsp+348h+phkResult], rax; phkResult
0x18002ed98  mov     r9d, r15d; samDesired
0x18002ed9b  xor     r8d, r8d; ulOptions
0x18002ed9e  lea     rdx, [rsp+348h+Name]; lpSubKey
0x18002eda6  mov     rcx, [rsp+348h+hKey]; hKey
0x18002edab  call    cs:__imp_RegOpenKeyExW
0x18002edb1  test    eax, eax
0x18002edb3  jnz     short loc_18002EDE8
0x18002edb5  lea     rax, [rsp+348h+var_2E0]
0x18002edba  mov     [rsp+348h+phkResult], rax
0x18002edbf  lea     r9, [rsp+348h+var_2F0]
0x18002edc4  lea     r8, [rsp+348h+Name]
0x18002edcc  mov     rdx, [rsp+348h+var_2F8]
0x18002edd1  call    ?AddHandlersForCall@CLchFinder@@AEAAJPEAUHKEY__@@PEBGAEAV?$list@PEAVCLch@@V?$allocator@PEAVCLch@@@std@@@std@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@@Z; CLchFinder::AddHandlersForCall(HKEY__ *,ushort const *,std::list<CLch *> &,std::map<std::wstring,std::wstring> &)
0x18002edd6  mov     rcx, [rsp+348h+var_2F8]; hKey
0x18002eddb  call    cs:__imp_RegCloseKey
0x18002ede1  inc     edi
0x18002ede3  jmp     loc_18002ED4D
0x18002ede8  inc     edi
0x18002edea  test    esi, esi
0x18002edec  jz      loc_18002ED4D
0x18002edf2  mov     rcx, [rsp+348h+hKey]; hKey
0x18002edf7  call    cs:__imp_RegCloseKey
0x18002edfd  mov     rcx, qword ptr [rsp+348h+var_2F0+8]
0x18002ee02  test    rcx, rcx
0x18002ee05  jz      loc_18002EF2E
0x18002ee0b  mov     eax, 8
0x18002ee10  mul     rcx
0x18002ee13  cmovb   rax, r13
0x18002ee17  mov     rcx, rax; unsigned __int64
0x18002ee1a  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002ee1f  mov     [rbx], rax
0x18002ee22  test    rax, rax
0x18002ee25  jz      loc_18002EF26
0x18002ee2b  mov     rcx, qword ptr [rsp+348h+var_2F0]
0x18002ee30  mov     rax, [rcx]
0x18002ee33  cmp     rax, rcx
0x18002ee36  jz      short loc_18002EE54
0x18002ee38  mov     r8d, [rbx+8]
0x18002ee3c  mov     rdx, [rbx]
0x18002ee3f  mov     rcx, [rax+10h]
0x18002ee43  mov     [rdx+r8*8], rcx
0x18002ee47  inc     dword ptr [rbx+8]
0x18002ee4a  mov     rax, [rax]
0x18002ee4d  mov     rcx, qword ptr [rsp+348h+var_2F0]
0x18002ee52  jmp     short loc_18002EE33
0x18002ee54  mov     edi, r12d
0x18002ee57  cmp     edi, [rbx+8]
0x18002ee5a  jnb     loc_18002EF34
0x18002ee60  mov     ecx, edi
0x18002ee62  mov     rax, [rbx]
0x18002ee65  mov     r13, [rax+rcx*8]
0x18002ee69  lea     rdx, [r13+50h]
0x18002ee6d  lea     rcx, [rsp+348h+var_2B8]
0x18002ee75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ee7a  lea     r8, [rsp+348h+var_2B8]
0x18002ee82  lea     rdx, [rsp+348h+var_2D0]
0x18002ee87  lea     rcx, [rsp+348h+var_2E0]
0x18002ee8c  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18002ee91  lea     r8, [rsp+348h+var_2B8]
0x18002ee99  mov     rdx, [rsp+348h+var_2C0]
0x18002eea1  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const,std::wstring const &)
0x18002eea6  mov     rsi, qword ptr [rsp+348h+var_2E0]
0x18002eeab  test    al, al
0x18002eead  cmovnz  rsi, [rsp+348h+var_2C0]
0x18002eeb6  lea     rcx, [rsp+348h+var_2B8]
0x18002eebe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002eec3  cmp     rsi, qword ptr [rsp+348h+var_2E0]
0x18002eec8  jz      short loc_18002EF1F
0x18002eeca  lea     r15, [rsi+40h]
0x18002eece  cmp     qword ptr [rsi+58h], 7
0x18002eed3  jbe     short loc_18002EED8
0x18002eed5  mov     r15, [r15]
0x18002eed8  mov     esi, r12d
0x18002eedb  cmp     esi, [rbx+8]
0x18002eede  jnb     short loc_18002EF0B
0x18002eee0  mov     r12d, esi
0x18002eee3  mov     rax, [rbx]
0x18002eee6  mov     rcx, [rax+r12*8]
0x18002eeea  add     rcx, 50h ; 'P'; lpString1
0x18002eeee  mov     rdx, r15; lpString2
0x18002eef1  call    cs:__imp_lstrcmpW
0x18002eef7  test    eax, eax
0x18002eef9  jz      short loc_18002EEFF
0x18002eefb  inc     esi
0x18002eefd  jmp     short loc_18002EEDB
0x18002eeff  mov     rax, [rbx]
0x18002ef02  mov     rcx, [rax+r12*8]
0x18002ef06  xor     r12d, r12d
0x18002ef09  jmp     short loc_18002EF11
0x18002ef0b  xor     r12d, r12d
0x18002ef0e  mov     ecx, r12d
0x18002ef11  mov     [r13+0C8h], rcx
0x18002ef18  mov     [rcx+0C0h], r13
0x18002ef1f  inc     edi
0x18002ef21  jmp     loc_18002EE57
0x18002ef26  mov     r14d, 8007000Eh
0x18002ef2c  jmp     short loc_18002EF34
0x18002ef2e  mov     r14d, 1
0x18002ef34  lea     rcx, [rsp+348h+var_2E0]
0x18002ef39  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18002ef3e  nop
0x18002ef3f  mov     rcx, qword ptr [rsp+348h+var_2F0]
0x18002ef44  mov     rax, [rcx+8]
0x18002ef48  mov     [rax], r12
0x18002ef4b  mov     rcx, [rcx]
0x18002ef4e  test    rcx, rcx
0x18002ef51  jz      short loc_18002EF68
0x18002ef53  mov     rbx, [rcx]
0x18002ef56  mov     edx, 18h
0x18002ef5b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002ef60  mov     rcx, rbx
0x18002ef63  test    rbx, rbx
0x18002ef66  jnz     short loc_18002EF53
0x18002ef68  mov     edx, 18h
0x18002ef6d  mov     rcx, qword ptr [rsp+348h+var_2F0]
0x18002ef72  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002ef77  nop
0x18002ef78  jmp     short loc_18002EF7F
0x18002ef7a  mov     r14d, [rsp+348h+cchName]
0x18002ef7f  mov     eax, r14d
0x18002ef82  mov     rcx, [rsp+348h+var_38]
0x18002ef8a  xor     rcx, rsp; StackCookie
0x18002ef8d  call    __security_check_cookie
0x18002ef92  lea     r11, [rsp+348h+var_28]
0x18002ef9a  mov     rbx, [r11+38h]
0x18002ef9e  mov     rsi, [r11+40h]
0x18002efa2  mov     rsp, r11
0x18002efa5  pop     r15
0x18002efa7  pop     r14
0x18002efa9  pop     r13
0x18002efab  pop     r12
0x18002efad  pop     rdi
0x18002efae  retn
```
