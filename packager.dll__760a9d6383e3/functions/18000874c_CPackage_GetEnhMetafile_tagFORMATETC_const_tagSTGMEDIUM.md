# CPackage::GetEnhMetafile(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x18000874c`
- end: `0x180008823`
- name: `?GetEnhMetafile@CPackage@@IEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(CPackage *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049f0`

## callees

- `0x180007680`
- `0x18000874c`
- `0x18000a474`
- `0x18000cbf0`

## import_xrefs

- `USER32!SetRect` at `0x1800087a8`
- `USER32!SetRect` at `0x1800087a8`
- `GDI32!CloseEnhMetaFile` at `0x1800087ed`
- `GDI32!CloseEnhMetaFile` at `0x1800087ed`
- `GDI32!CreateEnhMetaFileW` at `0x1800087c4`
- `GDI32!CreateEnhMetaFileW` at `0x1800087c4`

## pseudocode

```c
__int64 __fastcall CPackage::GetEnhMetafile(CPackage *this, const struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  __int64 v6; // r9
  HDC v7; // rax
  HDC v8; // rsi
  tagRECT rc; // [rsp+30h] [rbp-28h] BYREF

  if ( (a2->tymed & 0x40) == 0 )
    return 2147745892LL;
  v6 = *((_QWORD *)this + 12);
  rc = 0;
  SetRect(&rc, 0, 0, *(_DWORD *)(v6 + 1060), *(_DWORD *)(v6 + 1064));
  ConvertClientRectToMM(&rc);
  v7 = CreateEnhMetaFileW(0, 0, &rc, 0);
  v8 = v7;
  if ( v7 )
  {
    CPackage::_DrawIconToDC(this, v7, *((struct _IC **)this + 12), 0);
    a3->tymed = 64;
    a3->hBitmap = (HBITMAP)CloseEnhMetaFile(v8);
    return 0;
  }
  else
  {
    a3->tymed = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000874c  mov     [rsp+arg_8], rbx
0x180008751  mov     [rsp+arg_18], rsi
0x180008756  push    rdi
0x180008757  sub     rsp, 50h
0x18000875b  mov     rax, cs:__security_cookie
0x180008762  xor     rax, rsp
0x180008765  mov     [rsp+58h+var_18], rax
0x18000876a  test    byte ptr [rdx+18h], 40h
0x18000876e  mov     rbx, r8
0x180008771  mov     rdi, rcx
0x180008774  jnz     short loc_180008780
0x180008776  mov     eax, 80040064h
0x18000877b  jmp     loc_180008806
0x180008780  mov     r9, [rcx+60h]
0x180008784  xorps   xmm0, xmm0
0x180008787  movups  xmmword ptr [rsp+58h+rc.left], xmm0
0x18000878c  xor     r8d, r8d; yTop
0x18000878f  lea     rcx, [rsp+58h+rc]; lprc
0x180008794  xor     edx, edx; xLeft
0x180008796  mov     eax, [r9+428h]
0x18000879d  mov     r9d, [r9+424h]; xRight
0x1800087a4  mov     [rsp+58h+yBottom], eax; yBottom
0x1800087a8  call    cs:__imp_SetRect
0x1800087ae  lea     rcx, [rsp+58h+rc]; struct tagRECT *
0x1800087b3  call    ?ConvertClientRectToMM@@YAXPEAUtagRECT@@@Z; ConvertClientRectToMM(tagRECT *)
0x1800087b8  xor     r9d, r9d; lpDesc
0x1800087bb  lea     r8, [rsp+58h+rc]; lprc
0x1800087c0  xor     edx, edx; lpFilename
0x1800087c2  xor     ecx, ecx; hdc
0x1800087c4  call    cs:__imp_CreateEnhMetaFileW
0x1800087ca  mov     rsi, rax
0x1800087cd  test    rax, rax
0x1800087d0  jz      short loc_1800087FB
0x1800087d2  mov     r8, [rdi+60h]; struct _IC *
0x1800087d6  xor     r9d, r9d; bool
0x1800087d9  mov     rdx, rax; HDC
0x1800087dc  mov     rcx, rdi; this
0x1800087df  call    ?_DrawIconToDC@CPackage@@IEAAXPEAUHDC__@@PEAU_IC@@_N@Z; CPackage::_DrawIconToDC(HDC__ *,_IC *,bool)
0x1800087e4  mov     rcx, rsi; hdc
0x1800087e7  mov     dword ptr [rbx], 40h ; '@'
0x1800087ed  call    cs:__imp_CloseEnhMetaFile
0x1800087f3  mov     [rbx+8], rax
0x1800087f7  xor     eax, eax
0x1800087f9  jmp     short loc_180008806
0x1800087fb  mov     dword ptr [rbx], 0
0x180008801  mov     eax, 8007000Eh
0x180008806  mov     rcx, [rsp+58h+var_18]
0x18000880b  xor     rcx, rsp; StackCookie
0x18000880e  call    __security_check_cookie
0x180008813  mov     rbx, [rsp+58h+arg_8]
0x180008818  mov     rsi, [rsp+58h+arg_18]
0x18000881d  add     rsp, 50h
0x180008821  pop     rdi
0x180008822  retn
```
