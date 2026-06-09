# InitializeFlatSB

- ea: `0x180034cd0`
- end: `0x180034e71`
- name: `InitializeFlatSB`
- size: `417`
- prototype: `BOOL __stdcall(HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800529fc`

## callees

- `0x1800115f0`
- `0x180018090`
- `0x180030440`
- `0x180030800`
- `0x1800330c4`
- `0x180033a40`
- `0x180034cd0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180034df6`
- `GDI32!DeleteObject` at `0x180034e03`
- `GDI32!DeleteObject` at `0x180034df6`
- `GDI32!DeleteObject` at `0x180034e03`
- `KERNEL32!LocalFree` at `0x180034e0c`
- `KERNEL32!LocalFree` at `0x180034e0c`
- `USER32!GetWindowLongW` at `0x180034d16`
- `USER32!GetWindowLongW` at `0x180034d16`
- `USER32!GetScrollInfo` at `0x180034d41`
- `USER32!GetScrollInfo` at `0x180034d5c`
- `USER32!GetScrollInfo` at `0x180034d41`
- `USER32!GetScrollInfo` at `0x180034d5c`

## pseudocode

```c
BOOL __stdcall InitializeFlatSB(HWND a1)
{
  BOOL ScrollInfo; // r14d
  BOOL v3; // r15d
  LONG WindowLongW; // esi
  DWORD_PTR v5; // rbx
  char *inited; // rax
  DWORD_PTR pdwRefData; // [rsp+20h] [rbp-58h] BYREF
  struct tagSCROLLINFO v9; // [rsp+28h] [rbp-50h] BYREF
  struct tagSCROLLINFO v10; // [rsp+48h] [rbp-30h] BYREF

  pdwRefData = 0;
  memset(&v9, 0, sizeof(v9));
  ScrollInfo = 0;
  memset(&v10, 0, sizeof(v10));
  v3 = 0;
  WindowLongW = GetWindowLongW(a1, -16);
  v9.cbSize = 28;
  v10.cbSize = 28;
  v9.fMask = 31;
  v10.fMask = 31;
  if ( (WindowLongW & 0x100000) != 0 )
    ScrollInfo = GetScrollInfo(a1, 0, &v9);
  if ( (WindowLongW & 0x200000) != 0 )
    v3 = GetScrollInfo(a1, 1, &v10);
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &pdwRefData);
  if ( v3 || ScrollInfo )
  {
    v5 = pdwRefData;
    if ( ((pdwRefData + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      inited = FlatSB_Internal_InitPwSB((__int64)a1);
      v5 = (DWORD_PTR)inited;
      if ( !inited )
        return 0;
      if ( !SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, (DWORD_PTR)inited) )
      {
        DeleteObject(*(HGDIOBJ *)(v5 + 248));
        DeleteObject(*(HGDIOBJ *)(v5 + 240));
        LocalFree((HLOCAL)v5);
        return 0;
      }
    }
    *(_DWORD *)(v5 + 8) = WindowLongW & 0x300000;
    if ( ScrollInfo )
      FlatSB_Internal_SetScrollBar(v5, 0, &v9, 0);
    if ( v3 )
      FlatSB_Internal_SetScrollBar(v5, 1, &v10, 0);
    CCInvalidateFrame(a1);
    return 1;
  }
  return pdwRefData || SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, 0xFFFFFFFFFFFFFFFFuLL);
}

```

## disassembly

```asm
0x180034cd0  push    rbp
0x180034cd2  push    rbx
0x180034cd3  push    rsi
0x180034cd4  push    rdi
0x180034cd5  push    r14
0x180034cd7  push    r15
0x180034cd9  mov     rbp, rsp
0x180034cdc  sub     rsp, 78h
0x180034ce0  mov     rax, cs:__security_cookie
0x180034ce7  xor     rax, rsp
0x180034cea  mov     [rbp+var_10], rax
0x180034cee  xor     eax, eax
0x180034cf0  xorps   xmm0, xmm0
0x180034cf3  xorps   xmm1, xmm1
0x180034cf6  mov     [rbp+pdwRefData], rax
0x180034cfa  movups  xmmword ptr [rbp+var_50.cbSize], xmm0
0x180034cfe  mov     rdi, rcx
0x180034d01  xor     r14d, r14d
0x180034d04  movups  xmmword ptr [rbp+var_30.cbSize], xmm1
0x180034d08  lea     edx, [rax-10h]; nIndex
0x180034d0b  xor     r15d, r15d
0x180034d0e  movups  xmmword ptr [rbp+var_50.nMax], xmm0
0x180034d12  movups  xmmword ptr [rbp+var_30.nMax], xmm1
0x180034d16  call    cs:__imp_GetWindowLongW
0x180034d1c  mov     esi, eax
0x180034d1e  lea     eax, [r14+1Ch]
0x180034d22  mov     [rbp+var_50.cbSize], eax
0x180034d25  mov     [rbp+var_30.cbSize], eax
0x180034d28  lea     eax, [r14+1Fh]
0x180034d2c  mov     [rbp+var_50.fMask], eax
0x180034d2f  mov     [rbp+var_30.fMask], eax
0x180034d32  bt      esi, 14h
0x180034d36  jnb     short loc_180034D4A
0x180034d38  lea     r8, [rbp+var_50]; lpsi
0x180034d3c  xor     edx, edx; nBar
0x180034d3e  mov     rcx, rdi; hwnd
0x180034d41  call    cs:__imp_GetScrollInfo
0x180034d47  mov     r14d, eax
0x180034d4a  bt      esi, 15h
0x180034d4e  jnb     short loc_180034D65
0x180034d50  lea     r8, [rbp+var_30]; lpsi
0x180034d54  mov     edx, 1; nBar
0x180034d59  mov     rcx, rdi; hwnd
0x180034d5c  call    cs:__imp_GetScrollInfo
0x180034d62  mov     r15d, eax
0x180034d65  lea     r9, [rbp+pdwRefData]; pdwRefData
0x180034d69  xor     r8d, r8d; uIdSubclass
0x180034d6c  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034d73  mov     rcx, rdi; hWnd
0x180034d76  call    GetWindowSubclass
0x180034d7b  test    r15d, r15d
0x180034d7e  jnz     short loc_180034DAF
0x180034d80  test    r14d, r14d
0x180034d83  jnz     short loc_180034DAF
0x180034d85  cmp     [rbp+pdwRefData], 0
0x180034d8a  jnz     loc_180034E53
0x180034d90  or      r9, 0FFFFFFFFFFFFFFFFh; dwRefData
0x180034d94  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034d9b  xor     r8d, r8d; uIdSubclass
0x180034d9e  mov     rcx, rdi; hWnd
0x180034da1  call    SetWindowSubclass
0x180034da6  test    eax, eax
0x180034da8  jz      short loc_180034DCF
0x180034daa  jmp     loc_180034E53
0x180034daf  mov     rbx, [rbp+pdwRefData]
0x180034db3  lea     rax, [rbx+1]
0x180034db7  test    rax, 0FFFFFFFFFFFFFFFEh
0x180034dbd  jnz     short loc_180034E14
0x180034dbf  mov     rcx, rdi
0x180034dc2  call    FlatSB_Internal_InitPwSB
0x180034dc7  mov     rbx, rax
0x180034dca  test    rax, rax
0x180034dcd  jnz     short loc_180034DD6
0x180034dcf  xor     eax, eax
0x180034dd1  jmp     loc_180034E58
0x180034dd6  mov     r9, rbx; dwRefData
0x180034dd9  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034de0  xor     r8d, r8d; uIdSubclass
0x180034de3  mov     rcx, rdi; hWnd
0x180034de6  call    SetWindowSubclass
0x180034deb  test    eax, eax
0x180034ded  jnz     short loc_180034E14
0x180034def  mov     rcx, [rbx+0F8h]; ho
0x180034df6  call    cs:__imp_DeleteObject
0x180034dfc  mov     rcx, [rbx+0F0h]; ho
0x180034e03  call    cs:__imp_DeleteObject
0x180034e09  mov     rcx, rbx; hMem
0x180034e0c  call    cs:__imp_LocalFree
0x180034e12  jmp     short loc_180034DCF
0x180034e14  and     esi, 300000h
0x180034e1a  mov     [rbx+8], esi
0x180034e1d  test    r14d, r14d
0x180034e20  jz      short loc_180034E33
0x180034e22  xor     r9d, r9d
0x180034e25  lea     r8, [rbp+var_50]
0x180034e29  xor     edx, edx
0x180034e2b  mov     rcx, rbx
0x180034e2e  call    FlatSB_Internal_SetScrollBar
0x180034e33  test    r15d, r15d
0x180034e36  jz      short loc_180034E4B
0x180034e38  xor     r9d, r9d
0x180034e3b  lea     r8, [rbp+var_30]
0x180034e3f  mov     rcx, rbx
0x180034e42  lea     edx, [r9+1]
0x180034e46  call    FlatSB_Internal_SetScrollBar
0x180034e4b  mov     rcx, rdi
0x180034e4e  call    CCInvalidateFrame
0x180034e53  mov     eax, 1
0x180034e58  mov     rcx, [rbp+var_10]
0x180034e5c  xor     rcx, rsp; StackCookie
0x180034e5f  call    __security_check_cookie
0x180034e64  add     rsp, 78h
0x180034e68  pop     r15
0x180034e6a  pop     r14
0x180034e6c  pop     rdi
0x180034e6d  pop     rsi
0x180034e6e  pop     rbx
0x180034e6f  pop     rbp
0x180034e70  retn
```
