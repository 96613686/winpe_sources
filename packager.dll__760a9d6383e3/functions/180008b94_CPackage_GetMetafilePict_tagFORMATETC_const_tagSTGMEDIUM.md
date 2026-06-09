# CPackage::GetMetafilePict(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x180008b94`
- end: `0x180008c83`
- name: `?GetMetafilePict@CPackage@@IEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(CPackage *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049f0`

## callees

- `0x180007680`
- `0x180008b94`
- `0x18000a474`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008be0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008be0`
- `USER32!SetRect` at `0x180008c2f`
- `USER32!SetRect` at `0x180008c2f`
- `GDI32!CloseMetaFile` at `0x180008c56`
- `GDI32!CloseMetaFile` at `0x180008c56`
- `GDI32!CreateMetaFileW` at `0x180008bf4`
- `GDI32!CreateMetaFileW` at `0x180008bf4`

## pseudocode

```c
__int64 __fastcall CPackage::GetMetafilePict(CPackage *this, const struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  bool v3; // zf
  __int64 v7; // rbp
  HBITMAP v8; // rax
  HBITMAP v9; // rbx
  HDC MetaFileW; // rax
  HDC v11; // rdi
  struct tagRECT rc; // [rsp+30h] [rbp-38h] BYREF

  v3 = (a2->tymed & 0x20) == 0;
  rc = 0;
  if ( v3 )
    return 2147745892LL;
  v7 = *((_QWORD *)this + 12);
  a3->tymed = 32;
  v8 = (HBITMAP)GlobalAlloc(0x40u, 0x18u);
  a3->hBitmap = v8;
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  MetaFileW = CreateMetaFileW(0);
  v11 = MetaFileW;
  if ( !MetaFileW )
    return 2147942414LL;
  CPackage::_DrawIconToDC(this, MetaFileW, *((struct _IC **)this + 12), 1);
  SetRect(&rc, 0, 0, *(_DWORD *)(v7 + 1060), *(_DWORD *)(v7 + 1064));
  ConvertClientRectToMM(&rc);
  *(_DWORD *)v9 = 8;
  *(_DWORD *)(v9 + 1) = rc.right;
  *(_DWORD *)(v9 + 2) = rc.bottom;
  *((_QWORD *)v9 + 2) = CloseMetaFile(v11);
  return 0;
}

```

## disassembly

```asm
0x180008b94  mov     [rsp+arg_8], rbx
0x180008b99  push    rbp
0x180008b9a  push    rsi
0x180008b9b  push    rdi
0x180008b9c  sub     rsp, 50h
0x180008ba0  mov     rax, cs:__security_cookie
0x180008ba7  xor     rax, rsp
0x180008baa  mov     [rsp+68h+var_28], rax
0x180008baf  test    byte ptr [rdx+18h], 20h
0x180008bb3  xorps   xmm0, xmm0
0x180008bb6  movups  xmmword ptr [rsp+68h+rc.left], xmm0
0x180008bbb  mov     rdi, r8
0x180008bbe  mov     rsi, rcx
0x180008bc1  jnz     short loc_180008BCD
0x180008bc3  mov     eax, 80040064h
0x180008bc8  jmp     loc_180008C69
0x180008bcd  mov     rbp, [rcx+60h]
0x180008bd1  mov     edx, 18h; dwBytes
0x180008bd6  mov     dword ptr [r8], 20h ; ' '
0x180008bdd  lea     ecx, [rdx+28h]; uFlags
0x180008be0  call    cs:__imp_GlobalAlloc
0x180008be6  mov     [rdi+8], rax
0x180008bea  mov     rbx, rax
0x180008bed  test    rax, rax
0x180008bf0  jz      short loc_180008C64
0x180008bf2  xor     ecx, ecx; pszFile
0x180008bf4  call    cs:__imp_CreateMetaFileW
0x180008bfa  mov     rdi, rax
0x180008bfd  test    rax, rax
0x180008c00  jz      short loc_180008C64
0x180008c02  mov     r8, [rsi+60h]; struct _IC *
0x180008c06  mov     r9b, 1; bool
0x180008c09  mov     rdx, rax; HDC
0x180008c0c  mov     rcx, rsi; this
0x180008c0f  call    ?_DrawIconToDC@CPackage@@IEAAXPEAUHDC__@@PEAU_IC@@_N@Z; CPackage::_DrawIconToDC(HDC__ *,_IC *,bool)
0x180008c14  mov     ecx, [rbp+428h]
0x180008c1a  xor     r8d, r8d; yTop
0x180008c1d  mov     r9d, [rbp+424h]; xRight
0x180008c24  xor     edx, edx; xLeft
0x180008c26  mov     [rsp+68h+yBottom], ecx; yBottom
0x180008c2a  lea     rcx, [rsp+68h+rc]; lprc
0x180008c2f  call    cs:__imp_SetRect
0x180008c35  lea     rcx, [rsp+68h+rc]; struct tagRECT *
0x180008c3a  call    ?ConvertClientRectToMM@@YAXPEAUtagRECT@@@Z; ConvertClientRectToMM(tagRECT *)
0x180008c3f  mov     dword ptr [rbx], 8
0x180008c45  mov     rcx, rdi; hdc
0x180008c48  mov     eax, [rsp+68h+rc.right]
0x180008c4c  mov     [rbx+4], eax
0x180008c4f  mov     eax, [rsp+68h+rc.bottom]
0x180008c53  mov     [rbx+8], eax
0x180008c56  call    cs:__imp_CloseMetaFile
0x180008c5c  mov     [rbx+10h], rax
0x180008c60  xor     eax, eax
0x180008c62  jmp     short loc_180008C69
0x180008c64  mov     eax, 8007000Eh
0x180008c69  mov     rcx, [rsp+68h+var_28]
0x180008c6e  xor     rcx, rsp; StackCookie
0x180008c71  call    __security_check_cookie
0x180008c76  mov     rbx, [rsp+68h+arg_8]
0x180008c7b  add     rsp, 50h
0x180008c7f  pop     rdi
0x180008c80  pop     rsi
0x180008c81  pop     rbp
0x180008c82  retn
```
