# SupplicantIsUsingExplicitCreds

- ea: `0x18001c80c`
- end: `0x18001c830`
- name: `SupplicantIsUsingExplicitCreds`
- size: `36`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fa0`
- `0x18000a318`
- `0x180011abc`
- `0x180015f90`
- `0x18001b360`
- `0x18001ce44`
- `0x180024860`
- `0x180024c40`
- `0x180025dbc`
- `0x18002a22c`

## callees

- `0x18000abc0`
- `0x18001c80c`

## pseudocode

```c
_BOOL8 __fastcall SupplicantIsUsingExplicitCreds(__int64 a1)
{
  return *(_DWORD *)(a1 + 444) == 3 && !SupplicantIsDoingPLAP(a1);
}

```

## disassembly

```asm
0x18001c80c  sub     rsp, 28h
0x18001c810  cmp     dword ptr [rcx+1BCh], 3
0x18001c817  jnz     short loc_18001C829
0x18001c819  call    SupplicantIsDoingPLAP
0x18001c81e  test    eax, eax
0x18001c820  jnz     short loc_18001C829
0x18001c822  mov     eax, 1
0x18001c827  jmp     short loc_18001C82B
0x18001c829  xor     eax, eax
0x18001c82b  add     rsp, 28h
0x18001c82f  retn
```
