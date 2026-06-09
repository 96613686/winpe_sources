# DrawPlusMinus

- ea: `0x18011ea4c`
- end: `0x18011ed17`
- name: `DrawPlusMinus`
- size: `715`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int x@<edx>, int y@<r8d>, __int64, int, HGDIOBJ h, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180020498`
- `0x18002137c`
- `0x18014de0c`

## callees

- `0x18011ea4c`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18011eaba`
- `GDI32!CreateSolidBrush` at `0x18011eae6`
- `GDI32!CreateSolidBrush` at `0x18011eaba`
- `GDI32!CreateSolidBrush` at `0x18011eae6`
- `GDI32!DeleteObject` at `0x18011ece9`
- `GDI32!DeleteObject` at `0x18011ecf9`
- `GDI32!DeleteObject` at `0x18011ece9`
- `GDI32!DeleteObject` at `0x18011ecf9`
- `GDI32!PatBlt` at `0x18011eb56`
- `GDI32!PatBlt` at `0x18011eb94`
- `GDI32!PatBlt` at `0x18011ebbe`
- `GDI32!PatBlt` at `0x18011ebe7`
- `GDI32!PatBlt` at `0x18011ec10`
- `GDI32!PatBlt` at `0x18011ec53`
- `GDI32!PatBlt` at `0x18011ec78`
- `GDI32!PatBlt` at `0x18011eca9`
- `GDI32!PatBlt` at `0x18011ecc8`
- `GDI32!PatBlt` at `0x18011eb56`
- `GDI32!PatBlt` at `0x18011eb94`
- `GDI32!PatBlt` at `0x18011ebbe`
- `GDI32!PatBlt` at `0x18011ebe7`
- `GDI32!PatBlt` at `0x18011ec10`
- `GDI32!PatBlt` at `0x18011ec53`
- `GDI32!PatBlt` at `0x18011ec78`
- `GDI32!PatBlt` at `0x18011eca9`
- `GDI32!PatBlt` at `0x18011ecc8`
- `GDI32!SelectObject` at `0x18011eb0a`
- `GDI32!SelectObject` at `0x18011eb62`
- `GDI32!SelectObject` at `0x18011ec25`
- `GDI32!SelectObject` at `0x18011ecd6`
- `GDI32!SelectObject` at `0x18011eb0a`
- `GDI32!SelectObject` at `0x18011eb62`
- `GDI32!SelectObject` at `0x18011ec25`
- `GDI32!SelectObject` at `0x18011ecd6`
- `USER32!GetSysColor` at `0x18011eab2`
- `USER32!GetSysColor` at `0x18011eade`
- `USER32!GetSysColor` at `0x18011eab2`
- `USER32!GetSysColor` at `0x18011eade`

## pseudocode

```c
unsigned int __fastcall DrawPlusMinus(HDC hdc, int x, int y, int a4, HBRUSH a5, HBRUSH ya, HBRUSH h, int a8)
{
  HBRUSH SolidBrush; // r12
  int v12; // ebx
  int v13; // ebp
  COLORREF SysColor; // eax
  HBRUSH v15; // rsi
  COLORREF v16; // eax
  HBRUSH v17; // r13
  unsigned int result; // eax
  int v19; // [rsp+30h] [rbp-48h]
  HGDIOBJ v20; // [rsp+38h] [rbp-40h]
  int xa; // [rsp+88h] [rbp+10h]
  int v22; // [rsp+90h] [rbp+18h]
  int yb; // [rsp+A8h] [rbp+30h]
  int ha; // [rsp+B0h] [rbp+38h]

  SolidBrush = h;
  v22 = 0;
  v19 = 0;
  v12 = 7 * a4 / 10;
  v13 = 2 * v12 + 1;
  if ( !h )
  {
    SysColor = GetSysColor(5);
    SolidBrush = CreateSolidBrush(SysColor);
    v22 = 1;
  }
  v15 = ya;
  if ( ya )
  {
    v17 = a5;
  }
  else
  {
    v16 = GetSysColor(8);
    v15 = CreateSolidBrush(v16);
    v19 = 1;
    v17 = v15;
  }
  v20 = SelectObject(hdc, SolidBrush);
  yb = y - a4;
  xa = x - a4;
  ha = 2 * a4;
  PatBlt(hdc, x - a4, y - a4, 2 * a4, 2 * a4, 0xF00021u);
  SelectObject(hdc, v17);
  if ( v12 >= 5 )
  {
    PatBlt(hdc, x - v12, y - 1, v13, 3, 0xF00021u);
    if ( a8 )
      PatBlt(hdc, x - 1, y - v12, 3, 2 * v12 + 1, 0xF00021u);
    --v12;
    v13 -= 2;
  }
  PatBlt(hdc, x - v12, y, v13, 1, 0xF00021u);
  if ( a8 )
    PatBlt(hdc, x, y - v12, 1, v13, 0xF00021u);
  SelectObject(hdc, v15);
  PatBlt(hdc, xa, yb, ha + 1, 1, 0xF00021u);
  PatBlt(hdc, xa, yb, 1, ha + 1, 0xF00021u);
  PatBlt(hdc, xa, y + a4, ha + 1, 1, 0xF00021u);
  PatBlt(hdc, x + a4, yb, 1, ha + 1, 0xF00021u);
  result = (unsigned int)SelectObject(hdc, v20);
  if ( v22 )
    result = DeleteObject(SolidBrush);
  if ( v19 )
    return DeleteObject(v15);
  return result;
}

```

## disassembly

```asm
0x18011ea4c  mov     [rsp+arg_0], rbx
0x18011ea51  mov     [rsp+arg_18], r9d
0x18011ea56  push    rbp
0x18011ea57  push    rsi
0x18011ea58  push    rdi
0x18011ea59  push    r12
0x18011ea5b  push    r13
0x18011ea5d  push    r14
0x18011ea5f  push    r15
0x18011ea61  sub     rsp, 40h
0x18011ea65  mov     r12, [rsp+78h+h]
0x18011ea6d  mov     eax, 66666667h
0x18011ea72  imul    r10d, r9d, 7
0x18011ea76  mov     r15d, edx
0x18011ea79  mov     r14d, r8d
0x18011ea7c  mov     [rsp+78h+arg_10], 0
0x18011ea87  mov     rdi, rcx
0x18011ea8a  mov     [rsp+78h+var_48], 0
0x18011ea92  imul    r10d
0x18011ea95  mov     ebx, edx
0x18011ea97  sar     ebx, 2
0x18011ea9a  mov     eax, ebx
0x18011ea9c  shr     eax, 1Fh
0x18011ea9f  add     ebx, eax
0x18011eaa1  lea     ebp, ds:1[rbx*2]
0x18011eaa8  test    r12, r12
0x18011eaab  jnz     short loc_18011EACE
0x18011eaad  lea     ecx, [r12+5]; nIndex
0x18011eab2  call    cs:__imp_GetSysColor
0x18011eab8  mov     ecx, eax; color
0x18011eaba  call    cs:__imp_CreateSolidBrush
0x18011eac0  mov     r12, rax
0x18011eac3  mov     [rsp+78h+arg_10], 1
0x18011eace  mov     rsi, [rsp+78h+y]
0x18011ead6  test    rsi, rsi
0x18011ead9  jnz     short loc_18011EAFC
0x18011eadb  lea     ecx, [rsi+8]; nIndex
0x18011eade  call    cs:__imp_GetSysColor
0x18011eae4  mov     ecx, eax; color
0x18011eae6  call    cs:__imp_CreateSolidBrush
0x18011eaec  mov     rsi, rax
0x18011eaef  mov     [rsp+78h+var_48], 1
0x18011eaf7  mov     r13, rax
0x18011eafa  jmp     short loc_18011EB04
0x18011eafc  mov     r13, [rsp+78h+arg_20]
0x18011eb04  mov     rdx, r12; h
0x18011eb07  mov     rcx, rdi; hdc
0x18011eb0a  call    cs:__imp_SelectObject
0x18011eb10  mov     ecx, r14d
0x18011eb13  mov     [rsp+78h+rop], 0F00021h; rop
0x18011eb1b  mov     [rsp+78h+var_40], rax
0x18011eb20  mov     edx, r15d
0x18011eb23  mov     eax, [rsp+78h+arg_18]
0x18011eb2a  sub     ecx, eax
0x18011eb2c  mov     dword ptr [rsp+78h+y], ecx
0x18011eb33  sub     edx, eax; x
0x18011eb35  mov     [rsp+78h+x], edx
0x18011eb3c  lea     r8d, [rax+rax]
0x18011eb40  mov     dword ptr [rsp+78h+h], r8d
0x18011eb48  mov     r9d, r8d; w
0x18011eb4b  mov     [rsp+78h+var_58], r8d; h
0x18011eb50  mov     r8d, ecx; y
0x18011eb53  mov     rcx, rdi; hdc
0x18011eb56  call    cs:__imp_PatBlt
0x18011eb5c  mov     rdx, r13; h
0x18011eb5f  mov     rcx, rdi; hdc
0x18011eb62  call    cs:__imp_SelectObject
0x18011eb68  mov     r13d, [rsp+78h+arg_38]
0x18011eb70  cmp     ebx, 5
0x18011eb73  jl      short loc_18011EBC9
0x18011eb75  mov     edx, r15d
0x18011eb78  mov     [rsp+78h+rop], 0F00021h; rop
0x18011eb80  sub     edx, ebx; x
0x18011eb82  mov     [rsp+78h+var_58], 3; h
0x18011eb8a  lea     r8d, [r14-1]; y
0x18011eb8e  mov     r9d, ebp; w
0x18011eb91  mov     rcx, rdi; hdc
0x18011eb94  call    cs:__imp_PatBlt
0x18011eb9a  test    r13d, r13d
0x18011eb9d  jz      short loc_18011EBC4
0x18011eb9f  mov     r8d, r14d
0x18011eba2  mov     [rsp+78h+rop], 0F00021h; rop
0x18011ebaa  sub     r8d, ebx; y
0x18011ebad  mov     [rsp+78h+var_58], ebp; h
0x18011ebb1  lea     edx, [r15-1]; x
0x18011ebb5  mov     r9d, 3; w
0x18011ebbb  mov     rcx, rdi; hdc
0x18011ebbe  call    cs:__imp_PatBlt
0x18011ebc4  dec     ebx
0x18011ebc6  add     ebp, 0FFFFFFFEh
0x18011ebc9  mov     edx, r15d
0x18011ebcc  mov     [rsp+78h+rop], 0F00021h; rop
0x18011ebd4  sub     edx, ebx; x
0x18011ebd6  mov     [rsp+78h+var_58], 1; h
0x18011ebde  mov     r9d, ebp; w
0x18011ebe1  mov     r8d, r14d; y
0x18011ebe4  mov     rcx, rdi; hdc
0x18011ebe7  call    cs:__imp_PatBlt
0x18011ebed  test    r13d, r13d
0x18011ebf0  jz      short loc_18011EC16
0x18011ebf2  mov     r8d, r14d
0x18011ebf5  mov     [rsp+78h+rop], 0F00021h; rop
0x18011ebfd  sub     r8d, ebx; y
0x18011ec00  mov     [rsp+78h+var_58], ebp; h
0x18011ec04  mov     r9d, 1; w
0x18011ec0a  mov     edx, r15d; x
0x18011ec0d  mov     rcx, rdi; hdc
0x18011ec10  call    cs:__imp_PatBlt
0x18011ec16  mov     ebx, dword ptr [rsp+78h+h]
0x18011ec1d  mov     rdx, rsi; h
0x18011ec20  mov     rcx, rdi; hdc
0x18011ec23  inc     ebx
0x18011ec25  call    cs:__imp_SelectObject
0x18011ec2b  mov     r13d, dword ptr [rsp+78h+y]
0x18011ec33  mov     r9d, ebx; w
0x18011ec36  mov     edx, [rsp+78h+x]; x
0x18011ec3d  mov     r8d, r13d; y
0x18011ec40  mov     rcx, rdi; hdc
0x18011ec43  mov     [rsp+78h+rop], 0F00021h; rop
0x18011ec4b  mov     [rsp+78h+var_58], 1; h
0x18011ec53  call    cs:__imp_PatBlt
0x18011ec59  mov     edx, [rsp+78h+x]; x
0x18011ec60  mov     r9d, 1; w
0x18011ec66  mov     r8d, r13d; y
0x18011ec69  mov     [rsp+78h+rop], 0F00021h; rop
0x18011ec71  mov     rcx, rdi; hdc
0x18011ec74  mov     [rsp+78h+var_58], ebx; h
0x18011ec78  call    cs:__imp_PatBlt
0x18011ec7e  mov     ebp, [rsp+78h+arg_18]
0x18011ec85  mov     r9d, ebx; w
0x18011ec88  mov     edx, [rsp+78h+x]; x
0x18011ec8f  mov     rcx, rdi; hdc
0x18011ec92  lea     r8d, [r14+rbp]; y
0x18011ec96  mov     r14d, 0F00021h
0x18011ec9c  mov     [rsp+78h+rop], r14d; rop
0x18011eca1  mov     [rsp+78h+var_58], 1; h
0x18011eca9  call    cs:__imp_PatBlt
0x18011ecaf  lea     edx, [r15+rbp]; x
0x18011ecb3  mov     [rsp+78h+rop], r14d; rop
0x18011ecb8  mov     r9d, 1; w
0x18011ecbe  mov     [rsp+78h+var_58], ebx; h
0x18011ecc2  mov     r8d, r13d; y
0x18011ecc5  mov     rcx, rdi; hdc
0x18011ecc8  call    cs:__imp_PatBlt
0x18011ecce  mov     rdx, [rsp+78h+var_40]; h
0x18011ecd3  mov     rcx, rdi; hdc
0x18011ecd6  call    cs:__imp_SelectObject
0x18011ecdc  cmp     [rsp+78h+arg_10], 0
0x18011ece4  jz      short loc_18011ECEF
0x18011ece6  mov     rcx, r12; ho
0x18011ece9  call    cs:__imp_DeleteObject
0x18011ecef  cmp     [rsp+78h+var_48], 0
0x18011ecf4  jz      short loc_18011ECFF
0x18011ecf6  mov     rcx, rsi; ho
0x18011ecf9  call    cs:__imp_DeleteObject
0x18011ecff  mov     rbx, [rsp+78h+arg_0]
0x18011ed07  add     rsp, 40h
0x18011ed0b  pop     r15
0x18011ed0d  pop     r14
0x18011ed0f  pop     r13
0x18011ed11  pop     r12
0x18011ed13  pop     rdi
0x18011ed14  pop     rsi
0x18011ed15  pop     rbp
0x18011ed16  retn
```
