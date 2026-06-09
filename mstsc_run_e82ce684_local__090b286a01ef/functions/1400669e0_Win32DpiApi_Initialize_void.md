# Win32DpiApi::Initialize(void)

- ea: `0x1400669e0`
- end: `0x140066e40`
- name: `?Initialize@Win32DpiApi@@EEAAJXZ`
- size: `1120`
- prototype: `__int64 __fastcall(Win32DpiApi *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140066434`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x1400669e0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400669fe`
- `KERNEL32!LoadLibraryW` at `0x140066b67`
- `KERNEL32!LoadLibraryW` at `0x1400669fe`
- `KERNEL32!LoadLibraryW` at `0x140066b67`
- `KERNEL32!GetProcAddress` at `0x140066a1b`
- `KERNEL32!GetProcAddress` at `0x140066a6f`
- `KERNEL32!GetProcAddress` at `0x140066ac3`
- `KERNEL32!GetProcAddress` at `0x140066b17`
- `KERNEL32!GetProcAddress` at `0x140066b84`
- `KERNEL32!GetProcAddress` at `0x140066be1`
- `KERNEL32!GetProcAddress` at `0x140066c37`
- `KERNEL32!GetProcAddress` at `0x140066c8d`
- `KERNEL32!GetProcAddress` at `0x140066ce3`
- `KERNEL32!GetProcAddress` at `0x140066d3c`
- `KERNEL32!GetProcAddress` at `0x140066d95`
- `KERNEL32!GetProcAddress` at `0x140066a1b`
- `KERNEL32!GetProcAddress` at `0x140066a6f`
- `KERNEL32!GetProcAddress` at `0x140066ac3`
- `KERNEL32!GetProcAddress` at `0x140066b17`
- `KERNEL32!GetProcAddress` at `0x140066b84`
- `KERNEL32!GetProcAddress` at `0x140066be1`
- `KERNEL32!GetProcAddress` at `0x140066c37`
- `KERNEL32!GetProcAddress` at `0x140066c8d`
- `KERNEL32!GetProcAddress` at `0x140066ce3`
- `KERNEL32!GetProcAddress` at `0x140066d3c`
- `KERNEL32!GetProcAddress` at `0x140066d95`

## string_xrefs

- `0x1400669f7`: `shcore.dll`
- `0x140066b60`: `user32.dll`
- `0x140066d35`: `GetThreadDpiAwarenessContext`

## pseudocode

```c
__int64 __fastcall Win32DpiApi::Initialize(Win32DpiApi *this)
{
  unsigned int v2; // ebp
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
              v13 = GetProcAddress(*((HMODULE *)this + 6), "EnableNonClientDpiScaling");
              *((_QWORD *)this + 13) = v13;
              if ( !v13
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v14 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v14);
              }
              v15 = GetProcAddress(*((HMODULE *)this + 6), "GetDpiForWindow");
              *((_QWORD *)this + 14) = v15;
              if ( !v15
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v16 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v16);
              }
              v17 = GetProcAddress(*((HMODULE *)this + 6), "AdjustWindowRectExForDpi");
              *((_QWORD *)this + 15) = v17;
              if ( !v17
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v18 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v18);
              }
              v19 = GetProcAddress(*((HMODULE *)this + 6), "GetSystemMetricsForDpi");
              *((_QWORD *)this + 16) = v19;
              if ( !v19
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v20 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v20);
              }
              v21 = GetProcAddress(*((HMODULE *)this + 6), "GetThreadDpiAwarenessContext");
              *((_QWORD *)this + 17) = v21;
              if ( !v21
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v22 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v22);
              }
              v23 = GetProcAddress(*((HMODULE *)this + 6), "AreDpiAwarenessContextsEqual");
              *((_QWORD *)this + 18) = v23;
              if ( !v23
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v24 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v24);
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
            goto LABEL_63;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = RdpWppGetCurrentThreadActivityIdPrefix();
          v6 = 16;
          goto LABEL_63;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 15;
        goto LABEL_63;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 14;
LABEL_63:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_35628b70d5363a316590e8499969a27c_Traceguids, v5);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 18;
    goto LABEL_63;
  }
  return v2;
}

```

## disassembly

```asm
0x1400669e0  mov     [rsp+arg_0], rbx
0x1400669e5  mov     [rsp+arg_8], rbp
0x1400669ea  push    rdi
0x1400669eb  sub     rsp, 20h
0x1400669ef  mov     rbx, rcx
0x1400669f2  mov     ebp, 80004005h
0x1400669f7  lea     rcx, aShcoreDll_0; "shcore.dll"
0x1400669fe  call    cs:__imp_LoadLibraryW
0x140066a04  mov     [rbx+28h], rax
0x140066a08  test    rax, rax
0x140066a0b  jz      loc_140066DEB
0x140066a11  lea     rdx, aGetscalefactor; "GetScaleFactorForMonitor"
0x140066a18  mov     rcx, rax; hModule
0x140066a1b  call    cs:__imp_GetProcAddress
0x140066a21  mov     [rbx+38h], rax
0x140066a25  test    rax, rax
0x140066a28  jnz     short loc_140066A64
0x140066a2a  mov     rax, cs:WPP_GLOBAL_Control
0x140066a31  lea     rdi, WPP_GLOBAL_Control
0x140066a38  cmp     rax, rdi
0x140066a3b  jz      loc_140066E2E
0x140066a41  test    byte ptr [rax+1Ch], 1
0x140066a45  jz      loc_140066E2E
0x140066a4b  cmp     byte ptr [rax+19h], 2
0x140066a4f  jb      loc_140066E2E
0x140066a55  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066a5a  mov     edx, 0Eh
0x140066a5f  jmp     loc_140066E14
0x140066a64  mov     rcx, [rbx+28h]; hModule
0x140066a68  lea     rdx, aGetdpiformonit; "GetDpiForMonitor"
0x140066a6f  call    cs:__imp_GetProcAddress
0x140066a75  mov     [rbx+40h], rax
0x140066a79  test    rax, rax
0x140066a7c  jnz     short loc_140066AB8
0x140066a7e  mov     rax, cs:WPP_GLOBAL_Control
0x140066a85  lea     rdi, WPP_GLOBAL_Control
0x140066a8c  cmp     rax, rdi
0x140066a8f  jz      loc_140066E2E
0x140066a95  test    byte ptr [rax+1Ch], 1
0x140066a99  jz      loc_140066E2E
0x140066a9f  cmp     byte ptr [rax+19h], 2
0x140066aa3  jb      loc_140066E2E
0x140066aa9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066aae  mov     edx, 0Fh
0x140066ab3  jmp     loc_140066E14
0x140066ab8  mov     rcx, [rbx+28h]; hModule
0x140066abc  lea     rdx, aGetprocessdpia; "GetProcessDpiAwareness"
0x140066ac3  call    cs:__imp_GetProcAddress
0x140066ac9  mov     [rbx+48h], rax
0x140066acd  test    rax, rax
0x140066ad0  jnz     short loc_140066B0C
0x140066ad2  mov     rax, cs:WPP_GLOBAL_Control
0x140066ad9  lea     rdi, WPP_GLOBAL_Control
0x140066ae0  cmp     rax, rdi
0x140066ae3  jz      loc_140066E2E
0x140066ae9  test    byte ptr [rax+1Ch], 1
0x140066aed  jz      loc_140066E2E
0x140066af3  cmp     byte ptr [rax+19h], 2
0x140066af7  jb      loc_140066E2E
0x140066afd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066b02  mov     edx, 10h
0x140066b07  jmp     loc_140066E14
0x140066b0c  mov     rcx, [rbx+28h]; hModule
0x140066b10  lea     rdx, aSetprocessdpia; "SetProcessDpiAwareness"
0x140066b17  call    cs:__imp_GetProcAddress
0x140066b1d  mov     [rbx+50h], rax
0x140066b21  test    rax, rax
0x140066b24  jnz     short loc_140066B60
0x140066b26  mov     rax, cs:WPP_GLOBAL_Control
0x140066b2d  lea     rdi, WPP_GLOBAL_Control
0x140066b34  cmp     rax, rdi
0x140066b37  jz      loc_140066E2E
0x140066b3d  test    byte ptr [rax+1Ch], 1
0x140066b41  jz      loc_140066E2E
0x140066b47  cmp     byte ptr [rax+19h], 2
0x140066b4b  jb      loc_140066E2E
0x140066b51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066b56  mov     edx, 11h
0x140066b5b  jmp     loc_140066E14
0x140066b60  lea     rcx, aUser32Dll_0; "user32.dll"
0x140066b67  call    cs:__imp_LoadLibraryW
0x140066b6d  mov     [rbx+30h], rax
0x140066b71  test    rax, rax
0x140066b74  jz      loc_140066DE3
0x140066b7a  lea     rdx, aSetprocessdpia_0; "SetProcessDpiAwarenessContext"
0x140066b81  mov     rcx, rax; hModule
0x140066b84  call    cs:__imp_GetProcAddress
0x140066b8a  mov     [rbx+58h], rax
0x140066b8e  lea     rdi, WPP_GLOBAL_Control
0x140066b95  test    rax, rax
0x140066b98  jnz     short loc_140066BD6
0x140066b9a  mov     rax, cs:WPP_GLOBAL_Control
0x140066ba1  cmp     rax, rdi
0x140066ba4  jz      short loc_140066BD6
0x140066ba6  test    byte ptr [rax+1Ch], 1
0x140066baa  jz      short loc_140066BD6
0x140066bac  cmp     byte ptr [rax+19h], 5
0x140066bb0  jb      short loc_140066BD6
0x140066bb2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140066bbe  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066bc5  mov     edx, 13h
0x140066bca  mov     r9d, eax
0x140066bcd  mov     rcx, [rcx+10h]
0x140066bd1  call    WPP_SF_d
0x140066bd6  mov     rcx, [rbx+30h]; hModule
0x140066bda  lea     rdx, aEnablenonclien; "EnableNonClientDpiScaling"
0x140066be1  call    cs:__imp_GetProcAddress
0x140066be7  mov     [rbx+68h], rax
0x140066beb  test    rax, rax
0x140066bee  jnz     short loc_140066C2C
0x140066bf0  mov     rax, cs:WPP_GLOBAL_Control
0x140066bf7  cmp     rax, rdi
0x140066bfa  jz      short loc_140066C2C
0x140066bfc  test    byte ptr [rax+1Ch], 1
0x140066c00  jz      short loc_140066C2C
0x140066c02  cmp     byte ptr [rax+19h], 5
0x140066c06  jb      short loc_140066C2C
0x140066c08  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140066c14  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066c1b  mov     edx, 15h
0x140066c20  mov     r9d, eax
0x140066c23  mov     rcx, [rcx+10h]
0x140066c27  call    WPP_SF_d
0x140066c2c  mov     rcx, [rbx+30h]; hModule
0x140066c30  lea     rdx, aGetdpiforwindo; "GetDpiForWindow"
0x140066c37  call    cs:__imp_GetProcAddress
0x140066c3d  mov     [rbx+70h], rax
0x140066c41  test    rax, rax
0x140066c44  jnz     short loc_140066C82
0x140066c46  mov     rax, cs:WPP_GLOBAL_Control
0x140066c4d  cmp     rax, rdi
0x140066c50  jz      short loc_140066C82
0x140066c52  test    byte ptr [rax+1Ch], 1
0x140066c56  jz      short loc_140066C82
0x140066c58  cmp     byte ptr [rax+19h], 5
0x140066c5c  jb      short loc_140066C82
0x140066c5e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066c63  mov     rcx, cs:WPP_GLOBAL_Control
0x140066c6a  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066c71  mov     edx, 16h
0x140066c76  mov     r9d, eax
0x140066c79  mov     rcx, [rcx+10h]
0x140066c7d  call    WPP_SF_d
0x140066c82  mov     rcx, [rbx+30h]; hModule
0x140066c86  lea     rdx, aAdjustwindowre; "AdjustWindowRectExForDpi"
0x140066c8d  call    cs:__imp_GetProcAddress
0x140066c93  mov     [rbx+78h], rax
0x140066c97  test    rax, rax
0x140066c9a  jnz     short loc_140066CD8
0x140066c9c  mov     rax, cs:WPP_GLOBAL_Control
0x140066ca3  cmp     rax, rdi
0x140066ca6  jz      short loc_140066CD8
0x140066ca8  test    byte ptr [rax+1Ch], 1
0x140066cac  jz      short loc_140066CD8
0x140066cae  cmp     byte ptr [rax+19h], 5
0x140066cb2  jb      short loc_140066CD8
0x140066cb4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140066cc0  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066cc7  mov     edx, 17h
0x140066ccc  mov     r9d, eax
0x140066ccf  mov     rcx, [rcx+10h]
0x140066cd3  call    WPP_SF_d
0x140066cd8  mov     rcx, [rbx+30h]; hModule
0x140066cdc  lea     rdx, aGetsystemmetri; "GetSystemMetricsForDpi"
0x140066ce3  call    cs:__imp_GetProcAddress
0x140066ce9  mov     [rbx+80h], rax
0x140066cf0  test    rax, rax
0x140066cf3  jnz     short loc_140066D31
0x140066cf5  mov     rax, cs:WPP_GLOBAL_Control
0x140066cfc  cmp     rax, rdi
0x140066cff  jz      short loc_140066D31
0x140066d01  test    byte ptr [rax+1Ch], 1
0x140066d05  jz      short loc_140066D31
0x140066d07  cmp     byte ptr [rax+19h], 5
0x140066d0b  jb      short loc_140066D31
0x140066d0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066d12  mov     rcx, cs:WPP_GLOBAL_Control
0x140066d19  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066d20  mov     edx, 18h
0x140066d25  mov     r9d, eax
0x140066d28  mov     rcx, [rcx+10h]
0x140066d2c  call    WPP_SF_d
0x140066d31  mov     rcx, [rbx+30h]; hModule
0x140066d35  lea     rdx, aGetthreaddpiaw; "GetThreadDpiAwarenessContext"
0x140066d3c  call    cs:__imp_GetProcAddress
0x140066d42  mov     [rbx+88h], rax
0x140066d49  test    rax, rax
0x140066d4c  jnz     short loc_140066D8A
0x140066d4e  mov     rax, cs:WPP_GLOBAL_Control
0x140066d55  cmp     rax, rdi
0x140066d58  jz      short loc_140066D8A
0x140066d5a  test    byte ptr [rax+1Ch], 1
0x140066d5e  jz      short loc_140066D8A
0x140066d60  cmp     byte ptr [rax+19h], 5
0x140066d64  jb      short loc_140066D8A
0x140066d66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140066d72  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066d79  mov     edx, 19h
0x140066d7e  mov     r9d, eax
0x140066d81  mov     rcx, [rcx+10h]
0x140066d85  call    WPP_SF_d
0x140066d8a  mov     rcx, [rbx+30h]; hModule
0x140066d8e  lea     rdx, aAredpiawarenes; "AreDpiAwarenessContextsEqual"
0x140066d95  call    cs:__imp_GetProcAddress
0x140066d9b  mov     [rbx+90h], rax
0x140066da2  test    rax, rax
0x140066da5  jnz     short loc_140066DE3
0x140066da7  mov     rax, cs:WPP_GLOBAL_Control
0x140066dae  cmp     rax, rdi
0x140066db1  jz      short loc_140066DE3
0x140066db3  test    byte ptr [rax+1Ch], 1
0x140066db7  jz      short loc_140066DE3
0x140066db9  cmp     byte ptr [rax+19h], 5
0x140066dbd  jb      short loc_140066DE3
0x140066dbf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140066dcb  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066dd2  mov     edx, 1Ah
0x140066dd7  mov     r9d, eax
0x140066dda  mov     rcx, [rcx+10h]
0x140066dde  call    WPP_SF_d
0x140066de3  or      dword ptr [rbx+14h], 2
0x140066de7  xor     ebp, ebp
0x140066de9  jmp     short loc_140066E2E
0x140066deb  mov     rcx, cs:WPP_GLOBAL_Control
0x140066df2  lea     rdi, WPP_GLOBAL_Control
0x140066df9  cmp     rcx, rdi
0x140066dfc  jz      short loc_140066E2E
0x140066dfe  test    byte ptr [rcx+1Ch], 1
0x140066e02  jz      short loc_140066E2E
0x140066e04  cmp     byte ptr [rcx+19h], 5
0x140066e08  jb      short loc_140066E2E
0x140066e0a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066e0f  mov     edx, 12h
0x140066e14  mov     rcx, cs:WPP_GLOBAL_Control
0x140066e1b  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140066e22  mov     r9d, eax
0x140066e25  mov     rcx, [rcx+10h]
0x140066e29  call    WPP_SF_d
0x140066e2e  mov     rbx, [rsp+28h+arg_0]
0x140066e33  mov     eax, ebp
0x140066e35  mov     rbp, [rsp+28h+arg_8]
0x140066e3a  add     rsp, 20h
0x140066e3e  pop     rdi
0x140066e3f  retn
```
