# ATL::CAxHostWindow::get_Font(IFontDisp * *)

- ea: `0x140018920`
- end: `0x140018b3b`
- name: `?get_Font@CAxHostWindow@ATL@@UEAAJPEAPEAUIFontDisp@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, struct IFontDisp **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002463`
- `0x14000e4f8`
- `0x140018920`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `GDI32!GetStockObject` at `0x14001897e`
- `GDI32!GetStockObject` at `0x140018995`
- `GDI32!GetStockObject` at `0x14001897e`
- `GDI32!GetStockObject` at `0x140018995`
- `GDI32!GetObjectW` at `0x1400189d1`
- `GDI32!GetObjectW` at `0x1400189d1`
- `GDI32!GetDeviceCaps` at `0x140018a51`
- `GDI32!GetDeviceCaps` at `0x140018a98`
- `GDI32!GetDeviceCaps` at `0x140018a51`
- `GDI32!GetDeviceCaps` at `0x140018a98`
- `USER32!GetDesktopWindow` at `0x140018a69`
- `USER32!GetDesktopWindow` at `0x140018aa7`
- `USER32!GetDesktopWindow` at `0x140018a69`
- `USER32!GetDesktopWindow` at `0x140018aa7`
- `USER32!ReleaseDC` at `0x140018ab9`
- `USER32!ReleaseDC` at `0x140018ab9`
- `USER32!GetDC` at `0x140018a32`
- `USER32!GetDC` at `0x140018a78`
- `USER32!GetDC` at `0x140018a32`
- `USER32!GetDC` at `0x140018a78`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x140018ae8`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x140018ae8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAxHostWindow::get_Font(ATL::CAxHostWindow *this, LPVOID *a2)
{
  LPVOID *v5; // rbx
  HGDIOBJ StockObject; // rdi
  int v7; // r12d
  HWND v8; // rcx
  HDC v9; // rax
  HDC v10; // rdi
  int DeviceCaps; // r15d
  HWND v12; // rcx
  HWND DesktopWindow; // rax
  HDC DC; // rax
  tagFONTDESC FontDesc; // [rsp+20h] [rbp-69h] BYREF
  _DWORD pv[4]; // [rsp+50h] [rbp-39h] BYREF
  SHORT v17; // [rsp+60h] [rbp-29h]
  unsigned __int8 v18; // [rsp+64h] [rbp-25h]
  unsigned __int8 v19; // [rsp+65h] [rbp-24h]
  unsigned __int8 v20; // [rsp+66h] [rbp-23h]
  unsigned __int8 v21; // [rsp+67h] [rbp-22h]
  char v22; // [rsp+6Ch] [rbp-1Dh] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (LPVOID *)((char *)this + 200);
  if ( *((_QWORD *)this + 25) )
    goto LABEL_15;
  StockObject = GetStockObject(17);
  if ( !StockObject )
  {
    StockObject = GetStockObject(13);
    if ( !StockObject )
      return ATL::AtlHresultFromLastError();
  }
  memset_0(pv, 0, 0x5Cu);
  GetObjectW(StockObject, 92, pv);
  *(_QWORD *)&FontDesc.cbSizeofstruct = 40;
  FontDesc.cySize.int64 = 0;
  FontDesc.lpstrName = (LPOLESTR)&v22;
  FontDesc.sWeight = v17;
  FontDesc.sCharset = v21;
  FontDesc.fItalic = v18;
  FontDesc.fUnderline = v19;
  FontDesc.fStrikethrough = v20;
  v7 = -pv[0];
  if ( pv[0] > 0 )
    v7 = pv[0];
  v8 = (HWND)*((_QWORD *)this - 18);
  if ( !v8 )
  {
    DesktopWindow = GetDesktopWindow();
    DC = GetDC(DesktopWindow);
    v10 = DC;
    if ( DC )
    {
      DeviceCaps = GetDeviceCaps(DC, 90);
      v12 = GetDesktopWindow();
      goto LABEL_14;
    }
    return ATL::AtlHresultFromLastError();
  }
  v9 = GetDC(v8);
  v10 = v9;
  if ( !v9 )
    return ATL::AtlHresultFromLastError();
  DeviceCaps = GetDeviceCaps(v9, 90);
  v12 = (HWND)*((_QWORD *)this - 18);
LABEL_14:
  ReleaseDC(v12, v10);
  FontDesc.cySize.int64 = (unsigned int)(720000 * v7 / DeviceCaps);
  OleCreateFontIndirect(&FontDesc, &GUID_bef6e003_a874_101a_8bba_00aa00300cab, v5);
LABEL_15:
  *a2 = *v5;
  if ( *v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v5 + 8LL))(*v5);
  return 0;
}

```

## disassembly

```asm
0x140018920  mov     [rsp-8+arg_10], rbx
0x140018925  mov     [rsp-8+arg_18], rsi
0x14001892a  push    rbp
0x14001892b  push    rdi
0x14001892c  push    r12
0x14001892e  push    r14
0x140018930  push    r15
0x140018932  lea     rbp, [rsp-37h]
0x140018937  sub     rsp, 0C0h
0x14001893e  mov     rax, cs:__security_cookie
0x140018945  xor     rax, rsp
0x140018948  mov     [rbp+57h+var_30], rax
0x14001894c  mov     rsi, rdx
0x14001894f  mov     r14, rcx
0x140018952  test    rdx, rdx
0x140018955  jnz     short loc_140018961
0x140018957  mov     eax, 80004003h
0x14001895c  jmp     loc_140018B12
0x140018961  mov     qword ptr [rdx], 0
0x140018968  lea     rbx, [rcx+0C8h]
0x14001896f  cmp     qword ptr [rbx], 0
0x140018973  jnz     loc_140018AF5
0x140018979  mov     ecx, 11h; i
0x14001897e  call    cs:__imp_GetStockObject
0x140018985  nop     dword ptr [rax+rax+00h]
0x14001898a  mov     rdi, rax
0x14001898d  test    rax, rax
0x140018990  jnz     short loc_1400189B3
0x140018992  lea     ecx, [rax+0Dh]; i
0x140018995  call    cs:__imp_GetStockObject
0x14001899c  nop     dword ptr [rax+rax+00h]
0x1400189a1  mov     rdi, rax
0x1400189a4  test    rax, rax
0x1400189a7  jnz     short loc_1400189B3
0x1400189a9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400189ae  jmp     loc_140018B12
0x1400189b3  mov     r15d, 5Ch ; '\'
0x1400189b9  mov     r8d, r15d; Size
0x1400189bc  xor     edx, edx; Val
0x1400189be  lea     rcx, [rbp+57h+pv]; void *
0x1400189c2  call    memset_0
0x1400189c7  lea     r8, [rbp+57h+pv]; pv
0x1400189cb  mov     edx, r15d; c
0x1400189ce  mov     rcx, rdi; h
0x1400189d1  call    cs:__imp_GetObjectW
0x1400189d8  nop     dword ptr [rax+rax+00h]
0x1400189dd  mov     qword ptr [rbp+57h+FontDesc.cbSizeofstruct], 28h ; '('
0x1400189e5  mov     qword ptr [rbp+57h+FontDesc.cySize], 0
0x1400189ed  lea     rax, [rbp+57h+var_74]
0x1400189f1  mov     [rbp+57h+FontDesc.lpstrName], rax
0x1400189f5  movzx   eax, [rbp+57h+var_80]
0x1400189f9  mov     [rbp+57h+FontDesc.sWeight], ax
0x1400189fd  movzx   eax, [rbp+57h+var_79]
0x140018a01  mov     [rbp+57h+FontDesc.sCharset], ax
0x140018a05  movzx   eax, [rbp+57h+var_7C]
0x140018a09  mov     [rbp+57h+FontDesc.fItalic], eax
0x140018a0c  movzx   eax, [rbp+57h+var_7B]
0x140018a10  mov     [rbp+57h+FontDesc.fUnderline], eax
0x140018a13  movzx   eax, [rbp+57h+var_7A]
0x140018a17  mov     [rbp+57h+FontDesc.fStrikethrough], eax
0x140018a1a  mov     r12d, [rbp+57h+pv]
0x140018a1e  neg     r12d
0x140018a21  cmovs   r12d, [rbp+57h+pv]
0x140018a26  mov     rcx, [r14-90h]; hWnd
0x140018a2d  test    rcx, rcx
0x140018a30  jz      short loc_140018A69
0x140018a32  call    cs:__imp_GetDC
0x140018a39  nop     dword ptr [rax+rax+00h]
0x140018a3e  mov     rdi, rax
0x140018a41  test    rax, rax
0x140018a44  jz      loc_1400189A9
0x140018a4a  lea     edx, [r15-2]; index
0x140018a4e  mov     rcx, rax; hdc
0x140018a51  call    cs:__imp_GetDeviceCaps
0x140018a58  nop     dword ptr [rax+rax+00h]
0x140018a5d  mov     r15d, eax
0x140018a60  mov     rcx, [r14-90h]
0x140018a67  jmp     short loc_140018AB6
0x140018a69  call    cs:__imp_GetDesktopWindow
0x140018a70  nop     dword ptr [rax+rax+00h]
0x140018a75  mov     rcx, rax; hWnd
0x140018a78  call    cs:__imp_GetDC
0x140018a7f  nop     dword ptr [rax+rax+00h]
0x140018a84  mov     rdi, rax
0x140018a87  test    rax, rax
0x140018a8a  jz      loc_1400189A9
0x140018a90  mov     edx, 5Ah ; 'Z'; index
0x140018a95  mov     rcx, rax; hdc
0x140018a98  call    cs:__imp_GetDeviceCaps
0x140018a9f  nop     dword ptr [rax+rax+00h]
0x140018aa4  mov     r15d, eax
0x140018aa7  call    cs:__imp_GetDesktopWindow
0x140018aae  nop     dword ptr [rax+rax+00h]
0x140018ab3  mov     rcx, rax; hWnd
0x140018ab6  mov     rdx, rdi; hDC
0x140018ab9  call    cs:__imp_ReleaseDC
0x140018ac0  nop     dword ptr [rax+rax+00h]
0x140018ac5  imul    eax, r12d, 0AFC80h
0x140018acc  cdq
0x140018acd  idiv    r15d
0x140018ad0  mov     dword ptr [rbp+57h+FontDesc.cySize], eax
0x140018ad3  mov     dword ptr [rbp+57h+FontDesc.cySize+4], 0
0x140018ada  mov     r8, rbx; lplpvObj
0x140018add  lea     rdx, _GUID_bef6e003_a874_101a_8bba_00aa00300cab; riid
0x140018ae4  lea     rcx, [rbp+57h+FontDesc]; lpFontDesc
0x140018ae8  call    cs:__imp_OleCreateFontIndirect
0x140018aef  nop     dword ptr [rax+rax+00h]
0x140018af4  nop
0x140018af5  mov     rax, [rbx]
0x140018af8  mov     [rsi], rax
0x140018afb  mov     rcx, [rbx]
0x140018afe  test    rcx, rcx
0x140018b01  jz      short loc_140018B10
0x140018b03  mov     rax, [rcx]
0x140018b06  mov     rax, [rax+8]
0x140018b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018b0f  nop
0x140018b10  xor     eax, eax
0x140018b12  mov     rcx, [rbp+57h+var_30]
0x140018b16  xor     rcx, rsp; StackCookie
0x140018b19  call    __security_check_cookie
0x140018b1e  lea     r11, [rsp+0E0h+var_20]
0x140018b26  mov     rbx, [r11+40h]
0x140018b2a  mov     rsi, [r11+48h]
0x140018b2e  mov     rsp, r11
0x140018b31  pop     r15
0x140018b33  pop     r14
0x140018b35  pop     r12
0x140018b37  pop     rdi
0x140018b38  pop     rbp
0x140018b39  retn
```
