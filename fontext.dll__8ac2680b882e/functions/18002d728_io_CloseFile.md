# io_CloseFile

- ea: `0x18002d728`
- end: `0x18002d7f9`
- name: `io_CloseFile`
- size: `209`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002d1e0`
- `0x18002d84c`

## callees

- `0x18002d728`

## import_xrefs

- `msvcrt!free` at `0x18002d7e0`
- `msvcrt!free` at `0x18002d7e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d78d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d7d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d78d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d7d0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d7b2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d7b2`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002d7c0`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002d7c0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002d776`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002d776`

## pseudocode

```c
__int64 __fastcall io_CloseFile(void *Block)
{
  unsigned __int16 v2; // di
  unsigned int v3; // eax
  const void *v4; // rcx
  void *v5; // rcx

  if ( Block && *((_QWORD *)Block + 2) && *(_QWORD *)Block )
  {
    v2 = 0;
  }
  else
  {
    v2 = -1;
    if ( !Block )
      return v2;
  }
  v3 = *((_DWORD *)Block + 6) - *((_DWORD *)Block + 4);
  if ( v3 > *((_DWORD *)Block + 10) )
    *((_DWORD *)Block + 10) = v3;
  v4 = (const void *)*((_QWORD *)Block + 2);
  if ( v4 )
  {
    UnmapViewOfFile(v4);
    *((_QWORD *)Block + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)Block + 1);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)Block + 1) = 0;
  }
  if ( *(_QWORD *)Block )
  {
    if ( *((_BYTE *)Block + 44)
      && (SetFilePointer(*(HANDLE *)Block, *((_DWORD *)Block + 10), 0, 0) == -1 || !SetEndOfFile(*(HANDLE *)Block)) )
    {
      v2 = -1;
    }
    CloseHandle(*(HANDLE *)Block);
    *(_QWORD *)Block = 0;
  }
  free(Block);
  return v2;
}

```

## disassembly

```asm
0x18002d728  mov     [rsp+arg_0], rbx
0x18002d72d  mov     [rsp+arg_8], rbp
0x18002d732  push    rdi
0x18002d733  sub     rsp, 20h
0x18002d737  or      ebp, 0FFFFFFFFh
0x18002d73a  mov     rbx, rcx
0x18002d73d  test    rcx, rcx
0x18002d740  jz      short loc_18002D753
0x18002d742  cmp     qword ptr [rcx+10h], 0
0x18002d747  jz      short loc_18002D753
0x18002d749  cmp     qword ptr [rcx], 0
0x18002d74d  jz      short loc_18002D753
0x18002d74f  xor     edi, edi
0x18002d751  jmp     short loc_18002D75F
0x18002d753  movzx   edi, bp
0x18002d756  test    rbx, rbx
0x18002d759  jz      loc_18002D7E6
0x18002d75f  mov     eax, [rcx+18h]
0x18002d762  sub     eax, [rcx+10h]
0x18002d765  cmp     eax, [rcx+28h]
0x18002d768  jbe     short loc_18002D76D
0x18002d76a  mov     [rcx+28h], eax
0x18002d76d  mov     rcx, [rcx+10h]; lpBaseAddress
0x18002d771  test    rcx, rcx
0x18002d774  jz      short loc_18002D784
0x18002d776  call    cs:__imp_UnmapViewOfFile
0x18002d77c  mov     qword ptr [rbx+10h], 0
0x18002d784  mov     rcx, [rbx+8]; hObject
0x18002d788  test    rcx, rcx
0x18002d78b  jz      short loc_18002D79B
0x18002d78d  call    cs:__imp_CloseHandle
0x18002d793  mov     qword ptr [rbx+8], 0
0x18002d79b  mov     rcx, [rbx]; hFile
0x18002d79e  test    rcx, rcx
0x18002d7a1  jz      short loc_18002D7DD
0x18002d7a3  cmp     byte ptr [rbx+2Ch], 0
0x18002d7a7  jz      short loc_18002D7CD
0x18002d7a9  mov     edx, [rbx+28h]; lDistanceToMove
0x18002d7ac  xor     r9d, r9d; dwMoveMethod
0x18002d7af  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002d7b2  call    cs:__imp_SetFilePointer
0x18002d7b8  cmp     eax, 0FFFFFFFFh
0x18002d7bb  jz      short loc_18002D7CA
0x18002d7bd  mov     rcx, [rbx]; hFile
0x18002d7c0  call    cs:__imp_SetEndOfFile
0x18002d7c6  test    eax, eax
0x18002d7c8  jnz     short loc_18002D7CD
0x18002d7ca  movzx   edi, bp
0x18002d7cd  mov     rcx, [rbx]; hObject
0x18002d7d0  call    cs:__imp_CloseHandle
0x18002d7d6  mov     qword ptr [rbx], 0
0x18002d7dd  mov     rcx, rbx; Block
0x18002d7e0  call    cs:__imp_free
0x18002d7e6  mov     rbx, [rsp+28h+arg_0]
0x18002d7eb  movzx   eax, di
0x18002d7ee  mov     rbp, [rsp+28h+arg_8]
0x18002d7f3  add     rsp, 20h
0x18002d7f7  pop     rdi
0x18002d7f8  retn
```
