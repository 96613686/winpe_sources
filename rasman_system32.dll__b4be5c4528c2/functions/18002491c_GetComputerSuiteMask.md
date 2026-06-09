# GetComputerSuiteMask

- ea: `0x18002491c`
- end: `0x18002494b`
- name: `GetComputerSuiteMask`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020d30`

## callees

- `0x18002491c`
- `0x180024954`

## pseudocode

```c
__int64 __fastcall GetComputerSuiteMask(_DWORD *a1)
{
  unsigned int v1; // edx
  __int64 result; // rax

  v1 = 0;
  if ( dword_180031950 || (result = LoadSkuAndRole(), (v1 = result) == 0) )
  {
    *a1 = dword_180031920;
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x18002491c  push    rbx
0x18002491e  sub     rsp, 20h
0x180024922  xor     edx, edx
0x180024924  mov     rbx, rcx
0x180024927  cmp     cs:dword_180031950, edx
0x18002492d  jnz     short loc_18002493A
0x18002492f  call    LoadSkuAndRole
0x180024934  mov     edx, eax
0x180024936  test    eax, eax
0x180024938  jnz     short loc_180024944
0x18002493a  mov     eax, cs:dword_180031920
0x180024940  mov     [rbx], eax
0x180024942  mov     eax, edx
0x180024944  add     rsp, 20h
0x180024948  pop     rbx
0x180024949  retn
```
