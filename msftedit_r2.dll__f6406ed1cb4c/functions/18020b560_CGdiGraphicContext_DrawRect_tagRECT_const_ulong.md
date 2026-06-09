# CGdiGraphicContext::DrawRect(tagRECT const &,ulong *)

- ea: `0x18020b560`
- end: `0x18020b633`
- name: `?DrawRect@CGdiGraphicContext@@EEBA_NAEBUtagRECT@@PEAK@Z`
- size: `211`
- prototype: `bool __fastcall(CGdiGraphicContext *__hidden this, const struct tagRECT *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18020b560`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b597`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b5be`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b5f7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b60a`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b597`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b5be`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b5f7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18020b60a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18020b619`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18020b619`

## pseudocode

```c
bool __fastcall CGdiGraphicContext::DrawRect(HDC *this, const struct tagRECT *a2, unsigned int *a3)
{
  void *v5; // rax
  void *v6; // rsi
  HGDIOBJ v7; // rdi
  void *v8; // rax
  HGDIOBJ v9; // rbx

  v5 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))pfnCreatePen)(0, 0, *a3);
  v6 = v5;
  if ( v5 )
  {
    v7 = SelectObject(this[3], v5);
    v8 = (void *)((__int64 (__fastcall *)(__int64))pfnGetStockObject)(5);
    v9 = SelectObject(this[3], v8);
    ((void (__fastcall *)(HDC, _QWORD, _QWORD, _QWORD, LONG))pfnRectangle)(
      this[3],
      (unsigned int)a2->left,
      (unsigned int)a2->top,
      (unsigned int)a2->right,
      a2->bottom);
    SelectObject(this[3], v9);
    SelectObject(this[3], v7);
    DeleteObject(v6);
    LOBYTE(v5) = 1;
  }
  return (char)v5;
}

```

## disassembly

```asm
0x18020b560  push    rbx
0x18020b562  push    rbp
0x18020b563  push    rsi
0x18020b564  push    rdi
0x18020b565  push    r14
0x18020b567  sub     rsp, 30h
0x18020b56b  mov     r8d, [r8]
0x18020b56e  mov     r14, rdx
0x18020b571  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x18020b578  mov     rbp, rcx
0x18020b57b  xor     edx, edx
0x18020b57d  xor     ecx, ecx
0x18020b57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020b584  mov     rsi, rax
0x18020b587  test    rax, rax
0x18020b58a  jz      loc_18020B627
0x18020b590  mov     rcx, [rbp+18h]; hdc
0x18020b594  mov     rdx, rax; h
0x18020b597  call    cs:__imp_SelectObject
0x18020b59e  nop     dword ptr [rax+rax+00h]
0x18020b5a3  mov     rdi, rax
0x18020b5a6  mov     ecx, 5
0x18020b5ab  mov     rax, cs:?pfnGetStockObject@@3P6A_JXZEA; __int64 (*pfnGetStockObject)(void)
0x18020b5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020b5b7  mov     rcx, [rbp+18h]; hdc
0x18020b5bb  mov     rdx, rax; h
0x18020b5be  call    cs:__imp_SelectObject
0x18020b5c5  nop     dword ptr [rax+rax+00h]
0x18020b5ca  mov     ecx, [r14+0Ch]
0x18020b5ce  mov     rbx, rax
0x18020b5d1  mov     rax, cs:?pfnRectangle@@3P6A_JXZEA; __int64 (*pfnRectangle)(void)
0x18020b5d8  mov     r9d, [r14+8]
0x18020b5dc  mov     r8d, [r14+4]
0x18020b5e0  mov     edx, [r14]
0x18020b5e3  mov     [rsp+58h+var_38], ecx
0x18020b5e7  mov     rcx, [rbp+18h]
0x18020b5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020b5f0  mov     rcx, [rbp+18h]; hdc
0x18020b5f4  mov     rdx, rbx; h
0x18020b5f7  call    cs:__imp_SelectObject
0x18020b5fe  nop     dword ptr [rax+rax+00h]
0x18020b603  mov     rcx, [rbp+18h]; hdc
0x18020b607  mov     rdx, rdi; h
0x18020b60a  call    cs:__imp_SelectObject
0x18020b611  nop     dword ptr [rax+rax+00h]
0x18020b616  mov     rcx, rsi; ho
0x18020b619  call    cs:__imp_DeleteObject
0x18020b620  nop     dword ptr [rax+rax+00h]
0x18020b625  mov     al, 1
0x18020b627  add     rsp, 30h
0x18020b62b  pop     r14
0x18020b62d  pop     rdi
0x18020b62e  pop     rsi
0x18020b62f  pop     rbp
0x18020b630  pop     rbx
0x18020b631  retn
```
