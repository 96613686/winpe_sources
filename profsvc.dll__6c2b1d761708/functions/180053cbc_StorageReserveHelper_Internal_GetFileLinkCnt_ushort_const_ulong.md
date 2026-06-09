# StorageReserveHelper::Internal::GetFileLinkCnt(ushort const *,ulong *)

- ea: `0x180053cbc`
- end: `0x180053d8b`
- name: `?GetFileLinkCnt@Internal@StorageReserveHelper@@YAEPEBGPEAK@Z`
- size: `207`
- prototype: `unsigned __int8 __fastcall(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180036840`

## callees

- `0x18003bc70`
- `0x180053cbc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053d61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053d0e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053d0e`
- `ntdll!NtQueryInformationFile` at `0x180053d42`
- `ntdll!NtQueryInformationFile` at `0x180053d42`

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
0x180053cbc  mov     [rsp+arg_10], rbx
0x180053cc1  push    rdi
0x180053cc2  sub     rsp, 70h
0x180053cc6  mov     rax, cs:__security_cookie
0x180053ccd  xor     rax, rsp
0x180053cd0  mov     [rsp+78h+var_10], rax
0x180053cd5  xor     eax, eax
0x180053cd7  mov     rbx, rdx
0x180053cda  mov     [rsp+78h+hTemplateFile], rax; hTemplateFile
0x180053cdf  xorps   xmm0, xmm0
0x180053ce2  mov     [rdx], eax
0x180053ce4  xorps   xmm1, xmm1
0x180053ce7  mov     edx, 80h; dwDesiredAccess
0x180053cec  mov     [rsp+78h+var_28], rax
0x180053cf1  mov     [rsp+78h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x180053cf5  lea     r8d, [rax+7]; dwShareMode
0x180053cf9  xor     r9d, r9d; lpSecurityAttributes
0x180053cfc  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180053d04  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x180053d09  movups  [rsp+78h+FileInformation], xmm1
0x180053d0e  call    cs:__imp_CreateFileW
0x180053d15  nop     dword ptr [rax+rax+00h]
0x180053d1a  mov     rdi, rax
0x180053d1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053d21  jnz     short loc_180053D27
0x180053d23  xor     al, al
0x180053d25  jmp     short loc_180053D6F
0x180053d27  mov     r9d, 18h; Length
0x180053d2d  mov     [rsp+78h+dwCreationDisposition], 5; FileInformationClass
0x180053d35  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x180053d3a  mov     rcx, rdi; FileHandle
0x180053d3d  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x180053d42  call    cs:__imp_NtQueryInformationFile
0x180053d49  nop     dword ptr [rax+rax+00h]
0x180053d4e  test    eax, eax
0x180053d50  jns     short loc_180053D56
0x180053d52  xor     ebx, ebx
0x180053d54  jmp     short loc_180053D5E
0x180053d56  mov     eax, dword ptr [rsp+78h+var_28]
0x180053d5a  mov     [rbx], eax
0x180053d5c  mov     bl, 1
0x180053d5e  mov     rcx, rdi; hObject
0x180053d61  call    cs:__imp_CloseHandle
0x180053d68  nop     dword ptr [rax+rax+00h]
0x180053d6d  mov     al, bl
0x180053d6f  mov     rcx, [rsp+78h+var_10]
0x180053d74  xor     rcx, rsp; StackCookie
0x180053d77  call    __security_check_cookie
0x180053d7c  mov     rbx, [rsp+78h+arg_10]
0x180053d84  add     rsp, 70h
0x180053d88  pop     rdi
0x180053d89  retn
```
