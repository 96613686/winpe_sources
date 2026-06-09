# CFveApi::GetFveVolumeHandleForPartition(ushort const *,void * *)

- ea: `0x1800ad860`
- end: `0x1800ad9f3`
- name: `?GetFveVolumeHandleForPartition@CFveApi@@CAJPEBGPEAPEAX@Z`
- size: `403`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800ad3f4`

## callees

- `0x1800070c0`
- `0x180007f80`
- `0x1800090c0`
- `0x1800ad860`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad8eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad8eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ad9bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ad9bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8fc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800ad8a9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800ad8a9`

## string_xrefs

- `0x1800ad899`: `FveEnableTask.dll`

## pseudocode

```c
__int64 __fastcall CFveApi::GetFveVolumeHandleForPartition(const unsigned __int16 *a1, void **a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  signed int v5; // eax
  signed int v6; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v12[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v12, 0, 0x20Au);
  v11 = -1;
  LibraryW = LoadLibraryW(L"FveEnableTask.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "FveUtilitiesGetVolumeName");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(const wchar_t *, unsigned __int16 *, __int64))ProcAddress)(L"MAINOS", v12, 261);
      if ( !v6 )
        goto LABEL_12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids,
          (unsigned int)v6);
      if ( v6 >= 0 )
      {
LABEL_12:
        v6 = FveOpenVolumeExW(v12, 0, (__int64)&v11);
        if ( v6 < 0 )
        {
          v9 = v11;
        }
        else
        {
          v9 = -1;
          *a2 = (void *)v11;
        }
        if ( v9 != -1 )
          FveCloseVolume(v9);
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v4);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ad860  mov     [rsp+arg_0], rbx
0x1800ad865  mov     [rsp+arg_10], rsi
0x1800ad86a  push    rdi
0x1800ad86b  sub     rsp, 260h
0x1800ad872  mov     rax, cs:__security_cookie
0x1800ad879  xor     rax, rsp
0x1800ad87c  mov     [rsp+268h+var_18], rax
0x1800ad884  mov     rsi, rdx
0x1800ad887  lea     rcx, [rsp+268h+var_228]; void *
0x1800ad88c  xor     edx, edx; Val
0x1800ad88e  mov     r8d, 20Ah; Size
0x1800ad894  call    memset_0
0x1800ad899  lea     rcx, aFveenabletaskD; "FveEnableTask.dll"
0x1800ad8a0  mov     [rsp+268h+var_238], 0FFFFFFFFFFFFFFFFh
0x1800ad8a9  call    cs:__imp_LoadLibraryW
0x1800ad8b0  nop     dword ptr [rax+rax+00h]
0x1800ad8b5  mov     rdi, rax
0x1800ad8b8  test    rax, rax
0x1800ad8bb  jnz     short loc_1800AD8E1
0x1800ad8bd  call    cs:__imp_GetLastError
0x1800ad8c4  nop     dword ptr [rax+rax+00h]
0x1800ad8c9  mov     ebx, eax
0x1800ad8cb  test    eax, eax
0x1800ad8cd  jle     loc_1800AD9CB
0x1800ad8d3  movzx   ebx, ax
0x1800ad8d6  or      ebx, 80070000h
0x1800ad8dc  jmp     loc_1800AD9CB
0x1800ad8e1  lea     rdx, aFveutilitiesge; "FveUtilitiesGetVolumeName"
0x1800ad8e8  mov     rcx, rdi; hModule
0x1800ad8eb  call    cs:__imp_GetProcAddress
0x1800ad8f2  nop     dword ptr [rax+rax+00h]
0x1800ad8f7  test    rax, rax
0x1800ad8fa  jnz     short loc_1800AD920
0x1800ad8fc  call    cs:__imp_GetLastError
0x1800ad903  nop     dword ptr [rax+rax+00h]
0x1800ad908  mov     ebx, eax
0x1800ad90a  test    eax, eax
0x1800ad90c  jle     loc_1800AD9BC
0x1800ad912  movzx   ebx, ax
0x1800ad915  or      ebx, 80070000h
0x1800ad91b  jmp     loc_1800AD9BC
0x1800ad920  mov     r8d, 105h
0x1800ad926  lea     rdx, [rsp+268h+var_228]
0x1800ad92b  lea     rcx, aMainos; "MAINOS"
0x1800ad932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad937  mov     ebx, eax
0x1800ad939  test    eax, eax
0x1800ad93b  jz      short loc_1800AD972
0x1800ad93d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad944  lea     rax, WPP_GLOBAL_Control
0x1800ad94b  cmp     rcx, rax
0x1800ad94e  jz      short loc_1800AD96E
0x1800ad950  test    byte ptr [rcx+1Ch], 40h
0x1800ad954  jz      short loc_1800AD96E
0x1800ad956  mov     rcx, [rcx+10h]
0x1800ad95a  lea     r8, WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids
0x1800ad961  mov     edx, 12h
0x1800ad966  mov     r9d, ebx
0x1800ad969  call    WPP_SF_d
0x1800ad96e  test    ebx, ebx
0x1800ad970  js      short loc_1800AD9BC
0x1800ad972  or      r9d, 0FFFFFFFFh
0x1800ad976  lea     rax, [rsp+268h+var_238]
0x1800ad97b  mov     [rsp+268h+var_240], rax; __int64
0x1800ad980  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800ad985  xor     edx, edx
0x1800ad987  mov     [rsp+268h+var_248], 0; unsigned int
0x1800ad98f  lea     r8d, [r9+2]
0x1800ad993  call    FveOpenVolumeExW
0x1800ad998  mov     ebx, eax
0x1800ad99a  test    eax, eax
0x1800ad99c  js      short loc_1800AD9AC
0x1800ad99e  mov     rax, [rsp+268h+var_238]
0x1800ad9a3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ad9a7  mov     [rsi], rax
0x1800ad9aa  jmp     short loc_1800AD9B1
0x1800ad9ac  mov     rcx, [rsp+268h+var_238]
0x1800ad9b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ad9b5  jz      short loc_1800AD9BC
0x1800ad9b7  call    FveCloseVolume
0x1800ad9bc  mov     rcx, rdi; hLibModule
0x1800ad9bf  call    cs:__imp_FreeLibrary
0x1800ad9c6  nop     dword ptr [rax+rax+00h]
0x1800ad9cb  mov     eax, ebx
0x1800ad9cd  mov     rcx, [rsp+268h+var_18]
0x1800ad9d5  xor     rcx, rsp; StackCookie
0x1800ad9d8  call    __security_check_cookie
0x1800ad9dd  lea     r11, [rsp+268h+var_8]
0x1800ad9e5  mov     rbx, [r11+10h]
0x1800ad9e9  mov     rsi, [r11+20h]
0x1800ad9ed  mov     rsp, r11
0x1800ad9f0  pop     rdi
0x1800ad9f1  retn
```
