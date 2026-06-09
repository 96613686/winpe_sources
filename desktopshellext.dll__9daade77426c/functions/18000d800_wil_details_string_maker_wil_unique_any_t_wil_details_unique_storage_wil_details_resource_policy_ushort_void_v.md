# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18000d800`
- end: `0x18000d945`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800241c8`
- `0x18003b184`

## callees

- `0x18000d800`
- `0x180011a2c`
- `0x18002d848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d927`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d93a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d84c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d84c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d88c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d88c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d932`

## string_xrefs

- `0x18000d8c2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  __int64 v6; // rbx
  __int64 v7; // r15
  char *v8; // rax
  char *v9; // r14
  __int64 result; // rax
  void *v11; // rdi
  __int64 v12; // rax
  char *v13; // rbx
  rsize_t v14; // rbx
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  if ( a2 )
  {
    v12 = a3;
    v13 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v12 = 0x7FFFFFFF;
    for ( ; v12; --v12 )
    {
      if ( !*(_WORD *)v13 )
        break;
      v13 += 2;
    }
    v6 = (v13 - a2) >> 1;
  }
  else
  {
    v6 = a3;
  }
  if ( a3 == -1 )
    a3 = v6;
  v7 = 2 * a3;
  v8 = (char *)CoTaskMemAlloc(2 * a3 + 2);
  v9 = v8;
  if ( v8 )
  {
    if ( a2 )
    {
      v14 = 2 * v6;
      memcpy_s_1(v8, v7 + 2, a2, v14);
      *(_WORD *)&v9[v14] = 0;
    }
    else
    {
      *(_WORD *)v8 = 0;
    }
    *(_WORD *)&v9[v7] = 0;
  }
  if ( a1 == &v16 )
  {
    if ( v9 )
      CoTaskMemFree(v9);
  }
  else
  {
    v11 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v11);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v9;
  }
  result = 0;
  if ( !*(_QWORD *)a1 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x18000d800  push    rsi
0x18000d802  push    rdi
0x18000d803  sub     rsp, 38h
0x18000d807  mov     rdi, rdx
0x18000d80a  mov     rsi, rcx
0x18000d80d  test    rdx, rdx
0x18000d810  jnz     short loc_18000D81C
0x18000d812  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000d816  jz      loc_18000D8BD
0x18000d81c  mov     [rsp+48h+arg_0], rbx
0x18000d821  mov     [rsp+48h+arg_8], rbp
0x18000d826  mov     [rsp+48h+arg_10], r14
0x18000d82b  mov     [rsp+48h+var_18], r15
0x18000d830  test    rdi, rdi
0x18000d833  jnz     loc_18000D8D4
0x18000d839  mov     rbx, r8
0x18000d83c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000d840  cmovz   r8, rbx
0x18000d844  lea     r15, [r8+r8]
0x18000d848  lea     rcx, [r15+2]; cb
0x18000d84c  call    cs:__imp_CoTaskMemAlloc
0x18000d852  mov     r14, rax
0x18000d855  test    rax, rax
0x18000d858  jz      short loc_18000D870
0x18000d85a  test    rdi, rdi
0x18000d85d  jnz     loc_18000D906
0x18000d863  xor     eax, eax
0x18000d865  mov     [r14], ax
0x18000d869  xor     eax, eax
0x18000d86b  mov     [r15+r14], ax
0x18000d870  mov     r15, [rsp+48h+var_18]
0x18000d875  lea     rax, [rsp+48h+var_28]
0x18000d87a  mov     rbp, [rsp+48h+arg_8]
0x18000d87f  cmp     rsi, rax
0x18000d882  jnz     short loc_18000D8B0
0x18000d884  test    r14, r14
0x18000d887  jz      short loc_18000D892
0x18000d889  mov     rcx, r14; pv
0x18000d88c  call    cs:__imp_CoTaskMemFree
0x18000d892  mov     r14, [rsp+48h+arg_10]
0x18000d897  xor     eax, eax
0x18000d899  cmp     [rsi], rax
0x18000d89c  mov     ecx, 8007000Eh
0x18000d8a1  mov     rbx, [rsp+48h+arg_0]
0x18000d8a6  cmovz   eax, ecx
0x18000d8a9  add     rsp, 38h
0x18000d8ad  pop     rdi
0x18000d8ae  pop     rsi
0x18000d8af  retn
0x18000d8b0  mov     rdi, [rsi]
0x18000d8b3  test    rdi, rdi
0x18000d8b6  jnz     short loc_18000D927
0x18000d8b8  mov     [rsi], r14
0x18000d8bb  jmp     short loc_18000D892
0x18000d8bd  mov     rcx, [rsp+48h]; this
0x18000d8c2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d8c9  mov     edx, 0F89h; void *
0x18000d8ce  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d8d4  mov     ecx, 7FFFFFFFh
0x18000d8d9  mov     rax, r8
0x18000d8dc  cmp     r8, rcx
0x18000d8df  mov     rbx, rdi
0x18000d8e2  cmovnb  rax, rcx
0x18000d8e6  test    rax, rax
0x18000d8e9  jz      short loc_18000D8FB
0x18000d8eb  cmp     word ptr [rbx], 0
0x18000d8ef  jz      short loc_18000D8FB
0x18000d8f1  add     rbx, 2
0x18000d8f5  sub     rax, 1
0x18000d8f9  jnz     short loc_18000D8EB
0x18000d8fb  sub     rbx, rdi
0x18000d8fe  sar     rbx, 1
0x18000d901  jmp     loc_18000D83C
0x18000d906  add     rbx, rbx
0x18000d909  lea     rdx, [r15+2]; DestinationSize
0x18000d90d  mov     r9, rbx; SourceSize
0x18000d910  mov     r8, rdi; Source
0x18000d913  mov     rcx, r14; Destination
0x18000d916  call    memcpy_s_1
0x18000d91b  xor     ecx, ecx
0x18000d91d  mov     [rbx+r14], cx
0x18000d922  jmp     loc_18000D869
0x18000d927  call    cs:__imp_GetLastError
0x18000d92d  mov     rcx, rdi; pv
0x18000d930  mov     ebx, eax
0x18000d932  call    cs:__imp_CoTaskMemFree
0x18000d938  mov     ecx, ebx; dwErrCode
0x18000d93a  call    cs:__imp_SetLastError
0x18000d940  jmp     loc_18000D8B8
```
