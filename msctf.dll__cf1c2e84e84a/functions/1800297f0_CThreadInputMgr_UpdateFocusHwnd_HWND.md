# CThreadInputMgr::UpdateFocusHwnd(HWND__ *)

- ea: `0x1800297f0`
- end: `0x180029c62`
- name: `?UpdateFocusHwnd@CThreadInputMgr@@QEAAXPEAUHWND__@@@Z`
- size: `1138`
- prototype: `void __fastcall(CThreadInputMgr *__hidden this, HWND hwnd)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180027bc4`
- `0x180029200`

## callees

- `0x180029630`
- `0x1800297f0`
- `0x180055a4c`
- `0x180079a10`
- `0x18009c868`
- `0x18009eaea`
- `0x1800ab354`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800299aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800299e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029a96`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029ad0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029b1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029b54`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029b88`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029bb6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029bea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800299aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800299e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029a96`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029ad0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029b1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029b54`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029b88`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029bb6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029bea`
- `USER32!IsTopLevelWindow` at `0x1800298b7`
- `USER32!IsTopLevelWindow` at `0x1800298b7`
- `USER32!GetParent` at `0x18002988a`
- `USER32!GetParent` at `0x18002988a`
- `USER32!GetWindowThreadProcessId` at `0x1800298a7`
- `USER32!GetWindowThreadProcessId` at `0x1800298a7`
- `USER32!RealGetWindowClassW` at `0x180029956`
- `USER32!RealGetWindowClassW` at `0x180029956`
- `api-ms-win-core-textinput-client-l1-1-0!InputFocusChanged` at `0x180029840`
- `api-ms-win-core-textinput-client-l1-1-0!InputFocusChanged` at `0x180029840`

## pseudocode

```c
void __fastcall CThreadInputMgr::UpdateFocusHwnd(CThreadInputMgr *this, HWND hwnd)
{
  __int64 v3; // rdx
  HWND v5; // r15
  HWND i; // rcx
  HWND Parent; // rax
  HWND v8; // r14
  int v9; // ebx
  int v10; // r10d
  bool IsTSF3IMEActive; // al
  int v12; // r10d
  int v13; // r11d
  UINT WindowClassW; // eax
  unsigned __int64 v15; // rbx
  WCHAR v16[12]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v17[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String2[20]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t lpString2[28]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ptszClassName[264]; // [rsp+C0h] [rbp-40h] BYREF

  *((_QWORD *)this + 372) = hwnd;
  v3 = *((unsigned int *)this + 748);
  *((_QWORD *)this + 373) = 0;
  InputFocusChanged(hwnd, v3);
  *(_DWORD *)((char *)this + 3063) = 0;
  *((_BYTE *)this + 3073) = 0;
  *(_WORD *)((char *)this + 3057) = 0;
  *(_WORD *)((char *)this + 3067) = 0;
  *((_BYTE *)this + 3059) = 0;
  *((_BYTE *)this + 3076) = 0;
  if ( !hwnd )
  {
    *((_DWORD *)this + 778) &= 0x8000u;
    return;
  }
  v5 = hwnd;
  for ( i = hwnd; !(unsigned int)IsTopLevelWindow(i); i = v8 )
  {
    Parent = GetParent(v5);
    v8 = Parent;
    if ( !Parent )
      break;
    v9 = *(_DWORD *)(*((_QWORD *)this + 26) + 104LL);
    if ( v9 != GetWindowThreadProcessId(Parent, 0) )
      break;
    v5 = v8;
  }
  *((_QWORD *)this + 373) = v5;
  *((_BYTE *)this + 3076) = IsAllowingGamepadInvocationCached();
  *((_DWORD *)this + 778) = 0;
  if ( CThreadInputMgr::IsUWPApp(this) )
  {
    *((_BYTE *)this + 3059) = CThreadInputMgr::IsInputServiceEnabledWindow(
                                hwnd,
                                (bool *)this + 3060,
                                (bool *)this + 3073);
    return;
  }
  v10 = *((_DWORD *)this + 917);
  *((_BYTE *)this + 3059) = 1;
  if ( (v10 & 0x200000) == 0 && (g_dwAppCompatibility & 0x20000) != 0 )
  {
    IsTSF3IMEActive = CThreadInputMgr::IsTSF3IMEActive(this);
    *((_DWORD *)this + 917) = v13 | v12;
    if ( IsTSF3IMEActive )
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 11) + 8LL))((char *)this + 88);
  }
  memset_0(ptszClassName, 0, 0x208u);
  WindowClassW = RealGetWindowClassW(hwnd, ptszClassName, 0x103u);
  v15 = WindowClassW;
  if ( WindowClassW && WindowClassW < 0x104 )
  {
    if ( 2 * (unsigned __int64)WindowClassW >= 0x208 )
      _report_rangecheckfailure();
    ptszClassName[WindowClassW] = 0;
    if ( CompareStringW(0x7Fu, 0, ptszClassName, -1, L"EXCEL7", -1) == 2 )
    {
      *((_DWORD *)this + 778) |= 0x8000u;
      *((_BYTE *)this + 3063) = 1;
    }
    if ( CompareStringW(0x7Fu, 0, ptszClassName, -1, L"EXCEL6", -1) == 2 )
      *((_BYTE *)this + 3067) = 1;
    wcscpy(v16, L"RICHEDIT");
    wcscpy(v17, L"HwndWrapper");
    wcscpy(String2, L"Chrome_WidgetWin_");
    wcscpy(lpString2, L"Chrome_RenderWidgetHostHWND");
    if ( CompareStringW(0x7Fu, 0, ptszClassName, -1, L"OneNote::DocumentCanvas", -1) == 2 )
    {
      *((_BYTE *)this + 3063) = 1;
      return;
    }
    if ( (unsigned int)v15 > 0x11 && CompareStringW(0x7Fu, 0, ptszClassName, 17, String2, 17) == 2 )
    {
      *(_WORD *)((char *)this + 3063) = 257;
      *((_BYTE *)this + 3058) = 1;
      *((_BYTE *)this + 3051) = 1;
      return;
    }
    if ( (_DWORD)v15 == 27 )
    {
      if ( CompareStringW(0x7Fu, 0, ptszClassName, 27, lpString2, 27) == 2 )
      {
        *((_BYTE *)this + 3065) = 1;
        return;
      }
    }
    else if ( (unsigned int)v15 <= 0xB )
    {
LABEL_30:
      if ( CompareStringW(0x7Fu, 0, ptszClassName, -1, L"Credential Dialog Xaml Host", -1) == 2
        || (unsigned int)v15 > 8 && CompareStringW(0x7Fu, 0, ptszClassName, 8, v16, 8) == 2 )
      {
        *((_BYTE *)this + 3057) = 1;
      }
      else if ( v15 > 5 && CompareStringW(0x7Fu, 0, ptszClassName, 5, L"EXCEL", 5) == 2 )
      {
        *((_BYTE *)this + 3058) = 1;
        *((_BYTE *)this + 3068) = 1;
      }
      return;
    }
    if ( CompareStringW(0x7Fu, 0, ptszClassName, 11, v17, 11) == 2 )
    {
      *((_BYTE *)this + 3066) = 1;
      return;
    }
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x1800297f0  mov     [rsp-8+arg_10], rbx
0x1800297f5  push    rbp
0x1800297f6  push    rsi
0x1800297f7  push    rdi
0x1800297f8  push    r12
0x1800297fa  push    r13
0x1800297fc  push    r14
0x1800297fe  push    r15
0x180029800  lea     rbp, [rsp-1E0h]
0x180029808  sub     rsp, 2E0h
0x18002980f  mov     rax, cs:__security_cookie
0x180029816  xor     rax, rsp
0x180029819  mov     [rbp+210h+var_40], rax
0x180029820  mov     rsi, rdx
0x180029823  mov     [rcx+0BA0h], rdx
0x18002982a  mov     edx, [rcx+0BB0h]
0x180029830  mov     rdi, rcx
0x180029833  xor     r13d, r13d
0x180029836  mov     [rcx+0BA8h], r13
0x18002983d  mov     rcx, rsi
0x180029840  call    cs:__imp_InputFocusChanged
0x180029846  mov     [rdi+0BF7h], r13d
0x18002984d  lea     r12, [rdi+0C01h]
0x180029854  mov     [r12], r13b
0x180029858  mov     [rdi+0BF1h], r13w
0x180029860  mov     [rdi+0BFBh], r13w
0x180029868  mov     [rdi+0BF3h], r13b
0x18002986f  mov     [rdi+0C04h], r13b
0x180029876  test    rsi, rsi
0x180029879  jz      loc_180029C28
0x18002987f  mov     r15, rsi
0x180029882  mov     rcx, rsi
0x180029885  jmp     short loc_1800298B7
0x180029887  mov     rcx, r15; hWnd
0x18002988a  call    cs:__imp_GetParent
0x180029890  mov     r14, rax
0x180029893  test    rax, rax
0x180029896  jz      short loc_1800298C1
0x180029898  mov     rcx, [rdi+0D0h]
0x18002989f  xor     edx, edx; lpdwProcessId
0x1800298a1  mov     ebx, [rcx+68h]
0x1800298a4  mov     rcx, rax; hWnd
0x1800298a7  call    cs:__imp_GetWindowThreadProcessId
0x1800298ad  cmp     ebx, eax
0x1800298af  jnz     short loc_1800298C1
0x1800298b1  mov     r15, r14
0x1800298b4  mov     rcx, r14
0x1800298b7  call    cs:__imp_IsTopLevelWindow
0x1800298bd  test    eax, eax
0x1800298bf  jz      short loc_180029887
0x1800298c1  mov     [rdi+0BA8h], r15
0x1800298c8  call    ?IsAllowingGamepadInvocationCached@@YA_NXZ; IsAllowingGamepadInvocationCached(void)
0x1800298cd  mov     rcx, rdi; this
0x1800298d0  mov     [rdi+0C04h], al
0x1800298d6  mov     [rdi+0C28h], r13d
0x1800298dd  call    ?IsUWPApp@CThreadInputMgr@@QEBA_NXZ; CThreadInputMgr::IsUWPApp(void)
0x1800298e2  test    al, al
0x1800298e4  jnz     loc_180029C0E
0x1800298ea  mov     r10d, [rdi+0E54h]
0x1800298f1  mov     r11d, 200000h
0x1800298f7  mov     byte ptr [rdi+0BF3h], 1
0x1800298fe  test    r11d, r10d
0x180029901  jnz     short loc_180029935
0x180029903  test    cs:?g_dwAppCompatibility@@3KA, 20000h; ulong g_dwAppCompatibility
0x18002990d  jz      short loc_180029935
0x18002990f  mov     rcx, rdi; this
0x180029912  call    ?IsTSF3IMEActive@CThreadInputMgr@@QEBA_NXZ; CThreadInputMgr::IsTSF3IMEActive(void)
0x180029917  or      r10d, r11d
0x18002991a  mov     [rdi+0E54h], r10d
0x180029921  test    al, al
0x180029923  jz      short loc_180029935
0x180029925  lea     rcx, [rdi+58h]
0x180029929  mov     rax, [rcx]
0x18002992c  mov     rax, [rax+8]
0x180029930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029935  mov     r14d, 208h
0x18002993b  lea     rcx, [rbp+210h+ptszClassName]; void *
0x18002993f  mov     r8d, r14d; Size
0x180029942  xor     edx, edx; Val
0x180029944  call    memset_0
0x180029949  mov     r8d, 103h; cchClassNameMax
0x18002994f  lea     rdx, [rbp+210h+ptszClassName]; ptszClassName
0x180029953  mov     rcx, rsi; hwnd
0x180029956  call    cs:__imp_RealGetWindowClassW
0x18002995c  mov     ebx, eax
0x18002995e  test    eax, eax
0x180029960  jz      loc_180029C32
0x180029966  cmp     ebx, 104h
0x18002996c  jnb     loc_180029C32
0x180029972  lea     rcx, [rbx+rbx]
0x180029976  cmp     rcx, r14
0x180029979  jnb     loc_180029C5C
0x18002997f  xor     edx, edx; dwCmpFlags
0x180029981  mov     [rbp+rcx+210h+ptszClassName], r13w
0x180029987  or      r12d, 0FFFFFFFFh
0x18002998b  lea     rax, aExcel7; "EXCEL7"
0x180029992  mov     [rsp+310h+cchCount2], r12d; cchCount2
0x180029997  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x18002999b  mov     r9d, r12d; cchCount1
0x18002999e  mov     [rsp+310h+lpString2], rax; lpString2
0x1800299a3  lea     r14d, [rdx+7Fh]
0x1800299a7  mov     ecx, r14d; Locale
0x1800299aa  call    cs:__imp_CompareStringW
0x1800299b0  lea     r15d, [r12+3]
0x1800299b5  cmp     eax, r15d
0x1800299b8  jnz     short loc_1800299C9
0x1800299ba  bts     dword ptr [rdi+0C28h], 0Fh
0x1800299c2  mov     byte ptr [rdi+0BF7h], 1
0x1800299c9  lea     rax, aExcel6; "EXCEL6"
0x1800299d0  mov     [rsp+310h+cchCount2], r12d; cchCount2
0x1800299d5  mov     r9d, r12d; cchCount1
0x1800299d8  mov     [rsp+310h+lpString2], rax; lpString2
0x1800299dd  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x1800299e1  xor     edx, edx; dwCmpFlags
0x1800299e3  mov     ecx, r14d; Locale
0x1800299e6  call    cs:__imp_CompareStringW
0x1800299ec  cmp     eax, r15d
0x1800299ef  jnz     short loc_1800299F8
0x1800299f1  mov     byte ptr [rdi+0BFBh], 1
0x1800299f8  movzx   eax, word ptr cs:aRichedit+10h; ""
0x1800299ff  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029a03  movups  xmm0, xmmword ptr cs:aRichedit; "RICHEDIT"
0x180029a0a  mov     r9d, r12d; cchCount1
0x180029a0d  mov     [rsp+310h+var_2D0], ax
0x180029a12  movsd   xmm1, qword ptr cs:aHwndwrapper+10h; "per"
0x180029a1a  xor     edx, edx; dwCmpFlags
0x180029a1c  mov     eax, dword ptr cs:aChromeWidgetwi+20h; "_"
0x180029a22  mov     ecx, r14d; Locale
0x180029a25  movups  xmmword ptr [rsp+310h+var_2E0], xmm0
0x180029a2a  mov     [rbp+210h+var_290], eax
0x180029a2d  lea     rax, aOnenoteDocumen; "OneNote::DocumentCanvas"
0x180029a34  movups  xmm0, xmmword ptr cs:aHwndwrapper; "HwndWrapper"
0x180029a3b  mov     [rsp+310h+cchCount2], r12d; cchCount2
0x180029a40  movsd   [rsp+310h+var_2B8], xmm1
0x180029a46  movups  xmm1, xmmword ptr cs:aChromeWidgetwi+10h; "idgetWin_"
0x180029a4d  mov     [rsp+310h+lpString2], rax; lpString2
0x180029a52  movups  xmmword ptr [rsp+310h+var_2C8], xmm0
0x180029a57  movups  xmm0, xmmword ptr cs:aChromeWidgetwi; "Chrome_WidgetWin_"
0x180029a5e  movups  [rsp+310h+var_2A0], xmm1
0x180029a63  movups  xmm1, xmmword ptr cs:aChromeRenderwi+10h; "enderWidgetHostHWND"
0x180029a6a  movups  xmmword ptr [rsp+310h+String2], xmm0
0x180029a6f  movups  xmm0, xmmword ptr cs:aChromeRenderwi; "Chrome_RenderWidgetHostHWND"
0x180029a76  movups  xmmword ptr [rbp+210h+var_288+10h], xmm1
0x180029a7a  movsd   xmm1, qword ptr cs:aChromeRenderwi+30h; "WND"
0x180029a82  movups  xmmword ptr [rbp+210h+var_288], xmm0
0x180029a86  movups  xmm0, xmmword ptr cs:aChromeRenderwi+20h; "getHostHWND"
0x180029a8d  movsd   [rbp+210h+var_258], xmm1
0x180029a92  movups  [rbp+210h+var_268], xmm0
0x180029a96  call    cs:__imp_CompareStringW
0x180029a9c  cmp     eax, r15d
0x180029a9f  jnz     short loc_180029AAD
0x180029aa1  mov     byte ptr [rdi+0BF7h], 1
0x180029aa8  jmp     loc_180029C32
0x180029aad  mov     r9d, 11h; cchCount1
0x180029ab3  cmp     ebx, r9d
0x180029ab6  jbe     short loc_180029AF7
0x180029ab8  lea     rax, [rsp+310h+String2]
0x180029abd  mov     [rsp+310h+cchCount2], r9d; cchCount2
0x180029ac2  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029ac6  mov     [rsp+310h+lpString2], rax; lpString2
0x180029acb  xor     edx, edx; dwCmpFlags
0x180029acd  mov     ecx, r14d; Locale
0x180029ad0  call    cs:__imp_CompareStringW
0x180029ad6  cmp     eax, r15d
0x180029ad9  jnz     short loc_180029AF7
0x180029adb  mov     word ptr [rdi+0BF7h], 101h
0x180029ae4  mov     byte ptr [rdi+0BF2h], 1
0x180029aeb  mov     byte ptr [rdi+0BEBh], 1
0x180029af2  jmp     loc_180029C32
0x180029af7  mov     r13d, 0Bh
0x180029afd  lea     r9d, [r13+10h]; cchCount1
0x180029b01  cmp     ebx, r9d
0x180029b04  jnz     short loc_180029B34
0x180029b06  lea     rax, [rbp+210h+var_288]
0x180029b0a  mov     [rsp+310h+cchCount2], r9d; cchCount2
0x180029b0f  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029b13  mov     [rsp+310h+lpString2], rax; lpString2
0x180029b18  xor     edx, edx; dwCmpFlags
0x180029b1a  mov     ecx, r14d; Locale
0x180029b1d  call    cs:__imp_CompareStringW
0x180029b23  cmp     eax, r15d
0x180029b26  jnz     short loc_180029B39
0x180029b28  mov     byte ptr [rdi+0BF9h], 1
0x180029b2f  jmp     loc_180029C32
0x180029b34  cmp     ebx, r13d
0x180029b37  jbe     short loc_180029B6B
0x180029b39  lea     rax, [rsp+310h+var_2C8]
0x180029b3e  mov     [rsp+310h+cchCount2], r13d; cchCount2
0x180029b43  mov     r9d, r13d; cchCount1
0x180029b46  mov     [rsp+310h+lpString2], rax; lpString2
0x180029b4b  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029b4f  xor     edx, edx; dwCmpFlags
0x180029b51  mov     ecx, r14d; Locale
0x180029b54  call    cs:__imp_CompareStringW
0x180029b5a  cmp     eax, r15d
0x180029b5d  jnz     short loc_180029B6B
0x180029b5f  mov     byte ptr [rdi+0BFAh], 1
0x180029b66  jmp     loc_180029C32
0x180029b6b  lea     rax, aCredentialDial; "Credential Dialog Xaml Host"
0x180029b72  mov     [rsp+310h+cchCount2], r12d; cchCount2
0x180029b77  mov     r9d, r12d; cchCount1
0x180029b7a  mov     [rsp+310h+lpString2], rax; lpString2
0x180029b7f  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029b83  xor     edx, edx; dwCmpFlags
0x180029b85  mov     ecx, r14d; Locale
0x180029b88  call    cs:__imp_CompareStringW
0x180029b8e  cmp     eax, r15d
0x180029b91  jz      short loc_180029C05
0x180029b93  mov     r9d, 8; cchCount1
0x180029b99  cmp     ebx, r9d
0x180029b9c  jbe     short loc_180029BC1
0x180029b9e  lea     rax, [rsp+310h+var_2E0]
0x180029ba3  mov     [rsp+310h+cchCount2], r9d; cchCount2
0x180029ba8  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029bac  mov     [rsp+310h+lpString2], rax; lpString2
0x180029bb1  xor     edx, edx; dwCmpFlags
0x180029bb3  mov     ecx, r14d; Locale
0x180029bb6  call    cs:__imp_CompareStringW
0x180029bbc  cmp     eax, r15d
0x180029bbf  jz      short loc_180029C05
0x180029bc1  cmp     rbx, 5
0x180029bc5  jbe     short loc_180029C32
0x180029bc7  lea     rax, aExcel; "EXCEL"
0x180029bce  mov     [rsp+310h+cchCount2], 5; cchCount2
0x180029bd6  mov     r9d, 5; cchCount1
0x180029bdc  mov     [rsp+310h+lpString2], rax; lpString2
0x180029be1  lea     r8, [rbp+210h+ptszClassName]; lpString1
0x180029be5  xor     edx, edx; dwCmpFlags
0x180029be7  mov     ecx, r14d; Locale
0x180029bea  call    cs:__imp_CompareStringW
0x180029bf0  cmp     eax, r15d
0x180029bf3  jnz     short loc_180029C32
0x180029bf5  mov     byte ptr [rdi+0BF2h], 1
0x180029bfc  mov     byte ptr [rdi+0BFCh], 1
0x180029c03  jmp     short loc_180029C32
0x180029c05  mov     byte ptr [rdi+0BF1h], 1
0x180029c0c  jmp     short loc_180029C32
0x180029c0e  lea     rdx, [rdi+0BF4h]; bool *
0x180029c15  mov     r8, r12; bool *
0x180029c18  mov     rcx, rsi; hWnd
0x180029c1b  call    ?IsInputServiceEnabledWindow@CThreadInputMgr@@SA_NPEAUHWND__@@PEA_N1@Z; CThreadInputMgr::IsInputServiceEnabledWindow(HWND__ *,bool *,bool *)
0x180029c20  mov     [rdi+0BF3h], al
0x180029c26  jmp     short loc_180029C32
0x180029c28  and     dword ptr [rdi+0C28h], 8000h
0x180029c32  mov     rcx, [rbp+210h+var_40]
0x180029c39  xor     rcx, rsp; StackCookie
0x180029c3c  call    __security_check_cookie
0x180029c41  mov     rbx, [rsp+310h+arg_10]
0x180029c49  add     rsp, 2E0h
0x180029c50  pop     r15
0x180029c52  pop     r14
0x180029c54  pop     r13
0x180029c56  pop     r12
0x180029c58  pop     rdi
0x180029c59  pop     rsi
0x180029c5a  pop     rbp
0x180029c5b  retn
0x180029c5c  call    __report_rangecheckfailure
```
