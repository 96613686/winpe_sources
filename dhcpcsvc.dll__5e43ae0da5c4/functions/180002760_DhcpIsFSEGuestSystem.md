# DhcpIsFSEGuestSystem

- ea: `0x180002760`
- end: `0x1800027a3`
- name: `DhcpIsFSEGuestSystem`
- size: `67`
- prototype: ``
- caller_count: `29`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001490`
- `0x180005ec0`
- `0x180006300`
- `0x180006790`
- `0x1800068b0`
- `0x180006c90`
- `0x180007dd0`
- `0x180008210`
- `0x180009c90`
- `0x180009d40`
- `0x18000a2d0`
- `0x18000a410`
- `0x18000a4d0`
- `0x18000ac50`
- `0x18000b360`
- `0x18000b590`
- `0x18000b7c0`
- `0x18000b9d0`
- `0x18000bcc0`
- `0x18000beb0`
- `0x18000bf80`
- `0x18000c110`
- `0x18000c2f0`
- `0x18000c400`
- `0x18000c7d0`
- `0x18000c990`
- `0x18000cc10`
- `0x18000cfe0`
- `0x18000d8e0`

## callees

- `0x180002760`
- `0x1800028f0`
- `0x180004070`

## pseudocode

```c
_BOOL8 DhcpIsFSEGuestSystem()
{
  int v0; // eax

  v0 = dword_18001E21C;
  if ( !dword_18001E21C )
  {
    if ( (unsigned int)DhcpIsContainerSystem() && (unsigned int)DhcpIsFSEFlagEnabledInRegistry() )
      v0 = 1;
    else
      v0 = 2;
    dword_18001E21C = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x180002760  sub     rsp, 28h
0x180002764  mov     eax, cs:dword_18001E21C
0x18000276a  test    eax, eax
0x18000276c  jz      short loc_18000277D
0x18000276e  xor     ecx, ecx
0x180002770  cmp     eax, 1
0x180002773  setz    cl
0x180002776  mov     eax, ecx
0x180002778  add     rsp, 28h
0x18000277c  retn
0x18000277d  call    DhcpIsContainerSystem
0x180002782  test    eax, eax
0x180002784  jz      short loc_18000279C
0x180002786  call    DhcpIsFSEFlagEnabledInRegistry
0x18000278b  test    eax, eax
0x18000278d  jz      short loc_18000279C
0x18000278f  mov     eax, 1
0x180002794  mov     cs:dword_18001E21C, eax
0x18000279a  jmp     short loc_18000276E
0x18000279c  mov     eax, 2
0x1800027a1  jmp     short loc_180002794
```
