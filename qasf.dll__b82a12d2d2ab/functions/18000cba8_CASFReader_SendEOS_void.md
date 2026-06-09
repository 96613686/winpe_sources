# CASFReader::SendEOS(void)

- ea: `0x18000cba8`
- end: `0x18000cbf4`
- name: `?SendEOS@CASFReader@@AEAAJXZ`
- size: `76`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c2a0`
- `0x18000c630`

## callees

- `0x18000cba8`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::SendEOS(CASFReader *this)
{
  __int64 v1; // rbx

  if ( !*((_DWORD *)this + 114) )
  {
    v1 = *((_QWORD *)this + 35);
    for ( *((_DWORD *)this + 114) = 1; v1; v1 = *(_QWORD *)(v1 + 8) )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 16) + 152LL))(*(_QWORD *)(v1 + 16));
  }
  return 0;
}

```

## disassembly

```asm
0x18000cba8  push    rbx
0x18000cbaa  sub     rsp, 20h
0x18000cbae  cmp     dword ptr [rcx+1C8h], 0
0x18000cbb5  jnz     short loc_18000CBEC
0x18000cbb7  mov     rbx, [rcx+118h]
0x18000cbbe  mov     dword ptr [rcx+1C8h], 1
0x18000cbc8  test    rbx, rbx
0x18000cbcb  jz      short loc_18000CBEC
0x18000cbcd  mov     rcx, [rbx+10h]
0x18000cbd1  mov     rax, [rcx]
0x18000cbd4  mov     rax, [rax+98h]
0x18000cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe0  mov     rax, [rbx+8]
0x18000cbe4  mov     rbx, rax
0x18000cbe7  test    rax, rax
0x18000cbea  jnz     short loc_18000CBCD
0x18000cbec  xor     eax, eax
0x18000cbee  add     rsp, 20h
0x18000cbf2  pop     rbx
0x18000cbf3  retn
```
