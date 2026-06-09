# MRMASKBLT::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180090360`
- end: `0x18009065d`
- name: `?bPlay@MRMASKBLT@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `765`
- prototype: `__int64 __fastcall(MRMASKBLT *__hidden this, HDC hdcDest, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800305e0`

## callees

- `0x18001dc40`
- `0x18001e870`
- `0x18001eb5c`
- `0x18001ec70`
- `0x18001ff10`
- `0x180022504`
- `0x180024fb8`
- `0x1800785d4`
- `0x18008f380`
- `0x180090360`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009048a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009063f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180090470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009048a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009063f`
- `GDI32!DeleteDC` at `0x18009061c`
- `GDI32!DeleteDC` at `0x18009061c`
- `GDI32!SelectObject` at `0x18009059b`
- `GDI32!SelectObject` at `0x18009060a`
- `GDI32!SelectObject` at `0x18009059b`
- `GDI32!SelectObject` at `0x18009060a`
- `GDI32!SetWorldTransform` at `0x1800904ac`
- `GDI32!SetWorldTransform` at `0x1800904ac`
- `GDI32!DeleteObject` at `0x180090613`
- `GDI32!DeleteObject` at `0x18009062a`
- `GDI32!DeleteObject` at `0x180090613`
- `GDI32!DeleteObject` at `0x18009062a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MRMASKBLT::bPlay(MRMASKBLT *this, HDC hdcDest, struct tagHANDLETABLE *a3)
{
  unsigned int v6; // r13d
  BITMAPINFOHEADER *v7; // r14
  MF *v8; // rdi
  HBITMAP hbmMask; // rsi
  unsigned int v11; // r9d
  HLOCAL v12; // rdi
  HDC CompatibleDCAdvanced; // rax
  HDC hdcSrc; // rdi
  DWORD rop; // eax
  int v16; // eax
  HBITMAP DIBitmap; // rax
  HBITMAP v18; // r12
  HGDIOBJ v19; // r15
  HLOCAL hMem; // [rsp+60h] [rbp-9h] BYREF
  char v21; // [rsp+68h] [rbp-1h]
  BITMAPINFOHEADER *pbmih; // [rsp+70h] [rbp+7h] BYREF
  char v23; // [rsp+78h] [rbp+Fh]

  v6 = 0;
  v7 = 0;
  pbmih = 0;
  v23 = 0;
  v8 = (MF *)pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v8 || !MRMASKBLT::bCheckRecord(this, a3) )
    return 0;
  if ( MF::bClipped(v8, (MRMASKBLT *)((char *)this + 8)) )
    return 1;
  hbmMask = 0;
  v11 = *((_DWORD *)this + 29);
  if ( v11 )
  {
    hMem = 0;
    v21 = 0;
    if ( !(unsigned int)bCheckBitmap(
                          a3,
                          this,
                          *((_DWORD *)this + 28),
                          v11,
                          *((_DWORD *)this + 30),
                          *((_DWORD *)this + 31),
                          *((_DWORD *)this + 27),
                          0,
                          (BitmapInfoPtr *)&hMem) )
    {
      if ( hMem )
      {
        if ( v21 )
          LocalFree(hMem);
      }
      return 0;
    }
    v12 = hMem;
    hbmMask = (HBITMAP)CreateMonoDib(
                         (BITMAPINFO *)hMem,
                         (char *)this + *((unsigned int *)this + 30),
                         *((_DWORD *)this + 27));
    if ( !hbmMask )
    {
      if ( v12 && v21 )
        LocalFree(v12);
      return 0;
    }
    if ( v12 && v21 )
      LocalFree(v12);
  }
  CompatibleDCAdvanced = (HDC)CreateCompatibleDCAdvanced(hdcDest);
  hdcSrc = CompatibleDCAdvanced;
  if ( CompatibleDCAdvanced )
  {
    if ( SetWorldTransform(CompatibleDCAdvanced, (const XFORM *)((char *)this + 52)) )
    {
      rop = *((_DWORD *)this + 10);
      if ( ((rop ^ (4 * rop)) & 0xCCCC0000) != 0 )
      {
        v16 = bCheckBitmap(
                a3,
                this,
                *((_DWORD *)this + 21),
                *((_DWORD *)this + 22),
                *((_DWORD *)this + 23),
                *((_DWORD *)this + 24),
                *((_DWORD *)this + 20),
                0,
                (BitmapInfoPtr *)&pbmih);
        v7 = pbmih;
        if ( v16 )
        {
          DIBitmap = CreateDIBitmap(
                       hdcSrc,
                       pbmih,
                       6u,
                       (char *)this + *((unsigned int *)this + 23),
                       (const BITMAPINFO *)((char *)this + *((unsigned int *)this + 21)),
                       *((_DWORD *)this + 20));
          v18 = DIBitmap;
          if ( DIBitmap )
          {
            v19 = SelectObject(hdcSrc, DIBitmap);
            if ( v19 )
            {
              if ( SetBkColor(hdcSrc, *((_DWORD *)this + 19)) != -1 )
                v6 = MaskBlt(
                       hdcDest,
                       *((_DWORD *)this + 6),
                       *((_DWORD *)this + 7),
                       *((_DWORD *)this + 8),
                       *((_DWORD *)this + 9),
                       hdcSrc,
                       *((_DWORD *)this + 11),
                       *((_DWORD *)this + 12),
                       hbmMask,
                       *((_DWORD *)this + 25),
                       *((_DWORD *)this + 26),
                       *((_DWORD *)this + 10));
              SelectObject(hdcSrc, v19);
            }
            DeleteObject(v18);
          }
        }
      }
      else
      {
        v6 = MaskBlt(
               hdcDest,
               *((_DWORD *)this + 6),
               *((_DWORD *)this + 7),
               *((_DWORD *)this + 8),
               *((_DWORD *)this + 9),
               hdcSrc,
               *((_DWORD *)this + 11),
               *((_DWORD *)this + 12),
               hbmMask,
               *((_DWORD *)this + 25),
               *((_DWORD *)this + 26),
               rop);
      }
    }
    DeleteDC(hdcSrc);
  }
  if ( hbmMask )
    DeleteObject(hbmMask);
  if ( v7 && v23 )
    LocalFree(v7);
  return v6;
}

```

## disassembly

```asm
0x180090360  mov     [rsp-8+hdcDest], rdx
0x180090365  push    rbp
0x180090366  push    rbx
0x180090367  push    rsi
0x180090368  push    rdi
0x180090369  push    r12
0x18009036b  push    r13
0x18009036d  push    r14
0x18009036f  push    r15
0x180090371  lea     rbp, [rsp-1Fh]
0x180090376  sub     rsp, 88h
0x18009037d  mov     r15, r8
0x180090380  mov     r12, rdx
0x180090383  mov     rbx, rcx
0x180090386  xor     r13d, r13d
0x180090389  mov     r14d, r13d
0x18009038c  mov     [rbp+57h+pbmih], r13
0x180090390  mov     [rbp+57h+var_48], r13b
0x180090394  mov     edx, 460000h
0x180090399  mov     rcx, [r8]
0x18009039c  call    pvClientObjGet
0x1800903a1  mov     rdi, rax
0x1800903a4  test    rax, rax
0x1800903a7  jnz     short loc_1800903B0
0x1800903a9  xor     eax, eax
0x1800903ab  jmp     loc_180090649
0x1800903b0  mov     rdx, r15; struct tagHANDLETABLE *
0x1800903b3  mov     rcx, rbx; this
0x1800903b6  call    ?bCheckRecord@MRMASKBLT@@QEAAHPEAUtagHANDLETABLE@@@Z; MRMASKBLT::bCheckRecord(tagHANDLETABLE *)
0x1800903bb  test    eax, eax
0x1800903bd  jnz     short loc_1800903C1
0x1800903bf  jmp     short loc_1800903A9
0x1800903c1  lea     rdx, [rbx+8]; struct ERECTL *
0x1800903c5  mov     rcx, rdi; this
0x1800903c8  call    ?bClipped@MF@@QEAAHAEAVERECTL@@@Z; MF::bClipped(ERECTL &)
0x1800903cd  test    eax, eax
0x1800903cf  jz      short loc_1800903DB
0x1800903d1  mov     eax, 1
0x1800903d6  jmp     loc_180090649
0x1800903db  mov     rsi, r13
0x1800903de  mov     r9d, [rbx+74h]
0x1800903e2  test    r9d, r9d
0x1800903e5  jz      loc_180090491
0x1800903eb  mov     [rbp+57h+hMem], r13
0x1800903ef  mov     [rbp+57h+var_58], r13b
0x1800903f3  lea     rax, [rbp+57h+hMem]
0x1800903f7  mov     [rsp+0C0h+hbmMask], rax; BitmapInfoPtr *
0x1800903fc  mov     [rsp+0C0h+ySrc], r13d; int
0x180090401  mov     eax, [rbx+6Ch]
0x180090404  mov     [rsp+0C0h+xSrc], eax; int
0x180090408  mov     eax, [rbx+7Ch]
0x18009040b  mov     dword ptr [rsp+0C0h+hdcSrc], eax; int
0x18009040f  mov     eax, [rbx+78h]
0x180090412  mov     [rsp+0C0h+height], eax; int
0x180090416  mov     r8d, [rbx+70h]
0x18009041a  mov     rdx, rbx; this
0x18009041d  mov     rcx, r15; struct tagHANDLETABLE *
0x180090420  call    bCheckBitmap
0x180090425  test    eax, eax
0x180090427  jnz     short loc_180090444
0x180090429  mov     rcx, [rbp+57h+hMem]; hMem
0x18009042d  test    rcx, rcx
0x180090430  jz      short loc_18009043F
0x180090432  cmp     [rbp+57h+var_58], r13b
0x180090436  jz      short loc_18009043F
0x180090438  call    cs:__imp_LocalFree
0x18009043e  nop
0x18009043f  jmp     loc_1800903A9
0x180090444  mov     edx, [rbx+78h]
0x180090447  add     rdx, rbx; lpBits
0x18009044a  mov     r8d, [rbx+6Ch]; ColorUse
0x18009044e  mov     rdi, [rbp+57h+hMem]
0x180090452  mov     rcx, rdi; lpbmi
0x180090455  call    CreateMonoDib
0x18009045a  mov     rsi, rax
0x18009045d  test    rax, rax
0x180090460  jnz     short loc_18009047C
0x180090462  test    rdi, rdi
0x180090465  jz      short loc_180090477
0x180090467  cmp     [rbp+57h+var_58], r13b
0x18009046b  jz      short loc_180090477
0x18009046d  mov     rcx, rdi; hMem
0x180090470  call    cs:__imp_LocalFree
0x180090476  nop
0x180090477  jmp     loc_1800903A9
0x18009047c  test    rdi, rdi
0x18009047f  jz      short loc_180090491
0x180090481  cmp     [rbp+57h+var_58], r13b
0x180090485  jz      short loc_180090491
0x180090487  mov     rcx, rdi; hMem
0x18009048a  call    cs:__imp_LocalFree
0x180090490  nop
0x180090491  mov     rcx, r12
0x180090494  call    CreateCompatibleDCAdvanced
0x180090499  mov     rdi, rax
0x18009049c  test    rax, rax
0x18009049f  jz      loc_180090622
0x1800904a5  lea     rdx, [rbx+34h]; lpxf
0x1800904a9  mov     rcx, rax; hdc
0x1800904ac  call    cs:__imp_SetWorldTransform
0x1800904b2  test    eax, eax
0x1800904b4  jz      loc_180090619
0x1800904ba  mov     eax, [rbx+28h]
0x1800904bd  lea     ecx, ds:0[rax*4]
0x1800904c4  xor     ecx, eax
0x1800904c6  test    ecx, 0CCCC0000h
0x1800904cc  jnz     short loc_18009051A
0x1800904ce  mov     [rsp+0C0h+rop], eax; rop
0x1800904d2  mov     eax, [rbx+68h]
0x1800904d5  mov     [rsp+0C0h+yMask], eax; yMask
0x1800904d9  mov     eax, [rbx+64h]
0x1800904dc  mov     [rsp+0C0h+xMask], eax; xMask
0x1800904e0  mov     [rsp+0C0h+hbmMask], rsi; hbmMask
0x1800904e5  mov     eax, [rbx+30h]
0x1800904e8  mov     [rsp+0C0h+ySrc], eax; ySrc
0x1800904ec  mov     eax, [rbx+2Ch]
0x1800904ef  mov     [rsp+0C0h+xSrc], eax; xSrc
0x1800904f3  mov     [rsp+0C0h+hdcSrc], rdi; hdcSrc
0x1800904f8  mov     eax, [rbx+24h]
0x1800904fb  mov     [rsp+0C0h+height], eax; height
0x1800904ff  mov     r9d, [rbx+20h]; width
0x180090503  mov     r8d, [rbx+1Ch]; yDest
0x180090507  mov     edx, [rbx+18h]; xDest
0x18009050a  mov     rcx, r12; hdcDest
0x18009050d  call    MaskBlt
0x180090512  mov     r13d, eax
0x180090515  jmp     loc_180090619
0x18009051a  lea     rax, [rbp+57h+pbmih]
0x18009051e  mov     [rsp+0C0h+hbmMask], rax; BitmapInfoPtr *
0x180090523  mov     [rsp+0C0h+ySrc], 0; int
0x18009052b  mov     eax, [rbx+50h]
0x18009052e  mov     [rsp+0C0h+xSrc], eax; int
0x180090532  mov     eax, [rbx+60h]
0x180090535  mov     dword ptr [rsp+0C0h+hdcSrc], eax; int
0x180090539  mov     eax, [rbx+5Ch]
0x18009053c  mov     [rsp+0C0h+height], eax; int
0x180090540  mov     r9d, [rbx+58h]
0x180090544  mov     r8d, [rbx+54h]
0x180090548  mov     rdx, rbx; this
0x18009054b  mov     rcx, r15; struct tagHANDLETABLE *
0x18009054e  call    bCheckBitmap
0x180090553  mov     r14, [rbp+57h+pbmih]
0x180090557  test    eax, eax
0x180090559  jz      loc_180090619
0x18009055f  mov     ecx, [rbx+54h]
0x180090562  add     rcx, rbx
0x180090565  mov     r9d, [rbx+5Ch]
0x180090569  add     r9, rbx; pjBits
0x18009056c  mov     eax, [rbx+50h]
0x18009056f  mov     dword ptr [rsp+0C0h+hdcSrc], eax; iUsage
0x180090573  mov     qword ptr [rsp+0C0h+height], rcx; pbmi
0x180090578  mov     r8d, 6; flInit
0x18009057e  mov     rdx, r14; pbmih
0x180090581  mov     rcx, rdi; hdc
0x180090584  call    CreateDIBitmap
0x180090589  mov     r12, rax
0x18009058c  test    rax, rax
0x18009058f  jz      loc_180090619
0x180090595  mov     rdx, rax; h
0x180090598  mov     rcx, rdi; hdc
0x18009059b  call    cs:__imp_SelectObject
0x1800905a1  mov     r15, rax
0x1800905a4  test    rax, rax
0x1800905a7  jz      short loc_180090610
0x1800905a9  mov     edx, [rbx+4Ch]; color
0x1800905ac  mov     rcx, rdi; hdc
0x1800905af  call    SetBkColor
0x1800905b4  cmp     eax, 0FFFFFFFFh
0x1800905b7  jz      short loc_180090604
0x1800905b9  mov     ecx, [rbx+28h]
0x1800905bc  mov     [rsp+0C0h+rop], ecx; rop
0x1800905c0  mov     ecx, [rbx+68h]
0x1800905c3  mov     [rsp+0C0h+yMask], ecx; yMask
0x1800905c7  mov     eax, [rbx+64h]
0x1800905ca  mov     [rsp+0C0h+xMask], eax; xMask
0x1800905ce  mov     [rsp+0C0h+hbmMask], rsi; hbmMask
0x1800905d3  mov     eax, [rbx+30h]
0x1800905d6  mov     [rsp+0C0h+ySrc], eax; ySrc
0x1800905da  mov     eax, [rbx+2Ch]
0x1800905dd  mov     [rsp+0C0h+xSrc], eax; xSrc
0x1800905e1  mov     [rsp+0C0h+hdcSrc], rdi; hdcSrc
0x1800905e6  mov     eax, [rbx+24h]
0x1800905e9  mov     [rsp+0C0h+height], eax; height
0x1800905ed  mov     r9d, [rbx+20h]; width
0x1800905f1  mov     r8d, [rbx+1Ch]; yDest
0x1800905f5  mov     edx, [rbx+18h]; xDest
0x1800905f8  mov     rcx, [rbp+57h+hdcDest]; hdcDest
0x1800905fc  call    MaskBlt
0x180090601  mov     r13d, eax
0x180090604  mov     rdx, r15; h
0x180090607  mov     rcx, rdi; hdc
0x18009060a  call    cs:__imp_SelectObject
0x180090610  mov     rcx, r12; ho
0x180090613  call    cs:__imp_DeleteObject
0x180090619  mov     rcx, rdi; hdc
0x18009061c  call    cs:__imp_DeleteDC
0x180090622  test    rsi, rsi
0x180090625  jz      short loc_180090631
0x180090627  mov     rcx, rsi; ho
0x18009062a  call    cs:__imp_DeleteObject
0x180090630  nop
0x180090631  test    r14, r14
0x180090634  jz      short loc_180090646
0x180090636  cmp     [rbp+57h+var_48], 0
0x18009063a  jz      short loc_180090646
0x18009063c  mov     rcx, r14; hMem
0x18009063f  call    cs:__imp_LocalFree
0x180090645  nop
0x180090646  mov     eax, r13d
0x180090649  add     rsp, 88h
0x180090650  pop     r15
0x180090652  pop     r14
0x180090654  pop     r13
0x180090656  pop     r12
0x180090658  pop     rdi
0x180090659  pop     rsi
0x18009065a  pop     rbx
0x18009065b  pop     rbp
0x18009065c  retn
```
