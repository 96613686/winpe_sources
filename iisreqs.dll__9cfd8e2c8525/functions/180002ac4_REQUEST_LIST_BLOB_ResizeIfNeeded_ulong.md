# REQUEST_LIST_BLOB::ResizeIfNeeded(ulong)

- ea: `0x180002ac4`
- end: `0x180002b68`
- name: `?ResizeIfNeeded@REQUEST_LIST_BLOB@@AEAAJK@Z`
- size: `164`
- prototype: `__int64 __fastcall(REQUEST_LIST_BLOB *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ac8`
- `0x180001bbc`
- `0x180001cb4`

## callees

- `0x180002ac4`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall REQUEST_LIST_BLOB::ResizeIfNeeded(REQUEST_LIST_BLOB *this, unsigned int a2)
{
  unsigned int v2; // r8d
  __int64 v3; // rbp
  __int64 *v4; // rsi
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rdi

  v2 = 0;
  v3 = a2;
  v4 = (__int64 *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
  {
    v6 = 200 * *((_DWORD *)this + 6);
    v7 = *((_QWORD *)this + 2);
    if ( !v6 )
      v6 = 200;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, v6, v4);
    v2 = result;
    if ( (int)result < 0 )
      return result;
    v9 = *((unsigned int *)this + 1);
    v10 = *v4;
    *(_DWORD *)this = v6;
    *(_DWORD *)(v9 + v10) = 16909060;
    *((_DWORD *)this + 1) += 4;
  }
  v11 = v3 + 4;
  if ( (unsigned int)(*(_DWORD *)this - *((_DWORD *)this + 1)) >= (unsigned __int64)(v3 + 4) )
    return v2;
  if ( v11 <= 0x2710 )
    LODWORD(v11) = 10000;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 2) + 32LL))(
             *((_QWORD *)this + 2),
             (unsigned int)(v11 + *(_DWORD *)this),
             *((unsigned int *)this + 1),
             v4);
  v2 = result;
  if ( (int)result >= 0 )
  {
    *(_DWORD *)this += v11;
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180002ac4  push    rbx
0x180002ac6  push    rbp
0x180002ac7  push    rsi
0x180002ac8  push    rdi
0x180002ac9  sub     rsp, 38h
0x180002acd  xor     r8d, r8d
0x180002ad0  mov     ebp, edx
0x180002ad2  lea     rsi, [rcx+8]
0x180002ad6  mov     rbx, rcx
0x180002ad9  cmp     [rsi], r8
0x180002adc  jnz     short loc_180002B1E
0x180002ade  imul    edi, [rcx+18h], 0C8h
0x180002ae5  mov     eax, 0C8h
0x180002aea  mov     rcx, [rcx+10h]
0x180002aee  mov     r8, rsi
0x180002af1  test    edi, edi
0x180002af3  cmovz   edi, eax
0x180002af6  mov     rax, [rcx]
0x180002af9  mov     edx, edi
0x180002afb  mov     rax, [rax+18h]
0x180002aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b04  mov     r8d, eax
0x180002b07  test    eax, eax
0x180002b09  js      short loc_180002B5F
0x180002b0b  mov     ecx, [rbx+4]
0x180002b0e  mov     rax, [rsi]
0x180002b11  mov     [rbx], edi
0x180002b13  mov     dword ptr [rcx+rax], 1020304h
0x180002b1a  add     dword ptr [rbx+4], 4
0x180002b1e  mov     edx, [rbx]
0x180002b20  lea     rdi, [rbp+4]
0x180002b24  mov     eax, edx
0x180002b26  sub     eax, [rbx+4]
0x180002b29  cmp     rax, rdi
0x180002b2c  jnb     short loc_180002B5C
0x180002b2e  mov     eax, 2710h
0x180002b33  cmp     rdi, rax
0x180002b36  ja      short loc_180002B3A
0x180002b38  mov     edi, eax
0x180002b3a  mov     rcx, [rbx+10h]
0x180002b3e  add     edx, edi
0x180002b40  mov     r8d, [rbx+4]
0x180002b44  mov     r9, rsi
0x180002b47  mov     rax, [rcx]
0x180002b4a  mov     rax, [rax+20h]
0x180002b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b53  mov     r8d, eax
0x180002b56  test    eax, eax
0x180002b58  js      short loc_180002B5F
0x180002b5a  add     [rbx], edi
0x180002b5c  mov     eax, r8d
0x180002b5f  add     rsp, 38h
0x180002b63  pop     rdi
0x180002b64  pop     rsi
0x180002b65  pop     rbp
0x180002b66  pop     rbx
0x180002b67  retn
```
