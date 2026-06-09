# MupiDereferenceUncHardeningPrefixEntry

- ea: `0x140018980`
- end: `0x1400189a8`
- name: `MupiDereferenceUncHardeningPrefixEntry`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140014d38`
- `0x140017f50`
- `0x140018570`
- `0x14001a920`

## callees

- `0x140018980`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018996`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018996`

## pseudocode

```c
void __fastcall MupiDereferenceUncHardeningPrefixEntry(volatile signed __int32 *a1)
{
  if ( _InterlockedExchangeAdd(a1 + 1, 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag((PVOID)a1, 0x4855754Du);
}

```

## disassembly

```asm
0x140018980  sub     rsp, 28h
0x140018984  or      eax, 0FFFFFFFFh
0x140018987  lock xadd [rcx+4], eax
0x14001898c  cmp     eax, 1
0x14001898f  jnz     short loc_1400189A2
0x140018991  mov     edx, 4855754Dh; Tag
0x140018996  call    cs:__imp_ExFreePoolWithTag
0x14001899d  nop     dword ptr [rax+rax+00h]
0x1400189a2  add     rsp, 28h
0x1400189a6  retn
```
