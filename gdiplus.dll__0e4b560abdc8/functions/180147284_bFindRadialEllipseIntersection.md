# bFindRadialEllipseIntersection

- ea: `0x180147284`
- end: `0x1801474a2`
- name: `bFindRadialEllipseIntersection`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180146b74`

## callees

- `0x1800b1ee8`
- `0x1800e9380`
- `0x180147284`

## import_xrefs

- `GDI32!GetCurrentPositionEx` at `0x18014730c`
- `GDI32!GetCurrentPositionEx` at `0x1801473b5`
- `GDI32!GetCurrentPositionEx` at `0x180147436`
- `GDI32!GetCurrentPositionEx` at `0x18014730c`
- `GDI32!GetCurrentPositionEx` at `0x1801473b5`
- `GDI32!GetCurrentPositionEx` at `0x180147436`
- `GDI32!MoveToEx` at `0x180147473`
- `GDI32!MoveToEx` at `0x180147473`
- `GDI32!ArcTo` at `0x180147396`
- `GDI32!ArcTo` at `0x18014741b`
- `GDI32!ArcTo` at `0x180147396`
- `GDI32!ArcTo` at `0x18014741b`

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
  int v15; // ebx
  HDC v16; // rcx
  int v17; // r13d
  int v18; // r12d
  BOOL result; // eax
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
  v15 = 0;
  v16 = *(HDC *)(a1 + 40);
  v17 = a4;
  lppt = a10;
  v18 = a3;
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
        return v15;
      }
      yr1 = v31;
      xr1 = v30;
      v17 = right;
      v18 = top;
      v11 = left;
      yr2 = v33;
      xr2 = v32;
      bottom = v29;
      a5 = v29;
    }
    if ( ArcTo(*(HDC *)(a1 + 40), v11, v18, v17, bottom, xr1, yr1, xr1, yr1) )
    {
      v21 = lppt;
      if ( GetCurrentPositionEx(*(HDC *)(a1 + 40), lppt) )
      {
        if ( pfnSetVirtualResolution || (unsigned int)bXformWorkhorse(v21, 1, a1 + 108) )
        {
          if ( ArcTo(*(HDC *)(a1 + 40), v11, v18, v17, a5, xr2, yr2, xr2, yr2) )
          {
            v22 = v25;
            if ( GetCurrentPositionEx(*(HDC *)(a1 + 40), v25) )
            {
              if ( pfnSetVirtualResolution || (unsigned int)bXformWorkhorse(v22, 1, a1 + 108) )
                v15 = 1;
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
0x180147284  push    rbp
0x180147286  push    rbx
0x180147287  push    rsi
0x180147288  push    rdi
0x180147289  push    r12
0x18014728b  push    r13
0x18014728d  push    r14
0x18014728f  push    r15
0x180147291  lea     rbp, [rsp-7]
0x180147296  sub     rsp, 98h
0x18014729d  mov     rax, cs:__security_cookie
0x1801472a4  xor     rax, rsp
0x1801472a7  mov     [rbp+3Fh+var_48], rax
0x1801472ab  mov     rax, [rbp+3Fh+arg_48]
0x1801472b2  mov     r15d, edx
0x1801472b5  mov     esi, [rbp+3Fh+arg_28]
0x1801472b8  mov     rdi, rcx
0x1801472bb  mov     r14d, [rbp+3Fh+arg_30]
0x1801472bf  xor     ebx, ebx
0x1801472c1  mov     rcx, [rcx+28h]; hdc
0x1801472c5  mov     r13d, r9d
0x1801472c8  mov     [rbp+3Fh+lppt], rax
0x1801472cc  mov     r12d, r8d
0x1801472cf  mov     rax, [rbp+3Fh+arg_50]
0x1801472d6  mov     [rbp+3Fh+var_70], rax
0x1801472da  mov     eax, [rbp+3Fh+arg_20]
0x1801472dd  mov     [rbp+3Fh+var_5C], eax
0x1801472e0  mov     eax, [rbp+3Fh+arg_38]
0x1801472e6  mov     [rbp+3Fh+var_50], eax
0x1801472e9  mov     eax, [rbp+3Fh+arg_40]
0x1801472ef  mov     [rbp+3Fh+left], edx
0x1801472f2  lea     rdx, [rbp+3Fh+pt]; lppt
0x1801472f6  mov     [rbp+3Fh+var_4C], eax
0x1801472f9  mov     qword ptr [rbp+3Fh+pt.x], rbx
0x1801472fd  mov     [rbp+3Fh+top], r8d
0x180147301  mov     [rbp+3Fh+right], r9d
0x180147305  mov     [rbp+3Fh+var_58], esi
0x180147308  mov     [rbp+3Fh+var_54], r14d
0x18014730c  call    cs:__imp_GetCurrentPositionEx
0x180147313  nop     dword ptr [rax+rax+00h]
0x180147318  test    eax, eax
0x18014731a  jz      loc_180147481
0x180147320  cmp     cs:pfnSetVirtualResolution, rbx
0x180147327  jnz     short loc_180147370
0x180147329  lea     r8, [rdi+54h]
0x18014732d  mov     edx, 4
0x180147332  lea     rcx, [rbp+3Fh+left]
0x180147336  call    bXformWorkhorse
0x18014733b  test    eax, eax
0x18014733d  jz      loc_180147465
0x180147343  mov     eax, [rbp+3Fh+var_4C]
0x180147346  mov     r14d, [rbp+3Fh+var_54]
0x18014734a  mov     esi, [rbp+3Fh+var_58]
0x18014734d  mov     r13d, [rbp+3Fh+right]
0x180147351  mov     r12d, [rbp+3Fh+top]
0x180147355  mov     r15d, [rbp+3Fh+left]
0x180147359  mov     [rbp+3Fh+arg_40], eax
0x18014735f  mov     eax, [rbp+3Fh+var_50]
0x180147362  mov     [rbp+3Fh+arg_38], eax
0x180147368  mov     eax, [rbp+3Fh+var_5C]
0x18014736b  mov     [rbp+3Fh+arg_20], eax
0x18014736e  jmp     short loc_180147373
0x180147370  mov     eax, [rbp+3Fh+arg_20]
0x180147373  mov     rcx, [rdi+28h]; hdc
0x180147377  mov     r9d, r13d; right
0x18014737a  mov     [rsp+0D0h+yr2], r14d; yr2
0x18014737f  mov     r8d, r12d; top
0x180147382  mov     [rsp+0D0h+xr2], esi; xr2
0x180147386  mov     edx, r15d; left
0x180147389  mov     [rsp+0D0h+yr1], r14d; yr1
0x18014738e  mov     [rsp+0D0h+xr1], esi; xr1
0x180147392  mov     [rsp+0D0h+bottom], eax; bottom
0x180147396  call    cs:__imp_ArcTo
0x18014739d  nop     dword ptr [rax+rax+00h]
0x1801473a2  test    eax, eax
0x1801473a4  jz      loc_180147465
0x1801473aa  mov     rsi, [rbp+3Fh+lppt]
0x1801473ae  mov     rcx, [rdi+28h]; hdc
0x1801473b2  mov     rdx, rsi; lppt
0x1801473b5  call    cs:__imp_GetCurrentPositionEx
0x1801473bc  nop     dword ptr [rax+rax+00h]
0x1801473c1  test    eax, eax
0x1801473c3  jz      loc_180147465
0x1801473c9  cmp     cs:pfnSetVirtualResolution, rbx
0x1801473d0  mov     r14d, 1
0x1801473d6  jnz     short loc_1801473EB
0x1801473d8  lea     r8, [rdi+6Ch]
0x1801473dc  mov     edx, r14d
0x1801473df  mov     rcx, rsi
0x1801473e2  call    bXformWorkhorse
0x1801473e7  test    eax, eax
0x1801473e9  jz      short loc_180147465
0x1801473eb  mov     eax, [rbp+3Fh+arg_38]
0x1801473f1  mov     r9d, r13d; right
0x1801473f4  mov     ecx, [rbp+3Fh+arg_40]
0x1801473fa  mov     r8d, r12d; top
0x1801473fd  mov     [rsp+0D0h+yr2], ecx; yr2
0x180147401  mov     edx, r15d; left
0x180147404  mov     [rsp+0D0h+xr2], eax; xr2
0x180147408  mov     [rsp+0D0h+yr1], ecx; yr1
0x18014740c  mov     rcx, [rdi+28h]; hdc
0x180147410  mov     [rsp+0D0h+xr1], eax; xr1
0x180147414  mov     eax, [rbp+3Fh+arg_20]
0x180147417  mov     [rsp+0D0h+bottom], eax; bottom
0x18014741b  call    cs:__imp_ArcTo
0x180147422  nop     dword ptr [rax+rax+00h]
0x180147427  test    eax, eax
0x180147429  jz      short loc_180147465
0x18014742b  mov     rsi, [rbp+3Fh+var_70]
0x18014742f  mov     rcx, [rdi+28h]; hdc
0x180147433  mov     rdx, rsi; lppt
0x180147436  call    cs:__imp_GetCurrentPositionEx
0x18014743d  nop     dword ptr [rax+rax+00h]
0x180147442  test    eax, eax
0x180147444  jz      short loc_180147465
0x180147446  cmp     cs:pfnSetVirtualResolution, rbx
0x18014744d  jnz     short loc_180147462
0x18014744f  lea     r8, [rdi+6Ch]
0x180147453  mov     edx, r14d
0x180147456  mov     rcx, rsi
0x180147459  call    bXformWorkhorse
0x18014745e  test    eax, eax
0x180147460  jz      short loc_180147465
0x180147462  mov     ebx, r14d
0x180147465  mov     r8d, [rbp+3Fh+pt.y]; y
0x180147469  xor     r9d, r9d; lppt
0x18014746c  mov     edx, [rbp+3Fh+pt.x]; x
0x18014746f  mov     rcx, [rdi+28h]; hdc
0x180147473  call    cs:__imp_MoveToEx
0x18014747a  nop     dword ptr [rax+rax+00h]
0x18014747f  mov     eax, ebx
0x180147481  mov     rcx, [rbp+3Fh+var_48]
0x180147485  xor     rcx, rsp; StackCookie
0x180147488  call    __security_check_cookie
0x18014748d  add     rsp, 98h
0x180147494  pop     r15
0x180147496  pop     r14
0x180147498  pop     r13
0x18014749a  pop     r12
0x18014749c  pop     rdi
0x18014749d  pop     rsi
0x18014749e  pop     rbx
0x18014749f  pop     rbp
0x1801474a0  retn
```
