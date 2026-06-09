# GetNextLogArchiveExtent

- ea: `0x18000bbb0`
- end: `0x18000bc17`
- name: `GetNextLogArchiveExtent`
- size: `103`
- prototype: `BOOL __stdcall(CLFS_LOG_ARCHIVE_CONTEXT pvArchiveContext, CLFS_ARCHIVE_DESCRIPTOR rgadExtent[], ULONG cDescriptors, PULONG pcDescriptorsReturned)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000bbb0`
- `0x180010840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bbe1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bbe1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bc02`

## pseudocode

```c
BOOL __stdcall GetNextLogArchiveExtent(
        CLFS_LOG_ARCHIVE_CONTEXT pvArchiveContext,
        CLFS_ARCHIVE_DESCRIPTOR rgadExtent[],
        ULONG cDescriptors,
        PULONG pcDescriptorsReturned)
{
  DWORD NextExtent; // ebx
  DWORD v6; // ecx

  if ( !pvArchiveContext )
  {
LABEL_9:
    v6 = 6606;
    goto LABEL_10;
  }
  if ( rgadExtent && pcDescriptorsReturned && cDescriptors )
  {
    if ( *((_DWORD *)pvArchiveContext + 1) == 96 && *(_DWORD *)pvArchiveContext == -1040322548 )
    {
      NextExtent = CClfsArchiveContext::GetNextExtent(
                     (CClfsArchiveContext *)pvArchiveContext,
                     rgadExtent,
                     cDescriptors,
                     pcDescriptorsReturned);
      SetLastError(NextExtent);
      return NextExtent == 0;
    }
    goto LABEL_9;
  }
  v6 = 87;
LABEL_10:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18000bbb0  push    rbx
0x18000bbb2  sub     rsp, 20h
0x18000bbb6  test    rcx, rcx
0x18000bbb9  jz      short loc_18000BBFD
0x18000bbbb  test    rdx, rdx
0x18000bbbe  jz      short loc_18000BBF6
0x18000bbc0  test    r9, r9
0x18000bbc3  jz      short loc_18000BBF6
0x18000bbc5  test    r8d, r8d
0x18000bbc8  jz      short loc_18000BBF6
0x18000bbca  cmp     dword ptr [rcx+4], 60h ; '`'
0x18000bbce  jnz     short loc_18000BBFD
0x18000bbd0  cmp     dword ptr [rcx], 0C1FDF00Ch
0x18000bbd6  jnz     short loc_18000BBFD
0x18000bbd8  call    ?GetNextExtent@CClfsArchiveContext@@QEAAKQEAU_CLS_ARCHIVE_DESCRIPTOR@@KAEAK@Z; CClfsArchiveContext::GetNextExtent(_CLS_ARCHIVE_DESCRIPTOR * const,ulong,ulong &)
0x18000bbdd  mov     ecx, eax; dwErrCode
0x18000bbdf  mov     ebx, eax
0x18000bbe1  call    cs:__imp_SetLastError
0x18000bbe8  nop     dword ptr [rax+rax+00h]
0x18000bbed  xor     eax, eax
0x18000bbef  test    ebx, ebx
0x18000bbf1  setz    al
0x18000bbf4  jmp     short loc_18000BC10
0x18000bbf6  mov     ecx, 57h ; 'W'
0x18000bbfb  jmp     short loc_18000BC02
0x18000bbfd  mov     ecx, 19CEh; dwErrCode
0x18000bc02  call    cs:__imp_SetLastError
0x18000bc09  nop     dword ptr [rax+rax+00h]
0x18000bc0e  xor     eax, eax
0x18000bc10  add     rsp, 20h
0x18000bc14  pop     rbx
0x18000bc15  retn
```
