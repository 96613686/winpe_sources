# CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)

- ea: `0x14009f8f4`
- end: `0x14009fb04`
- name: `?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400a05e0`
- `0x1400a0890`
- `0x1400a0c90`
- `0x1400a17a0`
- `0x1400a1cb0`
- `0x1400a1f80`
- `0x1400a2190`
- `0x1400a2750`
- `0x1400a29b0`
- `0x1400a2e80`
- `0x1400a3040`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14009f8f4`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14009f964`
- `KERNEL32!LoadLibraryW` at `0x14009f964`
- `KERNEL32!FreeLibrary` at `0x14009faf1`
- `KERNEL32!FreeLibrary` at `0x14009faf1`
- `KERNEL32!GetProcAddress` at `0x14009f9f6`
- `KERNEL32!GetProcAddress` at `0x14009f9f6`
- `KERNEL32!GetLastError` at `0x14009f991`
- `KERNEL32!GetLastError` at `0x14009f9ce`
- `KERNEL32!GetLastError` at `0x14009fa20`
- `KERNEL32!GetLastError` at `0x14009fa5d`
- `KERNEL32!GetLastError` at `0x14009fa8b`
- `KERNEL32!GetLastError` at `0x14009f991`
- `KERNEL32!GetLastError` at `0x14009f9ce`
- `KERNEL32!GetLastError` at `0x14009fa20`
- `KERNEL32!GetLastError` at `0x14009fa5d`
- `KERNEL32!GetLastError` at `0x14009fa8b`

## string_xrefs

- `0x14009f9ec`: `GetAppContainerRegistryLocation`
- `0x14009f95d`: `userenv.dll`

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
0x14009f8f4  mov     [rsp+arg_0], rbx
0x14009f8f9  push    rsi
0x14009f8fa  sub     rsp, 30h
0x14009f8fe  mov     rbx, rcx
0x14009f901  test    rcx, rcx
0x14009f904  jnz     short loc_14009F95D
0x14009f906  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f90d  lea     rax, WPP_GLOBAL_Control
0x14009f914  cmp     rcx, rax
0x14009f917  jz      short loc_14009F953
0x14009f919  test    byte ptr [rcx+1Ch], 8
0x14009f91d  jz      short loc_14009F953
0x14009f91f  cmp     byte ptr [rcx+19h], 2
0x14009f923  jb      short loc_14009F953
0x14009f925  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009f92a  lea     rcx, aPhkey; "phKey"
0x14009f931  mov     r9d, eax
0x14009f934  mov     [rsp+38h+var_18], rcx
0x14009f939  lea     edx, [rbx+3Ch]
0x14009f93c  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f943  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009f94a  mov     rcx, [rcx+10h]
0x14009f94e  call    WPP_SF_Ds
0x14009f953  mov     ebx, 80004003h
0x14009f958  jmp     loc_14009FAF7
0x14009f95d  lea     rcx, aUserenvDll; "userenv.dll"
0x14009f964  call    cs:__imp_LoadLibraryW
0x14009f96a  mov     rsi, rax
0x14009f96d  test    rax, rax
0x14009f970  jnz     short loc_14009F9EC
0x14009f972  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f979  lea     rax, WPP_GLOBAL_Control
0x14009f980  cmp     rcx, rax
0x14009f983  jz      short loc_14009F9CE
0x14009f985  test    byte ptr [rcx+1Ch], 8
0x14009f989  jz      short loc_14009F9CE
0x14009f98b  cmp     byte ptr [rcx+19h], 2
0x14009f98f  jb      short loc_14009F9CE
0x14009f991  call    cs:__imp_GetLastError
0x14009f997  mov     ebx, eax
0x14009f999  test    eax, eax
0x14009f99b  jle     short loc_14009F9A6
0x14009f99d  movzx   ebx, ax
0x14009f9a0  or      ebx, 80070000h
0x14009f9a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009f9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f9b2  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009f9b9  mov     edx, 3Dh ; '='
0x14009f9be  mov     dword ptr [rsp+38h+var_18], ebx
0x14009f9c2  mov     r9d, eax
0x14009f9c5  mov     rcx, [rcx+10h]
0x14009f9c9  call    WPP_SF_Dd
0x14009f9ce  call    cs:__imp_GetLastError
0x14009f9d4  mov     ebx, eax
0x14009f9d6  test    eax, eax
0x14009f9d8  jle     loc_14009FAF7
0x14009f9de  movzx   ebx, ax
0x14009f9e1  or      ebx, 80070000h
0x14009f9e7  jmp     loc_14009FAF7
0x14009f9ec  lea     rdx, aGetappcontaine; "GetAppContainerRegistryLocation"
0x14009f9f3  mov     rcx, rsi; hModule
0x14009f9f6  call    cs:__imp_GetProcAddress
0x14009f9fc  test    rax, rax
0x14009f9ff  jnz     short loc_14009FA78
0x14009fa01  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fa08  lea     rax, WPP_GLOBAL_Control
0x14009fa0f  cmp     rcx, rax
0x14009fa12  jz      short loc_14009FA5D
0x14009fa14  test    byte ptr [rcx+1Ch], 8
0x14009fa18  jz      short loc_14009FA5D
0x14009fa1a  cmp     byte ptr [rcx+19h], 2
0x14009fa1e  jb      short loc_14009FA5D
0x14009fa20  call    cs:__imp_GetLastError
0x14009fa26  mov     ebx, eax
0x14009fa28  test    eax, eax
0x14009fa2a  jle     short loc_14009FA35
0x14009fa2c  movzx   ebx, ax
0x14009fa2f  or      ebx, 80070000h
0x14009fa35  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fa3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fa41  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009fa48  mov     edx, 3Eh ; '>'
0x14009fa4d  mov     dword ptr [rsp+38h+var_18], ebx
0x14009fa51  mov     r9d, eax
0x14009fa54  mov     rcx, [rcx+10h]
0x14009fa58  call    WPP_SF_Dd
0x14009fa5d  call    cs:__imp_GetLastError
0x14009fa63  mov     ebx, eax
0x14009fa65  test    eax, eax
0x14009fa67  jle     loc_14009FAEE
0x14009fa6d  movzx   ebx, ax
0x14009fa70  or      ebx, 80070000h
0x14009fa76  jmp     short loc_14009FAEE
0x14009fa78  mov     rdx, rbx
0x14009fa7b  mov     ecx, 0F003Fh
0x14009fa80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009fa85  mov     ebx, eax
0x14009fa87  test    eax, eax
0x14009fa89  jns     short loc_14009FAEE
0x14009fa8b  call    cs:__imp_GetLastError
0x14009fa91  cmp     eax, 7Ah ; 'z'
0x14009fa94  jz      short loc_14009FAEE
0x14009fa96  test    eax, eax
0x14009fa98  jg      short loc_14009FA9E
0x14009fa9a  mov     ebx, eax
0x14009fa9c  jmp     short loc_14009FAA7
0x14009fa9e  movzx   ebx, ax
0x14009faa1  or      ebx, 80070000h
0x14009faa7  mov     rcx, cs:WPP_GLOBAL_Control
0x14009faae  lea     rax, WPP_GLOBAL_Control
0x14009fab5  cmp     rcx, rax
0x14009fab8  jz      short loc_14009FAEE
0x14009faba  test    byte ptr [rcx+1Ch], 1
0x14009fabe  jz      short loc_14009FAEE
0x14009fac0  cmp     byte ptr [rcx+19h], 2
0x14009fac4  jb      short loc_14009FAEE
0x14009fac6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009facb  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fad2  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009fad9  mov     edx, 3Fh ; '?'
0x14009fade  mov     dword ptr [rsp+38h+var_18], ebx
0x14009fae2  mov     r9d, eax
0x14009fae5  mov     rcx, [rcx+10h]
0x14009fae9  call    WPP_SF_Dd
0x14009faee  mov     rcx, rsi; hLibModule
0x14009faf1  call    cs:__imp_FreeLibrary
0x14009faf7  mov     eax, ebx
0x14009faf9  mov     rbx, [rsp+38h+arg_0]
0x14009fafe  add     rsp, 30h
0x14009fb02  pop     rsi
0x14009fb03  retn
```
