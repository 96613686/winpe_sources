# CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)

- ea: `0x1400a1a64`
- end: `0x1400a1c74`
- name: `?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400a2750`
- `0x1400a2a00`
- `0x1400a2e00`
- `0x1400a3910`
- `0x1400a3e20`
- `0x1400a40f0`
- `0x1400a4300`
- `0x1400a48c0`
- `0x1400a4b20`
- `0x1400a4ff0`
- `0x1400a51b0`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x1400a1a64`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400a1ad4`
- `KERNEL32!LoadLibraryW` at `0x1400a1ad4`
- `KERNEL32!FreeLibrary` at `0x1400a1c61`
- `KERNEL32!FreeLibrary` at `0x1400a1c61`
- `KERNEL32!GetProcAddress` at `0x1400a1b66`
- `KERNEL32!GetProcAddress` at `0x1400a1b66`
- `KERNEL32!GetLastError` at `0x1400a1b01`
- `KERNEL32!GetLastError` at `0x1400a1b3e`
- `KERNEL32!GetLastError` at `0x1400a1b90`
- `KERNEL32!GetLastError` at `0x1400a1bcd`
- `KERNEL32!GetLastError` at `0x1400a1bfb`
- `KERNEL32!GetLastError` at `0x1400a1b01`
- `KERNEL32!GetLastError` at `0x1400a1b3e`
- `KERNEL32!GetLastError` at `0x1400a1b90`
- `KERNEL32!GetLastError` at `0x1400a1bcd`
- `KERNEL32!GetLastError` at `0x1400a1bfb`

## string_xrefs

- `0x1400a1acd`: `userenv.dll`
- `0x1400a1b5c`: `GetAppContainerRegistryLocation`

## pseudocode

```c
__int64 __fastcall CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY *a1)
{
  unsigned int v2; // eax
  signed int v3; // ebx
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  signed int v9; // eax
  FARPROC ProcAddress; // rax
  signed int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  signed int v14; // eax
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  if ( a1 )
  {
    LibraryW = LoadLibraryW(L"userenv.dll");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "GetAppContainerRegistryLocation");
      if ( ProcAddress )
      {
        v3 = ((__int64 (__fastcall *)(__int64, HKEY *))ProcAddress)(983103, a1);
        if ( v3 < 0 )
        {
          LastError = GetLastError();
          if ( LastError != 122 )
          {
            v3 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                CurrentThreadActivityIdPrefix,
                v3);
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = GetLastError();
          v12 = v11;
          if ( v11 > 0 )
            v12 = (unsigned __int16)v11 | 0x80070000;
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v13, v12);
        }
        v14 = GetLastError();
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
      }
      FreeLibrary(v5);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = GetLastError();
        v7 = v6;
        if ( v6 > 0 )
          v7 = (unsigned __int16)v6 | 0x80070000;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v8, v7);
      }
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
        v2,
        (__int64)"phKey");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400a1a64  mov     [rsp+arg_0], rbx
0x1400a1a69  push    rsi
0x1400a1a6a  sub     rsp, 30h
0x1400a1a6e  mov     rbx, rcx
0x1400a1a71  test    rcx, rcx
0x1400a1a74  jnz     short loc_1400A1ACD
0x1400a1a76  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1a7d  lea     rax, WPP_GLOBAL_Control
0x1400a1a84  cmp     rcx, rax
0x1400a1a87  jz      short loc_1400A1AC3
0x1400a1a89  test    byte ptr [rcx+1Ch], 8
0x1400a1a8d  jz      short loc_1400A1AC3
0x1400a1a8f  cmp     byte ptr [rcx+19h], 2
0x1400a1a93  jb      short loc_1400A1AC3
0x1400a1a95  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1a9a  lea     rcx, aPhkey; "phKey"
0x1400a1aa1  mov     r9d, eax
0x1400a1aa4  mov     [rsp+38h+var_18], rcx
0x1400a1aa9  lea     edx, [rbx+3Ch]
0x1400a1aac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1ab3  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1aba  mov     rcx, [rcx+10h]
0x1400a1abe  call    WPP_SF_Ds
0x1400a1ac3  mov     ebx, 80004003h
0x1400a1ac8  jmp     loc_1400A1C67
0x1400a1acd  lea     rcx, aUserenvDll; "userenv.dll"
0x1400a1ad4  call    cs:__imp_LoadLibraryW
0x1400a1ada  mov     rsi, rax
0x1400a1add  test    rax, rax
0x1400a1ae0  jnz     short loc_1400A1B5C
0x1400a1ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1ae9  lea     rax, WPP_GLOBAL_Control
0x1400a1af0  cmp     rcx, rax
0x1400a1af3  jz      short loc_1400A1B3E
0x1400a1af5  test    byte ptr [rcx+1Ch], 8
0x1400a1af9  jz      short loc_1400A1B3E
0x1400a1afb  cmp     byte ptr [rcx+19h], 2
0x1400a1aff  jb      short loc_1400A1B3E
0x1400a1b01  call    cs:__imp_GetLastError
0x1400a1b07  mov     ebx, eax
0x1400a1b09  test    eax, eax
0x1400a1b0b  jle     short loc_1400A1B16
0x1400a1b0d  movzx   ebx, ax
0x1400a1b10  or      ebx, 80070000h
0x1400a1b16  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1b22  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1b29  mov     edx, 3Dh ; '='
0x1400a1b2e  mov     dword ptr [rsp+38h+var_18], ebx
0x1400a1b32  mov     r9d, eax
0x1400a1b35  mov     rcx, [rcx+10h]
0x1400a1b39  call    WPP_SF_Dd
0x1400a1b3e  call    cs:__imp_GetLastError
0x1400a1b44  mov     ebx, eax
0x1400a1b46  test    eax, eax
0x1400a1b48  jle     loc_1400A1C67
0x1400a1b4e  movzx   ebx, ax
0x1400a1b51  or      ebx, 80070000h
0x1400a1b57  jmp     loc_1400A1C67
0x1400a1b5c  lea     rdx, aGetappcontaine; "GetAppContainerRegistryLocation"
0x1400a1b63  mov     rcx, rsi; hModule
0x1400a1b66  call    cs:__imp_GetProcAddress
0x1400a1b6c  test    rax, rax
0x1400a1b6f  jnz     short loc_1400A1BE8
0x1400a1b71  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1b78  lea     rax, WPP_GLOBAL_Control
0x1400a1b7f  cmp     rcx, rax
0x1400a1b82  jz      short loc_1400A1BCD
0x1400a1b84  test    byte ptr [rcx+1Ch], 8
0x1400a1b88  jz      short loc_1400A1BCD
0x1400a1b8a  cmp     byte ptr [rcx+19h], 2
0x1400a1b8e  jb      short loc_1400A1BCD
0x1400a1b90  call    cs:__imp_GetLastError
0x1400a1b96  mov     ebx, eax
0x1400a1b98  test    eax, eax
0x1400a1b9a  jle     short loc_1400A1BA5
0x1400a1b9c  movzx   ebx, ax
0x1400a1b9f  or      ebx, 80070000h
0x1400a1ba5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1baa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1bb1  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1bb8  mov     edx, 3Eh ; '>'
0x1400a1bbd  mov     dword ptr [rsp+38h+var_18], ebx
0x1400a1bc1  mov     r9d, eax
0x1400a1bc4  mov     rcx, [rcx+10h]
0x1400a1bc8  call    WPP_SF_Dd
0x1400a1bcd  call    cs:__imp_GetLastError
0x1400a1bd3  mov     ebx, eax
0x1400a1bd5  test    eax, eax
0x1400a1bd7  jle     loc_1400A1C5E
0x1400a1bdd  movzx   ebx, ax
0x1400a1be0  or      ebx, 80070000h
0x1400a1be6  jmp     short loc_1400A1C5E
0x1400a1be8  mov     rdx, rbx
0x1400a1beb  mov     ecx, 0F003Fh
0x1400a1bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a1bf5  mov     ebx, eax
0x1400a1bf7  test    eax, eax
0x1400a1bf9  jns     short loc_1400A1C5E
0x1400a1bfb  call    cs:__imp_GetLastError
0x1400a1c01  cmp     eax, 7Ah ; 'z'
0x1400a1c04  jz      short loc_1400A1C5E
0x1400a1c06  test    eax, eax
0x1400a1c08  jg      short loc_1400A1C0E
0x1400a1c0a  mov     ebx, eax
0x1400a1c0c  jmp     short loc_1400A1C17
0x1400a1c0e  movzx   ebx, ax
0x1400a1c11  or      ebx, 80070000h
0x1400a1c17  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1c1e  lea     rax, WPP_GLOBAL_Control
0x1400a1c25  cmp     rcx, rax
0x1400a1c28  jz      short loc_1400A1C5E
0x1400a1c2a  test    byte ptr [rcx+1Ch], 1
0x1400a1c2e  jz      short loc_1400A1C5E
0x1400a1c30  cmp     byte ptr [rcx+19h], 2
0x1400a1c34  jb      short loc_1400A1C5E
0x1400a1c36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1c42  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1c49  mov     edx, 3Fh ; '?'
0x1400a1c4e  mov     dword ptr [rsp+38h+var_18], ebx
0x1400a1c52  mov     r9d, eax
0x1400a1c55  mov     rcx, [rcx+10h]
0x1400a1c59  call    WPP_SF_Dd
0x1400a1c5e  mov     rcx, rsi; hLibModule
0x1400a1c61  call    cs:__imp_FreeLibrary
0x1400a1c67  mov     eax, ebx
0x1400a1c69  mov     rbx, [rsp+38h+arg_0]
0x1400a1c6e  add     rsp, 30h
0x1400a1c72  pop     rsi
0x1400a1c73  retn
```
