# ConvertPathToGdi::AndClip(HDC__ *)

- ea: `0x18004ff64`
- end: `0x180050090`
- name: `?AndClip@ConvertPathToGdi@@QEAAHPEAUHDC__@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18004dbb8`
- `0x180138d30`
- `0x18013da6c`

## callees

- `0x18004d544`
- `0x18004d608`
- `0x18004ff64`
- `0x1800d3340`

## import_xrefs

- `GDI32!SelectClipPath` at `0x180050069`
- `GDI32!SelectClipPath` at `0x180050069`
- `GDI32!PolyBezier` at `0x180050021`
- `GDI32!PolyBezier` at `0x180050021`
- `GDI32!SetPolyFillMode` at `0x18004ff9d`
- `GDI32!SetPolyFillMode` at `0x18005007b`
- `GDI32!SetPolyFillMode` at `0x18004ff9d`
- `GDI32!SetPolyFillMode` at `0x18005007b`
- `GDI32!EndPath` at `0x18005005a`
- `GDI32!EndPath` at `0x18005005a`
- `GDI32!BeginPath` at `0x18004ff8c`
- `GDI32!BeginPath` at `0x18004ff8c`
- `GDI32!PolyPolygon` at `0x18004ffff`
- `GDI32!PolyPolygon` at `0x18004ffff`
- `GDI32!Polygon` at `0x18004ffe2`
- `GDI32!Polygon` at `0x18004ffe2`

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
0x18004ff64  push    rbx
0x18004ff66  push    rbp
0x18004ff67  push    rsi
0x18004ff68  push    rdi
0x18004ff69  push    r14
0x18004ff6b  push    r15
0x18004ff6d  sub     rsp, 28h
0x18004ff71  cmp     dword ptr [rcx+1A8h], 0
0x18004ff78  mov     rbp, rdx
0x18004ff7b  mov     rsi, rcx
0x18004ff7e  mov     ebx, 1
0x18004ff83  jle     loc_180050081
0x18004ff89  mov     rcx, rdx; hdc
0x18004ff8c  call    cs:__imp_BeginPath
0x18004ff92  mov     edx, [rsi+1B0h]; mode
0x18004ff98  mov     rcx, rbp; hdc
0x18004ff9b  mov     edi, eax
0x18004ff9d  call    cs:__imp_SetPolyFillMode
0x18004ffa3  mov     ecx, [rsi+1BCh]; int
0x18004ffa9  mov     rdx, rbp; HDC
0x18004ffac  mov     r14d, eax
0x18004ffaf  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x18004ffb4  mov     ecx, [rsi+1B4h]
0x18004ffba  mov     r15d, eax
0x18004ffbd  test    bl, cl
0x18004ffbf  jz      short loc_180050007
0x18004ffc1  mov     r9d, [rsi+1ACh]; csz
0x18004ffc8  cmp     r9d, ebx
0x18004ffcb  jnz     short loc_18004FFEA
0x18004ffcd  test    edi, edi
0x18004ffcf  jz      short loc_180050040
0x18004ffd1  mov     r8d, [rsi+1A8h]; cpt
0x18004ffd8  mov     rcx, rbp; hdc
0x18004ffdb  mov     rdx, [rsi+198h]; apt
0x18004ffe2  call    cs:__imp_Polygon
0x18004ffe8  jmp     short loc_180050038
0x18004ffea  test    edi, edi
0x18004ffec  jz      short loc_180050040
0x18004ffee  mov     r8, [rsi+1A0h]; asz
0x18004fff5  mov     rcx, rbp; hdc
0x18004fff8  mov     rdx, [rsi+198h]; apt
0x18004ffff  call    cs:__imp_PolyPolygon
0x180050005  jmp     short loc_180050038
0x180050007  test    cl, 10h
0x18005000a  jz      short loc_180050029
0x18005000c  test    edi, edi
0x18005000e  jz      short loc_180050040
0x180050010  mov     r8d, [rsi+1A8h]; cpt
0x180050017  mov     rcx, rbp; hdc
0x18005001a  mov     rdx, [rsi+198h]; apt
0x180050021  call    cs:__imp_PolyBezier
0x180050027  jmp     short loc_180050038
0x180050029  test    edi, edi
0x18005002b  jz      short loc_180050040
0x18005002d  mov     rdx, rbp; HDC
0x180050030  mov     rcx, rsi; this
0x180050033  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x180050038  test    eax, eax
0x18005003a  jz      short loc_180050040
0x18005003c  mov     edi, ebx
0x18005003e  jmp     short loc_180050042
0x180050040  xor     edi, edi
0x180050042  mov     ecx, [rsi+1BCh]; int
0x180050048  mov     r8, rbp; HDC
0x18005004b  mov     edx, r15d; int
0x18005004e  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x180050053  test    edi, edi
0x180050055  jz      short loc_180050073
0x180050057  mov     rcx, rbp; hdc
0x18005005a  call    cs:__imp_EndPath
0x180050060  test    eax, eax
0x180050062  jz      short loc_180050073
0x180050064  mov     edx, ebx; mode
0x180050066  mov     rcx, rbp; hdc
0x180050069  call    cs:__imp_SelectClipPath
0x18005006f  test    eax, eax
0x180050071  jnz     short loc_180050075
0x180050073  xor     ebx, ebx
0x180050075  mov     edx, r14d; mode
0x180050078  mov     rcx, rbp; hdc
0x18005007b  call    cs:__imp_SetPolyFillMode
0x180050081  mov     eax, ebx
0x180050083  add     rsp, 28h
0x180050087  pop     r15
0x180050089  pop     r14
0x18005008b  pop     rdi
0x18005008c  pop     rsi
0x18005008d  pop     rbp
0x18005008e  pop     rbx
0x18005008f  retn
```
