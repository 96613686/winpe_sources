# CscStUtGenerateGuid

- ea: `0x14002b814`
- end: `0x14002b867`
- name: `CscStUtGenerateGuid`
- size: `83`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140055cc0`
- `0x140059edc`
- `0x14005fd08`

## callees

- `0x14002b814`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14002b820`
- `ntoskrnl!ExUuidCreate` at `0x14002b820`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002b847`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002b847`

## pseudocode

```c
__int64 __fastcall CscStUtGenerateGuid(UUID *Uuid)
{
  unsigned int v2; // edx
  __int64 result; // rax
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp+10h] BYREF

  while ( 1 )
  {
    v2 = ExUuidCreate(Uuid);
    if ( v2 != -1073741267 )
      break;
    Interval.QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  result = 0;
  if ( v2 != 1073872982 )
    return v2;
  return result;
}

```

## disassembly

```asm
0x14002b814  push    rbx
0x14002b816  sub     rsp, 20h
0x14002b81a  mov     rbx, rcx
0x14002b81d  mov     rcx, rbx; Uuid
0x14002b820  call    cs:__imp_ExUuidCreate
0x14002b827  nop     dword ptr [rax+rax+00h]
0x14002b82c  mov     edx, eax
0x14002b82e  cmp     eax, 0C000022Dh
0x14002b833  jnz     short loc_14002B855
0x14002b835  lea     r8, [rsp+28h+Interval]; Interval
0x14002b83a  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFF676980h
0x14002b843  xor     edx, edx; Alertable
0x14002b845  xor     ecx, ecx; WaitMode
0x14002b847  call    cs:__imp_KeDelayExecutionThread
0x14002b84e  nop     dword ptr [rax+rax+00h]
0x14002b853  jmp     short loc_14002B81D
0x14002b855  xor     eax, eax
0x14002b857  cmp     edx, 40020056h
0x14002b85d  cmovnz  eax, edx
0x14002b860  add     rsp, 20h
0x14002b864  pop     rbx
0x14002b865  retn
```
