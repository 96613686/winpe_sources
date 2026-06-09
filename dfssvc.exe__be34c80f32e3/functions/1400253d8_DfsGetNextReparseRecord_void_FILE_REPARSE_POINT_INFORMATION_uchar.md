# DfsGetNextReparseRecord(void *,_FILE_REPARSE_POINT_INFORMATION *,uchar *)

- ea: `0x1400253d8`
- end: `0x140025456`
- name: `?DfsGetNextReparseRecord@@YAKPEAXPEAU_FILE_REPARSE_POINT_INFORMATION@@PEAE@Z`
- size: `126`
- prototype: `unsigned int __fastcall(void *, struct _FILE_REPARSE_POINT_INFORMATION *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x140026018`

## callees

- `0x1400253d8`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x14002541e`
- `ntdll!NtQueryDirectoryFile` at `0x14002541e`
- `ntdll!RtlNtStatusToDosError` at `0x140025430`
- `ntdll!RtlNtStatusToDosError` at `0x140025430`

## pseudocode

```c
__int64 __fastcall DfsGetNextReparseRecord(void *a1, struct _FILE_REPARSE_POINT_INFORMATION *a2, unsigned __int8 *a3)
{
  unsigned int v3; // ebx
  int v5; // eax
  ULONG v6; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-18h] BYREF

  v3 = 0;
  IoStatusBlock = 0;
  v5 = NtQueryDirectoryFile(a1, 0, 0, 0, &IoStatusBlock, a2, 0x10u, FileReparsePointInformation, 1u, 0, 0);
  if ( v5 < 0 )
  {
    v6 = RtlNtStatusToDosError(v5);
    *a3 = 1;
    if ( v6 != 18 )
      return v6;
  }
  return v3;
}

```

## disassembly

```asm
0x1400253d8  mov     rax, rsp
0x1400253db  mov     [rax+8], rbx
0x1400253df  push    rdi
0x1400253e0  sub     rsp, 70h
0x1400253e4  xor     ebx, ebx
0x1400253e6  xorps   xmm0, xmm0
0x1400253e9  mov     [rax-28h], bl
0x1400253ec  mov     rdi, r8
0x1400253ef  mov     [rax-30h], rbx
0x1400253f3  xor     r9d, r9d; ApcContext
0x1400253f6  mov     byte ptr [rax-38h], 1
0x1400253fa  xor     r8d, r8d; ApcRoutine
0x1400253fd  mov     dword ptr [rax-40h], 21h ; '!'
0x140025404  mov     dword ptr [rax-48h], 10h
0x14002540b  mov     [rax-50h], rdx
0x14002540f  xor     edx, edx; Event
0x140025411  movups  xmmword ptr [rax-18h], xmm0
0x140025415  lea     rax, [rax-18h]
0x140025419  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x14002541e  call    cs:__imp_NtQueryDirectoryFile
0x140025425  nop     dword ptr [rax+rax+00h]
0x14002542a  test    eax, eax
0x14002542c  jns     short loc_140025445
0x14002542e  mov     ecx, eax; Status
0x140025430  call    cs:__imp_RtlNtStatusToDosError
0x140025437  nop     dword ptr [rax+rax+00h]
0x14002543c  cmp     eax, 12h
0x14002543f  mov     byte ptr [rdi], 1
0x140025442  cmovnz  ebx, eax
0x140025445  mov     eax, ebx
0x140025447  mov     rbx, [rsp+78h+arg_0]
0x14002544f  add     rsp, 70h
0x140025453  pop     rdi
0x140025454  retn
```
