# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000f150`
- end: `0x18000f274`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `292`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800127b0`
- `0x1800128a0`

## callees

- `0x18000f150`
- `0x180012b40`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f1b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f1b5`

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
0x18000f150  mov     [rsp-28h+arg_10], rbx
0x18000f155  push    rbp
0x18000f156  push    rsi
0x18000f157  push    rdi
0x18000f158  push    r14
0x18000f15a  push    r15
0x18000f15c  mov     rbp, rsp
0x18000f15f  sub     rsp, 50h
0x18000f163  mov     rax, cs:__security_cookie
0x18000f16a  xor     rax, rsp
0x18000f16d  mov     [rbp+var_8], rax
0x18000f171  mov     r14d, r8d
0x18000f174  mov     rbx, rdx
0x18000f177  mov     rsi, rcx
0x18000f17a  mov     [rbp+var_20], 0
0x18000f182  xorps   xmm0, xmm0
0x18000f185  movups  [rbp+var_18], xmm0
0x18000f189  test    rdx, rdx
0x18000f18c  jnz     short loc_18000F193
0x18000f18e  jmp     loc_18000F252
0x18000f193  lea     rax, [rbp+var_20]
0x18000f197  mov     [rsp+50h+ppv], rax; ppv
0x18000f19c  lea     r9, IID_ICatRegister; riid
0x18000f1a3  mov     r15d, 1
0x18000f1a9  mov     r8d, r15d; dwClsContext
0x18000f1ac  xor     edx, edx; pUnkOuter
0x18000f1ae  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000f1b5  call    cs:__imp_CoCreateInstance
0x18000f1bb  test    eax, eax
0x18000f1bd  jns     short loc_18000F236
0x18000f1bf  jmp     short loc_18000F23C
0x18000f1c1  mov     rax, [rbx+8]
0x18000f1c5  movups  xmm0, xmmword ptr [rax]
0x18000f1c8  movdqu  [rbp+var_18], xmm0
0x18000f1cd  lea     r9, [rbp+var_18]
0x18000f1d1  mov     r8d, r15d
0x18000f1d4  mov     rdx, rsi
0x18000f1d7  test    r14d, r14d
0x18000f1da  jz      short loc_18000F217
0x18000f1dc  cmp     ecx, r15d
0x18000f1df  mov     rcx, [rbp+var_20]
0x18000f1e3  mov     rax, [rcx]
0x18000f1e6  jnz     short loc_18000F1EE
0x18000f1e8  mov     rax, [rax+28h]
0x18000f1ec  jmp     short loc_18000F1F2
0x18000f1ee  mov     rax, [rax+38h]
0x18000f1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1f7  mov     edi, eax
0x18000f1f9  test    eax, eax
0x18000f1fb  jns     short loc_18000F232
0x18000f1fd  mov     rcx, [rbp+var_20]
0x18000f201  test    rcx, rcx
0x18000f204  jz      short loc_18000F213
0x18000f206  mov     rax, [rcx]
0x18000f209  mov     rax, [rax+10h]
0x18000f20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f212  nop
0x18000f213  mov     eax, edi
0x18000f215  jmp     short loc_18000F254
0x18000f217  cmp     ecx, r15d
0x18000f21a  mov     rcx, [rbp+var_20]
0x18000f21e  mov     rax, [rcx]
0x18000f221  jnz     short loc_18000F229
0x18000f223  mov     rax, [rax+30h]
0x18000f227  jmp     short loc_18000F22D
0x18000f229  mov     rax, [rax+40h]
0x18000f22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f232  add     rbx, 10h
0x18000f236  mov     ecx, [rbx]
0x18000f238  test    ecx, ecx
0x18000f23a  jnz     short loc_18000F1C1
0x18000f23c  mov     rcx, [rbp+var_20]
0x18000f240  test    rcx, rcx
0x18000f243  jz      short loc_18000F252
0x18000f245  mov     rax, [rcx]
0x18000f248  mov     rax, [rax+10h]
0x18000f24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f251  nop
0x18000f252  xor     eax, eax
0x18000f254  mov     rcx, [rbp+var_8]
0x18000f258  xor     rcx, rsp; StackCookie
0x18000f25b  call    __security_check_cookie
0x18000f260  mov     rbx, [rsp+50h+arg_10]
0x18000f268  add     rsp, 50h
0x18000f26c  pop     r15
0x18000f26e  pop     r14
0x18000f270  pop     rdi
0x18000f271  pop     rsi
0x18000f272  pop     rbp
0x18000f273  retn
```
