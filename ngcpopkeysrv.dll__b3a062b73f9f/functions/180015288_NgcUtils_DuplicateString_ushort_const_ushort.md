# NgcUtils::DuplicateString(ushort const *,ushort * *)

- ea: `0x180015288`
- end: `0x1800152ec`
- name: `?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z`
- size: `100`
- prototype: `__int64 __fastcall(NgcUtils *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800122c8`
- `0x180013f9c`
- `0x180017404`
- `0x18001c9a8`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180014e40`
- `0x180015288`

## string_xrefs

- `0x1800152b1`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::DuplicateString(NgcUtils *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v8,
    this,
    -1);
  if ( v8 )
  {
    *(_QWORD *)a2 = v8;
    v4 = 0;
    v8 = 0;
  }
  else
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)0x8007000ELL,
      v6);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
  return v4;
}

```

## disassembly

```asm
0x180015288  push    rbx; int
0x18001528a  sub     rsp, 20h
0x18001528e  mov     rbx, rdx
0x180015291  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015295  mov     rdx, rcx
0x180015298  lea     rcx, [rsp+28h+arg_10]
0x18001529d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800152a2  mov     rax, [rsp+28h+arg_10]
0x1800152a7  test    rax, rax
0x1800152aa  jnz     short loc_1800152CC
0x1800152ac  mov     rcx, [rsp+28h]; this
0x1800152b1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800152b8  mov     ebx, 8007000Eh
0x1800152bd  mov     edx, 0A0h; void *
0x1800152c2  mov     r9d, ebx; char *
0x1800152c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152ca  jmp     short loc_1800152DA
0x1800152cc  mov     [rbx], rax
0x1800152cf  xor     ebx, ebx
0x1800152d1  mov     [rsp+28h+arg_10], 0
0x1800152da  lea     rcx, [rsp+28h+arg_10]
0x1800152df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800152e4  mov     eax, ebx
0x1800152e6  add     rsp, 20h
0x1800152ea  pop     rbx
0x1800152eb  retn
```
