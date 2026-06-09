# wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::get_value_with_type<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,wil::err_exception_policy>(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong)

- ea: `0x180012f1c`
- end: `0x1800130d5`
- name: `??$get_value_with_type@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uerr_exception_policy@wil@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@AEBAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `441`
- prototype: `__int64 __fastcall(int, int, int, int, wil::reg::reg_view_details *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800140a8`

## callees

- `0x18000d590`
- `0x180012f1c`
- `0x180015b40`
- `0x180015b90`
- `0x180015c00`
- `0x1800237f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012fc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012fc3`

## string_xrefs

- `0x180013022`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800130a9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800130c3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180012fb7`: `EncoderDllName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::get_value_with_type<std::wstring,wil::err_exception_policy>(
        HKEY *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        wil::reg::reg_view_details *a5)
{
  _QWORD *v7; // rdx
  _WORD *v8; // rdi
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  int v11; // edx
  DWORD value_flags_from_value_type; // edi
  void *pvData; // rcx
  int ValueW; // eax
  _QWORD *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  __int64 result; // rax
  _QWORD *v20; // rdi
  __int64 v21; // rdx
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 pcbData; // [rsp+60h] [rbp+18h] BYREF

  pcbData = a3;
  if ( a4[3] <= 7u )
  {
    v8 = a4;
    v7 = a4;
  }
  else
  {
    v7 = (_QWORD *)*a4;
    v8 = (_WORD *)*a4;
  }
  v9 = (unsigned __int64)v7 + 2 * a4[2];
  v10 = (v9 - (unsigned __int64)v8 + 1) >> 1;
  if ( (unsigned __int64)v8 > v9 )
    v10 = 0;
  if ( v10 )
  {
    while ( v10 )
    {
      *v8++ = 0;
      --v10;
    }
  }
  value_flags_from_value_type = wil::reg::reg_view_details::get_value_flags_from_value_type(
                                  (wil::reg::reg_view_details *)(unsigned int)a5,
                                  2 * *((_DWORD *)a4 + 4) + 2);
  while ( 1 )
  {
    LODWORD(pcbData) = v11;
    if ( a4[3] <= 7u )
      pvData = a4;
    else
      pvData = (void *)*a4;
    ValueW = RegGetValueW(*a1, 0, L"EncoderDllName", value_flags_from_value_type, 0, pvData, (LPDWORD)&pcbData);
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW == -2147024662 )
    {
      v16 = (unsigned int)pcbData;
      goto LABEL_26;
    }
    if ( ValueW < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)ValueW,
        pdwType);
    v15 = a4[3] <= 7u ? a4 : (_QWORD *)*a4;
    v16 = (unsigned int)pcbData;
    if ( v15 || !(_DWORD)pcbData )
      break;
LABEL_26:
    v18 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a4, v16);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v18,
        pdwType);
    v11 = pcbData;
  }
  if ( 2 * *((_DWORD *)a4 + 4) + 2 != (_DWORD)pcbData )
  {
    v17 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a4, (unsigned int)pcbData);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v17,
        pdwType);
  }
  result = a4[2];
  if ( a4[3] <= 7u )
    v20 = a4;
  else
    v20 = (_QWORD *)*a4;
  if ( result )
  {
    result = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
               v20,
               (char *)v20 + 2 * result,
               0);
    if ( result != v21 )
    {
      result = (result - (__int64)v20) >> 1;
      if ( result != -1 )
        return std::wstring::resize(a4, result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012f1c  mov     [rsp+arg_0], rbx
0x180012f21  mov     [rsp+arg_8], rsi
0x180012f26  mov     [rsp+arg_10], r8
0x180012f2b  push    rdi
0x180012f2c  sub     rsp, 40h
0x180012f30  mov     rbx, r9
0x180012f33  mov     rsi, rcx
0x180012f36  cmp     qword ptr [r9+18h], 7
0x180012f3b  jbe     short loc_180012F45
0x180012f3d  mov     rdx, [r9]
0x180012f40  mov     rdi, rdx
0x180012f43  jmp     short loc_180012F4B
0x180012f45  mov     rdi, rbx
0x180012f48  mov     rdx, rbx
0x180012f4b  mov     rax, [r9+10h]
0x180012f4f  lea     rdx, [rdx+rax*2]
0x180012f53  mov     rcx, rdx
0x180012f56  sub     rcx, rdi
0x180012f59  inc     rcx
0x180012f5c  shr     rcx, 1
0x180012f5f  xor     eax, eax
0x180012f61  cmp     rdi, rdx
0x180012f64  cmova   rcx, rax
0x180012f68  test    rcx, rcx
0x180012f6b  jz      short loc_180012F73
0x180012f6d  movzx   eax, ax
0x180012f70  rep stosw
0x180012f73  mov     eax, [r9+10h]
0x180012f77  lea     edx, ds:2[rax*2]; unsigned int
0x180012f7e  mov     ecx, dword ptr [rsp+48h+arg_20]; this
0x180012f82  call    ?get_value_flags_from_value_type@reg_view_details@reg@wil@@YAKK@Z; wil::reg::reg_view_details::get_value_flags_from_value_type(ulong)
0x180012f87  mov     edi, eax
0x180012f89  mov     dword ptr [rsp+48h+arg_10], edx
0x180012f8d  cmp     qword ptr [rbx+18h], 7
0x180012f92  jbe     short loc_180012F99
0x180012f94  mov     rcx, [rbx]
0x180012f97  jmp     short loc_180012F9C
0x180012f99  mov     rcx, rbx
0x180012f9c  lea     rax, [rsp+48h+arg_10]
0x180012fa1  mov     [rsp+48h+pcbData], rax; pcbData
0x180012fa6  mov     [rsp+48h+pvData], rcx; pvData
0x180012fab  mov     [rsp+48h+pdwType], 0; int
0x180012fb4  mov     r9d, edi; dwFlags
0x180012fb7  lea     r8, aEncoderdllname; "EncoderDllName"
0x180012fbe  xor     edx, edx; lpSubKey
0x180012fc0  mov     rcx, [rsi]; hkey
0x180012fc3  call    cs:__imp_RegGetValueW
0x180012fc9  test    eax, eax
0x180012fcb  jle     short loc_180012FD5
0x180012fcd  movzx   eax, ax
0x180012fd0  or      eax, 80070000h
0x180012fd5  cmp     eax, 800700EAh
0x180012fda  jz      short loc_180013034
0x180012fdc  test    eax, eax
0x180012fde  js      loc_1800130A1
0x180012fe4  cmp     qword ptr [rbx+18h], 7
0x180012fe9  jbe     short loc_180012FF0
0x180012feb  mov     rax, [rbx]
0x180012fee  jmp     short loc_180012FF3
0x180012ff0  mov     rax, rbx
0x180012ff3  mov     edx, dword ptr [rsp+48h+arg_10]
0x180012ff7  test    rax, rax
0x180012ffa  jnz     short loc_180013000
0x180012ffc  test    edx, edx
0x180012ffe  jnz     short loc_180013038
0x180013000  mov     eax, [rbx+10h]
0x180013003  lea     eax, ds:2[rax*2]
0x18001300a  cmp     eax, edx
0x18001300c  jz      short loc_18001304D
0x18001300e  mov     rcx, rbx
0x180013011  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x180013016  test    eax, eax
0x180013018  jns     short loc_18001304D
0x18001301a  mov     rcx, [rsp+48h]; this
0x18001301f  mov     r9d, eax; char *
0x180013022  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013029  mov     edx, 1CBEh; void *
0x18001302e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013034  mov     edx, dword ptr [rsp+48h+arg_10]
0x180013038  mov     rcx, rbx
0x18001303b  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x180013040  test    eax, eax
0x180013042  js      short loc_1800130BB
0x180013044  mov     edx, dword ptr [rsp+48h+arg_10]
0x180013048  jmp     loc_180012F89
0x18001304d  mov     rax, [rbx+10h]
0x180013051  cmp     qword ptr [rbx+18h], 7
0x180013056  jbe     short loc_18001305D
0x180013058  mov     rdi, [rbx]
0x18001305b  jmp     short loc_180013060
0x18001305d  mov     rdi, rbx
0x180013060  test    rax, rax
0x180013063  jz      short loc_180013091
0x180013065  lea     rdx, [rdi+rax*2]
0x180013069  xor     r8d, r8d
0x18001306c  mov     rcx, rdi
0x18001306f  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x180013074  cmp     rax, rdx
0x180013077  jz      short loc_180013091
0x180013079  sub     rax, rdi
0x18001307c  sar     rax, 1
0x18001307f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013083  jz      short loc_180013091
0x180013085  mov     rdx, rax
0x180013088  mov     rcx, rbx
0x18001308b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180013090  nop
0x180013091  mov     rbx, [rsp+48h+arg_0]
0x180013096  mov     rsi, [rsp+48h+arg_8]
0x18001309b  add     rsp, 40h
0x18001309f  pop     rdi
0x1800130a0  retn
0x1800130a1  mov     rcx, [rsp+48h]; this
0x1800130a6  mov     r9d, eax; char *
0x1800130a9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800130b0  mov     edx, 1CBEh; void *
0x1800130b5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800130bb  mov     rcx, [rsp+48h]; this
0x1800130c0  mov     r9d, eax; char *
0x1800130c3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800130ca  mov     edx, 1CBEh; void *
0x1800130cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
