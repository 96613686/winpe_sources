# DirectUI::HWNDHost::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)

- ea: `0x180178360`
- end: `0x1801784cb`
- name: `?Paint@HWNDHost@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z`
- size: `363`
- prototype: `void __usercall(DirectUI::HWNDHost *__hidden this@<rcx>, HDC@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18009a490`
- `0x180114520`
- `0x180178360`
- `0x1801784d4`

## import_xrefs

- `GDI32!DeleteObject` at `0x180178444`
- `GDI32!DeleteObject` at `0x180178444`
- `GDI32!RectVisible` at `0x1801783c9`
- `GDI32!RectVisible` at `0x1801783c9`
- `GDI32!SelectObject` at `0x18017841a`
- `GDI32!SelectObject` at `0x18017843b`
- `GDI32!SelectObject` at `0x18017841a`
- `GDI32!SelectObject` at `0x18017843b`
- `GDI32!DeleteDC` at `0x18017844d`
- `GDI32!DeleteDC` at `0x18017844d`
- `GDI32!CreateCompatibleDC` at `0x1801783e3`
- `GDI32!CreateCompatibleDC` at `0x1801783e3`
- `GDI32!CreateCompatibleBitmap` at `0x180178406`
- `GDI32!CreateCompatibleBitmap` at `0x180178406`
- `GDI32!OffsetWindowOrgEx` at `0x18017846d`
- `GDI32!OffsetWindowOrgEx` at `0x18017846d`
- `GDI32!SetWindowOrgEx` at `0x18017849b`
- `GDI32!SetWindowOrgEx` at `0x18017849b`
- `USER32!SendMessageW` at `0x180178488`
- `USER32!SendMessageW` at `0x180178488`
- `USER32!UpdateWindow` at `0x1801784ac`
- `USER32!UpdateWindow` at `0x1801784ac`

## pseudocode

```c
void __fastcall DirectUI::HWNDHost::Paint(
        HWND *this,
        HDC a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        struct tagRECT *a5)
{
  HWND v7; // rcx
  HDC CompatibleDC; // r14
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v10; // r15
  HGDIOBJ v11; // rbx
  struct tagPOINT pt; // [rsp+30h] [rbp-28h] BYREF
  RECT rect; // [rsp+38h] [rbp-20h] BYREF

  rect = 0;
  DirectUI::Element::Paint((DirectUI::Element *)this, a2, a3, a4, a5, &rect);
  v7 = this[26];
  if ( v7 )
  {
    if ( *((_BYTE *)this + 202) )
    {
      if ( RectVisible(a2, &rect) )
      {
        if ( ((_BYTE)this[19] & 0x40) != 0 )
        {
          CompatibleDC = CreateCompatibleDC(a2);
          if ( CompatibleDC )
          {
            CompatibleBitmap = CreateCompatibleBitmap(a2, rect.right - rect.left, rect.bottom - rect.top);
            v10 = CompatibleBitmap;
            if ( CompatibleBitmap )
            {
              v11 = SelectObject(CompatibleDC, CompatibleBitmap);
              DirectUI::HWNDHost::PrintRTLControl((DirectUI::HWNDHost *)this, a2, CompatibleDC, &rect);
              SelectObject(CompatibleDC, v11);
              DeleteObject(v10);
            }
            DeleteDC(CompatibleDC);
          }
        }
        else
        {
          pt = 0;
          OffsetWindowOrgEx(a2, -rect.left, -rect.top, &pt);
          SendMessageW(this[27], 0x317u, (WPARAM)a2, 30);
          SetWindowOrgEx(a2, pt.x, pt.y, 0);
        }
      }
    }
    else if ( ((_BYTE)this[37] & 0x10) != 0 )
    {
      UpdateWindow(v7);
    }
  }
}

```

## disassembly

```asm
0x180178360  push    rbp
0x180178362  push    rbx
0x180178363  push    rsi
0x180178364  push    rdi
0x180178365  push    r14
0x180178367  push    r15
0x180178369  mov     rbp, rsp
0x18017836c  sub     rsp, 58h
0x180178370  mov     rax, cs:__security_cookie
0x180178377  xor     rax, rsp
0x18017837a  mov     [rbp+var_10], rax
0x18017837e  mov     rax, [rbp+arg_20]
0x180178382  mov     rsi, rcx
0x180178385  lea     rcx, [rbp+rect]
0x180178389  xorps   xmm0, xmm0
0x18017838c  mov     [rsp+58h+var_30], rcx; struct tagRECT *
0x180178391  mov     rdi, rdx
0x180178394  mov     rcx, rsi; this
0x180178397  mov     [rsp+58h+var_38], rax; struct tagRECT *
0x18017839c  movups  xmmword ptr [rbp+rect.left], xmm0
0x1801783a0  call    ?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z; DirectUI::Element::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)
0x1801783a5  mov     rcx, [rsi+0D0h]; hWnd
0x1801783ac  test    rcx, rcx
0x1801783af  jz      loc_1801784B2
0x1801783b5  cmp     byte ptr [rsi+0CAh], 0
0x1801783bc  jz      loc_1801784A3
0x1801783c2  lea     rdx, [rbp+rect]; lprect
0x1801783c6  mov     rcx, rdi; hdc
0x1801783c9  call    cs:__imp_RectVisible
0x1801783cf  test    eax, eax
0x1801783d1  jz      loc_1801784B2
0x1801783d7  test    byte ptr [rsi+98h], 40h
0x1801783de  mov     rcx, rdi; hdc
0x1801783e1  jz      short loc_180178455
0x1801783e3  call    cs:__imp_CreateCompatibleDC
0x1801783e9  mov     r14, rax
0x1801783ec  test    rax, rax
0x1801783ef  jz      loc_1801784B2
0x1801783f5  mov     r8d, [rbp+rect.bottom]
0x1801783f9  mov     rcx, rdi; hdc
0x1801783fc  mov     edx, [rbp+rect.right]
0x1801783ff  sub     r8d, [rbp+rect.top]; cy
0x180178403  sub     edx, [rbp+rect.left]; cx
0x180178406  call    cs:__imp_CreateCompatibleBitmap
0x18017840c  mov     r15, rax
0x18017840f  test    rax, rax
0x180178412  jz      short loc_18017844A
0x180178414  mov     rdx, rax; h
0x180178417  mov     rcx, r14; hdc
0x18017841a  call    cs:__imp_SelectObject
0x180178420  lea     r9, [rbp+rect]; struct tagRECT *
0x180178424  mov     r8, r14; HDC
0x180178427  mov     rdx, rdi; HDC
0x18017842a  mov     rcx, rsi; this
0x18017842d  mov     rbx, rax
0x180178430  call    ?PrintRTLControl@HWNDHost@DirectUI@@IEAAXPEAUHDC__@@0AEBUtagRECT@@@Z; DirectUI::HWNDHost::PrintRTLControl(HDC__ *,HDC__ *,tagRECT const &)
0x180178435  mov     rdx, rbx; h
0x180178438  mov     rcx, r14; hdc
0x18017843b  call    cs:__imp_SelectObject
0x180178441  mov     rcx, r15; ho
0x180178444  call    cs:__imp_DeleteObject
0x18017844a  mov     rcx, r14; hdc
0x18017844d  call    cs:__imp_DeleteDC
0x180178453  jmp     short loc_1801784B2
0x180178455  mov     r8d, [rbp+rect.top]
0x180178459  lea     r9, [rbp+pt]; lppt
0x18017845d  mov     edx, [rbp+rect.left]
0x180178460  neg     r8d; y
0x180178463  neg     edx; x
0x180178465  mov     qword ptr [rbp+pt.x], 0
0x18017846d  call    cs:__imp_OffsetWindowOrgEx
0x180178473  mov     rcx, [rsi+0D8h]; hWnd
0x18017847a  mov     r9d, 1Eh; lParam
0x180178480  mov     r8, rdi; wParam
0x180178483  mov     edx, 317h; Msg
0x180178488  call    cs:__imp_SendMessageW
0x18017848e  mov     r8d, [rbp+pt.y]; y
0x180178492  xor     r9d, r9d; lppt
0x180178495  mov     edx, [rbp+pt.x]; x
0x180178498  mov     rcx, rdi; hdc
0x18017849b  call    cs:__imp_SetWindowOrgEx
0x1801784a1  jmp     short loc_1801784B2
0x1801784a3  test    byte ptr [rsi+128h], 10h
0x1801784aa  jz      short loc_1801784B2
0x1801784ac  call    cs:__imp_UpdateWindow
0x1801784b2  mov     rcx, [rbp+var_10]
0x1801784b6  xor     rcx, rsp; StackCookie
0x1801784b9  call    __security_check_cookie
0x1801784be  add     rsp, 58h
0x1801784c2  pop     r15
0x1801784c4  pop     r14
0x1801784c6  pop     rdi
0x1801784c7  pop     rsi
0x1801784c8  pop     rbx
0x1801784c9  pop     rbp
0x1801784ca  retn
```
