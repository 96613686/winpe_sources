# ATL::CAxHostWindow::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x140011150`
- end: `0x14001131e`
- name: `?GetWindowContext@CAxHostWindow@ATL@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `462`
- prototype: `int(ATL::CAxHostWindow *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000f8d8`
- `0x14000f9ac`
- `0x140011150`
- `0x14004d010`

## import_xrefs

- `USER32!CreateAcceleratorTableW` at `0x1400112a8`
- `USER32!CreateAcceleratorTableW` at `0x1400112a8`
- `USER32!GetParent` at `0x1400112dc`
- `USER32!GetParent` at `0x1400112dc`
- `USER32!GetClientRect` at `0x140011263`
- `USER32!GetClientRect` at `0x14001127b`
- `USER32!GetClientRect` at `0x140011263`
- `USER32!GetClientRect` at `0x14001127b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAxHostWindow::GetWindowContext(
        ATL::CAxHostWindow *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lpRect,
        struct tagOIFI *a6)
{
  _QWORD *v10; // r15
  _QWORD *v11; // r14
  struct tagOIFI *v12; // rbx
  __int64 paccel; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a3 || !a4 || !lpRect )
    return 2147500035LL;
  v10 = (_QWORD *)((char *)this + 120);
  if ( !*((_QWORD *)this + 15) )
  {
    paccel = 0;
    ATL::CComObject<ATL::CAxFrameWindow>::CreateInstance(&paccel);
    (**(void (__fastcall ***)(__int64, GUID *, _QWORD *))(paccel + 72))(
      paccel + 72,
      &GUID_00000116_0000_0000_c000_000000000046,
      v10);
  }
  v11 = (_QWORD *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
  {
    paccel = 0;
    ATL::CComObject<ATL::CAxUIWindow>::CreateInstance(&paccel);
    (**(void (__fastcall ***)(__int64, GUID *, char *))(paccel + 72))(
      paccel + 72,
      &GUID_00000115_0000_0000_c000_000000000046,
      (char *)this + 128);
  }
  *a2 = (struct IOleInPlaceFrame *)*v10;
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  *a3 = (struct IOleInPlaceUIWindow *)*v11;
  if ( *v11 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  GetClientRect(*((HWND *)this - 10), a4);
  GetClientRect(*((HWND *)this - 10), lpRect);
  if ( !*((_QWORD *)this + 30) )
  {
    LODWORD(paccel) = 0;
    WORD2(paccel) = 0;
    *((_QWORD *)this + 30) = CreateAcceleratorTableW((LPACCEL)&paccel, 1);
  }
  v12 = a6;
  a6->cb = 32;
  v12->fMDIApp = (*((_DWORD *)this + 48) >> 2) & 1;
  v12->hwndFrame = GetParent(*((HWND *)this - 10));
  v12->haccel = (HACCEL)*((_QWORD *)this + 30);
  v12->cAccelEntries = *((_QWORD *)this + 30) != 0;
  return 0;
}

```

## disassembly

```asm
0x140011150  push    rbx
0x140011152  push    rsi
0x140011153  push    rdi
0x140011154  push    r12
0x140011156  push    r14
0x140011158  push    r15
0x14001115a  sub     rsp, 28h
0x14001115e  mov     r12, r9
0x140011161  mov     rbx, r8
0x140011164  mov     rsi, rdx
0x140011167  mov     rdi, rcx
0x14001116a  test    rdx, rdx
0x14001116d  jz      short loc_140011176
0x14001116f  mov     qword ptr [rdx], 0
0x140011176  test    rbx, rbx
0x140011179  jz      short loc_140011182
0x14001117b  mov     qword ptr [r8], 0
0x140011182  test    rsi, rsi
0x140011185  jz      loc_14001130A
0x14001118b  test    rbx, rbx
0x14001118e  jz      loc_14001130A
0x140011194  test    r12, r12
0x140011197  jz      loc_14001130A
0x14001119d  cmp     [rsp+58h+lpRect], 0
0x1400111a6  jz      loc_14001130A
0x1400111ac  lea     r15, [rcx+78h]
0x1400111b0  cmp     qword ptr [r15], 0
0x1400111b4  jnz     short loc_1400111E7
0x1400111b6  mov     [rsp+58h+paccel], 0
0x1400111bf  lea     rcx, [rsp+58h+paccel]
0x1400111c4  call    ?CreateInstance@?$CComObject@VCAxFrameWindow@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CAxFrameWindow>::CreateInstance(ATL::CComObject<ATL::CAxFrameWindow> * *)
0x1400111c9  mov     rcx, [rsp+58h+paccel]
0x1400111ce  add     rcx, 48h ; 'H'
0x1400111d2  mov     rax, [rcx]
0x1400111d5  mov     r8, r15
0x1400111d8  lea     rdx, _GUID_00000116_0000_0000_c000_000000000046
0x1400111df  mov     rax, [rax]
0x1400111e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111e7  lea     r14, [rdi+80h]
0x1400111ee  cmp     qword ptr [r14], 0
0x1400111f2  jnz     short loc_140011226
0x1400111f4  mov     [rsp+58h+paccel], 0
0x1400111fd  lea     rcx, [rsp+58h+paccel]
0x140011202  call    ?CreateInstance@?$CComObject@VCAxUIWindow@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CAxUIWindow>::CreateInstance(ATL::CComObject<ATL::CAxUIWindow> * *)
0x140011207  mov     rcx, [rsp+58h+paccel]
0x14001120c  add     rcx, 48h ; 'H'
0x140011210  mov     rax, [rcx]
0x140011213  mov     r8, r14
0x140011216  lea     rdx, _GUID_00000115_0000_0000_c000_000000000046
0x14001121d  mov     rax, [rax]
0x140011220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011225  nop
0x140011226  mov     rax, [r15]
0x140011229  mov     [rsi], rax
0x14001122c  mov     rcx, [r15]
0x14001122f  test    rcx, rcx
0x140011232  jz      short loc_140011241
0x140011234  mov     rax, [rcx]
0x140011237  mov     rax, [rax+8]
0x14001123b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011240  nop
0x140011241  mov     rax, [r14]
0x140011244  mov     [rbx], rax
0x140011247  mov     rcx, [r14]
0x14001124a  test    rcx, rcx
0x14001124d  jz      short loc_14001125C
0x14001124f  mov     rax, [rcx]
0x140011252  mov     rax, [rax+8]
0x140011256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001125b  nop
0x14001125c  mov     rdx, r12; lpRect
0x14001125f  mov     rcx, [rdi-50h]; hWnd
0x140011263  call    cs:__imp_GetClientRect
0x14001126a  nop     dword ptr [rax+rax+00h]
0x14001126f  mov     rdx, [rsp+58h+lpRect]; lpRect
0x140011277  mov     rcx, [rdi-50h]; hWnd
0x14001127b  call    cs:__imp_GetClientRect
0x140011282  nop     dword ptr [rax+rax+00h]
0x140011287  cmp     qword ptr [rdi+0F0h], 0
0x14001128f  jnz     short loc_1400112BB
0x140011291  mov     dword ptr [rsp+58h+paccel], 0
0x140011299  xor     eax, eax
0x14001129b  mov     word ptr [rsp+58h+paccel+4], ax
0x1400112a0  lea     edx, [rax+1]; cAccel
0x1400112a3  lea     rcx, [rsp+58h+paccel]; paccel
0x1400112a8  call    cs:__imp_CreateAcceleratorTableW
0x1400112af  nop     dword ptr [rax+rax+00h]
0x1400112b4  mov     [rdi+0F0h], rax
0x1400112bb  mov     rbx, [rsp+58h+arg_28]
0x1400112c3  mov     dword ptr [rbx], 20h ; ' '
0x1400112c9  mov     eax, [rdi+0C0h]
0x1400112cf  shr     eax, 2
0x1400112d2  and     eax, 1
0x1400112d5  mov     [rbx+4], eax
0x1400112d8  mov     rcx, [rdi-50h]; hWnd
0x1400112dc  call    cs:__imp_GetParent
0x1400112e3  nop     dword ptr [rax+rax+00h]
0x1400112e8  mov     [rbx+8], rax
0x1400112ec  mov     rax, [rdi+0F0h]
0x1400112f3  mov     [rbx+10h], rax
0x1400112f7  xor     eax, eax
0x1400112f9  cmp     [rdi+0F0h], rax
0x140011300  setnz   al
0x140011303  mov     [rbx+18h], eax
0x140011306  xor     eax, eax
0x140011308  jmp     short loc_14001130F
0x14001130a  mov     eax, 80004003h
0x14001130f  add     rsp, 28h
0x140011313  pop     r15
0x140011315  pop     r14
0x140011317  pop     r12
0x140011319  pop     rdi
0x14001131a  pop     rsi
0x14001131b  pop     rbx
0x14001131c  retn
```
