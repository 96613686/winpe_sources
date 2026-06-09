# StringAllocate

- ea: `0x1400093fc`
- end: `0x140009457`
- name: `StringAllocate`
- size: `91`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140008af4`
- `0x140008f9c`
- `0x140009bc4`
- `0x14000a4ec`

## callees

- `0x140008a70`
- `0x1400093fc`

## pseudocode

```c
__int64 __fastcall StringAllocate(__int64 a1, __int16 a2)
{
  __int16 v3; // di
  void *Memory; // rax
  __int64 result; // rax

  if ( a2 == -1 || !a1 )
    return 3221225485LL;
  v3 = a2 + 1;
  *(_WORD *)a1 = 0;
  Memory = DigestAllocateMemory((unsigned __int16)(a2 + 1));
  *(_QWORD *)(a1 + 8) = Memory;
  if ( Memory )
  {
    result = 0;
    *(_WORD *)(a1 + 2) = v3;
  }
  else
  {
    *(_WORD *)(a1 + 2) = 0;
    return 2148074240LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400093fc  mov     [rsp+arg_0], rbx
0x140009401  push    rdi
0x140009402  sub     rsp, 20h
0x140009406  mov     eax, 0FFFEh
0x14000940b  mov     rbx, rcx
0x14000940e  cmp     dx, ax
0x140009411  ja      short loc_140009446
0x140009413  test    rcx, rcx
0x140009416  jz      short loc_140009446
0x140009418  inc     dx
0x14000941b  xor     eax, eax
0x14000941d  movzx   edi, dx
0x140009420  mov     [rcx], ax
0x140009423  mov     ecx, edi; Size
0x140009425  call    DigestAllocateMemory
0x14000942a  mov     [rbx+8], rax
0x14000942e  test    rax, rax
0x140009431  jz      short loc_14000943B
0x140009433  xor     eax, eax
0x140009435  mov     [rbx+2], di
0x140009439  jmp     short loc_14000944B
0x14000943b  mov     [rbx+2], ax
0x14000943f  mov     eax, 80090300h
0x140009444  jmp     short loc_14000944B
0x140009446  mov     eax, 0C000000Dh
0x14000944b  mov     rbx, [rsp+28h+arg_0]
0x140009450  add     rsp, 20h
0x140009454  pop     rdi
0x140009455  retn
```
