# CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)

- ea: `0x180065198`
- end: `0x1800653de`
- name: `?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z`
- size: `582`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180064e44`
- `0x180066bc4`
- `0x18011d820`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x180065198`
- `0x1800653e4`
- `0x1800d3954`
- `0x1800f7db0`
- `0x180105d40`
- `0x18010673c`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800652c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800652c1`
- `GDI32!DeleteDC` at `0x180065328`
- `GDI32!DeleteDC` at `0x180065328`
- `GDI32!GetDIBits` at `0x18006523b`
- `GDI32!GetDIBits` at `0x18006529e`
- `GDI32!GetDIBits` at `0x18006523b`
- `GDI32!GetDIBits` at `0x18006529e`
- `GDI32!SelectObject` at `0x1800651fd`
- `GDI32!SelectObject` at `0x180065319`
- `GDI32!SelectObject` at `0x1800651fd`
- `GDI32!SelectObject` at `0x180065319`
- `GDI32!CreateCompatibleDC` at `0x1800651df`
- `GDI32!CreateCompatibleDC` at `0x1800651df`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP a1, void *a2, CopyOnWriteBitmap **a3)
{
  unsigned int v6; // ebx
  HDC CompatibleDC; // rax
  HDC v8; // rbp
  HGDIOBJ v9; // r15
  void *lpvBits; // rdi
  LONG biHeight; // r9d
  CopyOnWriteBitmap *v12; // rax
  CopyOnWriteBitmap *v13; // rax
  struct tagBITMAPINFO bmi; // [rsp+40h] [rbp-468h] BYREF

  v6 = 7;
  memset_0(&bmi, 0, 0x428u);
  CompatibleDC = CreateCompatibleDC(0);
  v8 = CompatibleDC;
  if ( CompatibleDC )
  {
    v9 = SelectObject(CompatibleDC, a2);
    bmi.bmiHeader.biSize = 40;
    if ( !GetDIBits(v8, a1, 0, 0, 0, &bmi, 0) || !bmi.bmiHeader.biSizeImage )
      goto LABEL_13;
    lpvBits = (void *)GpMallocEx(bmi.bmiHeader.biSizeImage, 0);
    if ( lpvBits )
    {
      biHeight = -bmi.bmiHeader.biHeight;
      if ( bmi.bmiHeader.biHeight > 0 )
        biHeight = bmi.bmiHeader.biHeight;
      if ( !GetDIBits(v8, a1, 0, biHeight, lpvBits, &bmi, 0) )
      {
        GpFree(lpvBits);
        goto LABEL_13;
      }
      v12 = (CopyOnWriteBitmap *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x108u);
      if ( v12 )
      {
        v13 = CopyOnWriteBitmap::CopyOnWriteBitmap(v12, &bmi, lpvBits, 1);
        *a3 = v13;
        if ( v13 )
        {
          if ( (*(unsigned int (__fastcall **)(CopyOnWriteBitmap *))(*(_QWORD *)v13 + 16LL))(v13) )
          {
            if ( bmi.bmiHeader.biXPelsPerMeter > 0 && bmi.bmiHeader.biYPelsPerMeter > 0 )
              CopyOnWriteBitmap::SetResolution(*a3);
            v6 = 0;
          }
          else
          {
            CopyOnWriteBitmap::Dispose(*a3);
            *a3 = 0;
            v6 = 2;
          }
          goto LABEL_13;
        }
      }
      else
      {
        *a3 = 0;
      }
      GpFree(lpvBits);
    }
    v6 = 3;
LABEL_13:
    SelectObject(v8, v9);
    DeleteDC(v8);
  }
  return v6;
}

```

## disassembly

```asm
0x180065198  mov     [rsp+arg_18], rbx
0x18006519d  push    rbp
0x18006519e  push    rsi
0x18006519f  push    rdi
0x1800651a0  push    r14
0x1800651a2  push    r15
0x1800651a4  sub     rsp, 480h
0x1800651ab  mov     rax, cs:__security_cookie
0x1800651b2  xor     rax, rsp
0x1800651b5  mov     [rsp+4A8h+var_38], rax
0x1800651bd  mov     rsi, r8
0x1800651c0  mov     rdi, rdx
0x1800651c3  mov     r14, rcx
0x1800651c6  xor     edx, edx; Val
0x1800651c8  mov     r8d, 428h; Size
0x1800651ce  lea     rcx, [rsp+4A8h+bmi]; void *
0x1800651d3  mov     ebx, 7
0x1800651d8  call    memset_0
0x1800651dd  xor     ecx, ecx; hdc
0x1800651df  call    cs:__imp_CreateCompatibleDC
0x1800651e6  nop     dword ptr [rax+rax+00h]
0x1800651eb  mov     rbp, rax
0x1800651ee  test    rax, rax
0x1800651f1  jz      loc_180065334
0x1800651f7  mov     rdx, rdi; h
0x1800651fa  mov     rcx, rax; hdc
0x1800651fd  call    cs:__imp_SelectObject
0x180065204  nop     dword ptr [rax+rax+00h]
0x180065209  mov     [rsp+4A8h+usage], 0; usage
0x180065211  xor     r9d, r9d; cLines
0x180065214  mov     r15, rax
0x180065217  mov     [rsp+4A8h+bmi.bmiHeader.biSize], 28h ; '('
0x18006521f  lea     rax, [rsp+4A8h+bmi]
0x180065224  xor     r8d, r8d; start
0x180065227  mov     [rsp+4A8h+lpbmi], rax; lpbmi
0x18006522c  mov     rdx, r14; hbm
0x18006522f  mov     rcx, rbp; hdc
0x180065232  mov     [rsp+4A8h+lpvBits], 0; lpvBits
0x18006523b  call    cs:__imp_GetDIBits
0x180065242  nop     dword ptr [rax+rax+00h]
0x180065247  test    eax, eax
0x180065249  jz      loc_180065313
0x18006524f  mov     eax, [rsp+4A8h+bmi.bmiHeader.biSizeImage]
0x180065253  test    eax, eax
0x180065255  jz      loc_180065313
0x18006525b  mov     ecx, eax
0x18006525d  xor     edx, edx
0x18006525f  call    GpMallocEx
0x180065264  mov     rdi, rax
0x180065267  test    rax, rax
0x18006526a  jz      loc_18006536D
0x180065270  mov     r9d, [rsp+4A8h+bmi.bmiHeader.biHeight]
0x180065275  lea     rax, [rsp+4A8h+bmi]
0x18006527a  neg     r9d
0x18006527d  mov     [rsp+4A8h+usage], 0; usage
0x180065285  mov     [rsp+4A8h+lpbmi], rax; lpbmi
0x18006528a  mov     rdx, r14; hbm
0x18006528d  cmovs   r9d, [rsp+4A8h+bmi.bmiHeader.biHeight]; cLines
0x180065293  mov     rcx, rbp; hdc
0x180065296  xor     r8d, r8d; start
0x180065299  mov     [rsp+4A8h+lpvBits], rdi; lpvBits
0x18006529e  call    cs:__imp_GetDIBits
0x1800652a5  nop     dword ptr [rax+rax+00h]
0x1800652aa  test    eax, eax
0x1800652ac  jz      loc_180065374
0x1800652b2  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800652b9  xor     edx, edx; dwFlags
0x1800652bb  mov     r8d, 108h; dwBytes
0x1800652c1  call    cs:__imp_HeapAlloc
0x1800652c8  nop     dword ptr [rax+rax+00h]
0x1800652cd  test    rax, rax
0x1800652d0  jz      loc_18006535E
0x1800652d6  lea     r9d, [rbx-6]; int
0x1800652da  mov     r8, rdi; void *
0x1800652dd  lea     rdx, [rsp+4A8h+bmi]; struct tagBITMAPINFO *
0x1800652e2  mov     rcx, rax; this
0x1800652e5  call    ??0CopyOnWriteBitmap@@AEAA@PEAUtagBITMAPINFO@@PEAXH@Z; CopyOnWriteBitmap::CopyOnWriteBitmap(tagBITMAPINFO *,void *,int)
0x1800652ea  mov     [rsi], rax
0x1800652ed  mov     rcx, rax
0x1800652f0  test    rax, rax
0x1800652f3  jz      short loc_180065365
0x1800652f5  mov     rax, [rax]
0x1800652f8  mov     rax, [rax+10h]
0x1800652fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065301  test    eax, eax
0x180065303  jz      short loc_18006537E
0x180065305  mov     eax, [rsp+4A8h+bmi.bmiHeader.biXPelsPerMeter]
0x180065309  test    eax, eax
0x18006530b  jg      loc_180065397
0x180065311  xor     ebx, ebx
0x180065313  mov     rdx, r15; h
0x180065316  mov     rcx, rbp; hdc
0x180065319  call    cs:__imp_SelectObject
0x180065320  nop     dword ptr [rax+rax+00h]
0x180065325  mov     rcx, rbp; hdc
0x180065328  call    cs:__imp_DeleteDC
0x18006532f  nop     dword ptr [rax+rax+00h]
0x180065334  mov     eax, ebx
0x180065336  mov     rcx, [rsp+4A8h+var_38]
0x18006533e  xor     rcx, rsp; StackCookie
0x180065341  call    __security_check_cookie
0x180065346  mov     rbx, [rsp+4A8h+arg_18]
0x18006534e  add     rsp, 480h
0x180065355  pop     r15
0x180065357  pop     r14
0x180065359  pop     rdi
0x18006535a  pop     rsi
0x18006535b  pop     rbp
0x18006535c  retn
0x18006535e  mov     qword ptr [rsi], 0
0x180065365  mov     rcx, rdi
0x180065368  call    GpFree
0x18006536d  mov     ebx, 3
0x180065372  jmp     short loc_180065313
0x180065374  mov     rcx, rdi
0x180065377  call    GpFree
0x18006537c  jmp     short loc_180065313
0x18006537e  mov     rcx, [rsi]; this
0x180065381  call    ?Dispose@CopyOnWriteBitmap@@AEAAXXZ; CopyOnWriteBitmap::Dispose(void)
0x180065386  mov     qword ptr [rsi], 0
0x18006538d  mov     ebx, 2
0x180065392  jmp     loc_180065313
0x180065397  mov     ecx, [rsp+4A8h+bmi.bmiHeader.biYPelsPerMeter]
0x18006539b  test    ecx, ecx
0x18006539d  jle     loc_180065311
0x1800653a3  movd    xmm2, ecx
0x1800653a7  mov     rcx, [rsi]
0x1800653aa  cvtdq2ps xmm2, xmm2
0x1800653ad  movd    xmm1, eax
0x1800653b1  mulss   xmm2, cs:__real@40228f5c
0x1800653b9  cvtdq2ps xmm1, xmm1
0x1800653bc  divss   xmm2, cs:__real@42c80000
0x1800653c4  mulss   xmm1, cs:__real@40228f5c
0x1800653cc  divss   xmm1, cs:__real@42c80000
0x1800653d4  call    ?SetResolution@CopyOnWriteBitmap@@AEAA?AW4Status@@MM@Z; CopyOnWriteBitmap::SetResolution(float,float)
0x1800653d9  jmp     loc_180065311
```
