# CUpDown::ArrowKeyWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180047770`
- end: `0x180047b0d`
- name: `?ArrowKeyWndProc@CUpDown@@IEAA_JPEAUHWND__@@I_K_J@Z`
- size: `925`
- prototype: `__int64 __usercall@<rax>(CUpDown *__hidden this@<rcx>, HWND hWnd@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047750`

## callees

- `0x180005e7c`
- `0x180046ca0`
- `0x180047770`
- `0x180047e10`
- `0x180047ec0`
- `0x180065d9c`
- `0x180114520`
- `0x180116cac`
- `0x180117828`
- `0x180117a9c`
- `0x180118718`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004781e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004781e`
- `GDI32!DeleteObject` at `0x180047a8f`
- `GDI32!DeleteObject` at `0x180047b02`
- `GDI32!DeleteObject` at `0x180047a8f`
- `GDI32!DeleteObject` at `0x180047b02`
- `GDI32!CombineRgn` at `0x180047a86`
- `GDI32!CombineRgn` at `0x180047a86`
- `GDI32!CreateRectRgn` at `0x180047a2e`
- `GDI32!CreateRectRgn` at `0x180047a66`
- `GDI32!CreateRectRgn` at `0x180047a2e`
- `GDI32!CreateRectRgn` at `0x180047a66`
- `USER32!GetPropW` at `0x18004780d`
- `USER32!GetPropW` at `0x18004780d`
- `USER32!GetCapture` at `0x180047879`
- `USER32!GetCapture` at `0x180047953`
- `USER32!GetCapture` at `0x180047980`
- `USER32!GetCapture` at `0x180047879`
- `USER32!GetCapture` at `0x180047953`
- `USER32!GetCapture` at `0x180047980`
- `USER32!GetWindowRect` at `0x180047a1a`
- `USER32!GetWindowRect` at `0x180047a52`
- `USER32!GetWindowRect` at `0x180047a1a`
- `USER32!GetWindowRect` at `0x180047a52`
- `USER32!IsWindow` at `0x1800477f2`
- `USER32!IsWindow` at `0x1800477f2`

## pseudocode

```c
LRESULT __fastcall CUpDown::ArrowKeyWndProc(CUpDown *this, HWND hWnd, int a3, WPARAM a4, LPARAM lParam)
{
  __int64 v5; // r12
  HRGN v6; // rsi
  HRGN v10; // r14
  _DWORD *PropW; // rax
  _DWORD *v12; // rdi
  int v13; // ebx
  HWND v15; // rbx
  int v16; // edx
  int v17; // ecx
  int v18; // ecx
  int v19; // ebx
  int v20; // esi
  HWND v21; // rbx
  HWND v22; // rbx
  unsigned int v23; // r8d
  HWND v24; // rcx
  HRGN RectRgn; // rbx
  HRGN v26; // rax
  bool v27; // zf
  struct tagRECT Rect; // [rsp+30h] [rbp-28h] BYREF

  v5 = 0;
  v6 = (HRGN)a4;
  v10 = 0;
  switch ( a3 )
  {
    case 8:
      dword_180211088 = 0;
      dword_180210378 = 8;
      goto LABEL_8;
    case 130:
      _SoftFadeEnd((UINT_PTR)this + 144);
      _SoftFadeEnd((UINT_PTR)this + 296);
      RemoveWindowSubclass(hWnd, CUpDown::s_ArrowKeyWndProc, 0);
      *((_DWORD *)this + 18) &= ~0x80u;
      v27 = (*((_BYTE *)this + 72) & 0x20) == 0;
      *((_QWORD *)this + 8) = 0;
      if ( !v27 )
        operator delete(this, 0x1C8u);
      goto LABEL_8;
    case 133:
      if ( !*((_QWORD *)this + 16) )
        goto LABEL_8;
      if ( *((_DWORD *)this + 23) != 1 )
        goto LABEL_8;
      v24 = *(HWND *)this;
      Rect = 0;
      GetWindowRect(v24, &Rect);
      RectRgn = CreateRectRgn(Rect.left, Rect.top, Rect.right, Rect.bottom);
      if ( !RectRgn )
        goto LABEL_8;
      if ( (unsigned __int64)v6 <= 1 )
      {
        GetWindowRect(hWnd, &Rect);
        v26 = CreateRectRgn(Rect.left, Rect.top, Rect.right, Rect.bottom);
        v10 = v26;
        if ( !v26 )
        {
LABEL_51:
          DeleteObject(RectRgn);
          goto LABEL_8;
        }
        v6 = v26;
      }
      CombineRgn(v6, v6, RectRgn, 4);
      goto LABEL_51;
    case 135:
      return DefSubclassProc(hWnd, 0x87u, a4, lParam) | 1;
    case 256:
      if ( a4 != 38 && a4 != 40 )
        goto LABEL_8;
      v22 = *(HWND *)this;
      if ( GetCapture() != v22 )
      {
        if ( (lParam & 0x40000000) == 0 )
          CUpDown::GetPos(this, 0);
        v23 = v6 == (HRGN)40;
        *((_DWORD *)this + 24) = v23;
        CUpDown::Squish(this, v6 != (HRGN)40, v23);
        CUpDown::Bump(this);
        CCNotifyNavigationKeyUsage(this, 1);
      }
      return 0;
    case 257:
      if ( a4 != 38 && a4 != 40 )
        goto LABEL_8;
      v21 = *(HWND *)this;
      if ( GetCapture() != v21 )
        CUpDown::Squish(this, 0, 0);
      return 0;
  }
  if ( ((a3 - 522) & 0xFFFFFFFB) == 0 )
  {
    v15 = *(HWND *)this;
    if ( GetCapture() != v15 && ((unsigned __int8)v6 & 0xC) == 0 )
    {
      v16 = -SWORD1(v6);
      if ( a3 != 526 )
        v16 = SWORD1(v6);
      if ( a3 == dword_180210378 )
      {
        v17 = dword_180211088;
      }
      else
      {
        v17 = 0;
        dword_180210378 = a3;
      }
      v18 = v17 - v16;
      dword_180211088 = v18;
      v19 = v18 / 120;
      if ( v18 / 120 )
      {
        dword_180211088 = v18 % 120;
        CUpDown::GetPos(this, 0);
        v20 = -v19;
        *((_DWORD *)this + 24) = v19 > 0;
        if ( v19 > 0 )
          v20 = v19;
        while ( v20 > 0 )
        {
          --v20;
          CUpDown::Squish(this, *((_DWORD *)this + 24) == 0, *((_DWORD *)this + 24));
          CUpDown::Bump(this);
        }
        CUpDown::Squish(this, 0, 0);
      }
      return 1;
    }
  }
LABEL_8:
  if ( IsWindow(hWnd) )
  {
    if ( g_aCC32Subclass )
    {
      PropW = GetPropW(hWnd, (LPCWSTR)(unsigned __int16)g_aCC32Subclass);
      v12 = PropW;
      if ( PropW )
      {
        v13 = PropW[3];
        if ( GetCurrentThreadId() == v13 )
        {
          if ( *((_QWORD *)v12 + 2) )
            v5 = CallNextSubclassProc((_DWORD)v12, (_DWORD)hWnd, a3, (_DWORD)v6, lParam);
        }
      }
    }
  }
  if ( v10 )
    DeleteObject(v10);
  return v5;
}

```

## disassembly

```asm
0x180047770  push    rbp
0x180047772  push    rbx
0x180047773  push    rsi
0x180047774  push    rdi
0x180047775  push    r12
0x180047777  push    r13
0x180047779  push    r14
0x18004777b  push    r15
0x18004777d  mov     rbp, rsp
0x180047780  sub     rsp, 58h
0x180047784  mov     rax, cs:__security_cookie
0x18004778b  xor     rax, rsp
0x18004778e  mov     [rbp+var_18], rax
0x180047792  xor     r12d, r12d
0x180047795  mov     eax, r8d
0x180047798  mov     rsi, r9
0x18004779b  mov     r13d, r8d
0x18004779e  mov     r15, rdx
0x1800477a1  mov     rdi, rcx
0x1800477a4  mov     r14d, r12d
0x1800477a7  sub     eax, 8
0x1800477aa  jz      loc_180047AE9
0x1800477b0  sub     eax, 7Ah ; 'z'
0x1800477b3  jz      loc_180047A9A
0x1800477b9  sub     eax, 3
0x1800477bc  jz      loc_1800479F5
0x1800477c2  sub     eax, 2
0x1800477c5  jz      loc_1800479D8
0x1800477cb  sub     eax, 79h ; 'y'
0x1800477ce  jz      loc_18004796D
0x1800477d4  cmp     eax, 1
0x1800477d7  jz      loc_180047940
0x1800477dd  lea     eax, [r8-20Ah]
0x1800477e4  test    eax, 0FFFFFFFBh
0x1800477e9  jz      loc_180047876
0x1800477ef  mov     rcx, r15; hWnd
0x1800477f2  call    cs:__imp_IsWindow
0x1800477f8  test    eax, eax
0x1800477fa  jz      short loc_18004784D
0x1800477fc  movzx   eax, cs:g_aCC32Subclass
0x180047803  test    ax, ax
0x180047806  jz      short loc_18004784D
0x180047808  mov     edx, eax; lpString
0x18004780a  mov     rcx, r15; hWnd
0x18004780d  call    cs:__imp_GetPropW
0x180047813  mov     rdi, rax
0x180047816  test    rax, rax
0x180047819  jz      short loc_18004784D
0x18004781b  mov     ebx, [rax+0Ch]
0x18004781e  call    cs:__imp_GetCurrentThreadId
0x180047824  cmp     eax, ebx
0x180047826  jnz     short loc_18004784D
0x180047828  xor     ebx, ebx
0x18004782a  cmp     [rdi+10h], rbx
0x18004782e  jz      short loc_18004784D
0x180047830  mov     rcx, [rbp+lParam]
0x180047834  mov     r9, rsi
0x180047837  mov     [rsp+58h+var_38], rcx
0x18004783c  mov     r8d, r13d
0x18004783f  mov     rcx, rdi
0x180047842  mov     rdx, r15
0x180047845  call    CallNextSubclassProc
0x18004784a  mov     r12, rax
0x18004784d  test    r14, r14
0x180047850  jnz     loc_180047AFF
0x180047856  mov     rax, r12
0x180047859  mov     rcx, [rbp+var_18]
0x18004785d  xor     rcx, rsp; StackCookie
0x180047860  call    __security_check_cookie
0x180047865  add     rsp, 58h
0x180047869  pop     r15
0x18004786b  pop     r14
0x18004786d  pop     r13
0x18004786f  pop     r12
0x180047871  pop     rdi
0x180047872  pop     rsi
0x180047873  pop     rbx
0x180047874  pop     rbp
0x180047875  retn
0x180047876  mov     rbx, [rcx]
0x180047879  call    cs:__imp_GetCapture
0x18004787f  cmp     rax, rbx
0x180047882  jz      loc_1800477EF
0x180047888  test    sil, 0Ch
0x18004788c  jnz     loc_1800477EF
0x180047892  shr     rsi, 10h
0x180047896  movsx   eax, si
0x180047899  mov     edx, eax
0x18004789b  neg     edx
0x18004789d  cmp     r13d, 20Eh
0x1800478a4  cmovnz  edx, eax
0x1800478a7  cmp     r13d, cs:dword_180210378
0x1800478ae  jz      short loc_1800478BC
0x1800478b0  mov     ecx, r12d
0x1800478b3  mov     cs:dword_180210378, r13d
0x1800478ba  jmp     short loc_1800478C2
0x1800478bc  mov     ecx, cs:dword_180211088
0x1800478c2  sub     ecx, edx
0x1800478c4  mov     eax, 88888889h
0x1800478c9  imul    ecx
0x1800478cb  mov     cs:dword_180211088, ecx
0x1800478d1  lea     ebx, [rcx+rdx]
0x1800478d4  sar     ebx, 6
0x1800478d7  mov     eax, ebx
0x1800478d9  shr     eax, 1Fh
0x1800478dc  add     ebx, eax
0x1800478de  jz      short loc_180047936
0x1800478e0  imul    eax, ebx, 78h ; 'x'
0x1800478e3  xor     edx, edx; int *
0x1800478e5  sub     ecx, eax
0x1800478e7  mov     cs:dword_180211088, ecx
0x1800478ed  mov     rcx, rdi; this
0x1800478f0  call    ?GetPos@CUpDown@@IEAA_JPEAH@Z; CUpDown::GetPos(int *)
0x1800478f5  test    ebx, ebx
0x1800478f7  mov     eax, r12d
0x1800478fa  mov     esi, ebx
0x1800478fc  setnle  al
0x1800478ff  neg     esi
0x180047901  mov     [rdi+60h], eax
0x180047904  cmovs   esi, ebx
0x180047907  jmp     short loc_180047925
0x180047909  mov     r8d, [rdi+60h]; unsigned int
0x18004790d  mov     edx, r12d
0x180047910  dec     esi
0x180047912  test    r8d, r8d
0x180047915  setz    dl; unsigned int
0x180047918  call    ?Squish@CUpDown@@IEAAXII@Z; CUpDown::Squish(uint,uint)
0x18004791d  mov     rcx, rdi; this
0x180047920  call    ?Bump@CUpDown@@IEAAXXZ; CUpDown::Bump(void)
0x180047925  mov     rcx, rdi; this
0x180047928  test    esi, esi
0x18004792a  jg      short loc_180047909
0x18004792c  xor     r8d, r8d; unsigned int
0x18004792f  xor     edx, edx; unsigned int
0x180047931  call    ?Squish@CUpDown@@IEAAXII@Z; CUpDown::Squish(uint,uint)
0x180047936  mov     eax, 1
0x18004793b  jmp     loc_180047859
0x180047940  cmp     rsi, 26h ; '&'
0x180047944  jz      short loc_180047950
0x180047946  cmp     rsi, 28h ; '('
0x18004794a  jnz     loc_1800477EF
0x180047950  mov     rbx, [rcx]
0x180047953  call    cs:__imp_GetCapture
0x180047959  cmp     rax, rbx
0x18004795c  jz      short loc_1800479D1
0x18004795e  xor     r8d, r8d; unsigned int
0x180047961  xor     edx, edx; unsigned int
0x180047963  mov     rcx, rdi; this
0x180047966  call    ?Squish@CUpDown@@IEAAXII@Z; CUpDown::Squish(uint,uint)
0x18004796b  jmp     short loc_1800479D1
0x18004796d  cmp     rsi, 26h ; '&'
0x180047971  jz      short loc_18004797D
0x180047973  cmp     rsi, 28h ; '('
0x180047977  jnz     loc_1800477EF
0x18004797d  mov     rbx, [rcx]
0x180047980  call    cs:__imp_GetCapture
0x180047986  cmp     rax, rbx
0x180047989  jz      short loc_1800479D1
0x18004798b  test    [rbp+lParam], 40000000h
0x180047993  jnz     short loc_18004799F
0x180047995  xor     edx, edx; int *
0x180047997  mov     rcx, rdi; this
0x18004799a  call    ?GetPos@CUpDown@@IEAA_JPEAH@Z; CUpDown::GetPos(int *)
0x18004799f  mov     r8d, r12d
0x1800479a2  cmp     rsi, 28h ; '('
0x1800479a6  mov     rcx, rdi; this
0x1800479a9  setz    r8b; unsigned int
0x1800479ad  mov     edx, r8d
0x1800479b0  mov     [rdi+60h], r8d
0x1800479b4  xor     edx, 1; unsigned int
0x1800479b7  call    ?Squish@CUpDown@@IEAAXII@Z; CUpDown::Squish(uint,uint)
0x1800479bc  mov     rcx, rdi; this
0x1800479bf  call    ?Bump@CUpDown@@IEAAXXZ; CUpDown::Bump(void)
0x1800479c4  mov     edx, 1
0x1800479c9  mov     rcx, rdi
0x1800479cc  call    CCNotifyNavigationKeyUsage
0x1800479d1  xor     eax, eax
0x1800479d3  jmp     loc_180047859
0x1800479d8  mov     r9, [rbp+lParam]; lParam
0x1800479dc  mov     r8, rsi; wParam
0x1800479df  mov     edx, 87h; uMsg
0x1800479e4  mov     rcx, r15; hWnd
0x1800479e7  call    DefSubclassProc
0x1800479ec  or      rax, 1
0x1800479f0  jmp     loc_180047859
0x1800479f5  cmp     [rcx+80h], r12
0x1800479fc  jz      loc_1800477EF
0x180047a02  cmp     dword ptr [rcx+5Ch], 1
0x180047a06  jnz     loc_1800477EF
0x180047a0c  mov     rcx, [rcx]; hWnd
0x180047a0f  lea     rdx, [rbp+Rect]; lpRect
0x180047a13  xorps   xmm0, xmm0
0x180047a16  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180047a1a  call    cs:__imp_GetWindowRect
0x180047a20  mov     r9d, [rbp+Rect.bottom]; y2
0x180047a24  mov     r8d, [rbp+Rect.right]; x2
0x180047a28  mov     edx, [rbp+Rect.top]; y1
0x180047a2b  mov     ecx, [rbp+Rect.left]; x1
0x180047a2e  call    cs:__imp_CreateRectRgn
0x180047a34  mov     rbx, rax
0x180047a37  test    rax, rax
0x180047a3a  jz      loc_1800477EF
0x180047a40  test    rsi, rsi
0x180047a43  jz      short loc_180047A4B
0x180047a45  cmp     rsi, 1
0x180047a49  jnz     short loc_180047A77
0x180047a4b  lea     rdx, [rbp+Rect]; lpRect
0x180047a4f  mov     rcx, r15; hWnd
0x180047a52  call    cs:__imp_GetWindowRect
0x180047a58  mov     r9d, [rbp+Rect.bottom]; y2
0x180047a5c  mov     r8d, [rbp+Rect.right]; x2
0x180047a60  mov     edx, [rbp+Rect.top]; y1
0x180047a63  mov     ecx, [rbp+Rect.left]; x1
0x180047a66  call    cs:__imp_CreateRectRgn
0x180047a6c  mov     r14, rax
0x180047a6f  test    rax, rax
0x180047a72  jz      short loc_180047A8C
0x180047a74  mov     rsi, rax
0x180047a77  mov     r9d, 4; iMode
0x180047a7d  mov     r8, rbx; hrgnSrc2
0x180047a80  mov     rdx, rsi; hrgnSrc1
0x180047a83  mov     rcx, rsi; hrgnDst
0x180047a86  call    cs:__imp_CombineRgn
0x180047a8c  mov     rcx, rbx; ho
0x180047a8f  call    cs:__imp_DeleteObject
0x180047a95  jmp     loc_1800477EF
0x180047a9a  add     rcx, 90h; uIDEvent
0x180047aa1  call    ?_SoftFadeEnd@@YAXPEAUtagCCSOFTFADE@@@Z; _SoftFadeEnd(tagCCSOFTFADE *)
0x180047aa6  lea     rcx, [rdi+128h]; uIDEvent
0x180047aad  call    ?_SoftFadeEnd@@YAXPEAUtagCCSOFTFADE@@@Z; _SoftFadeEnd(tagCCSOFTFADE *)
0x180047ab2  xor     r8d, r8d; uIdSubclass
0x180047ab5  lea     rdx, ?s_ArrowKeyWndProc@CUpDown@@KA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x180047abc  mov     rcx, r15; hWnd
0x180047abf  call    RemoveWindowSubclass
0x180047ac4  btr     dword ptr [rdi+48h], 7
0x180047ac9  test    byte ptr [rdi+48h], 20h
0x180047acd  mov     [rdi+40h], r12
0x180047ad1  jz      loc_1800477EF
0x180047ad7  mov     edx, 1C8h; unsigned __int64
0x180047adc  mov     rcx, rdi; void *
0x180047adf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180047ae4  jmp     loc_1800477EF
0x180047ae9  mov     cs:dword_180211088, r12d
0x180047af0  mov     cs:dword_180210378, 8
0x180047afa  jmp     loc_1800477EF
0x180047aff  mov     rcx, r14; ho
0x180047b02  call    cs:__imp_DeleteObject
0x180047b08  jmp     loc_180047856
```
