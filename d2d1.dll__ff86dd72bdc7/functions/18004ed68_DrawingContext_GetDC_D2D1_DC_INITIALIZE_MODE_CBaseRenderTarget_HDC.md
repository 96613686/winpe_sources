# DrawingContext::GetDC(D2D1_DC_INITIALIZE_MODE,CBaseRenderTarget *,HDC__ * *)

- ea: `0x18004ed68`
- end: `0x18004f033`
- name: `?GetDC@DrawingContext@@QEAAJW4D2D1_DC_INITIALIZE_MODE@@PEAVCBaseRenderTarget@@PEAPEAUHDC__@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(DrawingContext *__hidden this, enum D2D1_DC_INITIALIZE_MODE, struct CBaseRenderTarget *, HDC *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004dbc0`

## callees

- `0x18001fd58`
- `0x18004e4a8`
- `0x18004ed10`
- `0x18004ed68`
- `0x18004f040`
- `0x18004fd40`
- `0x1802170e0`
- `0x18025b100`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ef3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ef3a`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x18004f017`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x18004f017`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18004ef53`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18004efad`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18004ef53`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18004efad`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x18004ef2a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x18004ef2a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SelectClipRgn` at `0x18004ef46`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SelectClipRgn` at `0x18004ef46`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18004f028`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18004f028`

## pseudocode

```c
__int64 __fastcall DrawingContext::GetDC(DrawingContext *this, __int64 a2, struct CBaseRenderTarget *a3, HDC *a4)
{
  int v5; // ebp
  __int64 v7; // rcx
  int DC; // edi
  char IsSubTargetStackEmpty; // di
  __int64 v10; // rax
  __int64 v11; // rax
  int *v12; // rsi
  BitmapRealization *v13; // rdi
  bool v14; // al
  HDC v15; // rbx
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  HRGN RectRgn; // r14
  signed int LastError; // eax
  HBRUSH StockObject; // rax
  RECT hdc; // [rsp+20h] [rbp-48h] BYREF

  *(_QWORD *)&hdc.left = 0;
  *a4 = 0;
  v5 = a2;
  if ( (unsigned int)a2 > 1 )
  {
    v17 = -2147024809;
    goto LABEL_16;
  }
  if ( !*((_BYTE *)this + 304) )
  {
    v17 = -2003238911;
    goto LABEL_16;
  }
  if ( dword_1805DC038 != -1 && *((_QWORD *)this + 65) )
  {
    v18 = *((_QWORD *)this + 35);
    v19 = v18 + 32;
    v20 = -v18;
    if ( *(_BYTE *)((v19 & -(__int64)(v20 != 0)) + 8) )
      DebugSink::OutputDebugMessage((DebugSink *)(v19 & -(__int64)(v20 != 0)), 0x45Eu);
    goto LABEL_21;
  }
  v7 = *((_QWORD *)this + 52);
  if ( !v7 )
  {
    v17 = -2003238900;
LABEL_16:
    DoStackCapture(v17);
    return v17;
  }
  if ( ((*(__int64 (__fastcall **)(__int64, __int64, struct CBaseRenderTarget *))(*(_QWORD *)v7 + 256LL))(v7, a2, a3) & 8) == 0 )
  {
LABEL_21:
    v17 = -2003238886;
    goto LABEL_16;
  }
  DC = *((_DWORD *)this + 108);
  if ( DC < 0 )
    goto LABEL_25;
  DrawingContext::FlushBatch(this, 4);
  DC = *((_DWORD *)this + 108);
  if ( DC < 0 )
    goto LABEL_25;
  IsSubTargetStackEmpty = 0;
  if ( v5 == 1 )
    IsSubTargetStackEmpty = DrawingContext::IsSubTargetStackEmpty(this);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 52) + 232LL))(*((_QWORD *)this + 52));
  DC = BitmapRealization::GetDC(v10, IsSubTargetStackEmpty, (HDC *)&hdc);
  if ( DC < 0 )
  {
LABEL_25:
    DoStackCapture(DC);
    return (unsigned int)DC;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 52) + 232LL))(*((_QWORD *)this + 52));
  v12 = (int *)*((_QWORD *)this + 34);
  v13 = (BitmapRealization *)v11;
  v14 = DrawingContext::IsSubTargetStackEmpty(this);
  v15 = *(HDC *)&hdc.left;
  if ( !v14 )
  {
    RectRgn = CreateRectRgn(v12[52], v12[53], v12[54], v12[55]);
    if ( RectRgn )
    {
      SetLastError(0);
      if ( SelectClipRgn(v15, RectRgn) )
      {
        DeleteObject(RectRgn);
        goto LABEL_12;
      }
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( (v17 & 0x80000000) == 0 )
        v17 = -2003238887;
      DoStackCapture(v17);
      DeleteObject(RectRgn);
    }
    else
    {
      v17 = -2147024882;
      DoStackCapture(-2147024882);
    }
    if ( v13 )
      BitmapRealization::ReleaseDC(v13, 0);
    return v17;
  }
LABEL_12:
  if ( v5 == 1 )
  {
    hdc = (RECT)*((_OWORD *)v12 + 13);
    StockObject = (HBRUSH)GetStockObject(4);
    FillRect(v15, &hdc, StockObject);
  }
  *a4 = v15;
  return 0;
}

```

## disassembly

```asm
0x18004ed68  mov     [rsp+arg_8], rbx
0x18004ed6d  mov     [rsp+arg_10], rbp
0x18004ed72  push    rsi
0x18004ed73  push    rdi
0x18004ed74  push    r13
0x18004ed76  push    r14
0x18004ed78  push    r15
0x18004ed7a  sub     rsp, 40h
0x18004ed7e  mov     rax, cs:__security_cookie
0x18004ed85  xor     rax, rsp
0x18004ed88  mov     [rsp+68h+var_38], rax
0x18004ed8d  mov     [rsp+68h+hdc], 0
0x18004ed96  mov     r15, r9
0x18004ed99  mov     qword ptr [r9], 0
0x18004eda0  mov     ebp, edx
0x18004eda2  mov     rbx, rcx
0x18004eda5  test    edx, edx
0x18004eda7  jz      short loc_18004EDB2
0x18004eda9  cmp     edx, 1
0x18004edac  jnz     loc_18004EFC3
0x18004edb2  cmp     byte ptr [rcx+130h], 0
0x18004edb9  jz      loc_18004EFCD
0x18004edbf  cmp     cs:dword_1805DC038, 0FFFFFFFFh
0x18004edc6  jnz     loc_18004EED3
0x18004edcc  mov     rcx, [rcx+1A0h]
0x18004edd3  test    rcx, rcx
0x18004edd6  jz      loc_18004EEC3
0x18004eddc  mov     rax, [rcx]
0x18004eddf  mov     rax, [rax+100h]
0x18004ede6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edeb  test    al, 8
0x18004eded  jz      loc_18004EF09
0x18004edf3  mov     edi, [rbx+1B0h]
0x18004edf9  test    edi, edi
0x18004edfb  js      loc_18004EF5E
0x18004ee01  mov     edx, 4
0x18004ee06  mov     rcx, rbx
0x18004ee09  call    ?FlushBatch@DrawingContext@@QEAAXW4Enum@FlushReason@@@Z; DrawingContext::FlushBatch(FlushReason::Enum)
0x18004ee0e  mov     edi, [rbx+1B0h]
0x18004ee14  test    edi, edi
0x18004ee16  js      loc_18004EF5E
0x18004ee1c  xor     edi, edi
0x18004ee1e  lea     r13d, [rdi+1]
0x18004ee22  cmp     ebp, r13d
0x18004ee25  jz      loc_18004EFD7
0x18004ee2b  mov     rcx, [rbx+1A0h]
0x18004ee32  mov     rax, [rcx]
0x18004ee35  mov     rax, [rax+0E8h]
0x18004ee3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee41  lea     r8, [rsp+68h+hdc]
0x18004ee46  mov     edx, edi
0x18004ee48  mov     rcx, rax
0x18004ee4b  call    ?GetDC@BitmapRealization@@QEAAJW4Enum@GetDCFlags@@PEAPEAUHDC__@@@Z; BitmapRealization::GetDC(GetDCFlags::Enum,HDC__ * *)
0x18004ee50  mov     edi, eax
0x18004ee52  test    eax, eax
0x18004ee54  js      loc_18004EF5E
0x18004ee5a  mov     rcx, [rbx+1A0h]
0x18004ee61  mov     rax, [rcx]
0x18004ee64  mov     rax, [rax+0E8h]
0x18004ee6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee70  mov     rsi, [rbx+110h]
0x18004ee77  mov     rcx, rbx; this
0x18004ee7a  mov     rdi, rax
0x18004ee7d  call    ?IsSubTargetStackEmpty@DrawingContext@@AEBA_NXZ; DrawingContext::IsSubTargetStackEmpty(void)
0x18004ee82  mov     rbx, [rsp+68h+hdc]
0x18004ee87  test    al, al
0x18004ee89  jz      loc_18004EF10
0x18004ee8f  cmp     ebp, r13d
0x18004ee92  jz      loc_18004EFEA
0x18004ee98  mov     [r15], rbx
0x18004ee9b  xor     eax, eax
0x18004ee9d  mov     rcx, [rsp+68h+var_38]
0x18004eea2  xor     rcx, rsp; StackCookie
0x18004eea5  call    __security_check_cookie
0x18004eeaa  lea     r11, [rsp+68h+var_28]
0x18004eeaf  mov     rbx, [r11+38h]
0x18004eeb3  mov     rbp, [r11+40h]
0x18004eeb7  mov     rsp, r11
0x18004eeba  pop     r15
0x18004eebc  pop     r14
0x18004eebe  pop     r13
0x18004eec0  pop     rdi
0x18004eec1  pop     rsi
0x18004eec2  retn
0x18004eec3  mov     ebx, 8899000Ch
0x18004eec8  mov     ecx, ebx; int
0x18004eeca  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004eecf  mov     eax, ebx
0x18004eed1  jmp     short loc_18004EE9D
0x18004eed3  cmp     qword ptr [rcx+208h], 0
0x18004eedb  jz      loc_18004EDCC
0x18004eee1  mov     rax, [rcx+118h]
0x18004eee8  lea     rcx, [rax+20h]
0x18004eeec  neg     rax
0x18004eeef  sbb     r8, r8
0x18004eef2  and     r8, rcx
0x18004eef5  cmp     byte ptr [r8+8], 0
0x18004eefa  jz      short loc_18004EF09
0x18004eefc  mov     edx, 45Eh; unsigned int
0x18004ef01  mov     rcx, r8; this
0x18004ef04  call    ?OutputDebugMessage@DebugSink@@QEBAXIZZ; DebugSink::OutputDebugMessage(uint,...)
0x18004ef09  mov     ebx, 8899001Ah
0x18004ef0e  jmp     short loc_18004EEC8
0x18004ef10  mov     r9d, [rsi+0DCh]; y2
0x18004ef17  mov     r8d, [rsi+0D8h]; x2
0x18004ef1e  mov     edx, [rsi+0D4h]; y1
0x18004ef24  mov     ecx, [rsi+0D0h]; x1
0x18004ef2a  call    cs:__imp_CreateRectRgn
0x18004ef30  mov     r14, rax
0x18004ef33  test    rax, rax
0x18004ef36  jz      short loc_18004EF6C
0x18004ef38  xor     ecx, ecx; dwErrCode
0x18004ef3a  call    cs:__imp_SetLastError
0x18004ef40  mov     rdx, r14; hrgn
0x18004ef43  mov     rcx, rbx; hdc
0x18004ef46  call    cs:__imp_SelectClipRgn
0x18004ef4c  test    eax, eax
0x18004ef4e  jz      short loc_18004EFB5
0x18004ef50  mov     rcx, r14; ho
0x18004ef53  call    cs:__imp_DeleteObject
0x18004ef59  jmp     loc_18004EE8F
0x18004ef5e  mov     ecx, edi; int
0x18004ef60  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004ef65  mov     eax, edi
0x18004ef67  jmp     loc_18004EE9D
0x18004ef6c  mov     ebx, 8007000Eh
0x18004ef71  mov     ecx, ebx; int
0x18004ef73  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004ef78  test    rdi, rdi
0x18004ef7b  jz      loc_18004EECF
0x18004ef81  xor     edx, edx; struct tagRECT *
0x18004ef83  mov     rcx, rdi; this
0x18004ef86  call    ?ReleaseDC@BitmapRealization@@QEAAJPEBUtagRECT@@@Z; BitmapRealization::ReleaseDC(tagRECT const *)
0x18004ef8b  jmp     loc_18004EECF
0x18004ef90  movzx   ebx, ax
0x18004ef93  or      ebx, 80070000h
0x18004ef99  mov     eax, 88990019h
0x18004ef9e  test    ebx, ebx
0x18004efa0  cmovns  ebx, eax
0x18004efa3  mov     ecx, ebx; int
0x18004efa5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004efaa  mov     rcx, r14; ho
0x18004efad  call    cs:__imp_DeleteObject
0x18004efb3  jmp     short loc_18004EF78
0x18004efb5  call    cs:__imp_GetLastError
0x18004efbb  mov     ebx, eax
0x18004efbd  test    eax, eax
0x18004efbf  jle     short loc_18004EF99
0x18004efc1  jmp     short loc_18004EF90
0x18004efc3  mov     ebx, 80070057h
0x18004efc8  jmp     loc_18004EEC8
0x18004efcd  mov     ebx, 88990001h
0x18004efd2  jmp     loc_18004EEC8
0x18004efd7  mov     rcx, rbx; this
0x18004efda  call    ?IsSubTargetStackEmpty@DrawingContext@@AEBA_NXZ; DrawingContext::IsSubTargetStackEmpty(void)
0x18004efdf  test    al, al
0x18004efe1  cmovnz  edi, r13d
0x18004efe5  jmp     loc_18004EE2B
0x18004efea  mov     eax, [rsi+0D0h]
0x18004eff0  mov     ecx, 4; i
0x18004eff5  mov     dword ptr [rsp+68h+hdc], eax
0x18004eff9  mov     eax, [rsi+0D4h]
0x18004efff  mov     dword ptr [rsp+68h+hdc+4], eax
0x18004f003  mov     eax, [rsi+0D8h]
0x18004f009  mov     [rsp+68h+var_40], eax
0x18004f00d  mov     eax, [rsi+0DCh]
0x18004f013  mov     [rsp+68h+var_3C], eax
0x18004f017  call    cs:__imp_GetStockObject
0x18004f01d  lea     rdx, [rsp+68h+hdc]; lprc
0x18004f022  mov     rcx, rbx; hDC
0x18004f025  mov     r8, rax; hbr
0x18004f028  call    cs:__imp_FillRect
0x18004f02e  jmp     loc_18004EE98
```
