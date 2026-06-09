# CDXGIFactory::CheckOcclusion(HWND__ *,HWND__ *,bool *,bool *)

- ea: `0x1800965b0`
- end: `0x1800969be`
- name: `?CheckOcclusion@CDXGIFactory@@SAJPEAUHWND__@@0PEA_N1@Z`
- size: `1038`
- prototype: `__int64 __fastcall(HWND, HWND, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180008d40`

## callees

- `0x180006ee4`
- `0x18004c420`
- `0x18004c504`
- `0x18004f870`
- `0x180075fa0`
- `0x1800965b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096941`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096941`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18009688c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800968a5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800968be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18009688c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800968a5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800968be`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18009684e`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18009684e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoA` at `0x180096694`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoA` at `0x180096694`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800965fc`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800965fc`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x1800966e9`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x1800967b2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x1800966e9`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x1800967b2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x180096752`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x180096752`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18009693b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18009693b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x1800967fd`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x1800967fd`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x1800967c3`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x1800967c3`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongA` at `0x18009677b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongA` at `0x18009677b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassNameA` at `0x18009686f`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassNameA` at `0x18009686f`

## pseudocode

```c
__int64 __fastcall CDXGIFactory::CheckOcclusion(HWND a1, HWND a2, bool *a3, bool *a4)
{
  HWND hwnd; // [rsp+30h] [rbp-2B8h]
  int v6; // [rsp+38h] [rbp-2B0h]
  DWORD dwProcessId; // [rsp+3Ch] [rbp-2ACh] BYREF
  int pvParam; // [rsp+40h] [rbp-2A8h] BYREF
  int v9; // [rsp+44h] [rbp-2A4h]
  DWORD CurrentProcessId; // [rsp+48h] [rbp-2A0h]
  unsigned int v11; // [rsp+4Ch] [rbp-29Ch]
  LONG WindowLongA; // [rsp+54h] [rbp-294h]
  int v14; // [rsp+58h] [rbp-290h]
  struct tagRECT Rect; // [rsp+60h] [rbp-288h] BYREF
  RECT rcSrc2; // [rsp+70h] [rbp-278h] BYREF
  struct tagRECT rcDst; // [rsp+80h] [rbp-268h] BYREF
  struct tagWINDOWINFO pwi; // [rsp+90h] [rbp-258h] BYREF
  CHAR ClassName[256]; // [rsp+D0h] [rbp-218h] BYREF
  char v20[256]; // [rsp+1D0h] [rbp-118h] BYREF

  memset(&Rect, 0, sizeof(Rect));
  if ( GetClientRect(a2, &Rect) && (Rect.left >= Rect.right || Rect.top >= Rect.bottom) )
    return 142213121;
  if ( a1 == a2 )
    return 0;
  if ( (unsigned int)IsWindowCloaked(a1) || (unsigned int)IsWindowCloaked(a2) )
  {
    RecordJournal(0x87A0001u, "App window cloaked", 0);
    return 142213121;
  }
  else
  {
    pvParam = 0;
    if ( SystemParametersInfoA(0xAAu, 0, &pvParam, 0) && pvParam )
    {
      RecordJournal(0x87A0001u, "Lock screen active", 0);
      return 142213121;
    }
    else
    {
      v11 = 0;
      memset(&rcSrc2, 0, sizeof(rcSrc2));
      GetWindowRect(a1, &rcSrc2);
      hwnd = a1;
      v14 = 200;
      v6 = 200;
      *a3 = 0;
      v9 = 0;
      while ( hwnd )
      {
        if ( !v6-- )
          break;
        hwnd = GetWindow(hwnd, 3u);
        if ( !hwnd )
          break;
        if ( v9 || (WindowLongA = GetWindowLongA(hwnd, -20), (WindowLongA & 8) == 0) )
        {
          if ( IsWindowVisible(hwnd) )
          {
            memset(&pwi, 0, sizeof(pwi));
            pwi.cbSize = 60;
            if ( GetWindowInfo(hwnd, &pwi) )
            {
              if ( !(unsigned int)IsWindowTransparent(hwnd, &pwi) )
              {
                memset(&rcDst, 0, sizeof(rcDst));
                if ( IntersectRect(&rcDst, &pwi.rcClient, &rcSrc2) )
                {
                  if ( GetClassNameA(hwnd, ClassName, 256) )
                  {
                    if ( lstrcmpA(ClassName, "Shell_TrayWnd")
                      && lstrcmpA(ClassName, "Shell_SecondaryTrayWnd")
                      && lstrcmpA(ClassName, "Snapped Desktop") )
                    {
                      v11 = 142213121;
                      memset(v20, 0, sizeof(v20));
                      StringCchPrintfA(v20, 0x100u, "Occluder wnd ('Code' is HWND):%s", ClassName);
                      RecordJournal((unsigned int)hwnd, v20, 0);
                      dwProcessId = 0;
                      GetWindowThreadProcessId(hwnd, &dwProcessId);
                      CurrentProcessId = GetCurrentProcessId();
                      if ( dwProcessId != CurrentProcessId )
                      {
                        StringCchPrintfA(
                          v20,
                          0x100u,
                          "(cont.) Occluder PID: %d, currPID: %d",
                          dwProcessId,
                          CurrentProcessId);
                        RecordJournal((unsigned int)hwnd, v20, 0);
                        *a4 = 1;
                      }
                      return v11;
                    }
                    *a3 = 1;
                  }
                }
              }
            }
          }
        }
        else
        {
          v9 = 1;
          hwnd = a2;
          GetWindowRect(a2, &rcSrc2);
        }
      }
      return v11;
    }
  }
}

```

## disassembly

```asm
0x1800965b0  mov     [rsp+arg_18], r9
0x1800965b5  mov     [rsp+arg_10], r8
0x1800965ba  mov     [rsp+hWnd], rdx
0x1800965bf  mov     [rsp+arg_0], rcx
0x1800965c4  push    rdi
0x1800965c5  sub     rsp, 2E0h
0x1800965cc  mov     rax, cs:__security_cookie
0x1800965d3  xor     rax, rsp
0x1800965d6  mov     [rsp+2E8h+var_18], rax
0x1800965de  lea     rax, [rsp+2E8h+Rect]
0x1800965e3  mov     rdi, rax
0x1800965e6  xor     eax, eax
0x1800965e8  mov     ecx, 10h
0x1800965ed  rep stosb
0x1800965ef  lea     rdx, [rsp+2E8h+Rect]; lpRect
0x1800965f4  mov     rcx, [rsp+2E8h+hWnd]; hWnd
0x1800965fc  call    cs:__imp_GetClientRect
0x180096602  test    eax, eax
0x180096604  jz      short loc_180096624
0x180096606  mov     eax, [rsp+2E8h+Rect.right]
0x18009660a  cmp     [rsp+2E8h+Rect.left], eax
0x18009660e  jge     short loc_18009661A
0x180096610  mov     eax, [rsp+2E8h+Rect.bottom]
0x180096614  cmp     [rsp+2E8h+Rect.top], eax
0x180096618  jl      short loc_180096624
0x18009661a  mov     eax, 87A0001h
0x18009661f  jmp     loc_1800969A5
0x180096624  mov     rax, [rsp+2E8h+hWnd]
0x18009662c  cmp     [rsp+2E8h+arg_0], rax
0x180096634  jnz     short loc_18009663D
0x180096636  xor     eax, eax
0x180096638  jmp     loc_1800969A5
0x18009663d  mov     rcx, [rsp+2E8h+arg_0]; HWND
0x180096645  call    ?IsWindowCloaked@@YAHPEAUHWND__@@@Z; IsWindowCloaked(HWND__ *)
0x18009664a  test    eax, eax
0x18009664c  jnz     short loc_18009665F
0x18009664e  mov     rcx, [rsp+2E8h+hWnd]; HWND
0x180096656  call    ?IsWindowCloaked@@YAHPEAUHWND__@@@Z; IsWindowCloaked(HWND__ *)
0x18009665b  test    eax, eax
0x18009665d  jz      short loc_18009667D
0x18009665f  xor     r8d, r8d; bool
0x180096662  lea     rdx, aAppWindowCloak; "App window cloaked"
0x180096669  mov     ecx, 87A0001h; unsigned int
0x18009666e  call    ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x180096673  mov     eax, 87A0001h
0x180096678  jmp     loc_1800969A5
0x18009667d  mov     [rsp+2E8h+pvParam], 0
0x180096685  xor     r9d, r9d; fWinIni
0x180096688  lea     r8, [rsp+2E8h+pvParam]; pvParam
0x18009668d  xor     edx, edx; uiParam
0x18009668f  mov     ecx, 0AAh; uiAction
0x180096694  call    cs:__imp_SystemParametersInfoA
0x18009669a  test    eax, eax
0x18009669c  jz      short loc_1800966C3
0x18009669e  cmp     [rsp+2E8h+pvParam], 0
0x1800966a3  jz      short loc_1800966C3
0x1800966a5  xor     r8d, r8d; bool
0x1800966a8  lea     rdx, aLockScreenActi; "Lock screen active"
0x1800966af  mov     ecx, 87A0001h; unsigned int
0x1800966b4  call    ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x1800966b9  mov     eax, 87A0001h
0x1800966be  jmp     loc_1800969A5
0x1800966c3  mov     [rsp+2E8h+var_29C], 0
0x1800966cb  lea     rax, [rsp+2E8h+rcSrc2]
0x1800966d0  mov     rdi, rax
0x1800966d3  xor     eax, eax
0x1800966d5  mov     ecx, 10h
0x1800966da  rep stosb
0x1800966dc  lea     rdx, [rsp+2E8h+rcSrc2]; lpRect
0x1800966e1  mov     rcx, [rsp+2E8h+arg_0]; hWnd
0x1800966e9  call    cs:__imp_GetWindowRect
0x1800966ef  mov     rax, [rsp+2E8h+arg_0]
0x1800966f7  mov     [rsp+2E8h+hwnd], rax
0x1800966fc  mov     [rsp+2E8h+var_290], 0C8h
0x180096704  mov     [rsp+2E8h+var_2B0], 0C8h
0x18009670c  mov     rax, [rsp+2E8h+arg_10]
0x180096714  mov     byte ptr [rax], 0
0x180096717  mov     [rsp+2E8h+var_2A4], 0
0x18009671f  cmp     [rsp+2E8h+hwnd], 0
0x180096725  jz      loc_1800969A1
0x18009672b  mov     eax, [rsp+2E8h+var_2B0]
0x18009672f  mov     [rsp+2E8h+var_298], eax
0x180096733  mov     eax, [rsp+2E8h+var_2B0]
0x180096737  dec     eax
0x180096739  mov     [rsp+2E8h+var_2B0], eax
0x18009673d  cmp     [rsp+2E8h+var_298], 0
0x180096742  jz      loc_1800969A1
0x180096748  mov     edx, 3; uCmd
0x18009674d  mov     rcx, [rsp+2E8h+hwnd]; hWnd
0x180096752  call    cs:__imp_GetWindow
0x180096758  mov     [rsp+2E8h+hwnd], rax
0x18009675d  cmp     [rsp+2E8h+hwnd], 0
0x180096763  jnz     short loc_18009676A
0x180096765  jmp     loc_1800969A1
0x18009676a  cmp     [rsp+2E8h+var_2A4], 0
0x18009676f  jnz     short loc_1800967BE
0x180096771  mov     edx, 0FFFFFFECh; nIndex
0x180096776  mov     rcx, [rsp+2E8h+hwnd]; hWnd
0x18009677b  call    cs:__imp_GetWindowLongA
0x180096781  mov     [rsp+2E8h+var_294], eax
0x180096785  mov     eax, [rsp+2E8h+var_294]
0x180096789  and     eax, 8
0x18009678c  test    eax, eax
0x18009678e  jz      short loc_1800967BE
0x180096790  mov     [rsp+2E8h+var_2A4], 1
0x180096798  mov     rax, [rsp+2E8h+hWnd]
0x1800967a0  mov     [rsp+2E8h+hwnd], rax
0x1800967a5  lea     rdx, [rsp+2E8h+rcSrc2]; lpRect
0x1800967aa  mov     rcx, [rsp+2E8h+hWnd]; hWnd
0x1800967b2  call    cs:__imp_GetWindowRect
0x1800967b8  nop
0x1800967b9  jmp     loc_18009671F
0x1800967be  mov     rcx, [rsp+2E8h+hwnd]; hWnd
0x1800967c3  call    cs:__imp_IsWindowVisible
0x1800967c9  test    eax, eax
0x1800967cb  jz      loc_18009699C
0x1800967d1  lea     rax, [rsp+2E8h+pwi]
0x1800967d9  mov     rdi, rax
0x1800967dc  xor     eax, eax
0x1800967de  mov     ecx, 3Ch ; '<'
0x1800967e3  rep stosb
0x1800967e5  mov     [rsp+2E8h+pwi.cbSize], 3Ch ; '<'
0x1800967f0  lea     rdx, [rsp+2E8h+pwi]; pwi
0x1800967f8  mov     rcx, [rsp+2E8h+hwnd]; hwnd
0x1800967fd  call    cs:__imp_GetWindowInfo
0x180096803  test    eax, eax
0x180096805  jz      loc_18009699C
0x18009680b  lea     rdx, [rsp+2E8h+pwi]; struct tagWINDOWINFO *
0x180096813  mov     rcx, [rsp+2E8h+hwnd]; HWND
0x180096818  call    ?IsWindowTransparent@@YAHPEAUHWND__@@PEAUtagWINDOWINFO@@@Z; IsWindowTransparent(HWND__ *,tagWINDOWINFO *)
0x18009681d  test    eax, eax
0x18009681f  jnz     loc_18009699C
0x180096825  lea     rax, [rsp+2E8h+rcDst]
0x18009682d  mov     rdi, rax
0x180096830  xor     eax, eax
0x180096832  mov     ecx, 10h
0x180096837  rep stosb
0x180096839  lea     r8, [rsp+2E8h+rcSrc2]; lprcSrc2
0x18009683e  lea     rdx, [rsp+2E8h+pwi.rcClient]; lprcSrc1
0x180096846  lea     rcx, [rsp+2E8h+rcDst]; lprcDst
0x18009684e  call    cs:__imp_IntersectRect
0x180096854  test    eax, eax
0x180096856  jz      loc_18009699C
0x18009685c  mov     r8d, 100h; nMaxCount
0x180096862  lea     rdx, [rsp+2E8h+ClassName]; lpClassName
0x18009686a  mov     rcx, [rsp+2E8h+hwnd]; hWnd
0x18009686f  call    cs:__imp_GetClassNameA
0x180096875  test    eax, eax
0x180096877  jz      loc_18009699C
0x18009687d  lea     rdx, aShellTraywnd; "Shell_TrayWnd"
0x180096884  lea     rcx, [rsp+2E8h+ClassName]; lpString1
0x18009688c  call    cs:__imp_lstrcmpA
0x180096892  test    eax, eax
0x180096894  jz      short loc_1800968C8
0x180096896  lea     rdx, aShellSecondary; "Shell_SecondaryTrayWnd"
0x18009689d  lea     rcx, [rsp+2E8h+ClassName]; lpString1
0x1800968a5  call    cs:__imp_lstrcmpA
0x1800968ab  test    eax, eax
0x1800968ad  jz      short loc_1800968C8
0x1800968af  lea     rdx, aSnappedDesktop; "Snapped Desktop"
0x1800968b6  lea     rcx, [rsp+2E8h+ClassName]; lpString1
0x1800968be  call    cs:__imp_lstrcmpA
0x1800968c4  test    eax, eax
0x1800968c6  jnz     short loc_1800968D8
0x1800968c8  mov     rax, [rsp+2E8h+arg_10]
0x1800968d0  mov     byte ptr [rax], 1
0x1800968d3  jmp     loc_18009699C
0x1800968d8  mov     [rsp+2E8h+var_29C], 87A0001h
0x1800968e0  lea     rax, [rsp+2E8h+var_118]
0x1800968e8  mov     rdi, rax
0x1800968eb  xor     eax, eax
0x1800968ed  mov     ecx, 100h
0x1800968f2  rep stosb
0x1800968f4  lea     r9, [rsp+2E8h+ClassName]
0x1800968fc  lea     r8, aOccluderWndCod; "Occluder wnd ('Code' is HWND):%s"
0x180096903  mov     edx, 100h; unsigned __int64
0x180096908  lea     rcx, [rsp+2E8h+var_118]; char *
0x180096910  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180096915  xor     r8d, r8d; bool
0x180096918  lea     rdx, [rsp+2E8h+var_118]; char *
0x180096920  mov     ecx, dword ptr [rsp+2E8h+hwnd]; unsigned int
0x180096924  call    ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x180096929  mov     [rsp+2E8h+dwProcessId], 0
0x180096931  lea     rdx, [rsp+2E8h+dwProcessId]; lpdwProcessId
0x180096936  mov     rcx, [rsp+2E8h+hwnd]; hWnd
0x18009693b  call    cs:__imp_GetWindowThreadProcessId
0x180096941  call    cs:__imp_GetCurrentProcessId
0x180096947  mov     [rsp+2E8h+var_2A0], eax
0x18009694b  mov     eax, [rsp+2E8h+var_2A0]
0x18009694f  cmp     [rsp+2E8h+dwProcessId], eax
0x180096953  jz      short loc_18009699A
0x180096955  mov     eax, [rsp+2E8h+var_2A0]
0x180096959  mov     [rsp+2E8h+var_2C8], eax
0x18009695d  mov     r9d, [rsp+2E8h+dwProcessId]
0x180096962  lea     r8, aContOccluderPi; "(cont.) Occluder PID: %d, currPID: %d"
0x180096969  mov     edx, 100h; unsigned __int64
0x18009696e  lea     rcx, [rsp+2E8h+var_118]; char *
0x180096976  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18009697b  xor     r8d, r8d; bool
0x18009697e  lea     rdx, [rsp+2E8h+var_118]; char *
0x180096986  mov     ecx, dword ptr [rsp+2E8h+hwnd]; unsigned int
0x18009698a  call    ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x18009698f  mov     rax, [rsp+2E8h+arg_18]
0x180096997  mov     byte ptr [rax], 1
0x18009699a  jmp     short loc_1800969A1
0x18009699c  jmp     loc_18009671F
0x1800969a1  mov     eax, [rsp+2E8h+var_29C]
0x1800969a5  mov     rcx, [rsp+2E8h+var_18]
0x1800969ad  xor     rcx, rsp; StackCookie
0x1800969b0  call    __security_check_cookie
0x1800969b5  add     rsp, 2E0h
0x1800969bc  pop     rdi
0x1800969bd  retn
```
