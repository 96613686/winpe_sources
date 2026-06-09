# PuDbgDump

- ea: `0x18001ef40`
- end: `0x18001f036`
- name: `PuDbgDump`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001ef40`
- `0x180023254`

## import_xrefs

- `msvcrt!strrchr` at `0x18001ef57`
- `msvcrt!strrchr` at `0x18001ef57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f02f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef5d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001f01f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001f01f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001efb5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001efed`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001efb5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001efed`

## pseudocode

```c
void __fastcall PuDbgDump(__int64 a1, const char *a2, __int64 a3, __int64 a4, LPCVOID lpBuffer)
{
  DWORD LastError; // eax
  LPCVOID v7; // rsi
  __int64 v8; // rdi
  DWORD v9; // ebp
  void *v10; // rcx
  void *v11; // rcx
  CMemoryLog *v12; // rcx
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  strrchr(a2, 92);
  LastError = GetLastError();
  v7 = lpBuffer;
  v8 = -1;
  v9 = LastError;
  do
    ++v8;
  while ( *((_BYTE *)lpBuffer + v8) );
  if ( !a1 )
    goto LABEL_14;
  if ( (*(_BYTE *)(a1 + 648) & 8) != 0 )
  {
    v10 = *(void **)(a1 + 632);
    if ( v10 != (void *)-1LL )
    {
      NumberOfBytesWritten = 0;
      WriteFile(v10, lpBuffer, v8, &NumberOfBytesWritten, 0);
    }
  }
  if ( (*(_BYTE *)(a1 + 648) & 2) != 0 )
  {
    v11 = *(void **)(a1 + 624);
    if ( v11 != (void *)-1LL )
    {
      NumberOfBytesWritten = 0;
      WriteFile(v11, v7, v8, &NumberOfBytesWritten, 0);
    }
  }
  if ( (*(_BYTE *)(a1 + 648) & 0x20) != 0 )
  {
    v12 = *(CMemoryLog **)(a1 + 656);
    if ( v12 )
      CMemoryLog::Append(v12, (const char *)v7, v8);
  }
  if ( (*(_BYTE *)(a1 + 648) & 1) != 0 )
LABEL_14:
    OutputDebugStringA((LPCSTR)v7);
  SetLastError(v9);
}

```

## disassembly

```asm
0x18001ef40  push    rbx
0x18001ef42  push    rbp
0x18001ef43  push    rsi
0x18001ef44  push    rdi
0x18001ef45  sub     rsp, 38h
0x18001ef49  mov     rax, rdx
0x18001ef4c  mov     rbx, rcx
0x18001ef4f  mov     rcx, rax; Str
0x18001ef52  mov     edx, 5Ch ; '\'; Ch
0x18001ef57  call    cs:__imp_strrchr
0x18001ef5d  call    cs:__imp_GetLastError
0x18001ef63  mov     rsi, [rsp+58h+lpBuffer]
0x18001ef6b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ef6f  mov     ebp, eax
0x18001ef71  inc     rdi
0x18001ef74  cmp     byte ptr [rsi+rdi], 0
0x18001ef78  jnz     short loc_18001EF71
0x18001ef7a  test    rbx, rbx
0x18001ef7d  jz      loc_18001F01C
0x18001ef83  test    byte ptr [rbx+288h], 8
0x18001ef8a  jz      short loc_18001EFBB
0x18001ef8c  mov     rcx, [rbx+278h]; hFile
0x18001ef93  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ef97  jz      short loc_18001EFBB
0x18001ef99  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ef9e  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18001efa6  mov     r8d, edi; nNumberOfBytesToWrite
0x18001efa9  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18001efb2  mov     rdx, rsi; lpBuffer
0x18001efb5  call    cs:__imp_WriteFile
0x18001efbb  test    byte ptr [rbx+288h], 2
0x18001efc2  jz      short loc_18001EFF3
0x18001efc4  mov     rcx, [rbx+270h]; hFile
0x18001efcb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001efcf  jz      short loc_18001EFF3
0x18001efd1  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001efd6  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18001efde  mov     r8d, edi; nNumberOfBytesToWrite
0x18001efe1  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18001efea  mov     rdx, rsi; lpBuffer
0x18001efed  call    cs:__imp_WriteFile
0x18001eff3  test    byte ptr [rbx+288h], 20h
0x18001effa  jz      short loc_18001F013
0x18001effc  mov     rcx, [rbx+290h]; this
0x18001f003  test    rcx, rcx
0x18001f006  jz      short loc_18001F013
0x18001f008  mov     r8d, edi; unsigned int
0x18001f00b  mov     rdx, rsi; char *
0x18001f00e  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x18001f013  test    byte ptr [rbx+288h], 1
0x18001f01a  jz      short loc_18001F025
0x18001f01c  mov     rcx, rsi; lpOutputString
0x18001f01f  call    cs:__imp_OutputDebugStringA
0x18001f025  mov     ecx, ebp
0x18001f027  add     rsp, 38h
0x18001f02b  pop     rdi
0x18001f02c  pop     rsi
0x18001f02d  pop     rbp
0x18001f02e  pop     rbx
0x18001f02f  jmp     cs:__imp_SetLastError
```
