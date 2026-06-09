# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x180003be0`
- end: `0x180003d00`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `288`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003030`

## callees

- `0x180001e80`
- `0x180003be0`
- `0x180009f98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cdc`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  __int64 v6; // rax
  char *v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // r14
  char *v10; // rax
  char *v11; // rdi
  rsize_t v12; // rbx
  void *v13; // rbp
  DWORD LastError; // ebx
  __int64 result; // rax
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
  if ( a2 )
  {
    v6 = a3;
    v7 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v6 = 0x7FFFFFFF;
    for ( ; v6; --v6 )
    {
      if ( !*(_WORD *)v7 )
        break;
      v7 += 2;
    }
    v8 = (v7 - a2) >> 1;
  }
  else
  {
    v8 = a3;
  }
  if ( a3 == -1 )
    a3 = v8;
  v9 = 2 * a3;
  v10 = (char *)CoTaskMemAlloc(2 * a3 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v8;
      memcpy_s(v10, v9 + 2, a2, v12);
      *(_WORD *)&v11[v12] = 0;
    }
    else
    {
      *(_WORD *)v10 = 0;
    }
    *(_WORD *)&v11[v9] = 0;
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
0x180003be0  push    rbp
0x180003be2  push    rsi
0x180003be3  sub     rsp, 38h
0x180003be7  mov     rbp, rdx
0x180003bea  mov     rsi, rcx
0x180003bed  test    rdx, rdx
0x180003bf0  jnz     short loc_180003C03
0x180003bf2  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180003bf6  jnz     short loc_180003C03
0x180003bf8  mov     rcx, [rsp+48h]; this
0x180003bfd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180003c03  mov     [rsp+48h+arg_0], rbx
0x180003c08  mov     [rsp+48h+arg_8], rdi
0x180003c0d  mov     [rsp+48h+arg_10], r14
0x180003c12  mov     [rsp+48h+var_18], r15
0x180003c17  test    rbp, rbp
0x180003c1a  jz      short loc_180003C4B
0x180003c1c  mov     ecx, 7FFFFFFFh
0x180003c21  mov     rax, r8
0x180003c24  cmp     r8, rcx
0x180003c27  mov     rbx, rbp
0x180003c2a  cmovnb  rax, rcx
0x180003c2e  test    rax, rax
0x180003c31  jz      short loc_180003C43
0x180003c33  cmp     word ptr [rbx], 0
0x180003c37  jz      short loc_180003C43
0x180003c39  add     rbx, 2
0x180003c3d  sub     rax, 1
0x180003c41  jnz     short loc_180003C33
0x180003c43  sub     rbx, rbp
0x180003c46  sar     rbx, 1
0x180003c49  jmp     short loc_180003C4E
0x180003c4b  mov     rbx, r8
0x180003c4e  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180003c52  cmovz   r8, rbx
0x180003c56  lea     r14, [r8+r8]
0x180003c5a  lea     rcx, [r14+2]; cb
0x180003c5e  call    cs:__imp_CoTaskMemAlloc
0x180003c64  mov     rdi, rax
0x180003c67  test    rax, rax
0x180003c6a  jz      short loc_180003C9A
0x180003c6c  test    rbp, rbp
0x180003c6f  jz      short loc_180003C8E
0x180003c71  add     rbx, rbx
0x180003c74  lea     rdx, [r14+2]; DestinationSize
0x180003c78  mov     r9, rbx; SourceSize
0x180003c7b  mov     r8, rbp; Source
0x180003c7e  mov     rcx, rax; Destination
0x180003c81  call    memcpy_s
0x180003c86  xor     ecx, ecx
0x180003c88  mov     [rbx+rdi], cx
0x180003c8c  jmp     short loc_180003C93
0x180003c8e  xor     eax, eax
0x180003c90  mov     [rdi], ax
0x180003c93  xor     eax, eax
0x180003c95  mov     [r14+rdi], ax
0x180003c9a  mov     r15, [rsp+48h+var_18]
0x180003c9f  lea     rax, [rsp+48h+var_28]
0x180003ca4  mov     r14, [rsp+48h+arg_10]
0x180003ca9  cmp     rsi, rax
0x180003cac  jz      short loc_180003CD4
0x180003cae  mov     rbp, [rsi]
0x180003cb1  test    rbp, rbp
0x180003cb4  jz      short loc_180003CCF
0x180003cb6  call    cs:__imp_GetLastError
0x180003cbc  mov     rcx, rbp; pv
0x180003cbf  mov     ebx, eax
0x180003cc1  call    cs:__imp_CoTaskMemFree
0x180003cc7  mov     ecx, ebx; dwErrCode
0x180003cc9  call    cs:__imp_SetLastError
0x180003ccf  mov     [rsi], rdi
0x180003cd2  jmp     short loc_180003CE2
0x180003cd4  test    rdi, rdi
0x180003cd7  jz      short loc_180003CE2
0x180003cd9  mov     rcx, rdi; pv
0x180003cdc  call    cs:__imp_CoTaskMemFree
0x180003ce2  mov     rdi, [rsp+48h+arg_8]
0x180003ce7  xor     eax, eax
0x180003ce9  cmp     [rsi], rax
0x180003cec  mov     ecx, 8007000Eh
0x180003cf1  mov     rbx, [rsp+48h+arg_0]
0x180003cf6  cmovz   eax, ecx
0x180003cf9  add     rsp, 38h
0x180003cfd  pop     rsi
0x180003cfe  pop     rbp
0x180003cff  retn
```
