# __except_validate_context_record

- ea: `0x180004ed8`
- end: `0x180004f0f`
- name: `__except_validate_context_record`
- size: `55`
- prototype: `struct _TEB *__fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029f4`
- `0x180003e28`
- `0x1800042e0`

## callees

- `0x180004ed8`

## pseudocode

```c
struct _TEB *__fastcall _except_validate_context_record(__int64 a1)
{
  struct _TEB *result; // rax
  PVOID v2; // rcx

  result = (struct _TEB *)_guard_check_icall_fptr[0];
  if ( _guard_check_icall_fptr[0] != guard_check_icall_nop )
  {
    result = NtCurrentTeb();
    v2 = *(PVOID *)(a1 + 152);
    if ( v2 < result->NtTib.StackLimit || v2 > result->NtTib.StackBase )
      __fastfail(0xDu);
  }
  return result;
}

```

## disassembly

```asm
0x180004ed8  mov     rax, cs:__guard_check_icall_fptr
0x180004edf  lea     rdx, _guard_check_icall_nop
0x180004ee6  cmp     rax, rdx
0x180004ee9  jz      short locret_180004F0E
0x180004eeb  mov     rax, gs:30h
0x180004ef4  mov     rcx, [rcx+98h]
0x180004efb  cmp     rcx, [rax+10h]
0x180004eff  jb      short loc_180004F07
0x180004f01  cmp     rcx, [rax+8]
0x180004f05  jbe     short locret_180004F0E
0x180004f07  mov     ecx, 0Dh
0x180004f0c  int     29h; Win8: RtlFailFast(ecx)
0x180004f0e  retn
```
