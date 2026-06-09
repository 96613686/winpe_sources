# CPackage::IconReadFromStream(IStream *)

- ea: `0x180008c8c`
- end: `0x180008dc4`
- name: `?IconReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009fa0`

## callees

- `0x180008c8c`
- `0x18000a43c`
- `0x18000aef4`
- `0x18000afb4`
- `0x18000b7a0`
- `0x18000b94c`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180008cf7`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180008d1f`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180008cf7`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180008d1f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008cc0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008cc0`

## pseudocode

```c
__int64 __fastcall CPackage::IconReadFromStream(CPackage *this, struct IStream *a2)
{
  char *v4; // rbx
  CPackage *v5; // rcx
  _WORD v7[8]; // [rsp+30h] [rbp-348h] BYREF
  CHAR pszSrc[272]; // [rsp+40h] [rbp-338h] BYREF
  unsigned __int16 v9[264]; // [rsp+150h] [rbp-228h] BYREF

  v4 = (char *)GlobalAlloc(0x40u, 0x430u);
  if ( v4 )
  {
    StringReadFromStream(a2, pszSrc, 0x104u);
    SHAnsiToUnicode(pszSrc, (PWSTR)v4 + 264, 260);
    StringReadFromStream(a2, pszSrc, 0x104u);
    SHAnsiToUnicode(pszSrc, (PWSTR)v4 + 4, 260);
    v7[0] = 0;
    ((void (__fastcall *)(struct IStream *, _WORD *, __int64))a2->lpVtbl->Read)(a2, v7, 2);
    *((_DWORD *)v4 + 262) = v7[0];
    CPackage::_GetCurrentIcon(this, (struct _IC *)v4);
    CPackage::_CreateSaferIconTitle(this, v9, (struct _IC *)v4, 0);
    CPackage::_IconCalcSize(v5, (struct tagRECT *)(v4 + 1052), v9);
  }
  CPackage::_DestroyIC(this);
  *((_QWORD *)this + 12) = v4;
  return v4 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180008c8c  mov     [rsp+arg_10], rbx
0x180008c91  mov     [rsp+arg_18], rsi
0x180008c96  push    rdi
0x180008c97  sub     rsp, 370h
0x180008c9e  mov     rax, cs:__security_cookie
0x180008ca5  xor     rax, rsp
0x180008ca8  mov     [rsp+378h+var_18], rax
0x180008cb0  mov     rsi, rdx
0x180008cb3  mov     rdi, rcx
0x180008cb6  mov     edx, 430h; dwBytes
0x180008cbb  mov     ecx, 40h ; '@'; uFlags
0x180008cc0  call    cs:__imp_GlobalAlloc
0x180008cc6  mov     rbx, rax
0x180008cc9  test    rax, rax
0x180008ccc  jz      loc_180008D87
0x180008cd2  mov     r8d, 104h; unsigned int
0x180008cd8  lea     rdx, [rsp+378h+pszSrc]; char *
0x180008cdd  mov     rcx, rsi; struct IStream *
0x180008ce0  call    ?StringReadFromStream@@YAJPEAUIStream@@PEADI@Z; StringReadFromStream(IStream *,char *,uint)
0x180008ce5  lea     rdx, [rbx+210h]; pwszDst
0x180008cec  mov     r8d, 104h; cwchBuf
0x180008cf2  lea     rcx, [rsp+378h+pszSrc]; pszSrc
0x180008cf7  call    cs:__imp_SHAnsiToUnicode
0x180008cfd  mov     r8d, 104h; unsigned int
0x180008d03  lea     rdx, [rsp+378h+pszSrc]; char *
0x180008d08  mov     rcx, rsi; struct IStream *
0x180008d0b  call    ?StringReadFromStream@@YAJPEAUIStream@@PEADI@Z; StringReadFromStream(IStream *,char *,uint)
0x180008d10  lea     rdx, [rbx+8]; pwszDst
0x180008d14  mov     r8d, 104h; cwchBuf
0x180008d1a  lea     rcx, [rsp+378h+pszSrc]; pszSrc
0x180008d1f  call    cs:__imp_SHAnsiToUnicode
0x180008d25  xor     eax, eax
0x180008d27  lea     rdx, [rsp+378h+var_348]
0x180008d2c  mov     [rsp+378h+var_348], ax
0x180008d31  xor     r9d, r9d
0x180008d34  mov     rax, [rsi]
0x180008d37  mov     rcx, rsi
0x180008d3a  lea     r8d, [r9+2]
0x180008d3e  mov     rax, [rax+18h]
0x180008d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d47  movzx   eax, [rsp+378h+var_348]
0x180008d4c  mov     rdx, rbx; struct _IC *
0x180008d4f  mov     rcx, rdi; this
0x180008d52  mov     [rbx+418h], eax
0x180008d58  call    ?_GetCurrentIcon@CPackage@@IEAAXPEAU_IC@@@Z; CPackage::_GetCurrentIcon(_IC *)
0x180008d5d  xor     r9d, r9d; struct tagRECT *
0x180008d60  lea     rdx, [rsp+378h+var_228]; unsigned __int16 *
0x180008d68  mov     r8, rbx; struct _IC *
0x180008d6b  mov     rcx, rdi; this
0x180008d6e  call    ?_CreateSaferIconTitle@CPackage@@IEAAXPEAGPEAU_IC@@PEBUtagRECT@@@Z; CPackage::_CreateSaferIconTitle(ushort *,_IC *,tagRECT const *)
0x180008d73  lea     rdx, [rbx+41Ch]; struct tagRECT *
0x180008d7a  lea     r8, [rsp+378h+var_228]; unsigned __int16 *
0x180008d82  call    ?_IconCalcSize@CPackage@@IEAAHPEAUtagRECT@@PEBG@Z; CPackage::_IconCalcSize(tagRECT *,ushort const *)
0x180008d87  mov     rcx, rdi; this
0x180008d8a  call    ?_DestroyIC@CPackage@@IEAAXXZ; CPackage::_DestroyIC(void)
0x180008d8f  mov     [rdi+60h], rbx
0x180008d93  neg     rbx
0x180008d96  sbb     eax, eax
0x180008d98  not     eax
0x180008d9a  and     eax, 80004005h
0x180008d9f  mov     rcx, [rsp+378h+var_18]
0x180008da7  xor     rcx, rsp; StackCookie
0x180008daa  call    __security_check_cookie
0x180008daf  lea     r11, [rsp+378h+var_8]
0x180008db7  mov     rbx, [r11+20h]
0x180008dbb  mov     rsi, [r11+28h]
0x180008dbf  mov     rsp, r11
0x180008dc2  pop     rdi
0x180008dc3  retn
```
