# ResolveLinkInfoA

- ea: `0x1800055e0`
- end: `0x180005682`
- name: `ResolveLinkInfoA`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001670`
- `0x1800055e0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180005655`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180005655`

## pseudocode

```c
int __fastcall ResolveLinkInfoA(
        struct _ilinkinfoW *a1,
        CHAR *a2,
        unsigned int a3,
        HWND a4,
        _DWORD *a5,
        struct _ilinkinfoW **a6)
{
  int result; // eax
  WCHAR WideCharStr[264]; // [rsp+40h] [rbp-238h] BYREF

  result = ResolveLinkInfoW(a1, WideCharStr, a3, a4, a5, a6);
  if ( result )
    return WideCharToMultiByte(0, 0, WideCharStr, -1, a2, 260, 0, 0) != 0 ? result : 0;
  return result;
}

```

## disassembly

```asm
0x1800055e0  push    rbx; ResolveLinkInfo
0x1800055e2  push    rdi
0x1800055e3  sub     rsp, 268h
0x1800055ea  mov     rax, cs:__security_cookie
0x1800055f1  xor     rax, rsp
0x1800055f4  mov     [rsp+278h+var_28], rax
0x1800055fc  mov     rax, [rsp+278h+arg_28]
0x180005604  mov     rdi, rdx
0x180005607  mov     r10, [rsp+278h+arg_20]
0x18000560f  lea     rdx, [rsp+278h+WideCharStr]; unsigned __int16 *
0x180005614  mov     qword ptr [rsp+278h+cbMultiByte], rax; struct _ilinkinfoW **
0x180005619  mov     [rsp+278h+lpMultiByteStr], r10; __int64
0x18000561e  call    ResolveLinkInfoW
0x180005623  mov     ebx, eax
0x180005625  test    eax, eax
0x180005627  jz      short loc_180005667
0x180005629  mov     [rsp+278h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180005632  lea     r8, [rsp+278h+WideCharStr]; lpWideCharStr
0x180005637  mov     [rsp+278h+lpDefaultChar], 0; lpDefaultChar
0x180005640  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005644  mov     [rsp+278h+cbMultiByte], 104h; cbMultiByte
0x18000564c  xor     edx, edx; dwFlags
0x18000564e  xor     ecx, ecx; CodePage
0x180005650  mov     [rsp+278h+lpMultiByteStr], rdi; lpMultiByteStr
0x180005655  call    cs:__imp_WideCharToMultiByte
0x18000565c  nop     dword ptr [rax+rax+00h]
0x180005661  neg     eax
0x180005663  sbb     eax, eax
0x180005665  and     eax, ebx
0x180005667  mov     rcx, [rsp+278h+var_28]
0x18000566f  xor     rcx, rsp; StackCookie
0x180005672  call    __security_check_cookie
0x180005677  add     rsp, 268h
0x18000567e  pop     rdi
0x18000567f  pop     rbx
0x180005680  retn
```
