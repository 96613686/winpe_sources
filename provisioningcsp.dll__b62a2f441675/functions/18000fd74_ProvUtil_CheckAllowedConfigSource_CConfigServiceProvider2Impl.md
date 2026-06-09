# ProvUtil::CheckAllowedConfigSource(CConfigServiceProvider2Impl *)

- ea: `0x18000fd74`
- end: `0x18000ff36`
- name: `?CheckAllowedConfigSource@ProvUtil@@YAJPEAVCConfigServiceProvider2Impl@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(ProvUtil *__hidden this, struct CConfigServiceProvider2Impl *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180009890`
- `0x1800118a0`

## callees

- `0x180006974`
- `0x18000fd74`
- `0x180038010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000fde1`
- `OLEAUT32!__imp_VariantInit` at `0x18000fde1`
- `OLEAUT32!__imp_VariantClear` at `0x18000fe2c`
- `OLEAUT32!__imp_VariantClear` at `0x18000fe84`
- `OLEAUT32!__imp_VariantClear` at `0x18000fecb`
- `OLEAUT32!__imp_VariantClear` at `0x18000fefd`
- `OLEAUT32!__imp_VariantClear` at `0x18000fe2c`
- `OLEAUT32!__imp_VariantClear` at `0x18000fe84`
- `OLEAUT32!__imp_VariantClear` at `0x18000fecb`
- `OLEAUT32!__imp_VariantClear` at `0x18000fefd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ProvUtil::CheckAllowedConfigSource(ProvUtil *this, struct CConfigServiceProvider2Impl *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v13; // [rsp+50h] [rbp+10h] BYREF

  v13 = 0;
  v2 = (*(__int64 (__fastcall **)(ProvUtil *, __int64 *))(*(_QWORD *)this + 48LL))(this, &v13);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provutil.cpp",
      (const char *)(unsigned int)v2,
      *(int *)&pvarg.vt);
    v4 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v3;
  }
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v13 + 32LL))(
         v13,
         L"OMADM::AccountType",
         &pvarg);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provutil.cpp",
      (const char *)(unsigned int)v6,
      *(int *)&pvarg.vt);
    VariantClear(&pvarg);
    v7 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v3;
  }
  if ( pvarg.vt != 19 )
  {
    v3 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provutil.cpp",
      (const char *)0x8000FFFFLL,
      *(int *)&pvarg.vt);
    VariantClear(&pvarg);
    v8 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v3;
  }
  if ( ((1LL << pvarg.cVal) & 0xD403061) != 0 )
  {
    VariantClear(&pvarg);
    v9 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return 2248146961LL;
  }
  else
  {
    VariantClear(&pvarg);
    v10 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000fd74  mov     [rsp-8+arg_8], rbx
0x18000fd79  push    rbp
0x18000fd7a  mov     rbp, rsp
0x18000fd7d  sub     rsp, 40h
0x18000fd81  mov     [rbp+arg_0], 0
0x18000fd89  mov     rax, [rcx]
0x18000fd8c  lea     rdx, [rbp+arg_0]
0x18000fd90  mov     rax, [rax+30h]
0x18000fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd99  mov     ebx, eax
0x18000fd9b  test    eax, eax
0x18000fd9d  jns     short loc_18000FDDD
0x18000fd9f  mov     rcx, [rbp+8]; this
0x18000fda3  mov     r9d, eax; char *
0x18000fda6  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\provcsp\\provu"...
0x18000fdad  mov     edx, 0Eh; void *
0x18000fdb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fdb7  nop
0x18000fdb8  mov     rcx, [rbp+arg_0]
0x18000fdbc  test    rcx, rcx
0x18000fdbf  jz      short loc_18000FDD6
0x18000fdc1  mov     [rbp+arg_0], 0
0x18000fdc9  mov     rax, [rcx]
0x18000fdcc  mov     rax, [rax+10h]
0x18000fdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd5  nop
0x18000fdd6  mov     eax, ebx
0x18000fdd8  jmp     loc_18000FF2A
0x18000fddd  lea     rcx, [rbp+pvarg]; pvarg
0x18000fde1  call    cs:__imp_VariantInit
0x18000fde8  nop     dword ptr [rax+rax+00h]
0x18000fded  nop
0x18000fdee  mov     rcx, [rbp+arg_0]
0x18000fdf2  mov     rax, [rcx]
0x18000fdf5  lea     r8, [rbp+pvarg]
0x18000fdf9  lea     rdx, aOmadmAccountty; "OMADM::AccountType"
0x18000fe00  mov     rax, [rax+20h]
0x18000fe04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe09  mov     ebx, eax
0x18000fe0b  mov     edx, 13h; void *
0x18000fe10  test    eax, eax
0x18000fe12  jns     short loc_18000FE5C
0x18000fe14  mov     rcx, [rbp+8]; this
0x18000fe18  mov     r9d, eax; char *
0x18000fe1b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\provcsp\\provu"...
0x18000fe22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe27  nop
0x18000fe28  lea     rcx, [rbp+pvarg]; pvarg
0x18000fe2c  call    cs:__imp_VariantClear
0x18000fe33  nop     dword ptr [rax+rax+00h]
0x18000fe38  nop
0x18000fe39  mov     rcx, [rbp+arg_0]
0x18000fe3d  test    rcx, rcx
0x18000fe40  jz      short loc_18000FE57
0x18000fe42  mov     [rbp+arg_0], 0
0x18000fe4a  mov     rax, [rcx]
0x18000fe4d  mov     rax, [rax+10h]
0x18000fe51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe56  nop
0x18000fe57  jmp     loc_18000FDD6
0x18000fe5c  cmp     dx, word ptr [rbp+pvarg]
0x18000fe60  jz      short loc_18000FEB4
0x18000fe62  mov     rcx, [rbp+8]; this
0x18000fe66  mov     ebx, 8000FFFFh
0x18000fe6b  mov     r9d, ebx; char *
0x18000fe6e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\provcsp\\provu"...
0x18000fe75  mov     edx, 14h; void *
0x18000fe7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe7f  nop
0x18000fe80  lea     rcx, [rbp+pvarg]; pvarg
0x18000fe84  call    cs:__imp_VariantClear
0x18000fe8b  nop     dword ptr [rax+rax+00h]
0x18000fe90  nop
0x18000fe91  mov     rcx, [rbp+arg_0]
0x18000fe95  test    rcx, rcx
0x18000fe98  jz      short loc_18000FEAF
0x18000fe9a  mov     [rbp+arg_0], 0
0x18000fea2  mov     rdx, [rcx]
0x18000fea5  mov     rax, [rdx+10h]
0x18000fea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feae  nop
0x18000feaf  jmp     loc_18000FDD6
0x18000feb4  mov     ecx, dword ptr [rbp+pvarg+8]
0x18000feb7  mov     eax, 1
0x18000febc  shl     rax, cl
0x18000febf  lea     rcx, [rbp+pvarg]; pvarg
0x18000fec3  test    rax, 0D403061h
0x18000fec9  jz      short loc_18000FEFD
0x18000fecb  call    cs:__imp_VariantClear
0x18000fed2  nop     dword ptr [rax+rax+00h]
0x18000fed7  nop
0x18000fed8  mov     rcx, [rbp+arg_0]
0x18000fedc  test    rcx, rcx
0x18000fedf  jz      short loc_18000FEF6
0x18000fee1  mov     [rbp+arg_0], 0
0x18000fee9  mov     rax, [rcx]
0x18000feec  mov     rax, [rax+10h]
0x18000fef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fef5  nop
0x18000fef6  mov     eax, 86000011h
0x18000fefb  jmp     short loc_18000FF2A
0x18000fefd  call    cs:__imp_VariantClear
0x18000ff04  nop     dword ptr [rax+rax+00h]
0x18000ff09  nop
0x18000ff0a  mov     rcx, [rbp+arg_0]
0x18000ff0e  test    rcx, rcx
0x18000ff11  jz      short loc_18000FF28
0x18000ff13  mov     [rbp+arg_0], 0
0x18000ff1b  mov     rax, [rcx]
0x18000ff1e  mov     rax, [rax+10h]
0x18000ff22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff27  nop
0x18000ff28  xor     eax, eax
0x18000ff2a  mov     rbx, [rsp+40h+arg_8]
0x18000ff2f  add     rsp, 40h
0x18000ff33  pop     rbp
0x18000ff34  retn
```
