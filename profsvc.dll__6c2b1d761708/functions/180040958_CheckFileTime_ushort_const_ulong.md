# _CheckFileTime(ushort const *,ulong)

- ea: `0x180040958`
- end: `0x180040a6a`
- name: `?_CheckFileTime@@YA_NPEBGK@Z`
- size: `274`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180037bbc`

## callees

- `0x1800084bc`
- `0x180040958`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040a28`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040a28`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800409ed`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180040a3c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800409ed`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180040a3c`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800409cd`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800409cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040991`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040991`

## pseudocode

```c
bool __fastcall _CheckFileTime(const unsigned __int16 *a1, unsigned int a2)
{
  bool v3; // bl
  char *FileW; // rax
  LONG v5; // eax
  struct _FILETIME v6; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-20h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-18h] BYREF
  char *v10; // [rsp+50h] [rbp-10h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+20h] BYREF
  struct _FILETIME CreationTime; // [rsp+88h] [rbp+28h] BYREF

  v3 = 0;
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CreationTime = 0;
    LastWriteTime = 0;
    if ( GetFileTime(FileW, &CreationTime, 0, &LastWriteTime) )
    {
      FileTime1 = 0;
      v5 = CompareFileTime(&LastWriteTime, &CreationTime);
      v6 = LastWriteTime;
      SystemTimeAsFileTime = 0;
      if ( v5 == -1 )
        v6 = CreationTime;
      FileTime1 = (FILETIME)(*(_QWORD *)&v6 + 864000000000LL * a2);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v3 = CompareFileTime(&FileTime1, &SystemTimeAsFileTime) == -1;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  return v3;
}

```

## disassembly

```asm
0x180040958  mov     rax, rsp
0x18004095b  mov     [rax+8], rbx
0x18004095f  mov     [rax+10h], rdi
0x180040963  push    rbp
0x180040964  mov     rbp, rsp
0x180040967  sub     rsp, 60h
0x18004096b  mov     qword ptr [rax-38h], 0
0x180040973  xor     r9d, r9d; lpSecurityAttributes
0x180040976  mov     edi, edx
0x180040978  xor     bl, bl
0x18004097a  mov     dword ptr [rax-40h], 80h
0x180040981  mov     edx, 80000000h; dwDesiredAccess
0x180040986  mov     dword ptr [rax-48h], 3
0x18004098d  lea     r8d, [r9+1]; dwShareMode
0x180040991  call    cs:__imp_CreateFileW
0x180040998  nop     dword ptr [rax+rax+00h]
0x18004099d  mov     [rbp+var_10], rax
0x1800409a1  lea     rcx, [rax-1]
0x1800409a5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800409a9  ja      loc_180040A4E
0x1800409af  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1800409b3  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x1800409bb  xor     r8d, r8d; lpLastAccessTime
0x1800409be  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], 0
0x1800409c6  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x1800409ca  mov     rcx, rax; hFile
0x1800409cd  call    cs:__imp_GetFileTime
0x1800409d4  nop     dword ptr [rax+rax+00h]
0x1800409d9  test    eax, eax
0x1800409db  jz      short loc_180040A4E
0x1800409dd  lea     rdx, [rbp+CreationTime]; lpFileTime2
0x1800409e1  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x1800409e9  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x1800409ed  call    cs:__imp_CompareFileTime
0x1800409f4  nop     dword ptr [rax+rax+00h]
0x1800409f9  mov     rcx, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x1800409fd  mov     rdx, 0C92A69C000h
0x180040a07  cmp     eax, 0FFFFFFFFh
0x180040a0a  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180040a12  mov     eax, edi
0x180040a14  cmovz   rcx, qword ptr [rbp+CreationTime.dwLowDateTime]
0x180040a19  imul    rax, rdx
0x180040a1d  add     rax, rcx
0x180040a20  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180040a24  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180040a28  call    cs:__imp_GetSystemTimeAsFileTime
0x180040a2f  nop     dword ptr [rax+rax+00h]
0x180040a34  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x180040a38  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180040a3c  call    cs:__imp_CompareFileTime
0x180040a43  nop     dword ptr [rax+rax+00h]
0x180040a48  cmp     eax, 0FFFFFFFFh
0x180040a4b  setz    bl
0x180040a4e  lea     rcx, [rbp+var_10]
0x180040a52  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040a57  mov     rdi, [rsp+60h+arg_8]
0x180040a5c  mov     al, bl
0x180040a5e  mov     rbx, [rsp+60h+arg_0]
0x180040a63  add     rsp, 60h
0x180040a67  pop     rbp
0x180040a68  retn
```
