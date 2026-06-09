# ConvertPathToGdi::AndClip(HDC__ *)

- ea: `0x1800dcc0c`
- end: `0x1800dcd84`
- name: `?AndClip@ConvertPathToGdi@@QEAAHPEAUHDC__@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800cd174`
- `0x1801358f0`
- `0x18013d770`

## callees

- `0x18003bb1c`
- `0x18003bbec`
- `0x1800bd49c`
- `0x1800dcc0c`

## import_xrefs

- `GDI32!SelectClipPath` at `0x1800dcd44`
- `GDI32!SelectClipPath` at `0x1800dcd44`
- `GDI32!PolyBezier` at `0x1800dccf0`
- `GDI32!PolyBezier` at `0x1800dccf0`
- `GDI32!SetPolyFillMode` at `0x1800dcc56`
- `GDI32!SetPolyFillMode` at `0x1800dcd5c`
- `GDI32!SetPolyFillMode` at `0x1800dcc56`
- `GDI32!SetPolyFillMode` at `0x1800dcd5c`
- `GDI32!EndPath` at `0x1800dcd2f`
- `GDI32!EndPath` at `0x1800dcd2f`
- `GDI32!BeginPath` at `0x1800dcc3f`
- `GDI32!BeginPath` at `0x1800dcc3f`
- `GDI32!PolyPolygon` at `0x1800dccc8`
- `GDI32!PolyPolygon` at `0x1800dccc8`
- `GDI32!Polygon` at `0x1800dcca5`
- `GDI32!Polygon` at `0x1800dcca5`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::AndClip(ConvertPathToGdi *this, HDC a2)
{
  unsigned int v4; // ebx
  BOOL v5; // edi
  int v6; // r14d
  int v7; // eax
  int v8; // ecx
  int v9; // r15d
  int v10; // r9d
  int v11; // eax
  int v12; // edi

  v4 = 1;
  if ( *((int *)this + 106) <= 0 )
    return v4;
  v5 = BeginPath(a2);
  v6 = SetPolyFillMode(a2, *((_DWORD *)this + 108));
  v7 = SetupForIncreasedResolution(*((_DWORD *)this + 111), a2);
  v8 = *((_DWORD *)this + 109);
  v9 = v7;
  if ( (v8 & 1) != 0 )
  {
    v10 = *((_DWORD *)this + 107);
    if ( v10 == 1 )
    {
      if ( !v5 )
        goto LABEL_15;
      v11 = Polygon(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
    }
    else
    {
      if ( !v5 )
        goto LABEL_15;
      v11 = PolyPolygon(a2, *((const POINT **)this + 51), *((const INT **)this + 52), v10);
    }
  }
  else if ( (v8 & 0x10) != 0 )
  {
    if ( !v5 )
      goto LABEL_15;
    v11 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
  }
  else
  {
    if ( !v5 )
      goto LABEL_15;
    v11 = ConvertPathToGdi::DrawMixedPath(this, a2);
  }
  if ( v11 )
  {
    v12 = 1;
    goto LABEL_16;
  }
LABEL_15:
  v12 = 0;
LABEL_16:
  CleanupForIncreasedResolution(*((_DWORD *)this + 111), v9, a2);
  if ( !v12 || !EndPath(a2) || !SelectClipPath(a2, 1) )
    v4 = 0;
  SetPolyFillMode(a2, v6);
  return v4;
}

```

## disassembly

```asm
0x1800dcc0c  mov     [rsp+arg_0], rbx
0x1800dcc11  mov     [rsp+arg_8], rbp
0x1800dcc16  mov     [rsp+arg_10], rsi
0x1800dcc1b  push    rdi
0x1800dcc1c  push    r14
0x1800dcc1e  push    r15
0x1800dcc20  sub     rsp, 20h
0x1800dcc24  cmp     dword ptr [rcx+1A8h], 0
0x1800dcc2b  mov     rbp, rdx
0x1800dcc2e  mov     rsi, rcx
0x1800dcc31  mov     ebx, 1
0x1800dcc36  jle     loc_1800DCD68
0x1800dcc3c  mov     rcx, rdx; hdc
0x1800dcc3f  call    cs:__imp_BeginPath
0x1800dcc46  nop     dword ptr [rax+rax+00h]
0x1800dcc4b  mov     edx, [rsi+1B0h]; mode
0x1800dcc51  mov     rcx, rbp; hdc
0x1800dcc54  mov     edi, eax
0x1800dcc56  call    cs:__imp_SetPolyFillMode
0x1800dcc5d  nop     dword ptr [rax+rax+00h]
0x1800dcc62  mov     ecx, [rsi+1BCh]; int
0x1800dcc68  mov     rdx, rbp; HDC
0x1800dcc6b  mov     r14d, eax
0x1800dcc6e  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x1800dcc73  mov     ecx, [rsi+1B4h]
0x1800dcc79  mov     r15d, eax
0x1800dcc7c  test    bl, cl
0x1800dcc7e  jz      short loc_1800DCCD6
0x1800dcc80  mov     r9d, [rsi+1ACh]; csz
0x1800dcc87  cmp     r9d, ebx
0x1800dcc8a  jnz     short loc_1800DCCB3
0x1800dcc8c  test    edi, edi
0x1800dcc8e  jz      loc_1800DCD15
0x1800dcc94  mov     r8d, [rsi+1A8h]; cpt
0x1800dcc9b  mov     rcx, rbp; hdc
0x1800dcc9e  mov     rdx, [rsi+198h]; apt
0x1800dcca5  call    cs:__imp_Polygon
0x1800dccac  nop     dword ptr [rax+rax+00h]
0x1800dccb1  jmp     short loc_1800DCD0D
0x1800dccb3  test    edi, edi
0x1800dccb5  jz      short loc_1800DCD15
0x1800dccb7  mov     r8, [rsi+1A0h]; asz
0x1800dccbe  mov     rcx, rbp; hdc
0x1800dccc1  mov     rdx, [rsi+198h]; apt
0x1800dccc8  call    cs:__imp_PolyPolygon
0x1800dcccf  nop     dword ptr [rax+rax+00h]
0x1800dccd4  jmp     short loc_1800DCD0D
0x1800dccd6  test    cl, 10h
0x1800dccd9  jz      short loc_1800DCCFE
0x1800dccdb  test    edi, edi
0x1800dccdd  jz      short loc_1800DCD15
0x1800dccdf  mov     r8d, [rsi+1A8h]; cpt
0x1800dcce6  mov     rcx, rbp; hdc
0x1800dcce9  mov     rdx, [rsi+198h]; apt
0x1800dccf0  call    cs:__imp_PolyBezier
0x1800dccf7  nop     dword ptr [rax+rax+00h]
0x1800dccfc  jmp     short loc_1800DCD0D
0x1800dccfe  test    edi, edi
0x1800dcd00  jz      short loc_1800DCD15
0x1800dcd02  mov     rdx, rbp; HDC
0x1800dcd05  mov     rcx, rsi; this
0x1800dcd08  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x1800dcd0d  test    eax, eax
0x1800dcd0f  jz      short loc_1800DCD15
0x1800dcd11  mov     edi, ebx
0x1800dcd13  jmp     short loc_1800DCD17
0x1800dcd15  xor     edi, edi
0x1800dcd17  mov     ecx, [rsi+1BCh]; int
0x1800dcd1d  mov     r8, rbp; HDC
0x1800dcd20  mov     edx, r15d; int
0x1800dcd23  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x1800dcd28  test    edi, edi
0x1800dcd2a  jz      short loc_1800DCD54
0x1800dcd2c  mov     rcx, rbp; hdc
0x1800dcd2f  call    cs:__imp_EndPath
0x1800dcd36  nop     dword ptr [rax+rax+00h]
0x1800dcd3b  test    eax, eax
0x1800dcd3d  jz      short loc_1800DCD54
0x1800dcd3f  mov     edx, ebx; mode
0x1800dcd41  mov     rcx, rbp; hdc
0x1800dcd44  call    cs:__imp_SelectClipPath
0x1800dcd4b  nop     dword ptr [rax+rax+00h]
0x1800dcd50  test    eax, eax
0x1800dcd52  jnz     short loc_1800DCD56
0x1800dcd54  xor     ebx, ebx
0x1800dcd56  mov     edx, r14d; mode
0x1800dcd59  mov     rcx, rbp; hdc
0x1800dcd5c  call    cs:__imp_SetPolyFillMode
0x1800dcd63  nop     dword ptr [rax+rax+00h]
0x1800dcd68  mov     rbp, [rsp+38h+arg_8]
0x1800dcd6d  mov     eax, ebx
0x1800dcd6f  mov     rbx, [rsp+38h+arg_0]
0x1800dcd74  mov     rsi, [rsp+38h+arg_10]
0x1800dcd79  add     rsp, 20h
0x1800dcd7d  pop     r15
0x1800dcd7f  pop     r14
0x1800dcd81  pop     rdi
0x1800dcd82  retn
```
