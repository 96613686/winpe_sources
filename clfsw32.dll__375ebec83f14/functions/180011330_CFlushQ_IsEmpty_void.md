# CFlushQ::IsEmpty(void)

- ea: `0x180011330`
- end: `0x180011385`
- name: `?IsEmpty@CFlushQ@@QEAAHXZ`
- size: `85`
- prototype: `__int64 __fastcall(CFlushQ *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e534`
- `0x18000fa24`
- `0x180011cfc`
- `0x180014008`

## callees

- `0x180011330`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180011358`
- `ntdll!RtlLeaveCriticalSection` at `0x18001136b`
- `ntdll!RtlLeaveCriticalSection` at `0x180011358`
- `ntdll!RtlLeaveCriticalSection` at `0x18001136b`
- `ntdll!RtlEnterCriticalSection` at `0x180011344`
- `ntdll!RtlEnterCriticalSection` at `0x180011344`

## pseudocode

```c
__int64 __fastcall CFlushQ::IsEmpty(CFlushQ *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 16));
  if ( *(_DWORD *)this )
  {
    RtlLeaveCriticalSection(v1);
    return 0;
  }
  else
  {
    RtlLeaveCriticalSection(v1);
    return 1;
  }
}

```

## disassembly

```asm
0x180011330  mov     [rsp+arg_0], rbx
0x180011335  push    rdi
0x180011336  sub     rsp, 20h
0x18001133a  lea     rdi, [rcx+10h]
0x18001133e  mov     rbx, rcx
0x180011341  mov     rcx, rdi; CriticalSection
0x180011344  call    cs:__imp_RtlEnterCriticalSection
0x18001134b  nop     dword ptr [rax+rax+00h]
0x180011350  cmp     dword ptr [rbx], 0
0x180011353  mov     rcx, rdi; CriticalSection
0x180011356  jnz     short loc_18001136B
0x180011358  call    cs:__imp_RtlLeaveCriticalSection
0x18001135f  nop     dword ptr [rax+rax+00h]
0x180011364  mov     eax, 1
0x180011369  jmp     short loc_180011379
0x18001136b  call    cs:__imp_RtlLeaveCriticalSection
0x180011372  nop     dword ptr [rax+rax+00h]
0x180011377  xor     eax, eax
0x180011379  mov     rbx, [rsp+28h+arg_0]
0x18001137e  add     rsp, 20h
0x180011382  pop     rdi
0x180011383  retn
```
