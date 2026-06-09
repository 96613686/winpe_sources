# XML_READ_STREAM::GetUnicodeBuffer(void)

- ea: `0x18001db08`
- end: `0x18001dd18`
- name: `?GetUnicodeBuffer@XML_READ_STREAM@@AEAAJXZ`
- size: `528`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180026a50`

## callees

- `0x18001db08`
- `0x180059bd2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dca4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dca4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001dcc9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001dcc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbd6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001db55`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001db55`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001db97`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001db97`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001dcf8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001dcf8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001dbc9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001dbc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd01`

## pseudocode

```c
__int64 __fastcall XML_READ_STREAM::GetUnicodeBuffer(HANDLE *this)
{
  HANDLE FileMappingW; // rax
  void *v3; // r12
  signed int v4; // eax
  unsigned int v5; // ebx
  _DWORD *v6; // r14
  signed int LastError; // eax
  DWORD FileSize; // eax
  SIZE_T v9; // rsi
  signed int v10; // eax
  int v11; // edx
  int v12; // r15d
  size_t v13; // rbx
  HANDLE ProcessHeap; // rax
  void *v15; // rax
  unsigned int v16; // esi
  size_t v17; // r8
  const void *v18; // rdx
  HANDLE v19; // rax
  WCHAR *v20; // rax
  int v21; // eax
  HANDLE v22; // rdx
  int v23; // ecx

  FileMappingW = CreateFileMappingW(this[5], 0, 2u, 0, 0, 0);
  v3 = FileMappingW;
  if ( FileMappingW )
  {
    v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    if ( !v6 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_31;
    }
    FileSize = GetFileSize(this[5], 0);
    v9 = FileSize;
    if ( FileSize == -1 )
      goto LABEL_8;
    v11 = 0;
    v12 = 0;
    if ( FileSize < 2 )
    {
      if ( !FileSize )
      {
        v5 = -2147024809;
        goto LABEL_30;
      }
    }
    else if ( *(_WORD *)v6 == 0xFFFE || *(_WORD *)v6 == 0xFEFF )
    {
      v11 = 1;
      v12 = 1;
    }
    else if ( FileSize >= 4 && (*v6 == 1056979968 || *v6 == 4128828) )
    {
      v11 = 1;
    }
    v13 = FileSize;
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      v15 = HeapAlloc(ProcessHeap, 0, v9);
      this[6] = v15;
      if ( !v15 )
      {
LABEL_19:
        v5 = -2147024888;
LABEL_30:
        UnmapViewOfFile(v6);
LABEL_31:
        CloseHandle(v3);
        return v5;
      }
      v16 = v9 - 2;
      *((_DWORD *)this + 3) = v16 >> 1;
      if ( v12 )
      {
        v17 = v16;
        v18 = (char *)v6 + 2;
      }
      else
      {
        v17 = v13;
        v18 = v6;
      }
      memcpy_0(v15, v18, v17);
    }
    else
    {
      v19 = GetProcessHeap();
      v20 = (WCHAR *)HeapAlloc(v19, 0, 2 * v9);
      this[6] = v20;
      if ( !v20 )
        goto LABEL_19;
      v21 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v6, v9, v20, v9);
      *((_DWORD *)this + 3) = v21;
      if ( !v21 )
      {
LABEL_8:
        v10 = GetLastError();
        v5 = v10;
        if ( v10 > 0 )
          v5 = (unsigned __int16)v10 | 0x80070000;
        goto LABEL_30;
      }
    }
    v22 = this[6];
    v5 = 0;
    v23 = *((_DWORD *)this + 3);
    this[3] = v22;
    this[4] = v22;
    *((_DWORD *)this + 5) = v23;
    *((_DWORD *)this + 4) = 1;
    goto LABEL_30;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x18001db08  push    rbp
0x18001db0a  push    rbx
0x18001db0b  push    rsi
0x18001db0c  push    rdi
0x18001db0d  push    r12
0x18001db0f  push    r14
0x18001db11  push    r15
0x18001db13  mov     rbp, rsp
0x18001db16  sub     rsp, 30h
0x18001db1a  xor     r9d, r9d; dwMaximumSizeHigh
0x18001db1d  mov     [rsp+30h+lpName], 0; lpName
0x18001db26  mov     rdi, rcx
0x18001db29  mov     [rbp+arg_0], 0FFFEh
0x18001db2f  mov     rcx, [rcx+28h]; hFile
0x18001db33  xor     edx, edx; lpFileMappingAttributes
0x18001db35  mov     [rbp+arg_8], 0FEFFh
0x18001db3b  lea     r8d, [r9+2]; flProtect
0x18001db3f  mov     [rbp+arg_10], 3F003C00h
0x18001db46  mov     [rbp+arg_18], 3F003Ch
0x18001db4d  mov     [rsp+30h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18001db55  call    cs:__imp_CreateFileMappingW
0x18001db5b  mov     r12, rax
0x18001db5e  test    rax, rax
0x18001db61  jnz     short loc_18001DB81
0x18001db63  call    cs:__imp_GetLastError
0x18001db69  mov     ebx, eax
0x18001db6b  test    eax, eax
0x18001db6d  jle     loc_18001DD07
0x18001db73  movzx   ebx, ax
0x18001db76  or      ebx, 80070000h
0x18001db7c  jmp     loc_18001DD07
0x18001db81  xor     r9d, r9d; dwFileOffsetLow
0x18001db84  mov     qword ptr [rsp+30h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001db8d  xor     r8d, r8d; dwFileOffsetHigh
0x18001db90  mov     rcx, r12; hFileMappingObject
0x18001db93  lea     edx, [r9+4]; dwDesiredAccess
0x18001db97  call    cs:__imp_MapViewOfFile
0x18001db9d  mov     r14, rax
0x18001dba0  test    rax, rax
0x18001dba3  jnz     short loc_18001DBC3
0x18001dba5  call    cs:__imp_GetLastError
0x18001dbab  mov     ebx, eax
0x18001dbad  test    eax, eax
0x18001dbaf  jle     loc_18001DCFE
0x18001dbb5  movzx   ebx, ax
0x18001dbb8  or      ebx, 80070000h
0x18001dbbe  jmp     loc_18001DCFE
0x18001dbc3  mov     rcx, [rdi+28h]; hFile
0x18001dbc7  xor     edx, edx; lpFileSizeHigh
0x18001dbc9  call    cs:__imp_GetFileSize
0x18001dbcf  mov     esi, eax
0x18001dbd1  cmp     eax, 0FFFFFFFFh
0x18001dbd4  jnz     short loc_18001DBF4
0x18001dbd6  call    cs:__imp_GetLastError
0x18001dbdc  mov     ebx, eax
0x18001dbde  test    eax, eax
0x18001dbe0  jle     loc_18001DCF5
0x18001dbe6  movzx   ebx, ax
0x18001dbe9  or      ebx, 80070000h
0x18001dbef  jmp     loc_18001DCF5
0x18001dbf4  xor     edx, edx
0x18001dbf6  xor     r15d, r15d
0x18001dbf9  lea     r8d, [rdx+1]
0x18001dbfd  cmp     esi, 2
0x18001dc00  jb      short loc_18001DC60
0x18001dc02  movzx   ecx, word ptr [r14]
0x18001dc06  cmp     cx, [rbp+arg_0]
0x18001dc0a  jz      short loc_18001DC58
0x18001dc0c  cmp     cx, [rbp+arg_8]
0x18001dc10  jz      short loc_18001DC58
0x18001dc12  cmp     esi, 4
0x18001dc15  jb      short loc_18001DC27
0x18001dc17  mov     eax, [r14]
0x18001dc1a  cmp     eax, [rbp+arg_10]
0x18001dc1d  jz      short loc_18001DC24
0x18001dc1f  cmp     eax, [rbp+arg_18]
0x18001dc22  jnz     short loc_18001DC27
0x18001dc24  mov     edx, r8d
0x18001dc27  mov     rbx, rsi
0x18001dc2a  test    edx, edx
0x18001dc2c  jz      short loc_18001DC93
0x18001dc2e  call    cs:__imp_GetProcessHeap
0x18001dc34  mov     r8, rbx; dwBytes
0x18001dc37  xor     edx, edx; dwFlags
0x18001dc39  mov     rcx, rax; hHeap
0x18001dc3c  call    cs:__imp_HeapAlloc
0x18001dc42  mov     [rdi+30h], rax
0x18001dc46  mov     rcx, rax; void *
0x18001dc49  test    rax, rax
0x18001dc4c  jnz     short loc_18001DC6E
0x18001dc4e  mov     ebx, 80070008h
0x18001dc53  jmp     loc_18001DCF5
0x18001dc58  mov     edx, r8d
0x18001dc5b  mov     r15d, r8d
0x18001dc5e  jmp     short loc_18001DC27
0x18001dc60  test    eax, eax
0x18001dc62  jnz     short loc_18001DC27
0x18001dc64  mov     ebx, 80070057h
0x18001dc69  jmp     loc_18001DCF5
0x18001dc6e  add     esi, 0FFFFFFFEh
0x18001dc71  mov     eax, esi
0x18001dc73  shr     eax, 1
0x18001dc75  mov     [rdi+0Ch], eax
0x18001dc78  test    r15d, r15d
0x18001dc7b  jz      short loc_18001DC86
0x18001dc7d  mov     r8d, esi
0x18001dc80  lea     rdx, [r14+2]
0x18001dc84  jmp     short loc_18001DC8C
0x18001dc86  mov     r8, rbx; Size
0x18001dc89  mov     rdx, r14; Src
0x18001dc8c  call    memcpy_0
0x18001dc91  jmp     short loc_18001DCDA
0x18001dc93  add     rbx, rbx
0x18001dc96  call    cs:__imp_GetProcessHeap
0x18001dc9c  mov     r8, rbx; dwBytes
0x18001dc9f  xor     edx, edx; dwFlags
0x18001dca1  mov     rcx, rax; hHeap
0x18001dca4  call    cs:__imp_HeapAlloc
0x18001dcaa  mov     [rdi+30h], rax
0x18001dcae  test    rax, rax
0x18001dcb1  jz      short loc_18001DC4E
0x18001dcb3  mov     dword ptr [rsp+30h+lpName], esi; cchWideChar
0x18001dcb7  mov     r9d, esi; cbMultiByte
0x18001dcba  mov     r8, r14; lpMultiByteStr
0x18001dcbd  mov     qword ptr [rsp+30h+dwMaximumSizeLow], rax; lpWideCharStr
0x18001dcc2  xor     edx, edx; dwFlags
0x18001dcc4  mov     ecx, 0FDE9h; CodePage
0x18001dcc9  call    cs:__imp_MultiByteToWideChar
0x18001dccf  mov     [rdi+0Ch], eax
0x18001dcd2  test    eax, eax
0x18001dcd4  jz      loc_18001DBD6
0x18001dcda  mov     rdx, [rdi+30h]
0x18001dcde  xor     ebx, ebx
0x18001dce0  mov     ecx, [rdi+0Ch]
0x18001dce3  mov     [rdi+18h], rdx
0x18001dce7  mov     [rdi+20h], rdx
0x18001dceb  mov     [rdi+14h], ecx
0x18001dcee  mov     dword ptr [rdi+10h], 1
0x18001dcf5  mov     rcx, r14; lpBaseAddress
0x18001dcf8  call    cs:__imp_UnmapViewOfFile
0x18001dcfe  mov     rcx, r12; hObject
0x18001dd01  call    cs:__imp_CloseHandle
0x18001dd07  mov     eax, ebx
0x18001dd09  add     rsp, 30h
0x18001dd0d  pop     r15
0x18001dd0f  pop     r14
0x18001dd11  pop     r12
0x18001dd13  pop     rdi
0x18001dd14  pop     rsi
0x18001dd15  pop     rbx
0x18001dd16  pop     rbp
0x18001dd17  retn
```
