# CscDriverQueryDirectory

- ea: `0x180006460`
- end: `0x1800064dd`
- name: `CscDriverQueryDirectory`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006560`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x1800064b6`
- `ntdll!NtQueryDirectoryFile` at `0x1800064b6`

## pseudocode

```c
NTSTATUS __fastcall CscDriverQueryDirectory(
        void *a1,
        _DWORD *a2,
        void *FileInformation,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct _UNICODE_STRING *FileName,
        BOOLEAN RestartScan)
{
  NTSTATUS result; // eax
  int Information; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  result = NtQueryDirectoryFile(
             a1,
             0,
             0,
             0,
             &IoStatusBlock,
             FileInformation,
             0x2C0u,
             FileBothDirectoryInformation,
             1u,
             FileName,
             RestartScan);
  Information = IoStatusBlock.Information;
  if ( (result & 0xC0000000) == 0xC0000000 )
    Information = 0;
  *a2 = Information;
  return result;
}

```

## disassembly

```asm
0x180006460  push    rbx
0x180006462  sub     rsp, 70h
0x180006466  movzx   eax, [rsp+78h+arg_38]
0x18000646e  mov     rbx, rdx
0x180006471  mov     [rsp+78h+RestartScan], al; RestartScan
0x180006475  xorps   xmm0, xmm0
0x180006478  mov     rax, [rsp+78h+arg_30]
0x180006480  xor     r9d, r9d; ApcContext
0x180006483  mov     [rsp+78h+FileName], rax; FileName
0x180006488  xor     edx, edx; Event
0x18000648a  mov     [rsp+78h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18000648f  lea     rax, [rsp+78h+var_18]
0x180006494  mov     [rsp+78h+FileInformationClass], 3; FileInformationClass
0x18000649c  mov     [rsp+78h+Length], 2C0h; Length
0x1800064a4  mov     [rsp+78h+FileInformation], r8; FileInformation
0x1800064a9  xor     r8d, r8d; ApcRoutine
0x1800064ac  movups  xmmword ptr [rsp+78h+var_18], xmm0
0x1800064b1  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x1800064b6  call    cs:__imp_NtQueryDirectoryFile
0x1800064bc  mov     ecx, dword ptr [rsp+78h+var_18.Information]
0x1800064c0  xor     r8d, r8d
0x1800064c3  mov     edx, eax
0x1800064c5  and     edx, 0C0000000h
0x1800064cb  cmp     edx, 0C0000000h
0x1800064d1  cmovz   ecx, r8d
0x1800064d5  mov     [rbx], ecx
0x1800064d7  add     rsp, 70h
0x1800064db  pop     rbx
0x1800064dc  retn
```
