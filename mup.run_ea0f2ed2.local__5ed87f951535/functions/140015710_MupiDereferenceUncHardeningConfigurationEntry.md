# MupiDereferenceUncHardeningConfigurationEntry

- ea: `0x140015710`
- end: `0x14001574a`
- name: `MupiDereferenceUncHardeningConfigurationEntry`
- size: `58`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140015610`
- `0x1400158a4`

## callees

- `0x140015710`
- `0x14001e8c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015737`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015737`

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
0x140015710  push    rbx
0x140015712  sub     rsp, 20h
0x140015716  mov     rbx, rcx
0x140015719  or      eax, 0FFFFFFFFh
0x14001571c  lock xadd [rcx+4], eax
0x140015721  cmp     eax, 1
0x140015724  jnz     short loc_140015743
0x140015726  add     rcx, 18h
0x14001572a  call    RfsServerNameCleanup
0x14001572f  mov     edx, 4855754Dh; Tag
0x140015734  mov     rcx, rbx; P
0x140015737  call    cs:__imp_ExFreePoolWithTag
0x14001573e  nop     dword ptr [rax+rax+00h]
0x140015743  add     rsp, 20h
0x140015747  pop     rbx
0x140015748  retn
```
