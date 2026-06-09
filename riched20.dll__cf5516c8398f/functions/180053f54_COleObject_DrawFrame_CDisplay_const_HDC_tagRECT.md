# COleObject::DrawFrame(CDisplay const *,HDC__ *,tagRECT *)

- ea: `0x180053f54`
- end: `0x18005415a`
- name: `?DrawFrame@COleObject@@AEAAXPEBVCDisplay@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `518`
- prototype: `void(COleObject *__hidden this, const struct CDisplay *, HDC, struct tagRECT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18004a23c`
- `0x180054714`

## callees

- `0x1800475c4`
- `0x180053f54`
- `0x180054160`
- `0x180091140`

## import_xrefs

- `USER32!InvertRect` at `0x180053fa7`
- `USER32!InvertRect` at `0x180053fa7`
- `USER32!CopyRect` at `0x180053f91`
- `USER32!CopyRect` at `0x180053f91`
- `USER32!InflateRect` at `0x18005406f`
- `USER32!InflateRect` at `0x18005406f`
- `GDI32!GetCurrentObject` at `0x180054037`
- `GDI32!GetCurrentObject` at `0x180054037`
- `GDI32!GetStockObject` at `0x180053fc8`
- `GDI32!GetStockObject` at `0x180053fc8`
- `GDI32!SetROP2` at `0x180053fbd`
- `GDI32!SetROP2` at `0x180053fbd`
- `GDI32!SelectObject` at `0x180053fd4`
- `GDI32!SelectObject` at `0x180053fd4`
- `GDI32!RestoreDC` at `0x180053ffb`
- `GDI32!RestoreDC` at `0x180053ffb`
- `GDI32!SaveDC` at `0x180053faf`
- `GDI32!SaveDC` at `0x180053faf`
- `GDI32!SetBkMode` at `0x180054021`
- `GDI32!SetBkMode` at `0x18005413d`
- `GDI32!SetBkMode` at `0x180054021`
- `GDI32!SetBkMode` at `0x18005413d`
- `GDI32!Rectangle` at `0x180053fef`
- `GDI32!Rectangle` at `0x180053fef`

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
0x180053f54  push    rbp
0x180053f56  push    rbx
0x180053f57  push    rsi
0x180053f58  push    rdi
0x180053f59  push    r14
0x180053f5b  mov     rbp, rsp
0x180053f5e  sub     rsp, 60h
0x180053f62  mov     rax, cs:__security_cookie
0x180053f69  xor     rax, rsp
0x180053f6c  mov     [rbp+var_10], rax
0x180053f70  test    byte ptr [rcx+90h], 40h
0x180053f77  mov     rdi, r8
0x180053f7a  mov     rbx, rcx
0x180053f7d  jnz     loc_180054143
0x180053f83  xorps   xmm0, xmm0
0x180053f86  lea     rcx, [rbp+rcDst]; lprcDst
0x180053f8a  mov     rdx, r9; lprcSrc
0x180053f8d  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180053f91  call    cs:__imp_CopyRect
0x180053f97  test    byte ptr [rbx+90h], 4
0x180053f9e  mov     rcx, rdi; hdc
0x180053fa1  jz      short loc_180053FAF
0x180053fa3  lea     rdx, [rbp+rcDst]; lprc
0x180053fa7  call    cs:__imp_InvertRect
0x180053fad  jmp     short loc_180054001
0x180053faf  call    cs:__imp_SaveDC
0x180053fb5  mov     edx, 6; rop2
0x180053fba  mov     rcx, rdi; hdc
0x180053fbd  call    cs:__imp_SetROP2
0x180053fc3  mov     ecx, 5; i
0x180053fc8  call    cs:__imp_GetStockObject
0x180053fce  mov     rdx, rax; h
0x180053fd1  mov     rcx, rdi; hdc
0x180053fd4  call    cs:__imp_SelectObject
0x180053fda  mov     eax, [rbp+rcDst.bottom]
0x180053fdd  mov     rcx, rdi; hdc
0x180053fe0  mov     r9d, [rbp+rcDst.right]; right
0x180053fe4  mov     r8d, [rbp+rcDst.top]; top
0x180053fe8  mov     edx, [rbp+rcDst.left]; left
0x180053feb  mov     [rsp+60h+bottom], eax; bottom
0x180053fef  call    cs:__imp_Rectangle
0x180053ff5  or      edx, 0FFFFFFFFh; nSavedDC
0x180053ff8  mov     rcx, rdi; hdc
0x180053ffb  call    cs:__imp_RestoreDC
0x180054001  mov     r14d, 1
0x180054007  test    [rbx+90h], r14b
0x18005400e  jz      loc_180054143
0x180054014  xorps   xmm0, xmm0
0x180054017  mov     edx, r14d; mode
0x18005401a  mov     rcx, rdi; hdc
0x18005401d  movups  [rbp+var_20], xmm0
0x180054021  call    cs:__imp_SetBkMode
0x180054027  mov     edx, r14d; type
0x18005402a  mov     [rbx+9Ch], r14w
0x180054032  mov     rcx, rdi; hdc
0x180054035  mov     esi, eax
0x180054037  call    cs:__imp_GetCurrentObject
0x18005403d  mov     rcx, rax; void *
0x180054040  lea     r8, [rbp+var_20]; void *
0x180054044  lea     edx, [r14+0Fh]; int
0x180054048  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x18005404d  test    eax, eax
0x18005404f  jz      short loc_18005405F
0x180054051  mov     eax, dword ptr [rbp+var_20+4]
0x180054054  test    eax, eax
0x180054056  jz      short loc_18005405F
0x180054058  mov     [rbx+9Ch], ax
0x18005405f  movsx   edx, word ptr [rbx+9Ch]
0x180054066  lea     rcx, [rbp+rcDst]; lprc
0x18005406a  neg     edx; dx
0x18005406c  mov     r8d, edx; dy
0x18005406f  call    cs:__imp_InflateRect
0x180054075  mov     ebx, [rbp+rcDst.left]
0x180054078  mov     rdx, rdi; HDC
0x18005407b  mov     r9d, [rbp+rcDst.top]; int
0x18005407f  mov     r8d, ebx; int
0x180054082  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180054087  mov     eax, [rbp+rcDst.bottom]
0x18005408a  mov     r14d, 2
0x180054090  sub     eax, [rbp+rcDst.top]
0x180054093  mov     r8d, ebx; int
0x180054096  sub     eax, 6
0x180054099  cdq
0x18005409a  idiv    r14d
0x18005409d  mov     rdx, rdi; HDC
0x1800540a0  add     eax, [rbp+rcDst.top]
0x1800540a3  mov     r9d, eax; int
0x1800540a6  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800540ab  mov     r9d, [rbp+rcDst.bottom]
0x1800540af  mov     r8d, ebx; int
0x1800540b2  add     r9d, 0FFFFFFFAh; int
0x1800540b6  mov     rdx, rdi; HDC
0x1800540b9  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800540be  mov     ecx, [rbp+rcDst.left]; this
0x1800540c1  mov     eax, [rbp+rcDst.right]
0x1800540c4  mov     r9d, [rbp+rcDst.top]; int
0x1800540c8  sub     eax, ecx
0x1800540ca  sub     eax, 6
0x1800540cd  cdq
0x1800540ce  idiv    r14d
0x1800540d1  mov     rdx, rdi; HDC
0x1800540d4  lea     ebx, [rax+rcx]
0x1800540d7  mov     r8d, ebx; int
0x1800540da  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800540df  mov     r9d, [rbp+rcDst.bottom]
0x1800540e3  mov     r8d, ebx; int
0x1800540e6  add     r9d, 0FFFFFFFAh; int
0x1800540ea  mov     rdx, rdi; HDC
0x1800540ed  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x1800540f2  mov     ebx, [rbp+rcDst.right]
0x1800540f5  mov     rdx, rdi; HDC
0x1800540f8  mov     r9d, [rbp+rcDst.top]; int
0x1800540fc  add     ebx, 0FFFFFFFAh
0x1800540ff  mov     r8d, ebx; int
0x180054102  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180054107  mov     eax, [rbp+rcDst.bottom]
0x18005410a  mov     r8d, ebx; int
0x18005410d  sub     eax, [rbp+rcDst.top]
0x180054110  sub     eax, 6
0x180054113  cdq
0x180054114  idiv    r14d
0x180054117  mov     rdx, rdi; HDC
0x18005411a  add     eax, [rbp+rcDst.top]
0x18005411d  mov     r9d, eax; int
0x180054120  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180054125  mov     r9d, [rbp+rcDst.bottom]
0x180054129  mov     r8d, ebx; int
0x18005412c  add     r9d, 0FFFFFFFAh; int
0x180054130  mov     rdx, rdi; HDC
0x180054133  call    ?DrawHandle@COleObject@@AEAAXPEAUHDC__@@HH@Z; COleObject::DrawHandle(HDC__ *,int,int)
0x180054138  mov     edx, esi; mode
0x18005413a  mov     rcx, rdi; hdc
0x18005413d  call    cs:__imp_SetBkMode
0x180054143  mov     rcx, [rbp+var_10]
0x180054147  xor     rcx, rsp; StackCookie
0x18005414a  call    __security_check_cookie
0x18005414f  add     rsp, 60h
0x180054153  pop     r14
0x180054155  pop     rdi
0x180054156  pop     rsi
0x180054157  pop     rbx
0x180054158  pop     rbp
0x180054159  retn
```
