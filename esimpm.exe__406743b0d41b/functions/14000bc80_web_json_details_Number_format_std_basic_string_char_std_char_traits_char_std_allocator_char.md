# web::json::details::_Number::format(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x14000bc80`
- end: `0x14000bdda`
- name: `?format@_Number@details@json@web@@MEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `346`
- prototype: `void *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002f60`
- `0x140003b1c`
- `0x140003d54`
- `0x1400052c0`
- `0x14000bc80`
- `0x14000c490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64toa_s` at `0x14000bcc1`
- `api-ms-win-crt-private-l1-1-0!_o__i64toa_s` at `0x14000bcc1`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x14000bcc9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x14000bcc9`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x14000bcd9`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x14000bcd9`

## pseudocode

```c
void *__fastcall web::json::details::_Number::format(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  unsigned __int64 v4; // rcx
  size_t v5; // rax
  unsigned __int64 v6; // rdx
  size_t Size; // rdi
  __int64 v8; // rax
  char *v9; // rbx
  void *result; // rax
  __int64 v11; // xmm6_8
  __crt_locale_pointers *v12; // rax
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  char Buffer[32]; // [rsp+30h] [rbp-48h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 != 2 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      _ui64toa_s(v4, Buffer, 0x16u, 10);
    else
      _i64toa_s(v4, Buffer, 0x16u, 10);
    v5 = strnlen(Buffer, 0x16u);
    v6 = a2[3];
    Size = v5;
    v8 = a2[2];
    if ( Size <= v6 - v8 )
    {
      a2[2] = v8 + Size;
      if ( v6 > 0xF )
        a2 = (_QWORD *)*a2;
      v9 = (char *)a2 + v8;
      result = memmove_0(v9, Buffer, Size);
      v9[Size] = 0;
      return result;
    }
    return (void *)____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                     a2,
                     Size);
  }
  v11 = *(_QWORD *)(a1 + 8);
  v12 = utility::details::scoped_c_thread_locale::c_locale();
  v13 = sprintf_s_l(Buffer, 0x19u, "%.*g", v12, 17, v11);
  v14 = a2[3];
  v15 = a2[2];
  Size = v13;
  if ( v13 > v14 - v15 )
    return (void *)____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                     a2,
                     Size);
  a2[2] = v13 + v15;
  if ( v14 > 0xF )
    a2 = (_QWORD *)*a2;
  v16 = (char *)a2 + v15;
  result = memmove_0(v16, Buffer, v13);
  v16[Size] = 0;
  return result;
}

```

## disassembly

```asm
0x14000bc80  mov     [rsp+arg_10], rbx
0x14000bc85  push    rdi
0x14000bc86  sub     rsp, 70h
0x14000bc8a  mov     rax, cs:__security_cookie
0x14000bc91  xor     rax, rsp
0x14000bc94  mov     [rsp+78h+var_28], rax
0x14000bc99  mov     eax, [rcx+10h]
0x14000bc9c  mov     rbx, rdx
0x14000bc9f  cmp     eax, 2
0x14000bca2  jz      loc_14000BD2C
0x14000bca8  mov     rcx, [rcx+8]; Value
0x14000bcac  mov     r9d, 0Ah; Radix
0x14000bcb2  lea     rdx, [rsp+78h+Buffer]; Buffer
0x14000bcb7  mov     r8d, 16h; BufferCount
0x14000bcbd  test    eax, eax
0x14000bcbf  jnz     short loc_14000BCC9
0x14000bcc1  call    cs:__imp__i64toa_s
0x14000bcc7  jmp     short loc_14000BCCF
0x14000bcc9  call    cs:__imp__ui64toa_s
0x14000bccf  mov     edx, 16h; MaxCount
0x14000bcd4  lea     rcx, [rsp+78h+Buffer]; String
0x14000bcd9  call    cs:__imp_strnlen
0x14000bcdf  mov     rdx, [rbx+18h]
0x14000bce3  mov     rdi, rax
0x14000bce6  mov     rax, [rbx+10h]
0x14000bcea  mov     rcx, rdx
0x14000bced  sub     rcx, rax
0x14000bcf0  cmp     rdi, rcx
0x14000bcf3  ja      short loc_14000BD22
0x14000bcf5  lea     rcx, [rax+rdi]
0x14000bcf9  mov     [rbx+10h], rcx
0x14000bcfd  cmp     rdx, 0Fh
0x14000bd01  jbe     short loc_14000BD06
0x14000bd03  mov     rbx, [rbx]
0x14000bd06  add     rbx, rax
0x14000bd09  lea     rdx, [rsp+78h+Buffer]; Src
0x14000bd0e  mov     rcx, rbx; void *
0x14000bd11  mov     r8, rdi; Size
0x14000bd14  call    memmove_0
0x14000bd19  mov     byte ptr [rbx+rdi], 0
0x14000bd1d  jmp     loc_14000BDBF
0x14000bd22  lea     r9, [rsp+78h+Buffer]
0x14000bd27  jmp     loc_14000BDAC
0x14000bd2c  movaps  [rsp+78h+var_18], xmm6
0x14000bd31  movsd   xmm6, qword ptr [rcx+8]
0x14000bd36  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x14000bd3b  movsd   [rsp+78h+var_50], xmm6
0x14000bd41  lea     r8, aG; "%.*g"
0x14000bd48  mov     r9, rax; Locale
0x14000bd4b  mov     dword ptr [rsp+78h+Size], 11h
0x14000bd53  mov     edx, 19h; BufferCount
0x14000bd58  lea     rcx, [rsp+78h+Buffer]; Buffer
0x14000bd5d  call    _sprintf_s_l
0x14000bd62  mov     rdx, [rbx+18h]
0x14000bd66  mov     rcx, [rbx+10h]
0x14000bd6a  movaps  xmm6, [rsp+78h+var_18]
0x14000bd6f  movsxd  rdi, eax
0x14000bd72  mov     rax, rdx
0x14000bd75  sub     rax, rcx
0x14000bd78  cmp     rdi, rax
0x14000bd7b  ja      short loc_14000BDA7
0x14000bd7d  lea     rax, [rdi+rcx]
0x14000bd81  mov     [rbx+10h], rax
0x14000bd85  cmp     rdx, 0Fh
0x14000bd89  jbe     short loc_14000BD8E
0x14000bd8b  mov     rbx, [rbx]
0x14000bd8e  add     rbx, rcx
0x14000bd91  lea     rdx, [rsp+78h+Buffer]; Src
0x14000bd96  mov     rcx, rbx; void *
0x14000bd99  mov     r8, rdi; Size
0x14000bd9c  call    memmove_0
0x14000bda1  mov     byte ptr [rbx+rdi], 0
0x14000bda5  jmp     short loc_14000BDBF
0x14000bda7  lea     r9, [rsp+78h+Buffer]
0x14000bdac  xor     r8d, r8d
0x14000bdaf  mov     [rsp+78h+Size], rdi; Size
0x14000bdb4  mov     rdx, rdi
0x14000bdb7  mov     rcx, rbx; Src
0x14000bdba  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x14000bdbf  mov     rcx, [rsp+78h+var_28]
0x14000bdc4  xor     rcx, rsp; StackCookie
0x14000bdc7  call    __security_check_cookie
0x14000bdcc  mov     rbx, [rsp+78h+arg_10]
0x14000bdd4  add     rsp, 70h
0x14000bdd8  pop     rdi
0x14000bdd9  retn
```
