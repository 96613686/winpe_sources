# _lambda_38b19d9e4b8169e2748e59367af93d2c_::operator()(Windows::Internal::CHSTRINGResult &)

- ea: `0x1800680a0`
- end: `0x1800680eb`
- name: `??R_lambda_38b19d9e4b8169e2748e59367af93d2c_@@QEBAJAEAVCHSTRINGResult@Internal@Windows@@@Z`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180068790`

## callees

- `0x1800680a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800680d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800680d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800680be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800680be`

## pseudocode

```c
__int64 __fastcall _lambda_38b19d9e4b8169e2748e59367af93d2c_::operator()(HSTRING *a1, __int64 a2)
{
  HSTRING v2; // rdi
  HSTRING *v3; // rbx

  v2 = *a1;
  v3 = (HSTRING *)(a2 + 16);
  if ( !*a1 || v2 != *v3 )
  {
    WindowsDeleteString(*v3);
    *v3 = 0;
    WindowsDuplicateString(v2, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800680a0  mov     [rsp+arg_8], rbx
0x1800680a5  push    rdi
0x1800680a6  sub     rsp, 20h
0x1800680aa  mov     rdi, [rcx]
0x1800680ad  lea     rbx, [rdx+10h]
0x1800680b1  test    rdi, rdi
0x1800680b4  jz      short loc_1800680BB
0x1800680b6  cmp     rdi, [rbx]
0x1800680b9  jz      short loc_1800680D8
0x1800680bb  mov     rcx, [rbx]; string
0x1800680be  call    cs:__imp_WindowsDeleteString
0x1800680c4  mov     qword ptr [rbx], 0
0x1800680cb  mov     rdx, rbx; newString
0x1800680ce  mov     rcx, rdi; string
0x1800680d1  call    cs:__imp_WindowsDuplicateString
0x1800680d7  nop
0x1800680d8  xor     eax, eax
0x1800680da  jmp     short loc_1800680E0
0x1800680dc  mov     eax, [rsp+28h+arg_0]
0x1800680e0  mov     rbx, [rsp+28h+arg_8]
0x1800680e5  add     rsp, 20h
0x1800680e9  pop     rdi
0x1800680ea  retn
```
