# FreeProfileObject(void *)

- ea: `0x18000bbfc`
- end: `0x18000bcd2`
- name: `?FreeProfileObject@@YAHPEAX@Z`
- size: `214`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b070`

## callees

- `0x18000bbfc`
- `0x18000be44`
- `0x18000c310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc0f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000bc97`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000bc97`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000bc8d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000bc8d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000bc63`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000bc63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bca1`

## pseudocode

```c
__int64 __fastcall FreeProfileObject(unsigned __int64 a1)
{
  signed __int64 v1; // rbx
  DWORD LastError; // eax
  void *v3; // rcx
  DWORD v4; // esi
  unsigned int v5; // edi
  int v6; // ebp
  unsigned int *v7; // r10
  unsigned __int32 v8; // eax
  void *v9; // rcx
  void *v10; // rcx

  v1 = a1 ^ 0x49434D20;
  LastError = GetLastError();
  v3 = *(void **)(v1 + 16);
  v4 = LastError;
  if ( v3 )
    MemFree(v3);
  if ( (*(_BYTE *)(v1 + 28) & 1) != 0 )
  {
    v5 = 0;
    v6 = 0;
    if ( *(_QWORD *)(v1 + 56) )
    {
      if ( ValidProfile(v1) && v7[9] == 1886610273 )
      {
        v5 = *(_DWORD *)(v1 + 48);
        v6 = 1;
        v8 = _byteswap_ulong(*v7);
        if ( v8 <= v5 )
          v5 = v8;
      }
      UnmapViewOfFile(v7);
    }
    v9 = *(void **)(v1 + 40);
    if ( v9 )
      CloseHandle(v9);
    v10 = *(void **)(v1 + 32);
    if ( v10 )
    {
      if ( v6 )
      {
        SetFilePointer(v10, v5, 0, 0);
        SetEndOfFile(*(HANDLE *)(v1 + 32));
      }
      CloseHandle(*(HANDLE *)(v1 + 32));
    }
  }
  --*(_DWORD *)(v1 + 4);
  *(_DWORD *)v1 = 0;
  MemFree((LPVOID)v1);
  if ( v4 )
    SetLastError(v4);
  return 1;
}

```

## disassembly

```asm
0x18000bbfc  push    rbx
0x18000bbfe  push    rbp
0x18000bbff  push    rsi
0x18000bc00  push    rdi
0x18000bc01  sub     rsp, 28h
0x18000bc05  mov     rbx, rcx
0x18000bc08  xor     rbx, 49434D20h
0x18000bc0f  call    cs:__imp_GetLastError
0x18000bc15  mov     rcx, [rbx+10h]; lpMem
0x18000bc19  mov     esi, eax
0x18000bc1b  test    rcx, rcx
0x18000bc1e  jz      short loc_18000BC25
0x18000bc20  call    MemFree
0x18000bc25  test    byte ptr [rbx+1Ch], 1
0x18000bc29  jz      short loc_18000BCA7
0x18000bc2b  mov     r10, [rbx+38h]
0x18000bc2f  xor     edi, edi
0x18000bc31  xor     ebp, ebp
0x18000bc33  test    r10, r10
0x18000bc36  jz      short loc_18000BC69
0x18000bc38  mov     rcx, rbx
0x18000bc3b  call    ValidProfile
0x18000bc40  test    eax, eax
0x18000bc42  jz      short loc_18000BC60
0x18000bc44  cmp     dword ptr [r10+24h], 70736361h
0x18000bc4c  jnz     short loc_18000BC60
0x18000bc4e  mov     edi, [rbx+30h]
0x18000bc51  mov     ebp, 1
0x18000bc56  mov     eax, [r10]
0x18000bc59  bswap   eax
0x18000bc5b  cmp     eax, edi
0x18000bc5d  cmovbe  edi, eax
0x18000bc60  mov     rcx, r10; lpBaseAddress
0x18000bc63  call    cs:__imp_UnmapViewOfFile
0x18000bc69  mov     rcx, [rbx+28h]; hObject
0x18000bc6d  test    rcx, rcx
0x18000bc70  jz      short loc_18000BC78
0x18000bc72  call    cs:__imp_CloseHandle
0x18000bc78  mov     rcx, [rbx+20h]; hFile
0x18000bc7c  test    rcx, rcx
0x18000bc7f  jz      short loc_18000BCA7
0x18000bc81  test    ebp, ebp
0x18000bc83  jz      short loc_18000BC9D
0x18000bc85  xor     r9d, r9d; dwMoveMethod
0x18000bc88  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000bc8b  mov     edx, edi; lDistanceToMove
0x18000bc8d  call    cs:__imp_SetFilePointer
0x18000bc93  mov     rcx, [rbx+20h]; hFile
0x18000bc97  call    cs:__imp_SetEndOfFile
0x18000bc9d  mov     rcx, [rbx+20h]; hObject
0x18000bca1  call    cs:__imp_CloseHandle
0x18000bca7  dec     dword ptr [rbx+4]
0x18000bcaa  mov     rcx, rbx; lpMem
0x18000bcad  mov     dword ptr [rbx], 0
0x18000bcb3  call    MemFree
0x18000bcb8  test    esi, esi
0x18000bcba  jz      short loc_18000BCC4
0x18000bcbc  mov     ecx, esi; dwErrCode
0x18000bcbe  call    cs:__imp_SetLastError
0x18000bcc4  mov     eax, 1
0x18000bcc9  add     rsp, 28h
0x18000bccd  pop     rdi
0x18000bcce  pop     rsi
0x18000bccf  pop     rbp
0x18000bcd0  pop     rbx
0x18000bcd1  retn
```
