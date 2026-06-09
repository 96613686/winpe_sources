# CreateComponentCategory

- ea: `0x180080cd8`
- end: `0x180080df3`
- name: `CreateComponentCategory`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080fc4`

## callees

- `0x180080cd8`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180080d87`
- `msvcrt!wcsncpy_s` at `0x180080d87`
- `ole32!CoCreateInstance` at `0x180080d2c`
- `ole32!CoCreateInstance` at `0x180080d2c`

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
0x180080cd8  mov     rax, rsp
0x180080cdb  mov     [rax+18h], rbx
0x180080cdf  mov     [rax+20h], rsi
0x180080ce3  push    rdi
0x180080ce4  sub     rsp, 180h
0x180080ceb  movaps  xmmword ptr [rax-18h], xmm6
0x180080cef  mov     rax, cs:__security_cookie
0x180080cf6  xor     rax, rsp
0x180080cf9  mov     [rsp+188h+var_28], rax
0x180080d01  movaps  xmm6, xmmword ptr [rcx]
0x180080d04  lea     rax, [rsp+188h+var_158]
0x180080d09  xor     esi, esi
0x180080d0b  mov     [rsp+188h+ppv], rax; ppv
0x180080d10  mov     rdi, rdx
0x180080d13  mov     [rsp+188h+var_158], rsi
0x180080d18  lea     r9, IID_ICatRegister; riid
0x180080d1f  xor     edx, edx; pUnkOuter
0x180080d21  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180080d28  lea     r8d, [rsi+1]; dwClsContext
0x180080d2c  call    cs:__imp_CoCreateInstance
0x180080d33  nop     dword ptr [rax+rax+00h]
0x180080d38  test    eax, eax
0x180080d3a  js      loc_180080DC8
0x180080d40  xor     edx, edx; Val
0x180080d42  lea     rcx, [rsp+188h+Destination]; void *
0x180080d47  mov     r8d, 100h; Size
0x180080d4d  call    memset_0
0x180080d52  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180080d56  mov     [rsp+188h+var_138], 409h
0x180080d5e  movdqu  [rsp+188h+var_148], xmm6
0x180080d64  inc     rbx
0x180080d67  cmp     [rdi+rbx*2], si
0x180080d6b  jnz     short loc_180080D64
0x180080d6d  mov     eax, 7Fh
0x180080d72  lea     rcx, [rsp+188h+Destination]; Destination
0x180080d77  cmp     rbx, rax
0x180080d7a  mov     r8, rdi; Source
0x180080d7d  cmova   rbx, rax
0x180080d81  mov     r9, rbx; MaxCount
0x180080d84  lea     edx, [rax+1]; SizeInWords
0x180080d87  call    cs:__imp_wcsncpy_s
0x180080d8e  nop     dword ptr [rax+rax+00h]
0x180080d93  mov     rcx, [rsp+188h+var_158]
0x180080d98  lea     r8, [rsp+188h+var_148]
0x180080d9d  mov     [rsp+rbx*2+188h+Destination], si
0x180080da2  mov     edx, 1
0x180080da7  mov     rax, [rcx]
0x180080daa  mov     rax, [rax+18h]
0x180080dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080db3  mov     rcx, [rsp+188h+var_158]
0x180080db8  mov     ebx, eax
0x180080dba  mov     rdx, [rcx]
0x180080dbd  mov     rax, [rdx+10h]
0x180080dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080dc6  mov     eax, ebx
0x180080dc8  mov     rcx, [rsp+188h+var_28]
0x180080dd0  xor     rcx, rsp; StackCookie
0x180080dd3  call    __security_check_cookie
0x180080dd8  lea     r11, [rsp+188h+var_8]
0x180080de0  mov     rbx, [r11+20h]
0x180080de4  mov     rsi, [r11+28h]
0x180080de8  movaps  xmm6, xmmword ptr [r11-10h]
0x180080ded  mov     rsp, r11
0x180080df0  pop     rdi
0x180080df1  retn
```
