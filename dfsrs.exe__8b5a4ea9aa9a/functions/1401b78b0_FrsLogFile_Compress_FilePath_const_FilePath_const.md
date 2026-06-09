# FrsLogFile::Compress(FilePath const &,FilePath const &)

- ea: `0x1401b78b0`
- end: `0x1401b7ba2`
- name: `?Compress@FrsLogFile@@AEAAPEAVFrsStatus@@AEBVFilePath@@0@Z`
- size: `754`
- prototype: `struct FrsStatus *__fastcall(FrsLogFile *__hidden this, const struct FilePath *, const struct FilePath *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1401b7dbc`

## callees

- `0x140005cd0`
- `0x140006420`
- `0x140006470`
- `0x14000ee94`
- `0x14002c548`
- `0x14006c740`
- `0x1401af7b0`
- `0x1401b78b0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1401b7b60`
- `KERNEL32!DeleteFileW` at `0x1401b7b60`
- `KERNEL32!CreateFileW` at `0x1401b7904`
- `KERNEL32!CreateFileW` at `0x1401b7904`
- `KERNEL32!ReadFile` at `0x1401b7a30`
- `KERNEL32!ReadFile` at `0x1401b7a30`
- `KERNEL32!CloseHandle` at `0x1401b7b40`
- `KERNEL32!CloseHandle` at `0x1401b7b40`
- `KERNEL32!GetLastError` at `0x1401b792b`
- `KERNEL32!GetLastError` at `0x1401b7a40`
- `KERNEL32!GetLastError` at `0x1401b7b6c`
- `KERNEL32!GetLastError` at `0x1401b792b`
- `KERNEL32!GetLastError` at `0x1401b7a40`
- `KERNEL32!GetLastError` at `0x1401b7b6c`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7939`
- `KERNEL32!GetCurrentThreadId` at `0x1401b79b7`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7a4e`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7acc`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7939`
- `KERNEL32!GetCurrentThreadId` at `0x1401b79b7`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7a4e`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7acc`

## string_xrefs

- `0x1401b7913`: `FrsLogFile::Compress`
- `0x1401b7a6b`: `FrsLogFile::Compress`
- `0x1401b7aea`: `FrsLogFile::Compress`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall FrsLogFile::Compress(
        FrsLogFile *this,
        const struct FilePath *a2,
        const struct FilePath *a3)
{
  __int64 v5; // rbx
  HANDLE FileW; // rsi
  __int64 v7; // r8
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rbp
  DWORD v13; // eax
  __int64 v14; // rcx
  char *v15; // r15
  DWORD v16; // edi
  DWORD v17; // ebx
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v20; // r8d
  int v21; // r14d
  DWORD v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+8h] BYREF
  int v27; // [rsp+94h] [rbp+Ch]
  char *v28; // [rsp+98h] [rbp+10h] BYREF
  char v29; // [rsp+A8h] [rbp+20h] BYREF

  v27 = HIDWORD(this);
  v5 = 0;
  v28 = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW((LPCWSTR)(*((_QWORD *)a2 + 1) + 18LL), 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CurrentThreadId = GetCurrentThreadId();
    v5 = FrsStatusList::PushNewError(
           v10,
           LastError,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
           "FrsLogFile::Compress",
           234,
           CurrentThreadId,
           0);
    if ( v5 )
      goto LABEL_21;
  }
  v11 = (_QWORD *)FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(
                    &v29,
                    *((_QWORD *)a3 + 1) + 18LL,
                    v7);
  v12 = gzopen(*v11 + 17LL, "wb6");
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v29);
  if ( v12
    || (v13 = GetCurrentThreadId(),
        (v5 = FrsStatusList::PushNewError(
                v14,
                5,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                "FrsLogFile::Compress",
                243,
                v13,
                0)) == 0) )
  {
    v15 = (char *)operator_new(0x10000u);
    v28 = v15;
    while ( 1 )
    {
      v16 = 0;
      if ( !ReadFile(FileW, v15, 0x10000u, &NumberOfBytesRead, 0) )
      {
        v17 = GetLastError();
        v18 = GetCurrentThreadId();
        v5 = FrsStatusList::PushNewError(
               v19,
               v17,
               0,
               1,
               "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
               "FrsLogFile::Compress",
               268,
               v18,
               0);
      }
      v20 = NumberOfBytesRead;
      if ( !NumberOfBytesRead || v5 )
        break;
      while ( v16 < v20 )
      {
        v21 = gzwrite(v12, &v15[v16], v20 - v16);
        if ( !v21 )
        {
          v22 = GetCurrentThreadId();
          v5 = FrsStatusList::PushNewError(
                 v23,
                 5,
                 0,
                 1,
                 "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                 "FrsLogFile::Compress",
                 283,
                 v22,
                 0);
        }
        v16 += v21;
        if ( v5 )
          goto LABEL_15;
        v20 = NumberOfBytesRead;
      }
    }
LABEL_15:
    if ( v12 )
      gzclose(v12);
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v5 )
LABEL_21:
    v24 = *((_QWORD *)a3 + 1);
  else
    v24 = *((_QWORD *)a2 + 1);
  DeleteFileW((LPCWSTR)(v24 + 18));
  GetLastError();
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v28);
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x1401b78b0  mov     rax, rsp
0x1401b78b3  mov     [rax+18h], rbx
0x1401b78b7  mov     [rax+8], rcx
0x1401b78bb  push    rbp
0x1401b78bc  push    rsi
0x1401b78bd  push    rdi
0x1401b78be  push    r12
0x1401b78c0  push    r13
0x1401b78c2  push    r14
0x1401b78c4  push    r15
0x1401b78c6  sub     rsp, 50h
0x1401b78ca  mov     r12, r8
0x1401b78cd  mov     r13, rdx
0x1401b78d0  xor     r14d, r14d
0x1401b78d3  mov     ebx, r14d
0x1401b78d6  mov     [rax+10h], r14
0x1401b78da  mov     [rax+8], r14d
0x1401b78de  mov     rcx, [rdx+8]
0x1401b78e2  add     rcx, 12h; lpFileName
0x1401b78e6  mov     [rax-58h], r14
0x1401b78ea  mov     dword ptr [rax-60h], 2000000h
0x1401b78f1  mov     dword ptr [rax-68h], 3
0x1401b78f8  xor     r9d, r9d; lpSecurityAttributes
0x1401b78fb  mov     edx, 80000000h; dwDesiredAccess
0x1401b7900  lea     r8d, [r14+7]; dwShareMode
0x1401b7904  call    cs:__imp_CreateFileW
0x1401b790b  nop     dword ptr [rax+rax+00h]
0x1401b7910  mov     rsi, rax
0x1401b7913  lea     r15, aFrslogfileComp; "FrsLogFile::Compress"
0x1401b791a  lea     rbp, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b7921  lea     edi, [r14+1]
0x1401b7925  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401b7929  jnz     short loc_1401B7979
0x1401b792b  call    cs:__imp_GetLastError
0x1401b7932  nop     dword ptr [rax+rax+00h]
0x1401b7937  mov     ebx, eax
0x1401b7939  call    cs:__imp_GetCurrentThreadId
0x1401b7940  nop     dword ptr [rax+rax+00h]
0x1401b7945  mov     [rsp+88h+var_48], r14
0x1401b794a  mov     [rsp+88h+var_50], eax
0x1401b794e  mov     [rsp+88h+var_58], 0EAh
0x1401b7956  mov     [rsp+88h+var_60], r15
0x1401b795b  mov     [rsp+88h+lpOverlapped], rbp
0x1401b7960  mov     r9d, edi
0x1401b7963  xor     r8d, r8d
0x1401b7966  mov     edx, ebx
0x1401b7968  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b796d  mov     rbx, rax
0x1401b7970  test    rax, rax
0x1401b7973  jnz     loc_1401B7B57
0x1401b7979  mov     rdx, [r12+8]
0x1401b797e  add     rdx, 12h
0x1401b7982  lea     rcx, [rsp+88h+arg_18]
0x1401b798a  call    ??0?$FrsStringImpl@DG@@QEAA@PEBG@Z; FrsStringImpl<char,ushort>::FrsStringImpl<char,ushort>(ushort const *)
0x1401b798f  mov     rcx, [rax]
0x1401b7992  add     rcx, 11h
0x1401b7996  lea     rdx, aWb6; "wb6"
0x1401b799d  call    gzopen
0x1401b79a2  mov     rbp, rax
0x1401b79a5  lea     rcx, [rsp+88h+arg_18]
0x1401b79ad  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401b79b2  test    rbp, rbp
0x1401b79b5  jnz     short loc_1401B79FF
0x1401b79b7  call    cs:__imp_GetCurrentThreadId
0x1401b79be  nop     dword ptr [rax+rax+00h]
0x1401b79c3  mov     [rsp+88h+var_48], r14
0x1401b79c8  mov     [rsp+88h+var_50], eax
0x1401b79cc  mov     [rsp+88h+var_58], 0F3h
0x1401b79d4  mov     [rsp+88h+var_60], r15
0x1401b79d9  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b79e0  mov     [rsp+88h+lpOverlapped], rax
0x1401b79e5  mov     r9d, edi
0x1401b79e8  xor     r8d, r8d
0x1401b79eb  lea     edx, [rbp+5]
0x1401b79ee  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b79f3  mov     rbx, rax
0x1401b79f6  test    rax, rax
0x1401b79f9  jnz     loc_1401B7B37
0x1401b79ff  mov     ecx, 10000h; unsigned __int64
0x1401b7a04  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401b7a09  mov     r15, rax
0x1401b7a0c  mov     [rsp+88h+arg_8], rax
0x1401b7a14  mov     edi, r14d
0x1401b7a17  mov     [rsp+88h+lpOverlapped], r14; lpOverlapped
0x1401b7a1c  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1401b7a24  mov     r8d, 10000h; nNumberOfBytesToRead
0x1401b7a2a  mov     rdx, r15; lpBuffer
0x1401b7a2d  mov     rcx, rsi; hFile
0x1401b7a30  call    cs:__imp_ReadFile
0x1401b7a37  nop     dword ptr [rax+rax+00h]
0x1401b7a3c  test    eax, eax
0x1401b7a3e  jnz     short loc_1401B7A96
0x1401b7a40  call    cs:__imp_GetLastError
0x1401b7a47  nop     dword ptr [rax+rax+00h]
0x1401b7a4c  mov     ebx, eax
0x1401b7a4e  call    cs:__imp_GetCurrentThreadId
0x1401b7a55  nop     dword ptr [rax+rax+00h]
0x1401b7a5a  mov     [rsp+88h+var_48], r14
0x1401b7a5f  mov     [rsp+88h+var_50], eax
0x1401b7a63  mov     [rsp+88h+var_58], 10Ch
0x1401b7a6b  lea     rax, aFrslogfileComp; "FrsLogFile::Compress"
0x1401b7a72  mov     [rsp+88h+var_60], rax
0x1401b7a77  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b7a7e  mov     [rsp+88h+lpOverlapped], rax
0x1401b7a83  mov     r9d, 1
0x1401b7a89  xor     r8d, r8d
0x1401b7a8c  mov     edx, ebx
0x1401b7a8e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b7a93  mov     rbx, rax
0x1401b7a96  mov     r8d, [rsp+88h+NumberOfBytesRead]
0x1401b7a9e  test    r8d, r8d
0x1401b7aa1  jz      loc_1401B7B2A
0x1401b7aa7  test    rbx, rbx
0x1401b7aaa  jnz     short loc_1401B7B2A
0x1401b7aac  cmp     edi, r8d
0x1401b7aaf  jnb     loc_1401B7A14
0x1401b7ab5  sub     r8d, edi
0x1401b7ab8  mov     edx, edi
0x1401b7aba  add     rdx, r15
0x1401b7abd  mov     rcx, rbp
0x1401b7ac0  call    gzwrite
0x1401b7ac5  mov     r14d, eax
0x1401b7ac8  test    eax, eax
0x1401b7aca  jnz     short loc_1401B7B15
0x1401b7acc  call    cs:__imp_GetCurrentThreadId
0x1401b7ad3  nop     dword ptr [rax+rax+00h]
0x1401b7ad8  and     [rsp+88h+var_48], 0
0x1401b7ade  mov     [rsp+88h+var_50], eax
0x1401b7ae2  mov     [rsp+88h+var_58], 11Bh
0x1401b7aea  lea     rax, aFrslogfileComp; "FrsLogFile::Compress"
0x1401b7af1  mov     [rsp+88h+var_60], rax
0x1401b7af6  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b7afd  mov     [rsp+88h+lpOverlapped], rax
0x1401b7b02  lea     r9d, [r14+1]
0x1401b7b06  xor     r8d, r8d
0x1401b7b09  lea     edx, [r14+5]
0x1401b7b0d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b7b12  mov     rbx, rax
0x1401b7b15  add     edi, r14d
0x1401b7b18  xor     r14d, r14d
0x1401b7b1b  test    rbx, rbx
0x1401b7b1e  jnz     short loc_1401B7B2A
0x1401b7b20  mov     r8d, [rsp+88h+NumberOfBytesRead]
0x1401b7b28  jmp     short loc_1401B7AAC
0x1401b7b2a  test    rbp, rbp
0x1401b7b2d  jz      short loc_1401B7B37
0x1401b7b2f  mov     rcx, rbp
0x1401b7b32  call    gzclose
0x1401b7b37  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1401b7b3b  jz      short loc_1401B7B4C
0x1401b7b3d  mov     rcx, rsi; hObject
0x1401b7b40  call    cs:__imp_CloseHandle
0x1401b7b47  nop     dword ptr [rax+rax+00h]
0x1401b7b4c  test    rbx, rbx
0x1401b7b4f  jnz     short loc_1401B7B57
0x1401b7b51  mov     rcx, [r13+8]
0x1401b7b55  jmp     short loc_1401B7B5C
0x1401b7b57  mov     rcx, [r12+8]
0x1401b7b5c  add     rcx, 12h; lpFileName
0x1401b7b60  call    cs:__imp_DeleteFileW
0x1401b7b67  nop     dword ptr [rax+rax+00h]
0x1401b7b6c  call    cs:__imp_GetLastError
0x1401b7b73  nop     dword ptr [rax+rax+00h]
0x1401b7b78  nop
0x1401b7b79  lea     rcx, [rsp+88h+arg_8]
0x1401b7b81  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401b7b86  mov     rax, rbx
0x1401b7b89  mov     rbx, [rsp+88h+arg_10]
0x1401b7b91  add     rsp, 50h
0x1401b7b95  pop     r15
0x1401b7b97  pop     r14
0x1401b7b99  pop     r13
0x1401b7b9b  pop     r12
0x1401b7b9d  pop     rdi
0x1401b7b9e  pop     rsi
0x1401b7b9f  pop     rbp
0x1401b7ba0  retn
```
