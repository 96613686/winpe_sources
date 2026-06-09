# CRichEdDoc::_OnSize(HWND__ *,uint,int,int)

- ea: `0x180066a88`
- end: `0x180066c90`
- name: `?_OnSize@CRichEdDoc@@AEAAXPEAUHWND__@@IHH@Z`
- size: `520`
- prototype: `void(CRichEdDoc *__hidden this, HWND, unsigned int, int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180064430`
- `0x180064ec0`
- `0x180065a50`
- `0x1800672f4`

## callees

- `0x180066a88`
- `0x1800706e0`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x180066ad4`
- `USER32!GetSystemMetrics` at `0x180066af8`
- `USER32!GetSystemMetrics` at `0x180066b5c`
- `USER32!GetSystemMetrics` at `0x180066b82`
- `USER32!GetSystemMetrics` at `0x180066b9a`
- `USER32!GetSystemMetrics` at `0x180066bb5`
- `USER32!GetSystemMetrics` at `0x180066bda`
- `USER32!GetSystemMetrics` at `0x180066ad4`
- `USER32!GetSystemMetrics` at `0x180066af8`
- `USER32!GetSystemMetrics` at `0x180066b5c`
- `USER32!GetSystemMetrics` at `0x180066b82`
- `USER32!GetSystemMetrics` at `0x180066b9a`
- `USER32!GetSystemMetrics` at `0x180066bb5`
- `USER32!GetSystemMetrics` at `0x180066bda`
- `USER32!SetWindowPos` at `0x180066c32`
- `USER32!SetWindowPos` at `0x180066c32`
- `USER32!InvalidateRect` at `0x180066c58`
- `USER32!InvalidateRect` at `0x180066c58`
- `USER32!UpdateWindow` at `0x180066c65`
- `USER32!UpdateWindow` at `0x180066c65`

## pseudocode

```c
void __fastcall CRichEdDoc::_OnSize(CRichEdDoc *this, HWND a2, __int64 a3, int a4, int a5)
{
  __int64 v5; // rdi
  int v8; // r15d
  void (__fastcall *v9)(__int64, _QWORD, int *); // rbx
  int SystemMetrics; // eax
  __int64 v11; // rcx
  unsigned int v12; // r12d
  __int64 v13; // rsi
  int v14; // ebx
  void (__fastcall *v15)(__int64, _QWORD, _QWORD, _QWORD, int); // rdi
  int v16; // eax
  HWND v17; // rcx
  int v18; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-54h]
  __int64 v20; // [rsp+48h] [rbp-50h] BYREF
  int v21; // [rsp+50h] [rbp-48h]
  int v22; // [rsp+54h] [rbp-44h]

  v5 = *((_QWORD *)this + 101);
  v18 = 0;
  v8 = 0;
  if ( v5 )
  {
    v9 = *(void (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v5 + 24LL);
    SystemMetrics = GetSystemMetrics(5);
    v9(v5, (unsigned int)(a4 - 4 * SystemMetrics - 6), &v18);
    v8 = v18 + 3 + 2 * GetSystemMetrics(6);
  }
  v11 = *((_QWORD *)this + 95);
  if ( v11 && *((_DWORD *)this + 187) == 1 )
  {
    v20 = 0;
    v21 = a4;
    v22 = a5;
    (*(void (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v11 + 56LL))(v11, &v20, 0, 0);
  }
  else
  {
    if ( *((_QWORD *)this + 101) )
      v8 += 2 * GetSystemMetrics(6) + 3;
    *((_DWORD *)this + 186) = 0;
  }
  if ( *((_QWORD *)this + 101) )
  {
    v19 = a4 - 4 * GetSystemMetrics(5) - 6;
    GetSystemMetrics(6);
    v12 = *((_DWORD *)this + 186);
    if ( *((_DWORD *)this + 187) != 1 )
      v12 += 2 * GetSystemMetrics(6) + 3;
    v13 = *((_QWORD *)this + 101);
    v14 = v18;
    v15 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v13 + 32LL);
    v16 = GetSystemMetrics(5);
    v15(v13, (unsigned int)(2 * v16 + 3), v12, v19, v14);
  }
  *((_DWORD *)this + 186) += v8;
  v17 = (HWND)*((_QWORD *)this + 92);
  if ( v17 )
  {
    SetWindowPos(v17, 0, 0, *((_DWORD *)this + 186), a4, a5 - *((_DWORD *)this + 186), 0x14u);
    ResizePhishingBlockerWindow(*((HWND *)this + 92), *((struct IInfoWindow **)this + 101));
  }
  InvalidateRect(*((HWND *)this + 20), 0, 1);
  UpdateWindow(*((HWND *)this + 20));
}

```

## disassembly

```asm
0x180066a88  mov     [rsp+arg_8], rbx
0x180066a8d  push    rbp
0x180066a8e  push    rsi
0x180066a8f  push    rdi
0x180066a90  push    r12
0x180066a92  push    r13
0x180066a94  push    r14
0x180066a96  push    r15
0x180066a98  sub     rsp, 60h
0x180066a9c  mov     rax, cs:__security_cookie
0x180066aa3  xor     rax, rsp
0x180066aa6  mov     [rsp+98h+var_40], rax
0x180066aab  mov     rdi, [rcx+328h]
0x180066ab2  xor     esi, esi
0x180066ab4  mov     [rsp+98h+var_58], esi
0x180066ab8  mov     r13d, r9d
0x180066abb  mov     rbp, rcx
0x180066abe  mov     r15d, esi
0x180066ac1  lea     r12d, [rsi+6]
0x180066ac5  test    rdi, rdi
0x180066ac8  jz      short loc_180066B0B
0x180066aca  mov     rax, [rdi]
0x180066acd  lea     ecx, [rsi+5]; nIndex
0x180066ad0  mov     rbx, [rax+18h]
0x180066ad4  call    cs:__imp_GetSystemMetrics
0x180066ada  shl     eax, 2
0x180066add  mov     edx, r13d
0x180066ae0  sub     edx, eax
0x180066ae2  lea     r8, [rsp+98h+var_58]
0x180066ae7  sub     edx, r12d
0x180066aea  mov     rcx, rdi
0x180066aed  mov     rax, rbx
0x180066af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066af5  mov     ecx, r12d; nIndex
0x180066af8  call    cs:__imp_GetSystemMetrics
0x180066afe  mov     r15d, [rsp+98h+var_58]
0x180066b03  add     r15d, 3
0x180066b07  lea     r15d, [r15+rax*2]
0x180066b0b  mov     rcx, [rbp+2F8h]
0x180066b12  mov     r14d, [rsp+98h+arg_20]
0x180066b1a  test    rcx, rcx
0x180066b1d  jz      short loc_180066B50
0x180066b1f  cmp     dword ptr [rbp+2ECh], 1
0x180066b26  jnz     short loc_180066B50
0x180066b28  mov     [rsp+98h+var_50], rsi
0x180066b2d  lea     rdx, [rsp+98h+var_50]
0x180066b32  mov     [rsp+98h+var_48], r13d
0x180066b37  xor     r9d, r9d
0x180066b3a  mov     [rsp+98h+var_44], r14d
0x180066b3f  xor     r8d, r8d
0x180066b42  mov     rax, [rcx]
0x180066b45  mov     rax, [rax+38h]
0x180066b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b4e  jmp     short loc_180066B70
0x180066b50  cmp     [rbp+328h], rsi
0x180066b57  jz      short loc_180066B6A
0x180066b59  mov     ecx, r12d; nIndex
0x180066b5c  call    cs:__imp_GetSystemMetrics
0x180066b62  lea     r15d, [r15+rax*2]
0x180066b66  add     r15d, 3
0x180066b6a  mov     [rbp+2E8h], esi
0x180066b70  cmp     [rbp+328h], rsi
0x180066b77  jz      loc_180066BFE
0x180066b7d  mov     ecx, 5; nIndex
0x180066b82  call    cs:__imp_GetSystemMetrics
0x180066b88  shl     eax, 2
0x180066b8b  mov     edx, r13d
0x180066b8e  sub     edx, eax
0x180066b90  mov     ecx, r12d; nIndex
0x180066b93  lea     eax, [rdx-6]
0x180066b96  mov     [rsp+98h+var_54], eax
0x180066b9a  call    cs:__imp_GetSystemMetrics
0x180066ba0  cmp     dword ptr [rbp+2ECh], 1
0x180066ba7  mov     r12d, [rbp+2E8h]
0x180066bae  jz      short loc_180066BC3
0x180066bb0  mov     ecx, 6; nIndex
0x180066bb5  call    cs:__imp_GetSystemMetrics
0x180066bbb  lea     r12d, [r12+rax*2]
0x180066bbf  add     r12d, 3
0x180066bc3  mov     rsi, [rbp+328h]
0x180066bca  mov     ecx, 5; nIndex
0x180066bcf  mov     ebx, [rsp+98h+var_58]
0x180066bd3  mov     rax, [rsi]
0x180066bd6  mov     rdi, [rax+20h]
0x180066bda  call    cs:__imp_GetSystemMetrics
0x180066be0  mov     r9d, [rsp+98h+var_54]
0x180066be5  mov     r8d, r12d
0x180066be8  mov     rcx, rsi
0x180066beb  mov     [rsp+98h+var_78], ebx
0x180066bef  lea     edx, ds:3[rax*2]
0x180066bf6  mov     rax, rdi
0x180066bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bfe  add     [rbp+2E8h], r15d
0x180066c05  mov     rcx, [rbp+2E0h]; hWnd
0x180066c0c  mov     r9d, [rbp+2E8h]; Y
0x180066c13  test    rcx, rcx
0x180066c16  jz      short loc_180066C4B
0x180066c18  sub     r14d, r9d
0x180066c1b  mov     [rsp+98h+uFlags], 14h; uFlags
0x180066c23  mov     [rsp+98h+cy], r14d; cy
0x180066c28  xor     r8d, r8d; X
0x180066c2b  xor     edx, edx; hWndInsertAfter
0x180066c2d  mov     [rsp+98h+var_78], r13d; cx
0x180066c32  call    cs:__imp_SetWindowPos
0x180066c38  mov     rdx, [rbp+328h]; struct IInfoWindow *
0x180066c3f  mov     rcx, [rbp+2E0h]; hWndFrom
0x180066c46  call    ?ResizePhishingBlockerWindow@@YAXPEAUHWND__@@PEAUIInfoWindow@@@Z; ResizePhishingBlockerWindow(HWND__ *,IInfoWindow *)
0x180066c4b  mov     rcx, [rbp+0A0h]; hWnd
0x180066c52  xor     edx, edx; lpRect
0x180066c54  lea     r8d, [rdx+1]; bErase
0x180066c58  call    cs:__imp_InvalidateRect
0x180066c5e  mov     rcx, [rbp+0A0h]; hWnd
0x180066c65  call    cs:__imp_UpdateWindow
0x180066c6b  mov     rcx, [rsp+98h+var_40]
0x180066c70  xor     rcx, rsp; StackCookie
0x180066c73  call    __security_check_cookie
0x180066c78  mov     rbx, [rsp+98h+arg_8]
0x180066c80  add     rsp, 60h
0x180066c84  pop     r15
0x180066c86  pop     r14
0x180066c88  pop     r13
0x180066c8a  pop     r12
0x180066c8c  pop     rdi
0x180066c8d  pop     rsi
0x180066c8e  pop     rbp
0x180066c8f  retn
```
