# MpRegpAllocRenameKeyContext

- ea: `0x140033858`
- end: `0x1400338e8`
- name: `MpRegpAllocRenameKeyContext`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003937c`

## callees

- `0x140011610`
- `0x140033858`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033872`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033872`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocRenameKeyContext()
{
  char *v0; // rbx
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY result; // rax
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 896;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 896);
  ++*((_DWORD *)RegData + 229);
  result = ExpInterlockedPopEntrySList(v1);
  if ( result
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (result = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    result->Next = (struct _SLIST_ENTRY *)4254467;
    result[1].Next = 0;
    *((_QWORD *)&result[1].Next + 1) = 0;
    result[2].Next = 0;
    *((_QWORD *)&result->Next + 1) = MpRegpFreeRenameKeyContext;
    *((_QWORD *)&result[2].Next + 1) = 0;
    result[3].Next = 0;
    *((_QWORD *)&result[3].Next + 1) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140033858  push    rbx
0x14003385a  sub     rsp, 20h
0x14003385e  mov     rbx, cs:RegData
0x140033865  add     rbx, 380h
0x14003386c  mov     rcx, rbx; ListHead
0x14003386f  inc     dword ptr [rbx+14h]
0x140033872  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033879  nop     dword ptr [rax+rax+00h]
0x14003387e  test    rax, rax
0x140033881  jnz     short loc_14003389F
0x140033883  mov     edx, [rbx+2Ch]
0x140033886  mov     rax, [rbx+30h]
0x14003388a  mov     r8d, [rbx+28h]
0x14003388e  mov     ecx, [rbx+24h]
0x140033891  inc     dword ptr [rbx+18h]
0x140033894  call    cs:__guard_dispatch_icall_fptr
0x14003389a  test    rax, rax
0x14003389d  jz      short loc_1400338E1
0x14003389f  mov     qword ptr [rax], 40EB03h
0x1400338a6  lea     rcx, MpRegpFreeRenameKeyContext
0x1400338ad  mov     qword ptr [rax+10h], 0
0x1400338b5  mov     qword ptr [rax+18h], 0
0x1400338bd  mov     qword ptr [rax+20h], 0
0x1400338c5  mov     [rax+8], rcx
0x1400338c9  mov     qword ptr [rax+28h], 0
0x1400338d1  mov     qword ptr [rax+30h], 0
0x1400338d9  mov     qword ptr [rax+38h], 0
0x1400338e1  add     rsp, 20h
0x1400338e5  pop     rbx
0x1400338e6  retn
```
