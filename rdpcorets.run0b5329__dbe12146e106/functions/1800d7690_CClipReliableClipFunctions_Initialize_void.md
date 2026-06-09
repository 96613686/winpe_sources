# CClipReliableClipFunctions::Initialize(void)

- ea: `0x1800d7690`
- end: `0x1800d7863`
- name: `?Initialize@CClipReliableClipFunctions@@MEAAJXZ`
- size: `467`
- prototype: `__int64 __fastcall(CClipReliableClipFunctions *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800d727c`

## callees

- `0x1800091a8`
- `0x180032f60`
- `0x1800d7690`
- `0x1800d7d40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d770c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7775`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d77db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d770c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7775`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d77db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d76b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d771b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d77ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d76b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d771b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d77ea`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d76a4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d76a4`

## string_xrefs

- `0x1800d769d`: `user32.dll`
- `0x1800d776e`: `RemoveClipboardFormatListener`
- `0x1800d77d4`: `GetUpdatedClipboardFormats`

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
0x1800d7690  mov     [rsp+arg_0], rbx
0x1800d7695  push    rdi
0x1800d7696  sub     rsp, 30h
0x1800d769a  mov     rdi, rcx
0x1800d769d  lea     rcx, aUser32Dll_0; "user32.dll"
0x1800d76a4  call    cs:__imp_LoadLibraryW
0x1800d76aa  mov     [rdi+40h], rax
0x1800d76ae  test    rax, rax
0x1800d76b1  jnz     short loc_1800D7702
0x1800d76b3  call    cs:__imp_GetLastError
0x1800d76b9  mov     ebx, eax
0x1800d76bb  test    eax, eax
0x1800d76bd  jle     short loc_1800D76C8
0x1800d76bf  movzx   ebx, ax
0x1800d76c2  or      ebx, 80070000h
0x1800d76c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d76cf  lea     rax, WPP_GLOBAL_Control
0x1800d76d6  cmp     rcx, rax
0x1800d76d9  jz      loc_1800D7846
0x1800d76df  test    byte ptr [rcx+1Ch], 1
0x1800d76e3  jz      loc_1800D7846
0x1800d76e9  cmp     byte ptr [rcx+19h], 2
0x1800d76ed  jb      loc_1800D7846
0x1800d76f3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d76f8  mov     edx, 20h ; ' '
0x1800d76fd  jmp     loc_1800D7828
0x1800d7702  lea     rdx, aAddclipboardfo; "AddClipboardFormatListener"
0x1800d7709  mov     rcx, rax; hModule
0x1800d770c  call    cs:__imp_GetProcAddress
0x1800d7712  mov     [rdi+28h], rax
0x1800d7716  test    rax, rax
0x1800d7719  jnz     short loc_1800D776A
0x1800d771b  call    cs:__imp_GetLastError
0x1800d7721  mov     ebx, eax
0x1800d7723  test    eax, eax
0x1800d7725  jle     short loc_1800D7730
0x1800d7727  movzx   ebx, ax
0x1800d772a  or      ebx, 80070000h
0x1800d7730  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7737  lea     rax, WPP_GLOBAL_Control
0x1800d773e  cmp     rcx, rax
0x1800d7741  jz      loc_1800D7846
0x1800d7747  test    byte ptr [rcx+1Ch], 1
0x1800d774b  jz      loc_1800D7846
0x1800d7751  cmp     byte ptr [rcx+19h], 3
0x1800d7755  jb      loc_1800D7846
0x1800d775b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d7760  mov     edx, 21h ; '!'
0x1800d7765  jmp     loc_1800D7828
0x1800d776a  mov     rcx, [rdi+40h]; hModule
0x1800d776e  lea     rdx, aRemoveclipboar; "RemoveClipboardFormatListener"
0x1800d7775  call    cs:__imp_GetProcAddress
0x1800d777b  mov     [rdi+30h], rax
0x1800d777f  test    rax, rax
0x1800d7782  jnz     short loc_1800D77D0
0x1800d7784  call    cs:__imp_GetLastError
0x1800d778a  mov     ebx, eax
0x1800d778c  test    eax, eax
0x1800d778e  jle     short loc_1800D7799
0x1800d7790  movzx   ebx, ax
0x1800d7793  or      ebx, 80070000h
0x1800d7799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d77a0  lea     rax, WPP_GLOBAL_Control
0x1800d77a7  cmp     rcx, rax
0x1800d77aa  jz      loc_1800D7846
0x1800d77b0  test    byte ptr [rcx+1Ch], 1
0x1800d77b4  jz      loc_1800D7846
0x1800d77ba  cmp     byte ptr [rcx+19h], 3
0x1800d77be  jb      loc_1800D7846
0x1800d77c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d77c9  mov     edx, 22h ; '"'
0x1800d77ce  jmp     short loc_1800D7828
0x1800d77d0  mov     rcx, [rdi+40h]; hModule
0x1800d77d4  lea     rdx, aGetupdatedclip; "GetUpdatedClipboardFormats"
0x1800d77db  call    cs:__imp_GetProcAddress
0x1800d77e1  mov     [rdi+38h], rax
0x1800d77e5  test    rax, rax
0x1800d77e8  jnz     short loc_1800D7854
0x1800d77ea  call    cs:__imp_GetLastError
0x1800d77f0  mov     ebx, eax
0x1800d77f2  test    eax, eax
0x1800d77f4  jle     short loc_1800D77FF
0x1800d77f6  movzx   ebx, ax
0x1800d77f9  or      ebx, 80070000h
0x1800d77ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7806  lea     rax, WPP_GLOBAL_Control
0x1800d780d  cmp     rcx, rax
0x1800d7810  jz      short loc_1800D7846
0x1800d7812  test    byte ptr [rcx+1Ch], 1
0x1800d7816  jz      short loc_1800D7846
0x1800d7818  cmp     byte ptr [rcx+19h], 3
0x1800d781c  jb      short loc_1800D7846
0x1800d781e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d7823  mov     edx, 23h ; '#'
0x1800d7828  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d782f  lea     r8, WPP_675448f9cfd532c3e00fa9edf1015f2e_Traceguids
0x1800d7836  mov     r9d, eax
0x1800d7839  mov     [rsp+38h+var_18], ebx
0x1800d783d  mov     rcx, [rcx+10h]
0x1800d7841  call    WPP_SF_Dd
0x1800d7846  test    ebx, ebx
0x1800d7848  jns     short loc_1800D7856
0x1800d784a  mov     rcx, rdi; this
0x1800d784d  call    ?Terminate@CClipReliableClipFunctions@@MEAAJXZ; CClipReliableClipFunctions::Terminate(void)
0x1800d7852  jmp     short loc_1800D7856
0x1800d7854  xor     ebx, ebx
0x1800d7856  mov     eax, ebx
0x1800d7858  mov     rbx, [rsp+38h+arg_0]
0x1800d785d  add     rsp, 30h
0x1800d7861  pop     rdi
0x1800d7862  retn
```
