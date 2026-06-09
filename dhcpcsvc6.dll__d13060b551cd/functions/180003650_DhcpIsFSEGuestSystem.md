# DhcpIsFSEGuestSystem

- ea: `0x180003650`
- end: `0x18000368f`
- name: `DhcpIsFSEGuestSystem`
- size: `63`
- prototype: `_BOOL8()`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004870`
- `0x180004ad0`
- `0x180005040`
- `0x1800051b0`
- `0x180005270`
- `0x180005580`
- `0x180005640`
- `0x1800062f0`
- `0x180006770`
- `0x180006820`
- `0x180006cb0`

## callees

- `0x180003650`
- `0x180007338`
- `0x180007380`

## pseudocode

```c
_BOOL8 DhcpIsFSEGuestSystem()
{
  int v0; // eax
  __int64 v1; // rcx
  bool v2; // zf

  v0 = dword_18000F2A8;
  if ( !dword_18000F2A8 )
  {
    if ( !(unsigned int)DhcpIsContainerSystem()
      || (v2 = (unsigned int)DhcpIsFSEFlagEnabledInRegistry(v1) == 0, v0 = 1, v2) )
    {
      v0 = 2;
    }
    dword_18000F2A8 = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x180003650  sub     rsp, 28h
0x180003654  mov     eax, cs:dword_18000F2A8
0x18000365a  test    eax, eax
0x18000365c  jnz     short loc_180003680
0x18000365e  call    DhcpIsContainerSystem
0x180003663  test    eax, eax
0x180003665  jz      short loc_180003675
0x180003667  call    DhcpIsFSEFlagEnabledInRegistry
0x18000366c  test    eax, eax
0x18000366e  mov     eax, 1
0x180003673  jnz     short loc_18000367A
0x180003675  mov     eax, 2
0x18000367a  mov     cs:dword_18000F2A8, eax
0x180003680  xor     ecx, ecx
0x180003682  cmp     eax, 1
0x180003685  setz    cl
0x180003688  mov     eax, ecx
0x18000368a  add     rsp, 28h
0x18000368e  retn
```
