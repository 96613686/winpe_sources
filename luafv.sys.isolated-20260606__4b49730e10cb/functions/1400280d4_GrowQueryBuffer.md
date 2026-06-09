# GrowQueryBuffer

- ea: `0x1400280d4`
- end: `0x140028146`
- name: `GrowQueryBuffer`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140028008`
- `0x140028c84`
- `0x140028e5c`
- `0x140028f24`
- `0x140029784`
- `0x140029b30`

## callees

- `0x14001b6a0`
- `0x14001dd90`
- `0x1400280d4`

## pseudocode

```c
__int64 __fastcall GrowQueryBuffer(unsigned int a1)
{
  unsigned int v2; // edx
  __int64 result; // rax

  if ( QueryBuffer )
    LuafvFreePool((__int64)QueryBuffer);
  v2 = a1 + 512;
  if ( a1 + 512 >= a1 )
  {
    QueryBufferLength = v2 & 0xFFFFFE00;
    QueryBuffer = LuafvAllocatePool(1, v2 & 0xFFFFFE00, 1);
    return QueryBuffer == 0 ? 0xC000009A : 0;
  }
  else
  {
    QueryBufferLength = -1;
    result = 3221225621LL;
    QueryBuffer = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400280d4  push    rbx
0x1400280d6  sub     rsp, 20h
0x1400280da  mov     ebx, ecx
0x1400280dc  mov     rcx, cs:QueryBuffer
0x1400280e3  test    rcx, rcx
0x1400280e6  jz      short loc_1400280ED
0x1400280e8  call    LuafvFreePool
0x1400280ed  lea     edx, [rbx+200h]
0x1400280f3  cmp     edx, ebx
0x1400280f5  jnb     short loc_140028113
0x1400280f7  mov     cs:QueryBufferLength, 0FFFFFFFFh
0x140028101  mov     eax, 0C0000095h
0x140028106  mov     cs:QueryBuffer, 0
0x140028111  jmp     short loc_14002813F
0x140028113  and     edx, 0FFFFFE00h
0x140028119  mov     r8b, 1
0x14002811c  mov     ecx, 1
0x140028121  mov     cs:QueryBufferLength, edx
0x140028127  call    LuafvAllocatePool
0x14002812c  mov     cs:QueryBuffer, rax
0x140028133  neg     rax
0x140028136  sbb     eax, eax
0x140028138  not     eax
0x14002813a  and     eax, 0C000009Ah
0x14002813f  add     rsp, 20h
0x140028143  pop     rbx
0x140028144  retn
```
