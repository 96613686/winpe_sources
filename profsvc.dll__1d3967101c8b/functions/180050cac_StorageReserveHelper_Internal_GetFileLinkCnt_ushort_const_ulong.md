# StorageReserveHelper::Internal::GetFileLinkCnt(ushort const *,ulong *)

- ea: `0x180050cac`
- end: `0x180050d68`
- name: `?GetFileLinkCnt@Internal@StorageReserveHelper@@YAEPEBGPEAK@Z`
- size: `188`
- prototype: `unsigned __int8 __fastcall(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800361d4`

## callees

- `0x18003a730`
- `0x180050cac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050d45`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050cfe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050cfe`
- `ntdll!NtQueryInformationFile` at `0x180050d2c`
- `ntdll!NtQueryInformationFile` at `0x180050d2c`

## pseudocode

```c
char __fastcall StorageReserveHelper::Internal::GetFileLinkCnt(
        const WCHAR *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  char v7; // bl
  __int128 FileInformation; // [rsp+40h] [rbp-38h] BYREF
  __int64 v9; // [rsp+50h] [rbp-28h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-20h] BYREF

  *(_DWORD *)a2 = 0;
  v9 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  FileW = CreateFileW(this, 0x80u, 7u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  if ( NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation) >= 0 )
  {
    *(_DWORD *)a2 = v9;
    v7 = 1;
  }
  else
  {
    v7 = 0;
  }
  CloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x180050cac  mov     [rsp+arg_10], rbx
0x180050cb1  push    rdi
0x180050cb2  sub     rsp, 70h
0x180050cb6  mov     rax, cs:__security_cookie
0x180050cbd  xor     rax, rsp
0x180050cc0  mov     [rsp+78h+var_10], rax
0x180050cc5  xor     eax, eax
0x180050cc7  mov     rbx, rdx
0x180050cca  mov     [rsp+78h+hTemplateFile], rax; hTemplateFile
0x180050ccf  xorps   xmm0, xmm0
0x180050cd2  mov     [rdx], eax
0x180050cd4  xorps   xmm1, xmm1
0x180050cd7  mov     edx, 80h; dwDesiredAccess
0x180050cdc  mov     [rsp+78h+var_28], rax
0x180050ce1  mov     [rsp+78h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x180050ce5  lea     r8d, [rax+7]; dwShareMode
0x180050ce9  xor     r9d, r9d; lpSecurityAttributes
0x180050cec  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180050cf4  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x180050cf9  movups  [rsp+78h+FileInformation], xmm1
0x180050cfe  call    cs:__imp_CreateFileW
0x180050d04  mov     rdi, rax
0x180050d07  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180050d0b  jnz     short loc_180050D11
0x180050d0d  xor     al, al
0x180050d0f  jmp     short loc_180050D4D
0x180050d11  mov     r9d, 18h; Length
0x180050d17  mov     [rsp+78h+dwCreationDisposition], 5; FileInformationClass
0x180050d1f  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x180050d24  mov     rcx, rdi; FileHandle
0x180050d27  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x180050d2c  call    cs:__imp_NtQueryInformationFile
0x180050d32  test    eax, eax
0x180050d34  jns     short loc_180050D3A
0x180050d36  xor     ebx, ebx
0x180050d38  jmp     short loc_180050D42
0x180050d3a  mov     eax, dword ptr [rsp+78h+var_28]
0x180050d3e  mov     [rbx], eax
0x180050d40  mov     bl, 1
0x180050d42  mov     rcx, rdi; hObject
0x180050d45  call    cs:__imp_CloseHandle
0x180050d4b  mov     al, bl
0x180050d4d  mov     rcx, [rsp+78h+var_10]
0x180050d52  xor     rcx, rsp; StackCookie
0x180050d55  call    __security_check_cookie
0x180050d5a  mov     rbx, [rsp+78h+arg_10]
0x180050d62  add     rsp, 70h
0x180050d66  pop     rdi
0x180050d67  retn
```
