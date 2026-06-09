# CClipReliableClipFunctions::Initialize(void)

- ea: `0x140058920`
- end: `0x140058af3`
- name: `?Initialize@CClipReliableClipFunctions@@MEAAJXZ`
- size: `467`
- prototype: `__int64 __fastcall(CClipReliableClipFunctions *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x14005850c`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140058920`
- `0x140059050`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005899c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140058a05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140058a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005899c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140058a05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140058a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400589ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400589ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058a7a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140058934`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140058934`

## string_xrefs

- `0x14005892d`: `user32.dll`
- `0x1400589fe`: `RemoveClipboardFormatListener`
- `0x140058a64`: `GetUpdatedClipboardFormats`

## pseudocode

```c
__int64 __fastcall CClipReliableClipFunctions::Initialize(CClipReliableClipFunctions *this)
{
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  FARPROC ProcAddress; // rax
  signed int v8; // eax
  FARPROC v9; // rax
  signed int v10; // eax
  FARPROC v11; // rax
  signed int v12; // eax

  LibraryW = LoadLibraryW(L"user32.dll");
  *((_QWORD *)this + 8) = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 32;
    goto LABEL_29;
  }
  ProcAddress = GetProcAddress(LibraryW, "AddClipboardFormatListener");
  *((_QWORD *)this + 5) = ProcAddress;
  if ( !ProcAddress )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_30;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 33;
    goto LABEL_29;
  }
  v9 = GetProcAddress(*((HMODULE *)this + 8), "RemoveClipboardFormatListener");
  *((_QWORD *)this + 6) = v9;
  if ( !v9 )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_30;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 34;
    goto LABEL_29;
  }
  v11 = GetProcAddress(*((HMODULE *)this + 8), "GetUpdatedClipboardFormats");
  *((_QWORD *)this + 7) = v11;
  if ( v11 )
    return 0;
  v12 = GetLastError();
  v4 = v12;
  if ( v12 > 0 )
    v4 = (unsigned __int16)v12 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 35;
LABEL_29:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_675448f9cfd532c3e00fa9edf1015f2e_Traceguids,
      CurrentThreadActivityIdPrefix,
      v4);
  }
LABEL_30:
  if ( v4 < 0 )
    CClipReliableClipFunctions::Terminate(this);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140058920  mov     [rsp+arg_0], rbx
0x140058925  push    rdi
0x140058926  sub     rsp, 30h
0x14005892a  mov     rdi, rcx
0x14005892d  lea     rcx, aUser32Dll_0; "user32.dll"
0x140058934  call    cs:__imp_LoadLibraryW
0x14005893a  mov     [rdi+40h], rax
0x14005893e  test    rax, rax
0x140058941  jnz     short loc_140058992
0x140058943  call    cs:__imp_GetLastError
0x140058949  mov     ebx, eax
0x14005894b  test    eax, eax
0x14005894d  jle     short loc_140058958
0x14005894f  movzx   ebx, ax
0x140058952  or      ebx, 80070000h
0x140058958  mov     rcx, cs:WPP_GLOBAL_Control
0x14005895f  lea     rax, WPP_GLOBAL_Control
0x140058966  cmp     rcx, rax
0x140058969  jz      loc_140058AD6
0x14005896f  test    byte ptr [rcx+1Ch], 1
0x140058973  jz      loc_140058AD6
0x140058979  cmp     byte ptr [rcx+19h], 2
0x14005897d  jb      loc_140058AD6
0x140058983  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058988  mov     edx, 20h ; ' '
0x14005898d  jmp     loc_140058AB8
0x140058992  lea     rdx, aAddclipboardfo; "AddClipboardFormatListener"
0x140058999  mov     rcx, rax; hModule
0x14005899c  call    cs:__imp_GetProcAddress
0x1400589a2  mov     [rdi+28h], rax
0x1400589a6  test    rax, rax
0x1400589a9  jnz     short loc_1400589FA
0x1400589ab  call    cs:__imp_GetLastError
0x1400589b1  mov     ebx, eax
0x1400589b3  test    eax, eax
0x1400589b5  jle     short loc_1400589C0
0x1400589b7  movzx   ebx, ax
0x1400589ba  or      ebx, 80070000h
0x1400589c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400589c7  lea     rax, WPP_GLOBAL_Control
0x1400589ce  cmp     rcx, rax
0x1400589d1  jz      loc_140058AD6
0x1400589d7  test    byte ptr [rcx+1Ch], 1
0x1400589db  jz      loc_140058AD6
0x1400589e1  cmp     byte ptr [rcx+19h], 3
0x1400589e5  jb      loc_140058AD6
0x1400589eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400589f0  mov     edx, 21h ; '!'
0x1400589f5  jmp     loc_140058AB8
0x1400589fa  mov     rcx, [rdi+40h]; hModule
0x1400589fe  lea     rdx, aRemoveclipboar; "RemoveClipboardFormatListener"
0x140058a05  call    cs:__imp_GetProcAddress
0x140058a0b  mov     [rdi+30h], rax
0x140058a0f  test    rax, rax
0x140058a12  jnz     short loc_140058A60
0x140058a14  call    cs:__imp_GetLastError
0x140058a1a  mov     ebx, eax
0x140058a1c  test    eax, eax
0x140058a1e  jle     short loc_140058A29
0x140058a20  movzx   ebx, ax
0x140058a23  or      ebx, 80070000h
0x140058a29  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a30  lea     rax, WPP_GLOBAL_Control
0x140058a37  cmp     rcx, rax
0x140058a3a  jz      loc_140058AD6
0x140058a40  test    byte ptr [rcx+1Ch], 1
0x140058a44  jz      loc_140058AD6
0x140058a4a  cmp     byte ptr [rcx+19h], 3
0x140058a4e  jb      loc_140058AD6
0x140058a54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058a59  mov     edx, 22h ; '"'
0x140058a5e  jmp     short loc_140058AB8
0x140058a60  mov     rcx, [rdi+40h]; hModule
0x140058a64  lea     rdx, aGetupdatedclip; "GetUpdatedClipboardFormats"
0x140058a6b  call    cs:__imp_GetProcAddress
0x140058a71  mov     [rdi+38h], rax
0x140058a75  test    rax, rax
0x140058a78  jnz     short loc_140058AE4
0x140058a7a  call    cs:__imp_GetLastError
0x140058a80  mov     ebx, eax
0x140058a82  test    eax, eax
0x140058a84  jle     short loc_140058A8F
0x140058a86  movzx   ebx, ax
0x140058a89  or      ebx, 80070000h
0x140058a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a96  lea     rax, WPP_GLOBAL_Control
0x140058a9d  cmp     rcx, rax
0x140058aa0  jz      short loc_140058AD6
0x140058aa2  test    byte ptr [rcx+1Ch], 1
0x140058aa6  jz      short loc_140058AD6
0x140058aa8  cmp     byte ptr [rcx+19h], 3
0x140058aac  jb      short loc_140058AD6
0x140058aae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058ab3  mov     edx, 23h ; '#'
0x140058ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x140058abf  lea     r8, WPP_675448f9cfd532c3e00fa9edf1015f2e_Traceguids
0x140058ac6  mov     r9d, eax
0x140058ac9  mov     [rsp+38h+var_18], ebx
0x140058acd  mov     rcx, [rcx+10h]
0x140058ad1  call    WPP_SF_Dd
0x140058ad6  test    ebx, ebx
0x140058ad8  jns     short loc_140058AE6
0x140058ada  mov     rcx, rdi; this
0x140058add  call    ?Terminate@CClipReliableClipFunctions@@MEAAJXZ; CClipReliableClipFunctions::Terminate(void)
0x140058ae2  jmp     short loc_140058AE6
0x140058ae4  xor     ebx, ebx
0x140058ae6  mov     eax, ebx
0x140058ae8  mov     rbx, [rsp+38h+arg_0]
0x140058aed  add     rsp, 30h
0x140058af1  pop     rdi
0x140058af2  retn
```
