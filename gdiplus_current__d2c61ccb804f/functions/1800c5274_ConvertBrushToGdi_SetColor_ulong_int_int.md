# ConvertBrushToGdi::SetColor(ulong,int,int)

- ea: `0x1800c5274`
- end: `0x1800c5351`
- name: `?SetColor@ConvertBrushToGdi@@QEAAXKHH@Z`
- size: `221`
- prototype: `void(ConvertBrushToGdi *__hidden this, unsigned int, int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800da830`
- `0x1800e80f0`
- `0x1800f1c70`
- `0x1800f6f6c`
- `0x180142d30`
- `0x1801431e8`

## callees

- `0x18002720c`
- `0x1800c5274`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1800c52cb`
- `GDI32!CreateSolidBrush` at `0x1800c52cb`
- `GDI32!GetStockObject` at `0x1800c52fd`
- `GDI32!GetStockObject` at `0x1800c52fd`
- `GDI32!DeleteObject` at `0x1800c5315`
- `GDI32!DeleteObject` at `0x1800c532a`
- `GDI32!DeleteObject` at `0x1800c5315`
- `GDI32!DeleteObject` at `0x1800c532a`

## pseudocode

```c
void __fastcall ConvertBrushToGdi::SetColor(ConvertBrushToGdi *this, COLORREF a2, int a3, int a4)
{
  _DWORD *v4; // rdi
  COLORREF v5; // ebp
  _QWORD *v9; // rsi
  HBRUSH SolidBrush; // rax

  v4 = (_DWORD *)((char *)this + 4);
  v5 = a2 | 0x2000000;
  if ( !a4 )
    v5 = a2;
  if ( *(_DWORD *)this == 1198932785 )
  {
    if ( !*v4 && v5 == *((_DWORD *)this + 5) )
      return;
    v9 = (_QWORD *)((char *)this + 8);
    DeleteObject(*((HGDIOBJ *)this + 1));
    if ( *v4 == 2 )
    {
      DeleteObject(*((HGDIOBJ *)this + 3));
      *((_QWORD *)this + 3) = 0;
    }
  }
  else
  {
    v9 = (_QWORD *)((char *)this + 8);
  }
  *v4 = 0;
  if ( a4 || !a3 )
    SolidBrush = CreateSolidBrush(v5);
  else
    SolidBrush = ConvertBrushToGdi::CreateHalftoneBrush(v5);
  *v9 = SolidBrush;
  *((_DWORD *)this + 5) = v5;
  *(_DWORD *)this = SolidBrush != 0 ? 1198932785 : 1279869254;
  if ( !SolidBrush )
    *v9 = GetStockObject(2);
}

```

## disassembly

```asm
0x1800c5274  push    rbx
0x1800c5276  push    rbp
0x1800c5277  push    rsi
0x1800c5278  push    rdi
0x1800c5279  push    r14
0x1800c527b  push    r15
0x1800c527d  sub     rsp, 28h
0x1800c5281  mov     ebp, edx
0x1800c5283  lea     rdi, [rcx+4]
0x1800c5287  bts     ebp, 19h
0x1800c528b  mov     r14d, r9d
0x1800c528e  test    r9d, r9d
0x1800c5291  mov     r15d, r8d
0x1800c5294  mov     rbx, rcx
0x1800c5297  cmovz   ebp, edx
0x1800c529a  cmp     dword ptr [rcx], 47764331h
0x1800c52a0  jnz     short loc_1800C52BA
0x1800c52a2  cmp     dword ptr [rdi], 0
0x1800c52a5  jnz     short loc_1800C530E
0x1800c52a7  cmp     ebp, [rcx+14h]
0x1800c52aa  jnz     short loc_1800C530E
0x1800c52ac  add     rsp, 28h
0x1800c52b0  pop     r15
0x1800c52b2  pop     r14
0x1800c52b4  pop     rdi
0x1800c52b5  pop     rsi
0x1800c52b6  pop     rbp
0x1800c52b7  pop     rbx
0x1800c52b8  retn
0x1800c52ba  lea     rsi, [rcx+8]
0x1800c52be  mov     dword ptr [rdi], 0
0x1800c52c4  test    r14d, r14d
0x1800c52c7  jz      short loc_1800C5343
0x1800c52c9  mov     ecx, ebp; color
0x1800c52cb  call    cs:__imp_CreateSolidBrush
0x1800c52d2  nop     dword ptr [rax+rax+00h]
0x1800c52d7  mov     [rsi], rax
0x1800c52da  mov     rcx, rax
0x1800c52dd  neg     rax
0x1800c52e0  mov     [rbx+14h], ebp
0x1800c52e3  sbb     edx, edx
0x1800c52e5  and     edx, 0FB2D01EBh
0x1800c52eb  add     edx, 4C494146h
0x1800c52f1  mov     [rbx], edx
0x1800c52f3  test    rcx, rcx
0x1800c52f6  jnz     short loc_1800C52AC
0x1800c52f8  mov     ecx, 2; i
0x1800c52fd  call    cs:__imp_GetStockObject
0x1800c5304  nop     dword ptr [rax+rax+00h]
0x1800c5309  mov     [rsi], rax
0x1800c530c  jmp     short loc_1800C52AC
0x1800c530e  lea     rsi, [rcx+8]
0x1800c5312  mov     rcx, [rsi]; ho
0x1800c5315  call    cs:__imp_DeleteObject
0x1800c531c  nop     dword ptr [rax+rax+00h]
0x1800c5321  cmp     dword ptr [rdi], 2
0x1800c5324  jnz     short loc_1800C52BE
0x1800c5326  mov     rcx, [rbx+18h]; ho
0x1800c532a  call    cs:__imp_DeleteObject
0x1800c5331  nop     dword ptr [rax+rax+00h]
0x1800c5336  mov     qword ptr [rbx+18h], 0
0x1800c533e  jmp     loc_1800C52BE
0x1800c5343  test    r15d, r15d
0x1800c5346  jz      short loc_1800C52C9
0x1800c5348  mov     ecx, ebp; unsigned int
0x1800c534a  call    ?CreateHalftoneBrush@ConvertBrushToGdi@@SAPEAUHBRUSH__@@K@Z; ConvertBrushToGdi::CreateHalftoneBrush(ulong)
0x1800c534f  jmp     short loc_1800C52D7
```
