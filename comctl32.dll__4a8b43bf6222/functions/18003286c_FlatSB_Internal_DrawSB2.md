# FlatSB_Internal_DrawSB2

- ea: `0x18003286c`
- end: `0x180032a87`
- name: `FlatSB_Internal_DrawSB2`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180032a90`

## callees

- `0x1800115f0`
- `0x180031efc`
- `0x18003286c`
- `0x180032c2c`

## import_xrefs

- `GDI32!SelectObject` at `0x180032945`
- `GDI32!SelectObject` at `0x180032a4c`
- `GDI32!SelectObject` at `0x180032945`
- `GDI32!SelectObject` at `0x180032a4c`
- `USER32!GetSysColorBrush` at `0x180032939`
- `USER32!GetSysColorBrush` at `0x180032939`
- `USER32!CopyRect` at `0x18003295a`
- `USER32!CopyRect` at `0x18003295a`

## pseudocode

```c
__int64 __fastcall FlatSB_Internal_DrawSB2(RECT *a1, HDC a2, unsigned int a3, int a4, int a5)
{
  unsigned int v9; // ebx
  int left; // ebx
  __int64 result; // rax
  LONG v12; // r8d
  LONG v13; // r12d
  int v14; // r14d
  RECT *v15; // rcx
  RECT *v16; // rdx
  HBRUSH SysColorBrush; // rax
  UINT v18; // r9d
  HGDIOBJ h; // [rsp+30h] [rbp-20h]
  struct tagRECT rcDst; // [rsp+38h] [rbp-18h] BYREF

  if ( a1 )
  {
    left = a1[17].left;
    if ( a3 )
      left >>= 2;
    v9 = left & 3;
  }
  else
  {
    v9 = 0;
  }
  result = (unsigned int)((a1[1].right - a1[3].top) / 2);
  rcDst = 0;
  if ( (int)result > 0 )
  {
    v12 = a1[2].left;
    if ( a1[2].right - v12 > 0 )
    {
      v13 = a1[13].left;
      v14 = *(_DWORD *)((a3 != 0 ? 8 : 0) + *(_QWORD *)&a1->left + 4LL);
      v15 = (RECT *)((char *)a1 + 148);
      v16 = a1 + 9;
      if ( (int)result <= v14 )
        v14 = result;
      if ( a3 )
      {
        v16 = (RECT *)((char *)a1 + 148);
        v15 = a1 + 9;
      }
      v15->left = v12;
      v16->left = a1[3].top;
      v15->right = a1[2].right;
      v16->right = a1[1].right;
      SysColorBrush = GetSysColorBrush(18);
      h = SelectObject(a2, SysColorBrush);
      CopyRect(&rcDst, a1 + 9);
      if ( a3 )
      {
        rcDst.bottom = v14 + rcDst.top;
        if ( !a4 || v13 == 1 || a5 == 1 )
          FlatSB_Internal_DrawArrow(a1, a2, &rcDst, 0, (v9 & 1) << 8);
        rcDst.bottom = a1[9].bottom;
        rcDst.top = rcDst.bottom - v14;
        if ( a4 && v13 != 2 && a5 != 2 )
          goto LABEL_30;
        v18 = 1;
      }
      else
      {
        rcDst.right = v14 + rcDst.left;
        if ( !a4 || v13 == 5 || a5 == 5 )
          FlatSB_Internal_DrawArrow(a1, a2, &rcDst, 2u, (v9 & 1) << 8);
        rcDst.right = a1[9].right;
        rcDst.left = rcDst.right - v14;
        if ( a4 && v13 != 6 && a5 != 6 )
          goto LABEL_30;
        v18 = 3;
      }
      FlatSB_Internal_DrawArrow(a1, a2, &rcDst, v18, (v9 & 2) << 7);
LABEL_30:
      SelectObject(a2, h);
      return FlatSB_Internal_DrawThumb2(a1, a2, a3, v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003286c  mov     [rsp-38h+arg_18], rbx
0x180032871  push    rbp
0x180032872  push    rsi
0x180032873  push    rdi
0x180032874  push    r12
0x180032876  push    r13
0x180032878  push    r14
0x18003287a  push    r15
0x18003287c  mov     rbp, rsp
0x18003287f  sub     rsp, 50h
0x180032883  mov     rax, cs:__security_cookie
0x18003288a  xor     rax, rsp
0x18003288d  mov     [rbp+var_8], rax
0x180032891  mov     r15d, r9d
0x180032894  mov     r13d, r8d
0x180032897  mov     rsi, rdx
0x18003289a  mov     rdi, rcx
0x18003289d  test    rcx, rcx
0x1800328a0  jnz     short loc_1800328A6
0x1800328a2  xor     ebx, ebx
0x1800328a4  jmp     short loc_1800328B7
0x1800328a6  mov     ebx, [rcx+110h]
0x1800328ac  test    r13d, r13d
0x1800328af  jz      short loc_1800328B4
0x1800328b1  sar     ebx, 2
0x1800328b4  and     ebx, 3
0x1800328b7  mov     eax, [rcx+18h]
0x1800328ba  xorps   xmm0, xmm0
0x1800328bd  sub     eax, [rcx+34h]
0x1800328c0  cdq
0x1800328c1  sub     eax, edx
0x1800328c3  sar     eax, 1
0x1800328c5  mov     r9d, eax
0x1800328c8  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800328cc  test    eax, eax
0x1800328ce  jle     loc_180032A63
0x1800328d4  mov     r8d, [rcx+20h]
0x1800328d8  mov     ecx, [rcx+28h]
0x1800328db  sub     ecx, r8d
0x1800328de  test    ecx, ecx
0x1800328e0  jle     loc_180032A63
0x1800328e6  mov     rax, [rdi]
0x1800328e9  mov     ecx, r13d
0x1800328ec  mov     r12d, [rdi+0D0h]
0x1800328f3  neg     ecx
0x1800328f5  sbb     rdx, rdx
0x1800328f8  and     edx, 8
0x1800328fb  mov     r14d, [rdx+rax+4]
0x180032900  lea     rax, [rdi+90h]
0x180032907  lea     rcx, [rax+4]
0x18003290b  mov     rdx, rax
0x18003290e  cmp     r9d, r14d
0x180032911  cmovle  r14d, r9d
0x180032915  test    r13d, r13d
0x180032918  cmovnz  rdx, rcx
0x18003291c  cmovnz  rcx, rax
0x180032920  mov     [rcx], r8d
0x180032923  mov     eax, [rdi+34h]
0x180032926  mov     [rdx], eax
0x180032928  mov     eax, [rdi+28h]
0x18003292b  mov     [rcx+8], eax
0x18003292e  mov     ecx, 12h; nIndex
0x180032933  mov     eax, [rdi+18h]
0x180032936  mov     [rdx+8], eax
0x180032939  call    cs:__imp_GetSysColorBrush
0x18003293f  mov     rdx, rax; h
0x180032942  mov     rcx, rsi; hdc
0x180032945  call    cs:__imp_SelectObject
0x18003294b  lea     rdx, [rdi+90h]; lprcSrc
0x180032952  mov     [rbp+h], rax
0x180032956  lea     rcx, [rbp+rcDst]; lprcDst
0x18003295a  call    cs:__imp_CopyRect
0x180032960  test    r13d, r13d
0x180032963  jz      short loc_1800329C9
0x180032965  mov     edx, [rbp+rcDst.top]
0x180032968  add     edx, r14d
0x18003296b  mov     [rbp+rcDst.bottom], edx
0x18003296e  test    r15d, r15d
0x180032971  jz      short loc_18003297F
0x180032973  cmp     r12d, 1
0x180032977  jz      short loc_18003297F
0x180032979  cmp     [rbp+arg_20], 1
0x18003297d  jnz     short loc_18003299D
0x18003297f  mov     eax, ebx
0x180032981  lea     r8, [rbp+rcDst]
0x180032985  and     eax, 1
0x180032988  xor     r9d, r9d
0x18003298b  shl     eax, 8
0x18003298e  mov     rdx, rsi
0x180032991  mov     rcx, rdi
0x180032994  mov     [rsp+50h+var_30], eax
0x180032998  call    FlatSB_Internal_DrawArrow
0x18003299d  mov     eax, [rdi+9Ch]
0x1800329a3  mov     [rbp+rcDst.bottom], eax
0x1800329a6  sub     eax, r14d
0x1800329a9  mov     [rbp+rcDst.top], eax
0x1800329ac  test    r15d, r15d
0x1800329af  jz      short loc_1800329C1
0x1800329b1  cmp     r12d, 2
0x1800329b5  jz      short loc_1800329C1
0x1800329b7  cmp     [rbp+arg_20], 2
0x1800329bb  jnz     loc_180032A45
0x1800329c1  mov     r9d, 1
0x1800329c7  jmp     short loc_180032A2A
0x1800329c9  mov     ecx, [rbp+rcDst.left]
0x1800329cc  add     ecx, r14d
0x1800329cf  mov     [rbp+rcDst.right], ecx
0x1800329d2  test    r15d, r15d
0x1800329d5  jz      short loc_1800329E3
0x1800329d7  cmp     r12d, 5
0x1800329db  jz      short loc_1800329E3
0x1800329dd  cmp     [rbp+arg_20], 5
0x1800329e1  jnz     short loc_180032A04
0x1800329e3  mov     eax, ebx
0x1800329e5  lea     r8, [rbp+rcDst]
0x1800329e9  and     eax, 1
0x1800329ec  mov     r9d, 2
0x1800329f2  shl     eax, 8
0x1800329f5  mov     rdx, rsi
0x1800329f8  mov     rcx, rdi
0x1800329fb  mov     [rsp+50h+var_30], eax
0x1800329ff  call    FlatSB_Internal_DrawArrow
0x180032a04  mov     eax, [rdi+98h]
0x180032a0a  mov     [rbp+rcDst.right], eax
0x180032a0d  sub     eax, r14d
0x180032a10  mov     [rbp+rcDst.left], eax
0x180032a13  test    r15d, r15d
0x180032a16  jz      short loc_180032A24
0x180032a18  cmp     r12d, 6
0x180032a1c  jz      short loc_180032A24
0x180032a1e  cmp     [rbp+arg_20], 6
0x180032a22  jnz     short loc_180032A45
0x180032a24  mov     r9d, 3
0x180032a2a  mov     eax, ebx
0x180032a2c  lea     r8, [rbp+rcDst]
0x180032a30  and     eax, 2
0x180032a33  mov     rdx, rsi
0x180032a36  shl     eax, 7
0x180032a39  mov     rcx, rdi
0x180032a3c  mov     [rsp+50h+var_30], eax
0x180032a40  call    FlatSB_Internal_DrawArrow
0x180032a45  mov     rdx, [rbp+h]; h
0x180032a49  mov     rcx, rsi; hdc
0x180032a4c  call    cs:__imp_SelectObject
0x180032a52  mov     r9d, ebx
0x180032a55  mov     r8d, r13d
0x180032a58  mov     rdx, rsi
0x180032a5b  mov     rcx, rdi
0x180032a5e  call    FlatSB_Internal_DrawThumb2
0x180032a63  mov     rcx, [rbp+var_8]
0x180032a67  xor     rcx, rsp; StackCookie
0x180032a6a  call    __security_check_cookie
0x180032a6f  mov     rbx, [rsp+50h+arg_18]
0x180032a77  add     rsp, 50h
0x180032a7b  pop     r15
0x180032a7d  pop     r14
0x180032a7f  pop     r13
0x180032a81  pop     r12
0x180032a83  pop     rdi
0x180032a84  pop     rsi
0x180032a85  pop     rbp
0x180032a86  retn
```
