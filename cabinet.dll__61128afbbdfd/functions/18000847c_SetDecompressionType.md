# SetDecompressionType

- ea: `0x18000847c`
- end: `0x1800084e0`
- name: `SetDecompressionType`
- size: `100`
- prototype: `_BOOL8 __fastcall(__int16, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008264`
- `0x1800083c0`

## callees

- `0x18000847c`
- `0x1800084e8`
- `0x1800088c0`

## pseudocode

```c
_BOOL8 __fastcall SetDecompressionType(__int16 a1, __int64 *a2)
{
  __int64 v5; // rax

  if ( a1 == *((_WORD *)a2 + 133) )
    return 1;
  if ( (unsigned int)MDIDestroyDecompressionGlobal(a2) )
  {
    *((_WORD *)a2 + 133) = a1;
    return (unsigned int)MDICreateDecompressionGlobal(a2) != 0;
  }
  else
  {
    v5 = *a2;
    *(_QWORD *)v5 = 7;
    *(_DWORD *)(v5 + 8) = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x18000847c  mov     [rsp+arg_0], rbx
0x180008481  push    rdi
0x180008482  sub     rsp, 20h
0x180008486  mov     rbx, rdx
0x180008489  movzx   edi, cx
0x18000848c  cmp     cx, [rdx+10Ah]
0x180008493  jz      short loc_1800084D9
0x180008495  mov     rcx, rdx
0x180008498  call    MDIDestroyDecompressionGlobal
0x18000849d  test    eax, eax
0x18000849f  jz      short loc_1800084C4
0x1800084a1  mov     rcx, rbx
0x1800084a4  mov     [rbx+10Ah], di
0x1800084ab  call    MDICreateDecompressionGlobal
0x1800084b0  xor     ecx, ecx
0x1800084b2  test    eax, eax
0x1800084b4  setnz   cl
0x1800084b7  mov     eax, ecx
0x1800084b9  mov     rbx, [rsp+28h+arg_0]
0x1800084be  add     rsp, 20h
0x1800084c2  pop     rdi
0x1800084c3  retn
0x1800084c4  mov     rax, [rbx]
0x1800084c7  mov     qword ptr [rax], 7
0x1800084ce  mov     dword ptr [rax+8], 1
0x1800084d5  xor     eax, eax
0x1800084d7  jmp     short loc_1800084B9
0x1800084d9  mov     eax, 1
0x1800084de  jmp     short loc_1800084B9
```
