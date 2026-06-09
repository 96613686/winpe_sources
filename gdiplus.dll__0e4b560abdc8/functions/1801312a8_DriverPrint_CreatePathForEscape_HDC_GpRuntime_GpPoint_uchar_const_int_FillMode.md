# DriverPrint::CreatePathForEscape(HDC__ *,GpRuntime::GpPoint *,uchar const *,int,FillMode)

- ea: `0x1801312a8`
- end: `0x18013151b`
- name: `?CreatePathForEscape@DriverPrint@@IEAAXPEAUHDC__@@PEAVGpPoint@GpRuntime@@PEBEHW4FillMode@@@Z`
- size: `627`
- prototype: `void __high(HDC, struct GpRuntime::GpPoint *, const unsigned __int8 *, int, enum FillMode)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180135510`
- `0x180135cb0`

## callees

- `0x1800e9380`
- `0x1801312a8`

## import_xrefs

- `GDI32!StrokePath` at `0x1801314c7`
- `GDI32!StrokePath` at `0x1801314c7`
- `GDI32!EndPath` at `0x1801314b8`
- `GDI32!EndPath` at `0x1801314b8`
- `GDI32!CloseFigure` at `0x180131494`
- `GDI32!CloseFigure` at `0x180131494`
- `GDI32!PolylineTo` at `0x180131393`
- `GDI32!PolylineTo` at `0x18013147b`
- `GDI32!PolylineTo` at `0x180131393`
- `GDI32!PolylineTo` at `0x18013147b`
- `GDI32!PolyBezierTo` at `0x1801313db`
- `GDI32!PolyBezierTo` at `0x180131464`
- `GDI32!PolyBezierTo` at `0x1801313db`
- `GDI32!PolyBezierTo` at `0x180131464`
- `GDI32!MoveToEx` at `0x180131403`
- `GDI32!MoveToEx` at `0x180131403`
- `GDI32!BeginPath` at `0x18013134c`
- `GDI32!BeginPath` at `0x18013134c`
- `GDI32!Escape` at `0x18013133a`
- `GDI32!Escape` at `0x1801314ea`
- `GDI32!Escape` at `0x18013133a`
- `GDI32!Escape` at `0x1801314ea`

## pseudocode

```c
int __fastcall DriverPrint::CreatePathForEscape(__int64 a1, HDC a2, const POINT *a3, char *a4, int a5, int a6)
{
  char *v6; // r15
  const POINT *v7; // rdi
  signed int v9; // ebx
  char v10; // r14
  char v12; // r13
  char v13; // cl
  int v14; // ecx
  int v15; // ecx
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax
  int result; // eax
  int v20; // [rsp+30h] [rbp-30h]
  CHAR pvIn[2]; // [rsp+38h] [rbp-28h] BYREF
  char v22; // [rsp+3Ah] [rbp-26h]
  char v23; // [rsp+3Bh] [rbp-25h]
  int v24; // [rsp+3Ch] [rbp-24h]
  __int16 v25; // [rsp+40h] [rbp-20h]
  int v26; // [rsp+42h] [rbp-1Eh]
  __int16 v27; // [rsp+46h] [rbp-1Ah]
  int v28; // [rsp+48h] [rbp-18h]
  __int16 v29; // [rsp+4Ch] [rbp-14h]
  __int64 v30; // [rsp+4Eh] [rbp-12h]

  if ( a3 )
  {
    v6 = a4;
    v7 = a3;
    if ( a4 )
    {
      v23 = 1;
      v27 = 1;
      *(_WORD *)pvIn = 0;
      v22 = (a6 != 0) + 1;
      v24 = 5;
      v25 = 0;
      v26 = 0;
      v9 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      Escape(a2, 4096, 0, 0, 0);
      v10 = 0;
      BeginPath(a2);
LABEL_25:
      v16 = 1;
      v20 = 1;
      while ( 1 )
      {
        if ( a5 <= 0 )
        {
          EndPath(a2);
          StrokePath(a2);
          return Escape(a2, 4098, 30, pvIn, 0);
        }
        v12 = *v6;
        --a5;
        v13 = *v6++;
        v14 = v13 & 7;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            if ( v15 != 2 )
              goto LABEL_16;
            if ( v10 == 1 )
            {
              PolylineTo(a2, v7, v9);
              v10 = 3;
LABEL_9:
              v16 = v20;
              v17 = v9;
              v9 = 1;
              v7 += v17;
              goto LABEL_16;
            }
          }
          else if ( v10 == 3 )
          {
            if ( v9 == 3 * (v9 / 3) )
              PolyBezierTo(a2, v7, v9);
            v10 = 1;
            goto LABEL_9;
          }
          ++v9;
        }
        else
        {
          MoveToEx(a2, v7->x, v7->y, 0);
          v9 = 0;
          v10 = *v6 & 7;
          ++v7;
          v16 = 0;
          v20 = 0;
        }
LABEL_16:
        if ( v12 < 0 || !a5 || !*v6 && !v16 )
        {
          if ( v10 == 3 )
          {
            if ( v9 == 3 * (v9 / 3) )
              PolyBezierTo(a2, v7, v9);
          }
          else
          {
            PolylineTo(a2, v7, v9);
          }
          v18 = v9;
          v9 = 0;
          v7 += v18;
          CloseFigure(a2);
          goto LABEL_25;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801312a8  test    r8, r8
0x1801312ab  jz      locret_180131519
0x1801312b1  mov     [rsp-38h+arg_0], rbx
0x1801312b6  push    rbp
0x1801312b7  push    rsi
0x1801312b8  push    rdi
0x1801312b9  push    r12
0x1801312bb  push    r13
0x1801312bd  push    r14
0x1801312bf  push    r15
0x1801312c1  mov     rbp, rsp
0x1801312c4  sub     rsp, 60h
0x1801312c8  mov     rax, cs:__security_cookie
0x1801312cf  xor     rax, rsp
0x1801312d2  mov     [rbp+var_8], rax
0x1801312d6  xor     r13d, r13d
0x1801312d9  mov     r15, r9
0x1801312dc  mov     rdi, r8
0x1801312df  mov     rsi, rdx
0x1801312e2  test    r9, r9
0x1801312e5  jz      loc_1801314F6
0x1801312eb  cmp     [rbp+arg_28], r13d
0x1801312ef  lea     ecx, [r13+1]
0x1801312f3  mov     [rbp+var_25], cl
0x1801312f6  mov     edx, 1000h; iEscape
0x1801312fb  setnz   al
0x1801312fe  mov     [rbp+var_1A], cx
0x180131302  add     al, cl
0x180131304  mov     word ptr [rbp+pvIn], r13w
0x180131309  mov     rcx, rsi; hdc
0x18013130c  mov     [rbp+var_26], al
0x18013130f  xor     r9d, r9d; pvIn
0x180131312  mov     [rbp+var_24], 5
0x180131319  xor     r8d, r8d; cjIn
0x18013131c  mov     [rbp+var_20], r13w
0x180131321  mov     [rbp+var_1E], r13d
0x180131325  mov     ebx, r13d
0x180131328  mov     [rbp+var_18], r13d
0x18013132c  mov     [rbp+var_14], r13w
0x180131331  mov     [rbp+var_12], r13
0x180131335  mov     [rsp+60h+pvOut], r13; pvOut
0x18013133a  call    cs:__imp_Escape
0x180131341  nop     dword ptr [rax+rax+00h]
0x180131346  mov     rcx, rsi; hdc
0x180131349  mov     r14b, r13b
0x18013134c  call    cs:__imp_BeginPath
0x180131353  nop     dword ptr [rax+rax+00h]
0x180131358  mov     r12d, [rbp+arg_20]
0x18013135c  jmp     loc_1801314A0
0x180131361  movzx   r13d, byte ptr [r15]
0x180131365  sub     r12d, r8d
0x180131368  mov     ecx, r13d
0x18013136b  add     r15, r8
0x18013136e  and     ecx, 7
0x180131371  jz      loc_1801313F7
0x180131377  sub     ecx, 1
0x18013137a  jz      short loc_1801313B7
0x18013137c  cmp     ecx, 2
0x18013137f  jnz     loc_180131425
0x180131385  cmp     r14b, r8b
0x180131388  jnz     short loc_1801313F2
0x18013138a  mov     r8d, ebx; cpt
0x18013138d  mov     rdx, rdi; apt
0x180131390  mov     rcx, rsi; hdc
0x180131393  call    cs:__imp_PolylineTo
0x18013139a  nop     dword ptr [rax+rax+00h]
0x18013139f  mov     r8d, 1
0x1801313a5  mov     r14b, 3
0x1801313a8  mov     edx, [rbp+var_30]
0x1801313ab  movsxd  rax, ebx
0x1801313ae  mov     ebx, r8d
0x1801313b1  lea     rdi, [rdi+rax*8]
0x1801313b5  jmp     short loc_180131425
0x1801313b7  cmp     r14b, 3
0x1801313bb  jnz     short loc_1801313F2
0x1801313bd  mov     eax, 55555556h
0x1801313c2  imul    ebx
0x1801313c4  mov     eax, edx
0x1801313c6  shr     eax, 1Fh
0x1801313c9  add     edx, eax
0x1801313cb  lea     ecx, [rdx+rdx*2]
0x1801313ce  cmp     ebx, ecx
0x1801313d0  jnz     short loc_1801313ED
0x1801313d2  mov     r8d, ebx; cpt
0x1801313d5  mov     rdx, rdi; apt
0x1801313d8  mov     rcx, rsi; hdc
0x1801313db  call    cs:__imp_PolyBezierTo
0x1801313e2  nop     dword ptr [rax+rax+00h]
0x1801313e7  mov     r8d, 1
0x1801313ed  mov     r14b, r8b
0x1801313f0  jmp     short loc_1801313A8
0x1801313f2  add     ebx, r8d
0x1801313f5  jmp     short loc_180131425
0x1801313f7  mov     r8d, [rdi+4]; y
0x1801313fb  xor     r9d, r9d; lppt
0x1801313fe  mov     edx, [rdi]; x
0x180131400  mov     rcx, rsi; hdc
0x180131403  call    cs:__imp_MoveToEx
0x18013140a  nop     dword ptr [rax+rax+00h]
0x18013140f  mov     r14b, [r15]
0x180131412  xor     ebx, ebx
0x180131414  and     r14b, 7
0x180131418  add     rdi, 8
0x18013141c  xor     edx, edx
0x18013141e  mov     [rbp+var_30], edx
0x180131421  lea     r8d, [rbx+1]
0x180131425  test    r13b, r13b
0x180131428  js      short loc_18013143D
0x18013142a  xor     r13d, r13d
0x18013142d  test    r12d, r12d
0x180131430  jz      short loc_180131440
0x180131432  cmp     [r15], r13b
0x180131435  jnz     short loc_1801314AC
0x180131437  test    edx, edx
0x180131439  jnz     short loc_1801314AC
0x18013143b  jmp     short loc_180131440
0x18013143d  xor     r13d, r13d
0x180131440  cmp     r14b, 3
0x180131444  jnz     short loc_180131472
0x180131446  mov     eax, 55555556h
0x18013144b  imul    ebx
0x18013144d  mov     eax, edx
0x18013144f  shr     eax, 1Fh
0x180131452  add     edx, eax
0x180131454  lea     ecx, [rdx+rdx*2]
0x180131457  cmp     ebx, ecx
0x180131459  jnz     short loc_180131487
0x18013145b  mov     r8d, ebx; cpt
0x18013145e  mov     rdx, rdi; apt
0x180131461  mov     rcx, rsi; hdc
0x180131464  call    cs:__imp_PolyBezierTo
0x18013146b  nop     dword ptr [rax+rax+00h]
0x180131470  jmp     short loc_180131487
0x180131472  mov     r8d, ebx; cpt
0x180131475  mov     rdx, rdi; apt
0x180131478  mov     rcx, rsi; hdc
0x18013147b  call    cs:__imp_PolylineTo
0x180131482  nop     dword ptr [rax+rax+00h]
0x180131487  movsxd  rax, ebx
0x18013148a  mov     rcx, rsi; hdc
0x18013148d  mov     ebx, r13d
0x180131490  lea     rdi, [rdi+rax*8]
0x180131494  call    cs:__imp_CloseFigure
0x18013149b  nop     dword ptr [rax+rax+00h]
0x1801314a0  mov     r8d, 1
0x1801314a6  mov     edx, r8d
0x1801314a9  mov     [rbp+var_30], edx
0x1801314ac  test    r12d, r12d
0x1801314af  jg      loc_180131361
0x1801314b5  mov     rcx, rsi; hdc
0x1801314b8  call    cs:__imp_EndPath
0x1801314bf  nop     dword ptr [rax+rax+00h]
0x1801314c4  mov     rcx, rsi; hdc
0x1801314c7  call    cs:__imp_StrokePath
0x1801314ce  nop     dword ptr [rax+rax+00h]
0x1801314d3  lea     r9, [rbp+pvIn]; pvIn
0x1801314d7  mov     [rsp+60h+pvOut], r13; pvOut
0x1801314dc  mov     edx, 1002h; iEscape
0x1801314e1  mov     r8d, 1Eh; cjIn
0x1801314e7  mov     rcx, rsi; hdc
0x1801314ea  call    cs:__imp_Escape
0x1801314f1  nop     dword ptr [rax+rax+00h]
0x1801314f6  mov     rcx, [rbp+var_8]
0x1801314fa  xor     rcx, rsp; StackCookie
0x1801314fd  call    __security_check_cookie
0x180131502  mov     rbx, [rsp+60h+arg_0]
0x18013150a  add     rsp, 60h
0x18013150e  pop     r15
0x180131510  pop     r14
0x180131512  pop     r13
0x180131514  pop     r12
0x180131516  pop     rdi
0x180131517  pop     rsi
0x180131518  pop     rbp
0x180131519  retn
```
