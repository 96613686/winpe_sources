# gpCopyImage(uchar *,long,uchar const *,long,tagRECT const *,tagRECT const *,long)

- ea: `0x18007cab4`
- end: `0x18007cb55`
- name: `?gpCopyImage@@YAJPEAEJPEBEJPEBUtagRECT@@2J@Z`
- size: `161`
- prototype: `int(unsigned __int8 *, int, const unsigned __int8 *, int, const struct tagRECT *, const struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007b1c4`

## callees

- `0x180075de8`
- `0x180075e50`
- `0x18007cab4`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x18007cb3f`
- `MFPlat!MFCopyImage` at `0x18007cb3f`

## string_xrefs

- `0x18007caea`: `gpCopyImage`

## pseudocode

```c
HRESULT __fastcall gpCopyImage(
        unsigned __int8 *a1,
        LONG a2,
        const unsigned __int8 *a3,
        LONG a4,
        const struct tagRECT *a5,
        const struct tagRECT *a6)
{
  int v9; // edx
  LONG top; // ecx
  signed int dwLines; // r9d

  v9 = a6->right - a6->left;
  if ( v9 < 0 )
    return XvpOriginateError<21>("gpCopyImage", 2147942487LL, L"Invalid source width");
  top = a6->top;
  dwLines = a6->bottom - top;
  if ( dwLines >= 0 )
    return MFCopyImage(&a1[2 * a5->left + a5->top * a2], a2, &a3[2 * a6->left + a4 * top], a4, 2 * v9, dwLines);
  else
    return XvpOriginateError<22>();
}

```

## disassembly

```asm
0x18007cab4  mov     [rsp+arg_0], rbx
0x18007cab9  mov     [rsp+arg_8], rsi
0x18007cabe  push    rdi
0x18007cabf  sub     rsp, 30h
0x18007cac3  mov     rax, [rsp+38h+arg_28]
0x18007cac8  mov     ebx, edx
0x18007caca  mov     r11d, r9d
0x18007cacd  mov     rdi, r8
0x18007cad0  mov     rsi, rcx
0x18007cad3  mov     edx, [rax+8]
0x18007cad6  mov     r10d, [rax]
0x18007cad9  sub     edx, r10d
0x18007cadc  jns     short loc_18007CAF8
0x18007cade  lea     r8, aInvalidSourceW; "Invalid source width"
0x18007cae5  mov     edx, 80070057h
0x18007caea  lea     rcx, aGpcopyimage; "gpCopyImage"
0x18007caf1  call    ??$XvpOriginateError@$0BF@@@YAJQEADJAEAY0BF@$$CBG@Z; XvpOriginateError<21>(char * const,long,ushort const (&)[21])
0x18007caf6  jmp     short loc_18007CB45
0x18007caf8  mov     r9d, [rax+0Ch]
0x18007cafc  mov     ecx, [rax+4]
0x18007caff  sub     r9d, ecx
0x18007cb02  jns     short loc_18007CB0B
0x18007cb04  call    ??$XvpOriginateError@$0BG@@@YAJQEADJAEAY0BG@$$CBG@Z; XvpOriginateError<22>(char * const,long,ushort const (&)[22])
0x18007cb09  jmp     short loc_18007CB45
0x18007cb0b  imul    ecx, r11d
0x18007cb0f  add     edx, edx
0x18007cb11  mov     [rsp+38h+dwLines], r9d; dwLines
0x18007cb16  mov     r9d, r11d; lSrcStride
0x18007cb19  mov     [rsp+38h+dwWidthInBytes], edx; dwWidthInBytes
0x18007cb1d  mov     edx, ebx; lDestStride
0x18007cb1f  lea     eax, [rcx+r10*2]
0x18007cb23  mov     ecx, ebx
0x18007cb25  movsxd  r8, eax
0x18007cb28  mov     rax, [rsp+38h+arg_20]
0x18007cb2d  add     r8, rdi; pSrc
0x18007cb30  imul    ecx, [rax+4]
0x18007cb34  mov     eax, [rax]
0x18007cb36  lea     ecx, [rcx+rax*2]
0x18007cb39  movsxd  rcx, ecx
0x18007cb3c  add     rcx, rsi; pDest
0x18007cb3f  call    cs:__imp_MFCopyImage
0x18007cb45  mov     rbx, [rsp+38h+arg_0]
0x18007cb4a  mov     rsi, [rsp+38h+arg_8]
0x18007cb4f  add     rsp, 30h
0x18007cb53  pop     rdi
0x18007cb54  retn
```
