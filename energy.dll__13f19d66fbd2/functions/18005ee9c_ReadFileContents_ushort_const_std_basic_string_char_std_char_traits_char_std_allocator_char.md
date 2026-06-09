# ReadFileContents(ushort const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18005ee9c`
- end: `0x18005f015`
- name: `?ReadFileContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18007b860`

## callees

- `0x180004e20`
- `0x180027c30`
- `0x180027dc8`
- `0x180046b5c`
- `0x18004d8fc`
- `0x18005ee9c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005ef2c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005ef2c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005efc4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005efc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005eef5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005eef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005efef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005efef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadFileContents(__int64 a1, __int64 a2)
{
  LPCWSTR v3; // r10
  HANDLE FileW; // rax
  void *v5; // r14
  __int64 v6; // rsi
  signed int v7; // eax
  unsigned int v8; // ebx
  signed int LastError; // eax
  unsigned __int64 v10; // rdi
  char *v11; // rbx
  size_t v12; // rdi
  LPVOID lpBuffer; // [rsp+40h] [rbp-20h] BYREF
  void *v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h]
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+40h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+A8h] [rbp+48h] BYREF

  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&lpBuffer);
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  FileW = CreateFileW(v3, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v5 = FileW;
  v6 = -1;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !GetFileSizeEx(FileW, &FileSize) )
      goto LABEL_5;
    v10 = FileSize.QuadPart + 1;
    v11 = (char *)v15;
    if ( FileSize.QuadPart + 1 >= (unsigned __int64)((_BYTE *)v15 - (_BYTE *)lpBuffer) )
    {
      if ( FileSize.QuadPart + 1 <= (unsigned __int64)((_BYTE *)v15 - (_BYTE *)lpBuffer) )
        goto LABEL_14;
      if ( v10 > v16 - (__int64)lpBuffer )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&lpBuffer, FileSize.QuadPart + 1);
        LODWORD(v11) = (_DWORD)v15;
        goto LABEL_14;
      }
      v12 = v10 - ((_BYTE *)v15 - (_BYTE *)lpBuffer);
      memset_0(v15, 0, v12);
      v11 += v12;
    }
    else
    {
      v11 = (char *)lpBuffer + v10;
    }
    v15 = v11;
LABEL_14:
    if ( ReadFile(v5, lpBuffer, (_DWORD)v11 - (_DWORD)lpBuffer, &NumberOfBytesRead, 0) )
    {
      do
        ++v6;
      while ( *((_BYTE *)lpBuffer + v6) );
      std::string::_Assign<char>(a2, lpBuffer, v6);
      v8 = 0;
LABEL_17:
      CloseHandle(v5);
      goto LABEL_18;
    }
LABEL_5:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
LABEL_18:
  std::vector<unsigned char>::_Tidy(&lpBuffer);
  return v8;
}

```

## disassembly

```asm
0x18005ee9c  mov     [rsp-28h+arg_0], rbx
0x18005eea1  push    rbp
0x18005eea2  push    rsi
0x18005eea3  push    rdi
0x18005eea4  push    r14
0x18005eea6  push    r15
0x18005eea8  mov     rbp, rsp
0x18005eeab  sub     rsp, 60h
0x18005eeaf  mov     r15, rdx
0x18005eeb2  mov     r10, rcx
0x18005eeb5  lea     rcx, [rbp+lpBuffer]; void *
0x18005eeb9  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x18005eebe  nop
0x18005eebf  mov     [rbp+NumberOfBytesRead], 0
0x18005eec6  mov     qword ptr [rbp+FileSize], 0
0x18005eece  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18005eed7  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005eedf  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18005eee7  xor     r9d, r9d; lpSecurityAttributes
0x18005eeea  xor     r8d, r8d; dwShareMode
0x18005eeed  mov     edx, 80000000h; dwDesiredAccess
0x18005eef2  mov     rcx, r10; lpFileName
0x18005eef5  call    cs:__imp_CreateFileW
0x18005eefb  mov     r14, rax
0x18005eefe  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005ef02  cmp     rax, rsi
0x18005ef05  jnz     short loc_18005EF25
0x18005ef07  call    cs:__imp_GetLastError
0x18005ef0d  mov     ebx, eax
0x18005ef0f  test    eax, eax
0x18005ef11  jle     loc_18005EFF6
0x18005ef17  movzx   ebx, ax
0x18005ef1a  or      ebx, 80070000h
0x18005ef20  jmp     loc_18005EFF6
0x18005ef25  lea     rdx, [rbp+FileSize]; lpFileSize
0x18005ef29  mov     rcx, r14; hFile
0x18005ef2c  call    cs:__imp_GetFileSizeEx
0x18005ef32  test    eax, eax
0x18005ef34  jnz     short loc_18005EF54
0x18005ef36  call    cs:__imp_GetLastError
0x18005ef3c  mov     ebx, eax
0x18005ef3e  test    eax, eax
0x18005ef40  jle     loc_18005EFEC
0x18005ef46  movzx   ebx, ax
0x18005ef49  or      ebx, 80070000h
0x18005ef4f  jmp     loc_18005EFEC
0x18005ef54  mov     rdi, qword ptr [rbp+FileSize]
0x18005ef58  inc     rdi
0x18005ef5b  mov     rdx, [rbp+lpBuffer]
0x18005ef5f  mov     rbx, [rbp+var_18]
0x18005ef63  mov     rcx, rbx
0x18005ef66  sub     rcx, rdx
0x18005ef69  cmp     rdi, rcx
0x18005ef6c  jnb     short loc_18005EF74
0x18005ef6e  lea     rbx, [rdi+rdx]
0x18005ef72  jmp     short loc_18005EFA7
0x18005ef74  jbe     short loc_18005EFAB
0x18005ef76  mov     rax, [rbp+var_10]
0x18005ef7a  sub     rax, rdx
0x18005ef7d  cmp     rdi, rax
0x18005ef80  jbe     short loc_18005EF94
0x18005ef82  mov     rdx, rdi
0x18005ef85  lea     rcx, [rbp+lpBuffer]
0x18005ef89  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005ef8e  mov     rbx, [rbp+var_18]
0x18005ef92  jmp     short loc_18005EFAB
0x18005ef94  sub     rdi, rcx
0x18005ef97  mov     r8, rdi; Size
0x18005ef9a  xor     edx, edx; Val
0x18005ef9c  mov     rcx, rbx; void *
0x18005ef9f  call    memset_0
0x18005efa4  add     rbx, rdi
0x18005efa7  mov     [rbp+var_18], rbx
0x18005efab  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18005efaf  sub     ebx, edx
0x18005efb1  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x18005efba  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005efbe  mov     r8d, ebx; nNumberOfBytesToRead
0x18005efc1  mov     rcx, r14; hFile
0x18005efc4  call    cs:__imp_ReadFile
0x18005efca  test    eax, eax
0x18005efcc  jz      loc_18005EF36
0x18005efd2  mov     rdx, [rbp+lpBuffer]
0x18005efd6  inc     rsi
0x18005efd9  cmp     byte ptr [rdx+rsi], 0
0x18005efdd  jnz     short loc_18005EFD6
0x18005efdf  mov     r8, rsi
0x18005efe2  mov     rcx, r15
0x18005efe5  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18005efea  xor     ebx, ebx
0x18005efec  mov     rcx, r14; hObject
0x18005efef  call    cs:__imp_CloseHandle
0x18005eff5  nop
0x18005eff6  lea     rcx, [rbp+lpBuffer]
0x18005effa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005efff  mov     eax, ebx
0x18005f001  mov     rbx, [rsp+60h+arg_0]
0x18005f009  add     rsp, 60h
0x18005f00d  pop     r15
0x18005f00f  pop     r14
0x18005f011  pop     rdi
0x18005f012  pop     rsi
0x18005f013  pop     rbp
0x18005f014  retn
```
