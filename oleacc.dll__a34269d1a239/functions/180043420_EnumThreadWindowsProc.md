# EnumThreadWindowsProc

- ea: `0x180043420`
- end: `0x18004350e`
- name: `EnumThreadWindowsProc`
- size: `238`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001e4c0`
- `0x18001efc4`
- `0x1800266cc`
- `0x180043420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180043488`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180043488`
- `USER32!GetClassNameW` at `0x180043455`
- `USER32!GetClassNameW` at `0x180043455`

## pseudocode

```c
_BOOL8 __fastcall EnumThreadWindowsProc(HWND a1, __int64 a2)
{
  WCHAR *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  struct tagTOOLINFOW v8; // [rsp+30h] [rbp-F8h] BYREF
  WCHAR ClassName[64]; // [rsp+80h] [rbp-A8h] BYREF

  if ( GetClassNameW(a1, ClassName, 64)
    && CompareStringW(0x7Fu, 1u, ClassName, -1, L"tooltips_class32", -1) == 2
    && (v4 = *(WCHAR **)(a2 + 16),
        memset_0(&v8, 0, sizeof(v8)),
        v8.hwnd = *(HWND *)a2,
        v8.uId = *(unsigned int *)(a2 + 8),
        v8.cbSize = 64,
        v8.lpszText = v4,
        *v4 = 0,
        !(unsigned int)XSend_ToolTip_GetItem(a1, v5, v6, &v8)) )
  {
    return **(_WORD **)(a2 + 16) == 0;
  }
  else
  {
    return 1;
  }
}

```

## disassembly

```asm
0x180043420  mov     [rsp+arg_10], rbx
0x180043425  push    rbp
0x180043426  push    rsi
0x180043427  push    rdi
0x180043428  sub     rsp, 110h
0x18004342f  mov     rax, cs:__security_cookie
0x180043436  xor     rax, rsp
0x180043439  mov     [rsp+128h+var_28], rax
0x180043441  mov     rdi, rdx
0x180043444  mov     r8d, 40h ; '@'; nMaxCount
0x18004344a  lea     rdx, [rsp+128h+ClassName]; lpClassName
0x180043452  mov     rsi, rcx
0x180043455  call    cs:__imp_GetClassNameW
0x18004345b  xor     ebp, ebp
0x18004345d  test    eax, eax
0x18004345f  jz      loc_1800434E6
0x180043465  or      r9d, 0FFFFFFFFh; cchCount1
0x180043469  lea     rax, aTooltipsClass3; "tooltips_class32"
0x180043470  mov     [rsp+128h+cchCount2], r9d; cchCount2
0x180043475  lea     r8, [rsp+128h+ClassName]; lpString1
0x18004347d  lea     edx, [rbp+1]; dwCmpFlags
0x180043480  mov     [rsp+128h+lpString2], rax; unsigned int
0x180043485  lea     ecx, [rbp+7Fh]; Locale
0x180043488  call    cs:__imp_CompareStringW
0x18004348e  cmp     eax, 2
0x180043491  jnz     short loc_1800434E6
0x180043493  mov     rbx, [rdi+10h]
0x180043497  lea     r8d, [rbp+48h]; Size
0x18004349b  xor     edx, edx; Val
0x18004349d  lea     rcx, [rsp+128h+var_F8]; void *
0x1800434a2  call    memset_0
0x1800434a7  mov     rax, [rdi]
0x1800434aa  lea     r9, [rsp+128h+var_F8]; struct tagTOOLINFOW *
0x1800434af  mov     [rsp+128h+var_F8.hwnd], rax
0x1800434b4  mov     rcx, rsi; HWND
0x1800434b7  mov     eax, [rdi+8]
0x1800434ba  mov     [rsp+128h+var_F8.uId], rax
0x1800434bf  mov     [rsp+128h+var_F8.cbSize], 40h ; '@'
0x1800434c7  mov     [rsp+128h+var_F8.lpszText], rbx
0x1800434cc  mov     [rbx], bp
0x1800434cf  call    ?XSend_ToolTip_GetItem@@YAJPEAUHWND__@@I_KPEAUtagTOOLINFOW@@I@Z; XSend_ToolTip_GetItem(HWND__ *,uint,unsigned __int64,tagTOOLINFOW *,uint)
0x1800434d4  test    eax, eax
0x1800434d6  jnz     short loc_1800434E6
0x1800434d8  mov     rcx, [rdi+10h]
0x1800434dc  mov     eax, ebp
0x1800434de  cmp     [rcx], bp
0x1800434e1  setz    al
0x1800434e4  jmp     short loc_1800434EB
0x1800434e6  mov     eax, 1
0x1800434eb  mov     rcx, [rsp+128h+var_28]
0x1800434f3  xor     rcx, rsp; StackCookie
0x1800434f6  call    __security_check_cookie
0x1800434fb  mov     rbx, [rsp+128h+arg_10]
0x180043503  add     rsp, 110h
0x18004350a  pop     rdi
0x18004350b  pop     rsi
0x18004350c  pop     rbp
0x18004350d  retn
```
