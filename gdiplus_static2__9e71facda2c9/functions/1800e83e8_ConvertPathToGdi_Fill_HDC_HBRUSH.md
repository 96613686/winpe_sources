# ConvertPathToGdi::Fill(HDC__ *,HBRUSH__ *)

- ea: `0x1800e83e8`
- end: `0x1800e8694`
- name: `?Fill@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHBRUSH__@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HBRUSH h)`
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003eb90`
- `0x1800e80f0`
- `0x1800fafbc`
- `0x18014057c`
- `0x180144294`

## callees

- `0x18002aae8`
- `0x18002abc0`
- `0x1800d9598`
- `0x1800e83e8`
- `0x180144998`

## import_xrefs

- `GDI32!FillPath` at `0x1800e8625`
- `GDI32!FillPath` at `0x1800e8625`
- `GDI32!PolyBezier` at `0x1800e85ff`
- `GDI32!PolyBezier` at `0x1800e85ff`
- `GDI32!SetPolyFillMode` at `0x1800e8464`
- `GDI32!SetPolyFillMode` at `0x1800e863d`
- `GDI32!SetPolyFillMode` at `0x1800e8464`
- `GDI32!SetPolyFillMode` at `0x1800e863d`
- `GDI32!EndPath` at `0x1800e8612`
- `GDI32!EndPath` at `0x1800e8612`
- `GDI32!BeginPath` at `0x1800e85d1`
- `GDI32!BeginPath` at `0x1800e85d1`
- `GDI32!Polygon` at `0x1800e852d`
- `GDI32!Polygon` at `0x1800e852d`
- `GDI32!GetStockObject` at `0x1800e84bb`
- `GDI32!GetStockObject` at `0x1800e84bb`
- `GDI32!SelectObject` at `0x1800e844c`
- `GDI32!SelectObject` at `0x1800e84cd`
- `GDI32!SelectObject` at `0x1800e85c0`
- `GDI32!SelectObject` at `0x1800e864f`
- `GDI32!SelectObject` at `0x1800e844c`
- `GDI32!SelectObject` at `0x1800e84cd`
- `GDI32!SelectObject` at `0x1800e85c0`
- `GDI32!SelectObject` at `0x1800e864f`

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
0x1800e83e8  push    rbx
0x1800e83ea  push    rbp
0x1800e83eb  push    rsi
0x1800e83ec  push    rdi
0x1800e83ed  push    r12
0x1800e83ef  push    r13
0x1800e83f1  push    r14
0x1800e83f3  push    r15
0x1800e83f5  sub     rsp, 58h
0x1800e83f9  xor     ebx, ebx
0x1800e83fb  mov     r14, r8
0x1800e83fe  mov     rdi, rdx
0x1800e8401  mov     rsi, rcx
0x1800e8404  mov     ebp, 1
0x1800e8409  cmp     [rcx+1A8h], ebx
0x1800e840f  jle     loc_1800E866C
0x1800e8415  mov     ecx, [rcx+1BCh]; int
0x1800e841b  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x1800e8420  mov     r15d, eax
0x1800e8423  stmxcsr [rsp+98h+arg_0]
0x1800e842b  mov     ebx, [rsp+98h+arg_0]
0x1800e8432  mov     rdx, r14; h
0x1800e8435  mov     eax, ebx
0x1800e8437  mov     rcx, rdi; hdc
0x1800e843a  and     eax, 0FFFFFFC0h
0x1800e843d  mov     [rsp+98h+arg_0], eax
0x1800e8444  ldmxcsr [rsp+98h+arg_0]
0x1800e844c  call    cs:__imp_SelectObject
0x1800e8453  nop     dword ptr [rax+rax+00h]
0x1800e8458  mov     edx, [rsi+1B0h]; mode
0x1800e845e  mov     rcx, rdi; hdc
0x1800e8461  mov     r12, rax
0x1800e8464  call    cs:__imp_SetPolyFillMode
0x1800e846b  nop     dword ptr [rax+rax+00h]
0x1800e8470  mov     ecx, 0FFFFFFC0h
0x1800e8475  mov     r13d, eax
0x1800e8478  and     ebx, ecx
0x1800e847a  mov     [rsp+98h+arg_0], ebx
0x1800e8481  ldmxcsr [rsp+98h+arg_0]
0x1800e8489  test    [rsi+1B4h], bpl
0x1800e8490  jz      loc_1800E85CE
0x1800e8496  stmxcsr [rsp+98h+arg_0]
0x1800e849e  mov     ebx, [rsp+98h+arg_0]
0x1800e84a5  mov     eax, ebx
0x1800e84a7  and     eax, ecx
0x1800e84a9  lea     ecx, [rbp+7]; i
0x1800e84ac  mov     [rsp+98h+arg_0], eax
0x1800e84b3  ldmxcsr [rsp+98h+arg_0]
0x1800e84bb  call    cs:__imp_GetStockObject
0x1800e84c2  nop     dword ptr [rax+rax+00h]
0x1800e84c7  mov     rdx, rax; h
0x1800e84ca  mov     rcx, rdi; hdc
0x1800e84cd  call    cs:__imp_SelectObject
0x1800e84d4  nop     dword ptr [rax+rax+00h]
0x1800e84d9  mov     ecx, 0FFFFFFC0h
0x1800e84de  mov     r14, rax
0x1800e84e1  and     ebx, ecx
0x1800e84e3  mov     [rsp+98h+arg_0], ebx
0x1800e84ea  ldmxcsr [rsp+98h+arg_0]
0x1800e84f2  cmp     [rsi+1ACh], ebp
0x1800e84f8  jnz     short loc_1800E8551
0x1800e84fa  stmxcsr [rsp+98h+arg_0]
0x1800e8502  mov     ebx, [rsp+98h+arg_0]
0x1800e8509  mov     eax, ebx
0x1800e850b  mov     r8d, [rsi+1A8h]; cpt
0x1800e8512  and     eax, ecx
0x1800e8514  mov     rdx, [rsi+198h]; apt
0x1800e851b  mov     rcx, rdi; hdc
0x1800e851e  mov     [rsp+98h+arg_0], eax
0x1800e8525  ldmxcsr [rsp+98h+arg_0]
0x1800e852d  call    cs:__imp_Polygon
0x1800e8534  nop     dword ptr [rax+rax+00h]
0x1800e8539  mov     ecx, 0FFFFFFC0h
0x1800e853e  and     ebx, ecx
0x1800e8540  mov     [rsp+98h+arg_0], ebx
0x1800e8547  ldmxcsr [rsp+98h+arg_0]
0x1800e854f  jmp     short loc_1800E85B8
0x1800e8551  stmxcsr [rsp+98h+arg_0]
0x1800e8559  mov     ebx, [rsp+98h+arg_0]
0x1800e8560  mov     rdx, rdi; HDC
0x1800e8563  mov     eax, ebx
0x1800e8565  and     eax, ecx
0x1800e8567  lea     rcx, [rsp+98h+var_78]; this
0x1800e856c  mov     [rsp+98h+arg_0], eax
0x1800e8573  mov     rax, [rsi+198h]
0x1800e857a  ldmxcsr [rsp+98h+arg_0]
0x1800e8582  mov     [rsp+98h+var_78], rax
0x1800e8587  mov     rax, [rsi+1A0h]
0x1800e858e  mov     [rsp+98h+var_70], rax
0x1800e8593  mov     eax, [rsi+1ACh]
0x1800e8599  mov     [rsp+98h+var_68], eax
0x1800e859d  call    ?Draw@CPolyPolygon@@QEAAHPEAUHDC__@@@Z; CPolyPolygon::Draw(HDC__ *)
0x1800e85a2  mov     ecx, 0FFFFFFC0h
0x1800e85a7  and     ebx, ecx
0x1800e85a9  mov     [rsp+98h+arg_0], ebx
0x1800e85b0  ldmxcsr [rsp+98h+arg_0]
0x1800e85b8  mov     rdx, r14; h
0x1800e85bb  mov     rcx, rdi; hdc
0x1800e85be  mov     ebp, eax
0x1800e85c0  call    cs:__imp_SelectObject
0x1800e85c7  nop     dword ptr [rax+rax+00h]
0x1800e85cc  jmp     short loc_1800E8637
0x1800e85ce  mov     rcx, rdi; hdc
0x1800e85d1  call    cs:__imp_BeginPath
0x1800e85d8  nop     dword ptr [rax+rax+00h]
0x1800e85dd  test    byte ptr [rsi+1B4h], 10h
0x1800e85e4  jz      loc_1800E8680
0x1800e85ea  test    eax, eax
0x1800e85ec  jz      short loc_1800E8635
0x1800e85ee  mov     r8d, [rsi+1A8h]; cpt
0x1800e85f5  mov     rcx, rdi; hdc
0x1800e85f8  mov     rdx, [rsi+198h]; apt
0x1800e85ff  call    cs:__imp_PolyBezier
0x1800e8606  nop     dword ptr [rax+rax+00h]
0x1800e860b  test    eax, eax
0x1800e860d  jz      short loc_1800E8635
0x1800e860f  mov     rcx, rdi; hdc
0x1800e8612  call    cs:__imp_EndPath
0x1800e8619  nop     dword ptr [rax+rax+00h]
0x1800e861e  test    eax, eax
0x1800e8620  jz      short loc_1800E8635
0x1800e8622  mov     rcx, rdi; hdc
0x1800e8625  call    cs:__imp_FillPath
0x1800e862c  nop     dword ptr [rax+rax+00h]
0x1800e8631  test    eax, eax
0x1800e8633  jnz     short loc_1800E8637
0x1800e8635  xor     ebp, ebp
0x1800e8637  mov     edx, r13d; mode
0x1800e863a  mov     rcx, rdi; hdc
0x1800e863d  call    cs:__imp_SetPolyFillMode
0x1800e8644  nop     dword ptr [rax+rax+00h]
0x1800e8649  mov     rdx, r12; h
0x1800e864c  mov     rcx, rdi; hdc
0x1800e864f  call    cs:__imp_SelectObject
0x1800e8656  nop     dword ptr [rax+rax+00h]
0x1800e865b  mov     ecx, [rsi+1BCh]; int
0x1800e8661  mov     r8, rdi; HDC
0x1800e8664  mov     edx, r15d; int
0x1800e8667  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x1800e866c  mov     eax, ebp
0x1800e866e  add     rsp, 58h
0x1800e8672  pop     r15
0x1800e8674  pop     r14
0x1800e8676  pop     r13
0x1800e8678  pop     r12
0x1800e867a  pop     rdi
0x1800e867b  pop     rsi
0x1800e867c  pop     rbp
0x1800e867d  pop     rbx
0x1800e867e  retn
0x1800e8680  test    eax, eax
0x1800e8682  jz      short loc_1800E8635
0x1800e8684  mov     rdx, rdi; HDC
0x1800e8687  mov     rcx, rsi; this
0x1800e868a  call    ?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z; ConvertPathToGdi::DrawMixedPath(HDC__ *)
0x1800e868f  jmp     loc_1800E860B
```
