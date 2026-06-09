# NativeMsh::PwrshCommon::ProbeAssembly(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180008c30`
- end: `0x180008d2d`
- name: `?ProbeAssembly@PwrshCommon@NativeMsh@@MEAAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `253`
- prototype: `void __fastcall(unsigned __int8 (__fastcall ***)(_QWORD, void **), void *, void *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180005ff0`
- `0x180006100`
- `0x180007818`
- `0x180008c30`
- `0x1800096b0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008d10`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008d10`

## string_xrefs

- `0x180008c84`: `.ni.dll`

## pseudocode

```c
void __fastcall NativeMsh::PwrshCommon::ProbeAssembly(
        unsigned __int8 (__fastcall ***a1)(_QWORD, void **),
        void *a2,
        void *a3,
        void **a4)
{
  void *Src[3]; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int64 v9; // [rsp+38h] [rbp-18h]

  v9 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src, a2);
  std::wstring::operator+=(Src, a3);
  std::wstring::operator+=(Src, L".ni.dll");
  if ( (**a1)(a1, Src)
    || (std::wstring::assign(Src, a2),
        std::wstring::operator+=(Src, a3),
        std::wstring::operator+=(Src, L".dll"),
        (**a1)(a1, Src)) )
  {
    if ( a4 != Src )
      std::wstring::assign(a4);
  }
  if ( v9 >= 8 )
    operator delete(Src[0]);
}

```

## disassembly

```asm
0x180008c30  push    rbp
0x180008c32  push    rbx
0x180008c33  push    rsi
0x180008c34  push    rdi
0x180008c35  push    r14
0x180008c37  mov     rbp, rsp
0x180008c3a  sub     rsp, 50h
0x180008c3e  mov     rax, cs:__security_cookie
0x180008c45  xor     rax, rsp
0x180008c48  mov     [rbp+var_10], rax
0x180008c4c  mov     rbx, r9
0x180008c4f  mov     r14, r8
0x180008c52  mov     rsi, rdx
0x180008c55  mov     rdi, rcx
0x180008c58  mov     [rbp+var_18], 7
0x180008c60  mov     [rbp+var_20], 0
0x180008c68  xor     eax, eax
0x180008c6a  mov     word ptr [rbp+Src], ax
0x180008c6e  lea     rcx, [rbp+Src]; void *
0x180008c72  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008c77  nop
0x180008c78  mov     rdx, r14; void *
0x180008c7b  lea     rcx, [rbp+Src]; Src
0x180008c7f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180008c84  lea     rdx, aNiDll; ".ni.dll"
0x180008c8b  lea     rcx, [rbp+Src]; Src
0x180008c8f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180008c94  mov     rax, [rdi]
0x180008c97  lea     rdx, [rbp+Src]
0x180008c9b  mov     rcx, rdi
0x180008c9e  mov     rax, [rax]
0x180008ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ca6  test    al, al
0x180008ca8  jnz     short loc_180008CE8
0x180008caa  mov     rdx, rsi; Src
0x180008cad  lea     rcx, [rbp+Src]; void *
0x180008cb1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008cb6  mov     rdx, r14; void *
0x180008cb9  lea     rcx, [rbp+Src]; Src
0x180008cbd  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180008cc2  lea     rdx, aDll; ".dll"
0x180008cc9  lea     rcx, [rbp+Src]; Src
0x180008ccd  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180008cd2  mov     rax, [rdi]
0x180008cd5  lea     rdx, [rbp+Src]
0x180008cd9  mov     rcx, rdi
0x180008cdc  mov     rax, [rax]
0x180008cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce4  test    al, al
0x180008ce6  jz      short loc_180008D05
0x180008ce8  lea     rax, [rbp+Src]
0x180008cec  cmp     rbx, rax
0x180008cef  jz      short loc_180008D05
0x180008cf1  or      r9, 0FFFFFFFFFFFFFFFFh
0x180008cf5  xor     r8d, r8d
0x180008cf8  lea     rdx, [rbp+Src]
0x180008cfc  mov     rcx, rbx; void *
0x180008cff  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180008d04  nop
0x180008d05  cmp     [rbp+var_18], 8
0x180008d0a  jb      short loc_180008D16
0x180008d0c  mov     rcx, [rbp+Src]
0x180008d10  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008d16  mov     rcx, [rbp+var_10]
0x180008d1a  xor     rcx, rsp; StackCookie
0x180008d1d  call    __security_check_cookie
0x180008d22  add     rsp, 50h
0x180008d26  pop     r14
0x180008d28  pop     rdi
0x180008d29  pop     rsi
0x180008d2a  pop     rbx
0x180008d2b  pop     rbp
0x180008d2c  retn
```
