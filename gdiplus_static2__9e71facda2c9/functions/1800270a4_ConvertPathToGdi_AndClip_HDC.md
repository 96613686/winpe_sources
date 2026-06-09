# ConvertPathToGdi::AndClip(HDC__ *)

- ea: `0x1800270a4`
- end: `0x180027205`
- name: `?AndClip@ConvertPathToGdi@@QEAAHPEAUHDC__@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180028690`
- `0x180141270`
- `0x18014615c`

## callees

- `0x1800270a4`
- `0x18002aae8`
- `0x18002abc0`
- `0x1800d9598`

## import_xrefs

- `GDI32!SelectClipPath` at `0x1800271d1`
- `GDI32!SelectClipPath` at `0x1800271d1`
- `GDI32!PolyBezier` at `0x18002717d`
- `GDI32!PolyBezier` at `0x18002717d`
- `GDI32!SetPolyFillMode` at `0x1800270e3`
- `GDI32!SetPolyFillMode` at `0x1800271e9`
- `GDI32!SetPolyFillMode` at `0x1800270e3`
- `GDI32!SetPolyFillMode` at `0x1800271e9`
- `GDI32!EndPath` at `0x1800271bc`
- `GDI32!EndPath` at `0x1800271bc`
- `GDI32!BeginPath` at `0x1800270cc`
- `GDI32!BeginPath` at `0x1800270cc`
- `GDI32!PolyPolygon` at `0x180027155`
- `GDI32!PolyPolygon` at `0x180027155`
- `GDI32!Polygon` at `0x180027132`
- `GDI32!Polygon` at `0x180027132`

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
0x1800270a4  push    rbx
0x1800270a6  push    rbp
0x1800270a7  push    rsi
0x1800270a8  push    rdi
0x1800270a9  push    r14
0x1800270ab  push    r15
0x1800270ad  sub     rsp, 28h
0x1800270b1  cmp     dword ptr [rcx+1A8h], 0
0x1800270b8  mov     rbp, rdx
0x1800270bb  mov     rsi, rcx
0x1800270be  mov     ebx, 1
0x1800270c3  jle     loc_1800271F5
0x1800270c9  mov     rcx, rdx; hdc
0x1800270cc  call    cs:__imp_BeginPath
0x1800270d3  nop     dword ptr [rax+rax+00h]
0x1800270d8  mov     edx, [rsi+1B0h]; mode
0x1800270de  mov     rcx, rbp; hdc
0x1800270e1  mov     edi, eax
0x1800270e3  call    cs:__imp_SetPolyFillMode
0x1800270ea  nop     dword ptr [rax+rax+00h]
0x1800270ef  mov     ecx, [rsi+1BCh]; int
0x1800270f5  mov     rdx, rbp; HDC
0x1800270f8  mov     r14d, eax
0x1800270fb  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x180027100  mov     ecx, [rsi+1B4h]
0x180027106  mov     r15d, eax
0x180027109  test    bl, cl
0x18002710b  jz      short loc_180027163
0x18002710d  mov     r9d, [rsi+1ACh]; csz
0x180027114  cmp     r9d, ebx
0x180027117  jnz     short loc_180027140
0x180027119  test    edi, edi
0x18002711b  jz      loc_1800271A2
0x180027121  mov     r8d, [rsi+1A8h]; cpt
0x180027128  mov     rcx, rbp; hdc
0x18002712b  mov     rdx, [rsi+198h]; apt
0x180027132  call    cs:__imp_Polygon
0x180027139  nop     dword ptr [rax+rax+00h]
0x18002713e  jmp     short loc_18002719A
0x180027140  test    edi, edi
0x180027142  jz      short loc_1800271A2
0x180027144  mov     r8, [rsi+1A0h]; asz
0x18002714b  mov     rcx, rbp; hdc
0x18002714e  mov     rdx, [rsi+198h]; apt
0x180027155  call    cs:__imp_PolyPolygon
0x18002715c  nop     dword ptr [rax+rax+00h]
0x180027161  jmp     short loc_18002719A
0x180027163  test    cl, 10h
0x180027166  jz      short loc_18002718B
0x180027168  test    edi, edi
0x18002716a  jz      short loc_1800271A2
0x18002716c  mov     r8d, [rsi+1A8h]; cpt
0x180027173  mov     rcx, rbp; hdc
0x180027176  mov     rdx, [rsi+198h]; apt
0x18002717d  call    cs:__imp_PolyBezier
0x180027184  nop     dword ptr [rax+rax+00h]
0x180027189  jmp     short loc_18002719A
0x18002718b  test    edi, edi
0x18002718d  jz      short loc_1800271A2
0x18002718f  mov     rdx, rbp; HDC
0x180027192  mov     rcx, rsi; this
0x180027195  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x18002719a  test    eax, eax
0x18002719c  jz      short loc_1800271A2
0x18002719e  mov     edi, ebx
0x1800271a0  jmp     short loc_1800271A4
0x1800271a2  xor     edi, edi
0x1800271a4  mov     ecx, [rsi+1BCh]; int
0x1800271aa  mov     r8, rbp; HDC
0x1800271ad  mov     edx, r15d; int
0x1800271b0  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x1800271b5  test    edi, edi
0x1800271b7  jz      short loc_1800271E1
0x1800271b9  mov     rcx, rbp; hdc
0x1800271bc  call    cs:__imp_EndPath
0x1800271c3  nop     dword ptr [rax+rax+00h]
0x1800271c8  test    eax, eax
0x1800271ca  jz      short loc_1800271E1
0x1800271cc  mov     edx, ebx; mode
0x1800271ce  mov     rcx, rbp; hdc
0x1800271d1  call    cs:__imp_SelectClipPath
0x1800271d8  nop     dword ptr [rax+rax+00h]
0x1800271dd  test    eax, eax
0x1800271df  jnz     short loc_1800271E3
0x1800271e1  xor     ebx, ebx
0x1800271e3  mov     edx, r14d; mode
0x1800271e6  mov     rcx, rbp; hdc
0x1800271e9  call    cs:__imp_SetPolyFillMode
0x1800271f0  nop     dword ptr [rax+rax+00h]
0x1800271f5  mov     eax, ebx
0x1800271f7  add     rsp, 28h
0x1800271fb  pop     r15
0x1800271fd  pop     r14
0x1800271ff  pop     rdi
0x180027200  pop     rsi
0x180027201  pop     rbp
0x180027202  pop     rbx
0x180027203  retn
```
