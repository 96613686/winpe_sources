# WDigestReferenceContext

- ea: `0x14000936c`
- end: `0x14000939e`
- name: `WDigestReferenceContext`
- size: `50`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140021520`
- `0x140021590`
- `0x140021790`
- `0x1400286c0`
- `0x140028790`
- `0x140028800`
- `0x140028e50`

## callees

- `0x14000936c`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x14000937a`
- `ntoskrnl!MmIsUserAddress` at `0x14000937a`

## pseudocode

```c
__int64 __fastcall WDigestReferenceContext(__int64 a1)
{
  if ( !a1 || (unsigned __int8)MmIsUserAddress() )
    return 3221225480LL;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
  return 0;
}

```

## disassembly

```asm
0x14000936c  push    rbx
0x14000936e  sub     rsp, 20h
0x140009372  mov     rbx, rcx
0x140009375  test    rcx, rcx
0x140009378  jz      short loc_140009392
0x14000937a  call    cs:__imp_MmIsUserAddress
0x140009381  nop     dword ptr [rax+rax+00h]
0x140009386  test    al, al
0x140009388  jnz     short loc_140009392
0x14000938a  lock inc dword ptr [rbx+18h]
0x14000938e  xor     eax, eax
0x140009390  jmp     short loc_140009397
0x140009392  mov     eax, 0C0000008h
0x140009397  add     rsp, 20h
0x14000939b  pop     rbx
0x14000939c  retn
```
