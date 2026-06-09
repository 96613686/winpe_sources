# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x18001094c`
- end: `0x18001097c`
- name: `?InternalReadFile@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `48`
- prototype: `__int64 __fastcall(int, int, int, int, LPOVERLAPPED)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011ee4`
- `0x18001c2a8`

## callees

- `0x18001094c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001096f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001096f`
- `ntdll!RtlNtStatusToDosError` at `0x180010967`
- `ntdll!RtlNtStatusToDosError` at `0x180010967`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001095d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001095d`

## pseudocode

```c
BOOL __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalReadFile(
        void *a1,
        void *a2,
        DWORD a3,
        __int64 a4,
        LPOVERLAPPED lpOverlapped)
{
  return ReadFile(a1, a2, a3, 0, lpOverlapped);
}

```

## disassembly

```asm
0x18001094c  sub     rsp, 38h
0x180010950  mov     rax, [rsp+38h+arg_20]
0x180010955  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x18001095a  xor     r9d, r9d; lpNumberOfBytesRead
0x18001095d  call    cs:__imp_ReadFile
0x180010963  jmp     short loc_180010977
0x180010965  mov     ecx, eax; Status
0x180010967  call    cs:__imp_RtlNtStatusToDosError
0x18001096d  mov     ecx, eax; dwErrCode
0x18001096f  call    cs:__imp_SetLastError
0x180010975  xor     eax, eax
0x180010977  add     rsp, 38h
0x18001097b  retn
0x180028eec  push    rbp
0x180028eee  sub     rsp, 30h
0x180028ef2  mov     rbp, rdx
0x180028ef5  mov     rax, [rcx]
0x180028ef8  xor     ecx, ecx
0x180028efa  cmp     dword ptr [rax], 0C00000FDh
0x180028f00  setnz   cl
0x180028f03  mov     eax, ecx
0x180028f05  add     rsp, 30h
0x180028f09  pop     rbp
0x180028f0a  retn
```
