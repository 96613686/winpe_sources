# ConvertPathToGdi::Fill(HDC__ *,HBRUSH__ *)

- ea: `0x18004e87c`
- end: `0x18004ead8`
- name: `?Fill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h)`
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180050220`
- `0x1800b7160`
- `0x1800f3b84`
- `0x18013808c`
- `0x18013bd04`

## callees

- `0x18004d544`
- `0x18004d608`
- `0x18004e87c`
- `0x1800d3340`
- `0x18013c360`

## import_xrefs

- `GDI32!FillPath` at `0x18004ea7f`
- `GDI32!FillPath` at `0x18004ea7f`
- `GDI32!PolyBezier` at `0x18004ea65`
- `GDI32!PolyBezier` at `0x18004ea65`
- `GDI32!SetPolyFillMode` at `0x18004e8f2`
- `GDI32!SetPolyFillMode` at `0x18004ea91`
- `GDI32!SetPolyFillMode` at `0x18004e8f2`
- `GDI32!SetPolyFillMode` at `0x18004ea91`
- `GDI32!EndPath` at `0x18004ea72`
- `GDI32!EndPath` at `0x18004ea72`
- `GDI32!BeginPath` at `0x18004ea41`
- `GDI32!BeginPath` at `0x18004ea41`
- `GDI32!Polygon` at `0x18004e9a9`
- `GDI32!Polygon` at `0x18004e9a9`
- `GDI32!GetStockObject` at `0x18004e943`
- `GDI32!GetStockObject` at `0x18004e943`
- `GDI32!SelectObject` at `0x18004e8e0`
- `GDI32!SelectObject` at `0x18004e94f`
- `GDI32!SelectObject` at `0x18004ea36`
- `GDI32!SelectObject` at `0x18004ea9d`
- `GDI32!SelectObject` at `0x18004e8e0`
- `GDI32!SelectObject` at `0x18004e94f`
- `GDI32!SelectObject` at `0x18004ea36`
- `GDI32!SelectObject` at `0x18004ea9d`

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
  BOOL v14; // eax
  int v15; // eax
  _QWORD v17[2]; // [rsp+20h] [rbp-78h] BYREF
  int v18; // [rsp+30h] [rbp-68h]
  unsigned int v19; // [rsp+A0h] [rbp+8h]
  unsigned int v20; // [rsp+A0h] [rbp+8h]

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
      v19 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v19);
      StockObject = GetStockObject(8);
      v12 = SelectObject(a2, StockObject);
      _mm_setcsr(v19);
      v20 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v20);
      if ( *((_DWORD *)this + 107) == 1 )
      {
        v13 = Polygon(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
      }
      else
      {
        v17[0] = *((_QWORD *)this + 51);
        v17[1] = *((_QWORD *)this + 52);
        v18 = *((_DWORD *)this + 107);
        v13 = CPolyPolygon::Draw((CPolyPolygon *)v17, a2);
      }
      _mm_setcsr(v20);
      v6 = v13;
      SelectObject(a2, v12);
      goto LABEL_14;
    }
    v14 = BeginPath(a2);
    if ( (*((_BYTE *)this + 436) & 0x10) != 0 )
    {
      if ( v14 )
      {
        v15 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
LABEL_10:
        if ( v15 && EndPath(a2) && FillPath(a2) )
          goto LABEL_14;
      }
    }
    else if ( v14 )
    {
      v15 = ConvertPathToGdi::DrawMixedPath(this, a2);
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
0x18004e87c  push    rbx
0x18004e87e  push    rbp
0x18004e87f  push    rsi
0x18004e880  push    rdi
0x18004e881  push    r12
0x18004e883  push    r13
0x18004e885  push    r14
0x18004e887  push    r15
0x18004e889  sub     rsp, 58h
0x18004e88d  xor     ebx, ebx
0x18004e88f  mov     r14, r8
0x18004e892  mov     rdi, rdx
0x18004e895  mov     rsi, rcx
0x18004e898  mov     ebp, 1
0x18004e89d  cmp     [rcx+1A8h], ebx
0x18004e8a3  jle     loc_18004EAB4
0x18004e8a9  mov     ecx, [rcx+1BCh]; int
0x18004e8af  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x18004e8b4  mov     r15d, eax
0x18004e8b7  stmxcsr [rsp+98h+arg_0]
0x18004e8bf  mov     ebx, [rsp+98h+arg_0]
0x18004e8c6  mov     rdx, r14; h
0x18004e8c9  mov     eax, ebx
0x18004e8cb  mov     rcx, rdi; hdc
0x18004e8ce  and     eax, 0FFFFFFC0h
0x18004e8d1  mov     [rsp+98h+arg_0], eax
0x18004e8d8  ldmxcsr [rsp+98h+arg_0]
0x18004e8e0  call    cs:__imp_SelectObject
0x18004e8e6  mov     edx, [rsi+1B0h]; mode
0x18004e8ec  mov     rcx, rdi; hdc
0x18004e8ef  mov     r12, rax
0x18004e8f2  call    cs:__imp_SetPolyFillMode
0x18004e8f8  mov     ecx, 0FFFFFFC0h
0x18004e8fd  mov     r13d, eax
0x18004e900  and     ebx, ecx
0x18004e902  mov     [rsp+98h+arg_0], ebx
0x18004e909  ldmxcsr [rsp+98h+arg_0]
0x18004e911  test    [rsi+1B4h], bpl
0x18004e918  jz      loc_18004EA3E
0x18004e91e  stmxcsr [rsp+98h+arg_0]
0x18004e926  mov     ebx, [rsp+98h+arg_0]
0x18004e92d  mov     eax, ebx
0x18004e92f  and     eax, ecx
0x18004e931  lea     ecx, [rbp+7]; i
0x18004e934  mov     [rsp+98h+arg_0], eax
0x18004e93b  ldmxcsr [rsp+98h+arg_0]
0x18004e943  call    cs:__imp_GetStockObject
0x18004e949  mov     rdx, rax; h
0x18004e94c  mov     rcx, rdi; hdc
0x18004e94f  call    cs:__imp_SelectObject
0x18004e955  mov     ecx, 0FFFFFFC0h
0x18004e95a  mov     r14, rax
0x18004e95d  and     ebx, ecx
0x18004e95f  mov     [rsp+98h+arg_0], ebx
0x18004e966  ldmxcsr [rsp+98h+arg_0]
0x18004e96e  cmp     [rsi+1ACh], ebp
0x18004e974  jnz     short loc_18004E9C7
0x18004e976  stmxcsr [rsp+98h+arg_0]
0x18004e97e  mov     ebx, [rsp+98h+arg_0]
0x18004e985  mov     eax, ebx
0x18004e987  mov     r8d, [rsi+1A8h]; cpt
0x18004e98e  and     eax, ecx
0x18004e990  mov     rdx, [rsi+198h]; apt
0x18004e997  mov     rcx, rdi; hdc
0x18004e99a  mov     [rsp+98h+arg_0], eax
0x18004e9a1  ldmxcsr [rsp+98h+arg_0]
0x18004e9a9  call    cs:__imp_Polygon
0x18004e9af  mov     ecx, 0FFFFFFC0h
0x18004e9b4  and     ebx, ecx
0x18004e9b6  mov     [rsp+98h+arg_0], ebx
0x18004e9bd  ldmxcsr [rsp+98h+arg_0]
0x18004e9c5  jmp     short loc_18004EA2E
0x18004e9c7  stmxcsr [rsp+98h+arg_0]
0x18004e9cf  mov     ebx, [rsp+98h+arg_0]
0x18004e9d6  mov     rdx, rdi; HDC
0x18004e9d9  mov     eax, ebx
0x18004e9db  and     eax, ecx
0x18004e9dd  lea     rcx, [rsp+98h+var_78]; this
0x18004e9e2  mov     [rsp+98h+arg_0], eax
0x18004e9e9  mov     rax, [rsi+198h]
0x18004e9f0  ldmxcsr [rsp+98h+arg_0]
0x18004e9f8  mov     [rsp+98h+var_78], rax
0x18004e9fd  mov     rax, [rsi+1A0h]
0x18004ea04  mov     [rsp+98h+var_70], rax
0x18004ea09  mov     eax, [rsi+1ACh]
0x18004ea0f  mov     [rsp+98h+var_68], eax
0x18004ea13  call    ?Draw@CPolyPolygon@@QEAAHPEAUHDC__@@@Z; CPolyPolygon::Draw(HDC__ *)
0x18004ea18  mov     ecx, 0FFFFFFC0h
0x18004ea1d  and     ebx, ecx
0x18004ea1f  mov     [rsp+98h+arg_0], ebx
0x18004ea26  ldmxcsr [rsp+98h+arg_0]
0x18004ea2e  mov     rdx, r14; h
0x18004ea31  mov     rcx, rdi; hdc
0x18004ea34  mov     ebp, eax
0x18004ea36  call    cs:__imp_SelectObject
0x18004ea3c  jmp     short loc_18004EA8B
0x18004ea3e  mov     rcx, rdi; hdc
0x18004ea41  call    cs:__imp_BeginPath
0x18004ea47  test    byte ptr [rsi+1B4h], 10h
0x18004ea4e  jz      short loc_18004EAC7
0x18004ea50  test    eax, eax
0x18004ea52  jz      short loc_18004EA89
0x18004ea54  mov     r8d, [rsi+1A8h]; cpt
0x18004ea5b  mov     rcx, rdi; hdc
0x18004ea5e  mov     rdx, [rsi+198h]; apt
0x18004ea65  call    cs:__imp_PolyBezier
0x18004ea6b  test    eax, eax
0x18004ea6d  jz      short loc_18004EA89
0x18004ea6f  mov     rcx, rdi; hdc
0x18004ea72  call    cs:__imp_EndPath
0x18004ea78  test    eax, eax
0x18004ea7a  jz      short loc_18004EA89
0x18004ea7c  mov     rcx, rdi; hdc
0x18004ea7f  call    cs:__imp_FillPath
0x18004ea85  test    eax, eax
0x18004ea87  jnz     short loc_18004EA8B
0x18004ea89  xor     ebp, ebp
0x18004ea8b  mov     edx, r13d; mode
0x18004ea8e  mov     rcx, rdi; hdc
0x18004ea91  call    cs:__imp_SetPolyFillMode
0x18004ea97  mov     rdx, r12; h
0x18004ea9a  mov     rcx, rdi; hdc
0x18004ea9d  call    cs:__imp_SelectObject
0x18004eaa3  mov     ecx, [rsi+1BCh]; int
0x18004eaa9  mov     r8, rdi; HDC
0x18004eaac  mov     edx, r15d; int
0x18004eaaf  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x18004eab4  mov     eax, ebp
0x18004eab6  add     rsp, 58h
0x18004eaba  pop     r15
0x18004eabc  pop     r14
0x18004eabe  pop     r13
0x18004eac0  pop     r12
0x18004eac2  pop     rdi
0x18004eac3  pop     rsi
0x18004eac4  pop     rbp
0x18004eac5  pop     rbx
0x18004eac6  retn
0x18004eac7  test    eax, eax
0x18004eac9  jz      short loc_18004EA89
0x18004eacb  mov     rdx, rdi; HDC
0x18004eace  mov     rcx, rsi; this
0x18004ead1  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x18004ead6  jmp     short loc_18004EA6B
```
