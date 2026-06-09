# UIComposition::CreateCompositionWindow(IMCLock &,HWND__ *)

- ea: `0x1800477e0`
- end: `0x180047a55`
- name: `?CreateCompositionWindow@UIComposition@@AEAAJAEAVIMCLock@@PEAUHWND__@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800e3960`

## callees

- `0x18001cc80`
- `0x1800477e0`
- `0x1800486a0`
- `0x180048aa0`
- `0x180048bd4`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x1800478a4`
- `USER32!SetWindowLongPtrW` at `0x1800478de`
- `USER32!SetWindowLongPtrW` at `0x180047a02`
- `USER32!SetWindowLongPtrW` at `0x180047a15`
- `USER32!SetWindowLongPtrW` at `0x1800478a4`
- `USER32!SetWindowLongPtrW` at `0x1800478de`
- `USER32!SetWindowLongPtrW` at `0x180047a02`
- `USER32!SetWindowLongPtrW` at `0x180047a15`
- `USER32!CreateWindowExW` at `0x18004787f`
- `USER32!CreateWindowExW` at `0x1800479bc`
- `USER32!CreateWindowExW` at `0x18004787f`
- `USER32!CreateWindowExW` at `0x1800479bc`
- `USER32!IsWindow` at `0x180047815`
- `USER32!IsWindow` at `0x180047815`

## string_xrefs

- `0x180047845`: `MSCTFIME Composition`
- `0x180047971`: `MSCTFIME Composition`
- `0x180047961`: `UIComposition::Create. m_pDefFrameWindow==NULL`
- `0x180047940`: `UIComposition::Create. m_pCompButtonFrameWindow==NULL`
- `0x18004790c`: `UIComposition::Create. m_CompWnd[].hCompWnd==NULL`
- `0x1800479d9`: `UIComposition::Create. m_DefCompWnd.hCompWnd==NULL`

## pseudocode

```c
__int64 __fastcall UIComposition::CreateCompositionWindow(UIComposition *this, struct IMCLock *a2, HWND a3)
{
  int v6; // edi
  unsigned int i; // ebp
  HWND Window; // rax
  __int64 v9; // r15
  HWND v10; // rcx
  LONG_PTR v11; // r8
  __int64 v12; // rcx
  HWND v14; // rax
  __int64 v15; // rcx

  if ( *((_QWORD *)a2 + 1) )
  {
    v6 = *((_DWORD *)a2 + 6);
    if ( v6 >= 0 && IsWindow(a3) && (*((_BYTE *)this + 16) & 1) == 0 )
    {
      for ( i = 0; i < 3; ++i )
      {
        Window = CreateWindowExW(0, L"MSCTFIME Composition", 0, 0x88000000, 0, 0, 0, 0, a3, 0, g_hInst, 0);
        v9 = 18LL * (int)i;
        *((_QWORD *)this + 18 * (int)i + 3) = Window;
        if ( !Window )
        {
          UIComposition::DestroyCompositionWindow(this);
          CicTrace(2u, "UIComposition::Create. m_CompWnd[].hCompWnd==NULL");
          return 2147942414LL;
        }
        SetWindowLongPtrW(Window, -21, (LONG_PTR)this);
        if ( i )
        {
          if ( i == 1 )
          {
            v10 = (HWND)*((_QWORD *)this + 21);
            v11 = 1;
          }
          else
          {
            v10 = (HWND)*((_QWORD *)this + 39);
            v11 = 2;
          }
        }
        else
        {
          v10 = (HWND)*((_QWORD *)this + 3);
          v11 = 0;
        }
        SetWindowLongPtrW(v10, 0, v11);
        v12 = *(_QWORD *)((char *)this + 628);
        *((_QWORD *)this + v9 + 14) = *((_QWORD *)this + v9 + 3);
        *((_QWORD *)this + v9 + 17) = v12;
      }
      if ( UIComposition::CreateCompButtonWnd(this, a3, *((HIMC *)a2 + 2)) < 0 )
      {
        UIComposition::DestroyCompositionWindow(this);
        CicTrace(2u, "UIComposition::Create. m_pCompButtonFrameWindow==NULL");
        return 2147942414LL;
      }
      if ( UIComposition::CreateDefFrameWnd(this, a3, *((HIMC *)a2 + 2)) < 0 )
      {
        UIComposition::DestroyCompositionWindow(this);
        CicTrace(2u, "UIComposition::Create. m_pDefFrameWindow==NULL");
        return 2147942414LL;
      }
      v14 = CreateWindowExW(
              0x200u,
              L"MSCTFIME Composition",
              0,
              0x48000000u,
              0,
              0,
              0,
              0,
              *(HWND *)(*((_QWORD *)this + 83) + 168LL),
              0,
              g_hInst,
              0);
      *((_QWORD *)this + 57) = v14;
      if ( !v14 )
      {
        UIComposition::DestroyCompositionWindow(this);
        CicTrace(2u, "UIComposition::Create. m_DefCompWnd.hCompWnd==NULL");
        return 2147942414LL;
      }
      *(_QWORD *)(*((_QWORD *)this + 83) + 248LL) = v14;
      SetWindowLongPtrW(*((HWND *)this + 57), -21, (LONG_PTR)this);
      SetWindowLongPtrW(*((HWND *)this + 57), 0, -1);
      v15 = *(_QWORD *)((char *)this + 628);
      *((_QWORD *)this + 68) = *((_QWORD *)this + 57);
      *((_QWORD *)this + 71) = v15;
      *((_DWORD *)this + 4) |= 1u;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800477e0  push    rbx
0x1800477e2  push    rbp
0x1800477e3  push    rsi
0x1800477e4  push    rdi
0x1800477e5  push    r12
0x1800477e7  push    r13
0x1800477e9  push    r14
0x1800477eb  push    r15
0x1800477ed  sub     rsp, 68h
0x1800477f1  xor     r12d, r12d
0x1800477f4  mov     r14, r8
0x1800477f7  mov     rsi, rdx
0x1800477fa  mov     rbx, rcx
0x1800477fd  cmp     [rdx+8], r12
0x180047801  jz      loc_180047A3D
0x180047807  mov     edi, [rdx+18h]
0x18004780a  test    edi, edi
0x18004780c  js      loc_180047A42
0x180047812  mov     rcx, r8; hWnd
0x180047815  call    cs:__imp_IsWindow
0x18004781b  test    eax, eax
0x18004781d  jz      loc_180047A42
0x180047823  test    byte ptr [rbx+10h], 1
0x180047827  jnz     loc_180047A42
0x18004782d  mov     ebp, r12d
0x180047830  lea     r13d, [r12+2]
0x180047835  cmp     ebp, 3
0x180047838  jnb     loc_180047925
0x18004783e  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180047845  lea     rdx, ?s_szCompClassName@@3QBGB; "MSCTFIME Composition"
0x18004784c  mov     [rsp+0A8h+lpParam], r12; lpParam
0x180047851  mov     r9d, 88000000h; dwStyle
0x180047857  mov     [rsp+0A8h+hInstance], rax; hInstance
0x18004785c  xor     r8d, r8d; lpWindowName
0x18004785f  mov     [rsp+0A8h+hMenu], r12; hMenu
0x180047864  xor     ecx, ecx; dwExStyle
0x180047866  mov     [rsp+0A8h+hWndParent], r14; hWndParent
0x18004786b  mov     [rsp+0A8h+nHeight], r12d; nHeight
0x180047870  mov     [rsp+0A8h+nWidth], r12d; nWidth
0x180047875  mov     [rsp+0A8h+Y], r12d; Y
0x18004787a  mov     [rsp+0A8h+X], r12d; X
0x18004787f  call    cs:__imp_CreateWindowExW
0x180047885  movsxd  rcx, ebp
0x180047888  lea     r15, [rcx+rcx*8]
0x18004788c  add     r15, r15
0x18004788f  mov     [rbx+r15*8+18h], rax
0x180047894  test    rax, rax
0x180047897  jz      short loc_180047904
0x180047899  mov     r8, rbx; dwNewLong
0x18004789c  mov     edx, 0FFFFFFEBh; nIndex
0x1800478a1  mov     rcx, rax; hWnd
0x1800478a4  call    cs:__imp_SetWindowLongPtrW
0x1800478aa  mov     ecx, ebp
0x1800478ac  test    ebp, ebp
0x1800478ae  jz      short loc_1800478D5
0x1800478b0  sub     ecx, 1
0x1800478b3  jz      short loc_1800478C6
0x1800478b5  cmp     ecx, 1
0x1800478b8  jnz     short loc_1800478E4
0x1800478ba  mov     rcx, [rbx+138h]
0x1800478c1  mov     r8, r13
0x1800478c4  jmp     short loc_1800478DC
0x1800478c6  mov     rcx, [rbx+0A8h]
0x1800478cd  mov     r8d, 1
0x1800478d3  jmp     short loc_1800478DC
0x1800478d5  mov     rcx, [rbx+18h]; hWnd
0x1800478d9  xor     r8d, r8d; dwNewLong
0x1800478dc  xor     edx, edx; nIndex
0x1800478de  call    cs:__imp_SetWindowLongPtrW
0x1800478e4  mov     rcx, [rbx+274h]
0x1800478eb  inc     ebp
0x1800478ed  mov     rax, [rbx+r15*8+18h]
0x1800478f2  mov     [rbx+r15*8+70h], rax
0x1800478f7  mov     [rbx+r15*8+88h], rcx
0x1800478ff  jmp     loc_180047835
0x180047904  mov     rcx, rbx; this
0x180047907  call    ?DestroyCompositionWindow@UIComposition@@AEAAJXZ; UIComposition::DestroyCompositionWindow(void)
0x18004790c  lea     rdx, aUicompositionC_2; "UIComposition::Create. m_CompWnd[].hCom"...
0x180047913  mov     ecx, r13d; unsigned int
0x180047916  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18004791b  mov     eax, 8007000Eh
0x180047920  jmp     loc_180047A44
0x180047925  mov     r8, [rsi+10h]; HIMC
0x180047929  mov     rdx, r14; HWND
0x18004792c  mov     rcx, rbx; this
0x18004792f  call    ?CreateCompButtonWnd@UIComposition@@QEAAJPEAUHWND__@@PEAUHIMC__@@@Z; UIComposition::CreateCompButtonWnd(HWND__ *,HIMC__ *)
0x180047934  mov     rcx, rbx; this
0x180047937  test    eax, eax
0x180047939  jns     short loc_180047949
0x18004793b  call    ?DestroyCompositionWindow@UIComposition@@AEAAJXZ; UIComposition::DestroyCompositionWindow(void)
0x180047940  lea     rdx, aUicompositionC; "UIComposition::Create. m_pCompButtonFra"...
0x180047947  jmp     short loc_180047913
0x180047949  mov     r8, [rsi+10h]; HIMC
0x18004794d  mov     rdx, r14; HWND
0x180047950  call    ?CreateDefFrameWnd@UIComposition@@QEAAJPEAUHWND__@@PEAUHIMC__@@@Z; UIComposition::CreateDefFrameWnd(HWND__ *,HIMC__ *)
0x180047955  test    eax, eax
0x180047957  jns     short loc_18004796A
0x180047959  mov     rcx, rbx; this
0x18004795c  call    ?DestroyCompositionWindow@UIComposition@@AEAAJXZ; UIComposition::DestroyCompositionWindow(void)
0x180047961  lea     rdx, aUicompositionC_0; "UIComposition::Create. m_pDefFrameWindo"...
0x180047968  jmp     short loc_180047913
0x18004796a  mov     rcx, [rbx+298h]
0x180047971  lea     rdx, ?s_szCompClassName@@3QBGB; "MSCTFIME Composition"
0x180047978  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18004797f  mov     r9d, 48000000h; dwStyle
0x180047985  mov     [rsp+0A8h+lpParam], r12; lpParam
0x18004798a  xor     r8d, r8d; lpWindowName
0x18004798d  mov     [rsp+0A8h+hInstance], rax; hInstance
0x180047992  mov     rax, [rcx+0A8h]
0x180047999  mov     ecx, 200h; dwExStyle
0x18004799e  mov     [rsp+0A8h+hMenu], r12; hMenu
0x1800479a3  mov     [rsp+0A8h+hWndParent], rax; hWndParent
0x1800479a8  mov     [rsp+0A8h+nHeight], r12d; nHeight
0x1800479ad  mov     [rsp+0A8h+nWidth], r12d; nWidth
0x1800479b2  mov     [rsp+0A8h+Y], r12d; Y
0x1800479b7  mov     [rsp+0A8h+X], r12d; X
0x1800479bc  call    cs:__imp_CreateWindowExW
0x1800479c2  mov     [rbx+1C8h], rax
0x1800479c9  mov     rcx, rax
0x1800479cc  test    rax, rax
0x1800479cf  jnz     short loc_1800479E5
0x1800479d1  mov     rcx, rbx; this
0x1800479d4  call    ?DestroyCompositionWindow@UIComposition@@AEAAJXZ; UIComposition::DestroyCompositionWindow(void)
0x1800479d9  lea     rdx, aUicompositionC_1; "UIComposition::Create. m_DefCompWnd.hCo"...
0x1800479e0  jmp     loc_180047913
0x1800479e5  mov     rax, [rbx+298h]
0x1800479ec  mov     r8, rbx; dwNewLong
0x1800479ef  mov     edx, 0FFFFFFEBh; nIndex
0x1800479f4  mov     [rax+0F8h], rcx
0x1800479fb  mov     rcx, [rbx+1C8h]; hWnd
0x180047a02  call    cs:__imp_SetWindowLongPtrW
0x180047a08  mov     rcx, [rbx+1C8h]; hWnd
0x180047a0f  or      r8, 0FFFFFFFFFFFFFFFFh; dwNewLong
0x180047a13  xor     edx, edx; nIndex
0x180047a15  call    cs:__imp_SetWindowLongPtrW
0x180047a1b  mov     rcx, [rbx+274h]
0x180047a22  mov     rax, [rbx+1C8h]
0x180047a29  mov     [rbx+220h], rax
0x180047a30  mov     [rbx+238h], rcx
0x180047a37  or      dword ptr [rbx+10h], 1
0x180047a3b  jmp     short loc_180047A42
0x180047a3d  mov     edi, 80004005h
0x180047a42  mov     eax, edi
0x180047a44  add     rsp, 68h
0x180047a48  pop     r15
0x180047a4a  pop     r14
0x180047a4c  pop     r13
0x180047a4e  pop     r12
0x180047a50  pop     rdi
0x180047a51  pop     rsi
0x180047a52  pop     rbp
0x180047a53  pop     rbx
0x180047a54  retn
```
