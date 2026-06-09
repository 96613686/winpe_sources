# RemoveFilterFromFilterHashtable

- ea: `0x1800418bc`
- end: `0x18004198b`
- name: `RemoveFilterFromFilterHashtable`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003b6c4`
- `0x18003be30`
- `0x180041698`

## callees

- `0x18000438c`
- `0x180007e38`
- `0x180011500`
- `0x180041738`
- `0x1800418bc`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18004191d`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004191d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004195c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004195c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800418e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800418e3`

## string_xrefs

- `0x180041933`: `RtlRemoveEntryHashTable`
- `0x18004196d`: `RemoveFilterFromFilterHashtable`

## pseudocode

```c
__int64 __fastcall RemoveFilterFromFilterHashtable(unsigned __int16 a1, __int64 a2)
{
  __int64 EntryFromFilterHashtable; // rbx
  __int64 v5; // rcx
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)gWfpGlobal + 25);
  EntryFromFilterHashtable = FindEntryFromFilterHashtable(a1, a2, &v7);
  if ( !EntryFromFilterHashtable )
  {
    if ( (unsigned __int8)RtlRemoveEntryHashTable(*((_QWORD *)gWfpGlobal + 40), v7, 0) )
      WfpMemFree(&v7);
    else
      EntryFromFilterHashtable = WfpReportSysErrorAsNtStatus(v5, "RtlRemoveEntryHashTable", 3221225473LL);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)gWfpGlobal + 25);
  if ( EntryFromFilterHashtable )
    WfpReportError(EntryFromFilterHashtable, "RemoveFilterFromFilterHashtable");
  return EntryFromFilterHashtable;
}

```

## disassembly

```asm
0x1800418bc  mov     [rsp+arg_0], rbx
0x1800418c1  push    rdi
0x1800418c2  sub     rsp, 20h
0x1800418c6  movzx   edi, cx
0x1800418c9  mov     [rsp+28h+arg_10], 0
0x1800418d2  mov     rcx, cs:gWfpGlobal
0x1800418d9  mov     rbx, rdx
0x1800418dc  add     rcx, 3E8h; lpCriticalSection
0x1800418e3  call    cs:__imp_EnterCriticalSection
0x1800418ea  nop     dword ptr [rax+rax+00h]
0x1800418ef  lea     r8, [rsp+28h+arg_10]
0x1800418f4  mov     rdx, rbx
0x1800418f7  movzx   ecx, di
0x1800418fa  call    FindEntryFromFilterHashtable
0x1800418ff  mov     rbx, rax
0x180041902  test    rax, rax
0x180041905  jnz     short loc_18004194E
0x180041907  mov     rcx, cs:gWfpGlobal
0x18004190e  xor     r8d, r8d
0x180041911  mov     rdx, [rsp+28h+arg_10]
0x180041916  mov     rcx, [rcx+140h]
0x18004191d  call    cs:__imp_RtlRemoveEntryHashTable
0x180041924  nop     dword ptr [rax+rax+00h]
0x180041929  test    al, al
0x18004192b  jnz     short loc_180041944
0x18004192d  mov     r8d, 0C0000001h
0x180041933  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x18004193a  call    WfpReportSysErrorAsNtStatus
0x18004193f  mov     rbx, rax
0x180041942  jmp     short loc_18004194E
0x180041944  lea     rcx, [rsp+28h+arg_10]
0x180041949  call    WfpMemFree
0x18004194e  mov     rcx, cs:gWfpGlobal
0x180041955  add     rcx, 3E8h; lpCriticalSection
0x18004195c  call    cs:__imp_LeaveCriticalSection
0x180041963  nop     dword ptr [rax+rax+00h]
0x180041968  test    rbx, rbx
0x18004196b  jz      short loc_18004197C
0x18004196d  lea     rdx, aRemovefilterfr; "RemoveFilterFromFilterHashtable"
0x180041974  mov     rcx, rbx
0x180041977  call    WfpReportError
0x18004197c  mov     rax, rbx
0x18004197f  mov     rbx, [rsp+28h+arg_0]
0x180041984  add     rsp, 20h
0x180041988  pop     rdi
0x180041989  retn
```
