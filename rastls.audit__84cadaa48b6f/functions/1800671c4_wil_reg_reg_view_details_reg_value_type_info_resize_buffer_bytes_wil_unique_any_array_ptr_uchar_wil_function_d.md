# wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &,ulong)

- ea: `0x1800671c4`
- end: `0x180067280`
- name: `?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@4@K@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065da0`

## callees

- `0x18002dc28`
- `0x180038e4c`
- `0x180067188`
- `0x1800671c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800671e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800671e3`

## string_xrefs

- `0x180067201`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(__int64 a1, unsigned int a2)
{
  size_t v3; // rsi
  void *v4; // rax
  void *v5; // rdi
  unsigned int v6; // ebx
  size_t v7; // r8
  const void *v8; // rdx
  size_t v9; // rcx
  int v11[2]; // [rsp+20h] [rbp-18h] BYREF
  size_t v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v12 = 0;
  v3 = a2;
  v4 = CoTaskMemAlloc(a2);
  *(_QWORD *)v11 = v4;
  v5 = v4;
  if ( v4 )
  {
    v7 = *(_QWORD *)(a1 + 8);
    v8 = *(const void **)a1;
    v12 = v3;
    if ( v7 >= v3 )
      v7 = v3;
    memcpy_0(v4, v8, v7);
    if ( (int *)a1 != v11 )
    {
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(a1);
      v9 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)v11 = *(_QWORD *)a1;
      v12 = v9;
      *(_QWORD *)a1 = v5;
      *(_QWORD *)(a1 + 8) = v3;
    }
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x345,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)0x8007000ELL,
      0);
  }
  wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v11);
  return v6;
}

```

## disassembly

```asm
0x1800671c4  mov     [rsp+arg_0], rbx
0x1800671c9  mov     [rsp+arg_8], rsi
0x1800671ce  push    rdi
0x1800671cf  sub     rsp, 30h
0x1800671d3  mov     rbx, rcx
0x1800671d6  mov     [rsp+38h+var_10], 0
0x1800671df  mov     ecx, edx; cb
0x1800671e1  mov     esi, edx
0x1800671e3  call    cs:__imp_CoTaskMemAlloc
0x1800671ea  nop     dword ptr [rax+rax+00h]
0x1800671ef  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800671f4  mov     rdi, rax
0x1800671f7  test    rax, rax
0x1800671fa  jnz     short loc_18006721C
0x1800671fc  mov     rcx, [rsp+38h]; this
0x180067201  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180067208  mov     ebx, 8007000Eh
0x18006720d  mov     edx, 345h; void *
0x180067212  mov     r9d, ebx; char *
0x180067215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006721a  jmp     short loc_180067263
0x18006721c  mov     r8, [rbx+8]
0x180067220  mov     rcx, rdi; void *
0x180067223  mov     rdx, [rbx]; Src
0x180067226  cmp     r8, rsi
0x180067229  mov     [rsp+38h+var_10], rsi
0x18006722e  cmovnb  r8, rsi; Size
0x180067232  call    memcpy_0
0x180067237  lea     rax, [rsp+38h+var_18]
0x18006723c  cmp     rbx, rax
0x18006723f  jz      short loc_180067261
0x180067241  mov     rcx, rbx
0x180067244  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180067249  mov     rax, [rbx]
0x18006724c  mov     rcx, [rbx+8]
0x180067250  mov     qword ptr [rsp+38h+var_18], rax
0x180067255  mov     [rsp+38h+var_10], rcx
0x18006725a  mov     [rbx], rdi
0x18006725d  mov     [rbx+8], rsi
0x180067261  xor     ebx, ebx
0x180067263  lea     rcx, [rsp+38h+var_18]
0x180067268  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18006726d  mov     rsi, [rsp+38h+arg_8]
0x180067272  mov     eax, ebx
0x180067274  mov     rbx, [rsp+38h+arg_0]
0x180067279  add     rsp, 30h
0x18006727d  pop     rdi
0x18006727e  retn
```
