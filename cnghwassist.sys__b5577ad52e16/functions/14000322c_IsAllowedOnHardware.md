# IsAllowedOnHardware

- ea: `0x14000322c`
- end: `0x140003260`
- name: `IsAllowedOnHardware`
- size: `52`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003268`
- `0x140003520`
- `0x1400037ec`

## callees

- `0x14000322c`

## pseudocode

```c
char __fastcall IsAllowedOnHardware(_DWORD *a1)
{
  char v1; // dl

  v1 = 1;
  if ( (a1[23] & 1) != 0
    || (unsigned int)g_nSwThreadsRunning < *(_DWORD *)(*(_QWORD *)a1 + 36LL)
    || (unsigned __int64)(unsigned int)(a1[8] * *(_DWORD *)(*(_QWORD *)a1 + 52LL)) >> 8 > g_nBytesInQueues )
  {
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x14000322c  mov     eax, [rcx+5Ch]
0x14000322f  mov     dl, 1
0x140003231  test    dl, al
0x140003233  jnz     short loc_14000325B
0x140003235  mov     r8, [rcx]
0x140003238  mov     eax, [r8+24h]
0x14000323c  cmp     cs:g_nSwThreadsRunning, eax
0x140003242  jb      short loc_14000325B
0x140003244  mov     eax, [r8+34h]
0x140003248  imul    eax, [rcx+20h]
0x14000324c  mov     ecx, eax
0x14000324e  shr     rcx, 8
0x140003252  cmp     rcx, cs:g_nBytesInQueues
0x140003259  jbe     short loc_14000325D
0x14000325b  xor     dl, dl
0x14000325d  mov     al, dl
0x14000325f  retn
```
