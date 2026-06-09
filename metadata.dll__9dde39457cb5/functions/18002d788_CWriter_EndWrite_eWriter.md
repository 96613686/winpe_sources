# CWriter::EndWrite(eWriter)

- ea: `0x18002d788`
- end: `0x18002d861`
- name: `?EndWrite@CWriter@@QEAAJW4eWriter@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180009c14`
- `0x1800120b4`
- `0x180023df4`
- `0x180024e90`

## callees

- `0x180006d08`
- `0x18002d788`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002d7cd`
- `KERNEL32!CloseHandle` at `0x18002d7cd`
- `KERNEL32!DeleteFileW` at `0x18002d7e6`
- `KERNEL32!DeleteFileW` at `0x18002d7e6`
- `KERNEL32!GetLastError` at `0x18002d83f`
- `KERNEL32!GetLastError` at `0x18002d83f`
- `KERNEL32!FlushFileBuffers` at `0x18002d835`
- `KERNEL32!FlushFileBuffers` at `0x18002d835`
- `KERNEL32!SetEndOfFile` at `0x18002d824`
- `KERNEL32!SetEndOfFile` at `0x18002d824`

## string_xrefs

- `0x18002d7f5`: `</MBProperty>\n</configuration>\n`

## pseudocode

```c
__int64 __fastcall CWriter::EndWrite(__int64 a1, int a2)
{
  int v3; // edx
  unsigned int v5; // ebx
  char *v6; // rcx
  const WCHAR *v7; // rcx
  BOOL v8; // eax
  unsigned int v9; // r8d
  wchar_t *v10; // rdx
  signed int LastError; // eax

  if ( !a2 )
  {
    v9 = g_cchEndSchema;
    v10 = L"\t</DatabaseMeta>\r\n</MetaData>\r\n";
LABEL_11:
    v5 = CWriter::WriteToFile((CWriter *)a1, v10, v9, 1);
    if ( (v5 & 0x80000000) != 0 || !SetEndOfFile(*(HANDLE *)(a1 + 65592)) )
      goto LABEL_15;
    v8 = FlushFileBuffers(*(HANDLE *)(a1 + 65592));
    goto LABEL_14;
  }
  v3 = a2 - 1;
  if ( !v3 )
  {
    v9 = g_cchEndFile;
    v10 = L"</MBProperty>\r\n</configuration>\r\n";
    goto LABEL_11;
  }
  if ( v3 != 1 )
    return 2147942487LL;
  v5 = 0;
  if ( !*(_DWORD *)(a1 + 8) )
    return v5;
  v6 = *(char **)(a1 + 65592);
  if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return v5;
  CloseHandle(v6);
  v7 = *(const WCHAR **)a1;
  *(_QWORD *)(a1 + 65592) = -1;
  if ( !v7 )
    return v5;
  v8 = DeleteFileW(v7);
LABEL_14:
  if ( !v8 )
  {
LABEL_15:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x18002d788  mov     [rsp+arg_0], rbx
0x18002d78d  push    rdi
0x18002d78e  sub     rsp, 20h
0x18002d792  mov     rdi, rcx
0x18002d795  test    edx, edx
0x18002d797  jz      short loc_18002D7FE
0x18002d799  sub     edx, 1
0x18002d79c  jz      short loc_18002D7EE
0x18002d79e  cmp     edx, 1
0x18002d7a1  jz      short loc_18002D7AD
0x18002d7a3  mov     eax, 80070057h
0x18002d7a8  jmp     loc_18002D856
0x18002d7ad  xor     ebx, ebx
0x18002d7af  cmp     [rcx+8], ebx
0x18002d7b2  jz      loc_18002D854
0x18002d7b8  mov     rcx, [rcx+10038h]; hObject
0x18002d7bf  lea     rax, [rcx-1]
0x18002d7c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d7c7  ja      loc_18002D854
0x18002d7cd  call    cs:__imp_CloseHandle
0x18002d7d3  mov     rcx, [rdi]; lpFileName
0x18002d7d6  mov     qword ptr [rdi+10038h], 0FFFFFFFFFFFFFFFFh
0x18002d7e1  test    rcx, rcx
0x18002d7e4  jz      short loc_18002D854
0x18002d7e6  call    cs:__imp_DeleteFileW
0x18002d7ec  jmp     short loc_18002D83B
0x18002d7ee  mov     r8d, cs:?g_cchEndFile@@3KA; ulong g_cchEndFile
0x18002d7f5  lea     rdx, aMbpropertyConf; "</MBProperty>\r\n</configuration>\r\n"
0x18002d7fc  jmp     short loc_18002D80C
0x18002d7fe  mov     r8d, cs:?g_cchEndSchema@@3KA; unsigned int
0x18002d805  lea     rdx, aDatabasemetaMe; "\t</DatabaseMeta>\r\n</MetaData>\r\n"
0x18002d80c  mov     r9d, 1; int
0x18002d812  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002d817  mov     ebx, eax
0x18002d819  test    eax, eax
0x18002d81b  js      short loc_18002D83F
0x18002d81d  mov     rcx, [rdi+10038h]; hFile
0x18002d824  call    cs:__imp_SetEndOfFile
0x18002d82a  test    eax, eax
0x18002d82c  jz      short loc_18002D83F
0x18002d82e  mov     rcx, [rdi+10038h]; hFile
0x18002d835  call    cs:__imp_FlushFileBuffers
0x18002d83b  test    eax, eax
0x18002d83d  jnz     short loc_18002D854
0x18002d83f  call    cs:__imp_GetLastError
0x18002d845  mov     ebx, eax
0x18002d847  test    eax, eax
0x18002d849  jle     short loc_18002D854
0x18002d84b  movzx   ebx, ax
0x18002d84e  or      ebx, 80070000h
0x18002d854  mov     eax, ebx
0x18002d856  mov     rbx, [rsp+28h+arg_0]
0x18002d85b  add     rsp, 20h
0x18002d85f  pop     rdi
0x18002d860  retn
```
