# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x180105308`
- end: `0x1801053cf`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180104cec`

## callees

- `0x180105308`
- `0x1801055f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180105343`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180105343`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180105377`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180105377`

## pseudocode

```c
_QWORD *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(_QWORD *a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  __int64 FileInformation; // [rsp+50h] [rbp+8h] BYREF

  FileW = (char *)CreateFileW(a2, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
      && (FileInformation & 0x10) != 0
      && ((v6 = HIDWORD(FileInformation), (FileInformation & 0x400) == 0)
       || (FileInformation & 0x1000000000000000LL) != 0
       || HIDWORD(FileInformation) == -2147483624) )
    {
      if ( a3 )
      {
        *a3 = FileInformation;
        a3[9] = v6;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1,
        -1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180105308  mov     [rsp+arg_8], rbx
0x18010530d  push    rdi
0x18010530e  sub     rsp, 40h
0x180105312  mov     rax, rdx
0x180105315  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18010531e  xor     r9d, r9d; lpSecurityAttributes
0x180105321  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180105329  mov     rbx, r8
0x18010532c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180105334  mov     rdi, rcx
0x180105337  mov     edx, 80010000h; dwDesiredAccess
0x18010533c  mov     rcx, rax; lpFileName
0x18010533f  lea     r8d, [r9+1]; dwShareMode
0x180105343  call    cs:__imp_CreateFileW
0x18010534a  nop     dword ptr [rax+rax+00h]
0x18010534f  mov     [rdi], rax
0x180105352  lea     rdx, [rax-1]
0x180105356  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18010535a  ja      short loc_1801053C0
0x18010535c  mov     r9d, 8; dwBufferSize
0x180105362  mov     [rsp+48h+FileInformation], 0
0x18010536b  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x180105370  mov     rcx, rax; hFile
0x180105373  lea     edx, [r9+1]; FileInformationClass
0x180105377  call    cs:__imp_GetFileInformationByHandleEx
0x18010537e  nop     dword ptr [rax+rax+00h]
0x180105383  test    eax, eax
0x180105385  jz      short loc_1801053B4
0x180105387  mov     rax, [rsp+48h+FileInformation]
0x18010538c  test    al, 10h
0x18010538e  jz      short loc_1801053B4
0x180105390  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x180105394  bt      eax, 0Ah
0x180105398  jnb     short loc_1801053A8
0x18010539a  bt      ecx, 1Ch
0x18010539e  jb      short loc_1801053A8
0x1801053a0  cmp     ecx, 80000018h
0x1801053a6  jnz     short loc_1801053B4
0x1801053a8  test    rbx, rbx
0x1801053ab  jz      short loc_1801053C0
0x1801053ad  mov     [rbx], eax
0x1801053af  mov     [rbx+24h], ecx
0x1801053b2  jmp     short loc_1801053C0
0x1801053b4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801053b8  mov     rcx, rdi
0x1801053bb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801053c0  mov     rbx, [rsp+48h+arg_8]
0x1801053c5  mov     rax, rdi
0x1801053c8  add     rsp, 40h
0x1801053cc  pop     rdi
0x1801053cd  retn
```
