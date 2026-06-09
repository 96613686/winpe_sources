# CRailContWndExt::OnConQueuePanelWndEraseBackground(HWND__ *,unsigned __int64,__int64)

- ea: `0x140021c24`
- end: `0x140021d22`
- name: `?OnConQueuePanelWndEraseBackground@CRailContWndExt@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `254`
- prototype: `__int64(CRailContWndExt *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001f460`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x140021c24`
- `0x140113390`

## import_xrefs

- `USER32!GetClientRect` at `0x140021c7a`
- `USER32!GetClientRect` at `0x140021c7a`
- `GDI32!PatBlt` at `0x140021ca9`
- `GDI32!PatBlt` at `0x140021ca9`
- `GDI32!SelectObject` at `0x140021c86`
- `GDI32!SelectObject` at `0x140021c86`
- `GDI32!CreateSolidBrush` at `0x140021c64`
- `GDI32!CreateSolidBrush` at `0x140021c64`
- `GDI32!DeleteObject` at `0x140021cb2`
- `GDI32!DeleteObject` at `0x140021cb2`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::OnConQueuePanelWndEraseBackground(CRailContWndExt *this, HWND a2, HDC a3)
{
  __int64 v3; // rdi
  HBRUSH SolidBrush; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct tagRECT Rect; // [rsp+30h] [rbp-38h] BYREF

  v3 = 0;
  if ( (*((_DWORD *)this + 517) & 0x100) != 0 )
  {
    Rect = 0;
    SolidBrush = CreateSolidBrush(0xFFFFFFu);
    if ( SolidBrush )
    {
      GetClientRect(a2, &Rect);
      SelectObject(a3, SolidBrush);
      PatBlt(a3, 0, 0, Rect.right, Rect.bottom, 0xF00021u);
      DeleteObject(SolidBrush);
      return 1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140021c24  mov     [rsp+arg_0], rbx
0x140021c29  push    rbp
0x140021c2a  push    rsi
0x140021c2b  push    rdi
0x140021c2c  sub     rsp, 50h
0x140021c30  mov     rax, cs:__security_cookie
0x140021c37  xor     rax, rsp
0x140021c3a  mov     [rsp+68h+var_28], rax
0x140021c3f  xor     edi, edi
0x140021c41  mov     rsi, r8
0x140021c44  test    dword ptr [rcx+814h], 100h
0x140021c4e  mov     rbp, rdx
0x140021c51  jz      loc_140021D05
0x140021c57  xorps   xmm0, xmm0
0x140021c5a  mov     ecx, 0FFFFFFh; color
0x140021c5f  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x140021c64  call    cs:__imp_CreateSolidBrush
0x140021c6a  mov     rbx, rax
0x140021c6d  test    rax, rax
0x140021c70  jz      short loc_140021CBF
0x140021c72  lea     rdx, [rsp+68h+Rect]; lpRect
0x140021c77  mov     rcx, rbp; hWnd
0x140021c7a  call    cs:__imp_GetClientRect
0x140021c80  mov     rdx, rbx; h
0x140021c83  mov     rcx, rsi; hdc
0x140021c86  call    cs:__imp_SelectObject
0x140021c8c  mov     eax, [rsp+68h+Rect.bottom]
0x140021c90  xor     r8d, r8d; y
0x140021c93  mov     r9d, [rsp+68h+Rect.right]; w
0x140021c98  xor     edx, edx; x
0x140021c9a  mov     rcx, rsi; hdc
0x140021c9d  mov     [rsp+68h+rop], 0F00021h; rop
0x140021ca5  mov     [rsp+68h+h], eax; h
0x140021ca9  call    cs:__imp_PatBlt
0x140021caf  mov     rcx, rbx; ho
0x140021cb2  call    cs:__imp_DeleteObject
0x140021cb8  mov     edi, 1
0x140021cbd  jmp     short loc_140021D05
0x140021cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140021cc6  lea     rax, WPP_GLOBAL_Control
0x140021ccd  cmp     rcx, rax
0x140021cd0  jz      short loc_140021D05
0x140021cd2  test    dword ptr [rcx+1Ch], 1000h
0x140021cd9  jz      short loc_140021D05
0x140021cdb  cmp     byte ptr [rcx+19h], 2
0x140021cdf  jb      short loc_140021D05
0x140021ce1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140021ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ced  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140021cf4  mov     edx, 69h ; 'i'
0x140021cf9  mov     r9d, eax
0x140021cfc  mov     rcx, [rcx+10h]
0x140021d00  call    WPP_SF_d
0x140021d05  mov     rax, rdi
0x140021d08  mov     rcx, [rsp+68h+var_28]
0x140021d0d  xor     rcx, rsp; StackCookie
0x140021d10  call    __security_check_cookie
0x140021d15  mov     rbx, [rsp+68h+arg_0]
0x140021d1a  add     rsp, 50h
0x140021d1e  pop     rdi
0x140021d1f  pop     rsi
0x140021d20  pop     rbp
0x140021d21  retn
```
