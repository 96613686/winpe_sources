# NbtDispatchLmHostsIoctl

- ea: `0x14001b9d4`
- end: `0x14001ba78`
- name: `NbtDispatchLmHostsIoctl`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140047f20`

## callees

- `0x14001b9d4`
- `0x14001ba80`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001ba34`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001ba34`

## pseudocode

```c
__int64 __fastcall NbtDispatchLmHostsIoctl(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  __int64 v5; // rcx
  __int64 result; // rax
  BOOL v8; // esi
  PVOID v9; // rax

  v5 = *(_QWORD *)(a2 + 8);
  result = 3221225488LL;
  v8 = a4 == 2211986;
  *a5 = 0;
  if ( v5 && *(_DWORD *)(v5 + 40) >= 0x27Cu )
  {
    if ( (*(_BYTE *)(v5 + 10) & 5) != 0 )
      v9 = *(PVOID *)(v5 + 24);
    else
      v9 = MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000010u);
    if ( v9 )
    {
      result = NtProcessLmHSvcIrp(v5, v9, a3, a2, v8);
      *a5 = 1;
    }
    else
    {
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b9d4  mov     [rsp+arg_0], rbx
0x14001b9d9  mov     [rsp+arg_8], rsi
0x14001b9de  push    rdi
0x14001b9df  sub     rsp, 30h
0x14001b9e3  mov     rdi, [rsp+38h+arg_20]
0x14001b9e8  xor     esi, esi
0x14001b9ea  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14001b9ee  cmp     r9d, 21C092h
0x14001b9f5  mov     rbx, rdx
0x14001b9f8  mov     eax, 0C0000010h
0x14001b9fd  setz    sil
0x14001ba01  mov     dword ptr [rdi], 0
0x14001ba07  test    rcx, rcx
0x14001ba0a  jz      short loc_14001BA5A
0x14001ba0c  cmp     dword ptr [rcx+28h], 27Ch
0x14001ba13  jb      short loc_14001BA5A
0x14001ba15  test    byte ptr [rcx+0Ah], 5
0x14001ba19  jnz     short loc_14001BA72
0x14001ba1b  xor     r9d, r9d; RequestedAddress
0x14001ba1e  mov     [rsp+38h+Priority], 40000010h; Priority
0x14001ba26  xor     edx, edx; AccessMode
0x14001ba28  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001ba30  lea     r8d, [r9+1]; CacheType
0x14001ba34  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001ba3b  nop     dword ptr [rax+rax+00h]
0x14001ba40  test    rax, rax
0x14001ba43  jz      short loc_14001BA6B
0x14001ba45  mov     r9, rbx
0x14001ba48  mov     [rsp+38h+BugCheckOnFailure], esi
0x14001ba4c  mov     rdx, rax
0x14001ba4f  call    NtProcessLmHSvcIrp
0x14001ba54  mov     dword ptr [rdi], 1
0x14001ba5a  mov     rbx, [rsp+38h+arg_0]
0x14001ba5f  mov     rsi, [rsp+38h+arg_8]
0x14001ba64  add     rsp, 30h
0x14001ba68  pop     rdi
0x14001ba69  retn
0x14001ba6b  mov     eax, 0C000009Ah
0x14001ba70  jmp     short loc_14001BA5A
0x14001ba72  mov     rax, [rcx+18h]
0x14001ba76  jmp     short loc_14001BA40
```
