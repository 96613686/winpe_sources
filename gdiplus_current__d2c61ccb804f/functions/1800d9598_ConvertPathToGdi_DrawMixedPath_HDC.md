# ConvertPathToGdi::DrawMixedPath(HDC__ *)

- ea: `0x1800d9598`
- end: `0x1800d9753`
- name: `?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z`
- size: `443`
- prototype: `int(ConvertPathToGdi *__hidden this, HDC)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800270a4`
- `0x180029b74`
- `0x1800e83e8`
- `0x180144ac4`

## callees

- `0x1800d9598`

## import_xrefs

- `GDI32!LineTo` at `0x1800d9712`
- `GDI32!LineTo` at `0x1800d9712`
- `GDI32!CloseFigure` at `0x1800d96ba`
- `GDI32!CloseFigure` at `0x1800d9733`
- `GDI32!CloseFigure` at `0x1800d96ba`
- `GDI32!CloseFigure` at `0x1800d9733`
- `GDI32!PolylineTo` at `0x1800d9632`
- `GDI32!PolylineTo` at `0x1800d9632`
- `GDI32!PolyBezierTo` at `0x1800d9662`
- `GDI32!PolyBezierTo` at `0x1800d9662`
- `GDI32!MoveToEx` at `0x1800d96df`
- `GDI32!MoveToEx` at `0x1800d96df`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::DrawMixedPath(ConvertPathToGdi *this, HDC a2)
{
  __int64 v2; // r13
  __int64 *v3; // rsi
  int v4; // ebx
  unsigned int v7; // r8d
  int v8; // r15d
  __int64 v9; // r9
  __int64 v10; // rdi
  int v11; // edx
  int v12; // r10d
  const POINT *v13; // rdx
  BOOL v14; // eax

  v2 = *((int *)this + 106);
  v3 = (__int64 *)((char *)this + 416);
  v4 = 0;
  v7 = 1;
  v8 = v2 - 1;
  if ( (int)v2 - 1 >= 0 )
  {
    while ( 1 )
    {
      v9 = *v3;
      v10 = v4;
      v11 = *(_BYTE *)(*v3 + v4) & 7;
      if ( (*(_BYTE *)(*v3 + v4) & 7) == 0 )
        break;
      v12 = v4;
      do
        ++v4;
      while ( v4 <= v8 && (*(_BYTE *)(v4 + v9) & 7) == v11 );
      if ( v11 == 3 )
      {
        if ( !v7 )
          goto LABEL_28;
        v14 = PolyBezierTo(a2, (const POINT *)(*((_QWORD *)this + 51) + 8 * v10), v4 - v12);
      }
      else
      {
        v13 = (const POINT *)(*((_QWORD *)this + 51) + 8 * v10);
        if ( v4 - v12 == 1 )
        {
          if ( !v7 )
          {
LABEL_28:
            v7 = 0;
            goto LABEL_14;
          }
          v14 = LineTo(a2, v13->x, v13->y);
        }
        else
        {
          if ( !v7 )
            goto LABEL_28;
          v14 = PolylineTo(a2, v13, v4 - v12);
        }
      }
      if ( !v14 )
        goto LABEL_28;
      v7 = 1;
LABEL_14:
      if ( v4 > v8 )
        goto LABEL_15;
    }
    if ( v4 <= 0 || *(char *)(v9 + v4 - 1) >= 0 )
    {
      if ( !v7 )
        goto LABEL_24;
    }
    else if ( !v7 || !CloseFigure(a2) )
    {
      goto LABEL_24;
    }
    if ( MoveToEx(
           a2,
           *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * v4),
           *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * v4 + 4),
           0) )
    {
      v7 = 1;
LABEL_25:
      ++v4;
      goto LABEL_14;
    }
LABEL_24:
    v7 = 0;
    goto LABEL_25;
  }
LABEL_15:
  if ( *(char *)(v2 + *v3 - 1) < 0 )
    return v7 && CloseFigure(a2);
  return v7;
}

```

## disassembly

```asm
0x1800d9598  push    rbx
0x1800d959a  push    rbp
0x1800d959b  push    rsi
0x1800d959c  push    rdi
0x1800d959d  push    r12
0x1800d959f  push    r13
0x1800d95a1  push    r14
0x1800d95a3  push    r15
0x1800d95a5  sub     rsp, 28h
0x1800d95a9  movsxd  r13, dword ptr [rcx+1A8h]
0x1800d95b0  lea     rsi, [rcx+1A0h]
0x1800d95b7  xor     ebx, ebx
0x1800d95b9  mov     r12d, 1
0x1800d95bf  mov     rbp, rdx
0x1800d95c2  mov     r14, rcx
0x1800d95c5  mov     r8d, r12d
0x1800d95c8  lea     r15d, [r13-1]
0x1800d95cc  test    r15d, r15d
0x1800d95cf  js      loc_1800D9682
0x1800d95d5  mov     r9, [rsi]
0x1800d95d8  movsxd  rdi, ebx
0x1800d95db  movzx   edx, byte ptr [r9+rdi]
0x1800d95e0  and     edx, 7
0x1800d95e3  jz      loc_1800D96A6
0x1800d95e9  mov     r10d, ebx
0x1800d95ec  jmp     short loc_1800D95FD
0x1800d95ee  movsxd  rax, ebx
0x1800d95f1  movzx   ecx, byte ptr [rax+r9]
0x1800d95f6  and     ecx, 7
0x1800d95f9  cmp     ecx, edx
0x1800d95fb  jnz     short loc_1800D9605
0x1800d95fd  add     ebx, r12d
0x1800d9600  cmp     ebx, r15d
0x1800d9603  jle     short loc_1800D95EE
0x1800d9605  sub     edx, r12d
0x1800d9608  jnz     short loc_1800D9640
0x1800d960a  mov     rax, [r14+198h]
0x1800d9611  lea     rdx, [rax+rdi*8]; apt
0x1800d9615  mov     eax, ebx
0x1800d9617  sub     eax, r10d
0x1800d961a  cmp     eax, r12d
0x1800d961d  jz      loc_1800D9704
0x1800d9623  test    r8d, r8d
0x1800d9626  jz      loc_1800D9723
0x1800d962c  mov     r8d, eax; cpt
0x1800d962f  mov     rcx, rbp; hdc
0x1800d9632  call    cs:__imp_PolylineTo
0x1800d9639  nop     dword ptr [rax+rax+00h]
0x1800d963e  jmp     short loc_1800D966E
0x1800d9640  cmp     edx, 2
0x1800d9643  jnz     short loc_1800D960A
0x1800d9645  test    r8d, r8d
0x1800d9648  jz      loc_1800D9723
0x1800d964e  mov     rax, [r14+198h]
0x1800d9655  mov     r8d, ebx
0x1800d9658  sub     r8d, r10d; cpt
0x1800d965b  mov     rcx, rbp; hdc
0x1800d965e  lea     rdx, [rax+rdi*8]; apt
0x1800d9662  call    cs:__imp_PolyBezierTo
0x1800d9669  nop     dword ptr [rax+rax+00h]
0x1800d966e  test    eax, eax
0x1800d9670  jz      loc_1800D9723
0x1800d9676  mov     r8d, r12d
0x1800d9679  cmp     ebx, r15d
0x1800d967c  jle     loc_1800D95D5
0x1800d9682  mov     rax, [rsi]
0x1800d9685  cmp     byte ptr [r13+rax-1], 0
0x1800d968b  jl      loc_1800D972B
0x1800d9691  mov     eax, r8d
0x1800d9694  add     rsp, 28h
0x1800d9698  pop     r15
0x1800d969a  pop     r14
0x1800d969c  pop     r13
0x1800d969e  pop     r12
0x1800d96a0  pop     rdi
0x1800d96a1  pop     rsi
0x1800d96a2  pop     rbp
0x1800d96a3  pop     rbx
0x1800d96a4  retn
0x1800d96a6  test    ebx, ebx
0x1800d96a8  jle     short loc_1800D96F4
0x1800d96aa  cmp     byte ptr [r9+rdi-1], 0
0x1800d96b0  jge     short loc_1800D96F4
0x1800d96b2  test    r8d, r8d
0x1800d96b5  jz      short loc_1800D96F9
0x1800d96b7  mov     rcx, rbp; hdc
0x1800d96ba  call    cs:__imp_CloseFigure
0x1800d96c1  nop     dword ptr [rax+rax+00h]
0x1800d96c6  test    eax, eax
0x1800d96c8  jz      short loc_1800D96F9
0x1800d96ca  mov     rdx, [r14+198h]
0x1800d96d1  xor     r9d, r9d; lppt
0x1800d96d4  mov     rcx, rbp; hdc
0x1800d96d7  mov     r8d, [rdx+rdi*8+4]; y
0x1800d96dc  mov     edx, [rdx+rdi*8]; x
0x1800d96df  call    cs:__imp_MoveToEx
0x1800d96e6  nop     dword ptr [rax+rax+00h]
0x1800d96eb  test    eax, eax
0x1800d96ed  jz      short loc_1800D96F9
0x1800d96ef  mov     r8d, r12d
0x1800d96f2  jmp     short loc_1800D96FC
0x1800d96f4  test    r8d, r8d
0x1800d96f7  jnz     short loc_1800D96CA
0x1800d96f9  xor     r8d, r8d
0x1800d96fc  add     ebx, r12d
0x1800d96ff  jmp     loc_1800D9679
0x1800d9704  test    r8d, r8d
0x1800d9707  jz      short loc_1800D9723
0x1800d9709  mov     r8d, [rdx+4]; y
0x1800d970d  mov     rcx, rbp; hdc
0x1800d9710  mov     edx, [rdx]; x
0x1800d9712  call    cs:__imp_LineTo
0x1800d9719  nop     dword ptr [rax+rax+00h]
0x1800d971e  jmp     loc_1800D966E
0x1800d9723  xor     r8d, r8d
0x1800d9726  jmp     loc_1800D9679
0x1800d972b  test    r8d, r8d
0x1800d972e  jz      short loc_1800D974B
0x1800d9730  mov     rcx, rbp; hdc
0x1800d9733  call    cs:__imp_CloseFigure
0x1800d973a  nop     dword ptr [rax+rax+00h]
0x1800d973f  test    eax, eax
0x1800d9741  jz      short loc_1800D974B
0x1800d9743  mov     r8d, r12d
0x1800d9746  jmp     loc_1800D9691
0x1800d974b  xor     r8d, r8d
0x1800d974e  jmp     loc_1800D9691
```
