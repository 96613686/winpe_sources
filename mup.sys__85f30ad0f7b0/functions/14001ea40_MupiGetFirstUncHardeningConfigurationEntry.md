# MupiGetFirstUncHardeningConfigurationEntry

- ea: `0x14001ea40`
- end: `0x14001ea51`
- name: `MupiGetFirstUncHardeningConfigurationEntry`
- size: `17`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015838`
- `0x1400158f4`

## callees

- `0x14001ea40`

## pseudocode

```c
__int64 __fastcall MupiGetFirstUncHardeningConfigurationEntry(_QWORD *a1)
{
  if ( (_QWORD *)*a1 == a1 )
    return 0;
  else
    return *a1 - 8LL;
}

```

## disassembly

```asm
0x14001ea40  mov     rax, [rcx]
0x14001ea43  cmp     rax, rcx
0x14001ea46  jz      short loc_14001EA4E
0x14001ea48  add     rax, 0FFFFFFFFFFFFFFF8h
0x14001ea4c  retn
0x14001ea4e  xor     eax, eax
0x14001ea50  retn
```
