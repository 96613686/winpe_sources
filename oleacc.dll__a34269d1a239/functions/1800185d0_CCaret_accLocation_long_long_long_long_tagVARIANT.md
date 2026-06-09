# CCaret::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x1800185d0`
- end: `0x1800188c9`
- name: `?accLocation@CCaret@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `761`
- prototype: `__int64 __fastcall(CCaret *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800185d0`
- `0x18001d0c4`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180027e2c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018732`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018760`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001878e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800187b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018732`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018760`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001878e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800187b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800186b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800186b2`
- `USER32!GetWindowThreadProcessId` at `0x1800186ac`
- `USER32!GetWindowThreadProcessId` at `0x1800186ac`
- `USER32!GetDC` at `0x18001884c`
- `USER32!GetDC` at `0x18001884c`
- `USER32!ReleaseDC` at `0x180018883`
- `USER32!ReleaseDC` at `0x180018883`
- `USER32!MapWindowPoints` at `0x1800186db`
- `USER32!MapWindowPoints` at `0x1800186db`
- `USER32!GetWindowRect` at `0x1800187d2`
- `USER32!GetWindowRect` at `0x1800187d2`
- `USER32!GetClassNameW` at `0x18001888e`
- `USER32!GetClassNameW` at `0x18001888e`

## pseudocode

```c
__int64 __fastcall CCaret::accLocation(CCaret *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  __int64 v10; // rax
  HWND v11; // rcx
  DWORD CurrentProcessId; // eax
  HWND v13; // rcx
  struct HWND__ *v14; // rcx
  HWND v15; // rcx
  LONG x; // ecx
  LONG y; // eax
  LONG v19; // edx
  LONG v20; // r8d
  HDC DC; // rax
  HDC v22; // rbx
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  int v24[3]; // [rsp+34h] [rbp-CCh] BYREF
  struct tagRECT rcCaret; // [rsp+40h] [rbp-C0h] BYREF
  struct tagGUITHREADINFO v26; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPOINT Points[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR String1[128]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&v26, 0, sizeof(v26));
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v10 = *(_QWORD *)this;
  *(_OWORD *)&Points[0].x = 0;
  if ( !(*(unsigned int (__fastcall **)(CCaret *, struct tagVARIANT *))(v10 + 240))(this, a6) )
    return 2147942487LL;
  if ( !lpfnGuiThreadInfo )
    return 1;
  v26.cbSize = 72;
  if ( !lpfnGuiThreadInfo(0, &v26) )
    return 1;
  v11 = (HWND)*((_QWORD *)this + 10);
  if ( v26.hwndCaret != v11 )
    return 1;
  dwProcessId = 0;
  GetWindowThreadProcessId(v11, &dwProcessId);
  CurrentProcessId = GetCurrentProcessId();
  v13 = (HWND)*((_QWORD *)this + 10);
  if ( dwProcessId != CurrentProcessId )
  {
    *(RECT *)&Points[0].x = v26.rcCaret;
    MapWindowPoints(v13, 0, Points, 2u);
    goto LABEL_7;
  }
  DC = GetDC(v13);
  v22 = DC;
  if ( DC )
  {
    rcCaret = v26.rcCaret;
    GetDeviceRect(DC, &rcCaret, (struct tagRECT *)Points);
    ReleaseDC(*((HWND *)this + 10), v22);
LABEL_7:
    v14 = (struct HWND__ *)*((_QWORD *)this + 10);
    v24[0] = 0;
    String1[0] = 0;
    if ( lpfnRealGetWindowClass )
      lpfnRealGetWindowClass(v14, String1, 0x80u);
    else
      GetClassNameW(v14, String1, 128);
    if ( CompareStringW(0x7Fu, 1u, String1, -1, L"EDIT", -1) == 2
      && (unsigned int)GetEditCaretOffset(*((HWND *)this + 10), Points[1].y - Points[0].y, v24) )
    {
      Points[0].x -= v24[0];
      Points[1].x = Points[0].x + 1;
    }
    if ( CompareStringW(0x7Fu, 1u, String1, -1, L"RICHEDIT20A", -1) == 2
      || CompareStringW(0x7Fu, 1u, String1, -1, L"RICHEDIT20W", -1) == 2
      || CompareStringW(0x7Fu, 1u, String1, -1, L"RICHEDIT", -1) == 2 )
    {
      Points[0].x += 3;
      Points[1].x = Points[0].x + 1;
    }
    v15 = (HWND)*((_QWORD *)this + 10);
    Rect = 0;
    GetWindowRect(v15, &Rect);
    x = Points[1].x;
    if ( Points[1].x > Rect.left )
    {
      y = Points[1].y;
      if ( Points[1].y > Rect.top )
      {
        v19 = Points[0].x;
        if ( Points[0].x < Rect.right )
        {
          v20 = Points[0].y;
          if ( Points[0].y < Rect.bottom )
          {
            *a2 = Points[0].x;
            *a3 = v20;
            *a4 = x - v19;
            *a5 = y - v20;
            return 0;
          }
        }
      }
    }
    return 1;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800185d0  push    rbp
0x1800185d2  push    rbx
0x1800185d3  push    rsi
0x1800185d4  push    rdi
0x1800185d5  push    r12
0x1800185d7  push    r14
0x1800185d9  push    r15
0x1800185db  lea     rbp, [rsp-0D0h]
0x1800185e3  sub     rsp, 1D0h
0x1800185ea  mov     rax, cs:__security_cookie
0x1800185f1  xor     rax, rsp
0x1800185f4  mov     [rbp+100h+var_40], rax
0x1800185fb  mov     r12, [rbp+100h+arg_20]
0x180018602  mov     rsi, rdx
0x180018605  mov     rbx, [rbp+100h+arg_28]
0x18001860c  xor     edx, edx; Val
0x18001860e  mov     r14, r8
0x180018611  mov     rdi, rcx
0x180018614  lea     rcx, [rsp+200h+var_1B0]; void *
0x180018619  mov     r15, r9
0x18001861c  lea     r8d, [rdx+48h]; Size
0x180018620  call    memset_0
0x180018625  mov     dword ptr [rsi], 0
0x18001862b  xorps   xmm0, xmm0
0x18001862e  mov     dword ptr [r14], 0
0x180018635  mov     rdx, rbx
0x180018638  mov     dword ptr [r15], 0
0x18001863f  mov     rcx, rdi
0x180018642  mov     dword ptr [r12], 0
0x18001864a  mov     rax, [rdi]
0x18001864d  movups  xmmword ptr [rbp+100h+Points.x], xmm0
0x180018651  mov     rax, [rax+0F0h]
0x180018658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001865d  test    eax, eax
0x18001865f  jz      loc_180018845
0x180018665  mov     rax, cs:?lpfnGuiThreadInfo@@3P6AHKPEAUtagGUITHREADINFO@@@ZEA; int (*lpfnGuiThreadInfo)(ulong,tagGUITHREADINFO *)
0x18001866c  test    rax, rax
0x18001866f  jz      loc_1800187E0
0x180018675  lea     rdx, [rsp+200h+var_1B0]
0x18001867a  mov     [rsp+200h+var_1B0], 48h ; 'H'
0x180018682  xor     ecx, ecx
0x180018684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018689  test    eax, eax
0x18001868b  jz      loc_1800187E0
0x180018691  mov     rcx, [rdi+50h]; hWnd
0x180018695  cmp     [rbp+100h+var_180], rcx
0x180018699  jnz     loc_1800187E0
0x18001869f  lea     rdx, [rsp+200h+dwProcessId]; lpdwProcessId
0x1800186a4  mov     [rsp+200h+dwProcessId], 0
0x1800186ac  call    cs:__imp_GetWindowThreadProcessId
0x1800186b2  call    cs:__imp_GetCurrentProcessId
0x1800186b8  mov     rcx, [rdi+50h]; hWnd
0x1800186bc  cmp     [rsp+200h+dwProcessId], eax
0x1800186c0  jz      loc_18001884C
0x1800186c6  movups  xmm0, [rbp+100h+var_178]
0x1800186ca  mov     r9d, 2; cPoints
0x1800186d0  lea     r8, [rbp+100h+Points]; lpPoints
0x1800186d4  xor     edx, edx; hWndTo
0x1800186d6  movdqu  xmmword ptr [rbp+100h+Points.x], xmm0
0x1800186db  call    cs:__imp_MapWindowPoints
0x1800186e1  mov     rcx, [rdi+50h]; hWnd
0x1800186e5  lea     rdx, [rbp+100h+String1]; lpClassName
0x1800186e9  xor     eax, eax
0x1800186eb  mov     [rsp+200h+var_1CC], 0
0x1800186f3  mov     [rbp+100h+String1], ax
0x1800186f7  mov     r8d, 80h; nMaxCount
0x1800186fd  mov     rax, cs:?lpfnRealGetWindowClass@@3P6AIPEAUHWND__@@PEAGI@ZEA; uint (*lpfnRealGetWindowClass)(HWND__ *,ushort *,uint)
0x180018704  test    rax, rax
0x180018707  jz      loc_18001888E
0x18001870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018712  or      ebx, 0FFFFFFFFh
0x180018715  lea     rax, szClass; "EDIT"
0x18001871c  mov     [rsp+200h+cchCount2], ebx; cchCount2
0x180018720  lea     r8, [rbp+100h+String1]; lpString1
0x180018724  mov     r9d, ebx; cchCount1
0x180018727  mov     [rsp+200h+lpString2], rax; lpString2
0x18001872c  lea     edx, [rbx+2]; dwCmpFlags
0x18001872f  lea     ecx, [rdx+7Eh]; Locale
0x180018732  call    cs:__imp_CompareStringW
0x180018738  cmp     eax, 2
0x18001873b  jz      loc_180018899
0x180018741  mov     edx, 1; dwCmpFlags
0x180018746  mov     [rsp+200h+cchCount2], ebx; cchCount2
0x18001874a  lea     rax, aRichedit20a; "RICHEDIT20A"
0x180018751  mov     r9d, ebx; cchCount1
0x180018754  lea     r8, [rbp+100h+String1]; lpString1
0x180018758  mov     [rsp+200h+lpString2], rax; lpString2
0x18001875d  lea     ecx, [rdx+7Eh]; Locale
0x180018760  call    cs:__imp_CompareStringW
0x180018766  cmp     eax, 2
0x180018769  jz      loc_180018806
0x18001876f  mov     edx, 1; dwCmpFlags
0x180018774  mov     [rsp+200h+cchCount2], ebx; cchCount2
0x180018778  lea     rax, aRichedit20w_0; "RICHEDIT20W"
0x18001877f  mov     r9d, ebx; cchCount1
0x180018782  lea     r8, [rbp+100h+String1]; lpString1
0x180018786  mov     [rsp+200h+lpString2], rax; lpString2
0x18001878b  lea     ecx, [rdx+7Eh]; Locale
0x18001878e  call    cs:__imp_CompareStringW
0x180018794  cmp     eax, 2
0x180018797  jz      short loc_180018806
0x180018799  mov     edx, 1; dwCmpFlags
0x18001879e  mov     [rsp+200h+cchCount2], ebx; cchCount2
0x1800187a2  lea     rax, aRichedit_0; "RICHEDIT"
0x1800187a9  mov     r9d, ebx; cchCount1
0x1800187ac  lea     r8, [rbp+100h+String1]; lpString1
0x1800187b0  mov     [rsp+200h+lpString2], rax; lpString2
0x1800187b5  lea     ecx, [rdx+7Eh]; Locale
0x1800187b8  call    cs:__imp_CompareStringW
0x1800187be  cmp     eax, 2
0x1800187c1  jz      short loc_180018806
0x1800187c3  mov     rcx, [rdi+50h]; hWnd
0x1800187c7  lea     rdx, [rbp+100h+Rect]; lpRect
0x1800187cb  xorps   xmm0, xmm0
0x1800187ce  movups  xmmword ptr [rbp+100h+Rect.left], xmm0
0x1800187d2  call    cs:__imp_GetWindowRect
0x1800187d8  mov     ecx, [rbp+100h+Points.x+8]
0x1800187db  cmp     ecx, [rbp+100h+Rect.left]
0x1800187de  jg      short loc_180018816
0x1800187e0  mov     eax, 1
0x1800187e5  mov     rcx, [rbp+100h+var_40]
0x1800187ec  xor     rcx, rsp; StackCookie
0x1800187ef  call    __security_check_cookie
0x1800187f4  add     rsp, 1D0h
0x1800187fb  pop     r15
0x1800187fd  pop     r14
0x1800187ff  pop     r12
0x180018801  pop     rdi
0x180018802  pop     rsi
0x180018803  pop     rbx
0x180018804  pop     rbp
0x180018805  retn
0x180018806  mov     eax, [rbp+100h+Points.x]
0x180018809  add     eax, 3
0x18001880c  mov     [rbp+100h+Points.x], eax
0x18001880f  inc     eax
0x180018811  mov     [rbp+100h+Points.x+8], eax
0x180018814  jmp     short loc_1800187C3
0x180018816  mov     eax, [rbp+100h+Points.y+8]
0x180018819  cmp     eax, [rbp+100h+Rect.top]
0x18001881c  jle     short loc_1800187E0
0x18001881e  mov     edx, [rbp+100h+Points.x]
0x180018821  cmp     edx, [rbp+100h+Rect.right]
0x180018824  jge     short loc_1800187E0
0x180018826  mov     r8d, [rbp+100h+Points.y]
0x18001882a  cmp     r8d, [rbp+100h+Rect.bottom]
0x18001882e  jge     short loc_1800187E0
0x180018830  mov     [rsi], edx
0x180018832  sub     ecx, edx
0x180018834  mov     [r14], r8d
0x180018837  sub     eax, r8d
0x18001883a  mov     [r15], ecx
0x18001883d  mov     [r12], eax
0x180018841  xor     eax, eax
0x180018843  jmp     short loc_1800187E5
0x180018845  mov     eax, 80070057h
0x18001884a  jmp     short loc_1800187E5
0x18001884c  call    cs:__imp_GetDC
0x180018852  mov     rbx, rax
0x180018855  test    rax, rax
0x180018858  jnz     short loc_180018861
0x18001885a  mov     eax, 8007000Eh
0x18001885f  jmp     short loc_1800187E5
0x180018861  movups  xmm0, [rbp+100h+var_178]
0x180018865  lea     r8, [rbp+100h+Points]; struct tagRECT *
0x180018869  mov     rcx, rbx; hdc
0x18001886c  lea     rdx, [rsp+200h+var_1C0]; struct tagRECT
0x180018871  movdqu  xmmword ptr [rsp+200h+var_1C0.left], xmm0
0x180018877  call    ?GetDeviceRect@@YAHPEAUHDC__@@UtagRECT@@PEAU2@@Z; GetDeviceRect(HDC__ *,tagRECT,tagRECT *)
0x18001887c  mov     rcx, [rdi+50h]; hWnd
0x180018880  mov     rdx, rbx; hDC
0x180018883  call    cs:__imp_ReleaseDC
0x180018889  jmp     loc_1800186E1
0x18001888e  call    cs:__imp_GetClassNameW
0x180018894  jmp     loc_180018712
0x180018899  mov     edx, [rbp+100h+Points.y+8]
0x18001889c  lea     r8, [rsp+200h+var_1CC]; int *
0x1800188a1  sub     edx, [rbp+100h+Points.y]; int
0x1800188a4  mov     rcx, [rdi+50h]; hWnd
0x1800188a8  call    ?GetEditCaretOffset@@YAHPEAUHWND__@@HPEAH@Z; GetEditCaretOffset(HWND__ *,int,int *)
0x1800188ad  test    eax, eax
0x1800188af  jz      loc_180018741
0x1800188b5  mov     eax, [rbp+100h+Points.x]
0x1800188b8  sub     eax, [rsp+200h+var_1CC]
0x1800188bc  mov     [rbp+100h+Points.x], eax
0x1800188bf  inc     eax
0x1800188c1  mov     [rbp+100h+Points.x+8], eax
0x1800188c4  jmp     loc_180018741
```
