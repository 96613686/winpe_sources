# DeviceManagebilityCSP::Provider::GetAllEnrollmentInfo(utl::map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>> *)

- ea: `0x180040a54`
- end: `0x180040d53`
- name: `?GetAllEnrollmentInfo@Provider@DeviceManagebilityCSP@@YAJPEAV?$map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@@utl@@@Z`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180022e74`

## callees

- `0x1800026d0`
- `0x180002ae0`
- `0x18000b0f4`
- `0x18002cc9c`
- `0x18002ce80`
- `0x18003b9cc`
- `0x180040888`
- `0x180040a54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040b83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040c40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040b83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040c40`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040b2c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040b2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ae7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040d03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040d1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ae7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040d03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040d1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040aa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040aa8`

## pseudocode

```c
__int64 __fastcall DeviceManagebilityCSP::Provider::GetAllEnrollmentInfo(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // edi
  DWORD v6; // edi
  LSTATUS ValueW; // r8d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-298h]
  int phkResulta; // [rsp+20h] [rbp-298h]
  HKEY hKey; // [rsp+40h] [rbp-278h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-270h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-26Ch] BYREF
  void *Block; // [rsp+50h] [rbp-268h] BYREF
  _WORD *v16; // [rsp+58h] [rbp-260h]
  _QWORD v17[2]; // [rsp+60h] [rbp-258h] BYREF
  _BYTE v18[24]; // [rsp+78h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear(a1);
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DeviceManageabilityCSP\\Provider", 0, 0x20119u, &hKey);
  if ( v2 == 2 )
  {
LABEL_29:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( !v2 )
  {
    v6 = 0;
LABEL_9:
    cchName = 260;
    while ( 1 )
    {
      v2 = RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, 0);
      if ( v2 == 259 )
        goto LABEL_29;
      if ( v2 )
      {
        v3 = 44;
        goto LABEL_4;
      }
      pcbData = 0;
      if ( RegGetValueW(hKey, Name, L"EnrollmentInfo", 2u, 0, 0, &pcbData) )
      {
        ++v6;
        goto LABEL_9;
      }
      Block = v17;
      v16 = v17;
      LOWORD(v17[0]) = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::reserve(
                               &Block,
                               (unsigned __int64)pcbData >> 1) )
      {
        v4 = -2147024888;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\externalhelpers.cpp",
          (const char *)0x80070008LL,
          phkResulta);
        if ( Block != v17 )
          operator delete(Block);
        goto LABEL_5;
      }
      ValueW = RegGetValueW(hKey, Name, L"EnrollmentInfo", 2u, 0, Block, &pcbData);
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)Block + v8) );
      if ( Block == v17 )
        v9 = 7;
      else
        v9 = (__int64)(v17[0] - (_QWORD)Block) >> 1;
      if ( v8 > v9 )
        NT_ASSERT("FRE: _Len <= capacity()");
      v16 = (char *)Block + 2 * v8;
      *v16 = 0;
      if ( !ValueW )
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::emplace<unsigned short (&)[260],utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> &,0>(
          a1,
          v18,
          Name,
          &Block);
      ++v6;
      cchName = 260;
      if ( Block != v17 )
        operator delete(Block);
    }
  }
  v3 = 28;
LABEL_4:
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\externalhelpers.cpp",
         (const char *)v2,
         phkResult);
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180040a54  mov     [rsp+arg_8], rbx
0x180040a59  mov     [rsp+arg_10], rsi
0x180040a5e  push    rdi
0x180040a5f  sub     rsp, 2B0h
0x180040a66  mov     rax, cs:__security_cookie
0x180040a6d  xor     rax, rsp
0x180040a70  mov     [rsp+2B8h+var_18], rax
0x180040a78  mov     rsi, rcx
0x180040a7b  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x180040a80  xor     ebx, ebx
0x180040a82  mov     [rsp+2B8h+hKey], rbx
0x180040a87  lea     rax, [rsp+2B8h+hKey]
0x180040a8c  mov     [rsp+2B8h+phkResult], rax; unsigned int
0x180040a91  mov     r9d, 20119h; samDesired
0x180040a97  xor     r8d, r8d; ulOptions
0x180040a9a  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\DeviceManageabilit"...
0x180040aa1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040aa8  call    cs:__imp_RegOpenKeyExW
0x180040aaf  nop     dword ptr [rax+rax+00h]
0x180040ab4  cmp     eax, 2
0x180040ab7  jz      loc_180040D15
0x180040abd  test    eax, eax
0x180040abf  jz      short loc_180040AFA
0x180040ac1  lea     edx, [rbx+1Ch]; void *
0x180040ac4  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040acb  mov     r9d, eax; char *
0x180040ace  mov     rcx, [rsp+2B8h]; this
0x180040ad6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040adb  mov     edi, eax
0x180040add  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180040ae2  test    rcx, rcx
0x180040ae5  jz      short loc_180040AF3
0x180040ae7  call    cs:__imp_RegCloseKey
0x180040aee  nop     dword ptr [rax+rax+00h]
0x180040af3  mov     eax, edi
0x180040af5  jmp     loc_180040D2D
0x180040afa  mov     edi, ebx
0x180040afc  mov     [rsp+2B8h+cchName], 104h
0x180040b04  mov     [rsp+2B8h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180040b09  mov     [rsp+2B8h+lpcchClass], rbx; lpcchClass
0x180040b0e  mov     [rsp+2B8h+lpClass], rbx; lpClass
0x180040b13  mov     [rsp+2B8h+phkResult], rbx; lpReserved
0x180040b18  lea     r9, [rsp+2B8h+cchName]; lpcchName
0x180040b1d  lea     r8, [rsp+2B8h+Name]; lpName
0x180040b25  mov     edx, edi; dwIndex
0x180040b27  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180040b2c  call    cs:__imp_RegEnumKeyExW
0x180040b33  nop     dword ptr [rax+rax+00h]
0x180040b38  cmp     eax, 103h
0x180040b3d  jz      loc_180040D15
0x180040b43  test    eax, eax
0x180040b45  jz      short loc_180040B51
0x180040b47  mov     edx, 2Ch ; ','
0x180040b4c  jmp     loc_180040AC4
0x180040b51  mov     [rsp+2B8h+pcbData], ebx
0x180040b55  lea     rax, [rsp+2B8h+pcbData]
0x180040b5a  mov     [rsp+2B8h+lpcchClass], rax; pcbData
0x180040b5f  mov     [rsp+2B8h+lpClass], rbx; pvData
0x180040b64  mov     [rsp+2B8h+phkResult], rbx; int
0x180040b69  mov     r9d, 2; dwFlags
0x180040b6f  lea     r8, aEnrollmentinfo; "EnrollmentInfo"
0x180040b76  lea     rdx, [rsp+2B8h+Name]; lpSubKey
0x180040b7e  mov     rcx, [rsp+2B8h+hKey]; hkey
0x180040b83  call    cs:__imp_RegGetValueW
0x180040b8a  nop     dword ptr [rax+rax+00h]
0x180040b8f  test    eax, eax
0x180040b91  jz      short loc_180040B9A
0x180040b93  inc     edi
0x180040b95  jmp     loc_180040AFC
0x180040b9a  lea     rax, [rsp+2B8h+var_258]
0x180040b9f  mov     [rsp+2B8h+Block], rax
0x180040ba4  lea     rax, [rsp+2B8h+var_258]
0x180040ba9  mov     [rsp+2B8h+var_260], rax
0x180040bae  mov     word ptr [rsp+2B8h+var_258], bx
0x180040bb3  mov     edx, [rsp+2B8h+pcbData]
0x180040bb7  shr     rdx, 1
0x180040bba  lea     rcx, [rsp+2B8h+Block]
0x180040bbf  call    ?reserve@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::reserve(unsigned __int64)
0x180040bc4  test    al, al
0x180040bc6  jnz     short loc_180040C0D
0x180040bc8  mov     rcx, [rsp+2B8h]; this
0x180040bd0  mov     edi, 80070008h
0x180040bd5  mov     r9d, edi; char *
0x180040bd8  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040bdf  mov     edx, 3Fh ; '?'; void *
0x180040be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040be9  lea     rax, [rsp+2B8h+var_258]
0x180040bee  mov     rcx, [rsp+2B8h+Block]; Block
0x180040bf3  cmp     rcx, rax
0x180040bf6  jz      loc_180040ADD
0x180040bfc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180040c03  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040c08  jmp     loc_180040ADD
0x180040c0d  mov     rax, [rsp+2B8h+Block]
0x180040c12  lea     rcx, [rsp+2B8h+pcbData]
0x180040c17  mov     [rsp+2B8h+lpcchClass], rcx; pcbData
0x180040c1c  mov     [rsp+2B8h+lpClass], rax; pvData
0x180040c21  mov     [rsp+2B8h+phkResult], rbx; pdwType
0x180040c26  mov     r9d, 2; dwFlags
0x180040c2c  lea     r8, aEnrollmentinfo; "EnrollmentInfo"
0x180040c33  lea     rdx, [rsp+2B8h+Name]; lpSubKey
0x180040c3b  mov     rcx, [rsp+2B8h+hKey]; hkey
0x180040c40  call    cs:__imp_RegGetValueW
0x180040c47  nop     dword ptr [rax+rax+00h]
0x180040c4c  mov     r8d, eax
0x180040c4f  mov     rdx, [rsp+2B8h+Block]
0x180040c54  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180040c58  inc     rcx
0x180040c5b  cmp     [rdx+rcx*2], bx
0x180040c5f  jnz     short loc_180040C58
0x180040c61  lea     rax, [rsp+2B8h+var_258]
0x180040c66  cmp     rdx, rax
0x180040c69  jnz     short loc_180040C72
0x180040c6b  mov     eax, 7
0x180040c70  jmp     short loc_180040C7D
0x180040c72  mov     rax, [rsp+2B8h+var_258]
0x180040c77  sub     rax, rdx
0x180040c7a  sar     rax, 1
0x180040c7d  cmp     rcx, rax
0x180040c80  jbe     short loc_180040C84
0x180040c82  int     2Ch; NT_ASSERT("FRE: _Len <= capacity()")
0x180040c84  lea     rax, [rdx+rcx*2]
0x180040c88  mov     [rsp+2B8h+var_260], rax
0x180040c8d  mov     [rax], bx
0x180040c90  test    r8d, r8d
0x180040c93  jnz     short loc_180040CB0
0x180040c95  lea     r9, [rsp+2B8h+Block]
0x180040c9a  lea     r8, [rsp+2B8h+Name]
0x180040ca2  lea     rdx, [rsp+2B8h+var_240]
0x180040ca7  mov     rcx, rsi
0x180040caa  call    ??$emplace@AEAY0BAE@GAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@_N@1@AEAY0BAE@GAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::emplace<ushort (&)[260],utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,0>(ushort (&)[260],utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180040caf  nop
0x180040cb0  inc     edi
0x180040cb2  mov     [rsp+2B8h+cchName], 104h
0x180040cba  lea     rax, [rsp+2B8h+var_258]
0x180040cbf  mov     rcx, [rsp+2B8h+Block]; Block
0x180040cc4  cmp     rcx, rax
0x180040cc7  jz      loc_180040B04
0x180040ccd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180040cd4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040cd9  jmp     loc_180040B04
0x180040cde  lea     rax, [rsp+2B8h+var_258]
0x180040ce3  mov     rcx, [rsp+2B8h+Block]; Block
0x180040ce8  cmp     rcx, rax
0x180040ceb  jz      short loc_180040CF9
0x180040ced  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180040cf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040cf9  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180040cfe  test    rcx, rcx
0x180040d01  jz      short loc_180040D0F
0x180040d03  call    cs:__imp_RegCloseKey
0x180040d0a  nop     dword ptr [rax+rax+00h]
0x180040d0f  mov     eax, [rsp+2B8h+var_248]
0x180040d13  jmp     short loc_180040D2D
0x180040d15  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180040d1a  test    rcx, rcx
0x180040d1d  jz      short loc_180040D2B
0x180040d1f  call    cs:__imp_RegCloseKey
0x180040d26  nop     dword ptr [rax+rax+00h]
0x180040d2b  xor     eax, eax
0x180040d2d  mov     rcx, [rsp+2B8h+var_18]
0x180040d35  xor     rcx, rsp; StackCookie
0x180040d38  call    __security_check_cookie
0x180040d3d  lea     r11, [rsp+2B8h+var_8]
0x180040d45  mov     rbx, [r11+18h]
0x180040d49  mov     rsi, [r11+20h]
0x180040d4d  mov     rsp, r11
0x180040d50  pop     rdi
0x180040d51  retn
```
