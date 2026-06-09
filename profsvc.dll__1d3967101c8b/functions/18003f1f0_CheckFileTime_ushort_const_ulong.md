# _CheckFileTime(ushort const *,ulong)

- ea: `0x18003f1f0`
- end: `0x18003f2e3`
- name: `?_CheckFileTime@@YA_NPEBGK@Z`
- size: `243`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002c630`

## callees

- `0x18000a9b8`
- `0x18003f1f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003f2ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003f2ae`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003f279`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003f2bc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003f279`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003f2bc`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18003f25f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18003f25f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f229`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f229`

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
  void *v10; // [rsp+50h] [rbp-10h] BYREF
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
0x18003f1f0  mov     rax, rsp
0x18003f1f3  mov     [rax+8], rbx
0x18003f1f7  mov     [rax+10h], rdi
0x18003f1fb  push    rbp
0x18003f1fc  mov     rbp, rsp
0x18003f1ff  sub     rsp, 60h
0x18003f203  mov     qword ptr [rax-38h], 0
0x18003f20b  xor     r9d, r9d; lpSecurityAttributes
0x18003f20e  mov     edi, edx
0x18003f210  xor     bl, bl
0x18003f212  mov     dword ptr [rax-40h], 80h
0x18003f219  mov     edx, 80000000h; dwDesiredAccess
0x18003f21e  mov     dword ptr [rax-48h], 3
0x18003f225  lea     r8d, [r9+1]; dwShareMode
0x18003f229  call    cs:__imp_CreateFileW
0x18003f22f  mov     [rbp+var_10], rax
0x18003f233  lea     rcx, [rax-1]
0x18003f237  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003f23b  ja      loc_18003F2C8
0x18003f241  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x18003f245  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x18003f24d  xor     r8d, r8d; lpLastAccessTime
0x18003f250  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], 0
0x18003f258  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x18003f25c  mov     rcx, rax; hFile
0x18003f25f  call    cs:__imp_GetFileTime
0x18003f265  test    eax, eax
0x18003f267  jz      short loc_18003F2C8
0x18003f269  lea     rdx, [rbp+CreationTime]; lpFileTime2
0x18003f26d  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x18003f275  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x18003f279  call    cs:__imp_CompareFileTime
0x18003f27f  mov     rcx, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x18003f283  mov     rdx, 0C92A69C000h
0x18003f28d  cmp     eax, 0FFFFFFFFh
0x18003f290  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003f298  mov     eax, edi
0x18003f29a  cmovz   rcx, qword ptr [rbp+CreationTime.dwLowDateTime]
0x18003f29f  imul    rax, rdx
0x18003f2a3  add     rax, rcx
0x18003f2a6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003f2aa  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18003f2ae  call    cs:__imp_GetSystemTimeAsFileTime
0x18003f2b4  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x18003f2b8  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18003f2bc  call    cs:__imp_CompareFileTime
0x18003f2c2  cmp     eax, 0FFFFFFFFh
0x18003f2c5  setz    bl
0x18003f2c8  lea     rcx, [rbp+var_10]
0x18003f2cc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f2d1  mov     rdi, [rsp+60h+arg_8]
0x18003f2d6  mov     al, bl
0x18003f2d8  mov     rbx, [rsp+60h+arg_0]
0x18003f2dd  add     rsp, 60h
0x18003f2e1  pop     rbp
0x18003f2e2  retn
```
