# COleObject::DrawFrame(CDisplay const *,HDC__ *,tagRECT *)

- ea: `0x1800553fc`
- end: `0x18005564b`
- name: `?DrawFrame@COleObject@@AEAAXPEBVCDisplay@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `591`
- prototype: `void(COleObject *__hidden this, const struct CDisplay *, HDC, struct tagRECT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18004b3ac`
- `0x180055c28`

## callees

- `0x1800486b0`
- `0x1800553fc`
- `0x180055654`
- `0x180093c00`

## import_xrefs

- `USER32!InvertRect` at `0x180055455`
- `USER32!InvertRect` at `0x180055455`
- `USER32!CopyRect` at `0x180055439`
- `USER32!CopyRect` at `0x180055439`
- `USER32!InflateRect` at `0x180055553`
- `USER32!InflateRect` at `0x180055553`
- `GDI32!GetCurrentObject` at `0x180055515`
- `GDI32!GetCurrentObject` at `0x180055515`
- `GDI32!GetStockObject` at `0x180055488`
- `GDI32!GetStockObject` at `0x180055488`
- `GDI32!SetROP2` at `0x180055477`
- `GDI32!SetROP2` at `0x180055477`
- `GDI32!SelectObject` at `0x18005549a`
- `GDI32!SelectObject` at `0x18005549a`
- `GDI32!RestoreDC` at `0x1800554cd`
- `GDI32!RestoreDC` at `0x1800554cd`
- `GDI32!SaveDC` at `0x180055463`
- `GDI32!SaveDC` at `0x180055463`
- `GDI32!SetBkMode` at `0x1800554f9`
- `GDI32!SetBkMode` at `0x180055627`
- `GDI32!SetBkMode` at `0x1800554f9`
- `GDI32!SetBkMode` at `0x180055627`
- `GDI32!Rectangle` at `0x1800554bb`
- `GDI32!Rectangle` at `0x1800554bb`

## pseudocode

```c
void __fastcall COleObject::DrawFrame(COleObject *this, const struct CDisplay *a2, HDC a3, struct tagRECT *a4)
{
  HGDIOBJ StockObject; // rax
  int v7; // eax
  int v8; // esi
  HGDIOBJ CurrentObject; // rax
  LONG left; // ebx
  COleObject *v11; // rcx
  COleObject *v12; // rcx
  COleObject *v13; // rcx
  int v14; // eax
  int v15; // ebx
  COleObject *v16; // rcx
  int v17; // ebx
  COleObject *v18; // rcx
  COleObject *v19; // rcx
  COleObject *v20; // rcx
  struct tagRECT rcDst; // [rsp+30h] [rbp-30h] BYREF
  __int128 v22; // [rsp+40h] [rbp-20h] BYREF

  if ( (*((_BYTE *)this + 144) & 0x40) == 0 )
  {
    rcDst = 0;
    CopyRect(&rcDst, a4);
    if ( (*((_BYTE *)this + 144) & 4) != 0 )
    {
      InvertRect(a3, &rcDst);
    }
    else
    {
      SaveDC(a3);
      SetROP2(a3, 6);
      StockObject = GetStockObject(5);
      SelectObject(a3, StockObject);
      Rectangle(a3, rcDst.left, rcDst.top, rcDst.right, rcDst.bottom);
      RestoreDC(a3, -1);
    }
    if ( (*((_BYTE *)this + 144) & 1) != 0 )
    {
      v22 = 0;
      v7 = SetBkMode(a3, 1);
      *((_WORD *)this + 78) = 1;
      v8 = v7;
      CurrentObject = GetCurrentObject(a3, 1u);
      if ( (unsigned int)CW32System::GetObjectW(CurrentObject, 16, &v22) )
      {
        if ( DWORD1(v22) )
          *((_WORD *)this + 78) = WORD2(v22);
      }
      InflateRect(&rcDst, -*((__int16 *)this + 78), -*((__int16 *)this + 78));
      left = rcDst.left;
      COleObject::DrawHandle(v11, a3, rcDst.left, rcDst.top);
      COleObject::DrawHandle(v12, a3, left, rcDst.top + (rcDst.bottom - rcDst.top - 6) / 2);
      COleObject::DrawHandle(v13, a3, left, rcDst.bottom - 6);
      v14 = (rcDst.right - rcDst.left - 6) / 2;
      v15 = v14 + rcDst.left;
      COleObject::DrawHandle((COleObject *)(unsigned int)rcDst.left, a3, v14 + rcDst.left, rcDst.top);
      COleObject::DrawHandle(v16, a3, v15, rcDst.bottom - 6);
      v17 = rcDst.right - 6;
      COleObject::DrawHandle(v18, a3, rcDst.right - 6, rcDst.top);
      COleObject::DrawHandle(v19, a3, v17, rcDst.top + (rcDst.bottom - rcDst.top - 6) / 2);
      COleObject::DrawHandle(v20, a3, v17, rcDst.bottom - 6);
      SetBkMode(a3, v8);
    }
  }
}

```

## disassembly

```asm
0x1800553fc  push    rbp
0x1800553fe  push    rbx
0x1800553ff  push    rsi
0x180055400  push    rdi
0x180055401  push    r14
0x180055403  mov     rbp, rsp
0x180055406  sub     rsp, 60h
0x18005540a  mov     rax, cs:__security_cookie
0x180055411  xor     rax, rsp
0x180055414  mov     [rbp+var_10], rax
0x180055418  test    byte ptr [rcx+90h], 40h
0x18005541f  mov     rdi, r8
0x180055422  mov     rbx, rcx
0x180055425  jnz     loc_180055633
0x18005542b  xorps   xmm0, xmm0
0x18005542e  lea     rcx, [rbp+rcDst]; lprcDst
0x180055432  mov     rdx, r9; lprcSrc
0x180055435  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180055439  call    cs:__imp_CopyRect
0x180055440  nop     dword ptr [rax+rax+00h]
0x180055445  test    byte ptr [rbx+90h], 4
0x18005544c  mov     rcx, rdi; hdc
0x18005544f  jz      short loc_180055463
0x180055451  lea     rdx, [rbp+rcDst]; lprc
0x180055455  call    cs:__imp_InvertRect
0x18005545c  nop     dword ptr [rax+rax+00h]
0x180055461  jmp     short loc_1800554D9
0x180055463  call    cs:__imp_SaveDC
0x18005546a  nop     dword ptr [rax+rax+00h]
0x18005546f  mov     edx, 6; rop2
0x180055474  mov     rcx, rdi; hdc
0x180055477  call    cs:__imp_SetROP2
0x18005547e  nop     dword ptr [rax+rax+00h]
0x180055483  mov     ecx, 5; i
0x180055488  call    cs:__imp_GetStockObject
0x18005548f  nop     dword ptr [rax+rax+00h]
0x180055494  mov     rdx, rax; h
0x180055497  mov     rcx, rdi; hdc
0x18005549a  call    cs:__imp_SelectObject
0x1800554a1  nop     dword ptr [rax+rax+00h]
0x1800554a6  mov     eax, [rbp+rcDst.bottom]
0x1800554a9  mov     rcx, rdi; hdc
0x1800554ac  mov     r9d, [rbp+rcDst.right]; right
0x1800554b0  mov     r8d, [rbp+rcDst.top]; top
0x1800554b4  mov     edx, [rbp+rcDst.left]; left
0x1800554b7  mov     [rsp+60h+bottom], eax; bottom
0x1800554bb  call    cs:__imp_Rectangle
0x1800554c2  nop     dword ptr [rax+rax+00h]
0x1800554c7  or      edx, 0FFFFFFFFh; nSavedDC
0x1800554ca  mov     rcx, rdi; hdc
0x1800554cd  call    cs:__imp_RestoreDC
0x1800554d4  nop     dword ptr [rax+rax+00h]
0x1800554d9  mov     r14d, 1
0x1800554df  test    [rbx+90h], r14b
0x1800554e6  jz      loc_180055633
0x1800554ec  xorps   xmm0, xmm0
0x1800554ef  mov     edx, r14d; mode
0x1800554f2  mov     rcx, rdi; hdc
0x1800554f5  movups  [rbp+var_20], xmm0
0x1800554f9  call    cs:__imp_SetBkMode
0x180055500  nop     dword ptr [rax+rax+00h]
0x180055505  mov     edx, r14d; type
0x180055508  mov     [rbx+9Ch], r14w
0x180055510  mov     rcx, rdi; hdc
0x180055513  mov     esi, eax
0x180055515  call    cs:__imp_GetCurrentObject
0x18005551c  nop     dword ptr [rax+rax+00h]
0x180055521  mov     rcx, rax; void *
0x180055524  lea     r8, [rbp+var_20]; void *
0x180055528  lea     edx, [r14+0Fh]; int
0x18005552c  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x180055531  test    eax, eax
0x180055533  jz      short loc_180055543
0x180055535  mov     eax, dword ptr [rbp+var_20+4]
0x180055538  test    eax, eax
0x18005553a  jz      short loc_180055543
0x18005553c  mov     [rbx+9Ch], ax
0x180055543  movsx   edx, word ptr [rbx+9Ch]
0x18005554a  lea     rcx, [rbp+rcDst]; lprc
0x18005554e  neg     edx; dx
0x180055550  mov     r8d, edx; dy
0x180055553  call    cs:__imp_InflateRect
0x18005555a  nop     dword ptr [rax+rax+00h]
0x18005555f  mov     ebx, [rbp+rcDst.left]
0x180055562  mov     rdx, rdi; HDC
0x180055565  mov     r9d, [rbp+rcDst.top]; int
0x180055569  mov     r8d, ebx; int
0x18005556c  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180055571  mov     eax, [rbp+rcDst.bottom]
0x180055574  mov     r14d, 2
0x18005557a  sub     eax, [rbp+rcDst.top]
0x18005557d  mov     r8d, ebx; int
0x180055580  sub     eax, 6
0x180055583  cdq
0x180055584  idiv    r14d
0x180055587  mov     rdx, rdi; HDC
0x18005558a  add     eax, [rbp+rcDst.top]
0x18005558d  mov     r9d, eax; int
0x180055590  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180055595  mov     r9d, [rbp+rcDst.bottom]
0x180055599  mov     r8d, ebx; int
0x18005559c  add     r9d, 0FFFFFFFAh; int
0x1800555a0  mov     rdx, rdi; HDC
0x1800555a3  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800555a8  mov     ecx, [rbp+rcDst.left]; this
0x1800555ab  mov     eax, [rbp+rcDst.right]
0x1800555ae  mov     r9d, [rbp+rcDst.top]; int
0x1800555b2  sub     eax, ecx
0x1800555b4  sub     eax, 6
0x1800555b7  cdq
0x1800555b8  idiv    r14d
0x1800555bb  mov     rdx, rdi; HDC
0x1800555be  lea     ebx, [rax+rcx]
0x1800555c1  mov     r8d, ebx; int
0x1800555c4  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800555c9  mov     r9d, [rbp+rcDst.bottom]
0x1800555cd  mov     r8d, ebx; int
0x1800555d0  add     r9d, 0FFFFFFFAh; int
0x1800555d4  mov     rdx, rdi; HDC
0x1800555d7  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800555dc  mov     ebx, [rbp+rcDst.right]
0x1800555df  mov     rdx, rdi; HDC
0x1800555e2  mov     r9d, [rbp+rcDst.top]; int
0x1800555e6  add     ebx, 0FFFFFFFAh
0x1800555e9  mov     r8d, ebx; int
0x1800555ec  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800555f1  mov     eax, [rbp+rcDst.bottom]
0x1800555f4  mov     r8d, ebx; int
0x1800555f7  sub     eax, [rbp+rcDst.top]
0x1800555fa  sub     eax, 6
0x1800555fd  cdq
0x1800555fe  idiv    r14d
0x180055601  mov     rdx, rdi; HDC
0x180055604  add     eax, [rbp+rcDst.top]
0x180055607  mov     r9d, eax; int
0x18005560a  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x18005560f  mov     r9d, [rbp+rcDst.bottom]
0x180055613  mov     r8d, ebx; int
0x180055616  add     r9d, 0FFFFFFFAh; int
0x18005561a  mov     rdx, rdi; HDC
0x18005561d  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180055622  mov     edx, esi; mode
0x180055624  mov     rcx, rdi; hdc
0x180055627  call    cs:__imp_SetBkMode
0x18005562e  nop     dword ptr [rax+rax+00h]
0x180055633  mov     rcx, [rbp+var_10]
0x180055637  xor     rcx, rsp; StackCookie
0x18005563a  call    __security_check_cookie
0x18005563f  add     rsp, 60h
0x180055643  pop     r14
0x180055645  pop     rdi
0x180055646  pop     rsi
0x180055647  pop     rbx
0x180055648  pop     rbp
0x180055649  retn
```
