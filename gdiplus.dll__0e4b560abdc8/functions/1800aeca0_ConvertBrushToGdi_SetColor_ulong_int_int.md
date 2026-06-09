# ConvertBrushToGdi::SetColor(ulong,int,int)

- ea: `0x1800aeca0`
- end: `0x1800aed7b`
- name: `?SetColor@ConvertBrushToGdi@@QEAAXKHH@Z`
- size: `219`
- prototype: `void(ConvertBrushToGdi *__hidden this, unsigned int, int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ac30`
- `0x1800d6740`
- `0x180137ad0`
- `0x180137dd0`
- `0x180138a00`
- `0x180138be8`

## callees

- `0x1800aeca0`
- `0x1800d6520`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1800aed12`
- `GDI32!CreateSolidBrush` at `0x1800aed12`
- `GDI32!GetStockObject` at `0x1800aed45`
- `GDI32!GetStockObject` at `0x1800aed45`
- `GDI32!DeleteObject` at `0x1800aecf6`
- `GDI32!DeleteObject` at `0x1800aed5b`
- `GDI32!DeleteObject` at `0x1800aecf6`
- `GDI32!DeleteObject` at `0x1800aed5b`

## pseudocode

```c
void __fastcall ConvertBrushToGdi::SetColor(ConvertBrushToGdi *this, COLORREF a2, int a3, int a4)
{
  COLORREF v5; // edi
  HBRUSH SolidBrush; // rax

  v5 = a2 | 0x2000000;
  if ( !a4 )
    v5 = a2;
  if ( *(_DWORD *)this == 1198932785 )
  {
    if ( !*((_DWORD *)this + 1) && v5 == *((_DWORD *)this + 5) )
      return;
    DeleteObject(*((HGDIOBJ *)this + 1));
    if ( *((_DWORD *)this + 1) == 2 )
    {
      DeleteObject(*((HGDIOBJ *)this + 3));
      *((_QWORD *)this + 3) = 0;
    }
  }
  *((_DWORD *)this + 1) = 0;
  if ( a4 || !a3 )
    SolidBrush = CreateSolidBrush(v5);
  else
    SolidBrush = ConvertBrushToGdi::CreateHalftoneBrush(v5);
  *((_QWORD *)this + 1) = SolidBrush;
  *((_DWORD *)this + 5) = v5;
  *(_DWORD *)this = SolidBrush != 0 ? 1198932785 : 1279869254;
  if ( !SolidBrush )
    *((_QWORD *)this + 1) = GetStockObject(2);
}

```

## disassembly

```asm
0x1800aeca0  mov     [rsp+arg_0], rbx
0x1800aeca5  mov     [rsp+arg_8], rbp
0x1800aecaa  mov     [rsp+arg_10], rsi
0x1800aecaf  push    rdi
0x1800aecb0  sub     rsp, 20h
0x1800aecb4  mov     edi, edx
0x1800aecb6  mov     esi, r9d
0x1800aecb9  bts     edi, 19h
0x1800aecbd  mov     ebp, r8d
0x1800aecc0  test    r9d, r9d
0x1800aecc3  mov     rbx, rcx
0x1800aecc6  cmovz   edi, edx
0x1800aecc9  cmp     dword ptr [rcx], 47764331h
0x1800aeccf  jnz     short loc_1800AED08
0x1800aecd1  cmp     dword ptr [rcx+4], 0
0x1800aecd5  jnz     short loc_1800AECF2
0x1800aecd7  cmp     edi, [rcx+14h]
0x1800aecda  jnz     short loc_1800AECF2
0x1800aecdc  mov     rbx, [rsp+28h+arg_0]
0x1800aece1  mov     rbp, [rsp+28h+arg_8]
0x1800aece6  mov     rsi, [rsp+28h+arg_10]
0x1800aeceb  add     rsp, 20h
0x1800aecef  pop     rdi
0x1800aecf0  retn
0x1800aecf2  mov     rcx, [rcx+8]; ho
0x1800aecf6  call    cs:__imp_DeleteObject
0x1800aecfd  nop     dword ptr [rax+rax+00h]
0x1800aed02  cmp     dword ptr [rbx+4], 2
0x1800aed06  jz      short loc_1800AED57
0x1800aed08  and     dword ptr [rbx+4], 0
0x1800aed0c  test    esi, esi
0x1800aed0e  jz      short loc_1800AED6E
0x1800aed10  mov     ecx, edi; color
0x1800aed12  call    cs:__imp_CreateSolidBrush
0x1800aed19  nop     dword ptr [rax+rax+00h]
0x1800aed1e  mov     [rbx+8], rax
0x1800aed22  mov     rcx, rax
0x1800aed25  neg     rax
0x1800aed28  mov     [rbx+14h], edi
0x1800aed2b  sbb     edx, edx
0x1800aed2d  and     edx, 0FB2D01EBh
0x1800aed33  add     edx, 4C494146h
0x1800aed39  mov     [rbx], edx
0x1800aed3b  test    rcx, rcx
0x1800aed3e  jnz     short loc_1800AECDC
0x1800aed40  mov     ecx, 2; i
0x1800aed45  call    cs:__imp_GetStockObject
0x1800aed4c  nop     dword ptr [rax+rax+00h]
0x1800aed51  mov     [rbx+8], rax
0x1800aed55  jmp     short loc_1800AECDC
0x1800aed57  mov     rcx, [rbx+18h]; ho
0x1800aed5b  call    cs:__imp_DeleteObject
0x1800aed62  nop     dword ptr [rax+rax+00h]
0x1800aed67  and     qword ptr [rbx+18h], 0
0x1800aed6c  jmp     short loc_1800AED08
0x1800aed6e  test    ebp, ebp
0x1800aed70  jz      short loc_1800AED10
0x1800aed72  mov     ecx, edi; unsigned int
0x1800aed74  call    ?CreateHalftoneBrush@ConvertBrushToGdi@@SAPEAUHBRUSH__@@K@Z; ConvertBrushToGdi::CreateHalftoneBrush(ulong)
0x1800aed79  jmp     short loc_1800AED1E
```
