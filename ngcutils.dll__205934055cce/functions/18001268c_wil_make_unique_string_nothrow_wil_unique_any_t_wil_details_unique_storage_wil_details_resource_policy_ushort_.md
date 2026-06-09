# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001268c`
- end: `0x18001277f`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001290c`

## callees

- `0x180003b36`
- `0x180003bc8`
- `0x1800052f5`
- `0x180007a5c`
- `0x18001268c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012732`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800126fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800126fb`

## string_xrefs

- `0x18001276d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno(v14, v13, v15) = 34;
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
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x18001268c  push    rbx
0x18001268e  push    rbp
0x18001268f  push    rsi
0x180012690  push    rdi
0x180012691  push    r12
0x180012693  push    r14
0x180012695  push    r15
0x180012697  sub     rsp, 20h
0x18001269b  xor     r12d, r12d
0x18001269e  mov     rbx, r8
0x1800126a1  mov     rbp, rdx
0x1800126a4  mov     r15, rcx
0x1800126a7  test    rdx, rdx
0x1800126aa  jnz     short loc_1800126BB
0x1800126ac  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800126b0  jz      loc_180012768
0x1800126b6  mov     rdi, rbx
0x1800126b9  jmp     short loc_1800126F0
0x1800126bb  mov     ecx, 7FFFFFFFh
0x1800126c0  mov     rax, rbx
0x1800126c3  cmp     rbx, rcx
0x1800126c6  mov     rdi, rbp
0x1800126c9  cmovnb  rax, rcx
0x1800126cd  test    rax, rax
0x1800126d0  jz      short loc_1800126E2
0x1800126d2  cmp     [rdi], r12w
0x1800126d6  jz      short loc_1800126E2
0x1800126d8  add     rdi, 2
0x1800126dc  sub     rax, 1
0x1800126e0  jnz     short loc_1800126D2
0x1800126e2  sub     rdi, rbp
0x1800126e5  sar     rdi, 1
0x1800126e8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800126ec  cmovz   rbx, rdi
0x1800126f0  lea     r14, ds:2[rbx*2]
0x1800126f8  mov     rcx, r14; cb
0x1800126fb  call    cs:__imp_CoTaskMemAlloc
0x180012701  mov     rsi, rax
0x180012704  test    rax, rax
0x180012707  jz      short loc_180012753
0x180012709  test    rbp, rbp
0x18001270c  jz      short loc_18001274A
0x18001270e  add     rdi, rdi
0x180012711  jz      short loc_180012743
0x180012713  mov     rcx, rax; void *
0x180012716  cmp     r14, rdi
0x180012719  jb      short loc_180012728
0x18001271b  mov     r8, rdi; Size
0x18001271e  mov     rdx, rbp; Src
0x180012721  call    memcpy_0
0x180012726  jmp     short loc_180012743
0x180012728  mov     r8, r14; Size
0x18001272b  xor     edx, edx; Val
0x18001272d  call    memset_0
0x180012732  call    cs:__imp__o__errno
0x180012738  mov     dword ptr [rax], 22h ; '"'
0x18001273e  call    _invalid_parameter_noinfo
0x180012743  mov     [rdi+rsi], r12w
0x180012748  jmp     short loc_18001274E
0x18001274a  mov     [rax], r12w
0x18001274e  mov     [rsi+rbx*2], r12w
0x180012753  mov     [r15], rsi
0x180012756  mov     rax, r15
0x180012759  add     rsp, 20h
0x18001275d  pop     r15
0x18001275f  pop     r14
0x180012761  pop     r12
0x180012763  pop     rdi
0x180012764  pop     rsi
0x180012765  pop     rbp
0x180012766  pop     rbx
0x180012767  retn
0x180012768  mov     rcx, [rsp+58h]; this
0x18001276d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012774  mov     edx, 0F89h; void *
0x180012779  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
