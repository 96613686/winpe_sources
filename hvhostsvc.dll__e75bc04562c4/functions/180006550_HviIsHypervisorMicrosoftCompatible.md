# HviIsHypervisorMicrosoftCompatible

- ea: `0x180006550`
- end: `0x180006584`
- name: `HviIsHypervisorMicrosoftCompatible`
- size: `52`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800064d0`

## callees

- `0x180006510`
- `0x180006550`

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
0x180006550  push    rbx
0x180006552  sub     rsp, 30h
0x180006556  xorps   xmm0, xmm0
0x180006559  movups  [rsp+38h+var_18], xmm0
0x18000655e  call    HviIsAnyHypervisorPresent
0x180006563  test    al, al
0x180006565  jz      short loc_180006572
0x180006567  mov     eax, 40000001h
0x18000656c  xor     ecx, ecx
0x18000656e  cpuid
0x180006570  jmp     short loc_180006576
0x180006572  mov     eax, dword ptr [rsp+38h+var_18]
0x180006576  cmp     eax, 31237648h
0x18000657b  setz    al
0x18000657e  add     rsp, 30h
0x180006582  pop     rbx
0x180006583  retn
```
