# CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)

- ea: `0x180009310`
- end: `0x180009525`
- name: `?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z`
- size: `533`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008ebc`
- `0x180008ffc`
- `0x180115944`

## callees

- `0x180009310`
- `0x18000952c`
- `0x18001ec80`
- `0x1800ce55c`
- `0x1800f0e40`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800093cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000942a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800093cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000942a`
- `GDI32!DeleteDC` at `0x18000947d`
- `GDI32!DeleteDC` at `0x18000947d`
- `GDI32!GetDIBits` at `0x1800093a7`
- `GDI32!GetDIBits` at `0x18000940d`
- `GDI32!GetDIBits` at `0x1800093a7`
- `GDI32!GetDIBits` at `0x18000940d`
- `GDI32!SelectObject` at `0x18000936f`
- `GDI32!SelectObject` at `0x180009474`
- `GDI32!SelectObject` at `0x18000936f`
- `GDI32!SelectObject` at `0x180009474`
- `GDI32!CreateCompatibleDC` at `0x180009357`
- `GDI32!CreateCompatibleDC` at `0x180009357`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP a1, void *a2, CopyOnWriteBitmap **a3)
{
  unsigned int v6; // ebx
  HDC CompatibleDC; // rax
  HDC v8; // rbp
  HGDIOBJ v9; // r15
  void *lpvBits; // rdi
  UINT biHeight; // r9d
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
    lpvBits = HeapAlloc(GpRuntime::GpMemHeap, 0, bmi.bmiHeader.biSizeImage);
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
        v13 = CopyOnWriteBitmap::CopyOnWriteBitmap(v12, &bmi, (unsigned __int8 *)lpvBits, 1);
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
0x180009310  mov     [rsp+arg_18], rbx
0x180009315  push    rbp
0x180009316  push    rsi
0x180009317  push    rdi
0x180009318  push    r14
0x18000931a  push    r15
0x18000931c  sub     rsp, 480h
0x180009323  mov     rax, cs:__security_cookie
0x18000932a  xor     rax, rsp
0x18000932d  mov     [rsp+4A8h+var_38], rax
0x180009335  mov     rsi, r8
0x180009338  mov     rdi, rdx
0x18000933b  mov     r14, rcx
0x18000933e  xor     edx, edx; Val
0x180009340  mov     r8d, 428h; Size
0x180009346  lea     rcx, [rsp+4A8h+bmi]; void *
0x18000934b  mov     ebx, 7
0x180009350  call    memset_0
0x180009355  xor     ecx, ecx; hdc
0x180009357  call    cs:__imp_CreateCompatibleDC
0x18000935d  mov     rbp, rax
0x180009360  test    rax, rax
0x180009363  jz      loc_180009483
0x180009369  mov     rdx, rdi; h
0x18000936c  mov     rcx, rax; hdc
0x18000936f  call    cs:__imp_SelectObject
0x180009375  mov     [rsp+4A8h+usage], 0; usage
0x18000937d  xor     r9d, r9d; cLines
0x180009380  mov     r15, rax
0x180009383  mov     [rsp+4A8h+bmi.bmiHeader.biSize], 28h ; '('
0x18000938b  lea     rax, [rsp+4A8h+bmi]
0x180009390  xor     r8d, r8d; start
0x180009393  mov     [rsp+4A8h+lpbmi], rax; lpbmi
0x180009398  mov     rdx, r14; hbm
0x18000939b  mov     rcx, rbp; hdc
0x18000939e  mov     [rsp+4A8h+lpvBits], 0; lpvBits
0x1800093a7  call    cs:__imp_GetDIBits
0x1800093ad  test    eax, eax
0x1800093af  jz      loc_18000946E
0x1800093b5  mov     eax, [rsp+4A8h+bmi.bmiHeader.biSizeImage]
0x1800093b9  test    eax, eax
0x1800093bb  jz      loc_18000946E
0x1800093c1  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800093c8  mov     r8d, eax; dwBytes
0x1800093cb  xor     edx, edx; dwFlags
0x1800093cd  call    cs:__imp_HeapAlloc
0x1800093d3  mov     rdi, rax
0x1800093d6  test    rax, rax
0x1800093d9  jz      loc_1800094BB
0x1800093df  mov     r9d, [rsp+4A8h+bmi.bmiHeader.biHeight]
0x1800093e4  lea     rax, [rsp+4A8h+bmi]
0x1800093e9  neg     r9d
0x1800093ec  mov     [rsp+4A8h+usage], 0; usage
0x1800093f4  mov     [rsp+4A8h+lpbmi], rax; lpbmi
0x1800093f9  mov     rdx, r14; hbm
0x1800093fc  cmovs   r9d, [rsp+4A8h+bmi.bmiHeader.biHeight]; cLines
0x180009402  mov     rcx, rbp; hdc
0x180009405  xor     r8d, r8d; start
0x180009408  mov     [rsp+4A8h+lpvBits], rdi; lpvBits
0x18000940d  call    cs:__imp_GetDIBits
0x180009413  test    eax, eax
0x180009415  jz      loc_1800094C2
0x18000941b  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180009422  xor     edx, edx; dwFlags
0x180009424  mov     r8d, 108h; dwBytes
0x18000942a  call    cs:__imp_HeapAlloc
0x180009430  test    rax, rax
0x180009433  jz      short loc_1800094AC
0x180009435  lea     r9d, [rbx-6]; int
0x180009439  mov     r8, rdi; void *
0x18000943c  lea     rdx, [rsp+4A8h+bmi]; struct tagBITMAPINFO *
0x180009441  mov     rcx, rax; this
0x180009444  call    ??0CopyOnWriteBitmap@@AEAA@PEAUtagBITMAPINFO@@PEAXH@Z; CopyOnWriteBitmap::CopyOnWriteBitmap(tagBITMAPINFO *,void *,int)
0x180009449  mov     [rsi], rax
0x18000944c  mov     rcx, rax
0x18000944f  test    rax, rax
0x180009452  jz      short loc_1800094B3
0x180009454  mov     rax, [rax]
0x180009457  mov     rax, [rax+10h]
0x18000945b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009460  test    eax, eax
0x180009462  jz      short loc_1800094CC
0x180009464  mov     eax, [rsp+4A8h+bmi.bmiHeader.biXPelsPerMeter]
0x180009468  test    eax, eax
0x18000946a  jg      short loc_1800094E2
0x18000946c  xor     ebx, ebx
0x18000946e  mov     rdx, r15; h
0x180009471  mov     rcx, rbp; hdc
0x180009474  call    cs:__imp_SelectObject
0x18000947a  mov     rcx, rbp; hdc
0x18000947d  call    cs:__imp_DeleteDC
0x180009483  mov     eax, ebx
0x180009485  mov     rcx, [rsp+4A8h+var_38]
0x18000948d  xor     rcx, rsp; StackCookie
0x180009490  call    __security_check_cookie
0x180009495  mov     rbx, [rsp+4A8h+arg_18]
0x18000949d  add     rsp, 480h
0x1800094a4  pop     r15
0x1800094a6  pop     r14
0x1800094a8  pop     rdi
0x1800094a9  pop     rsi
0x1800094aa  pop     rbp
0x1800094ab  retn
0x1800094ac  mov     qword ptr [rsi], 0
0x1800094b3  mov     rcx, rdi
0x1800094b6  call    GpFree
0x1800094bb  mov     ebx, 3
0x1800094c0  jmp     short loc_18000946E
0x1800094c2  mov     rcx, rdi
0x1800094c5  call    GpFree
0x1800094ca  jmp     short loc_18000946E
0x1800094cc  mov     rcx, [rsi]; this
0x1800094cf  call    ?Dispose@CopyOnWriteBitmap@@AEAAXXZ; CopyOnWriteBitmap::Dispose(void)
0x1800094d4  mov     qword ptr [rsi], 0
0x1800094db  mov     ebx, 2
0x1800094e0  jmp     short loc_18000946E
0x1800094e2  mov     ecx, [rsp+4A8h+bmi.bmiHeader.biYPelsPerMeter]
0x1800094e6  test    ecx, ecx
0x1800094e8  jle     short loc_18000946C
0x1800094ea  movd    xmm2, ecx
0x1800094ee  mov     rcx, [rsi]
0x1800094f1  cvtdq2ps xmm2, xmm2
0x1800094f4  movd    xmm1, eax
0x1800094f8  mulss   xmm2, cs:__real@40228f5c
0x180009500  cvtdq2ps xmm1, xmm1
0x180009503  divss   xmm2, cs:__real@42c80000
0x18000950b  mulss   xmm1, cs:__real@40228f5c
0x180009513  divss   xmm1, cs:__real@42c80000
0x18000951b  call    ?SetResolution@CopyOnWriteBitmap@@AEAA?AW4Status@@MM@Z; CopyOnWriteBitmap::SetResolution(float,float)
0x180009520  jmp     loc_18000946C
```
