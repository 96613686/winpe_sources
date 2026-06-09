# CStatusBar::_SetParts(void)

- ea: `0x180023764`
- end: `0x180023942`
- name: `?_SetParts@CStatusBar@@IEAAJXZ`
- size: `478`
- prototype: `__int64 __fastcall(CStatusBar *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023710`
- `0x180026410`

## callees

- `0x180002240`
- `0x180023764`
- `0x180023948`
- `0x1800239bc`

## import_xrefs

- `SHLWAPI!__imp_ZoneComputePaneSize` at `0x1800237a7`
- `SHLWAPI!__imp_ZoneComputePaneSize` at `0x1800237a7`
- `USER32!InflateRect` at `0x1800238c7`
- `USER32!InflateRect` at `0x1800238c7`
- `USER32!GetSystemMetrics` at `0x1800237c8`
- `USER32!GetSystemMetrics` at `0x1800237d7`
- `USER32!GetSystemMetrics` at `0x1800238a7`
- `USER32!GetSystemMetrics` at `0x1800238b6`
- `USER32!GetSystemMetrics` at `0x1800238eb`
- `USER32!GetSystemMetrics` at `0x1800238fa`
- `USER32!GetSystemMetrics` at `0x1800237c8`
- `USER32!GetSystemMetrics` at `0x1800237d7`
- `USER32!GetSystemMetrics` at `0x1800238a7`
- `USER32!GetSystemMetrics` at `0x1800238b6`
- `USER32!GetSystemMetrics` at `0x1800238eb`
- `USER32!GetSystemMetrics` at `0x1800238fa`
- `USER32!GetClientRect` at `0x18002379d`
- `USER32!GetClientRect` at `0x18002379d`
- `USER32!SendMessageW` at `0x180023810`
- `USER32!SendMessageW` at `0x180023838`
- `USER32!SendMessageW` at `0x18002384d`
- `USER32!SendMessageW` at `0x18002386d`
- `USER32!SendMessageW` at `0x180023886`
- `USER32!SendMessageW` at `0x18002389c`
- `USER32!SendMessageW` at `0x1800238e0`
- `USER32!SendMessageW` at `0x180023911`
- `USER32!SendMessageW` at `0x180023810`
- `USER32!SendMessageW` at `0x180023838`
- `USER32!SendMessageW` at `0x18002384d`
- `USER32!SendMessageW` at `0x18002386d`
- `USER32!SendMessageW` at `0x180023886`
- `USER32!SendMessageW` at `0x18002389c`
- `USER32!SendMessageW` at `0x1800238e0`
- `USER32!SendMessageW` at `0x180023911`

## pseudocode

```c
__int64 __fastcall CStatusBar::_SetParts(CStatusBar *this)
{
  HWND v2; // rcx
  int v3; // eax
  int v4; // esi
  int v5; // edi
  int v6; // ebx
  int SystemMetrics; // eax
  HWND v8; // rcx
  int v9; // esi
  int v10; // eax
  LRESULT v11; // rax
  LRESULT v12; // rsi
  int v13; // edi
  int v14; // ebx
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  struct tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF
  _DWORD lParam[4]; // [rsp+30h] [rbp-28h] BYREF

  v2 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  if ( v2 )
  {
    GetClientRect(v2, &Rect);
    v3 = ZoneComputePaneSize(*((_QWORD *)this + 1));
    v4 = Rect.right - Rect.left;
    v5 = v3;
    lParam[0] = 1;
    *(_QWORD *)&lParam[1] = 0;
    v6 = 4 * GetSystemMetrics(45);
    SystemMetrics = GetSystemMetrics(49);
    v8 = (HWND)*((_QWORD *)this + 1);
    lParam[2] = -1;
    v9 = v4 - v6 - v5 - SystemMetrics;
    v10 = v9 - 125;
    if ( v9 - 125 < 1 )
      v10 = 1;
    lParam[0] = v10;
    if ( v9 < 1 )
      v9 = 1;
    lParam[1] = v9;
    v11 = SendMessageW(v8, 0x406u, 0, 0);
    v12 = v11;
    if ( v11 != 3 )
    {
      v13 = 0;
      if ( v11 > 0 )
      {
        do
        {
          SendMessageW(*((HWND *)this + 1), 0x40Bu, v13, 0);
          SendMessageW(*((HWND *)this + 1), 0x40Fu, v13++, 0);
        }
        while ( v13 < v12 );
      }
      SendMessageW(*((HWND *)this + 1), 0x404u, 0, 0);
    }
    SendMessageW(*((HWND *)this + 1), 0x404u, 3u, (LPARAM)lParam);
    SendMessageW(*((HWND *)this + 1), 0x40Au, 1u, (LPARAM)&Rect);
    v14 = -GetSystemMetrics(46);
    v15 = GetSystemMetrics(45);
    InflateRect(&Rect, -v15, v14);
    SendMessageW(*((HWND *)this + 1), 0x40Bu, 1u, (LPARAM)&::lParam);
    v16 = 2 * GetSystemMetrics(6);
    v17 = GetSystemMetrics(50);
    SendMessageW(*((HWND *)this + 1), 0x408u, v16 + v17, 0);
    CStatusBar::_SetZone(this);
    CStatusBar::_SetUserParts(this);
  }
  return 0;
}

```

## disassembly

```asm
0x180023764  push    rbp
0x180023766  push    rbx
0x180023767  push    rsi
0x180023768  push    rdi
0x180023769  push    r14
0x18002376b  push    r15
0x18002376d  mov     rbp, rsp
0x180023770  sub     rsp, 58h
0x180023774  mov     rax, cs:__security_cookie
0x18002377b  xor     rax, rsp
0x18002377e  mov     [rbp+var_18], rax
0x180023782  mov     r14, rcx
0x180023785  xorps   xmm0, xmm0
0x180023788  mov     rcx, [rcx+8]; hWnd
0x18002378c  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180023790  test    rcx, rcx
0x180023793  jz      loc_180023927
0x180023799  lea     rdx, [rbp+Rect]; lpRect
0x18002379d  call    cs:__imp_GetClientRect
0x1800237a3  mov     rcx, [r14+8]
0x1800237a7  call    cs:__imp_ZoneComputePaneSize
0x1800237ad  mov     esi, [rbp+Rect.right]
0x1800237b0  mov     r15d, 1
0x1800237b6  sub     esi, [rbp+Rect.left]
0x1800237b9  mov     edi, eax
0x1800237bb  xor     eax, eax
0x1800237bd  mov     [rbp+lParam], r15d
0x1800237c1  mov     qword ptr [rbp+lParam+4], rax
0x1800237c5  lea     ecx, [rax+2Dh]; nIndex
0x1800237c8  call    cs:__imp_GetSystemMetrics
0x1800237ce  mov     ebx, eax
0x1800237d0  lea     ecx, [r15+30h]; nIndex
0x1800237d4  shl     ebx, 2
0x1800237d7  call    cs:__imp_GetSystemMetrics
0x1800237dd  mov     rcx, [r14+8]; hWnd
0x1800237e1  sub     esi, ebx
0x1800237e3  sub     esi, edi
0x1800237e5  mov     [rbp+lParam+8], 0FFFFFFFFh
0x1800237ec  sub     esi, eax
0x1800237ee  mov     edx, 406h; Msg
0x1800237f3  lea     eax, [rsi-7Dh]
0x1800237f6  cmp     eax, r15d
0x1800237f9  cmovl   eax, r15d
0x1800237fd  cmp     esi, r15d
0x180023800  mov     [rbp+lParam], eax
0x180023803  cmovl   esi, r15d
0x180023807  xor     r9d, r9d; lParam
0x18002380a  xor     r8d, r8d; wParam
0x18002380d  mov     [rbp+lParam+4], esi
0x180023810  call    cs:__imp_SendMessageW
0x180023816  mov     rsi, rax
0x180023819  cmp     rax, 3
0x18002381d  jz      short loc_180023873
0x18002381f  xor     edi, edi
0x180023821  test    rax, rax
0x180023824  jle     short loc_18002385E
0x180023826  mov     rcx, [r14+8]; hWnd
0x18002382a  xor     r9d, r9d; lParam
0x18002382d  movsxd  rbx, edi
0x180023830  mov     edx, 40Bh; Msg
0x180023835  mov     r8, rbx; wParam
0x180023838  call    cs:__imp_SendMessageW
0x18002383e  mov     rcx, [r14+8]; hWnd
0x180023842  xor     r9d, r9d; lParam
0x180023845  mov     r8, rbx; wParam
0x180023848  mov     edx, 40Fh; Msg
0x18002384d  call    cs:__imp_SendMessageW
0x180023853  add     edi, r15d
0x180023856  movsxd  rax, edi
0x180023859  cmp     rax, rsi
0x18002385c  jl      short loc_180023826
0x18002385e  mov     rcx, [r14+8]; hWnd
0x180023862  xor     r9d, r9d; lParam
0x180023865  xor     r8d, r8d; wParam
0x180023868  mov     edx, 404h; Msg
0x18002386d  call    cs:__imp_SendMessageW
0x180023873  mov     rcx, [r14+8]; hWnd
0x180023877  lea     r9, [rbp+lParam]; lParam
0x18002387b  mov     edx, 404h; Msg
0x180023880  mov     r8d, 3; wParam
0x180023886  call    cs:__imp_SendMessageW
0x18002388c  mov     rcx, [r14+8]; hWnd
0x180023890  lea     r9, [rbp+Rect]; lParam
0x180023894  mov     r8, r15; wParam
0x180023897  mov     edx, 40Ah; Msg
0x18002389c  call    cs:__imp_SendMessageW
0x1800238a2  mov     ecx, 2Eh ; '.'; nIndex
0x1800238a7  call    cs:__imp_GetSystemMetrics
0x1800238ad  mov     ebx, eax
0x1800238af  mov     ecx, 2Dh ; '-'; nIndex
0x1800238b4  neg     ebx
0x1800238b6  call    cs:__imp_GetSystemMetrics
0x1800238bc  mov     r8d, ebx; dy
0x1800238bf  lea     rcx, [rbp+Rect]; lprc
0x1800238c3  neg     eax
0x1800238c5  mov     edx, eax; dx
0x1800238c7  call    cs:__imp_InflateRect
0x1800238cd  mov     rcx, [r14+8]; hWnd
0x1800238d1  lea     r9, lParam; lParam
0x1800238d8  mov     r8, r15; wParam
0x1800238db  mov     edx, 40Bh; Msg
0x1800238e0  call    cs:__imp_SendMessageW
0x1800238e6  mov     ecx, 6; nIndex
0x1800238eb  call    cs:__imp_GetSystemMetrics
0x1800238f1  mov     ebx, eax
0x1800238f3  mov     ecx, 32h ; '2'; nIndex
0x1800238f8  add     ebx, ebx
0x1800238fa  call    cs:__imp_GetSystemMetrics
0x180023900  mov     rcx, [r14+8]; hWnd
0x180023904  xor     r9d, r9d; lParam
0x180023907  add     eax, ebx
0x180023909  mov     edx, 408h; Msg
0x18002390e  movsxd  r8, eax; wParam
0x180023911  call    cs:__imp_SendMessageW
0x180023917  mov     rcx, r14; this
0x18002391a  call    ?_SetZone@CStatusBar@@IEAAJXZ; CStatusBar::_SetZone(void)
0x18002391f  mov     rcx, r14; this
0x180023922  call    ?_SetUserParts@CStatusBar@@IEAAXXZ; CStatusBar::_SetUserParts(void)
0x180023927  xor     eax, eax
0x180023929  mov     rcx, [rbp+var_18]
0x18002392d  xor     rcx, rsp; StackCookie
0x180023930  call    __security_check_cookie
0x180023935  add     rsp, 58h
0x180023939  pop     r15
0x18002393b  pop     r14
0x18002393d  pop     rdi
0x18002393e  pop     rsi
0x18002393f  pop     rbx
0x180023940  pop     rbp
0x180023941  retn
```
