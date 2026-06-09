# File::TryOpen(wchar_t const *,File::OpenMode)

- ea: `0x180123b68`
- end: `0x180123cae`
- name: `?TryOpen@File@@QEAAJPEB_WW4OpenMode@1@@Z`
- size: `326`
- prototype: `int __high(const wchar_t *, enum File::OpenMode)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18012388c`
- `0x180123ae0`
- `0x180237230`

## callees

- `0x180123b68`
- `0x180123ea0`
- `0x180123fe0`
- `0x1801644d0`
- `0x1801ecd38`
- `0x1802066a4`
- `0x18020a074`

## import_xrefs

- `kernel32!GetLastError` at `0x180123c16`
- `kernel32!GetLastError` at `0x180123c16`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180123b82`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180123bf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180123c6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180123b82`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180123bf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180123c6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123c0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123c0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180123bc9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180123bc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall File::TryOpen(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  const char *v6; // rdx
  UINT v7; // edi
  int v8; // eax
  DWORD v9; // edx
  DWORD v10; // r8d
  DWORD dwCreationDisposition; // ecx
  HANDLE FileW; // rax
  unsigned int v13; // ebx
  DWORD LastError; // esi
  struct DWrite::RefString::Data *v16; // rbx
  unsigned int v17; // esi
  HANDLE hObject; // [rsp+78h] [rbp+20h] BYREF

  v7 = SetErrorMode(0x8001u);
  v8 = a3 & 0xC;
  if ( (a3 & 0xC) == 0 )
  {
    v9 = 0x80000000;
    v10 = v8 + 7;
LABEL_3:
    dwCreationDisposition = 3;
    goto LABEL_4;
  }
  if ( v8 == 4 )
  {
    v9 = -1073741824;
    v10 = 5;
    goto LABEL_3;
  }
  if ( v8 != 8 )
  {
    FailAssert(0x4Du, v6);
    __debugbreak();
  }
  v9 = -1073741824;
  dwCreationDisposition = 2;
  v10 = 5;
LABEL_4:
  FileW = CreateFileW(a2, v9, v10, 0, dwCreationDisposition, (a3 & 2 | 0x10) << 24, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    GetDepersonalizedFilePath(&hObject, a2);
    v16 = (struct DWrite::RefString::Data *)hObject;
    LogEvent<long,EventTag,unsigned int,wchar_t const *>(g_errorTag, LastError, 1701603686, 97, (__int64)hObject + 8);
    v17 = IOException::MapFileOpenError(LastError);
    DWrite::RefString::DecrementRef(v16);
    SetErrorMode(v7);
    return v17;
  }
  else
  {
    hObject = FileW;
    v13 = File::TryOpen(a1, &hObject, a3);
    if ( hObject )
      CloseHandle(hObject);
    SetErrorMode(v7);
    return v13;
  }
}

```

## disassembly

```asm
0x180123b68  mov     [rsp+arg_0], rbx
0x180123b6d  push    rbp
0x180123b6e  push    rsi
0x180123b6f  push    rdi
0x180123b70  sub     rsp, 40h
0x180123b74  mov     ebx, r8d
0x180123b77  mov     rbp, rdx
0x180123b7a  mov     rsi, rcx
0x180123b7d  mov     ecx, 8001h; uMode
0x180123b82  call    cs:__imp_SetErrorMode
0x180123b88  mov     edi, eax
0x180123b8a  mov     [rsp+58h+arg_10], eax
0x180123b8e  mov     eax, ebx
0x180123b90  and     eax, 0Ch
0x180123b93  jnz     loc_180123C75
0x180123b99  mov     edx, 80000000h; dwDesiredAccess
0x180123b9e  lea     r8d, [rax+7]; dwShareMode
0x180123ba2  mov     ecx, 3
0x180123ba7  mov     eax, ebx
0x180123ba9  and     eax, 2
0x180123bac  or      eax, 10h
0x180123baf  shl     eax, 18h
0x180123bb2  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180123bbb  mov     [rsp+58h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180123bbf  mov     [rsp+58h+dwCreationDisposition], ecx; dwCreationDisposition
0x180123bc3  xor     r9d, r9d; lpSecurityAttributes
0x180123bc6  mov     rcx, rbp; lpFileName
0x180123bc9  call    cs:__imp_CreateFileW
0x180123bcf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180123bd3  jz      short loc_180123C16
0x180123bd5  mov     [rsp+58h+hObject], rax
0x180123bda  mov     r8d, ebx
0x180123bdd  lea     rdx, [rsp+58h+hObject]
0x180123be2  mov     rcx, rsi
0x180123be5  call    ?TryOpen@File@@QEAAJ$$QEAVWin32Handle@@W4OpenMode@1@@Z; File::TryOpen(Win32Handle &&,File::OpenMode)
0x180123bea  mov     ebx, eax
0x180123bec  mov     rcx, [rsp+58h+hObject]; hObject
0x180123bf1  test    rcx, rcx
0x180123bf4  jnz     short loc_180123C0D
0x180123bf6  mov     ecx, edi; uMode
0x180123bf8  call    cs:__imp_SetErrorMode
0x180123bfe  mov     eax, ebx
0x180123c00  mov     rbx, [rsp+58h+arg_0]
0x180123c05  add     rsp, 40h
0x180123c09  pop     rdi
0x180123c0a  pop     rsi
0x180123c0b  pop     rbp
0x180123c0c  retn
0x180123c0d  call    cs:__imp_CloseHandle
0x180123c13  nop
0x180123c14  jmp     short loc_180123BF6
0x180123c16  call    cs:__imp_GetLastError
0x180123c1c  mov     esi, eax
0x180123c1e  mov     rdx, rbp
0x180123c21  lea     rcx, [rsp+58h+hObject]
0x180123c26  call    ?GetDepersonalizedFilePath@@YA?AVRefString@DWrite@@PEB_W@Z; GetDepersonalizedFilePath(wchar_t const *)
0x180123c2b  mov     r8, 6F69656C6966h
0x180123c35  mov     rbx, [rsp+58h+hObject]
0x180123c3a  lea     rcx, [rbx+8]
0x180123c3e  mov     qword ptr [rsp+58h+dwCreationDisposition], rcx
0x180123c43  mov     r9d, 61h ; 'a'
0x180123c49  mov     edx, esi
0x180123c4b  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x180123c52  call    ??$LogEvent@JVEventTag@@IPEB_W@@YAXVEventTag@@J0IPEB_W@Z; LogEvent<long,EventTag,uint,wchar_t const *>(EventTag,long,EventTag,uint,wchar_t const *)
0x180123c57  mov     ecx, esi; int
0x180123c59  call    ?MapFileOpenError@IOException@@SAHH@Z; IOException::MapFileOpenError(int)
0x180123c5e  mov     esi, eax
0x180123c60  mov     rcx, rbx; struct DWrite::RefString::Data *
0x180123c63  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180123c68  nop
0x180123c69  mov     ecx, edi; uMode
0x180123c6b  call    cs:__imp_SetErrorMode
0x180123c71  mov     eax, esi
0x180123c73  jmp     short loc_180123C00
0x180123c75  cmp     eax, 4
0x180123c78  jz      short loc_180123C9D
0x180123c7a  cmp     eax, 8
0x180123c7d  jz      short loc_180123C8A
0x180123c7f  mov     ecx, 4Dh ; 'M'; unsigned int
0x180123c84  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x180123c89  int     3; Trap to Debugger
0x180123c8a  mov     edx, 0C0000000h
0x180123c8f  mov     ecx, 2
0x180123c94  lea     r8d, [rcx+3]
0x180123c98  jmp     loc_180123BA7
0x180123c9d  mov     edx, 0C0000000h
0x180123ca2  mov     r8d, 5
0x180123ca8  jmp     loc_180123BA2
```
