# DsRolepCheckFolderPresent

- ea: `0x18000c048`
- end: `0x18000c10c`
- name: `DsRolepCheckFolderPresent`
- size: `196`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c120`

## callees

- `0x18000c048`
- `0x180020dbc`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c08f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c08f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c0df`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c09b`

## string_xrefs

- `0x18000c0ba`: `	Error searching Path %ws:%lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepCheckFolderPresent(LPCWSTR lpFileName, _BYTE *a2)
{
  HANDLE FirstFileW; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *a2 = 0;
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( ((LastError - 2) & 0xFFFFFFEE) != 0 || LastError == 19 )
      DsRolepLogPrintRoutine(1, "\tError searching Path %ws:%lu\n", lpFileName, LastError);
    else
      return 0;
  }
  else
  {
    v6 = 0;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      *a2 = 1;
    FindClose(FirstFileW);
  }
  return v6;
}

```

## disassembly

```asm
0x18000c048  mov     [rsp+arg_10], rbx
0x18000c04d  mov     [rsp+arg_18], rsi
0x18000c052  push    rdi
0x18000c053  sub     rsp, 280h
0x18000c05a  mov     rax, cs:__security_cookie
0x18000c061  xor     rax, rsp
0x18000c064  mov     [rsp+288h+var_18], rax
0x18000c06c  mov     rdi, rdx
0x18000c06f  mov     rsi, rcx
0x18000c072  xor     edx, edx; Val
0x18000c074  lea     rcx, [rsp+288h+FindFileData]; void *
0x18000c079  mov     r8d, 250h; Size
0x18000c07f  call    memset_0
0x18000c084  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x18000c089  mov     byte ptr [rdi], 0
0x18000c08c  mov     rcx, rsi; lpFileName
0x18000c08f  call    cs:__imp_FindFirstFileW
0x18000c095  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c099  jnz     short loc_18000C0D0
0x18000c09b  call    cs:__imp_GetLastError
0x18000c0a1  mov     ebx, eax
0x18000c0a3  lea     ecx, [rax-2]
0x18000c0a6  test    ecx, 0FFFFFFEEh
0x18000c0ac  jnz     short loc_18000C0B7
0x18000c0ae  cmp     eax, 13h
0x18000c0b1  jz      short loc_18000C0B7
0x18000c0b3  xor     ebx, ebx
0x18000c0b5  jmp     short loc_18000C0E5
0x18000c0b7  mov     r9d, eax
0x18000c0ba  lea     rdx, aErrorSearching; "\tError searching Path %ws:%lu\n"
0x18000c0c1  mov     r8, rsi
0x18000c0c4  mov     ecx, 1
0x18000c0c9  call    DsRolepLogPrintRoutine
0x18000c0ce  jmp     short loc_18000C0E5
0x18000c0d0  xor     ebx, ebx
0x18000c0d2  test    byte ptr [rsp+288h+FindFileData.dwFileAttributes], 10h
0x18000c0d7  jz      short loc_18000C0DC
0x18000c0d9  mov     byte ptr [rdi], 1
0x18000c0dc  mov     rcx, rax; hFindFile
0x18000c0df  call    cs:__imp_FindClose
0x18000c0e5  mov     eax, ebx
0x18000c0e7  mov     rcx, [rsp+288h+var_18]
0x18000c0ef  xor     rcx, rsp; StackCookie
0x18000c0f2  call    __security_check_cookie
0x18000c0f7  lea     r11, [rsp+288h+var_8]
0x18000c0ff  mov     rbx, [r11+20h]
0x18000c103  mov     rsi, [r11+28h]
0x18000c107  mov     rsp, r11
0x18000c10a  pop     rdi
0x18000c10b  retn
```
