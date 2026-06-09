# CreateComponentCategory

- ea: `0x180443e18`
- end: `0x180443f3f`
- name: `CreateComponentCategory`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180444130`

## callees

- `0x180443e18`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180443ed9`
- `msvcrt!wcsncpy_s` at `0x180443ed9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180443e7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180443e7e`

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
  result = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv);
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
0x180443e18  mov     rax, rsp
0x180443e1b  mov     [rax+18h], rbx
0x180443e1f  mov     [rax+10h], rdx
0x180443e23  mov     [rax+8], rcx
0x180443e27  push    rbp
0x180443e28  push    rsi
0x180443e29  push    rdi
0x180443e2a  lea     rbp, [rsp-80h]
0x180443e2f  sub     rsp, 180h
0x180443e36  movaps  xmmword ptr [rax-28h], xmm6
0x180443e3a  mov     rax, cs:__security_cookie
0x180443e41  xor     rax, rsp
0x180443e44  mov     [rbp+90h+var_30], rax
0x180443e48  mov     rax, [rbp+90h+arg_0]
0x180443e4f  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180443e56  mov     rdi, [rbp+90h+Source]
0x180443e5d  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180443e64  xor     esi, esi
0x180443e66  xor     edx, edx; pUnkOuter
0x180443e68  mov     [rsp+190h+var_160], rsi
0x180443e6d  movaps  xmm6, xmmword ptr [rax]
0x180443e70  lea     rax, [rsp+190h+var_160]
0x180443e75  mov     [rsp+190h+ppv], rax; ppv
0x180443e7a  lea     r8d, [rsi+1]; dwClsContext
0x180443e7e  call    cs:__imp_CoCreateInstance
0x180443e85  nop     dword ptr [rax+rax+00h]
0x180443e8a  test    eax, eax
0x180443e8c  js      loc_180443F1A
0x180443e92  xor     edx, edx; Val
0x180443e94  lea     rcx, [rsp+190h+Destination]; void *
0x180443e99  mov     r8d, 100h; Size
0x180443e9f  call    memset_0
0x180443ea4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180443ea8  mov     [rsp+190h+var_140], 409h
0x180443eb0  movdqu  [rsp+190h+var_150], xmm6
0x180443eb6  inc     rbx
0x180443eb9  cmp     [rdi+rbx*2], si
0x180443ebd  jnz     short loc_180443EB6
0x180443ebf  mov     eax, 7Fh
0x180443ec4  lea     rcx, [rsp+190h+Destination]; Destination
0x180443ec9  cmp     rbx, rax
0x180443ecc  mov     r8, rdi; Source
0x180443ecf  cmova   rbx, rax
0x180443ed3  mov     r9, rbx; MaxCount
0x180443ed6  lea     edx, [rax+1]; SizeInWords
0x180443ed9  call    cs:__imp_wcsncpy_s
0x180443ee0  nop     dword ptr [rax+rax+00h]
0x180443ee5  mov     rcx, [rsp+190h+var_160]
0x180443eea  lea     r8, [rsp+190h+var_150]
0x180443eef  mov     [rsp+rbx*2+190h+Destination], si
0x180443ef4  mov     edx, 1
0x180443ef9  mov     rax, [rcx]
0x180443efc  mov     rax, [rax+18h]
0x180443f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180443f05  mov     rcx, [rsp+190h+var_160]
0x180443f0a  mov     ebx, eax
0x180443f0c  mov     rdx, [rcx]
0x180443f0f  mov     rax, [rdx+10h]
0x180443f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180443f18  mov     eax, ebx
0x180443f1a  mov     rcx, [rbp+90h+var_30]
0x180443f1e  xor     rcx, rsp; StackCookie
0x180443f21  call    __security_check_cookie
0x180443f26  lea     r11, [rsp+190h+var_10]
0x180443f2e  mov     rbx, [r11+30h]
0x180443f32  movaps  xmm6, xmmword ptr [r11-10h]
0x180443f37  mov     rsp, r11
0x180443f3a  pop     rdi
0x180443f3b  pop     rsi
0x180443f3c  pop     rbp
0x180443f3d  retn
```
