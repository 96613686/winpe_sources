# MupiDereferenceUncHardeningPrefixEntry

- ea: `0x140018930`
- end: `0x140018958`
- name: `MupiDereferenceUncHardeningPrefixEntry`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140014ce8`
- `0x140017f00`
- `0x140018520`
- `0x14001a8d0`

## callees

- `0x140018930`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018946`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018946`

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
0x140018930  sub     rsp, 28h
0x140018934  or      eax, 0FFFFFFFFh
0x140018937  lock xadd [rcx+4], eax
0x14001893c  cmp     eax, 1
0x14001893f  jnz     short loc_140018952
0x140018941  mov     edx, 4855754Dh; Tag
0x140018946  call    cs:__imp_ExFreePoolWithTag
0x14001894d  nop     dword ptr [rax+rax+00h]
0x140018952  add     rsp, 28h
0x140018956  retn
```
