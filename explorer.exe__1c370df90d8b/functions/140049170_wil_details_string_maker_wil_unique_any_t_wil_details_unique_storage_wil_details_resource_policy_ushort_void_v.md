# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x140049170`
- end: `0x1400492e2`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `370`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14009562c`
- `0x1400a18d8`
- `0x14010cf6c`

## callees

- `0x140049170`
- `0x140097920`
- `0x140104bd2`
- `0x140104cc8`
- `0x140104ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400492ae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400492ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400492d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400492d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400492c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400492c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004929c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400492cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004929c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400492cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400491e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400491e9`

## string_xrefs

- `0x140049282`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // r15
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  __int64 result; // rax
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v9 = (v8 - a2) >> 1;
  }
  else
  {
    v9 = a3;
  }
  if ( a3 == -1 )
    v4 = v9;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v9;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  if ( a1 == &v16 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    v13 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v13);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  result = 0;
  if ( !*(_QWORD *)a1 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x140049170  push    rbp
0x140049172  push    r14
0x140049174  push    r15
0x140049176  sub     rsp, 30h
0x14004917a  mov     r15, r8
0x14004917d  mov     rbp, rdx
0x140049180  mov     r14, rcx
0x140049183  test    rdx, rdx
0x140049186  jz      loc_140049273
0x14004918c  mov     [rsp+48h+arg_0], rbx
0x140049191  mov     [rsp+48h+arg_8], rsi
0x140049196  mov     [rsp+48h+arg_10], rdi
0x14004919b  test    rbp, rbp
0x14004919e  jz      loc_140049264
0x1400491a4  mov     ecx, 7FFFFFFFh
0x1400491a9  mov     rax, r15
0x1400491ac  cmp     r15, rcx
0x1400491af  mov     rbx, rbp
0x1400491b2  cmovnb  rax, rcx
0x1400491b6  test    rax, rax
0x1400491b9  jz      short loc_1400491D0
0x1400491bb  nop     dword ptr [rax+rax+00h]
0x1400491c0  cmp     word ptr [rbx], 0
0x1400491c4  jz      short loc_1400491D0
0x1400491c6  add     rbx, 2
0x1400491ca  sub     rax, 1
0x1400491ce  jnz     short loc_1400491C0
0x1400491d0  sub     rbx, rbp
0x1400491d3  sar     rbx, 1
0x1400491d6  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400491da  cmovz   r15, rbx
0x1400491de  lea     rsi, ds:2[r15*2]
0x1400491e6  mov     rcx, rsi; cb
0x1400491e9  call    cs:__imp_CoTaskMemAlloc
0x1400491ef  mov     rdi, rax
0x1400491f2  test    rax, rax
0x1400491f5  jz      short loc_140049225
0x1400491f7  test    rbp, rbp
0x1400491fa  jz      short loc_14004926C
0x1400491fc  add     rbx, rbx
0x1400491ff  jz      short loc_140049218
0x140049201  mov     rcx, rax; void *
0x140049204  cmp     rsi, rbx
0x140049207  jb      loc_1400492A4
0x14004920d  mov     r8, rbx; Size
0x140049210  mov     rdx, rbp; Src
0x140049213  call    memcpy_0
0x140049218  xor     eax, eax
0x14004921a  mov     [rbx+rdi], ax
0x14004921e  xor     eax, eax
0x140049220  mov     [rdi+r15*2], ax
0x140049225  lea     rax, [rsp+48h+var_28]
0x14004922a  cmp     r14, rax
0x14004922d  jz      short loc_140049294
0x14004922f  mov     rsi, [r14]
0x140049232  test    rsi, rsi
0x140049235  jnz     loc_1400492C4
0x14004923b  mov     [r14], rdi
0x14004923e  mov     rdi, [rsp+48h+arg_10]
0x140049243  xor     eax, eax
0x140049245  cmp     [r14], rax
0x140049248  mov     ecx, 8007000Eh
0x14004924d  mov     rsi, [rsp+48h+arg_8]
0x140049252  mov     rbx, [rsp+48h+arg_0]
0x140049257  cmovz   eax, ecx
0x14004925a  add     rsp, 30h
0x14004925e  pop     r15
0x140049260  pop     r14
0x140049262  pop     rbp
0x140049263  retn
0x140049264  mov     rbx, r15
0x140049267  jmp     loc_1400491D6
0x14004926c  xor     eax, eax
0x14004926e  mov     [rdi], ax
0x140049271  jmp     short loc_14004921E
0x140049273  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140049277  jnz     loc_14004918C
0x14004927d  mov     rcx, [rsp+48h]; this
0x140049282  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140049289  mov     edx, 0F89h; void *
0x14004928e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140049294  test    rdi, rdi
0x140049297  jz      short loc_14004923E
0x140049299  mov     rcx, rdi; pv
0x14004929c  call    cs:__imp_CoTaskMemFree
0x1400492a2  jmp     short loc_14004923E
0x1400492a4  mov     r8, rsi; Size
0x1400492a7  xor     edx, edx; Val
0x1400492a9  call    memset_0
0x1400492ae  call    cs:__imp__o__errno
0x1400492b4  mov     dword ptr [rax], 22h ; '"'
0x1400492ba  call    _invalid_parameter_noinfo
0x1400492bf  jmp     loc_140049218
0x1400492c4  call    cs:__imp_GetLastError
0x1400492ca  mov     rcx, rsi; pv
0x1400492cd  mov     ebx, eax
0x1400492cf  call    cs:__imp_CoTaskMemFree
0x1400492d5  mov     ecx, ebx; dwErrCode
0x1400492d7  call    cs:__imp_SetLastError
0x1400492dd  jmp     loc_14004923B
```
