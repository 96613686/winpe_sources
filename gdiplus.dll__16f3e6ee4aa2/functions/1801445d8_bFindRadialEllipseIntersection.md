# bFindRadialEllipseIntersection

- ea: `0x1801445d8`
- end: `0x1801447d3`
- name: `bFindRadialEllipseIntersection`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180143efc`

## callees

- `0x1800c3bb8`
- `0x1800fe680`
- `0x1801445d8`

## import_xrefs

- `GDI32!GetCurrentPositionEx` at `0x180144662`
- `GDI32!GetCurrentPositionEx` at `0x1801446ff`
- `GDI32!GetCurrentPositionEx` at `0x180144774`
- `GDI32!GetCurrentPositionEx` at `0x180144662`
- `GDI32!GetCurrentPositionEx` at `0x1801446ff`
- `GDI32!GetCurrentPositionEx` at `0x180144774`
- `GDI32!MoveToEx` at `0x1801447ab`
- `GDI32!MoveToEx` at `0x1801447ab`
- `GDI32!ArcTo` at `0x1801446e6`
- `GDI32!ArcTo` at `0x18014475f`
- `GDI32!ArcTo` at `0x1801446e6`
- `GDI32!ArcTo` at `0x18014475f`

## pseudocode

```c
BOOL __fastcall bFindRadialEllipseIntersection(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int xr2,
        int yr2,
        struct tagPOINT *a10,
        struct tagPOINT *a11)
{
  int v11; // r15d
  int xr1; // esi
  int yr1; // r14d
  int v15; // r13d
  HDC v16; // rcx
  int v17; // r12d
  BOOL result; // eax
  int v19; // edi
  int bottom; // eax
  LPPOINT v21; // rsi
  LPPOINT v22; // rsi
  struct tagPOINT pt; // [rsp+50h] [rbp-41h] BYREF
  LPPOINT lppt; // [rsp+58h] [rbp-39h]
  LPPOINT v25; // [rsp+60h] [rbp-31h]
  int left; // [rsp+68h] [rbp-29h] BYREF
  int top; // [rsp+6Ch] [rbp-25h]
  int right; // [rsp+70h] [rbp-21h]
  int v29; // [rsp+74h] [rbp-1Dh]
  int v30; // [rsp+78h] [rbp-19h]
  int v31; // [rsp+7Ch] [rbp-15h]
  int v32; // [rsp+80h] [rbp-11h]
  int v33; // [rsp+84h] [rbp-Dh]

  v11 = a2;
  xr1 = a6;
  yr1 = a7;
  v15 = a4;
  v16 = *(HDC *)(a1 + 40);
  v17 = a3;
  lppt = a10;
  v25 = a11;
  v29 = a5;
  v32 = xr2;
  left = a2;
  v33 = yr2;
  pt = 0;
  top = a3;
  right = a4;
  v30 = a6;
  v31 = a7;
  result = GetCurrentPositionEx(v16, &pt);
  if ( result )
  {
    v19 = 0;
    if ( pfnSetVirtualResolution )
    {
      bottom = a5;
    }
    else
    {
      if ( !(unsigned int)bXformWorkhorse(&left, 4, a1 + 84) )
      {
LABEL_15:
        MoveToEx(*(HDC *)(a1 + 40), pt.x, pt.y, 0);
        return v19;
      }
      yr1 = v31;
      xr1 = v30;
      v15 = right;
      v17 = top;
      v11 = left;
      yr2 = v33;
      xr2 = v32;
      bottom = v29;
      a5 = v29;
    }
    if ( ArcTo(*(HDC *)(a1 + 40), v11, v17, v15, bottom, xr1, yr1, xr1, yr1) )
    {
      v21 = lppt;
      if ( GetCurrentPositionEx(*(HDC *)(a1 + 40), lppt) )
      {
        if ( pfnSetVirtualResolution || (unsigned int)bXformWorkhorse(v21, 1, a1 + 108) )
        {
          if ( ArcTo(*(HDC *)(a1 + 40), v11, v17, v15, a5, xr2, yr2, xr2, yr2) )
          {
            v22 = v25;
            if ( GetCurrentPositionEx(*(HDC *)(a1 + 40), v25) )
            {
              if ( pfnSetVirtualResolution || (unsigned int)bXformWorkhorse(v22, 1, a1 + 108) )
                v19 = 1;
            }
          }
        }
      }
    }
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x1801445d8  push    rbp
0x1801445da  push    rbx
0x1801445db  push    rsi
0x1801445dc  push    rdi
0x1801445dd  push    r12
0x1801445df  push    r13
0x1801445e1  push    r14
0x1801445e3  push    r15
0x1801445e5  lea     rbp, [rsp-7]
0x1801445ea  sub     rsp, 98h
0x1801445f1  mov     rax, cs:__security_cookie
0x1801445f8  xor     rax, rsp
0x1801445fb  mov     [rbp+3Fh+var_48], rax
0x1801445ff  mov     rax, [rbp+3Fh+arg_48]
0x180144606  mov     r15d, edx
0x180144609  mov     esi, [rbp+3Fh+arg_28]
0x18014460c  mov     rbx, rcx
0x18014460f  mov     r14d, [rbp+3Fh+arg_30]
0x180144613  mov     r13d, r9d
0x180144616  mov     rcx, [rcx+28h]; hdc
0x18014461a  mov     r12d, r8d
0x18014461d  mov     [rbp+3Fh+lppt], rax
0x180144621  mov     rax, [rbp+3Fh+arg_50]
0x180144628  mov     [rbp+3Fh+var_70], rax
0x18014462c  mov     eax, [rbp+3Fh+arg_20]
0x18014462f  mov     [rbp+3Fh+var_5C], eax
0x180144632  mov     eax, [rbp+3Fh+arg_38]
0x180144638  mov     [rbp+3Fh+var_50], eax
0x18014463b  mov     eax, [rbp+3Fh+arg_40]
0x180144641  mov     [rbp+3Fh+left], edx
0x180144644  lea     rdx, [rbp+3Fh+pt]; lppt
0x180144648  mov     [rbp+3Fh+var_4C], eax
0x18014464b  mov     qword ptr [rbp+3Fh+pt.x], 0
0x180144653  mov     [rbp+3Fh+top], r8d
0x180144657  mov     [rbp+3Fh+right], r9d
0x18014465b  mov     [rbp+3Fh+var_58], esi
0x18014465e  mov     [rbp+3Fh+var_54], r14d
0x180144662  call    cs:__imp_GetCurrentPositionEx
0x180144668  test    eax, eax
0x18014466a  jz      loc_1801447B3
0x180144670  xor     edi, edi
0x180144672  cmp     cs:pfnSetVirtualResolution, rdi
0x180144679  jnz     short loc_1801446C0
0x18014467b  lea     r8, [rbx+54h]
0x18014467f  lea     edx, [rdi+4]
0x180144682  lea     rcx, [rbp+3Fh+left]
0x180144686  call    bXformWorkhorse
0x18014468b  test    eax, eax
0x18014468d  jz      loc_18014479D
0x180144693  mov     eax, [rbp+3Fh+var_4C]
0x180144696  mov     r14d, [rbp+3Fh+var_54]
0x18014469a  mov     esi, [rbp+3Fh+var_58]
0x18014469d  mov     r13d, [rbp+3Fh+right]
0x1801446a1  mov     r12d, [rbp+3Fh+top]
0x1801446a5  mov     r15d, [rbp+3Fh+left]
0x1801446a9  mov     [rbp+3Fh+arg_40], eax
0x1801446af  mov     eax, [rbp+3Fh+var_50]
0x1801446b2  mov     [rbp+3Fh+arg_38], eax
0x1801446b8  mov     eax, [rbp+3Fh+var_5C]
0x1801446bb  mov     [rbp+3Fh+arg_20], eax
0x1801446be  jmp     short loc_1801446C3
0x1801446c0  mov     eax, [rbp+3Fh+arg_20]
0x1801446c3  mov     rcx, [rbx+28h]; hdc
0x1801446c7  mov     r9d, r13d; right
0x1801446ca  mov     [rsp+0D0h+yr2], r14d; yr2
0x1801446cf  mov     r8d, r12d; top
0x1801446d2  mov     [rsp+0D0h+xr2], esi; xr2
0x1801446d6  mov     edx, r15d; left
0x1801446d9  mov     [rsp+0D0h+yr1], r14d; yr1
0x1801446de  mov     [rsp+0D0h+xr1], esi; xr1
0x1801446e2  mov     [rsp+0D0h+bottom], eax; bottom
0x1801446e6  call    cs:__imp_ArcTo
0x1801446ec  test    eax, eax
0x1801446ee  jz      loc_18014479D
0x1801446f4  mov     rsi, [rbp+3Fh+lppt]
0x1801446f8  mov     rcx, [rbx+28h]; hdc
0x1801446fc  mov     rdx, rsi; lppt
0x1801446ff  call    cs:__imp_GetCurrentPositionEx
0x180144705  test    eax, eax
0x180144707  jz      loc_18014479D
0x18014470d  cmp     cs:pfnSetVirtualResolution, rdi
0x180144714  mov     r14d, 1
0x18014471a  jnz     short loc_18014472F
0x18014471c  lea     r8, [rbx+6Ch]
0x180144720  mov     edx, r14d
0x180144723  mov     rcx, rsi
0x180144726  call    bXformWorkhorse
0x18014472b  test    eax, eax
0x18014472d  jz      short loc_18014479D
0x18014472f  mov     eax, [rbp+3Fh+arg_38]
0x180144735  mov     r9d, r13d; right
0x180144738  mov     ecx, [rbp+3Fh+arg_40]
0x18014473e  mov     r8d, r12d; top
0x180144741  mov     [rsp+0D0h+yr2], ecx; yr2
0x180144745  mov     edx, r15d; left
0x180144748  mov     [rsp+0D0h+xr2], eax; xr2
0x18014474c  mov     [rsp+0D0h+yr1], ecx; yr1
0x180144750  mov     rcx, [rbx+28h]; hdc
0x180144754  mov     [rsp+0D0h+xr1], eax; xr1
0x180144758  mov     eax, [rbp+3Fh+arg_20]
0x18014475b  mov     [rsp+0D0h+bottom], eax; bottom
0x18014475f  call    cs:__imp_ArcTo
0x180144765  test    eax, eax
0x180144767  jz      short loc_18014479D
0x180144769  mov     rsi, [rbp+3Fh+var_70]
0x18014476d  mov     rcx, [rbx+28h]; hdc
0x180144771  mov     rdx, rsi; lppt
0x180144774  call    cs:__imp_GetCurrentPositionEx
0x18014477a  test    eax, eax
0x18014477c  jz      short loc_18014479D
0x18014477e  cmp     cs:pfnSetVirtualResolution, rdi
0x180144785  jnz     short loc_18014479A
0x180144787  lea     r8, [rbx+6Ch]
0x18014478b  mov     edx, r14d
0x18014478e  mov     rcx, rsi
0x180144791  call    bXformWorkhorse
0x180144796  test    eax, eax
0x180144798  jz      short loc_18014479D
0x18014479a  mov     edi, r14d
0x18014479d  mov     r8d, [rbp+3Fh+pt.y]; y
0x1801447a1  xor     r9d, r9d; lppt
0x1801447a4  mov     edx, [rbp+3Fh+pt.x]; x
0x1801447a7  mov     rcx, [rbx+28h]; hdc
0x1801447ab  call    cs:__imp_MoveToEx
0x1801447b1  mov     eax, edi
0x1801447b3  mov     rcx, [rbp+3Fh+var_48]
0x1801447b7  xor     rcx, rsp; StackCookie
0x1801447ba  call    __security_check_cookie
0x1801447bf  add     rsp, 98h
0x1801447c6  pop     r15
0x1801447c8  pop     r14
0x1801447ca  pop     r13
0x1801447cc  pop     r12
0x1801447ce  pop     rdi
0x1801447cf  pop     rsi
0x1801447d0  pop     rbx
0x1801447d1  pop     rbp
0x1801447d2  retn
```
