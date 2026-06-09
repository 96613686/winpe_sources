# std::vector<BTHLE_PREPAIRING_ENTRY,std::allocator<BTHLE_PREPAIRING_ENTRY>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18002cad8`
- end: `0x18002cc58`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UBTHLE_PREPAIRING_ENTRY@@V?$allocator@UBTHLE_PREPAIRING_ENTRY@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18002cc80`

## callees

- `0x180001b94`
- `0x180001bcc`
- `0x18000270c`
- `0x180011bf8`
- `0x180017a1c`
- `0x18002cad8`
- `0x180034b5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18002cc3f`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18002cc3f`

## pseudocode

```c
char *__fastcall std::vector<BTHLE_PREPAIRING_ENTRY>::_Resize_reallocate<std::_Value_init_tag>(
        const void **a1,
        unsigned __int64 a2)
{
  unsigned __int64 v4; // r15
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rsi
  void *v9; // rax
  const struct std::nothrow_t *v10; // rdx
  char *v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  char *v14; // rcx
  char *v15; // r8
  char *result; // rax
  unsigned __int64 v17; // [rsp+58h] [rbp+10h]

  if ( a2 > 0xA3D70A3D70A3D70LL )
    std::vector<BTHLE_PREPAIRING_ENTRY>::_Xlength();
  v4 = 0x8F5C28F5C28F5C29uLL * ((_BYTE *)a1[1] - (_BYTE *)*a1);
  v5 = 0x8F5C28F5C28F5C29uLL * ((_BYTE *)a1[2] - (_BYTE *)*a1);
  v6 = v5 >> 1;
  if ( v5 > 0xA3D70A3D70A3D70LL - (v5 >> 1) )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v7 = v6 + v5;
  if ( v6 + v5 >= a2 )
  {
    v17 = v6 + v5;
    if ( v7 > 0xA3D70A3D70A3D70LL )
      goto LABEL_24;
  }
  else
  {
    v7 = a2;
    v17 = a2;
  }
  v8 = 25 * v7;
  if ( 25 * v7 < 0x1000 )
  {
    if ( v8 )
      v12 = operator new(25 * v7);
    else
      v12 = 0;
  }
  else
  {
    if ( v8 + 39 < v8 )
      goto LABEL_24;
    v9 = operator new(v8 + 39);
    if ( !v9 )
      goto LABEL_23;
    v12 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v12 - 1) = v9;
  }
  try
  {
    if ( a2 != v4 )
      memset_0((char *)v12 + 25 * v4, 0, 25 * (a2 - v4));
    memmove_0(v12, *a1, (_BYTE *)a1[1] - (_BYTE *)*a1);
  }
  catch ( ... )
  {
    std::allocator<BTHLE_PREPAIRING_ENTRY>::deallocate(v13, v12, v17);
    throw;
  }
  v14 = (char *)*a1;
  if ( *a1 )
  {
    v10 = (const struct std::nothrow_t *)((_BYTE *)a1[2] - v14);
    if ( (unsigned __int64)v10 < 0x1000 )
    {
LABEL_21:
      operator delete(v14, v10);
      goto LABEL_22;
    }
    v10 = (const struct std::nothrow_t *)((char *)v10 + 39);
    v15 = (char *)*((_QWORD *)v14 - 1);
    v11 = (char *)(v14 - v15);
    if ( (unsigned __int64)(v11 - 8) <= 0x1F )
    {
      v14 = v15;
      goto LABEL_21;
    }
LABEL_23:
    _o__invalid_parameter_noinfo_noreturn(v11, v10);
    __debugbreak();
    goto LABEL_24;
  }
LABEL_22:
  *a1 = v12;
  a1[1] = (char *)v12 + 25 * a2;
  result = (char *)v12 + v8;
  a1[2] = (char *)v12 + v8;
  return result;
}

```

## disassembly

```asm
0x18002cad8  mov     [rsp+arg_0], rbx
0x18002cadd  mov     [rsp+arg_10], r8
0x18002cae2  push    rsi
0x18002cae3  push    rdi
0x18002cae4  push    r13
0x18002cae6  push    r14
0x18002cae8  push    r15
0x18002caea  sub     rsp, 20h
0x18002caee  mov     r14, rdx
0x18002caf1  mov     rdi, rcx
0x18002caf4  mov     r8, 0A3D70A3D70A3D70h
0x18002cafe  cmp     rdx, r8
0x18002cb01  ja      loc_18002CC52
0x18002cb07  mov     r15, [rcx+8]
0x18002cb0b  sub     r15, [rcx]
0x18002cb0e  mov     r13, 8F5C28F5C28F5C29h
0x18002cb18  imul    r15, r13
0x18002cb1c  mov     rcx, [rcx+10h]
0x18002cb20  sub     rcx, [rdi]
0x18002cb23  imul    rcx, r13
0x18002cb27  mov     rdx, rcx
0x18002cb2a  shr     rdx, 1
0x18002cb2d  mov     rax, r8
0x18002cb30  sub     rax, rdx
0x18002cb33  cmp     rcx, rax
0x18002cb36  ja      loc_18002CC4C
0x18002cb3c  lea     rax, [rdx+rcx]
0x18002cb40  cmp     rax, r14
0x18002cb43  jnb     short loc_18002CB4F
0x18002cb45  mov     rax, r14
0x18002cb48  mov     [rsp+48h+arg_8], rax
0x18002cb4d  jmp     short loc_18002CB5D
0x18002cb4f  mov     [rsp+48h+arg_8], rax
0x18002cb54  cmp     rax, r8
0x18002cb57  ja      loc_18002CC4C
0x18002cb5d  imul    rsi, rax, 19h
0x18002cb61  cmp     rsi, 1000h
0x18002cb68  jb      short loc_18002CB93
0x18002cb6a  lea     rcx, [rsi+27h]; Size
0x18002cb6e  cmp     rcx, rsi
0x18002cb71  jbe     loc_18002CC4C
0x18002cb77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cb7c  test    rax, rax
0x18002cb7f  jz      loc_18002CC3F
0x18002cb85  lea     rbx, [rax+27h]
0x18002cb89  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18002cb8d  mov     [rbx-8], rax
0x18002cb91  jmp     short loc_18002CBA7
0x18002cb93  test    rsi, rsi
0x18002cb96  jz      short loc_18002CBA5
0x18002cb98  mov     rcx, rsi; Size
0x18002cb9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cba0  mov     rbx, rax
0x18002cba3  jmp     short loc_18002CBA7
0x18002cba5  xor     ebx, ebx
0x18002cba7  mov     [rsp+48h+arg_10], rbx
0x18002cbac  imul    rcx, r15, 19h
0x18002cbb0  add     rcx, rbx; void *
0x18002cbb3  mov     rax, r14
0x18002cbb6  sub     rax, r15
0x18002cbb9  jz      short loc_18002CBC6
0x18002cbbb  imul    r8, rax, 19h; Size
0x18002cbbf  xor     edx, edx; Val
0x18002cbc1  call    memset_0
0x18002cbc6  mov     r8, [rdi+8]
0x18002cbca  sub     r8, [rdi]; Size
0x18002cbcd  mov     rdx, [rdi]; Src
0x18002cbd0  mov     rcx, rbx; void *
0x18002cbd3  call    memmove_0
0x18002cbd8  nop
0x18002cbd9  mov     rcx, [rdi]
0x18002cbdc  test    rcx, rcx
0x18002cbdf  jz      short loc_18002CC16
0x18002cbe1  mov     rax, [rdi+10h]
0x18002cbe5  sub     rax, rcx
0x18002cbe8  imul    rax, r13
0x18002cbec  imul    rdx, rax, 19h
0x18002cbf0  cmp     rdx, 1000h
0x18002cbf7  jb      short loc_18002CC11
0x18002cbf9  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18002cbfd  mov     r8, [rcx-8]
0x18002cc01  sub     rcx, r8
0x18002cc04  lea     rax, [rcx-8]
0x18002cc08  cmp     rax, 1Fh
0x18002cc0c  ja      short loc_18002CC3F
0x18002cc0e  mov     rcx, r8; void *
0x18002cc11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cc16  mov     [rdi], rbx
0x18002cc19  imul    rax, r14, 19h
0x18002cc1d  add     rax, rbx
0x18002cc20  mov     [rdi+8], rax
0x18002cc24  lea     rax, [rsi+rbx]
0x18002cc28  mov     [rdi+10h], rax
0x18002cc2c  mov     rbx, [rsp+48h+arg_0]
0x18002cc31  add     rsp, 20h
0x18002cc35  pop     r15
0x18002cc37  pop     r14
0x18002cc39  pop     r13
0x18002cc3b  pop     rdi
0x18002cc3c  pop     rsi
0x18002cc3d  retn
0x18002cc3f  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18002cc46  nop     dword ptr [rax+rax+00h]
0x18002cc4b  int     3; Trap to Debugger
0x18002cc4c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18002cc52  call    ?_Xlength@?$vector@UBTHLE_PREPAIRING_ENTRY@@V?$allocator@UBTHLE_PREPAIRING_ENTRY@@@std@@@std@@CAXXZ; std::vector<BTHLE_PREPAIRING_ENTRY>::_Xlength(void)
```
