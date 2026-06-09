# InitGlobalData

- ea: `0x140002234`
- end: `0x140002289`
- name: `InitGlobalData`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x14000375c`
- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x140005bac`
- `0x140006394`
- `0x140006f9c`
- `0x140008788`
- `0x140008fe8`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ec0`

## callees

- `0x140001cc6`
- `0x14000e450`

## pseudocode

```c
__int64 __fastcall InitGlobalData(int a1, _DWORD *a2)
{
  memset_0(a2, 0, 0x98u);
  *a2 = a1;
  *((_QWORD *)a2 + 1) = -2147483646;
  a2[14] = a1 != 0 ? 1 : -1;
  return StringCopyW((_WORD *)a2 + 30, L"\\0", 3);
}

```

## disassembly

```asm
0x140002234  mov     [rsp+arg_0], rbx
0x140002239  push    rdi
0x14000223a  sub     rsp, 20h
0x14000223e  mov     rdi, rdx
0x140002241  mov     ebx, ecx
0x140002243  mov     rcx, rdi; void *
0x140002246  xor     edx, edx; Val
0x140002248  mov     r8d, 98h; Size
0x14000224e  call    memset_0
0x140002253  mov     [rdi], ebx
0x140002255  lea     rcx, [rdi+3Ch]
0x140002259  neg     ebx
0x14000225b  mov     qword ptr [rdi+8], 0FFFFFFFF80000002h
0x140002263  mov     r8d, 3
0x140002269  lea     rdx, a0; "\\0"
0x140002270  sbb     eax, eax
0x140002272  and     eax, 2
0x140002275  dec     eax
0x140002277  mov     [rdi+38h], eax
0x14000227a  mov     rbx, [rsp+28h+arg_0]
0x14000227f  add     rsp, 20h
0x140002283  pop     rdi
0x140002284  jmp     StringCopyW
```
