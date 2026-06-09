# LaunchClientProcessFromWow64(ushort const *,ushort *)

- ea: `0x140063878`
- end: `0x140063b44`
- name: `?LaunchClientProcessFromWow64@@YAJPEBGPEAG@Z`
- size: `716`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400645d0`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14001e210`
- `0x140063878`
- `0x140114010`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x1400639d2`
- `KERNEL32!CreateProcessW` at `0x1400639d2`
- `KERNEL32!LoadLibraryW` at `0x14006389a`
- `KERNEL32!LoadLibraryW` at `0x14006389a`
- `KERNEL32!FreeLibrary` at `0x140063b24`
- `KERNEL32!FreeLibrary` at `0x140063b24`
- `KERNEL32!GetProcAddress` at `0x14006391b`
- `KERNEL32!GetProcAddress` at `0x14006392e`
- `KERNEL32!GetProcAddress` at `0x14006391b`
- `KERNEL32!GetProcAddress` at `0x14006392e`
- `KERNEL32!CloseHandle` at `0x140063a42`
- `KERNEL32!CloseHandle` at `0x140063a4d`
- `KERNEL32!CloseHandle` at `0x140063a42`
- `KERNEL32!CloseHandle` at `0x140063a4d`
- `KERNEL32!GetLastError` at `0x1400638a8`
- `KERNEL32!GetLastError` at `0x1400639e3`
- `KERNEL32!GetLastError` at `0x1400638a8`
- `KERNEL32!GetLastError` at `0x1400639e3`

## string_xrefs

- `0x140063893`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall LaunchClientProcessFromWow64(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  FARPROC ProcAddress; // rbx
  FARPROC v10; // rax
  unsigned int (__fastcall *v11)(__int64); // rbp
  signed int LastError; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-88h] BYREF
  __int64 v20; // [rsp+110h] [rbp+18h] BYREF

  LibraryW = LoadLibraryW(L"kernel32.dll");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "Wow64DisableWow64FsRedirection");
    v10 = GetProcAddress(v5, "Wow64RevertWow64FsRedirection");
    v11 = (unsigned int (__fastcall *)(__int64))v10;
    if ( !ProcAddress || !v10 )
    {
      v7 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      goto LABEL_34;
    }
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    v20 = 0;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( ((unsigned int (__fastcall *)(__int64 *))ProcAddress)(&v20) )
    {
      if ( CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 1, 0x10u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        v7 = 0;
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
            v13,
            (__int64)lpApplicationName);
        }
      }
      if ( v11(v20) )
        goto LABEL_34;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_29:
        v7 = -2147467259;
LABEL_34:
        FreeLibrary(v5);
        return v7;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 16;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 17;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids, v14);
    goto LABEL_29;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids, v8);
  }
  return v7;
}

```

## disassembly

```asm
0x140063878  mov     [rsp+arg_0], rbx
0x14006387d  mov     [rsp+arg_8], rbp
0x140063882  push    rsi
0x140063883  push    rdi
0x140063884  push    r14
0x140063886  sub     rsp, 0E0h
0x14006388d  mov     r14, rcx
0x140063890  mov     rdi, rdx
0x140063893  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x14006389a  call    cs:__imp_LoadLibraryW
0x1400638a0  mov     rsi, rax
0x1400638a3  test    rax, rax
0x1400638a6  jnz     short loc_140063911
0x1400638a8  call    cs:__imp_GetLastError
0x1400638ae  mov     ebx, eax
0x1400638b0  test    eax, eax
0x1400638b2  jle     short loc_1400638BD
0x1400638b4  movzx   ebx, ax
0x1400638b7  or      ebx, 80070000h
0x1400638bd  mov     rax, cs:WPP_GLOBAL_Control
0x1400638c4  lea     rdi, WPP_GLOBAL_Control
0x1400638cb  cmp     rax, rdi
0x1400638ce  jz      loc_140063B2A
0x1400638d4  test    byte ptr [rax+1Ch], 1
0x1400638d8  jz      loc_140063B2A
0x1400638de  cmp     byte ptr [rax+19h], 2
0x1400638e2  jb      loc_140063B2A
0x1400638e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400638ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400638f4  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400638fb  mov     edx, 0Dh
0x140063900  mov     r9d, eax
0x140063903  mov     rcx, [rcx+10h]
0x140063907  call    WPP_SF_d
0x14006390c  jmp     loc_140063B2A
0x140063911  lea     rdx, aWow64disablewo; "Wow64DisableWow64FsRedirection"
0x140063918  mov     rcx, rsi; hModule
0x14006391b  call    cs:__imp_GetProcAddress
0x140063921  lea     rdx, aWow64revertwow; "Wow64RevertWow64FsRedirection"
0x140063928  mov     rcx, rsi; hModule
0x14006392b  mov     rbx, rax
0x14006392e  call    cs:__imp_GetProcAddress
0x140063934  mov     rbp, rax
0x140063937  test    rbx, rbx
0x14006393a  jz      loc_140063AD9
0x140063940  test    rax, rax
0x140063943  jz      loc_140063AD9
0x140063949  xor     edx, edx; Val
0x14006394b  lea     rcx, [rsp+0F8h+StartupInfo+4]; void *
0x140063950  lea     r8d, [rdx+64h]; Size
0x140063954  call    memset_0
0x140063959  xor     eax, eax
0x14006395b  mov     [rsp+0F8h+StartupInfo.cb], 68h ; 'h'
0x140063963  mov     qword ptr [rsp+0F8h+ProcessInformation.dwProcessId], rax
0x140063968  lea     rcx, [rsp+0F8h+arg_10]
0x140063970  mov     [rsp+0F8h+arg_10], rax
0x140063978  xorps   xmm0, xmm0
0x14006397b  mov     rax, rbx
0x14006397e  movups  xmmword ptr [rsp+0F8h+ProcessInformation.hProcess], xmm0
0x140063983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063988  test    eax, eax
0x14006398a  jz      loc_140063A8F
0x140063990  lea     rax, [rsp+0F8h+ProcessInformation]
0x140063995  xor     r9d, r9d; lpThreadAttributes
0x140063998  mov     [rsp+0F8h+lpProcessInformation], rax; lpProcessInformation
0x14006399d  xor     r8d, r8d; lpProcessAttributes
0x1400639a0  lea     rax, [rsp+0F8h+StartupInfo]
0x1400639a5  mov     rdx, rdi; lpCommandLine
0x1400639a8  mov     [rsp+0F8h+lpStartupInfo], rax; lpStartupInfo
0x1400639ad  mov     rcx, r14; lpApplicationName
0x1400639b0  mov     [rsp+0F8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1400639b9  mov     [rsp+0F8h+lpEnvironment], 0; lpEnvironment
0x1400639c2  mov     [rsp+0F8h+dwCreationFlags], 10h; dwCreationFlags
0x1400639ca  mov     [rsp+0F8h+bInheritHandles], 1; bInheritHandles
0x1400639d2  call    cs:__imp_CreateProcessW
0x1400639d8  lea     rdi, WPP_GLOBAL_Control
0x1400639df  test    eax, eax
0x1400639e1  jnz     short loc_140063A3B
0x1400639e3  call    cs:__imp_GetLastError
0x1400639e9  mov     ebx, eax
0x1400639eb  test    eax, eax
0x1400639ed  jle     short loc_1400639F8
0x1400639ef  movzx   ebx, ax
0x1400639f2  or      ebx, 80070000h
0x1400639f8  mov     rax, cs:WPP_GLOBAL_Control
0x1400639ff  cmp     rax, rdi
0x140063a02  jz      short loc_140063A53
0x140063a04  test    byte ptr [rax+1Ch], 1
0x140063a08  jz      short loc_140063A53
0x140063a0a  cmp     byte ptr [rax+19h], 2
0x140063a0e  jb      short loc_140063A53
0x140063a10  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063a15  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a1c  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140063a23  mov     edx, 0Fh
0x140063a28  mov     qword ptr [rsp+0F8h+bInheritHandles], r14
0x140063a2d  mov     r9d, eax
0x140063a30  mov     rcx, [rcx+10h]
0x140063a34  call    WPP_SF_DS
0x140063a39  jmp     short loc_140063A53
0x140063a3b  mov     rcx, [rsp+0F8h+ProcessInformation.hProcess]; hObject
0x140063a40  xor     ebx, ebx
0x140063a42  call    cs:__imp_CloseHandle
0x140063a48  mov     rcx, [rsp+0F8h+ProcessInformation.hThread]; hObject
0x140063a4d  call    cs:__imp_CloseHandle
0x140063a53  mov     rcx, [rsp+0F8h+arg_10]
0x140063a5b  mov     rax, rbp
0x140063a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063a63  test    eax, eax
0x140063a65  jnz     loc_140063B21
0x140063a6b  mov     rax, cs:WPP_GLOBAL_Control
0x140063a72  cmp     rax, rdi
0x140063a75  jz      short loc_140063AD2
0x140063a77  test    byte ptr [rax+1Ch], 1
0x140063a7b  jz      short loc_140063AD2
0x140063a7d  cmp     byte ptr [rax+19h], 2
0x140063a81  jb      short loc_140063AD2
0x140063a83  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063a88  mov     edx, 10h
0x140063a8d  jmp     short loc_140063AB8
0x140063a8f  mov     rax, cs:WPP_GLOBAL_Control
0x140063a96  lea     rdi, WPP_GLOBAL_Control
0x140063a9d  cmp     rax, rdi
0x140063aa0  jz      short loc_140063AD2
0x140063aa2  test    byte ptr [rax+1Ch], 1
0x140063aa6  jz      short loc_140063AD2
0x140063aa8  cmp     byte ptr [rax+19h], 2
0x140063aac  jb      short loc_140063AD2
0x140063aae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063ab3  mov     edx, 11h
0x140063ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x140063abf  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140063ac6  mov     r9d, eax
0x140063ac9  mov     rcx, [rcx+10h]
0x140063acd  call    WPP_SF_d
0x140063ad2  mov     ebx, 80004005h
0x140063ad7  jmp     short loc_140063B21
0x140063ad9  mov     ebx, 80004005h
0x140063ade  mov     rax, cs:WPP_GLOBAL_Control
0x140063ae5  lea     rdi, WPP_GLOBAL_Control
0x140063aec  cmp     rax, rdi
0x140063aef  jz      short loc_140063B21
0x140063af1  test    byte ptr [rax+1Ch], 1
0x140063af5  jz      short loc_140063B21
0x140063af7  cmp     byte ptr [rax+19h], 2
0x140063afb  jb      short loc_140063B21
0x140063afd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140063b02  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b09  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140063b10  mov     edx, 0Eh
0x140063b15  mov     r9d, eax
0x140063b18  mov     rcx, [rcx+10h]
0x140063b1c  call    WPP_SF_d
0x140063b21  mov     rcx, rsi; hLibModule
0x140063b24  call    cs:__imp_FreeLibrary
0x140063b2a  lea     r11, [rsp+0F8h+var_18]
0x140063b32  mov     eax, ebx
0x140063b34  mov     rbx, [r11+20h]
0x140063b38  mov     rbp, [r11+28h]
0x140063b3c  mov     rsp, r11
0x140063b3f  pop     r14
0x140063b41  pop     rdi
0x140063b42  pop     rsi
0x140063b43  retn
```
