# CASFReader::StopPushing(void)

- ea: `0x18000d550`
- end: `0x18000d5c8`
- name: `?StopPushing@CASFReader@@AEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc60`
- `0x18000dea0`

## callees

- `0x180008764`
- `0x18000d550`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::StopPushing(CASFReader *this)
{
  __int64 i; // rdi
  __int64 j; // rbx

  for ( i = *((_QWORD *)this + 35); i; i = *(_QWORD *)(i + 8) )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(i + 16) + 160LL))(*(_QWORD *)(i + 16));
  CASFReader::CallStop(this);
  for ( j = *((_QWORD *)this + 35); j; j = *(_QWORD *)(j + 8) )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(j + 16) + 168LL))(*(_QWORD *)(j + 16));
  return 0;
}

```

## disassembly

```asm
0x18000d550  mov     [rsp+arg_0], rbx
0x18000d555  push    rdi
0x18000d556  sub     rsp, 20h
0x18000d55a  mov     rdi, [rcx+118h]
0x18000d561  mov     rbx, rcx
0x18000d564  test    rdi, rdi
0x18000d567  jz      short loc_18000D588
0x18000d569  mov     rcx, [rdi+10h]
0x18000d56d  mov     rax, [rcx]
0x18000d570  mov     rax, [rax+0A0h]
0x18000d577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57c  mov     rax, [rdi+8]
0x18000d580  mov     rdi, rax
0x18000d583  test    rax, rax
0x18000d586  jnz     short loc_18000D569
0x18000d588  mov     rcx, rbx; this
0x18000d58b  call    ?CallStop@CASFReader@@AEAAJXZ; CASFReader::CallStop(void)
0x18000d590  mov     rbx, [rbx+118h]
0x18000d597  test    rbx, rbx
0x18000d59a  jz      short loc_18000D5BB
0x18000d59c  mov     rcx, [rbx+10h]
0x18000d5a0  mov     rax, [rcx]
0x18000d5a3  mov     rax, [rax+0A8h]
0x18000d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5af  mov     rax, [rbx+8]
0x18000d5b3  mov     rbx, rax
0x18000d5b6  test    rax, rax
0x18000d5b9  jnz     short loc_18000D59C
0x18000d5bb  mov     rbx, [rsp+28h+arg_0]
0x18000d5c0  xor     eax, eax
0x18000d5c2  add     rsp, 20h
0x18000d5c6  pop     rdi
0x18000d5c7  retn
```
