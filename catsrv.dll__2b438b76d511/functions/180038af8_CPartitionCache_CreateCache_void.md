# CPartitionCache::CreateCache(void)

- ea: `0x180038af8`
- end: `0x180038bdb`
- name: `?CreateCache@CPartitionCache@@AEAAJXZ`
- size: `227`
- prototype: `signed int __fastcall(CPartitionCache *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800389e8`

## callees

- `0x180038af8`
- `0x180038dec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bc3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180038b35`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180038ba7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180038b35`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180038ba7`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180038b0f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180038b82`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180038b0f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180038b82`

## pseudocode

```c
signed int __fastcall CPartitionCache::CreateCache(CPartitionCache *this)
{
  HANDLE v2; // rax
  LPVOID v3; // rax
  signed int result; // eax
  HANDLE v5; // rax
  LPVOID v6; // rax

  v2 = OpenFileMappingW(0x3001Fu, 0, L"Global\\{A64C7F33-DA35-459b-96CA-63B51FB0CDB9}");
  *((_QWORD *)this + 3) = v2;
  if ( v2 )
  {
    v3 = MapViewOfFile(v2, 0xF001Fu, 0, 0, 0);
    *((_QWORD *)this + 5) = v3;
    if ( v3 )
    {
      result = CPartitionCache::ReadInit(this);
      if ( result >= 0 )
        *((_DWORD *)this + 4) = 1;
      return result;
    }
    goto LABEL_11;
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147024891 )
  {
    v5 = OpenFileMappingW(4u, 0, L"Global\\{A64C7F33-DA35-459b-96CA-63B51FB0CDB9}");
    *((_QWORD *)this + 3) = v5;
    if ( v5 )
    {
      v6 = MapViewOfFile(v5, 4u, 0, 0, 0);
      *((_QWORD *)this + 5) = v6;
      if ( v6 )
        return CPartitionCache::ReadInit(this);
    }
LABEL_11:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180038af8  push    rbx
0x180038afa  sub     rsp, 30h
0x180038afe  mov     rbx, rcx
0x180038b01  lea     r8, aGlobalA64c7f33; "Global\\{A64C7F33-DA35-459b-96CA-63B51F"...
0x180038b08  mov     ecx, 3001Fh; dwDesiredAccess
0x180038b0d  xor     edx, edx; bInheritHandle
0x180038b0f  call    cs:__imp_OpenFileMappingW
0x180038b15  mov     [rbx+18h], rax
0x180038b19  test    rax, rax
0x180038b1c  jz      short loc_180038B5D
0x180038b1e  xor     r9d, r9d; dwFileOffsetLow
0x180038b21  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180038b2a  xor     r8d, r8d; dwFileOffsetHigh
0x180038b2d  mov     edx, 0F001Fh; dwDesiredAccess
0x180038b32  mov     rcx, rax; hFileMappingObject
0x180038b35  call    cs:__imp_MapViewOfFile
0x180038b3b  mov     [rbx+28h], rax
0x180038b3f  test    rax, rax
0x180038b42  jz      short loc_180038BC3
0x180038b44  mov     rcx, rbx; this
0x180038b47  call    ?ReadInit@CPartitionCache@@AEAAJXZ; CPartitionCache::ReadInit(void)
0x180038b4c  test    eax, eax
0x180038b4e  js      loc_180038BD5
0x180038b54  mov     dword ptr [rbx+10h], 1
0x180038b5b  jmp     short loc_180038BD5
0x180038b5d  call    cs:__imp_GetLastError
0x180038b63  test    eax, eax
0x180038b65  jle     short loc_180038B6F
0x180038b67  movzx   eax, ax
0x180038b6a  or      eax, 80070000h
0x180038b6f  cmp     eax, 80070005h
0x180038b74  jnz     short loc_180038BD5
0x180038b76  xor     edx, edx; bInheritHandle
0x180038b78  lea     r8, aGlobalA64c7f33; "Global\\{A64C7F33-DA35-459b-96CA-63B51F"...
0x180038b7f  lea     ecx, [rdx+4]; dwDesiredAccess
0x180038b82  call    cs:__imp_OpenFileMappingW
0x180038b88  mov     [rbx+18h], rax
0x180038b8c  test    rax, rax
0x180038b8f  jz      short loc_180038BC3
0x180038b91  xor     r9d, r9d; dwFileOffsetLow
0x180038b94  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180038b9d  xor     r8d, r8d; dwFileOffsetHigh
0x180038ba0  mov     rcx, rax; hFileMappingObject
0x180038ba3  lea     edx, [r9+4]; dwDesiredAccess
0x180038ba7  call    cs:__imp_MapViewOfFile
0x180038bad  mov     [rbx+28h], rax
0x180038bb1  test    rax, rax
0x180038bb4  jz      short loc_180038BC3
0x180038bb6  mov     rcx, rbx; this
0x180038bb9  add     rsp, 30h
0x180038bbd  pop     rbx
0x180038bbe  jmp     ?ReadInit@CPartitionCache@@AEAAJXZ; CPartitionCache::ReadInit(void)
0x180038bc3  call    cs:__imp_GetLastError
0x180038bc9  test    eax, eax
0x180038bcb  jle     short loc_180038BD5
0x180038bcd  movzx   eax, ax
0x180038bd0  or      eax, 80070000h
0x180038bd5  add     rsp, 30h
0x180038bd9  pop     rbx
0x180038bda  retn
```
