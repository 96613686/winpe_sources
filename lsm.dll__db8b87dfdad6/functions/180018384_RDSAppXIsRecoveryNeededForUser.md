# RDSAppXIsRecoveryNeededForUser

- ea: `0x180018384`
- end: `0x1800184a1`
- name: `RDSAppXIsRecoveryNeededForUser`
- size: `285`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001832c`

## callees

- `0x180018384`
- `0x1800184a8`
- `0x180018528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001844c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001844c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001846d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001846d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001848e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001848e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800183d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018440`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800183d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018440`

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
0x180018384  mov     rax, rsp
0x180018387  mov     [rax+8], rbx
0x18001838b  push    rdi
0x18001838c  sub     rsp, 40h
0x180018390  xor     edi, edi
0x180018392  mov     qword ptr [rax+10h], 0
0x18001839a  lea     rdx, [rax+10h]; unsigned __int16 **
0x18001839e  mov     [rax+18h], rdi
0x1800183a2  call    ?UserSidToRecoveryFileName@@YAJPEAXPEAPEAG@Z; UserSidToRecoveryFileName(void *,ushort * *)
0x1800183a7  mov     ebx, eax
0x1800183a9  test    eax, eax
0x1800183ab  js      loc_180018473
0x1800183b1  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x1800183b6  lea     r8d, [rdi+3]; dwShareMode
0x1800183ba  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x1800183bf  xor     r9d, r9d; lpSecurityAttributes
0x1800183c2  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800183ca  mov     edx, 0C0000000h; dwDesiredAccess
0x1800183cf  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800183d7  call    cs:__imp_CreateFileW
0x1800183dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800183e1  jnz     loc_18001846A
0x1800183e7  call    cs:__imp_GetLastError
0x1800183ed  mov     ebx, eax
0x1800183ef  test    eax, eax
0x1800183f1  jle     short loc_1800183FC
0x1800183f3  movzx   ebx, ax
0x1800183f6  or      ebx, 80070000h
0x1800183fc  test    ebx, ebx
0x1800183fe  jns     short loc_180018473
0x180018400  lea     rdx, [rsp+48h+arg_10]; unsigned __int16 **
0x180018405  lea     rcx, aS1518; "S-1-5-18"
0x18001840c  call    ?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z; UserSidToRecoveryFileName(ushort const *,ushort * *)
0x180018411  mov     ebx, eax
0x180018413  test    eax, eax
0x180018415  js      short loc_180018463
0x180018417  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18001841c  xor     r9d, r9d; lpSecurityAttributes
0x18001841f  mov     rdi, [rsp+48h+arg_10]
0x180018424  mov     edx, 0C0000000h; dwDesiredAccess
0x180018429  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180018431  mov     rcx, rdi; lpFileName
0x180018434  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001843c  lea     r8d, [r9+3]; dwShareMode
0x180018440  call    cs:__imp_CreateFileW
0x180018446  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001844a  jnz     short loc_18001846A
0x18001844c  call    cs:__imp_GetLastError
0x180018452  mov     ebx, eax
0x180018454  test    eax, eax
0x180018456  jle     short loc_180018473
0x180018458  movzx   ebx, ax
0x18001845b  or      ebx, 80070000h
0x180018461  jmp     short loc_180018473
0x180018463  mov     rdi, [rsp+48h+arg_10]
0x180018468  jmp     short loc_180018473
0x18001846a  mov     rcx, rax; hObject
0x18001846d  call    cs:__imp_CloseHandle
0x180018473  cmp     [rsp+48h+lpFileName], 0
0x180018479  jz      short loc_180018486
0x18001847b  mov     rcx, [rsp+48h+lpFileName]; hMem
0x180018480  call    cs:__imp_LocalFree
0x180018486  test    rdi, rdi
0x180018489  jz      short loc_180018494
0x18001848b  mov     rcx, rdi; hMem
0x18001848e  call    cs:__imp_LocalFree
0x180018494  mov     eax, ebx
0x180018496  mov     rbx, [rsp+48h+arg_0]
0x18001849b  add     rsp, 40h
0x18001849f  pop     rdi
0x1800184a0  retn
```
