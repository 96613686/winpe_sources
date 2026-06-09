# DpspUpdateFeedback

- ea: `0x180001458`
- end: `0x18000148b`
- name: `DpspUpdateFeedback`
- size: `51`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004864`
- `0x180004de4`

## callees

- `0x180001458`

## pseudocode

```c
__int64 __fastcall DpspUpdateFeedback(__int64 a1, __int64 a2)
{
  if ( (*(_BYTE *)(a2 + 120) & 0x10) != 0 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 104), 0x800u);
  if ( (*(_BYTE *)(a2 + 120) & 0x20) != 0 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 104), 0x1000u);
  if ( (*(_BYTE *)(a2 + 120) & 0x40) != 0 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 104), 0x2000u);
  return 0;
}

```

## disassembly

```asm
0x180001458  test    byte ptr [rdx+78h], 10h
0x18000145c  jnz     short loc_18000146D
0x18000145e  test    byte ptr [rdx+78h], 20h
0x180001462  jnz     short loc_180001477
0x180001464  test    byte ptr [rdx+78h], 40h
0x180001468  jnz     short loc_180001481
0x18000146a  xor     eax, eax
0x18000146c  retn
0x18000146d  lock or dword ptr [rcx+68h], 800h
0x180001475  jmp     short loc_18000145E
0x180001477  lock or dword ptr [rcx+68h], 1000h
0x18000147f  jmp     short loc_180001464
0x180001481  lock or dword ptr [rcx+68h], 2000h
0x180001489  jmp     short loc_18000146A
```
