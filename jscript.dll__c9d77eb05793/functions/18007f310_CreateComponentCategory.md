# CreateComponentCategory

- ea: `0x18007f310`
- end: `0x18007f41e`
- name: `CreateComponentCategory`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007f5cc`

## callees

- `0x18007f310`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18007f3b9`
- `msvcrt!wcsncpy_s` at `0x18007f3b9`
- `ole32!CoCreateInstance` at `0x18007f364`
- `ole32!CoCreateInstance` at `0x18007f364`

## pseudocode

```c
HRESULT __fastcall CreateComponentCategory(__int128 *a1, const wchar_t *a2)
{
  __int128 v2; // xmm6
  HRESULT result; // eax
  rsize_t v5; // rbx
  LPVOID v6; // rcx
  int v7; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-158h] BYREF
  __int128 v9; // [rsp+40h] [rbp-148h] BYREF
  int v10; // [rsp+50h] [rbp-138h]
  wchar_t Destination[134]; // [rsp+54h] [rbp-134h] BYREF

  v2 = *a1;
  ppv = 0;
  result = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
  if ( result >= 0 )
  {
    memset_0(Destination, 0, 0x100u);
    v5 = -1;
    v10 = 1033;
    v9 = v2;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 > 0x7F )
      v5 = 127;
    wcsncpy_s(Destination, 0x80u, a2, v5);
    v6 = ppv;
    Destination[v5] = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v6 + 24LL))(v6, 1, &v9);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18007f310  mov     rax, rsp
0x18007f313  mov     [rax+18h], rbx
0x18007f317  mov     [rax+20h], rsi
0x18007f31b  push    rdi
0x18007f31c  sub     rsp, 180h
0x18007f323  movaps  xmmword ptr [rax-18h], xmm6
0x18007f327  mov     rax, cs:__security_cookie
0x18007f32e  xor     rax, rsp
0x18007f331  mov     [rsp+188h+var_28], rax
0x18007f339  movaps  xmm6, xmmword ptr [rcx]
0x18007f33c  lea     rax, [rsp+188h+var_158]
0x18007f341  xor     esi, esi
0x18007f343  mov     [rsp+188h+ppv], rax; ppv
0x18007f348  mov     rdi, rdx
0x18007f34b  mov     [rsp+188h+var_158], rsi
0x18007f350  lea     r9, IID_ICatRegister; riid
0x18007f357  xor     edx, edx; pUnkOuter
0x18007f359  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18007f360  lea     r8d, [rsi+1]; dwClsContext
0x18007f364  call    cs:__imp_CoCreateInstance
0x18007f36a  test    eax, eax
0x18007f36c  js      loc_18007F3F4
0x18007f372  xor     edx, edx; Val
0x18007f374  lea     rcx, [rsp+188h+Destination]; void *
0x18007f379  mov     r8d, 100h; Size
0x18007f37f  call    memset_0
0x18007f384  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f388  mov     [rsp+188h+var_138], 409h
0x18007f390  movdqu  [rsp+188h+var_148], xmm6
0x18007f396  inc     rbx
0x18007f399  cmp     [rdi+rbx*2], si
0x18007f39d  jnz     short loc_18007F396
0x18007f39f  mov     eax, 7Fh
0x18007f3a4  lea     rcx, [rsp+188h+Destination]; Destination
0x18007f3a9  cmp     rbx, rax
0x18007f3ac  mov     r8, rdi; Source
0x18007f3af  cmova   rbx, rax
0x18007f3b3  mov     r9, rbx; MaxCount
0x18007f3b6  lea     edx, [rax+1]; SizeInWords
0x18007f3b9  call    cs:__imp_wcsncpy_s
0x18007f3bf  mov     rcx, [rsp+188h+var_158]
0x18007f3c4  lea     r8, [rsp+188h+var_148]
0x18007f3c9  mov     [rsp+rbx*2+188h+Destination], si
0x18007f3ce  mov     edx, 1
0x18007f3d3  mov     rax, [rcx]
0x18007f3d6  mov     rax, [rax+18h]
0x18007f3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3df  mov     rcx, [rsp+188h+var_158]
0x18007f3e4  mov     ebx, eax
0x18007f3e6  mov     rdx, [rcx]
0x18007f3e9  mov     rax, [rdx+10h]
0x18007f3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3f2  mov     eax, ebx
0x18007f3f4  mov     rcx, [rsp+188h+var_28]
0x18007f3fc  xor     rcx, rsp; StackCookie
0x18007f3ff  call    __security_check_cookie
0x18007f404  lea     r11, [rsp+188h+var_8]
0x18007f40c  mov     rbx, [r11+20h]
0x18007f410  mov     rsi, [r11+28h]
0x18007f414  movaps  xmm6, xmmword ptr [r11-10h]
0x18007f419  mov     rsp, r11
0x18007f41c  pop     rdi
0x18007f41d  retn
```
