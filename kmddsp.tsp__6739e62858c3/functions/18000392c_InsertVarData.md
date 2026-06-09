# InsertVarData

- ea: `0x18000392c`
- end: `0x180003977`
- name: `InsertVarData`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003488`
- `0x180004fe0`
- `0x180005550`
- `0x1800058b0`
- `0x180006140`

## callees

- `0x18000392c`
- `0x180008091`

## pseudocode

```c
__int64 __fastcall InsertVarData(__int64 a1, unsigned int *a2, __int64 a3, unsigned int *a4)
{
  unsigned int v4; // edi
  __int64 result; // rax

  v4 = *a2;
  if ( *a2 )
  {
    memcpy_0((void *)(a3 + *(unsigned int *)(a3 + 8)), (const void *)(a1 + a2[1]), v4);
    *a4 = v4;
    result = *(unsigned int *)(a3 + 8);
    a4[1] = result;
    *(_DWORD *)(a3 + 8) += v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000392c  mov     [rsp+arg_0], rbx
0x180003931  mov     [rsp+arg_8], rsi
0x180003936  push    rdi
0x180003937  sub     rsp, 20h
0x18000393b  mov     edi, [rdx]
0x18000393d  mov     rsi, r9
0x180003940  mov     rbx, r8
0x180003943  test    edi, edi
0x180003945  jz      short loc_180003966
0x180003947  mov     edx, [rdx+4]
0x18000394a  mov     r8d, edi; Size
0x18000394d  add     rdx, rcx; Src
0x180003950  mov     ecx, [rbx+8]
0x180003953  add     rcx, rbx; void *
0x180003956  call    memcpy_0
0x18000395b  mov     [rsi], edi
0x18000395d  mov     eax, [rbx+8]
0x180003960  mov     [rsi+4], eax
0x180003963  add     [rbx+8], edi
0x180003966  mov     rbx, [rsp+28h+arg_0]
0x18000396b  mov     rsi, [rsp+28h+arg_8]
0x180003970  add     rsp, 20h
0x180003974  pop     rdi
0x180003975  retn
```
