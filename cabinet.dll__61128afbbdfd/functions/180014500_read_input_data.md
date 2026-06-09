# read_input_data

- ea: `0x180014500`
- end: `0x180014560`
- name: `read_input_data`
- size: `96`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014384`

## callees

- `0x180014500`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall read_input_data(__int64 a1, void *a2)
{
  int v2; // edi
  __int64 result; // rax

  v2 = *(_DWORD *)(a1 + 2512);
  if ( v2 <= 0 )
    return 0;
  if ( v2 > 0x8000 )
    v2 = 0x8000;
  memcpy_0(a2, *(const void **)(a1 + 2504), (unsigned int)v2);
  *(_DWORD *)(a1 + 2512) -= v2;
  result = (unsigned int)v2;
  *(_QWORD *)(a1 + 2504) += (unsigned int)v2;
  return result;
}

```

## disassembly

```asm
0x180014500  mov     [rsp+arg_0], rbx
0x180014505  mov     [rsp+arg_8], rsi
0x18001450a  push    rdi
0x18001450b  sub     rsp, 20h
0x18001450f  mov     edi, [rcx+9D0h]
0x180014515  mov     rax, rdx
0x180014518  mov     rsi, rcx
0x18001451b  test    edi, edi
0x18001451d  jg      short loc_180014523
0x18001451f  xor     eax, eax
0x180014521  jmp     short loc_180014550
0x180014523  mov     rdx, [rsi+9C8h]; Src
0x18001452a  mov     ecx, 8000h
0x18001452f  cmp     edi, ecx
0x180014531  cmovg   edi, ecx
0x180014534  mov     rcx, rax; void *
0x180014537  mov     r8d, edi; Size
0x18001453a  mov     ebx, edi
0x18001453c  call    memcpy_0
0x180014541  sub     [rsi+9D0h], edi
0x180014547  mov     eax, edi
0x180014549  add     [rsi+9C8h], rbx
0x180014550  mov     rbx, [rsp+28h+arg_0]
0x180014555  mov     rsi, [rsp+28h+arg_8]
0x18001455a  add     rsp, 20h
0x18001455e  pop     rdi
0x18001455f  retn
```
