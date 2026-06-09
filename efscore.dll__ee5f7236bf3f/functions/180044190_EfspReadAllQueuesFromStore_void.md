# EfspReadAllQueuesFromStore(void)

- ea: `0x180044190`
- end: `0x1800443e4`
- name: `?EfspReadAllQueuesFromStore@@YAJXZ`
- size: `596`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800424b0`

## callees

- `0x180005045`
- `0x180010bf0`
- `0x180044190`
- `0x180044888`
- `0x180044eac`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dddf0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180044276`
- `msvcrt!swprintf_s` at `0x180044276`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180044397`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180044397`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800442bb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800442bb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800443ad`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800443ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044337`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044389`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044337`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044389`

## string_xrefs

- `0x1800442ff`: `_temp`

## pseudocode

```c
__int64 EfspReadAllQueuesFromStore(void)
{
  int v0; // ecx
  int StoreFilePath; // ebx
  HANDLE FirstFileW; // rdi
  __int64 v3; // rcx
  _WIN32_FIND_DATAW *v4; // rcx
  wchar_t *i; // rdx
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  lpMem[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(Buffer, 0, 0x208u);
  fnEfsLogTrace1Strings(v0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 34, 232);
  StoreFilePath = GetStoreFilePath(0, 0, lpMem, 0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              StoreFilePath,
              34,
              232) >= 0 )
  {
    if ( swprintf_s(Buffer, 0x104u, L"%s\\%s", lpMem[0], L"*efsfeq*.db") == -1 )
    {
      StoreFilePath = -2147024883;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024883, 34, 245);
    }
    else
    {
      FirstFileW = FindFirstFileW(Buffer, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        do
        {
          v3 = -1;
          do
            ++v3;
          while ( FindFileData.cFileName[v3] );
          v4 = (_WIN32_FIND_DATAW *)&FindFileData.cFileName[v3 - 1];
          for ( i = L""; ; --i )
          {
            if ( v4 == (_WIN32_FIND_DATAW *)FindFileData.cFileName || i == L"_temp" )
            {
              DeleteFileW(FindFileData.cFileName);
              goto LABEL_15;
            }
            if ( LOWORD(v4->dwFileAttributes) != *i )
              break;
            v4 = (_WIN32_FIND_DATAW *)((char *)v4 - 2);
          }
          StoreFilePath = ReadQueueFromFile(lpMem[0], FindFileData.cFileName);
          if ( StoreFilePath < 0 )
          {
            DeleteFileW(FindFileData.cFileName);
            fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, StoreFilePath, 34, 25);
            StoreFilePath = 0;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 34, 26);
          }
LABEL_15:
          ;
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( FirstFileW )
          FindClose(FirstFileW);
      }
    }
  }
  if ( lpMem[0] )
    EfsFreeHeap(lpMem[0]);
  return (unsigned int)StoreFilePath;
}

```

## disassembly

```asm
0x180044190  push    rbp
0x180044192  push    rbx
0x180044193  push    rdi
0x180044194  push    r14
0x180044196  push    r15
0x180044198  lea     rbp, [rsp-3C0h]
0x1800441a0  sub     rsp, 4C0h
0x1800441a7  mov     rax, cs:__security_cookie
0x1800441ae  xor     rax, rsp
0x1800441b1  mov     [rbp+3E0h+var_30], rax
0x1800441b8  xor     r14d, r14d
0x1800441bb  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x1800441c0  xor     edx, edx; Val
0x1800441c2  mov     [rsp+4E0h+lpMem], r14
0x1800441c7  mov     r8d, 250h; Size
0x1800441cd  call    memset_0
0x1800441d2  xor     edx, edx; Val
0x1800441d4  lea     rcx, [rbp+3E0h+Buffer]; void *
0x1800441db  mov     r8d, 208h; Size
0x1800441e1  call    memset_0
0x1800441e6  lea     r15d, [r14+22h]
0x1800441ea  mov     edi, 2E8h
0x1800441ef  mov     r9d, r15d
0x1800441f2  mov     dword ptr [rsp+4E0h+var_4C0], edi
0x1800441f6  lea     r8, sourceString
0x1800441fd  lea     rdx, EFS_TRACE_START_EVENT
0x180044204  call    fnEfsLogTrace1Strings
0x180044209  xor     r9d, r9d
0x18004420c  lea     r8, [rsp+4E0h+lpMem]
0x180044211  xor     edx, edx
0x180044213  xor     ecx, ecx
0x180044215  call    GetStoreFilePath
0x18004421a  mov     rcx, cs:g_hPublisher
0x180044221  lea     r9, sourceString
0x180044228  mov     [rsp+4E0h+var_4B0], edi
0x18004422c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180044233  mov     [rsp+4E0h+var_4B8], r15d
0x180044238  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18004423f  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x180044243  mov     ebx, eax
0x180044245  call    fnEfsLogTrace1String1Dword
0x18004424a  test    eax, eax
0x18004424c  js      loc_1800443B3
0x180044252  mov     r9, [rsp+4E0h+lpMem]
0x180044257  lea     rax, aEfsfeqDb; "*efsfeq*.db"
0x18004425e  lea     r8, aSS; "%s\\%s"
0x180044265  mov     [rsp+4E0h+var_4C0], rax
0x18004426a  mov     edx, 104h; BufferCount
0x18004426f  lea     rcx, [rbp+3E0h+Buffer]; Buffer
0x180044276  call    cs:__imp_swprintf_s
0x18004427c  cmp     eax, 0FFFFFFFFh
0x18004427f  jnz     short loc_1800442AF
0x180044281  mov     rcx, cs:g_hPublisher
0x180044288  lea     rdx, EFS_TRACE_ERROR
0x18004428f  mov     r9d, r15d
0x180044292  mov     dword ptr [rsp+4E0h+var_4C0], 2F5h
0x18004429a  mov     r8d, 8007000Dh
0x1800442a0  mov     ebx, 8007000Dh
0x1800442a5  call    fnEfsLogTrace1
0x1800442aa  jmp     loc_1800443B3
0x1800442af  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x1800442b4  lea     rcx, [rbp+3E0h+Buffer]; lpFileName
0x1800442bb  call    cs:__imp_FindFirstFileW
0x1800442c1  mov     rdi, rax
0x1800442c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800442c8  jz      loc_1800443B3
0x1800442ce  lea     rax, [rsp+4E0h+FindFileData.cFileName]
0x1800442d3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800442d7  inc     rcx
0x1800442da  cmp     [rax+rcx*2], r14w
0x1800442df  jnz     short loc_1800442D7
0x1800442e1  lea     rdx, [rsp+4E0h+FindFileData.dwReserved1+2]
0x1800442e6  lea     rcx, [rdx+rcx*2]
0x1800442ea  lea     rdx, aTemp+0Ah; ""
0x1800442f1  lea     rax, [rsp+4E0h+FindFileData.cFileName]
0x1800442f6  cmp     rcx, rax
0x1800442f9  jz      loc_180044384
0x1800442ff  lea     rax, aTemp; "_temp"
0x180044306  cmp     rdx, rax
0x180044309  jz      short loc_180044384
0x18004430b  movzx   eax, word ptr [rdx]
0x18004430e  cmp     [rcx], ax
0x180044311  jnz     short loc_18004431D
0x180044313  sub     rdx, 2
0x180044317  sub     rcx, 2
0x18004431b  jmp     short loc_1800442F1
0x18004431d  mov     rcx, [rsp+4E0h+lpMem]
0x180044322  lea     rdx, [rsp+4E0h+FindFileData.cFileName]
0x180044327  call    ReadQueueFromFile
0x18004432c  mov     ebx, eax
0x18004432e  test    eax, eax
0x180044330  jns     short loc_18004438F
0x180044332  lea     rcx, [rsp+4E0h+FindFileData.cFileName]; lpFileName
0x180044337  call    cs:__imp_DeleteFileW
0x18004433d  mov     rcx, cs:g_hPublisher
0x180044344  lea     rdx, EFS_API_ERROR
0x18004434b  mov     r9d, r15d
0x18004434e  mov     dword ptr [rsp+4E0h+var_4C0], 319h
0x180044356  mov     r8d, ebx
0x180044359  call    fnEfsLogTrace1
0x18004435e  mov     rcx, cs:g_hPublisher
0x180044365  lea     rdx, EFS_TRACE_STATUS
0x18004436c  mov     r9d, r15d
0x18004436f  mov     dword ptr [rsp+4E0h+var_4C0], 31Ah
0x180044377  xor     r8d, r8d
0x18004437a  mov     ebx, r14d
0x18004437d  call    fnEfsLogTrace1
0x180044382  jmp     short loc_18004438F
0x180044384  lea     rcx, [rsp+4E0h+FindFileData.cFileName]; lpFileName
0x180044389  call    cs:__imp_DeleteFileW
0x18004438f  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x180044394  mov     rcx, rdi; hFindFile
0x180044397  call    cs:__imp_FindNextFileW
0x18004439d  test    eax, eax
0x18004439f  jnz     loc_1800442CE
0x1800443a5  test    rdi, rdi
0x1800443a8  jz      short loc_1800443B3
0x1800443aa  mov     rcx, rdi; hFindFile
0x1800443ad  call    cs:__imp_FindClose
0x1800443b3  cmp     [rsp+4E0h+lpMem], r14
0x1800443b8  jz      short loc_1800443C4
0x1800443ba  mov     rcx, [rsp+4E0h+lpMem]; lpMem
0x1800443bf  call    EfsFreeHeap
0x1800443c4  mov     eax, ebx
0x1800443c6  mov     rcx, [rbp+3E0h+var_30]
0x1800443cd  xor     rcx, rsp; StackCookie
0x1800443d0  call    __security_check_cookie
0x1800443d5  add     rsp, 4C0h
0x1800443dc  pop     r15
0x1800443de  pop     r14
0x1800443e0  pop     rdi
0x1800443e1  pop     rbx
0x1800443e2  pop     rbp
0x1800443e3  retn
```
