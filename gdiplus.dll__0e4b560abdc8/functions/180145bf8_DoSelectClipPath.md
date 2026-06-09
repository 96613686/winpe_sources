# DoSelectClipPath

- ea: `0x180145bf8`
- end: `0x180145eb1`
- name: `DoSelectClipPath`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180140b10`

## callees

- `0x1800b12a8`
- `0x1800b2190`
- `0x1800b2b34`
- `0x1800d4f9c`
- `0x18013ec88`
- `0x18013f024`
- `0x1801453c0`
- `0x180145bf8`

## import_xrefs

- `GDI32!SelectClipPath` at `0x180145e63`
- `GDI32!SelectClipPath` at `0x180145e63`
- `GDI32!ExtSelectClipRgn` at `0x180145e38`
- `GDI32!ExtSelectClipRgn` at `0x180145e38`
- `GDI32!MoveToEx` at `0x180145d1d`
- `GDI32!MoveToEx` at `0x180145d39`
- `GDI32!MoveToEx` at `0x180145d1d`
- `GDI32!MoveToEx` at `0x180145d39`
- `GDI32!SetROP2` at `0x180145cea`
- `GDI32!SetROP2` at `0x180145cea`
- `GDI32!GetROP2` at `0x180145c75`
- `GDI32!GetROP2` at `0x180145c75`
- `GDI32!DeleteObject` at `0x180145e49`
- `GDI32!DeleteObject` at `0x180145e49`
- `GDI32!CreateRectRgn` at `0x180145e13`
- `GDI32!CreateRectRgn` at `0x180145e13`

## pseudocode

```c
__int64 __fastcall DoSelectClipPath(__int64 a1, int a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // r14d
  int v7; // eax
  HDC v8; // rcx
  int ROP2; // eax
  int v10; // ebx
  __int64 result; // rax
  HRGN RectRgn; // rax
  HRGN v13; // rbp
  int v14; // ebx
  __int16 v15; // [rsp+68h] [rbp+10h] BYREF

  v4 = bNoDCRgn(a1, 1);
  v5 = v4;
  v6 = 0;
  if ( (((a2 - 1) & 0xFFFFFFFB) == 0 || a2 == 2 && v4) && (*(_BYTE *)(a1 + 4) & 0x10) != 0 )
  {
    v7 = *(_DWORD *)(a1 + 484);
    switch ( v7 )
    {
      case 0:
        v8 = *(HDC *)(a1 + 40);
        *(_DWORD *)(a1 + 488) = *(_DWORD *)(a1 + 452);
        *(_DWORD *)(a1 + 484) = 1;
        ROP2 = GetROP2(v8);
        v10 = ROP2;
        if ( ROP2 != 13 && ROP2 != 4 )
        {
          *(_DWORD *)(a1 + 4) |= 0x40000000u;
          return 0;
        }
        if ( !(unsigned int)DoSaveDC(a1) )
          return 0;
        *(_DWORD *)(a1 + 472) = v10;
        v15 = 1;
        if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) )
          return 0;
        SetROP2(*(HDC *)(a1 + 40), 7);
        if ( !(unsigned int)bW16Emit1(a1, 260, 7) )
          return 0;
        MoveToEx(*(HDC *)(a1 + 40), 0, 0, (LPPOINT)(a1 + 476));
        MoveToEx(*(HDC *)(a1 + 40), *(_DWORD *)(a1 + 476), *(_DWORD *)(a1 + 480), 0);
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 504);
        return 1;
      case 1:
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 504);
        return 1;
      case 3:
        return (unsigned int)ConvertPathToPSClipPath(a1, 0)
            && (unsigned int)bW16Emit5(a1, 1574, 262, 20560, 20052, 6, 15);
    }
  }
  if ( (unsigned int)ConvertPathToPSClipPath(a1, 1) )
  {
    ++*(_DWORD *)(a1 + 456);
    v15 = 1;
    v6 = 1;
    if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) )
      return 0;
  }
  if ( (unsigned int)(a2 - 2) <= 2 )
  {
    if ( v5 )
    {
      RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
      v13 = RectRgn;
      if ( !RectRgn )
        return 0;
      v14 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
      DeleteObject(v13);
      if ( !v14 )
        return 0;
    }
  }
  if ( !SelectClipPath(*(HDC *)(a1 + 40), a2) )
    return 0;
  result = bDumpDCClipping(a1);
  if ( v6 )
  {
    v15 = 0;
    return (unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) != 0 ? (unsigned int)result : 0;
  }
  return result;
}

```

## disassembly

```asm
0x180145bf8  mov     [rsp+arg_0], rbx
0x180145bfd  mov     [rsp+arg_10], rbp
0x180145c02  mov     [rsp+arg_18], rsi
0x180145c07  push    rdi
0x180145c08  push    r14
0x180145c0a  push    r15
0x180145c0c  sub     rsp, 40h
0x180145c10  mov     esi, edx
0x180145c12  mov     ebp, 1
0x180145c17  mov     edx, ebp
0x180145c19  mov     rdi, rcx
0x180145c1c  call    bNoDCRgn
0x180145c21  xor     r15d, r15d
0x180145c24  lea     r8d, [rsi-1]
0x180145c28  mov     ebx, eax
0x180145c2a  mov     r14d, r15d
0x180145c2d  test    r8d, 0FFFFFFFBh
0x180145c34  jz      short loc_180145C47
0x180145c36  cmp     esi, 2
0x180145c39  jnz     loc_180145DBD
0x180145c3f  test    eax, eax
0x180145c41  jz      loc_180145DBD
0x180145c47  test    byte ptr [rdi+4], 10h
0x180145c4b  jz      loc_180145DBD
0x180145c51  mov     eax, [rdi+1E4h]
0x180145c57  test    eax, eax
0x180145c59  jnz     loc_180145D5A
0x180145c5f  mov     eax, [rdi+1C4h]
0x180145c65  mov     rcx, [rdi+28h]; hdc
0x180145c69  mov     [rdi+1E8h], eax
0x180145c6f  mov     [rdi+1E4h], ebp
0x180145c75  call    cs:__imp_GetROP2
0x180145c7c  nop     dword ptr [rax+rax+00h]
0x180145c81  mov     ebx, eax
0x180145c83  cmp     eax, 0Dh
0x180145c86  jz      short loc_180145CAE
0x180145c88  cmp     eax, 4
0x180145c8b  jz      short loc_180145CAE
0x180145c8d  bts     dword ptr [rdi+4], 1Eh
0x180145c92  xor     eax, eax
0x180145c94  mov     rbx, [rsp+58h+arg_0]
0x180145c99  mov     rbp, [rsp+58h+arg_10]
0x180145c9e  mov     rsi, [rsp+58h+arg_18]
0x180145ca3  add     rsp, 40h
0x180145ca7  pop     r15
0x180145ca9  pop     r14
0x180145cab  pop     rdi
0x180145cac  retn
0x180145cae  mov     rcx, rdi
0x180145cb1  call    DoSaveDC
0x180145cb6  test    eax, eax
0x180145cb8  jz      short loc_180145C92
0x180145cba  mov     edx, 26h ; '&'
0x180145cbf  mov     [rdi+1D8h], ebx
0x180145cc5  lea     r9, [rsp+58h+arg_8]
0x180145cca  mov     [rsp+58h+arg_8], bp
0x180145ccf  mov     rcx, rdi
0x180145cd2  lea     r8d, [rdx-24h]
0x180145cd6  call    bEmitWin16Escape
0x180145cdb  test    eax, eax
0x180145cdd  jz      short loc_180145C92
0x180145cdf  mov     rcx, [rdi+28h]; hdc
0x180145ce3  mov     ebx, 7
0x180145ce8  mov     edx, ebx; rop2
0x180145cea  call    cs:__imp_SetROP2
0x180145cf1  nop     dword ptr [rax+rax+00h]
0x180145cf6  mov     r8d, ebx
0x180145cf9  mov     edx, 104h
0x180145cfe  mov     rcx, rdi
0x180145d01  call    bW16Emit1
0x180145d06  test    eax, eax
0x180145d08  jz      short loc_180145C92
0x180145d0a  mov     rcx, [rdi+28h]; hdc
0x180145d0e  lea     rbx, [rdi+1DCh]
0x180145d15  mov     r9, rbx; lppt
0x180145d18  xor     r8d, r8d; y
0x180145d1b  xor     edx, edx; x
0x180145d1d  call    cs:__imp_MoveToEx
0x180145d24  nop     dword ptr [rax+rax+00h]
0x180145d29  mov     r8d, [rdi+1E0h]; y
0x180145d30  xor     r9d, r9d; lppt
0x180145d33  mov     edx, [rbx]; x
0x180145d35  mov     rcx, [rdi+28h]; hdc
0x180145d39  call    cs:__imp_MoveToEx
0x180145d40  nop     dword ptr [rax+rax+00h]
0x180145d45  mov     rcx, [rdi+1F8h]
0x180145d4c  mov     [rdi+218h], rcx
0x180145d53  mov     eax, ebp
0x180145d55  jmp     loc_180145C94
0x180145d5a  cmp     eax, ebp
0x180145d5c  jnz     short loc_180145D6E
0x180145d5e  mov     rax, [rdi+1F8h]
0x180145d65  mov     [rdi+218h], rax
0x180145d6c  jmp     short loc_180145D53
0x180145d6e  cmp     eax, 3
0x180145d71  jnz     short loc_180145DBD
0x180145d73  xor     edx, edx
0x180145d75  mov     rcx, rdi
0x180145d78  call    ConvertPathToPSClipPath
0x180145d7d  test    eax, eax
0x180145d7f  jz      loc_180145C92
0x180145d85  mov     [rsp+58h+var_28], 0Fh
0x180145d8c  mov     edx, 626h
0x180145d91  mov     [rsp+58h+var_30], 6
0x180145d98  mov     r9d, 5050h
0x180145d9e  mov     r8d, 106h
0x180145da4  mov     [rsp+58h+var_38], 4E54h
0x180145dab  mov     rcx, rdi
0x180145dae  call    bW16Emit5
0x180145db3  test    eax, eax
0x180145db5  jz      loc_180145C92
0x180145dbb  jmp     short loc_180145D53
0x180145dbd  mov     edx, ebp
0x180145dbf  mov     rcx, rdi
0x180145dc2  call    ConvertPathToPSClipPath
0x180145dc7  test    eax, eax
0x180145dc9  jz      short loc_180145DF7
0x180145dcb  add     [rdi+1C8h], ebp
0x180145dd1  lea     r9, [rsp+58h+arg_8]
0x180145dd6  mov     edx, 26h ; '&'
0x180145ddb  mov     [rsp+58h+arg_8], bp
0x180145de0  mov     rcx, rdi
0x180145de3  mov     r14d, ebp
0x180145de6  lea     r8d, [rdx-24h]
0x180145dea  call    bEmitWin16Escape
0x180145def  test    eax, eax
0x180145df1  jz      loc_180145C92
0x180145df7  lea     eax, [rsi-2]
0x180145dfa  cmp     eax, 2
0x180145dfd  ja      short loc_180145E5D
0x180145dff  test    ebx, ebx
0x180145e01  jz      short loc_180145E5D
0x180145e03  mov     r8d, 7FFFh; x2
0x180145e09  mov     ecx, 0FFFF8000h; x1
0x180145e0e  mov     r9d, r8d; y2
0x180145e11  mov     edx, ecx; y1
0x180145e13  call    cs:__imp_CreateRectRgn
0x180145e1a  nop     dword ptr [rax+rax+00h]
0x180145e1f  mov     rbp, rax
0x180145e22  test    rax, rax
0x180145e25  jz      loc_180145C92
0x180145e2b  mov     rcx, [rdi+28h]; hdc
0x180145e2f  mov     r8d, 5; mode
0x180145e35  mov     rdx, rax; hrgn
0x180145e38  call    cs:__imp_ExtSelectClipRgn
0x180145e3f  nop     dword ptr [rax+rax+00h]
0x180145e44  mov     rcx, rbp; ho
0x180145e47  mov     ebx, eax
0x180145e49  call    cs:__imp_DeleteObject
0x180145e50  nop     dword ptr [rax+rax+00h]
0x180145e55  test    ebx, ebx
0x180145e57  jz      loc_180145C92
0x180145e5d  mov     rcx, [rdi+28h]; hdc
0x180145e61  mov     edx, esi; mode
0x180145e63  call    cs:__imp_SelectClipPath
0x180145e6a  nop     dword ptr [rax+rax+00h]
0x180145e6f  test    eax, eax
0x180145e71  jz      loc_180145C92
0x180145e77  mov     rcx, rdi
0x180145e7a  call    bDumpDCClipping
0x180145e7f  mov     ebx, eax
0x180145e81  test    r14d, r14d
0x180145e84  jz      loc_180145C94
0x180145e8a  mov     edx, 26h ; '&'
0x180145e8f  mov     [rsp+58h+arg_8], r15w
0x180145e95  lea     r9, [rsp+58h+arg_8]
0x180145e9a  mov     rcx, rdi
0x180145e9d  lea     r8d, [rdx-24h]
0x180145ea1  call    bEmitWin16Escape
0x180145ea6  neg     eax
0x180145ea8  sbb     eax, eax
0x180145eaa  and     eax, ebx
0x180145eac  jmp     loc_180145C94
```
