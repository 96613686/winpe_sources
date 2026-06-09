# ReadLogArchiveMetadata

- ea: `0x18000c3c0`
- end: `0x18000c451`
- name: `ReadLogArchiveMetadata`
- size: `145`
- prototype: `BOOL __stdcall(CLFS_LOG_ARCHIVE_CONTEXT pvArchiveContext, ULONG cbOffset, ULONG cbBytesToRead, PBYTE pbReadBuffer, PULONG pcbBytesRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c3c0`
- `0x180012410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c410`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c410`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c437`

## pseudocode

```c
BOOL __stdcall ReadLogArchiveMetadata(
        CLFS_LOG_ARCHIVE_CONTEXT pvArchiveContext,
        ULONG cbOffset,
        ULONG cbBytesToRead,
        PBYTE pbReadBuffer,
        PULONG pcbBytesRead)
{
  PULONG v5; // rdi
  DWORD v6; // eax
  DWORD v7; // ebx
  DWORD v9; // ecx
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  if ( !pvArchiveContext )
    goto LABEL_11;
  if ( !pbReadBuffer || (v5 = pcbBytesRead) == 0 || !cbBytesToRead )
  {
    v9 = 87;
LABEL_12:
    SetLastError(v9);
    return 0;
  }
  if ( *((_DWORD *)pvArchiveContext + 1) != 96 || *(_DWORD *)pvArchiveContext != -1040322548 )
  {
LABEL_11:
    v9 = 6606;
    goto LABEL_12;
  }
  v6 = CClfsArchiveContext::ReadMetadata(
         (CClfsArchiveContext *)pvArchiveContext,
         cbOffset,
         cbBytesToRead,
         pbReadBuffer,
         &v10);
  v7 = v6;
  if ( v6 )
    SetLastError(v6);
  *v5 = v10;
  return v7 == 0;
}

```

## disassembly

```asm
0x18000c3c0  mov     [rsp+arg_8], rbx
0x18000c3c5  push    rdi
0x18000c3c6  sub     rsp, 30h
0x18000c3ca  mov     [rsp+38h+arg_0], 0
0x18000c3d2  test    rcx, rcx
0x18000c3d5  jz      short loc_18000C432
0x18000c3d7  test    r9, r9
0x18000c3da  jz      short loc_18000C42B
0x18000c3dc  mov     rdi, [rsp+38h+pcbBytesRead]
0x18000c3e1  test    rdi, rdi
0x18000c3e4  jz      short loc_18000C42B
0x18000c3e6  test    r8d, r8d
0x18000c3e9  jz      short loc_18000C42B
0x18000c3eb  cmp     dword ptr [rcx+4], 60h ; '`'
0x18000c3ef  jnz     short loc_18000C432
0x18000c3f1  cmp     dword ptr [rcx], 0C1FDF00Ch
0x18000c3f7  jnz     short loc_18000C432
0x18000c3f9  lea     rax, [rsp+38h+arg_0]
0x18000c3fe  mov     [rsp+38h+var_18], rax; unsigned int *
0x18000c403  call    ?ReadMetadata@CClfsArchiveContext@@QEAAKKKPEAEAEAK@Z; CClfsArchiveContext::ReadMetadata(ulong,ulong,uchar *,ulong &)
0x18000c408  mov     ebx, eax
0x18000c40a  test    eax, eax
0x18000c40c  jz      short loc_18000C41C
0x18000c40e  mov     ecx, eax; dwErrCode
0x18000c410  call    cs:__imp_SetLastError
0x18000c417  nop     dword ptr [rax+rax+00h]
0x18000c41c  mov     ecx, [rsp+38h+arg_0]
0x18000c420  xor     eax, eax
0x18000c422  test    ebx, ebx
0x18000c424  mov     [rdi], ecx
0x18000c426  setz    al
0x18000c429  jmp     short loc_18000C445
0x18000c42b  mov     ecx, 57h ; 'W'
0x18000c430  jmp     short loc_18000C437
0x18000c432  mov     ecx, 19CEh; dwErrCode
0x18000c437  call    cs:__imp_SetLastError
0x18000c43e  nop     dword ptr [rax+rax+00h]
0x18000c443  xor     eax, eax
0x18000c445  mov     rbx, [rsp+38h+arg_8]
0x18000c44a  add     rsp, 30h
0x18000c44e  pop     rdi
0x18000c44f  retn
```
