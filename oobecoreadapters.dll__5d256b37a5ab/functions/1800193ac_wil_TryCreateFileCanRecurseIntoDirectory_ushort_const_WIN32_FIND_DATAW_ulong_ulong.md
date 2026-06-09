# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x1800193ac`
- end: `0x180019473`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180018b80`

## callees

- `0x1800193ac`
- `0x18001955c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800193e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800193e7`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180019415`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180019415`

## pseudocode

```c
HANDLE *__fastcall wil::TryCreateFileCanRecurseIntoDirectory(HANDLE *a1, const WCHAR *a2, _DWORD *a3)
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
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a1);
      *a1 = (HANDLE)-1LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800193ac  mov     [rsp+arg_8], rbx
0x1800193b1  push    rdi
0x1800193b2  sub     rsp, 40h
0x1800193b6  mov     rax, rdx
0x1800193b9  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800193c2  xor     r9d, r9d; lpSecurityAttributes
0x1800193c5  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800193cd  mov     rdi, r8
0x1800193d0  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800193d8  mov     rbx, rcx
0x1800193db  mov     edx, 80010000h; dwDesiredAccess
0x1800193e0  mov     rcx, rax; lpFileName
0x1800193e3  lea     r8d, [r9+1]; dwShareMode
0x1800193e7  call    cs:__imp_CreateFileW
0x1800193ed  mov     [rbx], rax
0x1800193f0  lea     rdx, [rax-1]
0x1800193f4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800193f8  ja      short loc_180019465
0x1800193fa  mov     r9d, 8; dwBufferSize
0x180019400  mov     [rsp+48h+FileInformation], 0
0x180019409  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x18001940e  mov     rcx, rax; hFile
0x180019411  lea     edx, [r9+1]; FileInformationClass
0x180019415  call    cs:__imp_GetFileInformationByHandleEx
0x18001941b  test    eax, eax
0x18001941d  jz      short loc_18001944C
0x18001941f  mov     rax, [rsp+48h+FileInformation]
0x180019424  test    al, 10h
0x180019426  jz      short loc_18001944C
0x180019428  mov     ecx, dword ptr [rsp+48h+FileInformation+4]
0x18001942c  bt      eax, 0Ah
0x180019430  jnb     short loc_180019440
0x180019432  bt      ecx, 1Ch
0x180019436  jb      short loc_180019440
0x180019438  cmp     ecx, 80000018h
0x18001943e  jnz     short loc_18001944C
0x180019440  test    rdi, rdi
0x180019443  jz      short loc_180019465
0x180019445  mov     [rdi], eax
0x180019447  mov     [rdi+24h], ecx
0x18001944a  jmp     short loc_180019465
0x18001944c  mov     rcx, [rbx]; hObject
0x18001944f  lea     rax, [rcx-1]
0x180019453  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019457  ja      short loc_18001945E
0x180019459  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001945e  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180019465  mov     rax, rbx
0x180019468  mov     rbx, [rsp+48h+arg_8]
0x18001946d  add     rsp, 40h
0x180019471  pop     rdi
0x180019472  retn
```
