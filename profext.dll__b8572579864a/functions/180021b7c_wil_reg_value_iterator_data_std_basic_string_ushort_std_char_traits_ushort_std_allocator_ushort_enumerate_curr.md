# wil::reg::value_iterator_data<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::enumerate_current_index(void)

- ea: `0x180021b7c`
- end: `0x180021d35`
- name: `?enumerate_current_index@?$value_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@AEAAJXZ`
- size: `441`
- prototype: `__int64 __fastcall(LPWSTR lpValueName)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001f0c4`
- `0x180020ab0`

## callees

- `0x180004594`
- `0x180016ddc`
- `0x18001d388`
- `0x180021948`
- `0x180021b7c`
- `0x180021ffc`
- `0x180022044`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180021c61`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180021c61`

## string_xrefs

- `0x180021bd4`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180021c9f`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180021ce8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180021d23`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
int __fastcall wil::reg::value_iterator_data<std::wstring>::enumerate_current_index(
        LPWSTR lpValueName,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  DWORD v5; // eax
  __int64 v6; // rdi
  WCHAR *v8; // r8
  unsigned int v9; // eax
  int v10; // eax
  int v11; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cchValueName; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)lpValueName + 12) == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x68D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      a4);
  v5 = 32;
  if ( *((_DWORD *)lpValueName + 14) )
    v5 = *((_DWORD *)lpValueName + 14);
  while ( 1 )
  {
    v6 = v5;
    cchValueName = v5;
    if ( (unsigned __int64)v5 <= *((_QWORD *)lpValueName + 7) )
    {
      v6 = *((_QWORD *)lpValueName + 7);
    }
    else if ( (int)wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(lpValueName, 2 * v5) < 0 )
    {
      *((_QWORD *)lpValueName + 7) = 0;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x696,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)0x8007000ELL,
        lpReserved);
      return -2147024882;
    }
    wil::reg::reg_iterator_details::clear_name(lpValueName);
    *((_QWORD *)lpValueName + 7) = v6;
    if ( !v6 )
      goto LABEL_7;
    if ( cchValueName )
      v8 = *((_QWORD *)lpValueName + 3) < 8u ? lpValueName : *(WCHAR **)lpValueName;
    else
      v8 = 0;
    v9 = RegEnumValueW(
           *((HKEY *)lpValueName + 5),
           *((_DWORD *)lpValueName + 12),
           v8,
           &cchValueName,
           0,
           (LPDWORD)lpValueName + 8,
           0,
           0);
    if ( !v9 )
      break;
    if ( v9 == 259 )
    {
      wil::reg::reg_iterator_details::clear_name(lpValueName);
      *((_DWORD *)lpValueName + 12) = -1;
      return 0;
    }
    if ( v9 != 234 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x6CA,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
               (const char *)v9,
               lpReserved);
    if ( cchValueName == 0x4000 )
      return 0;
    v5 = 2 * cchValueName;
    if ( 2 * cchValueName > 0x4000 )
      v5 = 0x4000;
  }
  ++cchValueName;
  v10 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(lpValueName, 2 * cchValueName);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)(unsigned int)v10,
      lpReserved);
    return v11;
  }
  *((_QWORD *)lpValueName + 7) = cchValueName;
  *((_QWORD *)lpValueName + 7) = wil::reg::reg_view_details::reg_value_type_info::trim_buffer(lpValueName);
  return 0;
}

```

## disassembly

```asm
0x180021b7c  mov     [rsp+arg_8], rbx
0x180021b81  mov     [rsp+arg_10], rdi
0x180021b86  push    r14
0x180021b88  sub     rsp, 40h
0x180021b8c  cmp     dword ptr [rcx+30h], 0FFFFFFFFh
0x180021b90  mov     rbx, rcx
0x180021b93  jz      loc_180021D1E
0x180021b99  cmp     dword ptr [rcx+38h], 0
0x180021b9d  mov     eax, 20h ; ' '
0x180021ba2  mov     r14d, 4000h
0x180021ba8  cmova   eax, [rcx+38h]
0x180021bac  mov     edi, eax
0x180021bae  mov     [rsp+48h+cchValueName], eax
0x180021bb2  cmp     rdi, [rbx+38h]
0x180021bb6  jbe     short loc_180021C01
0x180021bb8  lea     edx, [rax+rax]
0x180021bbb  mov     rcx, rbx
0x180021bbe  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x180021bc3  test    eax, eax
0x180021bc5  jns     short loc_180021C05
0x180021bc7  mov     qword ptr [rbx+38h], 0
0x180021bcf  mov     rcx, [rsp+48h]; this
0x180021bd4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021bdb  mov     ebx, 8007000Eh
0x180021be0  mov     edx, 696h; void *
0x180021be5  mov     r9d, ebx; char *
0x180021be8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021bed  mov     eax, ebx
0x180021bef  mov     rbx, [rsp+48h+arg_8]
0x180021bf4  mov     rdi, [rsp+48h+arg_10]
0x180021bf9  add     rsp, 40h
0x180021bfd  pop     r14
0x180021bff  retn
0x180021c01  mov     rdi, [rbx+38h]
0x180021c05  mov     rcx, rbx
0x180021c08  call    ?clear_name@reg_iterator_details@reg@wil@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; wil::reg::reg_iterator_details::clear_name(std::wstring &,unsigned __int64)
0x180021c0d  mov     [rbx+38h], rdi
0x180021c11  test    rdi, rdi
0x180021c14  jz      short loc_180021BCF
0x180021c16  cmp     [rsp+48h+cchValueName], 0
0x180021c1b  lea     rax, [rbx+20h]
0x180021c1f  jnz     short loc_180021C26
0x180021c21  xor     r8d, r8d
0x180021c24  jmp     short loc_180021C35
0x180021c26  cmp     qword ptr [rbx+18h], 8
0x180021c2b  jb      short loc_180021C32
0x180021c2d  mov     r8, [rbx]
0x180021c30  jmp     short loc_180021C35
0x180021c32  mov     r8, rbx; lpValueName
0x180021c35  mov     edx, [rbx+30h]; dwIndex
0x180021c38  lea     r9, [rsp+48h+cchValueName]; lpcchValueName
0x180021c3d  mov     rcx, [rbx+28h]; hKey
0x180021c41  mov     [rsp+48h+lpcbData], 0; lpcbData
0x180021c4a  mov     [rsp+48h+lpData], 0; lpData
0x180021c53  mov     [rsp+48h+lpType], rax; lpType
0x180021c58  mov     [rsp+48h+lpReserved], 0; int
0x180021c61  call    cs:__imp_RegEnumValueW
0x180021c68  nop     dword ptr [rax+rax+00h]
0x180021c6d  test    eax, eax
0x180021c6f  jz      short loc_180021CC9
0x180021c71  cmp     eax, 103h
0x180021c76  jz      short loc_180021CB8
0x180021c78  cmp     eax, 0EAh
0x180021c7d  jnz     short loc_180021C9A
0x180021c7f  mov     eax, [rsp+48h+cchValueName]
0x180021c83  cmp     eax, r14d
0x180021c86  jz      loc_180021D17
0x180021c8c  add     eax, eax
0x180021c8e  cmp     eax, r14d
0x180021c91  cmova   eax, r14d
0x180021c95  jmp     loc_180021BAC
0x180021c9a  mov     rcx, [rsp+48h]; this
0x180021c9f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021ca6  mov     r9d, eax; char *
0x180021ca9  mov     edx, 6CAh; void *
0x180021cae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021cb3  jmp     loc_180021BEF
0x180021cb8  mov     rcx, rbx
0x180021cbb  call    ?clear_name@reg_iterator_details@reg@wil@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; wil::reg::reg_iterator_details::clear_name(std::wstring &,unsigned __int64)
0x180021cc0  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x180021cc7  jmp     short loc_180021D17
0x180021cc9  mov     edx, [rsp+48h+cchValueName]
0x180021ccd  mov     rcx, rbx
0x180021cd0  inc     edx
0x180021cd2  mov     [rsp+48h+cchValueName], edx
0x180021cd6  add     edx, edx
0x180021cd8  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x180021cdd  mov     edi, eax
0x180021cdf  test    eax, eax
0x180021ce1  jns     short loc_180021D03
0x180021ce3  mov     rcx, [rsp+48h]; this
0x180021ce8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021cef  mov     r9d, eax; char *
0x180021cf2  mov     edx, 6ACh; void *
0x180021cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021cfc  mov     eax, edi
0x180021cfe  jmp     loc_180021BEF
0x180021d03  mov     eax, [rsp+48h+cchValueName]
0x180021d07  mov     rcx, rbx
0x180021d0a  mov     [rbx+38h], rax
0x180021d0e  call    ?trim_buffer@reg_value_type_info@reg_view_details@reg@wil@@YA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wil::reg::reg_view_details::reg_value_type_info::trim_buffer(std::wstring &)
0x180021d13  mov     [rbx+38h], rax
0x180021d17  xor     eax, eax
0x180021d19  jmp     loc_180021BEF
0x180021d1e  mov     rcx, [rsp+48h]; this
0x180021d23  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021d2a  mov     edx, 68Dh; void *
0x180021d2f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
