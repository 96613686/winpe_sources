# FlatSB_SetScrollInfo

- ea: `0x180034450`
- end: `0x180034554`
- name: `FlatSB_SetScrollInfo`
- size: `260`
- prototype: `int __stdcall(HWND, int code, LPSCROLLINFO psi, BOOL fRedraw)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005b7fc`

## callees

- `0x180030440`
- `0x180030800`
- `0x1800330c4`
- `0x180033a40`
- `0x180034450`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800344fa`
- `GDI32!DeleteObject` at `0x180034507`
- `GDI32!DeleteObject` at `0x1800344fa`
- `GDI32!DeleteObject` at `0x180034507`
- `KERNEL32!LocalFree` at `0x180034510`
- `KERNEL32!LocalFree` at `0x180034510`
- `USER32!SetScrollInfo` at `0x1800344b3`
- `USER32!SetScrollInfo` at `0x1800344b3`

## pseudocode

```c
int __stdcall FlatSB_SetScrollInfo(HWND a1, int code, LPSCROLLINFO psi, BOOL fRedraw)
{
  HGDIOBJ *v8; // rbx
  char *inited; // rax
  DWORD_PTR v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  if ( !psi || psi->cbSize < 0x1C )
    return 0;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &v11);
  v8 = (HGDIOBJ *)v11;
  if ( !v11 )
    return SetScrollInfo(a1, code, psi, fRedraw);
  if ( v11 == -1 )
  {
    fRedraw = 1;
    if ( (psi->fMask & 1) == 0 )
      return 0;
    inited = FlatSB_Internal_InitPwSB((__int64)a1);
    v8 = (HGDIOBJ *)inited;
    if ( !inited )
      return 0;
    if ( !SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, (DWORD_PTR)inited) )
    {
      DeleteObject(v8[31]);
      DeleteObject(v8[30]);
      LocalFree(v8);
      return 0;
    }
  }
  else if ( a1 != *(HWND *)(v11 + 264) )
  {
    return 0;
  }
  if ( psi->fMask == 4 )
    psi->fMask = 20;
  return FlatSB_Internal_SetScrollBar(v8, (unsigned int)code, psi, fRedraw);
}

```

## disassembly

```asm
0x180034450  mov     rax, rsp
0x180034453  mov     [rax+8], rbx
0x180034457  mov     [rax+10h], rbp
0x18003445b  push    rsi
0x18003445c  push    rdi
0x18003445d  push    r14
0x18003445f  sub     rsp, 20h
0x180034463  mov     qword ptr [rax+18h], 0
0x18003446b  mov     ebp, r9d
0x18003446e  mov     rdi, r8
0x180034471  mov     r14d, edx
0x180034474  mov     rsi, rcx
0x180034477  test    r8, r8
0x18003447a  jz      loc_180034516
0x180034480  cmp     dword ptr [r8], 1Ch
0x180034484  jb      loc_180034516
0x18003448a  lea     r9, [rax+18h]; pdwRefData
0x18003448e  xor     r8d, r8d; uIdSubclass
0x180034491  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034498  call    GetWindowSubclass
0x18003449d  mov     rbx, [rsp+38h+arg_10]
0x1800344a2  test    rbx, rbx
0x1800344a5  jnz     short loc_1800344BB
0x1800344a7  mov     r9d, ebp; redraw
0x1800344aa  mov     r8, rdi; lpsi
0x1800344ad  mov     edx, r14d; nBar
0x1800344b0  mov     rcx, rsi; hwnd
0x1800344b3  call    cs:__imp_SetScrollInfo
0x1800344b9  jmp     short loc_180034518
0x1800344bb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800344bf  jnz     short loc_18003452B
0x1800344c1  lea     ebp, [rbx+2]
0x1800344c4  test    [rdi+4], bpl
0x1800344c8  jz      short loc_180034516
0x1800344ca  mov     rcx, rsi
0x1800344cd  call    FlatSB_Internal_InitPwSB
0x1800344d2  mov     rbx, rax
0x1800344d5  test    rax, rax
0x1800344d8  jz      short loc_180034516
0x1800344da  mov     r9, rax; dwRefData
0x1800344dd  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x1800344e4  xor     r8d, r8d; uIdSubclass
0x1800344e7  mov     rcx, rsi; hWnd
0x1800344ea  call    SetWindowSubclass
0x1800344ef  test    eax, eax
0x1800344f1  jnz     short loc_180034534
0x1800344f3  mov     rcx, [rbx+0F8h]; ho
0x1800344fa  call    cs:__imp_DeleteObject
0x180034500  mov     rcx, [rbx+0F0h]; ho
0x180034507  call    cs:__imp_DeleteObject
0x18003450d  mov     rcx, rbx; hMem
0x180034510  call    cs:__imp_LocalFree
0x180034516  xor     eax, eax
0x180034518  mov     rbx, [rsp+38h+arg_0]
0x18003451d  mov     rbp, [rsp+38h+arg_8]
0x180034522  add     rsp, 20h
0x180034526  pop     r14
0x180034528  pop     rdi
0x180034529  pop     rsi
0x18003452a  retn
0x18003452b  cmp     rsi, [rbx+108h]
0x180034532  jnz     short loc_180034516
0x180034534  cmp     dword ptr [rdi+4], 4
0x180034538  jnz     short loc_180034541
0x18003453a  mov     dword ptr [rdi+4], 14h
0x180034541  mov     r9d, ebp
0x180034544  mov     r8, rdi
0x180034547  mov     edx, r14d
0x18003454a  mov     rcx, rbx
0x18003454d  call    FlatSB_Internal_SetScrollBar
0x180034552  jmp     short loc_180034518
```
