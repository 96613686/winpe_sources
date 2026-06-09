# GetMultiStringRegValAsVector(ushort const *,ushort const *,ulong *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x18005c97c`
- end: `0x18005cd59`
- name: `?GetMultiStringRegValAsVector@@YAJPEBG0PEAKPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041b34`
- `0x18004b9ec`
- `0x18004d79c`

## callees

- `0x18003bf28`
- `0x18003dd9c`
- `0x180040024`
- `0x180042410`
- `0x18004317c`
- `0x180047080`
- `0x1800471d0`
- `0x180047524`
- `0x18004755c`
- `0x18004af14`
- `0x18004bfe4`
- `0x18004c034`
- `0x18005b59c`
- `0x18005b6d4`
- `0x18005c97c`
- `0x18005e91c`
- `0x18005e934`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ca22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005cb03`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ca22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005cb03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c9df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c9df`

## string_xrefs

- `0x18005ca31`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005cb14`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005cc44`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005cd16`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005ca15`: `UserAccountSids`
- `0x18005caf6`: `UserAccountSids`
- `0x18005c9d1`: `Software\Microsoft\IdentityStore\DeferredCacheCleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetMultiStringRegValAsVector(__int64 a1, __int64 a2, DWORD *a3, __int64 a4)
{
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  char *v11; // rdi
  unsigned __int64 v12; // rcx
  char *v13; // rax
  size_t v14; // rbx
  unsigned int v15; // eax
  unsigned __int64 v16; // rbx
  char *v17; // rdi
  unsigned __int64 v18; // rcx
  char *v19; // rax
  size_t v20; // rbx
  const wchar_t *v21; // r15
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rdi
  __int64 v24; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-69h]
  unsigned int phkResulta; // [rsp+20h] [rbp-69h]
  DWORD pcbData; // [rsp+40h] [rbp-49h] BYREF
  PVOID pvData[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v30; // [rsp+58h] [rbp-31h]
  HKEY hkey; // [rsp+60h] [rbp-29h] BYREF
  DWORD pdwType; // [rsp+68h] [rbp-21h] BYREF
  __int128 v33; // [rsp+70h] [rbp-19h] BYREF
  __int64 v34; // [rsp+80h] [rbp-9h]
  _OWORD v35[2]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *a3 = 0;
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityStore\\DeferredCacheCleanup", 0, 1u, &hkey);
  if ( ValueW )
  {
    v7 = 644;
LABEL_5:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
           (const char *)ValueW,
           phkResult);
LABEL_43:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v8;
  }
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, L"UserAccountSids", 0x20u, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    v7 = 654;
    goto LABEL_5;
  }
  if ( pdwType != 7 )
  {
    v8 = -2147024809;
    v9 = 656;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
      (const char *)v8,
      phkResult);
    goto LABEL_43;
  }
  if ( !pcbData || (pcbData & 1) != 0 )
  {
    v8 = -2147024872;
    v9 = 657;
    goto LABEL_42;
  }
  std::vector<std::wstring>::vector<std::wstring>(pvData);
  v10 = (unsigned __int64)pcbData >> 1;
  v11 = (char *)pvData[1];
  v12 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
  if ( v10 >= v12 )
  {
    if ( v10 <= v12 )
      goto LABEL_17;
    if ( v10 > (signed __int64)(v30 - (unsigned __int64)pvData[0]) >> 1 )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(pvData, (unsigned __int64)pcbData >> 1);
      goto LABEL_17;
    }
    v14 = 2 * (v10 - v12);
    memset_0(pvData[1], 0, v14);
    v13 = &v11[v14];
  }
  else
  {
    v13 = (char *)pvData[0] + 2 * v10;
  }
  pvData[1] = v13;
LABEL_17:
  v15 = RegGetValueW(hkey, 0, L"UserAccountSids", 0x20u, 0, pvData[0], &pcbData);
  if ( v15 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x29B,
           (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
           (const char *)v15,
           phkResulta);
LABEL_34:
    if ( pvData[0] )
    {
      std::_Deallocate<16>(pvData[0], 2 * ((signed __int64)(v30 - (unsigned __int64)pvData[0]) >> 1));
      v30 = 0;
      *(_OWORD *)pvData = 0;
    }
    goto LABEL_43;
  }
  v16 = (unsigned __int64)pcbData >> 1;
  v17 = (char *)pvData[1];
  v18 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
  if ( v16 < v18 )
  {
    v19 = (char *)pvData[0] + 2 * v16;
LABEL_25:
    pvData[1] = v19;
    goto LABEL_26;
  }
  if ( v16 > v18 )
  {
    if ( v16 <= (signed __int64)(v30 - (unsigned __int64)pvData[0]) >> 1 )
    {
      v20 = 2 * (v16 - v18);
      memset_0(pvData[1], 0, v20);
      v19 = &v17[v20];
      goto LABEL_25;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(pvData, (unsigned __int64)pcbData >> 1);
  }
LABEL_26:
  std::vector<std::wstring>::vector<std::wstring>(&v33);
  v21 = (const wchar_t *)pvData[0];
  v22 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
  if ( v22 )
  {
    v23 = 0;
    while ( v21[v23] )
    {
      memset(v35, 0, sizeof(v35));
      v24 = std::_WChar_traits<unsigned short>::length(&v21[v23]);
      std::wstring::_Construct<1,unsigned short const *>(v35, &v21[v23], v24);
      if ( *((_QWORD *)&v33 + 1) == v34 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v33, *((_QWORD *)&v33 + 1), v35);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)&v33 + 1), v35);
        *((_QWORD *)&v33 + 1) += 32LL;
      }
      std::wstring::_Tidy_deallocate(v35);
      v23 += wcsnlen_s(&v21[v23], v22 - v23) + 1;
      if ( v23 >= v22 )
      {
        v8 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AE,
          (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
          (const char *)0x80070057LL,
          phkResulta);
        std::vector<std::wstring>::_Tidy(&v33);
        goto LABEL_34;
      }
    }
  }
  if ( (__int128 *)a4 != &v33 )
  {
    std::vector<std::wstring>::_Tidy(a4);
    *(_OWORD *)a4 = v33;
    *(_QWORD *)(a4 + 16) = v34;
    v33 = 0;
    v34 = 0;
  }
  *a3 = pcbData;
  std::vector<std::wstring>::_Tidy(&v33);
  if ( pvData[0] )
  {
    std::_Deallocate<16>(pvData[0], 2 * ((signed __int64)(v30 - (unsigned __int64)pvData[0]) >> 1));
    *(_OWORD *)pvData = 0;
    v30 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x18005c97c  mov     [rsp-8+arg_0], rbx
0x18005c981  push    rbp
0x18005c982  push    rsi
0x18005c983  push    rdi
0x18005c984  push    r12
0x18005c986  push    r13
0x18005c988  push    r14
0x18005c98a  push    r15
0x18005c98c  lea     rbp, [rsp-27h]
0x18005c991  sub     rsp, 0B0h
0x18005c998  mov     rax, cs:__security_cookie
0x18005c99f  xor     rax, rsp
0x18005c9a2  mov     [rbp+57h+var_38], rax
0x18005c9a6  mov     r14, r9
0x18005c9a9  mov     r12, r8
0x18005c9ac  xor     r13d, r13d
0x18005c9af  mov     [r8], r13d
0x18005c9b2  mov     [rbp+57h+hkey], r13
0x18005c9b6  xor     edx, edx
0x18005c9b8  lea     rcx, [rbp+57h+hkey]
0x18005c9bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005c9c1  lea     rax, [rbp+57h+hkey]
0x18005c9c5  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18005c9ca  lea     r9d, [r13+1]; samDesired
0x18005c9ce  xor     r8d, r8d; ulOptions
0x18005c9d1  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityStore\\Def"...
0x18005c9d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c9df  call    cs:__imp_RegOpenKeyExW
0x18005c9e5  test    eax, eax
0x18005c9e7  jz      short loc_18005C9F0
0x18005c9e9  mov     edx, 284h
0x18005c9ee  jmp     short loc_18005CA31
0x18005c9f0  mov     [rbp+57h+pdwType], r13d
0x18005c9f4  mov     [rbp+57h+var_A0], r13d
0x18005c9f8  lea     rax, [rbp+57h+var_A0]
0x18005c9fc  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18005ca01  mov     [rsp+0E0h+pvData], r13; pvData
0x18005ca06  lea     rax, [rbp+57h+pdwType]
0x18005ca0a  mov     [rsp+0E0h+phkResult], rax; int
0x18005ca0f  mov     r9d, 20h ; ' '; dwFlags
0x18005ca15  lea     r8, aUseraccountsid; "UserAccountSids"
0x18005ca1c  xor     edx, edx; lpSubKey
0x18005ca1e  mov     rcx, [rbp+57h+hkey]; hkey
0x18005ca22  call    cs:__imp_RegGetValueW
0x18005ca28  test    eax, eax
0x18005ca2a  jz      short loc_18005CA4B
0x18005ca2c  mov     edx, 28Eh; void *
0x18005ca31  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005ca38  mov     r9d, eax; char *
0x18005ca3b  mov     rcx, [rbp+5Fh]; this
0x18005ca3f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ca44  mov     ebx, eax
0x18005ca46  jmp     loc_18005CD27
0x18005ca4b  cmp     [rbp+57h+pdwType], 7
0x18005ca4f  jz      short loc_18005CA60
0x18005ca51  mov     ebx, 80070057h
0x18005ca56  mov     edx, 290h
0x18005ca5b  jmp     loc_18005CD13
0x18005ca60  mov     eax, [rbp+57h+var_A0]
0x18005ca63  test    eax, eax
0x18005ca65  jz      loc_18005CD09
0x18005ca6b  test    al, 1
0x18005ca6d  jnz     loc_18005CD09
0x18005ca73  lea     rcx, [rbp+57h+var_98]
0x18005ca77  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18005ca7c  nop
0x18005ca7d  mov     ebx, [rbp+57h+var_A0]
0x18005ca80  shr     rbx, 1
0x18005ca83  mov     rdx, [rbp+57h+var_98]
0x18005ca87  mov     rdi, [rbp+57h+var_98+8]
0x18005ca8b  mov     rcx, rdi
0x18005ca8e  sub     rcx, rdx
0x18005ca91  sar     rcx, 1
0x18005ca94  cmp     rbx, rcx
0x18005ca97  jnb     short loc_18005CA9F
0x18005ca99  lea     rax, [rdx+rbx*2]
0x18005ca9d  jmp     short loc_18005CAD5
0x18005ca9f  jbe     short loc_18005CAD9
0x18005caa1  mov     rax, [rbp+57h+var_88]
0x18005caa5  sub     rax, rdx
0x18005caa8  sar     rax, 1
0x18005caab  cmp     rbx, rax
0x18005caae  jbe     short loc_18005CABE
0x18005cab0  mov     rdx, rbx
0x18005cab3  lea     rcx, [rbp+57h+var_98]
0x18005cab7  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005cabc  jmp     short loc_18005CAD9
0x18005cabe  sub     rbx, rcx
0x18005cac1  add     rbx, rbx
0x18005cac4  mov     r8, rbx; Size
0x18005cac7  xor     edx, edx; Val
0x18005cac9  mov     rcx, rdi; void *
0x18005cacc  call    memset_0
0x18005cad1  lea     rax, [rbx+rdi]
0x18005cad5  mov     [rbp+57h+var_98+8], rax
0x18005cad9  mov     rax, [rbp+57h+var_98]
0x18005cadd  lea     rcx, [rbp+57h+var_A0]
0x18005cae1  mov     [rsp+0E0h+pcbData], rcx; pcbData
0x18005cae6  mov     [rsp+0E0h+pvData], rax; pvData
0x18005caeb  mov     [rsp+0E0h+phkResult], r13; int
0x18005caf0  mov     r9d, 20h ; ' '; dwFlags
0x18005caf6  lea     r8, aUseraccountsid; "UserAccountSids"
0x18005cafd  xor     edx, edx; lpSubKey
0x18005caff  mov     rcx, [rbp+57h+hkey]; hkey
0x18005cb03  call    cs:__imp_RegGetValueW
0x18005cb09  test    eax, eax
0x18005cb0b  jz      short loc_18005CB2C
0x18005cb0d  mov     rcx, [rbp+5Fh]; this
0x18005cb11  mov     r9d, eax; char *
0x18005cb14  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005cb1b  mov     edx, 29Bh; void *
0x18005cb20  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005cb25  mov     ebx, eax
0x18005cb27  jmp     loc_18005CC60
0x18005cb2c  mov     ebx, [rbp+57h+var_A0]
0x18005cb2f  shr     rbx, 1
0x18005cb32  mov     rdx, [rbp+57h+var_98]
0x18005cb36  mov     rdi, [rbp+57h+var_98+8]
0x18005cb3a  mov     rcx, rdi
0x18005cb3d  sub     rcx, rdx
0x18005cb40  sar     rcx, 1
0x18005cb43  cmp     rbx, rcx
0x18005cb46  jnb     short loc_18005CB4E
0x18005cb48  lea     rax, [rdx+rbx*2]
0x18005cb4c  jmp     short loc_18005CB84
0x18005cb4e  jbe     short loc_18005CB88
0x18005cb50  mov     rax, [rbp+57h+var_88]
0x18005cb54  sub     rax, rdx
0x18005cb57  sar     rax, 1
0x18005cb5a  cmp     rbx, rax
0x18005cb5d  jbe     short loc_18005CB6D
0x18005cb5f  mov     rdx, rbx
0x18005cb62  lea     rcx, [rbp+57h+var_98]
0x18005cb66  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005cb6b  jmp     short loc_18005CB88
0x18005cb6d  sub     rbx, rcx
0x18005cb70  add     rbx, rbx
0x18005cb73  mov     r8, rbx; Size
0x18005cb76  xor     edx, edx; Val
0x18005cb78  mov     rcx, rdi; void *
0x18005cb7b  call    memset_0
0x18005cb80  lea     rax, [rbx+rdi]
0x18005cb84  mov     [rbp+57h+var_98+8], rax
0x18005cb88  lea     rcx, [rbp+57h+var_70]
0x18005cb8c  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18005cb91  nop
0x18005cb92  mov     r15, [rbp+57h+var_98]
0x18005cb96  mov     rbx, [rbp+57h+var_98+8]
0x18005cb9a  sub     rbx, r15
0x18005cb9d  sar     rbx, 1
0x18005cba0  jz      loc_18005CC90
0x18005cba6  mov     rdi, r13
0x18005cba9  cmp     r13, rbx
0x18005cbac  jnb     loc_18005CC90
0x18005cbb2  lea     rsi, [r15+rdi*2]
0x18005cbb6  cmp     [rsi], r13w
0x18005cbba  jz      loc_18005CC90
0x18005cbc0  xorps   xmm0, xmm0
0x18005cbc3  movups  [rbp+57h+var_58], xmm0
0x18005cbc7  xorps   xmm1, xmm1
0x18005cbca  movdqu  [rbp+57h+var_48], xmm1
0x18005cbcf  mov     rcx, rsi
0x18005cbd2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005cbd7  mov     r8, rax
0x18005cbda  mov     rdx, rsi
0x18005cbdd  lea     rcx, [rbp+57h+var_58]
0x18005cbe1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005cbe6  nop
0x18005cbe7  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x18005cbeb  cmp     rcx, [rbp+57h+var_60]
0x18005cbef  jz      short loc_18005CC01
0x18005cbf1  lea     rdx, [rbp+57h+var_58]
0x18005cbf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18005cbfa  add     qword ptr [rbp+57h+var_70+8], 20h ; ' '
0x18005cbff  jmp     short loc_18005CC12
0x18005cc01  lea     r8, [rbp+57h+var_58]
0x18005cc05  mov     rdx, rcx
0x18005cc08  lea     rcx, [rbp+57h+var_70]
0x18005cc0c  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18005cc11  nop
0x18005cc12  lea     rcx, [rbp+57h+var_58]
0x18005cc16  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005cc1b  mov     rdx, rbx
0x18005cc1e  sub     rdx, rdi; MaxCount
0x18005cc21  mov     rcx, rsi; Source
0x18005cc24  call    wcsnlen_s
0x18005cc29  inc     rdi
0x18005cc2c  add     rdi, rax
0x18005cc2f  cmp     rdi, rbx
0x18005cc32  jb      loc_18005CBB2
0x18005cc38  mov     rcx, [rbp+5Fh]; this
0x18005cc3c  mov     ebx, 80070057h
0x18005cc41  mov     r9d, ebx; char *
0x18005cc44  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005cc4b  mov     edx, 2AEh; void *
0x18005cc50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cc55  nop
0x18005cc56  lea     rcx, [rbp+57h+var_70]
0x18005cc5a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005cc5f  nop
0x18005cc60  mov     rcx, [rbp+57h+var_98]
0x18005cc64  test    rcx, rcx
0x18005cc67  jz      loc_18005CD27
0x18005cc6d  mov     rdx, [rbp+57h+var_88]
0x18005cc71  sub     rdx, rcx
0x18005cc74  sar     rdx, 1
0x18005cc77  add     rdx, rdx
0x18005cc7a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005cc7f  xorps   xmm0, xmm0
0x18005cc82  mov     [rbp+57h+var_88], r13
0x18005cc86  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18005cc8b  jmp     loc_18005CD27
0x18005cc90  lea     rax, [rbp+57h+var_70]
0x18005cc94  cmp     r14, rax
0x18005cc97  jz      short loc_18005CCC4
0x18005cc99  mov     rcx, r14
0x18005cc9c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005cca1  mov     rax, qword ptr [rbp+57h+var_70]
0x18005cca5  mov     [r14], rax
0x18005cca8  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18005ccac  mov     [r14+8], rax
0x18005ccb0  mov     rax, [rbp+57h+var_60]
0x18005ccb4  mov     [r14+10h], rax
0x18005ccb8  xorps   xmm0, xmm0
0x18005ccbb  movdqu  [rbp+57h+var_70], xmm0
0x18005ccc0  mov     [rbp+57h+var_60], r13
0x18005ccc4  mov     eax, [rbp+57h+var_A0]
0x18005ccc7  mov     [r12], eax
0x18005cccb  lea     rcx, [rbp+57h+var_70]
0x18005cccf  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005ccd4  nop
0x18005ccd5  mov     rcx, [rbp+57h+var_98]
0x18005ccd9  test    rcx, rcx
0x18005ccdc  jz      short loc_18005CCFC
0x18005ccde  mov     rdx, [rbp+57h+var_88]
0x18005cce2  sub     rdx, rcx
0x18005cce5  sar     rdx, 1
0x18005cce8  add     rdx, rdx
0x18005cceb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005ccf0  xorps   xmm0, xmm0
0x18005ccf3  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18005ccf8  mov     [rbp+57h+var_88], r13
0x18005ccfc  lea     rcx, [rbp+57h+hkey]
0x18005cd00  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005cd05  xor     eax, eax
0x18005cd07  jmp     short loc_18005CD32
0x18005cd09  mov     ebx, 80070018h
0x18005cd0e  mov     edx, 291h; void *
0x18005cd13  mov     r9d, ebx; char *
0x18005cd16  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005cd1d  mov     rcx, [rbp+5Fh]; this
0x18005cd21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd26  nop
0x18005cd27  lea     rcx, [rbp+57h+hkey]
0x18005cd2b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005cd30  mov     eax, ebx
0x18005cd32  mov     rcx, [rbp+57h+var_38]
0x18005cd36  xor     rcx, rsp; StackCookie
0x18005cd39  call    __security_check_cookie
0x18005cd3e  mov     rbx, [rsp+0E0h+arg_0]
0x18005cd46  add     rsp, 0B0h
0x18005cd4d  pop     r15
0x18005cd4f  pop     r14
0x18005cd51  pop     r13
0x18005cd53  pop     r12
0x18005cd55  pop     rdi
0x18005cd56  pop     rsi
0x18005cd57  pop     rbp
0x18005cd58  retn
```
