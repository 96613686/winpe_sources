# CxPlatPoolAlloc

- ea: `0x1400290b4`
- end: `0x1400290fd`
- name: `CxPlatPoolAlloc`
- size: `73`
- prototype: `PSLIST_ENTRY __fastcall(__int64)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x140005aa4`
- `0x140007b30`
- `0x140008268`
- `0x14000b850`
- `0x14000bad0`
- `0x14000bf30`
- `0x14000c440`
- `0x14000ca70`
- `0x14000d230`
- `0x14000d490`
- `0x14000d638`
- `0x14000fdb0`
- `0x140026f1c`
- `0x140029bb0`
- `0x14003a300`
- `0x14003ab74`
- `0x14003ade0`
- `0x14003b608`
- `0x14003ff2c`
- `0x1400410d0`

## callees

- `0x1400290b4`
- `0x14003c980`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400290c0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400290c0`

## pseudocode

```c
PSLIST_ENTRY __fastcall CxPlatPoolAlloc(__int64 a1)
{
  PSLIST_ENTRY result; // rax
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  ++*(_DWORD *)(a1 + 20);
  result = ExpInterlockedPopEntrySList((PSLIST_HEADER)a1);
  if ( result
    || (v3 = *(unsigned int *)(a1 + 44),
        v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(a1 + 48),
        v5 = *(unsigned int *)(a1 + 40),
        v6 = *(unsigned int *)(a1 + 36),
        ++*(_DWORD *)(a1 + 24),
        (result = (PSLIST_ENTRY)v4(v6, v3, v5, a1)) != 0) )
  {
    result->Next = (struct _SLIST_ENTRY *)a1;
    ++result;
  }
  return result;
}

```

## disassembly

```asm
0x1400290b4  push    rbx
0x1400290b6  sub     rsp, 30h
0x1400290ba  inc     dword ptr [rcx+14h]
0x1400290bd  mov     rbx, rcx
0x1400290c0  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400290c7  nop     dword ptr [rax+rax+00h]
0x1400290cc  test    rax, rax
0x1400290cf  jnz     short loc_1400290EF
0x1400290d1  mov     edx, [rbx+2Ch]
0x1400290d4  mov     r9, rbx
0x1400290d7  mov     rax, [rbx+30h]
0x1400290db  mov     r8d, [rbx+28h]
0x1400290df  mov     ecx, [rbx+24h]
0x1400290e2  inc     dword ptr [rbx+18h]
0x1400290e5  call    _guard_dispatch_icall
0x1400290ea  test    rax, rax
0x1400290ed  jz      short loc_1400290F6
0x1400290ef  mov     [rax], rbx
0x1400290f2  add     rax, 10h
0x1400290f6  add     rsp, 30h
0x1400290fa  pop     rbx
0x1400290fb  retn
```
