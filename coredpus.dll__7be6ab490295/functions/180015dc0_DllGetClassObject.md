# DllGetClassObject

- ea: `0x180015dc0`
- end: `0x180015eae`
- name: `DllGetClassObject`
- size: `238`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800045e0`
- `0x1800145f0`
- `0x180015cac`
- `0x180015dc0`
- `0x180030010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct ComRegisterFuncList *v6; // rbx
  struct ComRegisterFuncList *v7; // rax
  struct ComRegisterFuncList *v8; // rax
  CClassFactory *v10; // rax
  CClassFactory *v11; // rax
  CClassFactory *v12; // rsi
  HRESULT v13; // ebx
  struct IUnknown *(*v14)(void); // [rsp+60h] [rbp+18h] BYREF

  v14 = 0;
  if ( ppv )
    *ppv = 0;
  v6 = ComRegisterFuncListObj();
  v7 = ComRegisterFuncListObj();
  if ( v6 == (struct ComRegisterFuncList *)((char *)v7 + 8 * *((_QWORD *)v7 + 48)) )
  {
LABEL_6:
    if ( !v14 )
      return -2147221231;
  }
  else
  {
    while ( !v14 )
    {
      (*(void (__fastcall **)(const IID *const, struct IUnknown *(**)(void)))v6)(rclsid, &v14);
      v6 = (struct ComRegisterFuncList *)((char *)v6 + 8);
      v8 = ComRegisterFuncListObj();
      if ( v6 == (struct ComRegisterFuncList *)((char *)v8 + 8 * *((_QWORD *)v8 + 48)) )
        goto LABEL_6;
    }
  }
  v10 = (CClassFactory *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
    return -2147024882;
  v11 = CClassFactory::CClassFactory(v10, v14);
  v12 = v11;
  if ( !v11 )
    return -2147024882;
  _InterlockedIncrement(&dword_18003EBFC);
  v13 = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v11)(v11, riid, ppv);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v12 + 16LL))(v12);
  return v13;
}

```

## disassembly

```asm
0x180015dc0  push    rbx
0x180015dc2  push    rbp
0x180015dc3  push    rsi
0x180015dc4  push    rdi
0x180015dc5  sub     rsp, 28h
0x180015dc9  mov     [rsp+48h+arg_10], 0
0x180015dd2  mov     rdi, r8
0x180015dd5  mov     rbp, rdx
0x180015dd8  mov     rsi, rcx
0x180015ddb  test    r8, r8
0x180015dde  jz      short loc_180015DE7
0x180015de0  mov     qword ptr [r8], 0
0x180015de7  call    ?ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ; ComRegisterFuncListObj(void)
0x180015dec  mov     rbx, rax
0x180015def  call    ?ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ; ComRegisterFuncListObj(void)
0x180015df4  mov     rdx, [rax+180h]
0x180015dfb  lea     rcx, [rax+rdx*8]
0x180015dff  cmp     rbx, rcx
0x180015e02  jz      short loc_180015E35
0x180015e04  cmp     [rsp+48h+arg_10], 0
0x180015e0a  jnz     short loc_180015E44
0x180015e0c  mov     rax, [rbx]
0x180015e0f  lea     rdx, [rsp+48h+arg_10]
0x180015e14  mov     rcx, rsi
0x180015e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e1c  add     rbx, 8
0x180015e20  call    ?ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ; ComRegisterFuncListObj(void)
0x180015e25  mov     rcx, [rax+180h]
0x180015e2c  lea     rax, [rax+rcx*8]
0x180015e30  cmp     rbx, rax
0x180015e33  jnz     short loc_180015E04
0x180015e35  cmp     [rsp+48h+arg_10], 0
0x180015e3b  jnz     short loc_180015E44
0x180015e3d  mov     eax, 80040111h
0x180015e42  jmp     short loc_180015EA4
0x180015e44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015e4b  mov     ecx, 18h; unsigned __int64
0x180015e50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015e55  test    rax, rax
0x180015e58  jz      short loc_180015E9F
0x180015e5a  mov     rdx, [rsp+48h+arg_10]; struct IUnknown *(*)(void)
0x180015e5f  mov     rcx, rax; this
0x180015e62  call    ??0CClassFactory@@QEAA@P6APEAUIUnknown@@XZ@Z; CClassFactory::CClassFactory(IUnknown * (*)(void))
0x180015e67  mov     rsi, rax
0x180015e6a  test    rax, rax
0x180015e6d  jz      short loc_180015E9F
0x180015e6f  lock inc cs:dword_18003EBFC
0x180015e76  mov     rcx, [rax]
0x180015e79  mov     r8, rdi
0x180015e7c  mov     rdx, rbp
0x180015e7f  mov     rax, [rcx]
0x180015e82  mov     rcx, rsi
0x180015e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8a  mov     rcx, [rsi]
0x180015e8d  mov     ebx, eax
0x180015e8f  mov     rax, [rcx+10h]
0x180015e93  mov     rcx, rsi
0x180015e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e9b  mov     eax, ebx
0x180015e9d  jmp     short loc_180015EA4
0x180015e9f  mov     eax, 8007000Eh
0x180015ea4  add     rsp, 28h
0x180015ea8  pop     rdi
0x180015ea9  pop     rsi
0x180015eaa  pop     rbp
0x180015eab  pop     rbx
0x180015eac  retn
```
