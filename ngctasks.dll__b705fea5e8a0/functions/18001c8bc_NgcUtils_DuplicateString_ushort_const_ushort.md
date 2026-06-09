# NgcUtils::DuplicateString(ushort const *,ushort * *)

- ea: `0x18001c8bc`
- end: `0x18001c920`
- name: `?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z`
- size: `100`
- prototype: `__int64 __fastcall(NgcUtils *this, unsigned __int16 *, unsigned __int16 **, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012f0c`

## callees

- `0x18000cc34`
- `0x18000ff9c`
- `0x180010310`
- `0x18001c8bc`

## string_xrefs

- `0x18001c8e5`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::DuplicateString(
        NgcUtils *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        const char *a4)
{
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v9; // [rsp+40h] [rbp+18h] BYREF

  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v9,
    (char *)this,
    0xFFFFFFFFFFFFFFFFuLL,
    a4);
  if ( v9 )
  {
    *(_QWORD *)a2 = v9;
    v5 = 0;
    v9 = 0;
  }
  else
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)0x8007000ELL,
      v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
  return v5;
}

```

## disassembly

```asm
0x18001c8bc  push    rbx; int
0x18001c8be  sub     rsp, 20h
0x18001c8c2  mov     rbx, rdx
0x18001c8c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c8c9  mov     rdx, rcx
0x18001c8cc  lea     rcx, [rsp+28h+arg_10]
0x18001c8d1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001c8d6  mov     rax, [rsp+28h+arg_10]
0x18001c8db  test    rax, rax
0x18001c8de  jnz     short loc_18001C900
0x18001c8e0  mov     rcx, [rsp+28h]; this
0x18001c8e5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c8ec  mov     ebx, 8007000Eh
0x18001c8f1  mov     edx, 0A0h; void *
0x18001c8f6  mov     r9d, ebx; char *
0x18001c8f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8fe  jmp     short loc_18001C90E
0x18001c900  mov     [rbx], rax
0x18001c903  xor     ebx, ebx
0x18001c905  mov     [rsp+28h+arg_10], 0
0x18001c90e  lea     rcx, [rsp+28h+arg_10]
0x18001c913  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c918  mov     eax, ebx
0x18001c91a  add     rsp, 20h
0x18001c91e  pop     rbx
0x18001c91f  retn
```
