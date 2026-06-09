# SupplicantAreExplicitCredsConfigured

- ea: `0x18001ae8c`
- end: `0x18001aeac`
- name: `SupplicantAreExplicitCredsConfigured`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002470`

## callees

- `0x18001ae8c`

## pseudocode

```c
__int64 __fastcall SupplicantAreExplicitCredsConfigured(__int64 a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 376);
  if ( (*(_DWORD *)(*(unsigned int *)(v1 + 16) + v1 + 20) & 2) == 0 )
    return 0;
  result = 1;
  if ( (*(_BYTE *)(v1 + 8) & 1) == 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001ae8c  mov     rdx, [rcx+178h]
0x18001ae93  mov     eax, [rdx+10h]
0x18001ae96  mov     ecx, [rax+rdx+14h]
0x18001ae9a  test    cl, 2
0x18001ae9d  jz      short loc_18001AEA9
0x18001ae9f  mov     eax, 1
0x18001aea4  test    [rdx+8], al
0x18001aea7  jnz     short locret_18001AEAB
0x18001aea9  xor     eax, eax
0x18001aeab  retn
```
