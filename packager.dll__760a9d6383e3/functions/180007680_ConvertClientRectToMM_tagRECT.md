# ConvertClientRectToMM(tagRECT *)

- ea: `0x180007680`
- end: `0x180007744`
- name: `?ConvertClientRectToMM@@YAXPEAUtagRECT@@@Z`
- size: `196`
- prototype: `void __fastcall(struct tagRECT *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000874c`
- `0x180008b94`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800076f2`
- `KERNEL32!MulDiv` at `0x180007707`
- `KERNEL32!MulDiv` at `0x18000771a`
- `KERNEL32!MulDiv` at `0x18000772d`
- `KERNEL32!MulDiv` at `0x1800076f2`
- `KERNEL32!MulDiv` at `0x180007707`
- `KERNEL32!MulDiv` at `0x18000771a`
- `KERNEL32!MulDiv` at `0x18000772d`
- `USER32!ReleaseDC` at `0x1800076e1`
- `USER32!ReleaseDC` at `0x1800076e1`
- `USER32!GetWindowDC` at `0x180007692`
- `USER32!GetWindowDC` at `0x180007692`
- `GDI32!GetDeviceCaps` at `0x1800076a3`
- `GDI32!GetDeviceCaps` at `0x1800076b3`
- `GDI32!GetDeviceCaps` at `0x1800076c3`
- `GDI32!GetDeviceCaps` at `0x1800076d3`
- `GDI32!GetDeviceCaps` at `0x1800076a3`
- `GDI32!GetDeviceCaps` at `0x1800076b3`
- `GDI32!GetDeviceCaps` at `0x1800076c3`
- `GDI32!GetDeviceCaps` at `0x1800076d3`

## pseudocode

```c
void __fastcall ConvertClientRectToMM(struct tagRECT *a1)
{
  HDC WindowDC; // rdi
  int DeviceCaps; // ebx
  int v4; // esi
  int v5; // ebp
  int v6; // r14d
  LONG v7; // eax
  LONG top; // ecx
  LONG v9; // eax
  LONG right; // ecx
  LONG v11; // eax
  LONG bottom; // ecx

  WindowDC = GetWindowDC(0);
  DeviceCaps = GetDeviceCaps(WindowDC, 4);
  v4 = GetDeviceCaps(WindowDC, 6);
  v5 = GetDeviceCaps(WindowDC, 8);
  v6 = GetDeviceCaps(WindowDC, 10);
  ReleaseDC(0, WindowDC);
  DeviceCaps *= 100;
  v7 = MulDiv(a1->left, DeviceCaps, v5);
  top = a1->top;
  a1->left = v7;
  v9 = MulDiv(top, 100 * v4, v6);
  right = a1->right;
  a1->top = v9;
  v11 = MulDiv(right, DeviceCaps, v5);
  bottom = a1->bottom;
  a1->right = v11;
  a1->bottom = MulDiv(bottom, 100 * v4, v6);
}

```

## disassembly

```asm
0x180007680  push    rbx
0x180007682  push    rbp
0x180007683  push    rsi
0x180007684  push    rdi
0x180007685  push    r14
0x180007687  push    r15
0x180007689  sub     rsp, 28h
0x18000768d  mov     r15, rcx
0x180007690  xor     ecx, ecx; hWnd
0x180007692  call    cs:__imp_GetWindowDC
0x180007698  mov     rcx, rax; hdc
0x18000769b  mov     edx, 4; index
0x1800076a0  mov     rdi, rax
0x1800076a3  call    cs:__imp_GetDeviceCaps
0x1800076a9  mov     edx, 6; index
0x1800076ae  mov     rcx, rdi; hdc
0x1800076b1  mov     ebx, eax
0x1800076b3  call    cs:__imp_GetDeviceCaps
0x1800076b9  mov     edx, 8; index
0x1800076be  mov     rcx, rdi; hdc
0x1800076c1  mov     esi, eax
0x1800076c3  call    cs:__imp_GetDeviceCaps
0x1800076c9  mov     edx, 0Ah; index
0x1800076ce  mov     rcx, rdi; hdc
0x1800076d1  mov     ebp, eax
0x1800076d3  call    cs:__imp_GetDeviceCaps
0x1800076d9  mov     rdx, rdi; hDC
0x1800076dc  xor     ecx, ecx; hWnd
0x1800076de  mov     r14d, eax
0x1800076e1  call    cs:__imp_ReleaseDC
0x1800076e7  mov     ecx, [r15]; nNumber
0x1800076ea  mov     r8d, ebp; nDenominator
0x1800076ed  imul    ebx, 64h ; 'd'
0x1800076f0  mov     edx, ebx; nNumerator
0x1800076f2  call    cs:__imp_MulDiv
0x1800076f8  mov     ecx, [r15+4]; nNumber
0x1800076fc  mov     r8d, r14d; nDenominator
0x1800076ff  imul    edi, esi, 64h ; 'd'
0x180007702  mov     [r15], eax
0x180007705  mov     edx, edi; nNumerator
0x180007707  call    cs:__imp_MulDiv
0x18000770d  mov     ecx, [r15+8]; nNumber
0x180007711  mov     r8d, ebp; nDenominator
0x180007714  mov     edx, ebx; nNumerator
0x180007716  mov     [r15+4], eax
0x18000771a  call    cs:__imp_MulDiv
0x180007720  mov     ecx, [r15+0Ch]; nNumber
0x180007724  mov     r8d, r14d; nDenominator
0x180007727  mov     edx, edi; nNumerator
0x180007729  mov     [r15+8], eax
0x18000772d  call    cs:__imp_MulDiv
0x180007733  mov     [r15+0Ch], eax
0x180007737  add     rsp, 28h
0x18000773b  pop     r15
0x18000773d  pop     r14
0x18000773f  pop     rdi
0x180007740  pop     rsi
0x180007741  pop     rbp
0x180007742  pop     rbx
0x180007743  retn
```
