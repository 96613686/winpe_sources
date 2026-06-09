# BufferWriter::CAsyncIO::IOCreateFile(unsigned __int64,ushort const *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x1800a5a00`
- end: `0x1800a5af7`
- name: `?IOCreateFile@CAsyncIO@BufferWriter@@QEAAPEAX_KPEBGPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `247`
- prototype: `void *__fastcall(BufferWriter::CAsyncIO *__hidden this, ULONG_PTR CompletionKey, LPCWSTR lpFileName, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a62d8`

## callees

- `0x1800a492c`
- `0x1800a5a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5ade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5ade`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a5a16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a5a16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a5a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a5a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5ab1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5ace`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5ab1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5ace`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5a74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5a74`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800a5a99`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800a5a99`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::IOCreateFile(
        BufferWriter::CAsyncIO *this,
        ULONG_PTR CompletionKey,
        LPCWSTR lpFileName,
        struct _SECURITY_ATTRIBUTES *a4)
{
  DWORD v7; // eax
  __int64 v8; // rbx
  HANDLE FileW; // rax
  char *IoCompletionPort; // rsi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 1) || (v7 = BufferWriter::CAsyncIO::Active(this)) == 0 )
  {
    FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 1u, 0x40000080u, 0);
    v8 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      IoCompletionPort = (char *)CreateIoCompletionPort(FileW, *((HANDLE *)this + 1), CompletionKey, 1u);
      if ( IoCompletionPort != *((char **)this + 1) )
      {
        CloseHandle((HANDLE)v8);
        v8 = -1;
        if ( (unsigned __int64)(IoCompletionPort - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(IoCompletionPort);
      }
    }
  }
  else
  {
    v8 = -1;
    SetLastError(v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v8;
}

```

## disassembly

```asm
0x1800a5a00  push    rbx
0x1800a5a02  push    rbp
0x1800a5a03  push    rsi
0x1800a5a04  push    rdi
0x1800a5a05  sub     rsp, 48h
0x1800a5a09  mov     rdi, rcx
0x1800a5a0c  mov     rbx, r8
0x1800a5a0f  add     rcx, 10h; lpCriticalSection
0x1800a5a13  mov     rsi, rdx
0x1800a5a16  call    cs:__imp_EnterCriticalSection
0x1800a5a1d  nop     dword ptr [rax+rax+00h]
0x1800a5a22  cmp     qword ptr [rdi+8], 0
0x1800a5a27  jnz     short loc_1800A5A4C
0x1800a5a29  mov     rcx, rdi; this
0x1800a5a2c  call    ?Active@CAsyncIO@BufferWriter@@QEAAKXZ; BufferWriter::CAsyncIO::Active(void)
0x1800a5a31  test    eax, eax
0x1800a5a33  jz      short loc_1800A5A4C
0x1800a5a35  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a5a39  mov     ecx, eax; dwErrCode
0x1800a5a3b  call    cs:__imp_SetLastError
0x1800a5a42  nop     dword ptr [rax+rax+00h]
0x1800a5a47  jmp     loc_1800A5ADA
0x1800a5a4c  xor     r9d, r9d; lpSecurityAttributes
0x1800a5a4f  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800a5a58  mov     [rsp+68h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1800a5a60  mov     edx, 40000000h; dwDesiredAccess
0x1800a5a65  mov     rcx, rbx; lpFileName
0x1800a5a68  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x1800a5a70  lea     r8d, [r9+1]; dwShareMode
0x1800a5a74  call    cs:__imp_CreateFileW
0x1800a5a7b  nop     dword ptr [rax+rax+00h]
0x1800a5a80  mov     rbx, rax
0x1800a5a83  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5a87  jz      short loc_1800A5ADA
0x1800a5a89  mov     rdx, [rdi+8]; ExistingCompletionPort
0x1800a5a8d  mov     r9d, 1; NumberOfConcurrentThreads
0x1800a5a93  mov     r8, rsi; CompletionKey
0x1800a5a96  mov     rcx, rax; FileHandle
0x1800a5a99  call    cs:__imp_CreateIoCompletionPort
0x1800a5aa0  nop     dword ptr [rax+rax+00h]
0x1800a5aa5  mov     rsi, rax
0x1800a5aa8  cmp     rax, [rdi+8]
0x1800a5aac  jz      short loc_1800A5ADA
0x1800a5aae  mov     rcx, rbx; hObject
0x1800a5ab1  call    cs:__imp_CloseHandle
0x1800a5ab8  nop     dword ptr [rax+rax+00h]
0x1800a5abd  lea     rdx, [rsi-1]
0x1800a5ac1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a5ac5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a5ac9  ja      short loc_1800A5ADA
0x1800a5acb  mov     rcx, rsi; hObject
0x1800a5ace  call    cs:__imp_CloseHandle
0x1800a5ad5  nop     dword ptr [rax+rax+00h]
0x1800a5ada  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800a5ade  call    cs:__imp_LeaveCriticalSection
0x1800a5ae5  nop     dword ptr [rax+rax+00h]
0x1800a5aea  mov     rax, rbx
0x1800a5aed  add     rsp, 48h
0x1800a5af1  pop     rdi
0x1800a5af2  pop     rsi
0x1800a5af3  pop     rbp
0x1800a5af4  pop     rbx
0x1800a5af5  retn
```
