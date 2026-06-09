# CNG_FreeProtectionDescriptor

- ea: `0x180008cfc`
- end: `0x180008d97`
- name: `CNG_FreeProtectionDescriptor`
- size: `155`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058b0`
- `0x180007ae0`
- `0x1800090e0`
- `0x18000962c`

## callees

- `0x180007b80`
- `0x180008cfc`
- `0x18000a770`

## pseudocode

```c
__int64 __fastcall CNG_FreeProtectionDescriptor(unsigned int *a1, int a2, __int64 a3)
{
  unsigned __int64 i; // rsi
  __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rbp
  __int64 v10; // rcx

  for ( i = 0; i < *a1; ++i )
  {
    v5 = *((_QWORD *)a1 + 1);
    v6 = 32 * i;
    if ( *(_DWORD *)(v5 + 32 * i) )
    {
      v7 = 0;
      do
      {
        v8 = *(_QWORD *)(v6 + v5 + 8);
        v9 = 32 * v7;
        if ( *(_DWORD *)(v8 + 32 * v7 + 24) == 1 )
        {
          v10 = *(_QWORD *)(v8 + v9 + 16);
          if ( v10 )
          {
            NCryptCloseKeyProtector(v10, a2, a3);
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + v6 + 8) + v9 + 24) = 0;
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + v6 + 8) + v9 + 16) = 0;
          }
        }
        v5 = *((_QWORD *)a1 + 1);
        ++v7;
      }
      while ( v7 < *(unsigned int *)(v5 + 32 * i) );
    }
  }
  MSCryptFree(a1);
  return 0;
}

```

## disassembly

```asm
0x180008cfc  push    rbx
0x180008cfe  push    rbp
0x180008cff  push    rsi
0x180008d00  push    rdi
0x180008d01  push    r14
0x180008d03  sub     rsp, 20h
0x180008d07  xor     esi, esi
0x180008d09  mov     rbx, rcx
0x180008d0c  cmp     [rcx], esi
0x180008d0e  jbe     short loc_180008D82
0x180008d10  mov     rcx, [rbx+8]
0x180008d14  mov     rdi, rsi
0x180008d17  shl     rdi, 5
0x180008d1b  cmp     dword ptr [rcx+rdi], 0
0x180008d1f  jbe     short loc_180008D78
0x180008d21  xor     r14d, r14d
0x180008d24  mov     rax, [rdi+rcx+8]
0x180008d29  mov     rbp, r14
0x180008d2c  shl     rbp, 5
0x180008d30  cmp     dword ptr [rax+rbp+18h], 1
0x180008d35  jnz     short loc_180008D69
0x180008d37  mov     rcx, [rax+rbp+10h]
0x180008d3c  test    rcx, rcx
0x180008d3f  jz      short loc_180008D69
0x180008d41  call    NCryptCloseKeyProtector
0x180008d46  mov     rax, [rbx+8]
0x180008d4a  mov     rcx, [rax+rdi+8]
0x180008d4f  mov     dword ptr [rcx+rbp+18h], 0
0x180008d57  mov     rax, [rbx+8]
0x180008d5b  mov     rcx, [rax+rdi+8]
0x180008d60  mov     qword ptr [rcx+rbp+10h], 0
0x180008d69  mov     rcx, [rbx+8]
0x180008d6d  inc     r14
0x180008d70  mov     eax, [rcx+rdi]
0x180008d73  cmp     r14, rax
0x180008d76  jb      short loc_180008D24
0x180008d78  mov     eax, [rbx]
0x180008d7a  inc     rsi
0x180008d7d  cmp     rsi, rax
0x180008d80  jb      short loc_180008D10
0x180008d82  mov     rcx, rbx
0x180008d85  call    MSCryptFree
0x180008d8a  xor     eax, eax
0x180008d8c  add     rsp, 20h
0x180008d90  pop     r14
0x180008d92  pop     rdi
0x180008d93  pop     rsi
0x180008d94  pop     rbp
0x180008d95  pop     rbx
0x180008d96  retn
```
