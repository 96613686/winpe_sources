# CRdpWindowTracker::WorkerThreadProc(void)

- ea: `0x14005fb1c`
- end: `0x14005fe7b`
- name: `?WorkerThreadProc@CRdpWindowTracker@@AEAAKXZ`
- size: `863`
- prototype: `unsigned int __fastcall(CRdpWindowTracker *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14005ef50`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x140011054`
- `0x14005dc40`
- `0x14005f038`
- `0x14005fb1c`
- `0x14006b010`

## import_xrefs

- `USER32!CreateWindowExW` at `0x14005fc39`
- `USER32!CreateWindowExW` at `0x14005fc39`
- `USER32!RegisterClassExW` at `0x14005fbde`
- `USER32!RegisterClassExW` at `0x14005fbde`
- `USER32!GetMessageW` at `0x14005fdcd`
- `USER32!GetMessageW` at `0x14005fdcd`
- `USER32!LoadCursorW` at `0x14005fbbb`
- `USER32!LoadCursorW` at `0x14005fbbb`
- `USER32!TranslateMessage` at `0x14005fdaf`
- `USER32!TranslateMessage` at `0x14005fdaf`
- `USER32!GetClassInfoExW` at `0x14005fb83`
- `USER32!GetClassInfoExW` at `0x14005fb83`
- `USER32!DispatchMessageW` at `0x14005fdb9`
- `USER32!DispatchMessageW` at `0x14005fdb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005fb58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005fb58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fbe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fe10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fbe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fd71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005fe10`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x14005fd12`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x14005fd12`
- `WTSAPI32!WTSUnRegisterSessionNotification` at `0x14005fde8`
- `WTSAPI32!WTSUnRegisterSessionNotification` at `0x14005fde8`

## string_xrefs

- `0x14005fc71`: `"CreateWindow()"`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::WorkerThreadProc(HWND *this)
{
  HMODULE hInstance; // rdi
  HCURSOR CursorW; // rax
  HWND Window; // rax
  unsigned int v5; // eax
  int v6; // edi
  unsigned int v7; // eax
  signed int LastError; // eax
  unsigned int v9; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND v11; // rcx
  HWND v12; // rcx
  BOOL v13; // eax
  signed int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // eax
  HWND v17; // rcx
  __int64 Y; // [rsp+28h] [rbp-91h]
  MSG Msg; // [rsp+60h] [rbp-59h] BYREF
  struct tagWNDCLASSEXW wcx; // [rsp+90h] [rbp-29h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  memset_0(&wcx, 0, sizeof(wcx));
  hInstance = GetModuleHandleW(0);
  memset_0(&wcx, 0, sizeof(wcx));
  wcx.cbSize = 80;
  if ( GetClassInfoExW(hInstance, L"RDP_TrackingWindowClass", &wcx) )
    goto LABEL_4;
  wcx.style = 3;
  wcx.lpfnWndProc = (WNDPROC)CRdpWindowTracker::STATIC_WndProc;
  *(_QWORD *)&wcx.cbClsExtra = 0;
  wcx.hInstance = hInstance;
  wcx.hIcon = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  *(__m128i *)&wcx.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
  wcx.hCursor = CursorW;
  wcx.lpszClassName = L"RDP_TrackingWindowClass";
  wcx.hIconSm = 0;
  if ( RegisterClassExW(&wcx) || GetLastError() == 1410 )
  {
LABEL_4:
    Window = CreateWindowExW(
               0,
               L"RDP_TrackingWindowClass",
               L"RDP_TrackingWindow",
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               HWND_MESSAGE,
               0,
               hInstance,
               this);
    this[12] = Window;
    if ( Window )
    {
      v6 = CRdpWindowTracker::InitializeWinEventHooks((CRdpWindowTracker *)this);
      if ( v6 >= 0 )
      {
        if ( WTSRegisterSessionNotification(this[12], 0) )
        {
          v11 = this[9];
          *((_DWORD *)this + 72) = 1;
          (*(void (__fastcall **)(HWND, _QWORD, __int64))(*(_QWORD *)v11 + 40LL))(
            v11,
            (unsigned __int64)(this + 6) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
            4);
          while ( GetMessageW(&Msg, this[12], 0, 0) >= 0 )
          {
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              89,
              &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
              CurrentThreadActivityIdPrefix,
              v9);
          }
          GetLastError();
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(Y) = v6;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          v7,
          (__int64)"InitializeWinEventHooks() failed",
          Y);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v5,
        (__int64)"\"CreateWindow()\"");
    }
  }
  if ( *((_DWORD *)this + 72) )
  {
    v12 = this[12];
    if ( v12 )
    {
      v13 = WTSUnRegisterSessionNotification(v12);
      *((_DWORD *)this + 72) = 0;
      if ( !v13
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        v15 = v14;
        if ( v14 > 0 )
          v15 = (unsigned __int16)v14 | 0x80070000;
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids, v16, v15);
      }
    }
  }
  CRdpWindowTracker::TerminateWinEventHooks((CRdpWindowTracker *)this);
  v17 = this[4];
  this[12] = 0;
  (*(void (__fastcall **)(HWND))(*(_QWORD *)v17 + 16LL))(v17);
  return 0;
}

```

## disassembly

```asm
0x14005fb1c  push    rbp
0x14005fb1e  push    rbx
0x14005fb1f  push    rsi
0x14005fb20  push    rdi
0x14005fb21  push    r13
0x14005fb23  push    r15
0x14005fb25  lea     rbp, [rsp-2Fh]
0x14005fb2a  sub     rsp, 0E8h
0x14005fb31  xorps   xmm0, xmm0
0x14005fb34  mov     rbx, rcx
0x14005fb37  mov     esi, 50h ; 'P'
0x14005fb3c  lea     rcx, [rbp+57h+wcx]; void *
0x14005fb40  mov     r8d, esi; Size
0x14005fb43  xor     edx, edx; Val
0x14005fb45  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14005fb49  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14005fb4d  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14005fb51  call    memset_0
0x14005fb56  xor     ecx, ecx; lpModuleName
0x14005fb58  call    cs:__imp_GetModuleHandleW
0x14005fb5e  mov     r8d, esi; Size
0x14005fb61  lea     rcx, [rbp+57h+wcx]; void *
0x14005fb65  xor     edx, edx; Val
0x14005fb67  mov     rdi, rax
0x14005fb6a  call    memset_0
0x14005fb6f  lea     r13, szClass; "RDP_TrackingWindowClass"
0x14005fb76  mov     [rbp+57h+wcx.cbSize], esi
0x14005fb79  mov     rdx, r13; lpszClass
0x14005fb7c  lea     r8, [rbp+57h+wcx]; lpwcx
0x14005fb80  mov     rcx, rdi; hInstance
0x14005fb83  call    cs:__imp_GetClassInfoExW
0x14005fb89  xor     esi, esi
0x14005fb8b  lea     r15, WPP_GLOBAL_Control
0x14005fb92  test    eax, eax
0x14005fb94  jnz     short loc_14005FBFA
0x14005fb96  lea     rax, ?STATIC_WndProc@CRdpWindowTracker@@CA_JPEAUHWND__@@I_K_J@Z; CRdpWindowTracker::STATIC_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14005fb9d  mov     [rbp+57h+wcx.style], 3
0x14005fba4  mov     edx, 7F00h; lpCursorName
0x14005fba9  mov     [rbp+57h+wcx.lpfnWndProc], rax
0x14005fbad  xor     ecx, ecx; hInstance
0x14005fbaf  mov     qword ptr [rbp+57h+wcx.cbClsExtra], rsi
0x14005fbb3  mov     [rbp+57h+wcx.hInstance], rdi
0x14005fbb7  mov     [rbp+57h+wcx.hIcon], rsi
0x14005fbbb  call    cs:__imp_LoadCursorW
0x14005fbc1  movdqa  xmm0, cs:__xmm@00000000000000000000000000000006
0x14005fbc9  lea     rcx, [rbp+57h+wcx]; WNDCLASSEXW *
0x14005fbcd  movdqa  xmmword ptr [rbp+57h+wcx.hbrBackground], xmm0
0x14005fbd2  mov     [rbp+57h+wcx.hCursor], rax
0x14005fbd6  mov     [rbp+57h+wcx.lpszClassName], r13
0x14005fbda  mov     [rbp+57h+wcx.hIconSm], rsi
0x14005fbde  call    cs:__imp_RegisterClassExW
0x14005fbe4  test    ax, ax
0x14005fbe7  jnz     short loc_14005FBFA
0x14005fbe9  call    cs:__imp_GetLastError
0x14005fbef  cmp     eax, 582h
0x14005fbf4  jnz     loc_14005FDD7
0x14005fbfa  mov     [rsp+110h+lpParam], rbx; lpParam
0x14005fbff  lea     r8, aRdpTrackingwin_0; "RDP_TrackingWindow"
0x14005fc06  mov     [rsp+110h+hInstance], rdi; hInstance
0x14005fc0b  mov     eax, 80000000h
0x14005fc10  mov     [rsp+110h+hMenu], rsi; hMenu
0x14005fc15  mov     r9d, 80000000h; dwStyle
0x14005fc1b  mov     [rsp+110h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x14005fc24  mov     rdx, r13; lpClassName
0x14005fc27  mov     [rsp+110h+nHeight], eax; nHeight
0x14005fc2b  xor     ecx, ecx; dwExStyle
0x14005fc2d  mov     [rsp+110h+nWidth], eax; nWidth
0x14005fc31  mov     dword ptr [rsp+110h+Y], eax; Y
0x14005fc35  mov     [rsp+110h+X], eax; X
0x14005fc39  call    cs:__imp_CreateWindowExW
0x14005fc3f  mov     [rbx+60h], rax
0x14005fc43  test    rax, rax
0x14005fc46  jnz     short loc_14005FCA1
0x14005fc48  mov     rax, cs:WPP_GLOBAL_Control
0x14005fc4f  cmp     rax, r15
0x14005fc52  jz      loc_14005FDD7
0x14005fc58  test    byte ptr [rax+1Ch], 8
0x14005fc5c  jz      loc_14005FDD7
0x14005fc62  cmp     byte ptr [rax+19h], 2
0x14005fc66  jb      loc_14005FDD7
0x14005fc6c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005fc71  lea     rcx, aCreatewindow; "\"CreateWindow()\""
0x14005fc78  mov     edx, 57h ; 'W'
0x14005fc7d  mov     qword ptr [rsp+110h+X], rcx
0x14005fc82  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005fc89  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fc90  mov     r9d, eax
0x14005fc93  mov     rcx, [rcx+10h]
0x14005fc97  call    WPP_SF_Ds
0x14005fc9c  jmp     loc_14005FDD7
0x14005fca1  mov     rcx, rbx; this
0x14005fca4  call    ?InitializeWinEventHooks@CRdpWindowTracker@@AEAAJXZ; CRdpWindowTracker::InitializeWinEventHooks(void)
0x14005fca9  mov     edi, eax
0x14005fcab  test    eax, eax
0x14005fcad  jns     short loc_14005FD0C
0x14005fcaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fcb6  cmp     rcx, r15
0x14005fcb9  jz      loc_14005FDD7
0x14005fcbf  test    byte ptr [rcx+1Ch], 8
0x14005fcc3  jz      loc_14005FDD7
0x14005fcc9  cmp     byte ptr [rcx+19h], 2
0x14005fccd  jb      loc_14005FDD7
0x14005fcd3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005fcd8  lea     rcx, aInitializewine; "InitializeWinEventHooks() failed"
0x14005fcdf  mov     dword ptr [rsp+110h+Y], edi
0x14005fce3  mov     qword ptr [rsp+110h+X], rcx
0x14005fce8  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005fcef  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fcf6  mov     edx, 58h ; 'X'
0x14005fcfb  mov     r9d, eax
0x14005fcfe  mov     rcx, [rcx+10h]
0x14005fd02  call    WPP_SF_DsD
0x14005fd07  jmp     loc_14005FDD7
0x14005fd0c  mov     rcx, [rbx+60h]; hWnd
0x14005fd10  xor     edx, edx; dwFlags
0x14005fd12  call    cs:__imp_WTSRegisterSessionNotification
0x14005fd18  test    eax, eax
0x14005fd1a  jnz     short loc_14005FD79
0x14005fd1c  mov     rax, cs:WPP_GLOBAL_Control
0x14005fd23  cmp     rax, r15
0x14005fd26  jz      short loc_14005FD71
0x14005fd28  test    byte ptr [rax+1Ch], 8
0x14005fd2c  jz      short loc_14005FD71
0x14005fd2e  cmp     byte ptr [rax+19h], 2
0x14005fd32  jb      short loc_14005FD71
0x14005fd34  call    cs:__imp_GetLastError
0x14005fd3a  mov     edi, eax
0x14005fd3c  test    eax, eax
0x14005fd3e  jle     short loc_14005FD49
0x14005fd40  movzx   edi, ax
0x14005fd43  or      edi, 80070000h
0x14005fd49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005fd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fd55  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005fd5c  mov     edx, 59h ; 'Y'
0x14005fd61  mov     [rsp+110h+X], edi
0x14005fd65  mov     r9d, eax
0x14005fd68  mov     rcx, [rcx+10h]
0x14005fd6c  call    WPP_SF_Dd
0x14005fd71  call    cs:__imp_GetLastError
0x14005fd77  jmp     short loc_14005FDD7
0x14005fd79  mov     rcx, [rbx+48h]
0x14005fd7d  lea     r8, [rbx+30h]
0x14005fd81  mov     dword ptr [rbx+120h], 1
0x14005fd8b  mov     rax, rbx
0x14005fd8e  neg     rax
0x14005fd91  mov     r9, [rcx]
0x14005fd94  sbb     rdx, rdx
0x14005fd97  and     rdx, r8
0x14005fd9a  mov     r8d, 4
0x14005fda0  mov     rax, [r9+28h]
0x14005fda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005fda9  jmp     short loc_14005FDBF
0x14005fdab  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14005fdaf  call    cs:__imp_TranslateMessage
0x14005fdb5  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14005fdb9  call    cs:__imp_DispatchMessageW
0x14005fdbf  mov     rdx, [rbx+60h]; hWnd
0x14005fdc3  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14005fdc7  xor     r9d, r9d; wMsgFilterMax
0x14005fdca  xor     r8d, r8d; wMsgFilterMin
0x14005fdcd  call    cs:__imp_GetMessageW
0x14005fdd3  test    eax, eax
0x14005fdd5  jns     short loc_14005FDAB
0x14005fdd7  cmp     [rbx+120h], esi
0x14005fddd  jz      short loc_14005FE4D
0x14005fddf  mov     rcx, [rbx+60h]; hWnd
0x14005fde3  test    rcx, rcx
0x14005fde6  jz      short loc_14005FE4D
0x14005fde8  call    cs:__imp_WTSUnRegisterSessionNotification
0x14005fdee  mov     [rbx+120h], esi
0x14005fdf4  test    eax, eax
0x14005fdf6  jnz     short loc_14005FE4D
0x14005fdf8  mov     rax, cs:WPP_GLOBAL_Control
0x14005fdff  cmp     rax, r15
0x14005fe02  jz      short loc_14005FE4D
0x14005fe04  test    byte ptr [rax+1Ch], 8
0x14005fe08  jz      short loc_14005FE4D
0x14005fe0a  cmp     byte ptr [rax+19h], 2
0x14005fe0e  jb      short loc_14005FE4D
0x14005fe10  call    cs:__imp_GetLastError
0x14005fe16  mov     edi, eax
0x14005fe18  test    eax, eax
0x14005fe1a  jle     short loc_14005FE25
0x14005fe1c  movzx   edi, ax
0x14005fe1f  or      edi, 80070000h
0x14005fe25  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005fe2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fe31  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005fe38  mov     edx, 5Ah ; 'Z'
0x14005fe3d  mov     [rsp+110h+X], edi
0x14005fe41  mov     r9d, eax
0x14005fe44  mov     rcx, [rcx+10h]
0x14005fe48  call    WPP_SF_Dd
0x14005fe4d  mov     rcx, rbx; this
0x14005fe50  call    ?TerminateWinEventHooks@CRdpWindowTracker@@AEAAJXZ; CRdpWindowTracker::TerminateWinEventHooks(void)
0x14005fe55  mov     rcx, [rbx+20h]
0x14005fe59  mov     [rbx+60h], rsi
0x14005fe5d  mov     rax, [rcx]
0x14005fe60  mov     rax, [rax+10h]
0x14005fe64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005fe69  xor     eax, eax
0x14005fe6b  add     rsp, 0E8h
0x14005fe72  pop     r15
0x14005fe74  pop     r13
0x14005fe76  pop     rdi
0x14005fe77  pop     rsi
0x14005fe78  pop     rbx
0x14005fe79  pop     rbp
0x14005fe7a  retn
```
