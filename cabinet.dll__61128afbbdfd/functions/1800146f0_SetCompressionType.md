# SetCompressionType

- ea: `0x1800146f0`
- end: `0x18001473e`
- name: `SetCompressionType`
- size: `78`
- prototype: `__int64 __fastcall(__int16, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800014b4`
- `0x180002830`

## callees

- `0x180013f34`
- `0x180014088`
- `0x1800146f0`

## pseudocode

```c
__int64 __fastcall SetCompressionType(__int16 a1, __int64 a2)
{
  if ( !(unsigned int)MCIDestroyCompressionGlobal(a2) )
    return 0;
  *(_WORD *)(a2 + 676) = a1;
  if ( !(unsigned int)MCICreateCompressionGlobal(a2) )
  {
    *(_WORD *)(a2 + 676) = 15;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800146f0  mov     [rsp+arg_0], rbx
0x1800146f5  push    rdi
0x1800146f6  sub     rsp, 20h
0x1800146fa  movzx   edi, cx
0x1800146fd  mov     rbx, rdx
0x180014700  mov     rcx, rdx
0x180014703  call    MCIDestroyCompressionGlobal
0x180014708  test    eax, eax
0x18001470a  jnz     short loc_180014710
0x18001470c  xor     eax, eax
0x18001470e  jmp     short loc_180014733
0x180014710  mov     rcx, rbx
0x180014713  mov     [rbx+2A4h], di
0x18001471a  call    MCICreateCompressionGlobal
0x18001471f  test    eax, eax
0x180014721  jnz     short loc_18001472E
0x180014723  mov     word ptr [rbx+2A4h], 0Fh
0x18001472c  jmp     short loc_18001470C
0x18001472e  mov     eax, 1
0x180014733  mov     rbx, [rsp+28h+arg_0]
0x180014738  add     rsp, 20h
0x18001473c  pop     rdi
0x18001473d  retn
```
