# SmartNewPtrClear

- ea: `0x180018b28`
- end: `0x180018b5f`
- name: `SmartNewPtrClear`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800067e4`
- `0x18001bb30`
- `0x18001c4a0`
- `0x18001d680`
- `0x18001e1ec`
- `0x180021060`

## callees

- `0x180018b28`
- `0x180018b68`
- `0x18003d00e`

## pseudocode

```c
void *__fastcall SmartNewPtrClear(int a1, _WORD *a2)
{
  size_t v2; // rdi
  void *v3; // rax
  void *v4; // rbx

  v2 = a1;
  v3 = SmartNewPtr(a1, a2);
  v4 = v3;
  if ( v3 )
    memset_0(v3, 0, v2);
  return v4;
}

```

## disassembly

```asm
0x180018b28  mov     [rsp+arg_0], rbx
0x180018b2d  push    rdi
0x180018b2e  sub     rsp, 20h
0x180018b32  movsxd  rdi, ecx
0x180018b35  mov     ecx, edi
0x180018b37  call    SmartNewPtr
0x180018b3c  mov     rbx, rax
0x180018b3f  test    rax, rax
0x180018b42  jz      short loc_180018B51
0x180018b44  mov     r8, rdi; Size
0x180018b47  xor     edx, edx; Val
0x180018b49  mov     rcx, rax; void *
0x180018b4c  call    memset_0
0x180018b51  mov     rax, rbx
0x180018b54  mov     rbx, [rsp+28h+arg_0]
0x180018b59  add     rsp, 20h
0x180018b5d  pop     rdi
0x180018b5e  retn
```
