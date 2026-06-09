# PupOutputMessage(_DEBUG_PRINTS *,STRA *)

- ea: `0x180015748`
- end: `0x1800157d6`
- name: `?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z`
- size: `142`
- prototype: `void __fastcall(struct _DEBUG_PRINTS *, struct STRA *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007300`
- `0x1800180c0`
- `0x18001f0d0`

## callees

- `0x180015748`
- `0x180023254`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800157c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800157c5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180015790`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180015790`

## pseudocode

```c
void __fastcall PupOutputMessage(struct _DEBUG_PRINTS *a1, struct STRA *a2)
{
  void *v4; // rcx
  DWORD v5; // r8d
  const void *v6; // rdx
  CMemoryLog *v7; // rcx
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    goto LABEL_9;
  if ( (*((_BYTE *)a1 + 648) & 2) != 0 )
  {
    v4 = (void *)*((_QWORD *)a1 + 78);
    if ( v4 != (void *)-1LL )
    {
      v5 = *((_DWORD *)a2 + 12);
      v6 = (const void *)*((_QWORD *)a2 + 4);
      v8 = 0;
      WriteFile(v4, v6, v5, &v8, 0);
    }
  }
  if ( (*((_BYTE *)a1 + 648) & 0x20) != 0 )
  {
    v7 = (CMemoryLog *)*((_QWORD *)a1 + 82);
    if ( v7 )
      CMemoryLog::Append(v7, *((const char **)a2 + 4), *((_DWORD *)a2 + 12));
  }
  if ( (*((_BYTE *)a1 + 648) & 1) != 0 )
LABEL_9:
    OutputDebugStringA(*((LPCSTR *)a2 + 4));
}

```

## disassembly

```asm
0x180015748  mov     rax, rsp
0x18001574b  mov     [rax+10h], rbx
0x18001574f  push    rdi
0x180015750  sub     rsp, 30h
0x180015754  mov     rdi, rdx
0x180015757  mov     rbx, rcx
0x18001575a  test    rcx, rcx
0x18001575d  jz      short loc_1800157C1
0x18001575f  test    byte ptr [rcx+288h], 2
0x180015766  jz      short loc_180015796
0x180015768  mov     rcx, [rcx+270h]; hFile
0x18001576f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015773  jz      short loc_180015796
0x180015775  mov     r8d, [rdx+30h]; nNumberOfBytesToWrite
0x180015779  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x18001577d  mov     rdx, [rdx+20h]; lpBuffer
0x180015781  mov     dword ptr [rax+8], 0
0x180015788  mov     qword ptr [rax-18h], 0
0x180015790  call    cs:__imp_WriteFile
0x180015796  test    byte ptr [rbx+288h], 20h
0x18001579d  jz      short loc_1800157B8
0x18001579f  mov     rcx, [rbx+290h]; this
0x1800157a6  test    rcx, rcx
0x1800157a9  jz      short loc_1800157B8
0x1800157ab  mov     r8d, [rdi+30h]; unsigned int
0x1800157af  mov     rdx, [rdi+20h]; char *
0x1800157b3  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x1800157b8  test    byte ptr [rbx+288h], 1
0x1800157bf  jz      short loc_1800157CB
0x1800157c1  mov     rcx, [rdi+20h]; lpOutputString
0x1800157c5  call    cs:__imp_OutputDebugStringA
0x1800157cb  mov     rbx, [rsp+38h+arg_8]
0x1800157d0  add     rsp, 30h
0x1800157d4  pop     rdi
0x1800157d5  retn
```
