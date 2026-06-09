# WritePsz

- ea: `0x180016c44`
- end: `0x180016cb7`
- name: `WritePsz`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001bd8`

## callees

- `0x180016c44`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall WritePsz(
        __int64 a1,
        __int64 a2,
        unsigned int (__fastcall *a3)(__int64, __int64, _QWORD, int *, __int64),
        _DWORD *a4,
        __int64 a5)
{
  __int64 v6; // rdi
  __int64 result; // rax
  int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_BYTE *)(a2 + v6) );
  if ( v6 + 1 == a3(a1, a2, (unsigned int)(v6 + 1), &v8, a5) )
    return 1;
  a4[1] = v8;
  result = 0;
  *a4 = 6;
  a4[2] = 1;
  return result;
}

```

## disassembly

```asm
0x180016c44  mov     [rsp+arg_0], rbx
0x180016c49  push    rdi
0x180016c4a  sub     rsp, 30h
0x180016c4e  mov     rbx, r9
0x180016c51  mov     [rsp+38h+arg_10], 0
0x180016c59  mov     r10, r8
0x180016c5c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016c60  inc     rdi
0x180016c63  cmp     byte ptr [rdx+rdi], 0
0x180016c67  jnz     short loc_180016C60
0x180016c69  mov     rax, [rsp+38h+arg_20]
0x180016c6e  lea     r8d, [rdi+1]
0x180016c72  mov     [rsp+38h+var_18], rax
0x180016c77  lea     r9, [rsp+38h+arg_10]
0x180016c7c  mov     rax, r10
0x180016c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c84  mov     ecx, eax
0x180016c86  lea     rax, [rdi+1]
0x180016c8a  cmp     rax, rcx
0x180016c8d  jz      short loc_180016CA7
0x180016c8f  mov     eax, [rsp+38h+arg_10]
0x180016c93  mov     [rbx+4], eax
0x180016c96  xor     eax, eax
0x180016c98  mov     dword ptr [rbx], 6
0x180016c9e  mov     dword ptr [rbx+8], 1
0x180016ca5  jmp     short loc_180016CAC
0x180016ca7  mov     eax, 1
0x180016cac  mov     rbx, [rsp+38h+arg_0]
0x180016cb1  add     rsp, 30h
0x180016cb5  pop     rdi
0x180016cb6  retn
```
