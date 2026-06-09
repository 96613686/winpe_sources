# DRR_UninitRoamingTokenSet

- ea: `0x18000d384`
- end: `0x18000d3c6`
- name: `DRR_UninitRoamingTokenSet`
- size: `66`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036c8`
- `0x180005c00`
- `0x180006230`

## callees

- `0x18000d34c`
- `0x18000d384`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3ae`

## pseudocode

```c
HLOCAL __fastcall DRR_UninitRoamingTokenSet(__int64 a1)
{
  __int64 i; // rdi
  HLOCAL result; // rax

  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
    DRR_SecureFreeRoamingToken(*(unsigned int **)(*(_QWORD *)a1 + 8 * i));
  result = LocalFree(*(HLOCAL *)a1);
  *(_QWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000d384  mov     [rsp+arg_0], rbx
0x18000d389  push    rdi
0x18000d38a  sub     rsp, 20h
0x18000d38e  xor     edi, edi
0x18000d390  mov     rbx, rcx
0x18000d393  cmp     [rcx+8], edi
0x18000d396  jbe     short loc_18000D3AB
0x18000d398  mov     rcx, [rbx]
0x18000d39b  mov     rcx, [rcx+rdi*8]
0x18000d39f  call    DRR_SecureFreeRoamingToken
0x18000d3a4  inc     edi
0x18000d3a6  cmp     edi, [rbx+8]
0x18000d3a9  jb      short loc_18000D398
0x18000d3ab  mov     rcx, [rbx]; hMem
0x18000d3ae  call    cs:__imp_LocalFree
0x18000d3b4  mov     qword ptr [rbx], 0
0x18000d3bb  mov     rbx, [rsp+28h+arg_0]
0x18000d3c0  add     rsp, 20h
0x18000d3c4  pop     rdi
0x18000d3c5  retn
```
