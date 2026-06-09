# bFindRadialEllipseIntersection

- ea: `0x18014d168`
- end: `0x18014d388`
- name: `bFindRadialEllipseIntersection`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18014ca50`

## callees

- `0x1800c790c`
- `0x180105d40`
- `0x18014d168`

## import_xrefs

- `GDI32!GetCurrentPositionEx` at `0x18014d1f2`
- `GDI32!GetCurrentPositionEx` at `0x18014d29b`
- `GDI32!GetCurrentPositionEx` at `0x18014d31c`
- `GDI32!GetCurrentPositionEx` at `0x18014d1f2`
- `GDI32!GetCurrentPositionEx` at `0x18014d29b`
- `GDI32!GetCurrentPositionEx` at `0x18014d31c`
- `GDI32!MoveToEx` at `0x18014d359`
- `GDI32!MoveToEx` at `0x18014d359`
- `GDI32!ArcTo` at `0x18014d27c`
- `GDI32!ArcTo` at `0x18014d301`
- `GDI32!ArcTo` at `0x18014d27c`
- `GDI32!ArcTo` at `0x18014d301`

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
0x18014d168  push    rbp
0x18014d16a  push    rbx
0x18014d16b  push    rsi
0x18014d16c  push    rdi
0x18014d16d  push    r12
0x18014d16f  push    r13
0x18014d171  push    r14
0x18014d173  push    r15
0x18014d175  lea     rbp, [rsp-7]
0x18014d17a  sub     rsp, 98h
0x18014d181  mov     rax, cs:__security_cookie
0x18014d188  xor     rax, rsp
0x18014d18b  mov     [rbp+3Fh+var_48], rax
0x18014d18f  mov     rax, [rbp+3Fh+arg_48]
0x18014d196  mov     r15d, edx
0x18014d199  mov     esi, [rbp+3Fh+arg_28]
0x18014d19c  mov     rbx, rcx
0x18014d19f  mov     r14d, [rbp+3Fh+arg_30]
0x18014d1a3  mov     r13d, r9d
0x18014d1a6  mov     rcx, [rcx+28h]; hdc
0x18014d1aa  mov     r12d, r8d
0x18014d1ad  mov     [rbp+3Fh+lppt], rax
0x18014d1b1  mov     rax, [rbp+3Fh+arg_50]
0x18014d1b8  mov     [rbp+3Fh+var_70], rax
0x18014d1bc  mov     eax, [rbp+3Fh+arg_20]
0x18014d1bf  mov     [rbp+3Fh+var_5C], eax
0x18014d1c2  mov     eax, [rbp+3Fh+arg_38]
0x18014d1c8  mov     [rbp+3Fh+var_50], eax
0x18014d1cb  mov     eax, [rbp+3Fh+arg_40]
0x18014d1d1  mov     [rbp+3Fh+left], edx
0x18014d1d4  lea     rdx, [rbp+3Fh+pt]; lppt
0x18014d1d8  mov     [rbp+3Fh+var_4C], eax
0x18014d1db  mov     qword ptr [rbp+3Fh+pt.x], 0
0x18014d1e3  mov     [rbp+3Fh+top], r8d
0x18014d1e7  mov     [rbp+3Fh+right], r9d
0x18014d1eb  mov     [rbp+3Fh+var_58], esi
0x18014d1ee  mov     [rbp+3Fh+var_54], r14d
0x18014d1f2  call    cs:__imp_GetCurrentPositionEx
0x18014d1f9  nop     dword ptr [rax+rax+00h]
0x18014d1fe  test    eax, eax
0x18014d200  jz      loc_18014D367
0x18014d206  xor     edi, edi
0x18014d208  cmp     cs:pfnSetVirtualResolution, rdi
0x18014d20f  jnz     short loc_18014D256
0x18014d211  lea     r8, [rbx+54h]
0x18014d215  lea     edx, [rdi+4]
0x18014d218  lea     rcx, [rbp+3Fh+left]
0x18014d21c  call    bXformWorkhorse
0x18014d221  test    eax, eax
0x18014d223  jz      loc_18014D34B
0x18014d229  mov     eax, [rbp+3Fh+var_4C]
0x18014d22c  mov     r14d, [rbp+3Fh+var_54]
0x18014d230  mov     esi, [rbp+3Fh+var_58]
0x18014d233  mov     r13d, [rbp+3Fh+right]
0x18014d237  mov     r12d, [rbp+3Fh+top]
0x18014d23b  mov     r15d, [rbp+3Fh+left]
0x18014d23f  mov     [rbp+3Fh+arg_40], eax
0x18014d245  mov     eax, [rbp+3Fh+var_50]
0x18014d248  mov     [rbp+3Fh+arg_38], eax
0x18014d24e  mov     eax, [rbp+3Fh+var_5C]
0x18014d251  mov     [rbp+3Fh+arg_20], eax
0x18014d254  jmp     short loc_18014D259
0x18014d256  mov     eax, [rbp+3Fh+arg_20]
0x18014d259  mov     rcx, [rbx+28h]; hdc
0x18014d25d  mov     r9d, r13d; right
0x18014d260  mov     [rsp+0D0h+yr2], r14d; yr2
0x18014d265  mov     r8d, r12d; top
0x18014d268  mov     [rsp+0D0h+xr2], esi; xr2
0x18014d26c  mov     edx, r15d; left
0x18014d26f  mov     [rsp+0D0h+yr1], r14d; yr1
0x18014d274  mov     [rsp+0D0h+xr1], esi; xr1
0x18014d278  mov     [rsp+0D0h+bottom], eax; bottom
0x18014d27c  call    cs:__imp_ArcTo
0x18014d283  nop     dword ptr [rax+rax+00h]
0x18014d288  test    eax, eax
0x18014d28a  jz      loc_18014D34B
0x18014d290  mov     rsi, [rbp+3Fh+lppt]
0x18014d294  mov     rcx, [rbx+28h]; hdc
0x18014d298  mov     rdx, rsi; lppt
0x18014d29b  call    cs:__imp_GetCurrentPositionEx
0x18014d2a2  nop     dword ptr [rax+rax+00h]
0x18014d2a7  test    eax, eax
0x18014d2a9  jz      loc_18014D34B
0x18014d2af  cmp     cs:pfnSetVirtualResolution, rdi
0x18014d2b6  mov     r14d, 1
0x18014d2bc  jnz     short loc_18014D2D1
0x18014d2be  lea     r8, [rbx+6Ch]
0x18014d2c2  mov     edx, r14d
0x18014d2c5  mov     rcx, rsi
0x18014d2c8  call    bXformWorkhorse
0x18014d2cd  test    eax, eax
0x18014d2cf  jz      short loc_18014D34B
0x18014d2d1  mov     eax, [rbp+3Fh+arg_38]
0x18014d2d7  mov     r9d, r13d; right
0x18014d2da  mov     ecx, [rbp+3Fh+arg_40]
0x18014d2e0  mov     r8d, r12d; top
0x18014d2e3  mov     [rsp+0D0h+yr2], ecx; yr2
0x18014d2e7  mov     edx, r15d; left
0x18014d2ea  mov     [rsp+0D0h+xr2], eax; xr2
0x18014d2ee  mov     [rsp+0D0h+yr1], ecx; yr1
0x18014d2f2  mov     rcx, [rbx+28h]; hdc
0x18014d2f6  mov     [rsp+0D0h+xr1], eax; xr1
0x18014d2fa  mov     eax, [rbp+3Fh+arg_20]
0x18014d2fd  mov     [rsp+0D0h+bottom], eax; bottom
0x18014d301  call    cs:__imp_ArcTo
0x18014d308  nop     dword ptr [rax+rax+00h]
0x18014d30d  test    eax, eax
0x18014d30f  jz      short loc_18014D34B
0x18014d311  mov     rsi, [rbp+3Fh+var_70]
0x18014d315  mov     rcx, [rbx+28h]; hdc
0x18014d319  mov     rdx, rsi; lppt
0x18014d31c  call    cs:__imp_GetCurrentPositionEx
0x18014d323  nop     dword ptr [rax+rax+00h]
0x18014d328  test    eax, eax
0x18014d32a  jz      short loc_18014D34B
0x18014d32c  cmp     cs:pfnSetVirtualResolution, rdi
0x18014d333  jnz     short loc_18014D348
0x18014d335  lea     r8, [rbx+6Ch]
0x18014d339  mov     edx, r14d
0x18014d33c  mov     rcx, rsi
0x18014d33f  call    bXformWorkhorse
0x18014d344  test    eax, eax
0x18014d346  jz      short loc_18014D34B
0x18014d348  mov     edi, r14d
0x18014d34b  mov     r8d, [rbp+3Fh+pt.y]; y
0x18014d34f  xor     r9d, r9d; lppt
0x18014d352  mov     edx, [rbp+3Fh+pt.x]; x
0x18014d355  mov     rcx, [rbx+28h]; hdc
0x18014d359  call    cs:__imp_MoveToEx
0x18014d360  nop     dword ptr [rax+rax+00h]
0x18014d365  mov     eax, edi
0x18014d367  mov     rcx, [rbp+3Fh+var_48]
0x18014d36b  xor     rcx, rsp; StackCookie
0x18014d36e  call    __security_check_cookie
0x18014d373  add     rsp, 98h
0x18014d37a  pop     r15
0x18014d37c  pop     r14
0x18014d37e  pop     r13
0x18014d380  pop     r12
0x18014d382  pop     rdi
0x18014d383  pop     rsi
0x18014d384  pop     rbx
0x18014d385  pop     rbp
0x18014d386  retn
```
