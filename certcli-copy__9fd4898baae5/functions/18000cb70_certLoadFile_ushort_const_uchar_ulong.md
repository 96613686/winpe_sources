# certLoadFile(ushort const *,uchar * *,ulong *)

- ea: `0x18000cb70`
- end: `0x18000cca2`
- name: `?certLoadFile@@YAJPEBGPEAPEAEPEAK@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ca50`

## callees

- `0x18000cb70`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cc1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cc1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cbbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cbbc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000cbf3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000cbf3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000cc4e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000cc4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc87`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000cc0e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000cc0e`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000cbdd`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000cbdd`

## pseudocode

```c
__int64 __fastcall certLoadFile(const unsigned __int16 *a1, HLOCAL *a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v7; // rsi
  unsigned int v8; // ebx
  DWORD FileSize; // eax
  __int64 v10; // rbx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned __int8 *v13; // rax
  _BYTE *v14; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-28h] BYREF
  DWORD FileSizeHigh; // [rsp+88h] [rbp+20h] BYREF

  FileSizeHigh = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v10 = FileSize;
    if ( FileSize == -1 )
    {
      v8 = myHLastError();
      v11 = v8;
      v12 = 153748161;
    }
    else
    {
      v13 = (unsigned __int8 *)LocalAlloc(0, FileSize + 1);
      *a2 = v13;
      if ( v13 )
      {
        if ( ReadFile(v7, v13, v10, &NumberOfBytesRead, 0) )
        {
          v14 = *a2;
          *a3 = v10;
          v14[v10] = 0;
          v8 = 0;
          goto LABEL_11;
        }
        v8 = myHLastError();
        LocalFree(*a2);
        v11 = v8;
        *a2 = 0;
        v12 = 154731201;
      }
      else
      {
        v8 = -2147024882;
        v12 = 154206913;
        v11 = -2147024882;
      }
    }
    CSPrintErrorLineFile(v12, v11);
LABEL_11:
    CloseHandle(v7);
    return v8;
  }
  v8 = myHLastError();
  CSPrintErrorLineFileData(a1, 0x92302C1u, v8);
  return v8;
}

```

## disassembly

```asm
0x18000cb70  mov     rax, rsp
0x18000cb73  mov     [rax+8], rbx
0x18000cb77  mov     [rax+10h], rbp
0x18000cb7b  push    rsi
0x18000cb7c  push    rdi
0x18000cb7d  push    r14
0x18000cb7f  sub     rsp, 50h
0x18000cb83  mov     qword ptr [rax-38h], 0
0x18000cb8b  xor     r9d, r9d; lpSecurityAttributes
0x18000cb8e  mov     r14, r8
0x18000cb91  mov     dword ptr [rax-40h], 80h
0x18000cb98  mov     rdi, rdx
0x18000cb9b  mov     dword ptr [rax+20h], 0
0x18000cba2  mov     edx, 80000000h; dwDesiredAccess
0x18000cba7  mov     dword ptr [rax-28h], 0
0x18000cbae  lea     r8d, [r9+1]; dwShareMode
0x18000cbb2  mov     dword ptr [rax-48h], 3
0x18000cbb9  mov     rbp, rcx
0x18000cbbc  call    cs:__imp_CreateFileW
0x18000cbc2  mov     rsi, rax
0x18000cbc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cbc9  jnz     short loc_18000CBE8
0x18000cbcb  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000cbd0  mov     r8d, eax
0x18000cbd3  mov     edx, 92302C1h
0x18000cbd8  mov     rcx, rbp
0x18000cbdb  mov     ebx, eax
0x18000cbdd  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18000cbe3  jmp     loc_18000CC8D
0x18000cbe8  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x18000cbf0  mov     rcx, rsi; hFile
0x18000cbf3  call    cs:__imp_GetFileSize
0x18000cbf9  mov     ebx, eax
0x18000cbfb  cmp     eax, 0FFFFFFFFh
0x18000cbfe  jnz     short loc_18000CC16
0x18000cc00  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000cc05  mov     ebx, eax
0x18000cc07  mov     edx, eax
0x18000cc09  mov     ecx, 92A02C1h
0x18000cc0e  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000cc14  jmp     short loc_18000CC84
0x18000cc16  lea     edx, [rbx+1]; uBytes
0x18000cc19  xor     ecx, ecx; uFlags
0x18000cc1b  call    cs:__imp_LocalAlloc
0x18000cc21  mov     [rdi], rax
0x18000cc24  test    rax, rax
0x18000cc27  jnz     short loc_18000CC37
0x18000cc29  mov     ebx, 8007000Eh
0x18000cc2e  mov     ecx, 93102C1h
0x18000cc33  mov     edx, ebx
0x18000cc35  jmp     short loc_18000CC0E
0x18000cc37  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000cc3c  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000cc45  mov     r8d, ebx; nNumberOfBytesToRead
0x18000cc48  mov     rdx, rax; lpBuffer
0x18000cc4b  mov     rcx, rsi; hFile
0x18000cc4e  call    cs:__imp_ReadFile
0x18000cc54  test    eax, eax
0x18000cc56  jnz     short loc_18000CC78
0x18000cc58  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000cc5d  mov     rcx, [rdi]; hMem
0x18000cc60  mov     ebx, eax
0x18000cc62  call    cs:__imp_LocalFree
0x18000cc68  mov     edx, ebx
0x18000cc6a  mov     qword ptr [rdi], 0
0x18000cc71  mov     ecx, 93902C1h
0x18000cc76  jmp     short loc_18000CC0E
0x18000cc78  mov     rax, [rdi]
0x18000cc7b  mov     [r14], ebx
0x18000cc7e  mov     byte ptr [rbx+rax], 0
0x18000cc82  xor     ebx, ebx
0x18000cc84  mov     rcx, rsi; hObject
0x18000cc87  call    cs:__imp_CloseHandle
0x18000cc8d  mov     rbp, [rsp+68h+arg_8]
0x18000cc92  mov     eax, ebx
0x18000cc94  mov     rbx, [rsp+68h+arg_0]
0x18000cc99  add     rsp, 50h
0x18000cc9d  pop     r14
0x18000cc9f  pop     rdi
0x18000cca0  pop     rsi
0x18000cca1  retn
```
