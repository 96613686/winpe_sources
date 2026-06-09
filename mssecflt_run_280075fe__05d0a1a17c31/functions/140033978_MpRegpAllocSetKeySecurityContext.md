# MpRegpAllocSetKeySecurityContext

- ea: `0x140033978`
- end: `0x140033a08`
- name: `MpRegpAllocSetKeySecurityContext`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008524`

## callees

- `0x140011610`
- `0x140033978`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033992`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033992`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocSetKeySecurityContext()
{
  char *v0; // rbx
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY result; // rax
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 1152;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 1152);
  ++*((_DWORD *)RegData + 293);
  result = ExpInterlockedPopEntrySList(v1);
  if ( result
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (result = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    result->Next = (struct _SLIST_ENTRY *)4254469;
    result[1].Next = 0;
    *((_QWORD *)&result[1].Next + 1) = 0;
    result[2].Next = 0;
    *((_QWORD *)&result->Next + 1) = MpRegpFreeSetKeySecurityContext;
    *((_QWORD *)&result[2].Next + 1) = 0;
    result[3].Next = 0;
    *((_QWORD *)&result[3].Next + 1) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140033978  push    rbx
0x14003397a  sub     rsp, 20h
0x14003397e  mov     rbx, cs:RegData
0x140033985  add     rbx, 480h
0x14003398c  mov     rcx, rbx; ListHead
0x14003398f  inc     dword ptr [rbx+14h]
0x140033992  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033999  nop     dword ptr [rax+rax+00h]
0x14003399e  test    rax, rax
0x1400339a1  jnz     short loc_1400339BF
0x1400339a3  mov     edx, [rbx+2Ch]
0x1400339a6  mov     rax, [rbx+30h]
0x1400339aa  mov     r8d, [rbx+28h]
0x1400339ae  mov     ecx, [rbx+24h]
0x1400339b1  inc     dword ptr [rbx+18h]
0x1400339b4  call    cs:__guard_dispatch_icall_fptr
0x1400339ba  test    rax, rax
0x1400339bd  jz      short loc_140033A01
0x1400339bf  mov     qword ptr [rax], 40EB05h
0x1400339c6  lea     rcx, MpRegpFreeSetKeySecurityContext
0x1400339cd  mov     qword ptr [rax+10h], 0
0x1400339d5  mov     qword ptr [rax+18h], 0
0x1400339dd  mov     qword ptr [rax+20h], 0
0x1400339e5  mov     [rax+8], rcx
0x1400339e9  mov     qword ptr [rax+28h], 0
0x1400339f1  mov     qword ptr [rax+30h], 0
0x1400339f9  mov     qword ptr [rax+38h], 0
0x140033a01  add     rsp, 20h
0x140033a05  pop     rbx
0x140033a06  retn
```
