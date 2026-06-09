# Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)

- ea: `0x18001a4a8`
- end: `0x18001a4fd`
- name: `?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z`
- size: `85`
- prototype: `bool(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a090`

## callees

- `0x18001a4a8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a4d0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a4d0`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2)
{
  HANDLE FileW; // rax

  FileW = CreateFileW(a2, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x18001a4a8  sub     rsp, 48h
0x18001a4ac  mov     rcx, rdx; lpFileName
0x18001a4af  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001a4b8  mov     r8d, 3; dwShareMode
0x18001a4be  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001a4c6  xor     edx, edx; dwDesiredAccess
0x18001a4c8  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001a4cd  xor     r9d, r9d; lpSecurityAttributes
0x18001a4d0  call    cs:__imp_CreateFileW
0x18001a4d7  nop     dword ptr [rax+rax+00h]
0x18001a4dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a4e0  jz      short loc_18001A4F5
0x18001a4e2  mov     rcx, rax; hObject
0x18001a4e5  call    cs:__imp_CloseHandle
0x18001a4ec  nop     dword ptr [rax+rax+00h]
0x18001a4f1  mov     al, 1
0x18001a4f3  jmp     short loc_18001A4F7
0x18001a4f5  xor     al, al
0x18001a4f7  add     rsp, 48h
0x18001a4fb  retn
```
