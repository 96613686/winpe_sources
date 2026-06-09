# web::json::details::_Number::format(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000bde0`
- end: `0x14000bf44`
- name: `?format@_Number@details@json@web@@MEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002f60`
- `0x140003b1c`
- `0x140003bc4`
- `0x14000bde0`
- `0x14000c490`
- `0x14001aad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x14000be24`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x14000be24`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x14000be2c`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x14000be2c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000be3c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000be3c`

## pseudocode

```c
__int64 __fastcall web::json::details::_Number::format(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  __int64 v4; // rcx
  size_t v5; // rax
  unsigned __int64 v6; // r8
  __int64 v7; // rdx
  size_t v8; // rdi
  __int64 result; // rax
  __int64 v10; // xmm6_8
  __crt_locale_pointers *v11; // rax
  int v12; // eax
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdi
  wchar_t Source[28]; // [rsp+30h] [rbp-58h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 == 2 )
  {
    v10 = *(_QWORD *)(a1 + 8);
    v11 = utility::details::scoped_c_thread_locale::c_locale();
    v12 = swprintf_s_l(Source, 0x19u, L"%.*g", v11, 17, v10);
    v13 = a2[3];
    v14 = a2[2];
    if ( v12 > v13 - v14 )
    {
      return ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
               a2,
               v12);
    }
    else
    {
      v15 = v12 + v14;
      a2[2] = v15;
      if ( v13 > 7 )
        a2 = (_QWORD *)*a2;
      memmove_0((char *)a2 + 2 * v14, Source, 2LL * v12);
      result = 0;
      *((_WORD *)a2 + v15) = 0;
    }
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      _o__ui64tow_s(v4, Source, 22, 10);
    else
      _o__i64tow_s(v4, Source, 22, 10);
    v5 = wcsnlen(Source, 0x16u);
    v6 = a2[3];
    v7 = a2[2];
    if ( v5 > v6 - v7 )
    {
      return ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
               a2,
               v5);
    }
    else
    {
      v8 = v7 + v5;
      a2[2] = v7 + v5;
      if ( v6 > 7 )
        a2 = (_QWORD *)*a2;
      memmove_0((char *)a2 + 2 * v7, Source, 2 * v5);
      result = 0;
      *((_WORD *)a2 + v8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000bde0  mov     [rsp+arg_10], rbx
0x14000bde5  push    rdi
0x14000bde6  sub     rsp, 80h
0x14000bded  mov     rax, cs:__security_cookie
0x14000bdf4  xor     rax, rsp
0x14000bdf7  mov     [rsp+88h+var_20], rax
0x14000bdfc  mov     eax, [rcx+10h]
0x14000bdff  mov     rbx, rdx
0x14000be02  cmp     eax, 2
0x14000be05  jz      loc_14000BE95
0x14000be0b  mov     rcx, [rcx+8]
0x14000be0f  mov     r9d, 0Ah
0x14000be15  lea     rdx, [rsp+88h+Source]
0x14000be1a  mov     r8d, 16h
0x14000be20  test    eax, eax
0x14000be22  jnz     short loc_14000BE2C
0x14000be24  call    cs:__imp__o__i64tow_s
0x14000be2a  jmp     short loc_14000BE32
0x14000be2c  call    cs:__imp__o__ui64tow_s
0x14000be32  mov     edx, 16h; MaxCount
0x14000be37  lea     rcx, [rsp+88h+Source]; Source
0x14000be3c  call    cs:__imp_wcsnlen
0x14000be42  mov     r8, [rbx+18h]
0x14000be46  mov     rdx, [rbx+10h]
0x14000be4a  mov     rcx, r8
0x14000be4d  sub     rcx, rdx
0x14000be50  cmp     rax, rcx
0x14000be53  ja      short loc_14000BE83
0x14000be55  lea     rdi, [rdx+rax]
0x14000be59  mov     [rbx+10h], rdi
0x14000be5d  cmp     r8, 7
0x14000be61  jbe     short loc_14000BE66
0x14000be63  mov     rbx, [rbx]
0x14000be66  lea     rcx, [rbx+rdx*2]; void *
0x14000be6a  lea     rdx, [rsp+88h+Source]; Src
0x14000be6f  lea     r8, [rax+rax]; Size
0x14000be73  call    memmove_0
0x14000be78  xor     eax, eax
0x14000be7a  mov     [rbx+rdi*2], ax
0x14000be7e  jmp     loc_14000BF26
0x14000be83  mov     [rsp+88h+var_68], rax
0x14000be88  lea     r9, [rsp+88h+Source]
0x14000be8d  mov     rdx, rax
0x14000be90  jmp     loc_14000BF1B
0x14000be95  movaps  [rsp+88h+var_18], xmm6
0x14000be9a  movsd   xmm6, qword ptr [rcx+8]
0x14000be9f  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x14000bea4  movsd   [rsp+88h+var_60], xmm6
0x14000beaa  lea     r8, aG_0; "%.*g"
0x14000beb1  mov     r9, rax; Locale
0x14000beb4  mov     dword ptr [rsp+88h+var_68], 11h
0x14000bebc  mov     edx, 19h; BufferCount
0x14000bec1  lea     rcx, [rsp+88h+Source]; Buffer
0x14000bec6  call    _swprintf_s_l
0x14000becb  mov     r8, [rbx+18h]
0x14000becf  mov     rcx, [rbx+10h]
0x14000bed3  movaps  xmm6, [rsp+88h+var_18]
0x14000bed8  movsxd  rdx, eax
0x14000bedb  mov     rax, r8
0x14000bede  sub     rax, rcx
0x14000bee1  cmp     rdx, rax
0x14000bee4  ja      short loc_14000BF11
0x14000bee6  lea     rdi, [rdx+rcx]
0x14000beea  mov     [rbx+10h], rdi
0x14000beee  cmp     r8, 7
0x14000bef2  jbe     short loc_14000BEF7
0x14000bef4  mov     rbx, [rbx]
0x14000bef7  lea     r8, [rdx+rdx]; Size
0x14000befb  lea     rdx, [rsp+88h+Source]; Src
0x14000bf00  lea     rcx, [rbx+rcx*2]; void *
0x14000bf04  call    memmove_0
0x14000bf09  xor     eax, eax
0x14000bf0b  mov     [rbx+rdi*2], ax
0x14000bf0f  jmp     short loc_14000BF26
0x14000bf11  mov     [rsp+88h+var_68], rdx; __int64
0x14000bf16  lea     r9, [rsp+88h+Source]
0x14000bf1b  xor     r8d, r8d
0x14000bf1e  mov     rcx, rbx; Src
0x14000bf21  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x14000bf26  mov     rcx, [rsp+88h+var_20]
0x14000bf2b  xor     rcx, rsp; StackCookie
0x14000bf2e  call    __security_check_cookie
0x14000bf33  mov     rbx, [rsp+88h+arg_10]
0x14000bf3b  add     rsp, 80h
0x14000bf42  pop     rdi
0x14000bf43  retn
```
