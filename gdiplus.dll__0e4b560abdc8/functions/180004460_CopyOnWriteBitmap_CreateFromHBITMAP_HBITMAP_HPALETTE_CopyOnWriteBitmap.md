# CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)

- ea: `0x180004460`
- end: `0x180004690`
- name: `?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z`
- size: `560`
- prototype: `__int64 __fastcall(HBITMAP, void *, CopyOnWriteBitmap **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003be8`
- `0x180004300`
- `0x18010487c`

## callees

- `0x180004460`
- `0x180004698`
- `0x18001f950`
- `0x1800b9328`
- `0x1800e5044`
- `0x1800e728c`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004580`
- `GDI32!DeleteDC` at `0x1800045e3`
- `GDI32!DeleteDC` at `0x1800045e3`
- `GDI32!GetDIBits` at `0x1800044fd`
- `GDI32!GetDIBits` at `0x18000455d`
- `GDI32!GetDIBits` at `0x1800044fd`
- `GDI32!GetDIBits` at `0x18000455d`
- `GDI32!SelectObject` at `0x1800044c5`
- `GDI32!SelectObject` at `0x1800045d4`
- `GDI32!SelectObject` at `0x1800044c5`
- `GDI32!SelectObject` at `0x1800045d4`
- `GDI32!CreateCompatibleDC` at `0x1800044a7`
- `GDI32!CreateCompatibleDC` at `0x1800044a7`

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
  memset_0(&bmi.bmiHeader.biWidth, 0, 0x424u);
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
0x180004460  mov     [rsp+arg_18], rbx
0x180004465  push    rbp
0x180004466  push    rsi
0x180004467  push    rdi
0x180004468  push    r14
0x18000446a  push    r15
0x18000446c  sub     rsp, 480h
0x180004473  mov     rax, cs:__security_cookie
0x18000447a  xor     rax, rsp
0x18000447d  mov     [rsp+4A8h+var_38], rax
0x180004485  mov     rsi, r8
0x180004488  mov     rdi, rdx
0x18000448b  mov     r14, rcx
0x18000448e  xor     edx, edx; Val
0x180004490  mov     r8d, 424h; Size
0x180004496  lea     rcx, [rsp+4A8h+bmi.bmiHeader.biWidth]; void *
0x18000449b  mov     ebx, 7
0x1800044a0  call    memset_0
0x1800044a5  xor     ecx, ecx; hdc
0x1800044a7  call    cs:__imp_CreateCompatibleDC
0x1800044ae  nop     dword ptr [rax+rax+00h]
0x1800044b3  mov     rbp, rax
0x1800044b6  test    rax, rax
0x1800044b9  jz      loc_1800045EF
0x1800044bf  mov     rdx, rdi; h
0x1800044c2  mov     rcx, rax; hdc
0x1800044c5  call    cs:__imp_SelectObject
0x1800044cc  nop     dword ptr [rax+rax+00h]
0x1800044d1  and     [rsp+4A8h+var_478], 0
0x1800044d6  xor     r9d, r9d; cLines
0x1800044d9  mov     r15, rax
0x1800044dc  mov     [rsp+4A8h+bmi.bmiHeader.biSize], 28h ; '('
0x1800044e4  lea     rax, [rsp+4A8h+bmi]
0x1800044e9  xor     r8d, r8d; start
0x1800044ec  mov     [rsp+4A8h+lpbmi], rax; lpbmi
0x1800044f1  mov     rdx, r14; hbm
0x1800044f4  and     [rsp+4A8h+lpvBits], 0
0x1800044fa  mov     rcx, rbp; hdc
0x1800044fd  call    cs:__imp_GetDIBits
0x180004504  nop     dword ptr [rax+rax+00h]
0x180004509  test    eax, eax
0x18000450b  jz      loc_1800045CE
0x180004511  mov     eax, [rsp+4A8h+bmi.bmiHeader.biSizeImage]
0x180004515  test    eax, eax
0x180004517  jz      loc_1800045CE
0x18000451d  mov     ecx, eax
0x18000451f  xor     edx, edx
0x180004521  call    GpMallocEx
0x180004526  mov     rdi, rax
0x180004529  test    rax, rax
0x18000452c  jz      loc_180004625
0x180004532  mov     r9d, [rsp+4A8h+bmi.bmiHeader.biHeight]
0x180004537  lea     rax, [rsp+4A8h+bmi]
0x18000453c  neg     r9d
0x18000453f  mov     rdx, r14; hbm
0x180004542  mov     rcx, rbp; hdc
0x180004545  cmovs   r9d, [rsp+4A8h+bmi.bmiHeader.biHeight]; cLines
0x18000454b  xor     r8d, r8d; start
0x18000454e  and     [rsp+4A8h+var_478], 0
0x180004553  mov     [rsp+4A8h+lpbmi], rax; lpbmi
0x180004558  mov     [rsp+4A8h+lpvBits], rdi; lpvBits
0x18000455d  call    cs:__imp_GetDIBits
0x180004564  nop     dword ptr [rax+rax+00h]
0x180004569  test    eax, eax
0x18000456b  jz      loc_18000462C
0x180004571  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180004578  xor     edx, edx; dwFlags
0x18000457a  mov     r8d, 108h; dwBytes
0x180004580  call    cs:__imp_HeapAlloc
0x180004587  nop     dword ptr [rax+rax+00h]
0x18000458c  test    rax, rax
0x18000458f  jz      loc_180004619
0x180004595  lea     r9d, [rbx-6]; int
0x180004599  mov     r8, rdi; void *
0x18000459c  lea     rdx, [rsp+4A8h+bmi]; struct tagBITMAPINFO *
0x1800045a1  mov     rcx, rax; this
0x1800045a4  call    ??0CopyOnWriteBitmap@@AEAA@PEAUtagBITMAPINFO@@PEAXH@Z; CopyOnWriteBitmap::CopyOnWriteBitmap(tagBITMAPINFO *,void *,int)
0x1800045a9  mov     [rsi], rax
0x1800045ac  mov     rcx, rax
0x1800045af  test    rax, rax
0x1800045b2  jz      short loc_18000461D
0x1800045b4  mov     rax, [rax]
0x1800045b7  mov     rax, [rax+10h]
0x1800045bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c0  test    eax, eax
0x1800045c2  jz      short loc_180004636
0x1800045c4  mov     eax, [rsp+4A8h+bmi.bmiHeader.biXPelsPerMeter]
0x1800045c8  test    eax, eax
0x1800045ca  jg      short loc_180004649
0x1800045cc  xor     ebx, ebx
0x1800045ce  mov     rdx, r15; h
0x1800045d1  mov     rcx, rbp; hdc
0x1800045d4  call    cs:__imp_SelectObject
0x1800045db  nop     dword ptr [rax+rax+00h]
0x1800045e0  mov     rcx, rbp; hdc
0x1800045e3  call    cs:__imp_DeleteDC
0x1800045ea  nop     dword ptr [rax+rax+00h]
0x1800045ef  mov     eax, ebx
0x1800045f1  mov     rcx, [rsp+4A8h+var_38]
0x1800045f9  xor     rcx, rsp; StackCookie
0x1800045fc  call    __security_check_cookie
0x180004601  mov     rbx, [rsp+4A8h+arg_18]
0x180004609  add     rsp, 480h
0x180004610  pop     r15
0x180004612  pop     r14
0x180004614  pop     rdi
0x180004615  pop     rsi
0x180004616  pop     rbp
0x180004617  retn
0x180004619  and     qword ptr [rsi], 0
0x18000461d  mov     rcx, rdi
0x180004620  call    GpFree
0x180004625  mov     ebx, 3
0x18000462a  jmp     short loc_1800045CE
0x18000462c  mov     rcx, rdi
0x18000462f  call    GpFree
0x180004634  jmp     short loc_1800045CE
0x180004636  mov     rcx, [rsi]; this
0x180004639  call    ?Dispose@CopyOnWriteBitmap@@AEAAXXZ; CopyOnWriteBitmap::Dispose(void)
0x18000463e  and     qword ptr [rsi], 0
0x180004642  mov     ebx, 2
0x180004647  jmp     short loc_1800045CE
0x180004649  mov     ecx, [rsp+4A8h+bmi.bmiHeader.biYPelsPerMeter]
0x18000464d  test    ecx, ecx
0x18000464f  jle     loc_1800045CC
0x180004655  movd    xmm2, ecx
0x180004659  mov     rcx, [rsi]
0x18000465c  cvtdq2ps xmm2, xmm2
0x18000465f  movd    xmm1, eax
0x180004663  mulss   xmm2, cs:__real@40228f5c
0x18000466b  cvtdq2ps xmm1, xmm1
0x18000466e  divss   xmm2, cs:__real@42c80000
0x180004676  mulss   xmm1, cs:__real@40228f5c
0x18000467e  divss   xmm1, cs:__real@42c80000
0x180004686  call    ?SetResolution@CopyOnWriteBitmap@@AEAA?AW4Status@@MM@Z; CopyOnWriteBitmap::SetResolution(float,float)
0x18000468b  jmp     loc_1800045CC
```
