# MpRegpAllocCreateKeyQueryValueKeyContext

- ea: `0x1400336f8`
- end: `0x140033764`
- name: `MpRegpAllocCreateKeyQueryValueKeyContext`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140038e64`
- `0x14003925c`

## callees

- `0x140011610`
- `0x1400336f8`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003370f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003370f`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocCreateKeyQueryValueKeyContext()
{
  char *v0; // rbx
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY result; // rax
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 128;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 128);
  ++*((_DWORD *)RegData + 37);
  result = ExpInterlockedPopEntrySList(v1);
  if ( result
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (result = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    LODWORD(result->Next) = 3730176;
    *((_QWORD *)&result->Next + 1) = MpRegpFreeCreateKeyQueryValueKeyContext;
    *((_QWORD *)&result[2].Next + 1) = 0;
    result[3].Next = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400336f8  push    rbx
0x1400336fa  sub     rsp, 20h
0x1400336fe  mov     rbx, cs:RegData
0x140033705  sub     rbx, 0FFFFFFFFFFFFFF80h
0x140033709  mov     rcx, rbx; ListHead
0x14003370c  inc     dword ptr [rbx+14h]
0x14003370f  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033716  nop     dword ptr [rax+rax+00h]
0x14003371b  test    rax, rax
0x14003371e  jnz     short loc_14003373C
0x140033720  mov     edx, [rbx+2Ch]
0x140033723  mov     rax, [rbx+30h]
0x140033727  mov     r8d, [rbx+28h]
0x14003372b  mov     ecx, [rbx+24h]
0x14003372e  inc     dword ptr [rbx+18h]
0x140033731  call    cs:__guard_dispatch_icall_fptr
0x140033737  test    rax, rax
0x14003373a  jz      short loc_14003375D
0x14003373c  lea     rcx, MpRegpFreeCreateKeyQueryValueKeyContext
0x140033743  mov     dword ptr [rax], 38EB00h
0x140033749  mov     [rax+8], rcx
0x14003374d  mov     qword ptr [rax+28h], 0
0x140033755  mov     qword ptr [rax+30h], 0
0x14003375d  add     rsp, 20h
0x140033761  pop     rbx
0x140033762  retn
```
