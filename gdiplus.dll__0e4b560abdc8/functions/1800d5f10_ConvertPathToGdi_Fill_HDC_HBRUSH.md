# ConvertPathToGdi::Fill(HDC__ *,HBRUSH__ *)

- ea: `0x1800d5f10`
- end: `0x1800d61d4`
- name: `?Fill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h)`
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002ac30`
- `0x180131730`
- `0x180132b78`
- `0x1801331f0`
- `0x18013a6b4`

## callees

- `0x18003bb1c`
- `0x18003bbec`
- `0x1800bd49c`
- `0x1800d5f10`
- `0x18013ae2c`

## import_xrefs

- `GDI32!FillPath` at `0x1800d6158`
- `GDI32!FillPath` at `0x1800d6158`
- `GDI32!PolyBezier` at `0x1800d6132`
- `GDI32!PolyBezier` at `0x1800d6132`
- `GDI32!SetPolyFillMode` at `0x1800d5f97`
- `GDI32!SetPolyFillMode` at `0x1800d6170`
- `GDI32!SetPolyFillMode` at `0x1800d5f97`
- `GDI32!SetPolyFillMode` at `0x1800d6170`
- `GDI32!EndPath` at `0x1800d6145`
- `GDI32!EndPath` at `0x1800d6145`
- `GDI32!BeginPath` at `0x1800d6104`
- `GDI32!BeginPath` at `0x1800d6104`
- `GDI32!Polygon` at `0x1800d6060`
- `GDI32!Polygon` at `0x1800d6060`
- `GDI32!GetStockObject` at `0x1800d5fee`
- `GDI32!GetStockObject` at `0x1800d5fee`
- `GDI32!SelectObject` at `0x1800d5f7f`
- `GDI32!SelectObject` at `0x1800d6000`
- `GDI32!SelectObject` at `0x1800d60f3`
- `GDI32!SelectObject` at `0x1800d6182`
- `GDI32!SelectObject` at `0x1800d5f7f`
- `GDI32!SelectObject` at `0x1800d6000`
- `GDI32!SelectObject` at `0x1800d60f3`
- `GDI32!SelectObject` at `0x1800d6182`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::Fill(ConvertPathToGdi *this, HDC a2, HBRUSH h)
{
  unsigned int v6; // ebp
  int v7; // r15d
  int v8; // ebx
  HGDIOBJ v9; // r12
  int v10; // r13d
  HGDIOBJ StockObject; // rax
  HGDIOBJ v12; // r14
  unsigned int v13; // eax
  int v14; // edx
  __int64 v15; // rax
  BOOL v16; // eax
  int v17; // eax
  _QWORD v19[2]; // [rsp+20h] [rbp-58h] BYREF
  int v20; // [rsp+30h] [rbp-48h]
  unsigned int v21; // [rsp+80h] [rbp+8h]
  unsigned int v22; // [rsp+80h] [rbp+8h]

  v6 = 1;
  if ( *((int *)this + 106) > 0 )
  {
    v7 = SetupForIncreasedResolution(*((_DWORD *)this + 111), a2);
    v8 = _mm_getcsr();
    _mm_setcsr(v8 & 0xFFFFFFC0);
    v9 = SelectObject(a2, h);
    v10 = SetPolyFillMode(a2, *((_DWORD *)this + 108));
    _mm_setcsr(v8 & 0xFFFFFFC0);
    if ( (*((_BYTE *)this + 436) & 1) != 0 )
    {
      v21 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v21);
      StockObject = GetStockObject(8);
      v12 = SelectObject(a2, StockObject);
      _mm_setcsr(v21);
      if ( *((_DWORD *)this + 107) == 1 )
      {
        v22 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v22);
        v13 = Polygon(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
      }
      else
      {
        v14 = *((_DWORD *)this + 107);
        v22 = _mm_getcsr() & 0xFFFFFFC0;
        v15 = *((_QWORD *)this + 51);
        _mm_setcsr(v22);
        v19[1] = *((_QWORD *)this + 52);
        v20 = v14;
        v19[0] = v15;
        v13 = CPolyPolygon::Draw((CPolyPolygon *)v19, a2);
      }
      _mm_setcsr(v22);
      v6 = v13;
      SelectObject(a2, v12);
      goto LABEL_14;
    }
    v16 = BeginPath(a2);
    if ( (*((_BYTE *)this + 436) & 0x10) != 0 )
    {
      if ( v16 )
      {
        v17 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
LABEL_10:
        if ( v17 && EndPath(a2) && FillPath(a2) )
          goto LABEL_14;
      }
    }
    else if ( v16 )
    {
      v17 = ConvertPathToGdi::DrawMixedPath(this, a2);
      goto LABEL_10;
    }
    v6 = 0;
LABEL_14:
    SetPolyFillMode(a2, v10);
    SelectObject(a2, v9);
    CleanupForIncreasedResolution(*((_DWORD *)this + 111), v7, a2);
  }
  return v6;
}

```

## disassembly

```asm
0x1800d5f10  mov     [rsp+arg_8], rbx
0x1800d5f15  mov     [rsp+arg_10], rbp
0x1800d5f1a  mov     [rsp+arg_18], rsi
0x1800d5f1f  push    rdi
0x1800d5f20  push    r12
0x1800d5f22  push    r13
0x1800d5f24  push    r14
0x1800d5f26  push    r15
0x1800d5f28  sub     rsp, 50h
0x1800d5f2c  xor     ebx, ebx
0x1800d5f2e  mov     r14, r8
0x1800d5f31  mov     rdi, rdx
0x1800d5f34  mov     rsi, rcx
0x1800d5f37  mov     ebp, 1
0x1800d5f3c  cmp     [rcx+1A8h], ebx
0x1800d5f42  jle     loc_1800D619F
0x1800d5f48  mov     ecx, [rcx+1BCh]; int
0x1800d5f4e  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x1800d5f53  mov     r15d, eax
0x1800d5f56  stmxcsr [rsp+78h+arg_0]
0x1800d5f5e  mov     ebx, [rsp+78h+arg_0]
0x1800d5f65  mov     rdx, r14; h
0x1800d5f68  mov     eax, ebx
0x1800d5f6a  mov     rcx, rdi; hdc
0x1800d5f6d  and     eax, 0FFFFFFC0h
0x1800d5f70  mov     [rsp+78h+arg_0], eax
0x1800d5f77  ldmxcsr [rsp+78h+arg_0]
0x1800d5f7f  call    cs:__imp_SelectObject
0x1800d5f86  nop     dword ptr [rax+rax+00h]
0x1800d5f8b  mov     edx, [rsi+1B0h]; mode
0x1800d5f91  mov     rcx, rdi; hdc
0x1800d5f94  mov     r12, rax
0x1800d5f97  call    cs:__imp_SetPolyFillMode
0x1800d5f9e  nop     dword ptr [rax+rax+00h]
0x1800d5fa3  mov     ecx, 0FFFFFFC0h
0x1800d5fa8  mov     r13d, eax
0x1800d5fab  and     ebx, ecx
0x1800d5fad  mov     [rsp+78h+arg_0], ebx
0x1800d5fb4  ldmxcsr [rsp+78h+arg_0]
0x1800d5fbc  test    [rsi+1B4h], bpl
0x1800d5fc3  jz      loc_1800D6101
0x1800d5fc9  stmxcsr [rsp+78h+arg_0]
0x1800d5fd1  mov     ebx, [rsp+78h+arg_0]
0x1800d5fd8  mov     eax, ebx
0x1800d5fda  and     eax, ecx
0x1800d5fdc  lea     ecx, [rbp+7]; i
0x1800d5fdf  mov     [rsp+78h+arg_0], eax
0x1800d5fe6  ldmxcsr [rsp+78h+arg_0]
0x1800d5fee  call    cs:__imp_GetStockObject
0x1800d5ff5  nop     dword ptr [rax+rax+00h]
0x1800d5ffa  mov     rdx, rax; h
0x1800d5ffd  mov     rcx, rdi; hdc
0x1800d6000  call    cs:__imp_SelectObject
0x1800d6007  nop     dword ptr [rax+rax+00h]
0x1800d600c  mov     ecx, 0FFFFFFC0h
0x1800d6011  mov     r14, rax
0x1800d6014  and     ebx, ecx
0x1800d6016  mov     [rsp+78h+arg_0], ebx
0x1800d601d  ldmxcsr [rsp+78h+arg_0]
0x1800d6025  cmp     [rsi+1ACh], ebp
0x1800d602b  jnz     short loc_1800D6084
0x1800d602d  stmxcsr [rsp+78h+arg_0]
0x1800d6035  mov     ebx, [rsp+78h+arg_0]
0x1800d603c  mov     eax, ebx
0x1800d603e  mov     r8d, [rsi+1A8h]; cpt
0x1800d6045  and     eax, ecx
0x1800d6047  mov     rdx, [rsi+198h]; apt
0x1800d604e  mov     rcx, rdi; hdc
0x1800d6051  mov     [rsp+78h+arg_0], eax
0x1800d6058  ldmxcsr [rsp+78h+arg_0]
0x1800d6060  call    cs:__imp_Polygon
0x1800d6067  nop     dword ptr [rax+rax+00h]
0x1800d606c  mov     ecx, 0FFFFFFC0h
0x1800d6071  and     ebx, ecx
0x1800d6073  mov     [rsp+78h+arg_0], ebx
0x1800d607a  ldmxcsr [rsp+78h+arg_0]
0x1800d6082  jmp     short loc_1800D60EB
0x1800d6084  stmxcsr [rsp+78h+arg_0]
0x1800d608c  mov     ebx, [rsp+78h+arg_0]
0x1800d6093  mov     eax, ebx
0x1800d6095  mov     edx, [rsi+1ACh]
0x1800d609b  and     eax, ecx
0x1800d609d  mov     rcx, [rsi+1A0h]
0x1800d60a4  mov     [rsp+78h+arg_0], eax
0x1800d60ab  mov     rax, [rsi+198h]
0x1800d60b2  ldmxcsr [rsp+78h+arg_0]
0x1800d60ba  mov     [rsp+78h+var_50], rcx
0x1800d60bf  lea     rcx, [rsp+78h+var_58]; this
0x1800d60c4  mov     [rsp+78h+var_48], edx
0x1800d60c8  mov     rdx, rdi; HDC
0x1800d60cb  mov     [rsp+78h+var_58], rax
0x1800d60d0  call    ?Draw@CPolyPolygon@@QEAAHPEAUHDC__@@@Z; CPolyPolygon::Draw(HDC__ *)
0x1800d60d5  mov     ecx, 0FFFFFFC0h
0x1800d60da  and     ebx, ecx
0x1800d60dc  mov     [rsp+78h+arg_0], ebx
0x1800d60e3  ldmxcsr [rsp+78h+arg_0]
0x1800d60eb  mov     rdx, r14; h
0x1800d60ee  mov     rcx, rdi; hdc
0x1800d60f1  mov     ebp, eax
0x1800d60f3  call    cs:__imp_SelectObject
0x1800d60fa  nop     dword ptr [rax+rax+00h]
0x1800d60ff  jmp     short loc_1800D616A
0x1800d6101  mov     rcx, rdi; hdc
0x1800d6104  call    cs:__imp_BeginPath
0x1800d610b  nop     dword ptr [rax+rax+00h]
0x1800d6110  test    byte ptr [rsi+1B4h], 10h
0x1800d6117  jz      loc_1800D61C0
0x1800d611d  test    eax, eax
0x1800d611f  jz      short loc_1800D6168
0x1800d6121  mov     r8d, [rsi+1A8h]; cpt
0x1800d6128  mov     rcx, rdi; hdc
0x1800d612b  mov     rdx, [rsi+198h]; apt
0x1800d6132  call    cs:__imp_PolyBezier
0x1800d6139  nop     dword ptr [rax+rax+00h]
0x1800d613e  test    eax, eax
0x1800d6140  jz      short loc_1800D6168
0x1800d6142  mov     rcx, rdi; hdc
0x1800d6145  call    cs:__imp_EndPath
0x1800d614c  nop     dword ptr [rax+rax+00h]
0x1800d6151  test    eax, eax
0x1800d6153  jz      short loc_1800D6168
0x1800d6155  mov     rcx, rdi; hdc
0x1800d6158  call    cs:__imp_FillPath
0x1800d615f  nop     dword ptr [rax+rax+00h]
0x1800d6164  test    eax, eax
0x1800d6166  jnz     short loc_1800D616A
0x1800d6168  xor     ebp, ebp
0x1800d616a  mov     edx, r13d; mode
0x1800d616d  mov     rcx, rdi; hdc
0x1800d6170  call    cs:__imp_SetPolyFillMode
0x1800d6177  nop     dword ptr [rax+rax+00h]
0x1800d617c  mov     rdx, r12; h
0x1800d617f  mov     rcx, rdi; hdc
0x1800d6182  call    cs:__imp_SelectObject
0x1800d6189  nop     dword ptr [rax+rax+00h]
0x1800d618e  mov     ecx, [rsi+1BCh]; int
0x1800d6194  mov     r8, rdi; HDC
0x1800d6197  mov     edx, r15d; int
0x1800d619a  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x1800d619f  lea     r11, [rsp+78h+var_28]
0x1800d61a4  mov     eax, ebp
0x1800d61a6  mov     rbx, [r11+38h]
0x1800d61aa  mov     rbp, [r11+40h]
0x1800d61ae  mov     rsi, [r11+48h]
0x1800d61b2  mov     rsp, r11
0x1800d61b5  pop     r15
0x1800d61b7  pop     r14
0x1800d61b9  pop     r13
0x1800d61bb  pop     r12
0x1800d61bd  pop     rdi
0x1800d61be  retn
0x1800d61c0  test    eax, eax
0x1800d61c2  jz      short loc_1800D6168
0x1800d61c4  mov     rdx, rdi; HDC
0x1800d61c7  mov     rcx, rsi; this
0x1800d61ca  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x1800d61cf  jmp     loc_1800D613E
```
