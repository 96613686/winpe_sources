# CDocument::GetThumbnail(uint,HBITMAP__ * *,WTS_ALPHATYPE *)

- ea: `0x1802270d0`
- end: `0x1802272c4`
- name: `?GetThumbnail@CDocument@@UEAAHIPEAPEAUHBITMAP__@@PEAW4WTS_ALPHATYPE@@@Z`
- size: `500`
- prototype: `int __fastcall(CDocument *this, unsigned int cx, HBITMAP__ **phbmp, WTS_ALPHATYPE *pdwAlpha)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x180139950`
- `0x1802270d0`
- `0x18023d860`
- `0x1802aee30`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetDC` at `0x180227109`
- `USER32!GetDC` at `0x180227109`
- `USER32!ReleaseDC` at `0x18022721d`
- `USER32!ReleaseDC` at `0x18022725c`
- `USER32!ReleaseDC` at `0x18022721d`
- `USER32!ReleaseDC` at `0x18022725c`
- `GDI32!DeleteDC` at `0x180227297`
- `GDI32!DeleteDC` at `0x180227297`
- `GDI32!CreateCompatibleBitmap` at `0x18022718f`
- `GDI32!CreateCompatibleBitmap` at `0x18022718f`
- `GDI32!SelectObject` at `0x1802271b1`
- `GDI32!SelectObject` at `0x1802271ca`
- `GDI32!SelectObject` at `0x18022720a`
- `GDI32!SelectObject` at `0x1802271b1`
- `GDI32!SelectObject` at `0x1802271ca`
- `GDI32!SelectObject` at `0x18022720a`
- `GDI32!CreateCompatibleDC` at `0x180227163`
- `GDI32!CreateCompatibleDC` at `0x180227163`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDocument::GetThumbnail(CDocument *this, int cx, HBITMAP__ **phbmp, WTS_ALPHATYPE *pdwAlpha)
{
  HDC v7; // rsi
  CDC *v8; // rdi
  CDC *p_dc; // r15
  CGdiObject *v10; // rbx
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v14; // rax
  HGDIOBJ v15; // rax
  void *m_hObject; // rdx
  HGDIOBJ v17; // rax
  HBITMAP__ *v18; // rbx
  CHandleMap *m_pmapHGDIOBJ; // rcx
  unsigned int v20; // ebx
  HDC v21; // rax
  CBitmap bitmap; // [rsp+20h] [rbp-50h] BYREF
  CDC dc; // [rsp+30h] [rbp-40h] BYREF
  CRect rectDocBounds; // [rsp+50h] [rbp-20h] BYREF

  if ( pdwAlpha )
    *pdwAlpha = WTSAT_UNKNOWN;
  v7 = GetDC(0);
  v8 = CDC::FromHandle(v7);
  dc.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dc.m_hDC, 0, 20);
  p_dc = v8;
  v10 = 0;
  bitmap.m_hObject = 0;
  bitmap.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  *(_QWORD *)&rectDocBounds.left = 0;
  rectDocBounds.right = cx;
  rectDocBounds.bottom = cx;
  if ( v8 )
    m_hDC = v8->m_hDC;
  else
    m_hDC = 0;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach(&dc, CompatibleDC) )
  {
    CompatibleBitmap = CreateCompatibleBitmap(
                         v8->m_hDC,
                         rectDocBounds.right - rectDocBounds.left,
                         rectDocBounds.bottom - rectDocBounds.top);
    if ( CGdiObject::Attach(&bitmap, CompatibleBitmap) )
    {
      p_dc = &dc;
      v14 = SelectObject(dc.m_hDC, bitmap.m_hObject);
      v10 = CGdiObject::FromHandle(v14);
    }
    v15 = SelectObject(dc.m_hDC, bitmap.m_hObject);
    CGdiObject::FromHandle(v15);
    this->OnDrawThumbnail(this, &dc, &rectDocBounds);
    if ( p_dc != v8 )
    {
      if ( v10 )
        m_hObject = v10->m_hObject;
      else
        m_hObject = 0;
      v17 = SelectObject(dc.m_hDC, m_hObject);
      CGdiObject::FromHandle(v17);
    }
    ReleaseDC(0, v7);
    v18 = (HBITMAP__ *)bitmap.m_hObject;
    if ( bitmap.m_hObject )
    {
      m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
      if ( m_pmapHGDIOBJ )
        CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, bitmap.m_hObject);
    }
    bitmap.m_hObject = 0;
    *phbmp = v18;
    v20 = 1;
  }
  else
  {
    ReleaseDC(0, v7);
    v20 = 0;
  }
  bitmap.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bitmap);
  dc.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dc.m_hDC )
  {
    v21 = CDC::Detach(&dc);
    DeleteDC(v21);
  }
  return v20;
}

```

## disassembly

```asm
0x1802270d0  mov     [rsp-38h+arg_8], rbx
0x1802270d5  push    rbp
0x1802270d6  push    rsi
0x1802270d7  push    rdi
0x1802270d8  push    r12
0x1802270da  push    r13
0x1802270dc  push    r14
0x1802270de  push    r15
0x1802270e0  mov     rbp, rsp
0x1802270e3  sub     rsp, 70h
0x1802270e7  mov     rax, cs:__security_cookie
0x1802270ee  xor     rax, rsp
0x1802270f1  mov     [rbp+var_10], rax
0x1802270f5  mov     r12, phbmp
0x1802270f8  mov     r14d, edx
0x1802270fb  mov     r13, this
0x1802270fe  test    pdwAlpha, pdwAlpha
0x180227101  jz      short loc_180227107
0x180227103  and     dword ptr [pdwAlpha], 0
0x180227107  xor     ecx, ecx; hWnd
0x180227109  call    cs:__imp_GetDC
0x18022710f  mov     rsi, rax
0x180227112  mov     this, rax; hDC
0x180227115  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x18022711a  mov     rdi, rax
0x18022711d  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180227124  mov     [rbp+dc.__vftable], rax
0x180227128  xorps   xmm0, xmm0
0x18022712b  movdqu  xmmword ptr [rbp+dc.m_hDC], xmm0
0x180227130  and     [rbp+dc.m_bPrinting], 0
0x180227134  mov     r15, rdi
0x180227137  xor     ebx, ebx
0x180227139  xor     eax, eax
0x18022713b  mov     [rbp+bitmap.m_hObject], rax
0x18022713f  lea     this, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180227146  mov     [rbp+bitmap.__vftable], this
0x18022714a  mov     qword ptr [rbp+rectDocBounds.left], rax
0x18022714e  mov     [rbp+rectDocBounds.right], r14d
0x180227152  mov     [rbp+rectDocBounds.bottom], r14d
0x180227156  test    rdi, rdi
0x180227159  jnz     short loc_18022715F
0x18022715b  xor     ecx, ecx
0x18022715d  jmp     short loc_180227163
0x18022715f  mov     this, [rdi+8]; hdc
0x180227163  call    cs:__imp_CreateCompatibleDC
0x180227169  mov     rdx, rax; hDC
0x18022716c  lea     this, [rbp+dc]; this
0x180227170  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180227175  test    eax, eax
0x180227177  jz      loc_180227257
0x18022717d  mov     r8d, [rbp+rectDocBounds.bottom]
0x180227181  sub     r8d, [rbp+rectDocBounds.top]; cy
0x180227185  mov     edx, [rbp+rectDocBounds.right]
0x180227188  sub     edx, [rbp+rectDocBounds.left]; cx
0x18022718b  mov     this, [rdi+8]; hdc
0x18022718f  call    cs:__imp_CreateCompatibleBitmap
0x180227195  mov     rdx, rax; hObject
0x180227198  lea     this, [rbp+bitmap]; this
0x18022719c  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802271a1  test    eax, eax
0x1802271a3  jz      short loc_1802271C2
0x1802271a5  lea     r15, [rbp+dc]
0x1802271a9  mov     rdx, [rbp+bitmap.m_hObject]; h
0x1802271ad  mov     this, [rbp+dc.m_hDC]; hdc
0x1802271b1  call    cs:__imp_SelectObject
0x1802271b7  mov     this, rax; h
0x1802271ba  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802271bf  mov     rbx, rax
0x1802271c2  mov     rdx, [rbp+bitmap.m_hObject]; h
0x1802271c6  mov     this, [rbp+dc.m_hDC]; hdc
0x1802271ca  call    cs:__imp_SelectObject
0x1802271d0  mov     this, rax; h
0x1802271d3  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802271d8  mov     rdx, [r13+0]
0x1802271dc  mov     rax, [rdx+228h]
0x1802271e3  lea     phbmp, [rbp+rectDocBounds]
0x1802271e7  lea     rdx, [rbp+dc]
0x1802271eb  mov     this, r13
0x1802271ee  call    cs:__guard_dispatch_icall_fptr
0x1802271f4  cmp     r15, rdi
0x1802271f7  jz      short loc_180227218
0x1802271f9  test    rbx, rbx
0x1802271fc  jnz     short loc_180227202
0x1802271fe  xor     edx, edx
0x180227200  jmp     short loc_180227206
0x180227202  mov     rdx, [rbx+8]; h
0x180227206  mov     this, [rbp+dc.m_hDC]; hdc
0x18022720a  call    cs:__imp_SelectObject
0x180227210  mov     this, rax; h
0x180227213  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180227218  mov     rdx, rsi; hDC
0x18022721b  xor     ecx, ecx; hWnd
0x18022721d  call    cs:__imp_ReleaseDC
0x180227223  mov     rbx, [rbp+bitmap.m_hObject]
0x180227227  test    rbx, rbx
0x18022722a  jz      short loc_180227247
0x18022722c  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180227231  mov     this, [rax+40h]
0x180227235  test    this, this
0x180227238  jz      short loc_180227247
0x18022723a  add     this, 28h ; '('; this
0x18022723e  mov     rdx, [rbp+bitmap.m_hObject]; key
0x180227242  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x180227247  and     [rbp+bitmap.m_hObject], 0
0x18022724c  mov     [r12], rbx
0x180227250  mov     ebx, 1
0x180227255  jmp     short loc_180227264
0x180227257  mov     rdx, rsi; hDC
0x18022725a  xor     ecx, ecx; hWnd
0x18022725c  call    cs:__imp_ReleaseDC
0x180227262  xor     ebx, ebx
0x180227264  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18022726b  mov     [rbp+bitmap.__vftable], rax
0x18022726f  lea     this, [rbp+bitmap]; this
0x180227273  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180227278  nop
0x180227279  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180227280  mov     [rbp+dc.__vftable], rax
0x180227284  cmp     [rbp+dc.m_hDC], 0
0x180227289  jz      short loc_18022729E
0x18022728b  lea     this, [rbp+dc]; this
0x18022728f  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180227294  mov     this, rax; hdc
0x180227297  call    cs:__imp_DeleteDC
0x18022729d  nop
0x18022729e  mov     eax, ebx
0x1802272a0  mov     this, [rbp+var_10]
0x1802272a4  xor     this, rsp; StackCookie
0x1802272a7  call    __security_check_cookie
0x1802272ac  mov     rbx, [rsp+70h+arg_8]
0x1802272b4  add     rsp, 70h
0x1802272b8  pop     r15
0x1802272ba  pop     r14
0x1802272bc  pop     r13
0x1802272be  pop     r12
0x1802272c0  pop     rdi
0x1802272c1  pop     rsi
0x1802272c2  pop     rbp
0x1802272c3  retn
```
