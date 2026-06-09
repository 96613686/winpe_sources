# CPartitionCache::CreateCache(void)

- ea: `0x180052e18`
- end: `0x180052efb`
- name: `?CreateCache@CPartitionCache@@AEAAJXZ`
- size: `227`
- prototype: `signed int __fastcall(CPartitionCache *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180052d08`

## callees

- `0x180052e18`
- `0x180052f3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ee3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180052e55`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180052ec7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180052e55`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180052ec7`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180052e2f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180052ea2`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180052e2f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180052ea2`

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
0x180052e18  push    rbx
0x180052e1a  sub     rsp, 30h
0x180052e1e  mov     rbx, rcx
0x180052e21  lea     r8, aGlobalA64c7f33; "Global\\{A64C7F33-DA35-459b-96CA-63B51F"...
0x180052e28  mov     ecx, 3001Fh; dwDesiredAccess
0x180052e2d  xor     edx, edx; bInheritHandle
0x180052e2f  call    cs:__imp_OpenFileMappingW
0x180052e35  mov     [rbx+18h], rax
0x180052e39  test    rax, rax
0x180052e3c  jz      short loc_180052E7D
0x180052e3e  xor     r9d, r9d; dwFileOffsetLow
0x180052e41  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180052e4a  xor     r8d, r8d; dwFileOffsetHigh
0x180052e4d  mov     edx, 0F001Fh; dwDesiredAccess
0x180052e52  mov     rcx, rax; hFileMappingObject
0x180052e55  call    cs:__imp_MapViewOfFile
0x180052e5b  mov     [rbx+28h], rax
0x180052e5f  test    rax, rax
0x180052e62  jz      short loc_180052EE3
0x180052e64  mov     rcx, rbx; this
0x180052e67  call    ?ReadInit@CPartitionCache@@AEAAJXZ; CPartitionCache::ReadInit(void)
0x180052e6c  test    eax, eax
0x180052e6e  js      loc_180052EF5
0x180052e74  mov     dword ptr [rbx+10h], 1
0x180052e7b  jmp     short loc_180052EF5
0x180052e7d  call    cs:__imp_GetLastError
0x180052e83  test    eax, eax
0x180052e85  jle     short loc_180052E8F
0x180052e87  movzx   eax, ax
0x180052e8a  or      eax, 80070000h
0x180052e8f  cmp     eax, 80070005h
0x180052e94  jnz     short loc_180052EF5
0x180052e96  xor     edx, edx; bInheritHandle
0x180052e98  lea     r8, aGlobalA64c7f33; "Global\\{A64C7F33-DA35-459b-96CA-63B51F"...
0x180052e9f  lea     ecx, [rdx+4]; dwDesiredAccess
0x180052ea2  call    cs:__imp_OpenFileMappingW
0x180052ea8  mov     [rbx+18h], rax
0x180052eac  test    rax, rax
0x180052eaf  jz      short loc_180052EE3
0x180052eb1  xor     r9d, r9d; dwFileOffsetLow
0x180052eb4  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180052ebd  xor     r8d, r8d; dwFileOffsetHigh
0x180052ec0  mov     rcx, rax; hFileMappingObject
0x180052ec3  lea     edx, [r9+4]; dwDesiredAccess
0x180052ec7  call    cs:__imp_MapViewOfFile
0x180052ecd  mov     [rbx+28h], rax
0x180052ed1  test    rax, rax
0x180052ed4  jz      short loc_180052EE3
0x180052ed6  mov     rcx, rbx; this
0x180052ed9  add     rsp, 30h
0x180052edd  pop     rbx
0x180052ede  jmp     ?ReadInit@CPartitionCache@@AEAAJXZ; CPartitionCache::ReadInit(void)
0x180052ee3  call    cs:__imp_GetLastError
0x180052ee9  test    eax, eax
0x180052eeb  jle     short loc_180052EF5
0x180052eed  movzx   eax, ax
0x180052ef0  or      eax, 80070000h
0x180052ef5  add     rsp, 30h
0x180052ef9  pop     rbx
0x180052efa  retn
```
