# CTxtWinHost::Init(HWND__ *,tagCREATESTRUCTW const *,int,int)

- ea: `0x180061b60`
- end: `0x180061f1a`
- name: `?Init@CTxtWinHost@@UEAAHPEAUHWND__@@PEBUtagCREATESTRUCTW@@HH@Z`
- size: `954`
- prototype: `__int64 __usercall@<rax>(CTxtWinHost *__hidden this@<rcx>, HWND hWnd@<rdx>, const struct tagCREATESTRUCTW *@<r8>, int@<r9d>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18004277c`
- `0x1800601c4`
- `0x1800616e8`
- `0x180061b60`
- `0x180062af0`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x180061ba9`
- `USER32!SetWindowLongPtrW` at `0x180061cb7`
- `USER32!SetWindowLongPtrW` at `0x180061d06`
- `USER32!SetWindowLongPtrW` at `0x180061d1c`
- `USER32!SetWindowLongPtrW` at `0x180061e77`
- `USER32!SetWindowLongPtrW` at `0x180061ba9`
- `USER32!SetWindowLongPtrW` at `0x180061cb7`
- `USER32!SetWindowLongPtrW` at `0x180061d06`
- `USER32!SetWindowLongPtrW` at `0x180061d1c`
- `USER32!SetWindowLongPtrW` at `0x180061e77`
- `USER32!GetDC` at `0x180061c18`
- `USER32!GetDC` at `0x180061c18`
- `USER32!InvalidateRect` at `0x180061e8c`
- `USER32!InvalidateRect` at `0x180061e8c`
- `USER32!SetScrollRange` at `0x180061e39`
- `USER32!SetScrollRange` at `0x180061e56`
- `USER32!SetScrollRange` at `0x180061e39`
- `USER32!SetScrollRange` at `0x180061e56`
- `GDI32!GetBkMode` at `0x180061c27`
- `GDI32!GetBkMode` at `0x180061c27`

## pseudocode

```c
__int64 __fastcall CTxtWinHost::Init(CTxtWinHost *this, HWND hWnd, const struct tagCREATESTRUCTW *a3, int a4, int a5)
{
  int v9; // edi
  int v10; // edi
  int v11; // edi
  DWORD dwExStyle; // edx
  LONG style; // eax
  HDC DC; // rax
  int BkMode; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // r9d
  HWND v19; // rcx
  LONG_PTR v20; // r8
  int v21; // r9d
  int v22; // r8d
  int v23; // ecx
  LONG_PTR v24; // r8
  char v25; // al
  char v26; // cl
  int v27; // edx
  int v28; // ecx
  int v29; // eax
  int v30; // edx
  struct IUnknown **v31; // rdi
  struct IUnknown *v32; // rcx
  HWND v33; // rcx
  int v35; // [rsp+30h] [rbp-D8h] BYREF
  int v36; // [rsp+34h] [rbp-D4h]
  __int16 v37; // [rsp+3Ah] [rbp-CEh]
  __int16 v38; // [rsp+48h] [rbp-C0h]

  if ( !a3->lpszClass )
    return 0;
  if ( hWnd )
    SetWindowLongPtrW(hWnd, 0, (LONG_PTR)this);
  v9 = *((_DWORD *)this + 13) ^ (a4 << 18);
  *((_DWORD *)this + 11) = 4;
  v10 = *((_DWORD *)this + 13) ^ v9 & 0x40000;
  *((_QWORD *)this + 2) = hWnd;
  v11 = v10 | 0x20;
  *((_DWORD *)this + 13) = v11;
  *((_QWORD *)this + 3) = a3->hwndParent;
  dwExStyle = a3->dwExStyle;
  *((_DWORD *)this + 12) = dwExStyle;
  style = a3->style;
  *((_DWORD *)this + 11) = style;
  if ( a5 )
  {
    DC = GetDC(hWnd);
    BkMode = GetBkMode(DC);
    v16 = *((_DWORD *)this + 12);
    dwExStyle = BkMode == 1 ? v16 | 0x20 : v16 & 0xFFFFFFDF;
    *((_DWORD *)this + 12) = dwExStyle;
  }
  else
  {
    if ( (style & 0x100000) != 0 )
    {
      style |= 0x80u;
      *((_DWORD *)this + 11) = style;
    }
    if ( (style & 0x8000000) != 0 )
      *((_DWORD *)this + 13) = v11 | 0x800;
  }
  v17 = *((_DWORD *)this + 11);
  if ( (v17 & 0x200000) != 0 )
  {
    v17 |= 0x40u;
    *((_DWORD *)this + 11) = v17;
  }
  *((_DWORD *)this + 13) &= ~1u;
  *((_DWORD *)this + 13) |= (v17 >> 23) & 1;
  v18 = *((_DWORD *)this + 13);
  if ( (dwExStyle & 0x200) != 0 || (v17 & 0x4000) != 0 )
  {
    v18 |= 1u;
    *((_DWORD *)this + 13) = v18;
  }
  if ( (v17 & 0x20) != 0 )
    *((_WORD *)this + 48) = 42;
  if ( (v18 & 1) != 0 && CW32System::_dwMajorVersion >= 4 )
  {
    v19 = (HWND)*((_QWORD *)this + 2);
    v20 = dwExStyle | 0x200;
    *((_DWORD *)this + 12) = v20;
    SetWindowLongPtrW(v19, -20, v20);
  }
  v21 = *((_DWORD *)this + 12);
  if ( (v21 & 0x400000) != 0 )
  {
    v22 = *((_DWORD *)this + 11);
    v23 = ~v22 & 2;
    v24 = v22 ^ 2u;
    *((_DWORD *)this + 11) = v24;
    *((_DWORD *)this + 12) = (v21 ^ 0x2000) & 0xFFBFBFFF | (v23 << 13);
    SetWindowLongPtrW(*((HWND *)this + 2), -16, v24);
    SetWindowLongPtrW(*((HWND *)this + 2), -20, *((unsigned int *)this + 12));
  }
  if ( (int)CTxtWinHost::CreateTextServices(this) < 0 )
    return 0;
  v25 = CW32System::_cxBorder;
  v26 = CW32System::_cyBorder;
  *((_BYTE *)this + 103) = CW32System::_cxBorder;
  *((_BYTE *)this + 102) = v26;
  if ( (*((_BYTE *)this + 52) & 1) == 0 )
  {
    *((_BYTE *)this + 103) = 2 * v25;
    *((_BYTE *)this + 102) = 2 * v26;
  }
  CTxtWinHost::SetDefaultInset(this);
  memset_0(&v35, 0, 0x9Cu);
  v27 = *((_DWORD *)this + 12);
  if ( (*((_BYTE *)this + 44) & 3) == 0 && (v27 & 0x1000) == 0 )
  {
    v28 = 0;
    v29 = 0x10000;
  }
  else
  {
    v28 = 8;
    v29 = 65544;
    v36 = 8;
    v38 = 3;
    if ( (*((_BYTE *)this + 44) & 1) == 0 )
      v38 = 2;
  }
  v30 = v27 & 0x2000;
  if ( v30 )
  {
    v36 = v29;
    v37 = 1;
  }
  v31 = (struct IUnknown **)((char *)this + 32);
  if ( !v30 )
    v29 = v28;
  if ( v29 )
  {
    v32 = *v31;
    v35 = 188;
    ((void (__fastcall *)(struct IUnknown *, __int64, __int64, int *, _QWORD))v32->lpVtbl[1].QueryInterface)(
      v32,
      1095,
      4,
      &v35,
      0);
  }
  if ( a5 )
  {
    v31 = (struct IUnknown **)((char *)this + 32);
    CTxtEdit::Set10Mode(*((CTxtEdit **)this + 4));
    v33 = (HWND)*((_QWORD *)this + 2);
    if ( v33 )
    {
      if ( (*((_DWORD *)this + 11) & 0x2000) == 0 )
      {
        SetScrollRange(v33, 1, 0, 0, 1);
        SetScrollRange(*((HWND *)this + 2), 0, 0, 0, 1);
        SetWindowLongPtrW(*((HWND *)this + 2), -16, *((_DWORD *)this + 11) & 0xFFCFFFFF);
        InvalidateRect(*((HWND *)this + 2), 0, 1);
      }
    }
  }
  if ( a3->lpszName && ((int (__fastcall *)(struct IUnknown *))(*v31)->lpVtbl[4].Release)(*v31) < 0 )
  {
    SafeReleaseAndNULL(v31);
    return 0;
  }
  if ( (*((_BYTE *)this + 44) & 0x10) != 0 )
    ((void (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, _QWORD))(*v31)->lpVtbl[1].QueryInterface)(
      *v31,
      1228,
      1024,
      1536,
      0);
  return 1;
}

```

## disassembly

```asm
0x180061b60  mov     [rsp+arg_18], rbx
0x180061b65  push    rbp
0x180061b66  push    rsi
0x180061b67  push    rdi
0x180061b68  push    r12
0x180061b6a  push    r13
0x180061b6c  sub     rsp, 0E0h
0x180061b73  mov     rax, cs:__security_cookie
0x180061b7a  xor     rax, rsp
0x180061b7d  mov     [rsp+108h+var_38], rax
0x180061b85  cmp     qword ptr [r8+40h], 0
0x180061b8a  mov     edi, r9d
0x180061b8d  mov     rbp, r8
0x180061b90  mov     rsi, rdx
0x180061b93  mov     rbx, rcx
0x180061b96  jz      loc_180061EBC
0x180061b9c  test    rdx, rdx
0x180061b9f  jz      short loc_180061BB5
0x180061ba1  mov     r8, rcx; dwNewLong
0x180061ba4  xor     edx, edx; nIndex
0x180061ba6  mov     rcx, rsi; hWnd
0x180061ba9  call    cs:__imp_SetWindowLongPtrW
0x180061bb0  nop     dword ptr [rax+rax+00h]
0x180061bb5  shl     edi, 12h
0x180061bb8  mov     r12d, 1
0x180061bbe  xor     edi, [rbx+34h]
0x180061bc1  mov     dword ptr [rbx+2Ch], 4
0x180061bc8  and     edi, 40000h
0x180061bce  xor     edi, [rbx+34h]
0x180061bd1  mov     [rbx+10h], rsi
0x180061bd5  or      edi, 20h
0x180061bd8  cmp     [rsp+108h+arg_20], 0
0x180061be0  mov     [rbx+34h], edi
0x180061be3  mov     rax, [rbp+18h]
0x180061be7  mov     [rbx+18h], rax
0x180061beb  mov     edx, [rbp+48h]
0x180061bee  mov     [rbx+30h], edx
0x180061bf1  mov     eax, [rbp+30h]
0x180061bf4  mov     [rbx+2Ch], eax
0x180061bf7  jnz     short loc_180061C15
0x180061bf9  bt      eax, 14h
0x180061bfd  jnb     short loc_180061C06
0x180061bff  bts     eax, 7
0x180061c03  mov     [rbx+2Ch], eax
0x180061c06  bt      eax, 1Bh
0x180061c0a  jnb     short loc_180061C46
0x180061c0c  bts     edi, 0Bh
0x180061c10  mov     [rbx+34h], edi
0x180061c13  jmp     short loc_180061C46
0x180061c15  mov     rcx, rsi; hWnd
0x180061c18  call    cs:__imp_GetDC
0x180061c1f  nop     dword ptr [rax+rax+00h]
0x180061c24  mov     rcx, rax; hdc
0x180061c27  call    cs:__imp_GetBkMode
0x180061c2e  nop     dword ptr [rax+rax+00h]
0x180061c33  mov     edx, [rbx+30h]
0x180061c36  cmp     eax, r12d
0x180061c39  jnz     short loc_180061C40
0x180061c3b  or      edx, 20h
0x180061c3e  jmp     short loc_180061C43
0x180061c40  and     edx, 0FFFFFFDFh
0x180061c43  mov     [rbx+30h], edx
0x180061c46  mov     r8d, [rbx+2Ch]
0x180061c4a  bt      r8d, 15h
0x180061c4f  jnb     short loc_180061C59
0x180061c51  or      r8d, 40h
0x180061c55  mov     [rbx+2Ch], r8d
0x180061c59  and     dword ptr [rbx+34h], 0FFFFFFFEh
0x180061c5d  mov     eax, r8d
0x180061c60  shr     eax, 17h
0x180061c63  and     eax, r12d
0x180061c66  or      [rbx+34h], eax
0x180061c69  mov     r9d, [rbx+34h]
0x180061c6d  bt      edx, 9
0x180061c71  setnb   cl
0x180061c74  bt      r8d, 0Eh
0x180061c79  setnb   al
0x180061c7c  test    al, cl
0x180061c7e  jnz     short loc_180061C87
0x180061c80  or      r9d, r12d
0x180061c83  mov     [rbx+34h], r9d
0x180061c87  test    r8b, 20h
0x180061c8b  jz      short loc_180061C93
0x180061c8d  mov     word ptr [rbx+60h], 2Ah ; '*'
0x180061c93  mov     edi, 0FFFFFFECh
0x180061c98  test    r12b, r9b
0x180061c9b  jz      short loc_180061CC3
0x180061c9d  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180061ca4  jb      short loc_180061CC3
0x180061ca6  mov     rcx, [rbx+10h]; hWnd
0x180061caa  bts     edx, 9
0x180061cae  mov     r8d, edx; dwNewLong
0x180061cb1  mov     edx, edi; nIndex
0x180061cb3  mov     [rbx+30h], r8d
0x180061cb7  call    cs:__imp_SetWindowLongPtrW
0x180061cbe  nop     dword ptr [rax+rax+00h]
0x180061cc3  mov     r9d, [rbx+30h]
0x180061cc7  mov     esi, 2000h
0x180061ccc  mov     r13d, 2
0x180061cd2  bt      r9d, 16h
0x180061cd7  jnb     short loc_180061D28
0x180061cd9  mov     ecx, [rbx+2Ch]
0x180061cdc  lea     edx, [r13-12h]; nIndex
0x180061ce0  mov     r8d, ecx
0x180061ce3  xor     r9d, esi
0x180061ce6  not     ecx
0x180061ce8  and     r9d, 0FFBFBFFFh
0x180061cef  and     ecx, r13d
0x180061cf2  xor     r8d, r13d; dwNewLong
0x180061cf5  shl     ecx, 0Dh
0x180061cf8  or      ecx, r9d
0x180061cfb  mov     [rbx+2Ch], r8d
0x180061cff  mov     [rbx+30h], ecx
0x180061d02  mov     rcx, [rbx+10h]; hWnd
0x180061d06  call    cs:__imp_SetWindowLongPtrW
0x180061d0d  nop     dword ptr [rax+rax+00h]
0x180061d12  mov     r8d, [rbx+30h]; dwNewLong
0x180061d16  mov     edx, edi; nIndex
0x180061d18  mov     rcx, [rbx+10h]; hWnd
0x180061d1c  call    cs:__imp_SetWindowLongPtrW
0x180061d23  nop     dword ptr [rax+rax+00h]
0x180061d28  mov     rcx, rbx; this
0x180061d2b  call    ?CreateTextServices@CTxtWinHost@@QEAAJXZ; CTxtWinHost::CreateTextServices(void)
0x180061d30  test    eax, eax
0x180061d32  js      loc_180061EBC
0x180061d38  mov     al, byte ptr cs:?_cxBorder@CW32System@@0HA; int CW32System::_cxBorder
0x180061d3e  mov     cl, byte ptr cs:?_cyBorder@CW32System@@0HA; int CW32System::_cyBorder
0x180061d44  mov     [rbx+67h], al
0x180061d47  mov     [rbx+66h], cl
0x180061d4a  test    [rbx+34h], r12b
0x180061d4e  jnz     short loc_180061D5A
0x180061d50  add     al, al
0x180061d52  add     cl, cl
0x180061d54  mov     [rbx+67h], al
0x180061d57  mov     [rbx+66h], cl
0x180061d5a  mov     rcx, rbx; this
0x180061d5d  call    ?SetDefaultInset@CTxtWinHost@@QEAAXXZ; CTxtWinHost::SetDefaultInset(void)
0x180061d62  xor     edx, edx; Val
0x180061d64  lea     rcx, [rsp+108h+var_D8]; void *
0x180061d69  mov     r8d, 9Ch; Size
0x180061d6f  call    memset_0
0x180061d74  mov     edx, [rbx+30h]
0x180061d77  mov     r8d, 3
0x180061d7d  test    [rbx+2Ch], r8b
0x180061d81  setz    cl
0x180061d84  bt      edx, 0Ch
0x180061d88  setnb   al
0x180061d8b  test    al, cl
0x180061d8d  jz      short loc_180061D98
0x180061d8f  xor     ecx, ecx
0x180061d91  mov     eax, 10000h
0x180061d96  jmp     short loc_180061DB8
0x180061d98  mov     ecx, 8
0x180061d9d  mov     eax, 10008h
0x180061da2  mov     [rsp+108h+var_D4], ecx
0x180061da6  mov     [rsp+108h+var_C0], r8w
0x180061dac  test    [rbx+2Ch], r12b
0x180061db0  jnz     short loc_180061DB8
0x180061db2  mov     [rsp+108h+var_C0], r13w
0x180061db8  and     edx, esi
0x180061dba  jz      short loc_180061DC6
0x180061dbc  mov     [rsp+108h+var_D4], eax
0x180061dc0  mov     [rsp+108h+var_CE], r12w
0x180061dc6  test    edx, edx
0x180061dc8  lea     rdi, [rbx+20h]
0x180061dcc  cmovz   eax, ecx
0x180061dcf  test    eax, eax
0x180061dd1  jz      short loc_180061E03
0x180061dd3  mov     rcx, [rdi]
0x180061dd6  lea     r9, [rsp+108h+var_D8]
0x180061ddb  mov     [rsp+108h+var_D8], 0BCh
0x180061de3  mov     edx, 447h
0x180061de8  mov     r8d, 4
0x180061dee  mov     qword ptr [rsp+108h+bRedraw], 0
0x180061df7  mov     rax, [rcx]
0x180061dfa  mov     rax, [rax+18h]
0x180061dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e03  cmp     [rsp+108h+arg_20], 0
0x180061e0b  jz      loc_180061E98
0x180061e11  lea     rdi, [rbx+20h]
0x180061e15  mov     rcx, [rdi]; this
0x180061e18  call    ?Set10Mode@CTxtEdit@@QEAAXXZ; CTxtEdit::Set10Mode(void)
0x180061e1d  mov     rcx, [rbx+10h]; hWnd
0x180061e21  test    rcx, rcx
0x180061e24  jz      short loc_180061E98
0x180061e26  test    [rbx+2Ch], esi
0x180061e29  jnz     short loc_180061E98
0x180061e2b  xor     r9d, r9d; nMaxPos
0x180061e2e  mov     [rsp+108h+bRedraw], r12d; bRedraw
0x180061e33  xor     r8d, r8d; nMinPos
0x180061e36  mov     edx, r12d; nBar
0x180061e39  call    cs:__imp_SetScrollRange
0x180061e40  nop     dword ptr [rax+rax+00h]
0x180061e45  mov     rcx, [rbx+10h]; hWnd
0x180061e49  xor     r9d, r9d; nMaxPos
0x180061e4c  xor     r8d, r8d; nMinPos
0x180061e4f  mov     [rsp+108h+bRedraw], r12d; bRedraw
0x180061e54  xor     edx, edx; nBar
0x180061e56  call    cs:__imp_SetScrollRange
0x180061e5d  nop     dword ptr [rax+rax+00h]
0x180061e62  mov     r8d, [rbx+2Ch]
0x180061e66  mov     eax, 0FFCFFFFFh
0x180061e6b  mov     rcx, [rbx+10h]; hWnd
0x180061e6f  and     r8, rax; dwNewLong
0x180061e72  mov     edx, 0FFFFFFF0h; nIndex
0x180061e77  call    cs:__imp_SetWindowLongPtrW
0x180061e7e  nop     dword ptr [rax+rax+00h]
0x180061e83  mov     rcx, [rbx+10h]; hWnd
0x180061e87  mov     r8d, r12d; bErase
0x180061e8a  xor     edx, edx; lpRect
0x180061e8c  call    cs:__imp_InvalidateRect
0x180061e93  nop     dword ptr [rax+rax+00h]
0x180061e98  mov     rdx, [rbp+38h]
0x180061e9c  test    rdx, rdx
0x180061e9f  jz      short loc_180061EE6
0x180061ea1  mov     rcx, [rdi]
0x180061ea4  mov     rax, [rcx]
0x180061ea7  mov     rax, [rax+70h]
0x180061eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061eb0  test    eax, eax
0x180061eb2  jns     short loc_180061EE6
0x180061eb4  mov     rcx, rdi; struct IUnknown **
0x180061eb7  call    ?SafeReleaseAndNULL@@YAXPEAPEAUIUnknown@@@Z; SafeReleaseAndNULL(IUnknown * *)
0x180061ebc  xor     eax, eax
0x180061ebe  mov     rcx, [rsp+108h+var_38]
0x180061ec6  xor     rcx, rsp; StackCookie
0x180061ec9  call    __security_check_cookie
0x180061ece  mov     rbx, [rsp+108h+arg_18]
0x180061ed6  add     rsp, 0E0h
0x180061edd  pop     r13
0x180061edf  pop     r12
0x180061ee1  pop     rdi
0x180061ee2  pop     rsi
0x180061ee3  pop     rbp
0x180061ee4  retn
0x180061ee6  test    byte ptr [rbx+2Ch], 10h
0x180061eea  jz      short loc_180061F15
0x180061eec  mov     rcx, [rdi]
0x180061eef  mov     r9d, 600h
0x180061ef5  mov     r8d, 400h
0x180061efb  mov     qword ptr [rsp+108h+bRedraw], 0
0x180061f04  mov     rdx, [rcx]
0x180061f07  mov     rax, [rdx+18h]
0x180061f0b  mov     edx, 4CCh
0x180061f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f15  mov     eax, r12d
0x180061f18  jmp     short loc_180061EBE
```
