# _CopyFile(ushort const *,ushort const *)

- ea: `0x18000da48`
- end: `0x18000dc2c`
- name: `?_CopyFile@@YAJPEBG0@Z`
- size: `484`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000d620`

## callees

- `0x180002a8c`
- `0x180005b60`
- `0x18000608c`
- `0x18000a750`
- `0x18000da48`
- `0x18000dc34`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000db6e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000db6e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000db48`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000db48`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000da7e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dabf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000da7e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dabf`

## pseudocode

```c
__int64 __fastcall _CopyFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char *FileW; // rdi
  const char *v4; // r9
  char *v5; // rbx
  const char *v6; // r9
  int v7; // eax
  unsigned int v8; // esi
  void *v9; // rdx
  void *v10; // rsi
  void *v11; // rdx
  const char *v12; // r9
  __int64 v14; // rdx
  void *v15; // rdx
  unsigned int v16; // ebx
  unsigned int LastError; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  void *v19; // [rsp+40h] [rbp-10h] BYREF
  void *v20; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+30h] BYREF
  LPVOID lpBuffer; // [rsp+88h] [rbp+38h] BYREF

  FileW = (char *)CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x8200000u, 0);
  v19 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x55,
                  (unsigned int)"minio\\profapi\\load.cpp",
                  v4);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    return LastError;
  }
  else
  {
    v5 = (char *)CreateFileW(a2, 0x1F01FFu, 0, 0, 2u, 0x80u, 0);
    v20 = v5;
    if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5E,
             (unsigned int)"minio\\profapi\\load.cpp",
             v6);
    }
    else
    {
      lpBuffer = 0;
      v7 = ResultFromHeapAlloc(0x2000u, &lpBuffer);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v10 = lpBuffer;
        while ( 1 )
        {
          NumberOfBytesRead = 0;
          if ( !ReadFile(FileW, v10, 0x2000u, &NumberOfBytesRead, 0) )
            break;
          if ( !NumberOfBytesRead )
            goto LABEL_11;
          if ( !WriteFile(v5, v10, NumberOfBytesRead, &NumberOfBytesRead, 0) )
          {
            v14 = 107;
            goto LABEL_16;
          }
          if ( !NumberOfBytesRead )
          {
LABEL_11:
            if ( v10 )
              wil::details::FreeProcessHeap((wil::details *)v10, v11);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
            return 0;
          }
        }
        v14 = 103;
LABEL_16:
        v16 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v14,
                (unsigned int)"minio\\profapi\\load.cpp",
                v12);
        if ( v10 )
          wil::details::FreeProcessHeap((wil::details *)v10, v15);
        v8 = v16;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x61,
          (unsigned int)"minio\\profapi\\load.cpp",
          (const char *)(unsigned int)v7,
          dwCreationDisposition);
        if ( lpBuffer )
          wil::details::FreeProcessHeap((wil::details *)lpBuffer, v9);
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    return v8;
  }
}

```

## disassembly

```asm
0x18000da48  mov     rax, rsp
0x18000da4b  mov     [rax+8], rbx
0x18000da4f  push    rbp
0x18000da50  push    rsi
0x18000da51  push    rdi
0x18000da52  mov     rbp, rsp
0x18000da55  sub     rsp, 50h
0x18000da59  mov     qword ptr [rax-38h], 0
0x18000da61  xor     r9d, r9d; lpSecurityAttributes
0x18000da64  mov     rbx, rdx
0x18000da67  mov     dword ptr [rax-40h], 8200000h
0x18000da6e  mov     edx, 80000000h; dwDesiredAccess
0x18000da73  mov     dword ptr [rax-48h], 3
0x18000da7a  lea     r8d, [r9+5]; dwShareMode
0x18000da7e  call    cs:__imp_CreateFileW
0x18000da84  mov     rdi, rax
0x18000da87  mov     [rbp+var_10], rax
0x18000da8b  dec     rax
0x18000da8e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000da92  ja      loc_18000DBFD
0x18000da98  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18000daa1  xor     r9d, r9d; lpSecurityAttributes
0x18000daa4  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000daac  xor     r8d, r8d; dwShareMode
0x18000daaf  mov     edx, 1F01FFh; dwDesiredAccess
0x18000dab4  mov     [rsp+50h+dwCreationDisposition], 2; int
0x18000dabc  mov     rcx, rbx; lpFileName
0x18000dabf  call    cs:__imp_CreateFileW
0x18000dac5  mov     rbx, rax
0x18000dac8  mov     [rbp+var_8], rax
0x18000dacc  dec     rax
0x18000dacf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dad3  ja      loc_18000DBD0
0x18000dad9  lea     rdx, [rbp+lpBuffer]; void **
0x18000dadd  mov     [rbp+lpBuffer], 0
0x18000dae5  mov     ecx, 2000h; dwBytes
0x18000daea  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000daef  mov     esi, eax
0x18000daf1  test    eax, eax
0x18000daf3  jns     short loc_18000DB24
0x18000daf5  mov     rcx, [rbp+18h]; this
0x18000daf9  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000db00  mov     r9d, eax; char *
0x18000db03  mov     edx, 61h ; 'a'; void *
0x18000db08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db0d  mov     rcx, [rbp+lpBuffer]; this
0x18000db11  test    rcx, rcx
0x18000db14  jz      loc_18000DBE7
0x18000db1a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000db1f  jmp     loc_18000DBE7
0x18000db24  mov     rsi, [rbp+lpBuffer]
0x18000db28  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000db2c  mov     [rbp+NumberOfBytesRead], 0
0x18000db33  mov     r8d, 2000h; nNumberOfBytesToRead
0x18000db39  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x18000db42  mov     rdx, rsi; lpBuffer
0x18000db45  mov     rcx, rdi; hFile
0x18000db48  call    cs:__imp_ReadFile
0x18000db4e  test    eax, eax
0x18000db50  jz      short loc_18000DBA8
0x18000db52  mov     r8d, [rbp+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18000db56  test    r8d, r8d
0x18000db59  jz      short loc_18000DB7E
0x18000db5b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18000db5f  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x18000db68  mov     rdx, rsi; lpBuffer
0x18000db6b  mov     rcx, rbx; hFile
0x18000db6e  call    cs:__imp_WriteFile
0x18000db74  test    eax, eax
0x18000db76  jz      short loc_18000DBA1
0x18000db78  cmp     [rbp+NumberOfBytesRead], 0
0x18000db7c  jnz     short loc_18000DB28
0x18000db7e  test    rsi, rsi
0x18000db81  jz      short loc_18000DB8B
0x18000db83  mov     rcx, rsi; this
0x18000db86  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000db8b  lea     rcx, [rbp+var_8]
0x18000db8f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000db94  lea     rcx, [rbp+var_10]
0x18000db98  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000db9d  xor     eax, eax
0x18000db9f  jmp     short loc_18000DC1F
0x18000dba1  mov     edx, 6Bh ; 'k'
0x18000dba6  jmp     short loc_18000DBAD
0x18000dba8  mov     edx, 67h ; 'g'; void *
0x18000dbad  mov     rcx, [rbp+18h]; this
0x18000dbb1  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000dbb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dbbd  mov     ebx, eax
0x18000dbbf  test    rsi, rsi
0x18000dbc2  jz      short loc_18000DBCC
0x18000dbc4  mov     rcx, rsi; this
0x18000dbc7  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000dbcc  mov     esi, ebx
0x18000dbce  jmp     short loc_18000DBE7
0x18000dbd0  mov     rcx, [rbp+18h]; this
0x18000dbd4  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000dbdb  mov     edx, 5Eh ; '^'; void *
0x18000dbe0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dbe5  mov     esi, eax
0x18000dbe7  lea     rcx, [rbp+var_8]
0x18000dbeb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000dbf0  lea     rcx, [rbp+var_10]
0x18000dbf4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000dbf9  mov     eax, esi
0x18000dbfb  jmp     short loc_18000DC1F
0x18000dbfd  mov     rcx, [rbp+18h]; this
0x18000dc01  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000dc08  mov     edx, 55h ; 'U'; void *
0x18000dc0d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dc12  lea     rcx, [rbp+var_10]
0x18000dc16  mov     ebx, eax
0x18000dc18  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000dc1d  mov     eax, ebx
0x18000dc1f  mov     rbx, [rsp+50h+arg_0]
0x18000dc24  add     rsp, 50h
0x18000dc28  pop     rdi
0x18000dc29  pop     rsi
0x18000dc2a  pop     rbp
0x18000dc2b  retn
```
