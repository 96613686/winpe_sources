# TrackOnCreate

- ea: `0x18006ee98`
- end: `0x18006f08f`
- name: `TrackOnCreate`
- size: `503`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18006e230`

## callees

- `0x1800115f0`
- `0x1800184b8`
- `0x1800190a4`
- `0x18006dd50`
- `0x18006ee98`
- `0x18008691c`
- `0x180090020`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18006eed4`
- `KERNEL32!LocalAlloc` at `0x18006eed4`
- `USER32!SendMessageW` at `0x18006f059`
- `USER32!SendMessageW` at `0x18006f059`
- `USER32!SetWindowLongPtrW` at `0x18006eef3`
- `USER32!SetWindowLongPtrW` at `0x18006eef3`
- `USER32!CreateWindowExW` at `0x18006eff7`
- `USER32!CreateWindowExW` at `0x18006eff7`

## pseudocode

```c
__int64 __fastcall TrackOnCreate(HWND hWnd, __int64 a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  int v7; // eax
  bool v8; // zf
  __int64 (__fastcall *v9)(_QWORD, _QWORD); // rax
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  HWND Window; // rax
  LPARAM lParam; // [rsp+60h] [rbp-9h] BYREF
  HWND v15; // [rsp+68h] [rbp-1h]
  HWND v16; // [rsp+70h] [rbp+7h]
  __int64 v17; // [rsp+78h] [rbp+Fh]
  __int64 v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]
  __int64 v20; // [rsp+90h] [rbp+27h]
  __int64 v21; // [rsp+98h] [rbp+2Fh]

  InitDitherBrush();
  InitGlobalColors();
  v4 = LocalAlloc(0x40u, 0xE0u);
  v5 = v4;
  if ( !v4 )
    return -1;
  SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v4);
  CIInitialize(v5, hWnd, a2);
  v7 = g_cyHScroll;
  v5[49] = -1;
  v5[19] = 100;
  v5[40] = 1;
  v5[41] = -1;
  v5[42] = 1;
  v8 = g_fDBCSInputEnabled == 0;
  v5[24] = 4 * v7 / 3;
  if ( !v8 )
  {
    v9 = g_pfnImmAssociateContext;
    if ( g_pfnImmAssociateContext )
      v9 = (__int64 (__fastcall *)(_QWORD, _QWORD))g_pfnImmAssociateContext(hWnd, 0);
    *((_QWORD *)v5 + 25) = v9;
  }
  v10 = v5[4];
  v11 = v10 & 4;
  if ( (v10 & 2) != 0 )
    v12 = v11 != 0 ? 3 : 1;
  else
    v12 = v11 != 0 ? 2 : 0;
  v5[47] = v12;
  if ( (v10 & 0x100) != 0 )
  {
    Window = CreateWindowExW(
               0,
               L"tooltips_class32",
               &WindowName,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               *(HWND *)v5,
               0,
               g_hinst,
               0);
    *((_QWORD *)v5 + 22) = Window;
    if ( Window )
    {
      v15 = *(HWND *)v5;
      v16 = v15;
      v19 = 0;
      v21 = 0;
      lParam = 0x2300000040LL;
      v20 = -1;
      v18 = 0;
      v17 = 0;
      SendMessageW(Window, 0x432u, 0, (LPARAM)&lParam);
    }
    else
    {
      v5[4] &= ~0x100u;
    }
  }
  TBResize(v5);
  return 0;
}

```

## disassembly

```asm
0x18006ee98  mov     [rsp-8+arg_10], rbx
0x18006ee9d  push    rbp
0x18006ee9e  push    rsi
0x18006ee9f  push    rdi
0x18006eea0  lea     rbp, [rsp-47h]
0x18006eea5  sub     rsp, 0B0h
0x18006eeac  mov     rax, cs:__security_cookie
0x18006eeb3  xor     rax, rsp
0x18006eeb6  mov     [rbp+57h+var_20], rax
0x18006eeba  mov     rsi, rdx
0x18006eebd  mov     rdi, rcx
0x18006eec0  call    InitDitherBrush
0x18006eec5  call    InitGlobalColors
0x18006eeca  mov     edx, 0E0h; uBytes
0x18006eecf  mov     ecx, 40h ; '@'; uFlags
0x18006eed4  call    cs:__imp_LocalAlloc
0x18006eeda  mov     rbx, rax
0x18006eedd  test    rax, rax
0x18006eee0  jnz     short loc_18006EEEB
0x18006eee2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006eee6  jmp     loc_18006F070
0x18006eeeb  mov     r8, rbx; dwNewLong
0x18006eeee  xor     edx, edx; nIndex
0x18006eef0  mov     rcx, rdi; hWnd
0x18006eef3  call    cs:__imp_SetWindowLongPtrW
0x18006eef9  mov     r8, rsi
0x18006eefc  mov     rdx, rdi
0x18006eeff  mov     rcx, rbx
0x18006ef02  call    CIInitialize
0x18006ef07  mov     eax, cs:g_cyHScroll
0x18006ef0d  mov     esi, 1
0x18006ef12  mov     dword ptr [rbx+0C4h], 0FFFFFFFFh
0x18006ef1c  mov     dword ptr [rbx+4Ch], 64h ; 'd'
0x18006ef23  mov     [rbx+0A0h], esi
0x18006ef29  lea     ecx, ds:0[rax*4]
0x18006ef30  mov     dword ptr [rbx+0A4h], 0FFFFFFFFh
0x18006ef3a  mov     eax, 55555556h
0x18006ef3f  mov     [rbx+0A8h], esi
0x18006ef45  imul    ecx
0x18006ef47  mov     eax, edx
0x18006ef49  shr     eax, 1Fh
0x18006ef4c  add     edx, eax
0x18006ef4e  cmp     cs:g_fDBCSInputEnabled, 0
0x18006ef55  mov     [rbx+60h], edx
0x18006ef58  jz      short loc_18006EF77
0x18006ef5a  mov     rax, cs:g_pfnImmAssociateContext
0x18006ef61  test    rax, rax
0x18006ef64  jz      short loc_18006EF70
0x18006ef66  xor     edx, edx
0x18006ef68  mov     rcx, rdi
0x18006ef6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef70  mov     [rbx+0C8h], rax
0x18006ef77  mov     ecx, [rbx+10h]
0x18006ef7a  mov     eax, ecx
0x18006ef7c  and     eax, 4
0x18006ef7f  test    cl, 2
0x18006ef82  jz      short loc_18006EF8F
0x18006ef84  neg     eax
0x18006ef86  sbb     eax, eax
0x18006ef88  and     eax, 2
0x18006ef8b  add     eax, esi
0x18006ef8d  jmp     short loc_18006EF96
0x18006ef8f  neg     eax
0x18006ef91  sbb     eax, eax
0x18006ef93  and     eax, 2
0x18006ef96  mov     [rbx+0BCh], eax
0x18006ef9c  bt      ecx, 8
0x18006efa0  jnb     loc_18006F066
0x18006efa6  mov     rax, cs:g_hinst
0x18006efad  lea     r8, WindowName; lpWindowName
0x18006efb4  mov     [rsp+0C0h+lpParam], 0; lpParam
0x18006efbd  lea     rdx, c_szSToolTipsClass; "tooltips_class32"
0x18006efc4  mov     [rsp+0C0h+hInstance], rax; hInstance
0x18006efc9  mov     r9d, 80000000h; dwStyle
0x18006efcf  mov     rax, [rbx]
0x18006efd2  xor     ecx, ecx; dwExStyle
0x18006efd4  mov     [rsp+0C0h+hMenu], 0; hMenu
0x18006efdd  mov     [rsp+0C0h+hWndParent], rax; hWndParent
0x18006efe2  mov     eax, 80000000h
0x18006efe7  mov     [rsp+0C0h+nHeight], eax; nHeight
0x18006efeb  mov     [rsp+0C0h+nWidth], eax; nWidth
0x18006efef  mov     [rsp+0C0h+Y], eax; Y
0x18006eff3  mov     [rsp+0C0h+X], eax; X
0x18006eff7  call    cs:__imp_CreateWindowExW
0x18006effd  mov     [rbx+0B0h], rax
0x18006f004  test    rax, rax
0x18006f007  jz      short loc_18006F061
0x18006f009  mov     rcx, [rbx]
0x18006f00c  lea     r9, [rbp+57h+lParam]; lParam
0x18006f010  mov     [rbp+57h+var_58], rcx
0x18006f014  xor     r8d, r8d; wParam
0x18006f017  mov     [rbp+57h+var_50], rcx
0x18006f01b  mov     edx, 432h; Msg
0x18006f020  mov     rcx, rax; hWnd
0x18006f023  mov     [rbp+57h+var_38], 0
0x18006f02b  mov     [rbp+57h+var_28], 0
0x18006f033  mov     dword ptr [rbp+57h+lParam], 40h ; '@'
0x18006f03a  mov     dword ptr [rbp+57h+lParam+4], 23h ; '#'
0x18006f041  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFFh
0x18006f049  mov     [rbp+57h+var_40], 0
0x18006f051  mov     [rbp+57h+var_48], 0
0x18006f059  call    cs:__imp_SendMessageW
0x18006f05f  jmp     short loc_18006F066
0x18006f061  btr     dword ptr [rbx+10h], 8
0x18006f066  mov     rcx, rbx
0x18006f069  call    TBResize
0x18006f06e  xor     eax, eax
0x18006f070  mov     rcx, [rbp+57h+var_20]
0x18006f074  xor     rcx, rsp; StackCookie
0x18006f077  call    __security_check_cookie
0x18006f07c  mov     rbx, [rsp+0C0h+arg_10]
0x18006f084  add     rsp, 0B0h
0x18006f08b  pop     rdi
0x18006f08c  pop     rsi
0x18006f08d  pop     rbp
0x18006f08e  retn
```
