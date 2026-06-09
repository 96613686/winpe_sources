# ConvertPathToGdi::FillAndDraw(HDC__ *,HBRUSH__ *,HPEN__ *)

- ea: `0x18013af50`
- end: `0x18013b1a9`
- name: `?FillAndDraw@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@PEAUHPEN__@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h, HPEN)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180138be8`

## callees

- `0x18003bb1c`
- `0x18003bbec`
- `0x1800bd49c`
- `0x18013af50`

## import_xrefs

- `GDI32!StrokeAndFillPath` at `0x18013b0e6`
- `GDI32!StrokeAndFillPath` at `0x18013b0e6`
- `GDI32!PolyBezier` at `0x18013b0c0`
- `GDI32!PolyBezier` at `0x18013b0c0`
- `GDI32!SetPolyFillMode` at `0x18013afe3`
- `GDI32!SetPolyFillMode` at `0x18013b124`
- `GDI32!SetPolyFillMode` at `0x18013afe3`
- `GDI32!SetPolyFillMode` at `0x18013b124`
- `GDI32!EndPath` at `0x18013b0d3`
- `GDI32!EndPath` at `0x18013b0d3`
- `GDI32!BeginPath` at `0x18013b092`
- `GDI32!BeginPath` at `0x18013b092`
- `GDI32!PolyPolygon` at `0x18013b056`
- `GDI32!PolyPolygon` at `0x18013b056`
- `GDI32!Polygon` at `0x18013b03a`
- `GDI32!Polygon` at `0x18013b03a`
- `GDI32!SelectObject` at `0x18013afb6`
- `GDI32!SelectObject` at `0x18013afcb`
- `GDI32!SelectObject` at `0x18013b136`
- `GDI32!SelectObject` at `0x18013b148`
- `GDI32!SelectObject` at `0x18013afb6`
- `GDI32!SelectObject` at `0x18013afcb`
- `GDI32!SelectObject` at `0x18013b136`
- `GDI32!SelectObject` at `0x18013b148`

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
  unsigned int v21; // [rsp+50h] [rbp+8h]

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
0x18013af50  mov     [rsp+arg_8], rbx
0x18013af55  mov     [rsp+arg_10], rbp
0x18013af5a  mov     [rsp+arg_18], rsi
0x18013af5f  push    rdi
0x18013af60  push    r12
0x18013af62  push    r13
0x18013af64  push    r14
0x18013af66  push    r15
0x18013af68  sub     rsp, 20h
0x18013af6c  xor     ebx, ebx
0x18013af6e  mov     r14, r9
0x18013af71  mov     r15, r8
0x18013af74  mov     rsi, rdx
0x18013af77  mov     rdi, rcx
0x18013af7a  mov     ebp, 1
0x18013af7f  cmp     [rcx+1A8h], ebx
0x18013af85  jle     loc_18013B171
0x18013af8b  mov     ecx, [rcx+1BCh]; int
0x18013af91  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x18013af96  mov     r12d, eax
0x18013af99  stmxcsr [rsp+48h+arg_0]
0x18013af9e  mov     ebx, [rsp+48h+arg_0]
0x18013afa2  mov     rdx, r14; h
0x18013afa5  mov     eax, ebx
0x18013afa7  mov     rcx, rsi; hdc
0x18013afaa  and     eax, 0FFFFFFC0h
0x18013afad  mov     [rsp+48h+arg_0], eax
0x18013afb1  ldmxcsr [rsp+48h+arg_0]
0x18013afb6  call    cs:__imp_SelectObject
0x18013afbd  nop     dword ptr [rax+rax+00h]
0x18013afc2  mov     rdx, r15; h
0x18013afc5  mov     rcx, rsi; hdc
0x18013afc8  mov     r14, rax
0x18013afcb  call    cs:__imp_SelectObject
0x18013afd2  nop     dword ptr [rax+rax+00h]
0x18013afd7  mov     edx, [rdi+1B0h]; mode
0x18013afdd  mov     rcx, rsi; hdc
0x18013afe0  mov     r15, rax
0x18013afe3  call    cs:__imp_SetPolyFillMode
0x18013afea  nop     dword ptr [rax+rax+00h]
0x18013afef  mov     ecx, 0FFFFFFC0h
0x18013aff4  mov     r13d, eax
0x18013aff7  and     ebx, ecx
0x18013aff9  mov     [rsp+48h+arg_0], ebx
0x18013affd  ldmxcsr [rsp+48h+arg_0]
0x18013b002  test    [rdi+1B4h], bpl
0x18013b009  jz      short loc_18013B079
0x18013b00b  stmxcsr [rsp+48h+arg_0]
0x18013b010  mov     ebx, [rsp+48h+arg_0]
0x18013b014  mov     eax, ebx
0x18013b016  mov     rdx, [rdi+198h]; apt
0x18013b01d  and     eax, ecx
0x18013b01f  mov     rcx, rsi; hdc
0x18013b022  mov     [rsp+48h+arg_0], eax
0x18013b026  ldmxcsr [rsp+48h+arg_0]
0x18013b02b  cmp     [rdi+1ACh], ebp
0x18013b031  jnz     short loc_18013B048
0x18013b033  mov     r8d, [rdi+1A8h]; cpt
0x18013b03a  call    cs:__imp_Polygon
0x18013b041  nop     dword ptr [rax+rax+00h]
0x18013b046  jmp     short loc_18013B062
0x18013b048  mov     r9d, [rdi+1ACh]; csz
0x18013b04f  mov     r8, [rdi+1A0h]; asz
0x18013b056  call    cs:__imp_PolyPolygon
0x18013b05d  nop     dword ptr [rax+rax+00h]
0x18013b062  mov     ecx, 0FFFFFFC0h
0x18013b067  mov     ebp, eax
0x18013b069  and     ebx, ecx
0x18013b06b  mov     [rsp+48h+arg_0], ebx
0x18013b06f  ldmxcsr [rsp+48h+arg_0]
0x18013b074  jmp     loc_18013B108
0x18013b079  stmxcsr [rsp+48h+arg_0]
0x18013b07e  mov     ebx, [rsp+48h+arg_0]
0x18013b082  mov     eax, ebx
0x18013b084  and     eax, ecx
0x18013b086  mov     rcx, rsi; hdc
0x18013b089  mov     [rsp+48h+arg_0], eax
0x18013b08d  ldmxcsr [rsp+48h+arg_0]
0x18013b092  call    cs:__imp_BeginPath
0x18013b099  nop     dword ptr [rax+rax+00h]
0x18013b09e  test    byte ptr [rdi+1B4h], 10h
0x18013b0a5  jz      loc_18013B191
0x18013b0ab  test    eax, eax
0x18013b0ad  jz      short loc_18013B0F6
0x18013b0af  mov     r8d, [rdi+1A8h]; cpt
0x18013b0b6  mov     rcx, rsi; hdc
0x18013b0b9  mov     rdx, [rdi+198h]; apt
0x18013b0c0  call    cs:__imp_PolyBezier
0x18013b0c7  nop     dword ptr [rax+rax+00h]
0x18013b0cc  test    eax, eax
0x18013b0ce  jz      short loc_18013B0F6
0x18013b0d0  mov     rcx, rsi; hdc
0x18013b0d3  call    cs:__imp_EndPath
0x18013b0da  nop     dword ptr [rax+rax+00h]
0x18013b0df  test    eax, eax
0x18013b0e1  jz      short loc_18013B0F6
0x18013b0e3  mov     rcx, rsi; hdc
0x18013b0e6  call    cs:__imp_StrokeAndFillPath
0x18013b0ed  nop     dword ptr [rax+rax+00h]
0x18013b0f2  test    eax, eax
0x18013b0f4  jnz     short loc_18013B0F8
0x18013b0f6  xor     ebp, ebp
0x18013b0f8  mov     ecx, 0FFFFFFC0h
0x18013b0fd  and     ebx, ecx
0x18013b0ff  mov     [rsp+48h+arg_0], ebx
0x18013b103  ldmxcsr [rsp+48h+arg_0]
0x18013b108  stmxcsr [rsp+48h+arg_0]
0x18013b10d  mov     ebx, [rsp+48h+arg_0]
0x18013b111  mov     edx, r13d; mode
0x18013b114  mov     eax, ebx
0x18013b116  and     eax, ecx
0x18013b118  mov     rcx, rsi; hdc
0x18013b11b  mov     [rsp+48h+arg_0], eax
0x18013b11f  ldmxcsr [rsp+48h+arg_0]
0x18013b124  call    cs:__imp_SetPolyFillMode
0x18013b12b  nop     dword ptr [rax+rax+00h]
0x18013b130  mov     rdx, r15; h
0x18013b133  mov     rcx, rsi; hdc
0x18013b136  call    cs:__imp_SelectObject
0x18013b13d  nop     dword ptr [rax+rax+00h]
0x18013b142  mov     rdx, r14; h
0x18013b145  mov     rcx, rsi; hdc
0x18013b148  call    cs:__imp_SelectObject
0x18013b14f  nop     dword ptr [rax+rax+00h]
0x18013b154  mov     ecx, [rdi+1BCh]; int
0x18013b15a  and     ebx, 0FFFFFFC0h
0x18013b15d  mov     [rsp+48h+arg_0], ebx
0x18013b161  mov     r8, rsi; HDC
0x18013b164  ldmxcsr [rsp+48h+arg_0]
0x18013b169  mov     edx, r12d; int
0x18013b16c  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x18013b171  mov     rbx, [rsp+48h+arg_8]
0x18013b176  mov     eax, ebp
0x18013b178  mov     rbp, [rsp+48h+arg_10]
0x18013b17d  mov     rsi, [rsp+48h+arg_18]
0x18013b182  add     rsp, 20h
0x18013b186  pop     r15
0x18013b188  pop     r14
0x18013b18a  pop     r13
0x18013b18c  pop     r12
0x18013b18e  pop     rdi
0x18013b18f  retn
0x18013b191  test    eax, eax
0x18013b193  jz      loc_18013B0F6
0x18013b199  mov     rdx, rsi; HDC
0x18013b19c  mov     rcx, rdi; this
0x18013b19f  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x18013b1a4  jmp     loc_18013B0CC
```
