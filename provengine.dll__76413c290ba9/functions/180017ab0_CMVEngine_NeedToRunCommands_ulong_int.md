# CMVEngine::NeedToRunCommands(ulong,int *)

- ea: `0x180017ab0`
- end: `0x180017e71`
- name: `?NeedToRunCommands@CMVEngine@@UEAAJKPEAH@Z`
- size: `961`
- prototype: `__int64 __fastcall(CMVEngine *this, int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800098dc`
- `0x180009900`
- `0x18000b030`
- `0x18000b5b4`
- `0x18000c464`
- `0x180017ab0`
- `0x180043750`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017bb4`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017c3b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017bb4`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017c3b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017bdc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017c63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017d77`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017dc9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017e0b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017bdc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017c63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017d77`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017dc9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017e0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017ced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017ced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017def`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017def`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017d3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017d3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ca1`

## string_xrefs

- `0x180017c86`: `SOFTWARE\Microsoft\Provisioning\Commands\`

## pseudocode

```c
__int64 __fastcall CMVEngine::NeedToRunCommands(CMVEngine *this, int a2, int *a3)
{
  unsigned int v6; // ecx
  _QWORD *v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD **v16; // rdi
  _QWORD *i; // rbx
  HKEY v18; // r15
  DWORD LastError; // esi
  const WCHAR *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // ebx
  int phkResult; // [rsp+20h] [rbp-A8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-68h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-60h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-5Ch] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v29; // [rsp+80h] [rbp-48h]
  unsigned __int64 v30; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    v6 = 0;
    while ( a2 != *((_DWORD *)qword_18004C1C0 + v6) )
    {
      if ( ++v6 >= 3 )
        return 0;
    }
    if ( *((_QWORD *)this + 13) )
    {
      v7 = (_QWORD *)((char *)this + 96);
    }
    else
    {
      v7 = (_QWORD *)((char *)this + 96);
      v30 = 7;
      v29 = 0;
      LOWORD(lpSubKey[0]) = 0;
      std::wstring::assign(lpSubKey, L"DeviceContext");
      v8 = *v7;
      v10 = std::_List_buy<std::wstring>::_Buynode<std::wstring>(v9, *v7, *(_QWORD *)(*v7 + 8LL), lpSubKey);
      v11 = v7[1];
      if ( v11 == 0x555555555555554LL )
        std::_Xlength_error("list<T> too long");
      v7[1] = v11 + 1;
      *(_QWORD *)(v8 + 8) = v10;
      **(_QWORD **)(v10 + 8) = v10;
      if ( v30 >= 8 )
        operator delete((void *)lpSubKey[0]);
      v30 = 7;
      v29 = 0;
      LOWORD(lpSubKey[0]) = 0;
      std::wstring::assign(lpSubKey, L"PrimaryContext");
      v12 = *v7;
      v14 = std::_List_buy<std::wstring>::_Buynode<std::wstring>(v13, *v7, *(_QWORD *)(*v7 + 8LL), lpSubKey);
      v15 = v7[1];
      if ( 0x555555555555554LL == v15 )
        std::_Xlength_error("list<T> too long");
      v7[1] = v15 + 1;
      *(_QWORD *)(v12 + 8) = v14;
      **(_QWORD **)(v14 + 8) = v14;
      if ( v30 >= 8 )
        operator delete((void *)lpSubKey[0]);
    }
    cSubKeys = 0;
    v16 = (_QWORD **)*v7;
    for ( i = *v16; i != v16; i = (_QWORD *)*i )
    {
      hKey = 0;
      std::operator+<unsigned short>(lpSubKey, L"SOFTWARE\\Microsoft\\Provisioning\\Commands\\");
      v18 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v18);
        SetLastError(LastError);
      }
      hKey = 0;
      v20 = (const WCHAR *)lpSubKey;
      if ( v30 >= 8 )
        v20 = lpSubKey[0];
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 0x20019u, &hKey) )
      {
        cbMaxSubKeyLen = 0;
        v21 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( v21 )
        {
          v22 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xD75,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                  (const char *)v21,
                  phkResulta);
          if ( v30 >= 8 )
            operator delete((void *)lpSubKey[0]);
          v30 = 7;
          v29 = 0;
          LOWORD(lpSubKey[0]) = 0;
          if ( hKey )
            RegCloseKey(hKey);
          return v22;
        }
        if ( cSubKeys )
        {
          *a3 = 1;
          if ( v30 >= 8 )
            operator delete((void *)lpSubKey[0]);
          v30 = 7;
          v29 = 0;
          LOWORD(lpSubKey[0]) = 0;
          if ( hKey )
            RegCloseKey(hKey);
          return 0;
        }
      }
      if ( v30 >= 8 )
        operator delete((void *)lpSubKey[0]);
      LOWORD(lpSubKey[0]) = 0;
      v29 = 0;
      v30 = 7;
      if ( hKey )
        RegCloseKey(hKey);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD54,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180017ab0  mov     [rsp+arg_8], rbx
0x180017ab5  mov     [rsp+arg_18], rsi
0x180017aba  push    rdi
0x180017abb  push    r12
0x180017abd  push    r13
0x180017abf  push    r14
0x180017ac1  push    r15
0x180017ac3  sub     rsp, 0A0h
0x180017aca  mov     rax, cs:__security_cookie
0x180017ad1  xor     rax, rsp
0x180017ad4  mov     [rsp+0C8h+var_38], rax
0x180017adc  mov     r12, r8
0x180017adf  mov     rdi, rcx
0x180017ae2  xor     r13d, r13d
0x180017ae5  test    r8, r8
0x180017ae8  jnz     short loc_180017B12
0x180017aea  mov     rcx, [rsp+0C8h]; this
0x180017af2  mov     ebx, 80004003h
0x180017af7  mov     r9d, ebx; char *
0x180017afa  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180017b01  mov     edx, 0D54h; void *
0x180017b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b0b  mov     eax, ebx
0x180017b0d  jmp     loc_180017E43
0x180017b12  mov     [r8], r13d
0x180017b15  mov     ecx, r13d
0x180017b18  mov     eax, ecx
0x180017b1a  lea     r8, qword_18004C1C0
0x180017b21  cmp     edx, [r8+rax*4]
0x180017b25  jz      short loc_180017B35
0x180017b27  inc     ecx
0x180017b29  cmp     ecx, 3
0x180017b2c  jb      short loc_180017B18
0x180017b2e  xor     eax, eax
0x180017b30  jmp     loc_180017E43
0x180017b35  mov     r14d, 7
0x180017b3b  cmp     [rdi+68h], r13
0x180017b3f  jz      short loc_180017B4A
0x180017b41  add     rdi, 60h ; '`'
0x180017b45  jmp     loc_180017C69
0x180017b4a  add     rdi, 60h ; '`'
0x180017b4e  mov     [rsp+0C8h+var_40], r14
0x180017b56  mov     [rsp+0C8h+var_48], r13
0x180017b5e  mov     word ptr [rsp+0C8h+lpSubKey], r13w
0x180017b64  mov     r8d, 0Dh
0x180017b6a  lea     rdx, aDevicecontext; "DeviceContext"
0x180017b71  lea     rcx, [rsp+0C8h+lpSubKey]; void *
0x180017b76  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180017b7b  nop
0x180017b7c  mov     rsi, [rdi]
0x180017b7f  lea     r9, [rsp+0C8h+lpSubKey]
0x180017b84  mov     r8, [rsi+8]
0x180017b88  mov     rdx, rsi
0x180017b8b  call    ??$_Buynode@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_List_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@PEAU21@0$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_List_buy<std::wstring>::_Buynode<std::wstring>(std::_List_node<std::wstring,void *> *,std::_List_node<std::wstring,void *> *,std::wstring &&)
0x180017b90  mov     rdx, rax
0x180017b93  mov     rax, [rdi+8]
0x180017b97  mov     rbx, 555555555555554h
0x180017ba1  mov     rcx, rbx
0x180017ba4  sub     rcx, rax
0x180017ba7  cmp     rcx, 1
0x180017bab  jnb     short loc_180017BBA
0x180017bad  lea     rcx, aListTTooLong; "list<T> too long"
0x180017bb4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017bba  inc     rax
0x180017bbd  mov     [rdi+8], rax
0x180017bc1  mov     [rsi+8], rdx
0x180017bc5  mov     rax, [rdx+8]
0x180017bc9  mov     [rax], rdx
0x180017bcc  cmp     [rsp+0C8h+var_40], 8
0x180017bd5  jb      short loc_180017BE2
0x180017bd7  mov     rcx, [rsp+0C8h+lpSubKey]
0x180017bdc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017be2  mov     [rsp+0C8h+var_40], r14
0x180017bea  mov     [rsp+0C8h+var_48], r13
0x180017bf2  mov     word ptr [rsp+0C8h+lpSubKey], r13w
0x180017bf8  mov     r8d, 0Eh
0x180017bfe  lea     rdx, aPrimarycontext; "PrimaryContext"
0x180017c05  lea     rcx, [rsp+0C8h+lpSubKey]; void *
0x180017c0a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180017c0f  nop
0x180017c10  mov     rsi, [rdi]
0x180017c13  lea     r9, [rsp+0C8h+lpSubKey]
0x180017c18  mov     r8, [rsi+8]
0x180017c1c  mov     rdx, rsi
0x180017c1f  call    ??$_Buynode@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_List_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@PEAU21@0$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_List_buy<std::wstring>::_Buynode<std::wstring>(std::_List_node<std::wstring,void *> *,std::_List_node<std::wstring,void *> *,std::wstring &&)
0x180017c24  mov     rcx, rax
0x180017c27  mov     rax, [rdi+8]
0x180017c2b  sub     rbx, rax
0x180017c2e  cmp     rbx, 1
0x180017c32  jnb     short loc_180017C41
0x180017c34  lea     rcx, aListTTooLong; "list<T> too long"
0x180017c3b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017c41  inc     rax
0x180017c44  mov     [rdi+8], rax
0x180017c48  mov     [rsi+8], rcx
0x180017c4c  mov     rax, [rcx+8]
0x180017c50  mov     [rax], rcx
0x180017c53  cmp     [rsp+0C8h+var_40], 8
0x180017c5c  jb      short loc_180017C69
0x180017c5e  mov     rcx, [rsp+0C8h+lpSubKey]
0x180017c63  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017c69  mov     [rsp+0C8h+cSubKeys], r13d
0x180017c6e  mov     rdi, [rdi]
0x180017c71  mov     rbx, [rdi]
0x180017c74  cmp     rbx, rdi
0x180017c77  jz      loc_180017DF6
0x180017c7d  mov     [rsp+0C8h+hKey], r13
0x180017c82  lea     r8, [rbx+10h]
0x180017c86  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x180017c8d  lea     rcx, [rsp+0C8h+lpSubKey]; Src
0x180017c92  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x180017c97  mov     r15, [rsp+0C8h+hKey]
0x180017c9c  test    r15, r15
0x180017c9f  jz      short loc_180017CBA
0x180017ca1  call    cs:__imp_GetLastError
0x180017ca7  mov     esi, eax
0x180017ca9  mov     rcx, r15; hKey
0x180017cac  call    cs:__imp_RegCloseKey
0x180017cb2  mov     ecx, esi; dwErrCode
0x180017cb4  call    cs:__imp_SetLastError
0x180017cba  mov     [rsp+0C8h+hKey], r13
0x180017cbf  lea     rdx, [rsp+0C8h+lpSubKey]
0x180017cc4  cmp     [rsp+0C8h+var_40], 8
0x180017ccd  cmovnb  rdx, [rsp+0C8h+lpSubKey]; lpSubKey
0x180017cd3  lea     rax, [rsp+0C8h+hKey]
0x180017cd8  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180017cdd  mov     r9d, 20019h; samDesired
0x180017ce3  xor     r8d, r8d; ulOptions
0x180017ce6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017ced  call    cs:__imp_RegOpenKeyExW
0x180017cf3  test    eax, eax
0x180017cf5  jnz     loc_180017DFB
0x180017cfb  mov     [rsp+0C8h+cbMaxSubKeyLen], r13d
0x180017d00  mov     [rsp+0C8h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180017d05  mov     [rsp+0C8h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180017d0a  mov     [rsp+0C8h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180017d0f  mov     [rsp+0C8h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180017d14  mov     [rsp+0C8h+lpcValues], r13; lpcValues
0x180017d19  mov     [rsp+0C8h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180017d1e  lea     rax, [rsp+0C8h+cbMaxSubKeyLen]
0x180017d23  mov     [rsp+0C8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180017d28  lea     rax, [rsp+0C8h+cSubKeys]
0x180017d2d  mov     [rsp+0C8h+phkResult], rax; unsigned int
0x180017d32  xor     r9d, r9d; lpReserved
0x180017d35  xor     r8d, r8d; lpcchClass
0x180017d38  xor     edx, edx; lpClass
0x180017d3a  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180017d3f  call    cs:__imp_RegQueryInfoKeyW
0x180017d45  test    eax, eax
0x180017d47  jz      short loc_180017DAA
0x180017d49  mov     rcx, [rsp+0C8h]; this
0x180017d51  mov     r9d, eax; char *
0x180017d54  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180017d5b  mov     edx, 0D75h; void *
0x180017d60  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017d65  mov     ebx, eax
0x180017d67  cmp     [rsp+0C8h+var_40], 8
0x180017d70  jb      short loc_180017D7D
0x180017d72  mov     rcx, [rsp+0C8h+lpSubKey]
0x180017d77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017d7d  mov     [rsp+0C8h+var_40], r14
0x180017d85  mov     [rsp+0C8h+var_48], r13
0x180017d8d  mov     word ptr [rsp+0C8h+lpSubKey], r13w
0x180017d93  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180017d98  test    rcx, rcx
0x180017d9b  jz      short loc_180017DA3
0x180017d9d  call    cs:__imp_RegCloseKey
0x180017da3  mov     eax, ebx
0x180017da5  jmp     loc_180017E43
0x180017daa  cmp     [rsp+0C8h+cSubKeys], r13d
0x180017daf  jbe     short loc_180017DFB
0x180017db1  mov     dword ptr [r12], 1
0x180017db9  cmp     [rsp+0C8h+var_40], 8
0x180017dc2  jb      short loc_180017DCF
0x180017dc4  mov     rcx, [rsp+0C8h+lpSubKey]
0x180017dc9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017dcf  mov     [rsp+0C8h+var_40], r14
0x180017dd7  mov     [rsp+0C8h+var_48], r13
0x180017ddf  mov     word ptr [rsp+0C8h+lpSubKey], r13w
0x180017de5  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180017dea  test    rcx, rcx
0x180017ded  jz      short loc_180017DF6
0x180017def  call    cs:__imp_RegCloseKey
0x180017df5  nop
0x180017df6  jmp     loc_180017B2E
0x180017dfb  cmp     [rsp+0C8h+var_40], 8
0x180017e04  jb      short loc_180017E11
0x180017e06  mov     rcx, [rsp+0C8h+lpSubKey]
0x180017e0b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017e11  mov     word ptr [rsp+0C8h+lpSubKey], r13w
0x180017e17  mov     [rsp+0C8h+var_48], r13
0x180017e1f  mov     [rsp+0C8h+var_40], r14
0x180017e27  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180017e2c  test    rcx, rcx
0x180017e2f  jz      short loc_180017E37
0x180017e31  call    cs:__imp_RegCloseKey
0x180017e37  mov     rbx, [rbx]
0x180017e3a  jmp     loc_180017C74
0x180017e3f  mov     eax, [rsp+0C8h+cbMaxSubKeyLen]
0x180017e43  mov     rcx, [rsp+0C8h+var_38]
0x180017e4b  xor     rcx, rsp; StackCookie
0x180017e4e  call    __security_check_cookie
0x180017e53  lea     r11, [rsp+0C8h+var_28]
0x180017e5b  mov     rbx, [r11+38h]
0x180017e5f  mov     rsi, [r11+48h]
0x180017e63  mov     rsp, r11
0x180017e66  pop     r15
0x180017e68  pop     r14
0x180017e6a  pop     r13
0x180017e6c  pop     r12
0x180017e6e  pop     rdi
0x180017e6f  retn
```
