# GetBitmapType

- ea: `0x18000d080`
- end: `0x18000d1fc`
- name: `GetBitmapType`
- size: `380`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002a90`
- `0x18000be48`
- `0x18000d204`

## callees

- `0x1800014b0`
- `0x18000d080`
- `0x18000d3a4`
- `0x18000d570`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000d100`
- `GDI32!DeleteObject` at `0x18000d159`
- `GDI32!DeleteObject` at `0x18000d1e0`
- `GDI32!DeleteObject` at `0x18000d100`
- `GDI32!DeleteObject` at `0x18000d159`
- `GDI32!DeleteObject` at `0x18000d1e0`
- `GDI32!GetObjectW` at `0x18000d140`
- `GDI32!GetObjectW` at `0x18000d140`
- `GDI32!DeleteDC` at `0x18000d162`
- `GDI32!DeleteDC` at `0x18000d1e9`
- `GDI32!DeleteDC` at `0x18000d162`
- `GDI32!DeleteDC` at `0x18000d1e9`
- `GDI32!CreateCompatibleDC` at `0x18000d0ef`
- `GDI32!CreateCompatibleDC` at `0x18000d0ef`
- `GDI32!SelectObject` at `0x18000d12a`
- `GDI32!SelectObject` at `0x18000d150`
- `GDI32!SelectObject` at `0x18000d1d7`
- `GDI32!SelectObject` at `0x18000d12a`
- `GDI32!SelectObject` at `0x18000d150`
- `GDI32!SelectObject` at `0x18000d1d7`
- `GDI32!CreateCompatibleBitmap` at `0x18000d0d4`
- `GDI32!CreateCompatibleBitmap` at `0x18000d0d4`
- `GDI32!GetBitmapBits` at `0x18000d19f`
- `GDI32!GetBitmapBits` at `0x18000d19f`
- `GDI32!PatBlt` at `0x18000d184`
- `GDI32!PatBlt` at `0x18000d184`
- `USER32!GetDC` at `0x18000d0ba`
- `USER32!GetDC` at `0x18000d0ba`
- `USER32!ReleaseDC` at `0x18000d0e2`
- `USER32!ReleaseDC` at `0x18000d0e2`

## pseudocode

```c
__int64 GetBitmapType()
{
  __int64 result; // rax
  HDC DC; // rax
  HDC v2; // rbx
  HBITMAP CompatibleBitmap; // rsi
  HDC CompatibleDC; // rax
  HDC v5; // rdi
  HGDIOBJ v6; // rbp
  unsigned int SurfaceType; // ebx
  _OWORD pv[2]; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE vBits[160]; // [rsp+50h] [rbp-D8h] BYREF

  result = (unsigned int)dword_18001D484;
  memset(pv, 0, sizeof(pv));
  if ( dword_18001D484 == 0xFFFF )
  {
    DC = GetDC(0);
    v2 = DC;
    if ( !DC )
      return 0;
    CompatibleBitmap = CreateCompatibleBitmap(DC, 20, 2);
    ReleaseDC(0, v2);
    if ( !CompatibleBitmap )
      return 0;
    CompatibleDC = CreateCompatibleDC(0);
    v5 = CompatibleDC;
    if ( !CompatibleDC )
    {
      DeleteObject(CompatibleBitmap);
      return 0;
    }
    v6 = SelectObject(CompatibleDC, CompatibleBitmap);
    if ( !GetObjectW(CompatibleBitmap, 32, pv) )
    {
      SelectObject(v5, v6);
      DeleteObject(CompatibleBitmap);
      DeleteDC(v5);
      return 0;
    }
    PatBlt(v5, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), 0x42u);
    TestSurfaceType(v5);
    GetBitmapBits(CompatibleBitmap, 160, vBits);
    SurfaceType = GetSurfaceType(vBits);
    if ( !SurfaceType )
    {
      SurfaceType = GetSurfaceType(&vBits[SHIDWORD(pv[0])]);
      if ( SurfaceType )
        SurfaceType |= 0x80u;
    }
    SelectObject(v5, v6);
    DeleteObject(CompatibleBitmap);
    DeleteDC(v5);
    result = SurfaceType;
    dword_18001D484 = SurfaceType;
  }
  return result;
}

```

## disassembly

```asm
0x18000d080  push    rbx
0x18000d082  push    rbp
0x18000d083  push    rsi
0x18000d084  push    rdi
0x18000d085  sub     rsp, 108h
0x18000d08c  mov     rax, cs:__security_cookie
0x18000d093  xor     rax, rsp
0x18000d096  mov     [rsp+128h+var_38], rax
0x18000d09e  mov     eax, cs:dword_18001D484
0x18000d0a4  xorps   xmm0, xmm0
0x18000d0a7  movups  [rsp+128h+pv], xmm0
0x18000d0ac  movups  [rsp+128h+var_E8], xmm0
0x18000d0b1  cmp     eax, 0FFFFh
0x18000d0b6  jnz     short loc_18000D108
0x18000d0b8  xor     ecx, ecx; hWnd
0x18000d0ba  call    cs:__imp_GetDC
0x18000d0c0  mov     rbx, rax
0x18000d0c3  test    rax, rax
0x18000d0c6  jz      short loc_18000D106
0x18000d0c8  mov     edx, 14h; cx
0x18000d0cd  mov     rcx, rax; hdc
0x18000d0d0  lea     r8d, [rdx-12h]; cy
0x18000d0d4  call    cs:__imp_CreateCompatibleBitmap
0x18000d0da  mov     rdx, rbx; hDC
0x18000d0dd  xor     ecx, ecx; hWnd
0x18000d0df  mov     rsi, rax
0x18000d0e2  call    cs:__imp_ReleaseDC
0x18000d0e8  test    rsi, rsi
0x18000d0eb  jz      short loc_18000D106
0x18000d0ed  xor     ecx, ecx; hdc
0x18000d0ef  call    cs:__imp_CreateCompatibleDC
0x18000d0f5  mov     rdi, rax
0x18000d0f8  test    rax, rax
0x18000d0fb  jnz     short loc_18000D124
0x18000d0fd  mov     rcx, rsi; ho
0x18000d100  call    cs:__imp_DeleteObject
0x18000d106  xor     eax, eax
0x18000d108  mov     rcx, [rsp+128h+var_38]
0x18000d110  xor     rcx, rsp; StackCookie
0x18000d113  call    __security_check_cookie
0x18000d118  add     rsp, 108h
0x18000d11f  pop     rdi
0x18000d120  pop     rsi
0x18000d121  pop     rbp
0x18000d122  pop     rbx
0x18000d123  retn
0x18000d124  mov     rdx, rsi; h
0x18000d127  mov     rcx, rdi; hdc
0x18000d12a  call    cs:__imp_SelectObject
0x18000d130  lea     r8, [rsp+128h+pv]; pv
0x18000d135  mov     edx, 20h ; ' '; c
0x18000d13a  mov     rcx, rsi; h
0x18000d13d  mov     rbp, rax
0x18000d140  call    cs:__imp_GetObjectW
0x18000d146  mov     rcx, rdi; hdc
0x18000d149  test    eax, eax
0x18000d14b  jnz     short loc_18000D16A
0x18000d14d  mov     rdx, rbp; h
0x18000d150  call    cs:__imp_SelectObject
0x18000d156  mov     rcx, rsi; ho
0x18000d159  call    cs:__imp_DeleteObject
0x18000d15f  mov     rcx, rdi; hdc
0x18000d162  call    cs:__imp_DeleteDC
0x18000d168  jmp     short loc_18000D106
0x18000d16a  mov     eax, dword ptr [rsp+128h+pv+8]
0x18000d16e  xor     r8d, r8d; y
0x18000d171  mov     r9d, dword ptr [rsp+128h+pv+4]; w
0x18000d176  xor     edx, edx; x
0x18000d178  mov     [rsp+128h+rop], 42h ; 'B'; rop
0x18000d180  mov     [rsp+128h+h], eax; h
0x18000d184  call    cs:__imp_PatBlt
0x18000d18a  mov     rcx, rdi; hdc
0x18000d18d  call    TestSurfaceType
0x18000d192  lea     r8, [rsp+128h+vBits]; lpvBits
0x18000d197  mov     edx, 0A0h; cb
0x18000d19c  mov     rcx, rsi; hbit
0x18000d19f  call    cs:__imp_GetBitmapBits
0x18000d1a5  lea     rcx, [rsp+128h+vBits]; Buf1
0x18000d1aa  call    GetSurfaceType
0x18000d1af  mov     ebx, eax
0x18000d1b1  test    eax, eax
0x18000d1b3  jnz     short loc_18000D1D1
0x18000d1b5  movsxd  rax, dword ptr [rsp+128h+pv+0Ch]
0x18000d1ba  lea     rcx, [rsp+128h+vBits]
0x18000d1bf  add     rcx, rax; Buf1
0x18000d1c2  call    GetSurfaceType
0x18000d1c7  mov     ebx, eax
0x18000d1c9  test    eax, eax
0x18000d1cb  jz      short loc_18000D1D1
0x18000d1cd  bts     ebx, 7
0x18000d1d1  mov     rdx, rbp; h
0x18000d1d4  mov     rcx, rdi; hdc
0x18000d1d7  call    cs:__imp_SelectObject
0x18000d1dd  mov     rcx, rsi; ho
0x18000d1e0  call    cs:__imp_DeleteObject
0x18000d1e6  mov     rcx, rdi; hdc
0x18000d1e9  call    cs:__imp_DeleteDC
0x18000d1ef  mov     eax, ebx
0x18000d1f1  mov     cs:dword_18001D484, ebx
0x18000d1f7  jmp     loc_18000D108
```
