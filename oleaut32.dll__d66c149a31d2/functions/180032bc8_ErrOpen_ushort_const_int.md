# ErrOpen(ushort const *,int *)

- ea: `0x180032bc8`
- end: `0x180032cb4`
- name: `?ErrOpen@@YAJPEBGPEAH@Z`
- size: `236`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180044c0c`

## callees

- `0x180032bc8`
- `0x180032cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032c36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c9c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032bfc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032c93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032bfc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032c93`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180032c61`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180032c61`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180032cac`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180032cac`

## pseudocode

```c
__int64 __fastcall ErrOpen(LPCWSTR lpFileName, int *a2)
{
  HANDLE FileW; // rbx
  DWORD LastError; // edi
  DWORD v7; // eax
  PVOID OldValue; // [rsp+80h] [rbp+18h] BYREF

  FileW = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0x10000000u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError != 2 || !g_fIsWow64Process )
    goto LABEL_4;
  OldValue = 0;
  if ( Wow64DisableWow64FsRedirection(&OldValue) )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0x10000000u, 0);
    LastError = GetLastError();
    Wow64RevertWow64FsRedirection(OldValue);
  }
  SetLastError(LastError);
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_4:
    v7 = GetLastError();
    return TiperrOfOFErr(v7);
  }
  else
  {
LABEL_2:
    *a2 = (int)FileW;
    return 0;
  }
}

```

## disassembly

```asm
0x180032bc8  push    rbx
0x180032bca  push    rbp
0x180032bcb  push    rsi
0x180032bcc  push    rdi
0x180032bcd  sub     rsp, 48h
0x180032bd1  xor     r9d, r9d; lpSecurityAttributes
0x180032bd4  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180032bdd  mov     rsi, rdx
0x180032be0  mov     [rsp+68h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180032be8  mov     edx, 80000000h; dwDesiredAccess
0x180032bed  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180032bf5  mov     rbp, rcx
0x180032bf8  lea     r8d, [r9+5]; dwShareMode
0x180032bfc  call    cs:__imp_CreateFileW
0x180032c02  mov     rbx, rax
0x180032c05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032c09  jz      short loc_180032C18
0x180032c0b  mov     [rsi], ebx
0x180032c0d  xor     eax, eax
0x180032c0f  add     rsp, 48h
0x180032c13  pop     rdi
0x180032c14  pop     rsi
0x180032c15  pop     rbp
0x180032c16  pop     rbx
0x180032c17  retn
0x180032c18  call    cs:__imp_GetLastError
0x180032c1e  mov     edi, eax
0x180032c20  cmp     eax, 2
0x180032c23  jz      short loc_180032C44
0x180032c25  call    cs:__imp_GetLastError
0x180032c2b  mov     ecx, eax; unsigned int
0x180032c2d  call    ?TiperrOfOFErr@@YAJI@Z; TiperrOfOFErr(uint)
0x180032c32  jmp     short loc_180032C0F
0x180032c34  mov     ecx, edi; dwErrCode
0x180032c36  call    cs:__imp_SetLastError
0x180032c3c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180032c40  jz      short loc_180032C25
0x180032c42  jmp     short loc_180032C0B
0x180032c44  cmp     cs:?g_fIsWow64Process@@3HA, 0; int g_fIsWow64Process
0x180032c4b  jz      short loc_180032C25
0x180032c4d  lea     rcx, [rsp+68h+OldValue]; OldValue
0x180032c55  mov     [rsp+68h+OldValue], 0
0x180032c61  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180032c67  test    eax, eax
0x180032c69  jz      short loc_180032C34
0x180032c6b  xor     r9d, r9d; lpSecurityAttributes
0x180032c6e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180032c77  mov     [rsp+68h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180032c7f  mov     edx, 80000000h; dwDesiredAccess
0x180032c84  mov     rcx, rbp; lpFileName
0x180032c87  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180032c8f  lea     r8d, [r9+5]; dwShareMode
0x180032c93  call    cs:__imp_CreateFileW
0x180032c99  mov     rbx, rax
0x180032c9c  call    cs:__imp_GetLastError
0x180032ca2  mov     rcx, [rsp+68h+OldValue]; OlValue
0x180032caa  mov     edi, eax
0x180032cac  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180032cb2  jmp     short loc_180032C34
```
