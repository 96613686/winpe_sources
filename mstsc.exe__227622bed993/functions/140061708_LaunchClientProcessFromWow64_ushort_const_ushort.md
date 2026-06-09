# LaunchClientProcessFromWow64(ushort const *,ushort *)

- ea: `0x140061708`
- end: `0x1400619d4`
- name: `?LaunchClientProcessFromWow64@@YAJPEBGPEAG@Z`
- size: `716`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140062460`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14001e210`
- `0x140061708`
- `0x140112010`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x140061862`
- `KERNEL32!CreateProcessW` at `0x140061862`
- `KERNEL32!LoadLibraryW` at `0x14006172a`
- `KERNEL32!LoadLibraryW` at `0x14006172a`
- `KERNEL32!FreeLibrary` at `0x1400619b4`
- `KERNEL32!FreeLibrary` at `0x1400619b4`
- `KERNEL32!GetProcAddress` at `0x1400617ab`
- `KERNEL32!GetProcAddress` at `0x1400617be`
- `KERNEL32!GetProcAddress` at `0x1400617ab`
- `KERNEL32!GetProcAddress` at `0x1400617be`
- `KERNEL32!CloseHandle` at `0x1400618d2`
- `KERNEL32!CloseHandle` at `0x1400618dd`
- `KERNEL32!CloseHandle` at `0x1400618d2`
- `KERNEL32!CloseHandle` at `0x1400618dd`
- `KERNEL32!GetLastError` at `0x140061738`
- `KERNEL32!GetLastError` at `0x140061873`
- `KERNEL32!GetLastError` at `0x140061738`
- `KERNEL32!GetLastError` at `0x140061873`

## string_xrefs

- `0x140061723`: `kernel32.dll`

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
0x140061708  mov     [rsp+arg_0], rbx
0x14006170d  mov     [rsp+arg_8], rbp
0x140061712  push    rsi
0x140061713  push    rdi
0x140061714  push    r14
0x140061716  sub     rsp, 0E0h
0x14006171d  mov     r14, rcx
0x140061720  mov     rdi, rdx
0x140061723  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x14006172a  call    cs:__imp_LoadLibraryW
0x140061730  mov     rsi, rax
0x140061733  test    rax, rax
0x140061736  jnz     short loc_1400617A1
0x140061738  call    cs:__imp_GetLastError
0x14006173e  mov     ebx, eax
0x140061740  test    eax, eax
0x140061742  jle     short loc_14006174D
0x140061744  movzx   ebx, ax
0x140061747  or      ebx, 80070000h
0x14006174d  mov     rax, cs:WPP_GLOBAL_Control
0x140061754  lea     rdi, WPP_GLOBAL_Control
0x14006175b  cmp     rax, rdi
0x14006175e  jz      loc_1400619BA
0x140061764  test    byte ptr [rax+1Ch], 1
0x140061768  jz      loc_1400619BA
0x14006176e  cmp     byte ptr [rax+19h], 2
0x140061772  jb      loc_1400619BA
0x140061778  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006177d  mov     rcx, cs:WPP_GLOBAL_Control
0x140061784  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x14006178b  mov     edx, 0Dh
0x140061790  mov     r9d, eax
0x140061793  mov     rcx, [rcx+10h]
0x140061797  call    WPP_SF_d
0x14006179c  jmp     loc_1400619BA
0x1400617a1  lea     rdx, aWow64disablewo; "Wow64DisableWow64FsRedirection"
0x1400617a8  mov     rcx, rsi; hModule
0x1400617ab  call    cs:__imp_GetProcAddress
0x1400617b1  lea     rdx, aWow64revertwow; "Wow64RevertWow64FsRedirection"
0x1400617b8  mov     rcx, rsi; hModule
0x1400617bb  mov     rbx, rax
0x1400617be  call    cs:__imp_GetProcAddress
0x1400617c4  mov     rbp, rax
0x1400617c7  test    rbx, rbx
0x1400617ca  jz      loc_140061969
0x1400617d0  test    rax, rax
0x1400617d3  jz      loc_140061969
0x1400617d9  xor     edx, edx; Val
0x1400617db  lea     rcx, [rsp+0F8h+StartupInfo+4]; void *
0x1400617e0  lea     r8d, [rdx+64h]; Size
0x1400617e4  call    memset_0
0x1400617e9  xor     eax, eax
0x1400617eb  mov     [rsp+0F8h+StartupInfo.cb], 68h ; 'h'
0x1400617f3  mov     qword ptr [rsp+0F8h+ProcessInformation.dwProcessId], rax
0x1400617f8  lea     rcx, [rsp+0F8h+arg_10]
0x140061800  mov     [rsp+0F8h+arg_10], rax
0x140061808  xorps   xmm0, xmm0
0x14006180b  mov     rax, rbx
0x14006180e  movups  xmmword ptr [rsp+0F8h+ProcessInformation.hProcess], xmm0
0x140061813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140061818  test    eax, eax
0x14006181a  jz      loc_14006191F
0x140061820  lea     rax, [rsp+0F8h+ProcessInformation]
0x140061825  xor     r9d, r9d; lpThreadAttributes
0x140061828  mov     [rsp+0F8h+lpProcessInformation], rax; lpProcessInformation
0x14006182d  xor     r8d, r8d; lpProcessAttributes
0x140061830  lea     rax, [rsp+0F8h+StartupInfo]
0x140061835  mov     rdx, rdi; lpCommandLine
0x140061838  mov     [rsp+0F8h+lpStartupInfo], rax; lpStartupInfo
0x14006183d  mov     rcx, r14; lpApplicationName
0x140061840  mov     [rsp+0F8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140061849  mov     [rsp+0F8h+lpEnvironment], 0; lpEnvironment
0x140061852  mov     [rsp+0F8h+dwCreationFlags], 10h; dwCreationFlags
0x14006185a  mov     [rsp+0F8h+bInheritHandles], 1; bInheritHandles
0x140061862  call    cs:__imp_CreateProcessW
0x140061868  lea     rdi, WPP_GLOBAL_Control
0x14006186f  test    eax, eax
0x140061871  jnz     short loc_1400618CB
0x140061873  call    cs:__imp_GetLastError
0x140061879  mov     ebx, eax
0x14006187b  test    eax, eax
0x14006187d  jle     short loc_140061888
0x14006187f  movzx   ebx, ax
0x140061882  or      ebx, 80070000h
0x140061888  mov     rax, cs:WPP_GLOBAL_Control
0x14006188f  cmp     rax, rdi
0x140061892  jz      short loc_1400618E3
0x140061894  test    byte ptr [rax+1Ch], 1
0x140061898  jz      short loc_1400618E3
0x14006189a  cmp     byte ptr [rax+19h], 2
0x14006189e  jb      short loc_1400618E3
0x1400618a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400618a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400618ac  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400618b3  mov     edx, 0Fh
0x1400618b8  mov     qword ptr [rsp+0F8h+bInheritHandles], r14
0x1400618bd  mov     r9d, eax
0x1400618c0  mov     rcx, [rcx+10h]
0x1400618c4  call    WPP_SF_DS
0x1400618c9  jmp     short loc_1400618E3
0x1400618cb  mov     rcx, [rsp+0F8h+ProcessInformation.hProcess]; hObject
0x1400618d0  xor     ebx, ebx
0x1400618d2  call    cs:__imp_CloseHandle
0x1400618d8  mov     rcx, [rsp+0F8h+ProcessInformation.hThread]; hObject
0x1400618dd  call    cs:__imp_CloseHandle
0x1400618e3  mov     rcx, [rsp+0F8h+arg_10]
0x1400618eb  mov     rax, rbp
0x1400618ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400618f3  test    eax, eax
0x1400618f5  jnz     loc_1400619B1
0x1400618fb  mov     rax, cs:WPP_GLOBAL_Control
0x140061902  cmp     rax, rdi
0x140061905  jz      short loc_140061962
0x140061907  test    byte ptr [rax+1Ch], 1
0x14006190b  jz      short loc_140061962
0x14006190d  cmp     byte ptr [rax+19h], 2
0x140061911  jb      short loc_140061962
0x140061913  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140061918  mov     edx, 10h
0x14006191d  jmp     short loc_140061948
0x14006191f  mov     rax, cs:WPP_GLOBAL_Control
0x140061926  lea     rdi, WPP_GLOBAL_Control
0x14006192d  cmp     rax, rdi
0x140061930  jz      short loc_140061962
0x140061932  test    byte ptr [rax+1Ch], 1
0x140061936  jz      short loc_140061962
0x140061938  cmp     byte ptr [rax+19h], 2
0x14006193c  jb      short loc_140061962
0x14006193e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140061943  mov     edx, 11h
0x140061948  mov     rcx, cs:WPP_GLOBAL_Control
0x14006194f  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140061956  mov     r9d, eax
0x140061959  mov     rcx, [rcx+10h]
0x14006195d  call    WPP_SF_d
0x140061962  mov     ebx, 80004005h
0x140061967  jmp     short loc_1400619B1
0x140061969  mov     ebx, 80004005h
0x14006196e  mov     rax, cs:WPP_GLOBAL_Control
0x140061975  lea     rdi, WPP_GLOBAL_Control
0x14006197c  cmp     rax, rdi
0x14006197f  jz      short loc_1400619B1
0x140061981  test    byte ptr [rax+1Ch], 1
0x140061985  jz      short loc_1400619B1
0x140061987  cmp     byte ptr [rax+19h], 2
0x14006198b  jb      short loc_1400619B1
0x14006198d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140061992  mov     rcx, cs:WPP_GLOBAL_Control
0x140061999  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400619a0  mov     edx, 0Eh
0x1400619a5  mov     r9d, eax
0x1400619a8  mov     rcx, [rcx+10h]
0x1400619ac  call    WPP_SF_d
0x1400619b1  mov     rcx, rsi; hLibModule
0x1400619b4  call    cs:__imp_FreeLibrary
0x1400619ba  lea     r11, [rsp+0F8h+var_18]
0x1400619c2  mov     eax, ebx
0x1400619c4  mov     rbx, [r11+20h]
0x1400619c8  mov     rbp, [r11+28h]
0x1400619cc  mov     rsp, r11
0x1400619cf  pop     r14
0x1400619d1  pop     rdi
0x1400619d2  pop     rsi
0x1400619d3  retn
```
