# win_musl::DataBuffer::Clear(void)

- ea: `0x180035d60`
- end: `0x180035dc7`
- name: `?Clear@DataBuffer@win_musl@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180035a70`
- `0x180092fac`

## callees

- `0x180035d60`
- `0x180036b24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180035d97`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180035d97`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180035dae`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180035dae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180035dbf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180035dbf`

## pseudocode

```c
void __fastcall win_musl::DataBuffer::Clear(HANDLE *this)
{
  HANDLE v2; // rcx
  const CHAR *v3; // rcx

  std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(this);
  v2 = this[8];
  if ( dword_1801C4F90 != -1 && v2 != (HANDLE)-1LL )
  {
    if ( !SetFilePointerEx(v2, 0, 0, 0) )
    {
      v3 = "win_musl::DataBuffer::Clear, !atZero is true, file not at zero.\n";
LABEL_8:
      OutputDebugStringA(v3);
      goto LABEL_2;
    }
    if ( !SetEndOfFile(this[8]) )
    {
      v3 = "win_musl::DataBuffer::Clear, !truncated is true, failed to truncate file.\n";
      goto LABEL_8;
    }
  }
LABEL_2:
  this[9] = 0;
}

```

## disassembly

```asm
0x180035d60  push    rbx
0x180035d62  sub     rsp, 20h
0x180035d66  mov     rbx, rcx
0x180035d69  call    ?clear@?$list@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEAAXXZ; std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(void)
0x180035d6e  cmp     cs:dword_1801C4F90, 0FFFFFFFFh
0x180035d75  mov     rcx, [rbx+40h]; hFile
0x180035d79  jnz     short loc_180035D89
0x180035d7b  mov     qword ptr [rbx+48h], 0
0x180035d83  add     rsp, 20h
0x180035d87  pop     rbx
0x180035d88  retn
0x180035d89  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035d8d  jz      short loc_180035D7B
0x180035d8f  xor     edx, edx; liDistanceToMove
0x180035d91  xor     r9d, r9d; dwMoveMethod
0x180035d94  xor     r8d, r8d; lpNewFilePointer
0x180035d97  call    cs:__imp_SetFilePointerEx
0x180035d9d  test    eax, eax
0x180035d9f  jnz     short loc_180035DAA
0x180035da1  lea     rcx, aWinMuslDatabuf; "win_musl::DataBuffer::Clear, !atZero is"...
0x180035da8  jmp     short loc_180035DBF
0x180035daa  mov     rcx, [rbx+40h]; hFile
0x180035dae  call    cs:__imp_SetEndOfFile
0x180035db4  test    eax, eax
0x180035db6  jnz     short loc_180035D7B
0x180035db8  lea     rcx, aWinMuslDatabuf_0; "win_musl::DataBuffer::Clear, !truncated"...
0x180035dbf  call    cs:__imp_OutputDebugStringA
0x180035dc5  jmp     short loc_180035D7B
```
