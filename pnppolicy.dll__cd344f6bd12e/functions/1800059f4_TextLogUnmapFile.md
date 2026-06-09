# TextLogUnmapFile

- ea: `0x1800059f4`
- end: `0x180005a55`
- name: `TextLogUnmapFile`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800052c4`
- `0x1800054d4`
- `0x1800063bc`
- `0x180006590`

## callees

- `0x1800059f4`
- `0x1800080b8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a2b`
- `KERNEL32!FlushFileBuffers` at `0x180005a0c`
- `KERNEL32!FlushFileBuffers` at `0x180005a0c`

## pseudocode

```c
int __fastcall TextLogUnmapFile(__int64 a1)
{
  int result; // eax

  if ( *(_DWORD *)(a1 + 44) && *(_QWORD *)a1 != -1 )
    FlushFileBuffers(*(HANDLE *)a1);
  result = pSetupUnmapFileAndSetEOF(*(HANDLE *)a1, *(HANDLE *)(a1 + 8), *(LPCVOID *)(a1 + 16));
  if ( *(_QWORD *)a1 != -1 )
    result = CloseHandle(*(HANDLE *)a1);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = -1;
  *(_DWORD *)(a1 + 44) = 0;
  return result;
}

```

## disassembly

```asm
0x1800059f4  push    rbx
0x1800059f6  sub     rsp, 20h
0x1800059fa  cmp     dword ptr [rcx+2Ch], 0
0x1800059fe  mov     rbx, rcx
0x180005a01  jz      short loc_180005A12
0x180005a03  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180005a07  jz      short loc_180005A12
0x180005a09  mov     rcx, [rcx]; hFile
0x180005a0c  call    cs:__imp_FlushFileBuffers
0x180005a12  mov     r8, [rbx+10h]; lpBaseAddress
0x180005a16  mov     rdx, [rbx+8]; hObject
0x180005a1a  mov     rcx, [rbx]; hFile
0x180005a1d  call    pSetupUnmapFileAndSetEOF
0x180005a22  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180005a26  jz      short loc_180005A31
0x180005a28  mov     rcx, [rbx]; hObject
0x180005a2b  call    cs:__imp_CloseHandle
0x180005a31  mov     qword ptr [rbx+10h], 0
0x180005a39  mov     qword ptr [rbx+8], 0
0x180005a41  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180005a48  mov     dword ptr [rbx+2Ch], 0
0x180005a4f  add     rsp, 20h
0x180005a53  pop     rbx
0x180005a54  retn
```
