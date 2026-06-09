# ASN1BEREncLength

- ea: `0x180007e40`
- end: `0x180007ea3`
- name: `ASN1BEREncLength`
- size: `99`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180006aa0`
- `0x180006b80`
- `0x180006c50`
- `0x180006d00`
- `0x180006df0`
- `0x180006e80`
- `0x1800072a0`
- `0x180007310`
- `0x1800074e0`
- `0x1800075e0`
- `0x18000a070`
- `0x18000a160`

## callees

- `0x180007464`
- `0x180007c70`
- `0x180007e40`
- `0x180008658`

## pseudocode

```c
__int64 __fastcall ASN1BEREncLength(__int64 a1, unsigned int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx

  v4 = BERGetLength(a2, qword_18000C650, 4);
  v5 = v4 + a2;
  if ( (unsigned int)v5 < v4 || !(unsigned int)ASN1EncCheck(a1, v5) )
    return 0;
  BERPutLength(a1, a2, v4);
  return 1;
}

```

## disassembly

```asm
0x180007e40  mov     [rsp+arg_0], rbx
0x180007e45  mov     [rsp+arg_8], rsi
0x180007e4a  push    rdi
0x180007e4b  sub     rsp, 20h
0x180007e4f  mov     ebx, edx
0x180007e51  mov     rsi, rcx
0x180007e54  mov     ecx, ebx
0x180007e56  lea     rdx, qword_18000C650
0x180007e5d  mov     r8d, 4
0x180007e63  call    _BERGetLength
0x180007e68  mov     edi, eax
0x180007e6a  lea     edx, [rax+rbx]
0x180007e6d  cmp     edx, eax
0x180007e6f  jb      short loc_180007E91
0x180007e71  mov     rcx, rsi
0x180007e74  call    ASN1EncCheck
0x180007e79  test    eax, eax
0x180007e7b  jz      short loc_180007E91
0x180007e7d  mov     r8d, edi
0x180007e80  mov     edx, ebx
0x180007e82  mov     rcx, rsi
0x180007e85  call    _BERPutLength
0x180007e8a  mov     eax, 1
0x180007e8f  jmp     short loc_180007E93
0x180007e91  xor     eax, eax
0x180007e93  mov     rbx, [rsp+28h+arg_0]
0x180007e98  mov     rsi, [rsp+28h+arg_8]
0x180007e9d  add     rsp, 20h
0x180007ea1  pop     rdi
0x180007ea2  retn
```
