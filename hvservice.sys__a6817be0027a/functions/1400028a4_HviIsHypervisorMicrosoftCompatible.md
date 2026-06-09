# HviIsHypervisorMicrosoftCompatible

- ea: `0x1400028a4`
- end: `0x1400028d9`
- name: `HviIsHypervisorMicrosoftCompatible`
- size: `53`
- prototype: `bool()`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400027e4`
- `0x140002824`

## callees

- `0x140002864`
- `0x1400028a4`

## pseudocode

```c
bool HviIsHypervisorMicrosoftCompatible()
{
  if ( (unsigned __int8)HviIsAnyHypervisorPresent() )
  {
    _RAX = 1073741825;
    __asm { cpuid }
  }
  else
  {
    LODWORD(_RAX) = 0;
  }
  return (_DWORD)_RAX == 824407624;
}

```

## disassembly

```asm
0x1400028a4  push    rbx
0x1400028a6  sub     rsp, 30h
0x1400028aa  xorps   xmm0, xmm0
0x1400028ad  movups  [rsp+38h+var_18], xmm0
0x1400028b2  call    HviIsAnyHypervisorPresent
0x1400028b7  test    al, al
0x1400028b9  jz      short loc_1400028C6
0x1400028bb  mov     eax, 40000001h
0x1400028c0  xor     ecx, ecx
0x1400028c2  cpuid
0x1400028c4  jmp     short loc_1400028CA
0x1400028c6  mov     eax, dword ptr [rsp+38h+var_18]
0x1400028ca  cmp     eax, 31237648h
0x1400028cf  setz    al
0x1400028d2  add     rsp, 30h
0x1400028d6  pop     rbx
0x1400028d7  retn
```
