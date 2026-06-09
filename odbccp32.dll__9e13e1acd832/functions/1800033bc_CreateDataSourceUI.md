# CreateDataSourceUI

- ea: `0x1800033bc`
- end: `0x180003567`
- name: `CreateDataSourceUI`
- size: `427`
- prototype: `__int64 __fastcall(HWND, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000295c`

## callees

- `0x1800033bc`
- `0x180004bac`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x1800034df`
- `USER32!GetDesktopWindow` at `0x1800034df`
- `COMCTL32!PropertySheetW` at `0x180003534`
- `COMCTL32!PropertySheetW` at `0x180003534`

## pseudocode

```c
__int64 __fastcall CreateDataSourceUI(HWND a1, _QWORD *a2)
{
  unsigned int v4; // esi
  HWND DesktopWindow; // rax
  __int64 v6; // rax
  bool v7; // zf
  PROPSHEETHEADERW_V2 v9; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v12)(HWND); // [rsp+A8h] [rbp-58h]
  _QWORD *v13; // [rsp+B0h] [rbp-50h]
  __int64 v14; // [rsp+E8h] [rbp-18h]
  HINSTANCE v15; // [rsp+F0h] [rbp-10h]
  __int64 v16; // [rsp+F8h] [rbp-8h]
  __int64 v17; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v18)(HWND); // [rsp+110h] [rbp+10h]
  _QWORD *v19; // [rsp+118h] [rbp+18h]
  __int64 v20; // [rsp+150h] [rbp+50h]
  HINSTANCE v21; // [rsp+158h] [rbp+58h]
  __m128i v22; // [rsp+160h] [rbp+60h]
  __int64 (__fastcall *v23)(HWND); // [rsp+178h] [rbp+78h]
  _QWORD *v24; // [rsp+180h] [rbp+80h]
  __int64 v25; // [rsp+1B8h] [rbp+B8h]
  HINSTANCE v26; // [rsp+1C0h] [rbp+C0h]
  __int64 v27; // [rsp+1C8h] [rbp+C8h]
  __int64 v28; // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v29)(); // [rsp+1E0h] [rbp+E0h]
  _QWORD *v30; // [rsp+1E8h] [rbp+E8h]

  v4 = 1;
  memset_0(v10, 0, 0x1A0u);
  memset_0(&v9.hwndParent, 0, 0x58u);
  v18 = DriverPageProc;
  v12 = DSTypePageProc;
  v15 = g_hResDLL;
  v10[1] = g_hResDLL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v21 = g_hResDLL;
  v26 = g_hResDLL;
  v23 = SaveFDSNPageProc;
  v14 = 104;
  v16 = 1536;
  v17 = 0;
  v19 = a2;
  v10[0] = 104;
  v13 = a2;
  v20 = 104;
  v22 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = a2;
  v25 = 104;
  v27 = 1632;
  v28 = 0;
  v29 = FinishedPageProc;
  v30 = a2;
  v9.dwSize = 96;
  v9.dwFlags = 168;
  DesktopWindow = GetDesktopWindow();
  v9.nPages = 4;
  if ( a1 == DesktopWindow )
    a1 = 0;
  v9.hInstance = g_hResDLL;
  v6 = *a2;
  v9.hwndParent = a1;
  v7 = *(_DWORD *)(v6 + 20) == 4;
  v9.ppsp = (LPCPROPSHEETPAGEW)v10;
  v9.pszCaption = &SubKey;
  v9.nStartPage = v7;
  if ( PropertySheetW(&v9) == -1 )
  {
    PostInstError(11);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800033bc  push    rbp
0x1800033be  push    rbx
0x1800033bf  push    rsi
0x1800033c0  push    rdi
0x1800033c1  lea     rbp, [rsp-138h]
0x1800033c9  sub     rsp, 238h
0x1800033d0  mov     rax, cs:__security_cookie
0x1800033d7  xor     rax, rsp
0x1800033da  mov     [rbp+150h+var_30], rax
0x1800033e1  mov     rdi, rdx
0x1800033e4  mov     rbx, rcx
0x1800033e7  xor     edx, edx; Val
0x1800033e9  lea     rcx, [rbp+150h+var_1D0]; void *
0x1800033ed  mov     r8d, 1A0h; Size
0x1800033f3  mov     esi, 1
0x1800033f8  call    memset_0
0x1800033fd  xor     edx, edx; Val
0x1800033ff  lea     r8d, [rsi+57h]; Size
0x180003403  lea     rcx, [rsp+250h+var_230.hwndParent]; void *
0x180003408  call    memset_0
0x18000340d  mov     rax, cs:g_hResDLL
0x180003414  lea     rcx, DriverPageProc
0x18000341b  movdqa  xmm0, cs:__xmm@00000000000000000000000000000620
0x180003423  mov     [rbp+150h+var_140], rcx
0x180003427  lea     rcx, DSTypePageProc
0x18000342e  mov     [rbp+150h+var_1A8], rcx
0x180003432  lea     rcx, SaveFDSNPageProc
0x180003439  mov     [rbp+150h+var_160], rax
0x18000343d  mov     [rbp+150h+var_1C8], rax
0x180003441  movdqa  [rbp+150h+var_1C0], xmm0
0x180003446  movdqa  xmm0, cs:__xmm@00000000000000000000000000000640
0x18000344e  mov     [rbp+150h+var_F8], rax
0x180003452  mov     [rbp+150h+var_90], rax
0x180003459  lea     rax, FinishedPageProc
0x180003460  mov     [rbp+150h+var_D8], rcx
0x180003464  mov     [rbp+150h+var_168], 68h ; 'h'
0x18000346c  mov     [rbp+150h+var_158], 600h
0x180003474  mov     [rbp+150h+var_150], 0
0x18000347c  mov     [rbp+150h+var_138], rdi
0x180003480  mov     [rbp+150h+var_1D0], 68h ; 'h'
0x180003488  mov     [rbp+150h+var_1A0], rdi
0x18000348c  mov     [rbp+150h+var_100], 68h ; 'h'
0x180003494  movdqa  [rbp+150h+var_F0], xmm0
0x180003499  mov     [rbp+150h+var_D0], rdi
0x1800034a0  mov     [rbp+150h+var_98], 68h ; 'h'
0x1800034ab  mov     [rbp+150h+var_88], 660h
0x1800034b6  mov     [rbp+150h+var_80], 0
0x1800034c1  mov     [rbp+150h+var_70], rax
0x1800034c8  mov     [rbp+150h+var_68], rdi
0x1800034cf  mov     [rsp+250h+var_230.dwSize], 60h ; '`'
0x1800034d7  mov     [rsp+250h+var_230.dwFlags], 0A8h
0x1800034df  call    cs:__imp_GetDesktopWindow
0x1800034e5  mov     rcx, rax
0x1800034e8  mov     [rsp+250h+var_230.nPages], 4
0x1800034f0  xor     eax, eax
0x1800034f2  cmp     rbx, rcx
0x1800034f5  cmovz   rbx, rax
0x1800034f9  mov     rax, cs:g_hResDLL
0x180003500  mov     [rsp+250h+var_230.hInstance], rax
0x180003505  xor     ecx, ecx
0x180003507  mov     rax, [rdi]
0x18000350a  mov     [rsp+250h+var_230.hwndParent], rbx
0x18000350f  cmp     dword ptr [rax+14h], 4
0x180003513  lea     rax, [rbp+150h+var_1D0]
0x180003517  mov     qword ptr [rsp+250h+var_230.38h], rax
0x18000351c  lea     rax, SubKey
0x180003523  setz    cl
0x180003526  mov     [rsp+250h+var_230.pszCaption], rax
0x18000352b  mov     dword ptr [rsp+250h+var_230.30h], ecx
0x18000352f  lea     rcx, [rsp+250h+var_230]; LPCPROPSHEETHEADERW
0x180003534  call    cs:__imp_PropertySheetW
0x18000353a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000353e  jnz     short loc_18000354A
0x180003540  lea     ecx, [rsi+0Ah]
0x180003543  call    PostInstError
0x180003548  xor     esi, esi
0x18000354a  mov     eax, esi
0x18000354c  mov     rcx, [rbp+150h+var_30]
0x180003553  xor     rcx, rsp; StackCookie
0x180003556  call    __security_check_cookie
0x18000355b  add     rsp, 238h
0x180003562  pop     rdi
0x180003563  pop     rsi
0x180003564  pop     rbx
0x180003565  pop     rbp
0x180003566  retn
```
