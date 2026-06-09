# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x1400439e0`
- end: `0x140043b77`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `407`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400a7844`
- `0x1400a7ca0`
- `0x140117234`

## callees

- `0x1400439e0`
- `0x14009cf08`
- `0x14010ec86`
- `0x14010ed78`
- `0x14010ed90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140043b2b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140043b2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140043b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140043b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043b47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140043a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140043a59`

## string_xrefs

- `0x140043af9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1400439e0  push    rbp
0x1400439e2  push    r14
0x1400439e4  push    r15
0x1400439e6  sub     rsp, 30h
0x1400439ea  mov     r15, r8
0x1400439ed  mov     rbp, rdx
0x1400439f0  mov     r14, rcx
0x1400439f3  test    rdx, rdx
0x1400439f6  jz      loc_140043AEA
0x1400439fc  mov     [rsp+48h+arg_0], rbx
0x140043a01  mov     [rsp+48h+arg_8], rsi
0x140043a06  mov     [rsp+48h+arg_10], rdi
0x140043a0b  test    rbp, rbp
0x140043a0e  jz      loc_140043ADB
0x140043a14  mov     ecx, 7FFFFFFFh
0x140043a19  mov     rax, r15
0x140043a1c  cmp     r15, rcx
0x140043a1f  mov     rbx, rbp
0x140043a22  cmovnb  rax, rcx
0x140043a26  test    rax, rax
0x140043a29  jz      short loc_140043A40
0x140043a2b  nop     dword ptr [rax+rax+00h]
0x140043a30  cmp     word ptr [rbx], 0
0x140043a34  jz      short loc_140043A40
0x140043a36  add     rbx, 2
0x140043a3a  sub     rax, 1
0x140043a3e  jnz     short loc_140043A30
0x140043a40  sub     rbx, rbp
0x140043a43  sar     rbx, 1
0x140043a46  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140043a4a  cmovz   r15, rbx
0x140043a4e  lea     rsi, ds:2[r15*2]
0x140043a56  mov     rcx, rsi; cb
0x140043a59  call    cs:__imp_CoTaskMemAlloc
0x140043a60  nop     dword ptr [rax+rax+00h]
0x140043a65  mov     rdi, rax
0x140043a68  test    rax, rax
0x140043a6b  jz      short loc_140043A9B
0x140043a6d  test    rbp, rbp
0x140043a70  jz      short loc_140043AE3
0x140043a72  add     rbx, rbx
0x140043a75  jz      short loc_140043A8E
0x140043a77  mov     rcx, rax; void *
0x140043a7a  cmp     rsi, rbx
0x140043a7d  jb      loc_140043B21
0x140043a83  mov     r8, rbx; Size
0x140043a86  mov     rdx, rbp; Src
0x140043a89  call    memcpy_0
0x140043a8e  xor     eax, eax
0x140043a90  mov     [rbx+rdi], ax
0x140043a94  xor     eax, eax
0x140043a96  mov     [rdi+r15*2], ax
0x140043a9b  lea     rax, [rsp+48h+var_28]
0x140043aa0  cmp     r14, rax
0x140043aa3  jz      short loc_140043B0B
0x140043aa5  mov     rsi, [r14]
0x140043aa8  test    rsi, rsi
0x140043aab  jnz     loc_140043B47
0x140043ab1  mov     [r14], rdi
0x140043ab4  mov     rdi, [rsp+48h+arg_10]
0x140043ab9  xor     eax, eax
0x140043abb  cmp     [r14], rax
0x140043abe  mov     ecx, 8007000Eh
0x140043ac3  mov     rsi, [rsp+48h+arg_8]
0x140043ac8  mov     rbx, [rsp+48h+arg_0]
0x140043acd  cmovz   eax, ecx
0x140043ad0  add     rsp, 30h
0x140043ad4  pop     r15
0x140043ad6  pop     r14
0x140043ad8  pop     rbp
0x140043ad9  retn
0x140043adb  mov     rbx, r15
0x140043ade  jmp     loc_140043A46
0x140043ae3  xor     eax, eax
0x140043ae5  mov     [rdi], ax
0x140043ae8  jmp     short loc_140043A94
0x140043aea  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140043aee  jnz     loc_1400439FC
0x140043af4  mov     rcx, [rsp+48h]; this
0x140043af9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140043b00  mov     edx, 0F89h; void *
0x140043b05  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140043b0b  test    rdi, rdi
0x140043b0e  jz      short loc_140043AB4
0x140043b10  mov     rcx, rdi; pv
0x140043b13  call    cs:__imp_CoTaskMemFree
0x140043b1a  nop     dword ptr [rax+rax+00h]
0x140043b1f  jmp     short loc_140043AB4
0x140043b21  mov     r8, rsi; Size
0x140043b24  xor     edx, edx; Val
0x140043b26  call    memset_0
0x140043b2b  call    cs:__imp__o__errno
0x140043b32  nop     dword ptr [rax+rax+00h]
0x140043b37  mov     dword ptr [rax], 22h ; '"'
0x140043b3d  call    _invalid_parameter_noinfo
0x140043b42  jmp     loc_140043A8E
0x140043b47  call    cs:__imp_GetLastError
0x140043b4e  nop     dword ptr [rax+rax+00h]
0x140043b53  mov     rcx, rsi; pv
0x140043b56  mov     ebx, eax
0x140043b58  call    cs:__imp_CoTaskMemFree
0x140043b5f  nop     dword ptr [rax+rax+00h]
0x140043b64  mov     ecx, ebx; dwErrCode
0x140043b66  call    cs:__imp_SetLastError
0x140043b6d  nop     dword ptr [rax+rax+00h]
0x140043b72  jmp     loc_140043AB1
```
