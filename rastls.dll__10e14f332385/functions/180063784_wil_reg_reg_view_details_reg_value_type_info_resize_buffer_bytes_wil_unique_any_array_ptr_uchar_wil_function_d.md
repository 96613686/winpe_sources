# wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &,ulong)

- ea: `0x180063784`
- end: `0x180063839`
- name: `?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@4@K@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006241c`

## callees

- `0x18002b7b4`
- `0x18003623c`
- `0x180063750`
- `0x180063784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800637a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800637a3`

## string_xrefs

- `0x1800637bb`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

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
0x180063784  mov     [rsp+arg_0], rbx
0x180063789  mov     [rsp+arg_8], rsi
0x18006378e  push    rdi
0x18006378f  sub     rsp, 30h
0x180063793  mov     rbx, rcx
0x180063796  mov     [rsp+38h+var_10], 0
0x18006379f  mov     ecx, edx; cb
0x1800637a1  mov     esi, edx
0x1800637a3  call    cs:__imp_CoTaskMemAlloc
0x1800637a9  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800637ae  mov     rdi, rax
0x1800637b1  test    rax, rax
0x1800637b4  jnz     short loc_1800637D6
0x1800637b6  mov     rcx, [rsp+38h]; this
0x1800637bb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800637c2  mov     ebx, 8007000Eh
0x1800637c7  mov     edx, 345h; void *
0x1800637cc  mov     r9d, ebx; char *
0x1800637cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800637d4  jmp     short loc_18006381D
0x1800637d6  mov     r8, [rbx+8]
0x1800637da  mov     rcx, rdi; void *
0x1800637dd  mov     rdx, [rbx]; Src
0x1800637e0  cmp     r8, rsi
0x1800637e3  mov     [rsp+38h+var_10], rsi
0x1800637e8  cmovnb  r8, rsi; Size
0x1800637ec  call    memcpy_0
0x1800637f1  lea     rax, [rsp+38h+var_18]
0x1800637f6  cmp     rbx, rax
0x1800637f9  jz      short loc_18006381B
0x1800637fb  mov     rcx, rbx
0x1800637fe  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180063803  mov     rax, [rbx]
0x180063806  mov     rcx, [rbx+8]
0x18006380a  mov     qword ptr [rsp+38h+var_18], rax
0x18006380f  mov     [rsp+38h+var_10], rcx
0x180063814  mov     [rbx], rdi
0x180063817  mov     [rbx+8], rsi
0x18006381b  xor     ebx, ebx
0x18006381d  lea     rcx, [rsp+38h+var_18]
0x180063822  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180063827  mov     rsi, [rsp+38h+arg_8]
0x18006382c  mov     eax, ebx
0x18006382e  mov     rbx, [rsp+38h+arg_0]
0x180063833  add     rsp, 30h
0x180063837  pop     rdi
0x180063838  retn
```
