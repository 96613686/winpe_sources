# CRectTracker::Construct(void)

- ea: `0x1802819c0`
- end: `0x180281c1b`
- name: `?Construct@CRectTracker@@IEAAXXZ`
- size: `603`
- prototype: `void __fastcall(CRectTracker *this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18024ed90`
- `0x180281950`

## callees

- `0x1800349e0`
- `0x180034a80`
- `0x1802819c0`
- `0x1802b0dd0`
- `0x1802bba00`
- `0x1802c4640`
- `0x1802c49e4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180281bae`
- `KERNEL32!LeaveCriticalSection` at `0x180281bae`
- `KERNEL32!GetProfileIntW` at `0x180281b73`
- `KERNEL32!GetProfileIntW` at `0x180281b73`
- `USER32!SetRectEmpty` at `0x180281bcd`
- `USER32!SetRectEmpty` at `0x180281bcd`
- `USER32!LoadCursorW` at `0x180281aad`
- `USER32!LoadCursorW` at `0x180281ac2`
- `USER32!LoadCursorW` at `0x180281af5`
- `USER32!LoadCursorW` at `0x180281b0a`
- `USER32!LoadCursorW` at `0x180281b3d`
- `USER32!LoadCursorW` at `0x180281b52`
- `USER32!LoadCursorW` at `0x180281aad`
- `USER32!LoadCursorW` at `0x180281ac2`
- `USER32!LoadCursorW` at `0x180281af5`
- `USER32!LoadCursorW` at `0x180281b0a`
- `USER32!LoadCursorW` at `0x180281b3d`
- `USER32!LoadCursorW` at `0x180281b52`
- `GDI32!CreateBitmap` at `0x180281a32`
- `GDI32!CreateBitmap` at `0x180281a32`
- `GDI32!CreatePatternBrush` at `0x180281a47`
- `GDI32!CreatePatternBrush` at `0x180281a47`
- `GDI32!CreatePen` at `0x180281a7d`
- `GDI32!CreatePen` at `0x180281a7d`
- `GDI32!DeleteObject` at `0x180281a57`
- `GDI32!DeleteObject` at `0x180281a57`

## pseudocode

```c
void __fastcall CRectTracker::Construct(CRectTracker *this)
{
  unsigned __int16 v2; // cx
  __int64 i; // rax
  HBITMAP Bitmap; // rax
  HBITMAP v5; // rdi
  HINSTANCE ResourceHandle; // rdi
  HICON__ **v7; // rdx
  HICON__ **v8; // rcx
  int v9; // eax
  unsigned __int16 hatchPattern[8]; // [rsp+30h] [rbp-28h] BYREF

  AfxLockGlobals(5);
  if ( !bInitialized_2 )
  {
    if ( !_afxHatchBrush )
    {
      v2 = 4369;
      for ( i = 0; i < 4; ++i )
      {
        hatchPattern[i] = v2;
        hatchPattern[i + 4] = v2;
        v2 *= 2;
      }
      Bitmap = CreateBitmap(8, 8, 1u, 1u, hatchPattern);
      v5 = Bitmap;
      if ( !Bitmap || (_afxHatchBrush = CreatePatternBrush(Bitmap), DeleteObject(v5), !_afxHatchBrush) )
      {
        AfxUnlockGlobals(5);
        AfxThrowResourceException();
      }
    }
    if ( !_afxBlackDottedPen )
    {
      _afxBlackDottedPen = CreatePen(2, 0, 0);
      if ( !_afxBlackDottedPen )
      {
        AfxUnlockGlobals(5);
        AfxThrowResourceException();
      }
    }
    ResourceHandle = AfxFindResourceHandle((const wchar_t *)0x790B, (const wchar_t *)0xC);
    _afxCursors[0] = LoadCursorW(ResourceHandle, (LPCWSTR)0x7907);
    _afxCursors[1] = LoadCursorW(ResourceHandle, (LPCWSTR)0x7908);
    v7 = &_afxCursors[2];
    do
    {
      *v7 = *(v7 - 2);
      ++v7;
    }
    while ( (__int64)v7 < (__int64)&_afxCursors[4] );
    _afxCursors[4] = LoadCursorW(ResourceHandle, (LPCWSTR)0x7909);
    _afxCursors[5] = LoadCursorW(ResourceHandle, (LPCWSTR)0x790A);
    v8 = &_afxCursors[6];
    do
    {
      *v8 = *(v8 - 2);
      ++v8;
    }
    while ( (__int64)v8 < (__int64)&_afxCursors[8] );
    _afxCursors[8] = LoadCursorW(ResourceHandle, (LPCWSTR)0x790B);
    _afxCursors[9] = LoadCursorW(ResourceHandle, (LPCWSTR)0x790C);
    _afxHandleSize = GetProfileIntW(szWindows, szInplaceBorderWidth, 4);
    bInitialized_2 = 1;
  }
  if ( !_afxTrackerTerm )
    _afxTrackerTerm = atexit(AfxTrackerTerm) == 0;
  LeaveCriticalSection(&_afxResourceLock[5]);
  v9 = _afxHandleSize;
  this->m_nStyle = 0;
  this->m_nHandleSize = v9;
  v9 *= 2;
  this->m_sizeMin.cx = v9;
  this->m_sizeMin.cy = v9;
  SetRectEmpty(&this->m_rectLast);
  this->m_sizeLast.cy = 0;
  this->m_sizeLast.cx = 0;
  this->m_bErase = 0;
  this->m_bFinalErase = 0;
}

```

## disassembly

```asm
0x1802819c0  mov     [rsp+arg_8], rbx
0x1802819c5  push    rdi
0x1802819c6  sub     rsp, 50h
0x1802819ca  mov     rax, cs:__security_cookie
0x1802819d1  xor     rax, rsp
0x1802819d4  mov     [rsp+58h+var_18], rax
0x1802819d9  mov     rbx, this
0x1802819dc  mov     ecx, 5; nLockType
0x1802819e1  call    ?AfxLockGlobals@@YAXH@Z; AfxLockGlobals(int)
0x1802819e6  cmp     cs:bInitialized_2, 0
0x1802819ed  jnz     loc_180281B89
0x1802819f3  cmp     cs:?_afxHatchBrush@@3PEAUHBRUSH__@@EA, 0; HBRUSH__ * _afxHatchBrush
0x1802819fb  jnz     short loc_180281A6B
0x1802819fd  mov     ecx, 1111h
0x180281a02  xor     eax, eax
0x180281a04  mov     [rsp+rax*2+58h+hatchPattern], cx
0x180281a09  mov     [rsp+rax*2+58h+hatchPattern+8], cx
0x180281a0e  add     cx, cx
0x180281a11  inc     rax
0x180281a14  cmp     rax, 4
0x180281a18  jl      short loc_180281A04
0x180281a1a  mov     edx, 8; nHeight
0x180281a1f  lea     rax, [rsp+58h+hatchPattern]
0x180281a24  mov     ecx, edx; nWidth
0x180281a26  mov     [rsp+58h+lpBits], rax; lpBits
0x180281a2b  lea     r9d, [rdx-7]; nBitCount
0x180281a2f  mov     r8d, r9d; nPlanes
0x180281a32  call    cs:__imp_CreateBitmap
0x180281a38  mov     rdi, rax
0x180281a3b  test    rax, rax
0x180281a3e  jz      loc_180281C0B
0x180281a44  mov     this, rax; hbm
0x180281a47  call    cs:__imp_CreatePatternBrush
0x180281a4d  mov     this, rdi; ho
0x180281a50  mov     cs:?_afxHatchBrush@@3PEAUHBRUSH__@@EA, rax; HBRUSH__ * _afxHatchBrush
0x180281a57  call    cs:__imp_DeleteObject
0x180281a5d  cmp     cs:?_afxHatchBrush@@3PEAUHBRUSH__@@EA, 0; HBRUSH__ * _afxHatchBrush
0x180281a65  jz      loc_180281C0B
0x180281a6b  cmp     cs:?_afxBlackDottedPen@@3PEAUHPEN__@@EA, 0; HPEN__ * _afxBlackDottedPen
0x180281a73  jnz     short loc_180281A93
0x180281a75  xor     edx, edx; cWidth
0x180281a77  xor     r8d, r8d; color
0x180281a7a  lea     ecx, [rdx+2]; iStyle
0x180281a7d  call    cs:__imp_CreatePen
0x180281a83  mov     cs:?_afxBlackDottedPen@@3PEAUHPEN__@@EA, rax; HPEN__ * _afxBlackDottedPen
0x180281a8a  test    rax, rax
0x180281a8d  jz      loc_180281BFB
0x180281a93  mov     edx, 0Ch; lpszType
0x180281a98  mov     ecx, 790Bh; lpszName
0x180281a9d  call    ?AfxFindResourceHandle@@YAPEAUHINSTANCE__@@PEB_W0@Z; AfxFindResourceHandle(wchar_t const *,wchar_t const *)
0x180281aa2  mov     edx, 7907h; lpCursorName
0x180281aa7  mov     this, rax; hInstance
0x180281aaa  mov     rdi, rax
0x180281aad  call    cs:__imp_LoadCursorW
0x180281ab3  mov     edx, 7908h; lpCursorName
0x180281ab8  mov     this, rdi; hInstance
0x180281abb  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A, rax; HICON__ * near * _afxCursors
0x180281ac2  call    cs:__imp_LoadCursorW
0x180281ac8  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A+8, rax; HICON__ * near * _afxCursors
0x180281acf  lea     rdx, ?_afxCursors@@3PAPEAUHICON__@@A+10h; HICON__ * near * _afxCursors
0x180281ad6  lea     rax, ?_afxCursors@@3PAPEAUHICON__@@A+20h; HICON__ * near * _afxCursors
0x180281add  mov     this, [rdx-10h]
0x180281ae1  mov     [rdx], this
0x180281ae4  add     rdx, 8
0x180281ae8  cmp     rdx, rax
0x180281aeb  jl      short loc_180281ADD
0x180281aed  mov     edx, 7909h; lpCursorName
0x180281af2  mov     this, rdi; hInstance
0x180281af5  call    cs:__imp_LoadCursorW
0x180281afb  mov     edx, 790Ah; lpCursorName
0x180281b00  mov     this, rdi; hInstance
0x180281b03  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A+20h, rax; HICON__ * near * _afxCursors
0x180281b0a  call    cs:__imp_LoadCursorW
0x180281b10  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A+28h, rax; HICON__ * near * _afxCursors
0x180281b17  lea     this, ?_afxCursors@@3PAPEAUHICON__@@A+30h; HICON__ * near * _afxCursors
0x180281b1e  lea     r9, ?_afxCursors@@3PAPEAUHICON__@@A+40h; HICON__ * near * _afxCursors
0x180281b25  mov     rax, [this-10h]
0x180281b29  mov     [this], rax
0x180281b2c  add     this, 8
0x180281b30  cmp     this, r9
0x180281b33  jl      short loc_180281B25
0x180281b35  mov     edx, 790Bh; lpCursorName
0x180281b3a  mov     this, rdi; hInstance
0x180281b3d  call    cs:__imp_LoadCursorW
0x180281b43  mov     edx, 790Ch; lpCursorName
0x180281b48  mov     this, rdi; hInstance
0x180281b4b  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A+40h, rax; HICON__ * near * _afxCursors
0x180281b52  call    cs:__imp_LoadCursorW
0x180281b58  mov     r8d, 4; nDefault
0x180281b5e  lea     rdx, szInplaceBorderWidth; lpKeyName
0x180281b65  lea     this, szWindows; lpAppName
0x180281b6c  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A+48h, rax; HICON__ * near * _afxCursors
0x180281b73  call    cs:__imp_GetProfileIntW
0x180281b79  mov     cs:?_afxHandleSize@@3HA, eax; int _afxHandleSize
0x180281b7f  mov     cs:bInitialized_2, 1
0x180281b89  cmp     cs:?_afxTrackerTerm@@3DA, 0; char _afxTrackerTerm
0x180281b90  jnz     short loc_180281BA7
0x180281b92  lea     this, ?AfxTrackerTerm@@YAXXZ; function
0x180281b99  call    atexit
0x180281b9e  test    eax, eax
0x180281ba0  setz    cs:?_afxTrackerTerm@@3DA; char _afxTrackerTerm
0x180281ba7  lea     this, ?_afxResourceLock@@3PAU_RTL_CRITICAL_SECTION@@A.DebugInfo+0C8h; lpCriticalSection
0x180281bae  call    cs:__imp_LeaveCriticalSection
0x180281bb4  mov     eax, cs:?_afxHandleSize@@3HA; int _afxHandleSize
0x180281bba  lea     this, [rbx+2Ch]; lprc
0x180281bbe  and     dword ptr [rbx+8], 0
0x180281bc2  mov     [rbx+24h], eax
0x180281bc5  add     eax, eax
0x180281bc7  mov     [rbx+1Ch], eax
0x180281bca  mov     [rbx+20h], eax
0x180281bcd  call    cs:__imp_SetRectEmpty
0x180281bd3  and     dword ptr [rbx+40h], 0
0x180281bd7  and     dword ptr [rbx+3Ch], 0
0x180281bdb  and     dword ptr [rbx+44h], 0
0x180281bdf  and     dword ptr [rbx+48h], 0
0x180281be3  mov     this, [rsp+58h+var_18]
0x180281be8  xor     this, rsp; StackCookie
0x180281beb  call    __security_check_cookie
0x180281bf0  mov     rbx, [rsp+58h+arg_8]
0x180281bf5  add     rsp, 50h
0x180281bf9  pop     rdi
0x180281bfa  retn
0x180281bfb  mov     ecx, 5; nLockType
0x180281c00  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x180281c05  call    ?AfxThrowResourceException@@YAXXZ; AfxThrowResourceException(void)
0x180281c0b  mov     ecx, 5; nLockType
0x180281c10  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x180281c15  call    ?AfxThrowResourceException@@YAXXZ; AfxThrowResourceException(void)
```
