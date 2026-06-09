# ConvertPathToGdi::FillAndDraw(HDC__ *,HBRUSH__ *,HPEN__ *)

- ea: `0x18013c488`
- end: `0x18013c67a`
- name: `?FillAndDraw@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@PEAUHPEN__@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h, HPEN)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18013ac6c`

## callees

- `0x18004d544`
- `0x18004d608`
- `0x1800d3340`
- `0x18013c488`

## import_xrefs

- `GDI32!StrokeAndFillPath` at `0x18013c5e0`
- `GDI32!StrokeAndFillPath` at `0x18013c5e0`
- `GDI32!PolyBezier` at `0x18013c5c6`
- `GDI32!PolyBezier` at `0x18013c5c6`
- `GDI32!SetPolyFillMode` at `0x18013c504`
- `GDI32!SetPolyFillMode` at `0x18013c618`
- `GDI32!SetPolyFillMode` at `0x18013c504`
- `GDI32!SetPolyFillMode` at `0x18013c618`
- `GDI32!EndPath` at `0x18013c5d3`
- `GDI32!EndPath` at `0x18013c5d3`
- `GDI32!BeginPath` at `0x18013c59e`
- `GDI32!BeginPath` at `0x18013c59e`
- `GDI32!PolyPolygon` at `0x18013c56b`
- `GDI32!PolyPolygon` at `0x18013c56b`
- `GDI32!Polygon` at `0x18013c555`
- `GDI32!Polygon` at `0x18013c555`
- `GDI32!SelectObject` at `0x18013c4e3`
- `GDI32!SelectObject` at `0x18013c4f2`
- `GDI32!SelectObject` at `0x18013c624`
- `GDI32!SelectObject` at `0x18013c630`
- `GDI32!SelectObject` at `0x18013c4e3`
- `GDI32!SelectObject` at `0x18013c4f2`
- `GDI32!SelectObject` at `0x18013c624`
- `GDI32!SelectObject` at `0x18013c630`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::FillAndDraw(ConvertPathToGdi *this, HDC a2, HBRUSH h, HPEN a4)
{
  unsigned int v8; // ebp
  int v9; // r12d
  HGDIOBJ v10; // r14
  HGDIOBJ v11; // r15
  int v12; // r13d
  int v13; // ebx
  const POINT *v14; // rdx
  BOOL v15; // eax
  int v16; // ebx
  BOOL v17; // eax
  int v18; // eax
  int v19; // ebx
  unsigned int v21; // [rsp+70h] [rbp+8h]

  v8 = 1;
  if ( *((int *)this + 106) > 0 )
  {
    v9 = SetupForIncreasedResolution(*((_DWORD *)this + 111), a2);
    v21 = _mm_getcsr() & 0xFFFFFFC0;
    _mm_setcsr(v21);
    v10 = SelectObject(a2, a4);
    v11 = SelectObject(a2, h);
    v12 = SetPolyFillMode(a2, *((_DWORD *)this + 108));
    _mm_setcsr(v21);
    if ( (*((_BYTE *)this + 436) & 1) != 0 )
    {
      v13 = _mm_getcsr();
      v14 = (const POINT *)*((_QWORD *)this + 51);
      _mm_setcsr(v13 & 0xFFFFFFC0);
      if ( *((_DWORD *)this + 107) == 1 )
        v15 = Polygon(a2, v14, *((_DWORD *)this + 106));
      else
        v15 = PolyPolygon(a2, v14, *((const INT **)this + 52), *((_DWORD *)this + 107));
      v8 = v15;
      _mm_setcsr(v13 & 0xFFFFFFC0);
      goto LABEL_15;
    }
    v16 = _mm_getcsr();
    _mm_setcsr(v16 & 0xFFFFFFC0);
    v17 = BeginPath(a2);
    if ( (*((_BYTE *)this + 436) & 0x10) != 0 )
    {
      if ( v17 )
      {
        v18 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
LABEL_10:
        if ( v18 && EndPath(a2) && StrokeAndFillPath(a2) )
          goto LABEL_14;
      }
    }
    else if ( v17 )
    {
      v18 = ConvertPathToGdi::DrawMixedPath(this, a2);
      goto LABEL_10;
    }
    v8 = 0;
LABEL_14:
    _mm_setcsr(v16 & 0xFFFFFFC0);
LABEL_15:
    v19 = _mm_getcsr();
    _mm_setcsr(v19 & 0xFFFFFFC0);
    SetPolyFillMode(a2, v12);
    SelectObject(a2, v11);
    SelectObject(a2, v10);
    _mm_setcsr(v19 & 0xFFFFFFC0);
    CleanupForIncreasedResolution(*((_DWORD *)this + 111), v9, a2);
  }
  return v8;
}

```

## disassembly

```asm
0x18013c488  push    rbx
0x18013c48a  push    rbp
0x18013c48b  push    rsi
0x18013c48c  push    rdi
0x18013c48d  push    r12
0x18013c48f  push    r13
0x18013c491  push    r14
0x18013c493  push    r15
0x18013c495  sub     rsp, 28h
0x18013c499  xor     ebx, ebx
0x18013c49b  mov     r14, r9
0x18013c49e  mov     r15, r8
0x18013c4a1  mov     rsi, rdx
0x18013c4a4  mov     rdi, rcx
0x18013c4a7  mov     ebp, 1
0x18013c4ac  cmp     [rcx+1A8h], ebx
0x18013c4b2  jle     loc_18013C653
0x18013c4b8  mov     ecx, [rcx+1BCh]; int
0x18013c4be  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x18013c4c3  mov     r12d, eax
0x18013c4c6  stmxcsr [rsp+68h+arg_0]
0x18013c4cb  mov     ebx, [rsp+68h+arg_0]
0x18013c4cf  mov     rdx, r14; h
0x18013c4d2  mov     eax, ebx
0x18013c4d4  mov     rcx, rsi; hdc
0x18013c4d7  and     eax, 0FFFFFFC0h
0x18013c4da  mov     [rsp+68h+arg_0], eax
0x18013c4de  ldmxcsr [rsp+68h+arg_0]
0x18013c4e3  call    cs:__imp_SelectObject
0x18013c4e9  mov     rdx, r15; h
0x18013c4ec  mov     rcx, rsi; hdc
0x18013c4ef  mov     r14, rax
0x18013c4f2  call    cs:__imp_SelectObject
0x18013c4f8  mov     edx, [rdi+1B0h]; mode
0x18013c4fe  mov     rcx, rsi; hdc
0x18013c501  mov     r15, rax
0x18013c504  call    cs:__imp_SetPolyFillMode
0x18013c50a  mov     ecx, 0FFFFFFC0h
0x18013c50f  mov     r13d, eax
0x18013c512  and     ebx, ecx
0x18013c514  mov     [rsp+68h+arg_0], ebx
0x18013c518  ldmxcsr [rsp+68h+arg_0]
0x18013c51d  test    [rdi+1B4h], bpl
0x18013c524  jz      short loc_18013C585
0x18013c526  stmxcsr [rsp+68h+arg_0]
0x18013c52b  mov     ebx, [rsp+68h+arg_0]
0x18013c52f  mov     eax, ebx
0x18013c531  mov     rdx, [rdi+198h]; apt
0x18013c538  and     eax, ecx
0x18013c53a  mov     rcx, rsi; hdc
0x18013c53d  mov     [rsp+68h+arg_0], eax
0x18013c541  ldmxcsr [rsp+68h+arg_0]
0x18013c546  cmp     [rdi+1ACh], ebp
0x18013c54c  jnz     short loc_18013C55D
0x18013c54e  mov     r8d, [rdi+1A8h]; cpt
0x18013c555  call    cs:__imp_Polygon
0x18013c55b  jmp     short loc_18013C571
0x18013c55d  mov     r9d, [rdi+1ACh]; csz
0x18013c564  mov     r8, [rdi+1A0h]; asz
0x18013c56b  call    cs:__imp_PolyPolygon
0x18013c571  mov     ecx, 0FFFFFFC0h
0x18013c576  mov     ebp, eax
0x18013c578  and     ebx, ecx
0x18013c57a  mov     [rsp+68h+arg_0], ebx
0x18013c57e  ldmxcsr [rsp+68h+arg_0]
0x18013c583  jmp     short loc_18013C5FC
0x18013c585  stmxcsr [rsp+68h+arg_0]
0x18013c58a  mov     ebx, [rsp+68h+arg_0]
0x18013c58e  mov     eax, ebx
0x18013c590  and     eax, ecx
0x18013c592  mov     rcx, rsi; hdc
0x18013c595  mov     [rsp+68h+arg_0], eax
0x18013c599  ldmxcsr [rsp+68h+arg_0]
0x18013c59e  call    cs:__imp_BeginPath
0x18013c5a4  test    byte ptr [rdi+1B4h], 10h
0x18013c5ab  jz      loc_18013C666
0x18013c5b1  test    eax, eax
0x18013c5b3  jz      short loc_18013C5EA
0x18013c5b5  mov     r8d, [rdi+1A8h]; cpt
0x18013c5bc  mov     rcx, rsi; hdc
0x18013c5bf  mov     rdx, [rdi+198h]; apt
0x18013c5c6  call    cs:__imp_PolyBezier
0x18013c5cc  test    eax, eax
0x18013c5ce  jz      short loc_18013C5EA
0x18013c5d0  mov     rcx, rsi; hdc
0x18013c5d3  call    cs:__imp_EndPath
0x18013c5d9  test    eax, eax
0x18013c5db  jz      short loc_18013C5EA
0x18013c5dd  mov     rcx, rsi; hdc
0x18013c5e0  call    cs:__imp_StrokeAndFillPath
0x18013c5e6  test    eax, eax
0x18013c5e8  jnz     short loc_18013C5EC
0x18013c5ea  xor     ebp, ebp
0x18013c5ec  mov     ecx, 0FFFFFFC0h
0x18013c5f1  and     ebx, ecx
0x18013c5f3  mov     [rsp+68h+arg_0], ebx
0x18013c5f7  ldmxcsr [rsp+68h+arg_0]
0x18013c5fc  stmxcsr [rsp+68h+arg_0]
0x18013c601  mov     ebx, [rsp+68h+arg_0]
0x18013c605  mov     edx, r13d; mode
0x18013c608  mov     eax, ebx
0x18013c60a  and     eax, ecx
0x18013c60c  mov     rcx, rsi; hdc
0x18013c60f  mov     [rsp+68h+arg_0], eax
0x18013c613  ldmxcsr [rsp+68h+arg_0]
0x18013c618  call    cs:__imp_SetPolyFillMode
0x18013c61e  mov     rdx, r15; h
0x18013c621  mov     rcx, rsi; hdc
0x18013c624  call    cs:__imp_SelectObject
0x18013c62a  mov     rdx, r14; h
0x18013c62d  mov     rcx, rsi; hdc
0x18013c630  call    cs:__imp_SelectObject
0x18013c636  mov     ecx, [rdi+1BCh]; int
0x18013c63c  and     ebx, 0FFFFFFC0h
0x18013c63f  mov     [rsp+68h+arg_0], ebx
0x18013c643  mov     r8, rsi; HDC
0x18013c646  ldmxcsr [rsp+68h+arg_0]
0x18013c64b  mov     edx, r12d; int
0x18013c64e  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x18013c653  mov     eax, ebp
0x18013c655  add     rsp, 28h
0x18013c659  pop     r15
0x18013c65b  pop     r14
0x18013c65d  pop     r13
0x18013c65f  pop     r12
0x18013c661  pop     rdi
0x18013c662  pop     rsi
0x18013c663  pop     rbp
0x18013c664  pop     rbx
0x18013c665  retn
0x18013c666  test    eax, eax
0x18013c668  jz      short loc_18013C5EA
0x18013c66a  mov     rdx, rsi; HDC
0x18013c66d  mov     rcx, rdi; this
0x18013c670  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x18013c675  jmp     loc_18013C5CC
```
