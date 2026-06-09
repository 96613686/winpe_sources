# MpRegpAllocSaveKeyContext

- ea: `0x1400338e8`
- end: `0x140033978`
- name: `MpRegpAllocSaveKeyContext`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008378`

## callees

- `0x140011610`
- `0x1400338e8`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033902`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033902`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocSaveKeyContext()
{
  char *v0; // rbx
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY result; // rax
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 1024;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 1024);
  ++*((_DWORD *)RegData + 261);
  result = ExpInterlockedPopEntrySList(v1);
  if ( result
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (result = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    result->Next = (struct _SLIST_ENTRY *)4254468;
    result[1].Next = 0;
    *((_QWORD *)&result[1].Next + 1) = 0;
    result[2].Next = 0;
    *((_QWORD *)&result->Next + 1) = MpRegpFreeSaveKeyContext;
    *((_QWORD *)&result[2].Next + 1) = 0;
    result[3].Next = 0;
    *((_QWORD *)&result[3].Next + 1) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400338e8  push    rbx
0x1400338ea  sub     rsp, 20h
0x1400338ee  mov     rbx, cs:RegData
0x1400338f5  add     rbx, 400h
0x1400338fc  mov     rcx, rbx; ListHead
0x1400338ff  inc     dword ptr [rbx+14h]
0x140033902  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033909  nop     dword ptr [rax+rax+00h]
0x14003390e  test    rax, rax
0x140033911  jnz     short loc_14003392F
0x140033913  mov     edx, [rbx+2Ch]
0x140033916  mov     rax, [rbx+30h]
0x14003391a  mov     r8d, [rbx+28h]
0x14003391e  mov     ecx, [rbx+24h]
0x140033921  inc     dword ptr [rbx+18h]
0x140033924  call    cs:__guard_dispatch_icall_fptr
0x14003392a  test    rax, rax
0x14003392d  jz      short loc_140033971
0x14003392f  mov     qword ptr [rax], 40EB04h
0x140033936  lea     rcx, MpRegpFreeSaveKeyContext
0x14003393d  mov     qword ptr [rax+10h], 0
0x140033945  mov     qword ptr [rax+18h], 0
0x14003394d  mov     qword ptr [rax+20h], 0
0x140033955  mov     [rax+8], rcx
0x140033959  mov     qword ptr [rax+28h], 0
0x140033961  mov     qword ptr [rax+30h], 0
0x140033969  mov     qword ptr [rax+38h], 0
0x140033971  add     rsp, 20h
0x140033975  pop     rbx
0x140033976  retn
```
