# DrCheckCurrentProcessForServiceSid(void *)

- ea: `0x14002a4f8`
- end: `0x14002a52f`
- name: `?DrCheckCurrentProcessForServiceSid@@YAHPEAX@Z`
- size: `55`
- prototype: `_BOOL8 __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x140018ea4`
- `0x14002a1e0`
- `0x14002b088`
- `0x14002c54c`

## callees

- `0x14002a4f8`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x14002a50b`
- `ntoskrnl!RtlCheckTokenMembership` at `0x14002a50b`

## pseudocode

```c
_BOOL8 __fastcall DrCheckCurrentProcessForServiceSid(void *a1)
{
  char v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  return (int)RtlCheckTokenMembership(0, a1, &v2) >= 0 && v2 == 1;
}

```

## disassembly

```asm
0x14002a4f8  sub     rsp, 28h
0x14002a4fc  mov     rdx, rcx
0x14002a4ff  mov     [rsp+28h+arg_8], 0
0x14002a504  xor     ecx, ecx
0x14002a506  lea     r8, [rsp+28h+arg_8]
0x14002a50b  call    cs:__imp_RtlCheckTokenMembership
0x14002a512  nop     dword ptr [rax+rax+00h]
0x14002a517  test    eax, eax
0x14002a519  js      short loc_14002A527
0x14002a51b  xor     eax, eax
0x14002a51d  cmp     [rsp+28h+arg_8], 1
0x14002a522  setz    al
0x14002a525  jmp     short loc_14002A529
0x14002a527  xor     eax, eax
0x14002a529  add     rsp, 28h
0x14002a52d  retn
```
