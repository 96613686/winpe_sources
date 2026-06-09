# MupiDereferenceUncHardeningConfigurationEntry

- ea: `0x140015760`
- end: `0x14001579a`
- name: `MupiDereferenceUncHardeningConfigurationEntry`
- size: `58`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140015660`
- `0x1400158f4`

## callees

- `0x140015760`
- `0x14001e910`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015787`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015787`

## pseudocode

```c
void __fastcall MupiDereferenceUncHardeningConfigurationEntry(volatile signed __int32 *P)
{
  if ( _InterlockedExchangeAdd(P + 1, 0xFFFFFFFF) == 1 )
  {
    RfsServerNameCleanup(P + 6);
    ExFreePoolWithTag((PVOID)P, 0x4855754Du);
  }
}

```

## disassembly

```asm
0x140015760  push    rbx
0x140015762  sub     rsp, 20h
0x140015766  mov     rbx, rcx
0x140015769  or      eax, 0FFFFFFFFh
0x14001576c  lock xadd [rcx+4], eax
0x140015771  cmp     eax, 1
0x140015774  jnz     short loc_140015793
0x140015776  add     rcx, 18h
0x14001577a  call    RfsServerNameCleanup
0x14001577f  mov     edx, 4855754Dh; Tag
0x140015784  mov     rcx, rbx; P
0x140015787  call    cs:__imp_ExFreePoolWithTag
0x14001578e  nop     dword ptr [rax+rax+00h]
0x140015793  add     rsp, 20h
0x140015797  pop     rbx
0x140015798  retn
```
