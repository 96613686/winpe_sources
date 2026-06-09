# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)

- ea: `0x180001380`
- end: `0x18000150b`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `395`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180001170`
- `0x180009c4c`

## callees

- `0x180001380`
- `0x1800015e0`
- `0x1800016c0`
- `0x1800036b4`
- `0x180003700`
- `0x180004030`
- `0x180004764`
- `0x180005020`
- `0x180005b50`
- `0x180009598`
- `0x180009824`

## string_xrefs

- `0x1800013b0`: `uusbrain.dll`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, _QWORD *a2)
{
  const WCHAR *v4; // rcx
  unsigned int stats; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int128 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpFileName[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+B0h] [rbp-50h] BYREF

  *(_QWORD *)&v9 = L"uusbrain.dll";
  *((_QWORD *)&v9 + 1) = 12;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v12, &v9);
  std::filesystem::operator/(lpFileName, a2, (std::filesystem *)v12);
  std::wstring::_Tidy_deallocate(v12);
  v9 = 0;
  v10 = 0;
  v4 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v4 = lpFileName[0];
  stats = _std_fs_get_stats(v4);
  v6 = stats;
  if ( stats )
  {
    if ( !(unsigned __int8)_std_is_file_not_found(stats) )
    {
      std::string::string(v13, "exists");
      LODWORD(v9) = v6;
      *((_QWORD *)&v9 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      std::filesystem::filesystem_error::filesystem_error(pExceptionObject, v13, lpFileName, &v9);
      throw (std::filesystem::filesystem_error *)pExceptionObject;
    }
    v7 = 1;
  }
  else
  {
    if ( (v10 & 0x400) == 0 )
      goto LABEL_9;
    if ( DWORD1(v10) == -1610612724 )
    {
      v7 = 4;
      goto LABEL_12;
    }
    if ( DWORD1(v10) == -1610612733 )
      v7 = 10;
    else
LABEL_9:
      v7 = (unsigned __int128)(v10 & 0x10 | 0x20) >> 4;
  }
LABEL_12:
  if ( v7 == 1 )
    *(_BYTE *)(a1 + 32) = 0;
  else
    std::make_optional<std::filesystem::path,std::filesystem::path &,0>(a1, lpFileName);
  std::wstring::_Tidy_deallocate(lpFileName);
  return a1;
}

```

## disassembly

```asm
0x180001380  mov     [rsp-8+arg_10], rbx
0x180001385  mov     [rsp-8+arg_18], rdi
0x18000138a  push    rbp
0x18000138b  lea     rbp, [rsp-50h]
0x180001390  sub     rsp, 150h
0x180001397  mov     rax, cs:__security_cookie
0x18000139e  xor     rax, rsp
0x1800013a1  mov     [rbp+50h+var_10], rax
0x1800013a5  mov     rbx, rdx
0x1800013a8  mov     rdi, rcx
0x1800013ab  mov     qword ptr [rsp+150h+var_120], rcx
0x1800013b0  lea     rax, aUusbrainDll; "uusbrain.dll"
0x1800013b7  mov     qword ptr [rsp+150h+var_120], rax
0x1800013bc  mov     qword ptr [rsp+150h+var_120+8], 0Ch
0x1800013c5  lea     rdx, [rsp+150h+var_120]
0x1800013ca  lea     rcx, [rsp+150h+var_E0]
0x1800013cf  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1800013d4  nop
0x1800013d5  lea     r8, [rsp+150h+var_E0]; this
0x1800013da  mov     rdx, rbx; void *
0x1800013dd  lea     rcx, [rsp+150h+lpFileName]; Src
0x1800013e2  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800013e7  nop
0x1800013e8  lea     rcx, [rsp+150h+var_E0]
0x1800013ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800013f2  xorps   xmm0, xmm0
0x1800013f5  movups  [rsp+150h+var_120], xmm0
0x1800013fa  movups  [rsp+150h+var_110], xmm0
0x1800013ff  lea     rcx, [rsp+150h+lpFileName]
0x180001404  cmp     [rsp+150h+var_E8], 7
0x18000140a  cmova   rcx, [rsp+150h+lpFileName]; lpFileName
0x180001410  mov     r9d, 0FFFFFFFFh
0x180001416  mov     r8d, 3
0x18000141c  lea     rdx, [rsp+150h+var_120]
0x180001421  call    __std_fs_get_stats
0x180001426  mov     ebx, eax
0x180001428  test    eax, eax
0x18000142a  jnz     short loc_180001463
0x18000142c  mov     eax, dword ptr [rsp+150h+var_110]
0x180001430  bt      eax, 0Ah
0x180001434  jnb     short loc_180001458
0x180001436  mov     ecx, dword ptr [rsp+150h+var_110+4]
0x18000143a  cmp     ecx, 0A000000Ch
0x180001440  jnz     short loc_180001449
0x180001442  mov     eax, 4
0x180001447  jmp     short loc_180001473
0x180001449  cmp     ecx, 0A0000003h
0x18000144f  jnz     short loc_180001458
0x180001451  mov     eax, 0Ah
0x180001456  jmp     short loc_180001473
0x180001458  and     eax, 10h
0x18000145b  or      eax, 20h
0x18000145e  shr     eax, 4
0x180001461  jmp     short loc_180001473
0x180001463  mov     ecx, ebx
0x180001465  call    __std_is_file_not_found
0x18000146a  test    al, al
0x18000146c  jz      short loc_1800014BA
0x18000146e  mov     eax, 1
0x180001473  cmp     eax, 1
0x180001476  jz      short loc_1800014B4
0x180001478  lea     rdx, [rsp+150h+lpFileName]
0x18000147d  mov     rcx, rdi
0x180001480  call    ??$make_optional@Vpath@filesystem@std@@AEAV123@$0A@@std@@YA?AV?$optional@Vpath@filesystem@std@@@0@AEAVpath@filesystem@0@@Z; std::make_optional<std::filesystem::path,std::filesystem::path &,0>(std::filesystem::path &)
0x180001485  nop
0x180001486  lea     rcx, [rsp+150h+lpFileName]
0x18000148b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180001490  mov     rax, rdi
0x180001493  mov     rcx, [rbp+50h+var_10]
0x180001497  xor     rcx, rsp; StackCookie
0x18000149a  call    __security_check_cookie
0x18000149f  lea     r11, [rsp+150h+var_s0]
0x1800014a7  mov     rbx, [r11+20h]
0x1800014ab  mov     rdi, [r11+28h]
0x1800014af  mov     rsp, r11
0x1800014b2  pop     rbp
0x1800014b3  retn
0x1800014b4  mov     byte ptr [rdi+20h], 0
0x1800014b8  jmp     short loc_180001486
0x1800014ba  lea     rdx, aExists; "exists"
0x1800014c1  lea     rcx, [rbp+50h+var_C0]
0x1800014c5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800014ca  nop
0x1800014cb  mov     dword ptr [rsp+150h+var_120], ebx
0x1800014cf  mov     eax, dword ptr [rsp+150h+var_120+4]
0x1800014d3  mov     dword ptr [rsp+150h+var_120+4], eax
0x1800014d7  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800014de  mov     qword ptr [rsp+150h+var_120+8], rax
0x1800014e3  lea     r9, [rsp+150h+var_120]
0x1800014e8  lea     r8, [rsp+150h+lpFileName]
0x1800014ed  lea     rdx, [rbp+50h+var_C0]
0x1800014f1  lea     rcx, [rbp+50h+pExceptionObject]
0x1800014f5  call    ??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z; std::filesystem::filesystem_error::filesystem_error(std::string const &,std::filesystem::path const &,std::error_code)
0x1800014fa  lea     rdx, _TI5?AVfilesystem_error@filesystem@std@@; pThrowInfo
0x180001501  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180001505  call    _CxxThrowException_0
```
