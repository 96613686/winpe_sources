# ProvPackage::GetPackageId(void)

- ea: `0x18002e9b0`
- end: `0x18002eb48`
- name: `?GetPackageId@ProvPackage@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180023558`
- `0x180023830`

## callees

- `0x18001b388`
- `0x180020fe0`
- `0x1800210f0`
- `0x18002e9b0`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18002ea41`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18002ea41`

## pseudocode

```c
__int64 __fastcall ProvPackage::GetPackageId(_QWORD *a1, __int64 a2)
{
  void **v4; // rbp
  __int64 v5; // rbx
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // r8
  int v12[2]; // [rsp+20h] [rbp-98h] BYREF
  __int64 v13; // [rsp+28h] [rbp-90h]
  _WORD Src[40]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v13 = a2;
  v4 = (void **)(a1 + 15);
  if ( a1[17] )
  {
    *(_QWORD *)(a2 + 24) = 7;
    *(_QWORD *)(a2 + 16) = 0;
    *(_WORD *)a2 = 0;
    std::wstring::assign((void **)a2, (void **)a1 + 15, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    v5 = 0;
    v13 = 0;
    *(_QWORD *)v12 = 0;
    v6 = a1[13];
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
      v6 = *(_QWORD *)v12;
      if ( *(_QWORD *)v12 )
        v5 = *(_QWORD *)v12;
      v13 = v5;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v6 + 64LL))(v6, Src, 39);
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
    else
    {
      v10 = 0;
    }
    std::wstring::assign(v4, (char *)Src, v10);
    *(_QWORD *)(a2 + 24) = 7;
    *(_QWORD *)(a2 + 16) = 0;
    *(_WORD *)a2 = 0;
    std::wstring::assign((void **)a2, v4, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 128LL))(v5);
  }
  return a2;
}

```

## disassembly

```asm
0x18002e9b0  mov     [rsp+arg_10], rbx
0x18002e9b5  push    rbp
0x18002e9b6  push    rdi
0x18002e9b7  push    r14
0x18002e9b9  sub     rsp, 0A0h
0x18002e9c0  mov     rax, cs:__security_cookie
0x18002e9c7  xor     rax, rsp
0x18002e9ca  mov     [rsp+0B8h+var_28], rax
0x18002e9d2  mov     rdi, rdx
0x18002e9d5  mov     rax, rcx
0x18002e9d8  mov     [rsp+0B8h+var_90], rdx
0x18002e9dd  xor     r14d, r14d
0x18002e9e0  lea     rbp, [rcx+78h]
0x18002e9e4  cmp     [rbp+10h], r14
0x18002e9e8  jz      short loc_18002EA11
0x18002e9ea  mov     qword ptr [rdx+18h], 7
0x18002e9f2  mov     [rdx+10h], r14
0x18002e9f6  mov     [rdx], r14w
0x18002e9fa  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002e9fe  xor     r8d, r8d
0x18002ea01  mov     rdx, rbp
0x18002ea04  mov     rcx, rdi; void *
0x18002ea07  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ea0c  jmp     loc_18002EAF7
0x18002ea11  mov     rbx, r14
0x18002ea14  mov     [rsp+0B8h+var_90], rbx
0x18002ea19  mov     qword ptr [rsp+0B8h+var_98], r14; int
0x18002ea1e  mov     rcx, [rcx+68h]
0x18002ea22  test    rcx, rcx
0x18002ea25  jz      short loc_18002EA2E
0x18002ea27  mov     qword ptr [rsp+0B8h+var_98], rcx
0x18002ea2c  jmp     short loc_18002EA68
0x18002ea2e  lea     rcx, [rax+8]
0x18002ea32  cmp     qword ptr [rcx+18h], 8
0x18002ea37  jb      short loc_18002EA3C
0x18002ea39  mov     rcx, [rcx]
0x18002ea3c  lea     rdx, [rsp+0B8h+var_98]
0x18002ea41  call    cs:__imp_OpenProvisioningPackageForRead
0x18002ea47  mov     rcx, [rsp+0B8h]; this
0x18002ea4f  test    eax, eax
0x18002ea51  js      loc_18002EB33
0x18002ea57  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x18002ea5c  test    rcx, rcx
0x18002ea5f  cmovnz  rbx, rcx
0x18002ea63  mov     [rsp+0B8h+var_90], rbx
0x18002ea68  mov     rax, [rcx]
0x18002ea6b  mov     r8d, 27h ; '''
0x18002ea71  lea     rdx, [rsp+0B8h+Src]
0x18002ea76  mov     rax, [rax+40h]
0x18002ea7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea7f  mov     rcx, [rsp+0B8h]; this
0x18002ea87  test    eax, eax
0x18002ea89  js      loc_18002EB1E
0x18002ea8f  cmp     [rsp+0B8h+Src], r14w
0x18002ea95  jnz     short loc_18002EA9C
0x18002ea97  mov     r8, r14
0x18002ea9a  jmp     short loc_18002EAAF
0x18002ea9c  lea     rax, [rsp+0B8h+Src]
0x18002eaa1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002eaa5  inc     r8
0x18002eaa8  cmp     [rax+r8*2], r14w
0x18002eaad  jnz     short loc_18002EAA5
0x18002eaaf  lea     rdx, [rsp+0B8h+Src]; Src
0x18002eab4  mov     rcx, rbp; void *
0x18002eab7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002eabc  mov     qword ptr [rdi+18h], 7
0x18002eac4  mov     [rdi+10h], r14
0x18002eac8  mov     [rdi], r14w
0x18002eacc  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ead0  xor     r8d, r8d
0x18002ead3  mov     rdx, rbp
0x18002ead6  mov     rcx, rdi; void *
0x18002ead9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002eade  nop
0x18002eadf  test    rbx, rbx
0x18002eae2  jz      short loc_18002EAF7
0x18002eae4  mov     rax, [rbx]
0x18002eae7  mov     rcx, rbx
0x18002eaea  mov     rax, [rax+80h]
0x18002eaf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaf6  nop
0x18002eaf7  mov     rax, rdi
0x18002eafa  mov     rcx, [rsp+0B8h+var_28]
0x18002eb02  xor     rcx, rsp; StackCookie
0x18002eb05  call    __security_check_cookie
0x18002eb0a  mov     rbx, [rsp+0B8h+arg_10]
0x18002eb12  add     rsp, 0A0h
0x18002eb19  pop     r14
0x18002eb1b  pop     rdi
0x18002eb1c  pop     rbp
0x18002eb1d  retn
0x18002eb1e  mov     r9d, eax; char *
0x18002eb21  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002eb28  mov     edx, 1AAh; void *
0x18002eb2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eb33  mov     r9d, eax; char *
0x18002eb36  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002eb3d  mov     edx, 1A5h; void *
0x18002eb42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
