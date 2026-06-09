# Decompress

- ea: `0x180006b68`
- end: `0x180006c16`
- name: `Decompress`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x180006b68`
- `0x180006c1c`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        int a11,
        int a12,
        int a13,
        int a14)
{
  __int64 result; // rax
  __int64 v18; // [rsp+48h] [rbp-50h]
  __int64 v19; // [rsp+50h] [rbp-48h]
  __int64 v20; // [rsp+58h] [rbp-40h]

  if ( !*(_DWORD *)(a1 + 32) )
  {
    result = DecompressBegin(a1, a2, a3, a4, a5, a6, a7, a8, a9, v18, v19, v20, a13, a14);
    if ( (_DWORD)result )
      return result;
    *(_DWORD *)(a1 + 32) = 0;
  }
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64, int, int))(a1 + 8))(a3, a4, a9, a10, a11, a12);
  return 0;
}

```

## disassembly

```asm
0x180006b68  push    rbx
0x180006b6a  push    rbp
0x180006b6b  push    rsi
0x180006b6c  push    rdi
0x180006b6d  sub     rsp, 78h
0x180006b71  cmp     dword ptr [rcx+20h], 0
0x180006b75  mov     rbp, r9
0x180006b78  mov     rsi, [rsp+98h+arg_40]
0x180006b80  mov     rdi, r8
0x180006b83  mov     rbx, rcx
0x180006b86  jnz     short loc_180006BDB
0x180006b88  mov     eax, [rsp+98h+arg_68]
0x180006b8f  mov     [rsp+98h+var_30], eax
0x180006b93  mov     eax, [rsp+98h+arg_60]
0x180006b9a  mov     [rsp+98h+var_38], eax
0x180006b9e  mov     eax, [rsp+98h+arg_38]
0x180006ba5  mov     [rsp+98h+var_58], rsi
0x180006baa  mov     [rsp+98h+var_60], eax
0x180006bae  mov     eax, [rsp+98h+arg_30]
0x180006bb5  mov     [rsp+98h+var_68], eax
0x180006bb9  mov     eax, [rsp+98h+arg_28]
0x180006bc0  mov     [rsp+98h+var_70], eax
0x180006bc4  mov     eax, [rsp+98h+arg_20]
0x180006bcb  mov     [rsp+98h+var_78], eax
0x180006bcf  call    DecompressBegin
0x180006bd4  test    eax, eax
0x180006bd6  jnz     short loc_180006C0D
0x180006bd8  mov     [rbx+20h], eax
0x180006bdb  mov     ecx, [rsp+98h+arg_58]
0x180006be2  mov     r8, rsi
0x180006be5  mov     r9, [rsp+98h+arg_48]
0x180006bed  mov     rdx, rbp
0x180006bf0  mov     rax, [rbx+8]
0x180006bf4  mov     [rsp+98h+var_70], ecx
0x180006bf8  mov     ecx, [rsp+98h+arg_50]
0x180006bff  mov     [rsp+98h+var_78], ecx
0x180006c03  mov     rcx, rdi
0x180006c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c0b  xor     eax, eax
0x180006c0d  add     rsp, 78h
0x180006c11  pop     rdi
0x180006c12  pop     rsi
0x180006c13  pop     rbp
0x180006c14  pop     rbx
0x180006c15  retn
```
