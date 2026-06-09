# CreatePagefileMapping(ulong,ulong,ushort const *,void * *)

- ea: `0x18004ffec`
- end: `0x180050058`
- name: `?CreatePagefileMapping@@YAJKKPEBGPEAPEAX@Z`
- size: `108`
- prototype: `int(unsigned int, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18004b990`

## callees

- `0x18004ffec`
- `0x180050060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005003a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005003a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005000f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005000f`

## pseudocode

```c
__int64 __fastcall CreatePagefileMapping(__int64 a1, DWORD dwMaximumSizeLow, const unsigned __int16 *lpName, void **a4)
{
  HANDLE FileMappingW; // rdi
  DWORD LastError; // eax
  unsigned int v7; // ebx

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, lpName);
  LastError = GetLastError();
  if ( FileMappingW )
  {
    if ( LastError )
    {
      v7 = HRESULTFromWin32ErrorError(LastError);
      CloseHandle(FileMappingW);
    }
    else
    {
      *a4 = FileMappingW;
      return 0;
    }
  }
  else
  {
    return (unsigned int)HRESULTFromWin32ErrorError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18004ffec  mov     [rsp+arg_0], rbx
0x18004fff1  push    rdi
0x18004fff2  sub     rsp, 30h
0x18004fff6  mov     [rsp+38h+lpName], r8; lpName
0x18004fffb  mov     rbx, r9
0x18004fffe  xor     r9d, r9d; dwMaximumSizeHigh
0x180050001  mov     [rsp+38h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x180050005  xor     edx, edx; lpFileMappingAttributes
0x180050007  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18005000b  lea     r8d, [r9+4]; flProtect
0x18005000f  call    cs:__imp_CreateFileMappingW
0x180050015  mov     rdi, rax
0x180050018  call    cs:__imp_GetLastError
0x18005001e  test    rdi, rdi
0x180050021  jz      short loc_180050042
0x180050023  test    eax, eax
0x180050025  jnz     short loc_18005002E
0x180050027  mov     [rbx], rdi
0x18005002a  xor     ebx, ebx
0x18005002c  jmp     short loc_18005004B
0x18005002e  mov     ecx, eax; unsigned int
0x180050030  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180050035  mov     rcx, rdi; hObject
0x180050038  mov     ebx, eax
0x18005003a  call    cs:__imp_CloseHandle
0x180050040  jmp     short loc_18005004B
0x180050042  mov     ecx, eax; unsigned int
0x180050044  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180050049  mov     ebx, eax
0x18005004b  mov     eax, ebx
0x18005004d  mov     rbx, [rsp+38h+arg_0]
0x180050052  add     rsp, 30h
0x180050056  pop     rdi
0x180050057  retn
```
