# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x18010416c`
- end: `0x180104226`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180103bc4`

## callees

- `0x18010416c`
- `0x1801043d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801041a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801041a7`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1801041d5`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1801041d5`

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
0x18010416c  mov     [rsp+arg_8], rbx
0x180104171  push    rdi
0x180104172  sub     rsp, 40h
0x180104176  mov     rax, rdx
0x180104179  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180104182  xor     r9d, r9d; lpSecurityAttributes
0x180104185  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18010418d  mov     rbx, r8
0x180104190  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180104198  mov     rdi, rcx
0x18010419b  mov     edx, 80010000h; dwDesiredAccess
0x1801041a0  mov     rcx, rax; lpFileName
0x1801041a3  lea     r8d, [r9+1]; dwShareMode
0x1801041a7  call    cs:__imp_CreateFileW
0x1801041ad  mov     [rdi], rax
0x1801041b0  lea     rdx, [rax-1]
0x1801041b4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801041b8  ja      short loc_180104218
0x1801041ba  mov     r9d, 8; dwBufferSize
0x1801041c0  mov     [rsp+48h+FileInformation], 0
0x1801041c9  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x1801041ce  mov     rcx, rax; hFile
0x1801041d1  lea     edx, [r9+1]; FileInformationClass
0x1801041d5  call    cs:__imp_GetFileInformationByHandleEx
0x1801041db  test    eax, eax
0x1801041dd  jz      short loc_18010420C
0x1801041df  mov     rax, [rsp+48h+FileInformation]
0x1801041e4  test    al, 10h
0x1801041e6  jz      short loc_18010420C
0x1801041e8  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x1801041ec  bt      eax, 0Ah
0x1801041f0  jnb     short loc_180104200
0x1801041f2  bt      ecx, 1Ch
0x1801041f6  jb      short loc_180104200
0x1801041f8  cmp     ecx, 80000018h
0x1801041fe  jnz     short loc_18010420C
0x180104200  test    rbx, rbx
0x180104203  jz      short loc_180104218
0x180104205  mov     [rbx], eax
0x180104207  mov     [rbx+24h], ecx
0x18010420a  jmp     short loc_180104218
0x18010420c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180104210  mov     rcx, rdi
0x180104213  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180104218  mov     rbx, [rsp+48h+arg_8]
0x18010421d  mov     rax, rdi
0x180104220  add     rsp, 40h
0x180104224  pop     rdi
0x180104225  retn
```
