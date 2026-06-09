# CAdvIpcfgDlg::CopyListToClipboard(void)

- ea: `0x180058edc`
- end: `0x18005911f`
- name: `?CopyListToClipboard@CAdvIpcfgDlg@@AEAAXXZ`
- size: `579`
- prototype: `void __fastcall(CAdvIpcfgDlg *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005ab00`

## callees

- `0x180017b50`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x18002b5e8`
- `0x18002b82c`
- `0x180058edc`
- `0x180062130`

## import_xrefs

- `USER32!SendMessageW` at `0x180058f51`
- `USER32!SendMessageW` at `0x180058f9d`
- `USER32!SendMessageW` at `0x180059052`
- `USER32!SendMessageW` at `0x180058f51`
- `USER32!SendMessageW` at `0x180058f9d`
- `USER32!SendMessageW` at `0x180059052`
- `USER32!OpenClipboard` at `0x1800590bb`
- `USER32!OpenClipboard` at `0x1800590bb`
- `USER32!EmptyClipboard` at `0x1800590d0`
- `USER32!EmptyClipboard` at `0x1800590d0`
- `USER32!SetClipboardData` at `0x1800590de`
- `USER32!SetClipboardData` at `0x1800590de`
- `USER32!CloseClipboard` at `0x1800590e4`
- `USER32!CloseClipboard` at `0x1800590e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180059090`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180059090`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800590c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800590c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAdvIpcfgDlg::CopyListToClipboard(HWND *this)
{
  int v2; // ebx
  int v3; // edi
  __int64 v4; // rax
  __int64 v5; // r8
  __int64 v6; // r8
  SIZE_T v7; // rdi
  HLOCAL v8; // rax
  void *v9; // rbx
  void **v10; // rdx
  LPARAM lParam; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+28h] [rbp-D8h]
  _WORD *v13; // [rsp+38h] [rbp-C8h]
  int v14; // [rsp+40h] [rbp-C0h]
  void *Src[2]; // [rsp+80h] [rbp-80h] BYREF
  int v16; // [rsp+90h] [rbp-70h]
  unsigned __int64 v17; // [rsp+98h] [rbp-68h]
  _WORD v18[256]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(v18, 0, sizeof(v18));
  v2 = -1;
  std::wstring::wstring(Src, &Caption);
  v3 = 1;
  while ( 1 )
  {
    v2 = SendMessageW(this[10], 0x100Cu, v2, 0);
    if ( v2 == -1 )
      break;
    v18[0] = 0;
    memset_0(&lParam, 0, 0x58u);
    v14 = 255;
    v13 = v18;
    SendMessageW(this[10], 0x1073u, v2, (LPARAM)&lParam);
    v4 = -1;
    do
      ++v4;
    while ( v18[v4] );
    if ( v4 )
    {
      if ( v3 )
        v3 = 0;
      else
        std::wstring::_Append<unsigned short>(Src);
      v5 = -1;
      do
        ++v5;
      while ( v18[v5] );
      std::wstring::_Append<unsigned short>(Src);
    }
    std::wstring::_Append<unsigned short>(Src);
    v18[0] = 0;
    memset_0(&lParam, 0, 0x58u);
    v12 = 1;
    v14 = 255;
    v13 = v18;
    SendMessageW(this[10], 0x1073u, v2, (LPARAM)&lParam);
    v6 = -1;
    do
      ++v6;
    while ( v18[v6] );
    std::wstring::_Append<unsigned short>(Src);
  }
  v7 = 2 * v16 + 2;
  v8 = LocalAlloc(0x40u, v7);
  v9 = v8;
  if ( v8 )
  {
    v10 = Src;
    if ( v17 > 7 )
      v10 = (void **)Src[0];
    memcpy_0(v8, v10, v7);
    if ( OpenClipboard(this[1]) )
    {
      EmptyClipboard();
      SetClipboardData(0xDu, v9);
      CloseClipboard();
    }
    else
    {
      LocalFree(v9);
    }
  }
  std::wstring::_Tidy_deallocate((__int64)Src);
}

```

## disassembly

```asm
0x180058edc  mov     [rsp-8+arg_8], rbx
0x180058ee1  mov     [rsp-8+arg_10], rsi
0x180058ee6  push    rbp
0x180058ee7  push    rdi
0x180058ee8  push    r12
0x180058eea  push    r14
0x180058eec  push    r15
0x180058eee  lea     rbp, [rsp-1B0h]
0x180058ef6  sub     rsp, 2B0h
0x180058efd  mov     rax, cs:__security_cookie
0x180058f04  xor     rax, rsp
0x180058f07  mov     [rbp+1D0h+var_30], rax
0x180058f0e  mov     rsi, rcx
0x180058f11  xor     edx, edx; Val
0x180058f13  mov     r8d, 200h; Size
0x180058f19  lea     rcx, [rbp+1D0h+var_230]; void *
0x180058f1d  call    memset_0
0x180058f22  or      r12, 0FFFFFFFFFFFFFFFFh
0x180058f26  mov     ebx, r12d
0x180058f29  lea     rdx, Caption
0x180058f30  lea     rcx, [rbp+1D0h+Src]
0x180058f34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180058f39  nop
0x180058f3a  lea     edi, [r12+2]
0x180058f3f  xor     r15d, r15d
0x180058f42  movsxd  r8, ebx; wParam
0x180058f45  xor     r9d, r9d; lParam
0x180058f48  mov     edx, 100Ch; Msg
0x180058f4d  mov     rcx, [rsi+50h]; hWnd
0x180058f51  call    cs:__imp_SendMessageW
0x180058f57  mov     rbx, rax
0x180058f5a  cmp     eax, r12d
0x180058f5d  jz      loc_18005907B
0x180058f63  mov     [rbp+1D0h+var_230], r15w
0x180058f68  xor     edx, edx; Val
0x180058f6a  lea     r8d, [rdx+58h]; Size
0x180058f6e  lea     rcx, [rsp+2D0h+lParam]; void *
0x180058f73  call    memset_0
0x180058f78  mov     [rsp+2D0h+var_290], 0FFh
0x180058f80  lea     rax, [rbp+1D0h+var_230]
0x180058f84  mov     [rsp+2D0h+var_298], rax
0x180058f89  movsxd  r14, ebx
0x180058f8c  lea     r9, [rsp+2D0h+lParam]; lParam
0x180058f91  mov     r8, r14; wParam
0x180058f94  mov     edx, 1073h; Msg
0x180058f99  mov     rcx, [rsi+50h]; hWnd
0x180058f9d  call    cs:__imp_SendMessageW
0x180058fa3  lea     rcx, [rbp+1D0h+var_230]
0x180058fa7  mov     rax, r12
0x180058faa  inc     rax
0x180058fad  cmp     [rcx+rax*2], r15w
0x180058fb2  jnz     short loc_180058FAA
0x180058fb4  test    rax, rax
0x180058fb7  jnz     short loc_180058FC2
0x180058fb9  lea     rdx, asc_18007BB60; ", "
0x180058fc0  jmp     short loc_180059004
0x180058fc2  test    edi, edi
0x180058fc4  jnz     short loc_180058FDC
0x180058fc6  lea     r8d, [rdi+2]
0x180058fca  lea     rdx, asc_18007BB68; "\r\n"
0x180058fd1  lea     rcx, [rbp+1D0h+Src]; Src
0x180058fd5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180058fda  jmp     short loc_180058FDF
0x180058fdc  mov     edi, r15d
0x180058fdf  lea     rax, [rbp+1D0h+var_230]
0x180058fe3  mov     r8, r12
0x180058fe6  inc     r8
0x180058fe9  cmp     [rax+r8*2], r15w
0x180058fee  jnz     short loc_180058FE6
0x180058ff0  lea     rdx, [rbp+1D0h+var_230]
0x180058ff4  lea     rcx, [rbp+1D0h+Src]; Src
0x180058ff8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180058ffd  lea     rdx, asc_18007BB58; ": "
0x180059004  mov     r8d, 2
0x18005900a  lea     rcx, [rbp+1D0h+Src]; Src
0x18005900e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180059013  mov     [rbp+1D0h+var_230], r15w
0x180059018  xor     edx, edx; Val
0x18005901a  lea     r8d, [rdx+58h]; Size
0x18005901e  lea     rcx, [rsp+2D0h+lParam]; void *
0x180059023  call    memset_0
0x180059028  mov     [rsp+2D0h+var_2A8], 1
0x180059030  mov     [rsp+2D0h+var_290], 0FFh
0x180059038  lea     rax, [rbp+1D0h+var_230]
0x18005903c  mov     [rsp+2D0h+var_298], rax
0x180059041  lea     r9, [rsp+2D0h+lParam]; lParam
0x180059046  mov     r8, r14; wParam
0x180059049  mov     edx, 1073h; Msg
0x18005904e  mov     rcx, [rsi+50h]; hWnd
0x180059052  call    cs:__imp_SendMessageW
0x180059058  lea     rax, [rbp+1D0h+var_230]
0x18005905c  mov     r8, r12
0x18005905f  inc     r8
0x180059062  cmp     [rax+r8*2], r15w
0x180059067  jnz     short loc_18005905F
0x180059069  lea     rdx, [rbp+1D0h+var_230]
0x18005906d  lea     rcx, [rbp+1D0h+Src]; Src
0x180059071  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180059076  jmp     loc_180058F42
0x18005907b  mov     eax, [rbp+1D0h+var_240]
0x18005907e  lea     eax, ds:2[rax*2]
0x180059085  movsxd  rdi, eax
0x180059088  mov     rdx, rdi; uBytes
0x18005908b  mov     ecx, 40h ; '@'; uFlags
0x180059090  call    cs:__imp_LocalAlloc
0x180059096  mov     rbx, rax
0x180059099  test    rax, rax
0x18005909c  jz      short loc_1800590EB
0x18005909e  lea     rdx, [rbp+1D0h+Src]
0x1800590a2  cmp     [rbp+1D0h+var_238], 7
0x1800590a7  cmova   rdx, [rbp+1D0h+Src]; Src
0x1800590ac  mov     r8, rdi; Size
0x1800590af  mov     rcx, rax; void *
0x1800590b2  call    memcpy_0
0x1800590b7  mov     rcx, [rsi+8]; hWndNewOwner
0x1800590bb  call    cs:__imp_OpenClipboard
0x1800590c1  test    eax, eax
0x1800590c3  jnz     short loc_1800590D0
0x1800590c5  mov     rcx, rbx; hMem
0x1800590c8  call    cs:__imp_LocalFree
0x1800590ce  jmp     short loc_1800590EB
0x1800590d0  call    cs:__imp_EmptyClipboard
0x1800590d6  mov     rdx, rbx; hMem
0x1800590d9  mov     ecx, 0Dh; uFormat
0x1800590de  call    cs:__imp_SetClipboardData
0x1800590e4  call    cs:__imp_CloseClipboard
0x1800590ea  nop
0x1800590eb  lea     rcx, [rbp+1D0h+Src]
0x1800590ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800590f4  mov     rcx, [rbp+1D0h+var_30]
0x1800590fb  xor     rcx, rsp; StackCookie
0x1800590fe  call    __security_check_cookie
0x180059103  lea     r11, [rsp+2D0h+var_20]
0x18005910b  mov     rbx, [r11+38h]
0x18005910f  mov     rsi, [r11+40h]
0x180059113  mov     rsp, r11
0x180059116  pop     r15
0x180059118  pop     r14
0x18005911a  pop     r12
0x18005911c  pop     rdi
0x18005911d  pop     rbp
0x18005911e  retn
```
