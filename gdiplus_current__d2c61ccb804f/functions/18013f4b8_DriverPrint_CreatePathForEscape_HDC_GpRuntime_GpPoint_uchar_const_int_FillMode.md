# DriverPrint::CreatePathForEscape(HDC__ *,GpRuntime::GpPoint *,uchar const *,int,FillMode)

- ea: `0x18013f4b8`
- end: `0x18013f72b`
- name: `?CreatePathForEscape@DriverPrint@@IEAAXPEAUHDC__@@PEAVGpPoint@GpRuntime@@PEBEHW4FillMode@@@Z`
- size: `627`
- prototype: `void __high(HDC, struct GpRuntime::GpPoint *, const unsigned __int8 *, int, enum FillMode)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180140e80`
- `0x1801414b0`

## callees

- `0x180105d40`
- `0x18013f4b8`

## import_xrefs

- `GDI32!StrokePath` at `0x18013f6d7`
- `GDI32!StrokePath` at `0x18013f6d7`
- `GDI32!EndPath` at `0x18013f6c8`
- `GDI32!EndPath` at `0x18013f6c8`
- `GDI32!CloseFigure` at `0x18013f6a4`
- `GDI32!CloseFigure` at `0x18013f6a4`
- `GDI32!PolylineTo` at `0x18013f5a3`
- `GDI32!PolylineTo` at `0x18013f68b`
- `GDI32!PolylineTo` at `0x18013f5a3`
- `GDI32!PolylineTo` at `0x18013f68b`
- `GDI32!PolyBezierTo` at `0x18013f5eb`
- `GDI32!PolyBezierTo` at `0x18013f674`
- `GDI32!PolyBezierTo` at `0x18013f5eb`
- `GDI32!PolyBezierTo` at `0x18013f674`
- `GDI32!MoveToEx` at `0x18013f613`
- `GDI32!MoveToEx` at `0x18013f613`
- `GDI32!BeginPath` at `0x18013f55c`
- `GDI32!BeginPath` at `0x18013f55c`
- `GDI32!Escape` at `0x18013f54a`
- `GDI32!Escape` at `0x18013f6fa`
- `GDI32!Escape` at `0x18013f54a`
- `GDI32!Escape` at `0x18013f6fa`

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
0x18013f4b8  test    r8, r8
0x18013f4bb  jz      locret_18013F729
0x18013f4c1  mov     [rsp-38h+arg_0], rbx
0x18013f4c6  push    rbp
0x18013f4c7  push    rsi
0x18013f4c8  push    rdi
0x18013f4c9  push    r12
0x18013f4cb  push    r13
0x18013f4cd  push    r14
0x18013f4cf  push    r15
0x18013f4d1  mov     rbp, rsp
0x18013f4d4  sub     rsp, 60h
0x18013f4d8  mov     rax, cs:__security_cookie
0x18013f4df  xor     rax, rsp
0x18013f4e2  mov     [rbp+var_8], rax
0x18013f4e6  xor     r13d, r13d
0x18013f4e9  mov     r15, r9
0x18013f4ec  mov     rdi, r8
0x18013f4ef  mov     rsi, rdx
0x18013f4f2  test    r9, r9
0x18013f4f5  jz      loc_18013F706
0x18013f4fb  cmp     [rbp+arg_28], r13d
0x18013f4ff  lea     ecx, [r13+1]
0x18013f503  mov     [rbp+var_25], cl
0x18013f506  mov     edx, 1000h; iEscape
0x18013f50b  setnz   al
0x18013f50e  mov     [rbp+var_1A], cx
0x18013f512  add     al, cl
0x18013f514  mov     word ptr [rbp+pvIn], r13w
0x18013f519  mov     rcx, rsi; hdc
0x18013f51c  mov     [rbp+var_26], al
0x18013f51f  xor     r9d, r9d; pvIn
0x18013f522  mov     [rbp+var_24], 5
0x18013f529  xor     r8d, r8d; cjIn
0x18013f52c  mov     [rbp+var_20], r13w
0x18013f531  mov     [rbp+var_1E], r13d
0x18013f535  mov     ebx, r13d
0x18013f538  mov     [rbp+var_18], r13d
0x18013f53c  mov     [rbp+var_14], r13w
0x18013f541  mov     [rbp+var_12], r13
0x18013f545  mov     [rsp+60h+pvOut], r13; pvOut
0x18013f54a  call    cs:__imp_Escape
0x18013f551  nop     dword ptr [rax+rax+00h]
0x18013f556  mov     rcx, rsi; hdc
0x18013f559  mov     r14b, r13b
0x18013f55c  call    cs:__imp_BeginPath
0x18013f563  nop     dword ptr [rax+rax+00h]
0x18013f568  mov     r12d, [rbp+arg_20]
0x18013f56c  jmp     loc_18013F6B0
0x18013f571  movzx   r13d, byte ptr [r15]
0x18013f575  sub     r12d, r8d
0x18013f578  mov     ecx, r13d
0x18013f57b  add     r15, r8
0x18013f57e  and     ecx, 7
0x18013f581  jz      loc_18013F607
0x18013f587  sub     ecx, 1
0x18013f58a  jz      short loc_18013F5C7
0x18013f58c  cmp     ecx, 2
0x18013f58f  jnz     loc_18013F635
0x18013f595  cmp     r14b, r8b
0x18013f598  jnz     short loc_18013F602
0x18013f59a  mov     r8d, ebx; cpt
0x18013f59d  mov     rdx, rdi; apt
0x18013f5a0  mov     rcx, rsi; hdc
0x18013f5a3  call    cs:__imp_PolylineTo
0x18013f5aa  nop     dword ptr [rax+rax+00h]
0x18013f5af  mov     r8d, 1
0x18013f5b5  mov     r14b, 3
0x18013f5b8  mov     edx, [rbp+var_30]
0x18013f5bb  movsxd  rax, ebx
0x18013f5be  mov     ebx, r8d
0x18013f5c1  lea     rdi, [rdi+rax*8]
0x18013f5c5  jmp     short loc_18013F635
0x18013f5c7  cmp     r14b, 3
0x18013f5cb  jnz     short loc_18013F602
0x18013f5cd  mov     eax, 55555556h
0x18013f5d2  imul    ebx
0x18013f5d4  mov     eax, edx
0x18013f5d6  shr     eax, 1Fh
0x18013f5d9  add     edx, eax
0x18013f5db  lea     ecx, [rdx+rdx*2]
0x18013f5de  cmp     ebx, ecx
0x18013f5e0  jnz     short loc_18013F5FD
0x18013f5e2  mov     r8d, ebx; cpt
0x18013f5e5  mov     rdx, rdi; apt
0x18013f5e8  mov     rcx, rsi; hdc
0x18013f5eb  call    cs:__imp_PolyBezierTo
0x18013f5f2  nop     dword ptr [rax+rax+00h]
0x18013f5f7  mov     r8d, 1
0x18013f5fd  mov     r14b, r8b
0x18013f600  jmp     short loc_18013F5B8
0x18013f602  add     ebx, r8d
0x18013f605  jmp     short loc_18013F635
0x18013f607  mov     r8d, [rdi+4]; y
0x18013f60b  xor     r9d, r9d; lppt
0x18013f60e  mov     edx, [rdi]; x
0x18013f610  mov     rcx, rsi; hdc
0x18013f613  call    cs:__imp_MoveToEx
0x18013f61a  nop     dword ptr [rax+rax+00h]
0x18013f61f  mov     r14b, [r15]
0x18013f622  xor     ebx, ebx
0x18013f624  and     r14b, 7
0x18013f628  add     rdi, 8
0x18013f62c  xor     edx, edx
0x18013f62e  mov     [rbp+var_30], edx
0x18013f631  lea     r8d, [rbx+1]
0x18013f635  test    r13b, r13b
0x18013f638  js      short loc_18013F64D
0x18013f63a  xor     r13d, r13d
0x18013f63d  test    r12d, r12d
0x18013f640  jz      short loc_18013F650
0x18013f642  cmp     [r15], r13b
0x18013f645  jnz     short loc_18013F6BC
0x18013f647  test    edx, edx
0x18013f649  jnz     short loc_18013F6BC
0x18013f64b  jmp     short loc_18013F650
0x18013f64d  xor     r13d, r13d
0x18013f650  cmp     r14b, 3
0x18013f654  jnz     short loc_18013F682
0x18013f656  mov     eax, 55555556h
0x18013f65b  imul    ebx
0x18013f65d  mov     eax, edx
0x18013f65f  shr     eax, 1Fh
0x18013f662  add     edx, eax
0x18013f664  lea     ecx, [rdx+rdx*2]
0x18013f667  cmp     ebx, ecx
0x18013f669  jnz     short loc_18013F697
0x18013f66b  mov     r8d, ebx; cpt
0x18013f66e  mov     rdx, rdi; apt
0x18013f671  mov     rcx, rsi; hdc
0x18013f674  call    cs:__imp_PolyBezierTo
0x18013f67b  nop     dword ptr [rax+rax+00h]
0x18013f680  jmp     short loc_18013F697
0x18013f682  mov     r8d, ebx; cpt
0x18013f685  mov     rdx, rdi; apt
0x18013f688  mov     rcx, rsi; hdc
0x18013f68b  call    cs:__imp_PolylineTo
0x18013f692  nop     dword ptr [rax+rax+00h]
0x18013f697  movsxd  rax, ebx
0x18013f69a  mov     rcx, rsi; hdc
0x18013f69d  mov     ebx, r13d
0x18013f6a0  lea     rdi, [rdi+rax*8]
0x18013f6a4  call    cs:__imp_CloseFigure
0x18013f6ab  nop     dword ptr [rax+rax+00h]
0x18013f6b0  mov     r8d, 1
0x18013f6b6  mov     edx, r8d
0x18013f6b9  mov     [rbp+var_30], edx
0x18013f6bc  test    r12d, r12d
0x18013f6bf  jg      loc_18013F571
0x18013f6c5  mov     rcx, rsi; hdc
0x18013f6c8  call    cs:__imp_EndPath
0x18013f6cf  nop     dword ptr [rax+rax+00h]
0x18013f6d4  mov     rcx, rsi; hdc
0x18013f6d7  call    cs:__imp_StrokePath
0x18013f6de  nop     dword ptr [rax+rax+00h]
0x18013f6e3  lea     r9, [rbp+pvIn]; pvIn
0x18013f6e7  mov     [rsp+60h+pvOut], r13; pvOut
0x18013f6ec  mov     edx, 1002h; iEscape
0x18013f6f1  mov     r8d, 1Eh; cjIn
0x18013f6f7  mov     rcx, rsi; hdc
0x18013f6fa  call    cs:__imp_Escape
0x18013f701  nop     dword ptr [rax+rax+00h]
0x18013f706  mov     rcx, [rbp+var_8]
0x18013f70a  xor     rcx, rsp; StackCookie
0x18013f70d  call    __security_check_cookie
0x18013f712  mov     rbx, [rsp+60h+arg_0]
0x18013f71a  add     rsp, 60h
0x18013f71e  pop     r15
0x18013f720  pop     r14
0x18013f722  pop     r13
0x18013f724  pop     r12
0x18013f726  pop     rdi
0x18013f727  pop     rsi
0x18013f728  pop     rbp
0x18013f729  retn
```
