# ConvertPathToGdi::DrawMixedPath(HDC__ *)

- ea: `0x1800bd49c`
- end: `0x1800bd667`
- name: `?DrawMixedPath@ConvertPathToGdi@@IEAAHPEAUHDC__@@@Z`
- size: `459`
- prototype: `int(ConvertPathToGdi *__hidden this, HDC)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180029e00`
- `0x1800d5f10`
- `0x1800dcc0c`
- `0x18013af50`

## callees

- `0x1800bd49c`

## import_xrefs

- `GDI32!LineTo` at `0x1800bd629`
- `GDI32!LineTo` at `0x1800bd629`
- `GDI32!CloseFigure` at `0x1800bd5cb`
- `GDI32!CloseFigure` at `0x1800bd647`
- `GDI32!CloseFigure` at `0x1800bd5cb`
- `GDI32!CloseFigure` at `0x1800bd647`
- `GDI32!PolylineTo` at `0x1800bd53a`
- `GDI32!PolylineTo` at `0x1800bd53a`
- `GDI32!PolyBezierTo` at `0x1800bd5aa`
- `GDI32!PolyBezierTo` at `0x1800bd5aa`
- `GDI32!MoveToEx` at `0x1800bd5f0`
- `GDI32!MoveToEx` at `0x1800bd5f0`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::DrawMixedPath(ConvertPathToGdi *this, HDC a2)
{
  __int64 v2; // r15
  unsigned int v3; // r8d
  int v4; // edi
  __int64 v6; // r14
  __int64 v8; // rbx
  __int64 v9; // rdx
  int v10; // ecx
  __int64 v11; // r9
  __int64 v12; // r10
  const POINT *v13; // rdx
  BOOL v14; // eax
  bool v16; // zf

  v2 = *((int *)this + 106);
  v3 = 1;
  v4 = 0;
  v6 = v2 - 1;
  if ( v2 - 1 >= 0 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = *((_QWORD *)this + 52);
      v10 = *(_BYTE *)(v9 + v8) & 7;
      if ( (*(_BYTE *)(v9 + v8) & 7) == 0 )
        break;
      v11 = v4;
      v12 = v8;
      do
      {
        ++v4;
        ++v8;
      }
      while ( v8 <= v6 && (*(_BYTE *)(v9 + v8) & 7) == v10 );
      if ( v10 == 3 )
      {
        if ( !v3 )
          goto LABEL_27;
        v14 = PolyBezierTo(a2, (const POINT *)(*((_QWORD *)this + 51) + 8 * v11), v4 - v11);
      }
      else
      {
        v13 = (const POINT *)(*((_QWORD *)this + 51) + 8 * v12);
        if ( v4 - (_DWORD)v11 == 1 )
        {
          if ( !v3 )
          {
LABEL_27:
            v3 = 0;
            goto LABEL_13;
          }
          v14 = LineTo(a2, v13->x, v13->y);
        }
        else
        {
          if ( !v3 )
            goto LABEL_27;
          v14 = PolylineTo(a2, v13, v4 - v11);
        }
      }
      if ( !v14 )
        goto LABEL_27;
      v3 = 1;
LABEL_13:
      if ( v8 > v6 )
        goto LABEL_14;
    }
    if ( v4 <= 0 || *(char *)(v9 + v8 - 1) >= 0 )
    {
      v16 = v3 == 0;
    }
    else
    {
      if ( !v3 )
        goto LABEL_25;
      v16 = !CloseFigure(a2);
    }
    if ( !v16
      && MoveToEx(a2, *(_DWORD *)(*((_QWORD *)this + 51) + 8 * v8), *(_DWORD *)(*((_QWORD *)this + 51) + 8 * v8 + 4), 0) )
    {
      v3 = 1;
LABEL_26:
      ++v4;
      ++v8;
      goto LABEL_13;
    }
LABEL_25:
    v3 = 0;
    goto LABEL_26;
  }
LABEL_14:
  if ( *(char *)(*((_QWORD *)this + 52) + v2 - 1) < 0 )
    return v3 && CloseFigure(a2);
  return v3;
}

```

## disassembly

```asm
0x1800bd49c  mov     rax, rsp
0x1800bd49f  mov     [rax+8], rbx
0x1800bd4a3  mov     [rax+10h], rbp
0x1800bd4a7  mov     [rax+18h], rsi
0x1800bd4ab  mov     [rax+20h], rdi
0x1800bd4af  push    r12
0x1800bd4b1  push    r14
0x1800bd4b3  push    r15
0x1800bd4b5  sub     rsp, 20h
0x1800bd4b9  movsxd  r15, dword ptr [rcx+1A8h]
0x1800bd4c0  mov     r12d, 1
0x1800bd4c6  mov     r8d, r12d
0x1800bd4c9  mov     r14, r15
0x1800bd4cc  xor     edi, edi
0x1800bd4ce  mov     rsi, rdx
0x1800bd4d1  sub     r14, r8
0x1800bd4d4  mov     rbp, rcx
0x1800bd4d7  js      short loc_1800BD556
0x1800bd4d9  xor     ebx, ebx
0x1800bd4db  mov     rdx, [rbp+1A0h]
0x1800bd4e2  movzx   ecx, byte ptr [rdx+rbx]
0x1800bd4e6  and     ecx, 7
0x1800bd4e9  jz      loc_1800BD5B8
0x1800bd4ef  movsxd  r9, edi
0x1800bd4f2  mov     r10, rbx
0x1800bd4f5  jmp     short loc_1800BD502
0x1800bd4f7  movzx   eax, byte ptr [rdx+rbx]
0x1800bd4fb  and     eax, 7
0x1800bd4fe  cmp     eax, ecx
0x1800bd500  jnz     short loc_1800BD50D
0x1800bd502  add     edi, r12d
0x1800bd505  add     rbx, r12
0x1800bd508  cmp     rbx, r14
0x1800bd50b  jle     short loc_1800BD4F7
0x1800bd50d  sub     ecx, r12d
0x1800bd510  jnz     short loc_1800BD58C
0x1800bd512  mov     rax, [rbp+198h]
0x1800bd519  lea     rdx, [rax+r10*8]; apt
0x1800bd51d  mov     eax, edi
0x1800bd51f  sub     eax, r9d
0x1800bd522  cmp     eax, r12d
0x1800bd525  jz      loc_1800BD61B
0x1800bd52b  test    r8d, r8d
0x1800bd52e  jz      loc_1800BD613
0x1800bd534  mov     r8d, eax; cpt
0x1800bd537  mov     rcx, rsi; hdc
0x1800bd53a  call    cs:__imp_PolylineTo
0x1800bd541  nop     dword ptr [rax+rax+00h]
0x1800bd546  test    eax, eax
0x1800bd548  jz      loc_1800BD613
0x1800bd54e  mov     r8d, r12d
0x1800bd551  cmp     rbx, r14
0x1800bd554  jle     short loc_1800BD4DB
0x1800bd556  mov     rax, [rbp+1A0h]
0x1800bd55d  cmp     byte ptr [rax+r15-1], 0
0x1800bd563  jl      loc_1800BD63F
0x1800bd569  mov     rbx, [rsp+38h+arg_0]
0x1800bd56e  mov     eax, r8d
0x1800bd571  mov     rbp, [rsp+38h+arg_8]
0x1800bd576  mov     rsi, [rsp+38h+arg_10]
0x1800bd57b  mov     rdi, [rsp+38h+arg_18]
0x1800bd580  add     rsp, 20h
0x1800bd584  pop     r15
0x1800bd586  pop     r14
0x1800bd588  pop     r12
0x1800bd58a  retn
0x1800bd58c  cmp     ecx, 2
0x1800bd58f  jnz     short loc_1800BD512
0x1800bd591  test    r8d, r8d
0x1800bd594  jz      short loc_1800BD613
0x1800bd596  mov     rax, [rbp+198h]
0x1800bd59d  mov     r8d, edi
0x1800bd5a0  sub     r8d, r9d; cpt
0x1800bd5a3  mov     rcx, rsi; hdc
0x1800bd5a6  lea     rdx, [rax+r9*8]; apt
0x1800bd5aa  call    cs:__imp_PolyBezierTo
0x1800bd5b1  nop     dword ptr [rax+rax+00h]
0x1800bd5b6  jmp     short loc_1800BD546
0x1800bd5b8  test    edi, edi
0x1800bd5ba  jle     short loc_1800BD63A
0x1800bd5bc  cmp     byte ptr [rdx+rbx-1], 0
0x1800bd5c1  jge     short loc_1800BD63A
0x1800bd5c3  test    r8d, r8d
0x1800bd5c6  jz      short loc_1800BD605
0x1800bd5c8  mov     rcx, rsi; hdc
0x1800bd5cb  call    cs:__imp_CloseFigure
0x1800bd5d2  nop     dword ptr [rax+rax+00h]
0x1800bd5d7  test    eax, eax
0x1800bd5d9  jz      short loc_1800BD605
0x1800bd5db  mov     rdx, [rbp+198h]
0x1800bd5e2  xor     r9d, r9d; lppt
0x1800bd5e5  mov     rcx, rsi; hdc
0x1800bd5e8  mov     r8d, [rdx+rbx*8+4]; y
0x1800bd5ed  mov     edx, [rdx+rbx*8]; x
0x1800bd5f0  call    cs:__imp_MoveToEx
0x1800bd5f7  nop     dword ptr [rax+rax+00h]
0x1800bd5fc  test    eax, eax
0x1800bd5fe  jz      short loc_1800BD605
0x1800bd600  mov     r8d, r12d
0x1800bd603  jmp     short loc_1800BD608
0x1800bd605  xor     r8d, r8d
0x1800bd608  add     edi, r12d
0x1800bd60b  add     rbx, r12
0x1800bd60e  jmp     loc_1800BD551
0x1800bd613  xor     r8d, r8d
0x1800bd616  jmp     loc_1800BD551
0x1800bd61b  test    r8d, r8d
0x1800bd61e  jz      short loc_1800BD613
0x1800bd620  mov     r8d, [rdx+4]; y
0x1800bd624  mov     rcx, rsi; hdc
0x1800bd627  mov     edx, [rdx]; x
0x1800bd629  call    cs:__imp_LineTo
0x1800bd630  nop     dword ptr [rax+rax+00h]
0x1800bd635  jmp     loc_1800BD546
0x1800bd63a  test    r8d, r8d
0x1800bd63d  jmp     short loc_1800BD5D9
0x1800bd63f  test    r8d, r8d
0x1800bd642  jz      short loc_1800BD65F
0x1800bd644  mov     rcx, rsi; hdc
0x1800bd647  call    cs:__imp_CloseFigure
0x1800bd64e  nop     dword ptr [rax+rax+00h]
0x1800bd653  test    eax, eax
0x1800bd655  jz      short loc_1800BD65F
0x1800bd657  mov     r8d, r12d
0x1800bd65a  jmp     loc_1800BD569
0x1800bd65f  xor     r8d, r8d
0x1800bd662  jmp     loc_1800BD569
```
