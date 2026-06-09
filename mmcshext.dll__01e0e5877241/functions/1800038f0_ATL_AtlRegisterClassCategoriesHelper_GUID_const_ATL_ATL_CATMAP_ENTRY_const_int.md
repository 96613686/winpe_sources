# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800038f0`
- end: `0x180003a14`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `292`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006840`
- `0x180006900`

## callees

- `0x1800038f0`
- `0x18000a5b0`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003955`
- `ole32!CoCreateInstance` at `0x180003955`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(
        const struct _GUID *a1,
        const struct ATL::_ATL_CATMAP_ENTRY *a2,
        int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v10; // rax
  int v11; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int128 v13; // [rsp+38h] [rbp-18h] BYREF

  v4 = a2;
  ppv = 0;
  v13 = 0;
  if ( a2 )
  {
    if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv) >= 0 )
    {
      while ( 1 )
      {
        v11 = *(_DWORD *)v4;
        if ( !*(_DWORD *)v4 )
          break;
        v13 = *(_OWORD *)*((_QWORD *)v4 + 1);
        if ( a3 )
        {
          v6 = *(_QWORD *)ppv;
          if ( v11 == 1 )
            v7 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v6 + 40))(
                   ppv,
                   a1,
                   1,
                   &v13);
          else
            v7 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v6 + 56))(
                   ppv,
                   a1,
                   1,
                   &v13);
          v8 = v7;
          if ( v7 < 0 )
          {
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            return v8;
          }
        }
        else
        {
          v10 = *(_QWORD *)ppv;
          if ( v11 == 1 )
            (*(void (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v10 + 48))(ppv, a1, 1, &v13);
          else
            (*(void (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v10 + 64))(ppv, a1, 1, &v13);
        }
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return 0;
}

```

## disassembly

```asm
0x1800038f0  mov     [rsp-28h+arg_10], rbx
0x1800038f5  push    rbp
0x1800038f6  push    rsi
0x1800038f7  push    rdi
0x1800038f8  push    r14
0x1800038fa  push    r15
0x1800038fc  mov     rbp, rsp
0x1800038ff  sub     rsp, 50h
0x180003903  mov     rax, cs:__security_cookie
0x18000390a  xor     rax, rsp
0x18000390d  mov     [rbp+var_8], rax
0x180003911  mov     r14d, r8d
0x180003914  mov     rbx, rdx
0x180003917  mov     rsi, rcx
0x18000391a  mov     [rbp+var_20], 0
0x180003922  xorps   xmm0, xmm0
0x180003925  movups  [rbp+var_18], xmm0
0x180003929  test    rdx, rdx
0x18000392c  jnz     short loc_180003933
0x18000392e  jmp     loc_1800039F2
0x180003933  lea     rax, [rbp+var_20]
0x180003937  mov     [rsp+50h+ppv], rax; ppv
0x18000393c  lea     r9, IID_ICatRegister; riid
0x180003943  mov     r15d, 1
0x180003949  mov     r8d, r15d; dwClsContext
0x18000394c  xor     edx, edx; pUnkOuter
0x18000394e  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003955  call    cs:__imp_CoCreateInstance
0x18000395b  test    eax, eax
0x18000395d  jns     short loc_1800039D6
0x18000395f  jmp     short loc_1800039DC
0x180003961  mov     rax, [rbx+8]
0x180003965  movups  xmm0, xmmword ptr [rax]
0x180003968  movdqu  [rbp+var_18], xmm0
0x18000396d  lea     r9, [rbp+var_18]
0x180003971  mov     r8d, r15d
0x180003974  mov     rdx, rsi
0x180003977  test    r14d, r14d
0x18000397a  jz      short loc_1800039B7
0x18000397c  cmp     ecx, r15d
0x18000397f  mov     rcx, [rbp+var_20]
0x180003983  mov     rax, [rcx]
0x180003986  jnz     short loc_18000398E
0x180003988  mov     rax, [rax+28h]
0x18000398c  jmp     short loc_180003992
0x18000398e  mov     rax, [rax+38h]
0x180003992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003997  mov     edi, eax
0x180003999  test    eax, eax
0x18000399b  jns     short loc_1800039D2
0x18000399d  mov     rcx, [rbp+var_20]
0x1800039a1  test    rcx, rcx
0x1800039a4  jz      short loc_1800039B3
0x1800039a6  mov     rax, [rcx]
0x1800039a9  mov     rax, [rax+10h]
0x1800039ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b2  nop
0x1800039b3  mov     eax, edi
0x1800039b5  jmp     short loc_1800039F4
0x1800039b7  cmp     ecx, r15d
0x1800039ba  mov     rcx, [rbp+var_20]
0x1800039be  mov     rax, [rcx]
0x1800039c1  jnz     short loc_1800039C9
0x1800039c3  mov     rax, [rax+30h]
0x1800039c7  jmp     short loc_1800039CD
0x1800039c9  mov     rax, [rax+40h]
0x1800039cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d2  add     rbx, 10h
0x1800039d6  mov     ecx, [rbx]
0x1800039d8  test    ecx, ecx
0x1800039da  jnz     short loc_180003961
0x1800039dc  mov     rcx, [rbp+var_20]
0x1800039e0  test    rcx, rcx
0x1800039e3  jz      short loc_1800039F2
0x1800039e5  mov     rax, [rcx]
0x1800039e8  mov     rax, [rax+10h]
0x1800039ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f1  nop
0x1800039f2  xor     eax, eax
0x1800039f4  mov     rcx, [rbp+var_8]
0x1800039f8  xor     rcx, rsp; StackCookie
0x1800039fb  call    __security_check_cookie
0x180003a00  mov     rbx, [rsp+50h+arg_10]
0x180003a08  add     rsp, 50h
0x180003a0c  pop     r15
0x180003a0e  pop     r14
0x180003a10  pop     rdi
0x180003a11  pop     rsi
0x180003a12  pop     rbp
0x180003a13  retn
```
