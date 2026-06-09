# ProvPackage::GetPackageId(void)

- ea: `0x180041620`
- end: `0x1800417b8`
- name: `?GetPackageId@ProvPackage@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `408`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000af20`
- `0x18000b030`
- `0x180021cf4`
- `0x180041620`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800416b1`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800416b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ProvPackage::GetPackageId(_QWORD *a1, _QWORD *a2)
{
  void *v4; // rbp
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // r8
  int v12[2]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD *v13; // [rsp+28h] [rbp-90h]
  _WORD Src[40]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v13 = a2;
  v4 = a1 + 15;
  if ( a1[17] )
  {
    a2[3] = 7;
    a2[2] = 0;
    *(_WORD *)a2 = 0;
    std::wstring::assign(a2);
  }
  else
  {
    v5 = 0;
    v13 = 0;
    *(_QWORD *)v12 = 0;
    v6 = (_QWORD *)a1[13];
    if ( v6 )
    {
      *(_QWORD *)v12 = v6;
    }
    else
    {
      v7 = a1 + 1;
      if ( a1[4] >= 8u )
        v7 = (_QWORD *)*v7;
      v8 = OpenProvisioningPackageForRead(v7, v12);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
          (const char *)(unsigned int)v8,
          v12[0]);
      v6 = *(_QWORD **)v12;
      if ( *(_QWORD *)v12 )
        v5 = *(_QWORD **)v12;
      v13 = v5;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD *, _WORD *, __int64))(*v6 + 64LL))(v6, Src, 39);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
        (const char *)(unsigned int)v9,
        v12[0]);
    if ( Src[0] )
    {
      v10 = -1;
      do
        ++v10;
      while ( Src[v10] );
    }
    std::wstring::assign(v4, Src);
    a2[3] = 7;
    a2[2] = 0;
    *(_WORD *)a2 = 0;
    std::wstring::assign(a2);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD *))(*v5 + 128LL))(v5);
  }
  return a2;
}

```

## disassembly

```asm
0x180041620  mov     [rsp+arg_10], rbx
0x180041625  push    rbp
0x180041626  push    rdi
0x180041627  push    r14
0x180041629  sub     rsp, 0A0h
0x180041630  mov     rax, cs:__security_cookie
0x180041637  xor     rax, rsp
0x18004163a  mov     [rsp+0B8h+var_28], rax
0x180041642  mov     rdi, rdx
0x180041645  mov     rax, rcx
0x180041648  mov     [rsp+0B8h+var_90], rdx
0x18004164d  xor     r14d, r14d
0x180041650  lea     rbp, [rcx+78h]
0x180041654  cmp     [rbp+10h], r14
0x180041658  jz      short loc_180041681
0x18004165a  mov     qword ptr [rdx+18h], 7
0x180041662  mov     [rdx+10h], r14
0x180041666  mov     [rdx], r14w
0x18004166a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004166e  xor     r8d, r8d
0x180041671  mov     rdx, rbp
0x180041674  mov     rcx, rdi; void *
0x180041677  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18004167c  jmp     loc_180041767
0x180041681  mov     rbx, r14
0x180041684  mov     [rsp+0B8h+var_90], rbx
0x180041689  mov     qword ptr [rsp+0B8h+var_98], r14; int
0x18004168e  mov     rcx, [rcx+68h]
0x180041692  test    rcx, rcx
0x180041695  jz      short loc_18004169E
0x180041697  mov     qword ptr [rsp+0B8h+var_98], rcx
0x18004169c  jmp     short loc_1800416D8
0x18004169e  lea     rcx, [rax+8]
0x1800416a2  cmp     qword ptr [rcx+18h], 8
0x1800416a7  jb      short loc_1800416AC
0x1800416a9  mov     rcx, [rcx]
0x1800416ac  lea     rdx, [rsp+0B8h+var_98]
0x1800416b1  call    cs:__imp_OpenProvisioningPackageForRead
0x1800416b7  mov     rcx, [rsp+0B8h]; this
0x1800416bf  test    eax, eax
0x1800416c1  js      loc_1800417A3
0x1800416c7  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x1800416cc  test    rcx, rcx
0x1800416cf  cmovnz  rbx, rcx
0x1800416d3  mov     [rsp+0B8h+var_90], rbx
0x1800416d8  mov     rax, [rcx]
0x1800416db  mov     r8d, 27h ; '''
0x1800416e1  lea     rdx, [rsp+0B8h+Src]
0x1800416e6  mov     rax, [rax+40h]
0x1800416ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416ef  mov     rcx, [rsp+0B8h]; this
0x1800416f7  test    eax, eax
0x1800416f9  js      loc_18004178E
0x1800416ff  cmp     [rsp+0B8h+Src], r14w
0x180041705  jnz     short loc_18004170C
0x180041707  mov     r8, r14
0x18004170a  jmp     short loc_18004171F
0x18004170c  lea     rax, [rsp+0B8h+Src]
0x180041711  or      r8, 0FFFFFFFFFFFFFFFFh
0x180041715  inc     r8
0x180041718  cmp     [rax+r8*2], r14w
0x18004171d  jnz     short loc_180041715
0x18004171f  lea     rdx, [rsp+0B8h+Src]; Src
0x180041724  mov     rcx, rbp; void *
0x180041727  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004172c  mov     qword ptr [rdi+18h], 7
0x180041734  mov     [rdi+10h], r14
0x180041738  mov     [rdi], r14w
0x18004173c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180041740  xor     r8d, r8d
0x180041743  mov     rdx, rbp
0x180041746  mov     rcx, rdi; void *
0x180041749  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18004174e  nop
0x18004174f  test    rbx, rbx
0x180041752  jz      short loc_180041767
0x180041754  mov     rax, [rbx]
0x180041757  mov     rcx, rbx
0x18004175a  mov     rax, [rax+80h]
0x180041761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041766  nop
0x180041767  mov     rax, rdi
0x18004176a  mov     rcx, [rsp+0B8h+var_28]
0x180041772  xor     rcx, rsp; StackCookie
0x180041775  call    __security_check_cookie
0x18004177a  mov     rbx, [rsp+0B8h+arg_10]
0x180041782  add     rsp, 0A0h
0x180041789  pop     r14
0x18004178b  pop     rdi
0x18004178c  pop     rbp
0x18004178d  retn
0x18004178e  mov     r9d, eax; char *
0x180041791  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180041798  mov     edx, 1AAh; void *
0x18004179d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800417a3  mov     r9d, eax; char *
0x1800417a6  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800417ad  mov     edx, 1A5h; void *
0x1800417b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
