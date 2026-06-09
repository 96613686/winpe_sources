# DPCreateHandler

- ea: `0x18004021c`
- end: `0x180040423`
- name: `DPCreateHandler`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800414b0`

## callees

- `0x1800115f0`
- `0x1800184b8`
- `0x18004021c`
- `0x180040560`
- `0x180040730`
- `0x180043034`
- `0x1800441b4`
- `0x180044f88`

## import_xrefs

- `GDI32!GetStockObject` at `0x1800403a1`
- `GDI32!GetStockObject` at `0x1800403a1`
- `KERNEL32!GetLocalTime` at `0x180040389`
- `KERNEL32!GetLocalTime` at `0x180040389`
- `KERNEL32!GetUserDefaultLCID` at `0x180040329`
- `KERNEL32!GetUserDefaultLCID` at `0x180040329`
- `USER32!GetWindowLongW` at `0x180040340`
- `USER32!GetWindowLongW` at `0x180040340`
- `USER32!SendMessageW` at `0x1800403e9`
- `USER32!SendMessageW` at `0x1800403e9`
- `USER32!CreateWindowExW` at `0x1800402cc`
- `USER32!CreateWindowExW` at `0x1800402cc`

## pseudocode

```c
__int64 __fastcall DPCreateHandler(__int64 a1, HWND a2, __int64 a3)
{
  int v6; // r9d
  _DWORD *v8; // rdi
  HINSTANCE hInstance; // rax
  unsigned int v10; // eax
  __int16 UserDefaultLCID; // ax
  __int16 v12; // di
  __int16 v13; // di
  HGDIOBJ StockObject; // rax
  HWND v15; // rcx
  LRESULT v16; // rax
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-48h] BYREF

  SystemTime = 0;
  CIInitialize(a1, a2, a3);
  v6 = *(_DWORD *)(a1 + 16);
  if ( (v6 & 0xFFC0) != 0 )
    return -1;
  v8 = (_DWORD *)(a1 + 376);
  if ( (v6 & 1) != 0 )
  {
    hInstance = g_hinst;
    *v8 |= 2u;
    *(_QWORD *)(a1 + 56) = CreateWindowExW(
                             0,
                             L"msctls_updown32",
                             0,
                             v6 & 0x8000000 | 0x50000000u,
                             0x80000000,
                             0x80000000,
                             0x80000000,
                             0x80000000,
                             a2,
                             (HMENU)0x3E8,
                             hInstance,
                             0);
  }
  v10 = *(_DWORD *)(a1 + 16);
  if ( (v10 & 2) != 0 )
  {
    *(_DWORD *)(a1 + 160) = 1;
    *(_DWORD *)(a1 + 360) = -1;
  }
  *v8 &= ~1u;
  *v8 |= ((v10 >> 27) & 1) == 0;
  *v8 |= 0x40u;
  *(_OWORD *)(a1 + 104) = c_stEpoch;
  *(_QWORD *)(a1 + 368) = 1;
  *(_OWORD *)(a1 + 120) = c_stArmageddon;
  MCGetCalendarInfo(a1 + 272);
  UserDefaultLCID = GetUserDefaultLCID();
  *(_DWORD *)(a1 + 304) &= 0xFFFFFFFC;
  v12 = UserDefaultLCID;
  if ( (GetWindowLongW(a2, -20) & 0x400000) != 0 )
  {
    v13 = v12 & 0x3FF;
    if ( (*(_BYTE *)(a1 + 16) & 8) != 0 )
    {
      *(_DWORD *)(a1 + 304) |= 1u;
      if ( v13 == 1 )
        *(_DWORD *)(a1 + 304) |= 2u;
    }
    else if ( v13 == 13 )
    {
      *(_DWORD *)(a1 + 304) |= 1u;
    }
  }
  *(_QWORD *)(a1 + 152) = a1;
  GetLocalTime(&SystemTime);
  *(_SYSTEMTIME *)(a1 + 204) = SystemTime;
  StockObject = GetStockObject(17);
  *(_DWORD *)(a1 + 376) |= 0x100u;
  *(_QWORD *)(a1 + 168) = StockObject;
  DPHandleLocaleChange(a1);
  MCLoadString(4165, a1 + 242, 15);
  v15 = *(HWND *)(a3 + 24);
  v16 = 0;
  if ( v15 )
    v16 = SendMessageW(v15, 0x31u, 0, 0);
  DPHandleSetFont(a1, v16, 0);
  MCInitColorArray(a1 + 80);
  return 0;
}

```

## disassembly

```asm
0x18004021c  push    rbx
0x18004021e  push    rbp
0x18004021f  push    rsi
0x180040220  push    rdi
0x180040221  push    r14
0x180040223  sub     rsp, 80h
0x18004022a  mov     rax, cs:__security_cookie
0x180040231  xor     rax, rsp
0x180040234  mov     [rsp+0A8h+var_38], rax
0x180040239  xorps   xmm0, xmm0
0x18004023c  mov     rbp, r8
0x18004023f  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x180040244  mov     rsi, rdx
0x180040247  mov     rbx, rcx
0x18004024a  call    CIInitialize
0x18004024f  mov     r9d, [rbx+10h]
0x180040253  test    r9d, 0FFC0h
0x18004025a  jz      short loc_180040265
0x18004025c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040260  jmp     loc_180040408
0x180040265  mov     r14d, 1
0x18004026b  lea     rdi, [rbx+178h]
0x180040272  test    r14b, r9b
0x180040275  jz      short loc_1800402D6
0x180040277  mov     rax, cs:g_hinst
0x18004027e  lea     rdx, aMsctlsUpdown32; "msctls_updown32"
0x180040285  or      dword ptr [rdi], 2
0x180040288  and     r9d, 8000000h
0x18004028f  mov     [rsp+0A8h+lpParam], 0; lpParam
0x180040298  or      r9d, 50000000h; dwStyle
0x18004029f  mov     [rsp+0A8h+hInstance], rax; hInstance
0x1800402a4  xor     r8d, r8d; lpWindowName
0x1800402a7  mov     [rsp+0A8h+hMenu], 3E8h; hMenu
0x1800402b0  mov     eax, 80000000h
0x1800402b5  mov     [rsp+0A8h+hWndParent], rsi; hWndParent
0x1800402ba  xor     ecx, ecx; dwExStyle
0x1800402bc  mov     [rsp+0A8h+nHeight], eax; nHeight
0x1800402c0  mov     [rsp+0A8h+nWidth], eax; nWidth
0x1800402c4  mov     [rsp+0A8h+Y], eax; Y
0x1800402c8  mov     [rsp+0A8h+X], eax; X
0x1800402cc  call    cs:__imp_CreateWindowExW
0x1800402d2  mov     [rbx+38h], rax
0x1800402d6  mov     eax, [rbx+10h]
0x1800402d9  test    al, 2
0x1800402db  jz      short loc_1800402EE
0x1800402dd  mov     [rbx+0A0h], r14d
0x1800402e4  mov     dword ptr [rbx+168h], 0FFFFFFFFh
0x1800402ee  and     dword ptr [rdi], 0FFFFFFFEh
0x1800402f1  lea     rcx, [rbx+110h]
0x1800402f8  shr     eax, 1Bh
0x1800402fb  not     eax
0x1800402fd  and     eax, r14d
0x180040300  or      [rdi], eax
0x180040302  or      dword ptr [rdi], 40h
0x180040305  movups  xmm0, cs:c_stEpoch
0x18004030c  movdqu  xmmword ptr [rbx+68h], xmm0
0x180040311  movups  xmm1, cs:c_stArmageddon
0x180040318  mov     [rbx+170h], r14
0x18004031f  movdqu  xmmword ptr [rbx+78h], xmm1
0x180040324  call    MCGetCalendarInfo
0x180040329  call    cs:__imp_GetUserDefaultLCID
0x18004032f  and     dword ptr [rbx+130h], 0FFFFFFFCh
0x180040336  mov     edx, 0FFFFFFECh; nIndex
0x18004033b  mov     rcx, rsi; hWnd
0x18004033e  mov     edi, eax
0x180040340  call    cs:__imp_GetWindowLongW
0x180040346  bt      eax, 16h
0x18004034a  jnb     short loc_18004037D
0x18004034c  mov     eax, 3FFh
0x180040351  and     di, ax
0x180040354  test    byte ptr [rbx+10h], 8
0x180040358  jz      short loc_180040370
0x18004035a  or      [rbx+130h], r14d
0x180040361  cmp     di, r14w
0x180040365  jnz     short loc_18004037D
0x180040367  or      dword ptr [rbx+130h], 2
0x18004036e  jmp     short loc_18004037D
0x180040370  cmp     di, 0Dh
0x180040374  jnz     short loc_18004037D
0x180040376  or      [rbx+130h], r14d
0x18004037d  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180040382  mov     [rbx+98h], rbx
0x180040389  call    cs:__imp_GetLocalTime
0x18004038f  movups  xmm0, xmmword ptr [rsp+0A8h+SystemTime.wYear]
0x180040394  mov     ecx, 11h; i
0x180040399  movdqu  xmmword ptr [rbx+0CCh], xmm0
0x1800403a1  call    cs:__imp_GetStockObject
0x1800403a7  bts     dword ptr [rbx+178h], 8
0x1800403af  mov     rcx, rbx
0x1800403b2  mov     [rbx+0A8h], rax
0x1800403b9  call    DPHandleLocaleChange
0x1800403be  lea     rdx, [rbx+0F2h]
0x1800403c5  mov     ecx, 1045h
0x1800403ca  mov     r8d, 0Fh
0x1800403d0  call    MCLoadString
0x1800403d5  mov     rcx, [rbp+18h]; hWnd
0x1800403d9  xor     eax, eax
0x1800403db  test    rcx, rcx
0x1800403de  jz      short loc_1800403EF
0x1800403e0  xor     r9d, r9d; lParam
0x1800403e3  lea     edx, [rax+31h]; Msg
0x1800403e6  xor     r8d, r8d; wParam
0x1800403e9  call    cs:__imp_SendMessageW
0x1800403ef  xor     r8d, r8d
0x1800403f2  mov     rdx, rax
0x1800403f5  mov     rcx, rbx
0x1800403f8  call    DPHandleSetFont
0x1800403fd  lea     rcx, [rbx+50h]
0x180040401  call    MCInitColorArray
0x180040406  xor     eax, eax
0x180040408  mov     rcx, [rsp+0A8h+var_38]
0x18004040d  xor     rcx, rsp; StackCookie
0x180040410  call    __security_check_cookie
0x180040415  add     rsp, 80h
0x18004041c  pop     r14
0x18004041e  pop     rdi
0x18004041f  pop     rsi
0x180040420  pop     rbp
0x180040421  pop     rbx
0x180040422  retn
```
