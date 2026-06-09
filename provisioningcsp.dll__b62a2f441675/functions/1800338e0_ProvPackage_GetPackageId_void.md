# ProvPackage::GetPackageId(void)

- ea: `0x1800338e0`
- end: `0x180033a7f`
- name: `?GetPackageId@ProvPackage@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800090e0`
- `0x18000918c`
- `0x180009fac`
- `0x1800338e0`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x180033971`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x180033971`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800338e0  mov     [rsp+arg_10], rbx
0x1800338e5  push    rbp
0x1800338e6  push    rdi
0x1800338e7  push    r14
0x1800338e9  sub     rsp, 0A0h
0x1800338f0  mov     rax, cs:__security_cookie
0x1800338f7  xor     rax, rsp
0x1800338fa  mov     [rsp+0B8h+var_28], rax
0x180033902  mov     rdi, rdx
0x180033905  mov     rax, rcx
0x180033908  mov     [rsp+0B8h+var_90], rdx
0x18003390d  xor     r14d, r14d
0x180033910  lea     rbp, [rcx+78h]
0x180033914  cmp     [rbp+10h], r14
0x180033918  jz      short loc_180033941
0x18003391a  mov     qword ptr [rdx+18h], 7
0x180033922  mov     [rdx+10h], r14
0x180033926  mov     [rdx], r14w
0x18003392a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003392e  xor     r8d, r8d
0x180033931  mov     rdx, rbp
0x180033934  mov     rcx, rdi; void *
0x180033937  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003393c  jmp     loc_180033A2D
0x180033941  mov     rbx, r14
0x180033944  mov     [rsp+0B8h+var_90], rbx
0x180033949  mov     qword ptr [rsp+0B8h+var_98], r14; int
0x18003394e  mov     rcx, [rcx+68h]
0x180033952  test    rcx, rcx
0x180033955  jz      short loc_18003395E
0x180033957  mov     qword ptr [rsp+0B8h+var_98], rcx
0x18003395c  jmp     short loc_18003399E
0x18003395e  lea     rcx, [rax+8]
0x180033962  cmp     qword ptr [rcx+18h], 8
0x180033967  jb      short loc_18003396C
0x180033969  mov     rcx, [rcx]
0x18003396c  lea     rdx, [rsp+0B8h+var_98]
0x180033971  call    cs:__imp_OpenProvisioningPackageForRead
0x180033978  nop     dword ptr [rax+rax+00h]
0x18003397d  mov     rcx, [rsp+0B8h]; this
0x180033985  test    eax, eax
0x180033987  js      loc_180033A6A
0x18003398d  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x180033992  test    rcx, rcx
0x180033995  cmovnz  rbx, rcx
0x180033999  mov     [rsp+0B8h+var_90], rbx
0x18003399e  mov     rax, [rcx]
0x1800339a1  mov     r8d, 27h ; '''
0x1800339a7  lea     rdx, [rsp+0B8h+Src]
0x1800339ac  mov     rax, [rax+40h]
0x1800339b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339b5  mov     rcx, [rsp+0B8h]; this
0x1800339bd  test    eax, eax
0x1800339bf  js      loc_180033A55
0x1800339c5  cmp     [rsp+0B8h+Src], r14w
0x1800339cb  jnz     short loc_1800339D2
0x1800339cd  mov     r8, r14
0x1800339d0  jmp     short loc_1800339E5
0x1800339d2  lea     rax, [rsp+0B8h+Src]
0x1800339d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800339db  inc     r8
0x1800339de  cmp     [rax+r8*2], r14w
0x1800339e3  jnz     short loc_1800339DB
0x1800339e5  lea     rdx, [rsp+0B8h+Src]; Src
0x1800339ea  mov     rcx, rbp; void *
0x1800339ed  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800339f2  mov     qword ptr [rdi+18h], 7
0x1800339fa  mov     [rdi+10h], r14
0x1800339fe  mov     [rdi], r14w
0x180033a02  or      r9, 0FFFFFFFFFFFFFFFFh
0x180033a06  xor     r8d, r8d
0x180033a09  mov     rdx, rbp
0x180033a0c  mov     rcx, rdi; void *
0x180033a0f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180033a14  nop
0x180033a15  test    rbx, rbx
0x180033a18  jz      short loc_180033A2D
0x180033a1a  mov     rax, [rbx]
0x180033a1d  mov     rcx, rbx
0x180033a20  mov     rax, [rax+80h]
0x180033a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a2c  nop
0x180033a2d  mov     rax, rdi
0x180033a30  mov     rcx, [rsp+0B8h+var_28]
0x180033a38  xor     rcx, rsp; StackCookie
0x180033a3b  call    __security_check_cookie
0x180033a40  mov     rbx, [rsp+0B8h+arg_10]
0x180033a48  add     rsp, 0A0h
0x180033a4f  pop     r14
0x180033a51  pop     rdi
0x180033a52  pop     rbp
0x180033a53  retn
0x180033a55  mov     r9d, eax; char *
0x180033a58  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033a5f  mov     edx, 1AAh; void *
0x180033a64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033a6a  mov     r9d, eax; char *
0x180033a6d  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180033a74  mov     edx, 1A5h; void *
0x180033a79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
