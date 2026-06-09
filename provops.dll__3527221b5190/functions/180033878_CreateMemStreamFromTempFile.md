# CreateMemStreamFromTempFile

- ea: `0x180033878`
- end: `0x1800339e9`
- name: `CreateMemStreamFromTempFile`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180033520`

## callees

- `0x180003e6c`
- `0x18001b388`
- `0x180020710`
- `0x180033878`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003396f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003396f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003397e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003397e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800338dd`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800338dd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033941`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033941`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800338af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800338af`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180033959`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180033959`

## string_xrefs

- `0x18003398f`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800339a1`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800339b3`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800339c5`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800339d7`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
IStream *__fastcall CreateMemStreamFromTempFile(const WCHAR *a1)
{
  HANDLE FileW; // rax
  const char *v2; // r9
  void *v3; // rbx
  const char *v4; // r9
  DWORD LowPart; // esi
  void *v6; // rdi
  const char *v7; // r9
  IStream *v8; // rsi
  const char *v9; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp+8h] BYREF
  HANDLE v14; // [rsp+68h] [rbp+10h]
  void *v15; // [rsp+70h] [rbp+18h]

  if ( *((_QWORD *)a1 + 3) >= 8u )
    a1 = *(const WCHAR **)a1;
  FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x4000000u, 0);
  v3 = FileW;
  v14 = FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v2);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v4);
  if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      FileSize.QuadPart > 0xFFFFFFFFuLL ? (const char *)0x80070216LL : 0,
      dwCreationDisposition);
  LowPart = FileSize.LowPart;
  v6 = operator new[](FileSize.LowPart);
  v15 = v6;
  if ( !ReadFile(v3, v6, LowPart, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v7);
  v8 = SHCreateMemStream((const BYTE *)v6, LowPart);
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v9);
  operator delete[](v6);
  if ( v3 )
    CloseHandle(v3);
  return v8;
}

```

## disassembly

```asm
0x180033878  push    rbx
0x18003387a  push    rsi
0x18003387b  push    rdi
0x18003387c  sub     rsp, 40h
0x180033880  cmp     qword ptr [rcx+18h], 8
0x180033885  jb      short loc_18003388A
0x180033887  mov     rcx, [rcx]; lpFileName
0x18003388a  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180033893  mov     [rsp+58h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18003389b  mov     [rsp+58h+dwCreationDisposition], 3; int
0x1800338a3  xor     r9d, r9d; lpSecurityAttributes
0x1800338a6  mov     edx, 80000000h; dwDesiredAccess
0x1800338ab  lea     r8d, [r9+5]; dwShareMode
0x1800338af  call    cs:__imp_CreateFileW
0x1800338b5  mov     rbx, rax
0x1800338b8  mov     [rsp+58h+arg_8], rax
0x1800338bd  mov     rcx, [rsp+58h]; this
0x1800338c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800338c6  jz      loc_1800339A1
0x1800338cc  mov     qword ptr [rsp+58h+FileSize], 0
0x1800338d5  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x1800338da  mov     rcx, rax; hFile
0x1800338dd  call    cs:__imp_GetFileSizeEx
0x1800338e3  mov     rcx, [rsp+58h]; this
0x1800338e8  test    eax, eax
0x1800338ea  jz      loc_1800339B3
0x1800338f0  mov     rax, qword ptr [rsp+58h+FileSize]
0x1800338f5  mov     edx, 0FFFFFFFFh
0x1800338fa  mov     esi, edx
0x1800338fc  cmp     rax, rdx
0x1800338ff  cmovbe  esi, eax
0x180033902  cmp     rdx, rax
0x180033905  sbb     r9d, r9d
0x180033908  and     r9d, 80070216h; char *
0x18003390f  mov     rcx, [rsp+58h]; this
0x180033914  cmp     rax, rdx
0x180033917  ja      loc_1800339C5
0x18003391d  mov     ecx, esi; unsigned __int64
0x18003391f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180033924  mov     rdi, rax
0x180033927  mov     [rsp+58h+arg_10], rax
0x18003392c  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x180033935  xor     r9d, r9d; lpNumberOfBytesRead
0x180033938  mov     r8d, esi; nNumberOfBytesToRead
0x18003393b  mov     rdx, rax; lpBuffer
0x18003393e  mov     rcx, rbx; hFile
0x180033941  call    cs:__imp_ReadFile
0x180033947  mov     rcx, [rsp+58h]; this
0x18003394c  test    eax, eax
0x18003394e  jz      loc_1800339D7
0x180033954  mov     edx, esi; cbInit
0x180033956  mov     rcx, rdi; pInit
0x180033959  call    cs:__imp_SHCreateMemStream
0x18003395f  mov     rsi, rax
0x180033962  mov     rcx, [rsp+58h]; this
0x180033967  test    rax, rax
0x18003396a  jz      short loc_18003398F
0x18003396c  mov     rcx, rdi
0x18003396f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033975  nop
0x180033976  test    rbx, rbx
0x180033979  jz      short loc_180033984
0x18003397b  mov     rcx, rbx; hObject
0x18003397e  call    cs:__imp_CloseHandle
0x180033984  mov     rax, rsi
0x180033987  add     rsp, 40h
0x18003398b  pop     rdi
0x18003398c  pop     rsi
0x18003398d  pop     rbx
0x18003398e  retn
0x18003398f  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x180033996  mov     edx, 56h ; 'V'; void *
0x18003399b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800339a1  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800339a8  mov     edx, 4Bh ; 'K'; void *
0x1800339ad  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800339b3  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800339ba  mov     edx, 4Eh ; 'N'; void *
0x1800339bf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800339c5  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800339cc  mov     edx, 50h ; 'P'; void *
0x1800339d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800339d7  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800339de  mov     edx, 53h ; 'S'; void *
0x1800339e3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
