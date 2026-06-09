# DsRolepTreeCopy

- ea: `0x18000de20`
- end: `0x18000e111`
- name: `DsRolepTreeCopy`
- size: `753`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c600`
- `0x18000da70`
- `0x18000de20`

## callees

- `0x18000beb8`
- `0x18000c350`
- `0x18000de20`
- `0x180020dbc`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000e029`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000e029`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000dea8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000dea8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000dfba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000dfba`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e09a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000deb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000deb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e076`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000dffe`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000dffe`
- `ntdll!RtlFreeHeap` at `0x18000df68`
- `ntdll!RtlFreeHeap` at `0x18000dfa3`
- `ntdll!RtlFreeHeap` at `0x18000e0c1`
- `ntdll!RtlFreeHeap` at `0x18000e0de`
- `ntdll!RtlFreeHeap` at `0x18000df68`
- `ntdll!RtlFreeHeap` at `0x18000dfa3`
- `ntdll!RtlFreeHeap` at `0x18000e0c1`
- `ntdll!RtlFreeHeap` at `0x18000e0de`

## string_xrefs

- `0x18000dfcd`: `CreateDirectory on %ws failed with %lu\n`
- `0x18000e07f`: `CopyFile from %ws to %ws failed with %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepTreeCopy(__int64 a1, __int64 a2, unsigned int a3)
{
  WCHAR *v5; // rsi
  int v6; // eax
  WCHAR *v7; // rdi
  __int64 LastError; // rbx
  HANDLE FirstFileW; // r15
  int v10; // edx
  int v11; // edx
  DWORD v12; // eax
  unsigned int v13; // r14d
  LPCWSTR lpPathName; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  v17 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = 0;
  lpFileName = 0;
  lpPathName = 0;
  v6 = DsRolepAllocAndCopyPath(a1, L"*.*", &lpFileName);
  v7 = (WCHAR *)lpFileName;
  LODWORD(LastError) = v6;
  if ( !v6 )
  {
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(1, "FindFirstFile on %ws failed with %lu\n", a1, LastError);
    }
    else
    {
      while ( !(_DWORD)LastError )
      {
        v10 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v10 = FindFileData.cFileName[1];
        if ( v10 )
        {
          v11 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v11 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v11 = FindFileData.cFileName[2];
          }
          if ( v11 )
          {
            LODWORD(LastError) = DsRolepAllocAndCopyPath(a1, FindFileData.cFileName, &lpPathName);
            if ( (_DWORD)LastError )
              break;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
            v7 = (WCHAR *)lpPathName;
            LODWORD(LastError) = DsRolepAllocAndCopyPath(v17, FindFileData.cFileName, &lpPathName);
            if ( (_DWORD)LastError )
              break;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
            v5 = (WCHAR *)lpPathName;
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              if ( CreateDirectoryW(lpPathName, 0) )
              {
                LODWORD(LastError) = DsRolepTreeCopy(v7, v5, a3);
              }
              else
              {
                LastError = GetLastError();
                DsRolepLogPrintRoutine(1, "CreateDirectory on %ws failed with %lu\n", v5, LastError);
              }
            }
            else if ( !CopyFileW(v7, lpPathName, 0) )
            {
              LODWORD(LastError) = GetLastError();
              DsRolepLogPrintRoutine(1, "CopyFile from %ws to %ws failed with %lu\n", v7, v5, LastError);
              break;
            }
            if ( a3 )
              DsRolepCopyFileAttributes(v7, v5);
            if ( (_DWORD)LastError )
              break;
          }
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          v12 = GetLastError();
          LODWORD(LastError) = v12;
          if ( v12 )
          {
            if ( v12 != 18 )
              DsRolepLogPrintRoutine(1, "FindNextFile after on %ws failed with %lu\n", FindFileData.cFileName, v12);
          }
        }
      }
      FindClose(FirstFileW);
    }
  }
  v13 = 0;
  if ( (_DWORD)LastError != 18 )
    v13 = LastError;
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v13;
}

```

## disassembly

```asm
0x18000de20  mov     [rsp-8+arg_18], rbx
0x18000de25  push    rbp
0x18000de26  push    rsi
0x18000de27  push    rdi
0x18000de28  push    r12
0x18000de2a  push    r13
0x18000de2c  push    r14
0x18000de2e  push    r15
0x18000de30  lea     rbp, [rsp-1B0h]
0x18000de38  sub     rsp, 2B0h
0x18000de3f  mov     rax, cs:__security_cookie
0x18000de46  xor     rax, rsp
0x18000de49  mov     [rbp+1E0h+var_40], rax
0x18000de50  mov     r13d, r8d
0x18000de53  mov     [rsp+2E0h+var_2A0], rdx
0x18000de58  mov     r12, rcx
0x18000de5b  xor     edx, edx; Val
0x18000de5d  mov     r8d, 250h; Size
0x18000de63  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x18000de68  call    memset_0
0x18000de6d  xor     esi, esi
0x18000de6f  mov     [rsp+2E0h+lpFileName], 0
0x18000de78  lea     r8, [rsp+2E0h+lpFileName]
0x18000de7d  mov     [rsp+2E0h+lpPathName], rsi
0x18000de82  lea     rdx, asc_18003D798; "*.*"
0x18000de89  mov     rcx, r12
0x18000de8c  call    DsRolepAllocAndCopyPath
0x18000de91  mov     rdi, [rsp+2E0h+lpFileName]
0x18000de96  mov     ebx, eax
0x18000de98  test    eax, eax
0x18000de9a  jnz     loc_18000E0A0
0x18000dea0  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18000dea5  mov     rcx, rdi; lpFileName
0x18000dea8  call    cs:__imp_FindFirstFileW
0x18000deae  mov     r15, rax
0x18000deb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000deb5  jnz     short loc_18000DED9
0x18000deb7  call    cs:__imp_GetLastError
0x18000debd  mov     r8, r12
0x18000dec0  lea     rdx, aFindfirstfileO; "FindFirstFile on %ws failed with %lu\n"
0x18000dec7  mov     r9d, eax
0x18000deca  lea     ecx, [rsi+1]
0x18000decd  mov     ebx, eax
0x18000decf  call    DsRolepLogPrintRoutine
0x18000ded4  jmp     loc_18000E0A0
0x18000ded9  mov     r14d, 1
0x18000dedf  mov     ecx, 2Eh ; '.'
0x18000dee4  test    ebx, ebx
0x18000dee6  jnz     loc_18000E097
0x18000deec  movzx   edx, [rsp+2E0h+FindFileData.cFileName]
0x18000def1  movzx   eax, cx
0x18000def4  sub     edx, eax
0x18000def6  jnz     short loc_18000DF07
0x18000def8  movzx   edx, [rsp+2E0h+FindFileData.cFileName+2]
0x18000defd  xor     eax, eax
0x18000deff  movzx   ecx, ax
0x18000df02  sub     edx, ecx
0x18000df04  lea     ecx, [rbx+2Eh]
0x18000df07  test    edx, edx
0x18000df09  jz      loc_18000E021
0x18000df0f  movzx   edx, [rsp+2E0h+FindFileData.cFileName]
0x18000df14  movzx   eax, cx
0x18000df17  sub     edx, eax
0x18000df19  jnz     short loc_18000DF32
0x18000df1b  movzx   edx, [rsp+2E0h+FindFileData.cFileName+2]
0x18000df20  movzx   eax, cx
0x18000df23  sub     edx, eax
0x18000df25  jnz     short loc_18000DF32
0x18000df27  movzx   edx, [rbp+1E0h+FindFileData.cFileName+4]
0x18000df2b  xor     eax, eax
0x18000df2d  movzx   ecx, ax
0x18000df30  sub     edx, ecx
0x18000df32  test    edx, edx
0x18000df34  jz      loc_18000E021
0x18000df3a  lea     r8, [rsp+2E0h+lpPathName]
0x18000df3f  mov     rcx, r12
0x18000df42  lea     rdx, [rsp+2E0h+FindFileData.cFileName]
0x18000df47  call    DsRolepAllocAndCopyPath
0x18000df4c  mov     ebx, eax
0x18000df4e  test    eax, eax
0x18000df50  jnz     loc_18000E097
0x18000df56  mov     rcx, gs:60h
0x18000df5f  mov     r8, rdi; P
0x18000df62  xor     edx, edx; Flags
0x18000df64  mov     rcx, [rcx+30h]; HeapHandle
0x18000df68  call    cs:__imp_RtlFreeHeap
0x18000df6e  mov     rcx, [rsp+2E0h+var_2A0]
0x18000df73  lea     r8, [rsp+2E0h+lpPathName]
0x18000df78  mov     rdi, [rsp+2E0h+lpPathName]
0x18000df7d  lea     rdx, [rsp+2E0h+FindFileData.cFileName]
0x18000df82  call    DsRolepAllocAndCopyPath
0x18000df87  mov     ebx, eax
0x18000df89  test    eax, eax
0x18000df8b  jnz     loc_18000E097
0x18000df91  mov     rcx, gs:60h
0x18000df9a  mov     r8, rsi; P
0x18000df9d  xor     edx, edx; Flags
0x18000df9f  mov     rcx, [rcx+30h]; HeapHandle
0x18000dfa3  call    cs:__imp_RtlFreeHeap
0x18000dfa9  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x18000dfae  mov     rsi, [rsp+2E0h+lpPathName]
0x18000dfb3  jz      short loc_18000DFF5
0x18000dfb5  xor     edx, edx; lpSecurityAttributes
0x18000dfb7  mov     rcx, rsi; lpPathName
0x18000dfba  call    cs:__imp_CreateDirectoryW
0x18000dfc0  test    eax, eax
0x18000dfc2  jnz     short loc_18000DFE3
0x18000dfc4  call    cs:__imp_GetLastError
0x18000dfca  mov     r8, rsi
0x18000dfcd  lea     rdx, aCreatedirector; "CreateDirectory on %ws failed with %lu"...
0x18000dfd4  mov     r9d, eax
0x18000dfd7  mov     ecx, r14d
0x18000dfda  mov     ebx, eax
0x18000dfdc  call    DsRolepLogPrintRoutine
0x18000dfe1  jmp     short loc_18000E008
0x18000dfe3  mov     r8d, r13d
0x18000dfe6  mov     rdx, rsi
0x18000dfe9  mov     rcx, rdi
0x18000dfec  call    DsRolepTreeCopy
0x18000dff1  mov     ebx, eax
0x18000dff3  jmp     short loc_18000E008
0x18000dff5  xor     r8d, r8d; bFailIfExists
0x18000dff8  mov     rdx, rsi; lpNewFileName
0x18000dffb  mov     rcx, rdi; lpExistingFileName
0x18000dffe  call    cs:__imp_CopyFileW
0x18000e004  test    eax, eax
0x18000e006  jz      short loc_18000E076
0x18000e008  test    r13d, r13d
0x18000e00b  jz      short loc_18000E018
0x18000e00d  mov     rdx, rsi; LPCWSTR
0x18000e010  mov     rcx, rdi; lpFileName
0x18000e013  call    DsRolepCopyFileAttributes
0x18000e018  mov     ecx, 2Eh ; '.'
0x18000e01d  test    ebx, ebx
0x18000e01f  jnz     short loc_18000E097
0x18000e021  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18000e026  mov     rcx, r15; hFindFile
0x18000e029  call    cs:__imp_FindNextFileW
0x18000e02f  mov     ecx, 2Eh ; '.'
0x18000e034  test    eax, eax
0x18000e036  jnz     loc_18000DEE4
0x18000e03c  call    cs:__imp_GetLastError
0x18000e042  mov     ebx, eax
0x18000e044  mov     ecx, 2Eh ; '.'
0x18000e049  test    eax, eax
0x18000e04b  jz      loc_18000DEE4
0x18000e051  cmp     eax, 12h
0x18000e054  jz      loc_18000DEE4
0x18000e05a  mov     r9d, eax
0x18000e05d  lea     r8, [rsp+2E0h+FindFileData.cFileName]
0x18000e062  lea     rdx, aFindnextfileAf; "FindNextFile after on %ws failed with %"...
0x18000e069  mov     ecx, r14d
0x18000e06c  call    DsRolepLogPrintRoutine
0x18000e071  jmp     loc_18000DEDF
0x18000e076  call    cs:__imp_GetLastError
0x18000e07c  mov     r9, rsi
0x18000e07f  lea     rdx, aCopyfileFromWs; "CopyFile from %ws to %ws failed with %l"...
0x18000e086  mov     r8, rdi
0x18000e089  mov     [rsp+2E0h+var_2C0], eax
0x18000e08d  mov     ecx, r14d
0x18000e090  mov     ebx, eax
0x18000e092  call    DsRolepLogPrintRoutine
0x18000e097  mov     rcx, r15; hFindFile
0x18000e09a  call    cs:__imp_FindClose
0x18000e0a0  xor     r14d, r14d
0x18000e0a3  cmp     ebx, 12h
0x18000e0a6  cmovnz  r14d, ebx
0x18000e0aa  test    rdi, rdi
0x18000e0ad  jz      short loc_18000E0C7
0x18000e0af  mov     rcx, gs:60h
0x18000e0b8  mov     r8, rdi; P
0x18000e0bb  xor     edx, edx; Flags
0x18000e0bd  mov     rcx, [rcx+30h]; HeapHandle
0x18000e0c1  call    cs:__imp_RtlFreeHeap
0x18000e0c7  test    rsi, rsi
0x18000e0ca  jz      short loc_18000E0E4
0x18000e0cc  mov     rcx, gs:60h
0x18000e0d5  mov     r8, rsi; P
0x18000e0d8  xor     edx, edx; Flags
0x18000e0da  mov     rcx, [rcx+30h]; HeapHandle
0x18000e0de  call    cs:__imp_RtlFreeHeap
0x18000e0e4  mov     eax, r14d
0x18000e0e7  mov     rcx, [rbp+1E0h+var_40]
0x18000e0ee  xor     rcx, rsp; StackCookie
0x18000e0f1  call    __security_check_cookie
0x18000e0f6  mov     rbx, [rsp+2E0h+arg_18]
0x18000e0fe  add     rsp, 2B0h
0x18000e105  pop     r15
0x18000e107  pop     r14
0x18000e109  pop     r13
0x18000e10b  pop     r12
0x18000e10d  pop     rdi
0x18000e10e  pop     rsi
0x18000e10f  pop     rbp
0x18000e110  retn
```
