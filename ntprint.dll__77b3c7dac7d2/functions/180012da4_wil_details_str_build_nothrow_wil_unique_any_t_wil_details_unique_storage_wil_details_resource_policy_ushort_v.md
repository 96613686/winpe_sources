# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x180012da4`
- end: `0x180012f2b`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180012f34`

## callees

- `0x180007478`
- `0x180008520`
- `0x180012da4`
- `0x180012ff8`
- `0x180013018`
- `0x180015d20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012dff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012dff`

## string_xrefs

- `0x180012eb3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012ed8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012f19`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        const char *a4)
{
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rdi
  __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // r12
  unsigned __int16 *v12; // rcx
  int v13; // eax
  unsigned int v14; // esi
  int v16; // [rsp+20h] [rbp-20h]
  int v17; // [rsp+20h] [rbp-20h]
  unsigned __int64 *v18; // [rsp+28h] [rbp-18h]
  unsigned int v19; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned __int16 *v21; // [rsp+78h] [rbp+38h] BYREF
  unsigned __int16 *v22; // [rsp+80h] [rbp+40h] BYREF

  v22 = a3;
  v4 = 0;
  v5 = a2 + 64;
  v6 = a2;
  v8 = a2;
  do
  {
    v4 += *(_QWORD *)(v8 + 8);
    v8 += 16;
  }
  while ( v8 != v5 );
  v22 = 0;
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v9 = (unsigned __int16 *)LocalAlloc(0, 2 * v4 + 2);
  if ( v9 )
  {
    *v9 = 0;
    v9[v4] = 0;
  }
  v21 = v9;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v22,
    &v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
  v10 = v22;
  if ( v22 )
  {
    v21 = v22;
    v11 = (__int64)&v22[v4 + 1];
    v12 = v22;
    while ( 1 )
    {
      if ( v6 == v5 )
      {
        v21 = v10;
        v22 = 0;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          a1,
          &v21);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
        return 0;
      }
      if ( *(_QWORD *)v6 )
      {
        v13 = StringCchCopyNExW(
                v12,
                (v11 - (__int64)v12) >> 1,
                *(const unsigned __int16 **)v6,
                *(_QWORD *)(v6 + 8),
                &v21,
                v18,
                v19);
        v14 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x791,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v13,
            v17);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
          return v14;
        }
        v12 = v21;
      }
      v6 += 16;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x788,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)0x8007000ELL,
    v16);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012da4  mov     [rsp-28h+arg_0], rbx
0x180012da9  mov     [rsp-28h+arg_18], rsi
0x180012dae  mov     [rsp-28h+arg_10], r8
0x180012db3  push    rbp
0x180012db4  push    rdi
0x180012db5  push    r12
0x180012db7  push    r14
0x180012db9  push    r15
0x180012dbb  mov     rbp, rsp
0x180012dbe  sub     rsp, 40h
0x180012dc2  xor     esi, esi
0x180012dc4  lea     r14, [rdx+40h]
0x180012dc8  mov     rdi, rdx
0x180012dcb  mov     r15, rcx
0x180012dce  mov     rax, rdx
0x180012dd1  cmp     rdx, r14
0x180012dd4  jz      short loc_180012DE3
0x180012dd6  add     rsi, [rax+8]
0x180012dda  add     rax, 10h
0x180012dde  cmp     rax, r14
0x180012de1  jnz     short loc_180012DD6
0x180012de3  mov     [rbp+arg_10], 0
0x180012deb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180012def  jz      loc_180012F15
0x180012df5  lea     rdx, ds:2[rsi*2]; uBytes
0x180012dfd  xor     ecx, ecx; uFlags
0x180012dff  call    cs:__imp_LocalAlloc
0x180012e05  test    rax, rax
0x180012e08  jz      short loc_180012E13
0x180012e0a  xor     ecx, ecx
0x180012e0c  mov     [rax], cx
0x180012e0f  mov     [rax+rsi*2], cx
0x180012e13  lea     rdx, [rbp+arg_8]
0x180012e17  mov     [rbp+arg_8], rax
0x180012e1b  lea     rcx, [rbp+arg_10]
0x180012e1f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180012e24  lea     rcx, [rbp+arg_8]
0x180012e28  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012e2d  mov     rbx, [rbp+arg_10]
0x180012e31  test    rbx, rbx
0x180012e34  jz      loc_180012ED4
0x180012e3a  lea     r12, [rbx+2]
0x180012e3e  mov     [rbp+arg_8], rbx
0x180012e42  lea     r12, [r12+rsi*2]
0x180012e46  mov     rcx, rbx
0x180012e49  jmp     short loc_180012E7C
0x180012e4b  mov     r8, [rdi]; unsigned __int16 *
0x180012e4e  test    r8, r8
0x180012e51  jz      short loc_180012E78
0x180012e53  mov     r9, [rdi+8]; unsigned __int64
0x180012e57  lea     rax, [rbp+arg_8]
0x180012e5b  mov     rdx, r12
0x180012e5e  mov     [rsp+40h+var_20], rax; int
0x180012e63  sub     rdx, rcx
0x180012e66  sar     rdx, 1; unsigned __int64
0x180012e69  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180012e6e  mov     esi, eax
0x180012e70  test    eax, eax
0x180012e72  js      short loc_180012EAF
0x180012e74  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012e78  add     rdi, 10h
0x180012e7c  cmp     rdi, r14
0x180012e7f  jnz     short loc_180012E4B
0x180012e81  lea     rdx, [rbp+arg_8]
0x180012e85  mov     [rbp+arg_8], rbx
0x180012e89  mov     rcx, r15
0x180012e8c  mov     [rbp+arg_10], 0
0x180012e94  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180012e99  lea     rcx, [rbp+arg_8]
0x180012e9d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012ea2  lea     rcx, [rbp+arg_10]
0x180012ea6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012eab  xor     eax, eax
0x180012ead  jmp     short loc_180012EFC
0x180012eaf  mov     rcx, [rbp+28h]; this
0x180012eb3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012eba  mov     r9d, esi; char *
0x180012ebd  mov     edx, 791h; void *
0x180012ec2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ec7  lea     rcx, [rbp+arg_10]
0x180012ecb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012ed0  mov     eax, esi
0x180012ed2  jmp     short loc_180012EFC
0x180012ed4  mov     rcx, [rbp+28h]; this
0x180012ed8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012edf  mov     ebx, 8007000Eh
0x180012ee4  mov     edx, 788h; void *
0x180012ee9  mov     r9d, ebx; char *
0x180012eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ef1  lea     rcx, [rbp+arg_10]
0x180012ef5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012efa  mov     eax, ebx
0x180012efc  lea     r11, [rsp+40h+var_s0]
0x180012f01  mov     rbx, [r11+30h]
0x180012f05  mov     rsi, [r11+48h]
0x180012f09  mov     rsp, r11
0x180012f0c  pop     r15
0x180012f0e  pop     r14
0x180012f10  pop     r12
0x180012f12  pop     rdi
0x180012f13  pop     rbp
0x180012f14  retn
0x180012f15  mov     rcx, [rbp+28h]; this
0x180012f19  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012f20  mov     edx, 0F89h; void *
0x180012f25  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
