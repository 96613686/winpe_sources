# HviGetHypervisorFeatures

- ea: `0x140002824`
- end: `0x14000285e`
- name: `HviGetHypervisorFeatures`
- size: `58`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000fee8`
- `0x140015078`

## callees

- `0x140002824`
- `0x1400028a4`

## pseudocode

```c
__int64 HviGetHypervisorFeatures()
{
  __int64 result; // rax
  _DWORD *v1; // r10

  result = HviIsHypervisorMicrosoftCompatible();
  if ( (_BYTE)result )
  {
    _RAX = 1073741827;
    __asm { cpuid }
    *v1 = result;
    v1[1] = _RBX;
    v1[2] = _RCX;
    v1[3] = _RDX;
  }
  else
  {
    *(_QWORD *)v1 = 0;
    *((_QWORD *)v1 + 1) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002824  push    rbx
0x140002826  sub     rsp, 20h
0x14000282a  mov     r10, rcx
0x14000282d  call    HviIsHypervisorMicrosoftCompatible
0x140002832  xor     ecx, ecx
0x140002834  test    al, al
0x140002836  jz      short loc_140002850
0x140002838  mov     eax, 40000003h
0x14000283d  cpuid
0x14000283f  mov     [r10], eax
0x140002842  mov     [r10+4], ebx
0x140002846  mov     [r10+8], ecx
0x14000284a  mov     [r10+0Ch], edx
0x14000284e  jmp     short loc_140002857
0x140002850  mov     [r10], rcx
0x140002853  mov     [r10+8], rcx
0x140002857  add     rsp, 20h
0x14000285b  pop     rbx
0x14000285c  retn
```
