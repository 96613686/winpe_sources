# Progress_Paint(PRO_DATA *,HDC__ *)

- ea: `0x180006884`
- end: `0x180006a2f`
- name: `?Progress_Paint@@YAXPEAUPRO_DATA@@PEAUHDC__@@@Z`
- size: `427`
- prototype: `void __fastcall(struct PRO_DATA *, HDC)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006320`

## callees

- `0x180006884`
- `0x180006a38`
- `0x180006cf4`
- `0x180007450`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006923`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006923`
- `GDI32!SelectObject` at `0x1800069ef`
- `GDI32!SelectObject` at `0x1800069ef`
- `GDI32!DeleteDC` at `0x180006a24`
- `GDI32!DeleteDC` at `0x180006a24`
- `GDI32!CreateCompatibleDC` at `0x1800069b4`
- `GDI32!CreateCompatibleDC` at `0x1800069b4`
- `GDI32!CreateCompatibleBitmap` at `0x1800069da`
- `GDI32!CreateCompatibleBitmap` at `0x1800069da`
- `GDI32!OffsetWindowOrgEx` at `0x180006a05`
- `GDI32!OffsetWindowOrgEx` at `0x180006a05`
- `USER32!IsRectEmpty` at `0x1800068e8`
- `USER32!IsRectEmpty` at `0x1800068e8`
- `USER32!SetTimer` at `0x180006967`
- `USER32!SetTimer` at `0x180006967`
- `USER32!BeginPaint` at `0x180006976`
- `USER32!BeginPaint` at `0x180006976`
- `USER32!EndPaint` at `0x18000691d`
- `USER32!EndPaint` at `0x18000691d`

## pseudocode

```c
void __fastcall Progress_Paint(struct PRO_DATA *a1, HDC a2)
{
  HDC v4; // rdi
  HDC v5; // rax
  LONG left; // r15d
  LONG top; // r12d
  LONG right; // r13d
  HBITMAP CompatibleBitmap; // rax
  LONG bottom; // [rsp+20h] [rbp-79h]
  __int128 v11; // [rsp+28h] [rbp-71h] BYREF
  __int128 v12; // [rsp+38h] [rbp-61h]
  _BYTE v13[24]; // [rsp+48h] [rbp-51h] BYREF
  PAINTSTRUCT Paint; // [rsp+60h] [rbp-39h] BYREF

  v11 = 0;
  v12 = 0;
  memset(v13, 0, sizeof(v13));
  memset_0(&Paint, 0, sizeof(Paint));
  if ( a2 )
  {
    v4 = a2;
  }
  else
  {
    v5 = BeginPaint(*(HWND *)a1, &Paint);
    v4 = v5;
    if ( !g_fDisableDoubleBuffering )
    {
      left = Paint.rcPaint.left;
      top = Paint.rcPaint.top;
      right = Paint.rcPaint.right;
      *(_QWORD *)v13 = v5;
      bottom = Paint.rcPaint.bottom;
      *(RECT *)&v13[8] = Paint.rcPaint;
      *((_QWORD *)&v11 + 1) = CreateCompatibleDC(v5);
      if ( *((_QWORD *)&v11 + 1) )
      {
        CompatibleBitmap = CreateCompatibleBitmap(v4, right - left, bottom - top);
        *(_QWORD *)&v12 = CompatibleBitmap;
        if ( CompatibleBitmap )
        {
          *((_QWORD *)&v12 + 1) = SelectObject(*((HDC *)&v11 + 1), CompatibleBitmap);
          OffsetWindowOrgEx(*((HDC *)&v11 + 1), left, top, 0);
          LODWORD(v11) = 1;
          v4 = (HDC)*((_QWORD *)&v11 + 1);
        }
        else
        {
          DeleteDC(*((HDC *)&v11 + 1));
        }
      }
    }
  }
  if ( !IsRectEmpty(&Paint.rcPaint) && (*((_BYTE *)a1 + 64) & 8) != 0 )
    SetTimer(*(HWND *)a1, 1u, *((_DWORD *)a1 + 19), 0);
  if ( *((_QWORD *)a1 + 7) )
    Progress_PaintThemed(a1, v4);
  else
    Progress_PaintTraditional(a1, v4);
  if ( !a2 )
  {
    CCEndDoubleBuffer(&v11);
    EndPaint(*(HWND *)a1, &Paint);
  }
  *((_DWORD *)a1 + 23) = GetTickCount();
}

```

## disassembly

```asm
0x180006884  mov     [rsp-8+arg_10], rbx
0x180006889  push    rbp
0x18000688a  push    rsi
0x18000688b  push    rdi
0x18000688c  push    r12
0x18000688e  push    r13
0x180006890  push    r14
0x180006892  push    r15
0x180006894  lea     rbp, [rsp-27h]
0x180006899  sub     rsp, 0C0h
0x1800068a0  mov     rax, cs:__security_cookie
0x1800068a7  xor     rax, rsp
0x1800068aa  mov     [rbp+57h+var_40], rax
0x1800068ae  xorps   xmm0, xmm0
0x1800068b1  xor     eax, eax
0x1800068b3  mov     r14, rdx
0x1800068b6  mov     [rbp+57h+var_98], rax
0x1800068ba  mov     rbx, rcx
0x1800068bd  xor     edx, edx; Val
0x1800068bf  lea     rcx, [rbp+57h+Paint]; void *
0x1800068c3  lea     r8d, [rax+48h]; Size
0x1800068c7  movups  [rbp+57h+var_C8], xmm0
0x1800068cb  movups  [rbp+57h+var_B8], xmm0
0x1800068cf  movups  [rbp+57h+var_A8], xmm0
0x1800068d3  call    memset_0
0x1800068d8  test    r14, r14
0x1800068db  jz      loc_18000696F
0x1800068e1  mov     rdi, r14
0x1800068e4  lea     rcx, [rbp+57h+Paint.rcPaint]; lprc
0x1800068e8  call    cs:__imp_IsRectEmpty
0x1800068ee  test    eax, eax
0x1800068f0  jz      short loc_180006953
0x1800068f2  cmp     qword ptr [rbx+38h], 0
0x1800068f7  mov     rdx, rdi; HDC
0x1800068fa  mov     rcx, rbx; struct PRO_DATA *
0x1800068fd  jz      loc_180006A1A
0x180006903  call    ?Progress_PaintThemed@@YAXPEAUPRO_DATA@@PEAUHDC__@@@Z; Progress_PaintThemed(PRO_DATA *,HDC__ *)
0x180006908  test    r14, r14
0x18000690b  jnz     short loc_180006923
0x18000690d  lea     rcx, [rbp+57h+var_C8]
0x180006911  call    CCEndDoubleBuffer
0x180006916  mov     rcx, [rbx]; hWnd
0x180006919  lea     rdx, [rbp+57h+Paint]; lpPaint
0x18000691d  call    cs:__imp_EndPaint
0x180006923  call    cs:__imp_GetTickCount
0x180006929  mov     [rbx+5Ch], eax
0x18000692c  mov     rcx, [rbp+57h+var_40]
0x180006930  xor     rcx, rsp; StackCookie
0x180006933  call    __security_check_cookie
0x180006938  mov     rbx, [rsp+0F0h+arg_10]
0x180006940  add     rsp, 0C0h
0x180006947  pop     r15
0x180006949  pop     r14
0x18000694b  pop     r13
0x18000694d  pop     r12
0x18000694f  pop     rdi
0x180006950  pop     rsi
0x180006951  pop     rbp
0x180006952  retn
0x180006953  test    byte ptr [rbx+40h], 8
0x180006957  jz      short loc_1800068F2
0x180006959  mov     r8d, [rbx+4Ch]; uElapse
0x18000695d  xor     r9d, r9d; lpTimerFunc
0x180006960  mov     rcx, [rbx]; hWnd
0x180006963  lea     edx, [r9+1]; nIDEvent
0x180006967  call    cs:__imp_SetTimer
0x18000696d  jmp     short loc_1800068F2
0x18000696f  mov     rcx, [rbx]; hWnd
0x180006972  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180006976  call    cs:__imp_BeginPaint
0x18000697c  cmp     cs:g_fDisableDoubleBuffering, 0
0x180006983  mov     rdi, rax
0x180006986  jnz     loc_1800068E4
0x18000698c  mov     r15d, [rbp+57h+Paint.rcPaint.left]
0x180006990  mov     rcx, rdi; hdc
0x180006993  mov     r12d, [rbp+57h+Paint.rcPaint.top]
0x180006997  mov     r13d, [rbp+57h+Paint.rcPaint.right]
0x18000699b  mov     qword ptr [rbp+57h+var_A8], rax
0x18000699f  mov     eax, [rbp+57h+Paint.rcPaint.bottom]
0x1800069a2  mov     [rbp+57h+var_D0], eax
0x1800069a5  mov     dword ptr [rbp+57h+var_98+4], eax
0x1800069a8  mov     dword ptr [rbp+57h+var_A8+8], r15d
0x1800069ac  mov     dword ptr [rbp+57h+var_A8+0Ch], r12d
0x1800069b0  mov     dword ptr [rbp+57h+var_98], r13d
0x1800069b4  call    cs:__imp_CreateCompatibleDC
0x1800069ba  mov     qword ptr [rbp+57h+var_C8+8], rax
0x1800069be  mov     rsi, rax
0x1800069c1  test    rax, rax
0x1800069c4  jz      loc_1800068E4
0x1800069ca  mov     r8d, [rbp+57h+var_D0]
0x1800069ce  sub     r13d, r15d
0x1800069d1  sub     r8d, r12d; cy
0x1800069d4  mov     edx, r13d; cx
0x1800069d7  mov     rcx, rdi; hdc
0x1800069da  call    cs:__imp_CreateCompatibleBitmap
0x1800069e0  mov     qword ptr [rbp+57h+var_B8], rax
0x1800069e4  mov     rcx, rsi; hdc
0x1800069e7  test    rax, rax
0x1800069ea  jz      short loc_180006A24
0x1800069ec  mov     rdx, rax; h
0x1800069ef  call    cs:__imp_SelectObject
0x1800069f5  xor     r9d, r9d; lppt
0x1800069f8  mov     r8d, r12d; y
0x1800069fb  mov     edx, r15d; x
0x1800069fe  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180006a02  mov     rcx, rsi; hdc
0x180006a05  call    cs:__imp_OffsetWindowOrgEx
0x180006a0b  mov     dword ptr [rbp+57h+var_C8], 1
0x180006a12  mov     rdi, rsi
0x180006a15  jmp     loc_1800068E4
0x180006a1a  call    ?Progress_PaintTraditional@@YAXPEAUPRO_DATA@@PEAUHDC__@@@Z; Progress_PaintTraditional(PRO_DATA *,HDC__ *)
0x180006a1f  jmp     loc_180006908
0x180006a24  call    cs:__imp_DeleteDC
0x180006a2a  jmp     loc_1800068E4
```
