# DirectUI::FlipBitmapDDB(HBITMAP__ *,HBITMAP__ * *)

- ea: `0x1801650e0`
- end: `0x18016525b`
- name: `?FlipBitmapDDB@DirectUI@@YAHPEAUHBITMAP__@@PEAPEAU2@@Z`
- size: `379`
- prototype: `__int64 __fastcall(HGDIOBJ h, HBITMAP, HBITMAP *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18016502c`
- `0x180165264`

## callees

- `0x1801650e0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180165217`
- `GDI32!DeleteObject` at `0x180165217`
- `GDI32!GetObjectW` at `0x180165159`
- `GDI32!GetObjectW` at `0x180165159`
- `GDI32!SelectObject` at `0x18016518b`
- `GDI32!SelectObject` at `0x18016519a`
- `GDI32!SelectObject` at `0x1801651ed`
- `GDI32!SelectObject` at `0x1801651f9`
- `GDI32!SelectObject` at `0x18016518b`
- `GDI32!SelectObject` at `0x18016519a`
- `GDI32!SelectObject` at `0x1801651ed`
- `GDI32!SelectObject` at `0x1801651f9`
- `GDI32!DeleteDC` at `0x180165230`
- `GDI32!DeleteDC` at `0x18016523e`
- `GDI32!DeleteDC` at `0x180165230`
- `GDI32!DeleteDC` at `0x18016523e`
- `GDI32!CreateCompatibleDC` at `0x180165126`
- `GDI32!CreateCompatibleDC` at `0x18016513b`
- `GDI32!CreateCompatibleDC` at `0x180165126`
- `GDI32!CreateCompatibleDC` at `0x18016513b`
- `GDI32!CreateCompatibleBitmap` at `0x180165173`
- `GDI32!CreateCompatibleBitmap` at `0x180165173`
- `GDI32!StretchBlt` at `0x1801651df`
- `GDI32!StretchBlt` at `0x1801651df`
- `USER32!GetDC` at `0x18016510f`
- `USER32!GetDC` at `0x18016510f`
- `USER32!ReleaseDC` at `0x180165222`
- `USER32!ReleaseDC` at `0x180165222`

## pseudocode

```c
__int64 __fastcall DirectUI::FlipBitmapDDB(HGDIOBJ h, _QWORD *a2, HBITMAP *a3)
{
  unsigned int v4; // r15d
  HDC DC; // rax
  HDC v7; // r12
  HDC CompatibleDC; // rbp
  HDC hdcSrc; // r14
  HBITMAP CompatibleBitmap; // rbx
  HGDIOBJ v11; // rsi
  HGDIOBJ v12; // rdi
  BOOL v13; // ebx
  HGDIOBJ v14; // rax
  _OWORD pv[6]; // [rsp+60h] [rbp-68h] BYREF

  v4 = 0;
  pv[0] = 0;
  *a2 = 0;
  pv[1] = 0;
  DC = GetDC(0);
  v7 = DC;
  if ( DC )
  {
    CompatibleDC = 0;
    hdcSrc = CreateCompatibleDC(DC);
    if ( hdcSrc )
    {
      CompatibleDC = CreateCompatibleDC(v7);
      if ( CompatibleDC )
      {
        if ( GetObjectW(h, 32, pv) )
        {
          CompatibleBitmap = CreateCompatibleBitmap(v7, SDWORD1(pv[0]), SDWORD2(pv[0]));
          if ( CompatibleBitmap )
          {
            v11 = SelectObject(hdcSrc, h);
            v12 = SelectObject(CompatibleDC, CompatibleBitmap);
            v13 = StretchBlt(
                    CompatibleDC,
                    0,
                    0,
                    SDWORD1(pv[0]),
                    SDWORD2(pv[0]),
                    hdcSrc,
                    DWORD1(pv[0]) - 1,
                    0,
                    -DWORD1(pv[0]),
                    SDWORD2(pv[0]),
                    0xCC0020u);
            SelectObject(hdcSrc, v11);
            v14 = SelectObject(CompatibleDC, v12);
            if ( v13 )
            {
              *a2 = v14;
              v4 = 1;
            }
            else if ( v14 )
            {
              DeleteObject(v14);
            }
          }
        }
      }
    }
    ReleaseDC(0, v7);
    if ( hdcSrc )
      DeleteDC(hdcSrc);
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
  }
  return v4;
}

```

## disassembly

```asm
0x1801650e0  push    rbx
0x1801650e2  push    rbp
0x1801650e3  push    rsi
0x1801650e4  push    rdi
0x1801650e5  push    r12
0x1801650e7  push    r13
0x1801650e9  push    r14
0x1801650eb  push    r15
0x1801650ed  sub     rsp, 88h
0x1801650f4  xorps   xmm0, xmm0
0x1801650f7  mov     rdi, rcx
0x1801650fa  xor     r15d, r15d
0x1801650fd  xor     ecx, ecx; hWnd
0x1801650ff  movups  [rsp+0C8h+pv], xmm0
0x180165104  mov     [rdx], r15
0x180165107  mov     r13, rdx
0x18016510a  movups  [rsp+0C8h+var_58], xmm0
0x18016510f  call    cs:__imp_GetDC
0x180165115  mov     r12, rax
0x180165118  test    rax, rax
0x18016511b  jz      loc_180165244
0x180165121  mov     rcx, rax; hdc
0x180165124  xor     ebp, ebp
0x180165126  call    cs:__imp_CreateCompatibleDC
0x18016512c  mov     r14, rax
0x18016512f  test    rax, rax
0x180165132  jz      loc_18016521D
0x180165138  mov     rcx, r12; hdc
0x18016513b  call    cs:__imp_CreateCompatibleDC
0x180165141  mov     rbp, rax
0x180165144  test    rax, rax
0x180165147  jz      loc_18016521D
0x18016514d  lea     r8, [rsp+0C8h+pv]; pv
0x180165152  mov     rcx, rdi; h
0x180165155  lea     edx, [r15+20h]; c
0x180165159  call    cs:__imp_GetObjectW
0x18016515f  test    eax, eax
0x180165161  jz      loc_18016521D
0x180165167  mov     r8d, dword ptr [rsp+0C8h+pv+8]; cy
0x18016516c  mov     rcx, r12; hdc
0x18016516f  mov     edx, dword ptr [rsp+0C8h+pv+4]; cx
0x180165173  call    cs:__imp_CreateCompatibleBitmap
0x180165179  mov     rbx, rax
0x18016517c  test    rax, rax
0x18016517f  jz      loc_18016521D
0x180165185  mov     rdx, rdi; h
0x180165188  mov     rcx, r14; hdc
0x18016518b  call    cs:__imp_SelectObject
0x180165191  mov     rdx, rbx; h
0x180165194  mov     rcx, rbp; hdc
0x180165197  mov     rsi, rax
0x18016519a  call    cs:__imp_SelectObject
0x1801651a0  mov     edx, dword ptr [rsp+0C8h+pv+8]
0x1801651a4  xor     r8d, r8d; yDest
0x1801651a7  mov     r9d, dword ptr [rsp+0C8h+pv+4]; wDest
0x1801651ac  mov     rdi, rax
0x1801651af  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1801651b7  mov     eax, r9d
0x1801651ba  mov     [rsp+0C8h+hSrc], edx; hSrc
0x1801651be  neg     eax
0x1801651c0  mov     [rsp+0C8h+wSrc], eax; wSrc
0x1801651c4  lea     ecx, [r9-1]
0x1801651c8  mov     [rsp+0C8h+ySrc], r15d; ySrc
0x1801651cd  mov     [rsp+0C8h+xSrc], ecx; xSrc
0x1801651d1  mov     rcx, rbp; hdcDest
0x1801651d4  mov     [rsp+0C8h+hdcSrc], r14; hdcSrc
0x1801651d9  mov     [rsp+0C8h+hDest], edx; hDest
0x1801651dd  xor     edx, edx; xDest
0x1801651df  call    cs:__imp_StretchBlt
0x1801651e5  mov     rdx, rsi; h
0x1801651e8  mov     rcx, r14; hdc
0x1801651eb  mov     ebx, eax
0x1801651ed  call    cs:__imp_SelectObject
0x1801651f3  mov     rdx, rdi; h
0x1801651f6  mov     rcx, rbp; hdc
0x1801651f9  call    cs:__imp_SelectObject
0x1801651ff  test    ebx, ebx
0x180165201  jz      short loc_18016520F
0x180165203  mov     [r13+0], rax
0x180165207  mov     r15d, 1
0x18016520d  jmp     short loc_18016521D
0x18016520f  test    rax, rax
0x180165212  jz      short loc_18016521D
0x180165214  mov     rcx, rax; ho
0x180165217  call    cs:__imp_DeleteObject
0x18016521d  mov     rdx, r12; hDC
0x180165220  xor     ecx, ecx; hWnd
0x180165222  call    cs:__imp_ReleaseDC
0x180165228  test    r14, r14
0x18016522b  jz      short loc_180165236
0x18016522d  mov     rcx, r14; hdc
0x180165230  call    cs:__imp_DeleteDC
0x180165236  test    rbp, rbp
0x180165239  jz      short loc_180165244
0x18016523b  mov     rcx, rbp; hdc
0x18016523e  call    cs:__imp_DeleteDC
0x180165244  mov     eax, r15d
0x180165247  add     rsp, 88h
0x18016524e  pop     r15
0x180165250  pop     r14
0x180165252  pop     r13
0x180165254  pop     r12
0x180165256  pop     rdi
0x180165257  pop     rsi
0x180165258  pop     rbp
0x180165259  pop     rbx
0x18016525a  retn
```
