# DhcpIsWCOSSystem

- ea: `0x180002c00`
- end: `0x180002c4a`
- name: `DhcpIsWCOSSystem`
- size: `74`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800042d4`
- `0x180006300`
- `0x180009060`
- `0x180009584`
- `0x18000ece4`

## callees

- `0x180002c00`
- `0x180004240`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180002c1d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180002c1d`

## pseudocode

```c
_BOOL8 DhcpIsWCOSSystem()
{
  int v0; // eax

  v0 = dword_18001E224;
  if ( !dword_18001E224 )
  {
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled() || (unsigned int)DhcpIsXBOXSystem() )
    {
      v0 = 2;
      dword_18001E224 = 2;
    }
    else
    {
      v0 = 1;
      dword_18001E224 = 1;
    }
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x180002c00  sub     rsp, 28h
0x180002c04  mov     eax, cs:dword_18001E224
0x180002c0a  test    eax, eax
0x180002c0c  jz      short loc_180002C1D
0x180002c0e  xor     ecx, ecx
0x180002c10  cmp     eax, 1
0x180002c13  setz    cl
0x180002c16  mov     eax, ecx
0x180002c18  add     rsp, 28h
0x180002c1c  retn
0x180002c1d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180002c23  test    al, al
0x180002c25  jnz     short loc_180002C34
0x180002c27  mov     eax, 2
0x180002c2c  mov     cs:dword_18001E224, eax
0x180002c32  jmp     short loc_180002C0E
0x180002c34  call    DhcpIsXBOXSystem
0x180002c39  test    eax, eax
0x180002c3b  jnz     short loc_180002C27
0x180002c3d  mov     eax, 1
0x180002c42  mov     cs:dword_18001E224, eax
0x180002c48  jmp     short loc_180002C0E
```
