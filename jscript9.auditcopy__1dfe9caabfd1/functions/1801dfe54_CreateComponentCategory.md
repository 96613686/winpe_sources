# CreateComponentCategory

- ea: `0x1801dfe54`
- end: `0x1801dff7b`
- name: `CreateComponentCategory`
- size: `295`
- prototype: `HRESULT __fastcall(__int128 *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801e01f4`

## callees

- `0x1801cc26b`
- `0x1801dfe54`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1801dff15`
- `msvcrt!wcsncpy_s` at `0x1801dff15`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1801dfeba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1801dfeba`

## pseudocode

```c
HRESULT __fastcall CreateComponentCategory(__int128 *a1, const wchar_t *a2)
{
  __int128 v3; // xmm6
  HRESULT result; // eax
  rsize_t v5; // rbx
  LPVOID v6; // rcx
  int v7; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+50h] [rbp-B0h]
  wchar_t Destination[134]; // [rsp+54h] [rbp-ACh] BYREF

  ppv = 0;
  v3 = *a1;
  result = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
  if ( result >= 0 )
  {
    memset_0(Destination, 0, 0x100u);
    v5 = -1;
    v10 = 1033;
    v9 = v3;
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
0x1801dfe54  mov     rax, rsp
0x1801dfe57  mov     [rax+18h], rbx
0x1801dfe5b  mov     [rax+10h], rdx
0x1801dfe5f  mov     [rax+8], rcx
0x1801dfe63  push    rbp
0x1801dfe64  push    rsi
0x1801dfe65  push    rdi
0x1801dfe66  lea     rbp, [rsp-80h]
0x1801dfe6b  sub     rsp, 180h
0x1801dfe72  movaps  xmmword ptr [rax-28h], xmm6
0x1801dfe76  mov     rax, cs:__security_cookie
0x1801dfe7d  xor     rax, rsp
0x1801dfe80  mov     [rbp+90h+var_30], rax
0x1801dfe84  mov     rax, [rbp+90h+arg_0]
0x1801dfe8b  lea     r9, IID_ICatRegister; riid
0x1801dfe92  mov     rdi, [rbp+90h+Source]
0x1801dfe99  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1801dfea0  xor     esi, esi
0x1801dfea2  xor     edx, edx; pUnkOuter
0x1801dfea4  mov     [rsp+190h+var_160], rsi
0x1801dfea9  movaps  xmm6, xmmword ptr [rax]
0x1801dfeac  lea     rax, [rsp+190h+var_160]
0x1801dfeb1  mov     [rsp+190h+ppv], rax; ppv
0x1801dfeb6  lea     r8d, [rsi+1]; dwClsContext
0x1801dfeba  call    cs:__imp_CoCreateInstance
0x1801dfec1  nop     dword ptr [rax+rax+00h]
0x1801dfec6  test    eax, eax
0x1801dfec8  js      loc_1801DFF56
0x1801dfece  xor     edx, edx; Val
0x1801dfed0  lea     rcx, [rsp+190h+Destination]; void *
0x1801dfed5  mov     r8d, 100h; Size
0x1801dfedb  call    memset_0
0x1801dfee0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801dfee4  mov     [rsp+190h+var_140], 409h
0x1801dfeec  movdqu  [rsp+190h+var_150], xmm6
0x1801dfef2  inc     rbx
0x1801dfef5  cmp     [rdi+rbx*2], si
0x1801dfef9  jnz     short loc_1801DFEF2
0x1801dfefb  mov     eax, 7Fh
0x1801dff00  lea     rcx, [rsp+190h+Destination]; Destination
0x1801dff05  cmp     rbx, rax
0x1801dff08  mov     r8, rdi; Source
0x1801dff0b  cmova   rbx, rax
0x1801dff0f  mov     r9, rbx; MaxCount
0x1801dff12  lea     edx, [rax+1]; SizeInWords
0x1801dff15  call    cs:__imp_wcsncpy_s
0x1801dff1c  nop     dword ptr [rax+rax+00h]
0x1801dff21  mov     rcx, [rsp+190h+var_160]
0x1801dff26  lea     r8, [rsp+190h+var_150]
0x1801dff2b  mov     [rsp+rbx*2+190h+Destination], si
0x1801dff30  mov     edx, 1
0x1801dff35  mov     rax, [rcx]
0x1801dff38  mov     rax, [rax+18h]
0x1801dff3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dff41  mov     rcx, [rsp+190h+var_160]
0x1801dff46  mov     ebx, eax
0x1801dff48  mov     rdx, [rcx]
0x1801dff4b  mov     rax, [rdx+10h]
0x1801dff4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dff54  mov     eax, ebx
0x1801dff56  mov     rcx, [rbp+90h+var_30]
0x1801dff5a  xor     rcx, rsp; StackCookie
0x1801dff5d  call    __security_check_cookie
0x1801dff62  lea     r11, [rsp+190h+var_10]
0x1801dff6a  mov     rbx, [r11+30h]
0x1801dff6e  movaps  xmm6, xmmword ptr [r11-10h]
0x1801dff73  mov     rsp, r11
0x1801dff76  pop     rdi
0x1801dff77  pop     rsi
0x1801dff78  pop     rbp
0x1801dff79  retn
```
