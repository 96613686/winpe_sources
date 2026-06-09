# Win32DpiApi::Initialize(void)

- ea: `0x140059e30`
- end: `0x14005a2e9`
- name: `?Initialize@Win32DpiApi@@EEAAJXZ`
- size: `1209`
- prototype: `__int64 __fastcall(Win32DpiApi *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140059af8`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140059e30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059e6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059f15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059f69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059fd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a031`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a087`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a0dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a133`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a1e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a23b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059e6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059f15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059f69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059fd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a031`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a087`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a0dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a133`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a1e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005a23b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140059e50`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140059fb9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140059e50`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140059fb9`

## string_xrefs

- `0x140059fb2`: `user32.dll`
- `0x140059e49`: `shcore.dll`
- `0x14005a1db`: `GetThreadDpiAwarenessContext`

## pseudocode

```c
__int64 __fastcall Win32DpiApi::Initialize(Win32DpiApi *this)
{
  unsigned int v2; // r14d
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v5; // eax
  __int64 v6; // rdx
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  HMODULE v10; // rax
  FARPROC v11; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  FARPROC v13; // rax
  unsigned int v14; // eax
  FARPROC v15; // rax
  unsigned int v16; // eax
  FARPROC v17; // rax
  unsigned int v18; // eax
  FARPROC v19; // rax
  unsigned int v20; // eax
  FARPROC v21; // rax
  unsigned int v22; // eax
  FARPROC v23; // rax
  unsigned int v24; // eax
  FARPROC v25; // rax
  unsigned int v26; // eax

  v2 = -2147467259;
  LibraryW = LoadLibraryW(L"shcore.dll");
  *((_QWORD *)this + 5) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetScaleFactorForMonitor");
    *((_QWORD *)this + 7) = ProcAddress;
    if ( ProcAddress )
    {
      v7 = GetProcAddress(*((HMODULE *)this + 5), "GetDpiForMonitor");
      *((_QWORD *)this + 8) = v7;
      if ( v7 )
      {
        v8 = GetProcAddress(*((HMODULE *)this + 5), "GetProcessDpiAwareness");
        *((_QWORD *)this + 9) = v8;
        if ( v8 )
        {
          v9 = GetProcAddress(*((HMODULE *)this + 5), "SetProcessDpiAwareness");
          *((_QWORD *)this + 10) = v9;
          if ( v9 )
          {
            v10 = LoadLibraryW(L"user32.dll");
            *((_QWORD *)this + 6) = v10;
            if ( v10 )
            {
              v11 = GetProcAddress(v10, "SetProcessDpiAwarenessContext");
              *((_QWORD *)this + 11) = v11;
              if ( !v11
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  WPP_35628b70d5363a316590e8499969a27c_Traceguids,
                  CurrentThreadActivityIdPrefix);
              }
              v13 = GetProcAddress(*((HMODULE *)this + 6), (LPCSTR)0xA26);
              *((_QWORD *)this + 12) = v13;
              if ( !v13
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v14 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v14);
              }
              v15 = GetProcAddress(*((HMODULE *)this + 6), "EnableNonClientDpiScaling");
              *((_QWORD *)this + 13) = v15;
              if ( !v15
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v16 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v16);
              }
              v17 = GetProcAddress(*((HMODULE *)this + 6), "GetDpiForWindow");
              *((_QWORD *)this + 14) = v17;
              if ( !v17
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v18 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v18);
              }
              v19 = GetProcAddress(*((HMODULE *)this + 6), "AdjustWindowRectExForDpi");
              *((_QWORD *)this + 15) = v19;
              if ( !v19
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v20 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v20);
              }
              v21 = GetProcAddress(*((HMODULE *)this + 6), "GetSystemMetricsForDpi");
              *((_QWORD *)this + 16) = v21;
              if ( !v21
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v22 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v22);
              }
              v23 = GetProcAddress(*((HMODULE *)this + 6), "GetThreadDpiAwarenessContext");
              *((_QWORD *)this + 17) = v23;
              if ( !v23
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v24 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v24);
              }
              v25 = GetProcAddress(*((HMODULE *)this + 6), "AreDpiAwarenessContextsEqual");
              *((_QWORD *)this + 18) = v25;
              if ( !v25
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v26 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v26);
              }
            }
            *((_DWORD *)this + 5) |= 2u;
            return 0;
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v5 = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 17;
            goto LABEL_68;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = RdpWppGetCurrentThreadActivityIdPrefix();
          v6 = 16;
          goto LABEL_68;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 15;
        goto LABEL_68;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 14;
LABEL_68:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v5);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 18;
    goto LABEL_68;
  }
  return v2;
}

```

## disassembly

```asm
0x140059e30  mov     [rsp+arg_0], rbx
0x140059e35  mov     [rsp+arg_8], rsi
0x140059e3a  push    r14
0x140059e3c  sub     rsp, 20h
0x140059e40  mov     rbx, rcx
0x140059e43  mov     r14d, 80004005h
0x140059e49  lea     rcx, aShcoreDll; "shcore.dll"
0x140059e50  call    cs:__imp_LoadLibraryW
0x140059e56  mov     [rbx+28h], rax
0x140059e5a  test    rax, rax
0x140059e5d  jz      loc_14005A292
0x140059e63  lea     rdx, aGetscalefactor; "GetScaleFactorForMonitor"
0x140059e6a  mov     rcx, rax; hModule
0x140059e6d  call    cs:__imp_GetProcAddress
0x140059e73  mov     [rbx+38h], rax
0x140059e77  test    rax, rax
0x140059e7a  jnz     short loc_140059EB6
0x140059e7c  mov     rax, cs:WPP_GLOBAL_Control
0x140059e83  lea     rsi, WPP_GLOBAL_Control
0x140059e8a  cmp     rax, rsi
0x140059e8d  jz      loc_14005A2D5
0x140059e93  test    byte ptr [rax+1Ch], 1
0x140059e97  jz      loc_14005A2D5
0x140059e9d  cmp     byte ptr [rax+19h], 2
0x140059ea1  jb      loc_14005A2D5
0x140059ea7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059eac  mov     edx, 0Eh
0x140059eb1  jmp     loc_14005A2BB
0x140059eb6  mov     rcx, [rbx+28h]; hModule
0x140059eba  lea     rdx, aGetdpiformonit_0; "GetDpiForMonitor"
0x140059ec1  call    cs:__imp_GetProcAddress
0x140059ec7  mov     [rbx+40h], rax
0x140059ecb  test    rax, rax
0x140059ece  jnz     short loc_140059F0A
0x140059ed0  mov     rax, cs:WPP_GLOBAL_Control
0x140059ed7  lea     rsi, WPP_GLOBAL_Control
0x140059ede  cmp     rax, rsi
0x140059ee1  jz      loc_14005A2D5
0x140059ee7  test    byte ptr [rax+1Ch], 1
0x140059eeb  jz      loc_14005A2D5
0x140059ef1  cmp     byte ptr [rax+19h], 2
0x140059ef5  jb      loc_14005A2D5
0x140059efb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059f00  mov     edx, 0Fh
0x140059f05  jmp     loc_14005A2BB
0x140059f0a  mov     rcx, [rbx+28h]; hModule
0x140059f0e  lea     rdx, aGetprocessdpia; "GetProcessDpiAwareness"
0x140059f15  call    cs:__imp_GetProcAddress
0x140059f1b  mov     [rbx+48h], rax
0x140059f1f  test    rax, rax
0x140059f22  jnz     short loc_140059F5E
0x140059f24  mov     rax, cs:WPP_GLOBAL_Control
0x140059f2b  lea     rsi, WPP_GLOBAL_Control
0x140059f32  cmp     rax, rsi
0x140059f35  jz      loc_14005A2D5
0x140059f3b  test    byte ptr [rax+1Ch], 1
0x140059f3f  jz      loc_14005A2D5
0x140059f45  cmp     byte ptr [rax+19h], 2
0x140059f49  jb      loc_14005A2D5
0x140059f4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059f54  mov     edx, 10h
0x140059f59  jmp     loc_14005A2BB
0x140059f5e  mov     rcx, [rbx+28h]; hModule
0x140059f62  lea     rdx, aSetprocessdpia; "SetProcessDpiAwareness"
0x140059f69  call    cs:__imp_GetProcAddress
0x140059f6f  mov     [rbx+50h], rax
0x140059f73  test    rax, rax
0x140059f76  jnz     short loc_140059FB2
0x140059f78  mov     rax, cs:WPP_GLOBAL_Control
0x140059f7f  lea     rsi, WPP_GLOBAL_Control
0x140059f86  cmp     rax, rsi
0x140059f89  jz      loc_14005A2D5
0x140059f8f  test    byte ptr [rax+1Ch], 1
0x140059f93  jz      loc_14005A2D5
0x140059f99  cmp     byte ptr [rax+19h], 2
0x140059f9d  jb      loc_14005A2D5
0x140059fa3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059fa8  mov     edx, 11h
0x140059fad  jmp     loc_14005A2BB
0x140059fb2  lea     rcx, aUser32Dll_0; "user32.dll"
0x140059fb9  call    cs:__imp_LoadLibraryW
0x140059fbf  mov     [rbx+30h], rax
0x140059fc3  test    rax, rax
0x140059fc6  jz      loc_14005A289
0x140059fcc  lea     rdx, aSetprocessdpia_0; "SetProcessDpiAwarenessContext"
0x140059fd3  mov     rcx, rax; hModule
0x140059fd6  call    cs:__imp_GetProcAddress
0x140059fdc  mov     [rbx+58h], rax
0x140059fe0  lea     rsi, WPP_GLOBAL_Control
0x140059fe7  test    rax, rax
0x140059fea  jnz     short loc_14005A028
0x140059fec  mov     rax, cs:WPP_GLOBAL_Control
0x140059ff3  cmp     rax, rsi
0x140059ff6  jz      short loc_14005A028
0x140059ff8  test    byte ptr [rax+1Ch], 1
0x140059ffc  jz      short loc_14005A028
0x140059ffe  cmp     byte ptr [rax+19h], 5
0x14005a002  jb      short loc_14005A028
0x14005a004  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a009  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a010  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a017  mov     edx, 13h
0x14005a01c  mov     r9d, eax
0x14005a01f  mov     rcx, [rcx+10h]
0x14005a023  call    WPP_SF_d
0x14005a028  mov     rcx, [rbx+30h]; hModule
0x14005a02c  mov     edx, 0A26h; lpProcName
0x14005a031  call    cs:__imp_GetProcAddress
0x14005a037  mov     [rbx+60h], rax
0x14005a03b  test    rax, rax
0x14005a03e  jnz     short loc_14005A07C
0x14005a040  mov     rax, cs:WPP_GLOBAL_Control
0x14005a047  cmp     rax, rsi
0x14005a04a  jz      short loc_14005A07C
0x14005a04c  test    byte ptr [rax+1Ch], 1
0x14005a050  jz      short loc_14005A07C
0x14005a052  cmp     byte ptr [rax+19h], 5
0x14005a056  jb      short loc_14005A07C
0x14005a058  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a05d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a064  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a06b  mov     edx, 14h
0x14005a070  mov     r9d, eax
0x14005a073  mov     rcx, [rcx+10h]
0x14005a077  call    WPP_SF_d
0x14005a07c  mov     rcx, [rbx+30h]; hModule
0x14005a080  lea     rdx, aEnablenonclien; "EnableNonClientDpiScaling"
0x14005a087  call    cs:__imp_GetProcAddress
0x14005a08d  mov     [rbx+68h], rax
0x14005a091  test    rax, rax
0x14005a094  jnz     short loc_14005A0D2
0x14005a096  mov     rax, cs:WPP_GLOBAL_Control
0x14005a09d  cmp     rax, rsi
0x14005a0a0  jz      short loc_14005A0D2
0x14005a0a2  test    byte ptr [rax+1Ch], 1
0x14005a0a6  jz      short loc_14005A0D2
0x14005a0a8  cmp     byte ptr [rax+19h], 5
0x14005a0ac  jb      short loc_14005A0D2
0x14005a0ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a0ba  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a0c1  mov     edx, 15h
0x14005a0c6  mov     r9d, eax
0x14005a0c9  mov     rcx, [rcx+10h]
0x14005a0cd  call    WPP_SF_d
0x14005a0d2  mov     rcx, [rbx+30h]; hModule
0x14005a0d6  lea     rdx, aGetdpiforwindo; "GetDpiForWindow"
0x14005a0dd  call    cs:__imp_GetProcAddress
0x14005a0e3  mov     [rbx+70h], rax
0x14005a0e7  test    rax, rax
0x14005a0ea  jnz     short loc_14005A128
0x14005a0ec  mov     rax, cs:WPP_GLOBAL_Control
0x14005a0f3  cmp     rax, rsi
0x14005a0f6  jz      short loc_14005A128
0x14005a0f8  test    byte ptr [rax+1Ch], 1
0x14005a0fc  jz      short loc_14005A128
0x14005a0fe  cmp     byte ptr [rax+19h], 5
0x14005a102  jb      short loc_14005A128
0x14005a104  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a109  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a110  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a117  mov     edx, 16h
0x14005a11c  mov     r9d, eax
0x14005a11f  mov     rcx, [rcx+10h]
0x14005a123  call    WPP_SF_d
0x14005a128  mov     rcx, [rbx+30h]; hModule
0x14005a12c  lea     rdx, aAdjustwindowre; "AdjustWindowRectExForDpi"
0x14005a133  call    cs:__imp_GetProcAddress
0x14005a139  mov     [rbx+78h], rax
0x14005a13d  test    rax, rax
0x14005a140  jnz     short loc_14005A17E
0x14005a142  mov     rax, cs:WPP_GLOBAL_Control
0x14005a149  cmp     rax, rsi
0x14005a14c  jz      short loc_14005A17E
0x14005a14e  test    byte ptr [rax+1Ch], 1
0x14005a152  jz      short loc_14005A17E
0x14005a154  cmp     byte ptr [rax+19h], 5
0x14005a158  jb      short loc_14005A17E
0x14005a15a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a15f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a166  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a16d  mov     edx, 17h
0x14005a172  mov     r9d, eax
0x14005a175  mov     rcx, [rcx+10h]
0x14005a179  call    WPP_SF_d
0x14005a17e  mov     rcx, [rbx+30h]; hModule
0x14005a182  lea     rdx, aGetsystemmetri; "GetSystemMetricsForDpi"
0x14005a189  call    cs:__imp_GetProcAddress
0x14005a18f  mov     [rbx+80h], rax
0x14005a196  test    rax, rax
0x14005a199  jnz     short loc_14005A1D7
0x14005a19b  mov     rax, cs:WPP_GLOBAL_Control
0x14005a1a2  cmp     rax, rsi
0x14005a1a5  jz      short loc_14005A1D7
0x14005a1a7  test    byte ptr [rax+1Ch], 1
0x14005a1ab  jz      short loc_14005A1D7
0x14005a1ad  cmp     byte ptr [rax+19h], 5
0x14005a1b1  jb      short loc_14005A1D7
0x14005a1b3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a1bf  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a1c6  mov     edx, 18h
0x14005a1cb  mov     r9d, eax
0x14005a1ce  mov     rcx, [rcx+10h]
0x14005a1d2  call    WPP_SF_d
0x14005a1d7  mov     rcx, [rbx+30h]; hModule
0x14005a1db  lea     rdx, aGetthreaddpiaw; "GetThreadDpiAwarenessContext"
0x14005a1e2  call    cs:__imp_GetProcAddress
0x14005a1e8  mov     [rbx+88h], rax
0x14005a1ef  test    rax, rax
0x14005a1f2  jnz     short loc_14005A230
0x14005a1f4  mov     rax, cs:WPP_GLOBAL_Control
0x14005a1fb  cmp     rax, rsi
0x14005a1fe  jz      short loc_14005A230
0x14005a200  test    byte ptr [rax+1Ch], 1
0x14005a204  jz      short loc_14005A230
0x14005a206  cmp     byte ptr [rax+19h], 5
0x14005a20a  jb      short loc_14005A230
0x14005a20c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a211  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a218  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a21f  mov     edx, 19h
0x14005a224  mov     r9d, eax
0x14005a227  mov     rcx, [rcx+10h]
0x14005a22b  call    WPP_SF_d
0x14005a230  mov     rcx, [rbx+30h]; hModule
0x14005a234  lea     rdx, aAredpiawarenes; "AreDpiAwarenessContextsEqual"
0x14005a23b  call    cs:__imp_GetProcAddress
0x14005a241  mov     [rbx+90h], rax
0x14005a248  test    rax, rax
0x14005a24b  jnz     short loc_14005A289
0x14005a24d  mov     rax, cs:WPP_GLOBAL_Control
0x14005a254  cmp     rax, rsi
0x14005a257  jz      short loc_14005A289
0x14005a259  test    byte ptr [rax+1Ch], 1
0x14005a25d  jz      short loc_14005A289
0x14005a25f  cmp     byte ptr [rax+19h], 5
0x14005a263  jb      short loc_14005A289
0x14005a265  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a26a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a271  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a278  mov     edx, 1Ah
0x14005a27d  mov     r9d, eax
0x14005a280  mov     rcx, [rcx+10h]
0x14005a284  call    WPP_SF_d
0x14005a289  or      dword ptr [rbx+14h], 2
0x14005a28d  xor     r14d, r14d
0x14005a290  jmp     short loc_14005A2D5
0x14005a292  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a299  lea     rsi, WPP_GLOBAL_Control
0x14005a2a0  cmp     rcx, rsi
0x14005a2a3  jz      short loc_14005A2D5
0x14005a2a5  test    byte ptr [rcx+1Ch], 1
0x14005a2a9  jz      short loc_14005A2D5
0x14005a2ab  cmp     byte ptr [rcx+19h], 5
0x14005a2af  jb      short loc_14005A2D5
0x14005a2b1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005a2b6  mov     edx, 12h
0x14005a2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2c2  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x14005a2c9  mov     r9d, eax
0x14005a2cc  mov     rcx, [rcx+10h]
0x14005a2d0  call    WPP_SF_d
0x14005a2d5  mov     rbx, [rsp+28h+arg_0]
0x14005a2da  mov     eax, r14d
0x14005a2dd  mov     rsi, [rsp+28h+arg_8]
0x14005a2e2  add     rsp, 20h
0x14005a2e6  pop     r14
0x14005a2e8  retn
```
