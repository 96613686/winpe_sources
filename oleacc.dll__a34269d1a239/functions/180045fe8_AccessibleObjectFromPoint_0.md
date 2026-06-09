# AccessibleObjectFromPoint_0

- ea: `0x180045fe8`
- end: `0x18004617c`
- name: `AccessibleObjectFromPoint_0`
- size: `404`
- prototype: `HRESULT __stdcall(POINT ptScreen, IAccessible **ppacc, VARIANT *pvarChild)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800466a0`

## callees

- `0x180007b90`
- `0x1800151d4`
- `0x18001dbbc`
- `0x180045fe8`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180046082`
- `OLEAUT32!__imp_VariantInit` at `0x180046082`
- `OLEAUT32!__imp_VariantClear` at `0x180046112`
- `OLEAUT32!__imp_VariantClear` at `0x180046112`
- `OLEAUT32!__imp_VariantCopy` at `0x180046147`
- `OLEAUT32!__imp_VariantCopy` at `0x180046147`

## pseudocode

```c
HRESULT __stdcall AccessibleObjectFromPoint_0(POINT ptScreen, IAccessible **ppacc, VARIANT *pvarChild)
{
  unsigned int x; // ebx
  HWND v6; // rax
  HWND Ancestor; // rax
  int v9; // edi
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  unsigned int y; // [rsp+84h] [rbp+34h]
  void *ppvObject; // [rsp+88h] [rbp+38h] BYREF

  y = ptScreen.y;
  ppvObject = 0;
  x = ptScreen.x;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !ppacc )
    return -2147024809;
  if ( !pvarChild )
    return -2147024809;
  *ppacc = 0;
  pvarChild->vt = 0;
  v6 = MyWindowFromPhysicalPoint(ptScreen);
  if ( !v6 )
    return -2147024809;
  Ancestor = MyGetAncestor(v6, 2u);
  if ( !Ancestor )
    return -2147467259;
  v9 = AccessibleObjectFromWindow_0(Ancestor, 0, &IID_IAccessible, &ppvObject);
  while ( v9 >= 0 )
  {
    VariantInit(&pvarg);
    v9 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)ppvObject + 192LL))(
           ppvObject,
           x,
           y,
           &pvarg);
    if ( v9 < 0 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      return v9;
    }
    if ( pvarg.vt == 9 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      if ( !pvarg.llVal )
        return -2147467261;
      ppvObject = 0;
      v9 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, void **))pvarg.llVal)(
             pvarg.llVal,
             &IID_IAccessible,
             &ppvObject);
      (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 16))(pvarg.llVal);
    }
    else
    {
      if ( pvarg.vt == 3 || !pvarg.vt )
      {
        *ppacc = (IAccessible *)ppvObject;
        return VariantCopy(pvarChild, &pvarg);
      }
      VariantClear(&pvarg);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      v9 = -2147024809;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180045fe8  mov     [rsp-28h+arg_10], rbx
0x180045fed  mov     [rsp-28h+arg_0], rcx
0x180045ff2  push    rbp
0x180045ff3  push    rsi
0x180045ff4  push    rdi
0x180045ff5  push    r14
0x180045ff7  push    r15
0x180045ff9  mov     rbp, rsp
0x180045ffc  sub     rsp, 50h
0x180046000  xor     r15d, r15d
0x180046003  xor     eax, eax
0x180046005  mov     [rbp+ppvObject], r15
0x180046009  xorps   xmm0, xmm0
0x18004600c  mov     qword ptr [rbp+pvarg+10h], rax
0x180046010  mov     rsi, r8
0x180046013  mov     r14, rdx
0x180046016  mov     rbx, rcx
0x180046019  movups  xmmword ptr [rbp+pvarg], xmm0
0x18004601d  test    rdx, rdx
0x180046020  jz      loc_180046163
0x180046026  test    r8, r8
0x180046029  jz      loc_180046163
0x18004602f  mov     [rdx], r15
0x180046032  mov     [r8], r15w
0x180046036  call    ?MyWindowFromPhysicalPoint@@YAPEAUHWND__@@UtagPOINT@@@Z; MyWindowFromPhysicalPoint(tagPOINT)
0x18004603b  test    rax, rax
0x18004603e  jz      loc_180046163
0x180046044  lea     edx, [r15+2]; unsigned int
0x180046048  mov     rcx, rax; hWnd
0x18004604b  call    ?MyGetAncestor@@YAPEAUHWND__@@PEAU1@I@Z; MyGetAncestor(HWND__ *,uint)
0x180046050  test    rax, rax
0x180046053  jnz     short loc_18004605F
0x180046055  mov     eax, 80004005h
0x18004605a  jmp     loc_180046168
0x18004605f  lea     r9, [rbp+ppvObject]; ppvObject
0x180046063  xor     edx, edx; dwId
0x180046065  lea     r8, IID_IAccessible; riid
0x18004606c  mov     rcx, rax; hwnd
0x18004606f  call    AccessibleObjectFromWindow_0
0x180046074  mov     edi, eax
0x180046076  test    edi, edi
0x180046078  js      loc_18004615F
0x18004607e  lea     rcx, [rbp+pvarg]; pvarg
0x180046082  call    cs:__imp_VariantInit
0x180046088  mov     rcx, [rbp+ppvObject]
0x18004608c  lea     r9, [rbp+pvarg]
0x180046090  mov     r8d, dword ptr [rbp+arg_0+4]
0x180046094  mov     edx, ebx
0x180046096  mov     rax, [rcx]
0x180046099  mov     rax, [rax+0C0h]
0x1800460a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460a5  mov     edi, eax
0x1800460a7  test    eax, eax
0x1800460a9  js      loc_18004614F
0x1800460af  movzx   eax, word ptr [rbp+pvarg]
0x1800460b3  cmp     ax, 9
0x1800460b7  jnz     short loc_180046103
0x1800460b9  mov     rcx, [rbp+ppvObject]
0x1800460bd  mov     rax, [rcx]
0x1800460c0  mov     rax, [rax+10h]
0x1800460c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460c9  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800460cd  test    rcx, rcx
0x1800460d0  jz      short loc_180046132
0x1800460d2  mov     [rbp+ppvObject], r15
0x1800460d6  lea     r8, [rbp+ppvObject]
0x1800460da  mov     rax, [rcx]
0x1800460dd  lea     rdx, IID_IAccessible
0x1800460e4  mov     rax, [rax]
0x1800460e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460ec  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800460f0  mov     edi, eax
0x1800460f2  mov     rax, [rcx]
0x1800460f5  mov     rax, [rax+10h]
0x1800460f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460fe  jmp     loc_180046076
0x180046103  cmp     ax, 3
0x180046107  jz      short loc_180046139
0x180046109  test    ax, ax
0x18004610c  jz      short loc_180046139
0x18004610e  lea     rcx, [rbp+pvarg]; pvarg
0x180046112  call    cs:__imp_VariantClear
0x180046118  mov     rcx, [rbp+ppvObject]
0x18004611c  mov     rax, [rcx]
0x18004611f  mov     rax, [rax+10h]
0x180046123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046128  mov     edi, 80070057h
0x18004612d  jmp     loc_180046076
0x180046132  mov     eax, 80004003h
0x180046137  jmp     short loc_180046168
0x180046139  mov     rax, [rbp+ppvObject]
0x18004613d  lea     rdx, [rbp+pvarg]; pvargSrc
0x180046141  mov     rcx, rsi; pvargDest
0x180046144  mov     [r14], rax
0x180046147  call    cs:__imp_VariantCopy
0x18004614d  jmp     short loc_180046168
0x18004614f  mov     rcx, [rbp+ppvObject]
0x180046153  mov     rax, [rcx]
0x180046156  mov     rax, [rax+10h]
0x18004615a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004615f  mov     eax, edi
0x180046161  jmp     short loc_180046168
0x180046163  mov     eax, 80070057h
0x180046168  mov     rbx, [rsp+50h+arg_10]
0x180046170  add     rsp, 50h
0x180046174  pop     r15
0x180046176  pop     r14
0x180046178  pop     rdi
0x180046179  pop     rsi
0x18004617a  pop     rbp
0x18004617b  retn
```
