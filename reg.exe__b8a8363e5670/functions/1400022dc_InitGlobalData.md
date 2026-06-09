# InitGlobalData

- ea: `0x1400022dc`
- end: `0x140002331`
- name: `InitGlobalData`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1400038f8`
- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005ef0`
- `0x14000672c`
- `0x1400073d4`
- `0x140008cbc`
- `0x14000957c`
- `0x140009c68`
- `0x140009f80`
- `0x14000a4e4`

## callees

- `0x140001cc6`
- `0x14000f0c0`

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
0x1400022dc  mov     [rsp+arg_0], rbx
0x1400022e1  push    rdi
0x1400022e2  sub     rsp, 20h
0x1400022e6  mov     rdi, rdx
0x1400022e9  mov     ebx, ecx
0x1400022eb  mov     rcx, rdi; void *
0x1400022ee  xor     edx, edx; Val
0x1400022f0  mov     r8d, 98h; Size
0x1400022f6  call    memset_0
0x1400022fb  mov     [rdi], ebx
0x1400022fd  lea     rcx, [rdi+3Ch]
0x140002301  neg     ebx
0x140002303  mov     qword ptr [rdi+8], 0FFFFFFFF80000002h
0x14000230b  mov     r8d, 3
0x140002311  lea     rdx, a0; "\\0"
0x140002318  sbb     eax, eax
0x14000231a  and     eax, 2
0x14000231d  dec     eax
0x14000231f  mov     [rdi+38h], eax
0x140002322  mov     rbx, [rsp+28h+arg_0]
0x140002327  add     rsp, 20h
0x14000232b  pop     rdi
0x14000232c  jmp     StringCopyW
```
