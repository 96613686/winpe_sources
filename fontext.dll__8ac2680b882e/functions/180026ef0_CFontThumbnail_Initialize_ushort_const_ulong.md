# CFontThumbnail::Initialize(ushort const *,ulong)

- ea: `0x180026ef0`
- end: `0x180026fe3`
- name: `?Initialize@CFontThumbnail@@UEAAJPEBGK@Z`
- size: `243`
- prototype: `int(CFontThumbnail *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180006624`
- `0x1800223e8`
- `0x1800226f8`
- `0x1800230fc`
- `0x180026ef0`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `GDI32!AddFontResourceExW` at `0x180026f84`
- `GDI32!AddFontResourceExW` at `0x180026f84`
- `GDI32!RemoveFontResourceExW` at `0x180026fb8`
- `GDI32!RemoveFontResourceExW` at `0x180026fb8`

## pseudocode

```c
__int64 __fastcall CFontThumbnail::Initialize(CFontThumbnail *this, const unsigned __int16 *a2)
{
  const struct _ITEMIDLIST **v3; // rsi
  signed int v5; // ebx
  WCHAR name[528]; // [rsp+20h] [rbp-448h] BYREF

  v3 = (const struct _ITEMIDLIST **)((char *)this + 24);
  v5 = FID_CreateFromPath(a2, (struct _ITEMIDLIST **)this + 3);
  if ( v5 >= 0 )
  {
    memset_0(name, 0, 0x412u);
    if ( FID_Type(*v3) == 2 )
      FID_FontResourceFileName(*v3, name, 0x209u);
    else
      StringCchCopyW(name, 0x209u, a2);
    if ( AddFontResourceExW(name, 0x10u, 0) )
    {
      v5 = StringCchCopyW((unsigned __int16 *)this + 24, 0x209u, name);
      if ( v5 < 0 )
        RemoveFontResourceExW(name, 0x10u, 0);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026ef0  mov     [rsp+arg_10], rbx
0x180026ef5  push    rbp
0x180026ef6  push    rsi
0x180026ef7  push    rdi
0x180026ef8  sub     rsp, 450h
0x180026eff  mov     rax, cs:__security_cookie
0x180026f06  xor     rax, rsp
0x180026f09  mov     [rsp+468h+var_28], rax
0x180026f11  mov     rdi, rdx
0x180026f14  lea     rsi, [rcx+18h]
0x180026f18  mov     rbp, rcx
0x180026f1b  mov     rdx, rsi; struct _ITEMIDLIST **
0x180026f1e  mov     rcx, rdi; unsigned __int16 *
0x180026f21  call    ?FID_CreateFromPath@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; FID_CreateFromPath(ushort const *,_ITEMIDLIST * *)
0x180026f26  mov     ebx, eax
0x180026f28  test    eax, eax
0x180026f2a  js      loc_180026FBE
0x180026f30  xor     edx, edx; Val
0x180026f32  lea     rcx, [rsp+468h+name]; void *
0x180026f37  mov     r8d, 412h; Size
0x180026f3d  call    memset_0
0x180026f42  mov     rcx, [rsi]; struct _ITEMIDLIST *
0x180026f45  call    ?FID_Type@@YAKPEFBU_ITEMIDLIST@@@Z; FID_Type(_ITEMIDLIST const *)
0x180026f4a  cmp     eax, 2
0x180026f4d  jnz     short loc_180026F64
0x180026f4f  mov     rcx, [rsi]; struct _ITEMIDLIST *
0x180026f52  lea     rdx, [rsp+468h+name]; unsigned __int16 *
0x180026f57  mov     r8d, 209h; unsigned int
0x180026f5d  call    ?FID_FontResourceFileName@@YAXPEFBU_ITEMIDLIST@@PEAGI@Z; FID_FontResourceFileName(_ITEMIDLIST const *,ushort *,uint)
0x180026f62  jmp     short loc_180026F76
0x180026f64  mov     r8, rdi; unsigned __int16 *
0x180026f67  lea     rcx, [rsp+468h+name]; unsigned __int16 *
0x180026f6c  mov     edx, 209h; unsigned __int64
0x180026f71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026f76  xor     r8d, r8d; res
0x180026f79  lea     rcx, [rsp+468h+name]; name
0x180026f7e  lea     edi, [r8+10h]
0x180026f82  mov     edx, edi; fl
0x180026f84  call    cs:__imp_AddFontResourceExW
0x180026f8a  test    eax, eax
0x180026f8c  jnz     short loc_180026F95
0x180026f8e  mov     ebx, 80004005h
0x180026f93  jmp     short loc_180026FBE
0x180026f95  lea     rcx, [rbp+30h]; unsigned __int16 *
0x180026f99  mov     edx, 209h; unsigned __int64
0x180026f9e  lea     r8, [rsp+468h+name]; unsigned __int16 *
0x180026fa3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026fa8  mov     ebx, eax
0x180026faa  test    eax, eax
0x180026fac  jns     short loc_180026FBE
0x180026fae  xor     r8d, r8d; pdv
0x180026fb1  lea     rcx, [rsp+468h+name]; name
0x180026fb6  mov     edx, edi; fl
0x180026fb8  call    cs:__imp_RemoveFontResourceExW
0x180026fbe  mov     eax, ebx
0x180026fc0  mov     rcx, [rsp+468h+var_28]
0x180026fc8  xor     rcx, rsp; StackCookie
0x180026fcb  call    __security_check_cookie
0x180026fd0  mov     rbx, [rsp+468h+arg_10]
0x180026fd8  add     rsp, 450h
0x180026fdf  pop     rdi
0x180026fe0  pop     rsi
0x180026fe1  pop     rbp
0x180026fe2  retn
```
