# ReadFileToByteArray(ushort const *,uchar * *,ulong *)

- ea: `0x18004504c`
- end: `0x18004515d`
- name: `?ReadFileToByteArray@@YAJPEBGPEAPEAEPEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800445fc`

## callees

- `0x18000ac48`
- `0x18004504c`
- `0x180045164`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045141`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004509d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004509d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180045112`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180045112`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800450c1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800450c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800450dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800450dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045136`

## pseudocode

```c
__int64 __fastcall ReadFileToByteArray(const unsigned __int16 *a1, unsigned __int8 **a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  int Error; // ebx
  DWORD FileSize; // eax
  SIZE_T v8; // rsi
  void *v9; // rax
  void *v10; // rdi
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  *a3 = 0;
  hFile = 0;
  FileW = CreateFileW(a1, 0x80000000, 0, 0, 3u, 0x80u, 0);
  Error = ResultFromWin32Handle(FileW, &hFile);
  if ( Error >= 0 )
  {
    FileSize = GetFileSize(hFile, 0);
    v8 = FileSize;
    if ( FileSize == -1 )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_11;
    }
    v9 = CoTaskMemAlloc(v8);
    v10 = v9;
    if ( !v9 )
    {
      Error = -2147024882;
LABEL_11:
      CloseHandle(hFile);
      return (unsigned int)Error;
    }
    NumberOfBytesRead = 0;
    if ( ReadFile(hFile, v9, v8, &NumberOfBytesRead, 0) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_10:
        CoTaskMemFree(v10);
        goto LABEL_11;
      }
    }
    *a2 = (unsigned __int8 *)v10;
    v10 = 0;
    *a3 = v8;
    goto LABEL_10;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004504c  mov     rax, rsp
0x18004504f  mov     [rax+8], rbx
0x180045053  mov     [rax+20h], rsi
0x180045057  push    rdi
0x180045058  push    r14
0x18004505a  push    r15
0x18004505c  sub     rsp, 40h
0x180045060  mov     qword ptr [rax-28h], 0
0x180045068  mov     r14, r8
0x18004506b  mov     r15, rdx
0x18004506e  mov     qword ptr [rdx], 0
0x180045075  mov     dword ptr [r8], 0
0x18004507c  mov     edx, 80000000h; dwDesiredAccess
0x180045081  mov     dword ptr [rax-30h], 80h
0x180045088  xor     r8d, r8d; dwShareMode
0x18004508b  xor     r9d, r9d; lpSecurityAttributes
0x18004508e  mov     dword ptr [rax-38h], 3
0x180045095  mov     qword ptr [rax+18h], 0
0x18004509d  call    cs:__imp_CreateFileW
0x1800450a3  mov     rcx, rax; void *
0x1800450a6  lea     rdx, [rsp+58h+hFile]; void **
0x1800450ab  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1800450b0  mov     ebx, eax
0x1800450b2  test    eax, eax
0x1800450b4  js      loc_180045147
0x1800450ba  mov     rcx, [rsp+58h+hFile]; hFile
0x1800450bf  xor     edx, edx; lpFileSizeHigh
0x1800450c1  call    cs:__imp_GetFileSize
0x1800450c7  mov     esi, eax
0x1800450c9  cmp     eax, 0FFFFFFFFh
0x1800450cc  jnz     short loc_1800450D9
0x1800450ce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800450d3  mov     ebx, eax
0x1800450d5  test    eax, eax
0x1800450d7  js      short loc_18004513C
0x1800450d9  mov     rcx, rsi; cb
0x1800450dc  call    cs:__imp_CoTaskMemAlloc
0x1800450e2  mov     rdi, rax
0x1800450e5  test    rax, rax
0x1800450e8  jnz     short loc_1800450F1
0x1800450ea  mov     ebx, 8007000Eh
0x1800450ef  jmp     short loc_18004513C
0x1800450f1  mov     rcx, [rsp+58h+hFile]; hFile
0x1800450f6  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800450fb  mov     r8d, esi; nNumberOfBytesToRead
0x1800450fe  mov     [rsp+58h+NumberOfBytesRead], 0
0x180045106  mov     rdx, rdi; lpBuffer
0x180045109  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180045112  call    cs:__imp_ReadFile
0x180045118  test    eax, eax
0x18004511a  jz      short loc_180045120
0x18004511c  xor     ebx, ebx
0x18004511e  jmp     short loc_18004512B
0x180045120  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045125  mov     ebx, eax
0x180045127  test    eax, eax
0x180045129  js      short loc_180045133
0x18004512b  mov     [r15], rdi
0x18004512e  xor     edi, edi
0x180045130  mov     [r14], esi
0x180045133  mov     rcx, rdi; pv
0x180045136  call    cs:__imp_CoTaskMemFree
0x18004513c  mov     rcx, [rsp+58h+hFile]; hObject
0x180045141  call    cs:__imp_CloseHandle
0x180045147  mov     rsi, [rsp+58h+arg_18]
0x18004514c  mov     eax, ebx
0x18004514e  mov     rbx, [rsp+58h+arg_0]
0x180045153  add     rsp, 40h
0x180045157  pop     r15
0x180045159  pop     r14
0x18004515b  pop     rdi
0x18004515c  retn
```
