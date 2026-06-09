# PsmpBeginTimeCriticalTask

- ea: `0x18000eff0`
- end: `0x18000f05d`
- name: `PsmpBeginTimeCriticalTask`
- size: `109`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000abf0`

## callees

- `0x18000eff0`
- `0x18000f0bc`
- `0x180017ca4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f014`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f014`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f035`

## pseudocode

```c
__int64 __fastcall PsmpBeginTimeCriticalTask(__int64 a1)
{
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_i(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids,
      *(_QWORD *)(a1 + 96));
  RtlAcquireSRWLockExclusive(a1 + 328);
  ++*(_DWORD *)(a1 + 168);
  PsmpApplyTimeCriticalTaskQuota((_DWORD *)a1);
  return RtlReleaseSRWLockExclusive(a1 + 328);
}

```

## disassembly

```asm
0x18000eff0  mov     [rsp+arg_0], rbx
0x18000eff5  push    rdi
0x18000eff6  sub     rsp, 20h
0x18000effa  mov     rdi, rcx
0x18000effd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f004  test    byte ptr [rcx+1Ch], 1
0x18000f008  jnz     short loc_18000F03C
0x18000f00a  lea     rbx, [rdi+148h]
0x18000f011  mov     rcx, rbx
0x18000f014  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f01a  inc     dword ptr [rdi+0A8h]
0x18000f020  mov     rcx, rdi
0x18000f023  call    PsmpApplyTimeCriticalTaskQuota
0x18000f028  mov     rcx, rbx
0x18000f02b  mov     rbx, [rsp+28h+arg_0]
0x18000f030  add     rsp, 20h
0x18000f034  pop     rdi
0x18000f035  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x18000f03c  cmp     byte ptr [rcx+19h], 4
0x18000f040  jb      short loc_18000F00A
0x18000f042  mov     r9, [rdi+60h]
0x18000f046  lea     r8, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x18000f04d  mov     rcx, [rcx+10h]
0x18000f051  mov     edx, 0Bh
0x18000f056  call    WPP_SF_i
0x18000f05b  jmp     short loc_18000F00A
```
