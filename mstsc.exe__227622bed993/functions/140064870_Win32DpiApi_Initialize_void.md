# Win32DpiApi::Initialize(void)

- ea: `0x140064870`
- end: `0x140064cd0`
- name: `?Initialize@Win32DpiApi@@EEAAJXZ`
- size: `1120`
- prototype: `__int64 __fastcall(Win32DpiApi *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400642c4`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x140064870`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14006488e`
- `KERNEL32!LoadLibraryW` at `0x1400649f7`
- `KERNEL32!LoadLibraryW` at `0x14006488e`
- `KERNEL32!LoadLibraryW` at `0x1400649f7`
- `KERNEL32!GetProcAddress` at `0x1400648ab`
- `KERNEL32!GetProcAddress` at `0x1400648ff`
- `KERNEL32!GetProcAddress` at `0x140064953`
- `KERNEL32!GetProcAddress` at `0x1400649a7`
- `KERNEL32!GetProcAddress` at `0x140064a14`
- `KERNEL32!GetProcAddress` at `0x140064a71`
- `KERNEL32!GetProcAddress` at `0x140064ac7`
- `KERNEL32!GetProcAddress` at `0x140064b1d`
- `KERNEL32!GetProcAddress` at `0x140064b73`
- `KERNEL32!GetProcAddress` at `0x140064bcc`
- `KERNEL32!GetProcAddress` at `0x140064c25`
- `KERNEL32!GetProcAddress` at `0x1400648ab`
- `KERNEL32!GetProcAddress` at `0x1400648ff`
- `KERNEL32!GetProcAddress` at `0x140064953`
- `KERNEL32!GetProcAddress` at `0x1400649a7`
- `KERNEL32!GetProcAddress` at `0x140064a14`
- `KERNEL32!GetProcAddress` at `0x140064a71`
- `KERNEL32!GetProcAddress` at `0x140064ac7`
- `KERNEL32!GetProcAddress` at `0x140064b1d`
- `KERNEL32!GetProcAddress` at `0x140064b73`
- `KERNEL32!GetProcAddress` at `0x140064bcc`
- `KERNEL32!GetProcAddress` at `0x140064c25`

## string_xrefs

- `0x140064887`: `shcore.dll`
- `0x1400649f0`: `user32.dll`
- `0x140064bc5`: `GetThreadDpiAwarenessContext`

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
0x140064870  mov     [rsp+arg_0], rbx
0x140064875  mov     [rsp+arg_8], rbp
0x14006487a  push    rdi
0x14006487b  sub     rsp, 20h
0x14006487f  mov     rbx, rcx
0x140064882  mov     ebp, 80004005h
0x140064887  lea     rcx, aShcoreDll_0; "shcore.dll"
0x14006488e  call    cs:__imp_LoadLibraryW
0x140064894  mov     [rbx+28h], rax
0x140064898  test    rax, rax
0x14006489b  jz      loc_140064C7B
0x1400648a1  lea     rdx, aGetscalefactor; "GetScaleFactorForMonitor"
0x1400648a8  mov     rcx, rax; hModule
0x1400648ab  call    cs:__imp_GetProcAddress
0x1400648b1  mov     [rbx+38h], rax
0x1400648b5  test    rax, rax
0x1400648b8  jnz     short loc_1400648F4
0x1400648ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400648c1  lea     rdi, WPP_GLOBAL_Control
0x1400648c8  cmp     rax, rdi
0x1400648cb  jz      loc_140064CBE
0x1400648d1  test    byte ptr [rax+1Ch], 1
0x1400648d5  jz      loc_140064CBE
0x1400648db  cmp     byte ptr [rax+19h], 2
0x1400648df  jb      loc_140064CBE
0x1400648e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400648ea  mov     edx, 0Eh
0x1400648ef  jmp     loc_140064CA4
0x1400648f4  mov     rcx, [rbx+28h]; hModule
0x1400648f8  lea     rdx, aGetdpiformonit; "GetDpiForMonitor"
0x1400648ff  call    cs:__imp_GetProcAddress
0x140064905  mov     [rbx+40h], rax
0x140064909  test    rax, rax
0x14006490c  jnz     short loc_140064948
0x14006490e  mov     rax, cs:WPP_GLOBAL_Control
0x140064915  lea     rdi, WPP_GLOBAL_Control
0x14006491c  cmp     rax, rdi
0x14006491f  jz      loc_140064CBE
0x140064925  test    byte ptr [rax+1Ch], 1
0x140064929  jz      loc_140064CBE
0x14006492f  cmp     byte ptr [rax+19h], 2
0x140064933  jb      loc_140064CBE
0x140064939  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006493e  mov     edx, 0Fh
0x140064943  jmp     loc_140064CA4
0x140064948  mov     rcx, [rbx+28h]; hModule
0x14006494c  lea     rdx, aGetprocessdpia; "GetProcessDpiAwareness"
0x140064953  call    cs:__imp_GetProcAddress
0x140064959  mov     [rbx+48h], rax
0x14006495d  test    rax, rax
0x140064960  jnz     short loc_14006499C
0x140064962  mov     rax, cs:WPP_GLOBAL_Control
0x140064969  lea     rdi, WPP_GLOBAL_Control
0x140064970  cmp     rax, rdi
0x140064973  jz      loc_140064CBE
0x140064979  test    byte ptr [rax+1Ch], 1
0x14006497d  jz      loc_140064CBE
0x140064983  cmp     byte ptr [rax+19h], 2
0x140064987  jb      loc_140064CBE
0x14006498d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064992  mov     edx, 10h
0x140064997  jmp     loc_140064CA4
0x14006499c  mov     rcx, [rbx+28h]; hModule
0x1400649a0  lea     rdx, aSetprocessdpia; "SetProcessDpiAwareness"
0x1400649a7  call    cs:__imp_GetProcAddress
0x1400649ad  mov     [rbx+50h], rax
0x1400649b1  test    rax, rax
0x1400649b4  jnz     short loc_1400649F0
0x1400649b6  mov     rax, cs:WPP_GLOBAL_Control
0x1400649bd  lea     rdi, WPP_GLOBAL_Control
0x1400649c4  cmp     rax, rdi
0x1400649c7  jz      loc_140064CBE
0x1400649cd  test    byte ptr [rax+1Ch], 1
0x1400649d1  jz      loc_140064CBE
0x1400649d7  cmp     byte ptr [rax+19h], 2
0x1400649db  jb      loc_140064CBE
0x1400649e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400649e6  mov     edx, 11h
0x1400649eb  jmp     loc_140064CA4
0x1400649f0  lea     rcx, aUser32Dll_0; "user32.dll"
0x1400649f7  call    cs:__imp_LoadLibraryW
0x1400649fd  mov     [rbx+30h], rax
0x140064a01  test    rax, rax
0x140064a04  jz      loc_140064C73
0x140064a0a  lea     rdx, aSetprocessdpia_0; "SetProcessDpiAwarenessContext"
0x140064a11  mov     rcx, rax; hModule
0x140064a14  call    cs:__imp_GetProcAddress
0x140064a1a  mov     [rbx+58h], rax
0x140064a1e  lea     rdi, WPP_GLOBAL_Control
0x140064a25  test    rax, rax
0x140064a28  jnz     short loc_140064A66
0x140064a2a  mov     rax, cs:WPP_GLOBAL_Control
0x140064a31  cmp     rax, rdi
0x140064a34  jz      short loc_140064A66
0x140064a36  test    byte ptr [rax+1Ch], 1
0x140064a3a  jz      short loc_140064A66
0x140064a3c  cmp     byte ptr [rax+19h], 5
0x140064a40  jb      short loc_140064A66
0x140064a42  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064a47  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a4e  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064a55  mov     edx, 13h
0x140064a5a  mov     r9d, eax
0x140064a5d  mov     rcx, [rcx+10h]
0x140064a61  call    WPP_SF_d
0x140064a66  mov     rcx, [rbx+30h]; hModule
0x140064a6a  lea     rdx, aEnablenonclien; "EnableNonClientDpiScaling"
0x140064a71  call    cs:__imp_GetProcAddress
0x140064a77  mov     [rbx+68h], rax
0x140064a7b  test    rax, rax
0x140064a7e  jnz     short loc_140064ABC
0x140064a80  mov     rax, cs:WPP_GLOBAL_Control
0x140064a87  cmp     rax, rdi
0x140064a8a  jz      short loc_140064ABC
0x140064a8c  test    byte ptr [rax+1Ch], 1
0x140064a90  jz      short loc_140064ABC
0x140064a92  cmp     byte ptr [rax+19h], 5
0x140064a96  jb      short loc_140064ABC
0x140064a98  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140064aa4  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064aab  mov     edx, 15h
0x140064ab0  mov     r9d, eax
0x140064ab3  mov     rcx, [rcx+10h]
0x140064ab7  call    WPP_SF_d
0x140064abc  mov     rcx, [rbx+30h]; hModule
0x140064ac0  lea     rdx, aGetdpiforwindo; "GetDpiForWindow"
0x140064ac7  call    cs:__imp_GetProcAddress
0x140064acd  mov     [rbx+70h], rax
0x140064ad1  test    rax, rax
0x140064ad4  jnz     short loc_140064B12
0x140064ad6  mov     rax, cs:WPP_GLOBAL_Control
0x140064add  cmp     rax, rdi
0x140064ae0  jz      short loc_140064B12
0x140064ae2  test    byte ptr [rax+1Ch], 1
0x140064ae6  jz      short loc_140064B12
0x140064ae8  cmp     byte ptr [rax+19h], 5
0x140064aec  jb      short loc_140064B12
0x140064aee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064af3  mov     rcx, cs:WPP_GLOBAL_Control
0x140064afa  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064b01  mov     edx, 16h
0x140064b06  mov     r9d, eax
0x140064b09  mov     rcx, [rcx+10h]
0x140064b0d  call    WPP_SF_d
0x140064b12  mov     rcx, [rbx+30h]; hModule
0x140064b16  lea     rdx, aAdjustwindowre; "AdjustWindowRectExForDpi"
0x140064b1d  call    cs:__imp_GetProcAddress
0x140064b23  mov     [rbx+78h], rax
0x140064b27  test    rax, rax
0x140064b2a  jnz     short loc_140064B68
0x140064b2c  mov     rax, cs:WPP_GLOBAL_Control
0x140064b33  cmp     rax, rdi
0x140064b36  jz      short loc_140064B68
0x140064b38  test    byte ptr [rax+1Ch], 1
0x140064b3c  jz      short loc_140064B68
0x140064b3e  cmp     byte ptr [rax+19h], 5
0x140064b42  jb      short loc_140064B68
0x140064b44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064b49  mov     rcx, cs:WPP_GLOBAL_Control
0x140064b50  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064b57  mov     edx, 17h
0x140064b5c  mov     r9d, eax
0x140064b5f  mov     rcx, [rcx+10h]
0x140064b63  call    WPP_SF_d
0x140064b68  mov     rcx, [rbx+30h]; hModule
0x140064b6c  lea     rdx, aGetsystemmetri; "GetSystemMetricsForDpi"
0x140064b73  call    cs:__imp_GetProcAddress
0x140064b79  mov     [rbx+80h], rax
0x140064b80  test    rax, rax
0x140064b83  jnz     short loc_140064BC1
0x140064b85  mov     rax, cs:WPP_GLOBAL_Control
0x140064b8c  cmp     rax, rdi
0x140064b8f  jz      short loc_140064BC1
0x140064b91  test    byte ptr [rax+1Ch], 1
0x140064b95  jz      short loc_140064BC1
0x140064b97  cmp     byte ptr [rax+19h], 5
0x140064b9b  jb      short loc_140064BC1
0x140064b9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140064ba9  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064bb0  mov     edx, 18h
0x140064bb5  mov     r9d, eax
0x140064bb8  mov     rcx, [rcx+10h]
0x140064bbc  call    WPP_SF_d
0x140064bc1  mov     rcx, [rbx+30h]; hModule
0x140064bc5  lea     rdx, aGetthreaddpiaw; "GetThreadDpiAwarenessContext"
0x140064bcc  call    cs:__imp_GetProcAddress
0x140064bd2  mov     [rbx+88h], rax
0x140064bd9  test    rax, rax
0x140064bdc  jnz     short loc_140064C1A
0x140064bde  mov     rax, cs:WPP_GLOBAL_Control
0x140064be5  cmp     rax, rdi
0x140064be8  jz      short loc_140064C1A
0x140064bea  test    byte ptr [rax+1Ch], 1
0x140064bee  jz      short loc_140064C1A
0x140064bf0  cmp     byte ptr [rax+19h], 5
0x140064bf4  jb      short loc_140064C1A
0x140064bf6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c02  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064c09  mov     edx, 19h
0x140064c0e  mov     r9d, eax
0x140064c11  mov     rcx, [rcx+10h]
0x140064c15  call    WPP_SF_d
0x140064c1a  mov     rcx, [rbx+30h]; hModule
0x140064c1e  lea     rdx, aAredpiawarenes; "AreDpiAwarenessContextsEqual"
0x140064c25  call    cs:__imp_GetProcAddress
0x140064c2b  mov     [rbx+90h], rax
0x140064c32  test    rax, rax
0x140064c35  jnz     short loc_140064C73
0x140064c37  mov     rax, cs:WPP_GLOBAL_Control
0x140064c3e  cmp     rax, rdi
0x140064c41  jz      short loc_140064C73
0x140064c43  test    byte ptr [rax+1Ch], 1
0x140064c47  jz      short loc_140064C73
0x140064c49  cmp     byte ptr [rax+19h], 5
0x140064c4d  jb      short loc_140064C73
0x140064c4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064c54  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c5b  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064c62  mov     edx, 1Ah
0x140064c67  mov     r9d, eax
0x140064c6a  mov     rcx, [rcx+10h]
0x140064c6e  call    WPP_SF_d
0x140064c73  or      dword ptr [rbx+14h], 2
0x140064c77  xor     ebp, ebp
0x140064c79  jmp     short loc_140064CBE
0x140064c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c82  lea     rdi, WPP_GLOBAL_Control
0x140064c89  cmp     rcx, rdi
0x140064c8c  jz      short loc_140064CBE
0x140064c8e  test    byte ptr [rcx+1Ch], 1
0x140064c92  jz      short loc_140064CBE
0x140064c94  cmp     byte ptr [rcx+19h], 5
0x140064c98  jb      short loc_140064CBE
0x140064c9a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140064c9f  mov     edx, 12h
0x140064ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x140064cab  lea     r8, WPP_35628b70d5363a316590e8499969a27c_Traceguids
0x140064cb2  mov     r9d, eax
0x140064cb5  mov     rcx, [rcx+10h]
0x140064cb9  call    WPP_SF_d
0x140064cbe  mov     rbx, [rsp+28h+arg_0]
0x140064cc3  mov     eax, ebp
0x140064cc5  mov     rbp, [rsp+28h+arg_8]
0x140064cca  add     rsp, 20h
0x140064cce  pop     rdi
0x140064ccf  retn
```
