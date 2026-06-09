# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000c848`
- end: `0x18000c940`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `248`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c628`
- `0x180013000`

## callees

- `0x1800033ec`
- `0x18000c848`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000c8ac`
- `ole32!CoCreateInstance` at `0x18000c8ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(
        const struct _GUID *a1,
        const struct ATL::_ATL_CATMAP_ENTRY *a2,
        int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int128 v11; // [rsp+38h] [rbp-18h] BYREF

  v4 = a2;
  ppv = 0;
  v11 = 0;
  if ( a2 && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v11 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v6 + 40))(
                 ppv,
                 a1,
                 1,
                 &v11);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v6 + 56))(
                 ppv,
                 a1,
                 1,
                 &v11);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_15;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v6 + 48))(ppv, a1, 1, &v11);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v6 + 64))(ppv, a1, 1, &v11);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
  }
  v8 = 0;
LABEL_15:
  R<IADs>::~R<IADs>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18000c848  mov     [rsp-28h+arg_10], rbx
0x18000c84d  push    rbp
0x18000c84e  push    rsi
0x18000c84f  push    rdi
0x18000c850  push    r14
0x18000c852  push    r15
0x18000c854  mov     rbp, rsp
0x18000c857  sub     rsp, 50h
0x18000c85b  mov     rax, cs:__security_cookie
0x18000c862  xor     rax, rsp
0x18000c865  mov     [rbp+var_8], rax
0x18000c869  mov     r14d, r8d
0x18000c86c  mov     rbx, rdx
0x18000c86f  mov     rsi, rcx
0x18000c872  mov     [rbp+var_20], 0
0x18000c87a  xorps   xmm0, xmm0
0x18000c87d  movups  [rbp+var_18], xmm0
0x18000c881  test    rdx, rdx
0x18000c884  jz      loc_18000C913
0x18000c88a  lea     rax, [rbp+var_20]
0x18000c88e  mov     [rsp+50h+ppv], rax; ppv
0x18000c893  lea     r9, IID_ICatRegister; riid
0x18000c89a  mov     r15d, 1
0x18000c8a0  mov     r8d, r15d; dwClsContext
0x18000c8a3  xor     edx, edx; pUnkOuter
0x18000c8a5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000c8ac  call    cs:__imp_CoCreateInstance
0x18000c8b2  test    eax, eax
0x18000c8b4  js      short loc_18000C913
0x18000c8b6  cmp     dword ptr [rbx], 0
0x18000c8b9  jz      short loc_18000C913
0x18000c8bb  mov     rax, [rbx+8]
0x18000c8bf  movups  xmm0, xmmword ptr [rax]
0x18000c8c2  movdqu  [rbp+var_18], xmm0
0x18000c8c7  mov     rcx, [rbp+var_20]
0x18000c8cb  lea     r9, [rbp+var_18]
0x18000c8cf  mov     r8d, r15d
0x18000c8d2  mov     rdx, rsi
0x18000c8d5  mov     rax, [rcx]
0x18000c8d8  test    r14d, r14d
0x18000c8db  jz      short loc_18000C8F9
0x18000c8dd  cmp     [rbx], r15d
0x18000c8e0  jnz     short loc_18000C8E8
0x18000c8e2  mov     rax, [rax+28h]
0x18000c8e6  jmp     short loc_18000C8EC
0x18000c8e8  mov     rax, [rax+38h]
0x18000c8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8f1  mov     edi, eax
0x18000c8f3  test    eax, eax
0x18000c8f5  js      short loc_18000C915
0x18000c8f7  jmp     short loc_18000C90D
0x18000c8f9  cmp     [rbx], r15d
0x18000c8fc  jnz     short loc_18000C904
0x18000c8fe  mov     rax, [rax+30h]
0x18000c902  jmp     short loc_18000C908
0x18000c904  mov     rax, [rax+40h]
0x18000c908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90d  add     rbx, 10h
0x18000c911  jmp     short loc_18000C8B6
0x18000c913  xor     edi, edi
0x18000c915  lea     rcx, [rbp+var_20]
0x18000c919  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18000c91e  mov     eax, edi
0x18000c920  mov     rcx, [rbp+var_8]
0x18000c924  xor     rcx, rsp; StackCookie
0x18000c927  call    __security_check_cookie
0x18000c92c  mov     rbx, [rsp+50h+arg_10]
0x18000c934  add     rsp, 50h
0x18000c938  pop     r15
0x18000c93a  pop     r14
0x18000c93c  pop     rdi
0x18000c93d  pop     rsi
0x18000c93e  pop     rbp
0x18000c93f  retn
```
