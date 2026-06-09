# ConvertPathToGdi::FillAndDraw(HDC__ *,HBRUSH__ *,HPEN__ *)

- ea: `0x180144ac4`
- end: `0x180144d06`
- name: `?FillAndDraw@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@PEAUHPEN__@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h, HPEN)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1801431e8`

## callees

- `0x18002aae8`
- `0x18002abc0`
- `0x1800d9598`
- `0x180144ac4`

## import_xrefs

- `GDI32!StrokeAndFillPath` at `0x180144c4f`
- `GDI32!StrokeAndFillPath` at `0x180144c4f`
- `GDI32!PolyBezier` at `0x180144c29`
- `GDI32!PolyBezier` at `0x180144c29`
- `GDI32!SetPolyFillMode` at `0x180144b4c`
- `GDI32!SetPolyFillMode` at `0x180144c8d`
- `GDI32!SetPolyFillMode` at `0x180144b4c`
- `GDI32!SetPolyFillMode` at `0x180144c8d`
- `GDI32!EndPath` at `0x180144c3c`
- `GDI32!EndPath` at `0x180144c3c`
- `GDI32!BeginPath` at `0x180144bfb`
- `GDI32!BeginPath` at `0x180144bfb`
- `GDI32!PolyPolygon` at `0x180144bbf`
- `GDI32!PolyPolygon` at `0x180144bbf`
- `GDI32!Polygon` at `0x180144ba3`
- `GDI32!Polygon` at `0x180144ba3`
- `GDI32!SelectObject` at `0x180144b1f`
- `GDI32!SelectObject` at `0x180144b34`
- `GDI32!SelectObject` at `0x180144c9f`
- `GDI32!SelectObject` at `0x180144cb1`
- `GDI32!SelectObject` at `0x180144b1f`
- `GDI32!SelectObject` at `0x180144b34`
- `GDI32!SelectObject` at `0x180144c9f`
- `GDI32!SelectObject` at `0x180144cb1`

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
0x180144ac4  push    rbx
0x180144ac6  push    rbp
0x180144ac7  push    rsi
0x180144ac8  push    rdi
0x180144ac9  push    r12
0x180144acb  push    r13
0x180144acd  push    r14
0x180144acf  push    r15
0x180144ad1  sub     rsp, 28h
0x180144ad5  xor     ebx, ebx
0x180144ad7  mov     r14, r9
0x180144ada  mov     r15, r8
0x180144add  mov     rsi, rdx
0x180144ae0  mov     rdi, rcx
0x180144ae3  mov     ebp, 1
0x180144ae8  cmp     [rcx+1A8h], ebx
0x180144aee  jle     loc_180144CDA
0x180144af4  mov     ecx, [rcx+1BCh]; int
0x180144afa  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x180144aff  mov     r12d, eax
0x180144b02  stmxcsr [rsp+68h+arg_0]
0x180144b07  mov     ebx, [rsp+68h+arg_0]
0x180144b0b  mov     rdx, r14; h
0x180144b0e  mov     eax, ebx
0x180144b10  mov     rcx, rsi; hdc
0x180144b13  and     eax, 0FFFFFFC0h
0x180144b16  mov     [rsp+68h+arg_0], eax
0x180144b1a  ldmxcsr [rsp+68h+arg_0]
0x180144b1f  call    cs:__imp_SelectObject
0x180144b26  nop     dword ptr [rax+rax+00h]
0x180144b2b  mov     rdx, r15; h
0x180144b2e  mov     rcx, rsi; hdc
0x180144b31  mov     r14, rax
0x180144b34  call    cs:__imp_SelectObject
0x180144b3b  nop     dword ptr [rax+rax+00h]
0x180144b40  mov     edx, [rdi+1B0h]; mode
0x180144b46  mov     rcx, rsi; hdc
0x180144b49  mov     r15, rax
0x180144b4c  call    cs:__imp_SetPolyFillMode
0x180144b53  nop     dword ptr [rax+rax+00h]
0x180144b58  mov     ecx, 0FFFFFFC0h
0x180144b5d  mov     r13d, eax
0x180144b60  and     ebx, ecx
0x180144b62  mov     [rsp+68h+arg_0], ebx
0x180144b66  ldmxcsr [rsp+68h+arg_0]
0x180144b6b  test    [rdi+1B4h], bpl
0x180144b72  jz      short loc_180144BE2
0x180144b74  stmxcsr [rsp+68h+arg_0]
0x180144b79  mov     ebx, [rsp+68h+arg_0]
0x180144b7d  mov     eax, ebx
0x180144b7f  mov     rdx, [rdi+198h]; apt
0x180144b86  and     eax, ecx
0x180144b88  mov     rcx, rsi; hdc
0x180144b8b  mov     [rsp+68h+arg_0], eax
0x180144b8f  ldmxcsr [rsp+68h+arg_0]
0x180144b94  cmp     [rdi+1ACh], ebp
0x180144b9a  jnz     short loc_180144BB1
0x180144b9c  mov     r8d, [rdi+1A8h]; cpt
0x180144ba3  call    cs:__imp_Polygon
0x180144baa  nop     dword ptr [rax+rax+00h]
0x180144baf  jmp     short loc_180144BCB
0x180144bb1  mov     r9d, [rdi+1ACh]; csz
0x180144bb8  mov     r8, [rdi+1A0h]; asz
0x180144bbf  call    cs:__imp_PolyPolygon
0x180144bc6  nop     dword ptr [rax+rax+00h]
0x180144bcb  mov     ecx, 0FFFFFFC0h
0x180144bd0  mov     ebp, eax
0x180144bd2  and     ebx, ecx
0x180144bd4  mov     [rsp+68h+arg_0], ebx
0x180144bd8  ldmxcsr [rsp+68h+arg_0]
0x180144bdd  jmp     loc_180144C71
0x180144be2  stmxcsr [rsp+68h+arg_0]
0x180144be7  mov     ebx, [rsp+68h+arg_0]
0x180144beb  mov     eax, ebx
0x180144bed  and     eax, ecx
0x180144bef  mov     rcx, rsi; hdc
0x180144bf2  mov     [rsp+68h+arg_0], eax
0x180144bf6  ldmxcsr [rsp+68h+arg_0]
0x180144bfb  call    cs:__imp_BeginPath
0x180144c02  nop     dword ptr [rax+rax+00h]
0x180144c07  test    byte ptr [rdi+1B4h], 10h
0x180144c0e  jz      loc_180144CEE
0x180144c14  test    eax, eax
0x180144c16  jz      short loc_180144C5F
0x180144c18  mov     r8d, [rdi+1A8h]; cpt
0x180144c1f  mov     rcx, rsi; hdc
0x180144c22  mov     rdx, [rdi+198h]; apt
0x180144c29  call    cs:__imp_PolyBezier
0x180144c30  nop     dword ptr [rax+rax+00h]
0x180144c35  test    eax, eax
0x180144c37  jz      short loc_180144C5F
0x180144c39  mov     rcx, rsi; hdc
0x180144c3c  call    cs:__imp_EndPath
0x180144c43  nop     dword ptr [rax+rax+00h]
0x180144c48  test    eax, eax
0x180144c4a  jz      short loc_180144C5F
0x180144c4c  mov     rcx, rsi; hdc
0x180144c4f  call    cs:__imp_StrokeAndFillPath
0x180144c56  nop     dword ptr [rax+rax+00h]
0x180144c5b  test    eax, eax
0x180144c5d  jnz     short loc_180144C61
0x180144c5f  xor     ebp, ebp
0x180144c61  mov     ecx, 0FFFFFFC0h
0x180144c66  and     ebx, ecx
0x180144c68  mov     [rsp+68h+arg_0], ebx
0x180144c6c  ldmxcsr [rsp+68h+arg_0]
0x180144c71  stmxcsr [rsp+68h+arg_0]
0x180144c76  mov     ebx, [rsp+68h+arg_0]
0x180144c7a  mov     edx, r13d; mode
0x180144c7d  mov     eax, ebx
0x180144c7f  and     eax, ecx
0x180144c81  mov     rcx, rsi; hdc
0x180144c84  mov     [rsp+68h+arg_0], eax
0x180144c88  ldmxcsr [rsp+68h+arg_0]
0x180144c8d  call    cs:__imp_SetPolyFillMode
0x180144c94  nop     dword ptr [rax+rax+00h]
0x180144c99  mov     rdx, r15; h
0x180144c9c  mov     rcx, rsi; hdc
0x180144c9f  call    cs:__imp_SelectObject
0x180144ca6  nop     dword ptr [rax+rax+00h]
0x180144cab  mov     rdx, r14; h
0x180144cae  mov     rcx, rsi; hdc
0x180144cb1  call    cs:__imp_SelectObject
0x180144cb8  nop     dword ptr [rax+rax+00h]
0x180144cbd  mov     ecx, [rdi+1BCh]; int
0x180144cc3  and     ebx, 0FFFFFFC0h
0x180144cc6  mov     [rsp+68h+arg_0], ebx
0x180144cca  mov     r8, rsi; HDC
0x180144ccd  ldmxcsr [rsp+68h+arg_0]
0x180144cd2  mov     edx, r12d; int
0x180144cd5  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x180144cda  mov     eax, ebp
0x180144cdc  add     rsp, 28h
0x180144ce0  pop     r15
0x180144ce2  pop     r14
0x180144ce4  pop     r13
0x180144ce6  pop     r12
0x180144ce8  pop     rdi
0x180144ce9  pop     rsi
0x180144cea  pop     rbp
0x180144ceb  pop     rbx
0x180144cec  retn
0x180144cee  test    eax, eax
0x180144cf0  jz      loc_180144C5F
0x180144cf6  mov     rdx, rsi; HDC
0x180144cf9  mov     rcx, rdi; this
0x180144cfc  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x180144d01  jmp     loc_180144C35
```
