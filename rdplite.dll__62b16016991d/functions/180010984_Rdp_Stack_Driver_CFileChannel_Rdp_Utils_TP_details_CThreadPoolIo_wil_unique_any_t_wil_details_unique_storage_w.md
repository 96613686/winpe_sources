# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalWriteFile(void *,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x180010984`
- end: `0x1800109b4`
- name: `?InternalWriteFile@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `48`
- prototype: `__int64 __fastcall(int, int, int, int, LPOVERLAPPED)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180011fa0`
- `0x18001a514`

## callees

- `0x180010984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800109a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800109a7`
- `ntdll!RtlNtStatusToDosError` at `0x18001099f`
- `ntdll!RtlNtStatusToDosError` at `0x18001099f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010995`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010995`

## pseudocode

```c
BOOL __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalWriteFile(
        void *a1,
        const void *a2,
        DWORD a3,
        __int64 a4,
        LPOVERLAPPED lpOverlapped)
{
  return WriteFile(a1, a2, a3, 0, lpOverlapped);
}

```

## disassembly

```asm
0x180010984  sub     rsp, 38h
0x180010988  mov     rax, [rsp+38h+arg_20]
0x18001098d  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180010992  xor     r9d, r9d; lpNumberOfBytesWritten
0x180010995  call    cs:__imp_WriteFile
0x18001099b  jmp     short loc_1800109AF
0x18001099d  mov     ecx, eax; Status
0x18001099f  call    cs:__imp_RtlNtStatusToDosError
0x1800109a5  mov     ecx, eax; dwErrCode
0x1800109a7  call    cs:__imp_SetLastError
0x1800109ad  xor     eax, eax
0x1800109af  add     rsp, 38h
0x1800109b3  retn
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
