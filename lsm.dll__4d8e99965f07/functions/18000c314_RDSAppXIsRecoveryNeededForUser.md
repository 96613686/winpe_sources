# RDSAppXIsRecoveryNeededForUser

- ea: `0x18000c314`
- end: `0x18000c460`
- name: `RDSAppXIsRecoveryNeededForUser`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000c2b8`

## callees

- `0x18000c314`
- `0x18000c468`
- `0x18000c500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c419`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c446`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c367`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c3e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c367`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c3e0`

## pseudocode

```c
__int64 __fastcall RDSAppXIsRecoveryNeededForUser(void *a1)
{
  WCHAR *v1; // rdi
  signed int v2; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v5; // eax
  LPCWSTR lpFileName; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR v8; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  lpFileName = 0;
  v8 = 0;
  v2 = UserSidToRecoveryFileName(a1, (unsigned __int16 **)&lpFileName);
  if ( v2 < 0 )
    goto LABEL_12;
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_11;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 < 0 )
  {
    v2 = UserSidToRecoveryFileName(L"S-1-5-18", (unsigned __int16 **)&v8);
    if ( v2 < 0 )
    {
      v1 = (WCHAR *)v8;
      goto LABEL_12;
    }
    v1 = (WCHAR *)v8;
    FileW = CreateFileW(v8, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_12;
    }
LABEL_11:
    CloseHandle(FileW);
  }
LABEL_12:
  if ( lpFileName )
    LocalFree((HLOCAL)lpFileName);
  if ( v1 )
    LocalFree(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c314  mov     rax, rsp
0x18000c317  mov     [rax+8], rbx
0x18000c31b  push    rdi
0x18000c31c  sub     rsp, 40h
0x18000c320  xor     edi, edi
0x18000c322  mov     qword ptr [rax+10h], 0
0x18000c32a  lea     rdx, [rax+10h]; unsigned __int16 **
0x18000c32e  mov     [rax+18h], rdi
0x18000c332  call    ?UserSidToRecoveryFileName@@YAJPEAXPEAPEAG@Z; UserSidToRecoveryFileName(void *,ushort * *)
0x18000c337  mov     ebx, eax
0x18000c339  test    eax, eax
0x18000c33b  js      loc_18000C425
0x18000c341  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x18000c346  lea     r8d, [rdi+3]; dwShareMode
0x18000c34a  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18000c34f  xor     r9d, r9d; lpSecurityAttributes
0x18000c352  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c35a  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c35f  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c367  call    cs:__imp_CreateFileW
0x18000c36e  nop     dword ptr [rax+rax+00h]
0x18000c373  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c377  jnz     loc_18000C416
0x18000c37d  call    cs:__imp_GetLastError
0x18000c384  nop     dword ptr [rax+rax+00h]
0x18000c389  mov     ebx, eax
0x18000c38b  test    eax, eax
0x18000c38d  jle     short loc_18000C398
0x18000c38f  movzx   ebx, ax
0x18000c392  or      ebx, 80070000h
0x18000c398  test    ebx, ebx
0x18000c39a  jns     loc_18000C425
0x18000c3a0  lea     rdx, [rsp+48h+arg_10]; unsigned __int16 **
0x18000c3a5  lea     rcx, aS1518; "S-1-5-18"
0x18000c3ac  call    ?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z; UserSidToRecoveryFileName(ushort const *,ushort * *)
0x18000c3b1  mov     ebx, eax
0x18000c3b3  test    eax, eax
0x18000c3b5  js      short loc_18000C40F
0x18000c3b7  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18000c3bc  xor     r9d, r9d; lpSecurityAttributes
0x18000c3bf  mov     rdi, [rsp+48h+arg_10]
0x18000c3c4  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c3c9  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c3d1  mov     rcx, rdi; lpFileName
0x18000c3d4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c3dc  lea     r8d, [r9+3]; dwShareMode
0x18000c3e0  call    cs:__imp_CreateFileW
0x18000c3e7  nop     dword ptr [rax+rax+00h]
0x18000c3ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c3f0  jnz     short loc_18000C416
0x18000c3f2  call    cs:__imp_GetLastError
0x18000c3f9  nop     dword ptr [rax+rax+00h]
0x18000c3fe  mov     ebx, eax
0x18000c400  test    eax, eax
0x18000c402  jle     short loc_18000C425
0x18000c404  movzx   ebx, ax
0x18000c407  or      ebx, 80070000h
0x18000c40d  jmp     short loc_18000C425
0x18000c40f  mov     rdi, [rsp+48h+arg_10]
0x18000c414  jmp     short loc_18000C425
0x18000c416  mov     rcx, rax; hObject
0x18000c419  call    cs:__imp_CloseHandle
0x18000c420  nop     dword ptr [rax+rax+00h]
0x18000c425  cmp     [rsp+48h+lpFileName], 0
0x18000c42b  jz      short loc_18000C43E
0x18000c42d  mov     rcx, [rsp+48h+lpFileName]; hMem
0x18000c432  call    cs:__imp_LocalFree
0x18000c439  nop     dword ptr [rax+rax+00h]
0x18000c43e  test    rdi, rdi
0x18000c441  jz      short loc_18000C452
0x18000c443  mov     rcx, rdi; hMem
0x18000c446  call    cs:__imp_LocalFree
0x18000c44d  nop     dword ptr [rax+rax+00h]
0x18000c452  mov     eax, ebx
0x18000c454  mov     rbx, [rsp+48h+arg_0]
0x18000c459  add     rsp, 40h
0x18000c45d  pop     rdi
0x18000c45e  retn
```
