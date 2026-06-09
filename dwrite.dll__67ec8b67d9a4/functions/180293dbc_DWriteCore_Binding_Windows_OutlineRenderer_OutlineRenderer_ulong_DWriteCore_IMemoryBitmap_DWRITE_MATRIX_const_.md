# DWriteCore::Binding::Windows::OutlineRenderer::OutlineRenderer(ulong,DWriteCore::IMemoryBitmap *,DWRITE_MATRIX const &,bool)

- ea: `0x180293dbc`
- end: `0x180293ede`
- name: `??0OutlineRenderer@Windows@Binding@DWriteCore@@QEAA@KPEAUIMemoryBitmap@3@AEBUDWRITE_MATRIX@@_N@Z`
- size: `290`
- prototype: `__int64 __usercall@<rax>(DWriteCore::Binding::Windows::OutlineRenderer *__hidden this@<rcx>, unsigned int@<edx>, struct DWriteCore::IMemoryBitmap *@<r8>, const struct DWRITE_MATRIX *@<r9>, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18028e500`

## callees

- `0x180212490`
- `0x180293dbc`
- `0x1802941ec`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180293e49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180293e49`
- `ext-ms-win-gdi-draw-l1-1-0!GetWorldTransform` at `0x180293e57`
- `ext-ms-win-gdi-draw-l1-1-0!GetWorldTransform` at `0x180293e57`
- `ext-ms-win-gdi-draw-l1-1-0!SetWorldTransform` at `0x180293eba`
- `ext-ms-win-gdi-draw-l1-1-0!SetWorldTransform` at `0x180293eba`
- `ext-ms-win-gdi-path-l1-1-0!BeginPath` at `0x180293e61`
- `ext-ms-win-gdi-path-l1-1-0!BeginPath` at `0x180293e61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DWriteCore::Binding::Windows::OutlineRenderer *__fastcall DWriteCore::Binding::Windows::OutlineRenderer::OutlineRenderer(
        DWriteCore::Binding::Windows::OutlineRenderer *this,
        int a2,
        struct DWriteCore::IMemoryBitmap *a3,
        const struct DWRITE_MATRIX *a4,
        bool a5)
{
  BOOL v9; // eax
  __int64 v10; // rdx
  XFORM xf; // [rsp+28h] [rbp-40h] BYREF

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &DWriteCore::Binding::Windows::OutlineRenderer::`vftable';
  *((_QWORD *)this + 2) = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct DWriteCore::IMemoryBitmap *))(*(_QWORD *)a3 + 8LL))(a3);
  *((_QWORD *)this + 3) = (*(__int64 (__fastcall **)(struct DWriteCore::IMemoryBitmap *))(*(_QWORD *)a3 + 24LL))(a3);
  *((_DWORD *)this + 8) = a2 & 0xFFFFFF;
  *((_BYTE *)this + 60) = 0;
  *((_BYTE *)this + 61) = a5;
  *((_OWORD *)this + 4) = 0;
  *((_DWORD *)this + 20) = 0;
  SetLastError(0);
  GetWorldTransform(*((HDC *)this + 3), (LPXFORM)((char *)this + 36));
  v9 = BeginPath(*((HDC *)this + 3));
  DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(this, v9);
  *((_BYTE *)this + 60) = 1;
  v10 = 0;
  do
  {
    *(&xf.eM11 + (int)v10) = *((float *)a4 + v10) * 0.00048828125;
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (int)v10 < 4 );
  xf.eDx = *((FLOAT *)a4 + 4);
  xf.eDy = *((FLOAT *)a4 + 5);
  SetWorldTransform(*((HDC *)this + 3), &xf);
  return this;
}

```

## disassembly

```asm
0x180293dbc  mov     [rsp+arg_8], rbx
0x180293dc1  push    rbp
0x180293dc2  push    rsi
0x180293dc3  push    rdi
0x180293dc4  sub     rsp, 50h
0x180293dc8  mov     rax, cs:__security_cookie
0x180293dcf  xor     rax, rsp
0x180293dd2  mov     [rsp+68h+var_28], rax
0x180293dd7  mov     rsi, r9
0x180293dda  mov     rdi, r8
0x180293ddd  mov     ebp, edx
0x180293ddf  mov     rbx, rcx
0x180293de2  mov     [rsp+68h+var_48], rcx
0x180293de7  xor     eax, eax
0x180293de9  mov     [rcx+8], eax
0x180293dec  lea     rax, ??_7OutlineRenderer@Windows@Binding@DWriteCore@@6B@; const DWriteCore::Binding::Windows::OutlineRenderer::`vftable'
0x180293df3  mov     [rcx], rax
0x180293df6  mov     [rcx+10h], r8
0x180293dfa  test    r8, r8
0x180293dfd  jz      short loc_180293E0F
0x180293dff  mov     rax, [r8]
0x180293e02  mov     rcx, r8
0x180293e05  mov     rax, [rax+8]
0x180293e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293e0e  nop
0x180293e0f  mov     rax, [rdi]
0x180293e12  mov     rcx, rdi
0x180293e15  mov     rax, [rax+18h]
0x180293e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293e1e  mov     [rbx+18h], rax
0x180293e22  and     ebp, 0FFFFFFh
0x180293e28  mov     [rbx+20h], ebp
0x180293e2b  mov     byte ptr [rbx+3Ch], 0
0x180293e2f  mov     al, [rsp+68h+arg_20]
0x180293e36  mov     [rbx+3Dh], al
0x180293e39  xorps   xmm0, xmm0
0x180293e3c  movups  xmmword ptr [rbx+40h], xmm0
0x180293e40  mov     dword ptr [rbx+50h], 0
0x180293e47  xor     ecx, ecx; dwErrCode
0x180293e49  call    cs:__imp_SetLastError
0x180293e4f  lea     rdx, [rbx+24h]; lpxf
0x180293e53  mov     rcx, [rbx+18h]; hdc
0x180293e57  call    cs:__imp_GetWorldTransform
0x180293e5d  mov     rcx, [rbx+18h]; hdc
0x180293e61  call    cs:__imp_BeginPath
0x180293e67  mov     edx, eax; int
0x180293e69  mov     rcx, rbx; this
0x180293e6c  call    ?CheckBoolReturn@OutlineRenderer@Windows@Binding@DWriteCore@@AEAAXH@Z; DWriteCore::Binding::Windows::OutlineRenderer::CheckBoolReturn(int)
0x180293e71  mov     byte ptr [rbx+3Ch], 1
0x180293e75  xor     edx, edx
0x180293e77  movss   xmm0, dword ptr [rsi+rdx*4]
0x180293e7c  mulss   xmm0, cs:__real@3a000000
0x180293e84  lea     eax, ds:0[rdx*4]
0x180293e8b  movsxd  rcx, eax
0x180293e8e  movss   [rsp+rcx+68h+xf.eM11], xmm0
0x180293e94  inc     edx
0x180293e96  cmp     edx, 4
0x180293e99  jl      short loc_180293E77
0x180293e9b  movss   xmm0, dword ptr [rsi+10h]
0x180293ea0  movss   [rsp+68h+xf.eDx], xmm0
0x180293ea6  movss   xmm1, dword ptr [rsi+14h]
0x180293eab  movss   [rsp+68h+xf.eDy], xmm1
0x180293eb1  lea     rdx, [rsp+68h+xf]; lpxf
0x180293eb6  mov     rcx, [rbx+18h]; hdc
0x180293eba  call    cs:__imp_SetWorldTransform
0x180293ec0  nop
0x180293ec1  mov     rax, rbx
0x180293ec4  mov     rcx, [rsp+68h+var_28]
0x180293ec9  xor     rcx, rsp; StackCookie
0x180293ecc  call    __security_check_cookie
0x180293ed1  mov     rbx, [rsp+68h+arg_8]
0x180293ed6  add     rsp, 50h
0x180293eda  pop     rdi
0x180293edb  pop     rsi
0x180293edc  pop     rbp
0x180293edd  retn
```
